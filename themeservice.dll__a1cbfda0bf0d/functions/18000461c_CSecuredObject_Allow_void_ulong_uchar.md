# CSecuredObject::Allow(void *,ulong,uchar)

- ea: `0x18000461c`
- end: `0x18000473e`
- name: `?Allow@CSecuredObject@@QEBAJPEAXKE@Z`
- size: `290`
- prototype: `__int64 __fastcall(SE_OBJECT_TYPE *this, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180003190`

## callees

- `0x1800034c4`
- `0x18000461c`
- `0x180004744`
- `0x180004800`
- `0x1800048a0`
- `0x180004a1c`
- `0x18000f9c2`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180004668`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180004668`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800046c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800046c2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004677`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004677`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x1800046f8`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x1800046f8`

## pseudocode

```c
__int64 __fastcall CSecuredObject::Allow(SE_OBJECT_TYPE *this, void *a2)
{
  signed int DACL; // ebx
  DWORD LengthSid; // ebx
  char *v6; // rax
  void *v7; // rdi
  struct _ACL *pDacl; // rax
  DWORD v9; // eax
  void *v11; // [rsp+40h] [rbp-40h] BYREF
  void **v12; // [rsp+48h] [rbp-38h] BYREF
  __int64 v13; // [rsp+50h] [rbp-30h] BYREF
  __int128 v14; // [rsp+58h] [rbp-28h] BYREF

  v13 = 0;
  v12 = &CAccessControlList::`vftable';
  v14 = 0;
  DACL = CSecuredObject::GetDACL((CSecuredObject *)this, (struct CAccessControlList *)&v12);
  if ( DACL >= 0 )
  {
    LengthSid = GetLengthSid(a2);
    v6 = (char *)LocalAlloc(0, LengthSid + 8);
    v7 = v6;
    if ( v6 )
    {
      *(_WORD *)v6 = 0;
      *((_WORD *)v6 + 1) = LengthSid + 8;
      *((_DWORD *)v6 + 1) = 1;
      memcpy_0(v6 + 8, a2, LengthSid);
      v11 = v7;
      DACL = CDynamicArray<_ACCESS_ALLOWED_ACE *>::Add(&v13, &v11);
      if ( DACL >= 0 )
      {
        pDacl = (struct _ACL *)CAccessControlList::operator _ACL *(&v12);
        v9 = SetSecurityInfo(*(HANDLE *)this, this[2], 4u, 0, 0, pDacl, 0);
        DACL = 0;
        if ( v9 )
          DACL = v9 | 0x80070000;
      }
      else
      {
        LocalFree(v7);
      }
    }
    else
    {
      DACL = -1073741801;
    }
  }
  v12 = &CAccessControlList::`vftable';
  ReleaseMemoryWorker((char *)&v14 + 8);
  CDynamicPointerArrayBase<_ACCESS_ALLOWED_ACE,CTOwnershipPolicy_LocalMem<_ACCESS_ALLOWED_ACE>>::~CDynamicPointerArrayBase<_ACCESS_ALLOWED_ACE,CTOwnershipPolicy_LocalMem<_ACCESS_ALLOWED_ACE>>(&v13);
  return (unsigned int)DACL;
}

```

## disassembly

```asm
0x18000461c  push    rbp
0x18000461e  push    rbx
0x18000461f  push    rsi
0x180004620  push    rdi
0x180004621  push    r13
0x180004623  push    r14
0x180004625  push    r15
0x180004627  mov     rbp, rsp
0x18000462a  sub     rsp, 80h
0x180004631  mov     r14, rdx
0x180004634  mov     [rbp+var_30], 0
0x18000463c  xorps   xmm0, xmm0
0x18000463f  lea     r13, ??_7CAccessControlList@@6B@; const CAccessControlList::`vftable'
0x180004646  lea     rdx, [rbp+var_38]; struct CAccessControlList *
0x18000464a  mov     [rbp+var_38], r13
0x18000464e  movdqu  [rbp+var_28], xmm0
0x180004653  mov     r15, rcx
0x180004656  call    ?GetDACL@CSecuredObject@@AEBAJAEAVCAccessControlList@@@Z; CSecuredObject::GetDACL(CAccessControlList &)
0x18000465b  mov     ebx, eax
0x18000465d  test    eax, eax
0x18000465f  js      loc_180004714
0x180004665  mov     rcx, r14; pSid
0x180004668  call    cs:__imp_GetLengthSid
0x18000466e  mov     ebx, eax
0x180004670  xor     ecx, ecx; uFlags
0x180004672  lea     esi, [rbx+8]
0x180004675  mov     edx, esi; uBytes
0x180004677  call    cs:__imp_LocalAlloc
0x18000467d  mov     rdi, rax
0x180004680  test    rax, rax
0x180004683  jz      loc_18000470F
0x180004689  mov     r8d, ebx; Size
0x18000468c  mov     word ptr [rax], 0
0x180004691  lea     rcx, [rax+8]; void *
0x180004695  mov     [rax+2], si
0x180004699  mov     rdx, r14; Src
0x18000469c  mov     dword ptr [rax+4], 1
0x1800046a3  call    memcpy_0
0x1800046a8  lea     rdx, [rbp+var_40]
0x1800046ac  mov     [rbp+var_40], rdi
0x1800046b0  lea     rcx, [rbp+var_30]
0x1800046b4  call    ?Add@?$CDynamicArray@PEAU_ACCESS_ALLOWED_ACE@@@@QEAAJAEBQEAU_ACCESS_ALLOWED_ACE@@@Z; CDynamicArray<_ACCESS_ALLOWED_ACE *>::Add(_ACCESS_ALLOWED_ACE * const &)
0x1800046b9  mov     ebx, eax
0x1800046bb  test    eax, eax
0x1800046bd  jns     short loc_1800046CA
0x1800046bf  mov     rcx, rdi; hMem
0x1800046c2  call    cs:__imp_LocalFree
0x1800046c8  jmp     short loc_180004714
0x1800046ca  lea     rcx, [rbp+var_38]
0x1800046ce  call    ??BCAccessControlList@@QEAAPEAU_ACL@@XZ; CAccessControlList::operator _ACL *(void)
0x1800046d3  mov     edx, [r15+8]; ObjectType
0x1800046d7  xor     r9d, r9d; psidOwner
0x1800046da  mov     rcx, [r15]; handle
0x1800046dd  mov     [rsp+80h+pSacl], 0; pSacl
0x1800046e6  mov     [rsp+80h+pDacl], rax; pDacl
0x1800046eb  lea     r8d, [r9+4]; SecurityInfo
0x1800046ef  mov     [rsp+80h+psidGroup], 0; psidGroup
0x1800046f8  call    cs:__imp_SetSecurityInfo
0x1800046fe  xor     ebx, ebx
0x180004700  mov     ecx, eax
0x180004702  or      ecx, 80070000h
0x180004708  test    eax, eax
0x18000470a  cmovnz  ebx, ecx
0x18000470d  jmp     short loc_180004714
0x18000470f  mov     ebx, 0C0000017h
0x180004714  lea     rcx, [rbp+var_28+8]
0x180004718  mov     [rbp+var_38], r13
0x18000471c  call    ReleaseMemoryWorker
0x180004721  lea     rcx, [rbp+var_30]
0x180004725  call    ??1?$CDynamicPointerArrayBase@U_ACCESS_ALLOWED_ACE@@V?$CTOwnershipPolicy_LocalMem@U_ACCESS_ALLOWED_ACE@@@@@@IEAA@XZ; CDynamicPointerArrayBase<_ACCESS_ALLOWED_ACE,CTOwnershipPolicy_LocalMem<_ACCESS_ALLOWED_ACE>>::~CDynamicPointerArrayBase<_ACCESS_ALLOWED_ACE,CTOwnershipPolicy_LocalMem<_ACCESS_ALLOWED_ACE>>(void)
0x18000472a  mov     eax, ebx
0x18000472c  add     rsp, 80h
0x180004733  pop     r15
0x180004735  pop     r14
0x180004737  pop     r13
0x180004739  pop     rdi
0x18000473a  pop     rsi
0x18000473b  pop     rbx
0x18000473c  pop     rbp
0x18000473d  retn
```
