# Типы сообщений ошибок и предупреждений Kotlin

Предупреждения и ошибки, которые генерирует компилятор ``Kotlin`` часто нужно замаскировать, либо для того, чтобы они не мозолили глаза, либо просто потому, что логика программы нуждается именно в таком коде, который приводит к сообщению об ошибке или предупреждению.
Маскировка сообщений компилятора как в ``Java`` так и ``Kotlin`` происходит одинаково:

```kotlin
@Suppress("MESSAGE")
```
где ``"MESSAGE"`` - это тип сообщения.

Проблема в том, что узнать каким-то простым способом какой тип сообщения соответствует конкретному тексту часто оказывается невозможно. Подсказки ``Lint`` работают почему-то сильно не всегда, автодополнения нет, а разработчиками ``Kotlin`` эта информация почему-то нигде не опубликована.
Для облегчения поиска нужных типов сообщений я свел их вместе с текстом в одну таблицу. В случае возникновения необходимости замаскировать какое-то сообщение его можно легко найти в этой таблице и узнать какой тип нужно указать для ее подавления.
Возможно, кому-то эта информация пригодится.

<habracut/>

## Таблица сообщений и их типов

Тип|Сообщение
---|------
@delegate: annotations could be applied only to delegated properties|INAPPLICABLE_TARGET_PROPERTY_HAS_NO_DELEGATE
@field: annotations could be applied only to properties with backing fields|INAPPLICABLE_TARGET_PROPERTY_HAS_NO_BACKING_FIELD
@param: annotations could be applied only to primary constructor parameters|INAPPLICABLE_PARAM_TARGET
@receiver: annotations could be applied only to extension function or extension property declarations|INAPPLICABLE_RECEIVER_TARGET
A 'return' expression required in a function with a block body ('{...}')|NO_RETURN_IN_FUNCTION_WITH_BLOCK_BODY
A 'val'-property cannot have a setter|VAL_WITH_SETTER
A function is marked as tail-recursive but no tail calls are found|NO_TAIL_CALLS_FOUND
A function {0} with body cannot be abstract|ABSTRACT_FUNCTION_WITH_BODY
A receiver of type {0} is required|MISSING_RECEIVER
A supertype appears twice|SUPERTYPE_APPEARS_TWICE
A supertype cannot be dynamic|DYNAMIC_SUPERTYPE
A supertype cannot be nullable|NULLABLE_SUPERTYPE
A type annotation is required on a value parameter|VALUE_PARAMETER_WITH_NO_TYPE_ANNOTATION
Abstract function {0} in non-abstract class {1}|ABSTRACT_FUNCTION_IN_NON_ABSTRACT_CLASS
Abstract member cannot be accessed directly|ABSTRACT_SUPER_CALL
Abstract property in an interface cannot be private|PRIVATE_PROPERTY_IN_INTERFACE
Abstract property {0} in non-abstract class {1}|ABSTRACT_PROPERTY_IN_NON_ABSTRACT_CLASS
Accessor parameter name 'field' is shadowed by backing field variable|ACCESSOR_PARAMETER_NAME_SHADOWING
Ambiguous label|AMBIGUOUS_LABEL
An annotation parameter cannot be 'var'|VAR_ANNOTATION_PARAMETER
An annotation parameter cannot be nullable|NULLABLE_TYPE_OF_ANNOTATION_MEMBER
An annotation parameter must be a class literal (T::class)|ANNOTATION_PARAMETER_MUST_BE_KCLASS_LITERAL
An annotation parameter must be a compile-time constant|ANNOTATION_PARAMETER_MUST_BE_CONST
An anonymous function is not allowed to specify default values for its parameters|ANONYMOUS_FUNCTION_PARAMETER_WITH_DEFAULT_VALUE
An argument is already passed for this parameter|ARGUMENT_PASSED_TWICE
An enum annotation parameter must be a enum constant|ANNOTATION_PARAMETER_MUST_BE_ENUM_CONST
An interface cannot inherit from a class|INTERFACE_WITH_SUPERCLASS
An interface may not have a constructor|CONSTRUCTOR_IN_INTERFACE
An interface may not implement a method of 'Any'|METHOD_OF_ANY_IMPLEMENTED_IN_INTERFACE
An overriding function is not allowed to specify default values for its parameters|DEFAULT_VALUE_NOT_ALLOWED_IN_OVERRIDE
Annotation class cannot be instantiated|ANNOTATION_CLASS_CONSTRUCTOR_CALL
Annotation class cannot be instantiated|CALLABLE_REFERENCE_TO_ANNOTATION_CONSTRUCTOR
Annotation class cannot have supertypes|SUPERTYPES_FOR_ANNOTATION_CLASS
{0} annotations could be applied only to mutable properties|INAPPLICABLE_TARGET_PROPERTY_IMMUTABLE
{0} annotations could be applied only to property declarations|INAPPLICABLE_TARGET_ON_PROPERTY
Annotations on block-level expressions are being parsed differently depending on presence of a new line after them. Use new line if whole block-level expression must be annotated or wrap annotated expression in parentheses|ANNOTATIONS_ON_BLOCK_LEVEL_EXPRESSION_ON_THE_SAME_LINE
Anonymous functions with names are prohibited|ANONYMOUS_FUNCTION_WITH_NAME
Anonymous initializers are not allowed in interfaces|ANONYMOUS_INITIALIZER_IN_INTERFACE
Array class literal requires a type argument, please specify one in angle brackets|ARRAY_CLASS_LITERAL_REQUIRES_ARGUMENT
Assignment operators ambiguity: {0}|ASSIGN_OPERATOR_AMBIGUITY
Assignments are not expressions, and only expressions are allowed in this context|ASSIGNMENT_IN_EXPRESSION_CONTEXT
Body is not allowed for annotation class|ANNOTATION_CLASS_WITH_BODY
Bounds are not allowed on type alias parameters|BOUND_ON_TYPE_ALIAS_PARAMETER_NOT_ALLOWED
break and 'continue' are not allowed in 'when' statements. Consider using labels to continue/break from the outer loop|BREAK_OR_CONTINUE_IN_WHEN
break and 'continue' are only allowed inside a loop|BREAK_OR_CONTINUE_OUTSIDE_A_LOOP
break or 'continue' jumps across a function or a class boundary|BREAK_OR_CONTINUE_JUMPS_ACROSS_FUNCTION_BOUNDARY
Call to super is not allowed in enum constructor|DELEGATION_SUPER_CALL_IN_ENUM_CONSTRUCTOR
Cannot access {0} before superclass constructor has been called|INSTANCE_ACCESS_BEFORE_SUPER_CALL
Cannot access {0}: it is {1} in {2}|INVISIBLE_MEMBER
Cannot access {0}: it is {1} in {2}|INVISIBLE_REFERENCE
Cannot assign to {0}: the setter is {1} in {2}|INVISIBLE_SETTER
Cannot change access privilege {0} for {1} in {2}|CANNOT_CHANGE_ACCESS_PRIVILEGE
Cannot check for instance of erased type: {0}|CANNOT_CHECK_FOR_ERASED
Cannot choose among the following candidates without completing type inference: {0}|CANNOT_COMPLETE_RESOLVE
Cannot create an instance of an abstract class|CREATING_AN_INSTANCE_OF_ABSTRACT_CLASS
Cannot find a parameter with this name: {0}|NAMED_PARAMETER_NOT_FOUND
Cannot import {0}, functions and properties can be imported only from packages or objects|CANNOT_BE_IMPORTED
Cannot import-on-demand from object {0}|CANNOT_ALL_UNDER_IMPORT_FROM_SINGLETON
Cannot infer a type for this parameter. Please specify it explicitly.|CANNOT_INFER_PARAMETER_TYPE
Cannot infer visibility for {0}. Please specify it explicitly|CANNOT_INFER_VISIBILITY
Cannot inherit from a singleton|SINGLETON_IN_SUPERTYPE
Cannot use {0} as reified type parameter. Use a class instead.|TYPE_PARAMETER_AS_REIFIED
Cannot use {0} as reified type parameter|REIFIED_TYPE_FORBIDDEN_SUBSTITUTION
Cannot weaken access privilege {0} for {1} in {2}|CANNOT_WEAKEN_ACCESS_PRIVILEGE
Cant inline {0} here: it may contain non-local returns. Add crossinline modifier to parameter declaration {0}|NON_LOCAL_RETURN_NOT_ALLOWED
Captured values initialization is forbidden due to possible reassignment|CAPTURED_VAL_INITIALIZATION
{0} clashes with {1}: property types are incompatible|PROPERTY_TYPE_MISMATCH_ON_INHERITANCE
{0} clashes with {1}: property types do not match|VAR_TYPE_MISMATCH_ON_INHERITANCE
{0} clashes with {1}: return types are incompatible|RETURN_TYPE_MISMATCH_ON_INHERITANCE
Companion object of enum class {0} is uninitialized here|UNINITIALIZED_ENUM_COMPANION
compareTo() must return Int, but returns {0}|COMPARE_TO_TYPE_MISMATCH
Condition {0} is always {1}|SENSELESS_COMPARISON
Conditional branch result of type {0} is implicitly cast to {1}|IMPLICIT_CAST_TO_ANY
Conflicting declarations: {0}|REDECLARATION
Conflicting import, imported name {0} is ambiguous|CONFLICTING_IMPORT
Conflicting overloads: {0}|CONFLICTING_OVERLOADS
Conflicting projection in type alias expansion in intermediate type {0}|CONFLICTING_PROJECTION_IN_TYPEALIAS_EXPANSION
Const 'val' are only allowed on top level or in objects|CONST_VAL_NOT_TOP_LEVEL_OR_OBJECT
Const 'val' initializer should be a constant value|CONST_VAL_WITH_NON_CONST_INITIALIZER
Const 'val' should have an initializer|CONST_VAL_WITHOUT_INITIALIZER
Const 'val' should not have a delegate|CONST_VAL_WITH_DELEGATE
Const 'val' should not have a getter|CONST_VAL_WITH_GETTER
Const val has type {0}. Only primitives and String are allowed|TYPE_CANT_BE_USED_FOR_CONST_VAL
{0} construction is not yet supported in inline functions|NOT_YET_SUPPORTED_IN_INLINE
Constructor must be private in enum class|NON_PRIVATE_CONSTRUCTOR_IN_ENUM
Constructor must be private in sealed class|NON_PRIVATE_CONSTRUCTOR_IN_SEALED
Constructors are not allowed for objects|CONSTRUCTOR_IN_OBJECT
Data class inheritance from other classes is forbidden|DATA_CLASS_CANNOT_HAVE_CLASS_SUPERTYPES
Data class must have at least one primary constructor parameter|DATA_CLASS_WITHOUT_PARAMETERS
Data class primary constructor must have only property (val / var) parameters|DATA_CLASS_NOT_PROPERTY_PARAMETER
Declarations are not allowed in this position|DECLARATION_IN_ILLEGAL_CONTEXT
Default value of annotation parameter must be a compile-time constant|ANNOTATION_PARAMETER_DEFAULT_VALUE_MUST_BE_CONSTANT
Delegated properties are not allowed in interfaces|DELEGATED_PROPERTY_IN_INTERFACE
Delegated property cannot be abstract|ABSTRACT_DELEGATED_PROPERTY
Delegated property cannot have accessors with non-default implementations|ACCESSOR_FOR_DELEGATED_PROPERTY
Deprecated syntax. Use 'чч' instead of commas in when-condition for 'when' without argument|COMMA_IN_WHEN_CONDITION_WITHOUT_ARGUMENT
Destructured parameter {0} is never used|UNUSED_DESTRUCTURED_PARAMETER_ENTRY
Destructuring declaration initializer of type {1} must have a {0}() function|COMPONENT_FUNCTION_MISSING
Division by zero|DIVISION_BY_ZERO
{0} does not refer to a type parameter of {1}|NAME_IN_CONSTRAINT_IS_NOT_A_TYPE_PARAMETER
Duplicate label in when|DUPLICATE_LABEL_IN_WHEN
Dynamic type can not be used as an upper bound|DYNAMIC_UPPER_BOUND
Dynamic types are not allowed in this position|DYNAMIC_NOT_ALLOWED
else entry must be the last one in a when-expression|ELSE_MISPLACED_IN_WHEN
Elvis operator (?:) always returns the left operand of non-nullable type {0}|USELESS_ELVIS
Empty character literal|EMPTY_CHARACTER_LITERAL
Enum class cannot have type parameters|TYPE_PARAMETERS_IN_ENUM
Enum class cannot inherit from classes|CLASS_IN_SUPERTYPE_FOR_ENUM
Enum entry {0} is uninitialized here|UNINITIALIZED_ENUM_ENTRY
Enum has no default constructor, use 'entry(parameters)'|ENUM_ENTRY_SHOULD_BE_INITIALIZED
Enum types cannot be instantiated|ENUM_CLASS_CONSTRUCTOR_CALL
Expected a value of type {0}. Assignment operation is not an expression, so it does not return any value|ASSIGNMENT_TYPE_MISMATCH
Expected a value of type {0}|EXPECTED_TYPE_MISMATCH
Expected condition of type Boolean|EXPECTED_CONDITION
Expected parameter of type {0}|EXPECTED_PARAMETER_TYPE_MISMATCH
Expected performance impact of inlining {0} can be insignificant. Inlining works best for functions with lambda parameters|NOTHING_TO_INLINE
Expected {no parameters or one parameter of type or parameters of types} {1}|EXPECTED_PARAMETERS_NUMBER_MISMATCH
Explicit 'this' or 'super' call is required. There is no constructor in superclass that can be called without arguments|EXPLICIT_DELEGATION_CALL_REQUIRED
Explicitly qualified supertype is extended by another supertype {0}|QUALIFIED_SUPERTYPE_EXTENDED_BY_OTHER_SUPERTYPE
Expression expected, but a package name found|EXPRESSION_EXPECTED_PACKAGE_FOUND
Expression is inaccessible from a nested class {0}, use inner keyword to make the class inner|INACCESSIBLE_OUTER_CLASS_EXPRESSION
Expression under 'when' is never equal to null|SENSELESS_NULL_IN_WHEN
Expression {0}{1} cannot be invoked as a function. The function <OperatorNameConventions>() is not found|FUNCTION_EXPECTED
Extension function type can not be used as an upper bound|UPPER_BOUND_IS_EXTENSION_FUNCTION_TYPE
Extension function type is not allowed as supertypes|SUPERTYPE_IS_EXTENSION_FUNCTION_TYPE
Extension property cannot be initialized because it has no backing field|EXTENSION_PROPERTY_WITH_BACKING_FIELD
For-loop range must have an 'iterator()' method|ITERATOR_MISSING
Function declaration must have a name|FUNCTION_DECLARATION_WITH_NO_NAME
{0} function exposes its {2} parameter type{1}|EXPOSED_PARAMETER_TYPE
{0} function exposes its {2} return type{1}|EXPOSED_FUNCTION_RETURN_TYPE
Function invocation {0}({1}) expected|FUNCTION_CALL_EXPECTED
{0}() function returns {1}, but {2} is expected|COMPONENT_FUNCTION_RETURN_TYPE_MISMATCH
Function {0} generated for the data class conflicts with member of supertype {1}|DATA_CLASS_OVERRIDE_CONFLICT
Function {0} must have a body|NON_MEMBER_FUNCTION_NO_BODY
Function {0} should return Unit to be used by corresponding operator {1}|ASSIGNMENT_OPERATOR_SHOULD_RETURN_UNIT
Function {0} without a body must be abstract|NON_ABSTRACT_FUNCTION_WITH_NO_BODY
Function {0} without body cannot be private|PRIVATE_FUNCTION_WITH_NO_BODY
Function {0}() is ambiguous for this expression: {1}|COMPONENT_FUNCTION_AMBIGUITY
Functions inc(), dec() shouldn't return Unit to be used by operators ++, --|INC_DEC_SHOULD_NOT_RETURN_UNIT
Generic arguments of the base type must be specified|NO_GENERICS_IN_SUPERTYPE_SPECIFIER
{0} generic exposes its {2} parameter bound type{1}|EXPOSED_TYPE_PARAMETER_BOUND
Getter return type must be equal to the type of the property, i.e. {0}|WRONG_GETTER_RETURN_TYPE
Getter visibility must be the same as property visibility|GETTER_VISIBILITY_DIFFERS_FROM_PROPERTY_VISIBILITY
{0} has no access to {1}, so it cannot override it|CANNOT_OVERRIDE_INVISIBLE_MEMBER
hasNext() cannot be called on iterator() of type {0}|HAS_NEXT_MISSING
hasNext() is ambiguous for iterator() of type {0}|HAS_NEXT_FUNCTION_AMBIGUITY
{0} hides member of supertype {2} and needs override modifier|VIRTUAL_MEMBER_HIDDEN
If a type parameter has multiple constraints, they all need to be placed in the 'where' clause|MISPLACED_TYPE_PARAMETER_CONSTRAINTS
if must have both main and 'else' branches if used as an expression|INVALID_IF_AS_EXPRESSION
Illegal escape sequence|ILLEGAL_ESCAPE_SEQUENCE
Illegal escape: {0}|ILLEGAL_ESCAPE
Illegal usage of inline-parameter {0} in {1}. Add noinline modifier to the parameter declaration|USAGE_IS_NOT_INLINABLE
{0} implicitly overrides a final member {1} by delegation|OVERRIDING_FINAL_MEMBER_BY_DELEGATION
{0} in {1} is final and cannot be overridden|OVERRIDING_FINAL_MEMBER
Incompatible types: {0} and {1}|INCOMPATIBLE_TYPES
Incorrect character literal|INCORRECT_CHARACTER_LITERAL
Inferred type is a function type, but a non-function type {0} was expected. Use either = ... or '{ ... }, but not both.|TYPE_MISMATCH_DUE_TO_EQUALS_LAMBDA_IN_FUN
Inferred type {0} is an intersection, please specify the required type explicitly|IMPLICIT_INTERSECTION_TYPE
Infix call corresponds to a dot-qualified call {0}.{1}({2}) which is not allowed on a nullable receiver {0}. Use ?.-qualified call instead|UNSAFE_INFIX_CALL
infix modifier is inapplicable on this function: {0}|INAPPLICABLE_INFIX_MODIFIER
infix modifier is required on {0} in {1}|INFIX_MODIFIER_REQUIRED
{0} inherits conflicting members: {1}|CONFLICTING_INHERITED_MEMBERS
Initializer is not allowed here because this property has no backing field|PROPERTY_INITIALIZER_NO_BACKING_FIELD
Initializer required for destructuring declaration|INITIALIZER_REQUIRED_FOR_DESTRUCTURING_DECLARATION
Inline function {1} cannot be recursive|RECURSION_IN_INLINE
inline modifier is not allowed on virtual members. Only private or final members can be inlined|DECLARATION_CANT_BE_INLINED
Inline property cannot have backing field|INLINE_PROPERTY_WITH_BACKING_FIELD
Inline-parameter {0} of {1} must not be nullable. Add noinline modifier to the parameter declaration or make its type not nullable|NULLABLE_INLINE_PARAMETER
Interfaces cannot initialize supertypes|SUPERTYPE_INITIALIZED_IN_INTERFACE
Interfaces cannot use delegation|DELEGATION_IN_INTERFACE
Internal Error occurred while analyzing this expression:\n{0}|EXCEPTION_FROM_ANALYZER
Invalid @SinceKotlin annotation value (should be 'major.minor' or 'major.minor.patch')|ILLEGAL_SINCE_KOTLIN_VALUE
Invalid type of annotation member|INVALID_TYPE_OF_ANNOTATION_MEMBER
{0} is a final type, and thus a value of the type parameter is predetermined|FINAL_UPPER_BOUND
{0} is a member and an extension at the same time. References to such elements are not allowed|EXTENSION_IN_CLASS_REFERENCE_NOT_ALLOWED
{0} is an interface so it cannot be local. Try to use anonymous object or abstract class instead|LOCAL_INTERFACE_NOT_ALLOWED
{0} is deprecated. {1}|DEPRECATION
{0} is not an annotation class|NOT_AN_ANNOTATION_CLASS
{0} is not an expression, and only expressions are allowed here|EXPRESSION_EXPECTED
{0} is not an expression, it can not be used as a receiver for extension functions|SUPER_CANT_BE_EXTENSION_RECEIVER
{0} is not an expression, it can only be used on the left-hand side of a dot (.)|SUPER_IS_NOT_AN_EXPRESSION
is over enum entry is not allowed, use comparison instead|IS_ENUM_ENTRY
It may be not safe to use {0} as an argument for a reified type parameter. Use a non-generic type or * if possible|REIFIED_TYPE_UNSAFE_SUBSTITUTION
Lateinit is unnecessary: definitely initialized in constructors|UNNECESSARY_LATEINIT
lateinit modifier {0}|INAPPLICABLE_LATEINIT_MODIFIER
Left operand of elvis operator (?:) is a lambda expression|USELESS_ELVIS_ON_LAMBDA_EXPRESSION
Left-hand side of a callable reference cannot be a type parameter|CALLABLE_REFERENCE_LHS_NOT_A_CLASS
Left-hand side of a callable reference with a receiver parameter cannot be empty. Please specify the type of the receiver before '::' explicitly|CALLABLE_REFERENCE_TO_MEMBER_OR_EXTENSION_WITH_EMPTY_LHS
Local class cannot extend a sealed class|SEALED_SUPERTYPE_IN_LOCAL_CLASS
Local extension properties are not allowed|LOCAL_EXTENSION_PROPERTY
Local variables are not allowed to have delegates|LOCAL_VARIABLE_WITH_DELEGATE
Local variables are not allowed to have getters|LOCAL_VARIABLE_WITH_GETTER
Local variables are not allowed to have setters|LOCAL_VARIABLE_WITH_SETTER
Many supertypes available, please specify the one you mean in angle brackets, e.g. 'super<Foo>'|AMBIGUOUS_SUPER
{0} member exposes its {2} receiver type{1}|EXPOSED_RECEIVER_TYPE
Method iterator() is ambiguous for this expression: {0}|ITERATOR_AMBIGUITY
{0} method may be missing. None of the following functions will be called: {1}|DELEGATE_PD_METHOD_NONE_APPLICABLE
Missing {0} method on delegate of type {1}|DELEGATE_SPECIAL_FUNCTION_MISSING
Mixing named and positioned arguments is not allowed|MIXING_NAMED_AND_POSITIONED_ARGUMENTS
Modifier 'open' is redundant for abstract interface members|REDUNDANT_OPEN_IN_INTERFACE
{0} modifier is inapplicable. The reason is that {1}|INAPPLICABLE_MODIFIER
Modifier {0} is allowed only for function parameters of an inline function|ILLEGAL_INLINE_PARAMETER_MODIFIER
Modifier {0} is deprecated for {1}|DEPRECATED_MODIFIER_FOR_TARGET
Modifier {0} is deprecated in presence of {1}|DEPRECATED_MODIFIER_PAIR
Modifier {0} is deprecated inside {1}|DEPRECATED_MODIFIER_CONTAINING_DECLARATION
Modifier {0} is incompatible with {1}|INCOMPATIBLE_MODIFIERS
Modifier {0} is not applicable inside {1}|WRONG_MODIFIER_CONTAINING_DECLARATION
Modifier {0} is not applicable to {1}|WRONG_MODIFIER_TARGET
Modifier {0} is redundant because {1} is present|REDUNDANT_MODIFIER
Modifier {0} is redundant for {1}|REDUNDANT_MODIFIER_FOR_TARGET
More than one overridden descriptor declares a default value for {0}. As the compiler can not make sure these values agree, this is not allowed.|MULTIPLE_DEFAULTS_INHERITED_FROM_SUPERTYPES
More than one overridden descriptor declares a default value for {0}. As the compiler can not make sure these values agree, this is not allowed.|MULTIPLE_DEFAULTS_INHERITED_FROM_SUPERTYPES_WHEN_NO_EXPLICIT_OVERRIDE
Multiple vararg-parameters are prohibited|MULTIPLE_VARARG_PARAMETERS
{0} must be declared abstract or implement abstract base class member {1}|ABSTRACT_CLASS_MEMBER_NOT_IMPLEMENTED
{0} must be declared abstract or implement abstract member {1}|ABSTRACT_MEMBER_NOT_IMPLEMENTED
{0} must override {1} because it inherits many implementations of it|MANY_IMPL_MEMBER_NOT_IMPLEMENTED
{0} must override {1} because it inherits multiple interface methods of it|MANY_INTERFACES_MEMBER_NOT_IMPLEMENTED
{0} must return {1} but returns {2}|RESULT_TYPE_MISMATCH
Name shadowed: {0}|NAME_SHADOWING
Name {0}|INVALID_CHARACTERS
Named argument is not allowed for a parameter with an ambiguous name|NAME_FOR_AMBIGUOUS_PARAMETER
Named arguments are not allowed for {0}|NAMED_ARGUMENTS_NOT_ALLOWED
Named object {0} is a singleton and cannot be local. Try to use anonymous object instead|LOCAL_OBJECT_NOT_ALLOWED
Names of the parameter #{1} conflict in the following members of supertypes: {0}. This may cause problems when calling this function with named arguments.|DIFFERENT_NAMES_FOR_THE_SAME_PARAMETER_IN_SUPERTYPES
Names _, __, ___, ..., are reserved in Kotlin|UNDERSCORE_IS_RESERVED
Nested class is not allowed here, use 'inner' keyword to make the class inner|NESTED_CLASS_NOT_ALLOWED
Nested {0} accessed via instance reference|NESTED_CLASS_ACCESSED_VIA_INSTANCE_REFERENCE
Nested {0} should be qualified as {1}|NESTED_CLASS_SHOULD_BE_QUALIFIED
next() cannot be called on iterator() of type {0}|NEXT_MISSING
next() is ambiguous for iterator() of type {0}|NEXT_AMBIGUITY
No cast needed|USELESS_CAST
No get method providing array access|NO_GET_METHOD
No method 'equals(Any?): Boolean' available|EQUALS_MISSING
No receiver can be passed to this function or property|NO_RECEIVER_ALLOWED
No set method providing array access|NO_SET_METHOD
No supertypes are accessible in this context|SUPER_NOT_AVAILABLE
No type arguments or One type argument or {0,number,integer} type arguments expected for {1}|WRONG_NUMBER_OF_TYPE_ARGUMENTS
No type arguments or One type argument or {0,number,integer} type arguments expected. Use {1} if you dont want to pass type arguments|NO_TYPE_ARGUMENTS_ON_RHS
No value passed for parameter {0}|NO_VALUE_FOR_PARAMETER
Non-local returns are not allowed with inlining disabled|NON_LOCAL_RETURN_IN_DISABLED_INLINE
Non-null assertion (!!) is called on a lambda expression|NOT_NULL_ASSERTION_ON_LAMBDA_EXPRESSION
Non-null type is checked for instance of nullable type|USELESS_NULLABLE_CHECK
Non-private inline function cannot access members of private classes: {0}|PRIVATE_CLASS_MEMBER_FROM_INLINE
None of the following functions can be called with the arguments supplied: {0}|NONE_APPLICABLE
None of the hasNext() functions is applicable for iterator() of type {0}|HAS_NEXT_FUNCTION_NONE_APPLICABLE
None of the next() functions is applicable for iterator() of type {0}|NEXT_NONE_APPLICABLE
Not a class|NOT_A_CLASS
Not an immediate supertype|NOT_A_SUPERTYPE
Not nullable value required to call {0}() function of destructuring declaration initializer|COMPONENT_FUNCTION_ON_NULLABLE
Not nullable value required to call an 'iterator()' method on for-loop range|ITERATOR_ON_NULLABLE
Nothing property type can't be specified with type alias|ABBREVIATED_NOTHING_PROPERTY_TYPE
Nothing property type needs to be specified explicitly|IMPLICIT_NOTHING_PROPERTY_TYPE
Nothing return type can't be specified with type alias|ABBREVIATED_NOTHING_RETURN_TYPE
Nothing return type needs to be specified explicitly|IMPLICIT_NOTHING_RETURN_TYPE
Null can not be a value of a non-null type {0}|NULL_FOR_NONNULL_TYPE
{0} on catch parameter is not allowed|VAL_OR_VAR_ON_CATCH_PARAMETER
{0} on function parameter is not allowed|VAL_OR_VAR_ON_FUN_PARAMETER
{0} on loop parameter is not allowed|VAL_OR_VAR_ON_LOOP_PARAMETER
{0} on secondary constructor parameter is not allowed|VAL_OR_VAR_ON_SECONDARY_CONSTRUCTOR_PARAMETER
Only 'const val' can be used in constant expressions|NON_CONST_VAL_USED_IN_CONSTANT_EXPRESSION
Only classes and interfaces may serve as supertypes|SUPERTYPE_NOT_A_CLASS_OR_INTERFACE
Only classes are allowed on the left hand side of a class literal|CLASS_LITERAL_LHS_NOT_A_CLASS
Only interfaces can be delegated to|DELEGATION_NOT_TO_INTERFACE
Only one class may appear in a supertype list|MANY_CLASSES_IN_SUPERTYPE_LIST
Only one companion object is allowed per class|MANY_COMPANION_OBJECTS
Only one lambda expression is allowed outside a parenthesized argument list|MANY_LAMBDA_EXPRESSION_ARGUMENTS
Only one of the upper bounds can be a class|ONLY_ONE_CLASS_BOUND_ALLOWED
Only safe (?.) or non-null asserted (!!.) calls are allowed on a nullable receiver of type {0}|UNSAFE_CALL
Only type parameters of inline functions can be reified|REIFIED_TYPE_PARAMETER_NO_INLINE
open has no effect in a final class|NON_FINAL_MEMBER_IN_FINAL_CLASS
open has no effect in an object|NON_FINAL_MEMBER_IN_OBJECT
operator modifier is inapplicable on this function: {0}|INAPPLICABLE_OPERATOR_MODIFIER
operator modifier is required on {0} in {1}|OPERATOR_MODIFIER_REQUIRED
Operator {0} cannot be applied to {1} and {2}|EQUALITY_NOT_APPLICABLE
Out-projected type {1} prohibits the use of {0}|MEMBER_PROJECTED_OUT
Overload resolution ambiguity on method {0}: {1}|DELEGATE_SPECIAL_FUNCTION_AMBIGUITY
Overload resolution ambiguity: {0}|OVERLOAD_RESOLUTION_AMBIGUITY
Override by a function with reified type parameter|REIFIED_TYPE_PARAMETER_IN_OVERRIDE
Override by an inline function|OVERRIDE_BY_INLINE
{0} overrides nothing|NOTHING_TO_OVERRIDE
Packages cannot be imported|PACKAGE_CANNOT_BE_IMPORTED
Parameter {0} is never used|UNUSED_PARAMETER
Parameter {0} is uninitialized here|UNINITIALIZED_PARAMETER
Passing value as a vararg is only allowed inside a parenthesized argument list|VARARG_OUTSIDE_PARENTHESES
Please specify constructor invocation; classifier {0} does not have a companion object|NO_COMPANION_OBJECT
Primary constructor call expected|PRIMARY_CONSTRUCTOR_DELEGATION_CALL_EXPECTED
Primary constructor required for data class|PRIMARY_CONSTRUCTOR_REQUIRED_FOR_DATA_CLASS
Primary constructor vararg parameters are forbidden for data classes|DATA_CLASS_VARARG_PARAMETER
Private setters are not allowed for abstract properties|PRIVATE_SETTER_FOR_ABSTRACT_PROPERTY
Private setters are not allowed for open properties|PRIVATE_SETTER_FOR_OPEN_PROPERTY
Projection is conflicting with variance of the corresponding type parameter of {0}. Remove the projection or replace it with *|CONFLICTING_PROJECTION
Projection is redundant: the corresponding type parameter of {0} has the same variance|REDUNDANT_PROJECTION
Projections are not allowed for immediate arguments of a supertype|PROJECTION_IN_IMMEDIATE_ARGUMENT_TO_SUPERTYPE
Projections are not allowed on type arguments of functions and properties|PROJECTION_ON_NON_CLASS_TYPE_ARGUMENT
Property delegate must have a {0} method. None of the following functions is suitable: {1}|DELEGATE_SPECIAL_FUNCTION_NONE_APPLICABLE
{0} property exposes its {2} type{1}|EXPOSED_PROPERTY_TYPE
Property in an interface cannot have a backing field|BACKING_FIELD_IN_INTERFACE
Property initializers are not allowed in interfaces|PROPERTY_INITIALIZER_IN_INTERFACE
Property must be initialized or be abstract|MUST_BE_INITIALIZED_OR_BE_ABSTRACT
Property must be initialized|MUST_BE_INITIALIZED
Property with getter implementation cannot be abstract|ABSTRACT_PROPERTY_WITH_GETTER
Property with initializer cannot be abstract|ABSTRACT_PROPERTY_WITH_INITIALIZER
Property with setter implementation cannot be abstract|ABSTRACT_PROPERTY_WITH_SETTER
Protected constructor {0} from other classes can only be used in super-call|PROTECTED_CONSTRUCTOR_NOT_IN_SUPER_CALL
Public-API inline function cannot access non-public-API {0}|NON_PUBLIC_CALL_FROM_PUBLIC_INLINE
Recursive call is not a tail call|NON_TAIL_RECURSIVE_CALL
Recursive type alias in expansion: {0}|RECURSIVE_TYPEALIAS_EXPANSION
Redeclaration: {0}|PACKAGE_OR_CLASSIFIER_REDECLARATION
Redundant '?'|REDUNDANT_NULLABLE
Redundant annotation target {0}|REDUNDANT_ANNOTATION_TARGET
Reference has a nullable type {0}, use explicit ?.invoke() to make a function-like call instead|UNSAFE_IMPLICIT_INVOKE_CALL
Reified type is forbidden for catch parameter|REIFIED_TYPE_IN_CATCH_CLAUSE
Repeated {0}|REPEATED_MODIFIER
return is not allowed here|RETURN_NOT_ALLOWED
Return type of {0} is not a subtype of the return type of the overridden member {1}|RETURN_TYPE_MISMATCH_ON_OVERRIDE
Returns are not allowed for functions with expression body. Use block body in '{...}'|RETURN_IN_FUNCTION_WITH_EXPRESSION_BODY
Right operand of elvis operator (?:) is useless if it is null|USELESS_ELVIS_RIGHT_IS_NULL
Right-hand side has anonymous type. Please specify type explicitly|AMBIGUOUS_ANONYMOUS_TYPE_INFERRED
Safe-call is not allowed here|UNEXPECTED_SAFE_CALL
Sealed types cannot be instantiated|SEALED_CLASS_CONSTRUCTOR_CALL
Setter for {0} is removed by type projection|SETTER_PROJECTED_OUT
Setter parameter type must be equal to the type of the property, i.e. {0}|WRONG_SETTER_PARAMETER_TYPE
Setter parameters cannot have default values|SETTER_PARAMETER_WITH_DEFAULT_VALUE
Setter return type must be Unit|WRONG_SETTER_RETURN_TYPE
Setter visibility must be the same or less permissive than property visibility|SETTER_VISIBILITY_INCONSISTENT_WITH_PROPERTY_VISIBILITY
Smart cast to {0} is impossible, because {1} is a {2}|SMARTCAST_IMPOSSIBLE
{0} sub-interface exposes its {2} supertype{1}|EXPOSED_SUPER_INTERFACE
{0} subclass exposes its {2} supertype{1}|EXPOSED_SUPER_CLASS
Subclass of 'Throwable' may not have type parameters|GENERIC_THROWABLE_SUBCLASS
Superclass is not accessible from interface|SUPERCLASS_NOT_ACCESSIBLE_FROM_INTERFACE
Supertype initialization is impossible without primary constructor|SUPERTYPE_INITIALIZED_WITHOUT_PRIMARY_CONSTRUCTOR
Suspension functions can be called only within coroutine body|NON_LOCAL_SUSPENSION_POINT
Tail recursion optimization inside try/catch/finally is not supported|TAIL_RECURSION_IN_TRY_IS_NOT_SUPPORTED
The corresponding parameter in the supertype {0} is named {1}. This may cause problems when calling this function with named arguments.|PARAMETER_NAME_CHANGED_ON_OVERRIDE
The expression cannot be a selector (occur after a dot)|ILLEGAL_SELECTOR
The expression is unused|UNUSED_EXPRESSION
The feature is only available since Kotlin {0}|UNSUPPORTED_FEATURE
The iterator().hasNext() function of the loop range must return Boolean, but returns {0}|HAS_NEXT_FUNCTION_TYPE_MISMATCH
The label {0} does not denote a loop|NOT_A_LOOP_LABEL
The label {0} does not reference to a context from which we can return|NOT_A_RETURN_LABEL
The lambda expression here is an inlined argument so this annotation cannot be stored anywhere|NON_SOURCE_ANNOTATION_ON_INLINED_LAMBDA_EXPRESSION
The lambda expression is unused. If you mean a block, you can use 'run { ... }'|UNUSED_LAMBDA_EXPRESSION
The loop iterates over values of type {0} but the parameter is declared to be {1}|TYPE_MISMATCH_IN_FOR_LOOP
The result of the expression is always null|ALWAYS_NULL
The spread operator (*foo) may not be applied to an argument of nullable type|SPREAD_OF_NULLABLE
The spread operator (*foo) may only be applied in a vararg position|NON_VARARG_SPREAD
The value changed at {0} is never used|UNUSED_CHANGED_VALUE
The value is out of range|FLOAT_LITERAL_OUT_OF_RANGE
The value is out of range|INT_LITERAL_OUT_OF_RANGE
The value {0} assigned to {1} is never used|UNUSED_VALUE
The version is greater than the specified API version {0}|NEWER_VERSION_IN_SINCE_KOTLIN
The {0} function of property delegate is expected to return {1}, but returns {2}|DELEGATE_SPECIAL_FUNCTION_RETURN_TYPE_MISMATCH
The {0} invocation is a part of inline cycle|INLINE_CALL_CYCLE
The {0} literal does not conform to the expected type {1}|CONSTANT_EXPECTED_TYPE_MISMATCH
There is more than one label with such a name in this scope|LABEL_NAME_CLASH
There's a cycle in the delegation calls chain|CYCLIC_CONSTRUCTOR_DELEGATION_CALL
There's a cycle in the inheritance hierarchy for this type|CYCLIC_INHERITANCE_HIERARCHY
This annotation is not applicable to target {0} and use site target @{1}|WRONG_ANNOTATION_TARGET_WITH_USE_SITE_TARGET
This annotation is not applicable to target {0}|WRONG_ANNOTATION_TARGET
This annotation is not repeatable|REPEATED_ANNOTATION
This cast can never succeed|CAST_NEVER_SUCCEEDS
This class does not have a constructor|NO_CONSTRUCTOR
This class shouldnt be used in Kotlin. Use {0} instead.|PLATFORM_CLASS_MAPPED_TO_KOTLIN
This declaration is only available since Kotlin {0} and cannot be used with the specified API version {1}|API_NOT_AVAILABLE
This function must return a value of type {0}|RETURN_TYPE_MISMATCH
this is not defined in this context|NO_THIS
This operation has led to an overflow|INTEGER_OVERFLOW
This property cannot be declared abstract|ABSTRACT_PROPERTY_IN_PRIMARY_CONSTRUCTOR_PARAMETERS
This property must either have a type annotation, be initialized or be delegated|PROPERTY_WITH_NO_TYPE_NO_INITIALIZER
This type has a constructor, and thus must be initialized here|SUPERTYPE_NOT_INITIALIZED
This type is final, so it cannot be inherited from|FINAL_SUPERTYPE
This type is sealed, so it can be inherited by only its own nested classes or objects|SEALED_SUPERTYPE
This type parameter violates the Finite Bound Restriction|FINITE_BOUNDS_VIOLATION
This type parameter violates the Non-Expansive Inheritance Restriction|EXPANSIVE_INHERITANCE
This variable must either have a type annotation or be initialized|VARIABLE_WITH_NO_TYPE_NO_INITIALIZER
Too many arguments for {0}|TOO_MANY_ARGUMENTS
Too many characters in a character literal {0}|TOO_MANY_CHARACTERS_IN_CHARACTER_LITERAL
Type alias expanded to malformed type {0}: {1}|TYPEALIAS_EXPANDED_TO_MALFORMED_TYPE
Type alias expands to {0}, which is not a class, an interface, or an object|TYPEALIAS_SHOULD_EXPAND_TO_CLASS
Type alias parameter {0} is not used in the expanded type {1} and does not affect type checking|UNUSED_TYPEALIAS_PARAMETER
Type argument is not within its bounds: should be subtype of {0}|UPPER_BOUND_VIOLATED
Type argument resulting from type alias expansion is not within required bounds for {2}: should be subtype of {0}, substituted type is {1}|UPPER_BOUND_VIOLATED_IN_TYPEALIAS_EXPANSION
Type arguments are not allowed {0}|TYPE_ARGUMENTS_NOT_ALLOWED
Type arguments do not need to be specified in a 'super' qualifier|TYPE_ARGUMENTS_REDUNDANT_IN_SUPER_QUALIFIER
Type arguments for outer class are redundant when nested class is referenced|TYPE_ARGUMENTS_FOR_OUTER_CLASS_WHEN_NESTED_REFERENCED
Type arguments should be specified for an outer {0}. Use full class name to specify them|OUTER_CLASS_ARGUMENTS_REQUIRED
Type checking has run into a recursive problem. Easiest workaround: specify types of your declarations explicitly|TYPECHECKER_HAS_RUN_INTO_RECURSIVE_PROBLEM // TODO: message
Type inference failed. Expected type mismatch: inferred type is {1} but {0} was expected|TYPE_INFERENCE_EXPECTED_TYPE_MISMATCH
Type inference failed. Please try to specify type arguments explicitly.|TYPE_INFERENCE_INCORPORATION_ERROR
Type inference failed. The value of the type parameter {0} should be mentioned in input types (argument types, receiver type or expected type). Try to specify it explicitly.|TYPE_INFERENCE_ONLY_INPUT_TYPES
Type inference failed: {0}|TYPE_INFERENCE_CANNOT_CAPTURE_TYPES
Type inference failed: {0}|TYPE_INFERENCE_CONFLICTING_SUBSTITUTIONS
Type inference failed: {0}|TYPE_INFERENCE_NO_INFORMATION_FOR_PARAMETER
Type inference failed: {0}|TYPE_INFERENCE_PARAMETER_CONSTRAINT_ERROR
Type inference for control flow expression failed. Please specify its type explicitly.|TYPE_INFERENCE_FAILED_ON_SPECIAL_CONSTRUCT
Type mismatch: incompatible types of range and element checked in it|TYPE_MISMATCH_IN_RANGE
Type mismatch: inferred type is {1} but {0} was expected. Projected type {2} restricts use of {3}|TYPE_MISMATCH_DUE_TO_TYPE_PROJECTIONS
Type mismatch: inferred type is {1} but {0} was expected|TYPE_MISMATCH
Type of property {0} is not a subtype of overridden by delegation {1}|PROPERTY_TYPE_MISMATCH_BY_DELEGATION
Type of {0} doesnt match the type of the overridden var-property {1}|VAR_TYPE_MISMATCH_ON_OVERRIDE
Type of {0} is not a subtype of overridden by delegation {1}|RETURN_TYPE_MISMATCH_BY_DELEGATION
Type of {0} is not a subtype of the overridden property {1}|PROPERTY_TYPE_MISMATCH_ON_OVERRIDE
Type parameter already has this bound|REPEATED_BOUND
Type parameter cannot have any other bounds if it's bounded by another type parameter|BOUNDS_NOT_ALLOWED_IF_BOUNDED_BY_TYPE_PARAMETER
Type parameter has cyclic upper bounds|CYCLIC_GENERIC_UPPER_BOUND
Type parameter of a property must be used in its receiver type|TYPE_PARAMETER_OF_PROPERTY_NOT_USED_IN_RECEIVER
Type parameter {0} cannot have or inherit a companion object, so it cannot be on the left hand side of dot|TYPE_PARAMETER_ON_LHS_OF_DOT
Type parameter {0} is declared as {1} but occurs in {2} position in abbreviated type {3}|TYPE_VARIANCE_CONFLICT_IN_EXPANDED_TYPE
Type parameter {0} is declared as {1} but occurs in {2} position in type {3}|TYPE_VARIANCE_CONFLICT
Type parameter {0} is not an expression|TYPE_PARAMETER_IS_NOT_AN_EXPRESSION
Type parameter {0} of {1} has inconsistent bounds: {2}|INCONSISTENT_TYPE_PARAMETER_BOUNDS
Type parameter {0} of {1} has inconsistent values: {2}|INCONSISTENT_TYPE_PARAMETER_VALUES
Type parameters are not allowed here|TYPE_PARAMETERS_NOT_ALLOWED
Type parameters must be placed before the name of the function|DEPRECATED_TYPE_PARAMETER_SYNTAX
Type {0} is inaccessible in this context due to: {1}|INACCESSIBLE_TYPE
{0} typealias exposes {2} in expanded type{1}|EXPOSED_TYPEALIAS_EXPANDED_TYPE
Unchecked cast: {0} to {1}|UNCHECKED_CAST
Unnecessary non-null assertion (!!) on a non-null receiver of type {0}|UNNECESSARY_NOT_NULL_ASSERTION
Unnecessary safe call on a non-null receiver of type {0}|UNNECESSARY_SAFE_CALL
Unreachable code|UNREACHABLE_CODE
Unresolved reference. None of the following candidates is applicable because of receiver type mismatch: {0}|UNRESOLVED_REFERENCE_WRONG_RECEIVER
Unresolved reference: {0}|UNRESOLVED_REFERENCE
Unsupported [{0}]|UNSUPPORTED
Upper bounds of {0} have empty intersection|CONFLICTING_UPPER_BOUNDS
Use 'constructor' keyword after modifiers of primary constructor|MISSING_CONSTRUCTOR_KEYWORD
Use 'L' instead of 'l'|WRONG_LONG_SUFFIX
Use of enum entry names as types is not allowed, use enum type instead|ENUM_ENTRY_AS_TYPE
Using {0} is an error. {1}|DEPRECATION_ERROR
Val cannot be reassigned|VAL_REASSIGNMENT
val keyword is missing on annotation parameter|MISSING_VAL_ON_ANNOTATION_PARAMETER
Val-property {0} implicitly overrides a var-property {1} by delegation|VAR_OVERRIDDEN_BY_VAL_BY_DELEGATION
Var-property {0} cannot be overridden by val-property {1}|VAR_OVERRIDDEN_BY_VAL
Vararg on this parameter is useless|USELESS_VARARG_ON_PARAMETER
Variable cannot be initialized before declaration|INITIALIZATION_BEFORE_DECLARATION
Variable expected|VARIABLE_EXPECTED
Variable {0} initializer is redundant|VARIABLE_WITH_REDUNDANT_INITIALIZER
Variable {0} is assigned but never accessed|ASSIGNED_BUT_NEVER_ACCESSED_VARIABLE
Variable {0} is never used|UNUSED_VARIABLE
Variable {0} must be initialized|UNINITIALIZED_VARIABLE
Variance annotations are only allowed for type parameters of classes and interfaces|VARIANCE_ON_TYPE_PARAMETER_NOT_ALLOWED
Violation of Finite Bound Restriction for {0}|FINITE_BOUNDS_VIOLATION_IN_JAVA
Violation of Non-Expansive Inheritance Restriction for {0}|EXPANSIVE_INHERITANCE_IN_JAVA
Visibility modifiers are redundant in getter|REDUNDANT_MODIFIER_IN_GETTER
when expression must be exhaustive, add necessary {0}|NO_ELSE_IN_WHEN
when expression on enum is recommended to be exhaustive, add {0}|NON_EXHAUSTIVE_WHEN
