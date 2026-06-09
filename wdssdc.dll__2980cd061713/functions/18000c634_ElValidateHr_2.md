# ElValidateHr_2

- ea: `0x18000c634`
- end: `0x18000c727`
- name: `ElValidateHr_2`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000c4cc`

## callees

- `0x180006bf8`
- `0x18000c634`
- `0x18000d010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000c65a`
- `KERNEL32!GetLastError` at `0x18000c6a6`
- `KERNEL32!GetLastError` at `0x18000c6ea`
- `KERNEL32!GetLastError` at `0x18000c65a`
- `KERNEL32!GetLastError` at `0x18000c6a6`
- `KERNEL32!GetLastError` at `0x18000c6ea`
- `KERNEL32!SetLastError` at `0x18000c6de`
- `KERNEL32!SetLastError` at `0x18000c708`
- `KERNEL32!SetLastError` at `0x18000c6de`
- `KERNEL32!SetLastError` at `0x18000c708`

## string_xrefs

- `0x18000c676`: `base\eco\wds\lib\metadata\com\wdscommetadata.cpp`
- `0x18000c6bf`: `base\eco\wds\lib\metadata\com\wdscommetadata.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateHr_2(int a1, __int64 a2, __int64 a3, unsigned int a4)
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
      "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadata.cpp",
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
      "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadata.cpp",
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
0x18000c634  mov     [rsp+arg_0], rbx
0x18000c639  mov     [rsp+arg_8], rsi
0x18000c63e  push    rdi
0x18000c63f  sub     rsp, 40h
0x18000c643  mov     esi, r9d
0x18000c646  mov     edi, ecx
0x18000c648  test    ecx, ecx
0x18000c64a  jns     loc_18000C714
0x18000c650  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000c658  jz      short loc_18000C69C
0x18000c65a  call    cs:__imp_GetLastError
0x18000c661  nop     dword ptr [rax+rax+00h]
0x18000c666  lea     r9, qword_18000F3C0
0x18000c66d  mov     [rsp+48h+var_20], edi
0x18000c671  mov     [rsp+48h+var_28], r9
0x18000c676  lea     r8, aBaseEcoWdsLibM_2; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000c67d  mov     ebx, eax
0x18000c67f  lea     rdx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x18000c686  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000c68d  mov     r9d, esi
0x18000c690  mov     ecx, 80000h
0x18000c695  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c69a  jmp     short loc_18000C6DC
0x18000c69c  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000c6a4  jz      short loc_18000C6EA
0x18000c6a6  call    cs:__imp_GetLastError
0x18000c6ad  nop     dword ptr [rax+rax+00h]
0x18000c6b2  lea     r9, qword_18000F3C0
0x18000c6b9  mov     dword ptr [rsp+48h+var_28], edi
0x18000c6bd  mov     ebx, eax
0x18000c6bf  lea     rdx, aBaseEcoWdsLibM_2; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000c6c6  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000c6cd  lea     rcx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x18000c6d4  mov     r8d, esi
0x18000c6d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6dc  mov     ecx, ebx; dwErrCode
0x18000c6de  call    cs:__imp_SetLastError
0x18000c6e5  nop     dword ptr [rax+rax+00h]
0x18000c6ea  call    cs:__imp_GetLastError
0x18000c6f1  nop     dword ptr [rax+rax+00h]
0x18000c6f6  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x18000c6fd  mov     ebx, eax
0x18000c6ff  jz      short loc_18000C706
0x18000c701  call    ElTraceErrorInfo
0x18000c706  mov     ecx, ebx; dwErrCode
0x18000c708  call    cs:__imp_SetLastError
0x18000c70f  nop     dword ptr [rax+rax+00h]
0x18000c714  mov     rbx, [rsp+48h+arg_0]
0x18000c719  mov     eax, edi
0x18000c71b  mov     rsi, [rsp+48h+arg_8]
0x18000c720  add     rsp, 40h
0x18000c724  pop     rdi
0x18000c725  retn
```
