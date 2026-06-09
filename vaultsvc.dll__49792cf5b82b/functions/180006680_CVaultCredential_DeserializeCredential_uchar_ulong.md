# CVaultCredential::DeserializeCredential(uchar *,ulong)

- ea: `0x180006680`
- end: `0x180006d1c`
- name: `?DeserializeCredential@CVaultCredential@@AEAAKPEAEK@Z`
- size: `1692`
- prototype: `unsigned int __fastcall(CVaultCredential *__hidden this, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180010520`

## callees

- `0x180003140`
- `0x180003810`
- `0x180005b04`
- `0x180005d68`
- `0x180005df0`
- `0x180006610`
- `0x180006680`
- `0x180006d30`
- `0x180012210`
- `0x18002b3d0`
- `0x18003a580`
- `0x18003b7b0`
- `0x18003b7d8`
- `0x18004b43c`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006798`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800068bd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006aad`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006be3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006798`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800068bd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006aad`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006be3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006ae3`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18000676f`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18000676f`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
unsigned int __fastcall CVaultCredential::DeserializeCredential(
        CVaultCredential *this,
        unsigned __int8 *a2,
        unsigned int a3)
{
  char v6; // r12
  __int64 v7; // r9
  SIZE_T v8; // rsi
  unsigned __int8 *v9; // r14
  unsigned int v10; // r13d
  unsigned int i; // ebx
  HLOCAL v12; // rax
  __int64 v13; // rdx
  unsigned __int8 *v14; // r14
  unsigned int result; // eax
  __int16 v16; // ax
  unsigned __int8 *v17; // rdi
  unsigned int v18; // ebx
  unsigned int j; // esi
  __int64 v20; // rsi
  unsigned __int8 *v21; // rdi
  unsigned int v22; // ebx
  struct CVaultSid *v23; // rax
  struct CVaultSid *v24; // r14
  __int64 v25; // rcx
  __int64 *v26; // rax
  __int64 v27; // rcx
  const void *v28; // rsi
  size_t v29; // rdi
  void *v30; // rbx
  size_t v31; // r8
  unsigned __int64 v32; // rbx
  int SecurityDescriptor; // ebx
  char *v34; // rax
  PSECURITY_DESCRIPTOR *v35; // rdi
  unsigned int v36; // eax
  _WORD *v38; // rax
  unsigned int Source2; // [rsp+20h] [rbp-A8h] BYREF
  unsigned __int8 *v40; // [rsp+28h] [rbp-A0h] BYREF
  int v41; // [rsp+30h] [rbp-98h] BYREF
  int v42; // [rsp+34h] [rbp-94h] BYREF
  struct CVaultSid *v43[2]; // [rsp+38h] [rbp-90h] BYREF
  int v44; // [rsp+48h] [rbp-80h]
  _BYTE pIdentifierAuthority[39]; // [rsp+50h] [rbp-78h] BYREF
  int v46; // [rsp+78h] [rbp-50h]

  v41 = 0;
  v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 32LL))(*((_QWORD *)this + 1));
  v42 = 0;
  if ( a3 < 8 )
    return 122;
  *((_QWORD *)this + 6) = *(_QWORD *)a2;
  if ( a3 - 8 < 4 )
    return 122;
  *((_DWORD *)this + 45) = *((_DWORD *)a2 + 2);
  if ( a3 - 12 < 4 )
    return 122;
  v7 = *((unsigned int *)a2 + 3);
  LODWORD(v7) = v7 & 0xFFFFFEFF;
  *((_DWORD *)this + 44) = v7;
  if ( (v7 & 0xEFFF0800) != 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_49114d8a939f3a3d6447d5db247a3e77_Traceguids, v7);
    return 87;
  }
  LOWORD(Source2) = 0;
  if ( a3 - 16 < 4 )
    return 122;
  v8 = *((unsigned int *)a2 + 4);
  v9 = a2 + 20;
  v10 = a3 - 20;
  if ( (unsigned int)v8 >= 2 )
  {
    if ( (unsigned int)v8 <= v10 )
    {
      if ( (v8 & 1) == 0 )
      {
        for ( i = 0; i < (unsigned int)v8; i += 2 )
        {
          if ( RtlCompareMemory(&v9[i], &Source2, 2u) == 2 )
          {
            if ( i != v8 - 2 )
              return 1358;
            v12 = LocalAlloc(0x40u, v8);
            *((_QWORD *)this + 2) = v12;
            if ( !v12 )
              return 14;
            memcpy_0(v12, v9, v8);
            v9 += v8;
            v10 -= v8;
            if ( !*((_QWORD *)this + 2) )
              goto LABEL_56;
            goto LABEL_16;
          }
        }
      }
      return 1358;
    }
    return 122;
  }
  *((_QWORD *)this + 2) = 0;
LABEL_56:
  v38 = LocalAlloc(0x40u, 2u);
  *((_QWORD *)this + 2) = v38;
  if ( !v38 )
    return 14;
  *v38 = 0;
LABEL_16:
  if ( v10 < 4 )
    return 122;
  v13 = *(unsigned int *)v9;
  v14 = v9 + 4;
  if ( v10 - 4 < (unsigned int)v13 )
    return 122;
  v40 = &v14[v13];
  Source2 = v10 - 4 - v13;
  if ( (v6 & 1) != 0
    || (result = CVaultCredential::VaultDeserializeCredElement(
                   &v40,
                   &Source2,
                   *((struct IVaultSchema **)this + 1),
                   *((struct CVaultCredElement **)this + 3))) == 0 )
  {
    result = CVaultCredential::VaultDeserializeCredElement(
               &v40,
               &Source2,
               *((struct IVaultSchema **)this + 1),
               *((struct CVaultCredElement **)this + 4));
    if ( !result )
    {
      result = CVaultCredential::VaultDeserializeCredElement(
                 &v40,
                 &Source2,
                 *((struct IVaultSchema **)this + 1),
                 *((struct CVaultCredElement **)this + 5));
      if ( !result )
      {
        if ( Source2 >= 2 )
        {
          v16 = *(_WORD *)v40;
          v17 = v40 + 2;
          v40 += 2;
          v18 = Source2 - 2;
          Source2 -= 2;
          if ( v16 != *((_WORD *)this + 74) )
            return 1358;
          for ( j = 0; j < *((unsigned __int16 *)this + 74); ++j )
          {
            v32 = (unsigned __int64)j << 6;
            result = CVaultCredential::VaultDeserializeCredElement(
                       &v40,
                       &Source2,
                       *((struct IVaultSchema **)this + 1),
                       (struct CVaultCredElement *)(v32 + *((_QWORD *)this + 19)));
            if ( result )
              return result;
            (*(void (__fastcall **)(unsigned __int64, int *))(*(_QWORD *)(v32 + *((_QWORD *)this + 19)) + 8LL))(
              v32 + *((_QWORD *)this + 19),
              &v41);
            try
            {
              LODWORD(v43[0]) = v41;
              v43[1] = (struct CVaultSid *)(v32 + *((_QWORD *)this + 19));
              std::_Tree<std::_Tmap_traits<enum VAULT_SCHEMA_ELEMENT_ID,CVaultCredElement *,std::less<enum VAULT_SCHEMA_ELEMENT_ID>,std::allocator<std::pair<enum VAULT_SCHEMA_ELEMENT_ID const,CVaultCredElement *>>,0>>::_Emplace<std::pair<enum VAULT_SCHEMA_ELEMENT_ID,CVaultCredElement *>>(
                (char *)this + 160,
                pIdentifierAuthority,
                v43);
            }
            catch ( std::bad_alloc )
            {
              return 14;
            }
            v17 = v40;
            v18 = Source2;
          }
          *(_OWORD *)v43 = 0;
          if ( v18 < 4 )
            return 122;
          v20 = *(unsigned int *)v17;
          v21 = v17 + 4;
          v40 = v21;
          v22 = v18 - 4;
          Source2 = v22;
          if ( (unsigned int)v20 > v22 )
            return 122;
          if ( (_DWORD)v20 )
          {
            v23 = (struct CVaultSid *)LocalAlloc(0x40u, (unsigned int)v20);
            v24 = v23;
            if ( !v23 )
              return 14;
            memcpy_0(v23, v21, (unsigned int)v20);
            v40 = &v21[v20];
            Source2 = v22 - v20;
          }
          else
          {
            v24 = v43[1];
          }
          *((_DWORD *)this + 50) = v20;
          *((_QWORD *)this + 24) = v24;
          result = CVaultCredential::InitializeInternalProperties((char *)this + 184);
          if ( result )
            return result;
          result = CVaultGenericPropertyCollection<enum ECredPropertyId,5>::DeserializeCollection(
                     *((_QWORD *)this + 23),
                     &v40,
                     &Source2);
          if ( result )
            return result;
          memset(pIdentifierAuthority, 0, 24);
          v25 = *((_QWORD *)this + 23);
          if ( *(_DWORD *)(*(_QWORD *)(v25 + 16) + 4LL) == 8 )
          {
            v26 = *(__int64 **)(v25 + 8);
            v27 = *v26;
            if ( *(_DWORD *)(*v26 + 8) == 8 )
            {
              v28 = *(const void **)(v27 + 24);
              v29 = *(unsigned int *)(v27 + 16);
              v30 = (void *)*((_QWORD *)this + 27);
              if ( v30 )
              {
                (**(void (__fastcall ***)(_QWORD, _QWORD))v30)(*((_QWORD *)this + 27), 0);
                VaultFreeInternal(v30);
              }
              *((_QWORD *)this + 27) = 0;
              v43[1] = 0;
              v44 = 0;
              v43[0] = (struct CVaultSid *)AutoDereference<IVaultKeyManager>;
              memset(pIdentifierAuthority, 0, sizeof(pIdentifierAuthority));
              if ( (unsigned int)v29 < 0x27 )
              {
                v31 = v29;
                v46 = v29;
              }
              else
              {
                v31 = 39;
                v46 = 39;
              }
              memcpy_0(pIdentifierAuthority, v28, v31);
              SecurityDescriptor = CVaultPackageId::ComposeSid((PSID_IDENTIFIER_AUTHORITY)pIdentifierAuthority, &v43[1]);
              if ( SecurityDescriptor )
              {
                CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(v43);
                return SecurityDescriptor;
              }
              *(_QWORD *)pIdentifierAuthority = CVaultRoamingCredential::FreeRoamingCredential;
              *(_QWORD *)&pIdentifierAuthority[8] = 0;
              *(_DWORD *)&pIdentifierAuthority[16] = 0;
              v34 = (char *)LocalAlloc(0x40u, 0x50u);
              v35 = (PSECURITY_DESCRIPTOR *)v34;
              if ( v34 )
              {
                *(_QWORD *)v34 = &CVaultSecurable::`vftable';
                *((_DWORD *)v34 + 2) = 3;
                *(_OWORD *)(v34 + 12) = xmmword_1800515B8;
                *((_QWORD *)v34 + 5) = 0;
                *((_DWORD *)v34 + 12) = 0;
                *((_QWORD *)v34 + 4) = LocalFree;
                *((_QWORD *)v34 + 8) = 0;
                *((_DWORD *)v34 + 18) = 0;
                *((_QWORD *)v34 + 7) = AutoDereference<IVaultKeyManager>;
                CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(pIdentifierAuthority);
                *(_QWORD *)&pIdentifierAuthority[8] = v35;
                SecurityDescriptor = CVaultSecurable::CreateSecurityDescriptor(v35, v43[1]);
                if ( !SecurityDescriptor )
                {
                  *(_QWORD *)&pIdentifierAuthority[8] = 0;
                  *((_QWORD *)this + 27) = v35;
                  CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(pIdentifierAuthority);
                  SecurityDescriptor = 0;
                  goto LABEL_46;
                }
              }
              else if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
              {
                SecurityDescriptor = 14;
              }
              else
              {
                SecurityDescriptor = 14;
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids);
              }
              CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(pIdentifierAuthority);
LABEL_46:
              CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(v43);
              if ( !SecurityDescriptor )
              {
                v36 = (*(__int64 (__fastcall **)(CVaultCredential *, int *))(*(_QWORD *)this + 248LL))(this, &v42);
                SecurityDescriptor = v36;
                if ( !v36 )
                {
                  if ( v42 )
                    *((_DWORD *)this + 44) |= 0x100u;
                  return 0;
                }
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    32,
                    WPP_49114d8a939f3a3d6447d5db247a3e77_Traceguids,
                    v36);
                  return SecurityDescriptor;
                }
              }
              return SecurityDescriptor;
            }
          }
          return 87;
        }
        return 122;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180006680  push    rbx
0x180006682  push    rsi
0x180006683  push    rdi
0x180006684  push    r12
0x180006686  push    r13
0x180006688  push    r14
0x18000668a  push    r15
0x18000668c  sub     rsp, 90h
0x180006693  mov     rax, cs:__security_cookie
0x18000669a  xor     rax, rsp
0x18000669d  mov     [rsp+0C8h+var_48], rax
0x1800066a5  mov     ebx, r8d
0x1800066a8  mov     r14, rdx
0x1800066ab  mov     r15, rcx
0x1800066ae  xor     edi, edi
0x1800066b0  mov     [rsp+0C8h+var_98], edi
0x1800066b4  mov     rcx, [rcx+8]
0x1800066b8  mov     rax, [rcx]
0x1800066bb  mov     rax, [rax+20h]
0x1800066bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066c4  mov     r12d, eax
0x1800066c7  mov     [rsp+0C8h+var_94], edi
0x1800066cb  cmp     ebx, 8
0x1800066ce  jb      loc_180006D12
0x1800066d4  mov     rcx, [r14]
0x1800066d7  mov     [r15+30h], rcx
0x1800066db  lea     edx, [rbx-8]
0x1800066de  cmp     edx, 4
0x1800066e1  jb      loc_180006D12
0x1800066e7  mov     ecx, [r14+8]
0x1800066eb  mov     [r15+0B4h], ecx
0x1800066f2  add     edx, 0FFFFFFFCh
0x1800066f5  cmp     edx, 4
0x1800066f8  jb      loc_180006D12
0x1800066fe  mov     r9d, [r14+0Ch]
0x180006702  btr     r9d, 8
0x180006707  mov     [r15+0B0h], r9d
0x18000670e  test    r9d, 0EFFF0800h
0x180006715  jnz     loc_180006C1D
0x18000671b  add     edx, 0FFFFFFFCh
0x18000671e  mov     word ptr [rsp+0C8h+Source2], di
0x180006723  cmp     edx, 4
0x180006726  jb      loc_180006C55
0x18000672c  mov     esi, [r14+10h]
0x180006730  add     r14, 14h
0x180006734  lea     r13d, [rdx-4]
0x180006738  cmp     esi, 2
0x18000673b  jb      loc_180006BD5
0x180006741  cmp     esi, r13d
0x180006744  ja      loc_180006C55
0x18000674a  test    sil, 1
0x18000674e  jnz     loc_180006BCC
0x180006754  mov     ebx, edi
0x180006756  cmp     ebx, esi
0x180006758  jnb     loc_180006BCC
0x18000675e  mov     edi, ebx
0x180006760  lea     rcx, [rdi+r14]; Source1
0x180006764  mov     r8d, 2; Length
0x18000676a  lea     rdx, [rsp+0C8h+Source2]; Source2
0x18000676f  call    cs:__imp_RtlCompareMemory
0x180006775  cmp     rax, 2
0x180006779  jz      short loc_180006780
0x18000677b  add     ebx, 2
0x18000677e  jmp     short loc_180006756
0x180006780  mov     rbx, rsi
0x180006783  lea     rax, [rsi-2]
0x180006787  cmp     rdi, rax
0x18000678a  jnz     loc_180006BCC
0x180006790  mov     rdx, rbx; uBytes
0x180006793  mov     ecx, 40h ; '@'; uFlags
0x180006798  call    cs:__imp_LocalAlloc
0x18000679e  mov     [r15+10h], rax
0x1800067a2  test    rax, rax
0x1800067a5  jz      loc_180006BFA
0x1800067ab  mov     r8, rbx; Size
0x1800067ae  mov     rdx, r14; Src
0x1800067b1  mov     rcx, rax; void *
0x1800067b4  call    memcpy_0
0x1800067b9  add     r14, rbx
0x1800067bc  sub     r13d, esi
0x1800067bf  cmp     qword ptr [r15+10h], 0
0x1800067c4  jz      loc_180006C5F
0x1800067ca  cmp     r13d, 4
0x1800067ce  jb      loc_180006D12
0x1800067d4  mov     edx, [r14]
0x1800067d7  add     r14, 4
0x1800067db  lea     ecx, [r13-4]
0x1800067df  cmp     ecx, edx
0x1800067e1  jb      loc_180006D12
0x1800067e7  lea     rax, [r14+rdx]
0x1800067eb  mov     [rsp+0C8h+var_A0], rax
0x1800067f0  sub     ecx, edx
0x1800067f2  mov     [rsp+0C8h+Source2], ecx
0x1800067f6  test    r12b, 1
0x1800067fa  jz      loc_180006BAB
0x180006800  mov     r9, [r15+20h]; struct CVaultCredElement *
0x180006804  mov     r8, [r15+8]; struct IVaultSchema *
0x180006808  lea     rdx, [rsp+0C8h+Source2]; unsigned int *
0x18000680d  lea     rcx, [rsp+0C8h+var_A0]; unsigned __int8 **
0x180006812  call    ?VaultDeserializeCredElement@CVaultCredential@@CAKAEAPEAEAEAKPEAUIVaultSchema@@AEAVCVaultCredElement@@@Z; CVaultCredential::VaultDeserializeCredElement(uchar * &,ulong &,IVaultSchema *,CVaultCredElement &)
0x180006817  test    eax, eax
0x180006819  jnz     loc_180006B88
0x18000681f  mov     r9, [r15+28h]; struct CVaultCredElement *
0x180006823  mov     r8, [r15+8]; struct IVaultSchema *
0x180006827  lea     rdx, [rsp+0C8h+Source2]; unsigned int *
0x18000682c  lea     rcx, [rsp+0C8h+var_A0]; unsigned __int8 **
0x180006831  call    ?VaultDeserializeCredElement@CVaultCredential@@CAKAEAPEAEAEAKPEAUIVaultSchema@@AEAVCVaultCredElement@@@Z; CVaultCredential::VaultDeserializeCredElement(uchar * &,ulong &,IVaultSchema *,CVaultCredElement &)
0x180006836  test    eax, eax
0x180006838  jnz     loc_180006B88
0x18000683e  mov     ebx, [rsp+0C8h+Source2]
0x180006842  cmp     ebx, 2
0x180006845  jb      loc_180006D12
0x18000684b  mov     rdi, [rsp+0C8h+var_A0]
0x180006850  movzx   eax, word ptr [rdi]
0x180006853  add     rdi, 2
0x180006857  mov     [rsp+0C8h+var_A0], rdi
0x18000685c  add     ebx, 0FFFFFFFEh
0x18000685f  mov     [rsp+0C8h+Source2], ebx
0x180006863  cmp     ax, [r15+94h]
0x18000686b  jnz     loc_180006C66
0x180006871  xor     esi, esi
0x180006873  movzx   eax, word ptr [r15+94h]
0x18000687b  cmp     esi, eax
0x18000687d  jb      loc_1800069DB
0x180006883  xorps   xmm0, xmm0
0x180006886  movups  xmmword ptr [rsp+0C8h+var_90], xmm0
0x18000688b  cmp     ebx, 4
0x18000688e  jb      loc_180006C7A
0x180006894  mov     esi, [rdi]
0x180006896  add     rdi, 4
0x18000689a  mov     [rsp+0C8h+var_A0], rdi
0x18000689f  add     ebx, 0FFFFFFFCh
0x1800068a2  mov     [rsp+0C8h+Source2], ebx
0x1800068a6  cmp     esi, ebx
0x1800068a8  ja      loc_180006C7A
0x1800068ae  test    esi, esi
0x1800068b0  jz      loc_180006C03
0x1800068b6  mov     edx, esi; uBytes
0x1800068b8  mov     ecx, 40h ; '@'; uFlags
0x1800068bd  call    cs:__imp_LocalAlloc
0x1800068c3  mov     r14, rax
0x1800068c6  test    rax, rax
0x1800068c9  jz      loc_180006C81
0x1800068cf  mov     r8d, esi; Size
0x1800068d2  mov     rdx, rdi; Src
0x1800068d5  mov     rcx, rax; void *
0x1800068d8  call    memcpy_0
0x1800068dd  lea     rax, [rdi+rsi]
0x1800068e1  mov     [rsp+0C8h+var_A0], rax
0x1800068e6  sub     ebx, esi
0x1800068e8  mov     [rsp+0C8h+Source2], ebx
0x1800068ec  mov     [r15+0C8h], esi
0x1800068f3  mov     [r15+0C0h], r14
0x1800068fa  lea     rcx, [r15+0B8h]
0x180006901  call    ?InitializeInternalProperties@CVaultCredential@@SAKPEAPEAV?$CVaultGenericPropertyCollection@W4ECredPropertyId@@$04@@@Z; CVaultCredential::InitializeInternalProperties(CVaultGenericPropertyCollection<ECredPropertyId,5> * *)
0x180006906  test    eax, eax
0x180006908  jnz     loc_180006B88
0x18000690e  lea     r8, [rsp+0C8h+Source2]
0x180006913  lea     rdx, [rsp+0C8h+var_A0]
0x180006918  mov     rcx, [r15+0B8h]
0x18000691f  call    ?DeserializeCollection@?$CVaultGenericPropertyCollection@W4ECredPropertyId@@$04@@QEAAKAEAPEAEAEAK@Z; CVaultGenericPropertyCollection<ECredPropertyId,5>::DeserializeCollection(uchar * &,ulong &)
0x180006924  test    eax, eax
0x180006926  jnz     loc_180006B88
0x18000692c  xorps   xmm0, xmm0
0x18000692f  xor     eax, eax
0x180006931  movups  [rsp+0C8h+pIdentifierAuthority], xmm0
0x180006936  mov     qword ptr [rsp+0C8h+var_68], rax
0x18000693b  mov     rcx, [r15+0B8h]
0x180006942  mov     rax, [rcx+10h]
0x180006946  cmp     dword ptr [rax+4], 8
0x18000694a  jnz     loc_180006C4B
0x180006950  mov     rax, [rcx+8]
0x180006954  mov     rcx, [rax]
0x180006957  cmp     dword ptr [rcx+8], 8
0x18000695b  jnz     loc_180006C4B
0x180006961  mov     rsi, [rcx+18h]
0x180006965  mov     edi, [rcx+10h]
0x180006968  mov     rbx, [r15+0D8h]
0x18000696f  test    rbx, rbx
0x180006972  jz      short loc_18000698C
0x180006974  mov     rax, [rbx]
0x180006977  xor     edx, edx
0x180006979  mov     rcx, rbx
0x18000697c  mov     rax, [rax]
0x18000697f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006984  mov     rcx, rbx; hMem
0x180006987  call    ?VaultFreeInternal@@YAXPEAE@Z; VaultFreeInternal(uchar *)
0x18000698c  mov     eax, edi
0x18000698e  xor     r12d, r12d
0x180006991  mov     [r15+0D8h], r12
0x180006998  mov     [rsp+0C8h+var_90+8], r12
0x18000699d  mov     [rsp+0C8h+var_80], r12d
0x1800069a2  lea     r14, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x1800069a9  mov     [rsp+0C8h+var_90], r14
0x1800069ae  xorps   xmm0, xmm0
0x1800069b1  xor     ecx, ecx
0x1800069b3  movups  [rsp+0C8h+pIdentifierAuthority], xmm0
0x1800069b8  movups  xmmword ptr [rsp+0C8h+var_68], xmm0
0x1800069bd  mov     qword ptr [rsp+0C8h+var_68+0Fh], rcx
0x1800069c2  cmp     eax, 27h ; '''
0x1800069c5  jb      loc_180006A60
0x1800069cb  mov     r8d, 27h ; '''
0x1800069d1  mov     [rsp+0C8h+var_50], r8d
0x1800069d6  jmp     loc_180006A67
0x1800069db  mov     ebx, esi
0x1800069dd  shl     rbx, 6
0x1800069e1  mov     r9, [r15+98h]
0x1800069e8  add     r9, rbx; struct CVaultCredElement *
0x1800069eb  mov     r8, [r15+8]; struct IVaultSchema *
0x1800069ef  lea     rdx, [rsp+0C8h+Source2]; unsigned int *
0x1800069f4  lea     rcx, [rsp+0C8h+var_A0]; unsigned __int8 **
0x1800069f9  call    ?VaultDeserializeCredElement@CVaultCredential@@CAKAEAPEAEAEAKPEAUIVaultSchema@@AEAVCVaultCredElement@@@Z; CVaultCredential::VaultDeserializeCredElement(uchar * &,ulong &,IVaultSchema *,CVaultCredElement &)
0x1800069fe  test    eax, eax
0x180006a00  jnz     loc_180006B88
0x180006a06  mov     rcx, [r15+98h]
0x180006a0d  add     rcx, rbx
0x180006a10  mov     rax, [rcx]
0x180006a13  lea     rdx, [rsp+0C8h+var_98]
0x180006a18  mov     rax, [rax+8]
0x180006a1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a21  nop
0x180006a22  mov     eax, [rsp+0C8h+var_98]
0x180006a26  mov     dword ptr [rsp+0C8h+var_90], eax
0x180006a2a  mov     rcx, [r15+98h]
0x180006a31  add     rcx, rbx
0x180006a34  mov     [rsp+0C8h+var_90+8], rcx
0x180006a39  lea     rcx, [r15+0A0h]
0x180006a40  lea     r8, [rsp+0C8h+var_90]
0x180006a45  lea     rdx, [rsp+0C8h+pIdentifierAuthority]
0x180006a4a  call    ??$_Emplace@U?$pair@W4VAULT_SCHEMA_ELEMENT_ID@@PEAVCVaultCredElement@@@std@@@?$_Tree@V?$_Tmap_traits@W4VAULT_SCHEMA_ELEMENT_ID@@PEAVCVaultCredElement@@U?$less@W4VAULT_SCHEMA_ELEMENT_ID@@@std@@V?$allocator@U?$pair@$$CBW4VAULT_SCHEMA_ELEMENT_ID@@PEAVCVaultCredElement@@@std@@@4@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBW4VAULT_SCHEMA_ELEMENT_ID@@PEAVCVaultCredElement@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@W4VAULT_SCHEMA_ELEMENT_ID@@PEAVCVaultCredElement@@@1@@Z; std::_Tree<std::_Tmap_traits<VAULT_SCHEMA_ELEMENT_ID,CVaultCredElement *,std::less<VAULT_SCHEMA_ELEMENT_ID>,std::allocator<std::pair<VAULT_SCHEMA_ELEMENT_ID const,CVaultCredElement *>>,0>>::_Emplace<std::pair<VAULT_SCHEMA_ELEMENT_ID,CVaultCredElement *>>(std::pair<VAULT_SCHEMA_ELEMENT_ID,CVaultCredElement *> &&)
0x180006a4f  nop
0x180006a50  inc     esi
0x180006a52  mov     rdi, [rsp+0C8h+var_A0]
0x180006a57  mov     ebx, [rsp+0C8h+Source2]
0x180006a5b  jmp     loc_180006873
0x180006a60  mov     r8, rdi; Size
0x180006a63  mov     [rsp+0C8h+var_50], edi
0x180006a67  mov     rdx, rsi; Src
0x180006a6a  lea     rcx, [rsp+0C8h+pIdentifierAuthority]; void *
0x180006a6f  call    memcpy_0
0x180006a74  lea     rdx, [rsp+0C8h+var_90+8]; struct CVaultSid **
0x180006a79  lea     rcx, [rsp+0C8h+pIdentifierAuthority]; pIdentifierAuthority
0x180006a7e  call    ?ComposeSid@CVaultPackageId@@QEAAKPEAPEAVCVaultSid@@@Z; CVaultPackageId::ComposeSid(CVaultSid * *)
0x180006a83  mov     ebx, eax
0x180006a85  test    eax, eax
0x180006a87  jnz     loc_180006C88
0x180006a8d  lea     rax, ?FreeRoamingCredential@CVaultRoamingCredential@@SAXPEAV1@@Z; CVaultRoamingCredential::FreeRoamingCredential(CVaultRoamingCredential *)
0x180006a94  mov     qword ptr [rsp+0C8h+pIdentifierAuthority], rax
0x180006a99  mov     qword ptr [rsp+0C8h+pIdentifierAuthority+8], r12
0x180006a9e  mov     dword ptr [rsp+0C8h+var_68], r12d
0x180006aa3  mov     edx, 50h ; 'P'; uBytes
0x180006aa8  mov     ecx, 40h ; '@'; uFlags
0x180006aad  call    cs:__imp_LocalAlloc
0x180006ab3  mov     rdi, rax
0x180006ab6  test    rax, rax
0x180006ab9  jz      loc_180006C9A
0x180006abf  lea     rax, ??_7CVaultSecurable@@6B@; const CVaultSecurable::`vftable'
0x180006ac6  mov     [rdi], rax
0x180006ac9  mov     dword ptr [rdi+8], 3
0x180006ad0  movups  xmm0, cs:xmmword_1800515B8
0x180006ad7  movups  xmmword ptr [rdi+0Ch], xmm0
0x180006adb  mov     [rdi+28h], r12
0x180006adf  mov     [rdi+30h], r12d
0x180006ae3  mov     rax, cs:__imp_LocalFree
0x180006aea  mov     [rdi+20h], rax
0x180006aee  mov     [rdi+40h], r12
0x180006af2  mov     [rdi+48h], r12d
0x180006af6  mov     [rdi+38h], r14
0x180006afa  lea     rcx, [rsp+0C8h+pIdentifierAuthority]
0x180006aff  call    ?Delete@?$CVaultAutoPtr@PEAVCUserVault@@XPEAV1@$0A@@@QEAAXXZ; CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(void)
0x180006b04  mov     qword ptr [rsp+0C8h+pIdentifierAuthority+8], rdi
0x180006b09  mov     rdx, [rsp+0C8h+var_90+8]; struct CVaultSid *
0x180006b0e  mov     rcx, rdi; this
0x180006b11  call    ?CreateSecurityDescriptor@CVaultSecurable@@QEAAKPEAVCVaultSid@@@Z; CVaultSecurable::CreateSecurityDescriptor(CVaultSid *)
0x180006b16  mov     ebx, eax
0x180006b18  test    eax, eax
0x180006b1a  jnz     loc_180006C0D
0x180006b20  mov     qword ptr [rsp+0C8h+pIdentifierAuthority+8], r12
0x180006b25  mov     [r15+0D8h], rdi
0x180006b2c  lea     rcx, [rsp+0C8h+pIdentifierAuthority]
0x180006b31  call    ?Delete@?$CVaultAutoPtr@PEAVCUserVault@@XPEAV1@$0A@@@QEAAXXZ; CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(void)
0x180006b36  nop
0x180006b37  mov     ebx, r12d
0x180006b3a  lea     rdi, WPP_GLOBAL_Control
0x180006b41  lea     rcx, [rsp+0C8h+var_90]
0x180006b46  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180006b4b  nop
0x180006b4c  test    ebx, ebx
0x180006b4e  jnz     loc_180006C93
0x180006b54  mov     rax, [r15]
0x180006b57  lea     rdx, [rsp+0C8h+var_94]
0x180006b5c  mov     rcx, r15
0x180006b5f  mov     rax, [rax+0F8h]
0x180006b66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b6b  mov     ebx, eax
0x180006b6d  test    eax, eax
0x180006b6f  jnz     loc_180006CE1
0x180006b75  cmp     [rsp+0C8h+var_94], eax
0x180006b79  jz      short loc_180006B86
0x180006b7b  or      dword ptr [r15+0B0h], 100h
  ... truncated ...
```
