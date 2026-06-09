# wil::details::ThreadFailureCallbackFn__lambda_6b1d65cd1938606b4159120d1307db23___::_ThreadFailureCallbackFn__lambda_6b1d65cd1938606b4159120d1307db23___

- ea: `0x180004614`
- end: `0x18000461d`
- name: `wil::details::ThreadFailureCallbackFn__lambda_6b1d65cd1938606b4159120d1307db23___::_ThreadFailureCallbackFn__lambda_6b1d65cd1938606b4159120d1307db23___`
- size: `9`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f11b`

## callees

- `0x180005098`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackFn__lambda_6b1d65cd1938606b4159120d1307db23___::_ThreadFailureCallbackFn__lambda_6b1d65cd1938606b4159120d1307db23___(
        __int64 a1)
{
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)(a1 + 8));
}

```

## disassembly

```asm
0x180004614  add     rcx, 8; this
0x180004618  jmp     ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
```
