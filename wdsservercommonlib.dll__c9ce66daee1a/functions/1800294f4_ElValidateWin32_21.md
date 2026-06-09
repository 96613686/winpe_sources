# ElValidateWin32_21

- ea: `0x1800294f4`
- end: `0x1800295bd`
- name: `ElValidateWin32_21`
- size: `201`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800295d0`
- `0x1800296a0`
- `0x180029770`

## callees

- `0x1800294f4`
- `0x180030010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18002959e`
- `KERNEL32!SetLastError` at `0x18002959e`
- `KERNEL32!GetLastError` at `0x18002951a`
- `KERNEL32!GetLastError` at `0x180029566`
- `KERNEL32!GetLastError` at `0x18002951a`
- `KERNEL32!GetLastError` at `0x180029566`

## string_xrefs

- `0x180029536`: `onecore\base\eco\wds\wdslib\common\src\wdsidn.cpp`
- `0x18002957f`: `onecore\base\eco\wds\wdslib\common\src\wdsidn.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_21(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
{
  DWORD LastError; // ebx

  if ( a1 )
  {
    if ( g_ErrLibTraceFunctionEx )
    {
      LastError = GetLastError();
      g_ErrLibTraceFunctionEx(
        0x80000u,
        L"[%S:%u] Expression: %S, Win32 Error=0x%x",
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\wdsidn.cpp",
        a4,
        &dword_1800331C4,
        a1);
LABEL_6:
      SetLastError(LastError);
      return a1;
    }
    if ( g_ErrLibTraceFunction )
    {
      LastError = GetLastError();
      g_ErrLibTraceFunction(
        L"[%S:%u] Expression: %S, Win32 Error=0x%x",
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\wdsidn.cpp",
        a4,
        &dword_1800331C4,
        a1);
      goto LABEL_6;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1800294f4  mov     [rsp+arg_0], rbx
0x1800294f9  mov     [rsp+arg_8], rsi
0x1800294fe  push    rdi
0x1800294ff  sub     rsp, 40h
0x180029503  mov     esi, r9d
0x180029506  mov     edi, ecx
0x180029508  test    ecx, ecx
0x18002950a  jz      loc_1800295AA
0x180029510  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180029518  jz      short loc_18002955C
0x18002951a  call    cs:__imp_GetLastError
0x180029521  nop     dword ptr [rax+rax+00h]
0x180029526  lea     r9, dword_1800331C4
0x18002952d  mov     [rsp+48h+var_20], edi
0x180029531  mov     [rsp+48h+var_28], r9
0x180029536  lea     r8, aOnecoreBaseEco_34; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18002953d  mov     ebx, eax
0x18002953f  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180029546  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18002954d  mov     r9d, esi
0x180029550  mov     ecx, 80000h
0x180029555  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002955a  jmp     short loc_18002959C
0x18002955c  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180029564  jz      short loc_1800295AA
0x180029566  call    cs:__imp_GetLastError
0x18002956d  nop     dword ptr [rax+rax+00h]
0x180029572  lea     r9, dword_1800331C4
0x180029579  mov     dword ptr [rsp+48h+var_28], edi
0x18002957d  mov     ebx, eax
0x18002957f  lea     rdx, aOnecoreBaseEco_34; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180029586  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18002958d  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180029594  mov     r8d, esi
0x180029597  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002959c  mov     ecx, ebx; dwErrCode
0x18002959e  call    cs:__imp_SetLastError
0x1800295a5  nop     dword ptr [rax+rax+00h]
0x1800295aa  mov     rbx, [rsp+48h+arg_0]
0x1800295af  mov     eax, edi
0x1800295b1  mov     rsi, [rsp+48h+arg_8]
0x1800295b6  add     rsp, 40h
0x1800295ba  pop     rdi
0x1800295bb  retn
```
