# XE_FileWriter<XE_FileWriterDefaultPolicy<1,&wchar_t near * XEPackage0::DefaultFileExtension>,XE_MetadataTracker>::CreateLog(XE_Log *)

- ea: `0x1005bf9c0`
- end: `0x1005bfe78`
- name: `?CreateLog@?$XE_FileWriter@V?$XE_FileWriterDefaultPolicy@$00$1?DefaultFileExtension@XEPackage0@@3PA_WA@@VXE_MetadataTracker@@@@AEAAHPEAVXE_Log@@@Z`
- size: `1208`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x1005bec50`

## callees

- `0x100403070`
- `0x100444860`
- `0x100448a50`
- `0x1005bf8e0`
- `0x1005bf9c0`
- `0x1005c01f0`
- `0x1005c0470`

## import_xrefs

- `KERNEL32!SystemTimeToFileTime` at `0x1005bfa7a`
- `KERNEL32!SystemTimeToFileTime` at `0x1005bfa7a`
- `KERNEL32!GetSystemTime` at `0x1005bfa49`
- `KERNEL32!GetSystemTime` at `0x1005bfd97`
- `KERNEL32!GetSystemTime` at `0x1005bfa49`
- `KERNEL32!GetSystemTime` at `0x1005bfd97`
- `KERNEL32!SetEndOfFile` at `0x1005bfc38`
- `KERNEL32!SetEndOfFile` at `0x1005bfd30`
- `KERNEL32!SetEndOfFile` at `0x1005bfc38`
- `KERNEL32!SetEndOfFile` at `0x1005bfd30`
- `KERNEL32!SetFilePointerEx` at `0x1005bfc27`
- `KERNEL32!SetFilePointerEx` at `0x1005bfd1f`
- `KERNEL32!SetFilePointerEx` at `0x1005bfc27`
- `KERNEL32!SetFilePointerEx` at `0x1005bfd1f`
- `KERNEL32!CloseHandle` at `0x1005bfbd4`
- `KERNEL32!CloseHandle` at `0x1005bfd50`
- `KERNEL32!CloseHandle` at `0x1005bfbd4`
- `KERNEL32!CloseHandle` at `0x1005bfd50`
- `KERNEL32!GetLastError` at `0x1005bfc4c`
- `KERNEL32!GetLastError` at `0x1005bfd6a`
- `KERNEL32!GetLastError` at `0x1005bfdb2`
- `KERNEL32!GetLastError` at `0x1005bfdd1`
- `KERNEL32!GetLastError` at `0x1005bfe30`
- `KERNEL32!GetLastError` at `0x1005bfc4c`
- `KERNEL32!GetLastError` at `0x1005bfd6a`
- `KERNEL32!GetLastError` at `0x1005bfdb2`
- `KERNEL32!GetLastError` at `0x1005bfdd1`
- `KERNEL32!GetLastError` at `0x1005bfe30`

## pseudocode

```c
__int64 __fastcall XE_FileWriter<XE_FileWriterDefaultPolicy<1,&wchar_t near * XEPackage0::DefaultFileExtension>,XE_MetadataTracker>::CreateLog(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rax
  unsigned int v3; // r14d
  __int64 v6; // rsi
  int v7; // ebp
  unsigned __int16 v8; // r13
  unsigned __int8 (__fastcall ***v9)(_QWORD, __int64); // rax
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rsi
  struct _FILETIME v13; // rdx
  bool v14; // zf
  __int64 v15; // r8
  _WORD *v16; // rdx
  __int16 v17; // ax
  _WORD *v18; // rax
  __int64 v19; // rax
  void *v20; // rcx
  void *v21; // rsi
  __int64 v22; // rax
  unsigned __int64 v23; // rdx
  int v24; // eax
  __int64 *v25; // rsi
  __int64 v26; // rbp
  DWORD v27; // eax
  __int64 v28; // rax
  unsigned __int64 v29; // rax
  void *v30; // rcx
  void *v31; // rcx
  DWORD v32; // eax
  __int64 *v33; // rsi
  __int64 v34; // rbp
  DWORD LastError; // eax
  unsigned __int8 (__fastcall ***v36)(_QWORD, __int64); // rax
  __int64 v37; // rdx
  __int64 *v38; // rbx
  __int64 v39; // rdi
  DWORD v40; // eax
  __int64 v42; // [rsp+20h] [rbp-2B8h]
  int v43; // [rsp+28h] [rbp-2B0h]
  __int64 v44; // [rsp+30h] [rbp-2A8h]
  int v45; // [rsp+40h] [rbp-298h]
  struct _FILETIME FileTime; // [rsp+48h] [rbp-290h] BYREF
  SYSTEMTIME v47; // [rsp+50h] [rbp-288h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+60h] [rbp-278h] BYREF
  struct _SYSTEMTIME v49; // [rsp+70h] [rbp-268h] BYREF
  _WORD v50[264]; // [rsp+80h] [rbp-258h] BYREF

  v2 = a1 + 16;
  v50[0] = 0;
  v3 = 0;
  v45 = 0;
  while ( 1 )
  {
    v6 = *(unsigned int *)(a2 + 44);
    v7 = *(_DWORD *)(a2 + 40);
    v8 = 0;
    if ( !(unsigned int)XE_FileWriterDefaultPolicy<1,&wchar_t near * XEPackage0::DefaultFileExtension>::CanCreateFile(
                          v2,
                          v6,
                          *(unsigned int *)(a2 + 48)) )
      goto LABEL_57;
    v9 = (unsigned __int8 (__fastcall ***)(_QWORD, __int64))qword_1007152F8();
    LOBYTE(v10) = 6;
    if ( !(**v9)(v9, v10) )
    {
      GetSystemTime(&SystemTime);
      *(struct _SYSTEMTIME *)(a2 + 72) = SystemTime;
    }
    v11 = *(_QWORD *)(a1 + 40);
    v47 = *(SYSTEMTIME *)(a2 + 72);
    v12 = *(_QWORD *)(v11 + 8) + 1580 * v6;
    if ( !SystemTimeToFileTime(&v47, &FileTime) )
      goto LABEL_56;
    v13 = FileTime;
    v14 = FileTime == 0;
    if ( *(__int64 *)&FileTime < 0 )
    {
      v13 = (struct _FILETIME)-*(__int64 *)&FileTime;
      v14 = FileTime == 0;
    }
    LODWORD(v44) = 1;
    if ( v14 )
      v13 = (struct _FILETIME)1LL;
    if ( !(unsigned int)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))XE_LogSpecs::LogSpec::CreateFilePathInternal)(
                          v12,
                          v13,
                          v50,
                          260,
                          &v47,
                          v7,
                          v44) )
    {
LABEL_56:
      v33 = *(__int64 **)(a1 + 1656);
      v34 = *v33;
      LastError = GetLastError();
      (*(void (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD))(v34 + 48))(v33, LastError, 0, 0);
      goto LABEL_57;
    }
    v15 = 260;
    v16 = (_WORD *)(a2 + 112);
    do
    {
      if ( v15 == -2147483386 )
        break;
      v17 = *(_WORD *)((char *)v16 + (_QWORD)&v50[-56] - a2);
      if ( !v17 )
        break;
      *v16++ = v17;
      --v15;
    }
    while ( v15 );
    v18 = v16 - 1;
    if ( v15 )
      v18 = v16;
    *v18 = 0;
    *(_QWORD *)(a2 + 104) = a2 + 112;
    if ( qword_100715060 && (unsigned __int8)qword_100715060(a2 + 112, 260) )
    {
      *(_DWORD *)(a2 + 52) = 1;
      XE_FileWriter<XE_FileWriterDefaultPolicy<1,&wchar_t near * XEPackage0::DefaultFileExtension>,XE_MetadataTracker>::OpenAzureContainerIfNeeded(a1);
      *(_QWORD *)(a1 + 1808) = 1;
      LODWORD(v42) = 1;
      v19 = qword_100715068(v50, 0x40000000, 1, 0, v42, 671088768, 0, a1 + 1688);
    }
    else
    {
      v44 = 0;
      v43 = 671088768;
      *(_DWORD *)(a2 + 52) = 0;
      v19 = qword_100714F18(v50, 0x40000000, 1, 0, 1, v43, v44);
    }
    v20 = *(void **)(a2 + 632);
    v21 = (void *)v19;
    if ( v20 != (void *)-1LL && v20 != (void *)v19 )
      CloseHandle(v20);
    *(_QWORD *)(a2 + 632) = v21;
    if ( v21 == (void *)-1LL )
    {
      v32 = GetLastError();
      if ( v32 == 80 )
      {
        GetSystemTime(&v49);
        *(struct _SYSTEMTIME *)(a2 + 72) = v49;
      }
      else
      {
        (*(void (__fastcall **)(_QWORD, _QWORD, _WORD *, _QWORD))(**(_QWORD **)(a1 + 1656) + 48LL))(
          *(_QWORD *)(a1 + 1656),
          v32,
          v50,
          0);
      }
      goto LABEL_57;
    }
    v22 = *(_QWORD *)(a1 + 32);
    *(_QWORD *)(a2 + 16) = v22;
    if ( v22 )
    {
      v23 = *(unsigned int *)(a2 + 8)
          * (((unsigned __int64)*(unsigned int *)(a2 + 8) + v22 - 1)
           / *(unsigned int *)(a2 + 8));
      if ( *(_DWORD *)(a2 + 52) )
      {
        v24 = qword_100715080(v21, v23);
      }
      else
      {
        if ( !SetFilePointerEx(v21, (LARGE_INTEGER)v23, 0, 0) )
          goto LABEL_31;
        v24 = SetEndOfFile(*(HANDLE *)(a2 + 632));
      }
      if ( v24 )
        goto LABEL_32;
LABEL_31:
      v25 = *(__int64 **)(a1 + 1656);
      v26 = *v25;
      v27 = GetLastError();
      (*(void (__fastcall **)(__int64 *, _QWORD, _QWORD, _WORD *))(v26 + 56))(v25, v27, *(_QWORD *)(a2 + 16), v50);
      v8 = 36;
      if ( v3 )
        goto LABEL_32;
      goto LABEL_42;
    }
    *(_QWORD *)(a2 + 16) = *(_QWORD *)(a1 + 24);
    if ( !*(_DWORD *)(a2 + 52)
      || ((v28 = *(_QWORD *)(a1 + 24)) == 0
        ? (v29 = 0)
        : (v29 = *(unsigned int *)(a2 + 8)
               * (((unsigned __int64)*(unsigned int *)(a2 + 8) + v28 - 1)
                / *(unsigned int *)(a2 + 8))),
          (v3 = qword_100715080(v21, v29)) != 0) )
    {
LABEL_32:
      v3 = XE_FileWriter<XE_FileWriterDefaultPolicy<1,&wchar_t near * XEPackage0::DefaultFileExtension>,XE_MetadataTracker>::WriteFileHeader(
             a1,
             a2);
      if ( v3 )
      {
        v3 = XE_MetadataTracker::SerializeMetadata(
               *(XE_MetadataTracker **)(a1 + 1664),
               (const struct XE_SessionMetadata *)(*(_QWORD *)(a1 + 1664) + 32LL),
               (void *)a2);
        if ( v3 )
          goto LABEL_57;
        v8 = 38;
      }
      else
      {
        v8 = 39;
      }
      goto LABEL_42;
    }
    v8 = 37;
LABEL_42:
    v30 = *(void **)(a2 + 632);
    if ( v30 != (void *)-1LL )
    {
      if ( *(_DWORD *)(a2 + 52) )
      {
        qword_100715080(v30, 0);
      }
      else if ( SetFilePointerEx(v30, 0, 0, 0) )
      {
        SetEndOfFile(*(HANDLE *)(a2 + 632));
      }
      v31 = *(void **)(a2 + 632);
      if ( *(_DWORD *)(a2 + 52) )
      {
        qword_100715090(v31);
      }
      else if ( v31 != (void *)-1LL )
      {
        CloseHandle(v31);
      }
      *(_QWORD *)(a2 + 632) = -1;
    }
    *(_QWORD *)(a2 + 648) = 0;
LABEL_57:
    if ( *(_QWORD *)(a2 + 632) != -1 )
      break;
    if ( GetLastError() != 80 )
      break;
    v36 = (unsigned __int8 (__fastcall ***)(_QWORD, __int64))qword_1007152F8();
    LOBYTE(v37) = 14;
    v14 = (**v36)(v36, v37) == 0;
    v2 = a1 + 16;
    if ( !v14 )
    {
      ++v45;
      v2 = a1 + 16;
      if ( v45 >= 10 )
        break;
    }
  }
  if ( v3 )
  {
    *(_DWORD *)(a2 + 48) = 0;
  }
  else if ( !*(_WORD *)(qword_100715040() + 4) )
  {
    v38 = *(__int64 **)(a1 + 1656);
    v39 = *v38;
    v40 = GetLastError();
    (*(void (__fastcall **)(__int64 *, _QWORD, _WORD *, _QWORD))(v39 + 48))(v38, v40, v50, v8);
  }
  return v3;
}

```

## disassembly

```asm
0x1005bf9c0  mov     [rsp+arg_10], rbx
0x1005bf9c5  push    rbp
0x1005bf9c6  push    rsi
0x1005bf9c7  push    rdi
0x1005bf9c8  push    r12
0x1005bf9ca  push    r13
0x1005bf9cc  push    r14
0x1005bf9ce  push    r15
0x1005bf9d0  sub     rsp, 2A0h
0x1005bf9d7  mov     rax, cs:__security_cookie
0x1005bf9de  xor     rax, rsp
0x1005bf9e1  mov     [rsp+2D8h+var_48], rax
0x1005bf9e9  xor     ebx, ebx
0x1005bf9eb  lea     rax, [rcx+10h]
0x1005bf9ef  mov     [rsp+2D8h+var_258], bx
0x1005bf9f7  mov     r14d, ebx
0x1005bf9fa  mov     [rsp+2D8h+var_298], ebx
0x1005bf9fe  mov     rdi, rdx
0x1005bfa01  mov     r15, rcx
0x1005bfa04  nop     dword ptr [rax+00h]
0x1005bfa08  nop     dword ptr [rax+rax+00000000h]
0x1005bfa10  mov     esi, [rdi+2Ch]
0x1005bfa13  mov     rcx, rax
0x1005bfa16  mov     ebp, [rdi+28h]
0x1005bfa19  mov     edx, esi
0x1005bfa1b  mov     r8d, [rdi+30h]
0x1005bfa1f  mov     r13d, ebx
0x1005bfa22  call    ?CanCreateFile@?$XE_FileWriterDefaultPolicy@$00$1?DefaultFileExtension@XEPackage0@@3PA_WA@@QEAAHIH@Z; XE_FileWriterDefaultPolicy<1,&wchar_t near * XEPackage0::DefaultFileExtension>::CanCreateFile(uint,int)
0x1005bfa27  test    eax, eax
0x1005bfa29  jz      loc_1005BFDC7
0x1005bfa2f  call    cs:qword_1007152F8
0x1005bfa35  mov     dl, 6
0x1005bfa37  mov     rcx, rax
0x1005bfa3a  mov     r8, [rax]
0x1005bfa3d  call    qword ptr [r8]
0x1005bfa40  test    al, al
0x1005bfa42  jnz     short loc_1005BFA58
0x1005bfa44  lea     rcx, [rsp+2D8h+SystemTime]; lpSystemTime
0x1005bfa49  call    cs:__imp_GetSystemTime
0x1005bfa4f  movups  xmm0, xmmword ptr [rsp+2D8h+SystemTime.wYear]
0x1005bfa54  movups  xmmword ptr [rdi+48h], xmm0
0x1005bfa58  mov     rcx, [r15+28h]
0x1005bfa5c  lea     rdx, [rsp+2D8h+FileTime]; lpFileTime
0x1005bfa61  movups  xmm0, xmmword ptr [rdi+48h]
0x1005bfa65  imul    rsi, 62Ch
0x1005bfa6c  movups  xmmword ptr [rsp+2D8h+var_288.wYear], xmm0
0x1005bfa71  add     rsi, [rcx+8]
0x1005bfa75  lea     rcx, [rsp+2D8h+var_288]; lpSystemTime
0x1005bfa7a  call    cs:__imp_SystemTimeToFileTime
0x1005bfa80  test    eax, eax
0x1005bfa82  jz      loc_1005BFDA8
0x1005bfa88  mov     rdx, qword ptr [rsp+2D8h+FileTime.dwLowDateTime]
0x1005bfa8d  test    rdx, rdx
0x1005bfa90  jns     short loc_1005BFA98
0x1005bfa92  neg     rdx
0x1005bfa95  test    rdx, rdx
0x1005bfa98  mov     eax, 1
0x1005bfa9d  lea     r8, [rsp+2D8h+var_258]
0x1005bfaa5  mov     dword ptr [rsp+2D8h+var_2A8], eax
0x1005bfaa9  cmovz   rdx, rax
0x1005bfaad  lea     rax, [rsp+2D8h+var_288]
0x1005bfab2  mov     [rsp+2D8h+var_2B0], ebp
0x1005bfab6  mov     r9d, 104h
0x1005bfabc  mov     [rsp+2D8h+var_2B8], rax
0x1005bfac1  mov     rcx, rsi
0x1005bfac4  call    ?CreateFilePathInternal@LogSpec@XE_LogSpecs@@AEBAH_JQEA_WIAEBU_SYSTEMTIME@@IW4XE_FileSourceType@@@Z; XE_LogSpecs::LogSpec::CreateFilePathInternal(__int64,wchar_t * const,uint,_SYSTEMTIME const &,uint,XE_FileSourceType)
0x1005bfac9  test    eax, eax
0x1005bfacb  jz      loc_1005BFDA8
0x1005bfad1  lea     r9, [rdi+70h]
0x1005bfad5  mov     r8d, 104h
0x1005bfadb  lea     rcx, [rsp+2D8h+var_258]
0x1005bfae3  mov     rdx, r9
0x1005bfae6  sub     rcx, r9
0x1005bfae9  nop     dword ptr [rax+00000000h]
0x1005bfaf0  lea     rax, [r8+7FFFFEFAh]
0x1005bfaf7  test    rax, rax
0x1005bfafa  jz      short loc_1005BFB12
0x1005bfafc  movzx   eax, word ptr [rcx+rdx]
0x1005bfb00  test    ax, ax
0x1005bfb03  jz      short loc_1005BFB12
0x1005bfb05  mov     [rdx], ax
0x1005bfb08  add     rdx, 2
0x1005bfb0c  sub     r8, 1
0x1005bfb10  jnz     short loc_1005BFAF0
0x1005bfb12  test    r8, r8
0x1005bfb15  lea     rax, [rdx-2]
0x1005bfb19  cmovnz  rax, rdx
0x1005bfb1d  mov     [rax], bx
0x1005bfb20  mov     [rdi+68h], r9
0x1005bfb24  mov     rax, cs:qword_100715060
0x1005bfb2b  test    rax, rax
0x1005bfb2e  jz      short loc_1005BFB8D
0x1005bfb30  mov     edx, 104h
0x1005bfb35  mov     rcx, r9
0x1005bfb38  call    rax ; qword_100715060
0x1005bfb3a  test    al, al
0x1005bfb3c  jz      short loc_1005BFB8D
0x1005bfb3e  mov     ebp, 1
0x1005bfb43  mov     rcx, r15
0x1005bfb46  mov     [rdi+34h], ebp
0x1005bfb49  call    ?OpenAzureContainerIfNeeded@?$XE_FileWriter@V?$XE_FileWriterDefaultPolicy@$00$1?DefaultFileExtension@XEPackage0@@3PA_WA@@VXE_MetadataTracker@@@@AEAA_NXZ; XE_FileWriter<XE_FileWriterDefaultPolicy<1,&wchar_t near * XEPackage0::DefaultFileExtension>,XE_MetadataTracker>::OpenAzureContainerIfNeeded(void)
0x1005bfb4e  lea     rax, [r15+698h]
0x1005bfb55  mov     [r15+710h], rbp
0x1005bfb5c  mov     [rsp+2D8h+var_2A0], rax
0x1005bfb61  lea     rcx, [rsp+2D8h+var_258]
0x1005bfb69  mov     [rsp+2D8h+var_2A8], rbx
0x1005bfb6e  xor     r9d, r9d
0x1005bfb71  mov     [rsp+2D8h+var_2B0], 28000080h
0x1005bfb79  mov     r8d, ebp
0x1005bfb7c  mov     edx, 40000000h
0x1005bfb81  mov     dword ptr [rsp+2D8h+var_2B8], ebp
0x1005bfb85  call    cs:qword_100715068
0x1005bfb8b  jmp     short loc_1005BFBBF
0x1005bfb8d  mov     eax, 1
0x1005bfb92  mov     [rsp+2D8h+var_2A8], rbx
0x1005bfb97  mov     r8d, eax
0x1005bfb9a  mov     [rsp+2D8h+var_2B0], 28000080h
0x1005bfba2  xor     r9d, r9d
0x1005bfba5  mov     [rdi+34h], ebx
0x1005bfba8  mov     edx, 40000000h
0x1005bfbad  mov     dword ptr [rsp+2D8h+var_2B8], eax
0x1005bfbb1  lea     rcx, [rsp+2D8h+var_258]
0x1005bfbb9  call    cs:qword_100714F18
0x1005bfbbf  mov     rcx, [rdi+278h]; hObject
0x1005bfbc6  mov     rsi, rax
0x1005bfbc9  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1005bfbcd  jz      short loc_1005BFBDA
0x1005bfbcf  cmp     rcx, rax
0x1005bfbd2  jz      short loc_1005BFBDA
0x1005bfbd4  call    cs:__imp_CloseHandle
0x1005bfbda  mov     [rdi+278h], rsi
0x1005bfbe1  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1005bfbe5  jz      loc_1005BFD6A
0x1005bfbeb  mov     rax, [r15+20h]
0x1005bfbef  mov     [rdi+10h], rax
0x1005bfbf3  test    rax, rax
0x1005bfbf6  jz      loc_1005BFCAE
0x1005bfbfc  mov     ecx, [rdi+8]
0x1005bfbff  dec     rax
0x1005bfc02  add     rax, rcx
0x1005bfc05  xor     edx, edx
0x1005bfc07  div     rcx
0x1005bfc0a  imul    rax, rcx
0x1005bfc0e  mov     rcx, rsi; hFile
0x1005bfc11  mov     rdx, rax; liDistanceToMove
0x1005bfc14  cmp     [rdi+34h], ebx
0x1005bfc17  jz      short loc_1005BFC21
0x1005bfc19  call    cs:qword_100715080
0x1005bfc1f  jmp     short loc_1005BFC3E
0x1005bfc21  xor     r9d, r9d; dwMoveMethod
0x1005bfc24  xor     r8d, r8d; lpNewFilePointer
0x1005bfc27  call    cs:__imp_SetFilePointerEx
0x1005bfc2d  test    eax, eax
0x1005bfc2f  jz      short loc_1005BFC42
0x1005bfc31  mov     rcx, [rdi+278h]; hFile
0x1005bfc38  call    cs:__imp_SetEndOfFile
0x1005bfc3e  test    eax, eax
0x1005bfc40  jnz     short loc_1005BFC75
0x1005bfc42  mov     rsi, [r15+678h]
0x1005bfc49  mov     rbp, [rsi]
0x1005bfc4c  call    cs:__imp_GetLastError
0x1005bfc52  mov     r8, [rdi+10h]
0x1005bfc56  lea     r9, [rsp+2D8h+var_258]
0x1005bfc5e  mov     edx, eax
0x1005bfc60  mov     rcx, rsi
0x1005bfc63  call    qword ptr [rbp+38h]
0x1005bfc66  mov     r13d, 24h ; '$'
0x1005bfc6c  test    r14d, r14d
0x1005bfc6f  jz      loc_1005BFCFA
0x1005bfc75  mov     eax, [rdi+28h]
0x1005bfc78  mov     rdx, rdi
0x1005bfc7b  mov     rcx, r15
0x1005bfc7e  call    ?WriteFileHeader@?$XE_FileWriter@V?$XE_FileWriterDefaultPolicy@$00$1?DefaultFileExtension@XEPackage0@@3PA_WA@@VXE_MetadataTracker@@@@AEAAHPEAVXE_Log@@@Z; XE_FileWriter<XE_FileWriterDefaultPolicy<1,&wchar_t near * XEPackage0::DefaultFileExtension>,XE_MetadataTracker>::WriteFileHeader(XE_Log *)
0x1005bfc83  mov     r14d, eax
0x1005bfc86  test    eax, eax
0x1005bfc88  jz      short loc_1005BFCF4
0x1005bfc8a  mov     rcx, [r15+680h]; this
0x1005bfc91  mov     r8, rdi; void *
0x1005bfc94  lea     rdx, [rcx+20h]; struct XE_SessionMetadata *
0x1005bfc98  call    ?SerializeMetadata@XE_MetadataTracker@@AEAAHPEBVXE_SessionMetadata@@PEAX@Z; XE_MetadataTracker::SerializeMetadata(XE_SessionMetadata const *,void *)
0x1005bfc9d  mov     r14d, eax
0x1005bfca0  test    eax, eax
0x1005bfca2  jnz     loc_1005BFDC7
0x1005bfca8  lea     r13d, [rax+26h]
0x1005bfcac  jmp     short loc_1005BFCFA
0x1005bfcae  mov     rax, [r15+18h]
0x1005bfcb2  mov     [rdi+10h], rax
0x1005bfcb6  cmp     [rdi+34h], ebx
0x1005bfcb9  jz      short loc_1005BFC75
0x1005bfcbb  mov     rax, [r15+18h]
0x1005bfcbf  test    rax, rax
0x1005bfcc2  jz      short loc_1005BFCD8
0x1005bfcc4  mov     ecx, [rdi+8]
0x1005bfcc7  dec     rax
0x1005bfcca  add     rax, rcx
0x1005bfccd  xor     edx, edx
0x1005bfccf  div     rcx
0x1005bfcd2  imul    rax, rcx
0x1005bfcd6  jmp     short loc_1005BFCDB
0x1005bfcd8  mov     rax, rbx
0x1005bfcdb  mov     rdx, rax
0x1005bfcde  mov     rcx, rsi
0x1005bfce1  call    cs:qword_100715080
0x1005bfce7  mov     r14d, eax
0x1005bfcea  test    eax, eax
0x1005bfcec  jnz     short loc_1005BFC75
0x1005bfcee  lea     r13d, [rax+25h]
0x1005bfcf2  jmp     short loc_1005BFCFA
0x1005bfcf4  mov     r13d, 27h ; '''
0x1005bfcfa  mov     rcx, [rdi+278h]; hFile
0x1005bfd01  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1005bfd05  jz      short loc_1005BFD61
0x1005bfd07  cmp     [rdi+34h], ebx
0x1005bfd0a  jz      short loc_1005BFD16
0x1005bfd0c  xor     edx, edx
0x1005bfd0e  call    cs:qword_100715080
0x1005bfd14  jmp     short loc_1005BFD36
0x1005bfd16  xor     r9d, r9d; dwMoveMethod
0x1005bfd19  xor     r8d, r8d; lpNewFilePointer
0x1005bfd1c  mov     rdx, rbx; liDistanceToMove
0x1005bfd1f  call    cs:__imp_SetFilePointerEx
0x1005bfd25  test    eax, eax
0x1005bfd27  jz      short loc_1005BFD36
0x1005bfd29  mov     rcx, [rdi+278h]; hFile
0x1005bfd30  call    cs:__imp_SetEndOfFile
0x1005bfd36  mov     rcx, [rdi+278h]; hObject
0x1005bfd3d  cmp     [rdi+34h], ebx
0x1005bfd40  jz      short loc_1005BFD4A
0x1005bfd42  call    cs:qword_100715090
0x1005bfd48  jmp     short loc_1005BFD56
0x1005bfd4a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1005bfd4e  jz      short loc_1005BFD56
0x1005bfd50  call    cs:__imp_CloseHandle
0x1005bfd56  mov     qword ptr [rdi+278h], 0FFFFFFFFFFFFFFFFh
0x1005bfd61  mov     [rdi+288h], rbx
0x1005bfd68  jmp     short loc_1005BFDC7
0x1005bfd6a  call    cs:__imp_GetLastError
0x1005bfd70  cmp     eax, 50h ; 'P'
0x1005bfd73  jz      short loc_1005BFD92
0x1005bfd75  mov     rcx, [r15+678h]
0x1005bfd7c  lea     r8, [rsp+2D8h+var_258]
0x1005bfd84  xor     r9d, r9d
0x1005bfd87  mov     edx, eax
0x1005bfd89  mov     r10, [rcx]
0x1005bfd8c  call    qword ptr [r10+30h]
0x1005bfd90  jmp     short loc_1005BFDC7
0x1005bfd92  lea     rcx, [rsp+2D8h+var_268]; lpSystemTime
0x1005bfd97  call    cs:__imp_GetSystemTime
0x1005bfd9d  movups  xmm0, xmmword ptr [rsp+2D8h+var_268.wYear]
0x1005bfda2  movups  xmmword ptr [rdi+48h], xmm0
0x1005bfda6  jmp     short loc_1005BFDC7
0x1005bfda8  mov     rsi, [r15+678h]
0x1005bfdaf  mov     rbp, [rsi]
0x1005bfdb2  call    cs:__imp_GetLastError
0x1005bfdb8  movzx   r9d, bx
0x1005bfdbc  xor     r8d, r8d
0x1005bfdbf  mov     edx, eax
0x1005bfdc1  mov     rcx, rsi
0x1005bfdc4  call    qword ptr [rbp+30h]
0x1005bfdc7  cmp     qword ptr [rdi+278h], 0FFFFFFFFFFFFFFFFh
0x1005bfdcf  jnz     short loc_1005BFE10
0x1005bfdd1  call    cs:__imp_GetLastError
0x1005bfdd7  cmp     eax, 50h ; 'P'
0x1005bfdda  jnz     short loc_1005BFE10
0x1005bfddc  call    cs:qword_1007152F8
0x1005bfde2  mov     dl, 0Eh
0x1005bfde4  mov     rcx, rax
0x1005bfde7  mov     r8, [rax]
0x1005bfdea  call    qword ptr [r8]
0x1005bfded  test    al, al
0x1005bfdef  lea     rax, [r15+10h]
0x1005bfdf3  jz      loc_1005BFA10
0x1005bfdf9  mov     eax, [rsp+2D8h+var_298]
0x1005bfdfd  inc     eax
0x1005bfdff  mov     [rsp+2D8h+var_298], eax
0x1005bfe03  cmp     eax, 0Ah
0x1005bfe06  lea     rax, [r15+10h]
0x1005bfe0a  jl      loc_1005BFA10
0x1005bfe10  test    r14d, r14d
0x1005bfe13  jz      short loc_1005BFE1A
0x1005bfe15  mov     [rdi+30h], ebx
0x1005bfe18  jmp     short loc_1005BFE4A
0x1005bfe1a  call    cs:qword_100715040
0x1005bfe20  cmp     [rax+4], bx
0x1005bfe24  jnz     short loc_1005BFE4A
0x1005bfe26  mov     rbx, [r15+678h]
0x1005bfe2d  mov     rdi, [rbx]
0x1005bfe30  call    cs:__imp_GetLastError
0x1005bfe36  movzx   r9d, r13w
0x1005bfe3a  lea     r8, [rsp+2D8h+var_258]
0x1005bfe42  mov     edx, eax
0x1005bfe44  mov     rcx, rbx
0x1005bfe47  call    qword ptr [rdi+30h]
0x1005bfe4a  mov     eax, r14d
0x1005bfe4d  mov     rcx, [rsp+2D8h+var_48]
0x1005bfe55  xor     rcx, rsp; StackCookie
0x1005bfe58  call    __security_check_cookie
0x1005bfe5d  mov     rbx, [rsp+2D8h+arg_10]
0x1005bfe65  add     rsp, 2A0h
0x1005bfe6c  pop     r15
  ... truncated ...
```
