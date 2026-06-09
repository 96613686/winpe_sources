# ElValidateWin32_21

- ea: `0x18002a6b4`
- end: `0x18002a77d`
- name: `ElValidateWin32_21`
- size: `201`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002a790`
- `0x18002a870`
- `0x18002a950`

## callees

- `0x18002a6b4`
- `0x180031010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18002a75e`
- `KERNEL32!SetLastError` at `0x18002a75e`
- `KERNEL32!GetLastError` at `0x18002a6da`
- `KERNEL32!GetLastError` at `0x18002a726`
- `KERNEL32!GetLastError` at `0x18002a6da`
- `KERNEL32!GetLastError` at `0x18002a726`

## string_xrefs

- `0x18002a6f6`: `onecore\base\eco\wds\wdslib\common\src\wdsidn.cpp`
- `0x18002a73f`: `onecore\base\eco\wds\wdslib\common\src\wdsidn.cpp`

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
        &dword_18003572C,
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
        &dword_18003572C,
        a1);
      goto LABEL_6;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18002a6b4  mov     [rsp+arg_0], rbx
0x18002a6b9  mov     [rsp+arg_8], rsi
0x18002a6be  push    rdi
0x18002a6bf  sub     rsp, 40h
0x18002a6c3  mov     esi, r9d
0x18002a6c6  mov     edi, ecx
0x18002a6c8  test    ecx, ecx
0x18002a6ca  jz      loc_18002A76A
0x18002a6d0  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18002a6d8  jz      short loc_18002A71C
0x18002a6da  call    cs:__imp_GetLastError
0x18002a6e1  nop     dword ptr [rax+rax+00h]
0x18002a6e6  lea     r9, dword_18003572C
0x18002a6ed  mov     [rsp+48h+var_20], edi
0x18002a6f1  mov     [rsp+48h+var_28], r9
0x18002a6f6  lea     r8, aOnecoreBaseEco_33; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18002a6fd  mov     ebx, eax
0x18002a6ff  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18002a706  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18002a70d  mov     r9d, esi
0x18002a710  mov     ecx, 80000h
0x18002a715  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a71a  jmp     short loc_18002A75C
0x18002a71c  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18002a724  jz      short loc_18002A76A
0x18002a726  call    cs:__imp_GetLastError
0x18002a72d  nop     dword ptr [rax+rax+00h]
0x18002a732  lea     r9, dword_18003572C
0x18002a739  mov     dword ptr [rsp+48h+var_28], edi
0x18002a73d  mov     ebx, eax
0x18002a73f  lea     rdx, aOnecoreBaseEco_33; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18002a746  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18002a74d  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18002a754  mov     r8d, esi
0x18002a757  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a75c  mov     ecx, ebx; dwErrCode
0x18002a75e  call    cs:__imp_SetLastError
0x18002a765  nop     dword ptr [rax+rax+00h]
0x18002a76a  mov     rbx, [rsp+48h+arg_0]
0x18002a76f  mov     eax, edi
0x18002a771  mov     rsi, [rsp+48h+arg_8]
0x18002a776  add     rsp, 40h
0x18002a77a  pop     rdi
0x18002a77b  retn
```
