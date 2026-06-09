# CSWbemSecurity::CSWbemSecurity(CSWbemSecurity *)

- ea: `0x180011b50`
- end: `0x180011e06`
- name: `??0CSWbemSecurity@@QEAA@PEAV0@@Z`
- size: `694`
- prototype: `CSWbemSecurity *__fastcall(CSWbemSecurity *__hidden this, struct CSWbemSecurity *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800307ac`

## callees

- `0x18000fd64`
- `0x180011b50`
- `0x180013920`
- `0x1800197ec`
- `0x180019870`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180011bea`
- `OLEAUT32!__imp_SysAllocString` at `0x180011cad`
- `OLEAUT32!__imp_SysAllocString` at `0x180011bea`
- `OLEAUT32!__imp_SysAllocString` at `0x180011cad`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180011c29`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180011ddc`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180011c29`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180011ddc`

## string_xrefs

- `0x180011be3`: `SWbemSecurity`
- `0x180011ca6`: `SWbemPrivilegeSet`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
CSWbemSecurity *__fastcall CSWbemSecurity::CSWbemSecurity(CSWbemSecurity *this, struct CSWbemSecurity *a2)
{
  _QWORD **v4; // r15
  GUID *v5; // rax
  GUID *v6; // rbp
  __int64 v7; // rbx
  __int64 v8; // rbx
  __int64 v9; // rbx
  int v11; // edi
  __int64 v12; // rsi
  __int64 v13; // r8
  __int64 i; // rax
  CSWbemPrivilegeSet *v15; // rax
  CSWbemPrivilegeSet *v16; // rax
  int v17; // [rsp+20h] [rbp-68h]
  int v18; // [rsp+30h] [rbp-58h] BYREF
  __int64 v19; // [rsp+38h] [rbp-50h]
  _BYTE v20[72]; // [rsp+40h] [rbp-48h] BYREF

  *(_QWORD *)this = &CSWbemSecurity::`vftable'{for `ISWbemSecurity'};
  *((_QWORD *)this + 1) = &CSWbemSecurity::`vftable'{for `ISupportErrorInfo'};
  *((_QWORD *)this + 2) = &CSWbemSecurity::`vftable'{for `ISWbemInternalSecurity'};
  *((_QWORD *)this + 3) = &CSWbemSecurity::`vftable'{for `IProvideClassInfo'};
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = &CDispatchHelp::`vftable';
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_DWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 10) = this;
  *(GUID *)((char *)this + 88) = IID_ISWbemSecurity;
  *(GUID *)((char *)this + 104) = CLSID_SWbemSecurity;
  *((_QWORD *)this + 6) = SysAllocString(L"SWbemSecurity");
  *((_DWORD *)this + 34) = 1;
  if ( a2 )
  {
    v4 = (_QWORD **)*((_QWORD *)a2 + 4);
    if ( v4 )
    {
      ((void (__fastcall *)(_QWORD))(*v4)[1])(*((_QWORD *)a2 + 4));
      v5 = (GUID *)CWin32DefaultArena::WbemMemAlloc(0x88u);
      v6 = v5;
      if ( v5 )
      {
        *(_QWORD *)&v5->Data1 = &CSWbemPrivilegeSet::`vftable'{for `ISWbemPrivilegeSet'};
        *(_QWORD *)v5->Data4 = &CSWbemPrivilegeSet::`vftable'{for `ISupportErrorInfo'};
        *(_QWORD *)&v5[1].Data1 = &CSWbemPrivilegeSet::`vftable'{for `IProvideClassInfo'};
        *(_QWORD *)&v5[2].Data1 = &CDispatchHelp::`vftable';
        *(_QWORD *)v5[3].Data4 = 0;
        *(_QWORD *)&v5[4].Data1 = 0;
        *(_QWORD *)v5[4].Data4 = 0;
        *(_QWORD *)v5[2].Data4 = 0;
        v5[3].Data1 = 0;
        *(_QWORD *)&v5[7].Data1 = 0;
        *(_QWORD *)v5[7].Data4 = 0;
        *(_QWORD *)&v5[7].Data1 = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<enum WbemPrivilegeEnum const,CSWbemPrivilege *>,CWbemAllocator<CSWbemPrivilege *>>>::_Buyheadnode();
        *(_QWORD *)v6[4].Data4 = v6;
        v6[5] = IID_ISWbemPrivilegeSet;
        v6[6] = CLSID_SWbemPrivilegeSet;
        *(_QWORD *)v6[2].Data4 = SysAllocString(L"SWbemPrivilegeSet");
        v6[8].Data1 = 1;
        v6[1].Data4[0] = 1;
        v7 = *v4[14];
        while ( (_QWORD *)v7 != v4[14] )
        {
          v11 = *(_DWORD *)(v7 + 32);
          v12 = *(_QWORD *)(v7 + 40);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
          v18 = v11;
          v19 = v12;
          LOBYTE(v17) = byte_180045B58;
          std::_Tree<std::_Tmap_traits<enum WbemPrivilegeEnum,CSWbemPrivilege *,std::less<int>,CWbemAllocator<CSWbemPrivilege *>,0>>::_Insert_nohint<std::pair<enum WbemPrivilegeEnum const,CSWbemPrivilege *>,std::_Nil>(
            &v6[7],
            v20,
            v13,
            &v18,
            v17);
          if ( !*(_BYTE *)(v7 + 25) )
          {
            if ( *(_BYTE *)(*(_QWORD *)(v7 + 16) + 25LL) )
            {
              for ( i = *(_QWORD *)(v7 + 8); !*(_BYTE *)(i + 25); i = *(_QWORD *)(i + 8) )
              {
                if ( v7 != *(_QWORD *)(i + 16) )
                  break;
                v7 = i;
              }
              v7 = i;
            }
            else
            {
              v7 = std::_Tree_val<std::_Tree_simple_types<std::pair<enum WbemPrivilegeEnum const,CSWbemPrivilege *>>>::_Min();
            }
          }
        }
        _InterlockedIncrement(&g_cObj);
      }
      else
      {
        v6 = 0;
      }
      *((_QWORD *)this + 4) = v6;
      ((void (__fastcall *)(_QWORD **))(*v4)[2])(v4);
    }
    else
    {
      v15 = (CSWbemPrivilegeSet *)CWin32DefaultArena::WbemMemAlloc(0x88u);
      if ( v15 )
        v16 = CSWbemPrivilegeSet::CSWbemPrivilegeSet(v15);
      else
        v16 = 0;
      *((_QWORD *)this + 4) = v16;
    }
    v8 = *((_QWORD *)a2 + 15);
    if ( v8 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v8 + 8LL))(*((_QWORD *)a2 + 15));
    *((_QWORD *)this + 15) = v8;
    v9 = *((_QWORD *)a2 + 16);
    if ( v9 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v9 + 8LL))(*((_QWORD *)a2 + 16));
    *((_QWORD *)this + 16) = v9;
  }
  _InterlockedIncrement(&g_cObj);
  return this;
}

```

## disassembly

```asm
0x180011b50  mov     [rsp+arg_18], rbx
0x180011b55  mov     [rsp+arg_0], rcx
0x180011b5a  push    rbp
0x180011b5b  push    rsi
0x180011b5c  push    rdi
0x180011b5d  push    r12
0x180011b5f  push    r13
0x180011b61  push    r14
0x180011b63  push    r15
0x180011b65  sub     rsp, 50h
0x180011b69  mov     r13, rdx
0x180011b6c  mov     r14, rcx
0x180011b6f  lea     rax, ??_7CSWbemSecurity@@6BISWbemSecurity@@@; const CSWbemSecurity::`vftable'{for `ISWbemSecurity'}
0x180011b76  mov     [rcx], rax
0x180011b79  lea     rax, ??_7CSWbemSecurity@@6BISupportErrorInfo@@@; const CSWbemSecurity::`vftable'{for `ISupportErrorInfo'}
0x180011b80  mov     [rcx+8], rax
0x180011b84  lea     rax, ??_7CSWbemSecurity@@6BISWbemInternalSecurity@@@; const CSWbemSecurity::`vftable'{for `ISWbemInternalSecurity'}
0x180011b8b  mov     [rcx+10h], rax
0x180011b8f  lea     rax, ??_7CSWbemSecurity@@6BIProvideClassInfo@@@; const CSWbemSecurity::`vftable'{for `IProvideClassInfo'}
0x180011b96  mov     [rcx+18h], rax
0x180011b9a  xor     ebx, ebx
0x180011b9c  mov     [rcx+20h], rbx
0x180011ba0  lea     rdi, ??_7CDispatchHelp@@6B@; const CDispatchHelp::`vftable'
0x180011ba7  mov     [rcx+28h], rdi
0x180011bab  mov     [rcx+40h], rbx
0x180011baf  mov     [rcx+48h], rbx
0x180011bb3  mov     [rcx+50h], rbx
0x180011bb7  mov     [rcx+30h], rbx
0x180011bbb  mov     [rcx+38h], ebx
0x180011bbe  mov     [rcx+78h], rbx
0x180011bc2  mov     [rcx+80h], rbx
0x180011bc9  movups  xmm1, xmmword ptr cs:CLSID_SWbemSecurity.Data1
0x180011bd0  movups  xmm0, xmmword ptr cs:IID_ISWbemSecurity.Data1
0x180011bd7  mov     [rcx+50h], rcx
0x180011bdb  movups  xmmword ptr [rcx+58h], xmm0
0x180011bdf  movups  xmmword ptr [rcx+68h], xmm1
0x180011be3  lea     rcx, aSwbemsecurity; "SWbemSecurity"
0x180011bea  call    cs:__imp_SysAllocString
0x180011bf0  mov     [r14+30h], rax
0x180011bf4  mov     dword ptr [r14+88h], 1
0x180011bff  test    r13, r13
0x180011c02  jz      loc_180011D2A
0x180011c08  mov     r15, [r13+20h]
0x180011c0c  test    r15, r15
0x180011c0f  jz      loc_180011DD7
0x180011c15  mov     rax, [r15]
0x180011c18  mov     rcx, r15
0x180011c1b  mov     rax, [rax+8]
0x180011c1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c24  mov     ecx, 88h
0x180011c29  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180011c2f  mov     rbp, rax
0x180011c32  mov     [rsp+88h+arg_8], rax
0x180011c3a  test    rax, rax
0x180011c3d  jz      loc_180011DAA
0x180011c43  lea     rax, ??_7CSWbemPrivilegeSet@@6BISWbemPrivilegeSet@@@; const CSWbemPrivilegeSet::`vftable'{for `ISWbemPrivilegeSet'}
0x180011c4a  mov     [rbp+0], rax
0x180011c4e  lea     rax, ??_7CSWbemPrivilegeSet@@6BISupportErrorInfo@@@; const CSWbemPrivilegeSet::`vftable'{for `ISupportErrorInfo'}
0x180011c55  mov     [rbp+8], rax
0x180011c59  lea     rax, ??_7CSWbemPrivilegeSet@@6BIProvideClassInfo@@@; const CSWbemPrivilegeSet::`vftable'{for `IProvideClassInfo'}
0x180011c60  mov     [rbp+10h], rax
0x180011c64  mov     [rbp+20h], rdi
0x180011c68  mov     [rbp+38h], rbx
0x180011c6c  mov     [rbp+40h], rbx
0x180011c70  mov     [rbp+48h], rbx
0x180011c74  mov     [rbp+28h], rbx
0x180011c78  mov     [rbp+30h], ebx
0x180011c7b  mov     [rbp+70h], rbx
0x180011c7f  mov     [rbp+78h], rbx
0x180011c83  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBW4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@@std@@V?$CWbemAllocator@PEAVCSWbemPrivilege@@@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBW4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<WbemPrivilegeEnum const,CSWbemPrivilege *>,CWbemAllocator<CSWbemPrivilege *>>>::_Buyheadnode(void)
0x180011c88  mov     [rbp+70h], rax
0x180011c8c  movups  xmm1, xmmword ptr cs:CLSID_SWbemPrivilegeSet.Data1
0x180011c93  movups  xmm0, xmmword ptr cs:IID_ISWbemPrivilegeSet.Data1
0x180011c9a  mov     [rbp+48h], rbp
0x180011c9e  movups  xmmword ptr [rbp+50h], xmm0
0x180011ca2  movups  xmmword ptr [rbp+60h], xmm1
0x180011ca6  lea     rcx, aSwbemprivilege_0; "SWbemPrivilegeSet"
0x180011cad  call    cs:__imp_SysAllocString
0x180011cb3  mov     [rbp+28h], rax
0x180011cb7  mov     dword ptr [rbp+80h], 1
0x180011cc1  mov     byte ptr [rbp+18h], 1
0x180011cc5  mov     rbx, [r15+70h]
0x180011cc9  mov     rbx, [rbx]
0x180011ccc  cmp     rbx, [r15+70h]
0x180011cd0  jnz     short loc_180011D4C
0x180011cd2  lock inc cs:?g_cObj@@3JA; long g_cObj
0x180011cd9  mov     [r14+20h], rbp
0x180011cdd  mov     rax, [r15]
0x180011ce0  mov     rcx, r15
0x180011ce3  mov     rax, [rax+10h]
0x180011ce7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011cec  mov     rbx, [r13+78h]
0x180011cf0  test    rbx, rbx
0x180011cf3  jz      short loc_180011D04
0x180011cf5  mov     rax, [rbx]
0x180011cf8  mov     rcx, rbx
0x180011cfb  mov     rax, [rax+8]
0x180011cff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d04  mov     [r14+78h], rbx
0x180011d08  mov     rbx, [r13+80h]
0x180011d0f  test    rbx, rbx
0x180011d12  jz      short loc_180011D23
0x180011d14  mov     rax, [rbx]
0x180011d17  mov     rcx, rbx
0x180011d1a  mov     rax, [rax+8]
0x180011d1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d23  mov     [r14+80h], rbx
0x180011d2a  lock inc cs:?g_cObj@@3JA; long g_cObj
0x180011d31  mov     rax, r14
0x180011d34  mov     rbx, [rsp+88h+arg_18]
0x180011d3c  add     rsp, 50h
0x180011d40  pop     r15
0x180011d42  pop     r14
0x180011d44  pop     r13
0x180011d46  pop     r12
0x180011d48  pop     rdi
0x180011d49  pop     rsi
0x180011d4a  pop     rbp
0x180011d4b  retn
0x180011d4c  mov     edi, [rbx+20h]
0x180011d4f  mov     rsi, [rbx+28h]
0x180011d53  mov     rax, [rsi]
0x180011d56  mov     rcx, rsi
0x180011d59  mov     rax, [rax+8]
0x180011d5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d62  mov     [rsp+88h+var_58], edi
0x180011d66  mov     [rsp+88h+var_50], rsi
0x180011d6b  movzx   eax, cs:byte_180045B58
0x180011d72  mov     byte ptr [rsp+88h+var_68], al
0x180011d76  lea     r9, [rsp+88h+var_58]
0x180011d7b  lea     rdx, [rsp+88h+var_48]
0x180011d80  lea     rcx, [rbp+70h]
0x180011d84  call    ??$_Insert_nohint@U?$pair@$$CBW4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@@std@@U_Nil@2@@?$_Tree@V?$_Tmap_traits@W4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@U?$less@H@std@@V?$CWbemAllocator@PEAVCSWbemPrivilege@@@@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@@std@@@std@@@std@@@std@@_N@1@_N$$QEAU?$pair@$$CBW4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@@1@U_Nil@1@@Z; std::_Tree<std::_Tmap_traits<WbemPrivilegeEnum,CSWbemPrivilege *,std::less<int>,CWbemAllocator<CSWbemPrivilege *>,0>>::_Insert_nohint<std::pair<WbemPrivilegeEnum const,CSWbemPrivilege *>,std::_Nil>(bool,std::pair<WbemPrivilegeEnum const,CSWbemPrivilege *> &&,std::_Nil)
0x180011d89  cmp     byte ptr [rbx+19h], 0
0x180011d8d  jnz     loc_180011CCC
0x180011d93  mov     rcx, [rbx+10h]
0x180011d97  cmp     byte ptr [rcx+19h], 0
0x180011d9b  jnz     short loc_180011DB2
0x180011d9d  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBW4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<WbemPrivilegeEnum const,CSWbemPrivilege *>>>::_Min(std::_Tree_node<std::pair<WbemPrivilegeEnum const,CSWbemPrivilege *>,void *> *)
0x180011da2  mov     rbx, rax
0x180011da5  jmp     loc_180011CCC
0x180011daa  mov     rbp, rbx
0x180011dad  jmp     loc_180011CD9
0x180011db2  mov     rax, [rbx+8]
0x180011db6  cmp     byte ptr [rax+19h], 0
0x180011dba  jnz     short loc_180011DCF
0x180011dbc  cmp     rbx, [rax+10h]
0x180011dc0  jnz     short loc_180011DCF
0x180011dc2  mov     rbx, rax
0x180011dc5  mov     rax, [rax+8]
0x180011dc9  cmp     byte ptr [rax+19h], 0
0x180011dcd  jz      short loc_180011DBC
0x180011dcf  mov     rbx, rax
0x180011dd2  jmp     loc_180011CCC
0x180011dd7  mov     ecx, 88h
0x180011ddc  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180011de2  mov     [rsp+88h+arg_8], rax
0x180011dea  test    rax, rax
0x180011ded  jz      short loc_180011DF9
0x180011def  mov     rcx, rax; this
0x180011df2  call    ??0CSWbemPrivilegeSet@@QEAA@XZ; CSWbemPrivilegeSet::CSWbemPrivilegeSet(void)
0x180011df7  jmp     short loc_180011DFC
0x180011df9  mov     rax, rbx
0x180011dfc  mov     [r14+20h], rax
0x180011e00  jmp     loc_180011CEC
```
