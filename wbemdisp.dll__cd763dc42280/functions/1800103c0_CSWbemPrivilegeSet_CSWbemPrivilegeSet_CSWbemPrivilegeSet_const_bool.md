# CSWbemPrivilegeSet::CSWbemPrivilegeSet(CSWbemPrivilegeSet const &,bool)

- ea: `0x1800103c0`
- end: `0x180010514`
- name: `??0CSWbemPrivilegeSet@@QEAA@AEBV0@_N@Z`
- size: `340`
- prototype: `CSWbemPrivilegeSet *__fastcall(CSWbemPrivilegeSet *__hidden this, const struct CSWbemPrivilegeSet *, bool)`
- caller_count: `5`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800017fc`
- `0x180009c20`
- `0x18000e9a0`
- `0x180010590`
- `0x18002dec0`

## callees

- `0x1800103c0`
- `0x180013920`
- `0x1800197ec`
- `0x180019870`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180010453`
- `OLEAUT32!__imp_SysAllocString` at `0x180010453`

## string_xrefs

- `0x18001044c`: `SWbemPrivilegeSet`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
CSWbemPrivilegeSet *__fastcall CSWbemPrivilegeSet::CSWbemPrivilegeSet(
        CSWbemPrivilegeSet *this,
        const struct CSWbemPrivilegeSet *a2,
        char a3)
{
  __int64 v6; // rbx
  int v7; // esi
  __int64 v8; // r14
  __int64 v9; // r8
  __int64 i; // rax
  int v12; // [rsp+20h] [rbp-58h]
  int v13; // [rsp+30h] [rbp-48h] BYREF
  __int64 v14; // [rsp+38h] [rbp-40h]
  _BYTE v15[56]; // [rsp+40h] [rbp-38h] BYREF

  *(_QWORD *)this = &CSWbemPrivilegeSet::`vftable'{for `ISWbemPrivilegeSet'};
  *((_QWORD *)this + 1) = &CSWbemPrivilegeSet::`vftable'{for `ISupportErrorInfo'};
  *((_QWORD *)this + 2) = &CSWbemPrivilegeSet::`vftable'{for `IProvideClassInfo'};
  *((_QWORD *)this + 4) = &CDispatchHelp::`vftable';
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_DWORD *)this + 12) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 14) = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<enum WbemPrivilegeEnum const,CSWbemPrivilege *>,CWbemAllocator<CSWbemPrivilege *>>>::_Buyheadnode();
  *((_QWORD *)this + 9) = this;
  *((GUID *)this + 5) = IID_ISWbemPrivilegeSet;
  *((GUID *)this + 6) = CLSID_SWbemPrivilegeSet;
  *((_QWORD *)this + 5) = SysAllocString(L"SWbemPrivilegeSet");
  *((_DWORD *)this + 32) = 1;
  *((_BYTE *)this + 24) = a3;
  v6 = **((_QWORD **)a2 + 14);
  while ( v6 != *((_QWORD *)a2 + 14) )
  {
    v7 = *(_DWORD *)(v6 + 32);
    v8 = *(_QWORD *)(v6 + 40);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
    v13 = v7;
    v14 = v8;
    LOBYTE(v12) = byte_180045B58;
    std::_Tree<std::_Tmap_traits<enum WbemPrivilegeEnum,CSWbemPrivilege *,std::less<int>,CWbemAllocator<CSWbemPrivilege *>,0>>::_Insert_nohint<std::pair<enum WbemPrivilegeEnum const,CSWbemPrivilege *>,std::_Nil>(
      (char *)this + 112,
      v15,
      v9,
      &v13,
      v12);
    if ( !*(_BYTE *)(v6 + 25) )
    {
      if ( *(_BYTE *)(*(_QWORD *)(v6 + 16) + 25LL) )
      {
        for ( i = *(_QWORD *)(v6 + 8); !*(_BYTE *)(i + 25); i = *(_QWORD *)(i + 8) )
        {
          if ( v6 != *(_QWORD *)(i + 16) )
            break;
          v6 = i;
        }
        v6 = i;
      }
      else
      {
        v6 = std::_Tree_val<std::_Tree_simple_types<std::pair<enum WbemPrivilegeEnum const,CSWbemPrivilege *>>>::_Min();
      }
    }
  }
  _InterlockedIncrement(&g_cObj);
  return this;
}

```

## disassembly

```asm
0x1800103c0  mov     [rsp+arg_10], rbx
0x1800103c5  mov     [rsp+arg_0], rcx
0x1800103ca  push    rbp
0x1800103cb  push    rsi
0x1800103cc  push    rdi
0x1800103cd  push    r14
0x1800103cf  push    r15
0x1800103d1  sub     rsp, 50h
0x1800103d5  movzx   ebx, r8b
0x1800103d9  mov     rdi, rdx
0x1800103dc  mov     r15, rcx
0x1800103df  lea     rax, ??_7CSWbemPrivilegeSet@@6BISWbemPrivilegeSet@@@; const CSWbemPrivilegeSet::`vftable'{for `ISWbemPrivilegeSet'}
0x1800103e6  mov     [rcx], rax
0x1800103e9  lea     rax, ??_7CSWbemPrivilegeSet@@6BISupportErrorInfo@@@; const CSWbemPrivilegeSet::`vftable'{for `ISupportErrorInfo'}
0x1800103f0  mov     [rcx+8], rax
0x1800103f4  lea     rax, ??_7CSWbemPrivilegeSet@@6BIProvideClassInfo@@@; const CSWbemPrivilegeSet::`vftable'{for `IProvideClassInfo'}
0x1800103fb  mov     [rcx+10h], rax
0x1800103ff  lea     rax, ??_7CDispatchHelp@@6B@; const CDispatchHelp::`vftable'
0x180010406  mov     [rcx+20h], rax
0x18001040a  xor     eax, eax
0x18001040c  mov     [rcx+38h], rax
0x180010410  mov     [rcx+40h], rax
0x180010414  mov     [rcx+48h], rax
0x180010418  mov     [rcx+28h], rax
0x18001041c  mov     [rcx+30h], eax
0x18001041f  mov     [rcx+70h], rax
0x180010423  mov     [rcx+78h], rax
0x180010427  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBW4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@@std@@V?$CWbemAllocator@PEAVCSWbemPrivilege@@@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBW4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<WbemPrivilegeEnum const,CSWbemPrivilege *>,CWbemAllocator<CSWbemPrivilege *>>>::_Buyheadnode(void)
0x18001042c  mov     [r15+70h], rax
0x180010430  movups  xmm1, xmmword ptr cs:CLSID_SWbemPrivilegeSet.Data1
0x180010437  movups  xmm0, xmmword ptr cs:IID_ISWbemPrivilegeSet.Data1
0x18001043e  mov     [r15+48h], r15
0x180010442  movups  xmmword ptr [r15+50h], xmm0
0x180010447  movups  xmmword ptr [r15+60h], xmm1
0x18001044c  lea     rcx, aSwbemprivilege_0; "SWbemPrivilegeSet"
0x180010453  call    cs:__imp_SysAllocString
0x180010459  mov     [r15+28h], rax
0x18001045d  mov     dword ptr [r15+80h], 1
0x180010468  mov     [r15+18h], bl
0x18001046c  mov     rbx, [rdi+70h]
0x180010470  mov     rbx, [rbx]
0x180010473  cmp     rbx, [rdi+70h]
0x180010477  jz      short loc_1800104D0
0x180010479  mov     esi, [rbx+20h]
0x18001047c  mov     r14, [rbx+28h]
0x180010480  mov     rax, [r14]
0x180010483  mov     rcx, r14
0x180010486  mov     rax, [rax+8]
0x18001048a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001048f  mov     [rsp+78h+var_48], esi
0x180010493  mov     [rsp+78h+var_40], r14
0x180010498  movzx   eax, cs:byte_180045B58
0x18001049f  mov     byte ptr [rsp+78h+var_58], al
0x1800104a3  lea     r9, [rsp+78h+var_48]
0x1800104a8  lea     rdx, [rsp+78h+var_38]
0x1800104ad  lea     rcx, [r15+70h]
0x1800104b1  call    ??$_Insert_nohint@U?$pair@$$CBW4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@@std@@U_Nil@2@@?$_Tree@V?$_Tmap_traits@W4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@U?$less@H@std@@V?$CWbemAllocator@PEAVCSWbemPrivilege@@@@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@@std@@@std@@@std@@@std@@_N@1@_N$$QEAU?$pair@$$CBW4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@@1@U_Nil@1@@Z; std::_Tree<std::_Tmap_traits<WbemPrivilegeEnum,CSWbemPrivilege *,std::less<int>,CWbemAllocator<CSWbemPrivilege *>,0>>::_Insert_nohint<std::pair<WbemPrivilegeEnum const,CSWbemPrivilege *>,std::_Nil>(bool,std::pair<WbemPrivilegeEnum const,CSWbemPrivilege *> &&,std::_Nil)
0x1800104b6  cmp     byte ptr [rbx+19h], 0
0x1800104ba  jnz     short loc_180010473
0x1800104bc  mov     rcx, [rbx+10h]
0x1800104c0  cmp     byte ptr [rcx+19h], 0
0x1800104c4  jnz     short loc_1800104EE
0x1800104c6  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBW4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<WbemPrivilegeEnum const,CSWbemPrivilege *>>>::_Min(std::_Tree_node<std::pair<WbemPrivilegeEnum const,CSWbemPrivilege *>,void *> *)
0x1800104cb  mov     rbx, rax
0x1800104ce  jmp     short loc_180010473
0x1800104d0  lock inc cs:?g_cObj@@3JA; long g_cObj
0x1800104d7  mov     rax, r15
0x1800104da  mov     rbx, [rsp+78h+arg_10]
0x1800104e2  add     rsp, 50h
0x1800104e6  pop     r15
0x1800104e8  pop     r14
0x1800104ea  pop     rdi
0x1800104eb  pop     rsi
0x1800104ec  pop     rbp
0x1800104ed  retn
0x1800104ee  mov     rax, [rbx+8]
0x1800104f2  cmp     byte ptr [rax+19h], 0
0x1800104f6  jnz     short loc_18001050B
0x1800104f8  cmp     rbx, [rax+10h]
0x1800104fc  jnz     short loc_18001050B
0x1800104fe  mov     rbx, rax
0x180010501  mov     rax, [rax+8]
0x180010505  cmp     byte ptr [rax+19h], 0
0x180010509  jz      short loc_1800104F8
0x18001050b  mov     rbx, rax
0x18001050e  jmp     loc_180010473
```
