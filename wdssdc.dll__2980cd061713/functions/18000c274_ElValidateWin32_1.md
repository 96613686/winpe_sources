# ElValidateWin32_1

- ea: `0x18000c274`
- end: `0x18000c33d`
- name: `ElValidateWin32_1`
- size: `201`
- prototype: ``
- caller_count: `31`
- callee_count: `2`
- tags: ``

## callers

- `0x180008da0`
- `0x180008ec0`
- `0x180008f70`
- `0x18000906c`
- `0x180009194`
- `0x180009390`
- `0x1800093e0`
- `0x180009554`
- `0x180009714`
- `0x180009770`
- `0x1800098a4`
- `0x180009990`
- `0x180009ba8`
- `0x180009e70`
- `0x180009fd0`
- `0x18000a108`
- `0x18000a598`
- `0x18000a6a0`
- `0x18000a980`
- `0x18000ab24`
- `0x18000ac28`
- `0x18000ae80`
- `0x18000b160`
- `0x18000b58c`
- `0x18000b6d4`
- `0x18000b8ec`
- `0x18000b960`
- `0x18000ba40`
- `0x18000bb58`
- `0x18000bc94`
- `0x18000c0b0`

## callees

- `0x18000c274`
- `0x18000d010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000c29a`
- `KERNEL32!GetLastError` at `0x18000c2e6`
- `KERNEL32!GetLastError` at `0x18000c29a`
- `KERNEL32!GetLastError` at `0x18000c2e6`
- `KERNEL32!SetLastError` at `0x18000c31e`
- `KERNEL32!SetLastError` at `0x18000c31e`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_1(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
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
        "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp",
        a4,
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
        "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp",
        a4,
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
0x18000c274  mov     [rsp+arg_0], rbx
0x18000c279  mov     [rsp+arg_8], rsi
0x18000c27e  push    rdi
0x18000c27f  sub     rsp, 40h
0x18000c283  mov     esi, r9d
0x18000c286  mov     edi, ecx
0x18000c288  test    ecx, ecx
0x18000c28a  jz      loc_18000C32A
0x18000c290  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000c298  jz      short loc_18000C2DC
0x18000c29a  call    cs:__imp_GetLastError
0x18000c2a1  nop     dword ptr [rax+rax+00h]
0x18000c2a6  lea     r9, qword_18000F3C0
0x18000c2ad  mov     [rsp+48h+var_20], edi
0x18000c2b1  mov     [rsp+48h+var_28], r9
0x18000c2b6  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x18000c2bd  mov     ebx, eax
0x18000c2bf  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18000c2c6  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000c2cd  mov     r9d, esi
0x18000c2d0  mov     ecx, 80000h
0x18000c2d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2da  jmp     short loc_18000C31C
0x18000c2dc  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000c2e4  jz      short loc_18000C32A
0x18000c2e6  call    cs:__imp_GetLastError
0x18000c2ed  nop     dword ptr [rax+rax+00h]
0x18000c2f2  lea     r9, qword_18000F3C0
0x18000c2f9  mov     dword ptr [rsp+48h+var_28], edi
0x18000c2fd  mov     ebx, eax
0x18000c2ff  lea     rdx, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x18000c306  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000c30d  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18000c314  mov     r8d, esi
0x18000c317  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c31c  mov     ecx, ebx; dwErrCode
0x18000c31e  call    cs:__imp_SetLastError
0x18000c325  nop     dword ptr [rax+rax+00h]
0x18000c32a  mov     rbx, [rsp+48h+arg_0]
0x18000c32f  mov     eax, edi
0x18000c331  mov     rsi, [rsp+48h+arg_8]
0x18000c336  add     rsp, 40h
0x18000c33a  pop     rdi
0x18000c33b  retn
```
