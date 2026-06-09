# CSdEFSReadObj::CreateForRestore(ushort const *,ushort const *,ulong,ulong,uchar const *,ulong,uchar const *,ulong,ulong,ulong,ulong,int)

- ea: `0x180044400`
- end: `0x1800449ef`
- name: `?CreateForRestore@CSdEFSReadObj@@UEAAJPEBG0KKPEBEK1KKKKH@Z`
- size: `1519`
- prototype: `__int64 __usercall@<rax>(CSdEFSReadObj *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, unsigned int@<r9d>, DWORD dwShareMode, const unsigned __int8 *Src, SIZE_T cb, PSECURITY_DESCRIPTOR pSecurityDescriptor, unsigned int, unsigned int, unsigned int, unsigned int, int)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180008240`
- `0x180044400`
- `0x180046a68`
- `0x180046c60`
- `0x180047118`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f5d0`
- `0x18009a24c`
- `0x1800c97c2`
- `0x1800cb010`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18004468c`
- `KERNEL32!CreateFileW` at `0x1800446fd`
- `KERNEL32!CreateFileW` at `0x18004468c`
- `KERNEL32!CreateFileW` at `0x1800446fd`
- `KERNEL32!CloseHandle` at `0x1800446cf`
- `KERNEL32!CloseHandle` at `0x1800448cc`
- `KERNEL32!CloseHandle` at `0x180044984`
- `KERNEL32!CloseHandle` at `0x1800449af`
- `KERNEL32!CloseHandle` at `0x1800449c2`
- `KERNEL32!CloseHandle` at `0x1800446cf`
- `KERNEL32!CloseHandle` at `0x1800448cc`
- `KERNEL32!CloseHandle` at `0x180044984`
- `KERNEL32!CloseHandle` at `0x1800449af`
- `KERNEL32!CloseHandle` at `0x1800449c2`
- `KERNEL32!DeviceIoControl` at `0x1800447b8`
- `KERNEL32!DeviceIoControl` at `0x1800447b8`
- `KERNEL32!SetFileTime` at `0x1800447f6`
- `KERNEL32!SetFileTime` at `0x1800447f6`
- `KERNEL32!SetFileShortNameW` at `0x180044745`
- `KERNEL32!SetFileShortNameW` at `0x180044745`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x1800448c3`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x1800448c3`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18004483d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18004483d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18004487b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18004487b`
- `ole32!CoTaskMemFree` at `0x18004494b`
- `ole32!CoTaskMemFree` at `0x18004494b`
- `ole32!CoTaskMemAlloc` at `0x18004455a`
- `ole32!CoTaskMemAlloc` at `0x18004455a`
- `ext-ms-win-advapi32-encryptedfile-l1-1-0!CloseEncryptedFileRaw` at `0x18004493d`
- `ext-ms-win-advapi32-encryptedfile-l1-1-0!CloseEncryptedFileRaw` at `0x18004493d`

## string_xrefs

- `0x180044437`: `CSdEFSReadObj::CreateForRestore`

## pseudocode

```c
__int64 __fastcall CSdEFSReadObj::CreateForRestore(
        CSdEFSReadObj *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        DWORD a4,
        DWORD dwShareMode,
        unsigned __int8 *Src,
        SIZE_T cb,
        unsigned __int8 *pSecurityDescriptor,
        unsigned int a9,
        unsigned int a10,
        unsigned int a11,
        char a12,
        int a13)
{
  struct _SECURITY_ATTRIBUTES *v15; // r12
  void *v16; // r14
  __int16 v17; // ax
  int v18; // edi
  void *v19; // r15
  unsigned __int8 *v20; // rdi
  __int64 FileW; // rbx
  __int16 v22; // ax
  __int16 v23; // ax
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  int v27; // ecx
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  SECURITY_INFORMATION v31; // edx
  CSdEFSReadObj *v32; // rcx
  char *v33; // rcx
  int LastFailureAsHRESULT; // [rsp+48h] [rbp-89h] BYREF
  __int16 v36; // [rsp+4Ch] [rbp-85h]
  __int16 v37; // [rsp+4Eh] [rbp-83h]
  WINBOOL bDaclPresent; // [rsp+80h] [rbp-51h] BYREF
  WINBOOL bSaclPresent; // [rsp+84h] [rbp-4Dh] BYREF
  FILETIME CreationTime; // [rsp+88h] [rbp-49h] BYREF
  HANDLE hObject; // [rsp+90h] [rbp-41h] BYREF
  DWORD dwFlagsAndAttributes; // [rsp+98h] [rbp-39h]
  DWORD BytesReturned; // [rsp+9Ch] [rbp-35h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+A0h] [rbp-31h] BYREF
  WINBOOL bSaclDefaulted; // [rsp+A4h] [rbp-2Dh] BYREF
  void *v46; // [rsp+A8h] [rbp-29h] BYREF
  PACL pDacl; // [rsp+B0h] [rbp-21h] BYREF
  PACL pSacl; // [rsp+B8h] [rbp-19h] BYREF
  __int128 v49; // [rsp+C0h] [rbp-11h] BYREF
  __int64 v50; // [rsp+D0h] [rbp-1h]
  unsigned int dwCreationDisposition; // [rsp+120h] [rbp+4Fh]

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&LastFailureAsHRESULT,
    "CSdEFSReadObj::CreateForRestore",
    826,
    1);
  v49 = 0;
  v50 = 0;
  hObject = (HANDLE)-1LL;
  v15 = 0;
  pDacl = 0;
  pSacl = 0;
  bDaclPresent = 0;
  bSaclPresent = 0;
  bDaclDefaulted = 0;
  bSaclDefaulted = 0;
  v16 = 0;
  v46 = 0;
  CreationTime.dwLowDateTime = -1;
  CreationTime.dwHighDateTime = -1;
  BytesReturned = 0;
  v17 = 851;
  if ( !a2 || (v36 = 851, v17 = 852, (a11 & 0x4000) == 0) || (v36 = 852, v17 = 853, (a11 & 0x800) != 0) )
  {
    v18 = -2147024809;
LABEL_3:
    LastFailureAsHRESULT = v18;
LABEL_4:
    v37 = v17;
    goto LABEL_71;
  }
  v36 = 853;
  v17 = 856;
  if ( *((_DWORD *)this + 21) )
  {
    v18 = -2130706378;
    goto LABEL_3;
  }
  LastFailureAsHRESULT = 0;
  v36 = 856;
  if ( a13 )
  {
    v18 = (*(__int64 (__fastcall **)(CSdEFSReadObj *, const unsigned __int16 *))(*(_QWORD *)this + 112LL))(this, a2);
    LastFailureAsHRESULT = v18;
    v17 = 862;
    if ( v18 < 0 )
      goto LABEL_4;
    v36 = 862;
    dwCreationDisposition = 2;
  }
  else
  {
    dwCreationDisposition = a10;
  }
  v19 = 0;
  CSdEFSReadObj::_Dispose(this);
  v20 = pSecurityDescriptor;
  if ( !pSecurityDescriptor )
  {
    v20 = Src;
    goto LABEL_20;
  }
  if ( !Src || !(_DWORD)cb )
  {
LABEL_20:
    if ( !v20 )
      goto LABEL_22;
    goto LABEL_21;
  }
  v19 = CoTaskMemAlloc((unsigned int)cb);
  v17 = 892;
  if ( !v19 )
  {
    v18 = -2147024882;
    goto LABEL_3;
  }
  LastFailureAsHRESULT = 0;
  v36 = 892;
  memcpy_0(v19, Src, (unsigned int)cb);
LABEL_21:
  LODWORD(v50) = 0;
  LODWORD(v49) = 24;
  *((_QWORD *)&v49 + 1) = v20;
  v15 = (struct _SECURITY_ATTRIBUTES *)&v49;
LABEL_22:
  FileW = -1;
  LastFailureAsHRESULT = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 96LL))(*((_QWORD *)this + 5));
  v22 = 913;
  if ( LastFailureAsHRESULT >= 0 )
  {
    v36 = 913;
    LastFailureAsHRESULT = CSdEFSReadObj::_CreateTemporary(this, &hObject);
    v23 = 916;
    if ( LastFailureAsHRESULT >= 0
      && (v36 = 916,
          LastFailureAsHRESULT = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 104LL))(*((_QWORD *)this + 5)),
          v23 = 918,
          LastFailureAsHRESULT >= 0) )
    {
      v36 = 918;
      LastFailureAsHRESULT = CBsString::Set((CSdEFSReadObj *)((char *)this + 56), a2);
      v22 = 924;
      if ( LastFailureAsHRESULT < 0 )
        goto LABEL_23;
      v36 = 924;
      dwFlagsAndAttributes = a11 & 0xFFFFBFF8;
      FileW = (__int64)CreateFileW(a2, a4, dwShareMode, v15, dwCreationDisposition, a11 & 0xFFFFBFF8, 0);
      if ( ((FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v24);
        v22 = 939;
        goto LABEL_23;
      }
      LastFailureAsHRESULT = 0;
      v36 = 939;
      *((_DWORD *)this + 20) = 1;
      CloseHandle((HANDLE)FileW);
      FileW = (__int64)CreateFileW(a2, a4, dwShareMode, v15, 3u, dwFlagsAndAttributes, 0);
      if ( ((FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v25);
        v22 = 956;
        goto LABEL_23;
      }
      LastFailureAsHRESULT = 0;
      v36 = 956;
      if ( a3 && !SetFileShortNameW((HANDLE)FileW, a3) && (a12 & 1) == 0 )
      {
        v27 = GetLastFailureAsHRESULT(v26);
        if ( v27 == -2147024713 )
          v27 = 0;
        LastFailureAsHRESULT = v27;
        v22 = 972;
        if ( v27 < 0 )
          goto LABEL_23;
        v36 = 972;
      }
      if ( (a11 & 0x200) != 0 )
      {
        if ( !DeviceIoControl((HANDLE)FileW, 0x900C4u, 0, 0, 0, 0, &BytesReturned, 0) )
        {
          LastFailureAsHRESULT = GetLastFailureAsHRESULT(v28);
          v22 = 978;
          goto LABEL_23;
        }
        LastFailureAsHRESULT = 0;
        v36 = 978;
      }
      if ( !SetFileTime((HANDLE)FileW, &CreationTime, &CreationTime, &CreationTime) )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v29);
        v22 = 981;
        goto LABEL_23;
      }
      LastFailureAsHRESULT = 0;
      v36 = 981;
      if ( v20 )
      {
        if ( !GetSecurityDescriptorDacl(v20, &bDaclPresent, &pDacl, &bDaclDefaulted) )
        {
          LastFailureAsHRESULT = GetLastFailureAsHRESULT(v30);
          v22 = 985;
          goto LABEL_23;
        }
        LastFailureAsHRESULT = 0;
        v36 = 985;
        if ( !GetSecurityDescriptorSacl(v20, &bSaclPresent, &pSacl, &bSaclDefaulted) )
        {
          LastFailureAsHRESULT = GetLastFailureAsHRESULT(0);
          v22 = 986;
          goto LABEL_23;
        }
        v31 = 0;
        LastFailureAsHRESULT = 0;
        v36 = 986;
        if ( bDaclPresent )
          v31 = 4;
        if ( bSaclPresent )
          v31 |= 0x18u;
        SetKernelObjectSecurity((HANDLE)FileW, v31, v20);
      }
      CloseHandle((HANDLE)FileW);
      v32 = (CSdEFSReadObj *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_073a8bff2569312743b066711ccc96ff_Traceguids, a2);
      LastFailureAsHRESULT = CSdEFSReadObj::_OpenEncryptedFileRawWithRetry(v32, a2, 1u, &v46);
      if ( LastFailureAsHRESULT >= 0 )
      {
        FileW = -1;
        v36 = 1014;
        *((_DWORD *)this + 21) = 2;
        *((_QWORD *)this + 6) = v46;
        *((_DWORD *)this + 18) = dwShareMode;
        *((_DWORD *)this + 19) = a11;
        v33 = (char *)*((_QWORD *)this + 11);
        if ( (unsigned __int64)(v33 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(v33);
        *((_QWORD *)this + 11) = hObject;
        hObject = (HANDLE)-1LL;
        *((_QWORD *)this + 22) = v19;
        goto LABEL_67;
      }
      v37 = 1014;
      v16 = v46;
    }
    else
    {
      v37 = v23;
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 104LL))(*((_QWORD *)this + 5));
    }
    FileW = -1;
    if ( v16 )
      CloseEncryptedFileRaw(v16);
    goto LABEL_62;
  }
LABEL_23:
  v37 = v22;
LABEL_62:
  if ( v19 )
    CoTaskMemFree(v19);
LABEL_67:
  v18 = LastFailureAsHRESULT;
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
LABEL_71:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x180044400  mov     rax, rsp
0x180044403  mov     [rax+8], rbx
0x180044407  mov     [rax+20h], r9d
0x18004440b  mov     [rax+18h], r8
0x18004440f  push    rbp
0x180044410  push    rsi
0x180044411  push    rdi
0x180044412  push    r12
0x180044414  push    r13
0x180044416  push    r14
0x180044418  push    r15
0x18004441a  lea     rbp, [rax-3Fh]
0x18004441e  sub     rsp, 0D0h
0x180044425  mov     r13, rdx
0x180044428  mov     rsi, rcx
0x18004442b  mov     r9d, 1; unsigned __int16
0x180044431  mov     r8d, 33Ah; unsigned __int16
0x180044437  lea     rdx, aCsdefsreadobjC_4; "CSdEFSReadObj::CreateForRestore"
0x18004443e  lea     rcx, [rsp+100h+var_C0]; this
0x180044443  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180044448  xorps   xmm0, xmm0
0x18004444b  xor     eax, eax
0x18004444d  movups  [rbp+37h+var_48], xmm0
0x180044451  mov     [rbp+37h+var_38], rax
0x180044455  mov     [rbp+37h+hObject], 0FFFFFFFFFFFFFFFFh
0x18004445d  xor     r12d, r12d
0x180044460  mov     [rbp+37h+pDacl], r12
0x180044464  mov     [rbp+37h+pSacl], r12
0x180044468  mov     [rbp+37h+bDaclPresent], r12d
0x18004446c  mov     [rbp+37h+bSaclPresent], r12d
0x180044470  mov     [rbp+37h+bDaclDefaulted], r12d
0x180044474  mov     [rbp+37h+bSaclDefaulted], r12d
0x180044478  mov     r14d, r12d
0x18004447b  mov     [rbp+37h+var_60], r12
0x18004447f  or      eax, 0FFFFFFFFh
0x180044482  mov     [rbp+37h+CreationTime.dwLowDateTime], eax
0x180044485  mov     [rbp+37h+CreationTime.dwHighDateTime], eax
0x180044488  mov     [rbp+37h+BytesReturned], r12d
0x18004448c  mov     eax, 353h
0x180044491  test    r13, r13
0x180044494  jnz     short loc_1800444A9
0x180044496  mov     edi, 80070057h
0x18004449b  mov     [rsp+100h+var_C0], edi
0x18004449f  mov     [rsp+100h+var_BA], ax
0x1800444a4  jmp     loc_1800449C8
0x1800444a9  mov     [rsp+100h+var_BC], ax
0x1800444ae  mov     ecx, [rbp+37h+arg_50]
0x1800444b4  mov     eax, 354h
0x1800444b9  bt      ecx, 0Eh
0x1800444bd  jnb     short loc_180044496
0x1800444bf  mov     [rsp+100h+var_BC], ax
0x1800444c4  mov     eax, 355h
0x1800444c9  bt      ecx, 0Bh
0x1800444cd  jb      short loc_180044496
0x1800444cf  mov     [rsp+100h+var_BC], ax
0x1800444d4  mov     eax, 358h
0x1800444d9  cmp     [rsi+54h], r12d
0x1800444dd  jz      short loc_1800444E6
0x1800444df  mov     edi, 81000036h
0x1800444e4  jmp     short loc_18004449B
0x1800444e6  mov     [rsp+100h+var_C0], r12d
0x1800444eb  mov     [rsp+100h+var_BC], ax
0x1800444f0  cmp     [rbp+37h+arg_60], r12d
0x1800444f7  jz      short loc_180044528
0x1800444f9  mov     rax, [rsi]
0x1800444fc  mov     rdx, r13
0x1800444ff  mov     rcx, rsi
0x180044502  mov     rax, [rax+70h]
0x180044506  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004450b  mov     edi, eax
0x18004450d  mov     [rsp+100h+var_C0], eax
0x180044511  test    eax, eax
0x180044513  mov     eax, 35Eh
0x180044518  js      short loc_18004449F
0x18004451a  mov     [rsp+100h+var_BC], ax
0x18004451f  mov     [rbp+37h+arg_8], 2
0x180044526  jmp     short loc_180044531
0x180044528  mov     eax, [rbp+37h+arg_48]
0x18004452e  mov     [rbp+37h+arg_8], eax
0x180044531  mov     r15, r12
0x180044534  mov     rcx, rsi; this
0x180044537  call    ?_Dispose@CSdEFSReadObj@@AEAAJXZ; CSdEFSReadObj::_Dispose(void)
0x18004453c  mov     rdi, [rbp+37h+pSecurityDescriptor]
0x180044540  test    rdi, rdi
0x180044543  jz      short loc_180044591
0x180044545  mov     rbx, [rbp+37h+Src]
0x180044549  test    rbx, rbx
0x18004454c  jz      short loc_180044595
0x18004454e  mov     eax, dword ptr [rbp+37h+cb]
0x180044551  test    eax, eax
0x180044553  jz      short loc_180044595
0x180044555  mov     r12d, eax
0x180044558  mov     ecx, eax; cb
0x18004455a  call    cs:__imp_CoTaskMemAlloc
0x180044560  mov     r15, rax
0x180044563  test    rax, rax
0x180044566  mov     eax, 37Ch
0x18004456b  jnz     short loc_180044577
0x18004456d  mov     edi, 8007000Eh
0x180044572  jmp     loc_18004449B
0x180044577  mov     [rsp+100h+var_C0], r14d
0x18004457c  mov     [rsp+100h+var_BC], ax
0x180044581  mov     r8, r12; Size
0x180044584  mov     rdx, rbx; Src
0x180044587  mov     rcx, r15; void *
0x18004458a  call    memcpy_0
0x18004458f  jmp     short loc_18004459A
0x180044591  mov     rdi, [rbp+37h+Src]
0x180044595  test    rdi, rdi
0x180044598  jz      short loc_1800445AD
0x18004459a  mov     dword ptr [rbp+37h+var_38], r14d
0x18004459e  mov     dword ptr [rbp+37h+var_48], 18h
0x1800445a5  mov     qword ptr [rbp+37h+var_48+8], rdi
0x1800445a9  lea     r12, [rbp+37h+var_48]
0x1800445ad  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800445b1  mov     rcx, [rsi+28h]
0x1800445b5  mov     rax, [rcx]
0x1800445b8  mov     rax, [rax+60h]
0x1800445bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800445c1  mov     [rsp+100h+var_C0], eax
0x1800445c5  test    eax, eax
0x1800445c7  mov     eax, 391h
0x1800445cc  jns     short loc_1800445D8
0x1800445ce  mov     [rsp+100h+var_BA], ax
0x1800445d3  jmp     loc_180044943
0x1800445d8  mov     [rsp+100h+var_BC], ax
0x1800445dd  lea     rdx, [rbp+37h+hObject]; void **
0x1800445e1  mov     rcx, rsi; this
0x1800445e4  call    ?_CreateTemporary@CSdEFSReadObj@@AEAAJPEAPEAX@Z; CSdEFSReadObj::_CreateTemporary(void * *)
0x1800445e9  mov     [rsp+100h+var_C0], eax
0x1800445ed  test    eax, eax
0x1800445ef  mov     eax, 394h
0x1800445f4  js      short loc_180044618
0x1800445f6  mov     [rsp+100h+var_BC], ax
0x1800445fb  mov     rcx, [rsi+28h]
0x1800445ff  mov     rax, [rcx]
0x180044602  mov     rax, [rax+68h]
0x180044606  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004460b  mov     [rsp+100h+var_C0], eax
0x18004460f  test    eax, eax
0x180044611  mov     eax, 396h
0x180044616  jns     short loc_180044632
0x180044618  mov     [rsp+100h+var_BA], ax
0x18004461d  mov     rcx, [rsi+28h]
0x180044621  mov     rax, [rcx]
0x180044624  mov     rax, [rax+68h]
0x180044628  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004462d  jmp     loc_18004492E
0x180044632  mov     [rsp+100h+var_BC], ax
0x180044637  lea     rcx, [rsi+38h]; this
0x18004463b  mov     rdx, r13; unsigned __int16 *
0x18004463e  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180044643  mov     [rsp+100h+var_C0], eax
0x180044647  test    eax, eax
0x180044649  mov     eax, 39Ch
0x18004464e  js      loc_1800445CE
0x180044654  mov     [rsp+100h+var_BC], ax
0x180044659  mov     r14d, [rbp+37h+arg_50]
0x180044660  mov     eax, r14d
0x180044663  and     eax, 0FFFFBFF8h
0x180044668  mov     [rbp+37h+var_70], eax
0x18004466b  mov     [rsp+100h+hTemplateFile], 0; hTemplateFile
0x180044674  mov     [rsp+100h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x180044678  mov     eax, [rbp+37h+arg_8]
0x18004467b  mov     [rsp+100h+dwCreationDisposition], eax; dwCreationDisposition
0x18004467f  mov     r9, r12; lpSecurityAttributes
0x180044682  mov     r8d, [rbp+37h+dwShareMode]; dwShareMode
0x180044686  mov     edx, [rbp+37h+dwDesiredAccess]; dwDesiredAccess
0x180044689  mov     rcx, r13; lpFileName
0x18004468c  call    cs:__imp_CreateFileW
0x180044692  mov     rbx, rax
0x180044695  inc     rax
0x180044698  test    rax, 0FFFFFFFFFFFFFFFEh
0x18004469e  jnz     short loc_1800446B3
0x1800446a0  call    GetLastFailureAsHRESULT
0x1800446a5  mov     [rsp+100h+var_C0], eax
0x1800446a9  mov     eax, 3ABh
0x1800446ae  jmp     loc_1800445CE
0x1800446b3  mov     [rsp+100h+var_C0], 0
0x1800446bb  mov     eax, 3ABh
0x1800446c0  mov     [rsp+100h+var_BC], ax
0x1800446c5  mov     dword ptr [rsi+50h], 1
0x1800446cc  mov     rcx, rbx; hObject
0x1800446cf  call    cs:__imp_CloseHandle
0x1800446d5  mov     [rsp+100h+hTemplateFile], 0; hTemplateFile
0x1800446de  mov     eax, [rbp+37h+var_70]
0x1800446e1  mov     [rsp+100h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x1800446e5  mov     [rsp+100h+dwCreationDisposition], 3; dwCreationDisposition
0x1800446ed  mov     r9, r12; lpSecurityAttributes
0x1800446f0  mov     r12d, [rbp+37h+dwShareMode]
0x1800446f4  mov     r8d, r12d; dwShareMode
0x1800446f7  mov     edx, [rbp+37h+dwDesiredAccess]; dwDesiredAccess
0x1800446fa  mov     rcx, r13; lpFileName
0x1800446fd  call    cs:__imp_CreateFileW
0x180044703  mov     rbx, rax
0x180044706  inc     rax
0x180044709  test    rax, 0FFFFFFFFFFFFFFFEh
0x18004470f  jnz     short loc_180044724
0x180044711  call    GetLastFailureAsHRESULT
0x180044716  mov     [rsp+100h+var_C0], eax
0x18004471a  mov     eax, 3BCh
0x18004471f  jmp     loc_1800445CE
0x180044724  mov     [rsp+100h+var_C0], 0
0x18004472c  mov     eax, 3BCh
0x180044731  mov     [rsp+100h+var_BC], ax
0x180044736  mov     rax, [rbp+37h+lpShortName]
0x18004473a  test    rax, rax
0x18004473d  jz      short loc_180044780
0x18004473f  mov     rdx, rax; lpShortName
0x180044742  mov     rcx, rbx; hFile
0x180044745  call    cs:__imp_SetFileShortNameW
0x18004474b  test    eax, eax
0x18004474d  jnz     short loc_180044780
0x18004474f  test    [rbp+37h+arg_58], 1
0x180044756  jnz     short loc_180044780
0x180044758  call    GetLastFailureAsHRESULT
0x18004475d  mov     ecx, eax
0x18004475f  xor     eax, eax
0x180044761  cmp     ecx, 800700B7h
0x180044767  cmovz   ecx, eax
0x18004476a  mov     [rsp+100h+var_C0], ecx
0x18004476e  mov     eax, 3CCh
0x180044773  test    ecx, ecx
0x180044775  js      loc_1800445CE
0x18004477b  mov     [rsp+100h+var_BC], ax
0x180044780  bt      r14d, 9
0x180044785  jnb     short loc_1800447E7
0x180044787  mov     [rsp+100h+lpOverlapped], 0; lpOverlapped
0x180044790  lea     rax, [rbp+37h+BytesReturned]
0x180044794  mov     [rsp+100h+hTemplateFile], rax; lpBytesReturned
0x180044799  mov     [rsp+100h+dwFlagsAndAttributes], 0; nOutBufferSize
0x1800447a1  mov     qword ptr [rsp+100h+dwCreationDisposition], 0; lpOutBuffer
0x1800447aa  xor     r9d, r9d; nInBufferSize
0x1800447ad  xor     r8d, r8d; lpInBuffer
0x1800447b0  mov     edx, 900C4h; dwIoControlCode
0x1800447b5  mov     rcx, rbx; hDevice
0x1800447b8  call    cs:__imp_DeviceIoControl
0x1800447be  test    eax, eax
0x1800447c0  jnz     short loc_1800447D5
0x1800447c2  call    GetLastFailureAsHRESULT
0x1800447c7  mov     [rsp+100h+var_C0], eax
0x1800447cb  mov     eax, 3D2h
0x1800447d0  jmp     loc_1800445CE
0x1800447d5  mov     [rsp+100h+var_C0], 0
0x1800447dd  mov     eax, 3D2h
0x1800447e2  mov     [rsp+100h+var_BC], ax
0x1800447e7  lea     r9, [rbp+37h+CreationTime]; lpLastWriteTime
0x1800447eb  lea     r8, [rbp+37h+CreationTime]; lpLastAccessTime
0x1800447ef  lea     rdx, [rbp+37h+CreationTime]; lpCreationTime
0x1800447f3  mov     rcx, rbx; hFile
0x1800447f6  call    cs:__imp_SetFileTime
0x1800447fc  test    eax, eax
0x1800447fe  jnz     short loc_180044813
0x180044800  call    GetLastFailureAsHRESULT
0x180044805  mov     [rsp+100h+var_C0], eax
0x180044809  mov     eax, 3D5h
0x18004480e  jmp     loc_1800445CE
0x180044813  mov     [rsp+100h+var_C0], 0
0x18004481b  mov     eax, 3D5h
0x180044820  mov     [rsp+100h+var_BC], ax
0x180044825  test    rdi, rdi
0x180044828  jz      loc_1800448C9
0x18004482e  lea     r9, [rbp+37h+bDaclDefaulted]; lpbDaclDefaulted
0x180044832  lea     r8, [rbp+37h+pDacl]; pDacl
0x180044836  lea     rdx, [rbp+37h+bDaclPresent]; lpbDaclPresent
0x18004483a  mov     rcx, rdi; pSecurityDescriptor
0x18004483d  call    cs:__imp_GetSecurityDescriptorDacl
0x180044843  test    eax, eax
0x180044845  jnz     short loc_18004485A
0x180044847  call    GetLastFailureAsHRESULT
0x18004484c  mov     [rsp+100h+var_C0], eax
0x180044850  mov     eax, 3D9h
0x180044855  jmp     loc_1800445CE
0x18004485a  mov     [rsp+100h+var_C0], 0
0x180044862  mov     eax, 3D9h
0x180044867  mov     [rsp+100h+var_BC], ax
0x18004486c  lea     r9, [rbp+37h+bSaclDefaulted]; lpbSaclDefaulted
0x180044870  lea     r8, [rbp+37h+pSacl]; pSacl
0x180044874  lea     rdx, [rbp+37h+bSaclPresent]; lpbSaclPresent
0x180044878  mov     rcx, rdi; pSecurityDescriptor
0x18004487b  call    cs:__imp_GetSecurityDescriptorSacl
0x180044881  xor     ecx, ecx
0x180044883  test    eax, eax
0x180044885  jnz     short loc_18004489A
0x180044887  call    GetLastFailureAsHRESULT
0x18004488c  mov     [rsp+100h+var_C0], eax
0x180044890  mov     eax, 3DAh
0x180044895  jmp     loc_1800445CE
0x18004489a  mov     edx, ecx
0x18004489c  mov     [rsp+100h+var_C0], ecx
0x1800448a0  mov     eax, 3DAh
0x1800448a5  mov     [rsp+100h+var_BC], ax
0x1800448aa  mov     eax, 4
0x1800448af  cmp     [rbp+37h+bDaclPresent], ecx
0x1800448b2  cmovnz  edx, eax
0x1800448b5  cmp     [rbp+37h+bSaclPresent], ecx
0x1800448b8  jz      short loc_1800448BD
0x1800448ba  or      edx, 18h; SecurityInformation
0x1800448bd  mov     r8, rdi; SecurityDescriptor
0x1800448c0  mov     rcx, rbx; Handle
  ... truncated ...
```
