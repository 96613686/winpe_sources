# ElValidateWin32_0

- ea: `0x1800065a4`
- end: `0x18000666d`
- name: `ElValidateWin32_0`
- size: `201`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800063a0`
- `0x180006440`

## callees

- `0x1800065a4`
- `0x180031010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000664e`
- `KERNEL32!SetLastError` at `0x18000664e`
- `KERNEL32!GetLastError` at `0x1800065ca`
- `KERNEL32!GetLastError` at `0x180006616`
- `KERNEL32!GetLastError` at `0x1800065ca`
- `KERNEL32!GetLastError` at `0x180006616`

## string_xrefs

- `0x1800065e6`: `onecore\base\eco\wds\wdslib\common\src\eventlog2.cpp`
- `0x18000662f`: `onecore\base\eco\wds\wdslib\common\src\eventlog2.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_0(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\eventlog2.cpp",
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\eventlog2.cpp",
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
0x1800065a4  mov     [rsp+arg_0], rbx
0x1800065a9  mov     [rsp+arg_8], rsi
0x1800065ae  push    rdi
0x1800065af  sub     rsp, 40h
0x1800065b3  mov     esi, r9d
0x1800065b6  mov     edi, ecx
0x1800065b8  test    ecx, ecx
0x1800065ba  jz      loc_18000665A
0x1800065c0  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800065c8  jz      short loc_18000660C
0x1800065ca  call    cs:__imp_GetLastError
0x1800065d1  nop     dword ptr [rax+rax+00h]
0x1800065d6  lea     r9, dword_18003572C
0x1800065dd  mov     [rsp+48h+var_20], edi
0x1800065e1  mov     [rsp+48h+var_28], r9
0x1800065e6  lea     r8, aOnecoreBaseEco_10; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x1800065ed  mov     ebx, eax
0x1800065ef  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x1800065f6  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800065fd  mov     r9d, esi
0x180006600  mov     ecx, 80000h
0x180006605  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000660a  jmp     short loc_18000664C
0x18000660c  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180006614  jz      short loc_18000665A
0x180006616  call    cs:__imp_GetLastError
0x18000661d  nop     dword ptr [rax+rax+00h]
0x180006622  lea     r9, dword_18003572C
0x180006629  mov     dword ptr [rsp+48h+var_28], edi
0x18000662d  mov     ebx, eax
0x18000662f  lea     rdx, aOnecoreBaseEco_10; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180006636  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000663d  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180006644  mov     r8d, esi
0x180006647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000664c  mov     ecx, ebx; dwErrCode
0x18000664e  call    cs:__imp_SetLastError
0x180006655  nop     dword ptr [rax+rax+00h]
0x18000665a  mov     rbx, [rsp+48h+arg_0]
0x18000665f  mov     eax, edi
0x180006661  mov     rsi, [rsp+48h+arg_8]
0x180006666  add     rsp, 40h
0x18000666a  pop     rdi
0x18000666b  retn
```
