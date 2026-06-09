# SHGetPictureFromDataFileForUser(ushort const *,uchar * *,ulong *)

- ea: `0x18000e8b4`
- end: `0x18000ea7b`
- name: `?SHGetPictureFromDataFileForUser@@YAJPEBGPEAPEAEPEAK@Z`
- size: `455`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x18000ed10`

## callees

- `0x18000c240`
- `0x18000daec`
- `0x18000e6c8`
- `0x18000e6ec`
- `0x18000e81c`
- `0x18000e8b4`
- `0x18000ec7c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ea39`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ea39`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ea49`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ea49`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000e993`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000e993`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000ea0d`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000ea0d`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18000e9b6`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18000e9b6`

## pseudocode

```c
__int64 __fastcall SHGetPictureFromDataFileForUser(const unsigned __int16 *a1, unsigned __int8 **a2, unsigned int *a3)
{
  unsigned int v5; // edx
  int UserPicturePath; // ebx
  HANDLE FileW; // rax
  void *v8; // r14
  DWORD FileSize; // eax
  unsigned int v10; // edx
  DWORD v11; // edi
  void *v12; // rcx
  unsigned __int8 *v13; // rsi
  DWORD FileSizeHigh; // [rsp+40h] [rbp-C0h] BYREF
  DWORD NumberOfBytesRead; // [rsp+44h] [rbp-BCh] BYREF
  LPVOID lpBuffer; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR FileName[264]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v19[264]; // [rsp+260h] [rbp+160h] BYREF

  UserPicturePath = SHAcctAccountName2DataFileName(a1, v19, (unsigned int)a3);
  if ( UserPicturePath >= 0 )
  {
    UserPicturePath = SHAcctGetUserPicturePath(FileName, v5);
    if ( UserPicturePath >= 0 )
    {
      UserPicturePath = StringCchCatW(FileName, 0x104u, L"\\");
      if ( UserPicturePath >= 0 )
      {
        UserPicturePath = StringCchCatW(FileName, 0x104u, v19);
        if ( UserPicturePath >= 0 )
        {
          UserPicturePath = StringCchCatW(FileName, 0x104u, L".dat");
          if ( UserPicturePath >= 0 )
          {
            FileW = CreateFileW(FileName, 1u, 1u, 0, 3u, 0x80u, 0);
            v8 = FileW;
            if ( FileW == (HANDLE)-1LL )
            {
              return (unsigned int)ResultFromLastError();
            }
            else
            {
              FileSizeHigh = 0;
              FileSize = GetFileSize(FileW, &FileSizeHigh);
              v11 = FileSize;
              if ( FileSizeHigh || (v12 = (void *)(FileSize - 1), (unsigned int)v12 > 0xFFFFFFFD) )
              {
                UserPicturePath = -2147023890;
              }
              else
              {
                lpBuffer = 0;
                UserPicturePath = CTLocalAllocPolicy::Alloc(v12, v10, FileSize, &lpBuffer);
                if ( UserPicturePath >= 0 )
                {
                  v13 = (unsigned __int8 *)lpBuffer;
                  NumberOfBytesRead = 0;
                  if ( ReadFile(v8, lpBuffer, v11, &NumberOfBytesRead, 0) )
                  {
                    if ( NumberOfBytesRead == v11 )
                    {
                      *a2 = v13;
                      v13 = 0;
                      *a3 = v11;
                    }
                    else
                    {
                      UserPicturePath = -2147467259;
                    }
                  }
                  else
                  {
                    UserPicturePath = ResultFromLastError();
                  }
                  LocalFree(v13);
                }
              }
              CloseHandle(v8);
            }
          }
        }
      }
    }
  }
  return (unsigned int)UserPicturePath;
}

```

## disassembly

```asm
0x18000e8b4  push    rbp
0x18000e8b6  push    rbx
0x18000e8b7  push    rsi
0x18000e8b8  push    rdi
0x18000e8b9  push    r12
0x18000e8bb  push    r14
0x18000e8bd  push    r15
0x18000e8bf  lea     rbp, [rsp-380h]
0x18000e8c7  sub     rsp, 480h
0x18000e8ce  mov     rax, cs:__security_cookie
0x18000e8d5  xor     rax, rsp
0x18000e8d8  mov     [rbp+3B0h+var_40], rax
0x18000e8df  mov     r15, rdx
0x18000e8e2  mov     r12, r8
0x18000e8e5  lea     rdx, [rbp+3B0h+var_250]; unsigned __int16 *
0x18000e8ec  call    ?SHAcctAccountName2DataFileName@@YAJPEBGPEAGK@Z; SHAcctAccountName2DataFileName(ushort const *,ushort *,ulong)
0x18000e8f1  mov     ebx, eax
0x18000e8f3  test    eax, eax
0x18000e8f5  js      loc_18000EA58
0x18000e8fb  lea     rcx, [rsp+4B0h+FileName]; unsigned __int16 *
0x18000e900  call    ?SHAcctGetUserPicturePath@@YAJPEAGK@Z; SHAcctGetUserPicturePath(ushort *,ulong)
0x18000e905  mov     ebx, eax
0x18000e907  test    eax, eax
0x18000e909  js      loc_18000EA58
0x18000e90f  mov     edi, 104h
0x18000e914  lea     r8, asc_18001ADA8; "\\"
0x18000e91b  mov     edx, edi; unsigned __int64
0x18000e91d  lea     rcx, [rsp+4B0h+FileName]; unsigned __int16 *
0x18000e922  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000e927  mov     ebx, eax
0x18000e929  test    eax, eax
0x18000e92b  js      loc_18000EA58
0x18000e931  lea     r8, [rbp+3B0h+var_250]; unsigned __int16 *
0x18000e938  mov     edx, edi; unsigned __int64
0x18000e93a  lea     rcx, [rsp+4B0h+FileName]; unsigned __int16 *
0x18000e93f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000e944  mov     ebx, eax
0x18000e946  test    eax, eax
0x18000e948  js      loc_18000EA58
0x18000e94e  lea     r8, aDat; ".dat"
0x18000e955  mov     edx, edi; unsigned __int64
0x18000e957  lea     rcx, [rsp+4B0h+FileName]; unsigned __int16 *
0x18000e95c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000e961  mov     ebx, eax
0x18000e963  test    eax, eax
0x18000e965  js      loc_18000EA58
0x18000e96b  xor     r9d, r9d; lpSecurityAttributes
0x18000e96e  mov     [rsp+4B0h+hTemplateFile], 0; hTemplateFile
0x18000e977  mov     [rsp+4B0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000e97f  lea     rcx, [rsp+4B0h+FileName]; lpFileName
0x18000e984  mov     [rsp+4B0h+dwCreationDisposition], 3; dwCreationDisposition
0x18000e98c  lea     edx, [r9+1]; dwDesiredAccess
0x18000e990  mov     r8d, edx; dwShareMode
0x18000e993  call    cs:__imp_CreateFileW
0x18000e999  mov     r14, rax
0x18000e99c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000e9a0  jz      loc_18000EA51
0x18000e9a6  lea     rdx, [rsp+4B0h+FileSizeHigh]; lpFileSizeHigh
0x18000e9ab  mov     [rsp+4B0h+FileSizeHigh], 0
0x18000e9b3  mov     rcx, rax; hFile
0x18000e9b6  call    cs:__imp_GetFileSize
0x18000e9bc  cmp     [rsp+4B0h+FileSizeHigh], 0
0x18000e9c1  mov     edi, eax
0x18000e9c3  ja      short loc_18000EA41
0x18000e9c5  lea     ecx, [rdi-1]; void *
0x18000e9c8  cmp     ecx, 0FFFFFFFDh
0x18000e9cb  ja      short loc_18000EA41
0x18000e9cd  mov     r8d, edi; unsigned __int64
0x18000e9d0  mov     [rsp+4B0h+lpBuffer], 0
0x18000e9d9  lea     r9, [rsp+4B0h+lpBuffer]; void **
0x18000e9de  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18000e9e3  mov     ebx, eax
0x18000e9e5  test    eax, eax
0x18000e9e7  js      short loc_18000EA46
0x18000e9e9  mov     rsi, [rsp+4B0h+lpBuffer]
0x18000e9ee  lea     r9, [rsp+4B0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18000e9f3  mov     rdx, rsi; lpBuffer
0x18000e9f6  mov     [rsp+4B0h+NumberOfBytesRead], 0
0x18000e9fe  mov     r8d, edi; nNumberOfBytesToRead
0x18000ea01  mov     qword ptr [rsp+4B0h+dwCreationDisposition], 0; lpOverlapped
0x18000ea0a  mov     rcx, r14; hFile
0x18000ea0d  call    cs:__imp_ReadFile
0x18000ea13  test    eax, eax
0x18000ea15  jz      short loc_18000EA2F
0x18000ea17  cmp     [rsp+4B0h+NumberOfBytesRead], edi
0x18000ea1b  jz      short loc_18000EA24
0x18000ea1d  mov     ebx, 80004005h
0x18000ea22  jmp     short loc_18000EA36
0x18000ea24  mov     [r15], rsi
0x18000ea27  xor     esi, esi
0x18000ea29  mov     [r12], edi
0x18000ea2d  jmp     short loc_18000EA36
0x18000ea2f  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18000ea34  mov     ebx, eax
0x18000ea36  mov     rcx, rsi; hMem
0x18000ea39  call    cs:__imp_LocalFree
0x18000ea3f  jmp     short loc_18000EA46
0x18000ea41  mov     ebx, 800703EEh
0x18000ea46  mov     rcx, r14; hObject
0x18000ea49  call    cs:__imp_CloseHandle
0x18000ea4f  jmp     short loc_18000EA58
0x18000ea51  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18000ea56  mov     ebx, eax
0x18000ea58  mov     eax, ebx
0x18000ea5a  mov     rcx, [rbp+3B0h+var_40]
0x18000ea61  xor     rcx, rsp; StackCookie
0x18000ea64  call    __security_check_cookie
0x18000ea69  add     rsp, 480h
0x18000ea70  pop     r15
0x18000ea72  pop     r14
0x18000ea74  pop     r12
0x18000ea76  pop     rdi
0x18000ea77  pop     rsi
0x18000ea78  pop     rbx
0x18000ea79  pop     rbp
0x18000ea7a  retn
```
