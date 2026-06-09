# WritePageToMultiPageTiff(_MINIDRV_TRANSFER_CONTEXT *)

- ea: `0x18002d564`
- end: `0x18002d6dc`
- name: `?WritePageToMultiPageTiff@@YAJPEAU_MINIDRV_TRANSFER_CONTEXT@@@Z`
- size: `376`
- prototype: `__int64 __fastcall(struct _MINIDRV_TRANSFER_CONTEXT *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x18002cf80`

## callees

- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18002d564`
- `0x18002dcdc`
- `0x18002de18`
- `0x18002def8`

## import_xrefs

- `KERNEL32!WriteFile` at `0x18002d646`
- `KERNEL32!WriteFile` at `0x18002d646`
- `KERNEL32!GetLastError` at `0x18002d659`
- `KERNEL32!GetLastError` at `0x18002d659`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002d594`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002d61c`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002d594`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002d61c`

## string_xrefs

- `0x18002d670`: `wiasWriteMultiPageTiffHeader, error 0x%X writing image data`
- `0x18002d698`: `wiasWriteMultiPageTiffHeader, error 0x%X writing image data`
- `0x18002d67f`: `WritePageToMultiPageTiff`
- `0x18002d6af`: `WritePageToMultiPageTiff`

## pseudocode

```c
__int64 __fastcall WritePageToMultiPageTiff(HANDLE *a1)
{
  _DWORD *v2; // r14
  LONG v3; // r12d
  int *v4; // rsi
  int *v5; // r15
  int v6; // ecx
  __int64 result; // rax
  _DWORD *v8; // rbp
  unsigned int v9; // edi
  int v10; // eax
  DWORD v11; // r8d
  HANDLE v12; // rdx
  HANDLE v13; // rcx
  signed int LastError; // eax
  char *v15; // rbx
  void *v16; // rdx
  void **v17; // rax
  void *v18; // rdx
  __int64 v19; // rcx
  DWORD NumberOfBytesWritten; // [rsp+60h] [rbp+8h] BYREF

  NumberOfBytesWritten = 0;
  v2 = a1 + 16;
  v3 = SetFilePointer(a1[6], 0, 0, 1u);
  v4 = (int *)a1 + 33;
  v5 = (int *)(a1 + 17);
  if ( !*((_DWORD *)a1 + 32) )
  {
    v8 = a1 + 16;
LABEL_7:
    result = UpdateFileLong(
               *v4 + (*v2 != 0 ? 118 : 126),
               *((_DWORD *)a1 + 30) - *((_DWORD *)a1 + 29),
               (struct _MINIDRV_TRANSFER_CONTEXT *)a1);
    v9 = result;
    if ( (int)result >= 0 )
    {
      SetFilePointer(a1[6], v3, 0, 0);
      v10 = *v4;
      v11 = *((_DWORD *)a1 + 30);
      v12 = a1[10];
      v13 = a1[6];
      *v5 = *v4;
      *v4 = v11 + v10;
      if ( !WriteFile(v13, v12, v11, &NumberOfBytesWritten, 0) || *((_DWORD *)a1 + 30) != NumberOfBytesWritten )
      {
        LastError = GetLastError();
        v9 = LastError;
        if ( LastError > 0 )
          v9 = (unsigned __int16)LastError | 0x80070000;
        v15 = (char *)WiaTrace_TraceLog("wiasWriteMultiPageTiffHeader, error 0x%X writing image data");
        WriteDbgTraceErrorWI("WritePageToMultiPageTiff", v15);
        WiaTrcLib::Free((WiaTrcLib *)v15, v16);
        v17 = (void **)WiaTrace_Trace("wiasWriteMultiPageTiffHeader, error 0x%X writing image data", v9);
        WiaTrace_ProcessTrace_Ex(v19, v18, (void *)"WritePageToMultiPageTiff", 1, v17);
      }
      *v2 = *v8 + 1;
      return v9;
    }
    return result;
  }
  v6 = 166;
  if ( *v2 != 1 )
    v6 = 158;
  result = UpdateFileLong(*v5 + v6, *v4, (struct _MINIDRV_TRANSFER_CONTEXT *)a1);
  if ( (int)result >= 0 )
  {
    v8 = a1 + 16;
    goto LABEL_7;
  }
  return result;
}

```

## disassembly

```asm
0x18002d564  mov     [rsp+arg_8], rbx
0x18002d569  mov     [rsp+arg_10], rbp
0x18002d56e  push    rsi
0x18002d56f  push    rdi
0x18002d570  push    r12
0x18002d572  push    r14
0x18002d574  push    r15
0x18002d576  sub     rsp, 30h
0x18002d57a  mov     rbx, rcx
0x18002d57d  mov     [rsp+58h+NumberOfBytesWritten], 0
0x18002d585  mov     rcx, [rcx+30h]; hFile
0x18002d589  mov     r9d, 1; dwMoveMethod
0x18002d58f  xor     r8d, r8d; lpDistanceToMoveHigh
0x18002d592  xor     edx, edx; lDistanceToMove
0x18002d594  call    cs:__imp_SetFilePointer
0x18002d59a  lea     r14, [rbx+80h]
0x18002d5a1  mov     r12d, eax
0x18002d5a4  cmp     dword ptr [r14], 0
0x18002d5a8  lea     rsi, [rbx+84h]
0x18002d5af  lea     r15, [rbx+88h]
0x18002d5b6  jz      short loc_18002D5E5
0x18002d5b8  cmp     dword ptr [r14], 1
0x18002d5bc  mov     ecx, 0A6h
0x18002d5c1  mov     edx, [rsi]; int
0x18002d5c3  mov     r8, rbx; struct _MINIDRV_TRANSFER_CONTEXT *
0x18002d5c6  lea     eax, [rcx-8]
0x18002d5c9  cmovnz  ecx, eax
0x18002d5cc  add     ecx, [r15]; lDistanceToMove
0x18002d5cf  call    ?UpdateFileLong@@YAJJJPEAU_MINIDRV_TRANSFER_CONTEXT@@@Z; UpdateFileLong(long,long,_MINIDRV_TRANSFER_CONTEXT *)
0x18002d5d4  test    eax, eax
0x18002d5d6  js      loc_18002D6C5
0x18002d5dc  lea     rbp, [rbx+80h]
0x18002d5e3  jmp     short loc_18002D5E8
0x18002d5e5  mov     rbp, r14
0x18002d5e8  mov     edx, [rbx+78h]
0x18002d5eb  mov     r8, rbx; struct _MINIDRV_TRANSFER_CONTEXT *
0x18002d5ee  sub     edx, [rbx+74h]; int
0x18002d5f1  mov     eax, [r14]
0x18002d5f4  neg     eax
0x18002d5f6  sbb     ecx, ecx
0x18002d5f8  and     ecx, 0FFFFFFF8h
0x18002d5fb  add     ecx, 7Eh ; '~'
0x18002d5fe  add     ecx, [rsi]; lDistanceToMove
0x18002d600  call    ?UpdateFileLong@@YAJJJPEAU_MINIDRV_TRANSFER_CONTEXT@@@Z; UpdateFileLong(long,long,_MINIDRV_TRANSFER_CONTEXT *)
0x18002d605  mov     edi, eax
0x18002d607  test    eax, eax
0x18002d609  js      loc_18002D6C5
0x18002d60f  mov     rcx, [rbx+30h]; hFile
0x18002d613  xor     r9d, r9d; dwMoveMethod
0x18002d616  xor     r8d, r8d; lpDistanceToMoveHigh
0x18002d619  mov     edx, r12d; lDistanceToMove
0x18002d61c  call    cs:__imp_SetFilePointer
0x18002d622  mov     eax, [rsi]
0x18002d624  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18002d629  mov     r8d, [rbx+78h]; nNumberOfBytesToWrite
0x18002d62d  mov     rdx, [rbx+50h]; lpBuffer
0x18002d631  mov     rcx, [rbx+30h]; hFile
0x18002d635  mov     [r15], eax
0x18002d638  add     eax, r8d
0x18002d63b  mov     [rsi], eax
0x18002d63d  mov     [rsp+58h+lpOverlapped], 0; lpOverlapped
0x18002d646  call    cs:__imp_WriteFile
0x18002d64c  test    eax, eax
0x18002d64e  jz      short loc_18002D659
0x18002d650  mov     eax, [rsp+58h+NumberOfBytesWritten]
0x18002d654  cmp     [rbx+78h], eax
0x18002d657  jz      short loc_18002D6BB
0x18002d659  call    cs:__imp_GetLastError
0x18002d65f  mov     edi, eax
0x18002d661  test    eax, eax
0x18002d663  jle     short loc_18002D66E
0x18002d665  movzx   edi, ax
0x18002d668  or      edi, 80070000h
0x18002d66e  mov     edx, edi
0x18002d670  lea     rcx, aWiaswritemulti_2; "wiasWriteMultiPageTiffHeader, error 0x%"...
0x18002d677  call    WiaTrace_TraceLog
0x18002d67c  mov     rdx, rax; char *
0x18002d67f  lea     rcx, aWritepagetomul_0; "WritePageToMultiPageTiff"
0x18002d686  mov     rbx, rax
0x18002d689  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18002d68e  mov     rcx, rbx; this
0x18002d691  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002d696  mov     edx, edi
0x18002d698  lea     rcx, aWiaswritemulti_2; "wiasWriteMultiPageTiffHeader, error 0x%"...
0x18002d69f  call    WiaTrace_Trace
0x18002d6a4  mov     r9d, 1; int
0x18002d6aa  mov     [rsp+58h+lpOverlapped], rax; lpMem
0x18002d6af  lea     r8, aWritepagetomul_0; "WritePageToMultiPageTiff"
0x18002d6b6  call    WiaTrace_ProcessTrace_Ex
0x18002d6bb  mov     eax, [rbp+0]
0x18002d6be  inc     eax
0x18002d6c0  mov     [r14], eax
0x18002d6c3  mov     eax, edi
0x18002d6c5  mov     rbx, [rsp+58h+arg_8]
0x18002d6ca  mov     rbp, [rsp+58h+arg_10]
0x18002d6cf  add     rsp, 30h
0x18002d6d3  pop     r15
0x18002d6d5  pop     r14
0x18002d6d7  pop     r12
0x18002d6d9  pop     rdi
0x18002d6da  pop     rsi
0x18002d6db  retn
```
