# ElValidateWin32_2

- ea: `0x18000c404`
- end: `0x18000c4c6`
- name: `ElValidateWin32_2`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000c344`

## callees

- `0x18000c404`
- `0x18000d010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000c422`
- `KERNEL32!GetLastError` at `0x18000c471`
- `KERNEL32!GetLastError` at `0x18000c422`
- `KERNEL32!GetLastError` at `0x18000c471`
- `KERNEL32!SetLastError` at `0x18000c4ac`
- `KERNEL32!SetLastError` at `0x18000c4ac`

## string_xrefs

- `0x18000c43e`: `base\eco\wds\lib\metadata\com\wdsdevicecontrollerclient.cpp`
- `0x18000c48a`: `base\eco\wds\lib\metadata\com\wdsdevicecontrollerclient.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_2(unsigned int a1)
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
        186,
        qword_18000F3C0,
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
        186,
        qword_18000F3C0,
        a1);
      goto LABEL_6;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18000c404  mov     [rsp+arg_0], rbx
0x18000c409  push    rdi
0x18000c40a  sub     rsp, 40h
0x18000c40e  mov     edi, ecx
0x18000c410  test    ecx, ecx
0x18000c412  jz      loc_18000C4B8
0x18000c418  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000c420  jz      short loc_18000C467
0x18000c422  call    cs:__imp_GetLastError
0x18000c429  nop     dword ptr [rax+rax+00h]
0x18000c42e  lea     r9, qword_18000F3C0
0x18000c435  mov     [rsp+48h+var_20], edi
0x18000c439  mov     [rsp+48h+var_28], r9
0x18000c43e  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000c445  mov     ebx, eax
0x18000c447  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18000c44e  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000c455  mov     r9d, 0BAh
0x18000c45b  mov     ecx, 80000h
0x18000c460  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c465  jmp     short loc_18000C4AA
0x18000c467  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000c46f  jz      short loc_18000C4B8
0x18000c471  call    cs:__imp_GetLastError
0x18000c478  nop     dword ptr [rax+rax+00h]
0x18000c47d  lea     r9, qword_18000F3C0
0x18000c484  mov     dword ptr [rsp+48h+var_28], edi
0x18000c488  mov     ebx, eax
0x18000c48a  lea     rdx, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000c491  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000c498  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18000c49f  mov     r8d, 0BAh
0x18000c4a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c4aa  mov     ecx, ebx; dwErrCode
0x18000c4ac  call    cs:__imp_SetLastError
0x18000c4b3  nop     dword ptr [rax+rax+00h]
0x18000c4b8  mov     rbx, [rsp+48h+arg_0]
0x18000c4bd  mov     eax, edi
0x18000c4bf  add     rsp, 40h
0x18000c4c3  pop     rdi
0x18000c4c4  retn
```
