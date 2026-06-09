# ElValidateWin32_7

- ea: `0x1800132c4`
- end: `0x18001338d`
- name: `ElValidateWin32_7`
- size: `201`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180012890`
- `0x180012a18`
- `0x180012b5c`
- `0x180012c20`
- `0x180012d80`
- `0x180013030`
- `0x180013170`

## callees

- `0x1800132c4`
- `0x180017010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18001336e`
- `KERNEL32!SetLastError` at `0x18001336e`
- `KERNEL32!GetLastError` at `0x1800132ea`
- `KERNEL32!GetLastError` at `0x180013336`
- `KERNEL32!GetLastError` at `0x1800132ea`
- `KERNEL32!GetLastError` at `0x180013336`

## string_xrefs

- `0x180013306`: `base\eco\wds\lib\metadata\com\wdsmetadatastoremanagementclient.cpp`
- `0x18001334f`: `base\eco\wds\lib\metadata\com\wdsmetadatastoremanagementclient.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_7(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
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
        "base\\eco\\wds\\lib\\metadata\\com\\wdsmetadatastoremanagementclient.cpp",
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
        "base\\eco\\wds\\lib\\metadata\\com\\wdsmetadatastoremanagementclient.cpp",
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
0x1800132c4  mov     [rsp+arg_0], rbx
0x1800132c9  mov     [rsp+arg_8], rsi
0x1800132ce  push    rdi
0x1800132cf  sub     rsp, 40h
0x1800132d3  mov     esi, r9d
0x1800132d6  mov     edi, ecx
0x1800132d8  test    ecx, ecx
0x1800132da  jz      loc_18001337A
0x1800132e0  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800132e8  jz      short loc_18001332C
0x1800132ea  call    cs:__imp_GetLastError
0x1800132f1  nop     dword ptr [rax+rax+00h]
0x1800132f6  lea     r9, dword_18001A184
0x1800132fd  mov     [rsp+48h+var_20], edi
0x180013301  mov     [rsp+48h+var_28], r9
0x180013306  lea     r8, aBaseEcoWdsLibM_2; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18001330d  mov     ebx, eax
0x18001330f  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180013316  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18001331d  mov     r9d, esi
0x180013320  mov     ecx, 80000h
0x180013325  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001332a  jmp     short loc_18001336C
0x18001332c  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180013334  jz      short loc_18001337A
0x180013336  call    cs:__imp_GetLastError
0x18001333d  nop     dword ptr [rax+rax+00h]
0x180013342  lea     r9, dword_18001A184
0x180013349  mov     dword ptr [rsp+48h+var_28], edi
0x18001334d  mov     ebx, eax
0x18001334f  lea     rdx, aBaseEcoWdsLibM_2; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180013356  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18001335d  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180013364  mov     r8d, esi
0x180013367  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001336c  mov     ecx, ebx; dwErrCode
0x18001336e  call    cs:__imp_SetLastError
0x180013375  nop     dword ptr [rax+rax+00h]
0x18001337a  mov     rbx, [rsp+48h+arg_0]
0x18001337f  mov     eax, edi
0x180013381  mov     rsi, [rsp+48h+arg_8]
0x180013386  add     rsp, 40h
0x18001338a  pop     rdi
0x18001338b  retn
```
