# ElValidateWin32_3

- ea: `0x180011090`
- end: `0x180011159`
- name: `ElValidateWin32_3`
- size: `201`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800102a0`
- `0x180010b84`
- `0x180010c24`
- `0x180010c74`
- `0x180010d70`

## callees

- `0x180011090`
- `0x180017010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18001113a`
- `KERNEL32!SetLastError` at `0x18001113a`
- `KERNEL32!GetLastError` at `0x1800110b6`
- `KERNEL32!GetLastError` at `0x180011102`
- `KERNEL32!GetLastError` at `0x1800110b6`
- `KERNEL32!GetLastError` at `0x180011102`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_3(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
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
        "base\\eco\\wds\\clientapi\\lib\\src\\imgsrvpacket.cpp",
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
        "base\\eco\\wds\\clientapi\\lib\\src\\imgsrvpacket.cpp",
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
0x180011090  mov     [rsp+arg_0], rbx
0x180011095  mov     [rsp+arg_8], rsi
0x18001109a  push    rdi
0x18001109b  sub     rsp, 40h
0x18001109f  mov     esi, r9d
0x1800110a2  mov     edi, ecx
0x1800110a4  test    ecx, ecx
0x1800110a6  jz      loc_180011146
0x1800110ac  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800110b4  jz      short loc_1800110F8
0x1800110b6  call    cs:__imp_GetLastError
0x1800110bd  nop     dword ptr [rax+rax+00h]
0x1800110c2  lea     r9, dword_18001A184
0x1800110c9  mov     [rsp+48h+var_20], edi
0x1800110cd  mov     [rsp+48h+var_28], r9
0x1800110d2  lea     r8, aBaseEcoWdsClie; "base\\eco\\wds\\clientapi\\lib\\src\\im"...
0x1800110d9  mov     ebx, eax
0x1800110db  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x1800110e2  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800110e9  mov     r9d, esi
0x1800110ec  mov     ecx, 80000h
0x1800110f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110f6  jmp     short loc_180011138
0x1800110f8  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180011100  jz      short loc_180011146
0x180011102  call    cs:__imp_GetLastError
0x180011109  nop     dword ptr [rax+rax+00h]
0x18001110e  lea     r9, dword_18001A184
0x180011115  mov     dword ptr [rsp+48h+var_28], edi
0x180011119  mov     ebx, eax
0x18001111b  lea     rdx, aBaseEcoWdsClie; "base\\eco\\wds\\clientapi\\lib\\src\\im"...
0x180011122  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180011129  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180011130  mov     r8d, esi
0x180011133  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011138  mov     ecx, ebx; dwErrCode
0x18001113a  call    cs:__imp_SetLastError
0x180011141  nop     dword ptr [rax+rax+00h]
0x180011146  mov     rbx, [rsp+48h+arg_0]
0x18001114b  mov     eax, edi
0x18001114d  mov     rsi, [rsp+48h+arg_8]
0x180011152  add     rsp, 40h
0x180011156  pop     rdi
0x180011157  retn
```
