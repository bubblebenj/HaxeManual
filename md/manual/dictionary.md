<a name="define-dollar-type" class="anch"></a>

##### `$type`
`$type` is a compile-time mechanism being called like a function, with a single argument. The compiler evaluates the argument expression and then outputs the type of that expression.

<a name="define-class-t" class="anch"></a>

##### `Class<T>`
This type is compatible with all class types, which means that all classes (not their instances) can be assigned to it. At compile-time, `Class<T>` can be considered to be the common base type of all class types. However, this relation is not reflected in generated code.

This type is useful when an API requires a value to be **a** class, but not a specific one. This applies to several methods of the [Haxe reflection API](std-reflection.md).

<a name="define-enum-t" class="anch"></a>

##### `Enum<T>`
This type is compatible with all enum types. At compile-time, `Enum<T>` can be considered to be the common base type of all enum types. However, this relation is not reflected in generated code.

<a name="define-null-t" class="anch"></a>

##### `Null<T>`
On static targets the types `Null<Int>`, `Null<Float>` and `Null<Bool>` can be used in order to allow `null` as a value. On dynamic targets this has no effect. `Null<T>` can also be used with other types in order to document that `null` is an allowed value.

<a name="define-ast" class="anch"></a>

##### Abstract Syntax Tree (AST)
The AST is the result of **parsing** Haxe code into a typed structure. This structure is exposed to macros through the types defined in the file `haxe/macro/Expr.hx` of the Haxe Standard Library.

<a name="define-accessor-method" class="anch"></a>

##### Accessor method
An **accessor method** (or short **accessor**) for a field named `field` of type `T` is a **getter** named `get_field` of type `Void->T` or a **setter** named `set_field` of type `T->T`.

<a name="define-bool" class="anch"></a>

##### Bool
Represents a value which can be either **true** or **false**.

<a name="define-class-field" class="anch"></a>

##### Class Field
A class field is a variable, property or method of a class which can either be static or non-static. Non-static fields are referred to as **member** fields, so we speak of e.g. a **static method** or a **member variable**.

<a name="define-compiler-flag" class="anch"></a>

##### Compiler Flag
A compiler flag is a configurable value which may influence the compilation process. Such a flag can be set by invoking the command line with `-D key=value` or just `-D key`, in which case the value defaults to `"1"`. The compiler also sets several flags internally to pass information between different compilation steps.

<a name="define-compound-type" class="anch"></a>

##### Compound Type
A compound type is a type which has sub-types. This includes any type with [type parameters](type-system-type-parameters.md) and the [function](types-function.md) type.

<a name="define-contravariance" class="anch"></a>

##### Contravariance
A [compound type](dictionary.md#define-compound-type) is considered contravariant if its component types can be assigned to less generic components, i.e. if they are only written, but never read.

<a name="define-covariance" class="anch"></a>

##### Covariance
A [compound type](dictionary.md#define-compound-type) is considered covariant if its component types can be assigned to less specific components, i.e. if they are only read, but never written.

<a name="define-default-value" class="anch"></a>

##### Default values

Basic types have the following default values on static targets:
* `Int`: `0`
* `Float`: `NaN` on Flash, `0.0` on other static targets
* `Bool`: `false`



<a name="define-definition" class="anch"></a>

##### Definition name
Definition description

<a name="define-dynamic-target" class="anch"></a>

##### Dynamic target
Dynamic targets are more lenient with their types and allow `null` values for basic types. They consist of JavaScript, PHP, Neko and Flash 6-8.

<a name="define-enumvalue" class="anch"></a>

##### EnumValue
EnumValue is a special type which unifies with all enum instances. It is used by the Haxe Standard Library to provide some operations for all enum instances, and can be employed in user-code accordingly in cases where an API requires **an** enum instance, but not a specific one.

<a name="define-expected-type" class="anch"></a>

##### Expected Type
Expected types occur when the type of an expression is known before that expression has been typed, e.g. because the expression is argument to a function call. They can influence typing of that expression through what is called [top-down inference](type-system-top-down-inference.md).

<a name="define-float" class="anch"></a>

##### Float
Represents a double-precision IEEE 64-bit floating point number.

<a name="define-generic-type-parameter" class="anch"></a>

##### Generic Type Parameter
A type parameter is said to be generic if its containing class or method is generic.

<a name="define-identifier" class="anch"></a>

##### Identifier
Haxe identifiers start with an underscore `_`, a dollar `$`, a lower-case character `a-z` or an upper-case character `A-Z`. After that, any combination and number of `_`, `A-Z`, `a-z` and `0-9` may follow.

Further limitations follow from the usage context, which are checked upon typing:
* Type names must start with an upper-case letter `A-Z` or an underscore `_`.
* Leading dollars are not allowed for any kind of [name](dictionary.md#define-name) (dollar-names are mostly used for [macro reification](macro-reification.md)).


<a name="define-int" class="anch"></a>

##### Int
Represents an integral number.

<a name="define-macro-context" class="anch"></a>

##### Macro Context
The macro context is the environment in which the macro is executed. Depending on the macro type, it can be considered to be a class being built or a function being typed. Contextual information can be obtained through the `haxe.macro.Context` API.

<a name="define-module" class="anch"></a>

##### Module
All Haxe code is organized in modules, which are addressed using paths. In essence, each .hx file represents a module which may contain several types. A type may be `private`, in which case only its containing module can access it.

<a name="define-name" class="anch"></a>

##### Name
A general name may refer to
* a type,
* a local variable,
* a local function or
* a field.


<a name="define-nullable" class="anch"></a>

##### nullable
A type in Haxe is considered **nullable** if `null` is a valid value for it.

<a name="define-physical-field" class="anch"></a>

##### Physical field
A field is considered to be **physical** if it is either
* a [variable](class-field-variable.md)
* a [property](class-field-property.md) with the read-access or write-access identifier being `default` or `null`
* a [property](class-field-property.md) with `:isVar` [metadata](lf-metadata.md)



<a name="define-private-type" class="anch"></a>

##### Private type
A type can be made private by using the `private` modifier. As a result, the type can only be directly accessed from within the [module](dictionary.md#define-module) it is defined in.

Private types, unlike public ones, do not become a member of their containing package.

<a name="define-read-access" class="anch"></a>

##### Read Access
A read access to a field occurs when a right-hand side [field access expression](expression-field-access.md) is used. This includes calls in the form of `obj.field()`, where `field` is accessed to be read.

<a name="define-static-extension" class="anch"></a>

##### Static Extension
A static extension allows pseudo-extending existing types without modifying their source. In Haxe this is achieved by declaring a static method with a first argument of the extending type and then bringing the defining class into context through `using`.

<a name="define-static-target" class="anch"></a>

##### Static target
Static targets employ their own type system where `null` is not a valid value for basic types. This is true for the Flash, C++, Java and C# targets.

<a name="define-string" class="anch"></a>

##### String
A String is a sequence of characters.

<a name="define-structural-subtyping" class="anch"></a>

##### Structural Subtyping
Structural subtyping defines an implicit relation between types that have the same structure.

<a name="define-type-path" class="anch"></a>

##### Type path
The (dot-)path to a type consists of the package, the module name and the type name. Its general form is `pack1.pack2.packN.ModuleName.TypeName`.

<a name="define-underlying-type" class="anch"></a>

##### Underlying Type
The underlying type of an abstract is the type which is used to represent said abstract at runtime. It is usually a concrete (i.e. non-abstract) type, but could be another abstract type as well.

<a name="define-unification" class="anch"></a>

##### Unification
Unification between two types A and B is a directional process which answers the question if A **can be assigned to** B. It may **mutate** either type if it is or has a [monomorph](types-monomorph.md).

<a name="define-void" class="anch"></a>

##### Void
Void denotes the absence of a type. It is used to express that something (usually a function) has no value.

<a name="define-write-access" class="anch"></a>

##### Write Access
A write access to a field occurs when a [field access expression](expression-field-access.md) is assigned a value in the form of `obj.field = value`. It may also occur in combination with [read access](dictionary.md#define-read-access) for special assignment operators such as `+=` in expressions like `obj.field += value`.