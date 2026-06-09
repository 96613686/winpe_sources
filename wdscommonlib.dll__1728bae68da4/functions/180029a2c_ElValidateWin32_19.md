# ElValidateWin32_19

- ea: `0x180029a2c`
- end: `0x180029af5`
- name: `ElValidateWin32_19`
- size: `201`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180029330`
- `0x180029390`
- `0x180029490`
- `0x180029500`

## callees

- `0x180029a2c`
- `0x180031010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180029ad6`
- `KERNEL32!SetLastError` at `0x180029ad6`
- `KERNEL32!GetLastError` at `0x180029a52`
- `KERNEL32!GetLastError` at `0x180029a9e`
- `KERNEL32!GetLastError` at `0x180029a52`
- `KERNEL32!GetLastError` at `0x180029a9e`

## string_xrefs

- `0x180029a6e`: `onecore\base\eco\wds\wdslib\common\src\privilege.cpp`
- `0x180029ab7`: `onecore\base\eco\wds\wdslib\common\src\privilege.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_19(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\privilege.cpp",
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\privilege.cpp",
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
0x180029a2c  mov     [rsp+arg_0], rbx
0x180029a31  mov     [rsp+arg_8], rsi
0x180029a36  push    rdi
0x180029a37  sub     rsp, 40h
0x180029a3b  mov     esi, r9d
0x180029a3e  mov     edi, ecx
0x180029a40  test    ecx, ecx
0x180029a42  jz      loc_180029AE2
0x180029a48  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180029a50  jz      short loc_180029A94
0x180029a52  call    cs:__imp_GetLastError
0x180029a59  nop     dword ptr [rax+rax+00h]
0x180029a5e  lea     r9, dword_18003572C
0x180029a65  mov     [rsp+48h+var_20], edi
0x180029a69  mov     [rsp+48h+var_28], r9
0x180029a6e  lea     r8, aOnecoreBaseEco_11; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180029a75  mov     ebx, eax
0x180029a77  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180029a7e  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180029a85  mov     r9d, esi
0x180029a88  mov     ecx, 80000h
0x180029a8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029a92  jmp     short loc_180029AD4
0x180029a94  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180029a9c  jz      short loc_180029AE2
0x180029a9e  call    cs:__imp_GetLastError
0x180029aa5  nop     dword ptr [rax+rax+00h]
0x180029aaa  lea     r9, dword_18003572C
0x180029ab1  mov     dword ptr [rsp+48h+var_28], edi
0x180029ab5  mov     ebx, eax
0x180029ab7  lea     rdx, aOnecoreBaseEco_11; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180029abe  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180029ac5  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180029acc  mov     r8d, esi
0x180029acf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ad4  mov     ecx, ebx; dwErrCode
0x180029ad6  call    cs:__imp_SetLastError
0x180029add  nop     dword ptr [rax+rax+00h]
0x180029ae2  mov     rbx, [rsp+48h+arg_0]
0x180029ae7  mov     eax, edi
0x180029ae9  mov     rsi, [rsp+48h+arg_8]
0x180029aee  add     rsp, 40h
0x180029af2  pop     rdi
0x180029af3  retn
```
