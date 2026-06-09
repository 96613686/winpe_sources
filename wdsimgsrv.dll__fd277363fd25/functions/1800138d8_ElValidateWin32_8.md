# ElValidateWin32_8

- ea: `0x1800138d8`
- end: `0x1800139a1`
- name: `ElValidateWin32_8`
- size: `201`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180013508`
- `0x180013654`
- `0x180013700`

## callees

- `0x1800138d8`
- `0x180017010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180013982`
- `KERNEL32!SetLastError` at `0x180013982`
- `KERNEL32!GetLastError` at `0x1800138fe`
- `KERNEL32!GetLastError` at `0x18001394a`
- `KERNEL32!GetLastError` at `0x1800138fe`
- `KERNEL32!GetLastError` at `0x18001394a`

## string_xrefs

- `0x18001391a`: `base\eco\wds\lib\metadata\com\wdsdevicecontrollerclient.cpp`
- `0x180013963`: `base\eco\wds\lib\metadata\com\wdsdevicecontrollerclient.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_8(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
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
        "base\\eco\\wds\\lib\\metadata\\com\\wdsdevicecontrollerclient.cpp",
        a4,
        &dword_18001A184,
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
        "base\\eco\\wds\\lib\\metadata\\com\\wdsdevicecontrollerclient.cpp",
        a4,
        &dword_18001A184,
        a1);
      goto LABEL_6;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1800138d8  mov     [rsp+arg_0], rbx
0x1800138dd  mov     [rsp+arg_8], rsi
0x1800138e2  push    rdi
0x1800138e3  sub     rsp, 40h
0x1800138e7  mov     esi, r9d
0x1800138ea  mov     edi, ecx
0x1800138ec  test    ecx, ecx
0x1800138ee  jz      loc_18001398E
0x1800138f4  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800138fc  jz      short loc_180013940
0x1800138fe  call    cs:__imp_GetLastError
0x180013905  nop     dword ptr [rax+rax+00h]
0x18001390a  lea     r9, dword_18001A184
0x180013911  mov     [rsp+48h+var_20], edi
0x180013915  mov     [rsp+48h+var_28], r9
0x18001391a  lea     r8, aBaseEcoWdsLibM_1; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180013921  mov     ebx, eax
0x180013923  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18001392a  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180013931  mov     r9d, esi
0x180013934  mov     ecx, 80000h
0x180013939  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001393e  jmp     short loc_180013980
0x180013940  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180013948  jz      short loc_18001398E
0x18001394a  call    cs:__imp_GetLastError
0x180013951  nop     dword ptr [rax+rax+00h]
0x180013956  lea     r9, dword_18001A184
0x18001395d  mov     dword ptr [rsp+48h+var_28], edi
0x180013961  mov     ebx, eax
0x180013963  lea     rdx, aBaseEcoWdsLibM_1; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18001396a  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180013971  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180013978  mov     r8d, esi
0x18001397b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013980  mov     ecx, ebx; dwErrCode
0x180013982  call    cs:__imp_SetLastError
0x180013989  nop     dword ptr [rax+rax+00h]
0x18001398e  mov     rbx, [rsp+48h+arg_0]
0x180013993  mov     eax, edi
0x180013995  mov     rsi, [rsp+48h+arg_8]
0x18001399a  add     rsp, 40h
0x18001399e  pop     rdi
0x18001399f  retn
```
