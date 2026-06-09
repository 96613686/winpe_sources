# CSamPropStore::Commit(void)

- ea: `0x180014d90`
- end: `0x18001534d`
- name: `?Commit@CSamPropStore@@UEAAJXZ`
- size: `1469`
- prototype: `__int64 __fastcall(struct IPropertyStore *this)`
- caller_count: `0`
- callee_count: `22`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1800020d0`
- `0x180007300`
- `0x180008c10`
- `0x18000bbd0`
- `0x18000c240`
- `0x18000cb84`
- `0x18000fc2c`
- `0x18000fce4`
- `0x18001066c`
- `0x1800106d0`
- `0x180010744`
- `0x180011e80`
- `0x1800126c0`
- `0x180012acc`
- `0x1800133e0`
- `0x180013580`
- `0x180014d90`
- `0x180015660`
- `0x180015d30`
- `0x180016330`
- `0x1800167d4`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001527c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001528c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001527c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001528c`

## pseudocode

```c
__int64 __fastcall CSamPropStore::Commit(struct IPropertyStore *this)
{
  struct IPropertyStoreVtbl *lpVtbl; // rcx
  int Group; // edi
  unsigned int v4; // esi
  __int64 v5; // rdx
  __int64 v6; // r8
  struct IPropertyStoreVtbl *v7; // rcx
  int v8; // eax
  struct IPropertyStore *v9; // rsi
  int User; // eax
  struct _USER_ALL_INFORMATION *v11; // r15
  struct IPropertyStoreVtbl *v12; // r12
  UNICODE_STRING *p_UserName; // r14
  int v14; // eax
  struct IPropertyStore *v15; // rsi
  unsigned int v16; // r14d
  LPVOID *v17; // r15
  struct IPropertyStoreVtbl *v18; // rdx
  struct IPropertyStoreVtbl *v19; // rcx
  struct IPropertyStoreVtbl *v20; // rcx
  struct _ALIAS_GENERAL_INFORMATION *v21; // r13
  struct IPropertyStoreVtbl *hdpa; // rax
  _BYTE *v23; // r12
  unsigned int i; // esi
  unsigned int v26; // [rsp+38h] [rbp-C8h]
  char v27[4]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v28; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v29; // [rsp+58h] [rbp-A8h] BYREF
  int v30; // [rsp+5Ch] [rbp-A4h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE DestinationString[40]; // [rsp+68h] [rbp-98h] BYREF
  __int128 v33; // [rsp+90h] [rbp-70h] BYREF
  __int64 v34; // [rsp+A0h] [rbp-60h]
  __int128 v35; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v36; // [rsp+B8h] [rbp-48h]
  __int128 v37; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v38; // [rsp+D0h] [rbp-30h]
  _USER_ALL_INFORMATION v39; // [rsp+E0h] [rbp-20h] BYREF
  _DWORD v40[44]; // [rsp+220h] [rbp+120h] BYREF

  lpVtbl = this[12].lpVtbl;
  Group = 0;
  v28 = 0;
  if ( lpVtbl )
  {
    Group = (*((__int64 (__fastcall **)(struct IPropertyStoreVtbl *, unsigned int *))lpVtbl->QueryInterface + 3))(
              lpVtbl,
              &v28);
    if ( Group >= 0 )
    {
      v4 = v28;
      if ( v28 )
      {
        v39.LastLogon.LowPart = 0;
        memset_0((char *)&v39.LastLogon.QuadPart + 4, 0, 0x138u);
        memset_0(v40, 0, 0xA8u);
        memset(DestinationString, 0, sizeof(DestinationString));
        v34 = 0;
        v33 = 0;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_ddd(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, v6, v4, this[10].lpVtbl, HIDWORD(this[10].lpVtbl));
        v7 = this[12].lpVtbl;
        v36 = 0;
        v38 = 0;
        v35 = 0;
        v37 = 0;
        (*((void (__fastcall **)(struct IPropertyStoreVtbl *, __int128 *, __int128 *))v7->QueryInterface + 5))(
          v7,
          &PKEY_SAM_DateChanged,
          &v35);
        (*((void (__fastcall **)(struct IPropertyStoreVtbl *, __int128 *, __int128 *))this[12].lpVtbl->QueryInterface + 5))(
          this[12].lpVtbl,
          &PKEY_SAM_Version,
          &v37);
        if ( HIDWORD(this[10].lpVtbl) != 2
          || (Group = CopyAliasStructure((struct _UNICODE_STRING *)this[5].lpVtbl, DestinationString), Group >= 0)
          && (Group = CopyAliasExtStructure(
                        (struct _ALIAS_EXTENDED_INFORMATION *const)this[6].lpVtbl,
                        (struct _ALIAS_EXTENDED_INFORMATION *)&v33),
              Group >= 0) )
        {
          *(_DWORD *)v27 = 0;
          v8 = CSamPropStore::_CopyCacheIntoStruct(
                 this,
                 &v39,
                 (struct _USER_EXTENDED_INFORMATION *)v40,
                 (struct _ALIAS_GENERAL_INFORMATION *)DestinationString,
                 (struct _ALIAS_EXTENDED_INFORMATION *)&v33,
                 (unsigned int *)v27);
          Group = v8;
          if ( v8 < 0 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              WPP_SF_ddD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                18,
                WPP_7df418057efb386bc095915f6151cd01_Traceguids,
                LODWORD(this[10].lpVtbl),
                HIDWORD(this[10].lpVtbl),
                v8);
          }
          else if ( HIDWORD(this[10].lpVtbl) == 1 )
          {
            v9 = this + 3;
            User = CSUpdateOrCreateUser(
                     this[11].lpVtbl,
                     (struct _UNICODE_STRING *)&this[3].lpVtbl->SetValue,
                     (__int64)&v39,
                     v40,
                     (unsigned int)this[8].lpVtbl,
                     v27[0]);
            Group = User;
            if ( User >= 0 )
            {
              v11 = (struct _USER_ALL_INFORMATION *)v9->lpVtbl;
              v12 = this[4].lpVtbl;
              p_UserName = &v39.UserName;
              this[4].lpVtbl = 0;
              v9->lpVtbl = 0;
              if ( !v39.UserName.Length )
                p_UserName = &v11->UserName;
              Group = CSGetUserAccountInfo(
                        this[11].lpVtbl,
                        (__int64)&this[4],
                        (__int64)p_UserName,
                        (struct _USER_ALL_INFORMATION **)&this[3],
                        (struct _USER_EXTENDED_INFORMATION **)&this[4],
                        &this[9],
                        (_DWORD *)&this[9].lpVtbl + 1);
              if ( Group < 0 )
              {
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                {
                  WPP_SF_ZddD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    14,
                    (unsigned int)WPP_7df418057efb386bc095915f6151cd01_Traceguids,
                    (_DWORD)p_UserName,
                    (char)this[10].lpVtbl,
                    HIDWORD(this[10].lpVtbl),
                    Group);
                }
              }
              else
              {
                LODWORD(this[10].lpVtbl) = v9->lpVtbl[4].Release;
                HIDWORD(this[10].lpVtbl) = 1;
                HIDWORD(this[8].lpVtbl) = 0;
              }
              FreeUserStructure(v11, 1);
              FreeUserExtStructure((struct _USER_EXTENDED_INFORMATION *)v12, 1);
            }
            else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                   && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              WPP_SF_ZddD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                13,
                (unsigned int)WPP_7df418057efb386bc095915f6151cd01_Traceguids,
                LODWORD(v9->lpVtbl) + 48,
                (char)this[10].lpVtbl,
                HIDWORD(this[10].lpVtbl),
                User);
            }
            FreeUserStructure(&v39, 0);
            FreeUserExtStructure((struct _USER_EXTENDED_INFORMATION *)v40, 0);
          }
          else if ( HIDWORD(this[10].lpVtbl) == 2 )
          {
            pv = 0;
            v29 = 0;
            v30 = 0;
            v14 = CSamPropStore::_CopyGroupMembersFromCache(
                    (CSamPropStore *)this,
                    (unsigned __int16 ***)&pv,
                    &v29,
                    &v30);
            Group = v14;
            if ( v14 < 0 )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                WPP_SF_ZddD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  17,
                  (unsigned int)WPP_7df418057efb386bc095915f6151cd01_Traceguids,
                  this[5].lpVtbl,
                  (char)this[10].lpVtbl,
                  HIDWORD(this[10].lpVtbl),
                  v14);
              }
            }
            else
            {
              v15 = this + 5;
              v16 = v29;
              v17 = (LPVOID *)pv;
              v18 = this[5].lpVtbl;
              v19 = this[11].lpVtbl;
              v26 = (unsigned int)this[8].lpVtbl;
              *(_DWORD *)&DestinationString[16] = v29;
              Group = CSUpdateOrCreateGroup(
                        v19,
                        (__int64)v18,
                        DestinationString,
                        (__int64)&v33,
                        (unsigned __int16 **)pv,
                        v29,
                        v30,
                        v26,
                        v27[0]);
              if ( Group < 0 )
              {
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                {
                  WPP_SF_ZddD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    16,
                    (unsigned int)WPP_7df418057efb386bc095915f6151cd01_Traceguids,
                    v15->lpVtbl,
                    (char)this[10].lpVtbl,
                    HIDWORD(this[10].lpVtbl),
                    Group);
                }
              }
              else
              {
                v20 = this[7].lpVtbl;
                v21 = (struct _ALIAS_GENERAL_INFORMATION *)v15->lpVtbl;
                pv = this[6].lpVtbl;
                v15->lpVtbl = 0;
                this[6].lpVtbl = 0;
                if ( v20 )
                {
                  g_pfn_DPA_DestroyCallback(
                    (HDPA)v20,
                    CDPA_Base<IPropertyStore,CTContainer_PolicyRelease<IPropertyStore>>::_StandardDestroyCB,
                    0);
                  this[7].lpVtbl = 0;
                }
                hdpa = (struct IPropertyStoreVtbl *)g_pfn_DPA_Create(1);
                this[7].lpVtbl = hdpa;
                if ( hdpa )
                {
                  v23 = DestinationString;
                  if ( !*(_WORD *)DestinationString )
                    v23 = v21;
                  Group = CSGetGroupAccountInfo(
                            this[11].lpVtbl,
                            (__int64)v23,
                            (struct _UNICODE_STRING **)&this[5],
                            (struct _ALIAS_EXTENDED_INFORMATION **)&this[6],
                            (HDPA)hdpa);
                  if ( Group < 0 )
                  {
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                    {
                      WPP_SF_ZddD(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        15,
                        (unsigned int)WPP_7df418057efb386bc095915f6151cd01_Traceguids,
                        (_DWORD)v23,
                        (char)this[10].lpVtbl,
                        HIDWORD(this[10].lpVtbl),
                        Group);
                    }
                  }
                  else
                  {
                    HIDWORD(this[10].lpVtbl) = 2;
                    HIDWORD(this[8].lpVtbl) = 0;
                  }
                }
                else
                {
                  Group = -2147024882;
                }
                FreeAliasStructure(v21, 1);
                FreeAliasExtStructure((struct _ALIAS_EXTENDED_INFORMATION *)pv, 1);
              }
              for ( i = 0; i < v16; ++i )
                CoTaskMemFree(v17[i]);
              CoTaskMemFree(v17);
            }
            FreeAliasStructure((struct _ALIAS_GENERAL_INFORMATION *)DestinationString, 0);
            FreeAliasExtStructure((struct _ALIAS_EXTENDED_INFORMATION *)&v33, 0);
          }
        }
        CSamPropStore::_NotifyShell((CSamPropStore *)this);
      }
    }
  }
  return (unsigned int)Group;
}

```

## disassembly

```asm
0x180014d90  push    rbp
0x180014d92  push    rbx
0x180014d93  push    rsi
0x180014d94  push    rdi
0x180014d95  push    r12
0x180014d97  push    r13
0x180014d99  push    r14
0x180014d9b  push    r15
0x180014d9d  lea     rbp, [rsp-1E8h]
0x180014da5  sub     rsp, 2E8h
0x180014dac  mov     rax, cs:__security_cookie
0x180014db3  xor     rax, rsp
0x180014db6  mov     [rbp+220h+var_50], rax
0x180014dbd  xor     r12d, r12d
0x180014dc0  mov     rbx, rcx
0x180014dc3  mov     rcx, [rcx+60h]
0x180014dc7  mov     edi, r12d
0x180014dca  mov     [rsp+320h+var_2CC], r12d
0x180014dcf  test    rcx, rcx
0x180014dd2  jz      loc_180015328
0x180014dd8  mov     rax, [rcx]
0x180014ddb  lea     rdx, [rsp+320h+var_2CC]
0x180014de0  mov     rax, [rax+18h]
0x180014de4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014de9  mov     edi, eax
0x180014deb  test    eax, eax
0x180014ded  js      loc_180015328
0x180014df3  mov     esi, [rsp+320h+var_2CC]
0x180014df7  test    esi, esi
0x180014df9  jz      loc_180015328
0x180014dff  xor     edx, edx; Val
0x180014e01  mov     dword ptr [rbp+220h+var_240.LastLogon], r12d
0x180014e05  mov     r8d, 138h; Size
0x180014e0b  lea     rcx, [rbp+220h+var_240.LastLogon+4]; void *
0x180014e0f  call    memset_0
0x180014e14  xor     edx, edx; Val
0x180014e16  lea     rcx, [rbp+220h+var_100]; void *
0x180014e1d  mov     r8d, 0A8h; Size
0x180014e23  call    memset_0
0x180014e28  xorps   xmm0, xmm0
0x180014e2b  mov     [rsp+320h+DestinationString.Length], r12w
0x180014e31  xor     eax, eax
0x180014e33  movups  [rsp+320h+var_2A6], xmm0
0x180014e38  mov     qword ptr [rbp+220h+var_2A6+0Eh], rax
0x180014e3c  movups  xmmword ptr [rsp+320h+DestinationString.MaximumLength], xmm0
0x180014e41  mov     [rbp+220h+var_280], rax
0x180014e45  movups  [rbp+220h+var_290], xmm0
0x180014e49  mov     rcx, cs:WPP_GLOBAL_Control
0x180014e50  lea     r14, WPP_GLOBAL_Control
0x180014e57  cmp     rcx, r14
0x180014e5a  jz      short loc_180014E7C
0x180014e5c  test    byte ptr [rcx+1Ch], 8
0x180014e60  jz      short loc_180014E7C
0x180014e62  mov     eax, [rbx+54h]
0x180014e65  mov     r9d, esi
0x180014e68  mov     rcx, [rcx+10h]
0x180014e6c  mov     dword ptr [rsp+320h+var_2F8], eax
0x180014e70  mov     eax, [rbx+50h]
0x180014e73  mov     dword ptr [rsp+320h+hdpa], eax
0x180014e77  call    WPP_SF_ddd
0x180014e7c  mov     rcx, [rbx+60h]
0x180014e80  lea     r8, [rbp+220h+var_278]
0x180014e84  xor     eax, eax
0x180014e86  lea     rdx, PKEY_SAM_DateChanged
0x180014e8d  mov     [rbp+220h+var_268], rax
0x180014e91  xorps   xmm0, xmm0
0x180014e94  mov     [rbp+220h+var_250], rax
0x180014e98  xorps   xmm1, xmm1
0x180014e9b  movups  [rbp+220h+var_278], xmm0
0x180014e9f  movups  [rbp+220h+var_260], xmm1
0x180014ea3  mov     rax, [rcx]
0x180014ea6  mov     rax, [rax+28h]
0x180014eaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014eaf  mov     rcx, [rbx+60h]
0x180014eb3  lea     r8, [rbp+220h+var_260]
0x180014eb7  lea     rdx, PKEY_SAM_Version
0x180014ebe  mov     rax, [rcx]
0x180014ec1  mov     rax, [rax+28h]
0x180014ec5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014eca  mov     r13d, 2
0x180014ed0  cmp     [rbx+54h], r13d
0x180014ed4  jnz     short loc_180014F05
0x180014ed6  mov     rcx, [rbx+28h]; struct _UNICODE_STRING *
0x180014eda  lea     rdx, [rsp+320h+DestinationString]; DestinationString
0x180014edf  call    ?CopyAliasStructure@@YAJQEAU_ALIAS_GENERAL_INFORMATION@@PEAU1@@Z; CopyAliasStructure(_ALIAS_GENERAL_INFORMATION * const,_ALIAS_GENERAL_INFORMATION *)
0x180014ee4  mov     edi, eax
0x180014ee6  test    eax, eax
0x180014ee8  js      loc_180015320
0x180014eee  mov     rcx, [rbx+30h]; struct _ALIAS_EXTENDED_INFORMATION *
0x180014ef2  lea     rdx, [rbp+220h+var_290]; struct _ALIAS_EXTENDED_INFORMATION *
0x180014ef6  call    ?CopyAliasExtStructure@@YAJQEAU_ALIAS_EXTENDED_INFORMATION@@PEAU1@@Z; CopyAliasExtStructure(_ALIAS_EXTENDED_INFORMATION * const,_ALIAS_EXTENDED_INFORMATION *)
0x180014efb  mov     edi, eax
0x180014efd  test    eax, eax
0x180014eff  js      loc_180015320
0x180014f05  lea     rax, [rsp+320h+var_2D0]
0x180014f0a  mov     dword ptr [rsp+320h+var_2D0], r12d
0x180014f0f  mov     [rsp+320h+var_2F8], rax; unsigned int *
0x180014f14  lea     r9, [rsp+320h+DestinationString]; struct _ALIAS_GENERAL_INFORMATION *
0x180014f19  lea     rax, [rbp+220h+var_290]
0x180014f1d  mov     rcx, rbx; this
0x180014f20  lea     r8, [rbp+220h+var_100]; struct _USER_EXTENDED_INFORMATION *
0x180014f27  mov     [rsp+320h+hdpa], rax; struct _ALIAS_EXTENDED_INFORMATION *
0x180014f2c  lea     rdx, [rbp+220h+var_240]; struct _USER_ALL_INFORMATION *
0x180014f30  call    ?_CopyCacheIntoStruct@CSamPropStore@@AEAAJPEAU_USER_ALL_INFORMATION@@PEAU_USER_EXTENDED_INFORMATION@@PEAU_ALIAS_GENERAL_INFORMATION@@PEAU_ALIAS_EXTENDED_INFORMATION@@PEAK@Z; CSamPropStore::_CopyCacheIntoStruct(_USER_ALL_INFORMATION *,_USER_EXTENDED_INFORMATION *,_ALIAS_GENERAL_INFORMATION *,_ALIAS_EXTENDED_INFORMATION *,ulong *)
0x180014f35  mov     edi, eax
0x180014f37  test    eax, eax
0x180014f39  js      loc_1800152EA
0x180014f3f  cmp     dword ptr [rbx+54h], 1
0x180014f43  jnz     loc_1800150AE
0x180014f49  mov     eax, dword ptr [rsp+320h+var_2D0]
0x180014f4d  lea     rsi, [rbx+18h]
0x180014f51  mov     rdx, [rsi]
0x180014f54  lea     r9, [rbp+220h+var_100]
0x180014f5b  mov     rcx, [rbx+58h]; void *
0x180014f5f  lea     r8, [rbp+220h+var_240]
0x180014f63  mov     dword ptr [rsp+320h+var_2F8], eax; int
0x180014f67  add     rdx, 30h ; '0'; struct _UNICODE_STRING *
0x180014f6b  mov     eax, [rbx+40h]
0x180014f6e  mov     dword ptr [rsp+320h+hdpa], eax; unsigned int
0x180014f72  call    CSUpdateOrCreateUser
0x180014f77  mov     edi, eax
0x180014f79  test    eax, eax
0x180014f7b  jns     short loc_180014FCA
0x180014f7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180014f84  cmp     rcx, r14
0x180014f87  jz      loc_180015090
0x180014f8d  test    [rcx+1Ch], r13b
0x180014f91  jz      loc_180015090
0x180014f97  mov     r9, [rsi]
0x180014f9a  lea     r8, WPP_7df418057efb386bc095915f6151cd01_Traceguids
0x180014fa1  mov     rcx, [rcx+10h]
0x180014fa5  add     r9, 30h ; '0'
0x180014fa9  mov     [rsp+320h+var_2F0], eax
0x180014fad  mov     edx, 0Dh
0x180014fb2  mov     eax, [rbx+54h]
0x180014fb5  mov     dword ptr [rsp+320h+var_2F8], eax
0x180014fb9  mov     eax, [rbx+50h]
0x180014fbc  mov     dword ptr [rsp+320h+hdpa], eax
0x180014fc0  call    WPP_SF_ZddD
0x180014fc5  jmp     loc_180015090
0x180014fca  mov     r15, [rsi]
0x180014fcd  lea     rdx, [rbx+20h]
0x180014fd1  mov     r12, [rdx]
0x180014fd4  lea     r14, [rbp+220h+var_240.UserName]
0x180014fd8  xor     r13d, r13d
0x180014fdb  mov     [rdx], r13
0x180014fde  mov     [rsi], r13
0x180014fe1  cmp     [rbp+220h+var_240.UserName.Length], r13w
0x180014fe6  ja      short loc_180014FEC
0x180014fe8  lea     r14, [r15+30h]
0x180014fec  lea     rax, [rbx+4Ch]
0x180014ff0  mov     r9, rsi
0x180014ff3  mov     qword ptr [rsp+320h+var_2F0], rax
0x180014ff8  lea     rcx, [rbx+48h]
0x180014ffc  mov     [rsp+320h+var_2F8], rcx
0x180015001  mov     r8, r14
0x180015004  mov     rcx, [rbx+58h]
0x180015008  mov     [rsp+320h+hdpa], rdx
0x18001500d  call    CSGetUserAccountInfo
0x180015012  mov     edi, eax
0x180015014  test    eax, eax
0x180015016  js      short loc_180015031
0x180015018  mov     rax, [rsi]
0x18001501b  mov     ecx, [rax+110h]
0x180015021  mov     [rbx+50h], ecx
0x180015024  mov     dword ptr [rbx+54h], 1
0x18001502b  mov     [rbx+44h], r13d
0x18001502f  jmp     short loc_180015074
0x180015031  mov     rcx, cs:WPP_GLOBAL_Control
0x180015038  lea     rax, WPP_GLOBAL_Control
0x18001503f  cmp     rcx, rax
0x180015042  jz      short loc_180015074
0x180015044  test    byte ptr [rcx+1Ch], 2
0x180015048  jz      short loc_180015074
0x18001504a  mov     eax, [rbx+54h]
0x18001504d  lea     r8, WPP_7df418057efb386bc095915f6151cd01_Traceguids
0x180015054  mov     rcx, [rcx+10h]
0x180015058  mov     edx, 0Eh
0x18001505d  mov     [rsp+320h+var_2F0], edi
0x180015061  mov     r9, r14
0x180015064  mov     dword ptr [rsp+320h+var_2F8], eax
0x180015068  mov     eax, [rbx+50h]
0x18001506b  mov     dword ptr [rsp+320h+hdpa], eax
0x18001506f  call    WPP_SF_ZddD
0x180015074  mov     r13d, 1
0x18001507a  mov     rcx, r15; pv
0x18001507d  mov     edx, r13d; int
0x180015080  call    ?FreeUserStructure@@YAJPEAU_USER_ALL_INFORMATION@@H@Z; FreeUserStructure(_USER_ALL_INFORMATION *,int)
0x180015085  mov     edx, r13d; int
0x180015088  mov     rcx, r12; pv
0x18001508b  call    ?FreeUserExtStructure@@YAJPEAU_USER_EXTENDED_INFORMATION@@H@Z; FreeUserExtStructure(_USER_EXTENDED_INFORMATION *,int)
0x180015090  xor     edx, edx; int
0x180015092  lea     rcx, [rbp+220h+var_240]; pv
0x180015096  call    ?FreeUserStructure@@YAJPEAU_USER_ALL_INFORMATION@@H@Z; FreeUserStructure(_USER_ALL_INFORMATION *,int)
0x18001509b  xor     edx, edx; int
0x18001509d  lea     rcx, [rbp+220h+var_100]; pv
0x1800150a4  call    ?FreeUserExtStructure@@YAJPEAU_USER_EXTENDED_INFORMATION@@H@Z; FreeUserExtStructure(_USER_EXTENDED_INFORMATION *,int)
0x1800150a9  jmp     loc_180015320
0x1800150ae  cmp     [rbx+54h], r13d
0x1800150b2  jnz     loc_180015320
0x1800150b8  lea     r9, [rsp+320h+var_2C4]; int *
0x1800150bd  mov     [rsp+320h+pv], r12
0x1800150c2  lea     r8, [rsp+320h+var_2C8]; unsigned int *
0x1800150c7  mov     [rsp+320h+var_2C8], r12d
0x1800150cc  lea     rdx, [rsp+320h+pv]; unsigned __int16 ***
0x1800150d1  mov     [rsp+320h+var_2C4], r12d
0x1800150d6  mov     rcx, rbx; this
0x1800150d9  call    ?_CopyGroupMembersFromCache@CSamPropStore@@AEAAJPEAPEAPEAGPEAKPEAH@Z; CSamPropStore::_CopyGroupMembersFromCache(ushort * * *,ulong *,int *)
0x1800150de  mov     edi, eax
0x1800150e0  test    eax, eax
0x1800150e2  js      loc_180015294
0x1800150e8  mov     eax, dword ptr [rsp+320h+var_2D0]
0x1800150ec  lea     rsi, [rbx+28h]
0x1800150f0  mov     r14d, [rsp+320h+var_2C8]
0x1800150f5  lea     r9, [rbp+220h+var_290]
0x1800150f9  mov     r15, [rsp+320h+pv]
0x1800150fe  lea     r8, [rsp+320h+DestinationString]
0x180015103  mov     rdx, [rsi]
0x180015106  mov     rcx, [rbx+58h]; void *
0x18001510a  mov     dword ptr [rsp+320h+var_2E0], eax; char
0x18001510e  mov     eax, [rbx+40h]
0x180015111  mov     [rsp+320h+var_2E8], eax; unsigned int
0x180015115  mov     eax, [rsp+320h+var_2C4]
0x180015119  mov     [rsp+320h+var_2F0], eax; int
0x18001511d  mov     dword ptr [rsp+320h+var_2F8], r14d; unsigned int
0x180015122  mov     [rsp+320h+hdpa], r15; unsigned __int16 **
0x180015127  mov     [rsp+78h], r14d
0x18001512c  call    CSUpdateOrCreateGroup
0x180015131  mov     edi, eax
0x180015133  test    eax, eax
0x180015135  js      loc_18001522B
0x18001513b  mov     rcx, [rbx+38h]; hdpa
0x18001513f  lea     rdi, [rbx+30h]
0x180015143  mov     rax, [rdi]
0x180015146  mov     r13, [rsi]
0x180015149  mov     [rsp+320h+pv], rax
0x18001514e  mov     [rsi], r12
0x180015151  mov     [rdi], r12
0x180015154  test    rcx, rcx
0x180015157  jz      short loc_18001516D
0x180015159  xor     r8d, r8d; pData
0x18001515c  lea     rdx, ?_StandardDestroyCB@?$CDPA_Base@UIPropertyStore@@V?$CTContainer_PolicyRelease@UIPropertyStore@@@@@@CAHPEAUIPropertyStore@@PEAX@Z; pfnCB
0x180015163  call    cs:g_pfn_DPA_DestroyCallback
0x180015169  mov     [rbx+38h], r12
0x18001516d  mov     ecx, 1; cItemGrow
0x180015172  call    cs:g_pfn_DPA_Create
0x180015178  mov     [rbx+38h], rax
0x18001517c  test    rax, rax
0x18001517f  jnz     short loc_18001518B
0x180015181  mov     edi, 8007000Eh
0x180015186  jmp     loc_18001520E
0x18001518b  xor     ecx, ecx
0x18001518d  mov     [rsp+320h+hdpa], rax; hdpa
0x180015192  cmp     [rsp+320h+DestinationString.Length], cx
0x180015197  lea     r12, [rsp+320h+DestinationString]
0x18001519c  mov     rcx, [rbx+58h]; int
0x1800151a0  mov     r9, rdi; int
0x1800151a3  cmovbe  r12, r13
0x1800151a7  mov     r8, rsi; int
0x1800151aa  mov     rdx, r12; int
0x1800151ad  call    CSGetGroupAccountInfo
0x1800151b2  mov     edi, eax
0x1800151b4  test    eax, eax
0x1800151b6  js      short loc_1800151C8
0x1800151b8  xor     r12d, r12d
0x1800151bb  mov     dword ptr [rbx+54h], 2
0x1800151c2  mov     [rbx+44h], r12d
0x1800151c6  jmp     short loc_18001520E
0x1800151c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800151cf  lea     rax, WPP_GLOBAL_Control
0x1800151d6  cmp     rcx, rax
0x1800151d9  jz      short loc_18001520B
0x1800151db  test    byte ptr [rcx+1Ch], 2
0x1800151df  jz      short loc_18001520B
0x1800151e1  mov     eax, [rbx+54h]
0x1800151e4  lea     r8, WPP_7df418057efb386bc095915f6151cd01_Traceguids
0x1800151eb  mov     rcx, [rcx+10h]
0x1800151ef  mov     edx, 0Fh
0x1800151f4  mov     [rsp+320h+var_2F0], edi
0x1800151f8  mov     r9, r12
0x1800151fb  mov     dword ptr [rsp+320h+var_2F8], eax
0x1800151ff  mov     eax, [rbx+50h]
0x180015202  mov     dword ptr [rsp+320h+hdpa], eax
0x180015206  call    WPP_SF_ZddD
0x18001520b  xor     r12d, r12d
0x18001520e  mov     esi, 1
0x180015213  mov     rcx, r13; pv
0x180015216  mov     edx, esi; int
0x180015218  call    ?FreeAliasStructure@@YAJPEAU_ALIAS_GENERAL_INFORMATION@@H@Z; FreeAliasStructure(_ALIAS_GENERAL_INFORMATION *,int)
0x18001521d  mov     rcx, [rsp+320h+pv]; pv
0x180015222  mov     edx, esi; int
0x180015224  call    ?FreeAliasExtStructure@@YAJPEAU_ALIAS_EXTENDED_INFORMATION@@H@Z; FreeAliasExtStructure(_ALIAS_EXTENDED_INFORMATION *,int)
0x180015229  jmp     short loc_18001526E
0x18001522b  mov     rcx, cs:WPP_GLOBAL_Control
0x180015232  lea     rax, WPP_GLOBAL_Control
0x180015239  cmp     rcx, rax
0x18001523c  jz      short loc_18001526E
0x18001523e  test    [rcx+1Ch], r13b
0x180015242  jz      short loc_18001526E
0x180015244  mov     eax, [rbx+54h]
  ... truncated ...
```
