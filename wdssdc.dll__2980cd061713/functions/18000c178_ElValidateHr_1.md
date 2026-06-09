# ElValidateHr_1

- ea: `0x18000c178`
- end: `0x18000c26b`
- name: `ElValidateHr_1`
- size: `243`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180008f70`
- `0x18000a108`
- `0x18000bf70`

## callees

- `0x180006bf8`
- `0x18000c178`
- `0x18000d010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000c19e`
- `KERNEL32!GetLastError` at `0x18000c1ea`
- `KERNEL32!GetLastError` at `0x18000c22e`
- `KERNEL32!GetLastError` at `0x18000c19e`
- `KERNEL32!GetLastError` at `0x18000c1ea`
- `KERNEL32!GetLastError` at `0x18000c22e`
- `KERNEL32!SetLastError` at `0x18000c222`
- `KERNEL32!SetLastError` at `0x18000c24c`
- `KERNEL32!SetLastError` at `0x18000c222`
- `KERNEL32!SetLastError` at `0x18000c24c`

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
      "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp",
      a4,
      qword_18000F3C0,
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
      "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp",
      a4,
      qword_18000F3C0,
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
0x18000c178  mov     [rsp+arg_0], rbx
0x18000c17d  mov     [rsp+arg_8], rsi
0x18000c182  push    rdi
0x18000c183  sub     rsp, 40h
0x18000c187  mov     esi, r9d
0x18000c18a  mov     edi, ecx
0x18000c18c  test    ecx, ecx
0x18000c18e  jns     loc_18000C258
0x18000c194  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000c19c  jz      short loc_18000C1E0
0x18000c19e  call    cs:__imp_GetLastError
0x18000c1a5  nop     dword ptr [rax+rax+00h]
0x18000c1aa  lea     r9, qword_18000F3C0
0x18000c1b1  mov     [rsp+48h+var_20], edi
0x18000c1b5  mov     [rsp+48h+var_28], r9
0x18000c1ba  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x18000c1c1  mov     ebx, eax
0x18000c1c3  lea     rdx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x18000c1ca  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000c1d1  mov     r9d, esi
0x18000c1d4  mov     ecx, 80000h
0x18000c1d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1de  jmp     short loc_18000C220
0x18000c1e0  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000c1e8  jz      short loc_18000C22E
0x18000c1ea  call    cs:__imp_GetLastError
0x18000c1f1  nop     dword ptr [rax+rax+00h]
0x18000c1f6  lea     r9, qword_18000F3C0
0x18000c1fd  mov     dword ptr [rsp+48h+var_28], edi
0x18000c201  mov     ebx, eax
0x18000c203  lea     rdx, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x18000c20a  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000c211  lea     rcx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x18000c218  mov     r8d, esi
0x18000c21b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c220  mov     ecx, ebx; dwErrCode
0x18000c222  call    cs:__imp_SetLastError
0x18000c229  nop     dword ptr [rax+rax+00h]
0x18000c22e  call    cs:__imp_GetLastError
0x18000c235  nop     dword ptr [rax+rax+00h]
0x18000c23a  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x18000c241  mov     ebx, eax
0x18000c243  jz      short loc_18000C24A
0x18000c245  call    ElTraceErrorInfo
0x18000c24a  mov     ecx, ebx; dwErrCode
0x18000c24c  call    cs:__imp_SetLastError
0x18000c253  nop     dword ptr [rax+rax+00h]
0x18000c258  mov     rbx, [rsp+48h+arg_0]
0x18000c25d  mov     eax, edi
0x18000c25f  mov     rsi, [rsp+48h+arg_8]
0x18000c264  add     rsp, 40h
0x18000c268  pop     rdi
0x18000c269  retn
```
