# DiamondNotifyFunction(FDINOTIFICATIONTYPE,FDINOTIFICATION *)

- ea: `0x180001f80`
- end: `0x180002192`
- name: `?DiamondNotifyFunction@@YA_JW4FDINOTIFICATIONTYPE@@PEAUFDINOTIFICATION@@@Z`
- size: `530`
- prototype: `__int64 __fastcall(enum FDINOTIFICATIONTYPE, struct FDINOTIFICATION *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180001f80`
- `0x180002898`
- `0x1800031b0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x180002104`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x18000211f`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x180002104`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x18000211f`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x18000203d`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x18000203d`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x180002021`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x180002021`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180002176`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180002176`
- `KERNELBASE!lstrcmpiA` at `0x180002148`
- `KERNELBASE!lstrcmpiA` at `0x180002148`
- `KERNEL32!_lclose` at `0x180002046`
- `KERNEL32!_lclose` at `0x180002046`
- `KERNEL32!_lcreat` at `0x180002165`
- `KERNEL32!_lcreat` at `0x180002165`

## pseudocode

```c
__int64 __fastcall DiamondNotifyFunction(enum FDINOTIFICATIONTYPE a1, struct FDINOTIFICATION *a2)
{
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  __int64 result; // rax
  void **pv; // rcx
  void *hf; // rbx
  void *v9; // rcx
  void *v10; // r14
  char *v11; // rax
  char v12; // dl
  char *v13; // rbx
  char *v14; // rax
  char *v15; // rax
  __int64 v16; // rcx
  unsigned __int64 v17; // rcx
  __int64 v18; // rdx
  char *v19; // rax
  const CHAR *v20; // rcx
  DWORD FullPathNameA; // ebx
  DWORD v22; // eax
  struct _FILETIME CreationTime; // [rsp+20h] [rbp-E0h] BYREF
  struct _FILETIME LastWriteTime; // [rsp+28h] [rbp-D8h] BYREF
  struct _FILETIME LastAccessTime; // [rsp+30h] [rbp-D0h] BYREF
  CHAR String2[272]; // [rsp+40h] [rbp-C0h] BYREF
  CHAR Buffer[272]; // [rsp+150h] [rbp+50h] BYREF

  if ( a1 == fdintCABINET_INFO )
    return 0;
  v3 = a1 - 1;
  if ( !v3 )
    return 0;
  v4 = v3 - 1;
  if ( v4 )
  {
    v5 = v4 - 1;
    if ( v5 )
    {
      if ( (unsigned int)(v5 - 1) <= 1 )
        return 0;
      return -1;
    }
    pv = (void **)a2->pv;
    hf = (void *)a2->hf;
    CreationTime = 0;
    LastAccessTime = 0;
    v9 = *pv;
    LastWriteTime = 0;
    if ( GetFileTime(v9, &CreationTime, &LastAccessTime, &LastWriteTime) )
      SetFileTime(hf, &CreationTime, &LastAccessTime, &LastWriteTime);
    _lclose(a2->hf);
    return 1;
  }
  else
  {
    v10 = a2->pv;
    if ( *((_DWORD *)v10 + 6) )
    {
      v11 = StringRevChar(*((char **)v10 + 2), (char)a2);
      v13 = v11 ? v11 + 1 : (char *)*((_QWORD *)v10 + 2);
      v14 = StringRevChar(a2->psz1, v12);
      v15 = v14 ? v14 + 1 : a2->psz1;
      v16 = -1;
      do
        ++v16;
      while ( v13[v16] );
      v17 = v16 + 1;
      if ( v17 )
      {
        if ( v17 <= 0x7FFFFFFF )
        {
          v18 = 2147483646;
          do
          {
            if ( !v18 )
              break;
            if ( !*v15 )
              break;
            *v13++ = *v15++;
            --v18;
            --v17;
          }
          while ( v17 );
          v19 = v13 - 1;
          if ( v17 )
            v19 = v13;
          *v19 = 0;
        }
        else
        {
          *v13 = 0;
        }
      }
    }
    v20 = (const CHAR *)*((_QWORD *)v10 + 1);
    CreationTime = 0;
    FullPathNameA = GetFullPathNameA(v20, 0x104u, Buffer, (LPSTR *)&CreationTime);
    v22 = GetFullPathNameA(*((LPCSTR *)v10 + 2), 0x104u, String2, (LPSTR *)&CreationTime);
    if ( FullPathNameA - 1 > 0x102 || v22 - 1 > 0x102 || !lstrcmpiA(Buffer, String2) )
      return 0;
    *(_DWORD *)(*((_QWORD *)v10 + 4) + 68LL) = a2->cb;
    LODWORD(result) = _lcreat(*((LPCSTR *)v10 + 2), 0);
    if ( (_DWORD)result == -1 )
    {
      *(_DWORD *)TlsGetValue(itlsDiamondContext) = -2;
      return -1;
    }
    return (int)result;
  }
}

```

## disassembly

```asm
0x180001f80  push    rbp
0x180001f82  push    rbx
0x180001f83  push    rdi
0x180001f84  push    r14
0x180001f86  lea     rbp, [rsp-178h]
0x180001f8e  sub     rsp, 278h
0x180001f95  mov     rax, cs:__security_cookie
0x180001f9c  xor     rax, rsp
0x180001f9f  mov     [rbp+190h+var_30], rax
0x180001fa6  mov     rdi, rdx
0x180001fa9  test    ecx, ecx
0x180001fab  jz      short loc_180001FCE
0x180001fad  sub     ecx, 1
0x180001fb0  jz      short loc_180001FCE
0x180001fb2  sub     ecx, 1
0x180001fb5  jz      loc_180002056
0x180001fbb  sub     ecx, 1
0x180001fbe  jz      short loc_180001FEC
0x180001fc0  sub     ecx, 1
0x180001fc3  jz      short loc_180001FCE
0x180001fc5  cmp     ecx, 1
0x180001fc8  jnz     loc_180002182
0x180001fce  xor     eax, eax
0x180001fd0  mov     rcx, [rbp+190h+var_30]
0x180001fd7  xor     rcx, rsp; StackCookie
0x180001fda  call    __security_check_cookie
0x180001fdf  add     rsp, 278h
0x180001fe6  pop     r14
0x180001fe8  pop     rdi
0x180001fe9  pop     rbx
0x180001fea  pop     rbp
0x180001feb  retn
0x180001fec  mov     rcx, [rdx+20h]
0x180001ff0  lea     r9, [rsp+290h+LastWriteTime]; lpLastWriteTime
0x180001ff5  mov     rbx, [rdx+28h]
0x180001ff9  lea     r8, [rsp+290h+LastAccessTime]; lpLastAccessTime
0x180001ffe  lea     rdx, [rsp+290h+CreationTime]; lpCreationTime
0x180002003  mov     qword ptr [rsp+290h+CreationTime.dwLowDateTime], 0
0x18000200c  mov     qword ptr [rsp+290h+LastAccessTime.dwLowDateTime], 0
0x180002015  mov     rcx, [rcx]; hFile
0x180002018  mov     qword ptr [rsp+290h+LastWriteTime.dwLowDateTime], 0
0x180002021  call    cs:__imp_GetFileTime
0x180002027  test    eax, eax
0x180002029  jz      short loc_180002043
0x18000202b  lea     r9, [rsp+290h+LastWriteTime]; lpLastWriteTime
0x180002030  mov     rcx, rbx; hFile
0x180002033  lea     r8, [rsp+290h+LastAccessTime]; lpLastAccessTime
0x180002038  lea     rdx, [rsp+290h+CreationTime]; lpCreationTime
0x18000203d  call    cs:__imp_SetFileTime
0x180002043  mov     ecx, [rdi+28h]; hFile
0x180002046  call    cs:__imp__lclose
0x18000204c  mov     eax, 1
0x180002051  jmp     loc_180001FD0
0x180002056  mov     r14, [rdx+20h]
0x18000205a  cmp     dword ptr [r14+18h], 0
0x18000205f  jz      loc_1800020E9
0x180002065  mov     rcx, [r14+10h]; Buf1
0x180002069  call    ?StringRevChar@@YAPEADPEADD@Z; StringRevChar(char *,char)
0x18000206e  mov     rbx, rax
0x180002071  test    rax, rax
0x180002074  jz      short loc_18000207B
0x180002076  inc     rbx
0x180002079  jmp     short loc_18000207F
0x18000207b  mov     rbx, [r14+10h]
0x18000207f  mov     rcx, [rdi+8]; Buf1
0x180002083  call    ?StringRevChar@@YAPEADPEADD@Z; StringRevChar(char *,char)
0x180002088  test    rax, rax
0x18000208b  jz      short loc_180002092
0x18000208d  inc     rax
0x180002090  jmp     short loc_180002096
0x180002092  mov     rax, [rdi+8]
0x180002096  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000209a  inc     rcx
0x18000209d  cmp     byte ptr [rbx+rcx], 0
0x1800020a1  jnz     short loc_18000209A
0x1800020a3  add     rcx, 1
0x1800020a7  jz      short loc_1800020E9
0x1800020a9  cmp     rcx, 7FFFFFFFh
0x1800020b0  jbe     short loc_1800020B7
0x1800020b2  mov     byte ptr [rbx], 0
0x1800020b5  jmp     short loc_1800020E9
0x1800020b7  mov     edx, 7FFFFFFEh
0x1800020bc  test    rdx, rdx
0x1800020bf  jz      short loc_1800020DB
0x1800020c1  mov     r8b, [rax]
0x1800020c4  test    r8b, r8b
0x1800020c7  jz      short loc_1800020DB
0x1800020c9  mov     [rbx], r8b
0x1800020cc  inc     rax
0x1800020cf  inc     rbx
0x1800020d2  dec     rdx
0x1800020d5  sub     rcx, 1
0x1800020d9  jnz     short loc_1800020BC
0x1800020db  test    rcx, rcx
0x1800020de  lea     rax, [rbx-1]
0x1800020e2  cmovnz  rax, rbx
0x1800020e6  mov     byte ptr [rax], 0
0x1800020e9  mov     rcx, [r14+8]; lpFileName
0x1800020ed  lea     r9, [rsp+290h+CreationTime]; lpFilePart
0x1800020f2  lea     r8, [rbp+190h+Buffer]; lpBuffer
0x1800020f6  mov     qword ptr [rsp+290h+CreationTime.dwLowDateTime], 0
0x1800020ff  mov     edx, 104h; nBufferLength
0x180002104  call    cs:__imp_GetFullPathNameA
0x18000210a  mov     rcx, [r14+10h]; lpFileName
0x18000210e  lea     r9, [rsp+290h+CreationTime]; lpFilePart
0x180002113  lea     r8, [rsp+290h+String2]; lpBuffer
0x180002118  mov     edx, 104h; nBufferLength
0x18000211d  mov     ebx, eax
0x18000211f  call    cs:__imp_GetFullPathNameA
0x180002125  lea     ecx, [rbx-1]
0x180002128  mov     edx, 102h
0x18000212d  cmp     ecx, edx
0x18000212f  ja      loc_180001FCE
0x180002135  dec     eax
0x180002137  cmp     eax, edx
0x180002139  ja      loc_180001FCE
0x18000213f  lea     rdx, [rsp+290h+String2]; lpString2
0x180002144  lea     rcx, [rbp+190h+Buffer]; lpString1
0x180002148  call    cs:__imp_lstrcmpiA
0x18000214e  test    eax, eax
0x180002150  jz      loc_180001FCE
0x180002156  mov     rcx, [r14+20h]
0x18000215a  xor     edx, edx; iAttribute
0x18000215c  mov     eax, [rdi]
0x18000215e  mov     [rcx+44h], eax
0x180002161  mov     rcx, [r14+10h]; lpPathName
0x180002165  call    cs:__imp__lcreat
0x18000216b  cmp     eax, 0FFFFFFFFh
0x18000216e  jnz     short loc_18000218B
0x180002170  mov     ecx, cs:?itlsDiamondContext@@3KA; dwTlsIndex
0x180002176  call    cs:__imp_TlsGetValue
0x18000217c  mov     dword ptr [rax], 0FFFFFFFEh
0x180002182  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002186  jmp     loc_180001FD0
0x18000218b  cdqe
0x18000218d  jmp     loc_180001FD0
```
