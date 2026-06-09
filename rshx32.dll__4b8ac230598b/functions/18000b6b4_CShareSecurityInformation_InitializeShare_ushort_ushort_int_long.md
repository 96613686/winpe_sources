# CShareSecurityInformation::InitializeShare(ushort *,ushort *,int,long *)

- ea: `0x18000b6b4`
- end: `0x18000bcab`
- name: `?InitializeShare@CShareSecurityInformation@@SAPEAV1@PEAG0HPEAJ@Z`
- size: `1527`
- prototype: `struct CShareSecurityInformation *__fastcall(unsigned __int16 *, unsigned __int16 *, int, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800070b0`

## callees

- `0x180005610`
- `0x180009600`
- `0x18000ae80`
- `0x18000b6b4`
- `0x18000bcb4`
- `0x18001d322`
- `0x18001d33a`
- `0x18001d370`

## import_xrefs

- `msvcrt!wcschr` at `0x18000b9fa`
- `msvcrt!wcschr` at `0x18000ba0f`
- `msvcrt!wcschr` at `0x18000ba24`
- `msvcrt!wcschr` at `0x18000b9fa`
- `msvcrt!wcschr` at `0x18000ba0f`
- `msvcrt!wcschr` at `0x18000ba24`
- `msvcrt!_wcsnicmp` at `0x18000b822`
- `msvcrt!_wcsnicmp` at `0x18000b855`
- `msvcrt!_wcsnicmp` at `0x18000b822`
- `msvcrt!_wcsnicmp` at `0x18000b855`
- `msvcrt!wcsnlen` at `0x18000b9d4`
- `msvcrt!wcsnlen` at `0x18000ba53`
- `msvcrt!wcsnlen` at `0x18000bb12`
- `msvcrt!wcsnlen` at `0x18000bbbe`
- `msvcrt!wcsnlen` at `0x18000b9d4`
- `msvcrt!wcsnlen` at `0x18000ba53`
- `msvcrt!wcsnlen` at `0x18000bb12`
- `msvcrt!wcsnlen` at `0x18000bbbe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b87d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b8f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bc26`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bc2f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bc38`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b87d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b8f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bc26`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bc2f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bc38`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b8a9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b90f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ba66`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000baca`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000bb28`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000bb53`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000bbd8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000bbff`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000bc7a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b8a9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b90f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ba66`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000baca`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000bb28`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000bb53`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000bbd8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000bbff`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000bc7a`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18000b900`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18000babc`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18000b900`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18000babc`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18000b74f`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18000b74f`
- `netutils!NetApiBufferFree` at `0x18000b968`
- `netutils!NetApiBufferFree` at `0x18000bb01`
- `netutils!NetApiBufferFree` at `0x18000b968`
- `netutils!NetApiBufferFree` at `0x18000bb01`
- `srvcli!NetShareEnum` at `0x18000b7a7`
- `srvcli!NetShareEnum` at `0x18000b7a7`
- `srvcli!NetShareGetInfo` at `0x18000ba98`
- `srvcli!NetShareGetInfo` at `0x18000ba98`

## pseudocode

```c
struct CShareSecurityInformation *__fastcall CShareSecurityInformation::InitializeShare(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        int a3,
        int *a4)
{
  wchar_t *v6; // r15
  int v7; // r14d
  void *v8; // r13
  CShareSecurityInformation *v9; // rdi
  unsigned __int16 *v10; // rbx
  DWORD FullPathNameW; // eax
  WCHAR *v12; // rsi
  DWORD v13; // eax
  __int64 v14; // r11
  DWORD v15; // edx
  LPBYTE v16; // rax
  wchar_t *v17; // rcx
  __int64 v18; // rsi
  bool v19; // cf
  int v20; // eax
  int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // rdx
  const unsigned __int16 *v24; // r8
  DWORD v25; // esi
  HLOCAL v26; // rax
  wchar_t *v27; // rax
  const wchar_t *v28; // rbx
  wchar_t v29; // dx
  unsigned int v30; // eax
  __int64 v31; // rsi
  unsigned __int16 *v32; // rax
  LPBYTE v33; // rcx
  SIZE_T SecurityDescriptorLength; // rsi
  HLOCAL v35; // rax
  size_t v36; // r14
  unsigned __int16 *v37; // rax
  unsigned __int16 *v38; // rsi
  CShareSecurityInformation *v39; // rax
  CShareSecurityInformation *v40; // rax
  size_t v41; // r14
  unsigned __int16 *v42; // rax
  CShareSecurityInformation *v43; // rax
  CShareSecurityInformation *v45; // rax
  DWORD v46; // [rsp+40h] [rbp-C0h]
  LPBYTE v47; // [rsp+48h] [rbp-B8h] BYREF
  LPWSTR servername; // [rsp+50h] [rbp-B0h]
  DWORD entriesread; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int MaxCount; // [rsp+5Ch] [rbp-A4h]
  unsigned int MaxCount_4; // [rsp+60h] [rbp-A0h]
  DWORD resume_handle; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD totalentries; // [rsp+68h] [rbp-98h] BYREF
  DWORD v54; // [rsp+6Ch] [rbp-94h]
  LPBYTE bufptr; // [rsp+70h] [rbp-90h] BYREF
  wchar_t *String1; // [rsp+78h] [rbp-88h]
  wchar_t Source[264]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t Buffer[264]; // [rsp+290h] [rbp+190h] BYREF

  servername = a1;
  v47 = 0;
  bufptr = 0;
  v6 = a1;
  entriesread = 0;
  totalentries = 0;
  resume_handle = 0;
  v7 = 0;
  v8 = 0;
  memset_0(Buffer, 0, 0x208u);
  v9 = 0;
  if ( a3 )
  {
    memset_0(Source, 0, 0x208u);
    if ( !(unsigned int)IsDfsPath(a2, 0, 0, Source, 0x104u) && wcsnlen(a2, 0x104u) > 2 )
    {
      if ( *a2 == 92 && a2[1] == 92 )
      {
        v27 = wcschr(a2 + 2, 0x5Cu);
        if ( v27 )
        {
          v28 = v27 + 1;
          if ( wcschr(v27 + 1, 0x5Cu) )
            v29 = 92;
          else
            v29 = 0;
          v30 = wcschr(v28, v29) - v28 + 1;
          if ( v30 > 0x104 )
            v30 = 260;
          StringCchCopyW(Source, v30, v28);
        }
      }
      v6 = servername;
    }
    v31 = (unsigned int)wcsnlen(Source, 0x104u) + 1;
    v32 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v31);
    v10 = v32;
    if ( !v32 )
      goto LABEL_71;
    StringCchCopyW(v32, (unsigned int)v31, Source);
    if ( NetShareGetInfo(v6, Source, 0x1F6u, &v47) )
    {
      v36 = wcsnlen(v6, 0x104u);
      v37 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v36 + 2);
      v38 = v37;
      if ( !v37 )
        goto LABEL_71;
      StringCchCopyW(v37, v36 + 1, v6);
      v39 = (CShareSecurityInformation *)LocalAlloc(0x40u, 0x110u);
      if ( !v39 )
        goto LABEL_70;
      v40 = CShareSecurityInformation::CShareSecurityInformation(v39, v10, v38, 0);
      v9 = v40;
      if ( !v40 )
        goto LABEL_70;
      v7 = CShareSecurityInformation::InitializeShareThread(v40);
      v10 = 0;
    }
    else
    {
      v33 = v47;
      if ( *((_DWORD *)v47 + 2) || !*((_QWORD *)v47 + 8) )
      {
        v7 = -2147024809;
      }
      else
      {
        SecurityDescriptorLength = GetSecurityDescriptorLength(*((PSECURITY_DESCRIPTOR *)v47 + 8));
        v35 = LocalAlloc(0x40u, SecurityDescriptorLength);
        v8 = v35;
        if ( v35 )
          memcpy_0(v35, *((const void **)v47 + 8), SecurityDescriptorLength);
        else
          v7 = -2147024882;
        v33 = v47;
      }
      NetApiBufferFree(v33);
    }
  }
  else
  {
    v10 = 0;
    FullPathNameW = GetFullPathNameW(a2, 0x104u, Buffer, 0);
    MaxCount = FullPathNameW;
    if ( FullPathNameW )
    {
      MaxCount_4 = 0;
      if ( FullPathNameW < 0x104 )
      {
        v12 = servername;
        while ( 1 )
        {
          v13 = NetShareEnum(v12, 0x1F6u, &bufptr, 0xFFFFFFFF, &entriesread, &totalentries, &resume_handle);
          LODWORD(v14) = 0;
          v54 = v13;
          if ( v13 && v13 != 234 )
            goto LABEL_63;
          v15 = 0;
          v16 = bufptr;
          v47 = bufptr;
          v46 = 0;
          if ( !entriesread )
            goto LABEL_32;
          while ( 1 )
          {
            if ( *((_DWORD *)v16 + 2) != (_DWORD)v14 )
              goto LABEL_28;
            v17 = (wchar_t *)*((_QWORD *)v16 + 5);
            v18 = -1;
            String1 = v17;
            do
              ++v18;
            while ( v17[v18] != (_WORD)v14 );
            if ( (unsigned int)v18 <= MaxCount_4 )
              goto LABEL_28;
            v19 = (unsigned int)v18 < MaxCount;
            if ( (unsigned int)v18 > MaxCount )
              goto LABEL_28;
            if ( (_DWORD)v18 == MaxCount )
            {
              v20 = _wcsnicmp(v17, Buffer, MaxCount);
              LODWORD(v14) = 0;
              if ( !v20 )
                goto LABEL_19;
              v19 = (unsigned int)v18 < MaxCount;
              v17 = String1;
              v15 = v46;
            }
            if ( v19 )
              break;
LABEL_28:
            ++v15;
            v16 = v47 + 72;
            v46 = v15;
            v47 += 72;
            if ( v15 >= entriesread )
              goto LABEL_31;
          }
          String1 = (wchar_t *)(unsigned int)v18;
          v21 = _wcsnicmp(v17, Buffer, (unsigned int)v18);
          LODWORD(v14) = 0;
          if ( v21 || Buffer[(_QWORD)String1] != 92 )
            goto LABEL_27;
LABEL_19:
          LocalFree(v10);
          v22 = -1;
          do
            ++v22;
          while ( *(_WORD *)(*(_QWORD *)v47 + 2 * v22) );
          v10 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v22 + 2);
          if ( v10 )
            break;
LABEL_30:
          v7 = -2147024882;
LABEL_31:
          v12 = servername;
LABEL_32:
          NetApiBufferFree(bufptr);
          if ( v7 < 0 )
            goto LABEL_71;
          if ( v54 != 234 )
            goto LABEL_65;
        }
        v23 = -1;
        v24 = *(const unsigned __int16 **)v47;
        do
          ++v23;
        while ( v24[v23] );
        StringCchCopyW(v10, v23 + 1, v24);
        MaxCount_4 = v18;
        if ( *((_QWORD *)v47 + 8) != v14 )
        {
          LocalFree(v8);
          v25 = GetSecurityDescriptorLength(*((PSECURITY_DESCRIPTOR *)v47 + 8));
          v26 = LocalAlloc(0x40u, v25);
          v8 = v26;
          if ( !v26 )
            goto LABEL_30;
          memcpy_0(v26, *((const void **)v47 + 8), v25);
          LODWORD(v14) = 0;
        }
LABEL_27:
        v15 = v46;
        goto LABEL_28;
      }
    }
    v7 = -2147024882;
  }
  v12 = servername;
LABEL_63:
  if ( v7 >= 0 && !v9 )
  {
LABEL_65:
    if ( v10 )
    {
      if ( v12 )
      {
        v41 = wcsnlen(v12, 0x104u);
        v42 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v41 + 2);
        v38 = v42;
        if ( v42 )
        {
          StringCchCopyW(v42, v41 + 1, servername);
          v43 = (CShareSecurityInformation *)LocalAlloc(0x40u, 0x110u);
          if ( !v43 )
          {
            v9 = 0;
            goto LABEL_70;
          }
          v9 = CShareSecurityInformation::CShareSecurityInformation(v43, v10, v38, v8);
          if ( !v9 )
          {
LABEL_70:
            LocalFree(v38);
            goto LABEL_71;
          }
LABEL_75:
          v10 = 0;
          v8 = 0;
        }
      }
      else
      {
        v45 = (CShareSecurityInformation *)LocalAlloc(0x40u, 0x110u);
        if ( !v45 )
        {
          v9 = 0;
          goto LABEL_71;
        }
        v9 = CShareSecurityInformation::CShareSecurityInformation(v45, v10, 0, v8);
        if ( v9 )
          goto LABEL_75;
      }
    }
  }
LABEL_71:
  LocalFree(v8);
  LocalFree(v10);
  return v9;
}

```

## disassembly

```asm
0x18000b6b4  mov     [rsp-8+arg_10], rbx
0x18000b6b9  push    rbp
0x18000b6ba  push    rsi
0x18000b6bb  push    rdi
0x18000b6bc  push    r12
0x18000b6be  push    r13
0x18000b6c0  push    r14
0x18000b6c2  push    r15
0x18000b6c4  lea     rbp, [rsp-3B0h]
0x18000b6cc  sub     rsp, 4B0h
0x18000b6d3  mov     rax, cs:__security_cookie
0x18000b6da  xor     rax, rsp
0x18000b6dd  mov     [rbp+3E0h+var_40], rax
0x18000b6e4  xor     r12d, r12d
0x18000b6e7  mov     [rsp+4E0h+servername], rcx
0x18000b6ec  mov     ebx, r8d
0x18000b6ef  mov     [rsp+4E0h+var_498], r12
0x18000b6f4  mov     rsi, rdx
0x18000b6f7  mov     [rsp+4E0h+bufptr], r12
0x18000b6fc  mov     r15, rcx
0x18000b6ff  mov     [rsp+4E0h+var_488], r12d
0x18000b704  xor     edx, edx; Val
0x18000b706  mov     [rsp+4E0h+var_478], r12d
0x18000b70b  mov     r8d, 208h; Size
0x18000b711  mov     [rsp+4E0h+var_47C], r12d
0x18000b716  lea     rcx, [rbp+3E0h+Buffer]; void *
0x18000b71d  mov     r14d, r12d
0x18000b720  mov     r13d, r12d
0x18000b723  call    memset_0
0x18000b728  mov     edi, r12d
0x18000b72b  test    ebx, ebx
0x18000b72d  jnz     loc_18000B99D
0x18000b733  mov     r12d, 104h
0x18000b739  lea     r8, [rbp+3E0h+Buffer]; lpBuffer
0x18000b740  xor     r15d, r15d
0x18000b743  mov     edx, r12d; nBufferLength
0x18000b746  xor     r9d, r9d; lpFilePart
0x18000b749  mov     rcx, rsi; lpFileName
0x18000b74c  mov     ebx, r15d
0x18000b74f  call    cs:__imp_GetFullPathNameW
0x18000b755  mov     dword ptr [rsp+4E0h+MaxCount], eax
0x18000b759  test    eax, eax
0x18000b75b  jz      loc_18000B98D
0x18000b761  mov     dword ptr [rsp+4E0h+MaxCount+4], r15d
0x18000b766  cmp     eax, r12d
0x18000b769  jnb     loc_18000B98D
0x18000b76f  mov     rsi, [rsp+4E0h+servername]
0x18000b774  lea     r15d, [rdi+5Ch]
0x18000b778  lea     rax, [rsp+4E0h+var_47C]
0x18000b77d  or      r9d, 0FFFFFFFFh; prefmaxlen
0x18000b781  mov     [rsp+4E0h+resume_handle], rax; resume_handle
0x18000b786  lea     r8, [rsp+4E0h+bufptr]; bufptr
0x18000b78b  lea     rax, [rsp+4E0h+var_478]
0x18000b790  mov     edx, 1F6h; level
0x18000b795  mov     [rsp+4E0h+totalentries], rax; totalentries
0x18000b79a  mov     rcx, rsi; servername
0x18000b79d  lea     rax, [rsp+4E0h+var_488]
0x18000b7a2  mov     [rsp+4E0h+entriesread], rax; entriesread
0x18000b7a7  call    cs:__imp_NetShareEnum
0x18000b7ad  xor     r11d, r11d
0x18000b7b0  mov     [rsp+4E0h+var_474], eax
0x18000b7b4  test    eax, eax
0x18000b7b6  jz      short loc_18000B7C3
0x18000b7b8  cmp     eax, 0EAh
0x18000b7bd  jnz     loc_18000BB95
0x18000b7c3  mov     edx, r11d
0x18000b7c6  mov     rax, [rsp+4E0h+bufptr]
0x18000b7cb  mov     [rsp+4E0h+var_498], rax
0x18000b7d0  mov     [rsp+4E0h+var_4A0], edx
0x18000b7d4  cmp     [rsp+4E0h+var_488], r11d
0x18000b7d9  jbe     loc_18000B963
0x18000b7df  cmp     [rax+8], r11d
0x18000b7e3  jnz     loc_18000B938
0x18000b7e9  mov     rcx, [rax+28h]; String1
0x18000b7ed  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000b7f1  mov     [rsp+4E0h+String1], rcx
0x18000b7f6  inc     rsi
0x18000b7f9  cmp     [rcx+rsi*2], r11w
0x18000b7fe  jnz     short loc_18000B7F6
0x18000b800  cmp     esi, dword ptr [rsp+4E0h+MaxCount+4]
0x18000b804  jbe     loc_18000B938
0x18000b80a  mov     eax, dword ptr [rsp+4E0h+MaxCount]
0x18000b80e  cmp     esi, eax
0x18000b810  ja      loc_18000B938
0x18000b816  jnz     short loc_18000B83E
0x18000b818  mov     r8d, eax; MaxCount
0x18000b81b  lea     rdx, [rbp+3E0h+Buffer]; String2
0x18000b822  call    cs:__imp__wcsnicmp
0x18000b828  xor     r11d, r11d
0x18000b82b  test    eax, eax
0x18000b82d  jz      short loc_18000B87A
0x18000b82f  mov     eax, dword ptr [rsp+4E0h+MaxCount]
0x18000b833  cmp     esi, eax
0x18000b835  mov     rcx, [rsp+4E0h+String1]; String1
0x18000b83a  mov     edx, [rsp+4E0h+var_4A0]
0x18000b83e  jnb     loc_18000B938
0x18000b844  mov     eax, esi
0x18000b846  lea     rdx, [rbp+3E0h+Buffer]; String2
0x18000b84d  mov     r8d, esi; MaxCount
0x18000b850  mov     [rsp+4E0h+String1], rax
0x18000b855  call    cs:__imp__wcsnicmp
0x18000b85b  xor     r11d, r11d
0x18000b85e  test    eax, eax
0x18000b860  jnz     loc_18000B934
0x18000b866  mov     rax, [rsp+4E0h+String1]
0x18000b86b  cmp     [rbp+rax*2+3E0h+Buffer], r15w
0x18000b874  jnz     loc_18000B934
0x18000b87a  mov     rcx, rbx; hMem
0x18000b87d  call    cs:__imp_LocalFree
0x18000b883  mov     rax, [rsp+4E0h+var_498]
0x18000b888  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000b88c  xor     r8d, r8d
0x18000b88f  mov     rcx, [rax]
0x18000b892  inc     rdx
0x18000b895  cmp     [rcx+rdx*2], r8w
0x18000b89a  jnz     short loc_18000B892
0x18000b89c  lea     rdx, ds:2[rdx*2]; uBytes
0x18000b8a4  mov     ecx, 40h ; '@'; uFlags
0x18000b8a9  call    cs:__imp_LocalAlloc
0x18000b8af  xor     r11d, r11d
0x18000b8b2  mov     rbx, rax
0x18000b8b5  test    rax, rax
0x18000b8b8  jz      loc_18000B958
0x18000b8be  mov     rax, [rsp+4E0h+var_498]
0x18000b8c3  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000b8c7  mov     r8, [rax]; unsigned __int16 *
0x18000b8ca  inc     rdx
0x18000b8cd  cmp     [r8+rdx*2], r11w
0x18000b8d2  jnz     short loc_18000B8CA
0x18000b8d4  inc     rdx; unsigned __int64
0x18000b8d7  mov     rcx, rbx; unsigned __int16 *
0x18000b8da  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b8df  mov     rax, [rsp+4E0h+var_498]
0x18000b8e4  mov     dword ptr [rsp+4E0h+MaxCount+4], esi
0x18000b8e8  cmp     [rax+40h], r11
0x18000b8ec  jz      short loc_18000B934
0x18000b8ee  mov     rcx, r13; hMem
0x18000b8f1  call    cs:__imp_LocalFree
0x18000b8f7  mov     rcx, [rsp+4E0h+var_498]
0x18000b8fc  mov     rcx, [rcx+40h]; pSecurityDescriptor
0x18000b900  call    cs:__imp_GetSecurityDescriptorLength
0x18000b906  mov     edx, eax; uBytes
0x18000b908  mov     ecx, 40h ; '@'; uFlags
0x18000b90d  mov     esi, eax
0x18000b90f  call    cs:__imp_LocalAlloc
0x18000b915  mov     r13, rax
0x18000b918  test    rax, rax
0x18000b91b  jz      short loc_18000B958
0x18000b91d  mov     rdx, [rsp+4E0h+var_498]
0x18000b922  mov     r8d, esi; Size
0x18000b925  mov     rcx, rax; void *
0x18000b928  mov     rdx, [rdx+40h]; Src
0x18000b92c  call    memcpy_0
0x18000b931  xor     r11d, r11d
0x18000b934  mov     edx, [rsp+4E0h+var_4A0]
0x18000b938  mov     rax, [rsp+4E0h+var_498]
0x18000b93d  inc     edx
0x18000b93f  add     rax, 48h ; 'H'
0x18000b943  mov     [rsp+4E0h+var_4A0], edx
0x18000b947  mov     [rsp+4E0h+var_498], rax
0x18000b94c  cmp     edx, [rsp+4E0h+var_488]
0x18000b950  jb      loc_18000B7DF
0x18000b956  jmp     short loc_18000B95E
0x18000b958  mov     r14d, 8007000Eh
0x18000b95e  mov     rsi, [rsp+4E0h+servername]
0x18000b963  mov     rcx, [rsp+4E0h+bufptr]; Buffer
0x18000b968  call    cs:__imp_NetApiBufferFree
0x18000b96e  test    r14d, r14d
0x18000b971  js      loc_18000BC2C
0x18000b977  cmp     [rsp+4E0h+var_474], 0EAh
0x18000b97f  jz      loc_18000B778
0x18000b985  xor     r15d, r15d
0x18000b988  jmp     loc_18000BBAA
0x18000b98d  mov     r14d, 8007000Eh
0x18000b993  mov     rsi, [rsp+4E0h+servername]
0x18000b998  jmp     loc_18000BB98
0x18000b99d  xor     edx, edx; Val
0x18000b99f  lea     rcx, [rbp+3E0h+Source]; void *
0x18000b9a3  mov     r8d, 208h; Size
0x18000b9a9  call    memset_0
0x18000b9ae  mov     r12d, 104h
0x18000b9b4  lea     r9, [rbp+3E0h+Source]; unsigned __int16 *
0x18000b9b8  xor     r8d, r8d; unsigned int
0x18000b9bb  mov     dword ptr [rsp+4E0h+entriesread], r12d; unsigned int
0x18000b9c0  xor     edx, edx; unsigned __int16 *
0x18000b9c2  mov     rcx, rsi; unsigned __int16 *
0x18000b9c5  call    ?IsDfsPath@@YAHPEBGPEAGI1I@Z; IsDfsPath(ushort const *,ushort *,uint,ushort *,uint)
0x18000b9ca  test    eax, eax
0x18000b9cc  jnz     short loc_18000BA4C
0x18000b9ce  mov     edx, r12d; MaxCount
0x18000b9d1  mov     rcx, rsi; Source
0x18000b9d4  call    cs:__imp_wcsnlen
0x18000b9da  cmp     rax, 2
0x18000b9de  jbe     short loc_18000BA4C
0x18000b9e0  mov     r15d, 5Ch ; '\'
0x18000b9e6  cmp     [rsi], r15w
0x18000b9ea  jnz     short loc_18000BA47
0x18000b9ec  cmp     [rsi+2], r15w
0x18000b9f1  jnz     short loc_18000BA47
0x18000b9f3  mov     edx, r15d; Ch
0x18000b9f6  lea     rcx, [rsi+4]; Str
0x18000b9fa  call    cs:__imp_wcschr
0x18000ba00  test    rax, rax
0x18000ba03  jz      short loc_18000BA47
0x18000ba05  lea     rbx, [rax+2]
0x18000ba09  mov     edx, r15d; Ch
0x18000ba0c  mov     rcx, rbx; Str
0x18000ba0f  call    cs:__imp_wcschr
0x18000ba15  mov     rcx, rbx; Str
0x18000ba18  test    rax, rax
0x18000ba1b  jz      short loc_18000BA22
0x18000ba1d  mov     edx, r15d
0x18000ba20  jmp     short loc_18000BA24
0x18000ba22  xor     edx, edx; Ch
0x18000ba24  call    cs:__imp_wcschr
0x18000ba2a  mov     r8, rbx; unsigned __int16 *
0x18000ba2d  lea     rcx, [rbp+3E0h+Source]; unsigned __int16 *
0x18000ba31  sub     rax, rbx
0x18000ba34  sar     rax, 1
0x18000ba37  inc     eax
0x18000ba39  cmp     eax, r12d
0x18000ba3c  cmova   eax, r12d
0x18000ba40  mov     edx, eax; unsigned __int64
0x18000ba42  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000ba47  mov     r15, [rsp+4E0h+servername]
0x18000ba4c  mov     rdx, r12; MaxCount
0x18000ba4f  lea     rcx, [rbp+3E0h+Source]; Source
0x18000ba53  call    cs:__imp_wcsnlen
0x18000ba59  inc     eax
0x18000ba5b  mov     ecx, 40h ; '@'; uFlags
0x18000ba60  mov     esi, eax
0x18000ba62  lea     rdx, [rax+rax]; uBytes
0x18000ba66  call    cs:__imp_LocalAlloc
0x18000ba6c  mov     rbx, rax
0x18000ba6f  test    rax, rax
0x18000ba72  jz      loc_18000BC2C
0x18000ba78  lea     r8, [rbp+3E0h+Source]; unsigned __int16 *
0x18000ba7c  mov     edx, esi; unsigned __int64
0x18000ba7e  mov     rcx, rax; unsigned __int16 *
0x18000ba81  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000ba86  lea     r9, [rsp+4E0h+var_498]; bufptr
0x18000ba8b  mov     r8d, 1F6h; level
0x18000ba91  lea     rdx, [rbp+3E0h+Source]; netname
0x18000ba95  mov     rcx, r15; servername
0x18000ba98  call    cs:__imp_NetShareGetInfo
0x18000ba9e  test    eax, eax
0x18000baa0  jnz     short loc_18000BB0C
0x18000baa2  mov     rcx, [rsp+4E0h+var_498]; Buffer
0x18000baa7  xor     r15d, r15d
0x18000baaa  cmp     [rcx+8], r15d
0x18000baae  jnz     short loc_18000BAFB
0x18000bab0  mov     rax, [rcx+40h]
0x18000bab4  test    rax, rax
0x18000bab7  jz      short loc_18000BAFB
0x18000bab9  mov     rcx, rax; pSecurityDescriptor
0x18000babc  call    cs:__imp_GetSecurityDescriptorLength
0x18000bac2  mov     edx, eax; uBytes
0x18000bac4  lea     ecx, [r15+40h]; uFlags
0x18000bac8  mov     esi, eax
0x18000baca  call    cs:__imp_LocalAlloc
0x18000bad0  mov     r13, rax
0x18000bad3  test    rax, rax
0x18000bad6  jnz     short loc_18000BAE5
0x18000bad8  mov     r14d, 8007000Eh
0x18000bade  mov     rcx, [rsp+4E0h+var_498]
0x18000bae3  jmp     short loc_18000BB01
0x18000bae5  mov     rdx, [rsp+4E0h+var_498]
0x18000baea  mov     r8, rsi; Size
0x18000baed  mov     rcx, rax; void *
0x18000baf0  mov     rdx, [rdx+40h]; Src
0x18000baf4  call    memcpy_0
0x18000baf9  jmp     short loc_18000BADE
0x18000bafb  mov     r14d, 80070057h
0x18000bb01  call    cs:__imp_NetApiBufferFree
0x18000bb07  jmp     loc_18000B993
0x18000bb0c  mov     rdx, r12; MaxCount
0x18000bb0f  mov     rcx, r15; Source
0x18000bb12  call    cs:__imp_wcsnlen
0x18000bb18  mov     ecx, 40h ; '@'; uFlags
0x18000bb1d  mov     r14, rax
0x18000bb20  lea     rdx, ds:2[rax*2]; uBytes
0x18000bb28  call    cs:__imp_LocalAlloc
0x18000bb2e  mov     rsi, rax
0x18000bb31  test    rax, rax
0x18000bb34  jz      loc_18000BC2C
0x18000bb3a  lea     rdx, [r14+1]; unsigned __int64
0x18000bb3e  mov     r8, r15; unsigned __int16 *
0x18000bb41  mov     rcx, rax; unsigned __int16 *
0x18000bb44  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000bb49  mov     edx, 110h; uBytes
0x18000bb4e  mov     ecx, 40h ; '@'; uFlags
0x18000bb53  call    cs:__imp_LocalAlloc
0x18000bb59  xor     r15d, r15d
0x18000bb5c  test    rax, rax
0x18000bb5f  jz      loc_18000BC23
0x18000bb65  xor     r9d, r9d; void *
0x18000bb68  mov     r8, rsi; unsigned __int16 *
0x18000bb6b  mov     rdx, rbx; unsigned __int16 *
0x18000bb6e  mov     rcx, rax; this
0x18000bb71  call    ??0CShareSecurityInformation@@QEAA@PEAG0PEAX@Z; CShareSecurityInformation::CShareSecurityInformation(ushort *,ushort *,void *)
  ... truncated ...
```
