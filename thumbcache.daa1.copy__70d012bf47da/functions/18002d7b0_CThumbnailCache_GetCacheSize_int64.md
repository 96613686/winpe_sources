# CThumbnailCache::GetCacheSize(__int64 *)

- ea: `0x18002d7b0`
- end: `0x18002d8a4`
- name: `?GetCacheSize@CThumbnailCache@@UEAAJPEA_J@Z`
- size: `244`
- prototype: `__int64 __fastcall(CThumbnailCache *__hidden this, __int64 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180015c74`
- `0x1800177e0`
- `0x18002d7b0`
- `0x180035830`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d858`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d858`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002d836`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002d836`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18002d84a`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18002d84a`

## pseudocode

```c
__int64 __fastcall CThumbnailCache::GetCacheSize(CThumbnailCache *this, __int64 *a2)
{
  char *v2; // r14
  __int64 v4; // rbp
  int DataFilePath; // ebx
  unsigned int v6; // edi
  __int64 v7; // r8
  __int64 v8; // rdx
  HANDLE FileW; // rax
  void *v10; // rsi
  WCHAR FileName[264]; // [rsp+40h] [rbp-248h] BYREF

  v2 = (char *)this - 8;
  v4 = 0;
  DataFilePath = CThumbnailCache::_ComputeCacheDirectory((CThumbnailCache *)((char *)this - 8));
  v6 = 0;
  while ( DataFilePath >= 0 )
  {
    if ( v6 == 14 )
    {
      v7 = 0xFFFFFFFFLL;
      v8 = 1;
    }
    else
    {
      v7 = v6;
      v8 = 0;
    }
    DataFilePath = CThumbnailCache::_GetDataFilePath(v2, v8, v7, FileName);
    if ( DataFilePath >= 0 )
    {
      FileW = CreateFileW(FileName, 0, 7u, 0, 3u, 0, 0);
      v10 = FileW;
      if ( FileW != (HANDLE)-1LL )
      {
        v4 += GetFileSize(FileW, 0);
        CloseHandle(v10);
      }
    }
    if ( (int)++v6 > 14 )
    {
      if ( DataFilePath >= 0 )
        *a2 = v4;
      return (unsigned int)DataFilePath;
    }
  }
  return (unsigned int)DataFilePath;
}

```

## disassembly

```asm
0x18002d7b0  mov     [rsp+arg_10], rbx
0x18002d7b5  push    rbp
0x18002d7b6  push    rsi
0x18002d7b7  push    rdi
0x18002d7b8  push    r14
0x18002d7ba  push    r15
0x18002d7bc  sub     rsp, 260h
0x18002d7c3  mov     rax, cs:__security_cookie
0x18002d7ca  xor     rax, rsp
0x18002d7cd  mov     [rsp+288h+var_38], rax
0x18002d7d5  lea     r14, [rcx-8]
0x18002d7d9  mov     r15, rdx
0x18002d7dc  mov     rcx, r14; this
0x18002d7df  xor     ebp, ebp
0x18002d7e1  call    ?_ComputeCacheDirectory@CThumbnailCache@@AEAAJXZ; CThumbnailCache::_ComputeCacheDirectory(void)
0x18002d7e6  mov     ebx, eax
0x18002d7e8  xor     edi, edi
0x18002d7ea  test    ebx, ebx
0x18002d7ec  js      short loc_18002D869
0x18002d7ee  lea     r9, [rsp+288h+FileName]
0x18002d7f3  mov     rcx, r14
0x18002d7f6  cmp     edi, 0Eh
0x18002d7f9  jz      loc_18002D892
0x18002d7ff  mov     r8d, edi
0x18002d802  xor     edx, edx
0x18002d804  call    ?_GetDataFilePath@CThumbnailCache@@AEAAJHW4THUMBSIZE@@PEAGI@Z; CThumbnailCache::_GetDataFilePath(int,THUMBSIZE,ushort *,uint)
0x18002d809  mov     ebx, eax
0x18002d80b  test    eax, eax
0x18002d80d  js      short loc_18002D85E
0x18002d80f  xor     r9d, r9d; lpSecurityAttributes
0x18002d812  mov     [rsp+288h+hTemplateFile], 0; hTemplateFile
0x18002d81b  mov     [rsp+288h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18002d823  lea     rcx, [rsp+288h+FileName]; lpFileName
0x18002d828  xor     edx, edx; dwDesiredAccess
0x18002d82a  mov     [rsp+288h+dwCreationDisposition], 3; dwCreationDisposition
0x18002d832  lea     r8d, [r9+7]; dwShareMode
0x18002d836  call    cs:__imp_CreateFileW
0x18002d83c  mov     rsi, rax
0x18002d83f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002d843  jz      short loc_18002D85E
0x18002d845  xor     edx, edx; lpFileSizeHigh
0x18002d847  mov     rcx, rax; hFile
0x18002d84a  call    cs:__imp_GetFileSize
0x18002d850  mov     ecx, eax
0x18002d852  add     rbp, rcx
0x18002d855  mov     rcx, rsi; hObject
0x18002d858  call    cs:__imp_CloseHandle
0x18002d85e  inc     edi
0x18002d860  cmp     edi, 0Eh
0x18002d863  jle     short loc_18002D7EA
0x18002d865  test    ebx, ebx
0x18002d867  jns     short loc_18002D89F
0x18002d869  mov     eax, ebx
0x18002d86b  mov     rcx, [rsp+288h+var_38]
0x18002d873  xor     rcx, rsp; StackCookie
0x18002d876  call    __security_check_cookie
0x18002d87b  mov     rbx, [rsp+288h+arg_10]
0x18002d883  add     rsp, 260h
0x18002d88a  pop     r15
0x18002d88c  pop     r14
0x18002d88e  pop     rdi
0x18002d88f  pop     rsi
0x18002d890  pop     rbp
0x18002d891  retn
0x18002d892  or      r8d, 0FFFFFFFFh
0x18002d896  lea     edx, [r8+2]
0x18002d89a  jmp     loc_18002D804
0x18002d89f  mov     [r15], rbp
0x18002d8a2  jmp     short loc_18002D869
```
