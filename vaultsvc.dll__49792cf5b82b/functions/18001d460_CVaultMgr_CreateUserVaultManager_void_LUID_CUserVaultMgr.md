# CVaultMgr::CreateUserVaultManager(void *,_LUID *,CUserVaultMgr * *)

- ea: `0x18001d460`
- end: `0x18001d752`
- name: `?CreateUserVaultManager@CVaultMgr@@QEAAKPEAXPEAU_LUID@@PEAPEAVCUserVaultMgr@@@Z`
- size: `754`
- prototype: `__int64 __fastcall(CVaultMgr *this, void *, struct _LUID *, struct CUserVaultMgr **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001eda0`

## callees

- `0x180003140`
- `0x18001d380`
- `0x18001d3f8`
- `0x18001d460`
- `0x18003d720`
- `0x18004b43c`
- `0x18004d010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18001d509`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18001d509`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18001d4f2`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18001d4f2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d57c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d5d4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d57c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d5d4`
- `ntdll!RtlEqualSid` at `0x18001d549`
- `ntdll!RtlEqualSid` at `0x18001d549`
- `ntdll!RtlValidSid` at `0x18001d4b9`
- `ntdll!RtlValidSid` at `0x18001d4e1`
- `ntdll!RtlValidSid` at `0x18001d4b9`
- `ntdll!RtlValidSid` at `0x18001d4e1`
- `ntdll!RtlReleaseResource` at `0x18001d592`
- `ntdll!RtlReleaseResource` at `0x18001d5ea`
- `ntdll!RtlReleaseResource` at `0x18001d66d`
- `ntdll!RtlReleaseResource` at `0x18001d6d3`
- `ntdll!RtlReleaseResource` at `0x18001d6fb`
- `ntdll!RtlReleaseResource` at `0x18001d592`
- `ntdll!RtlReleaseResource` at `0x18001d5ea`
- `ntdll!RtlReleaseResource` at `0x18001d66d`
- `ntdll!RtlReleaseResource` at `0x18001d6d3`
- `ntdll!RtlReleaseResource` at `0x18001d6fb`
- `ntdll!RtlAcquireResourceExclusive` at `0x18001d516`
- `ntdll!RtlAcquireResourceExclusive` at `0x18001d516`
- `ntdll!RtlLengthSid` at `0x18001d569`
- `ntdll!RtlLengthSid` at `0x18001d569`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CVaultMgr::CreateUserVaultManager(
        CVaultMgr *this,
        void *a2,
        struct _LUID *a3,
        struct CUserVaultMgr **a4)
{
  PUCHAR SidSubAuthorityCount; // rax
  DWORD v8; // ebx
  __int64 v9; // r13
  __int64 i; // rbx
  struct CUserVaultMgr *v11; // rcx
  SIZE_T v12; // r14
  _QWORD *v13; // rax
  __int64 v14; // rbx
  CUserVaultMgr *v16; // rax
  CUserVaultMgr *v17; // r14
  unsigned int v18; // esi
  __int64 v19; // r8
  __int64 (__fastcall *v20)(); // [rsp+40h] [rbp-58h] BYREF
  CUserVaultMgr *v21; // [rsp+48h] [rbp-50h]
  int v22; // [rsp+50h] [rbp-48h]
  __int64 v23; // [rsp+58h] [rbp-40h] BYREF
  _QWORD *v24; // [rsp+60h] [rbp-38h]
  int v25; // [rsp+68h] [rbp-30h]
  CUserVaultMgr *v26; // [rsp+A0h] [rbp+8h]

  v24 = 0;
  v25 = 0;
  v23 = 0;
  v20 = AutoDereference<IVaultKeyManager>;
  v21 = 0;
  v22 = 0;
  if ( !RtlValidSid(a2)
    || !RtlValidSid(a2)
    || (SidSubAuthorityCount = GetSidSubAuthorityCount(a2), !*SidSubAuthorityCount) )
  {
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v20);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v23);
    return 87;
  }
  v8 = *GetSidSubAuthority(a2, (unsigned int)*SidSubAuthorityCount - 1);
  RtlAcquireResourceExclusive(&Resource, 1u);
  v9 = v8 % 0xB;
  for ( i = VaultGlobals::g_VaultMgr[v9]; ; i = *(_QWORD *)(i + 16) )
  {
    if ( !i )
      goto LABEL_9;
    if ( RtlEqualSid(a2, *(PSID *)i) )
      break;
  }
  v11 = *(struct CUserVaultMgr **)(i + 8);
  if ( !v11 )
  {
LABEL_9:
    v12 = RtlLengthSid(a2) + 24;
    v13 = LocalAlloc(0x40u, v12);
    v14 = (__int64)v13;
    v24 = v13;
    if ( !v13
      || (*v13 = v13 + 3,
          memcpy_0(v13 + 3, a2, v12 - 24),
          v16 = (CUserVaultMgr *)LocalAlloc(0x40u, 0xC0u),
          (v26 = v16) == 0) )
    {
      RtlReleaseResource(&Resource);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v20);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v23);
      return 14;
    }
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v17 = CUserVaultMgr::CUserVaultMgr(v16);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v20);
      v21 = v17;
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
      {
        v21 = 0;
        VaultFreeInternal(v26);
        __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_18001D6F4);
        RtlReleaseResource(&Resource);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v20);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v23);
        return 14;
      }
    }
    v18 = CUserVaultMgr::InitializeMgr(v17);
    if ( v18 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_LLD(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, v19, (unsigned int)a3->HighPart, a3->LowPart, v18);
      RtlReleaseResource(&Resource);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v20);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v23);
      return v18;
    }
    v21 = 0;
    *(_QWORD *)(v14 + 8) = v17;
    *(_QWORD *)(v14 + 16) = VaultGlobals::g_VaultMgr[v9];
    v24 = 0;
    VaultGlobals::g_VaultMgr[v9] = v14;
    v11 = *(struct CUserVaultMgr **)(v14 + 8);
  }
  if ( a4 )
  {
    *a4 = v11;
    (**(void (__fastcall ***)(struct CUserVaultMgr *))v11)(v11);
  }
  RtlReleaseResource(&Resource);
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v20);
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v23);
  return 0;
}

```

## disassembly

```asm
0x18001d460  mov     r11, rsp
0x18001d463  mov     [r11+10h], rbx
0x18001d467  mov     [r11+18h], rsi
0x18001d46b  mov     [r11+8], rcx
0x18001d46f  push    rdi
0x18001d470  push    r12
0x18001d472  push    r13
0x18001d474  push    r14
0x18001d476  push    r15
0x18001d478  sub     rsp, 70h
0x18001d47c  mov     r15, r9
0x18001d47f  mov     r12, r8
0x18001d482  mov     rsi, rdx
0x18001d485  xor     r14d, r14d
0x18001d488  mov     [r11-38h], r14
0x18001d48c  mov     [r11-30h], r14d
0x18001d490  mov     [r11-40h], r14
0x18001d494  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x18001d49b  mov     [r11-58h], rax
0x18001d49f  mov     [r11-50h], r14
0x18001d4a3  mov     [r11-48h], r14d
0x18001d4a7  lea     rdi, Resource
0x18001d4ae  mov     [r11-68h], rdi
0x18001d4b2  mov     [r11-60h], r14b
0x18001d4b6  mov     rcx, rdx; Sid
0x18001d4b9  call    cs:__imp_RtlValidSid
0x18001d4bf  test    al, al
0x18001d4c1  jnz     short loc_18001D4DE
0x18001d4c3  lea     rcx, [rsp+98h+var_58]
0x18001d4c8  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001d4cd  nop
0x18001d4ce  lea     rcx, [rsp+98h+var_40]
0x18001d4d3  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001d4d8  nop
0x18001d4d9  jmp     loc_18001D733
0x18001d4de  mov     rcx, rsi; Sid
0x18001d4e1  call    cs:__imp_RtlValidSid
0x18001d4e7  test    al, al
0x18001d4e9  jz      loc_18001D71D
0x18001d4ef  mov     rcx, rsi; pSid
0x18001d4f2  call    cs:__imp_GetSidSubAuthorityCount
0x18001d4f8  cmp     [rax], r14b
0x18001d4fb  jz      loc_18001D71D
0x18001d501  movzx   edx, byte ptr [rax]
0x18001d504  dec     edx; nSubAuthority
0x18001d506  mov     rcx, rsi; pSid
0x18001d509  call    cs:__imp_GetSidSubAuthority
0x18001d50f  mov     ebx, [rax]
0x18001d511  mov     dl, 1; Wait
0x18001d513  mov     rcx, rdi; Resource
0x18001d516  call    cs:__imp_RtlAcquireResourceExclusive
0x18001d51c  mov     [rsp+98h+var_60], 1
0x18001d521  mov     eax, 0BA2E8BA3h
0x18001d526  mul     ebx
0x18001d528  shr     edx, 3
0x18001d52b  imul    eax, edx, 0Bh
0x18001d52e  sub     ebx, eax
0x18001d530  mov     r13d, ebx
0x18001d533  lea     rax, ?g_VaultMgr@VaultGlobals@@3VCVaultMgr@@A; CVaultMgr VaultGlobals::g_VaultMgr
0x18001d53a  mov     rbx, [rax+rbx*8]
0x18001d53e  test    rbx, rbx
0x18001d541  jz      short loc_18001D566
0x18001d543  mov     rdx, [rbx]; Sid2
0x18001d546  mov     rcx, rsi; Sid1
0x18001d549  call    cs:__imp_RtlEqualSid
0x18001d54f  test    al, al
0x18001d551  jnz     short loc_18001D559
0x18001d553  mov     rbx, [rbx+10h]
0x18001d557  jmp     short loc_18001D53E
0x18001d559  mov     rcx, [rbx+8]
0x18001d55d  test    rcx, rcx
0x18001d560  jnz     loc_18001D6BD
0x18001d566  mov     rcx, rsi; Sid
0x18001d569  call    cs:__imp_RtlLengthSid
0x18001d56f  add     eax, 18h
0x18001d572  mov     r14d, eax
0x18001d575  mov     edx, eax; uBytes
0x18001d577  mov     ecx, 40h ; '@'; uFlags
0x18001d57c  call    cs:__imp_LocalAlloc
0x18001d582  mov     rbx, rax
0x18001d585  mov     [rsp+98h+var_38], rax
0x18001d58a  test    rax, rax
0x18001d58d  jnz     short loc_18001D5B9
0x18001d58f  mov     rcx, rdi; Resource
0x18001d592  call    cs:__imp_RtlReleaseResource
0x18001d598  nop
0x18001d599  lea     rcx, [rsp+98h+var_58]
0x18001d59e  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001d5a3  nop
0x18001d5a4  lea     rcx, [rsp+98h+var_40]
0x18001d5a9  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001d5ae  nop
0x18001d5af  mov     eax, 0Eh
0x18001d5b4  jmp     loc_18001D738
0x18001d5b9  lea     rcx, [rax+18h]; void *
0x18001d5bd  mov     [rax], rcx
0x18001d5c0  lea     r8, [r14-18h]; Size
0x18001d5c4  mov     rdx, rsi; Src
0x18001d5c7  call    memcpy_0
0x18001d5cc  mov     edx, 0C0h; uBytes
0x18001d5d1  lea     ecx, [rdx-80h]; uFlags
0x18001d5d4  call    cs:__imp_LocalAlloc
0x18001d5da  mov     [rsp+98h+arg_0], rax
0x18001d5e2  test    rax, rax
0x18001d5e5  jnz     short loc_18001D609
0x18001d5e7  mov     rcx, rdi; Resource
0x18001d5ea  call    cs:__imp_RtlReleaseResource
0x18001d5f0  nop
0x18001d5f1  lea     rcx, [rsp+98h+var_58]
0x18001d5f6  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001d5fb  nop
0x18001d5fc  lea     rcx, [rsp+98h+var_40]
0x18001d601  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001d606  nop
0x18001d607  jmp     short loc_18001D5AF
0x18001d609  mov     rcx, rax; this
0x18001d60c  call    ??0CUserVaultMgr@@QEAA@XZ; CUserVaultMgr::CUserVaultMgr(void)
0x18001d611  mov     r14, rax
0x18001d614  lea     rcx, [rsp+98h+var_58]
0x18001d619  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001d61e  mov     [rsp+98h+var_50], r14
0x18001d623  mov     rcx, r14; this
0x18001d626  call    ?InitializeMgr@CUserVaultMgr@@QEAAKXZ; CUserVaultMgr::InitializeMgr(void)
0x18001d62b  mov     esi, eax
0x18001d62d  test    eax, eax
0x18001d62f  jz      short loc_18001D691
0x18001d631  lea     rax, WPP_GLOBAL_Control
0x18001d638  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d63f  cmp     rcx, rax
0x18001d642  jz      short loc_18001D66A
0x18001d644  test    byte ptr [rcx+1Ch], 2
0x18001d648  jz      short loc_18001D66A
0x18001d64a  mov     edx, 45h ; 'E'
0x18001d64f  mov     [rsp+98h+var_70], esi
0x18001d653  mov     eax, [r12]
0x18001d657  mov     [rsp+98h+var_78], eax
0x18001d65b  mov     r9d, [r12+4]
0x18001d660  mov     rcx, [rcx+10h]
0x18001d664  call    WPP_SF_LLD
0x18001d669  nop
0x18001d66a  mov     rcx, rdi; Resource
0x18001d66d  call    cs:__imp_RtlReleaseResource
0x18001d673  nop
0x18001d674  lea     rcx, [rsp+98h+var_58]
0x18001d679  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001d67e  nop
0x18001d67f  lea     rcx, [rsp+98h+var_40]
0x18001d684  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001d689  nop
0x18001d68a  mov     eax, esi
0x18001d68c  jmp     loc_18001D738
0x18001d691  mov     [rsp+98h+var_50], 0
0x18001d69a  mov     [rbx+8], r14
0x18001d69e  lea     rcx, ?g_VaultMgr@VaultGlobals@@3VCVaultMgr@@A; CVaultMgr VaultGlobals::g_VaultMgr
0x18001d6a5  mov     rax, [rcx+r13*8]
0x18001d6a9  mov     [rbx+10h], rax
0x18001d6ad  xor     r14d, r14d
0x18001d6b0  mov     [rsp+98h+var_38], r14
0x18001d6b5  mov     [rcx+r13*8], rbx
0x18001d6b9  mov     rcx, [rbx+8]
0x18001d6bd  test    r15, r15
0x18001d6c0  jz      short loc_18001D6D0
0x18001d6c2  mov     [r15], rcx
0x18001d6c5  mov     rax, [rcx]
0x18001d6c8  mov     rax, [rax]
0x18001d6cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d6d0  mov     rcx, rdi; Resource
0x18001d6d3  call    cs:__imp_RtlReleaseResource
0x18001d6d9  nop
0x18001d6da  lea     rcx, [rsp+98h+var_58]
0x18001d6df  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001d6e4  nop
0x18001d6e5  lea     rcx, [rsp+98h+var_40]
0x18001d6ea  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001d6ef  nop
0x18001d6f0  xor     eax, eax
0x18001d6f2  jmp     short loc_18001D738
0x18001d6f4  lea     rcx, Resource; Resource
0x18001d6fb  call    cs:__imp_RtlReleaseResource
0x18001d701  nop
0x18001d702  lea     rcx, [rsp+98h+var_58]
0x18001d707  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001d70c  nop
0x18001d70d  lea     rcx, [rsp+98h+var_40]
0x18001d712  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001d717  nop
0x18001d718  jmp     loc_18001D5AF
0x18001d71d  lea     rcx, [rsp+98h+var_58]
0x18001d722  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001d727  nop
0x18001d728  lea     rcx, [rsp+98h+var_40]
0x18001d72d  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001d732  nop
0x18001d733  mov     eax, 57h ; 'W'
0x18001d738  lea     r11, [rsp+98h+var_28]
0x18001d73d  mov     rbx, [r11+38h]
0x18001d741  mov     rsi, [r11+40h]
0x18001d745  mov     rsp, r11
0x18001d748  pop     r15
0x18001d74a  pop     r14
0x18001d74c  pop     r13
0x18001d74e  pop     r12
0x18001d750  pop     rdi
0x18001d751  retn
```
