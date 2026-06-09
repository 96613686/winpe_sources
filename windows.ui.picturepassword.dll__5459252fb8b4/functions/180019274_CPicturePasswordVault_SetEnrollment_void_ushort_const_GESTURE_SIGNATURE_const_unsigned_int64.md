# CPicturePasswordVault::SetEnrollment(void *,ushort const *,GESTURE_SIGNATURE const *,unsigned __int64)

- ea: `0x180019274`
- end: `0x18001960a`
- name: `?SetEnrollment@CPicturePasswordVault@@SAJPEAXPEBGPEBUGESTURE_SIGNATURE@@_K@Z`
- size: `918`
- prototype: `__int64 __fastcall(PSID Sid, const unsigned __int16 *, const struct GESTURE_SIGNATURE *Src)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000b318`

## callees

- `0x180002610`
- `0x180005a2c`
- `0x1800092b8`
- `0x18000a0e4`
- `0x18000a64c`
- `0x18000a67c`
- `0x180015b00`
- `0x180018d64`
- `0x180019274`
- `0x180019610`
- `0x1800197cc`
- `0x1800198d4`
- `0x18001e3a0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800193b4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800193b4`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180019536`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180019536`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180019594`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180019594`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800195b2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800195b2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001941d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001941d`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultCloseVault` at `0x1800194dd`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultCloseVault` at `0x1800194dd`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultAddItem` at `0x1800194c3`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultAddItem` at `0x1800194c3`

## pseudocode

```c
__int64 __fastcall CPicturePasswordVault::SetEnrollment(
        PSID Sid,
        const unsigned __int16 *a2,
        const struct GESTURE_SIGNATURE *Src)
{
  __int64 v3; // rsi
  unsigned __int64 v4; // rdi
  PSID v7; // r12
  unsigned __int64 v8; // r14
  signed int Error; // ebx
  unsigned __int64 v10; // r9
  unsigned __int16 *v11; // rdi
  unsigned __int64 v12; // rcx
  int v13; // ecx
  void *v14; // rcx
  int v15; // r12d
  LPWSTR v16; // r14
  __int64 v17; // r15
  PSID v18; // rbx
  DWORD LengthSid; // eax
  int v20; // eax
  __int64 i; // rsi
  const unsigned __int16 *v22; // r8
  LSTATUS Key; // eax
  unsigned __int16 **dwOptions; // [rsp+20h] [rbp-E0h]
  unsigned __int64 *samDesired; // [rsp+28h] [rbp-D8h]
  unsigned int lpSecurityAttributes; // [rsp+30h] [rbp-D0h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+50h] [rbp-B0h] BYREF
  LPWSTR StringSid; // [rsp+58h] [rbp-A8h] BYREF
  size_t Size; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v31; // [rsp+68h] [rbp-98h] BYREF
  PSID pSid; // [rsp+70h] [rbp-90h]
  unsigned __int16 *v33; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v34[2]; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v35; // [rsp+90h] [rbp-70h]
  int v36; // [rsp+94h] [rbp-6Ch]
  unsigned __int16 *v37; // [rsp+98h] [rbp-68h]
  _QWORD v38[2]; // [rsp+A0h] [rbp-60h] BYREF
  int v39; // [rsp+B0h] [rbp-50h]
  int v40; // [rsp+B4h] [rbp-4Ch]
  LPWSTR v41; // [rsp+B8h] [rbp-48h]
  LPCWSTR lpSubKey[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v43; // [rsp+D0h] [rbp-30h]
  int v44; // [rsp+E0h] [rbp-20h]
  HKEY hKey; // [rsp+E8h] [rbp-18h]
  _QWORD v46[4]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v47; // [rsp+110h] [rbp+10h] BYREF
  const wchar_t *v48; // [rsp+120h] [rbp+20h]
  _QWORD *v49; // [rsp+128h] [rbp+28h]
  LPCWSTR *v50; // [rsp+130h] [rbp+30h]
  _QWORD *v51; // [rsp+138h] [rbp+38h]
  __int64 v52; // [rsp+140h] [rbp+40h]
  struct _FILETIME v53; // [rsp+148h] [rbp+48h]
  int v54; // [rsp+150h] [rbp+50h]
  int v55; // [rsp+154h] [rbp+54h]
  _QWORD *v56; // [rsp+158h] [rbp+58h]

  v3 = -1;
  pSid = Sid;
  v4 = -1;
  v7 = Sid;
  do
    ++v4;
  while ( a2[v4] );
  v8 = v4 + 1;
  v33 = 0;
  if ( v4 + 1 < v4 )
  {
    Error = -2147024362;
  }
  else
  {
    Error = _AllocArray<unsigned short,CTLocalAllocPolicy>(Sid, a2, v4 + 1, &v33);
    if ( Error >= 0 )
    {
      v10 = v4;
      v11 = v33;
      StringCchCopyNExW(v33, v8, a2, v10, dwOptions, samDesired, lpSecurityAttributes);
      v12 = -1;
      v31 = 0;
      do
        ++v12;
      while ( v11[v12] );
      Error = ULongLongToULong(v12, &v31);
      if ( Error >= 0 )
      {
        LODWORD(Size) = 0;
        Error = ULongLongToULong(0x3Cu, (unsigned int *)&Size);
        if ( Error >= 0 )
        {
          StringSid = 0;
          SystemTimeAsFileTime = 0;
          Error = ULongLongMult(
                    (unsigned int)(v13 - 57),
                    (unsigned int)(v13 - 40),
                    (unsigned __int64 *)&SystemTimeAsFileTime);
          if ( Error >= 0 )
          {
            Error = CTLocalAllocPolicy::Alloc(v14, 0x40u, *(_QWORD *)&SystemTimeAsFileTime, (void **)&StringSid);
            if ( Error >= 0 )
            {
              v15 = Size;
              v16 = StringSid;
              v17 = (unsigned int)Size;
              memcpy_0(StringSid, Src, (unsigned int)Size);
              SystemTimeAsFileTime = 0;
              GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
              Size = 0;
              Error = _OpenPicturePasswordVault((void **)&Size);
              if ( Error >= 0 )
              {
                v18 = pSid;
                v46[3] = 0;
                v46[0] = 1;
                *(_OWORD *)lpSubKey = 0;
                LODWORD(lpSubKey[0]) = 2;
                LODWORD(lpSubKey[1]) = 8;
                v46[1] = 7;
                v46[2] = L"Picture Password Vault Resource";
                v43 = 0;
                LengthSid = GetLengthSid(pSid);
                v34[1] = 8;
                LODWORD(v43) = LengthSid;
                v38[1] = 8;
                v36 = 0;
                v40 = 0;
                v35 = 2 * v31 + 2;
                v48 = L"Picture Password Credential";
                v49 = v46;
                v50 = lpSubKey;
                v51 = v34;
                v53 = SystemTimeAsFileTime;
                v56 = v38;
                *((_QWORD *)&v43 + 1) = v18;
                v34[0] = 3;
                v37 = v11;
                v38[0] = 100;
                v39 = v15;
                v41 = v16;
                v47 = c_guidPicturePasswordVaultSchema;
                v52 = 0;
                v54 = 0;
                v55 = 1;
                v20 = VaultAddItem(Size, &v47, 0, 0, 0);
                Error = v20;
                if ( v20 > 0 )
                  Error = (unsigned __int16)v20 | 0x80070000;
                VaultCloseVault(&Size);
              }
              if ( v15 )
              {
                do
                {
                  *(_BYTE *)v16 = 0;
                  v16 = (LPWSTR)((char *)v16 + 1);
                  --v17;
                }
                while ( v17 );
              }
              v7 = pSid;
            }
          }
          CLocalMemPtr<unsigned short>::~CLocalMemPtr<unsigned short>(&StringSid);
        }
      }
      do
        ++v3;
      while ( v11[v3] );
      for ( i = 2 * v3; i; --i )
      {
        *(_BYTE *)v11 = 0;
        v11 = (unsigned __int16 *)((char *)v11 + 1);
      }
      if ( Error >= 0 )
      {
        StringSid = 0;
        if ( ConvertSidToStringSidW(v7, &StringSid) || (Error = ResultFromKnownLastError(), Error >= 0) )
        {
          CConvenienceLogonEnrollmentData::CConvenienceLogonEnrollmentData(
            (CConvenienceLogonEnrollmentData *)lpSubKey,
            StringSid,
            v22);
          Error = v44;
          if ( v44 >= 0 )
          {
            SystemTimeAsFileTime = 0;
            Key = RegCreateKeyExW(hKey, lpSubKey[1], 0, 0, 0, 0x20006u, 0, (PHKEY)&SystemTimeAsFileTime, 0);
            Error = Key;
            if ( Key > 0 )
              Error = (unsigned __int16)Key | 0x80070000;
            if ( Error >= 0 )
              RegCloseKey(*(HKEY *)&SystemTimeAsFileTime);
          }
          CConvenienceLogonEnrollmentData::~CConvenienceLogonEnrollmentData((CConvenienceLogonEnrollmentData *)lpSubKey);
        }
        CLocalMemPtr<unsigned short>::~CLocalMemPtr<unsigned short>(&StringSid);
      }
    }
  }
  CLocalMemPtr<unsigned short>::~CLocalMemPtr<unsigned short>(&v33);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180019274  mov     rax, rsp
0x180019277  mov     [rax+20h], rbx
0x18001927b  push    rbp
0x18001927c  push    rsi
0x18001927d  push    rdi
0x18001927e  push    r12
0x180019280  push    r13
0x180019282  push    r14
0x180019284  push    r15
0x180019286  lea     rbp, [rsp-80h]
0x18001928b  sub     rsp, 180h
0x180019292  movaps  xmmword ptr [rax-48h], xmm6
0x180019296  mov     rax, cs:__security_cookie
0x18001929d  xor     rax, rsp
0x1800192a0  mov     [rbp+0B0h+var_50], rax
0x1800192a4  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800192a8  mov     [rsp+1B0h+pSid], rcx
0x1800192ad  mov     rdi, rsi
0x1800192b0  xor     eax, eax
0x1800192b2  mov     r13, r8
0x1800192b5  mov     r15, rdx
0x1800192b8  mov     r12, rcx
0x1800192bb  inc     rdi
0x1800192be  cmp     [rdx+rdi*2], ax
0x1800192c2  jnz     short loc_1800192BB
0x1800192c4  lea     r14, [rdi+1]
0x1800192c8  mov     [rsp+1B0h+var_138], rax
0x1800192cd  cmp     r14, rdi
0x1800192d0  jb      loc_1800195CD
0x1800192d6  lea     r9, [rsp+1B0h+var_138]
0x1800192db  mov     r8, r14
0x1800192de  call    ??$_AllocArray@GVCTLocalAllocPolicy@@@@YAJPEAXK_KPEAPEAG@Z; _AllocArray<ushort,CTLocalAllocPolicy>(void *,ulong,unsigned __int64,ushort * *)
0x1800192e3  mov     ebx, eax
0x1800192e5  test    eax, eax
0x1800192e7  js      loc_1800195D2
0x1800192ed  mov     r9, rdi; unsigned __int64
0x1800192f0  mov     r8, r15; unsigned __int16 *
0x1800192f3  mov     rdi, [rsp+1B0h+var_138]
0x1800192f8  mov     rdx, r14; unsigned __int64
0x1800192fb  mov     rcx, rdi; unsigned __int16 *
0x1800192fe  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x180019303  xor     r14d, r14d
0x180019306  mov     rcx, rsi
0x180019309  mov     [rsp+1B0h+var_148], r14d
0x18001930e  inc     rcx; unsigned __int64
0x180019311  cmp     [rdi+rcx*2], r14w
0x180019316  jnz     short loc_18001930E
0x180019318  lea     rdx, [rsp+1B0h+var_148]; unsigned int *
0x18001931d  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180019322  mov     ebx, eax
0x180019324  test    eax, eax
0x180019326  js      loc_180019506
0x18001932c  lea     rdx, [rsp+1B0h+Size]; unsigned int *
0x180019331  mov     dword ptr [rsp+1B0h+Size], r14d
0x180019336  mov     ecx, 3Ch ; '<'; unsigned __int64
0x18001933b  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180019340  mov     ebx, eax
0x180019342  test    eax, eax
0x180019344  js      loc_180019506
0x18001934a  lea     edx, [rcx-28h]; unsigned __int64
0x18001934d  mov     [rsp+1B0h+StringSid], r14
0x180019352  lea     ecx, [rdx-11h]; unsigned __int64
0x180019355  mov     qword ptr [rsp+1B0h+SystemTimeAsFileTime.dwLowDateTime], r14
0x18001935a  lea     r8, [rsp+1B0h+SystemTimeAsFileTime]; unsigned __int64 *
0x18001935f  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180019364  mov     ebx, eax
0x180019366  test    eax, eax
0x180019368  js      loc_1800194FC
0x18001936e  mov     r8, qword ptr [rsp+1B0h+SystemTimeAsFileTime.dwLowDateTime]; unsigned __int64
0x180019373  lea     r9, [rsp+1B0h+StringSid]; void **
0x180019378  mov     edx, 40h ; '@'; unsigned int
0x18001937d  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180019382  mov     ebx, eax
0x180019384  test    eax, eax
0x180019386  js      loc_1800194FC
0x18001938c  mov     r12d, dword ptr [rsp+1B0h+Size]
0x180019391  mov     rdx, r13; Src
0x180019394  mov     r14, [rsp+1B0h+StringSid]
0x180019399  mov     r8d, r12d; Size
0x18001939c  mov     rcx, r14; void *
0x18001939f  mov     r15d, r12d
0x1800193a2  call    memcpy_0
0x1800193a7  xor     r13d, r13d
0x1800193aa  lea     rcx, [rsp+1B0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800193af  mov     qword ptr [rsp+1B0h+SystemTimeAsFileTime.dwLowDateTime], r13
0x1800193b4  call    cs:__imp_GetSystemTimeAsFileTime
0x1800193ba  lea     rcx, [rsp+1B0h+Size]; void **
0x1800193bf  mov     [rsp+1B0h+Size], r13
0x1800193c4  call    ?_OpenPicturePasswordVault@@YAJPEAPEAX@Z; _OpenPicturePasswordVault(void * *)
0x1800193c9  mov     ebx, eax
0x1800193cb  test    eax, eax
0x1800193cd  js      loc_1800194E3
0x1800193d3  mov     rbx, [rsp+1B0h+pSid]
0x1800193d8  lea     rax, aPicturePasswor_1; "Picture Password Vault Resource"
0x1800193df  movups  xmm6, cs:c_guidPicturePasswordVaultSchema
0x1800193e6  mov     [rbp+0B0h+var_A8], r13
0x1800193ea  mov     r13d, 8
0x1800193f0  xorps   xmm0, xmm0
0x1800193f3  mov     [rbp+0B0h+var_C0], 1
0x1800193fb  movups  xmmword ptr [rbp+0B0h+lpSubKey], xmm0
0x1800193ff  mov     rcx, rbx; pSid
0x180019402  mov     dword ptr [rbp+0B0h+lpSubKey], 2
0x180019409  mov     dword ptr [rbp+0B0h+lpSubKey+8], r13d
0x18001940d  mov     [rbp+0B0h+var_B8], 7
0x180019415  mov     [rbp+0B0h+var_B0], rax
0x180019419  movups  [rbp+0B0h+var_E0], xmm0
0x18001941d  call    cs:__imp_GetLengthSid
0x180019423  xor     ecx, ecx
0x180019425  mov     [rbp+0B0h+var_128], r13
0x180019429  mov     dword ptr [rbp+0B0h+var_E0], eax
0x18001942c  lea     rdx, [rbp+0B0h+var_A0]
0x180019430  mov     eax, [rsp+1B0h+var_148]
0x180019434  xor     r9d, r9d
0x180019437  mov     [rbp+0B0h+var_108], r13
0x18001943b  xor     r8d, r8d
0x18001943e  xor     r13d, r13d
0x180019441  mov     [rbp+0B0h+var_11C], ecx
0x180019444  mov     [rbp+0B0h+var_FC], ecx
0x180019447  mov     rcx, [rsp+1B0h+Size]
0x18001944c  lea     eax, ds:2[rax*2]
0x180019453  mov     [rbp+0B0h+var_120], eax
0x180019456  lea     rax, aPicturePasswor_0; "Picture Password Credential"
0x18001945d  mov     [rbp+0B0h+var_90], rax
0x180019461  lea     rax, [rbp+0B0h+var_C0]
0x180019465  mov     [rbp+0B0h+var_88], rax
0x180019469  lea     rax, [rbp+0B0h+lpSubKey]
0x18001946d  mov     [rbp+0B0h+var_80], rax
0x180019471  lea     rax, [rbp+0B0h+var_130]
0x180019475  mov     [rbp+0B0h+var_78], rax
0x180019479  mov     rax, qword ptr [rsp+1B0h+SystemTimeAsFileTime.dwLowDateTime]
0x18001947e  mov     [rbp+0B0h+var_68], rax
0x180019482  lea     rax, [rbp+0B0h+var_110]
0x180019486  mov     [rbp+0B0h+var_58], rax
0x18001948a  mov     qword ptr [rbp+0B0h+var_E0+8], rbx
0x18001948e  mov     [rbp+0B0h+var_130], 3
0x180019496  mov     [rbp+0B0h+var_118], rdi
0x18001949a  mov     [rbp+0B0h+var_110], 64h ; 'd'
0x1800194a2  mov     [rbp+0B0h+var_100], r12d
0x1800194a6  mov     [rbp+0B0h+var_F8], r14
0x1800194aa  movdqu  [rbp+0B0h+var_A0], xmm6
0x1800194af  mov     [rbp+0B0h+var_70], r13
0x1800194b3  mov     [rbp+0B0h+var_60], r13d
0x1800194b7  mov     [rbp+0B0h+var_5C], 1
0x1800194be  mov     dword ptr [rsp+1B0h+dwOptions], r13d
0x1800194c3  call    cs:__imp_VaultAddItem
0x1800194c9  mov     ebx, eax
0x1800194cb  test    eax, eax
0x1800194cd  jle     short loc_1800194D8
0x1800194cf  movzx   ebx, ax
0x1800194d2  or      ebx, 80070000h
0x1800194d8  lea     rcx, [rsp+1B0h+Size]
0x1800194dd  call    cs:__imp_VaultCloseVault
0x1800194e3  test    r12d, r12d
0x1800194e6  jz      short loc_1800194F4
0x1800194e8  mov     [r14], r13b
0x1800194eb  inc     r14
0x1800194ee  sub     r15, 1
0x1800194f2  jnz     short loc_1800194E8
0x1800194f4  mov     r12, [rsp+1B0h+pSid]
0x1800194f9  xor     r14d, r14d
0x1800194fc  lea     rcx, [rsp+1B0h+StringSid]
0x180019501  call    ??1?$CLocalMemPtr@G@@QEAA@XZ; CLocalMemPtr<ushort>::~CLocalMemPtr<ushort>(void)
0x180019506  inc     rsi
0x180019509  cmp     [rdi+rsi*2], r14w
0x18001950e  jnz     short loc_180019506
0x180019510  add     rsi, rsi
0x180019513  jz      short loc_180019521
0x180019515  mov     [rdi], r14b
0x180019518  inc     rdi
0x18001951b  sub     rsi, 1
0x18001951f  jnz     short loc_180019515
0x180019521  test    ebx, ebx
0x180019523  js      loc_1800195D2
0x180019529  lea     rdx, [rsp+1B0h+StringSid]; StringSid
0x18001952e  mov     [rsp+1B0h+StringSid], r14
0x180019533  mov     rcx, r12; Sid
0x180019536  call    cs:__imp_ConvertSidToStringSidW
0x18001953c  test    eax, eax
0x18001953e  jnz     short loc_18001954B
0x180019540  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180019545  mov     ebx, eax
0x180019547  test    eax, eax
0x180019549  js      short loc_1800195C1
0x18001954b  mov     rdx, [rsp+1B0h+StringSid]; unsigned __int16 *
0x180019550  lea     rcx, [rbp+0B0h+lpSubKey]; this
0x180019554  call    ??0CConvenienceLogonEnrollmentData@@QEAA@PEBG0@Z; CConvenienceLogonEnrollmentData::CConvenienceLogonEnrollmentData(ushort const *,ushort const *)
0x180019559  mov     ebx, [rbp+0B0h+var_D0]
0x18001955c  test    ebx, ebx
0x18001955e  js      short loc_1800195B8
0x180019560  mov     rdx, [rbp+0B0h+lpSubKey+8]; lpSubKey
0x180019564  lea     rax, [rsp+1B0h+SystemTimeAsFileTime]
0x180019569  mov     rcx, [rbp+0B0h+hKey]; hKey
0x18001956d  xor     r9d, r9d; lpClass
0x180019570  mov     [rsp+1B0h+lpdwDisposition], r14; lpdwDisposition
0x180019575  xor     r8d, r8d; Reserved
0x180019578  mov     [rsp+1B0h+phkResult], rax; phkResult
0x18001957d  mov     [rsp+1B0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180019582  mov     dword ptr [rsp+1B0h+samDesired], 20006h; samDesired
0x18001958a  mov     dword ptr [rsp+1B0h+dwOptions], r14d; dwOptions
0x18001958f  mov     qword ptr [rsp+1B0h+SystemTimeAsFileTime.dwLowDateTime], r14
0x180019594  call    cs:__imp_RegCreateKeyExW
0x18001959a  mov     ebx, eax
0x18001959c  test    eax, eax
0x18001959e  jle     short loc_1800195A9
0x1800195a0  movzx   ebx, ax
0x1800195a3  or      ebx, 80070000h
0x1800195a9  test    ebx, ebx
0x1800195ab  js      short loc_1800195B8
0x1800195ad  mov     rcx, qword ptr [rsp+1B0h+SystemTimeAsFileTime.dwLowDateTime]; hKey
0x1800195b2  call    cs:__imp_RegCloseKey
0x1800195b8  lea     rcx, [rbp+0B0h+lpSubKey]; this
0x1800195bc  call    ??1CConvenienceLogonEnrollmentData@@UEAA@XZ; CConvenienceLogonEnrollmentData::~CConvenienceLogonEnrollmentData(void)
0x1800195c1  lea     rcx, [rsp+1B0h+StringSid]
0x1800195c6  call    ??1?$CLocalMemPtr@G@@QEAA@XZ; CLocalMemPtr<ushort>::~CLocalMemPtr<ushort>(void)
0x1800195cb  jmp     short loc_1800195D2
0x1800195cd  mov     ebx, 80070216h
0x1800195d2  lea     rcx, [rsp+1B0h+var_138]
0x1800195d7  call    ??1?$CLocalMemPtr@G@@QEAA@XZ; CLocalMemPtr<ushort>::~CLocalMemPtr<ushort>(void)
0x1800195dc  mov     eax, ebx
0x1800195de  mov     rcx, [rbp+0B0h+var_50]
0x1800195e2  xor     rcx, rsp; StackCookie
0x1800195e5  call    __security_check_cookie
0x1800195ea  lea     r11, [rsp+1B0h+var_30]
0x1800195f2  mov     rbx, [r11+58h]
0x1800195f6  movaps  xmm6, xmmword ptr [r11-10h]
0x1800195fb  mov     rsp, r11
0x1800195fe  pop     r15
0x180019600  pop     r14
0x180019602  pop     r13
0x180019604  pop     r12
0x180019606  pop     rdi
0x180019607  pop     rsi
0x180019608  pop     rbp
0x180019609  retn
```
