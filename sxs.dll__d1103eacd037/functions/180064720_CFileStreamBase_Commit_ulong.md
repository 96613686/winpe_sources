# CFileStreamBase::Commit(ulong)

- ea: `0x180064720`
- end: `0x1800647c7`
- name: `?Commit@CFileStreamBase@@UEAAJK@Z`
- size: `167`
- prototype: `__int64 __fastcall(CFileStreamBase *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180063c20`

## callees

- `0x18000c000`
- `0x18004e3a0`
- `0x180064720`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064759`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064778`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064759`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064778`

## string_xrefs

- `0x18006472f`: `SXS.DLL: Entered CFileStreamBase::Commit()\n`
- `0x180064784`: `CFileStreamBase::Commit`
- `0x1800647a1`: `CFileStreamBase::Commit`
- `0x180064793`: `SXS.DLL: %s() failed; ::FusionpGetLastWin32Error() = %d\n`
- `0x1800647ad`: `SXS.DLL: Leaving %s()\n`

## pseudocode

```c
__int64 __fastcall CFileStreamBase::Commit(CFileStreamBase *this, int a2)
{
  signed int v5; // ebx
  signed int LastError; // eax
  DWORD v7; // eax

  FusionpDbgPrintEx(0x80000002, "SXS.DLL: Entered CFileStreamBase::Commit()\n");
  if ( a2 )
    return 2147942487LL;
  v5 = 0;
  if ( (unsigned int)CFileStreamBase::Close(this) )
    goto LABEL_8;
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
  if ( v5 >= 0 )
  {
LABEL_8:
    FusionpDbgPrintEx(0x80000002, "SXS.DLL: Leaving %s()\n", "CFileStreamBase::Commit");
  }
  else
  {
    v7 = GetLastError();
    FusionpDbgPrintEx(
      0xC0000000,
      "SXS.DLL: %s() failed; ::FusionpGetLastWin32Error() = %d\n",
      "CFileStreamBase::Commit",
      v7);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180064720  mov     [rsp+arg_0], rbx
0x180064725  push    rdi
0x180064726  sub     rsp, 20h
0x18006472a  mov     ebx, edx
0x18006472c  mov     rdi, rcx
0x18006472f  lea     rdx, aSxsDllEnteredC_1; "SXS.DLL: Entered CFileStreamBase::Commi"...
0x180064736  mov     ecx, 80000002h; unsigned int
0x18006473b  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x180064740  test    ebx, ebx
0x180064742  jz      short loc_18006474B
0x180064744  mov     eax, 80070057h
0x180064749  jmp     short loc_1800647BB
0x18006474b  mov     rcx, rdi; this
0x18006474e  xor     ebx, ebx
0x180064750  call    ?Close@CFileStreamBase@@QEAAHXZ; CFileStreamBase::Close(void)
0x180064755  test    eax, eax
0x180064757  jnz     short loc_1800647A1
0x180064759  call    cs:__imp_GetLastError
0x180064760  nop     dword ptr [rax+rax+00h]
0x180064765  mov     ebx, eax
0x180064767  test    eax, eax
0x180064769  jle     short loc_180064774
0x18006476b  movzx   ebx, ax
0x18006476e  or      ebx, 80070000h
0x180064774  test    ebx, ebx
0x180064776  jns     short loc_1800647A1
0x180064778  call    cs:__imp_GetLastError
0x18006477f  nop     dword ptr [rax+rax+00h]
0x180064784  lea     r8, aCfilestreambas_1; "CFileStreamBase::Commit"
0x18006478b  mov     ecx, 0C0000000h; unsigned int
0x180064790  mov     r9d, eax
0x180064793  lea     rdx, aSxsDllSFailedF; "SXS.DLL: %s() failed; ::FusionpGetLastW"...
0x18006479a  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x18006479f  jmp     short loc_1800647B9
0x1800647a1  lea     r8, aCfilestreambas_1; "CFileStreamBase::Commit"
0x1800647a8  mov     ecx, 80000002h; unsigned int
0x1800647ad  lea     rdx, aSxsDllLeavingS; "SXS.DLL: Leaving %s()\n"
0x1800647b4  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x1800647b9  mov     eax, ebx
0x1800647bb  mov     rbx, [rsp+28h+arg_0]
0x1800647c0  add     rsp, 20h
0x1800647c4  pop     rdi
0x1800647c5  retn
```
