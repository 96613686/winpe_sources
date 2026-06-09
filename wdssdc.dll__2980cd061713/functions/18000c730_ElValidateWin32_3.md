# ElValidateWin32_3

- ea: `0x18000c730`
- end: `0x18000c7f2`
- name: `ElValidateWin32_3`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000c4cc`

## callees

- `0x18000c730`
- `0x18000d010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000c74e`
- `KERNEL32!GetLastError` at `0x18000c79d`
- `KERNEL32!GetLastError` at `0x18000c74e`
- `KERNEL32!GetLastError` at `0x18000c79d`
- `KERNEL32!SetLastError` at `0x18000c7d8`
- `KERNEL32!SetLastError` at `0x18000c7d8`

## string_xrefs

- `0x18000c76a`: `base\eco\wds\lib\metadata\com\wdscommetadata.cpp`
- `0x18000c7b6`: `base\eco\wds\lib\metadata\com\wdscommetadata.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_3(unsigned int a1)
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
        "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadata.cpp",
        160,
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
        "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadata.cpp",
        160,
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
0x18000c730  mov     [rsp+arg_0], rbx
0x18000c735  push    rdi
0x18000c736  sub     rsp, 40h
0x18000c73a  mov     edi, ecx
0x18000c73c  test    ecx, ecx
0x18000c73e  jz      loc_18000C7E4
0x18000c744  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000c74c  jz      short loc_18000C793
0x18000c74e  call    cs:__imp_GetLastError
0x18000c755  nop     dword ptr [rax+rax+00h]
0x18000c75a  lea     r9, qword_18000F3C0
0x18000c761  mov     [rsp+48h+var_20], edi
0x18000c765  mov     [rsp+48h+var_28], r9
0x18000c76a  lea     r8, aBaseEcoWdsLibM_2; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000c771  mov     ebx, eax
0x18000c773  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18000c77a  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000c781  mov     r9d, 0A0h
0x18000c787  mov     ecx, 80000h
0x18000c78c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c791  jmp     short loc_18000C7D6
0x18000c793  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000c79b  jz      short loc_18000C7E4
0x18000c79d  call    cs:__imp_GetLastError
0x18000c7a4  nop     dword ptr [rax+rax+00h]
0x18000c7a9  lea     r9, qword_18000F3C0
0x18000c7b0  mov     dword ptr [rsp+48h+var_28], edi
0x18000c7b4  mov     ebx, eax
0x18000c7b6  lea     rdx, aBaseEcoWdsLibM_2; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000c7bd  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000c7c4  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18000c7cb  mov     r8d, 0A0h
0x18000c7d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7d6  mov     ecx, ebx; dwErrCode
0x18000c7d8  call    cs:__imp_SetLastError
0x18000c7df  nop     dword ptr [rax+rax+00h]
0x18000c7e4  mov     rbx, [rsp+48h+arg_0]
0x18000c7e9  mov     eax, edi
0x18000c7eb  add     rsp, 40h
0x18000c7ef  pop     rdi
0x18000c7f0  retn
```
