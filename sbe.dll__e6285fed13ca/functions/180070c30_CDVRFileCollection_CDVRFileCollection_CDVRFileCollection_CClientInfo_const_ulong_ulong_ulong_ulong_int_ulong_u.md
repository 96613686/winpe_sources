# CDVRFileCollection::CDVRFileCollection(CDVRFileCollection::CClientInfo const *,ulong,ulong,ulong,ulong,int,ulong,ushort const *,ushort const *,int,int,long *)

- ea: `0x180070c30`
- end: `0x18007141d`
- name: `??0CDVRFileCollection@@QEAA@PEBUCClientInfo@0@KKKKHKPEBG1HHPEAJ@Z`
- size: `2029`
- prototype: `CDVRFileCollection *__usercall@<rax>(CDVRFileCollection *__hidden this@<rcx>, const struct CDVRFileCollection::CClientInfo *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int, unsigned int, int, unsigned int, const unsigned __int16 *, LPCWSTR lpFileName, int, int, int *)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180063528`
- `0x180068fd0`
- `0x18006b020`

## callees

- `0x1800017ec`
- `0x180001c00`
- `0x18000256c`
- `0x18000262c`
- `0x180070c30`
- `0x180073368`
- `0x180073504`
- `0x180073ebc`
- `0x180085ef0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800711a0`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800711c2`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800711a0`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800711c2`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180070f17`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180070f17`
- `KERNEL32!CloseHandle` at `0x180071331`
- `KERNEL32!CloseHandle` at `0x180071331`
- `KERNEL32!InitializeCriticalSection` at `0x180070d3e`
- `KERNEL32!InitializeCriticalSection` at `0x180070d3e`
- `KERNEL32!GetLastError` at `0x180070df4`
- `KERNEL32!GetLastError` at `0x1800712de`
- `KERNEL32!GetLastError` at `0x180070df4`
- `KERNEL32!GetLastError` at `0x1800712de`
- `KERNEL32!GetCurrentProcessId` at `0x180071040`
- `KERNEL32!GetCurrentProcessId` at `0x180071040`
- `KERNEL32!GetFileAttributesW` at `0x180070de9`
- `KERNEL32!GetFileAttributesW` at `0x180070de9`
- `KERNEL32!RemoveDirectoryW` at `0x1800713b1`
- `KERNEL32!RemoveDirectoryW` at `0x1800b4be4`
- `KERNEL32!RemoveDirectoryW` at `0x1800713b1`
- `KERNEL32!RemoveDirectoryW` at `0x1800b4be4`
- `KERNEL32!ReleaseMutex` at `0x18007139c`
- `KERNEL32!ReleaseMutex` at `0x1800b4bc5`
- `KERNEL32!ReleaseMutex` at `0x18007139c`
- `KERNEL32!ReleaseMutex` at `0x1800b4bc5`
- `KERNEL32!CreateMutexW` at `0x1800712d5`
- `KERNEL32!CreateMutexW` at `0x1800712d5`
- `KERNEL32!SetFileAttributesW` at `0x180070e2e`
- `KERNEL32!SetFileAttributesW` at `0x180070e2e`
- `KERNEL32!CreateDirectoryW` at `0x180070dd8`
- `KERNEL32!CreateDirectoryW` at `0x180070dd8`
- `KERNEL32!GetFullPathNameW` at `0x180070e66`
- `KERNEL32!GetFullPathNameW` at `0x180070eb0`
- `KERNEL32!GetFullPathNameW` at `0x180070e66`
- `KERNEL32!GetFullPathNameW` at `0x180070eb0`

## string_xrefs

- `0x180070db1`: `TempSBE`

## pseudocode

```c
CDVRFileCollection *__fastcall CDVRFileCollection::CDVRFileCollection(
        CDVRFileCollection *this,
        const struct CDVRFileCollection::CClientInfo *a2,
        int a3,
        int a4,
        unsigned int a5,
        unsigned int a6,
        int a7,
        unsigned int a8,
        const unsigned __int16 *a9,
        LPCWSTR lpFileName,
        int a11,
        int a12,
        int *a13)
{
  struct CDVRFileCollection::CSharedData **v14; // rsi
  int v15; // r15d
  __int64 v16; // rax
  unsigned __int64 v17; // r14
  wchar_t *v18; // rax
  signed int v19; // ebx
  DWORD FileAttributesW; // eax
  signed int v21; // eax
  DWORD FullPathNameW; // eax
  DWORD v23; // ebx
  DWORD v24; // r14d
  WCHAR *v25; // rax
  DWORD v26; // eax
  __int64 v27; // rbx
  void *v28; // rax
  unsigned int v29; // r14d
  unsigned int v30; // r15d
  size_t v31; // rbx
  struct CDVRFileCollection::CSharedData *v32; // rax
  struct CDVRFileCollection::CSharedData *v33; // rcx
  unsigned int v34; // edx
  unsigned int v35; // r8d
  unsigned int v36; // r10d
  struct CDVRFileCollection::CSharedData *v37; // r9
  __int64 v38; // r11
  __int64 v39; // rdx
  __int64 v40; // r10
  __int16 v41; // ax
  __int64 v42; // r9
  enum _ACCESS_MODE v43; // r8d
  size_t v44; // r12
  WCHAR *v45; // r14
  ULONG v46; // ecx
  int v47; // eax
  unsigned int v48; // ebx
  int v49; // eax
  int v50; // r13d
  struct _SECURITY_ATTRIBUTES *v51; // rcx
  HANDLE MutexW; // r14
  DWORD LastError; // eax
  const unsigned __int16 *v55; // [rsp+20h] [rbp-138h]
  int v56; // [rsp+64h] [rbp-F4h]
  int v58; // [rsp+6Ch] [rbp-ECh]
  unsigned int v59; // [rsp+70h] [rbp-E8h] BYREF
  void *v60; // [rsp+78h] [rbp-E0h] BYREF
  struct CDVRFileCollection::CClientInfo *v61; // [rsp+80h] [rbp-D8h]
  CDVRFileCollection *v62; // [rsp+88h] [rbp-D0h]
  int *v63; // [rsp+90h] [rbp-C8h]
  int *v64; // [rsp+98h] [rbp-C0h]
  LPWSTR FilePart; // [rsp+A0h] [rbp-B8h] BYREF
  struct _ACL *v66; // [rsp+A8h] [rbp-B0h] BYREF
  __int128 v67; // [rsp+B0h] [rbp-A8h] BYREF
  __int64 v68; // [rsp+C0h] [rbp-98h]
  WCHAR Buffer; // [rsp+C8h] [rbp-90h] BYREF
  WCHAR Name[22]; // [rsp+D0h] [rbp-88h] BYREF
  wchar_t v71; // [rsp+FCh] [rbp-5Ch] BYREF
  char v72; // [rsp+FEh] [rbp-5Ah] BYREF

  LODWORD(v60) = a4;
  v61 = a2;
  v62 = this;
  v64 = a13;
  v63 = a13;
  *(_QWORD *)this = &CDVRFileCollection::`vftable';
  *((_DWORD *)this + 2) = a5;
  *((_DWORD *)this + 3) = a6;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  v14 = (struct CDVRFileCollection::CSharedData **)((char *)this + 32);
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = -1;
  *((_QWORD *)this + 17) = 1;
  *((_QWORD *)this + 18) = 0;
  *((_DWORD *)this + 38) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_DWORD *)this + 42) = a12;
  *((_DWORD *)this + 43) = 0;
  v58 = 0;
  v15 = 0;
  v56 = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  memset_0((char *)this + 176, 0, 0x100u);
  _InterlockedIncrement((volatile signed __int32 *)this + 36);
  if ( a9 )
  {
    v16 = -1;
    do
      ++v16;
    while ( a9[v16] );
    v17 = (unsigned int)(v16 + 9);
    v18 = (wchar_t *)operator new[](saturated_mul(v17, 2u));
    *((_QWORD *)this + 13) = v18;
    if ( !v18 )
      goto LABEL_5;
    v55 = L"TempSBE";
    swprintf_s(v18, v17, L"%s\\%s", a9);
    if ( CreateDirectoryW(*((LPCWSTR *)this + 13), 0) )
    {
      v58 = 1;
    }
    else
    {
      FileAttributesW = GetFileAttributesW(*((LPCWSTR *)this + 13));
      if ( FileAttributesW == -1 )
        goto LABEL_8;
      if ( (FileAttributesW & 0x10) == 0 )
      {
        v19 = -2147024629;
        goto LABEL_63;
      }
    }
    SetFileAttributesW(*((LPCWSTR *)this + 13), 6u);
  }
  if ( !lpFileName )
  {
LABEL_23:
    v29 = 568 * *((_DWORD *)this + 2) + 1912;
    v30 = *((_DWORD *)this + 35);
    v59 = v30;
    if ( lpFileName )
    {
      v19 = CDVRFileCollection::CreateMemoryMap(
              this,
              v61,
              0,
              0,
              v29,
              &v59,
              1u,
              a11 != 0 ? 128 : 0x4000000,
              v14,
              (void **)this + 6,
              (void **)this + 16);
      if ( v19 >= 0 )
      {
        *((_DWORD *)this + 43) |= 1u;
        v31 = v29;
        v30 = v59;
        goto LABEL_29;
      }
    }
    else
    {
      v31 = v29;
      v32 = (struct CDVRFileCollection::CSharedData *)operator new[](v29);
      if ( v32 )
      {
        *v14 = v32;
        *((_DWORD *)this + 43) |= 2u;
LABEL_29:
        memset_0(*v14, 0, v31);
        v33 = *v14;
        *((_QWORD *)this + 5) = (char *)*v14 + 1912;
        *(GUID *)v33 = CDVRFileCollection::m_guidV11;
        *((_DWORD *)*v14 + 4) = a3;
        *((_DWORD *)*v14 + 5) = (_DWORD)v60;
        *((_DWORD *)*v14 + 14) = 1;
        *((_DWORD *)*v14 + 17) = GetCurrentProcessId();
        *((_DWORD *)*v14 + 19) = a8;
        *((_DWORD *)*v14 + 21) = 0;
        *((_WORD *)*v14 + 44) = 0;
        if ( a7 )
          *((_DWORD *)*v14 + 152) |= 1u;
        *((_WORD *)*v14 + 950) = -1;
        *((_WORD *)*v14 + 949) = -1;
        *((_WORD *)*v14 + 948) = -1;
        *((_WORD *)*v14 + 953) = -1;
        *((_WORD *)*v14 + 952) = -1;
        *((_WORD *)*v14 + 951) = -1;
        LOWORD(v34) = 0;
        v35 = 0;
        v36 = 0;
        while ( v35 < *((_DWORD *)this + 2) )
        {
          *(_WORD *)(568LL * v35 + *((_QWORD *)this + 5) + 566) = v34;
          v37 = *v14;
          v38 = *((unsigned __int16 *)*v14 + 952);
          v39 = 568LL * v36;
          *(_WORD *)(*((_QWORD *)this + 5) + v39 + 562) = *((_WORD *)*v14 + 953);
          *(_WORD *)(*((_QWORD *)this + 5) + v39 + 564) = v38;
          v40 = *((_QWORD *)this + 5);
          v41 = *(_WORD *)(v40 + v39 + 566);
          if ( (_WORD)v38 == 0xFFFF )
            *((_WORD *)v37 + 951) = v41;
          else
            *(_WORD *)(568 * v38 + v40 + 562) = v41;
          *((_WORD *)v37 + 952) = *(_WORD *)(*((_QWORD *)this + 5) + v39 + 566);
          v34 = v35 + 1;
          v35 = v34;
          v36 = v34;
        }
        if ( lpFileName )
        {
          if ( GetProcessIntegrityLevel() == 4096 )
          {
            _o_wcscpy_s(Name, 39, L"Local\\_MS_TSDVR_MUTEX_", v42);
            v44 = 18;
            v45 = &v71;
          }
          else
          {
            _o_wcscpy_s(Name, 40, L"Global\\_MS_TSDVR_MUTEX_", v42);
            v44 = 17;
            v45 = (WCHAR *)&v72;
          }
          FilePart = v45;
          v66 = 0;
          v60 = 0;
          v67 = 0;
          v68 = 0;
          v46 = *((_DWORD *)v61 + 4);
          if ( v46 )
          {
            v47 = CreateACL(v46, *((void ***)v61 + 3), v43, 0x1F0001u, (enum _ACCESS_MODE)v55, 0x100000u, &v66, &v60);
            v19 = v47;
            if ( v47 )
            {
              if ( v47 > 0 )
                v19 = (unsigned __int16)v47 | 0x80070000;
              goto LABEL_62;
            }
            LODWORD(v67) = 24;
            *((_QWORD *)&v67 + 1) = v60;
            LODWORD(v68) = 0;
          }
          v48 = 1;
          v49 = 1;
          v50 = 1;
          while ( v49 != -1 )
          {
            swprintf_s(v45, v44, L"%u", v48);
            v51 = (struct _SECURITY_ATTRIBUTES *)&v67;
            if ( !*((_DWORD *)v61 + 4) )
              v51 = 0;
            MutexW = CreateMutexW(v51, 1, Name);
            LastError = GetLastError();
            if ( MutexW )
            {
              if ( LastError != 183 )
              {
                *((_DWORD *)*v14 + 15) = v48;
                *((_QWORD *)this + 12) = MutexW;
                break;
              }
              CloseHandle(MutexW);
            }
            v48 = v50 + 1;
            v49 = ++v50;
            v45 = FilePart;
          }
          if ( *((_DWORD *)v61 + 4) )
            FreeSecurityDescriptors(&v66, &v60);
          if ( !v50 )
          {
            v19 = -2147467259;
            goto LABEL_62;
          }
          v56 = 1;
          *((_DWORD *)this + 35) = v30;
          *((_DWORD *)this + 43) |= 0x80u;
          _InterlockedExchange((volatile __int32 *)*v14 + 20, v30);
        }
        else
        {
          *((_DWORD *)*v14 + 15) = 1;
          *((_DWORD *)this + 43) |= 0x10u;
        }
        *((_DWORD *)this + 43) |= 0x100u;
        v19 = 0;
        goto LABEL_62;
      }
      v19 = -2147024882;
    }
LABEL_62:
    v15 = v56;
    goto LABEL_63;
  }
  Buffer = 0;
  FilePart = 0;
  FullPathNameW = GetFullPathNameW(lpFileName, 0, &Buffer, 0);
  v23 = FullPathNameW;
  if ( FullPathNameW )
  {
    v24 = FullPathNameW + 1;
    v25 = (WCHAR *)operator new[](saturated_mul(FullPathNameW + 1, 2u));
    *((_QWORD *)this + 14) = v25;
    if ( !v25 )
      goto LABEL_5;
    v26 = GetFullPathNameW(lpFileName, v24, v25, &FilePart);
    if ( v26 )
    {
      if ( v26 > v23 )
      {
        v19 = -2147467259;
        goto LABEL_63;
      }
      v27 = ((__int64)FilePart - *((_QWORD *)this + 14)) >> 1;
      v28 = operator new[](saturated_mul((unsigned int)(v27 + 1), 2u));
      *((_QWORD *)this + 15) = v28;
      if ( v28 )
      {
        _o_wcsncpy_s(v28, (unsigned int)(v27 + 1), *((_QWORD *)this + 14), (unsigned int)v27);
        *(_WORD *)(*((_QWORD *)this + 15) + 2LL * (unsigned int)v27) = 0;
        goto LABEL_23;
      }
LABEL_5:
      v19 = -2147024882;
      goto LABEL_63;
    }
  }
LABEL_8:
  v21 = GetLastError();
  v19 = v21;
  if ( v21 > 0 )
    v19 = (unsigned __int16)v21 | 0x80070000;
LABEL_63:
  if ( v15 )
    ReleaseMutex(*((HANDLE *)this + 12));
  if ( v19 < 0 )
  {
    if ( v58 )
      RemoveDirectoryW(*((LPCWSTR *)this + 13));
    if ( *v14 )
      *((_DWORD *)*v14 + 18) = 1;
  }
  if ( v64 )
    *v64 = v19;
  return this;
}

```

## disassembly

```asm
0x180070c30  mov     [rsp+arg_10], rbx
0x180070c35  mov     [rsp+arg_18], rsi
0x180070c3a  push    rdi
0x180070c3b  push    r12
0x180070c3d  push    r13
0x180070c3f  push    r14
0x180070c41  push    r15
0x180070c43  sub     rsp, 130h
0x180070c4a  mov     rax, cs:__security_cookie
0x180070c51  xor     rax, rsp
0x180070c54  mov     [rsp+158h+var_38], rax
0x180070c5c  mov     dword ptr [rsp+158h+var_E0], r9d
0x180070c61  mov     [rsp+158h+var_F0], r8d
0x180070c66  mov     [rsp+158h+var_D8], rdx
0x180070c6e  mov     rdi, rcx
0x180070c71  mov     [rsp+158h+var_D0], rcx
0x180070c79  mov     rbx, [rsp+158h+arg_40]
0x180070c81  mov     r13, [rsp+158h+lpFileName]
0x180070c89  mov     rax, [rsp+158h+arg_60]
0x180070c91  mov     [rsp+158h+var_C0], rax
0x180070c99  mov     [rsp+158h+var_C8], rax
0x180070ca1  lea     rax, ??_7CDVRFileCollection@@6B@; const CDVRFileCollection::`vftable'
0x180070ca8  mov     [rcx], rax
0x180070cab  mov     eax, [rsp+158h+arg_20]
0x180070cb2  mov     [rcx+8], eax
0x180070cb5  mov     eax, [rsp+158h+arg_28]
0x180070cbc  mov     [rcx+0Ch], eax
0x180070cbf  xor     r14d, r14d
0x180070cc2  mov     [rcx+10h], r14
0x180070cc6  mov     [rcx+18h], r14
0x180070cca  lea     rsi, [rcx+20h]
0x180070cce  mov     [rsi], r14
0x180070cd1  mov     [rcx+28h], r14
0x180070cd5  mov     [rcx+30h], r14
0x180070cd9  mov     [rcx+60h], r14
0x180070cdd  mov     [rcx+68h], r14
0x180070ce1  mov     [rcx+70h], r14
0x180070ce5  mov     [rcx+78h], r14
0x180070ce9  or      r12, 0FFFFFFFFFFFFFFFFh
0x180070ced  mov     [rcx+80h], r12
0x180070cf4  mov     qword ptr [rcx+88h], 1
0x180070cff  mov     [rcx+90h], r14
0x180070d06  mov     [rcx+98h], r14d
0x180070d0d  mov     [rcx+0A0h], r14
0x180070d14  mov     eax, [rsp+158h+arg_58]
0x180070d1b  mov     [rcx+0A8h], eax
0x180070d21  mov     [rcx+0ACh], r14d
0x180070d28  mov     [rsp+158h+var_F8], r14d
0x180070d2d  mov     [rsp+158h+var_EC], r14d
0x180070d32  mov     r15d, r14d
0x180070d35  mov     [rsp+158h+var_F4], r14d
0x180070d3a  add     rcx, 38h ; '8'; lpCriticalSection
0x180070d3e  call    cs:__imp_InitializeCriticalSection
0x180070d44  lea     rcx, [rdi+0B0h]; void *
0x180070d4b  xor     edx, edx; Val
0x180070d4d  mov     r8d, 100h; Size
0x180070d53  call    memset_0
0x180070d58  nop
0x180070d59  lock inc dword ptr [rdi+90h]
0x180070d60  test    rbx, rbx
0x180070d63  jz      loc_180070E36
0x180070d69  mov     rax, r12
0x180070d6c  inc     rax
0x180070d6f  cmp     [rbx+rax*2], r14w
0x180070d74  jnz     short loc_180070D6C
0x180070d76  lea     r14d, [rax+9]
0x180070d7a  mov     r12d, 2
0x180070d80  mov     eax, r12d
0x180070d83  mul     r14
0x180070d86  lea     rcx, [r12-3]
0x180070d8b  cmovb   rax, rcx
0x180070d8f  mov     rcx, rax; unsigned __int64
0x180070d92  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180070d97  mov     [rdi+68h], rax
0x180070d9b  test    rax, rax
0x180070d9e  jnz     short loc_180070DB1
0x180070da0  mov     ebx, 8007000Eh
0x180070da5  mov     [rsp+158h+var_F8], ebx
0x180070da9  xor     r14d, r14d
0x180070dac  jmp     loc_180071393
0x180070db1  lea     rcx, aTempsbe; "TempSBE"
0x180070db8  mov     qword ptr [rsp+158h+var_138], rcx
0x180070dbd  mov     r9, rbx
0x180070dc0  lea     r8, aSS; "%s\\%s"
0x180070dc7  mov     rdx, r14; BufferCount
0x180070dca  mov     rcx, rax; Buffer
0x180070dcd  call    swprintf_s
0x180070dd2  xor     edx, edx; lpSecurityAttributes
0x180070dd4  mov     rcx, [rdi+68h]; lpPathName
0x180070dd8  call    cs:__imp_CreateDirectoryW
0x180070dde  xor     r14d, r14d
0x180070de1  test    eax, eax
0x180070de3  jnz     short loc_180070E1D
0x180070de5  mov     rcx, [rdi+68h]; lpFileName
0x180070de9  call    cs:__imp_GetFileAttributesW
0x180070def  cmp     eax, 0FFFFFFFFh
0x180070df2  jnz     short loc_180070E12
0x180070df4  call    cs:__imp_GetLastError
0x180070dfa  mov     ebx, eax
0x180070dfc  test    eax, eax
0x180070dfe  jle     short loc_180070E09
0x180070e00  movzx   ebx, ax
0x180070e03  or      ebx, 80070000h
0x180070e09  mov     [rsp+158h+var_F8], ebx
0x180070e0d  jmp     loc_180071393
0x180070e12  test    al, 10h
0x180070e14  jnz     short loc_180070E25
0x180070e16  mov     ebx, 8007010Bh
0x180070e1b  jmp     short loc_180070E09
0x180070e1d  mov     [rsp+158h+var_EC], 1
0x180070e25  mov     edx, 6; dwFileAttributes
0x180070e2a  mov     rcx, [rdi+68h]; lpFileName
0x180070e2e  call    cs:__imp_SetFileAttributesW
0x180070e34  jmp     short loc_180070E3C
0x180070e36  mov     r12d, 2
0x180070e3c  test    r13, r13
0x180070e3f  jz      loc_180070F27
0x180070e45  mov     [rsp+158h+Buffer], r14w
0x180070e4e  mov     [rsp+158h+FilePart], r14
0x180070e56  xor     r9d, r9d; lpFilePart
0x180070e59  lea     r8, [rsp+158h+Buffer]; lpBuffer
0x180070e61  xor     edx, edx; nBufferLength
0x180070e63  mov     rcx, r13; lpFileName
0x180070e66  call    cs:__imp_GetFullPathNameW
0x180070e6c  mov     ebx, eax
0x180070e6e  test    eax, eax
0x180070e70  jz      short loc_180070DF4
0x180070e72  lea     r14d, [rax+1]
0x180070e76  mov     ecx, r14d
0x180070e79  mov     rax, r12
0x180070e7c  mul     rcx
0x180070e7f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180070e86  cmovb   rax, rcx
0x180070e8a  mov     rcx, rax; unsigned __int64
0x180070e8d  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180070e92  mov     [rdi+70h], rax
0x180070e96  test    rax, rax
0x180070e99  jz      loc_180070DA0
0x180070e9f  lea     r9, [rsp+158h+FilePart]; lpFilePart
0x180070ea7  mov     r8, rax; lpBuffer
0x180070eaa  mov     edx, r14d; nBufferLength
0x180070ead  mov     rcx, r13; lpFileName
0x180070eb0  call    cs:__imp_GetFullPathNameW
0x180070eb6  xor     r14d, r14d
0x180070eb9  test    eax, eax
0x180070ebb  jz      loc_180070DF4
0x180070ec1  cmp     eax, ebx
0x180070ec3  jbe     short loc_180070ECF
0x180070ec5  mov     ebx, 80004005h
0x180070eca  jmp     loc_180070E09
0x180070ecf  mov     rbx, [rsp+158h+FilePart]
0x180070ed7  sub     rbx, [rdi+70h]
0x180070edb  sar     rbx, 1
0x180070ede  lea     r14d, [rbx+1]
0x180070ee2  mov     rax, r12
0x180070ee5  mul     r14
0x180070ee8  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180070eef  cmovb   rax, rcx
0x180070ef3  mov     rcx, rax; unsigned __int64
0x180070ef6  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180070efb  mov     [rdi+78h], rax
0x180070eff  test    rax, rax
0x180070f02  jz      loc_180070DA0
0x180070f08  mov     ebx, ebx
0x180070f0a  mov     r9d, ebx
0x180070f0d  mov     r8, [rdi+70h]
0x180070f11  mov     edx, r14d
0x180070f14  mov     rcx, rax
0x180070f17  call    cs:__imp__o_wcsncpy_s
0x180070f1d  mov     rcx, [rdi+78h]
0x180070f21  xor     eax, eax
0x180070f23  mov     [rcx+rbx*2], ax
0x180070f27  imul    r14d, [rdi+8], 238h
0x180070f2f  add     r14d, 778h
0x180070f36  mov     r15d, [rdi+8Ch]
0x180070f3d  mov     [rsp+158h+var_E8], r15d
0x180070f42  test    r13, r13
0x180070f45  jz      loc_180070FD2
0x180070f4b  neg     [rsp+158h+arg_50]
0x180070f52  sbb     eax, eax
0x180070f54  and     eax, 0FC000080h
0x180070f59  add     eax, 4000000h
0x180070f5e  lea     rcx, [rdi+80h]
0x180070f65  mov     [rsp+158h+var_108], rcx; void **
0x180070f6a  lea     rcx, [rdi+30h]
0x180070f6e  mov     [rsp+158h+var_110], rcx; void **
0x180070f73  mov     [rsp+158h+var_118], rsi; struct CDVRFileCollection::CSharedData **
0x180070f78  mov     dword ptr [rsp+158h+var_120], eax; unsigned int
0x180070f7c  mov     r12d, 1
0x180070f82  mov     dword ptr [rsp+158h+var_128], r12d; unsigned int
0x180070f87  lea     rax, [rsp+158h+var_E8]
0x180070f8c  mov     [rsp+158h+var_130], rax; unsigned int *
0x180070f91  mov     [rsp+158h+var_138], r14d; unsigned int
0x180070f96  xor     r9d, r9d; unsigned __int8 *
0x180070f99  xor     r8d, r8d; unsigned int
0x180070f9c  mov     rdx, [rsp+158h+var_D8]; struct CDVRFileCollection::CClientInfo *
0x180070fa4  mov     rcx, rdi; this
0x180070fa7  call    ?CreateMemoryMap@CDVRFileCollection@@IEAAJPEBUCClientInfo@1@KPEAEKAEAKKKAEAPEAUCSharedData@1@PEAPEAX4@Z; CDVRFileCollection::CreateMemoryMap(CDVRFileCollection::CClientInfo const *,ulong,uchar *,ulong,ulong &,ulong,ulong,CDVRFileCollection::CSharedData * &,void * *,void * *)
0x180070fac  mov     ebx, eax
0x180070fae  test    eax, eax
0x180070fb0  jns     short loc_180070FBE
0x180070fb2  mov     [rsp+158h+var_F8], eax
0x180070fb6  xor     r14d, r14d
0x180070fb9  jmp     loc_18007138E
0x180070fbe  or      [rdi+0ACh], r12d
0x180070fc5  mov     ebx, r14d
0x180070fc8  mov     r15d, [rsp+158h+var_E8]
0x180070fcd  xor     r14d, r14d
0x180070fd0  jmp     short loc_180070FFF
0x180070fd2  mov     ebx, r14d
0x180070fd5  mov     ecx, r14d; unsigned __int64
0x180070fd8  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180070fdd  xor     r14d, r14d
0x180070fe0  test    rax, rax
0x180070fe3  jnz     short loc_180070FEF
0x180070fe5  mov     ebx, 8007000Eh
0x180070fea  jmp     loc_18007138A
0x180070fef  mov     [rsi], rax
0x180070ff2  or      [rdi+0ACh], r12d
0x180070ff9  mov     r12d, 1
0x180070fff  mov     r8, rbx; Size
0x180071002  xor     edx, edx; Val
0x180071004  mov     rcx, [rsi]; void *
0x180071007  call    memset_0
0x18007100c  mov     rcx, [rsi]
0x18007100f  lea     rax, [rcx+778h]
0x180071016  mov     [rdi+28h], rax
0x18007101a  movups  xmm0, xmmword ptr cs:?m_guidV11@CDVRFileCollection@@2U_GUID@@B.Data1; _GUID const CDVRFileCollection::m_guidV11 ...
0x180071021  movdqu  xmmword ptr [rcx], xmm0
0x180071025  mov     rax, [rsi]
0x180071028  mov     ecx, [rsp+158h+var_F0]
0x18007102c  mov     [rax+10h], ecx
0x18007102f  mov     rax, [rsi]
0x180071032  mov     ecx, dword ptr [rsp+158h+var_E0]
0x180071036  mov     [rax+14h], ecx
0x180071039  mov     rax, [rsi]
0x18007103c  mov     [rax+38h], r12d
0x180071040  call    cs:__imp_GetCurrentProcessId
0x180071046  mov     ecx, eax
0x180071048  mov     rax, [rsi]
0x18007104b  mov     [rax+44h], ecx
0x18007104e  mov     rcx, [rsi]
0x180071051  mov     eax, [rsp+158h+arg_38]
0x180071058  mov     [rcx+4Ch], eax
0x18007105b  mov     rax, [rsi]
0x18007105e  mov     [rax+54h], r14d
0x180071062  mov     rcx, [rsi]
0x180071065  mov     [rcx+58h], r14w
0x18007106a  cmp     [rsp+158h+arg_30], r14d
0x180071072  jz      short loc_18007107E
0x180071074  mov     rax, [rsi]
0x180071077  or      [rax+260h], r12d
0x18007107e  mov     rax, [rsi]
0x180071081  mov     ebx, 0FFFFh
0x180071086  mov     [rax+76Ch], bx
0x18007108d  mov     rax, [rsi]
0x180071090  mov     [rax+76Ah], bx
0x180071097  mov     rax, [rsi]
0x18007109a  mov     [rax+768h], bx
0x1800710a1  mov     rax, [rsi]
0x1800710a4  mov     [rax+772h], bx
0x1800710ab  mov     rax, [rsi]
0x1800710ae  mov     [rax+770h], bx
0x1800710b5  mov     rax, [rsi]
0x1800710b8  mov     [rax+76Eh], bx
0x1800710bf  mov     [rsp+158h+var_F0], r14d
0x1800710c4  mov     edx, r14d
0x1800710c7  mov     r8d, r14d
0x1800710ca  mov     r10d, r14d
0x1800710cd  mov     [rsp+158h+var_F0], edx
0x1800710d1  cmp     r8d, [rdi+8]
0x1800710d5  jnb     loc_180071177
0x1800710db  mov     eax, r8d
0x1800710de  imul    rcx, rax, 238h
0x1800710e5  mov     rax, [rdi+28h]
0x1800710e9  mov     [rcx+rax+236h], dx
0x1800710f1  mov     r9, [rsi]
0x1800710f4  movzx   r11d, word ptr [r9+770h]
0x1800710fc  mov     eax, r10d
0x1800710ff  imul    rdx, rax, 238h
0x180071106  mov     rcx, [rdi+28h]
0x18007110a  movzx   eax, word ptr [r9+772h]
0x180071112  mov     [rcx+rdx+232h], ax
0x18007111a  mov     rax, [rdi+28h]
0x18007111e  mov     [rax+rdx+234h], r11w
0x180071127  mov     r10, [rdi+28h]
0x18007112b  movzx   eax, word ptr [r10+rdx+236h]
0x180071134  cmp     r11w, bx
0x180071138  jnz     short loc_180071144
0x18007113a  mov     [r9+76Eh], ax
0x180071142  jmp     short loc_180071154
0x180071144  imul    rcx, r11, 238h
0x18007114b  mov     [rcx+r10+232h], ax
0x180071154  mov     rax, [rdi+28h]
0x180071158  movzx   ecx, word ptr [rax+rdx+236h]
0x180071160  mov     [r9+770h], cx
0x180071168  lea     edx, [r8+1]
0x18007116c  mov     r8d, edx
0x18007116f  mov     r10d, edx
0x180071172  jmp     loc_1800710CD
  ... truncated ...
```
