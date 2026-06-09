# ElValidateHr_3

- ea: `0x180017374`
- end: `0x180017467`
- name: `ElValidateHr_3`
- size: `243`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180015830`
- `0x180015a30`

## callees

- `0x180006ea4`
- `0x180017374`
- `0x180031010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18001741e`
- `KERNEL32!SetLastError` at `0x180017448`
- `KERNEL32!SetLastError` at `0x18001741e`
- `KERNEL32!SetLastError` at `0x180017448`
- `KERNEL32!GetLastError` at `0x18001739a`
- `KERNEL32!GetLastError` at `0x1800173e6`
- `KERNEL32!GetLastError` at `0x18001742a`
- `KERNEL32!GetLastError` at `0x18001739a`
- `KERNEL32!GetLastError` at `0x1800173e6`
- `KERNEL32!GetLastError` at `0x18001742a`

## string_xrefs

- `0x1800173b6`: `onecore\base\eco\wds\wdslib\common\src\strutil.cpp`
- `0x1800173ff`: `onecore\base\eco\wds\wdslib\common\src\strutil.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateHr_3(int a1, __int64 a2, __int64 a3, unsigned int a4)
{
  DWORD LastError; // ebx
  DWORD v7; // ebx

  if ( a1 >= 0 )
    return (unsigned int)a1;
  if ( g_ErrLibTraceFunctionEx )
  {
    LastError = GetLastError();
    g_ErrLibTraceFunctionEx(
      0x80000u,
      L"[%S:%u] Expression: %S, hr=0x%x",
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\strutil.cpp",
      a4,
      &dword_18003572C,
      a1);
LABEL_6:
    SetLastError(LastError);
    goto LABEL_7;
  }
  if ( g_ErrLibTraceFunction )
  {
    LastError = GetLastError();
    g_ErrLibTraceFunction(
      L"[%S:%u] Expression: %S, hr=0x%x",
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\strutil.cpp",
      a4,
      &dword_18003572C,
      a1);
    goto LABEL_6;
  }
LABEL_7:
  v7 = GetLastError();
  if ( (g_uErrLibFlags & 1) != 0 )
    ElTraceErrorInfo();
  SetLastError(v7);
  return (unsigned int)a1;
}

```

## disassembly

```asm
0x180017374  mov     [rsp+arg_0], rbx
0x180017379  mov     [rsp+arg_8], rsi
0x18001737e  push    rdi
0x18001737f  sub     rsp, 40h
0x180017383  mov     esi, r9d
0x180017386  mov     edi, ecx
0x180017388  test    ecx, ecx
0x18001738a  jns     loc_180017454
0x180017390  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180017398  jz      short loc_1800173DC
0x18001739a  call    cs:__imp_GetLastError
0x1800173a1  nop     dword ptr [rax+rax+00h]
0x1800173a6  lea     r9, dword_18003572C
0x1800173ad  mov     [rsp+48h+var_20], edi
0x1800173b1  mov     [rsp+48h+var_28], r9
0x1800173b6  lea     r8, aOnecoreBaseEco_6; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x1800173bd  mov     ebx, eax
0x1800173bf  lea     rdx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x1800173c6  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800173cd  mov     r9d, esi
0x1800173d0  mov     ecx, 80000h
0x1800173d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800173da  jmp     short loc_18001741C
0x1800173dc  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800173e4  jz      short loc_18001742A
0x1800173e6  call    cs:__imp_GetLastError
0x1800173ed  nop     dword ptr [rax+rax+00h]
0x1800173f2  lea     r9, dword_18003572C
0x1800173f9  mov     dword ptr [rsp+48h+var_28], edi
0x1800173fd  mov     ebx, eax
0x1800173ff  lea     rdx, aOnecoreBaseEco_6; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180017406  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18001740d  lea     rcx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x180017414  mov     r8d, esi
0x180017417  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001741c  mov     ecx, ebx; dwErrCode
0x18001741e  call    cs:__imp_SetLastError
0x180017425  nop     dword ptr [rax+rax+00h]
0x18001742a  call    cs:__imp_GetLastError
0x180017431  nop     dword ptr [rax+rax+00h]
0x180017436  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x18001743d  mov     ebx, eax
0x18001743f  jz      short loc_180017446
0x180017441  call    ElTraceErrorInfo
0x180017446  mov     ecx, ebx; dwErrCode
0x180017448  call    cs:__imp_SetLastError
0x18001744f  nop     dword ptr [rax+rax+00h]
0x180017454  mov     rbx, [rsp+48h+arg_0]
0x180017459  mov     eax, edi
0x18001745b  mov     rsi, [rsp+48h+arg_8]
0x180017460  add     rsp, 40h
0x180017464  pop     rdi
0x180017465  retn
```
