# CDlpStateXml::Serialize(void)

- ea: `0x180070950`
- end: `0x180070ba2`
- name: `?Serialize@CDlpStateXml@@QEAAJXZ`
- size: `594`
- prototype: `__int64 __fastcall(CDlpStateXml *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x1800720c4`

## callees

- `0x18000aba4`
- `0x18001fd60`
- `0x180070950`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180070a7b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180070b1c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180070a7b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180070b1c`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180070a20`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180070ac9`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180070a20`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180070ac9`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180070a9e`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180070b3b`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180070a9e`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180070b3b`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180070a43`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180070ae8`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180070a43`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180070ae8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800709cc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180070b84`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800709cc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180070b84`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800709da`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180070b92`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800709da`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180070b92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070b45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070b45`
- `UNATTEND!UnattendFreeNode` at `0x180070b6e`
- `UNATTEND!UnattendFreeNode` at `0x180070b6e`
- `UNATTEND!UnattendCtxSerializeToBuffer` at `0x1800709f7`
- `UNATTEND!UnattendCtxSerializeToBuffer` at `0x1800709f7`
- `UNATTEND!UnattendCtxPrettyPrint` at `0x1800709b7`
- `UNATTEND!UnattendCtxPrettyPrint` at `0x1800709b7`
- `UNATTEND!UnattendCtxGetRootNode` at `0x180070991`
- `UNATTEND!UnattendCtxGetRootNode` at `0x180070991`

## pseudocode

```c
__int64 __fastcall CDlpStateXml::Serialize(CDlpStateXml *this)
{
  __int64 v2; // rcx
  int RootNode; // eax
  unsigned int v4; // ebx
  __int64 v5; // rcx
  void *v6; // rbx
  HANDLE ProcessHeap; // rax
  signed int LastError; // eax
  void *v9; // rdi
  HANDLE v10; // rax
  _OWORD v12[2]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v13; // [rsp+50h] [rbp-10h]
  DWORD NumberOfBytesWritten; // [rsp+80h] [rbp+20h] BYREF
  LPVOID lpMem; // [rsp+88h] [rbp+28h] BYREF
  __int64 nNumberOfBytesToWrite; // [rsp+90h] [rbp+30h] BYREF

  lpMem = 0;
  nNumberOfBytesToWrite = 0;
  v2 = *((_QWORD *)this + 16);
  NumberOfBytesWritten = 0;
  memset(v12, 0, sizeof(v12));
  v13 = 0;
  RootNode = UnattendCtxGetRootNode(v2, v12);
  v4 = RootNode;
  if ( RootNode < 0 )
    goto LABEL_2;
  v4 = UnattendCtxPrettyPrint(*((_QWORD *)this + 16), v12, &lpMem, &nNumberOfBytesToWrite);
  if ( (v4 & 0x80000000) != 0 )
  {
    v6 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v6);
      lpMem = 0;
    }
    RootNode = UnattendCtxSerializeToBuffer(*((_QWORD *)this + 16), &lpMem, &nNumberOfBytesToWrite);
    v4 = RootNode;
    if ( RootNode < 0 )
    {
LABEL_2:
      v5 = (unsigned int)RootNode;
LABEL_20:
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
      goto LABEL_21;
    }
  }
  if ( !SetFilePointerEx(
          (HANDLE)(*((_QWORD *)this + 13) & -(__int64)(((*((_QWORD *)this + 13) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) != 0)),
          0,
          0,
          0)
    || !SetEndOfFile((HANDLE)(*((_QWORD *)this + 13)
                            & -(__int64)(((*((_QWORD *)this + 13) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) != 0)))
    || !WriteFile(
          (HANDLE)(*((_QWORD *)this + 13) & -(__int64)(((*((_QWORD *)this + 13) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) != 0)),
          lpMem,
          nNumberOfBytesToWrite,
          &NumberOfBytesWritten,
          0)
    || !FlushFileBuffers((HANDLE)(*((_QWORD *)this + 13)
                                & -(__int64)(((*((_QWORD *)this + 13) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) != 0)))
    || !SetFilePointerEx(
          (HANDLE)(*((_QWORD *)this + 14) & -(__int64)(((*((_QWORD *)this + 14) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) != 0)),
          0,
          0,
          0)
    || !SetEndOfFile((HANDLE)(*((_QWORD *)this + 14)
                            & -(__int64)(((*((_QWORD *)this + 14) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) != 0)))
    || !WriteFile(
          (HANDLE)(*((_QWORD *)this + 14) & -(__int64)(((*((_QWORD *)this + 14) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) != 0)),
          lpMem,
          nNumberOfBytesToWrite,
          &NumberOfBytesWritten,
          0)
    || !FlushFileBuffers((HANDLE)(*((_QWORD *)this + 14)
                                & -(__int64)(((*((_QWORD *)this + 14) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) != 0))) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v4 = -2147467259;
    }
    v5 = v4;
    goto LABEL_20;
  }
LABEL_21:
  UnattendFreeNode(v12);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
  v9 = lpMem;
  if ( lpMem )
  {
    v10 = GetProcessHeap();
    HeapFree(v10, 0, v9);
  }
  return v4;
}

```

## disassembly

```asm
0x180070950  push    rbp
0x180070952  push    rbx
0x180070953  push    rdi
0x180070954  mov     rbp, rsp
0x180070957  sub     rsp, 60h
0x18007095b  xorps   xmm0, xmm0
0x18007095e  mov     [rbp+lpMem], 0
0x180070966  mov     rdi, rcx
0x180070969  mov     [rbp+nNumberOfBytesToWrite], 0
0x180070971  mov     rcx, [rcx+80h]
0x180070978  lea     rdx, [rbp+var_30]
0x18007097c  xor     eax, eax
0x18007097e  mov     [rbp+NumberOfBytesWritten], 0
0x180070985  movups  [rbp+var_30], xmm0
0x180070989  mov     [rbp+var_10], rax
0x18007098d  movups  [rbp+var_20], xmm0
0x180070991  call    cs:__imp_UnattendCtxGetRootNode
0x180070997  mov     ebx, eax
0x180070999  test    eax, eax
0x18007099b  jns     short loc_1800709A4
0x18007099d  mov     ecx, eax
0x18007099f  jmp     loc_180070B65
0x1800709a4  mov     rcx, [rdi+80h]
0x1800709ab  lea     r9, [rbp+nNumberOfBytesToWrite]
0x1800709af  lea     r8, [rbp+lpMem]
0x1800709b3  lea     rdx, [rbp+var_30]
0x1800709b7  call    cs:__imp_UnattendCtxPrettyPrint
0x1800709bd  mov     ebx, eax
0x1800709bf  test    eax, eax
0x1800709c1  jns     short loc_180070A03
0x1800709c3  mov     rbx, [rbp+lpMem]
0x1800709c7  test    rbx, rbx
0x1800709ca  jz      short loc_1800709E8
0x1800709cc  call    cs:__imp_GetProcessHeap
0x1800709d2  mov     r8, rbx; lpMem
0x1800709d5  xor     edx, edx; dwFlags
0x1800709d7  mov     rcx, rax; hHeap
0x1800709da  call    cs:__imp_HeapFree
0x1800709e0  mov     [rbp+lpMem], 0
0x1800709e8  mov     rcx, [rdi+80h]
0x1800709ef  lea     r8, [rbp+nNumberOfBytesToWrite]
0x1800709f3  lea     rdx, [rbp+lpMem]
0x1800709f7  call    cs:__imp_UnattendCtxSerializeToBuffer
0x1800709fd  mov     ebx, eax
0x1800709ff  test    eax, eax
0x180070a01  js      short loc_18007099D
0x180070a03  mov     r8, [rdi+68h]
0x180070a07  xor     edx, edx; liDistanceToMove
0x180070a09  lea     rax, [r8+1]
0x180070a0d  and     rax, 0FFFFFFFFFFFFFFFEh
0x180070a11  neg     rax
0x180070a14  sbb     rcx, rcx
0x180070a17  xor     r9d, r9d; dwMoveMethod
0x180070a1a  and     rcx, r8; hFile
0x180070a1d  xor     r8d, r8d; lpNewFilePointer
0x180070a20  call    cs:__imp_SetFilePointerEx
0x180070a26  test    eax, eax
0x180070a28  jz      loc_180070B45
0x180070a2e  mov     rdx, [rdi+68h]
0x180070a32  lea     rax, [rdx+1]
0x180070a36  and     rax, 0FFFFFFFFFFFFFFFEh
0x180070a3a  neg     rax
0x180070a3d  sbb     rcx, rcx
0x180070a40  and     rcx, rdx; hFile
0x180070a43  call    cs:__imp_SetEndOfFile
0x180070a49  test    eax, eax
0x180070a4b  jz      loc_180070B45
0x180070a51  mov     r8, [rdi+68h]
0x180070a55  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180070a59  mov     rdx, [rbp+lpMem]; lpBuffer
0x180070a5d  mov     [rsp+60h+lpOverlapped], 0; lpOverlapped
0x180070a66  lea     rax, [r8+1]
0x180070a6a  and     rax, 0FFFFFFFFFFFFFFFEh
0x180070a6e  neg     rax
0x180070a71  sbb     rcx, rcx
0x180070a74  and     rcx, r8; hFile
0x180070a77  mov     r8d, dword ptr [rbp+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x180070a7b  call    cs:__imp_WriteFile
0x180070a81  test    eax, eax
0x180070a83  jz      loc_180070B45
0x180070a89  mov     rdx, [rdi+68h]
0x180070a8d  lea     rax, [rdx+1]
0x180070a91  and     rax, 0FFFFFFFFFFFFFFFEh
0x180070a95  neg     rax
0x180070a98  sbb     rcx, rcx
0x180070a9b  and     rcx, rdx; hFile
0x180070a9e  call    cs:__imp_FlushFileBuffers
0x180070aa4  test    eax, eax
0x180070aa6  jz      loc_180070B45
0x180070aac  mov     r8, [rdi+70h]
0x180070ab0  xor     edx, edx; liDistanceToMove
0x180070ab2  lea     rax, [r8+1]
0x180070ab6  and     rax, 0FFFFFFFFFFFFFFFEh
0x180070aba  neg     rax
0x180070abd  sbb     rcx, rcx
0x180070ac0  xor     r9d, r9d; dwMoveMethod
0x180070ac3  and     rcx, r8; hFile
0x180070ac6  xor     r8d, r8d; lpNewFilePointer
0x180070ac9  call    cs:__imp_SetFilePointerEx
0x180070acf  test    eax, eax
0x180070ad1  jz      short loc_180070B45
0x180070ad3  mov     rdx, [rdi+70h]
0x180070ad7  lea     rax, [rdx+1]
0x180070adb  and     rax, 0FFFFFFFFFFFFFFFEh
0x180070adf  neg     rax
0x180070ae2  sbb     rcx, rcx
0x180070ae5  and     rcx, rdx; hFile
0x180070ae8  call    cs:__imp_SetEndOfFile
0x180070aee  test    eax, eax
0x180070af0  jz      short loc_180070B45
0x180070af2  mov     r8, [rdi+70h]
0x180070af6  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180070afa  mov     rdx, [rbp+lpMem]; lpBuffer
0x180070afe  mov     [rsp+60h+lpOverlapped], 0; lpOverlapped
0x180070b07  lea     rax, [r8+1]
0x180070b0b  and     rax, 0FFFFFFFFFFFFFFFEh
0x180070b0f  neg     rax
0x180070b12  sbb     rcx, rcx
0x180070b15  and     rcx, r8; hFile
0x180070b18  mov     r8d, dword ptr [rbp+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x180070b1c  call    cs:__imp_WriteFile
0x180070b22  test    eax, eax
0x180070b24  jz      short loc_180070B45
0x180070b26  mov     rdx, [rdi+70h]
0x180070b2a  lea     rax, [rdx+1]
0x180070b2e  and     rax, 0FFFFFFFFFFFFFFFEh
0x180070b32  neg     rax
0x180070b35  sbb     rcx, rcx
0x180070b38  and     rcx, rdx; hFile
0x180070b3b  call    cs:__imp_FlushFileBuffers
0x180070b41  test    eax, eax
0x180070b43  jnz     short loc_180070B6A
0x180070b45  call    cs:__imp_GetLastError
0x180070b4b  mov     ebx, eax
0x180070b4d  test    eax, eax
0x180070b4f  jnz     short loc_180070B58
0x180070b51  mov     ebx, 80004005h
0x180070b56  jmp     short loc_180070B63
0x180070b58  jle     short loc_180070B63
0x180070b5a  movzx   ebx, ax
0x180070b5d  or      ebx, 80070000h
0x180070b63  mov     ecx, ebx
0x180070b65  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180070b6a  lea     rcx, [rbp+var_30]
0x180070b6e  call    cs:__imp_UnattendFreeNode
0x180070b74  mov     ecx, ebx
0x180070b76  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180070b7b  mov     rdi, [rbp+lpMem]
0x180070b7f  test    rdi, rdi
0x180070b82  jz      short loc_180070B98
0x180070b84  call    cs:__imp_GetProcessHeap
0x180070b8a  mov     r8, rdi; lpMem
0x180070b8d  xor     edx, edx; dwFlags
0x180070b8f  mov     rcx, rax; hHeap
0x180070b92  call    cs:__imp_HeapFree
0x180070b98  mov     eax, ebx
0x180070b9a  add     rsp, 60h
0x180070b9e  pop     rdi
0x180070b9f  pop     rbx
0x180070ba0  pop     rbp
0x180070ba1  retn
```
