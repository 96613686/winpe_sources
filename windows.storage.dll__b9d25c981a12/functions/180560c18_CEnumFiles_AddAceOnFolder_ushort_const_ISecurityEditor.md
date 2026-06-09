# CEnumFiles::_AddAceOnFolder(ushort const *,ISecurityEditor *)

- ea: `0x180560c18`
- end: `0x180560f46`
- name: `?_AddAceOnFolder@CEnumFiles@@AEAAJPEBGPEAUISecurityEditor@@@Z`
- size: `814`
- prototype: `__int64 __fastcall(CEnumFiles *__hidden this, const unsigned __int16 *, struct ISecurityEditor *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18056151c`

## callees

- `0x18004e06c`
- `0x1800fe62c`
- `0x180109b7c`
- `0x1802965ac`
- `0x1803b1f60`
- `0x1803b243c`
- `0x1805602f0`
- `0x18056031c`
- `0x1805606dc`
- `0x18056087c`
- `0x180560c18`
- `0x180561178`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180560e7d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180560e8d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180560e9c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180560eb9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180560e7d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180560e8d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180560e9c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180560eb9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180560ec9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180560ec9`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180560cc8`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180560cc8`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180560de7`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180560de7`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180560dce`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180560dce`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180560e27`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180560e27`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180560c8d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180560c8d`

## pseudocode

```c
__int64 __fastcall CEnumFiles::_AddAceOnFolder(
        CEnumFiles *this,
        const unsigned __int16 *a2,
        struct ISecurityEditor *a3)
{
  __int64 v3; // rax
  int Error; // ebx
  PSECURITY_DESCRIPTOR v7; // rsi
  struct _ACL *v8; // r14
  struct _ACL *v9; // rax
  int v10; // r9d
  CAceList *v11; // rdi
  unsigned int v12; // edx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // r9
  PACL v16; // r15
  void *v17; // rbx
  __int64 v18; // rax
  void *v19; // rdx
  unsigned __int8 v20; // r8
  unsigned __int8 v21; // r9
  CAce *v23; // rsi
  PACL v24; // [rsp+30h] [rbp-39h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+38h] [rbp-31h] BYREF
  LPWSTR v26; // [rsp+40h] [rbp-29h] BYREF
  LPCWSTR StringSecurityDescriptor; // [rsp+48h] [rbp-21h] BYREF
  PACL pDacl; // [rsp+50h] [rbp-19h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+58h] [rbp-11h] BYREF
  WINBOOL bDaclPresent; // [rsp+5Ch] [rbp-Dh] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+60h] [rbp-9h] BYREF
  __int64 v32; // [rsp+80h] [rbp+17h]

  v3 = *(_QWORD *)a3;
  StringSecurityDescriptor = 0;
  Error = (*(__int64 (__fastcall **)(struct ISecurityEditor *, const unsigned __int16 *, __int64, __int64, LPCWSTR *))(v3 + 24))(
            a3,
            a2,
            1,
            4,
            &StringSecurityDescriptor);
  if ( Error >= 0 )
  {
    SecurityDescriptor = 0;
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0) )
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
        goto LABEL_22;
    }
    pDacl = 0;
    bDaclDefaulted = 0;
    bDaclPresent = 0;
    if ( !GetSecurityDescriptorDacl(SecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted) )
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
        goto LABEL_21;
    }
    v7 = SecurityDescriptor;
    v8 = pDacl;
    Error = -2147024882;
    v9 = (struct _ACL *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
    v24 = v9;
    v11 = (CAceList *)v9;
    if ( !v9 )
      goto LABEL_21;
    *v9 = 0;
    v9[1] = 0;
    v9[2] = 0;
    v9[3] = (struct _ACL)1LL;
    Error = CAceList::_InitFromAclAndSD((CAceList *)v9, v8, v7, v10);
    if ( Error < 0 )
    {
LABEL_20:
      CAceList::`scalar deleting destructor'(v11, v12);
      goto LABEL_21;
    }
    v24 = 0;
    Error = SHQueryToken<_TOKEN_USER>(v13, v12, 0, &v24);
    if ( Error < 0 )
    {
LABEL_19:
      if ( v11 )
        goto LABEL_20;
LABEL_21:
      LocalFree(SecurityDescriptor);
LABEL_22:
      CoTaskMemFree((LPVOID)StringSecurityDescriptor);
      return (unsigned int)Error;
    }
    v16 = v24;
    LOBYTE(v15) = 3;
    v17 = (void *)*v24;
    v18 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))CAceList::s_FindAce)(
            v14,
            (char *)v11 + 8,
            *v24,
            v15,
            0);
    v24 = (PACL)v18;
    if ( v18 )
    {
      *(_DWORD *)(v18 + 4) = 2032127;
    }
    else
    {
      Error = CAce::CreateInstance(v17, (unsigned int)v19, v20, v21, (struct CAce **)&v24);
      if ( Error < 0 )
      {
LABEL_18:
        LocalFree(v16);
        goto LABEL_19;
      }
      v23 = (CAce *)v24;
      Error = CDPA_Base<CPendingOperation,CTContainer_PolicyUnOwned<CPendingOperation>>::AppendPtr((char *)v11 + 8, v24);
      if ( Error < 0 )
      {
        if ( v23 )
          CAce::`scalar deleting destructor'(v23, (unsigned int)v19);
        goto LABEL_18;
      }
    }
    v24 = 0;
    Error = CAceList::GetAclForExplicitEntries(v11, v19, &v24);
    if ( Error >= 0 )
    {
      v32 = 0;
      memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
      InitializeSecurityDescriptor(pSecurityDescriptor, 1u);
      if ( SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v24, 0) || (Error = ResultFromKnownLastError(), Error >= 0) )
      {
        v26 = 0;
        if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(pSecurityDescriptor, 1u, 4u, &v26, 0)
          || (Error = ResultFromKnownLastError(), Error >= 0) )
        {
          Error = (*(__int64 (__fastcall **)(struct ISecurityEditor *, const unsigned __int16 *, __int64, _QWORD, LPWSTR))(*(_QWORD *)a3 + 32LL))(
                    a3,
                    a2,
                    1,
                    *((_DWORD *)v11 + 6) != 0 ? 536870916 : -2147483644,
                    v26);
          LocalFree(v26);
        }
      }
      LocalFree(v24);
    }
    goto LABEL_18;
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180560c18  mov     [rsp-8+arg_0], rbx
0x180560c1d  push    rbp
0x180560c1e  push    rsi
0x180560c1f  push    rdi
0x180560c20  push    r12
0x180560c22  push    r13
0x180560c24  push    r14
0x180560c26  push    r15
0x180560c28  lea     rbp, [rsp-27h]
0x180560c2d  sub     rsp, 90h
0x180560c34  mov     rax, cs:__security_cookie
0x180560c3b  xor     rax, rsp
0x180560c3e  mov     [rbp+57h+var_38], rax
0x180560c42  mov     rax, [r8]
0x180560c45  lea     rcx, [rbp+57h+StringSecurityDescriptor]
0x180560c49  xor     r15d, r15d
0x180560c4c  mov     [rsp+0C0h+StringSecurityDescriptorLen], rcx
0x180560c51  mov     r12, r8
0x180560c54  mov     [rbp+57h+StringSecurityDescriptor], r15
0x180560c58  mov     rcx, r12
0x180560c5b  mov     r13, rdx
0x180560c5e  mov     rax, [rax+18h]
0x180560c62  lea     edi, [r15+1]
0x180560c66  mov     r8d, edi
0x180560c69  lea     r9d, [r15+4]
0x180560c6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180560c72  mov     ebx, eax
0x180560c74  test    eax, eax
0x180560c76  js      loc_180560ED5
0x180560c7c  mov     rcx, [rbp+57h+StringSecurityDescriptor]; StringSecurityDescriptor
0x180560c80  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x180560c84  xor     r9d, r9d; SecurityDescriptorSize
0x180560c87  mov     [rbp+57h+SecurityDescriptor], r15
0x180560c8b  mov     edx, edi; StringSDRevision
0x180560c8d  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180560c94  nop     dword ptr [rax+rax+00h]
0x180560c99  test    eax, eax
0x180560c9b  jnz     short loc_180560CAC
0x180560c9d  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180560ca2  mov     ebx, eax
0x180560ca4  test    eax, eax
0x180560ca6  js      loc_180560EC5
0x180560cac  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x180560cb0  lea     r9, [rbp+57h+bDaclDefaulted]; lpbDaclDefaulted
0x180560cb4  lea     r8, [rbp+57h+pDacl]; pDacl
0x180560cb8  mov     [rbp+57h+pDacl], r15
0x180560cbc  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x180560cc0  mov     [rbp+57h+bDaclDefaulted], r15d
0x180560cc4  mov     [rbp+57h+bDaclPresent], r15d
0x180560cc8  call    cs:__imp_GetSecurityDescriptorDacl
0x180560ccf  nop     dword ptr [rax+rax+00h]
0x180560cd4  test    eax, eax
0x180560cd6  jnz     short loc_180560CE7
0x180560cd8  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180560cdd  mov     ebx, eax
0x180560cdf  test    eax, eax
0x180560ce1  js      loc_180560EB5
0x180560ce7  mov     rsi, [rbp+57h+SecurityDescriptor]
0x180560ceb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180560cf2  mov     r14, [rbp+57h+pDacl]
0x180560cf6  mov     ecx, 20h ; ' '; unsigned __int64
0x180560cfb  mov     ebx, 8007000Eh
0x180560d00  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180560d05  mov     [rbp+57h+var_90], rax
0x180560d09  mov     rdi, rax
0x180560d0c  test    rax, rax
0x180560d0f  jz      loc_180560EB5
0x180560d15  mov     [rax], r15
0x180560d18  mov     [rax+8], r15
0x180560d1c  mov     [rax+10h], r15
0x180560d20  mov     qword ptr [rax+18h], 1
0x180560d28  test    rax, rax
0x180560d2b  jz      loc_180560EB5
0x180560d31  mov     r8, rsi; void *
0x180560d34  mov     rdx, r14; struct _ACL *
0x180560d37  mov     rcx, rax; this
0x180560d3a  call    ?_InitFromAclAndSD@CAceList@@AEAAJPEAU_ACL@@PEAXH@Z; CAceList::_InitFromAclAndSD(_ACL *,void *,int)
0x180560d3f  mov     ebx, eax
0x180560d41  test    eax, eax
0x180560d43  js      loc_180560EAD
0x180560d49  lea     r9, [rbp+57h+var_90]
0x180560d4d  mov     [rbp+57h+var_90], r15
0x180560d51  xor     r8d, r8d
0x180560d54  call    ??$SHQueryToken@U_TOKEN_USER@@@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@HPEAPEAU_TOKEN_USER@@@Z; SHQueryToken<_TOKEN_USER>(void *,_TOKEN_INFORMATION_CLASS,int,_TOKEN_USER * *)
0x180560d59  mov     ebx, eax
0x180560d5b  test    eax, eax
0x180560d5d  js      loc_180560EA8
0x180560d63  mov     r15, [rbp+57h+var_90]
0x180560d67  lea     rdx, [rdi+8]
0x180560d6b  mov     r9b, 3
0x180560d6e  mov     [rsp+0C0h+StringSecurityDescriptorLen], 0
0x180560d77  mov     rbx, [r15]
0x180560d7a  mov     r8, rbx
0x180560d7d  call    ?s_FindAce@CAceList@@AEAAPEAVCAce@@AEAV?$CDPA@VCAce@@V?$CTContainer_PolicyUnOwned@VCAce@@@@@@PEAXEPEBV2@@Z; CAceList::s_FindAce(CDPA<CAce,CTContainer_PolicyUnOwned<CAce>> &,void *,uchar,CAce const *)
0x180560d82  mov     [rbp+57h+var_90], rax
0x180560d86  test    rax, rax
0x180560d89  jz      loc_180560EFF
0x180560d8f  mov     dword ptr [rax+4], 1F01FFh
0x180560d96  lea     r8, [rbp+57h+var_90]; struct _ACL **
0x180560d9a  mov     [rbp+57h+var_90], 0
0x180560da2  mov     rcx, rdi; this
0x180560da5  call    ?GetAclForExplicitEntries@CAceList@@QEAAJPEAXPEAPEAU_ACL@@@Z; CAceList::GetAclForExplicitEntries(void *,_ACL * *)
0x180560daa  mov     ebx, eax
0x180560dac  test    eax, eax
0x180560dae  js      loc_180560E99
0x180560db4  xor     eax, eax
0x180560db6  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180560dba  xorps   xmm0, xmm0
0x180560dbd  mov     [rbp+57h+var_40], rax
0x180560dc1  movups  [rbp+57h+pSecurityDescriptor], xmm0
0x180560dc5  lea     esi, [rax+1]
0x180560dc8  mov     edx, esi; dwRevision
0x180560dca  movups  [rbp+57h+var_50], xmm0
0x180560dce  call    cs:__imp_InitializeSecurityDescriptor
0x180560dd5  nop     dword ptr [rax+rax+00h]
0x180560dda  mov     r8, [rbp+57h+var_90]; pDacl
0x180560dde  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180560de2  xor     r9d, r9d; bDaclDefaulted
0x180560de5  mov     edx, esi; bDaclPresent
0x180560de7  call    cs:__imp_SetSecurityDescriptorDacl
0x180560dee  nop     dword ptr [rax+rax+00h]
0x180560df3  test    eax, eax
0x180560df5  jnz     short loc_180560E06
0x180560df7  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180560dfc  mov     ebx, eax
0x180560dfe  test    eax, eax
0x180560e00  js      loc_180560E89
0x180560e06  lea     r9, [rbp+57h+var_80]; StringSecurityDescriptor
0x180560e0a  mov     [rbp+57h+var_80], 0
0x180560e12  mov     r8d, 4; SecurityInformation
0x180560e18  mov     [rsp+0C0h+StringSecurityDescriptorLen], 0; StringSecurityDescriptorLen
0x180560e21  mov     edx, esi; RequestedStringSDRevision
0x180560e23  lea     rcx, [rbp+57h+pSecurityDescriptor]; SecurityDescriptor
0x180560e27  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x180560e2e  nop     dword ptr [rax+rax+00h]
0x180560e33  test    eax, eax
0x180560e35  jnz     short loc_180560E42
0x180560e37  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180560e3c  mov     ebx, eax
0x180560e3e  test    eax, eax
0x180560e40  js      short loc_180560E89
0x180560e42  mov     eax, [rdi+18h]
0x180560e45  mov     r8d, esi
0x180560e48  mov     r10, [r12]
0x180560e4c  neg     eax
0x180560e4e  mov     r11, [rbp+57h+var_80]
0x180560e52  mov     rdx, r13
0x180560e55  sbb     r9d, r9d
0x180560e58  mov     [rsp+0C0h+StringSecurityDescriptorLen], r11
0x180560e5d  and     r9d, 0A0000000h
0x180560e64  mov     rcx, r12
0x180560e67  mov     rax, [r10+20h]
0x180560e6b  add     r9d, 80000004h
0x180560e72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180560e77  mov     rcx, [rbp+57h+var_80]; hMem
0x180560e7b  mov     ebx, eax
0x180560e7d  call    cs:__imp_LocalFree
0x180560e84  nop     dword ptr [rax+rax+00h]
0x180560e89  mov     rcx, [rbp+57h+var_90]; hMem
0x180560e8d  call    cs:__imp_LocalFree
0x180560e94  nop     dword ptr [rax+rax+00h]
0x180560e99  mov     rcx, r15; hMem
0x180560e9c  call    cs:__imp_LocalFree
0x180560ea3  nop     dword ptr [rax+rax+00h]
0x180560ea8  test    rdi, rdi
0x180560eab  jz      short loc_180560EB5
0x180560ead  mov     rcx, rdi; this
0x180560eb0  call    ??_GCAceList@@QEAAPEAXI@Z; CAceList::`scalar deleting destructor'(uint)
0x180560eb5  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x180560eb9  call    cs:__imp_LocalFree
0x180560ec0  nop     dword ptr [rax+rax+00h]
0x180560ec5  mov     rcx, [rbp+57h+StringSecurityDescriptor]; pv
0x180560ec9  call    cs:__imp_CoTaskMemFree
0x180560ed0  nop     dword ptr [rax+rax+00h]
0x180560ed5  mov     eax, ebx
0x180560ed7  mov     rcx, [rbp+57h+var_38]
0x180560edb  xor     rcx, rsp; StackCookie
0x180560ede  call    __security_check_cookie
0x180560ee3  mov     rbx, [rsp+0C0h+arg_0]
0x180560eeb  add     rsp, 90h
0x180560ef2  pop     r15
0x180560ef4  pop     r14
0x180560ef6  pop     r13
0x180560ef8  pop     r12
0x180560efa  pop     rdi
0x180560efb  pop     rsi
0x180560efc  pop     rbp
0x180560efd  retn
0x180560eff  lea     rax, [rbp+57h+var_90]
0x180560f03  mov     rcx, rbx; void *
0x180560f06  mov     [rsp+0C0h+StringSecurityDescriptorLen], rax; struct CAce **
0x180560f0b  call    ?CreateInstance@CAce@@SAJPEAXKEEPEAPEAV1@@Z; CAce::CreateInstance(void *,ulong,uchar,uchar,CAce * *)
0x180560f10  mov     ebx, eax
0x180560f12  test    eax, eax
0x180560f14  js      short loc_180560E99
0x180560f16  mov     rsi, [rbp+57h+var_90]
0x180560f1a  lea     rcx, [rdi+8]
0x180560f1e  mov     rdx, rsi
0x180560f21  call    ?AppendPtr@?$CDPA_Base@VCPendingOperation@@V?$CTContainer_PolicyUnOwned@VCPendingOperation@@@@@@QEAAJPEAVCPendingOperation@@PEAH@Z; CDPA_Base<CPendingOperation,CTContainer_PolicyUnOwned<CPendingOperation>>::AppendPtr(CPendingOperation *,int *)
0x180560f26  mov     ebx, eax
0x180560f28  test    eax, eax
0x180560f2a  jns     loc_180560D96
0x180560f30  test    rsi, rsi
0x180560f33  jz      loc_180560E99
0x180560f39  mov     rcx, rsi; this
0x180560f3c  call    ??_GCAce@@QEAAPEAXI@Z; CAce::`scalar deleting destructor'(uint)
0x180560f41  jmp     loc_180560E99
```
