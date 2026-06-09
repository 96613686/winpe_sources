# ElValidateHr_1

- ea: `0x18000f398`
- end: `0x18000f48b`
- name: `ElValidateHr_1`
- size: `243`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000e770`
- `0x18000f150`

## callees

- `0x1800063c4`
- `0x18000f398`
- `0x180030010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000f442`
- `KERNEL32!SetLastError` at `0x18000f46c`
- `KERNEL32!SetLastError` at `0x18000f442`
- `KERNEL32!SetLastError` at `0x18000f46c`
- `KERNEL32!GetLastError` at `0x18000f3be`
- `KERNEL32!GetLastError` at `0x18000f40a`
- `KERNEL32!GetLastError` at `0x18000f44e`
- `KERNEL32!GetLastError` at `0x18000f3be`
- `KERNEL32!GetLastError` at `0x18000f40a`
- `KERNEL32!GetLastError` at `0x18000f44e`

## string_xrefs

- `0x18000f3da`: `onecore\base\eco\wds\wdslib\common\src\regkey.cpp`
- `0x18000f423`: `onecore\base\eco\wds\wdslib\common\src\regkey.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateHr_1(int a1, __int64 a2, __int64 a3, unsigned int a4)
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
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\regkey.cpp",
      a4,
      &dword_1800331C4,
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
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\regkey.cpp",
      a4,
      &dword_1800331C4,
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
0x18000f398  mov     [rsp+arg_0], rbx
0x18000f39d  mov     [rsp+arg_8], rsi
0x18000f3a2  push    rdi
0x18000f3a3  sub     rsp, 40h
0x18000f3a7  mov     esi, r9d
0x18000f3aa  mov     edi, ecx
0x18000f3ac  test    ecx, ecx
0x18000f3ae  jns     loc_18000F478
0x18000f3b4  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000f3bc  jz      short loc_18000F400
0x18000f3be  call    cs:__imp_GetLastError
0x18000f3c5  nop     dword ptr [rax+rax+00h]
0x18000f3ca  lea     r9, dword_1800331C4
0x18000f3d1  mov     [rsp+48h+var_20], edi
0x18000f3d5  mov     [rsp+48h+var_28], r9
0x18000f3da  lea     r8, aOnecoreBaseEco_32; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18000f3e1  mov     ebx, eax
0x18000f3e3  lea     rdx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x18000f3ea  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000f3f1  mov     r9d, esi
0x18000f3f4  mov     ecx, 80000h
0x18000f3f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3fe  jmp     short loc_18000F440
0x18000f400  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000f408  jz      short loc_18000F44E
0x18000f40a  call    cs:__imp_GetLastError
0x18000f411  nop     dword ptr [rax+rax+00h]
0x18000f416  lea     r9, dword_1800331C4
0x18000f41d  mov     dword ptr [rsp+48h+var_28], edi
0x18000f421  mov     ebx, eax
0x18000f423  lea     rdx, aOnecoreBaseEco_32; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18000f42a  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000f431  lea     rcx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x18000f438  mov     r8d, esi
0x18000f43b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f440  mov     ecx, ebx; dwErrCode
0x18000f442  call    cs:__imp_SetLastError
0x18000f449  nop     dword ptr [rax+rax+00h]
0x18000f44e  call    cs:__imp_GetLastError
0x18000f455  nop     dword ptr [rax+rax+00h]
0x18000f45a  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x18000f461  mov     ebx, eax
0x18000f463  jz      short loc_18000F46A
0x18000f465  call    ElTraceErrorInfo
0x18000f46a  mov     ecx, ebx; dwErrCode
0x18000f46c  call    cs:__imp_SetLastError
0x18000f473  nop     dword ptr [rax+rax+00h]
0x18000f478  mov     rbx, [rsp+48h+arg_0]
0x18000f47d  mov     eax, edi
0x18000f47f  mov     rsi, [rsp+48h+arg_8]
0x18000f484  add     rsp, 40h
0x18000f488  pop     rdi
0x18000f489  retn
```
