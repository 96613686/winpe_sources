# SxInitializeCOMSecurityForSPP(void)

- ea: `0x140007030`
- end: `0x1400074d1`
- name: `?SxInitializeCOMSecurityForSPP@@YAJXZ`
- size: `1185`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x140002f30`
- `0x14000312c`

## callees

- `0x140002e1c`
- `0x140006cc8`
- `0x140007030`
- `0x14000e324`
- `0x14000e41c`
- `0x14001094e`
- `0x140010980`

## import_xrefs

- `ADVAPI32!SetSecurityDescriptorDacl` at `0x140007421`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x140007421`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x1400073e7`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x1400073e7`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x1400073ae`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x1400073ae`
- `ADVAPI32!SetEntriesInAclW` at `0x140007357`
- `ADVAPI32!SetEntriesInAclW` at `0x140007357`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x140007135`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x140007135`
- `ADVAPI32!CreateWellKnownSid` at `0x140007178`
- `ADVAPI32!CreateWellKnownSid` at `0x1400071b5`
- `ADVAPI32!CreateWellKnownSid` at `0x1400071f5`
- `ADVAPI32!CreateWellKnownSid` at `0x140007235`
- `ADVAPI32!CreateWellKnownSid` at `0x140007275`
- `ADVAPI32!CreateWellKnownSid` at `0x140007178`
- `ADVAPI32!CreateWellKnownSid` at `0x1400071b5`
- `ADVAPI32!CreateWellKnownSid` at `0x1400071f5`
- `ADVAPI32!CreateWellKnownSid` at `0x140007235`
- `ADVAPI32!CreateWellKnownSid` at `0x140007275`
- `KERNEL32!LocalFree` at `0x140007497`
- `KERNEL32!LocalFree` at `0x140007497`
- `ole32!CoInitializeSecurity` at `0x140007477`
- `ole32!CoInitializeSecurity` at `0x140007477`

## string_xrefs

- `0x140007092`: `SxInitializeCOMSecurityForSPP`

## pseudocode

```c
__int64 SxInitializeCOMSecurityForSPP(void)
{
  __int16 v0; // ax
  signed int v1; // eax
  bool v2; // sf
  unsigned int v3; // ebx
  __int64 v4; // rdx
  __int64 v5; // r8
  DWORD cbSid; // [rsp+50h] [rbp-B0h] BYREF
  HRESULT LastFailureAsHRESULT; // [rsp+58h] [rbp-A8h] BYREF
  __int16 v9; // [rsp+5Ch] [rbp-A4h]
  __int16 v10; // [rsp+5Eh] [rbp-A2h]
  PACL NewAcl; // [rsp+90h] [rbp-70h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v13; // [rsp+B8h] [rbp-48h]
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+C0h] [rbp-40h] BYREF
  int v15; // [rsp+F0h] [rbp-10h]
  __int64 v16; // [rsp+F4h] [rbp-Ch]
  __int64 v17; // [rsp+100h] [rbp+0h]
  __int64 v18; // [rsp+108h] [rbp+8h]
  int v19; // [rsp+110h] [rbp+10h]
  _BYTE *v20; // [rsp+118h] [rbp+18h]
  int v21; // [rsp+120h] [rbp+20h]
  __int64 v22; // [rsp+124h] [rbp+24h]
  __int64 v23; // [rsp+130h] [rbp+30h]
  __int64 v24; // [rsp+138h] [rbp+38h]
  int v25; // [rsp+140h] [rbp+40h]
  _BYTE *v26; // [rsp+148h] [rbp+48h]
  int v27; // [rsp+150h] [rbp+50h]
  __int64 v28; // [rsp+154h] [rbp+54h]
  __int64 v29; // [rsp+160h] [rbp+60h]
  __int64 v30; // [rsp+168h] [rbp+68h]
  int v31; // [rsp+170h] [rbp+70h]
  _BYTE *v32; // [rsp+178h] [rbp+78h]
  int v33; // [rsp+180h] [rbp+80h]
  __int64 v34; // [rsp+184h] [rbp+84h]
  __int64 v35; // [rsp+190h] [rbp+90h]
  __int64 v36; // [rsp+198h] [rbp+98h]
  int v37; // [rsp+1A0h] [rbp+A0h]
  _BYTE *v38; // [rsp+1A8h] [rbp+A8h]
  _BYTE pSid[80]; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v40[80]; // [rsp+200h] [rbp+100h] BYREF
  _BYTE v41[80]; // [rsp+250h] [rbp+150h] BYREF
  _BYTE v42[80]; // [rsp+2A0h] [rbp+1A0h] BYREF
  _BYTE v43[80]; // [rsp+2F0h] [rbp+1F0h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_b81a483d4b6a372fb7a9076c2baad016_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&LastFailureAsHRESULT,
    "SxInitializeCOMSecurityForSPP",
    34,
    1);
  v13 = 0;
  pListOfExplicitEntries.grfAccessPermissions = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  memset_0(&pListOfExplicitEntries.grfAccessMode, 0, 0xECu);
  NewAcl = 0;
  memset_0(pSid, 0, 0x48u);
  memset_0(v40, 0, 0x48u);
  memset_0(v41, 0, 0x48u);
  memset_0(v42, 0, 0x48u);
  memset_0(v43, 0, 0x48u);
  cbSid = 0;
  if ( InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
  {
    LastFailureAsHRESULT = 0;
    v9 = 57;
    cbSid = 72;
    if ( CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, pSid, &cbSid) )
    {
      LastFailureAsHRESULT = 0;
      v9 = 61;
      cbSid = 72;
      if ( CreateWellKnownSid(WinLocalServiceSid, 0, v40, &cbSid) )
      {
        LastFailureAsHRESULT = 0;
        v9 = 65;
        cbSid = 72;
        if ( CreateWellKnownSid(WinNetworkServiceSid, 0, v41, &cbSid) )
        {
          LastFailureAsHRESULT = 0;
          v9 = 69;
          cbSid = 72;
          if ( CreateWellKnownSid(WinSelfSid, 0, v42, &cbSid) )
          {
            LastFailureAsHRESULT = 0;
            v9 = 73;
            cbSid = 72;
            if ( CreateWellKnownSid(WinLocalSystemSid, 0, v43, &cbSid) )
            {
              LastFailureAsHRESULT = 0;
              v9 = 77;
              pListOfExplicitEntries.Trustee.pMultipleTrustee = 0;
              *(_QWORD *)&pListOfExplicitEntries.Trustee.MultipleTrusteeOperation = 0;
              v17 = 0;
              *(_QWORD *)&pListOfExplicitEntries.grfAccessMode = 2;
              pListOfExplicitEntries.grfAccessPermissions = 3;
              pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)pSid;
              v20 = v40;
              v26 = v41;
              v32 = v42;
              v15 = 3;
              v21 = 3;
              v27 = 3;
              v33 = 3;
              v38 = v43;
              pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_GROUP;
              v16 = 2;
              v18 = 0;
              v19 = 2;
              v22 = 2;
              v23 = 0;
              v24 = 0;
              v25 = 2;
              v28 = 2;
              v29 = 0;
              v30 = 0;
              v31 = 2;
              v34 = 2;
              v35 = 0;
              v36 = 0;
              v37 = 2;
              v1 = SetEntriesInAclW(5u, &pListOfExplicitEntries, 0, &NewAcl);
              if ( v1 > 0 )
                v1 = (unsigned __int16)v1 | 0x80070000;
              LastFailureAsHRESULT = v1;
              v2 = v1 < 0;
              v0 = 125;
              if ( !v2 )
              {
                v9 = 125;
                v0 = 126;
                if ( NewAcl )
                {
                  LastFailureAsHRESULT = 0;
                  v9 = 126;
                  if ( SetSecurityDescriptorOwner(pSecurityDescriptor, pSid, 0) )
                  {
                    LastFailureAsHRESULT = 0;
                    v9 = 129;
                    if ( SetSecurityDescriptorGroup(pSecurityDescriptor, pSid, 0) )
                    {
                      LastFailureAsHRESULT = 0;
                      v9 = 132;
                      if ( SetSecurityDescriptorDacl(pSecurityDescriptor, 1, NewAcl, 0) )
                      {
                        LastFailureAsHRESULT = 0;
                        v9 = 135;
                        LastFailureAsHRESULT = CoInitializeSecurity(
                                                 pSecurityDescriptor,
                                                 -1,
                                                 0,
                                                 0,
                                                 6u,
                                                 2u,
                                                 0,
                                                 0x3000u,
                                                 0);
                        v0 = 145;
                        if ( LastFailureAsHRESULT >= 0 )
                        {
                          v9 = 145;
                          goto LABEL_30;
                        }
                      }
                      else
                      {
                        LastFailureAsHRESULT = GetLastFailureAsHRESULT();
                        v0 = 135;
                      }
                    }
                    else
                    {
                      LastFailureAsHRESULT = GetLastFailureAsHRESULT();
                      v0 = 132;
                    }
                  }
                  else
                  {
                    LastFailureAsHRESULT = GetLastFailureAsHRESULT();
                    v0 = 129;
                  }
                }
                else
                {
                  LastFailureAsHRESULT = -2147024882;
                }
              }
            }
            else
            {
              LastFailureAsHRESULT = GetLastFailureAsHRESULT();
              v0 = 77;
            }
          }
          else
          {
            LastFailureAsHRESULT = GetLastFailureAsHRESULT();
            v0 = 73;
          }
        }
        else
        {
          LastFailureAsHRESULT = GetLastFailureAsHRESULT();
          v0 = 69;
        }
      }
      else
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT();
        v0 = 65;
      }
    }
    else
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT();
      v0 = 61;
    }
  }
  else
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT();
    v0 = 57;
  }
  v10 = v0;
LABEL_30:
  LocalFree(NewAcl);
  v3 = LastFailureAsHRESULT;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, v4, v5);
  return v3;
}

```

## disassembly

```asm
0x140007030  mov     [rsp-8+arg_0], rbx
0x140007035  mov     [rsp-8+arg_8], rdi
0x14000703a  push    rbp
0x14000703b  lea     rbp, [rsp-250h]
0x140007043  sub     rsp, 350h
0x14000704a  mov     rax, cs:__security_cookie
0x140007051  xor     rax, rsp
0x140007054  mov     [rbp+250h+var_10], rax
0x14000705b  mov     rcx, cs:WPP_GLOBAL_Control
0x140007062  lea     rax, WPP_GLOBAL_Control
0x140007069  cmp     rcx, rax
0x14000706c  jz      short loc_14000708C
0x14000706e  test    dword ptr [rcx+1Ch], 20000000h
0x140007075  jz      short loc_14000708C
0x140007077  mov     rcx, [rcx+10h]
0x14000707b  lea     r8, WPP_b81a483d4b6a372fb7a9076c2baad016_Traceguids
0x140007082  mov     edx, 0Ah
0x140007087  call    WPP_SF_
0x14000708c  mov     r9d, 1; unsigned __int16
0x140007092  lea     rdx, aSxinitializeco; "SxInitializeCOMSecurityForSPP"
0x140007099  lea     rcx, [rsp+350h+var_2F8]; this
0x14000709e  lea     r8d, [r9+21h]; unsigned __int16
0x1400070a2  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1400070a7  xorps   xmm0, xmm0
0x1400070aa  lea     rcx, [rbp+250h+pListOfExplicitEntries.grfAccessMode]; void *
0x1400070ae  xor     eax, eax
0x1400070b0  xor     ebx, ebx
0x1400070b2  xor     edx, edx; Val
0x1400070b4  mov     [rbp+250h+var_298], rax
0x1400070b8  mov     r8d, 0ECh; Size
0x1400070be  mov     [rbp+250h+pListOfExplicitEntries.grfAccessPermissions], ebx
0x1400070c1  movups  [rbp+250h+pSecurityDescriptor], xmm0
0x1400070c5  movups  [rbp+250h+var_2A8], xmm0
0x1400070c9  call    memset_0
0x1400070ce  lea     edi, [rbx+48h]
0x1400070d1  mov     [rbp+250h+NewAcl], rbx
0x1400070d5  mov     r8d, edi; Size
0x1400070d8  lea     rcx, [rbp+250h+pSid]; void *
0x1400070df  xor     edx, edx; Val
0x1400070e1  call    memset_0
0x1400070e6  mov     r8d, edi; Size
0x1400070e9  lea     rcx, [rbp+250h+var_150]; void *
0x1400070f0  xor     edx, edx; Val
0x1400070f2  call    memset_0
0x1400070f7  mov     r8d, edi; Size
0x1400070fa  lea     rcx, [rbp+250h+var_100]; void *
0x140007101  xor     edx, edx; Val
0x140007103  call    memset_0
0x140007108  mov     r8d, edi; Size
0x14000710b  lea     rcx, [rbp+250h+var_B0]; void *
0x140007112  xor     edx, edx; Val
0x140007114  call    memset_0
0x140007119  mov     r8d, edi; Size
0x14000711c  lea     rcx, [rbp+250h+var_60]; void *
0x140007123  xor     edx, edx; Val
0x140007125  call    memset_0
0x14000712a  lea     edx, [rbx+1]; dwRevision
0x14000712d  mov     [rsp+350h+cbSid], ebx
0x140007131  lea     rcx, [rbp+250h+pSecurityDescriptor]; pSecurityDescriptor
0x140007135  call    cs:__imp_InitializeSecurityDescriptor
0x14000713b  test    eax, eax
0x14000713d  jnz     short loc_140007155
0x14000713f  call    GetLastFailureAsHRESULT
0x140007144  mov     [rsp+350h+var_2F8], eax
0x140007148  lea     eax, [rbx+39h]
0x14000714b  mov     [rsp+350h+var_2F2], ax
0x140007150  jmp     loc_140007493
0x140007155  mov     eax, 39h ; '9'
0x14000715a  mov     [rsp+350h+var_2F8], ebx
0x14000715e  lea     r9, [rsp+350h+cbSid]; cbSid
0x140007163  mov     [rsp+350h+var_2F4], ax
0x140007168  lea     r8, [rbp+250h+pSid]; pSid
0x14000716f  mov     [rsp+350h+cbSid], edi
0x140007173  xor     edx, edx; DomainSid
0x140007175  lea     ecx, [rax-1Fh]; WellKnownSidType
0x140007178  call    cs:__imp_CreateWellKnownSid
0x14000717e  test    eax, eax
0x140007180  jnz     short loc_140007192
0x140007182  call    GetLastFailureAsHRESULT
0x140007187  mov     [rsp+350h+var_2F8], eax
0x14000718b  mov     eax, 3Dh ; '='
0x140007190  jmp     short loc_14000714B
0x140007192  mov     eax, 3Dh ; '='
0x140007197  mov     [rsp+350h+var_2F8], ebx
0x14000719b  lea     r9, [rsp+350h+cbSid]; cbSid
0x1400071a0  mov     [rsp+350h+var_2F4], ax
0x1400071a5  lea     r8, [rbp+250h+var_150]; pSid
0x1400071ac  mov     [rsp+350h+cbSid], edi
0x1400071b0  xor     edx, edx; DomainSid
0x1400071b2  lea     ecx, [rax-26h]; WellKnownSidType
0x1400071b5  call    cs:__imp_CreateWellKnownSid
0x1400071bb  test    eax, eax
0x1400071bd  jnz     short loc_1400071D2
0x1400071bf  call    GetLastFailureAsHRESULT
0x1400071c4  mov     [rsp+350h+var_2F8], eax
0x1400071c8  mov     eax, 41h ; 'A'
0x1400071cd  jmp     loc_14000714B
0x1400071d2  mov     eax, 41h ; 'A'
0x1400071d7  mov     [rsp+350h+var_2F8], ebx
0x1400071db  lea     r9, [rsp+350h+cbSid]; cbSid
0x1400071e0  mov     [rsp+350h+var_2F4], ax
0x1400071e5  lea     r8, [rbp+250h+var_100]; pSid
0x1400071ec  mov     [rsp+350h+cbSid], edi
0x1400071f0  xor     edx, edx; DomainSid
0x1400071f2  lea     ecx, [rax-29h]; WellKnownSidType
0x1400071f5  call    cs:__imp_CreateWellKnownSid
0x1400071fb  test    eax, eax
0x1400071fd  jnz     short loc_140007212
0x1400071ff  call    GetLastFailureAsHRESULT
0x140007204  mov     [rsp+350h+var_2F8], eax
0x140007208  mov     eax, 45h ; 'E'
0x14000720d  jmp     loc_14000714B
0x140007212  mov     eax, 45h ; 'E'
0x140007217  mov     [rsp+350h+var_2F8], ebx
0x14000721b  lea     r9, [rsp+350h+cbSid]; cbSid
0x140007220  mov     [rsp+350h+var_2F4], ax
0x140007225  lea     r8, [rbp+250h+var_B0]; pSid
0x14000722c  mov     [rsp+350h+cbSid], edi
0x140007230  xor     edx, edx; DomainSid
0x140007232  lea     ecx, [rax-35h]; WellKnownSidType
0x140007235  call    cs:__imp_CreateWellKnownSid
0x14000723b  test    eax, eax
0x14000723d  jnz     short loc_140007252
0x14000723f  call    GetLastFailureAsHRESULT
0x140007244  mov     [rsp+350h+var_2F8], eax
0x140007248  mov     eax, 49h ; 'I'
0x14000724d  jmp     loc_14000714B
0x140007252  mov     eax, 49h ; 'I'
0x140007257  mov     [rsp+350h+var_2F8], ebx
0x14000725b  lea     r9, [rsp+350h+cbSid]; cbSid
0x140007260  mov     [rsp+350h+var_2F4], ax
0x140007265  lea     r8, [rbp+250h+var_60]; pSid
0x14000726c  mov     [rsp+350h+cbSid], edi
0x140007270  xor     edx, edx; DomainSid
0x140007272  lea     ecx, [rax-33h]; WellKnownSidType
0x140007275  call    cs:__imp_CreateWellKnownSid
0x14000727b  test    eax, eax
0x14000727d  jnz     short loc_140007292
0x14000727f  call    GetLastFailureAsHRESULT
0x140007284  mov     [rsp+350h+var_2F8], eax
0x140007288  mov     eax, 4Dh ; 'M'
0x14000728d  jmp     loc_14000714B
0x140007292  mov     eax, 4Dh ; 'M'
0x140007297  mov     [rsp+350h+var_2F8], ebx
0x14000729b  mov     [rsp+350h+var_2F4], ax
0x1400072a0  lea     r9, [rbp+250h+NewAcl]; NewAcl
0x1400072a4  xor     r8d, r8d; OldAcl
0x1400072a7  mov     [rbp+250h+pListOfExplicitEntries.Trustee.pMultipleTrustee], rbx
0x1400072ab  lea     rdx, [rbp+250h+pListOfExplicitEntries]; pListOfExplicitEntries
0x1400072af  mov     qword ptr [rbp+250h+pListOfExplicitEntries.Trustee.MultipleTrusteeOperation], rbx
0x1400072b3  lea     edi, [rax-4Bh]
0x1400072b6  mov     [rbp+250h+var_250], rbx
0x1400072ba  lea     ecx, [rax-4Ah]
0x1400072bd  mov     qword ptr [rbp+250h+pListOfExplicitEntries.grfAccessMode], rdi
0x1400072c1  lea     rax, [rbp+250h+pSid]
0x1400072c8  mov     [rbp+250h+pListOfExplicitEntries.grfAccessPermissions], ecx
0x1400072cb  mov     [rbp+250h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x1400072cf  lea     rax, [rbp+250h+var_150]
0x1400072d6  mov     [rbp+250h+var_238], rax
0x1400072da  lea     rax, [rbp+250h+var_100]
0x1400072e1  mov     [rbp+250h+var_208], rax
0x1400072e5  lea     rax, [rbp+250h+var_B0]
0x1400072ec  mov     [rbp+250h+var_1D8], rax
0x1400072f0  lea     rax, [rbp+250h+var_60]
0x1400072f7  mov     [rbp+250h+var_260], ecx
0x1400072fa  mov     [rbp+250h+var_230], ecx
0x1400072fd  mov     [rbp+250h+var_200], ecx
0x140007300  mov     [rbp+250h+var_1D0], ecx
0x140007306  lea     ecx, [rdi+3]; cCountOfExplicitEntries
0x140007309  mov     [rbp+250h+var_1A8], rax
0x140007310  mov     [rbp+250h+pListOfExplicitEntries.Trustee.TrusteeType], edi
0x140007313  mov     [rbp+250h+var_25C], rdi
0x140007317  mov     [rbp+250h+var_248], rbx
0x14000731b  mov     [rbp+250h+var_240], edi
0x14000731e  mov     [rbp+250h+var_22C], rdi
0x140007322  mov     [rbp+250h+var_220], rbx
0x140007326  mov     [rbp+250h+var_218], rbx
0x14000732a  mov     [rbp+250h+var_210], edi
0x14000732d  mov     [rbp+250h+var_1FC], rdi
0x140007331  mov     [rbp+250h+var_1F0], rbx
0x140007335  mov     [rbp+250h+var_1E8], rbx
0x140007339  mov     [rbp+250h+var_1E0], edi
0x14000733c  mov     [rbp+250h+var_1CC], rdi
0x140007343  mov     [rbp+250h+var_1C0], rbx
0x14000734a  mov     [rbp+250h+var_1B8], rbx
0x140007351  mov     [rbp+250h+var_1B0], edi
0x140007357  call    cs:__imp_SetEntriesInAclW
0x14000735d  test    eax, eax
0x14000735f  jle     short loc_140007369
0x140007361  movzx   eax, ax
0x140007364  or      eax, 80070000h
0x140007369  mov     [rsp+350h+var_2F8], eax
0x14000736d  test    eax, eax
0x14000736f  mov     eax, 7Dh ; '}'
0x140007374  js      loc_14000714B
0x14000737a  mov     [rsp+350h+var_2F4], ax
0x14000737f  mov     eax, 7Eh ; '~'
0x140007384  cmp     [rbp+250h+NewAcl], rbx
0x140007388  jnz     short loc_140007397
0x14000738a  mov     [rsp+350h+var_2F8], 8007000Eh
0x140007392  jmp     loc_14000714B
0x140007397  xor     r8d, r8d; bOwnerDefaulted
0x14000739a  mov     [rsp+350h+var_2F8], ebx
0x14000739e  lea     rdx, [rbp+250h+pSid]; pOwner
0x1400073a5  mov     [rsp+350h+var_2F4], ax
0x1400073aa  lea     rcx, [rbp+250h+pSecurityDescriptor]; pSecurityDescriptor
0x1400073ae  call    cs:__imp_SetSecurityDescriptorOwner
0x1400073b4  test    eax, eax
0x1400073b6  jnz     short loc_1400073CB
0x1400073b8  call    GetLastFailureAsHRESULT
0x1400073bd  mov     [rsp+350h+var_2F8], eax
0x1400073c1  mov     eax, 81h
0x1400073c6  jmp     loc_14000714B
0x1400073cb  mov     eax, 81h
0x1400073d0  mov     [rsp+350h+var_2F8], ebx
0x1400073d4  xor     r8d, r8d; bGroupDefaulted
0x1400073d7  mov     [rsp+350h+var_2F4], ax
0x1400073dc  lea     rdx, [rbp+250h+pSid]; pGroup
0x1400073e3  lea     rcx, [rbp+250h+pSecurityDescriptor]; pSecurityDescriptor
0x1400073e7  call    cs:__imp_SetSecurityDescriptorGroup
0x1400073ed  test    eax, eax
0x1400073ef  jnz     short loc_140007404
0x1400073f1  call    GetLastFailureAsHRESULT
0x1400073f6  mov     [rsp+350h+var_2F8], eax
0x1400073fa  mov     eax, 84h
0x1400073ff  jmp     loc_14000714B
0x140007404  mov     r8, [rbp+250h+NewAcl]; pDacl
0x140007408  lea     rcx, [rbp+250h+pSecurityDescriptor]; pSecurityDescriptor
0x14000740c  xor     r9d, r9d; bDaclDefaulted
0x14000740f  mov     [rsp+350h+var_2F8], ebx
0x140007413  mov     eax, 84h
0x140007418  mov     [rsp+350h+var_2F4], ax
0x14000741d  lea     edx, [r9+1]; bDaclPresent
0x140007421  call    cs:__imp_SetSecurityDescriptorDacl
0x140007427  test    eax, eax
0x140007429  jnz     short loc_14000743E
0x14000742b  call    GetLastFailureAsHRESULT
0x140007430  mov     [rsp+350h+var_2F8], eax
0x140007434  mov     eax, 87h
0x140007439  jmp     loc_14000714B
0x14000743e  mov     [rsp+350h+pReserved3], rbx; pReserved3
0x140007443  lea     rcx, [rbp+250h+pSecurityDescriptor]; pSecDesc
0x140007447  mov     [rsp+350h+dwCapabilities], 3000h; dwCapabilities
0x14000744f  mov     eax, 87h
0x140007454  mov     [rsp+350h+pAuthList], rbx; pAuthList
0x140007459  xor     r9d, r9d; pReserved1
0x14000745c  mov     [rsp+350h+dwImpLevel], edi; dwImpLevel
0x140007460  xor     r8d, r8d; asAuthSvc
0x140007463  or      edx, 0FFFFFFFFh; cAuthSvc
0x140007466  mov     [rsp+350h+dwAuthnLevel], 6; dwAuthnLevel
0x14000746e  mov     [rsp+350h+var_2F8], ebx
0x140007472  mov     [rsp+350h+var_2F4], ax
0x140007477  call    cs:__imp_CoInitializeSecurity
0x14000747d  mov     [rsp+350h+var_2F8], eax
0x140007481  test    eax, eax
0x140007483  mov     eax, 91h
0x140007488  js      loc_14000714B
0x14000748e  mov     [rsp+350h+var_2F4], ax
0x140007493  mov     rcx, [rbp+250h+NewAcl]; hMem
0x140007497  call    cs:__imp_LocalFree
0x14000749d  mov     ebx, [rsp+350h+var_2F8]
0x1400074a1  lea     rcx, [rsp+350h+var_2F8]; this
0x1400074a6  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1400074ab  mov     eax, ebx
0x1400074ad  mov     rcx, [rbp+250h+var_10]
0x1400074b4  xor     rcx, rsp; StackCookie
0x1400074b7  call    __security_check_cookie
0x1400074bc  lea     r11, [rsp+350h+var_s0]
0x1400074c4  mov     rbx, [r11+10h]
0x1400074c8  mov     rdi, [r11+18h]
0x1400074cc  mov     rsp, r11
0x1400074cf  pop     rbp
0x1400074d0  retn
```
