# BLB_SECURITY_HELPER::CreateSD(ushort const *,ushort const *,uchar,void * *)

- ea: `0x1400efa40`
- end: `0x1400f0076`
- name: `?CreateSD@BLB_SECURITY_HELPER@@SAJPEBG0EPEAPEAX@Z`
- size: `1590`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int8, void **)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1400f046c`

## callees

- `0x140007ad3`
- `0x14000bb24`
- `0x14000bb4c`
- `0x14000cbcc`
- `0x14001358c`
- `0x140014260`
- `0x140014384`
- `0x14005f490`
- `0x14006795c`
- `0x140068738`
- `0x140087bf4`
- `0x1400889f0`
- `0x1400940f0`
- `0x140094600`
- `0x140094ff8`
- `0x1400efa40`
- `0x140134cd2`
- `0x140134d20`

## import_xrefs

- `ADVAPI32!GetLengthSid` at `0x1400efd90`
- `ADVAPI32!GetLengthSid` at `0x1400efd90`
- `ADVAPI32!IsValidSid` at `0x1400efd9b`
- `ADVAPI32!IsValidSid` at `0x1400efd9b`
- `ADVAPI32!CopySid` at `0x1400efdd7`
- `ADVAPI32!CopySid` at `0x1400efdd7`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x1400eff73`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x1400eff73`
- `ADVAPI32!ConvertSidToStringSidW` at `0x1400efe49`
- `ADVAPI32!ConvertSidToStringSidW` at `0x1400efe49`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400eff07`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400eff07`
- `KERNEL32!LocalFree` at `0x1400efb1d`
- `KERNEL32!LocalFree` at `0x1400efb36`
- `KERNEL32!LocalFree` at `0x1400efb1d`
- `KERNEL32!LocalFree` at `0x1400efb36`
- `KERNEL32!GetLastError` at `0x1400efde3`
- `KERNEL32!GetLastError` at `0x1400efe53`
- `KERNEL32!GetLastError` at `0x1400eff11`
- `KERNEL32!GetLastError` at `0x1400efde3`
- `KERNEL32!GetLastError` at `0x1400efe53`
- `KERNEL32!GetLastError` at `0x1400eff11`
- `ole32!CoTaskMemAlloc` at `0x1400efeaa`
- `ole32!CoTaskMemAlloc` at `0x1400efeaa`
- `ole32!CoTaskMemFree` at `0x1400efb4d`
- `ole32!CoTaskMemFree` at `0x1400efb5b`
- `ole32!CoTaskMemFree` at `0x1400efb69`
- `ole32!CoTaskMemFree` at `0x1400efb77`
- `ole32!CoTaskMemFree` at `0x1400f0059`
- `ole32!CoTaskMemFree` at `0x1400f006b`
- `ole32!CoTaskMemFree` at `0x1400efb4d`
- `ole32!CoTaskMemFree` at `0x1400efb5b`
- `ole32!CoTaskMemFree` at `0x1400efb69`
- `ole32!CoTaskMemFree` at `0x1400efb77`
- `ole32!CoTaskMemFree` at `0x1400f0059`
- `ole32!CoTaskMemFree` at `0x1400f006b`

## pseudocode

```c
__int64 __fastcall BLB_SECURITY_HELPER::CreateSD(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        char a3,
        void **a4)
{
  __int64 v4; // r15
  PSID v7; // r13
  WCHAR *v8; // r12
  unsigned __int16 *v9; // rsi
  signed int MachineNameFromSharePath; // edi
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  void *v13; // rbx
  void *v14; // r14
  unsigned __int8 v16; // si
  int v17; // eax
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  HLOCAL lpSecurityDescriptor; // rcx
  ATL::CSid *v21; // rax
  struct _SID *PSID; // rsi
  DWORD LengthSid; // ebx
  int v24; // eax
  signed int v25; // eax
  _QWORD *v26; // rcx
  __int64 v27; // rdx
  unsigned __int16 *v28; // r14
  signed int v29; // eax
  __int64 v30; // rax
  unsigned __int64 v31; // rbx
  SIZE_T v32; // rdi
  unsigned __int16 *v33; // rax
  signed int LastError; // eax
  int v35; // eax
  __int64 v36; // rax
  __int64 v37; // rcx
  WCHAR *i; // rax
  __int64 v39; // rcx
  unsigned __int16 *j; // rax
  unsigned __int8 v41[8]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v42; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v43; // [rsp+48h] [rbp-B8h]
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  ULONG SecurityDescriptorSize; // [rsp+58h] [rbp-A8h] BYREF
  HLOCAL SecurityDescriptor; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR lpAccountName; // [rsp+68h] [rbp-98h] BYREF
  HLOCAL hMem; // [rsp+70h] [rbp-90h] BYREF
  void *v49; // [rsp+78h] [rbp-88h] BYREF
  PSID pDestinationSid; // [rsp+80h] [rbp-80h] BYREF
  void **v51; // [rsp+88h] [rbp-78h]
  struct _SECURITY_ATTRIBUTES v52; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v53[128]; // [rsp+B0h] [rbp-50h] BYREF

  v51 = a4;
  SecurityDescriptor = 0;
  v4 = -1;
  v49 = 0;
  SecurityDescriptorSize = 0;
  pDestinationSid = 0;
  v7 = 0;
  hMem = 0;
  v8 = 0;
  v43 = 0;
  v9 = 0;
  pv = 0;
  lpAccountName = 0;
  v42 = 0;
  if ( !a3 )
  {
    if ( a2 )
    {
      MachineNameFromSharePath = -2147024809;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)MachineNameFromSharePath;
      }
      v12 = 41;
      goto LABEL_7;
    }
    v21 = (ATL::CSid *)ATL::Sids::System(v53);
    PSID = ATL::CSid::_GetPSID(v21);
    ATL::CSid::~CSid((ATL::CSid *)v53);
    LengthSid = GetLengthSid(PSID);
    if ( !IsValidSid(PSID) )
    {
      v9 = v42;
      MachineNameFromSharePath = -2147023559;
      goto LABEL_8;
    }
    v24 = BlbutilMemalloc(&pDestinationSid, 1u, LengthSid);
    v7 = pDestinationSid;
    MachineNameFromSharePath = v24;
    if ( v24 < 0 )
      goto LABEL_62;
    if ( CopySid(LengthSid, pDestinationSid, PSID) )
    {
      if ( ConvertSidToStringSidW(v7, (LPWSTR *)&hMem) )
      {
        v30 = -1;
        do
          ++v30;
        while ( *((_WORD *)hMem + v30) );
        v31 = v30 + 59;
        v32 = 2 * (v30 + 59);
        v33 = (unsigned __int16 *)CoTaskMemAlloc(v32);
        v43 = v33;
        v28 = v33;
        if ( v33 )
        {
          memset_0(v33, 0, v32);
          MachineNameFromSharePath = StringCchPrintfW(
                                       v28,
                                       v31,
                                       L"O:%wsD:PAR(A;OICI;FA;;;BA)(A;OICI;FA;;;BO)(A;OICI;FA;;;CO)",
                                       hMem);
          if ( MachineNameFromSharePath >= 0 )
          {
            if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
                   v28,
                   1u,
                   &SecurityDescriptor,
                   &SecurityDescriptorSize) )
            {
              lpSecurityDescriptor = SecurityDescriptor;
              goto LABEL_84;
            }
            LastError = GetLastError();
            MachineNameFromSharePath = LastError;
            if ( LastError > 0 )
              MachineNameFromSharePath = (unsigned __int16)LastError | 0x80070000;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_69eba809750e303923687b65610740a4_Traceguids);
            }
          }
        }
        else
        {
          MachineNameFromSharePath = -2147024882;
        }
LABEL_63:
        v9 = v42;
        v13 = 0;
LABEL_102:
        if ( v7 )
          CoTaskMemFree(v7);
        if ( v28 )
          CoTaskMemFree(v28);
        goto LABEL_9;
      }
      v29 = GetLastError();
      MachineNameFromSharePath = v29;
      if ( v29 > 0 )
        MachineNameFromSharePath = (unsigned __int16)v29 | 0x80070000;
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_62:
        v28 = 0;
        goto LABEL_63;
      }
      v27 = 43;
    }
    else
    {
      v25 = GetLastError();
      MachineNameFromSharePath = v25;
      if ( v25 > 0 )
        MachineNameFromSharePath = (unsigned __int16)v25 | 0x80070000;
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_62;
      }
      v27 = 42;
    }
    WPP_SF_d(v26[2], v27, WPP_69eba809750e303923687b65610740a4_Traceguids);
    goto LABEL_62;
  }
  if ( a2 )
  {
    v41[0] = 1;
    memset(&v52, 0, sizeof(v52));
    MachineNameFromSharePath = BlbutilGetMachineNameFromSharePath(a1, (unsigned __int16 **)&pv);
    if ( MachineNameFromSharePath < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          45,
          (unsigned int)WPP_69eba809750e303923687b65610740a4_Traceguids,
          (_DWORD)a1,
          MachineNameFromSharePath);
      }
      goto LABEL_8;
    }
    MachineNameFromSharePath = BlbutilIsDomainUser(a2, (LPCWSTR)pv, v41);
    if ( MachineNameFromSharePath < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v14 = pv;
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_SSD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            46,
            (unsigned int)WPP_69eba809750e303923687b65610740a4_Traceguids,
            (_DWORD)a2,
            (__int64)pv,
            MachineNameFromSharePath);
        v13 = 0;
        goto LABEL_10;
      }
      goto LABEL_8;
    }
    v16 = v41[0];
    if ( v41[0] )
      v17 = BlbutilDuplicateString(a2, (unsigned __int16 **)&lpAccountName, 0);
    else
      v17 = BlbutilSplitUsername(a2, (unsigned __int16 **)&lpAccountName, &v42);
    v8 = (WCHAR *)lpAccountName;
    MachineNameFromSharePath = v17;
    if ( v17 < 0 )
      goto LABEL_91;
    MachineNameFromSharePath = BlbutilCreateSecurityDescriptorForNetworkShare(
                                 a1,
                                 lpAccountName,
                                 v16,
                                 &v52,
                                 &SecurityDescriptorSize);
    if ( MachineNameFromSharePath < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_91;
      }
      v19 = 47;
      goto LABEL_44;
    }
    lpSecurityDescriptor = v52.lpSecurityDescriptor;
    SecurityDescriptor = v52.lpSecurityDescriptor;
LABEL_84:
    if ( IsValidSecurityDescriptor(lpSecurityDescriptor) )
    {
      v35 = BlbutilMemalloc(&v49, 1u, SecurityDescriptorSize);
      v13 = v49;
      MachineNameFromSharePath = v35;
      if ( v35 < 0 )
        goto LABEL_92;
      memcpy_0(v49, SecurityDescriptor, SecurityDescriptorSize);
      *v51 = v13;
LABEL_91:
      v13 = 0;
LABEL_92:
      if ( v8 )
      {
        v36 = -1;
        do
          ++v36;
        while ( v8[v36] );
        v37 = 2 * v36;
        for ( i = v8; v37; --v37 )
        {
          *(_BYTE *)i = 0;
          i = (WCHAR *)((char *)i + 1);
        }
      }
      v9 = v42;
      if ( v42 )
      {
        do
          ++v4;
        while ( v42[v4] );
        v39 = 2 * v4;
        for ( j = v42; v39; --v39 )
        {
          *(_BYTE *)j = 0;
          j = (unsigned __int16 *)((char *)j + 1);
        }
      }
      v28 = v43;
      goto LABEL_102;
    }
    MachineNameFromSharePath = -2147023558;
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_91;
    }
    v19 = 48;
LABEL_44:
    WPP_SF_d(v18[2], v19, WPP_69eba809750e303923687b65610740a4_Traceguids);
    goto LABEL_91;
  }
  MachineNameFromSharePath = -2147024809;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    return (unsigned int)MachineNameFromSharePath;
  }
  v12 = 40;
LABEL_7:
  WPP_SF_(v11[2], v12, WPP_69eba809750e303923687b65610740a4_Traceguids);
LABEL_8:
  v13 = 0;
LABEL_9:
  v14 = pv;
LABEL_10:
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  if ( SecurityDescriptor )
  {
    LocalFree(SecurityDescriptor);
    SecurityDescriptor = 0;
  }
  if ( v8 )
    CoTaskMemFree(v8);
  if ( v9 )
    CoTaskMemFree(v9);
  if ( v14 )
    CoTaskMemFree(v14);
  if ( v13 )
    CoTaskMemFree(v13);
  return (unsigned int)MachineNameFromSharePath;
}

```

## disassembly

```asm
0x1400efa40  mov     [rsp-8+arg_10], rbx
0x1400efa45  push    rbp
0x1400efa46  push    rsi
0x1400efa47  push    rdi
0x1400efa48  push    r12
0x1400efa4a  push    r13
0x1400efa4c  push    r14
0x1400efa4e  push    r15
0x1400efa50  lea     rbp, [rsp-40h]
0x1400efa55  sub     rsp, 140h
0x1400efa5c  mov     rax, cs:__security_cookie
0x1400efa63  xor     rax, rsp
0x1400efa66  mov     [rbp+70h+var_40], rax
0x1400efa6a  xor     edi, edi
0x1400efa6c  mov     [rbp+70h+var_E8], r9
0x1400efa70  mov     eax, edi
0x1400efa72  mov     [rsp+170h+SecurityDescriptor], rdi
0x1400efa77  or      r15, 0FFFFFFFFFFFFFFFFh
0x1400efa7b  mov     [rsp+170h+var_140], rax
0x1400efa80  mov     [rsp+170h+var_F8], rax
0x1400efa85  mov     rbx, rdx
0x1400efa88  mov     [rsp+170h+SecurityDescriptorSize], edi
0x1400efa8c  mov     r14, rcx
0x1400efa8f  mov     [rbp+70h+pDestinationSid], rdi
0x1400efa93  mov     r13d, edi
0x1400efa96  mov     [rsp+170h+hMem], rdi
0x1400efa9b  mov     r12d, edi
0x1400efa9e  mov     [rsp+170h+var_128], rdi
0x1400efaa3  mov     esi, edi
0x1400efaa5  mov     [rsp+170h+pv], rdi
0x1400efaaa  mov     [rsp+170h+lpAccountName], rdi
0x1400efaaf  mov     [rsp+170h+var_130], rdi
0x1400efab4  test    r8b, r8b
0x1400efab7  jz      loc_1400EFD31
0x1400efabd  test    rdx, rdx
0x1400efac0  jnz     loc_1400EFBA6
0x1400efac6  mov     edi, 80070057h
0x1400efacb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400efad2  lea     rax, WPP_GLOBAL_Control
0x1400efad9  cmp     rcx, rax
0x1400efadc  jz      loc_1400EFB7D
0x1400efae2  test    byte ptr [rcx+1Ch], 1
0x1400efae6  jz      loc_1400EFB7D
0x1400efaec  cmp     byte ptr [rcx+19h], 2
0x1400efaf0  jb      loc_1400EFB7D
0x1400efaf6  lea     edx, [rbx+28h]
0x1400efaf9  mov     rcx, [rcx+10h]
0x1400efafd  lea     r8, WPP_69eba809750e303923687b65610740a4_Traceguids
0x1400efb04  call    WPP_SF_
0x1400efb09  mov     rbx, [rsp+170h+var_140]
0x1400efb0e  mov     r14, [rsp+170h+pv]
0x1400efb13  mov     rcx, [rsp+170h+hMem]; hMem
0x1400efb18  test    rcx, rcx
0x1400efb1b  jz      short loc_1400EFB2C
0x1400efb1d  call    cs:__imp_LocalFree
0x1400efb23  mov     [rsp+170h+hMem], 0
0x1400efb2c  mov     rcx, [rsp+170h+SecurityDescriptor]; hMem
0x1400efb31  test    rcx, rcx
0x1400efb34  jz      short loc_1400EFB45
0x1400efb36  call    cs:__imp_LocalFree
0x1400efb3c  mov     [rsp+170h+SecurityDescriptor], 0
0x1400efb45  test    r12, r12
0x1400efb48  jz      short loc_1400EFB53
0x1400efb4a  mov     rcx, r12; pv
0x1400efb4d  call    cs:__imp_CoTaskMemFree
0x1400efb53  test    rsi, rsi
0x1400efb56  jz      short loc_1400EFB61
0x1400efb58  mov     rcx, rsi; pv
0x1400efb5b  call    cs:__imp_CoTaskMemFree
0x1400efb61  test    r14, r14
0x1400efb64  jz      short loc_1400EFB6F
0x1400efb66  mov     rcx, r14; pv
0x1400efb69  call    cs:__imp_CoTaskMemFree
0x1400efb6f  test    rbx, rbx
0x1400efb72  jz      short loc_1400EFB7D
0x1400efb74  mov     rcx, rbx; pv
0x1400efb77  call    cs:__imp_CoTaskMemFree
0x1400efb7d  mov     eax, edi
0x1400efb7f  mov     rcx, [rbp+70h+var_40]
0x1400efb83  xor     rcx, rsp; StackCookie
0x1400efb86  call    __security_check_cookie
0x1400efb8b  mov     rbx, [rsp+170h+arg_10]
0x1400efb93  add     rsp, 140h
0x1400efb9a  pop     r15
0x1400efb9c  pop     r14
0x1400efb9e  pop     r13
0x1400efba0  pop     r12
0x1400efba2  pop     rdi
0x1400efba3  pop     rsi
0x1400efba4  pop     rbp
0x1400efba5  retn
0x1400efba6  xorps   xmm0, xmm0
0x1400efba9  mov     [rsp+170h+var_138], 1
0x1400efbae  lea     rdx, [rsp+170h+pv]; unsigned __int16 **
0x1400efbb3  mov     qword ptr [rbp+70h+var_E0.bInheritHandle], rax
0x1400efbb7  movups  xmmword ptr [rbp+70h+var_E0.nLength], xmm0
0x1400efbbb  call    ?BlbutilGetMachineNameFromSharePath@@YAJPEBGPEAPEAG@Z; BlbutilGetMachineNameFromSharePath(ushort const *,ushort * *)
0x1400efbc0  mov     edi, eax
0x1400efbc2  test    eax, eax
0x1400efbc4  jns     short loc_1400EFC12
0x1400efbc6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400efbcd  lea     rax, WPP_GLOBAL_Control
0x1400efbd4  cmp     rcx, rax
0x1400efbd7  jz      loc_1400EFB09
0x1400efbdd  test    byte ptr [rcx+1Ch], 1
0x1400efbe1  jz      loc_1400EFB09
0x1400efbe7  cmp     byte ptr [rcx+19h], 2
0x1400efbeb  jb      loc_1400EFB09
0x1400efbf1  mov     rcx, [rcx+10h]
0x1400efbf5  lea     r8, WPP_69eba809750e303923687b65610740a4_Traceguids
0x1400efbfc  mov     edx, 2Dh ; '-'
0x1400efc01  mov     dword ptr [rsp+170h+var_150], edi
0x1400efc05  mov     r9, r14
0x1400efc08  call    WPP_SF_Sd
0x1400efc0d  jmp     loc_1400EFB09
0x1400efc12  mov     rdx, [rsp+170h+pv]; lpSystemName
0x1400efc17  lea     r8, [rsp+170h+var_138]; unsigned __int8 *
0x1400efc1c  mov     rcx, rbx; lpAccountName
0x1400efc1f  call    ?BlbutilIsDomainUser@@YAJPEBG0PEAE@Z; BlbutilIsDomainUser(ushort const *,ushort const *,uchar *)
0x1400efc24  mov     edi, eax
0x1400efc26  test    eax, eax
0x1400efc28  jns     short loc_1400EFC81
0x1400efc2a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400efc31  lea     rax, WPP_GLOBAL_Control
0x1400efc38  cmp     rcx, rax
0x1400efc3b  jz      loc_1400EFB09
0x1400efc41  test    byte ptr [rcx+1Ch], 1
0x1400efc45  jz      loc_1400EFB09
0x1400efc4b  cmp     byte ptr [rcx+19h], 2
0x1400efc4f  mov     r14, [rsp+170h+pv]
0x1400efc54  jb      short loc_1400EFC77
0x1400efc56  mov     rcx, [rcx+10h]
0x1400efc5a  lea     r8, WPP_69eba809750e303923687b65610740a4_Traceguids
0x1400efc61  mov     edx, 2Eh ; '.'
0x1400efc66  mov     [rsp+170h+var_148], edi
0x1400efc6a  mov     r9, rbx
0x1400efc6d  mov     [rsp+170h+var_150], r14
0x1400efc72  call    WPP_SF_SSD
0x1400efc77  mov     rbx, [rsp+170h+var_140]
0x1400efc7c  jmp     loc_1400EFB13
0x1400efc81  mov     sil, [rsp+170h+var_138]
0x1400efc86  lea     rdx, [rsp+170h+lpAccountName]; unsigned __int16 **
0x1400efc8b  mov     rcx, rbx; unsigned __int16 *
0x1400efc8e  test    sil, sil
0x1400efc91  jnz     short loc_1400EFCA6
0x1400efc93  lea     r8, [rsp+170h+var_130]; unsigned __int16 **
0x1400efc98  call    ?BlbutilSplitUsername@@YAJPEBGPEAPEAG1@Z; BlbutilSplitUsername(ushort const *,ushort * *,ushort * *)
0x1400efc9d  jmp     short loc_1400EFCAE
0x1400efc9f  xor     esi, esi
0x1400efca1  jmp     loc_1400EFFEE
0x1400efca6  xor     r8d, r8d; unsigned __int64
0x1400efca9  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x1400efcae  mov     r12, [rsp+170h+lpAccountName]
0x1400efcb3  mov     edi, eax
0x1400efcb5  test    eax, eax
0x1400efcb7  js      short loc_1400EFC9F
0x1400efcb9  lea     rax, [rsp+170h+SecurityDescriptorSize]
0x1400efcbe  mov     r8b, sil; unsigned __int8
0x1400efcc1  lea     r9, [rbp+70h+var_E0]; struct _SECURITY_ATTRIBUTES *
0x1400efcc5  mov     [rsp+170h+var_150], rax; unsigned int *
0x1400efcca  mov     rdx, r12; lpAccountName
0x1400efccd  mov     rcx, r14; unsigned __int16 *
0x1400efcd0  call    ?BlbutilCreateSecurityDescriptorForNetworkShare@@YAJPEBG0EPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; BlbutilCreateSecurityDescriptorForNetworkShare(ushort const *,ushort const *,uchar,_SECURITY_ATTRIBUTES *,ulong *)
0x1400efcd5  xor     esi, esi
0x1400efcd7  mov     edi, eax
0x1400efcd9  test    eax, eax
0x1400efcdb  jns     short loc_1400EFD23
0x1400efcdd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400efce4  lea     rax, WPP_GLOBAL_Control
0x1400efceb  cmp     rcx, rax
0x1400efcee  jz      loc_1400EFFEE
0x1400efcf4  test    byte ptr [rcx+1Ch], 1
0x1400efcf8  jz      loc_1400EFFEE
0x1400efcfe  cmp     byte ptr [rcx+19h], 2
0x1400efd02  jb      loc_1400EFFEE
0x1400efd08  lea     edx, [rsi+2Fh]
0x1400efd0b  mov     r9d, edi
0x1400efd0e  mov     rcx, [rcx+10h]
0x1400efd12  lea     r8, WPP_69eba809750e303923687b65610740a4_Traceguids
0x1400efd19  call    WPP_SF_d
0x1400efd1e  jmp     loc_1400EFFEE
0x1400efd23  mov     rcx, [rbp+70h+var_E0.lpSecurityDescriptor]
0x1400efd27  mov     [rsp+170h+SecurityDescriptor], rcx
0x1400efd2c  jmp     loc_1400EFF73
0x1400efd31  test    rbx, rbx
0x1400efd34  jz      short loc_1400EFD70
0x1400efd36  mov     edi, 80070057h
0x1400efd3b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400efd42  lea     rax, WPP_GLOBAL_Control
0x1400efd49  cmp     rcx, rax
0x1400efd4c  jz      loc_1400EFB7D
0x1400efd52  test    byte ptr [rcx+1Ch], 1
0x1400efd56  jz      loc_1400EFB7D
0x1400efd5c  cmp     byte ptr [rcx+19h], 2
0x1400efd60  jb      loc_1400EFB7D
0x1400efd66  mov     edx, 29h ; ')'
0x1400efd6b  jmp     loc_1400EFAF9
0x1400efd70  lea     rcx, [rbp+70h+var_C0]
0x1400efd74  call    ?System@Sids@ATL@@YA?AVCSid@2@XZ; ATL::Sids::System(void)
0x1400efd79  mov     rcx, rax; this
0x1400efd7c  call    ?_GetPSID@CSid@ATL@@AEBAPEAU_SID@@XZ; ATL::CSid::_GetPSID(void)
0x1400efd81  lea     rcx, [rbp+70h+var_C0]; this
0x1400efd85  mov     rsi, rax
0x1400efd88  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x1400efd8d  mov     rcx, rsi; pSid
0x1400efd90  call    cs:__imp_GetLengthSid
0x1400efd96  mov     rcx, rsi; pSid
0x1400efd99  mov     ebx, eax
0x1400efd9b  call    cs:__imp_IsValidSid
0x1400efda1  test    eax, eax
0x1400efda3  jnz     short loc_1400EFDB4
0x1400efda5  mov     rsi, [rsp+170h+var_130]
0x1400efdaa  mov     edi, 80070539h
0x1400efdaf  jmp     loc_1400EFB09
0x1400efdb4  mov     r8d, ebx; unsigned int
0x1400efdb7  lea     rcx, [rbp+70h+pDestinationSid]; void **
0x1400efdbb  mov     edx, 1; unsigned int
0x1400efdc0  call    ?BlbutilMemalloc@@YAJPEAPEAXKK@Z; BlbutilMemalloc(void * *,ulong,ulong)
0x1400efdc5  mov     r13, [rbp+70h+pDestinationSid]
0x1400efdc9  mov     edi, eax
0x1400efdcb  test    eax, eax
0x1400efdcd  js      short loc_1400EFE2F
0x1400efdcf  mov     r8, rsi; pSourceSid
0x1400efdd2  mov     rdx, r13; pDestinationSid
0x1400efdd5  mov     ecx, ebx; nDestinationSidLength
0x1400efdd7  call    cs:__imp_CopySid
0x1400efddd  xor     esi, esi
0x1400efddf  test    eax, eax
0x1400efde1  jnz     short loc_1400EFE41
0x1400efde3  call    cs:__imp_GetLastError
0x1400efde9  mov     edi, eax
0x1400efdeb  test    eax, eax
0x1400efded  jle     short loc_1400EFDF8
0x1400efdef  movzx   edi, ax
0x1400efdf2  or      edi, 80070000h
0x1400efdf8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400efdff  lea     rax, WPP_GLOBAL_Control
0x1400efe06  cmp     rcx, rax
0x1400efe09  jz      short loc_1400EFE2F
0x1400efe0b  test    byte ptr [rcx+1Ch], 1
0x1400efe0f  jz      short loc_1400EFE2F
0x1400efe11  cmp     byte ptr [rcx+19h], 2
0x1400efe15  jb      short loc_1400EFE2F
0x1400efe17  mov     edx, 2Ah ; '*'
0x1400efe1c  mov     rcx, [rcx+10h]
0x1400efe20  lea     r8, WPP_69eba809750e303923687b65610740a4_Traceguids
0x1400efe27  mov     r9d, edi
0x1400efe2a  call    WPP_SF_d
0x1400efe2f  mov     r14, r12
0x1400efe32  mov     rsi, [rsp+170h+var_130]
0x1400efe37  mov     rbx, [rsp+170h+var_140]
0x1400efe3c  jmp     loc_1400F0051
0x1400efe41  lea     rdx, [rsp+170h+hMem]; StringSid
0x1400efe46  mov     rcx, r13; Sid
0x1400efe49  call    cs:__imp_ConvertSidToStringSidW
0x1400efe4f  test    eax, eax
0x1400efe51  jnz     short loc_1400EFE8E
0x1400efe53  call    cs:__imp_GetLastError
0x1400efe59  mov     edi, eax
0x1400efe5b  test    eax, eax
0x1400efe5d  jle     short loc_1400EFE68
0x1400efe5f  movzx   edi, ax
0x1400efe62  or      edi, 80070000h
0x1400efe68  mov     rcx, cs:WPP_GLOBAL_Control
0x1400efe6f  lea     rax, WPP_GLOBAL_Control
0x1400efe76  cmp     rcx, rax
0x1400efe79  jz      short loc_1400EFE2F
0x1400efe7b  test    byte ptr [rcx+1Ch], 1
0x1400efe7f  jz      short loc_1400EFE2F
0x1400efe81  cmp     byte ptr [rcx+19h], 2
0x1400efe85  jb      short loc_1400EFE2F
0x1400efe87  mov     edx, 2Bh ; '+'
0x1400efe8c  jmp     short loc_1400EFE1C
0x1400efe8e  mov     rcx, [rsp+170h+hMem]
0x1400efe93  mov     rax, r15
0x1400efe96  inc     rax
0x1400efe99  cmp     [rcx+rax*2], si
0x1400efe9d  jnz     short loc_1400EFE96
0x1400efe9f  lea     rbx, [rax+3Bh]
0x1400efea3  lea     rdi, [rbx+rbx]
0x1400efea7  mov     rcx, rdi; cb
0x1400efeaa  call    cs:__imp_CoTaskMemAlloc
0x1400efeb0  mov     [rsp+170h+var_128], rax
0x1400efeb5  mov     r14, rax
0x1400efeb8  test    rax, rax
0x1400efebb  jnz     short loc_1400EFEC7
0x1400efebd  mov     edi, 8007000Eh
0x1400efec2  jmp     loc_1400EFE32
0x1400efec7  mov     r8, rdi; Size
0x1400efeca  xor     edx, edx; Val
0x1400efecc  mov     rcx, r14; void *
0x1400efecf  call    memset_0
0x1400efed4  mov     r9, [rsp+170h+hMem]
0x1400efed9  lea     r8, aOWsdParAOiciFa; "O:%wsD:PAR(A;OICI;FA;;;BA)(A;OICI;FA;;;"...
0x1400efee0  mov     rdx, rbx; unsigned __int64
0x1400efee3  mov     rcx, r14; unsigned __int16 *
0x1400efee6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400efeeb  mov     edi, eax
0x1400efeed  test    eax, eax
0x1400efeef  js      loc_1400EFE32
  ... truncated ...
```
