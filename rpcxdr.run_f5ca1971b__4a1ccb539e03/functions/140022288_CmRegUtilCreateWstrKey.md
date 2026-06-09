# CmRegUtilCreateWstrKey

- ea: `0x140022288`
- end: `0x1400222df`
- name: `CmRegUtilCreateWstrKey`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140021a78`
- `0x140021f60`

## callees

- `0x1400120a8`
- `0x1400221dc`
- `0x140022288`

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
0x140022288  sub     rsp, 58h
0x14002228c  mov     r10, rcx
0x14002228f  xorps   xmm0, xmm0
0x140022292  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x140022297  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm0
0x14002229c  call    WdmlibRtlInitUnicodeStringEx
0x1400222a1  test    eax, eax
0x1400222a3  js      short loc_1400222D9
0x1400222a5  mov     rax, [rsp+58h+arg_30]
0x1400222ad  lea     rdx, [rsp+58h+DestinationString]
0x1400222b2  mov     [rsp+58h+var_28], rax
0x1400222b7  mov     rcx, r10
0x1400222ba  mov     rax, [rsp+58h+arg_28]
0x1400222c2  mov     [rsp+58h+var_30], rax
0x1400222c7  mov     rax, [rsp+58h+arg_20]
0x1400222cf  mov     [rsp+58h+var_38], rax
0x1400222d4  call    CmRegUtilCreateUcKey
0x1400222d9  add     rsp, 58h
0x1400222dd  retn
```
