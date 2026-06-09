# ElValidateWin32_6

- ea: `0x180017470`
- end: `0x180017539`
- name: `ElValidateWin32_6`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180016410`

## callees

- `0x180017470`
- `0x180031010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18001751a`
- `KERNEL32!SetLastError` at `0x18001751a`
- `KERNEL32!GetLastError` at `0x180017496`
- `KERNEL32!GetLastError` at `0x1800174e2`
- `KERNEL32!GetLastError` at `0x180017496`
- `KERNEL32!GetLastError` at `0x1800174e2`

## string_xrefs

- `0x1800174b2`: `onecore\base\eco\wds\wdslib\common\src\strutil.cpp`
- `0x1800174fb`: `onecore\base\eco\wds\wdslib\common\src\strutil.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_6(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\strutil.cpp",
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\strutil.cpp",
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
0x180017470  mov     [rsp+arg_0], rbx
0x180017475  mov     [rsp+arg_8], rsi
0x18001747a  push    rdi
0x18001747b  sub     rsp, 40h
0x18001747f  mov     esi, r9d
0x180017482  mov     edi, ecx
0x180017484  test    ecx, ecx
0x180017486  jz      loc_180017526
0x18001748c  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180017494  jz      short loc_1800174D8
0x180017496  call    cs:__imp_GetLastError
0x18001749d  nop     dword ptr [rax+rax+00h]
0x1800174a2  lea     r9, dword_18003572C
0x1800174a9  mov     [rsp+48h+var_20], edi
0x1800174ad  mov     [rsp+48h+var_28], r9
0x1800174b2  lea     r8, aOnecoreBaseEco_6; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x1800174b9  mov     ebx, eax
0x1800174bb  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x1800174c2  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800174c9  mov     r9d, esi
0x1800174cc  mov     ecx, 80000h
0x1800174d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800174d6  jmp     short loc_180017518
0x1800174d8  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800174e0  jz      short loc_180017526
0x1800174e2  call    cs:__imp_GetLastError
0x1800174e9  nop     dword ptr [rax+rax+00h]
0x1800174ee  lea     r9, dword_18003572C
0x1800174f5  mov     dword ptr [rsp+48h+var_28], edi
0x1800174f9  mov     ebx, eax
0x1800174fb  lea     rdx, aOnecoreBaseEco_6; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180017502  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180017509  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180017510  mov     r8d, esi
0x180017513  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017518  mov     ecx, ebx; dwErrCode
0x18001751a  call    cs:__imp_SetLastError
0x180017521  nop     dword ptr [rax+rax+00h]
0x180017526  mov     rbx, [rsp+48h+arg_0]
0x18001752b  mov     eax, edi
0x18001752d  mov     rsi, [rsp+48h+arg_8]
0x180017532  add     rsp, 40h
0x180017536  pop     rdi
0x180017537  retn
```
