# CThumbnailCache::_CheckExclusiveAccessToCache(bool *)

- ea: `0x180042e24`
- end: `0x180042f02`
- name: `?_CheckExclusiveAccessToCache@CThumbnailCache@@AEAAJPEA_N@Z`
- size: `222`
- prototype: `__int64 __fastcall(CThumbnailCache *__hidden this, bool *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18002acdc`
- `0x1800416d0`

## callees

- `0x1800177e0`
- `0x180035830`
- `0x180042e24`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042ec0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042ec0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180042eb1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180042eb1`

## pseudocode

```c
__int64 __fastcall CThumbnailCache::_CheckExclusiveAccessToCache(CThumbnailCache *this, bool *a2)
{
  int DataFilePath; // ebx
  int v3; // esi
  bool v6; // di
  int v7; // r8d
  int v8; // edx
  HANDLE FileW; // rax
  WCHAR FileName[264]; // [rsp+40h] [rbp-248h] BYREF

  DataFilePath = 0;
  *a2 = 0;
  v3 = 0;
  v6 = 1;
  while ( DataFilePath >= 0 )
  {
    if ( !v6 )
      goto LABEL_13;
    if ( v3 == 14 )
    {
      v7 = -1;
      v8 = 1;
    }
    else
    {
      v7 = v3;
      v8 = 0;
    }
    DataFilePath = CThumbnailCache::_GetDataFilePath((__int64)this, v8, v7, FileName);
    if ( DataFilePath >= 0 )
    {
      FileW = CreateFileW(FileName, 0x40000000u, 0, 0, 3u, 0, 0);
      if ( FileW == (HANDLE)-1LL )
        v6 = 0;
      else
        CloseHandle(FileW);
    }
    if ( ++v3 > 14 )
    {
      if ( DataFilePath < 0 )
        return (unsigned int)DataFilePath;
LABEL_13:
      *a2 = v6;
      return (unsigned int)DataFilePath;
    }
  }
  return (unsigned int)DataFilePath;
}

```

## disassembly

```asm
0x180042e24  mov     [rsp+arg_10], rbx
0x180042e29  push    rbp
0x180042e2a  push    rsi
0x180042e2b  push    rdi
0x180042e2c  push    r14
0x180042e2e  push    r15
0x180042e30  sub     rsp, 260h
0x180042e37  mov     rax, cs:__security_cookie
0x180042e3e  xor     rax, rsp
0x180042e41  mov     [rsp+288h+var_38], rax
0x180042e49  xor     ebx, ebx
0x180042e4b  mov     byte ptr [rdx], 0
0x180042e4e  xor     esi, esi
0x180042e50  mov     r14, rdx
0x180042e53  mov     r15, rcx
0x180042e56  mov     dil, 1
0x180042e59  test    ebx, ebx
0x180042e5b  js      short loc_180042ED9
0x180042e5d  test    dil, dil
0x180042e60  jz      short loc_180042ED6
0x180042e62  lea     r9, [rsp+288h+FileName]
0x180042e67  mov     rcx, r15
0x180042e6a  cmp     esi, 0Eh
0x180042e6d  jnz     short loc_180042E78
0x180042e6f  or      r8d, 0FFFFFFFFh
0x180042e73  lea     edx, [rsi-0Dh]
0x180042e76  jmp     short loc_180042E7D
0x180042e78  mov     r8d, esi
0x180042e7b  xor     edx, edx
0x180042e7d  call    ?_GetDataFilePath@CThumbnailCache@@AEAAJHW4THUMBSIZE@@PEAGI@Z; CThumbnailCache::_GetDataFilePath(int,THUMBSIZE,ushort *,uint)
0x180042e82  mov     ebx, eax
0x180042e84  test    eax, eax
0x180042e86  js      short loc_180042ECB
0x180042e88  mov     [rsp+288h+hTemplateFile], 0; hTemplateFile
0x180042e91  lea     rcx, [rsp+288h+FileName]; lpFileName
0x180042e96  mov     [rsp+288h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180042e9e  xor     r9d, r9d; lpSecurityAttributes
0x180042ea1  xor     r8d, r8d; dwShareMode
0x180042ea4  mov     [rsp+288h+dwCreationDisposition], 3; dwCreationDisposition
0x180042eac  mov     edx, 40000000h; dwDesiredAccess
0x180042eb1  call    cs:__imp_CreateFileW
0x180042eb7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180042ebb  jz      short loc_180042EC8
0x180042ebd  mov     rcx, rax; hObject
0x180042ec0  call    cs:__imp_CloseHandle
0x180042ec6  jmp     short loc_180042ECB
0x180042ec8  xor     dil, dil
0x180042ecb  inc     esi
0x180042ecd  cmp     esi, 0Eh
0x180042ed0  jle     short loc_180042E59
0x180042ed2  test    ebx, ebx
0x180042ed4  js      short loc_180042ED9
0x180042ed6  mov     [r14], dil
0x180042ed9  mov     eax, ebx
0x180042edb  mov     rcx, [rsp+288h+var_38]
0x180042ee3  xor     rcx, rsp; StackCookie
0x180042ee6  call    __security_check_cookie
0x180042eeb  mov     rbx, [rsp+288h+arg_10]
0x180042ef3  add     rsp, 260h
0x180042efa  pop     r15
0x180042efc  pop     r14
0x180042efe  pop     rdi
0x180042eff  pop     rsi
0x180042f00  pop     rbp
0x180042f01  retn
```
