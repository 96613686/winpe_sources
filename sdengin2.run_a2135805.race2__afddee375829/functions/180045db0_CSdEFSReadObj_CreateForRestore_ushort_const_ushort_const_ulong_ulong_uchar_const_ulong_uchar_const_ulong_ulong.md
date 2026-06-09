# CSdEFSReadObj::CreateForRestore(ushort const *,ushort const *,ulong,ulong,uchar const *,ulong,uchar const *,ulong,ulong,ulong,ulong,int)

- ea: `0x180045db0`
- end: `0x180046400`
- name: `?CreateForRestore@CSdEFSReadObj@@UEAAJPEBG0KKPEBEK1KKKKH@Z`
- size: `1616`
- prototype: `__int64 __usercall@<rax>(CSdEFSReadObj *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, unsigned int@<r9d>, DWORD dwShareMode, const unsigned __int8 *Src, SIZE_T cb, PSECURITY_DESCRIPTOR pSecurityDescriptor, unsigned int, unsigned int, unsigned int, unsigned int, int)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800083e4`
- `0x180045db0`
- `0x1800485b0`
- `0x1800487bc`
- `0x180048c88`
- `0x180072e08`
- `0x180072f14`
- `0x1800935fc`
- `0x18009e904`
- `0x1800cf552`
- `0x1800d1010`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180046042`
- `KERNEL32!CreateFileW` at `0x1800460bf`
- `KERNEL32!CreateFileW` at `0x180046042`
- `KERNEL32!CreateFileW` at `0x1800460bf`
- `KERNEL32!CloseHandle` at `0x18004608b`
- `KERNEL32!CloseHandle` at `0x1800462b8`
- `KERNEL32!CloseHandle` at `0x180046382`
- `KERNEL32!CloseHandle` at `0x1800463b3`
- `KERNEL32!CloseHandle` at `0x1800463cc`
- `KERNEL32!CloseHandle` at `0x18004608b`
- `KERNEL32!CloseHandle` at `0x1800462b8`
- `KERNEL32!CloseHandle` at `0x180046382`
- `KERNEL32!CloseHandle` at `0x1800463b3`
- `KERNEL32!CloseHandle` at `0x1800463cc`
- `KERNEL32!DeviceIoControl` at `0x180046186`
- `KERNEL32!DeviceIoControl` at `0x180046186`
- `KERNEL32!SetFileTime` at `0x1800461ca`
- `KERNEL32!SetFileTime` at `0x1800461ca`
- `KERNEL32!SetFileShortNameW` at `0x18004610d`
- `KERNEL32!SetFileShortNameW` at `0x18004610d`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x1800462a9`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x1800462a9`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180046217`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180046217`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18004625b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18004625b`
- `ole32!CoTaskMemFree` at `0x180046343`
- `ole32!CoTaskMemFree` at `0x180046343`
- `ole32!CoTaskMemAlloc` at `0x180045f0a`
- `ole32!CoTaskMemAlloc` at `0x180045f0a`
- `ext-ms-win-advapi32-encryptedfile-l1-1-0!CloseEncryptedFileRaw` at `0x18004632f`
- `ext-ms-win-advapi32-encryptedfile-l1-1-0!CloseEncryptedFileRaw` at `0x18004632f`

## string_xrefs

- `0x180045de7`: `CSdEFSReadObj::CreateForRestore`

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
  int v26; // ecx
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  SECURITY_INFORMATION v30; // edx
  CSdEFSReadObj *v31; // rcx
  char *v32; // rcx
  int LastFailureAsHRESULT; // [rsp+48h] [rbp-89h] BYREF
  __int16 v35; // [rsp+4Ch] [rbp-85h]
  __int16 v36; // [rsp+4Eh] [rbp-83h]
  WINBOOL bDaclPresent; // [rsp+80h] [rbp-51h] BYREF
  WINBOOL bSaclPresent; // [rsp+84h] [rbp-4Dh] BYREF
  FILETIME CreationTime; // [rsp+88h] [rbp-49h] BYREF
  HANDLE hObject; // [rsp+90h] [rbp-41h] BYREF
  DWORD dwFlagsAndAttributes; // [rsp+98h] [rbp-39h]
  DWORD BytesReturned; // [rsp+9Ch] [rbp-35h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+A0h] [rbp-31h] BYREF
  WINBOOL bSaclDefaulted; // [rsp+A4h] [rbp-2Dh] BYREF
  void *v45; // [rsp+A8h] [rbp-29h] BYREF
  PACL pDacl; // [rsp+B0h] [rbp-21h] BYREF
  PACL pSacl; // [rsp+B8h] [rbp-19h] BYREF
  __int128 v48; // [rsp+C0h] [rbp-11h] BYREF
  __int64 v49; // [rsp+D0h] [rbp-1h]
  unsigned int dwCreationDisposition; // [rsp+120h] [rbp+4Fh]

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&LastFailureAsHRESULT,
    "CSdEFSReadObj::CreateForRestore",
    0x33Au,
    1u);
  v48 = 0;
  v49 = 0;
  hObject = (HANDLE)-1LL;
  v15 = 0;
  pDacl = 0;
  pSacl = 0;
  bDaclPresent = 0;
  bSaclPresent = 0;
  bDaclDefaulted = 0;
  bSaclDefaulted = 0;
  v16 = 0;
  v45 = 0;
  CreationTime.dwLowDateTime = -1;
  CreationTime.dwHighDateTime = -1;
  BytesReturned = 0;
  v17 = 851;
  if ( !a2 || (v35 = 851, v17 = 852, (a11 & 0x4000) == 0) || (v35 = 852, v17 = 853, (a11 & 0x800) != 0) )
  {
    v18 = -2147024809;
LABEL_3:
    LastFailureAsHRESULT = v18;
LABEL_4:
    v36 = v17;
    goto LABEL_71;
  }
  v35 = 853;
  v17 = 856;
  if ( *((_DWORD *)this + 21) )
  {
    v18 = -2130706378;
    goto LABEL_3;
  }
  LastFailureAsHRESULT = 0;
  v35 = 856;
  if ( a13 )
  {
    v18 = (*(__int64 (__fastcall **)(CSdEFSReadObj *, const unsigned __int16 *))(*(_QWORD *)this + 112LL))(this, a2);
    LastFailureAsHRESULT = v18;
    v17 = 862;
    if ( v18 < 0 )
      goto LABEL_4;
    v35 = 862;
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
  v35 = 892;
  memcpy_0(v19, Src, (unsigned int)cb);
LABEL_21:
  LODWORD(v49) = 0;
  LODWORD(v48) = 24;
  *((_QWORD *)&v48 + 1) = v20;
  v15 = (struct _SECURITY_ATTRIBUTES *)&v48;
LABEL_22:
  FileW = -1;
  LastFailureAsHRESULT = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 96LL))(*((_QWORD *)this + 5));
  v22 = 913;
  if ( LastFailureAsHRESULT >= 0 )
  {
    v35 = 913;
    LastFailureAsHRESULT = CSdEFSReadObj::_CreateTemporary(this, &hObject);
    v23 = 916;
    if ( LastFailureAsHRESULT >= 0
      && (v35 = 916,
          LastFailureAsHRESULT = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 104LL))(*((_QWORD *)this + 5)),
          v23 = 918,
          LastFailureAsHRESULT >= 0) )
    {
      v35 = 918;
      LastFailureAsHRESULT = CBsString::Set((CSdEFSReadObj *)((char *)this + 56), a2);
      v22 = 924;
      if ( LastFailureAsHRESULT < 0 )
        goto LABEL_23;
      v35 = 924;
      dwFlagsAndAttributes = a11 & 0xFFFFBFF8;
      FileW = (__int64)CreateFileW(a2, a4, dwShareMode, v15, dwCreationDisposition, a11 & 0xFFFFBFF8, 0);
      if ( ((FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v24);
        v22 = 939;
        goto LABEL_23;
      }
      LastFailureAsHRESULT = 0;
      v35 = 939;
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
      v35 = 956;
      if ( a3 && !SetFileShortNameW((HANDLE)FileW, a3) && (a12 & 1) == 0 )
      {
        v26 = ((__int64 (*)(void))GetLastFailureAsHRESULT)();
        if ( v26 == -2147024713 )
          v26 = 0;
        LastFailureAsHRESULT = v26;
        v22 = 972;
        if ( v26 < 0 )
          goto LABEL_23;
        v35 = 972;
      }
      if ( (a11 & 0x200) != 0 )
      {
        if ( !DeviceIoControl((HANDLE)FileW, 0x900C4u, 0, 0, 0, 0, &BytesReturned, 0) )
        {
          LastFailureAsHRESULT = GetLastFailureAsHRESULT(v27);
          v22 = 978;
          goto LABEL_23;
        }
        LastFailureAsHRESULT = 0;
        v35 = 978;
      }
      if ( !SetFileTime((HANDLE)FileW, &CreationTime, &CreationTime, &CreationTime) )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v28);
        v22 = 981;
        goto LABEL_23;
      }
      LastFailureAsHRESULT = 0;
      v35 = 981;
      if ( v20 )
      {
        if ( !GetSecurityDescriptorDacl(v20, &bDaclPresent, &pDacl, &bDaclDefaulted) )
        {
          LastFailureAsHRESULT = GetLastFailureAsHRESULT(v29);
          v22 = 985;
          goto LABEL_23;
        }
        LastFailureAsHRESULT = 0;
        v35 = 985;
        if ( !GetSecurityDescriptorSacl(v20, &bSaclPresent, &pSacl, &bSaclDefaulted) )
        {
          LastFailureAsHRESULT = GetLastFailureAsHRESULT(0);
          v22 = 986;
          goto LABEL_23;
        }
        v30 = 0;
        LastFailureAsHRESULT = 0;
        v35 = 986;
        if ( bDaclPresent )
          v30 = 4;
        if ( bSaclPresent )
          v30 |= 0x18u;
        SetKernelObjectSecurity((HANDLE)FileW, v30, v20);
      }
      CloseHandle((HANDLE)FileW);
      v31 = (CSdEFSReadObj *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_073a8bff2569312743b066711ccc96ff_Traceguids, a2);
      LastFailureAsHRESULT = CSdEFSReadObj::_OpenEncryptedFileRawWithRetry(v31, a2, 1u, &v45);
      if ( LastFailureAsHRESULT >= 0 )
      {
        FileW = -1;
        v35 = 1014;
        *((_DWORD *)this + 21) = 2;
        *((_QWORD *)this + 6) = v45;
        *((_DWORD *)this + 18) = dwShareMode;
        *((_DWORD *)this + 19) = a11;
        v32 = (char *)*((_QWORD *)this + 11);
        if ( (unsigned __int64)(v32 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(v32);
        *((_QWORD *)this + 11) = hObject;
        hObject = (HANDLE)-1LL;
        *((_QWORD *)this + 22) = v19;
        goto LABEL_67;
      }
      v36 = 1014;
      v16 = v45;
    }
    else
    {
      v36 = v23;
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 104LL))(*((_QWORD *)this + 5));
    }
    FileW = -1;
    if ( v16 )
      CloseEncryptedFileRaw(v16);
    goto LABEL_62;
  }
LABEL_23:
  v36 = v22;
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
0x180045db0  mov     rax, rsp
0x180045db3  mov     [rax+8], rbx
0x180045db7  mov     [rax+20h], r9d
0x180045dbb  mov     [rax+18h], r8
0x180045dbf  push    rbp
0x180045dc0  push    rsi
0x180045dc1  push    rdi
0x180045dc2  push    r12
0x180045dc4  push    r13
0x180045dc6  push    r14
0x180045dc8  push    r15
0x180045dca  lea     rbp, [rax-3Fh]
0x180045dce  sub     rsp, 0D0h
0x180045dd5  mov     r13, rdx
0x180045dd8  mov     rsi, rcx
0x180045ddb  mov     r9d, 1; unsigned __int16
0x180045de1  mov     r8d, 33Ah; unsigned __int16
0x180045de7  lea     rdx, aCsdefsreadobjC_4; "CSdEFSReadObj::CreateForRestore"
0x180045dee  lea     rcx, [rsp+100h+var_C0]; this
0x180045df3  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180045df8  xorps   xmm0, xmm0
0x180045dfb  xor     eax, eax
0x180045dfd  movups  [rbp+37h+var_48], xmm0
0x180045e01  mov     [rbp+37h+var_38], rax
0x180045e05  mov     [rbp+37h+hObject], 0FFFFFFFFFFFFFFFFh
0x180045e0d  xor     r12d, r12d
0x180045e10  mov     [rbp+37h+pDacl], r12
0x180045e14  mov     [rbp+37h+pSacl], r12
0x180045e18  mov     [rbp+37h+bDaclPresent], r12d
0x180045e1c  mov     [rbp+37h+bSaclPresent], r12d
0x180045e20  mov     [rbp+37h+bDaclDefaulted], r12d
0x180045e24  mov     [rbp+37h+bSaclDefaulted], r12d
0x180045e28  mov     r14d, r12d
0x180045e2b  mov     [rbp+37h+var_60], r12
0x180045e2f  or      eax, 0FFFFFFFFh
0x180045e32  mov     [rbp+37h+CreationTime.dwLowDateTime], eax
0x180045e35  mov     [rbp+37h+CreationTime.dwHighDateTime], eax
0x180045e38  mov     [rbp+37h+BytesReturned], r12d
0x180045e3c  mov     eax, 353h
0x180045e41  test    r13, r13
0x180045e44  jnz     short loc_180045E59
0x180045e46  mov     edi, 80070057h
0x180045e4b  mov     [rsp+100h+var_C0], edi
0x180045e4f  mov     [rsp+100h+var_BA], ax
0x180045e54  jmp     loc_1800463D8
0x180045e59  mov     [rsp+100h+var_BC], ax
0x180045e5e  mov     ecx, [rbp+37h+arg_50]
0x180045e64  mov     eax, 354h
0x180045e69  bt      ecx, 0Eh
0x180045e6d  jnb     short loc_180045E46
0x180045e6f  mov     [rsp+100h+var_BC], ax
0x180045e74  mov     eax, 355h
0x180045e79  bt      ecx, 0Bh
0x180045e7d  jb      short loc_180045E46
0x180045e7f  mov     [rsp+100h+var_BC], ax
0x180045e84  mov     eax, 358h
0x180045e89  cmp     [rsi+54h], r12d
0x180045e8d  jz      short loc_180045E96
0x180045e8f  mov     edi, 81000036h
0x180045e94  jmp     short loc_180045E4B
0x180045e96  mov     [rsp+100h+var_C0], r12d
0x180045e9b  mov     [rsp+100h+var_BC], ax
0x180045ea0  cmp     [rbp+37h+arg_60], r12d
0x180045ea7  jz      short loc_180045ED8
0x180045ea9  mov     rax, [rsi]
0x180045eac  mov     rdx, r13
0x180045eaf  mov     rcx, rsi
0x180045eb2  mov     rax, [rax+70h]
0x180045eb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045ebb  mov     edi, eax
0x180045ebd  mov     [rsp+100h+var_C0], eax
0x180045ec1  test    eax, eax
0x180045ec3  mov     eax, 35Eh
0x180045ec8  js      short loc_180045E4F
0x180045eca  mov     [rsp+100h+var_BC], ax
0x180045ecf  mov     [rbp+37h+arg_8], 2
0x180045ed6  jmp     short loc_180045EE1
0x180045ed8  mov     eax, [rbp+37h+arg_48]
0x180045ede  mov     [rbp+37h+arg_8], eax
0x180045ee1  mov     r15, r12
0x180045ee4  mov     rcx, rsi; this
0x180045ee7  call    ?_Dispose@CSdEFSReadObj@@AEAAJXZ; CSdEFSReadObj::_Dispose(void)
0x180045eec  mov     rdi, [rbp+37h+pSecurityDescriptor]
0x180045ef0  test    rdi, rdi
0x180045ef3  jz      short loc_180045F47
0x180045ef5  mov     rbx, [rbp+37h+Src]
0x180045ef9  test    rbx, rbx
0x180045efc  jz      short loc_180045F4B
0x180045efe  mov     eax, dword ptr [rbp+37h+cb]
0x180045f01  test    eax, eax
0x180045f03  jz      short loc_180045F4B
0x180045f05  mov     r12d, eax
0x180045f08  mov     ecx, eax; cb
0x180045f0a  call    cs:__imp_CoTaskMemAlloc
0x180045f11  nop     dword ptr [rax+rax+00h]
0x180045f16  mov     r15, rax
0x180045f19  test    rax, rax
0x180045f1c  mov     eax, 37Ch
0x180045f21  jnz     short loc_180045F2D
0x180045f23  mov     edi, 8007000Eh
0x180045f28  jmp     loc_180045E4B
0x180045f2d  mov     [rsp+100h+var_C0], r14d
0x180045f32  mov     [rsp+100h+var_BC], ax
0x180045f37  mov     r8, r12; Size
0x180045f3a  mov     rdx, rbx; Src
0x180045f3d  mov     rcx, r15; void *
0x180045f40  call    memcpy_0
0x180045f45  jmp     short loc_180045F50
0x180045f47  mov     rdi, [rbp+37h+Src]
0x180045f4b  test    rdi, rdi
0x180045f4e  jz      short loc_180045F63
0x180045f50  mov     dword ptr [rbp+37h+var_38], r14d
0x180045f54  mov     dword ptr [rbp+37h+var_48], 18h
0x180045f5b  mov     qword ptr [rbp+37h+var_48+8], rdi
0x180045f5f  lea     r12, [rbp+37h+var_48]
0x180045f63  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180045f67  mov     rcx, [rsi+28h]
0x180045f6b  mov     rax, [rcx]
0x180045f6e  mov     rax, [rax+60h]
0x180045f72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045f77  mov     [rsp+100h+var_C0], eax
0x180045f7b  test    eax, eax
0x180045f7d  mov     eax, 391h
0x180045f82  jns     short loc_180045F8E
0x180045f84  mov     [rsp+100h+var_BA], ax
0x180045f89  jmp     loc_18004633B
0x180045f8e  mov     [rsp+100h+var_BC], ax
0x180045f93  lea     rdx, [rbp+37h+hObject]; void **
0x180045f97  mov     rcx, rsi; this
0x180045f9a  call    ?_CreateTemporary@CSdEFSReadObj@@AEAAJPEAPEAX@Z; CSdEFSReadObj::_CreateTemporary(void * *)
0x180045f9f  mov     [rsp+100h+var_C0], eax
0x180045fa3  test    eax, eax
0x180045fa5  mov     eax, 394h
0x180045faa  js      short loc_180045FCE
0x180045fac  mov     [rsp+100h+var_BC], ax
0x180045fb1  mov     rcx, [rsi+28h]
0x180045fb5  mov     rax, [rcx]
0x180045fb8  mov     rax, [rax+68h]
0x180045fbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045fc1  mov     [rsp+100h+var_C0], eax
0x180045fc5  test    eax, eax
0x180045fc7  mov     eax, 396h
0x180045fcc  jns     short loc_180045FE8
0x180045fce  mov     [rsp+100h+var_BA], ax
0x180045fd3  mov     rcx, [rsi+28h]
0x180045fd7  mov     rax, [rcx]
0x180045fda  mov     rax, [rax+68h]
0x180045fde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045fe3  jmp     loc_180046320
0x180045fe8  mov     [rsp+100h+var_BC], ax
0x180045fed  lea     rcx, [rsi+38h]; this
0x180045ff1  mov     rdx, r13; unsigned __int16 *
0x180045ff4  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180045ff9  mov     [rsp+100h+var_C0], eax
0x180045ffd  test    eax, eax
0x180045fff  mov     eax, 39Ch
0x180046004  js      loc_180045F84
0x18004600a  mov     [rsp+100h+var_BC], ax
0x18004600f  mov     r14d, [rbp+37h+arg_50]
0x180046016  mov     eax, r14d
0x180046019  and     eax, 0FFFFBFF8h
0x18004601e  mov     [rbp+37h+var_70], eax
0x180046021  mov     [rsp+100h+hTemplateFile], 0; hTemplateFile
0x18004602a  mov     [rsp+100h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x18004602e  mov     eax, [rbp+37h+arg_8]
0x180046031  mov     [rsp+100h+dwCreationDisposition], eax; dwCreationDisposition
0x180046035  mov     r9, r12; lpSecurityAttributes
0x180046038  mov     r8d, [rbp+37h+dwShareMode]; dwShareMode
0x18004603c  mov     edx, [rbp+37h+dwDesiredAccess]; dwDesiredAccess
0x18004603f  mov     rcx, r13; lpFileName
0x180046042  call    cs:__imp_CreateFileW
0x180046049  nop     dword ptr [rax+rax+00h]
0x18004604e  mov     rbx, rax
0x180046051  inc     rax
0x180046054  test    rax, 0FFFFFFFFFFFFFFFEh
0x18004605a  jnz     short loc_18004606F
0x18004605c  call    GetLastFailureAsHRESULT
0x180046061  mov     [rsp+100h+var_C0], eax
0x180046065  mov     eax, 3ABh
0x18004606a  jmp     loc_180045F84
0x18004606f  mov     [rsp+100h+var_C0], 0
0x180046077  mov     eax, 3ABh
0x18004607c  mov     [rsp+100h+var_BC], ax
0x180046081  mov     dword ptr [rsi+50h], 1
0x180046088  mov     rcx, rbx; hObject
0x18004608b  call    cs:__imp_CloseHandle
0x180046092  nop     dword ptr [rax+rax+00h]
0x180046097  mov     [rsp+100h+hTemplateFile], 0; hTemplateFile
0x1800460a0  mov     eax, [rbp+37h+var_70]
0x1800460a3  mov     [rsp+100h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x1800460a7  mov     [rsp+100h+dwCreationDisposition], 3; dwCreationDisposition
0x1800460af  mov     r9, r12; lpSecurityAttributes
0x1800460b2  mov     r12d, [rbp+37h+dwShareMode]
0x1800460b6  mov     r8d, r12d; dwShareMode
0x1800460b9  mov     edx, [rbp+37h+dwDesiredAccess]; dwDesiredAccess
0x1800460bc  mov     rcx, r13; lpFileName
0x1800460bf  call    cs:__imp_CreateFileW
0x1800460c6  nop     dword ptr [rax+rax+00h]
0x1800460cb  mov     rbx, rax
0x1800460ce  inc     rax
0x1800460d1  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800460d7  jnz     short loc_1800460EC
0x1800460d9  call    GetLastFailureAsHRESULT
0x1800460de  mov     [rsp+100h+var_C0], eax
0x1800460e2  mov     eax, 3BCh
0x1800460e7  jmp     loc_180045F84
0x1800460ec  mov     [rsp+100h+var_C0], 0
0x1800460f4  mov     eax, 3BCh
0x1800460f9  mov     [rsp+100h+var_BC], ax
0x1800460fe  mov     rax, [rbp+37h+lpShortName]
0x180046102  test    rax, rax
0x180046105  jz      short loc_18004614E
0x180046107  mov     rdx, rax; lpShortName
0x18004610a  mov     rcx, rbx; hFile
0x18004610d  call    cs:__imp_SetFileShortNameW
0x180046114  nop     dword ptr [rax+rax+00h]
0x180046119  test    eax, eax
0x18004611b  jnz     short loc_18004614E
0x18004611d  test    [rbp+37h+arg_58], 1
0x180046124  jnz     short loc_18004614E
0x180046126  call    GetLastFailureAsHRESULT
0x18004612b  mov     ecx, eax
0x18004612d  xor     eax, eax
0x18004612f  cmp     ecx, 800700B7h
0x180046135  cmovz   ecx, eax
0x180046138  mov     [rsp+100h+var_C0], ecx
0x18004613c  mov     eax, 3CCh
0x180046141  test    ecx, ecx
0x180046143  js      loc_180045F84
0x180046149  mov     [rsp+100h+var_BC], ax
0x18004614e  bt      r14d, 9
0x180046153  jnb     short loc_1800461BB
0x180046155  mov     [rsp+100h+lpOverlapped], 0; lpOverlapped
0x18004615e  lea     rax, [rbp+37h+BytesReturned]
0x180046162  mov     [rsp+100h+hTemplateFile], rax; lpBytesReturned
0x180046167  mov     [rsp+100h+dwFlagsAndAttributes], 0; nOutBufferSize
0x18004616f  mov     qword ptr [rsp+100h+dwCreationDisposition], 0; lpOutBuffer
0x180046178  xor     r9d, r9d; nInBufferSize
0x18004617b  xor     r8d, r8d; lpInBuffer
0x18004617e  mov     edx, 900C4h; dwIoControlCode
0x180046183  mov     rcx, rbx; hDevice
0x180046186  call    cs:__imp_DeviceIoControl
0x18004618d  nop     dword ptr [rax+rax+00h]
0x180046192  test    eax, eax
0x180046194  jnz     short loc_1800461A9
0x180046196  call    GetLastFailureAsHRESULT
0x18004619b  mov     [rsp+100h+var_C0], eax
0x18004619f  mov     eax, 3D2h
0x1800461a4  jmp     loc_180045F84
0x1800461a9  mov     [rsp+100h+var_C0], 0
0x1800461b1  mov     eax, 3D2h
0x1800461b6  mov     [rsp+100h+var_BC], ax
0x1800461bb  lea     r9, [rbp+37h+CreationTime]; lpLastWriteTime
0x1800461bf  lea     r8, [rbp+37h+CreationTime]; lpLastAccessTime
0x1800461c3  lea     rdx, [rbp+37h+CreationTime]; lpCreationTime
0x1800461c7  mov     rcx, rbx; hFile
0x1800461ca  call    cs:__imp_SetFileTime
0x1800461d1  nop     dword ptr [rax+rax+00h]
0x1800461d6  test    eax, eax
0x1800461d8  jnz     short loc_1800461ED
0x1800461da  call    GetLastFailureAsHRESULT
0x1800461df  mov     [rsp+100h+var_C0], eax
0x1800461e3  mov     eax, 3D5h
0x1800461e8  jmp     loc_180045F84
0x1800461ed  mov     [rsp+100h+var_C0], 0
0x1800461f5  mov     eax, 3D5h
0x1800461fa  mov     [rsp+100h+var_BC], ax
0x1800461ff  test    rdi, rdi
0x180046202  jz      loc_1800462B5
0x180046208  lea     r9, [rbp+37h+bDaclDefaulted]; lpbDaclDefaulted
0x18004620c  lea     r8, [rbp+37h+pDacl]; pDacl
0x180046210  lea     rdx, [rbp+37h+bDaclPresent]; lpbDaclPresent
0x180046214  mov     rcx, rdi; pSecurityDescriptor
0x180046217  call    cs:__imp_GetSecurityDescriptorDacl
0x18004621e  nop     dword ptr [rax+rax+00h]
0x180046223  test    eax, eax
0x180046225  jnz     short loc_18004623A
0x180046227  call    GetLastFailureAsHRESULT
0x18004622c  mov     [rsp+100h+var_C0], eax
0x180046230  mov     eax, 3D9h
0x180046235  jmp     loc_180045F84
0x18004623a  mov     [rsp+100h+var_C0], 0
0x180046242  mov     eax, 3D9h
0x180046247  mov     [rsp+100h+var_BC], ax
0x18004624c  lea     r9, [rbp+37h+bSaclDefaulted]; lpbSaclDefaulted
0x180046250  lea     r8, [rbp+37h+pSacl]; pSacl
0x180046254  lea     rdx, [rbp+37h+bSaclPresent]; lpbSaclPresent
0x180046258  mov     rcx, rdi; pSecurityDescriptor
0x18004625b  call    cs:__imp_GetSecurityDescriptorSacl
0x180046262  nop     dword ptr [rax+rax+00h]
0x180046267  xor     ecx, ecx
0x180046269  test    eax, eax
0x18004626b  jnz     short loc_180046280
0x18004626d  call    GetLastFailureAsHRESULT
0x180046272  mov     [rsp+100h+var_C0], eax
0x180046276  mov     eax, 3DAh
0x18004627b  jmp     loc_180045F84
0x180046280  mov     edx, ecx
0x180046282  mov     [rsp+100h+var_C0], ecx
0x180046286  mov     eax, 3DAh
  ... truncated ...
```
