# EtlFile::GetLogFileInfo(ulong,BinXmlVariant &)

- ea: `0x1800b51a0`
- end: `0x1800b5404`
- name: `?GetLogFileInfo@EtlFile@@UEAAXKAEAUBinXmlVariant@@@Z`
- size: `612`
- prototype: `void __fastcall(EtlFile *this, unsigned int, struct BinXmlVariant *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800b5410`

## callees

- `0x180017e94`
- `0x1800613d8`
- `0x180092008`
- `0x18009aee0`
- `0x1800b51a0`
- `0x1800b582c`
- `0x1800d334c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b527b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b527b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b53db`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b53db`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800b5381`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800b5381`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x1800b52b3`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x1800b52d5`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x1800b5320`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x1800b53bf`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x1800b52b3`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x1800b52d5`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x1800b5320`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x1800b53bf`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall EtlFile::GetLogFileInfo(EtlFile *this, unsigned int a2, struct BinXmlVariant *a3)
{
  __int64 v6; // rsi
  __int64 v7; // r15
  unsigned int i; // esi
  __int64 v9; // rcx
  unsigned int v10; // esi
  DWORD GrantedAccess; // [rsp+30h] [rbp-59h] BYREF
  __int128 pExceptionObject; // [rsp+38h] [rbp-51h] BYREF
  __int64 v13; // [rsp+48h] [rbp-41h]
  int v14; // [rsp+50h] [rbp-39h]
  int v15; // [rsp+54h] [rbp-35h]
  int v16; // [rsp+58h] [rbp-31h]
  char *v17; // [rsp+60h] [rbp-29h]
  struct _WIN32_FILE_ATTRIBUTE_DATA FileInformation; // [rsp+68h] [rbp-21h] BYREF
  FILETIME FileTime1[2]; // [rsp+90h] [rbp+7h] BYREF
  __int128 v20; // [rsp+A0h] [rbp+17h]
  DWORD v21; // [rsp+B0h] [rbp+27h]

  *((_DWORD *)a3 + 3) = 0;
  GrantedAccess = 0;
  if ( !EvtCheckAccess(*((PSECURITY_DESCRIPTOR *)this + 76), 1u, &GrantedAccess, 0, 0) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_df2db0e57fcf329b720e46088dc10b5a_Traceguids, 5);
    }
    pExceptionObject = 0;
    v13 = 0;
    v14 = 5;
    v15 = -1;
    v16 = 183;
    throw (EvtException *)&pExceptionObject;
  }
  v17 = (char *)this + 672;
  AcquireSRWLockExclusive((PSRWLOCK)this + 84);
  memset(&FileInformation, 0, sizeof(FileInformation));
  *(_OWORD *)&FileTime1[0].dwLowDateTime = 0;
  v20 = 0;
  v21 = 0;
  if ( *((_DWORD *)this + 141) >= 2u )
  {
    v6 = *((unsigned int *)this + 142);
    if ( GetFileAttributesExW(
           *((LPCWSTR *)this + 4 * (unsigned int)(v6 - 1) + 6),
           GetFileExInfoStandard,
           &FileInformation) )
    {
      if ( a2 )
      {
        if ( a2 != 3 )
        {
LABEL_13:
          GetGenericLogFileInfo(&FileInformation, a2, a3);
          goto LABEL_27;
        }
        v7 = 0;
        for ( i = 0; i < *((_DWORD *)this + 141); ++i )
        {
          if ( GetFileAttributesExW(*((LPCWSTR *)this + 4 * i + 6), GetFileExInfoStandard, &FileInformation) )
            v7 += FileInformation.nFileSizeLow | ((unsigned __int64)FileInformation.nFileSizeHigh << 32);
        }
        *((_DWORD *)a3 + 3) = 10;
        *(_QWORD *)a3 = v7;
      }
      else
      {
        if ( (unsigned int)v6 >= *((_DWORD *)this + 141) || !FileExists(*((const wchar_t **)this + 4 * v6 + 6)) )
          LODWORD(v6) = 0;
        v9 = (unsigned int)v6;
        v10 = v6 + 1;
        while ( GetFileAttributesExW(*((LPCWSTR *)this + 4 * v9 + 6), GetFileExInfoStandard, FileTime1)
             && CompareFileTime((const FILETIME *)&FileTime1[0].dwHighDateTime, &FileInformation.ftCreationTime) < 0 )
        {
          v9 = v10 < *((_DWORD *)this + 141) ? v10 : 0;
          *(_OWORD *)&FileInformation.dwFileAttributes = *(_OWORD *)&FileTime1[0].dwLowDateTime;
          *(_OWORD *)&FileInformation.ftLastAccessTime.dwHighDateTime = v20;
          FileInformation.nFileSizeLow = v21;
          v10 = v9 + 1;
        }
        *((_DWORD *)a3 + 3) = 17;
        *(FILETIME *)a3 = FileInformation.ftCreationTime;
      }
    }
  }
  else if ( GetFileAttributesExW(*((LPCWSTR *)this + 2), GetFileExInfoStandard, &FileInformation) )
  {
    goto LABEL_13;
  }
LABEL_27:
  ReleaseSRWLockExclusive((PSRWLOCK)this + 84);
}

```

## disassembly

```asm
0x1800b51a0  mov     [rsp-8+arg_8], rbx
0x1800b51a5  push    rbp
0x1800b51a6  push    rsi
0x1800b51a7  push    rdi
0x1800b51a8  push    r14
0x1800b51aa  push    r15
0x1800b51ac  lea     rbp, [rsp-37h]
0x1800b51b1  sub     rsp, 0C0h
0x1800b51b8  mov     rax, cs:__security_cookie
0x1800b51bf  xor     rax, rsp
0x1800b51c2  mov     [rbp+57h+var_28], rax
0x1800b51c6  mov     r14, r8
0x1800b51c9  mov     r15d, edx
0x1800b51cc  mov     rdi, rcx
0x1800b51cf  mov     dword ptr [r8+0Ch], 0
0x1800b51d7  mov     [rbp+57h+GrantedAccess], 0
0x1800b51de  mov     [rsp+0E0h+var_C0], 0; bool
0x1800b51e3  xor     r9d, r9d; bool
0x1800b51e6  lea     r8, [rbp+57h+GrantedAccess]; GrantedAccess
0x1800b51ea  lea     edx, [r9+1]; DesiredAccess
0x1800b51ee  mov     rcx, [rcx+260h]; SecurityDescriptor
0x1800b51f5  call    ?EvtCheckAccess@@YA_NPEAXKAEAK_N2@Z; EvtCheckAccess(void *,ulong,ulong &,bool,bool)
0x1800b51fa  test    al, al
0x1800b51fc  jnz     short loc_1800B526D
0x1800b51fe  lea     rax, WPP_GLOBAL_Control
0x1800b5205  mov     ebx, 5
0x1800b520a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5211  cmp     rcx, rax
0x1800b5214  jz      short loc_1800B523B
0x1800b5216  test    dword ptr [rcx+1Ch], 200h
0x1800b521d  jz      short loc_1800B523B
0x1800b521f  cmp     byte ptr [rcx+19h], 2
0x1800b5223  jb      short loc_1800B523B
0x1800b5225  lea     edx, [rbx+11h]
0x1800b5228  mov     r9d, ebx
0x1800b522b  lea     r8, WPP_df2db0e57fcf329b720e46088dc10b5a_Traceguids
0x1800b5232  mov     rcx, [rcx+10h]
0x1800b5236  call    WPP_SF_d
0x1800b523b  xorps   xmm0, xmm0
0x1800b523e  movdqu  [rbp+57h+pExceptionObject], xmm0
0x1800b5243  mov     [rbp+57h+var_98], 0
0x1800b524b  mov     [rbp+57h+var_90], ebx
0x1800b524e  mov     [rbp+57h+var_8C], 0FFFFFFFFh
0x1800b5255  mov     [rbp+57h+var_88], 0B7h
0x1800b525c  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800b5263  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800b5267  call    _CxxThrowException_0
0x1800b526d  lea     rbx, [rdi+2A0h]
0x1800b5274  mov     [rbp+57h+var_80], rbx
0x1800b5278  mov     rcx, rbx; SRWLock
0x1800b527b  call    cs:__imp_AcquireSRWLockExclusive
0x1800b5281  nop
0x1800b5282  xorps   xmm0, xmm0
0x1800b5285  xor     eax, eax
0x1800b5287  movups  [rbp+57h+FileInformation], xmm0
0x1800b528b  movups  [rbp+57h+var_68], xmm0
0x1800b528f  mov     [rbp+57h+var_58], eax
0x1800b5292  xorps   xmm1, xmm1
0x1800b5295  movups  xmmword ptr [rbp+57h+FileTime1.dwLowDateTime], xmm1
0x1800b5299  movups  [rbp+57h+var_40], xmm1
0x1800b529d  mov     [rbp+57h+var_30], eax
0x1800b52a0  lea     r8, [rbp+57h+FileInformation]; lpFileInformation
0x1800b52a4  xor     edx, edx; fInfoLevelId
0x1800b52a6  cmp     dword ptr [rdi+234h], 2
0x1800b52ad  jnb     short loc_1800B52C3
0x1800b52af  mov     rcx, [rdi+10h]; lpFileName
0x1800b52b3  call    cs:__imp_GetFileAttributesExW
0x1800b52b9  test    eax, eax
0x1800b52bb  jz      loc_1800B53D8
0x1800b52c1  jmp     short loc_1800B52EE
0x1800b52c3  mov     esi, [rdi+238h]
0x1800b52c9  lea     ecx, [rsi-1]
0x1800b52cc  shl     rcx, 5
0x1800b52d0  mov     rcx, [rcx+rdi+30h]; lpFileName
0x1800b52d5  call    cs:__imp_GetFileAttributesExW
0x1800b52db  test    eax, eax
0x1800b52dd  jz      loc_1800B53D8
0x1800b52e3  test    r15d, r15d
0x1800b52e6  jz      short loc_1800B5354
0x1800b52e8  cmp     r15d, 3
0x1800b52ec  jz      short loc_1800B5302
0x1800b52ee  mov     r8, r14; struct BinXmlVariant *
0x1800b52f1  mov     edx, r15d; unsigned int
0x1800b52f4  lea     rcx, [rbp+57h+FileInformation]; struct _WIN32_FILE_ATTRIBUTE_DATA *
0x1800b52f8  call    ?GetGenericLogFileInfo@@YAXAEAU_WIN32_FILE_ATTRIBUTE_DATA@@KAEAUBinXmlVariant@@@Z; GetGenericLogFileInfo(_WIN32_FILE_ATTRIBUTE_DATA &,ulong,BinXmlVariant &)
0x1800b52fd  jmp     loc_1800B53D8
0x1800b5302  xor     r15d, r15d
0x1800b5305  xor     esi, esi
0x1800b5307  cmp     [rdi+234h], esi
0x1800b530d  jbe     short loc_1800B5344
0x1800b530f  mov     ecx, esi
0x1800b5311  shl     rcx, 5
0x1800b5315  lea     r8, [rbp+57h+FileInformation]; lpFileInformation
0x1800b5319  xor     edx, edx; fInfoLevelId
0x1800b531b  mov     rcx, [rcx+rdi+30h]; lpFileName
0x1800b5320  call    cs:__imp_GetFileAttributesExW
0x1800b5326  test    eax, eax
0x1800b5328  jz      short loc_1800B533A
0x1800b532a  mov     ecx, dword ptr [rbp+57h+var_68+0Ch]
0x1800b532d  shl     rcx, 20h
0x1800b5331  mov     eax, [rbp+57h+var_58]
0x1800b5334  or      rcx, rax
0x1800b5337  add     r15, rcx
0x1800b533a  inc     esi
0x1800b533c  cmp     esi, [rdi+234h]
0x1800b5342  jb      short loc_1800B530F
0x1800b5344  mov     dword ptr [r14+0Ch], 0Ah
0x1800b534c  mov     [r14], r15
0x1800b534f  jmp     loc_1800B53D8
0x1800b5354  cmp     esi, [rdi+234h]
0x1800b535a  jnb     short loc_1800B5371
0x1800b535c  mov     rcx, rsi
0x1800b535f  shl     rcx, 5
0x1800b5363  mov     rcx, [rcx+rdi+30h]; wchar_t *
0x1800b5368  call    ?FileExists@@YA_NPEB_W@Z; FileExists(wchar_t const *)
0x1800b536d  test    al, al
0x1800b536f  jnz     short loc_1800B5373
0x1800b5371  xor     esi, esi
0x1800b5373  mov     ecx, esi
0x1800b5375  inc     esi
0x1800b5377  jmp     short loc_1800B53B0
0x1800b5379  lea     rdx, [rbp+57h+FileInformation+4]; lpFileTime2
0x1800b537d  lea     rcx, [rbp+57h+FileTime1.dwHighDateTime]; lpFileTime1
0x1800b5381  call    cs:__imp_CompareFileTime
0x1800b5387  test    eax, eax
0x1800b5389  jns     short loc_1800B53C9
0x1800b538b  cmp     esi, [rdi+234h]
0x1800b5391  sbb     eax, eax
0x1800b5393  and     eax, esi
0x1800b5395  mov     ecx, eax
0x1800b5397  movups  xmm0, xmmword ptr [rbp+57h+FileTime1.dwLowDateTime]
0x1800b539b  movups  [rbp+57h+FileInformation], xmm0
0x1800b539f  movups  xmm1, [rbp+57h+var_40]
0x1800b53a3  movups  [rbp+57h+var_68], xmm1
0x1800b53a7  mov     eax, [rbp+57h+var_30]
0x1800b53aa  mov     [rbp+57h+var_58], eax
0x1800b53ad  lea     esi, [rcx+1]
0x1800b53b0  shl     rcx, 5
0x1800b53b4  lea     r8, [rbp+57h+FileTime1]; lpFileInformation
0x1800b53b8  xor     edx, edx; fInfoLevelId
0x1800b53ba  mov     rcx, [rcx+rdi+30h]; lpFileName
0x1800b53bf  call    cs:__imp_GetFileAttributesExW
0x1800b53c5  test    eax, eax
0x1800b53c7  jnz     short loc_1800B5379
0x1800b53c9  mov     dword ptr [r14+0Ch], 11h
0x1800b53d1  mov     rax, qword ptr [rbp+57h+FileInformation+4]
0x1800b53d5  mov     [r14], rax
0x1800b53d8  mov     rcx, rbx; SRWLock
0x1800b53db  call    cs:__imp_ReleaseSRWLockExclusive
0x1800b53e1  mov     rcx, [rbp+57h+var_28]
0x1800b53e5  xor     rcx, rsp; StackCookie
0x1800b53e8  call    __security_check_cookie
0x1800b53ed  mov     rbx, [rsp+0E0h+arg_8]
0x1800b53f5  add     rsp, 0C0h
0x1800b53fc  pop     r15
0x1800b53fe  pop     r14
0x1800b5400  pop     rdi
0x1800b5401  pop     rsi
0x1800b5402  pop     rbp
0x1800b5403  retn
```
