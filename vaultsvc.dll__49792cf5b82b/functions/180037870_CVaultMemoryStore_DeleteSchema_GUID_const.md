# CVaultMemoryStore::DeleteSchema(_GUID const *)

- ea: `0x180037870`
- end: `0x1800379e5`
- name: `?DeleteSchema@CVaultMemoryStore@@UEAAKPEBU_GUID@@@Z`
- size: `373`
- prototype: `unsigned int __fastcall(CVaultMemoryStore *__hidden this, const struct _GUID *)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18001ab50`
- `0x180040f30`

## callees

- `0x180024a50`
- `0x18002d340`
- `0x18002e2e0`
- `0x180037870`
- `0x180037b0c`
- `0x180037bcc`
- `0x18003a580`
- `0x18004d010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x1800378c8`
- `ntdll!RtlReleaseResource` at `0x1800378fd`
- `ntdll!RtlReleaseResource` at `0x180037968`
- `ntdll!RtlReleaseResource` at `0x18003797f`
- `ntdll!RtlReleaseResource` at `0x1800379bd`
- `ntdll!RtlReleaseResource` at `0x1800378c8`
- `ntdll!RtlReleaseResource` at `0x1800378fd`
- `ntdll!RtlReleaseResource` at `0x180037968`
- `ntdll!RtlReleaseResource` at `0x18003797f`
- `ntdll!RtlReleaseResource` at `0x1800379bd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVaultMemoryStore::DeleteSchema(CVaultMemoryStore *this, const struct _GUID *a2)
{
  __int64 *v5; // rax
  __int64 v6; // rbx
  __int64 v7; // rax
  unsigned int v8; // r14d
  __int64 v9; // rax
  __int64 v10; // rax
  PRTL_RESOURCE Resource; // [rsp+20h] [rbp-40h] BYREF
  char v12; // [rsp+28h] [rbp-38h]
  __int64 v13; // [rsp+30h] [rbp-30h] BYREF
  _BYTE v14[8]; // [rsp+38h] [rbp-28h] BYREF
  __int128 v15; // [rsp+40h] [rbp-20h] BYREF

  v15 = 0;
  CVaultRtlLock::CVaultRtlLock(&Resource, (char *)this + 192, 1);
  if ( *((_BYTE *)this + 288) )
  {
    if ( v12 )
      RtlReleaseResource(Resource);
    return 55;
  }
  else
  {
    v5 = (__int64 *)std::_Tree<std::_Tmap_traits<_GUID,IVaultSchema *,GuidCmp,std::allocator<std::pair<_GUID const,IVaultSchema *>>,0>>::find(
                      (char *)this + 8,
                      v14,
                      a2);
    v6 = *v5;
    if ( *v5 == *((_QWORD *)this + 1) )
    {
      if ( v12 )
        RtlReleaseResource(Resource);
      return 1168;
    }
    else
    {
      v7 = **((_QWORD **)this + 3);
      v13 = v7;
      while ( v7 != *((_QWORD *)this + 3) )
      {
        v8 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(**(_QWORD **)(v7 + 48) + 24LL))(*(_QWORD *)(v7 + 48), &v15);
        if ( v8 )
        {
          if ( v12 )
            RtlReleaseResource(Resource);
          return v8;
        }
        v9 = v15 - *(_QWORD *)&a2->Data1;
        if ( (_QWORD)v15 == *(_QWORD *)&a2->Data1 )
          v9 = *((_QWORD *)&v15 + 1) - *(_QWORD *)a2->Data4;
        if ( !v9 )
        {
          if ( v12 )
            RtlReleaseResource(Resource);
          return 32;
        }
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_VAULT_CAUB const,IVaultCredential *>>>,std::_Iterator_base0>::operator++(&v13);
        v7 = v13;
      }
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v6 + 48) + 8LL))(*(_QWORD *)(v6 + 48));
      v10 = std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,IVaultSchema *>>>::_Extract(
              (char *)this + 8,
              v6);
      std::_Deallocate<16>(v10, 56);
      if ( v12 )
        RtlReleaseResource(Resource);
      return 0;
    }
  }
}

```

## disassembly

```asm
0x180037870  mov     [rsp-28h+arg_10], rbx
0x180037875  push    rbp
0x180037876  push    rsi
0x180037877  push    rdi
0x180037878  push    r14
0x18003787a  push    r15
0x18003787c  mov     rbp, rsp
0x18003787f  sub     rsp, 60h
0x180037883  mov     rax, cs:__security_cookie
0x18003788a  xor     rax, rsp
0x18003788d  mov     [rbp+var_10], rax
0x180037891  mov     rsi, rdx
0x180037894  mov     rdi, rcx
0x180037897  xorps   xmm0, xmm0
0x18003789a  movups  [rbp+var_20], xmm0
0x18003789e  lea     rdx, [rcx+0C0h]
0x1800378a5  mov     r8d, 1
0x1800378ab  lea     rcx, [rbp+Resource]
0x1800378af  call    ??0CVaultRtlLock@@QEAA@PEAU_RTL_RESOURCE@@W4eVaultLock@@@Z; CVaultRtlLock::CVaultRtlLock(_RTL_RESOURCE *,eVaultLock)
0x1800378b4  nop
0x1800378b5  cmp     byte ptr [rdi+120h], 0
0x1800378bc  jz      short loc_1800378D8
0x1800378be  cmp     [rbp+var_38], 0
0x1800378c2  jz      short loc_1800378CE
0x1800378c4  mov     rcx, [rbp+Resource]; Resource
0x1800378c8  call    cs:__imp_RtlReleaseResource
0x1800378ce  mov     eax, 37h ; '7'
0x1800378d3  jmp     loc_1800379C5
0x1800378d8  lea     r15, [rdi+8]
0x1800378dc  mov     r8, rsi
0x1800378df  lea     rdx, [rbp+var_28]
0x1800378e3  mov     rcx, r15
0x1800378e6  call    ?find@?$_Tree@V?$_Tmap_traits@U_GUID@@PEAUIVaultSchema@@UGuidCmp@@V?$allocator@U?$pair@$$CBU_GUID@@PEAUIVaultSchema@@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@PEAUIVaultSchema@@@std@@@std@@@std@@@2@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,IVaultSchema *,GuidCmp,std::allocator<std::pair<_GUID const,IVaultSchema *>>,0>>::find(_GUID const &)
0x1800378eb  mov     rbx, [rax]
0x1800378ee  cmp     rbx, [r15]
0x1800378f1  jnz     short loc_18003790D
0x1800378f3  cmp     [rbp+var_38], 0
0x1800378f7  jz      short loc_180037903
0x1800378f9  mov     rcx, [rbp+Resource]; Resource
0x1800378fd  call    cs:__imp_RtlReleaseResource
0x180037903  mov     eax, 490h
0x180037908  jmp     loc_1800379C5
0x18003790d  mov     rax, [rdi+18h]
0x180037911  mov     rax, [rax]
0x180037914  mov     [rbp+var_30], rax
0x180037918  cmp     rax, [rdi+18h]
0x18003791c  jz      short loc_18003798A
0x18003791e  mov     rcx, [rax+30h]
0x180037922  mov     rax, [rcx]
0x180037925  lea     rdx, [rbp+var_20]
0x180037929  mov     rax, [rax+18h]
0x18003792d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037932  mov     r14d, eax
0x180037935  test    eax, eax
0x180037937  jnz     short loc_180037975
0x180037939  mov     rax, qword ptr [rbp+var_20]
0x18003793d  sub     rax, [rsi]
0x180037940  jnz     short loc_18003794A
0x180037942  mov     rax, qword ptr [rbp+var_20+8]
0x180037946  sub     rax, [rsi+8]
0x18003794a  test    rax, rax
0x18003794d  jz      short loc_18003795E
0x18003794f  lea     rcx, [rbp+var_30]
0x180037953  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_VAULT_CAUB@@PEAUIVaultCredential@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_VAULT_CAUB const,IVaultCredential *>>>,std::_Iterator_base0>::operator++(void)
0x180037958  mov     rax, [rbp+var_30]
0x18003795c  jmp     short loc_180037918
0x18003795e  cmp     [rbp+var_38], 0
0x180037962  jz      short loc_18003796E
0x180037964  mov     rcx, [rbp+Resource]; Resource
0x180037968  call    cs:__imp_RtlReleaseResource
0x18003796e  mov     eax, 20h ; ' '
0x180037973  jmp     short loc_1800379C5
0x180037975  cmp     [rbp+var_38], 0
0x180037979  jz      short loc_180037985
0x18003797b  mov     rcx, [rbp+Resource]; Resource
0x18003797f  call    cs:__imp_RtlReleaseResource
0x180037985  mov     eax, r14d
0x180037988  jmp     short loc_1800379C5
0x18003798a  mov     rcx, [rbx+30h]
0x18003798e  mov     rax, [rcx]
0x180037991  mov     rax, [rax+8]
0x180037995  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003799a  mov     rdx, rbx
0x18003799d  mov     rcx, r15
0x1800379a0  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@PEAUIVaultSchema@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@PEAUIVaultSchema@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@PEAUIVaultSchema@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,IVaultSchema *>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,IVaultSchema *>>>,std::_Iterator_base0>)
0x1800379a5  mov     edx, 38h ; '8'
0x1800379aa  mov     rcx, rax
0x1800379ad  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800379b2  nop
0x1800379b3  cmp     [rbp+var_38], 0
0x1800379b7  jz      short loc_1800379C3
0x1800379b9  mov     rcx, [rbp+Resource]; Resource
0x1800379bd  call    cs:__imp_RtlReleaseResource
0x1800379c3  xor     eax, eax
0x1800379c5  mov     rcx, [rbp+var_10]
0x1800379c9  xor     rcx, rsp; StackCookie
0x1800379cc  call    __security_check_cookie
0x1800379d1  mov     rbx, [rsp+60h+arg_10]
0x1800379d9  add     rsp, 60h
0x1800379dd  pop     r15
0x1800379df  pop     r14
0x1800379e1  pop     rdi
0x1800379e2  pop     rsi
0x1800379e3  pop     rbp
0x1800379e4  retn
```
