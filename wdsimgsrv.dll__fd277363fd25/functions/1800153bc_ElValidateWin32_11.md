# ElValidateWin32_11

- ea: `0x1800153bc`
- end: `0x180015485`
- name: `ElValidateWin32_11`
- size: `201`
- prototype: ``
- caller_count: `13`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180014d10`
- `0x180014d4c`
- `0x180014df0`
- `0x180014e2c`
- `0x180014e68`
- `0x180014f24`
- `0x180014f60`
- `0x180015094`
- `0x1800150d0`
- `0x180015134`
- `0x18001518c`
- `0x1800151c8`
- `0x1800152b4`

## callees

- `0x1800153bc`
- `0x180017010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180015466`
- `KERNEL32!SetLastError` at `0x180015466`
- `KERNEL32!GetLastError` at `0x1800153e2`
- `KERNEL32!GetLastError` at `0x18001542e`
- `KERNEL32!GetLastError` at `0x1800153e2`
- `KERNEL32!GetLastError` at `0x18001542e`

## string_xrefs

- `0x1800153fe`: `base\eco\wds\lib\metadata\com\wdsdevicecontrollerpacket.cpp`
- `0x180015447`: `base\eco\wds\lib\metadata\com\wdsdevicecontrollerpacket.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_11(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
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
        "base\\eco\\wds\\lib\\metadata\\com\\wdsdevicecontrollerpacket.cpp",
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
        "base\\eco\\wds\\lib\\metadata\\com\\wdsdevicecontrollerpacket.cpp",
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
0x1800153bc  mov     [rsp+arg_0], rbx
0x1800153c1  mov     [rsp+arg_8], rsi
0x1800153c6  push    rdi
0x1800153c7  sub     rsp, 40h
0x1800153cb  mov     esi, r9d
0x1800153ce  mov     edi, ecx
0x1800153d0  test    ecx, ecx
0x1800153d2  jz      loc_180015472
0x1800153d8  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800153e0  jz      short loc_180015424
0x1800153e2  call    cs:__imp_GetLastError
0x1800153e9  nop     dword ptr [rax+rax+00h]
0x1800153ee  lea     r9, dword_18001A184
0x1800153f5  mov     [rsp+48h+var_20], edi
0x1800153f9  mov     [rsp+48h+var_28], r9
0x1800153fe  lea     r8, aBaseEcoWdsLibM_5; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180015405  mov     ebx, eax
0x180015407  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18001540e  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180015415  mov     r9d, esi
0x180015418  mov     ecx, 80000h
0x18001541d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015422  jmp     short loc_180015464
0x180015424  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18001542c  jz      short loc_180015472
0x18001542e  call    cs:__imp_GetLastError
0x180015435  nop     dword ptr [rax+rax+00h]
0x18001543a  lea     r9, dword_18001A184
0x180015441  mov     dword ptr [rsp+48h+var_28], edi
0x180015445  mov     ebx, eax
0x180015447  lea     rdx, aBaseEcoWdsLibM_5; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18001544e  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180015455  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18001545c  mov     r8d, esi
0x18001545f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015464  mov     ecx, ebx; dwErrCode
0x180015466  call    cs:__imp_SetLastError
0x18001546d  nop     dword ptr [rax+rax+00h]
0x180015472  mov     rbx, [rsp+48h+arg_0]
0x180015477  mov     eax, edi
0x180015479  mov     rsi, [rsp+48h+arg_8]
0x18001547e  add     rsp, 40h
0x180015482  pop     rdi
0x180015483  retn
```
