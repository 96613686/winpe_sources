# CmRegUtilCreateWstrKey

- ea: `0x1400194c8`
- end: `0x14001951f`
- name: `CmRegUtilCreateWstrKey`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140018cb8`
- `0x1400191a0`

## callees

- `0x140004f04`
- `0x14001941c`
- `0x1400194c8`

## pseudocode

```c
NTSTATUS __fastcall CmRegUtilCreateWstrKey(
        __int64 a1,
        const WCHAR *a2,
        __int64 a3,
        __int64 a4,
        void *a5,
        ULONG *a6,
        _QWORD *a7)
{
  NTSTATUS result; // eax
  __int64 v8; // r8
  __int64 v9; // r9
  void *v10; // r10
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-18h] BYREF

  DestinationString = 0;
  result = WdmlibRtlInitUnicodeStringEx(&DestinationString, a2);
  if ( result >= 0 )
    return CmRegUtilCreateUcKey(v10, &DestinationString, v8, v9, a5, a6, a7);
  return result;
}

```

## disassembly

```asm
0x1400194c8  sub     rsp, 58h
0x1400194cc  mov     r10, rcx
0x1400194cf  xorps   xmm0, xmm0
0x1400194d2  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x1400194d7  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm0
0x1400194dc  call    WdmlibRtlInitUnicodeStringEx
0x1400194e1  test    eax, eax
0x1400194e3  js      short loc_140019519
0x1400194e5  mov     rax, [rsp+58h+arg_30]
0x1400194ed  lea     rdx, [rsp+58h+DestinationString]
0x1400194f2  mov     [rsp+58h+var_28], rax
0x1400194f7  mov     rcx, r10
0x1400194fa  mov     rax, [rsp+58h+arg_28]
0x140019502  mov     [rsp+58h+var_30], rax
0x140019507  mov     rax, [rsp+58h+arg_20]
0x14001950f  mov     [rsp+58h+var_38], rax
0x140019514  call    CmRegUtilCreateUcKey
0x140019519  add     rsp, 58h
0x14001951d  retn
```
