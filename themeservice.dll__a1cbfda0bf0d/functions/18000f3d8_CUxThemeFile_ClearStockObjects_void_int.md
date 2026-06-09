# CUxThemeFile::ClearStockObjects(void *,int)

- ea: `0x18000f3d8`
- end: `0x18000f5d7`
- name: `?ClearStockObjects@CUxThemeFile@@SAJPEAXH@Z`
- size: `511`
- prototype: `__int64 __fastcall(HANDLE hFileMappingObject)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18000f5e0`

## callees

- `0x180002ae0`
- `0x18000f3d8`
- `0x18000f67c`
- `0x18000fa00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000f53d`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000f53d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f4b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f546`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f4b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f546`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000f430`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000f439`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000f430`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000f439`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000f501`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000f501`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f596`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f5af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f596`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f5af`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000f461`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000f461`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000f59f`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000f59f`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000f41e`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000f481`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000f4a5`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000f41e`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000f481`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000f4a5`

## pseudocode

```c
__int64 __fastcall CUxThemeFile::ClearStockObjects(HANDLE hFileMappingObject)
{
  char v2; // r15
  _DWORD *v3; // rbx
  HANDLE CurrentProcess; // rbx
  HANDLE v5; // rax
  signed int v6; // eax
  unsigned int v7; // edi
  __int64 CurrentProcessId; // r9
  ULONG SessionId; // esi
  const unsigned __int16 *v10; // r8
  HANDLE Semaphore; // r14
  DWORD LastError; // eax
  HBITMAP *v13; // rsi
  HBITMAP *v14; // rbp
  SIZE_T dwNumberOfBytesToMap; // [rsp+20h] [rbp-F8h]
  HANDLE TargetHandle; // [rsp+40h] [rbp-D8h] BYREF
  WCHAR Name[64]; // [rsp+50h] [rbp-C8h] BYREF

  TargetHandle = 0;
  v2 = 1;
  v3 = MapViewOfFile(hFileMappingObject, 2u, 0, 0, 0);
  if ( v3
    || (CurrentProcess = GetCurrentProcess(),
        v5 = GetCurrentProcess(),
        DuplicateHandle(v5, hFileMappingObject, CurrentProcess, &TargetHandle, 2u, 0, 0))
    && (v3 = MapViewOfFile(TargetHandle, 2u, 0, 0, 0)) != 0
    || (v2 = 0, (v3 = MapViewOfFile(hFileMappingObject, 4u, 0, 0, 0)) != 0) )
  {
    v7 = 0;
    if ( (*v3 & 4) != 0 )
    {
      CurrentProcessId = (unsigned int)v3[1];
      SessionId = NtCurrentPeb()->SessionId;
      if ( (_DWORD)CurrentProcessId )
      {
        v10 = L"Global\\ClearStockGlobal%d-%d";
      }
      else
      {
        CurrentProcessId = GetCurrentProcessId();
        v10 = L"ClearStockLocal%d-%d";
      }
      LODWORD(dwNumberOfBytesToMap) = SessionId;
      StringCchPrintfW(Name, 0x40u, v10, CurrentProcessId, dwNumberOfBytesToMap);
      Semaphore = CreateSemaphoreExW(0, 0, 1, Name, 0, 0x1F0003u);
      LastError = GetLastError();
      if ( LastError != 183 && LastError != 5 && (*v3 & 4) != 0 )
      {
        v13 = (HBITMAP *)((char *)v3 + (int)v3[3]);
        v14 = &v13[v3[2]];
        while ( v13 < v14 )
        {
          if ( *v13 )
            CUxThemeFile::DeleteStockBitmap(*v13);
          ++v13;
        }
        if ( v2 )
          *v3 &= ~4u;
      }
      if ( Semaphore )
        CloseHandle(Semaphore);
    }
    UnmapViewOfFile(v3);
  }
  else
  {
    v6 = GetLastError();
    v7 = v6;
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80070000;
  }
  if ( TargetHandle )
    CloseHandle(TargetHandle);
  return v7;
}

```

## disassembly

```asm
0x18000f3d8  push    rbx
0x18000f3da  push    rbp
0x18000f3db  push    rsi
0x18000f3dc  push    rdi
0x18000f3dd  push    r14
0x18000f3df  push    r15
0x18000f3e1  sub     rsp, 0E8h
0x18000f3e8  mov     rax, cs:__security_cookie
0x18000f3ef  xor     rax, rsp
0x18000f3f2  mov     [rsp+118h+var_48], rax
0x18000f3fa  xor     r9d, r9d; dwFileOffsetLow
0x18000f3fd  mov     [rsp+118h+TargetHandle], 0
0x18000f406  xor     r8d, r8d; dwFileOffsetHigh
0x18000f409  mov     [rsp+118h+dwNumberOfBytesToMap], 0; dwNumberOfBytesToMap
0x18000f412  mov     rdi, rcx
0x18000f415  mov     r15b, 1
0x18000f418  lea     esi, [r9+2]
0x18000f41c  mov     edx, esi; dwDesiredAccess
0x18000f41e  call    cs:__imp_MapViewOfFile
0x18000f424  mov     rbx, rax
0x18000f427  test    rax, rax
0x18000f42a  jnz     loc_18000F4D4
0x18000f430  call    cs:__imp_GetCurrentProcess
0x18000f436  mov     rbx, rax
0x18000f439  call    cs:__imp_GetCurrentProcess
0x18000f43f  mov     [rsp+118h+dwOptions], 0; dwOptions
0x18000f447  lea     r9, [rsp+118h+TargetHandle]; lpTargetHandle
0x18000f44c  mov     rcx, rax; hSourceProcessHandle
0x18000f44f  mov     [rsp+118h+bInheritHandle], 0; bInheritHandle
0x18000f457  mov     r8, rbx; hTargetProcessHandle
0x18000f45a  mov     dword ptr [rsp+118h+dwNumberOfBytesToMap], esi; dwDesiredAccess
0x18000f45e  mov     rdx, rdi; hSourceHandle
0x18000f461  call    cs:__imp_DuplicateHandle
0x18000f467  test    eax, eax
0x18000f469  jz      short loc_18000F48F
0x18000f46b  mov     rcx, [rsp+118h+TargetHandle]; hFileMappingObject
0x18000f470  xor     r9d, r9d; dwFileOffsetLow
0x18000f473  xor     r8d, r8d; dwFileOffsetHigh
0x18000f476  mov     [rsp+118h+dwNumberOfBytesToMap], 0; dwNumberOfBytesToMap
0x18000f47f  mov     edx, esi; dwDesiredAccess
0x18000f481  call    cs:__imp_MapViewOfFile
0x18000f487  mov     rbx, rax
0x18000f48a  test    rax, rax
0x18000f48d  jnz     short loc_18000F4D4
0x18000f48f  xor     r9d, r9d; dwFileOffsetLow
0x18000f492  mov     [rsp+118h+dwNumberOfBytesToMap], 0; dwNumberOfBytesToMap
0x18000f49b  xor     r8d, r8d; dwFileOffsetHigh
0x18000f49e  mov     rcx, rdi; hFileMappingObject
0x18000f4a1  lea     edx, [r9+4]; dwDesiredAccess
0x18000f4a5  call    cs:__imp_MapViewOfFile
0x18000f4ab  xor     r15b, r15b
0x18000f4ae  mov     rbx, rax
0x18000f4b1  test    rax, rax
0x18000f4b4  jnz     short loc_18000F4D4
0x18000f4b6  call    cs:__imp_GetLastError
0x18000f4bc  mov     edi, eax
0x18000f4be  test    eax, eax
0x18000f4c0  jle     loc_18000F5A5
0x18000f4c6  movzx   edi, ax
0x18000f4c9  or      edi, 80070000h
0x18000f4cf  jmp     loc_18000F5A5
0x18000f4d4  mov     eax, [rbx]
0x18000f4d6  xor     edi, edi
0x18000f4d8  test    al, 4
0x18000f4da  jz      loc_18000F59C
0x18000f4e0  mov     rax, gs:60h
0x18000f4e9  mov     r9d, [rbx+4]
0x18000f4ed  mov     esi, [rax+2C0h]
0x18000f4f3  test    r9d, r9d
0x18000f4f6  jz      short loc_18000F501
0x18000f4f8  lea     r8, aGlobalClearsto; "Global\\ClearStockGlobal%d-%d"
0x18000f4ff  jmp     short loc_18000F511
0x18000f501  call    cs:__imp_GetCurrentProcessId
0x18000f507  mov     r9d, eax
0x18000f50a  lea     r8, aClearstockloca; "ClearStockLocal%d-%d"
0x18000f511  mov     edx, 40h ; '@'; unsigned __int64
0x18000f516  mov     dword ptr [rsp+118h+dwNumberOfBytesToMap], esi
0x18000f51a  lea     rcx, [rsp+118h+Name]; unsigned __int16 *
0x18000f51f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000f524  xor     edx, edx; lInitialCount
0x18000f526  mov     [rsp+118h+bInheritHandle], 1F0003h; dwDesiredAccess
0x18000f52e  lea     r9, [rsp+118h+Name]; lpName
0x18000f533  mov     dword ptr [rsp+118h+dwNumberOfBytesToMap], edi; dwFlags
0x18000f537  xor     ecx, ecx; lpSemaphoreAttributes
0x18000f539  lea     r8d, [rdx+1]; lMaximumCount
0x18000f53d  call    cs:__imp_CreateSemaphoreExW
0x18000f543  mov     r14, rax
0x18000f546  call    cs:__imp_GetLastError
0x18000f54c  cmp     eax, 0B7h
0x18000f551  jz      short loc_18000F58E
0x18000f553  cmp     eax, 5
0x18000f556  jz      short loc_18000F58E
0x18000f558  mov     ecx, [rbx]
0x18000f55a  test    cl, 4
0x18000f55d  jz      short loc_18000F58E
0x18000f55f  movsxd  rsi, dword ptr [rbx+0Ch]
0x18000f563  movsxd  rax, dword ptr [rbx+8]
0x18000f567  add     rsi, rbx
0x18000f56a  lea     rbp, [rsi+rax*8]
0x18000f56e  jmp     short loc_18000F581
0x18000f570  mov     rcx, [rsi]; HBITMAP
0x18000f573  test    rcx, rcx
0x18000f576  jz      short loc_18000F57D
0x18000f578  call    ?DeleteStockBitmap@CUxThemeFile@@CAXPEAUHBITMAP__@@@Z; CUxThemeFile::DeleteStockBitmap(HBITMAP__ *)
0x18000f57d  add     rsi, 8
0x18000f581  cmp     rsi, rbp
0x18000f584  jb      short loc_18000F570
0x18000f586  test    r15b, r15b
0x18000f589  jz      short loc_18000F58E
0x18000f58b  and     dword ptr [rbx], 0FFFFFFFBh
0x18000f58e  test    r14, r14
0x18000f591  jz      short loc_18000F59C
0x18000f593  mov     rcx, r14; hObject
0x18000f596  call    cs:__imp_CloseHandle
0x18000f59c  mov     rcx, rbx; lpBaseAddress
0x18000f59f  call    cs:__imp_UnmapViewOfFile
0x18000f5a5  mov     rcx, [rsp+118h+TargetHandle]; hObject
0x18000f5aa  test    rcx, rcx
0x18000f5ad  jz      short loc_18000F5B5
0x18000f5af  call    cs:__imp_CloseHandle
0x18000f5b5  mov     eax, edi
0x18000f5b7  mov     rcx, [rsp+118h+var_48]
0x18000f5bf  xor     rcx, rsp; StackCookie
0x18000f5c2  call    __security_check_cookie
0x18000f5c7  add     rsp, 0E8h
0x18000f5ce  pop     r15
0x18000f5d0  pop     r14
0x18000f5d2  pop     rdi
0x18000f5d3  pop     rsi
0x18000f5d4  pop     rbp
0x18000f5d5  pop     rbx
0x18000f5d6  retn
```
