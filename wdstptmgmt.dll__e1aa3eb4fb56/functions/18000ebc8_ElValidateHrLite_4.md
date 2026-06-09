# ElValidateHrLite_4

- ea: `0x18000ebc8`
- end: `0x18000ec91`
- name: `ElValidateHrLite_4`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18000eb74`

## callees

- `0x18000ebc8`
- `0x180020010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000ec72`
- `KERNEL32!SetLastError` at `0x18000ec72`
- `KERNEL32!GetLastError` at `0x18000ebee`
- `KERNEL32!GetLastError` at `0x18000ec3a`
- `KERNEL32!GetLastError` at `0x18000ebee`
- `KERNEL32!GetLastError` at `0x18000ec3a`

## string_xrefs

- `0x18000ec0a`: `base\eco\wds\wdstptmgmt\src\wdstransportservicepolicy.cpp`
- `0x18000ec53`: `base\eco\wds\wdstptmgmt\src\wdstransportservicepolicy.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateHrLite_4(int a1, __int64 a2, __int64 a3, unsigned int a4)
{
  DWORD LastError; // ebx

  if ( a1 < 0 )
  {
    if ( g_ErrLibTraceFunctionEx )
    {
      LastError = GetLastError();
      g_ErrLibTraceFunctionEx(
        0x80000u,
        L"[%S:%u] Expression: %S, hr=0x%x",
        "base\\eco\\wds\\wdstptmgmt\\src\\wdstransportservicepolicy.cpp",
        a4,
        word_1800257AA,
        a1);
LABEL_6:
      SetLastError(LastError);
      return (unsigned int)a1;
    }
    if ( g_ErrLibTraceFunction )
    {
      LastError = GetLastError();
      g_ErrLibTraceFunction(
        L"[%S:%u] Expression: %S, hr=0x%x",
        "base\\eco\\wds\\wdstptmgmt\\src\\wdstransportservicepolicy.cpp",
        a4,
        word_1800257AA,
        a1);
      goto LABEL_6;
    }
  }
  return (unsigned int)a1;
}

```

## disassembly

```asm
0x18000ebc8  mov     [rsp+arg_0], rbx
0x18000ebcd  mov     [rsp+arg_8], rsi
0x18000ebd2  push    rdi
0x18000ebd3  sub     rsp, 40h
0x18000ebd7  mov     esi, r9d
0x18000ebda  mov     edi, ecx
0x18000ebdc  test    ecx, ecx
0x18000ebde  jns     loc_18000EC7E
0x18000ebe4  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000ebec  jz      short loc_18000EC30
0x18000ebee  call    cs:__imp_GetLastError
0x18000ebf5  nop     dword ptr [rax+rax+00h]
0x18000ebfa  lea     r9, word_1800257AA
0x18000ec01  mov     [rsp+48h+var_20], edi
0x18000ec05  mov     [rsp+48h+var_28], r9
0x18000ec0a  lea     r8, aBaseEcoWdsWdst_12; "base\\eco\\wds\\wdstptmgmt\\src\\wdstra"...
0x18000ec11  mov     ebx, eax
0x18000ec13  lea     rdx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x18000ec1a  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000ec21  mov     r9d, esi
0x18000ec24  mov     ecx, 80000h
0x18000ec29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec2e  jmp     short loc_18000EC70
0x18000ec30  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000ec38  jz      short loc_18000EC7E
0x18000ec3a  call    cs:__imp_GetLastError
0x18000ec41  nop     dword ptr [rax+rax+00h]
0x18000ec46  lea     r9, word_1800257AA
0x18000ec4d  mov     dword ptr [rsp+48h+var_28], edi
0x18000ec51  mov     ebx, eax
0x18000ec53  lea     rdx, aBaseEcoWdsWdst_12; "base\\eco\\wds\\wdstptmgmt\\src\\wdstra"...
0x18000ec5a  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000ec61  lea     rcx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x18000ec68  mov     r8d, esi
0x18000ec6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec70  mov     ecx, ebx; dwErrCode
0x18000ec72  call    cs:__imp_SetLastError
0x18000ec79  nop     dword ptr [rax+rax+00h]
0x18000ec7e  mov     rbx, [rsp+48h+arg_0]
0x18000ec83  mov     eax, edi
0x18000ec85  mov     rsi, [rsp+48h+arg_8]
0x18000ec8a  add     rsp, 40h
0x18000ec8e  pop     rdi
0x18000ec8f  retn
```
