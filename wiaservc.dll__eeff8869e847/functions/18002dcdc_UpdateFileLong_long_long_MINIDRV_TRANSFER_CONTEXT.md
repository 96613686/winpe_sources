# UpdateFileLong(long,long,_MINIDRV_TRANSFER_CONTEXT *)

- ea: `0x18002dcdc`
- end: `0x18002de12`
- name: `?UpdateFileLong@@YAJJJPEAU_MINIDRV_TRANSFER_CONTEXT@@@Z`
- size: `310`
- prototype: `__int64 __fastcall(LONG lDistanceToMove, int, struct _MINIDRV_TRANSFER_CONTEXT *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, installer_update`

## callers

- `0x18002d564`

## callees

- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18002dcdc`
- `0x18002de18`
- `0x18002def8`

## import_xrefs

- `KERNEL32!WriteFile` at `0x18002dd33`
- `KERNEL32!WriteFile` at `0x18002dd33`
- `KERNEL32!GetLastError` at `0x18002dd4b`
- `KERNEL32!GetLastError` at `0x18002dd98`
- `KERNEL32!GetLastError` at `0x18002dd4b`
- `KERNEL32!GetLastError` at `0x18002dd98`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002dd07`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002dd07`

## string_xrefs

- `0x18002dd71`: `UpdateFileLong`
- `0x18002ddc1`: `UpdateFileLong`
- `0x18002ddf4`: `UpdateFileLong`
- `0x18002ddb0`: `UpdateFileLong, error 0x%X seeking to offset: %d`
- `0x18002dddb`: `UpdateFileLong, error 0x%X seeking to offset: %d`
- `0x18002dd62`: `UpdateFileLong, error writing long value 0x%X`
- `0x18002dd8a`: `UpdateFileLong, error writing long value 0x%X`

## pseudocode

```c
__int64 __fastcall UpdateFileLong(LONG lDistanceToMove, int a2, HANDLE *a3)
{
  signed int v6; // eax
  unsigned int v7; // edi
  char *v8; // rbx
  void *v9; // rdx
  void **v10; // rax
  void *v11; // rdx
  __int64 v12; // rcx
  signed int LastError; // eax
  char *v14; // rbx
  void *v15; // rdx
  int Buffer; // [rsp+48h] [rbp+10h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+50h] [rbp+18h] BYREF

  Buffer = a2;
  NumberOfBytesWritten = 0;
  if ( SetFilePointer(a3[6], lDistanceToMove, 0, 0) == -1 )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    v14 = (char *)WiaTrace_TraceLog("UpdateFileLong, error 0x%X seeking to offset: %d");
    WriteDbgTraceErrorWI("UpdateFileLong", v14);
    WiaTrcLib::Free((WiaTrcLib *)v14, v15);
    v10 = (void **)WiaTrace_Trace("UpdateFileLong, error 0x%X seeking to offset: %d", v7, lDistanceToMove);
  }
  else
  {
    if ( WriteFile(a3[6], &Buffer, 4u, &NumberOfBytesWritten, 0) && NumberOfBytesWritten == 4 )
      return 0;
    v6 = GetLastError();
    v7 = v6;
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80070000;
    v8 = (char *)WiaTrace_TraceLog("UpdateFileLong, error writing long value 0x%X");
    WriteDbgTraceErrorWI("UpdateFileLong", v8);
    WiaTrcLib::Free((WiaTrcLib *)v8, v9);
    v10 = (void **)WiaTrace_Trace("UpdateFileLong, error writing long value 0x%X", v7);
  }
  WiaTrace_ProcessTrace_Ex(v12, v11, (void *)"UpdateFileLong", 1, v10);
  return v7;
}

```

## disassembly

```asm
0x18002dcdc  mov     rax, rsp
0x18002dcdf  mov     [rax+8], rbx
0x18002dce3  mov     [rax+20h], rsi
0x18002dce7  mov     [rax+10h], edx
0x18002dcea  push    rdi
0x18002dceb  sub     rsp, 30h
0x18002dcef  mov     rbx, r8
0x18002dcf2  mov     dword ptr [rax+18h], 0
0x18002dcf9  mov     esi, ecx
0x18002dcfb  mov     edx, ecx; lDistanceToMove
0x18002dcfd  xor     r9d, r9d; dwMoveMethod
0x18002dd00  xor     r8d, r8d; lpDistanceToMoveHigh
0x18002dd03  mov     rcx, [rbx+30h]; hFile
0x18002dd07  call    cs:__imp_SetFilePointer
0x18002dd0d  cmp     eax, 0FFFFFFFFh
0x18002dd10  jz      loc_18002DD98
0x18002dd16  mov     rcx, [rbx+30h]; hFile
0x18002dd1a  lea     r9, [rsp+38h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18002dd1f  mov     r8d, 4; nNumberOfBytesToWrite
0x18002dd25  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x18002dd2e  lea     rdx, [rsp+38h+Buffer]; lpBuffer
0x18002dd33  call    cs:__imp_WriteFile
0x18002dd39  test    eax, eax
0x18002dd3b  jz      short loc_18002DD4B
0x18002dd3d  cmp     [rsp+38h+NumberOfBytesWritten], 4
0x18002dd42  jnz     short loc_18002DD4B
0x18002dd44  xor     eax, eax
0x18002dd46  jmp     loc_18002DE02
0x18002dd4b  call    cs:__imp_GetLastError
0x18002dd51  mov     edi, eax
0x18002dd53  test    eax, eax
0x18002dd55  jle     short loc_18002DD60
0x18002dd57  movzx   edi, ax
0x18002dd5a  or      edi, 80070000h
0x18002dd60  mov     edx, edi
0x18002dd62  lea     rcx, aUpdatefilelong_0; "UpdateFileLong, error writing long valu"...
0x18002dd69  call    WiaTrace_TraceLog
0x18002dd6e  mov     rdx, rax; char *
0x18002dd71  lea     rcx, aUpdatefilelong; "UpdateFileLong"
0x18002dd78  mov     rbx, rax
0x18002dd7b  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18002dd80  mov     rcx, rbx; this
0x18002dd83  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002dd88  mov     edx, edi
0x18002dd8a  lea     rcx, aUpdatefilelong_0; "UpdateFileLong, error writing long valu"...
0x18002dd91  call    WiaTrace_Trace
0x18002dd96  jmp     short loc_18002DDE9
0x18002dd98  call    cs:__imp_GetLastError
0x18002dd9e  mov     edi, eax
0x18002dda0  test    eax, eax
0x18002dda2  jle     short loc_18002DDAD
0x18002dda4  movzx   edi, ax
0x18002dda7  or      edi, 80070000h
0x18002ddad  mov     r8d, esi
0x18002ddb0  lea     rcx, aUpdatefilelong_1; "UpdateFileLong, error 0x%X seeking to o"...
0x18002ddb7  mov     edx, edi
0x18002ddb9  call    WiaTrace_TraceLog
0x18002ddbe  mov     rdx, rax; char *
0x18002ddc1  lea     rcx, aUpdatefilelong; "UpdateFileLong"
0x18002ddc8  mov     rbx, rax
0x18002ddcb  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18002ddd0  mov     rcx, rbx; this
0x18002ddd3  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002ddd8  mov     r8d, esi
0x18002dddb  lea     rcx, aUpdatefilelong_1; "UpdateFileLong, error 0x%X seeking to o"...
0x18002dde2  mov     edx, edi
0x18002dde4  call    WiaTrace_Trace
0x18002dde9  mov     r9d, 1; int
0x18002ddef  mov     [rsp+38h+lpOverlapped], rax; lpMem
0x18002ddf4  lea     r8, aUpdatefilelong; "UpdateFileLong"
0x18002ddfb  call    WiaTrace_ProcessTrace_Ex
0x18002de00  mov     eax, edi
0x18002de02  mov     rbx, [rsp+38h+arg_0]
0x18002de07  mov     rsi, [rsp+38h+arg_18]
0x18002de0c  add     rsp, 30h
0x18002de10  pop     rdi
0x18002de11  retn
```
