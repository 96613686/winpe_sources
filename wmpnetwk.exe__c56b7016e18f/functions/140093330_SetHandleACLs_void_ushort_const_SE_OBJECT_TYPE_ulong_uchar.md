# SetHandleACLs(void *,ushort const *,_SE_OBJECT_TYPE,ulong,uchar)

- ea: `0x140093330`
- end: `0x14009391b`
- name: `?SetHandleACLs@@YAHPEAXPEBGW4_SE_OBJECT_TYPE@@KE@Z`
- size: `1515`
- prototype: `__int64 __fastcall(HKEY, LPCWSTR StringSid, __int32, unsigned int, unsigned __int8)`
- caller_count: `3`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140044548`
- `0x1400448e0`
- `0x1400926e0`

## callees

- `0x14003f17c`
- `0x140046020`
- `0x14004639c`
- `0x140047798`
- `0x14004b074`
- `0x14004ddd0`
- `0x14005ea04`
- `0x140091fd8`
- `0x1400920b4`
- `0x140092348`
- `0x1400923dc`
- `0x140093330`
- `0x140093b94`
- `0x140093bf8`
- `0x140093edc`
- `0x1400940c4`
- `0x140094134`
- `0x1400941b4`

## import_xrefs

- `ADVAPI32!GetSecurityDescriptorDacl` at `0x1400935a3`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x1400935a3`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x14009373d`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x14009373d`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x14009353c`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x14009353c`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x1400936cd`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x1400936cd`
- `ADVAPI32!RegSetKeySecurity` at `0x140093806`
- `ADVAPI32!RegSetKeySecurity` at `0x140093806`
- `ADVAPI32!SetSecurityDescriptorControl` at `0x1400937a6`
- `ADVAPI32!SetSecurityDescriptorControl` at `0x1400937a6`
- `KERNEL32!GetCurrentProcess` at `0x14009342f`
- `KERNEL32!GetCurrentProcess` at `0x14009342f`
- `KERNEL32!IsWow64Process` at `0x14009343c`
- `KERNEL32!IsWow64Process` at `0x14009343c`
- `KERNEL32!RegGetKeySecurity` at `0x14009346c`
- `KERNEL32!RegGetKeySecurity` at `0x1400934cf`
- `KERNEL32!RegGetKeySecurity` at `0x14009346c`
- `KERNEL32!RegGetKeySecurity` at `0x1400934cf`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 __fastcall SetHandleACLs(HKEY a1, LPCWSTR StringSid, __int32 a3, unsigned int a4, unsigned __int8 a5)
{
  unsigned int v5; // edi
  PVOID *v9; // r10
  unsigned int SecurityDescriptorControl; // ebx
  HANDLE CurrentProcess; // rax
  int v12; // r13d
  void *v13; // rdi
  LSTATUS KeySecurity; // esi
  unsigned int v15; // esi
  __int64 v16; // r8
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rdx
  __int64 v20; // r8
  bool Dacl; // al
  unsigned int v22; // r9d
  BOOL v23; // eax
  struct _ACL *PACL; // rax
  const struct _ACL *v25; // rax
  __int64 v26; // rdx
  __int64 v27; // r8
  BOOL v28; // eax
  unsigned int v29; // eax
  __int64 v30; // rdx
  __int64 v31; // r8
  unsigned int v32; // edi
  unsigned int v33; // ecx
  bool v34; // al
  DWORD cbSecurityDescriptor; // [rsp+40h] [rbp-61h] BYREF
  WINBOOL bDaclPresent; // [rsp+44h] [rbp-5Dh] BYREF
  DWORD dwRevision; // [rsp+48h] [rbp-59h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+4Ch] [rbp-55h] BYREF
  int v40; // [rsp+50h] [rbp-51h] BYREF
  PACL pDacl; // [rsp+58h] [rbp-49h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+60h] [rbp-41h] BYREF
  __int64 v43; // [rsp+80h] [rbp-21h]
  _QWORD v44[2]; // [rsp+88h] [rbp-19h] BYREF
  char v45; // [rsp+98h] [rbp-9h]
  int v46; // [rsp+9Ch] [rbp-5h]
  __int64 v47; // [rsp+A0h] [rbp-1h]
  __int64 v48; // [rsp+A8h] [rbp+7h]
  __int64 v49; // [rsp+B0h] [rbp+Fh]
  int v50; // [rsp+B8h] [rbp+17h]
  WINBOOL Wow64Process; // [rsp+108h] [rbp+67h] BYREF
  unsigned int v52; // [rsp+118h] [rbp+77h]

  v52 = a4;
  v5 = a4;
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qSDLD(*((_QWORD *)WPP_GLOBAL_Control + 2), (_DWORD)StringSid, a3, (_DWORD)a1, (__int64)StringSid, a3, a4, a5);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  v40 = 0;
  v44[1] = 0;
  v45 = 0;
  v46 = 2;
  v44[0] = &ATL::CDacl::`vftable';
  v47 = 0;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  dwRevision = 0;
  if ( StringSid )
  {
    if ( a3 == 4
      && (Wow64Process = 0, CurrentProcess = GetCurrentProcess(), IsWow64Process(CurrentProcess, &Wow64Process))
      && Wow64Process )
    {
      v12 = 1;
      SecurityDescriptorControl = 0;
      v13 = 0;
      cbSecurityDescriptor = 0;
      KeySecurity = RegGetKeySecurity(a1, 4u, 0, &cbSecurityDescriptor);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          37,
          &WPP_92b3b3424e563441648ef2499742b7fb_Traceguids,
          a1,
          KeySecurity);
      }
      if ( KeySecurity == 122 )
      {
        v13 = operator new[](cbSecurityDescriptor);
        v15 = RegGetKeySecurity(a1, 4u, v13, &cbSecurityDescriptor);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v16 = *((unsigned __int8 *)WPP_GLOBAL_Control + 25);
          v17 = 5;
          if ( v15 )
            v17 = 2;
          if ( (unsigned int)v16 >= (unsigned int)v17 )
            WPP_SF_DqqD(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, v16, v15, a1, v13, cbSecurityDescriptor);
        }
        if ( !v15 )
        {
          LOWORD(Wow64Process) = 0;
          SecurityDescriptorControl = GetSecurityDescriptorControl(
                                        v13,
                                        (PSECURITY_DESCRIPTOR_CONTROL)&Wow64Process,
                                        &dwRevision);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_qlll(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              (unsigned __int16)Wow64Process,
              v18,
              v13,
              (unsigned __int16)Wow64Process,
              dwRevision,
              SecurityDescriptorControl);
          }
          if ( SecurityDescriptorControl )
          {
            bDaclPresent = 0;
            pDacl = 0;
            bDaclDefaulted = 0;
            SecurityDescriptorControl = GetSecurityDescriptorDacl(v13, &bDaclPresent, &pDacl, &bDaclDefaulted);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              WPP_SF_qlqll(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v19,
                v20,
                v13,
                bDaclPresent,
                pDacl,
                bDaclDefaulted,
                SecurityDescriptorControl);
            }
            if ( SecurityDescriptorControl )
            {
              if ( bDaclPresent )
              {
                ATL::CDacl::operator=((ATL::CDacl *)v44, pDacl);
                SecurityDescriptorControl = 1;
              }
              else
              {
                SecurityDescriptorControl = 0;
              }
            }
          }
        }
      }
      operator delete(v13);
      v5 = v52;
    }
    else
    {
      v12 = 0;
      Dacl = ATL::AtlGetDacl(a1, (enum _SE_OBJECT_TYPE)a3, (struct ATL::CDacl *)v44);
      SecurityDescriptorControl = Dacl;
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_45;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_92b3b3424e563441648ef2499742b7fb_Traceguids, Dacl);
    }
    v9 = (PVOID *)WPP_GLOBAL_Control;
LABEL_45:
    if ( SecurityDescriptorControl != 1 )
      goto LABEL_77;
    SecurityDescriptorControl = AddAccessSidToDacl((struct ATL::CDacl *)v44, StringSid, v5, a5, &v40);
    if ( SecurityDescriptorControl != 1 || v40 != 1 )
    {
      v9 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_77;
    }
    if ( v12 )
    {
      memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
      v43 = 0;
      v23 = InitializeSecurityDescriptor(pSecurityDescriptor, 1u);
      SecurityDescriptorControl = v23;
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          43,
          &WPP_92b3b3424e563441648ef2499742b7fb_Traceguids,
          pSecurityDescriptor,
          v23);
        v9 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( SecurityDescriptorControl )
      {
        PACL = (struct _ACL *)ATL::CAcl::GetPACL((ATL::CAcl *)v44);
        SecurityDescriptorControl = SetSecurityDescriptorDacl(pSecurityDescriptor, 1, PACL, 0);
        v9 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v25 = ATL::CAcl::GetPACL((ATL::CAcl *)v44);
          WPP_SF_qql(*((_QWORD *)WPP_GLOBAL_Control + 2), v26, v27, pSecurityDescriptor, v25, SecurityDescriptorControl);
          v9 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( SecurityDescriptorControl )
        {
          v28 = SetSecurityDescriptorControl(pSecurityDescriptor, 0x1000u, 0x1000u);
          SecurityDescriptorControl = v28;
          v9 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              45,
              &WPP_92b3b3424e563441648ef2499742b7fb_Traceguids,
              pSecurityDescriptor,
              v28);
            v9 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( SecurityDescriptorControl )
          {
            v29 = RegSetKeySecurity(a1, 4u, pSecurityDescriptor);
            v32 = v29;
            v9 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              v33 = 5;
              if ( v29 )
                v33 = 2;
              if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= v33 )
              {
                WPP_SF_Dqq(*((_QWORD *)WPP_GLOBAL_Control + 2), v30, v31, v29, a1, pSecurityDescriptor);
                v9 = (PVOID *)WPP_GLOBAL_Control;
              }
            }
            if ( v32 )
              SecurityDescriptorControl = 0;
          }
        }
      }
      goto LABEL_77;
    }
    v34 = ATL::AtlSetDacl(a1, (SE_OBJECT_TYPE)a3, (const struct ATL::CDacl *)v44, v22);
    SecurityDescriptorControl = v34;
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_81;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      goto LABEL_77;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_92b3b3424e563441648ef2499742b7fb_Traceguids, v34);
    goto LABEL_10;
  }
  SecurityDescriptorControl = 0;
  if ( v9 == &WPP_GLOBAL_Control )
    goto LABEL_81;
  if ( (*((_BYTE *)v9 + 28) & 2) != 0 && *((_BYTE *)v9 + 25) >= 2u )
  {
    WPP_SF_(v9[2], 36, &WPP_92b3b3424e563441648ef2499742b7fb_Traceguids);
LABEL_10:
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_77:
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 1) != 0 && *((_BYTE *)v9 + 25) >= 5u )
    WPP_SF_d(v9[2], 48, &WPP_92b3b3424e563441648ef2499742b7fb_Traceguids, SecurityDescriptorControl);
LABEL_81:
  ATL::CDacl::~CDacl((ATL::CDacl *)v44);
  return SecurityDescriptorControl;
}

```

## disassembly

```asm
0x140093330  mov     [rsp-8+arg_0], rbx
0x140093335  mov     [rsp-8+arg_18], r9d
0x14009333a  push    rbp
0x14009333b  push    rsi
0x14009333c  push    rdi
0x14009333d  push    r12
0x14009333f  push    r13
0x140093341  push    r14
0x140093343  push    r15
0x140093345  lea     rbp, [rsp-1Fh]
0x14009334a  sub     rsp, 0C0h
0x140093351  mov     edi, r9d
0x140093354  mov     r15d, r8d
0x140093357  mov     r12, rdx
0x14009335a  mov     r14, rcx
0x14009335d  lea     rax, WPP_GLOBAL_Control
0x140093364  mov     r10, cs:WPP_GLOBAL_Control
0x14009336b  cmp     r10, rax
0x14009336e  jz      short loc_1400933A8
0x140093370  test    byte ptr [r10+1Ch], 1
0x140093375  jz      short loc_1400933A8
0x140093377  cmp     byte ptr [r10+19h], 5
0x14009337c  jb      short loc_1400933A8
0x14009337e  movzx   eax, [rbp+4Fh+arg_20]
0x140093382  mov     [rsp+0F0h+var_B8], eax
0x140093386  mov     [rsp+0F0h+var_C0], r9d
0x14009338b  mov     dword ptr [rsp+0F0h+var_C8], r8d
0x140093390  mov     [rsp+0F0h+var_D0], rdx
0x140093395  mov     r9, rcx
0x140093398  mov     rcx, [r10+10h]
0x14009339c  call    WPP_SF_qSDLD
0x1400933a1  mov     r10, cs:WPP_GLOBAL_Control
0x1400933a8  xor     esi, esi
0x1400933aa  mov     [rbp+4Fh+var_A0], esi
0x1400933ad  mov     [rbp+4Fh+var_60], rsi
0x1400933b1  mov     [rbp+4Fh+var_58], sil
0x1400933b5  lea     ecx, [rsi+2]
0x1400933b8  mov     [rbp+4Fh+var_54], ecx
0x1400933bb  lea     rax, ??_7CDacl@ATL@@6B@; const ATL::CDacl::`vftable'
0x1400933c2  mov     [rbp+4Fh+var_68], rax
0x1400933c6  mov     [rbp+4Fh+var_50], rsi
0x1400933ca  mov     [rbp+4Fh+var_48], rsi
0x1400933ce  mov     [rbp+4Fh+var_40], rsi
0x1400933d2  mov     [rbp+4Fh+var_38], esi
0x1400933d5  mov     [rbp+4Fh+dwRevision], esi
0x1400933d8  test    r12, r12
0x1400933db  jnz     short loc_140093422
0x1400933dd  mov     ebx, esi
0x1400933df  lea     rdi, WPP_GLOBAL_Control
0x1400933e6  cmp     r10, rdi
0x1400933e9  jz      loc_1400938F5
0x1400933ef  test    [r10+1Ch], cl
0x1400933f3  jz      loc_1400938C9
0x1400933f9  cmp     [r10+19h], cl
0x1400933fd  jb      loc_1400938C9
0x140093403  lea     edx, [rsi+24h]
0x140093406  lea     r8, WPP_92b3b3424e563441648ef2499742b7fb_Traceguids
0x14009340d  mov     rcx, [r10+10h]
0x140093411  call    WPP_SF_
0x140093416  mov     r10, cs:WPP_GLOBAL_Control
0x14009341d  jmp     loc_1400938C9
0x140093422  cmp     r15d, 4
0x140093426  jnz     loc_14009361F
0x14009342c  mov     [rbp+4Fh+Wow64Process], esi
0x14009342f  call    cs:__imp_GetCurrentProcess
0x140093435  mov     rcx, rax; hProcess
0x140093438  lea     rdx, [rbp+4Fh+Wow64Process]; Wow64Process
0x14009343c  call    cs:__imp_IsWow64Process
0x140093442  test    eax, eax
0x140093444  jz      loc_14009361F
0x14009344a  cmp     [rbp+4Fh+Wow64Process], esi
0x14009344d  jz      loc_14009361F
0x140093453  lea     r13d, [r15-3]
0x140093457  mov     ebx, esi
0x140093459  mov     rdi, rsi
0x14009345c  mov     [rbp+4Fh+cbSecurityDescriptor], esi
0x14009345f  lea     r9, [rbp+4Fh+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x140093463  xor     r8d, r8d; pSecurityDescriptor
0x140093466  mov     edx, r15d; SecurityInformation
0x140093469  mov     rcx, r14; hKey
0x14009346c  call    cs:__imp_RegGetKeySecurity
0x140093472  mov     esi, eax
0x140093474  mov     rcx, cs:WPP_GLOBAL_Control
0x14009347b  lea     rax, WPP_GLOBAL_Control
0x140093482  cmp     rcx, rax
0x140093485  jz      short loc_1400934AE
0x140093487  test    byte ptr [rcx+1Ch], 2
0x14009348b  jz      short loc_1400934AE
0x14009348d  cmp     [rcx+19h], r15b
0x140093491  jb      short loc_1400934AE
0x140093493  lea     edx, [r15+21h]
0x140093497  mov     dword ptr [rsp+0F0h+var_D0], esi
0x14009349b  mov     r9, r14
0x14009349e  lea     r8, WPP_92b3b3424e563441648ef2499742b7fb_Traceguids
0x1400934a5  mov     rcx, [rcx+10h]
0x1400934a9  call    WPP_SF_qD
0x1400934ae  cmp     esi, 7Ah ; 'z'
0x1400934b1  jnz     loc_140093610
0x1400934b7  mov     ecx, [rbp+4Fh+cbSecurityDescriptor]; unsigned __int64
0x1400934ba  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1400934bf  mov     rdi, rax
0x1400934c2  lea     r9, [rbp+4Fh+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x1400934c6  mov     r8, rax; pSecurityDescriptor
0x1400934c9  lea     edx, [rsi-76h]; SecurityInformation
0x1400934cc  mov     rcx, r14; hKey
0x1400934cf  call    cs:__imp_RegGetKeySecurity
0x1400934d5  mov     esi, eax
0x1400934d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400934de  lea     rax, WPP_GLOBAL_Control
0x1400934e5  cmp     rcx, rax
0x1400934e8  jz      short loc_140093523
0x1400934ea  mov     eax, 2
0x1400934ef  test    [rcx+1Ch], al
0x1400934f2  jz      short loc_140093523
0x1400934f4  movzx   r8d, byte ptr [rcx+19h]
0x1400934f9  lea     edx, [rax+3]
0x1400934fc  test    esi, esi
0x1400934fe  cmovnz  edx, eax
0x140093501  cmp     r8d, edx
0x140093504  jb      short loc_140093523
0x140093506  mov     eax, [rbp+4Fh+cbSecurityDescriptor]
0x140093509  mov     [rsp+0F0h+var_C0], eax
0x14009350d  mov     [rsp+0F0h+var_C8], rdi
0x140093512  mov     [rsp+0F0h+var_D0], r14
0x140093517  mov     r9d, esi
0x14009351a  mov     rcx, [rcx+10h]
0x14009351e  call    WPP_SF_DqqD
0x140093523  test    esi, esi
0x140093525  jnz     loc_140093610
0x14009352b  xor     esi, esi
0x14009352d  mov     word ptr [rbp+4Fh+Wow64Process], si
0x140093531  lea     r8, [rbp+4Fh+dwRevision]; lpdwRevision
0x140093535  lea     rdx, [rbp+4Fh+Wow64Process]; pControl
0x140093539  mov     rcx, rdi; pSecurityDescriptor
0x14009353c  call    cs:__imp_GetSecurityDescriptorControl
0x140093542  mov     ebx, eax
0x140093544  mov     rcx, cs:WPP_GLOBAL_Control
0x14009354b  lea     rax, WPP_GLOBAL_Control
0x140093552  cmp     rcx, rax
0x140093555  jz      short loc_140093582
0x140093557  test    byte ptr [rcx+1Ch], 2
0x14009355b  jz      short loc_140093582
0x14009355d  cmp     byte ptr [rcx+19h], 4
0x140093561  jb      short loc_140093582
0x140093563  movzx   edx, word ptr [rbp+4Fh+Wow64Process]
0x140093567  mov     [rsp+0F0h+var_C0], ebx
0x14009356b  mov     eax, [rbp+4Fh+dwRevision]
0x14009356e  mov     dword ptr [rsp+0F0h+var_C8], eax
0x140093572  mov     dword ptr [rsp+0F0h+var_D0], edx
0x140093576  mov     r9, rdi
0x140093579  mov     rcx, [rcx+10h]
0x14009357d  call    WPP_SF_qlll
0x140093582  test    ebx, ebx
0x140093584  jz      loc_140093612
0x14009358a  mov     [rbp+4Fh+bDaclPresent], esi
0x14009358d  mov     [rbp+4Fh+pDacl], rsi
0x140093591  mov     [rbp+4Fh+bDaclDefaulted], esi
0x140093594  lea     r9, [rbp+4Fh+bDaclDefaulted]; lpbDaclDefaulted
0x140093598  lea     r8, [rbp+4Fh+pDacl]; pDacl
0x14009359c  lea     rdx, [rbp+4Fh+bDaclPresent]; lpbDaclPresent
0x1400935a0  mov     rcx, rdi; pSecurityDescriptor
0x1400935a3  call    cs:__imp_GetSecurityDescriptorDacl
0x1400935a9  mov     ebx, eax
0x1400935ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400935b2  lea     rax, WPP_GLOBAL_Control
0x1400935b9  cmp     rcx, rax
0x1400935bc  jz      short loc_1400935F1
0x1400935be  test    byte ptr [rcx+1Ch], 2
0x1400935c2  jz      short loc_1400935F1
0x1400935c4  cmp     byte ptr [rcx+19h], 4
0x1400935c8  jb      short loc_1400935F1
0x1400935ca  mov     [rsp+0F0h+var_B8], ebx
0x1400935ce  mov     eax, [rbp+4Fh+bDaclDefaulted]
0x1400935d1  mov     [rsp+0F0h+var_C0], eax
0x1400935d5  mov     rax, [rbp+4Fh+pDacl]
0x1400935d9  mov     [rsp+0F0h+var_C8], rax
0x1400935de  mov     eax, [rbp+4Fh+bDaclPresent]
0x1400935e1  mov     dword ptr [rsp+0F0h+var_D0], eax
0x1400935e5  mov     r9, rdi
0x1400935e8  mov     rcx, [rcx+10h]
0x1400935ec  call    WPP_SF_qlqll
0x1400935f1  test    ebx, ebx
0x1400935f3  jz      short loc_140093612
0x1400935f5  cmp     [rbp+4Fh+bDaclPresent], esi
0x1400935f8  jz      short loc_14009360C
0x1400935fa  mov     rdx, [rbp+4Fh+pDacl]; struct _ACL *
0x1400935fe  lea     rcx, [rbp+4Fh+var_68]; this
0x140093602  call    ??4CDacl@ATL@@QEAAAEAV01@AEBU_ACL@@@Z; ATL::CDacl::operator=(_ACL const &)
0x140093607  mov     ebx, r13d
0x14009360a  jmp     short loc_140093612
0x14009360c  mov     ebx, esi
0x14009360e  jmp     short loc_140093612
0x140093610  xor     esi, esi
0x140093612  mov     rcx, rdi; Block
0x140093615  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14009361a  mov     edi, [rbp+4Fh+arg_18]
0x14009361d  jmp     short loc_14009366D
0x14009361f  mov     r13d, esi
0x140093622  lea     r8, [rbp+4Fh+var_68]; struct ATL::CDacl *
0x140093626  mov     edx, r15d; enum _SE_OBJECT_TYPE
0x140093629  mov     rcx, r14; void *
0x14009362c  call    ?AtlGetDacl@ATL@@YA_NPEAXW4_SE_OBJECT_TYPE@@PEAVCDacl@1@@Z; ATL::AtlGetDacl(void *,_SE_OBJECT_TYPE,ATL::CDacl *)
0x140093631  movzx   ebx, al
0x140093634  mov     r10, cs:WPP_GLOBAL_Control
0x14009363b  lea     rcx, WPP_GLOBAL_Control
0x140093642  cmp     r10, rcx
0x140093645  jz      short loc_140093674
0x140093647  test    byte ptr [r10+1Ch], 2
0x14009364c  jz      short loc_140093674
0x14009364e  cmp     byte ptr [r10+19h], 4
0x140093653  jb      short loc_140093674
0x140093655  mov     edx, 2Ah ; '*'
0x14009365a  mov     r9d, ebx
0x14009365d  lea     r8, WPP_92b3b3424e563441648ef2499742b7fb_Traceguids
0x140093664  mov     rcx, [r10+10h]
0x140093668  call    WPP_SF_d
0x14009366d  mov     r10, cs:WPP_GLOBAL_Control
0x140093674  cmp     ebx, 1
0x140093677  jnz     loc_1400938C2
0x14009367d  lea     rax, [rbp+4Fh+var_A0]
0x140093681  mov     [rsp+0F0h+var_D0], rax; int *
0x140093686  mov     r9b, [rbp+4Fh+arg_20]; unsigned __int8
0x14009368a  mov     r8d, edi; unsigned int
0x14009368d  mov     rdx, r12; StringSid
0x140093690  lea     rcx, [rbp+4Fh+var_68]; this
0x140093694  call    ?AddAccessSidToDacl@@YAHAEAVCDacl@ATL@@PEBGKEAEAH@Z; AddAccessSidToDacl(ATL::CDacl &,ushort const *,ulong,uchar,int &)
0x140093699  mov     ebx, eax
0x14009369b  cmp     eax, 1
0x14009369e  jnz     loc_1400938BB
0x1400936a4  cmp     [rbp+4Fh+var_A0], eax
0x1400936a7  jnz     loc_1400938BB
0x1400936ad  test    r13d, r13d
0x1400936b0  jz      loc_14009386B
0x1400936b6  xorps   xmm0, xmm0
0x1400936b9  xor     eax, eax
0x1400936bb  movups  [rbp+4Fh+pSecurityDescriptor], xmm0
0x1400936bf  movups  [rbp+4Fh+var_80], xmm0
0x1400936c3  mov     [rbp+4Fh+var_70], rax
0x1400936c7  mov     edx, ebx; dwRevision
0x1400936c9  lea     rcx, [rbp+4Fh+pSecurityDescriptor]; pSecurityDescriptor
0x1400936cd  call    cs:__imp_InitializeSecurityDescriptor
0x1400936d3  mov     ebx, eax
0x1400936d5  mov     r10, cs:WPP_GLOBAL_Control
0x1400936dc  lea     rcx, WPP_GLOBAL_Control
0x1400936e3  mov     r15d, 2
0x1400936e9  cmp     r10, rcx
0x1400936ec  jz      short loc_14009371E
0x1400936ee  test    [r10+1Ch], r15b
0x1400936f2  jz      short loc_14009371E
0x1400936f4  cmp     byte ptr [r10+19h], 4
0x1400936f9  jb      short loc_14009371E
0x1400936fb  lea     edx, [r15+29h]
0x1400936ff  mov     dword ptr [rsp+0F0h+var_D0], eax
0x140093703  lea     r9, [rbp+4Fh+pSecurityDescriptor]
0x140093707  lea     r8, WPP_92b3b3424e563441648ef2499742b7fb_Traceguids
0x14009370e  mov     rcx, [r10+10h]
0x140093712  call    WPP_SF_qD
0x140093717  mov     r10, cs:WPP_GLOBAL_Control
0x14009371e  test    ebx, ebx
0x140093720  jz      loc_1400938C2
0x140093726  lea     rcx, [rbp+4Fh+var_68]; this
0x14009372a  call    ?GetPACL@CAcl@ATL@@QEBAPEBU_ACL@@XZ; ATL::CAcl::GetPACL(void)
0x14009372f  mov     r8, rax; pDacl
0x140093732  xor     r9d, r9d; bDaclDefaulted
0x140093735  lea     edx, [r9+1]; bDaclPresent
0x140093739  lea     rcx, [rbp+4Fh+pSecurityDescriptor]; pSecurityDescriptor
0x14009373d  call    cs:__imp_SetSecurityDescriptorDacl
0x140093743  mov     ebx, eax
0x140093745  mov     r10, cs:WPP_GLOBAL_Control
0x14009374c  lea     rcx, WPP_GLOBAL_Control
0x140093753  cmp     r10, rcx
0x140093756  jz      short loc_140093792
0x140093758  test    [r10+1Ch], r15b
0x14009375c  jz      short loc_140093792
0x14009375e  cmp     byte ptr [r10+19h], 4
0x140093763  jb      short loc_140093792
0x140093765  lea     rcx, [rbp+4Fh+var_68]; this
0x140093769  call    ?GetPACL@CAcl@ATL@@QEBAPEBU_ACL@@XZ; ATL::CAcl::GetPACL(void)
0x14009376e  mov     dword ptr [rsp+0F0h+var_C8], ebx
0x140093772  mov     [rsp+0F0h+var_D0], rax
0x140093777  lea     r9, [rbp+4Fh+pSecurityDescriptor]
0x14009377b  mov     rcx, cs:WPP_GLOBAL_Control
0x140093782  mov     rcx, [rcx+10h]
0x140093786  call    WPP_SF_qql
0x14009378b  mov     r10, cs:WPP_GLOBAL_Control
0x140093792  test    ebx, ebx
0x140093794  jz      loc_1400938C2
0x14009379a  mov     edx, 1000h; ControlBitsOfInterest
0x14009379f  mov     r8d, edx; ControlBitsToSet
0x1400937a2  lea     rcx, [rbp+4Fh+pSecurityDescriptor]; pSecurityDescriptor
0x1400937a6  call    cs:__imp_SetSecurityDescriptorControl
0x1400937ac  mov     ebx, eax
0x1400937ae  mov     r10, cs:WPP_GLOBAL_Control
0x1400937b5  lea     rcx, WPP_GLOBAL_Control
0x1400937bc  cmp     r10, rcx
0x1400937bf  jz      short loc_1400937F2
0x1400937c1  test    [r10+1Ch], r15b
0x1400937c5  jz      short loc_1400937F2
0x1400937c7  cmp     byte ptr [r10+19h], 4
0x1400937cc  jb      short loc_1400937F2
  ... truncated ...
```
