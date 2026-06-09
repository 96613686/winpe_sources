# AgAlpGetReadWriteView

- ea: `0x1800707c4`
- end: `0x1800708c1`
- name: `AgAlpGetReadWriteView`
- size: `253`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, __int64, _OWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18005ee60`
- `0x1800aca00`

## callees

- `0x18004b9fc`
- `0x180052b7c`
- `0x1800707c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070894`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070894`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180070887`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007089f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180070887`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007089f`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18007087e`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18007087e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180070853`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180070853`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180070870`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180070870`

## pseudocode

```c
__int64 __fastcall AgAlpGetReadWriteView(LPCWSTR lpFileName, __int64 a2, _OWORD *a3)
{
  int i; // esi
  DWORD ViewOfFile; // eax
  DWORD LastError; // ebx
  HANDLE FileW; // rax
  void *v9; // rdi
  int v11; // [rsp+68h] [rbp+10h] BYREF

  v11 = 0;
  for ( i = 0; ; i = 1 )
  {
    ViewOfFile = PfSvGetViewOfFileEx(lpFileName, 2, a3, &v11);
    LastError = ViewOfFile;
    if ( ViewOfFile )
    {
      if ( ViewOfFile != 2 )
        return LastError;
    }
    else
    {
      if ( v11 == 334168 )
        return LastError;
      PfSvUnmapViewOfFile(a3);
      *a3 = 0;
    }
    if ( i )
      break;
    FileW = CreateFileW(lpFileName, 0xC0000000, 0, 0, 2u, 0, 0);
    v9 = FileW;
    if ( FileW == (HANDLE)-1LL )
      return LastError;
    if ( SetFilePointer(FileW, 334168, 0, 0) == -1 )
    {
      LastError = GetLastError();
      CloseHandle(v9);
      return LastError;
    }
    SetEndOfFile(v9);
    CloseHandle(v9);
  }
  return 1;
}

```

## disassembly

```asm
0x1800707c4  mov     rax, rsp
0x1800707c7  mov     [rax+8], rbx
0x1800707cb  mov     [rax+18h], rbp
0x1800707cf  mov     [rax+10h], edx
0x1800707d2  push    rsi
0x1800707d3  push    rdi
0x1800707d4  push    r14
0x1800707d6  sub     rsp, 40h
0x1800707da  mov     rbp, r8
0x1800707dd  mov     dword ptr [rax+10h], 0
0x1800707e4  mov     r14, rcx
0x1800707e7  xor     esi, esi
0x1800707e9  lea     r9, [rsp+58h+arg_8]
0x1800707ee  mov     r8, rbp
0x1800707f1  mov     edx, 2
0x1800707f6  mov     rcx, r14
0x1800707f9  call    PfSvGetViewOfFileEx
0x1800707fe  mov     ebx, eax
0x180070800  test    eax, eax
0x180070802  jnz     short loc_180070823
0x180070804  cmp     [rsp+58h+arg_8], 51958h
0x18007080c  jz      loc_1800708AC
0x180070812  mov     rcx, rbp
0x180070815  call    PfSvUnmapViewOfFile
0x18007081a  xorps   xmm0, xmm0
0x18007081d  movups  xmmword ptr [rbp+0], xmm0
0x180070821  jmp     short loc_18007082C
0x180070823  cmp     eax, 2
0x180070826  jnz     loc_1800708AC
0x18007082c  test    esi, esi
0x18007082e  jnz     short loc_1800708A7
0x180070830  mov     [rsp+58h+hTemplateFile], 0; hTemplateFile
0x180070839  xor     r9d, r9d; lpSecurityAttributes
0x18007083c  mov     [rsp+58h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x180070840  xor     r8d, r8d; dwShareMode
0x180070843  mov     edx, 0C0000000h; dwDesiredAccess
0x180070848  mov     [rsp+58h+dwCreationDisposition], 2; dwCreationDisposition
0x180070850  mov     rcx, r14; lpFileName
0x180070853  call    cs:__imp_CreateFileW
0x180070859  mov     rdi, rax
0x18007085c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180070860  jz      short loc_1800708AC
0x180070862  xor     r9d, r9d; dwMoveMethod
0x180070865  xor     r8d, r8d; lpDistanceToMoveHigh
0x180070868  mov     edx, 51958h; lDistanceToMove
0x18007086d  mov     rcx, rax; hFile
0x180070870  call    cs:__imp_SetFilePointer
0x180070876  cmp     eax, 0FFFFFFFFh
0x180070879  jz      short loc_180070894
0x18007087b  mov     rcx, rdi; hFile
0x18007087e  call    cs:__imp_SetEndOfFile
0x180070884  mov     rcx, rdi; hObject
0x180070887  call    cs:__imp_CloseHandle
0x18007088d  inc     esi
0x18007088f  jmp     loc_1800707E9
0x180070894  call    cs:__imp_GetLastError
0x18007089a  mov     ebx, eax
0x18007089c  mov     rcx, rdi; hObject
0x18007089f  call    cs:__imp_CloseHandle
0x1800708a5  jmp     short loc_1800708AC
0x1800708a7  mov     ebx, 1
0x1800708ac  mov     rbp, [rsp+58h+arg_10]
0x1800708b1  mov     eax, ebx
0x1800708b3  mov     rbx, [rsp+58h+arg_0]
0x1800708b8  add     rsp, 40h
0x1800708bc  pop     r14
0x1800708be  pop     rdi
0x1800708bf  pop     rsi
0x1800708c0  retn
```
