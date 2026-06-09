# ElValidateHr_0

- ea: `0x180003c68`
- end: `0x180003d5b`
- name: `ElValidateHr_0`
- size: `243`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `52`
- callee_count: `3`
- tags: ``

## callers

- `0x180003e40`
- `0x180003eb0`
- `0x180003f40`
- `0x180003ff0`
- `0x1800041a0`
- `0x180004230`
- `0x1800042d0`
- `0x180004320`
- `0x1800043d0`
- `0x180004530`
- `0x180004600`
- `0x180004690`
- `0x180004710`
- `0x180004790`
- `0x180004830`
- `0x1800048d0`
- `0x180004950`
- `0x1800049d0`
- `0x180004a70`
- `0x180004af0`
- `0x180004b90`
- `0x180004c10`
- `0x180004ca0`
- `0x180004d20`
- `0x180004da0`
- `0x180004e40`
- `0x180004ee0`
- `0x180004f60`
- `0x180005000`
- `0x180005080`
- `0x180005120`
- `0x1800051c0`
- `0x180005250`
- `0x1800052e0`
- `0x180005380`
- `0x180005410`
- `0x1800054b0`
- `0x180005540`
- `0x1800055e0`
- `0x180005680`
- `0x180005810`
- `0x1800058a0`
- `0x180005920`
- `0x180005a90`
- `0x180005ad0`
- `0x180005d20`
- `0x180005d70`
- `0x180005e10`
- `0x180005ea0`
- `0x180005f40`

## callees

- `0x180003130`
- `0x180003c68`
- `0x180011010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180003c8e`
- `KERNEL32!GetLastError` at `0x180003cda`
- `KERNEL32!GetLastError` at `0x180003d1e`
- `KERNEL32!GetLastError` at `0x180003c8e`
- `KERNEL32!GetLastError` at `0x180003cda`
- `KERNEL32!GetLastError` at `0x180003d1e`
- `KERNEL32!SetLastError` at `0x180003d12`
- `KERNEL32!SetLastError` at `0x180003d3c`
- `KERNEL32!SetLastError` at `0x180003d12`
- `KERNEL32!SetLastError` at `0x180003d3c`

## pseudocode

```c
__int64 __fastcall ElValidateHr_0(int a1, __int64 a2, __int64 a3, unsigned int a4)
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
      "base\\eco\\wds\\wdsimage\\src\\imageapis.cpp",
      a4,
      &word_180013F66,
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
      "base\\eco\\wds\\wdsimage\\src\\imageapis.cpp",
      a4,
      &word_180013F66,
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
0x180003c68  mov     [rsp+arg_0], rbx
0x180003c6d  mov     [rsp+arg_8], rsi
0x180003c72  push    rdi
0x180003c73  sub     rsp, 40h
0x180003c77  mov     esi, r9d
0x180003c7a  mov     edi, ecx
0x180003c7c  test    ecx, ecx
0x180003c7e  jns     loc_180003D48
0x180003c84  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180003c8c  jz      short loc_180003CD0
0x180003c8e  call    cs:__imp_GetLastError
0x180003c95  nop     dword ptr [rax+rax+00h]
0x180003c9a  lea     r9, word_180013F66
0x180003ca1  mov     [rsp+48h+var_20], edi
0x180003ca5  mov     [rsp+48h+var_28], r9
0x180003caa  lea     r8, aBaseEcoWdsWdsi_1; "base\\eco\\wds\\wdsimage\\src\\imageapi"...
0x180003cb1  mov     ebx, eax
0x180003cb3  lea     rdx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x180003cba  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180003cc1  mov     r9d, esi
0x180003cc4  mov     ecx, 80000h
0x180003cc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cce  jmp     short loc_180003D10
0x180003cd0  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180003cd8  jz      short loc_180003D1E
0x180003cda  call    cs:__imp_GetLastError
0x180003ce1  nop     dword ptr [rax+rax+00h]
0x180003ce6  lea     r9, word_180013F66
0x180003ced  mov     dword ptr [rsp+48h+var_28], edi
0x180003cf1  mov     ebx, eax
0x180003cf3  lea     rdx, aBaseEcoWdsWdsi_1; "base\\eco\\wds\\wdsimage\\src\\imageapi"...
0x180003cfa  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180003d01  lea     rcx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x180003d08  mov     r8d, esi
0x180003d0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d10  mov     ecx, ebx; dwErrCode
0x180003d12  call    cs:__imp_SetLastError
0x180003d19  nop     dword ptr [rax+rax+00h]
0x180003d1e  call    cs:__imp_GetLastError
0x180003d25  nop     dword ptr [rax+rax+00h]
0x180003d2a  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x180003d31  mov     ebx, eax
0x180003d33  jz      short loc_180003D3A
0x180003d35  call    ElTraceErrorInfo
0x180003d3a  mov     ecx, ebx; dwErrCode
0x180003d3c  call    cs:__imp_SetLastError
0x180003d43  nop     dword ptr [rax+rax+00h]
0x180003d48  mov     rbx, [rsp+48h+arg_0]
0x180003d4d  mov     eax, edi
0x180003d4f  mov     rsi, [rsp+48h+arg_8]
0x180003d54  add     rsp, 40h
0x180003d58  pop     rdi
0x180003d59  retn
```
