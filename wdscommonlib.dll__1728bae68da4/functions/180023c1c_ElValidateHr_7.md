# ElValidateHr_7

- ea: `0x180023c1c`
- end: `0x180023d0f`
- name: `ElValidateHr_7`
- size: `243`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180021ce0`
- `0x180022d50`
- `0x1800235d0`
- `0x1800237f0`

## callees

- `0x180006ea4`
- `0x180023c1c`
- `0x180031010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180023cc6`
- `KERNEL32!SetLastError` at `0x180023cf0`
- `KERNEL32!SetLastError` at `0x180023cc6`
- `KERNEL32!SetLastError` at `0x180023cf0`
- `KERNEL32!GetLastError` at `0x180023c42`
- `KERNEL32!GetLastError` at `0x180023c8e`
- `KERNEL32!GetLastError` at `0x180023cd2`
- `KERNEL32!GetLastError` at `0x180023c42`
- `KERNEL32!GetLastError` at `0x180023c8e`
- `KERNEL32!GetLastError` at `0x180023cd2`

## string_xrefs

- `0x180023c5e`: `onecore\base\eco\wds\wdslib\common\src\netaddr.cpp`
- `0x180023ca7`: `onecore\base\eco\wds\wdslib\common\src\netaddr.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateHr_7(int a1, __int64 a2, __int64 a3, unsigned int a4)
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
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\netaddr.cpp",
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
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\netaddr.cpp",
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
0x180023c1c  mov     [rsp+arg_0], rbx
0x180023c21  mov     [rsp+arg_8], rsi
0x180023c26  push    rdi
0x180023c27  sub     rsp, 40h
0x180023c2b  mov     esi, r9d
0x180023c2e  mov     edi, ecx
0x180023c30  test    ecx, ecx
0x180023c32  jns     loc_180023CFC
0x180023c38  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180023c40  jz      short loc_180023C84
0x180023c42  call    cs:__imp_GetLastError
0x180023c49  nop     dword ptr [rax+rax+00h]
0x180023c4e  lea     r9, dword_18003572C
0x180023c55  mov     [rsp+48h+var_20], edi
0x180023c59  mov     [rsp+48h+var_28], r9
0x180023c5e  lea     r8, aOnecoreBaseEco_9; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180023c65  mov     ebx, eax
0x180023c67  lea     rdx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x180023c6e  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180023c75  mov     r9d, esi
0x180023c78  mov     ecx, 80000h
0x180023c7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023c82  jmp     short loc_180023CC4
0x180023c84  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180023c8c  jz      short loc_180023CD2
0x180023c8e  call    cs:__imp_GetLastError
0x180023c95  nop     dword ptr [rax+rax+00h]
0x180023c9a  lea     r9, dword_18003572C
0x180023ca1  mov     dword ptr [rsp+48h+var_28], edi
0x180023ca5  mov     ebx, eax
0x180023ca7  lea     rdx, aOnecoreBaseEco_9; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180023cae  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180023cb5  lea     rcx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x180023cbc  mov     r8d, esi
0x180023cbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023cc4  mov     ecx, ebx; dwErrCode
0x180023cc6  call    cs:__imp_SetLastError
0x180023ccd  nop     dword ptr [rax+rax+00h]
0x180023cd2  call    cs:__imp_GetLastError
0x180023cd9  nop     dword ptr [rax+rax+00h]
0x180023cde  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x180023ce5  mov     ebx, eax
0x180023ce7  jz      short loc_180023CEE
0x180023ce9  call    ElTraceErrorInfo
0x180023cee  mov     ecx, ebx; dwErrCode
0x180023cf0  call    cs:__imp_SetLastError
0x180023cf7  nop     dword ptr [rax+rax+00h]
0x180023cfc  mov     rbx, [rsp+48h+arg_0]
0x180023d01  mov     eax, edi
0x180023d03  mov     rsi, [rsp+48h+arg_8]
0x180023d08  add     rsp, 40h
0x180023d0c  pop     rdi
0x180023d0d  retn
```
