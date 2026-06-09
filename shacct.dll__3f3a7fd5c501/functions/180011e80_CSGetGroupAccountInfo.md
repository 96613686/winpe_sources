# CSGetGroupAccountInfo

- ea: `0x180011e80`
- end: `0x1800123ba`
- name: `CSGetGroupAccountInfo`
- size: `1338`
- prototype: `__int64 __fastcall(int, int, int, int, HDPA hdpa)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800123c0`
- `0x180014d90`

## callees

- `0x180002bf0`
- `0x180003660`
- `0x1800037e0`
- `0x180008300`
- `0x18000b9e0`
- `0x18000bcec`
- `0x18000fc2c`
- `0x18000fce4`
- `0x1800100e4`
- `0x180010ce4`
- `0x180011e80`
- `0x180012f18`
- `0x1800130c4`
- `0x1800132b4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualDomainSid` at `0x180012174`
- `api-ms-win-security-base-l1-1-0!EqualDomainSid` at `0x1800121ba`
- `api-ms-win-security-base-l1-1-0!EqualDomainSid` at `0x180012174`
- `api-ms-win-security-base-l1-1-0!EqualDomainSid` at `0x1800121ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012268`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012271`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800122a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012268`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012271`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800122a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011f92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001201f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011f92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001201f`
- `SAMLIB!SamGetMembersInAlias` at `0x18001209c`
- `SAMLIB!SamGetMembersInAlias` at `0x18001209c`
- `SAMLIB!SamQueryInformationAlias` at `0x180011f6c`
- `SAMLIB!SamQueryInformationAlias` at `0x180012009`
- `SAMLIB!SamQueryInformationAlias` at `0x180011f6c`
- `SAMLIB!SamQueryInformationAlias` at `0x180012009`
- `SAMLIB!SamLookupNamesInDomain` at `0x180011f18`
- `SAMLIB!SamLookupNamesInDomain` at `0x180011f18`
- `SAMLIB!SamCloseHandle` at `0x1800122fa`
- `SAMLIB!SamCloseHandle` at `0x18001238d`
- `SAMLIB!SamCloseHandle` at `0x180012397`
- `SAMLIB!SamCloseHandle` at `0x1800122fa`
- `SAMLIB!SamCloseHandle` at `0x18001238d`
- `SAMLIB!SamCloseHandle` at `0x180012397`
- `SAMLIB!SamOpenAlias` at `0x180011f4d`
- `SAMLIB!SamOpenAlias` at `0x180011f4d`
- `SAMLIB!SamFreeMemory` at `0x180011fb3`
- `SAMLIB!SamFreeMemory` at `0x180012040`
- `SAMLIB!SamFreeMemory` at `0x1800122b0`
- `SAMLIB!SamFreeMemory` at `0x180012342`
- `SAMLIB!SamFreeMemory` at `0x18001234c`
- `SAMLIB!SamFreeMemory` at `0x180011fb3`
- `SAMLIB!SamFreeMemory` at `0x180012040`
- `SAMLIB!SamFreeMemory` at `0x1800122b0`
- `SAMLIB!SamFreeMemory` at `0x180012342`
- `SAMLIB!SamFreeMemory` at `0x18001234c`
- `api-ms-win-security-lsalookup-l1-1-2!LsaLookupUserAccountType` at `0x180012153`
- `api-ms-win-security-lsalookup-l1-1-2!LsaLookupUserAccountType` at `0x180012153`

## pseudocode

```c
__int64 __fastcall CSGetGroupAccountInfo(
        void *a1,
        __int64 a2,
        struct _UNICODE_STRING **a3,
        struct _ALIAS_EXTENDED_INFORMATION **a4,
        HDPA hdpa)
{
  int v8; // ebx
  int v9; // ebx
  int v10; // r8d
  int v11; // ebx
  int v12; // r8d
  int v13; // ebx
  int v14; // r8d
  struct _UNICODE_STRING *v15; // rax
  _QWORD *v16; // rcx
  int v17; // ebx
  struct _ALIAS_EXTENDED_INFORMATION *v18; // rax
  int MembersInAlias; // eax
  int v20; // eax
  _QWORD *v21; // rsi
  int v22; // eax
  PSID v23; // r13
  ULONG v24; // eax
  __int64 v25; // r12
  __int64 v26; // rdx
  __int64 v27; // r8
  PSID v28; // rcx
  int v29; // eax
  WCHAR *v30; // xmm1_8
  PSID v31; // rcx
  int v32; // eax
  int v33; // edx
  void *p; // [rsp+30h] [rbp-61h] BYREF
  ULONG Count; // [rsp+38h] [rbp-59h] BYREF
  int v37; // [rsp+3Ch] [rbp-55h] BYREF
  PSID *Sids; // [rsp+40h] [rbp-51h] BYREF
  __int64 v39; // [rsp+48h] [rbp-49h] BYREF
  PSID pv; // [rsp+50h] [rbp-41h] BYREF
  void *v41; // [rsp+58h] [rbp-39h] BYREF
  struct _UNICODE_STRING *v42; // [rsp+60h] [rbp-31h] BYREF
  unsigned int *v43; // [rsp+68h] [rbp-29h] BYREF
  _DWORD *v44; // [rsp+70h] [rbp-21h] BYREF
  void *v45; // [rsp+78h] [rbp-19h] BYREF
  _SID_INFO v46; // [rsp+80h] [rbp-11h] BYREF
  PSID pSid2; // [rsp+F8h] [rbp+67h] BYREF

  v44 = 0;
  v43 = 0;
  if ( !a2 || !hdpa || !a3 )
    return (unsigned int)-2147467261;
  *a3 = 0;
  *a4 = 0;
  v45 = 0;
  v41 = 0;
  v8 = SamHandleForDomain(a1, 0x20021u, 0x20385u, &v45, &v41);
  if ( v8 >= 0 )
  {
    v9 = SamLookupNamesInDomain(v41, 1, a2, &v43, &v44);
    if ( v9 < 0 )
    {
      v8 = v9 | 0x10000000;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_ZD(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, v10, a2, v8);
      goto LABEL_77;
    }
    if ( *v44 != 4 )
    {
      v8 = -805306230;
      goto LABEL_73;
    }
    v39 = 0;
    v11 = SamOpenAlias(v41, 131084, *v43, &v39);
    if ( v11 < 0 )
    {
      v8 = v11 | 0x10000000;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_ZD(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, v12, a2, v8);
      goto LABEL_73;
    }
    v42 = 0;
    v13 = SamQueryInformationAlias(v39, 1, &v42);
    if ( v13 < 0 )
    {
      v8 = v13 | 0x10000000;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
LABEL_16:
        if ( v8 < 0 )
          goto LABEL_64;
        pSid2 = 0;
        v17 = SamQueryInformationAlias(v39, 5, &pSid2);
        if ( v17 < 0 )
        {
          v8 = v17 | 0x10000000;
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          {
LABEL_25:
            if ( v8 >= 0 )
            {
              Count = 0;
              Sids = 0;
              MembersInAlias = SamGetMembersInAlias(v39, &Sids, &Count);
              if ( MembersInAlias >= 0 )
              {
                if ( Count )
                {
                  pSid2 = 0;
                  v20 = LookupSids(Count, Sids, (struct _SID_INFO **)&pSid2);
                  v21 = pSid2;
                  v8 = v20;
                  if ( v20 >= 0 && pSid2 )
                  {
                    pSid2 = 0;
                    pv = 0;
                    v8 = CSGetAccountDomainSid(&pSid2);
                    if ( v8 >= 0 )
                    {
                      v22 = CSGetBuiltInDomainSid(&pv);
                      v23 = pSid2;
                      v8 = v22;
                      if ( v22 >= 0 )
                      {
                        v24 = Count;
                        v25 = 0;
                        if ( Count )
                        {
                          while ( 1 )
                          {
                            LODWORD(pSid2) = 0;
                            if ( v21[3 * v25 + 2] )
                              break;
LABEL_51:
                            v25 = (unsigned int)(v25 + 1);
                            if ( (unsigned int)v25 >= v24 )
                              goto LABEL_52;
                          }
                          v37 = 0;
                          LsaLookupUserAccountType(Sids[v25], &v37);
                          p = 0;
                          if ( v37 != 5 )
                          {
                            if ( EqualDomainSid(Sids[v25], v23, (BOOL *)&pSid2) && (_DWORD)pSid2 )
                            {
                              v28 = v23;
LABEL_38:
                              v29 = CSGetAccountPropertyStore(v28, v21[3 * v25 + 2], 1, 0, &p);
LABEL_47:
                              v8 = v29;
                              if ( v29 >= 0 && DPA_InsertPtr(hdpa, 0x7FFFFFFF, p) != -1 )
                                p = 0;
                              SafeRelease<IPropertyStore>(&p);
                              v24 = Count;
                              goto LABEL_51;
                            }
                            if ( v37 != 5 && EqualDomainSid(Sids[v25], pv, (BOOL *)&pSid2) && (_DWORD)pSid2 )
                            {
                              v28 = pv;
                              goto LABEL_38;
                            }
                          }
                          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                          {
                            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), v26, v27, v21[3 * v25 + 2]);
                          }
                          v30 = (WCHAR *)v21[3 * v25 + 2];
                          v31 = Sids[v25];
                          *(_OWORD *)&v46.pSid = *(_OWORD *)&v21[3 * v25];
                          v46.pwzClass = v30;
                          v29 = CreateReadOnlyPropertyStore(v31, &v46, (struct IPropertyStore **)&p);
                          goto LABEL_47;
                        }
LABEL_52:
                        v32 = 0;
                        if ( *(int *)hdpa <= 0 )
                          v32 = v8;
                        v8 = v32;
                        CoTaskMemFree(pv);
                      }
                      CoTaskMemFree(v23);
                    }
                  }
                  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      60,
                      WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids,
                      (unsigned int)v20);
                  }
                  CoTaskMemFree(v21);
                }
                SamFreeMemory(Sids);
                goto LABEL_68;
              }
              v8 = MembersInAlias | 0x10000000;
              v16 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
              {
LABEL_68:
                SamCloseHandle(v39);
LABEL_73:
                SamFreeMemory(v43);
                SamFreeMemory(v44);
LABEL_77:
                SamCloseHandle(v41);
                SamCloseHandle(v45);
                return (unsigned int)v8;
              }
              v33 = 61;
LABEL_67:
              WPP_SF_ZD(v16[2], v33, v14, a2, v8);
              goto LABEL_68;
            }
LABEL_64:
            if ( v16 == &WPP_GLOBAL_Control || (*((_BYTE *)v16 + 28) & 2) == 0 )
              goto LABEL_68;
            v33 = 62;
            goto LABEL_67;
          }
          WPP_SF_ZD(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, v14, a2, v8);
        }
        else
        {
          v8 = -2147024882;
          v18 = (struct _ALIAS_EXTENDED_INFORMATION *)CoTaskMemAlloc(0x18u);
          *a4 = v18;
          if ( v18 )
            v8 = CopyAliasExtStructure((struct _ALIAS_EXTENDED_INFORMATION *const)pSid2, v18);
          SamFreeMemory(pSid2);
        }
        v16 = WPP_GLOBAL_Control;
        goto LABEL_25;
      }
      WPP_SF_ZD(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, v14, a2, v8);
    }
    else
    {
      v8 = -2147024882;
      v15 = (struct _UNICODE_STRING *)CoTaskMemAlloc(0x28u);
      *a3 = v15;
      if ( v15 )
        v8 = CopyAliasStructure(v42, v15);
      SamFreeMemory(v42);
    }
    v16 = WPP_GLOBAL_Control;
    goto LABEL_16;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180011e80  push    rbp
0x180011e82  push    rbx
0x180011e83  push    rsi
0x180011e84  push    rdi
0x180011e85  push    r12
0x180011e87  push    r13
0x180011e89  push    r14
0x180011e8b  push    r15
0x180011e8d  lea     rbp, [rsp-17h]
0x180011e92  sub     rsp, 0A8h
0x180011e99  xor     edi, edi
0x180011e9b  mov     r13, r9
0x180011e9e  mov     [rbp+4Fh+var_70], rdi
0x180011ea2  mov     r12, r8
0x180011ea5  mov     [rbp+4Fh+var_78], rdi
0x180011ea9  mov     rsi, rdx
0x180011eac  test    rdx, rdx
0x180011eaf  jz      loc_18001239F
0x180011eb5  cmp     [rbp+4Fh+hdpa], rdi
0x180011eb9  jz      loc_18001239F
0x180011ebf  test    r8, r8
0x180011ec2  jz      loc_18001239F
0x180011ec8  mov     [r8], rdi
0x180011ecb  lea     rax, [rbp+4Fh+var_88]
0x180011ecf  mov     [r9], rdi
0x180011ed2  mov     edx, 20021h; unsigned int
0x180011ed7  lea     r9, [rbp+4Fh+var_68]; void **
0x180011edb  mov     [rbp+4Fh+var_68], rdi
0x180011edf  mov     r8d, 20385h; unsigned int
0x180011ee5  mov     [rbp+4Fh+var_88], rdi
0x180011ee9  mov     [rsp+0E0h+var_C0], rax; void **
0x180011eee  call    ?SamHandleForDomain@@YAJPEAXKKPEAPEAX1@Z; SamHandleForDomain(void *,ulong,ulong,void * *,void * *)
0x180011ef3  mov     ebx, eax
0x180011ef5  test    eax, eax
0x180011ef7  js      loc_1800123A4
0x180011efd  mov     rcx, [rbp+4Fh+var_88]
0x180011f01  lea     rax, [rbp+4Fh+var_70]
0x180011f05  lea     r14d, [rdi+1]
0x180011f09  mov     [rsp+0E0h+var_C0], rax
0x180011f0e  mov     edx, r14d
0x180011f11  lea     r9, [rbp+4Fh+var_78]
0x180011f15  mov     r8, rsi
0x180011f18  call    cs:__imp_SamLookupNamesInDomain
0x180011f1e  mov     ebx, eax
0x180011f20  test    eax, eax
0x180011f22  js      loc_180012354
0x180011f28  mov     rax, [rbp+4Fh+var_70]
0x180011f2c  cmp     dword ptr [rax], 4
0x180011f2f  jnz     loc_180012339
0x180011f35  mov     r8, [rbp+4Fh+var_78]
0x180011f39  lea     r9, [rbp+4Fh+var_98]
0x180011f3d  mov     rcx, [rbp+4Fh+var_88]
0x180011f41  mov     edx, 2000Ch
0x180011f46  mov     [rbp+4Fh+var_98], rdi
0x180011f4a  mov     r8d, [r8]
0x180011f4d  call    cs:__imp_SamOpenAlias
0x180011f53  mov     ebx, eax
0x180011f55  test    eax, eax
0x180011f57  js      loc_180012302
0x180011f5d  mov     rcx, [rbp+4Fh+var_98]
0x180011f61  lea     r8, [rbp+4Fh+var_80]
0x180011f65  mov     edx, r14d
0x180011f68  mov     [rbp+4Fh+var_80], rdi
0x180011f6c  call    cs:__imp_SamQueryInformationAlias
0x180011f72  mov     dil, 2
0x180011f75  lea     r15, WPP_GLOBAL_Control
0x180011f7c  mov     ebx, eax
0x180011f7e  mov     r14d, 10000000h
0x180011f84  test    eax, eax
0x180011f86  js      short loc_180011FBB
0x180011f88  mov     ecx, 28h ; '('; cb
0x180011f8d  mov     ebx, 8007000Eh
0x180011f92  call    cs:__imp_CoTaskMemAlloc
0x180011f98  mov     [r12], rax
0x180011f9c  test    rax, rax
0x180011f9f  jz      short loc_180011FAF
0x180011fa1  mov     rcx, [rbp+4Fh+var_80]; struct _UNICODE_STRING *
0x180011fa5  mov     rdx, rax; DestinationString
0x180011fa8  call    ?CopyAliasStructure@@YAJQEAU_ALIAS_GENERAL_INFORMATION@@PEAU1@@Z; CopyAliasStructure(_ALIAS_GENERAL_INFORMATION * const,_ALIAS_GENERAL_INFORMATION *)
0x180011fad  mov     ebx, eax
0x180011faf  mov     rcx, [rbp+4Fh+var_80]
0x180011fb3  call    cs:__imp_SamFreeMemory
0x180011fb9  jmp     short loc_180011FE5
0x180011fbb  or      ebx, r14d
0x180011fbe  mov     rcx, cs:WPP_GLOBAL_Control
0x180011fc5  cmp     rcx, r15
0x180011fc8  jz      short loc_180011FEC
0x180011fca  test    [rcx+1Ch], dil
0x180011fce  jz      short loc_180011FEC
0x180011fd0  mov     rcx, [rcx+10h]
0x180011fd4  mov     edx, 39h ; '9'
0x180011fd9  mov     r9, rsi
0x180011fdc  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x180011fe0  call    WPP_SF_ZD
0x180011fe5  mov     rcx, cs:WPP_GLOBAL_Control
0x180011fec  test    ebx, ebx
0x180011fee  js      loc_1800122D6
0x180011ff4  mov     rcx, [rbp+4Fh+var_98]
0x180011ff8  lea     r8, [rbp+4Fh+pSid2]
0x180011ffc  mov     edx, 5
0x180012001  mov     [rbp+4Fh+pSid2], 0
0x180012009  call    cs:__imp_SamQueryInformationAlias
0x18001200f  mov     ebx, eax
0x180012011  test    eax, eax
0x180012013  js      short loc_180012048
0x180012015  mov     ecx, 18h; cb
0x18001201a  mov     ebx, 8007000Eh
0x18001201f  call    cs:__imp_CoTaskMemAlloc
0x180012025  mov     [r13+0], rax
0x180012029  test    rax, rax
0x18001202c  jz      short loc_18001203C
0x18001202e  mov     rcx, [rbp+4Fh+pSid2]; struct _ALIAS_EXTENDED_INFORMATION *
0x180012032  mov     rdx, rax; struct _ALIAS_EXTENDED_INFORMATION *
0x180012035  call    ?CopyAliasExtStructure@@YAJQEAU_ALIAS_EXTENDED_INFORMATION@@PEAU1@@Z; CopyAliasExtStructure(_ALIAS_EXTENDED_INFORMATION * const,_ALIAS_EXTENDED_INFORMATION *)
0x18001203a  mov     ebx, eax
0x18001203c  mov     rcx, [rbp+4Fh+pSid2]
0x180012040  call    cs:__imp_SamFreeMemory
0x180012046  jmp     short loc_180012072
0x180012048  or      ebx, r14d
0x18001204b  mov     rcx, cs:WPP_GLOBAL_Control
0x180012052  cmp     rcx, r15
0x180012055  jz      short loc_180012079
0x180012057  test    [rcx+1Ch], dil
0x18001205b  jz      short loc_180012079
0x18001205d  mov     rcx, [rcx+10h]
0x180012061  mov     edx, 3Ah ; ':'
0x180012066  mov     r9, rsi
0x180012069  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x18001206d  call    WPP_SF_ZD
0x180012072  mov     rcx, cs:WPP_GLOBAL_Control
0x180012079  test    ebx, ebx
0x18001207b  js      loc_1800122D6
0x180012081  mov     rcx, [rbp+4Fh+var_98]
0x180012085  lea     r8, [rbp+4Fh+Count]
0x180012089  lea     rdx, [rbp+4Fh+Sids]
0x18001208d  mov     [rbp+4Fh+Count], 0
0x180012094  mov     [rbp+4Fh+Sids], 0
0x18001209c  call    cs:__imp_SamGetMembersInAlias
0x1800120a2  test    eax, eax
0x1800120a4  js      loc_1800122B8
0x1800120aa  mov     ecx, [rbp+4Fh+Count]; Count
0x1800120ad  test    ecx, ecx
0x1800120af  jz      loc_1800122AC
0x1800120b5  mov     rdx, [rbp+4Fh+Sids]; Sids
0x1800120b9  lea     r8, [rbp+4Fh+pSid2]; struct _SID_INFO **
0x1800120bd  mov     [rbp+4Fh+pSid2], 0
0x1800120c5  call    ?LookupSids@@YAJKPEAPEAXPEAPEAU_SID_INFO@@@Z; LookupSids(ulong,void * *,_SID_INFO * *)
0x1800120ca  mov     rsi, [rbp+4Fh+pSid2]
0x1800120ce  mov     ebx, eax
0x1800120d0  test    eax, eax
0x1800120d2  js      loc_180012279
0x1800120d8  test    rsi, rsi
0x1800120db  jz      loc_180012279
0x1800120e1  lea     rcx, [rbp+4Fh+pSid2]
0x1800120e5  mov     [rbp+4Fh+pSid2], 0
0x1800120ed  mov     [rbp+4Fh+pv], 0
0x1800120f5  call    CSGetAccountDomainSid
0x1800120fa  mov     ebx, eax
0x1800120fc  test    eax, eax
0x1800120fe  js      loc_1800122A3
0x180012104  lea     rcx, [rbp+4Fh+pv]
0x180012108  call    CSGetBuiltInDomainSid
0x18001210d  mov     r13, [rbp+4Fh+pSid2]
0x180012111  mov     ebx, eax
0x180012113  test    eax, eax
0x180012115  js      loc_18001226E
0x18001211b  mov     eax, [rbp+4Fh+Count]
0x18001211e  xor     r12d, r12d
0x180012121  test    eax, eax
0x180012123  jz      loc_180012257
0x180012129  lea     r14, [r12+r12*2]
0x18001212d  mov     dword ptr [rbp+4Fh+pSid2], 0
0x180012134  cmp     qword ptr [rsi+r14*8+10h], 0
0x18001213a  jz      loc_18001224B
0x180012140  mov     rcx, [rbp+4Fh+Sids]
0x180012144  lea     rdx, [rbp+4Fh+var_A4]
0x180012148  mov     [rbp+4Fh+var_A4], 0
0x18001214f  mov     rcx, [rcx+r12*8]
0x180012153  call    cs:__imp_LsaLookupUserAccountType
0x180012159  xor     ebx, ebx
0x18001215b  cmp     [rbp+4Fh+var_A4], 5
0x18001215f  mov     [rbp+4Fh+p], rbx
0x180012163  jz      short loc_1800121CF
0x180012165  mov     rcx, [rbp+4Fh+Sids]
0x180012169  lea     r8, [rbp+4Fh+pSid2]; pfEqual
0x18001216d  mov     rdx, r13; pSid2
0x180012170  mov     rcx, [rcx+r12*8]; pSid1
0x180012174  call    cs:__imp_EqualDomainSid
0x18001217a  test    eax, eax
0x18001217c  jz      short loc_1800121A4
0x18001217e  cmp     dword ptr [rbp+4Fh+pSid2], ebx
0x180012181  jz      short loc_1800121A4
0x180012183  mov     rcx, r13
0x180012186  mov     rdx, [rsi+r14*8+10h]
0x18001218b  lea     rax, [rbp+4Fh+p]
0x18001218f  mov     r8d, 1
0x180012195  mov     [rsp+0E0h+var_C0], rax
0x18001219a  xor     r9d, r9d
0x18001219d  call    CSGetAccountPropertyStore
0x1800121a2  jmp     short loc_180012219
0x1800121a4  cmp     [rbp+4Fh+var_A4], 5
0x1800121a8  jz      short loc_1800121CF
0x1800121aa  mov     rcx, [rbp+4Fh+Sids]
0x1800121ae  lea     r8, [rbp+4Fh+pSid2]; pfEqual
0x1800121b2  mov     rdx, [rbp+4Fh+pv]; pSid2
0x1800121b6  mov     rcx, [rcx+r12*8]; pSid1
0x1800121ba  call    cs:__imp_EqualDomainSid
0x1800121c0  test    eax, eax
0x1800121c2  jz      short loc_1800121CF
0x1800121c4  cmp     dword ptr [rbp+4Fh+pSid2], ebx
0x1800121c7  jz      short loc_1800121CF
0x1800121c9  mov     rcx, [rbp+4Fh+pv]
0x1800121cd  jmp     short loc_180012186
0x1800121cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800121d6  cmp     rcx, r15
0x1800121d9  jz      short loc_1800121EF
0x1800121db  test    byte ptr [rcx+1Ch], 4
0x1800121df  jz      short loc_1800121EF
0x1800121e1  mov     r9, [rsi+r14*8+10h]
0x1800121e6  mov     rcx, [rcx+10h]
0x1800121ea  call    WPP_SF_S
0x1800121ef  mov     rcx, [rbp+4Fh+Sids]
0x1800121f3  lea     r8, [rbp+4Fh+p]; struct IPropertyStore **
0x1800121f7  movups  xmm0, xmmword ptr [rsi+r14*8]
0x1800121fc  lea     rdx, [rbp+4Fh+var_60]; struct _SID_INFO
0x180012200  movsd   xmm1, qword ptr [rsi+r14*8+10h]
0x180012207  mov     rcx, [rcx+r12*8]; pSid
0x18001220b  movaps  xmmword ptr [rbp+4Fh+var_60.pSid], xmm0
0x18001220f  movsd   [rbp+4Fh+var_60.pwzClass], xmm1
0x180012214  call    ?CreateReadOnlyPropertyStore@@YAJPEAXU_SID_INFO@@PEAPEAUIPropertyStore@@@Z; CreateReadOnlyPropertyStore(void *,_SID_INFO,IPropertyStore * *)
0x180012219  mov     ebx, eax
0x18001221b  test    eax, eax
0x18001221d  js      short loc_18001223F
0x18001221f  mov     r8, [rbp+4Fh+p]; p
0x180012223  mov     edx, 7FFFFFFFh; i
0x180012228  mov     rcx, [rbp+4Fh+hdpa]; hdpa
0x18001222c  call    cs:__imp_DPA_InsertPtr
0x180012232  cmp     eax, 0FFFFFFFFh
0x180012235  jz      short loc_18001223F
0x180012237  mov     [rbp+4Fh+p], 0
0x18001223f  lea     rcx, [rbp+4Fh+p]
0x180012243  call    ??$SafeRelease@UIPropertyStore@@@@YAXPEAPEAUIPropertyStore@@@Z; SafeRelease<IPropertyStore>(IPropertyStore * *)
0x180012248  mov     eax, [rbp+4Fh+Count]
0x18001224b  inc     r12d
0x18001224e  cmp     r12d, eax
0x180012251  jb      loc_180012129
0x180012257  mov     rcx, [rbp+4Fh+hdpa]
0x18001225b  xor     eax, eax
0x18001225d  cmp     [rcx], eax
0x18001225f  mov     rcx, [rbp+4Fh+pv]; pv
0x180012263  cmovle  eax, ebx
0x180012266  mov     ebx, eax
0x180012268  call    cs:__imp_CoTaskMemFree
0x18001226e  mov     rcx, r13; pv
0x180012271  call    cs:__imp_CoTaskMemFree
0x180012277  jmp     short loc_1800122A3
0x180012279  mov     rcx, cs:WPP_GLOBAL_Control
0x180012280  cmp     rcx, r15
0x180012283  jz      short loc_1800122A3
0x180012285  test    [rcx+1Ch], dil
0x180012289  jz      short loc_1800122A3
0x18001228b  mov     rcx, [rcx+10h]
0x18001228f  lea     r8, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids
0x180012296  mov     edx, 3Ch ; '<'
0x18001229b  mov     r9d, eax
0x18001229e  call    WPP_SF_d
0x1800122a3  mov     rcx, rsi; pv
0x1800122a6  call    cs:__imp_CoTaskMemFree
0x1800122ac  mov     rcx, [rbp+4Fh+Sids]
0x1800122b0  call    cs:__imp_SamFreeMemory
0x1800122b6  jmp     short loc_1800122F6
0x1800122b8  mov     ebx, eax
0x1800122ba  or      ebx, r14d
0x1800122bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800122c4  cmp     rcx, r15
0x1800122c7  jz      short loc_1800122F6
0x1800122c9  test    [rcx+1Ch], dil
0x1800122cd  jz      short loc_1800122F6
0x1800122cf  mov     edx, 3Dh ; '='
0x1800122d4  jmp     short loc_1800122E6
0x1800122d6  cmp     rcx, r15
0x1800122d9  jz      short loc_1800122F6
0x1800122db  test    [rcx+1Ch], dil
0x1800122df  jz      short loc_1800122F6
0x1800122e1  mov     edx, 3Eh ; '>'
0x1800122e6  mov     rcx, [rcx+10h]
0x1800122ea  mov     r9, rsi
0x1800122ed  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x1800122f1  call    WPP_SF_ZD
0x1800122f6  mov     rcx, [rbp+4Fh+var_98]
0x1800122fa  call    cs:__imp_SamCloseHandle
0x180012300  jmp     short loc_18001233E
0x180012302  bts     ebx, 1Ch
0x180012306  mov     rcx, cs:WPP_GLOBAL_Control
0x18001230d  lea     r15, WPP_GLOBAL_Control
0x180012314  cmp     rcx, r15
0x180012317  jz      short loc_18001233E
0x180012319  mov     dil, 2
0x18001231c  test    [rcx+1Ch], dil
0x180012320  jz      short loc_18001233E
  ... truncated ...
```
