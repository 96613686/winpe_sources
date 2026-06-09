# SetObjectAccess2(void *)

- ea: `0x18003f730`
- end: `0x18003f9a4`
- name: `?SetObjectAccess2@@YAHPEAX@Z`
- size: `628`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180004a70`
- `0x18000a290`
- `0x18000ab30`
- `0x18001b3c4`
- `0x18001b730`
- `0x18001b8a0`
- `0x18001ba10`
- `0x18001bfac`
- `0x18001c340`
- `0x18001d19c`
- `0x18001d230`
- `0x18001d250`
- `0x180023900`
- `0x180023a60`
- `0x180039f70`
- `0x18003f730`
- `0x180043e24`
- `0x180044310`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f792`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f792`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f945`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f945`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003f95b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003f95b`
- `ntdll!RtlFreeSid` at `0x18003f865`
- `ntdll!RtlFreeSid` at `0x18003f865`

## string_xrefs

- `0x18003f94d`: `SetKernelObjectSecurity`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SetObjectAccess2(void *a1)
{
  __int64 v2; // rdx
  void *v4; // rax
  __int64 v5; // rdx
  void *v6; // rbx
  __int64 v7; // rdx
  void *v8; // rax
  CNtAce *v9; // rbx
  FARPROC ProcAddress; // rax
  unsigned int v11; // ebx
  DWORD SecurityDll; // eax
  unsigned int v13; // [rsp+20h] [rbp-59h]
  unsigned int v14; // [rsp+28h] [rbp-51h]
  unsigned int v15; // [rsp+30h] [rbp-49h]
  unsigned int v16; // [rsp+38h] [rbp-41h]
  unsigned int v17; // [rsp+40h] [rbp-39h]
  unsigned int v18; // [rsp+48h] [rbp-31h]
  unsigned int v19[2]; // [rsp+60h] [rbp-19h] BYREF
  void *v20; // [rsp+68h] [rbp-11h] BYREF
  int v21; // [rsp+70h] [rbp-9h]
  PSID Sid; // [rsp+78h] [rbp-1h] BYREF
  void *v23; // [rsp+80h] [rbp+7h] BYREF
  int v24; // [rsp+88h] [rbp+Fh]
  void *v25[2]; // [rsp+90h] [rbp+17h] BYREF
  void *v26[3]; // [rsp+A0h] [rbp+27h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v27; // [rsp+B8h] [rbp+3Fh] BYREF

  if ( !(unsigned int)IsNT() )
    return 1;
  v19[0] = 0;
  if ( (unsigned int)DLGetKernelObjectSecurity(a1, v2, 0, 0, v19) == 1 )
    return 0;
  if ( GetLastError() != 122 )
    return 0;
  v4 = CWin32DefaultArena::WbemMemAlloc(v19[0]);
  v6 = v4;
  if ( !v4 )
    return 0;
  v25[0] = v4;
  v25[1] = 0;
  if ( !(unsigned int)DLGetKernelObjectSecurity(a1, v5, v4, v19[0], v19) )
  {
LABEL_17:
    CVectorDeleteMe<char>::~CVectorDeleteMe<char>(v25);
    return 0;
  }
  CNtSecurityDescriptor::CNtSecurityDescriptor((CNtSecurityDescriptor *)&v20, v6);
  if ( v21 )
  {
LABEL_16:
    CNtAcl::~CNtAcl(&v20);
    goto LABEL_17;
  }
  CNtAcl::CNtAcl((CNtAcl *)&v23, 0x80u);
  if ( !(unsigned int)CNtSecurityDescriptor::GetDacl((CNtSecurityDescriptor *)&v20, (struct CNtAcl *)&v23) )
  {
LABEL_15:
    CNtAcl::~CNtAcl(&v23);
    goto LABEL_16;
  }
  Sid = 0;
  *(_DWORD *)v27.Value = 0;
  *(_WORD *)&v27.Value[4] = 256;
  LOBYTE(v7) = 1;
  if ( (unsigned int)DLAllocateAndInitializeSid(&v27, v7, 0, 0, v13, v14, v15, v16, v17, v18, &Sid) )
  {
    CNtSid::CNtSid((CNtSid *)v26, Sid);
    RtlFreeSid(Sid);
    v8 = CWin32DefaultArena::WbemMemAlloc(0x18u);
    v26[2] = v8;
    if ( v8 )
      v9 = CNtAce::CNtAce((CNtAce *)v8, 1048578, 0, 0, (struct CNtSid *)v26);
    else
      v9 = 0;
    if ( !v9 )
    {
      CMUILocale::_Free(v26[0]);
      goto LABEL_15;
    }
    if ( !*((_DWORD *)v9 + 4) )
      CNtAcl::AddAce((CNtAcl *)&v23, v9);
    CNtAce::`scalar deleting destructor'(v9, 1u);
    CMUILocale::_Free(v26[0]);
  }
  if ( v24 )
    goto LABEL_15;
  CNtSecurityDescriptor::SetDacl((CNtSecurityDescriptor *)&v20, (struct CNtAcl *)&v23);
  ProcAddress = (FARPROC)qword_1800702B8;
  if ( qword_1800702B8 )
    goto LABEL_27;
  v11 = 0;
  SecurityDll = DLpLoadSecurityDll();
  if ( !SecurityDll )
  {
    ProcAddress = GetProcAddress(g_hInstSecurityDLL, "SetKernelObjectSecurity");
    qword_1800702B8 = (__int64)ProcAddress;
    if ( !ProcAddress )
      goto LABEL_28;
LABEL_27:
    v11 = ((__int64 (__fastcall *)(void *, __int64, void *))ProcAddress)(a1, 4, v20);
    goto LABEL_28;
  }
  SetLastError(SecurityDll);
LABEL_28:
  CNtAcl::~CNtAcl(&v23);
  CNtAcl::~CNtAcl(&v20);
  CVectorDeleteMe<char>::~CVectorDeleteMe<char>(v25);
  return v11;
}

```

## disassembly

```asm
0x18003f730  mov     [rsp-8+arg_8], rbx
0x18003f735  mov     [rsp-8+arg_10], rdi
0x18003f73a  push    rbp
0x18003f73b  lea     rbp, [rsp-57h]
0x18003f740  sub     rsp, 0D0h
0x18003f747  mov     rax, cs:__security_cookie
0x18003f74e  xor     rax, rsp
0x18003f751  mov     [rbp+57h+var_10], rax
0x18003f755  mov     rdi, rcx
0x18003f758  call    ?IsNT@@YAHXZ; IsNT(void)
0x18003f75d  test    eax, eax
0x18003f75f  jnz     short loc_18003F76B
0x18003f761  mov     eax, 1
0x18003f766  jmp     loc_18003F8CF
0x18003f76b  mov     [rbp+57h+var_70], 0
0x18003f772  lea     rax, [rbp+57h+var_70]
0x18003f776  mov     [rsp+0D0h+var_B0], rax; unsigned int *
0x18003f77b  xor     r9d, r9d; unsigned int
0x18003f77e  xor     r8d, r8d; void *
0x18003f781  mov     rcx, rdi; void *
0x18003f784  call    ?DLGetKernelObjectSecurity@@YAHPEAXK0KPEAK@Z; DLGetKernelObjectSecurity(void *,ulong,void *,ulong,ulong *)
0x18003f789  cmp     eax, 1
0x18003f78c  jz      loc_18003F8CD
0x18003f792  call    cs:__imp_GetLastError
0x18003f798  cmp     eax, 7Ah ; 'z'
0x18003f79b  jnz     loc_18003F8CD
0x18003f7a1  mov     ecx, [rbp+57h+var_70]; unsigned __int64
0x18003f7a4  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18003f7a9  mov     rbx, rax
0x18003f7ac  test    rax, rax
0x18003f7af  jz      loc_18003F8CD
0x18003f7b5  mov     [rbp+57h+var_40], rax
0x18003f7b9  mov     [rbp+57h+var_38], 0
0x18003f7c1  lea     rax, [rbp+57h+var_70]
0x18003f7c5  mov     [rsp+0D0h+var_B0], rax; unsigned int
0x18003f7ca  mov     r9d, [rbp+57h+var_70]; unsigned int
0x18003f7ce  mov     r8, rbx; void *
0x18003f7d1  mov     rcx, rdi; void *
0x18003f7d4  call    ?DLGetKernelObjectSecurity@@YAHPEAXK0KPEAK@Z; DLGetKernelObjectSecurity(void *,ulong,void *,ulong,ulong *)
0x18003f7d9  test    eax, eax
0x18003f7db  jz      loc_18003F8C4
0x18003f7e1  mov     rdx, rbx; void *
0x18003f7e4  lea     rcx, [rbp+57h+var_68]; this
0x18003f7e8  call    ??0CNtSecurityDescriptor@@QEAA@PEAX@Z; CNtSecurityDescriptor::CNtSecurityDescriptor(void *)
0x18003f7ed  nop
0x18003f7ee  cmp     [rbp+57h+var_60], 0
0x18003f7f2  jnz     loc_18003F8BA
0x18003f7f8  mov     edx, 80h; unsigned int
0x18003f7fd  lea     rcx, [rbp+57h+var_50]; this
0x18003f801  call    ??0CNtAcl@@QEAA@K@Z; CNtAcl::CNtAcl(ulong)
0x18003f806  nop
0x18003f807  lea     rdx, [rbp+57h+var_50]; struct CNtAcl *
0x18003f80b  lea     rcx, [rbp+57h+var_68]; this
0x18003f80f  call    ?GetDacl@CNtSecurityDescriptor@@QEAAHAEAVCNtAcl@@@Z; CNtSecurityDescriptor::GetDacl(CNtAcl &)
0x18003f814  test    eax, eax
0x18003f816  jz      loc_18003F8B0
0x18003f81c  mov     [rbp+57h+Sid], 0
0x18003f824  mov     dword ptr [rbp+57h+var_18.Value], 0
0x18003f82b  mov     word ptr [rbp+57h+var_18.Value+4], 100h
0x18003f831  lea     rax, [rbp+57h+Sid]
0x18003f835  mov     [rsp+0D0h+var_80], rax; void **
0x18003f83a  xor     r9d, r9d; unsigned int
0x18003f83d  xor     r8d, r8d; unsigned int
0x18003f840  mov     dl, 1; unsigned __int8
0x18003f842  lea     rcx, [rbp+57h+var_18]; struct _SID_IDENTIFIER_AUTHORITY *
0x18003f846  call    ?DLAllocateAndInitializeSid@@YAHPEAU_SID_IDENTIFIER_AUTHORITY@@EKKKKKKKKPEAPEAX@Z; DLAllocateAndInitializeSid(_SID_IDENTIFIER_AUTHORITY *,uchar,ulong,ulong,ulong,ulong,ulong,ulong,ulong,ulong,void * *)
0x18003f84b  test    eax, eax
0x18003f84d  jz      loc_18003F919
0x18003f853  mov     rdx, [rbp+57h+Sid]; void *
0x18003f857  lea     rcx, [rbp+57h+var_30]; this
0x18003f85b  call    ??0CNtSid@@QEAA@PEAX@Z; CNtSid::CNtSid(void *)
0x18003f860  nop
0x18003f861  mov     rcx, [rbp+57h+Sid]; Sid
0x18003f865  call    cs:__imp_RtlFreeSid
0x18003f86b  mov     ecx, 18h; unsigned __int64
0x18003f870  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18003f875  mov     [rbp+57h+var_20], rax
0x18003f879  test    rax, rax
0x18003f87c  jz      short loc_18003F89F
0x18003f87e  lea     rcx, [rbp+57h+var_30]
0x18003f882  mov     [rsp+0D0h+var_B0], rcx; struct CNtSid *
0x18003f887  xor     r9d, r9d; unsigned int
0x18003f88a  xor     r8d, r8d; unsigned int
0x18003f88d  mov     edx, 100002h; unsigned int
0x18003f892  mov     rcx, rax; this
0x18003f895  call    ??0CNtAce@@QEAA@KKKAEAVCNtSid@@@Z; CNtAce::CNtAce(ulong,ulong,ulong,CNtSid &)
0x18003f89a  mov     rbx, rax
0x18003f89d  jmp     short loc_18003F8A1
0x18003f89f  xor     ebx, ebx
0x18003f8a1  test    rbx, rbx
0x18003f8a4  jnz     short loc_18003F8F0
0x18003f8a6  mov     rcx, [rbp+57h+var_30]; void *
0x18003f8aa  call    ?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x18003f8af  nop
0x18003f8b0  lea     rcx, [rbp+57h+var_50]; this
0x18003f8b4  call    ??1CNtAcl@@QEAA@XZ; CNtAcl::~CNtAcl(void)
0x18003f8b9  nop
0x18003f8ba  lea     rcx, [rbp+57h+var_68]; this
0x18003f8be  call    ??1CNtAcl@@QEAA@XZ; CNtAcl::~CNtAcl(void)
0x18003f8c3  nop
0x18003f8c4  lea     rcx, [rbp+57h+var_40]
0x18003f8c8  call    ??1?$CVectorDeleteMe@D@@QEAA@XZ; CVectorDeleteMe<char>::~CVectorDeleteMe<char>(void)
0x18003f8cd  xor     eax, eax
0x18003f8cf  mov     rcx, [rbp+57h+var_10]
0x18003f8d3  xor     rcx, rsp; StackCookie
0x18003f8d6  call    __security_check_cookie
0x18003f8db  lea     r11, [rsp+0D0h+var_s0]
0x18003f8e3  mov     rbx, [r11+18h]
0x18003f8e7  mov     rdi, [r11+20h]
0x18003f8eb  mov     rsp, r11
0x18003f8ee  pop     rbp
0x18003f8ef  retn
0x18003f8f0  cmp     dword ptr [rbx+10h], 0
0x18003f8f4  jnz     short loc_18003F902
0x18003f8f6  mov     rdx, rbx; struct CNtAce *
0x18003f8f9  lea     rcx, [rbp+57h+var_50]; this
0x18003f8fd  call    ?AddAce@CNtAcl@@QEAAHPEAVCNtAce@@@Z; CNtAcl::AddAce(CNtAce *)
0x18003f902  mov     edx, 1; unsigned int
0x18003f907  mov     rcx, rbx; this
0x18003f90a  call    ??_GCNtAce@@UEAAPEAXI@Z; CNtAce::`scalar deleting destructor'(uint)
0x18003f90f  nop
0x18003f910  mov     rcx, [rbp+57h+var_30]; void *
0x18003f914  call    ?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x18003f919  cmp     [rbp+57h+var_48], 0
0x18003f91d  jnz     short loc_18003F8B0
0x18003f91f  lea     rdx, [rbp+57h+var_50]; struct CNtAcl *
0x18003f923  lea     rcx, [rbp+57h+var_68]; this
0x18003f927  call    ?SetDacl@CNtSecurityDescriptor@@QEAAHPEAVCNtAcl@@@Z; CNtSecurityDescriptor::SetDacl(CNtAcl *)
0x18003f92c  mov     rax, cs:qword_1800702B8
0x18003f933  test    rax, rax
0x18003f936  jnz     short loc_18003F96D
0x18003f938  xor     ebx, ebx
0x18003f93a  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x18003f93f  test    eax, eax
0x18003f941  jz      short loc_18003F94D
0x18003f943  mov     ecx, eax; dwErrCode
0x18003f945  call    cs:__imp_SetLastError
0x18003f94b  jmp     short loc_18003F980
0x18003f94d  lea     rdx, aSetkernelobjec; "SetKernelObjectSecurity"
0x18003f954  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18003f95b  call    cs:__imp_GetProcAddress
0x18003f961  mov     cs:qword_1800702B8, rax
0x18003f968  test    rax, rax
0x18003f96b  jz      short loc_18003F980
0x18003f96d  mov     r8, [rbp+57h+var_68]
0x18003f971  mov     edx, 4
0x18003f976  mov     rcx, rdi
0x18003f979  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f97e  mov     ebx, eax
0x18003f980  lea     rcx, [rbp+57h+var_50]; this
0x18003f984  call    ??1CNtAcl@@QEAA@XZ; CNtAcl::~CNtAcl(void)
0x18003f989  nop
0x18003f98a  lea     rcx, [rbp+57h+var_68]; this
0x18003f98e  call    ??1CNtAcl@@QEAA@XZ; CNtAcl::~CNtAcl(void)
0x18003f993  nop
0x18003f994  lea     rcx, [rbp+57h+var_40]
0x18003f998  call    ??1?$CVectorDeleteMe@D@@QEAA@XZ; CVectorDeleteMe<char>::~CVectorDeleteMe<char>(void)
0x18003f99d  mov     eax, ebx
0x18003f99f  jmp     loc_18003F8CF
```
