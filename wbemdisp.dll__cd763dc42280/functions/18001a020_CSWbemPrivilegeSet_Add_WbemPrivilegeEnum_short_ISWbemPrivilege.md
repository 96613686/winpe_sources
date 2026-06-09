# CSWbemPrivilegeSet::Add(WbemPrivilegeEnum,short,ISWbemPrivilege * *)

- ea: `0x18001a020`
- end: `0x18001a1d2`
- name: `?Add@CSWbemPrivilegeSet@@UEAAJW4WbemPrivilegeEnum@@FPEAPEAUISWbemPrivilege@@@Z`
- size: `434`
- prototype: `int(CSWbemPrivilegeSet *__hidden this, enum WbemPrivilegeEnum, __int16, struct ISWbemPrivilege **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18001c274`

## callees

- `0x1800050dc`
- `0x180006300`
- `0x180018864`
- `0x18001a020`
- `0x18001a30c`
- `0x18001bd30`
- `0x18001bef4`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a196`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a196`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001a10c`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001a10c`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18001a0f9`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18001a0f9`

## pseudocode

```c
__int64 __fastcall CSWbemPrivilegeSet::Add(
        CSWbemPrivilegeSet *this,
        enum WbemPrivilegeEnum a2,
        unsigned __int16 a3,
        struct ISWbemPrivilege **a4)
{
  int v8; // ebx
  __int64 v9; // rdi
  const WCHAR *NameFromId; // rax
  struct IDispatch *v11; // rax
  CSWbemPrivilege *v12; // rax
  CSWbemPrivilege *v13; // rdi
  _QWORD v15[2]; // [rsp+20h] [rbp-48h] BYREF
  _BYTE v16[16]; // [rsp+30h] [rbp-38h] BYREF
  enum WbemPrivilegeEnum v17; // [rsp+78h] [rbp+10h] BYREF
  struct _LUID Luid; // [rsp+88h] [rbp+20h] BYREF

  v17 = a2;
  ResetLastErrors();
  if ( !a4 )
  {
    v8 = -2147217400;
LABEL_20:
    CDispatchHelp::RaiseException((CSWbemPrivilegeSet *)((char *)this + 32), v8);
    return (unsigned int)v8;
  }
  if ( !*((_BYTE *)this + 24) )
  {
    v8 = -2147217373;
    goto LABEL_20;
  }
  std::_Tree<std::_Tmap_traits<enum WbemPrivilegeEnum,CSWbemPrivilege *,std::less<int>,CWbemAllocator<CSWbemPrivilege *>,0>>::find(
    (char *)this + 112,
    &Luid,
    &v17);
  if ( Luid == *((_QWORD *)this + 14) )
  {
    Luid = 0;
    NameFromId = CSWbemPrivilege::GetNameFromId(a2);
    if ( NameFromId && (!CSWbemSecurity::s_bIsNT || LookupPrivilegeValueW(0, NameFromId, &Luid)) )
    {
      v11 = (struct IDispatch *)CWin32DefaultArena::WbemMemAlloc(0x80u);
      v15[0] = v11;
      if ( !v11 || (v12 = CSWbemPrivilege::CSWbemPrivilege(v11, a2, &Luid, a3 != 0), (v13 = v12) == 0) )
      {
        v8 = -2147217402;
        goto LABEL_20;
      }
      v8 = (**(__int64 (__fastcall ***)(CSWbemPrivilege *, GUID *, struct ISWbemPrivilege **))v12)(
             v12,
             &IID_ISWbemPrivilege,
             a4);
      if ( v8 < 0 )
      {
        (*(void (__fastcall **)(CSWbemPrivilege *, __int64))(*(_QWORD *)v13 + 96LL))(v13, 1);
      }
      else
      {
        LODWORD(v15[0]) = a2;
        v15[1] = v13;
        std::_Tree<std::_Tmap_traits<enum WbemPrivilegeEnum,CSWbemPrivilege *,std::less<int>,CWbemAllocator<CSWbemPrivilege *>,0>>::insert(
          (char *)this + 112,
          v16,
          v15);
      }
    }
    else
    {
      GetLastError();
      v8 = -2147217400;
    }
  }
  else
  {
    v9 = *(_QWORD *)(*(_QWORD *)&Luid + 40LL);
    v8 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct ISWbemPrivilege **))v9)(v9, &IID_ISWbemPrivilege, a4);
    if ( v8 < 0 )
      goto LABEL_20;
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v9 + 64LL))(v9, a3);
  }
  if ( v8 < 0 )
    goto LABEL_20;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001a020  mov     [rsp+arg_0], rbx
0x18001a025  mov     [rsp+arg_10], rbp
0x18001a02a  mov     [rsp+arg_8], edx
0x18001a02e  push    rsi
0x18001a02f  push    rdi
0x18001a030  push    r12
0x18001a032  push    r14
0x18001a034  push    r15
0x18001a036  sub     rsp, 40h
0x18001a03a  mov     rbx, r9
0x18001a03d  movzx   r15d, r8w
0x18001a041  mov     esi, edx
0x18001a043  mov     rbp, rcx
0x18001a046  call    ?ResetLastErrors@@YAXXZ; ResetLastErrors(void)
0x18001a04b  xor     r12d, r12d
0x18001a04e  test    rbx, rbx
0x18001a051  jnz     short loc_18001A05D
0x18001a053  mov     ebx, 80041008h
0x18001a058  jmp     loc_18001A1AC
0x18001a05d  cmp     [rbp+18h], r12b
0x18001a061  jz      loc_18001A1A7
0x18001a067  lea     r14, [rbp+70h]
0x18001a06b  mov     rcx, r14
0x18001a06e  lea     r8, [rsp+68h+arg_8]
0x18001a073  lea     rdx, [rsp+68h+Luid]
0x18001a07b  call    ?find@?$_Tree@V?$_Tmap_traits@W4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@U?$less@H@std@@V?$CWbemAllocator@PEAVCSWbemPrivilege@@@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@@std@@@std@@@std@@@2@AEBW4WbemPrivilegeEnum@@@Z; std::_Tree<std::_Tmap_traits<WbemPrivilegeEnum,CSWbemPrivilege *,std::less<int>,CWbemAllocator<CSWbemPrivilege *>,0>>::find(WbemPrivilegeEnum const &)
0x18001a080  mov     rdx, qword ptr [rsp+68h+Luid.LowPart]
0x18001a088  cmp     rdx, [r14]
0x18001a08b  jz      short loc_18001A0CB
0x18001a08d  mov     rdi, [rdx+28h]
0x18001a091  mov     r8, rbx
0x18001a094  lea     rdx, IID_ISWbemPrivilege
0x18001a09b  mov     rcx, rdi
0x18001a09e  mov     rax, [rdi]
0x18001a0a1  mov     rax, [rax]
0x18001a0a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a0a9  mov     ebx, eax
0x18001a0ab  test    eax, eax
0x18001a0ad  js      loc_18001A1AC
0x18001a0b3  mov     rdx, [rdi]
0x18001a0b6  mov     rcx, rdi
0x18001a0b9  mov     rax, [rdx+40h]
0x18001a0bd  movzx   edx, r15w
0x18001a0c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a0c6  jmp     loc_18001A1A1
0x18001a0cb  mov     ecx, esi; enum WbemPrivilegeEnum
0x18001a0cd  mov     qword ptr [rsp+68h+Luid.LowPart], r12
0x18001a0d5  call    ?GetNameFromId@CSWbemPrivilege@@SAPEAGW4WbemPrivilegeEnum@@@Z; CSWbemPrivilege::GetNameFromId(WbemPrivilegeEnum)
0x18001a0da  test    rax, rax
0x18001a0dd  jz      loc_18001A196
0x18001a0e3  cmp     cs:?s_bIsNT@CSWbemSecurity@@0_NA, r12b; bool CSWbemSecurity::s_bIsNT
0x18001a0ea  jz      short loc_18001A107
0x18001a0ec  lea     r8, [rsp+68h+Luid]; lpLuid
0x18001a0f4  mov     rdx, rax; lpName
0x18001a0f7  xor     ecx, ecx; lpSystemName
0x18001a0f9  call    cs:__imp_LookupPrivilegeValueW
0x18001a0ff  test    eax, eax
0x18001a101  jz      loc_18001A196
0x18001a107  mov     ecx, 80h
0x18001a10c  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18001a112  mov     [rsp+68h+var_48], rax
0x18001a117  test    rax, rax
0x18001a11a  jz      short loc_18001A18F
0x18001a11c  test    r15w, r15w
0x18001a120  lea     r8, [rsp+68h+Luid]; struct _LUID *
0x18001a128  mov     edx, esi; enum WbemPrivilegeEnum
0x18001a12a  mov     rcx, rax; this
0x18001a12d  setnz   r9b; bool
0x18001a131  call    ??0CSWbemPrivilege@@QEAA@W4WbemPrivilegeEnum@@AEAU_LUID@@_N@Z; CSWbemPrivilege::CSWbemPrivilege(WbemPrivilegeEnum,_LUID &,bool)
0x18001a136  mov     rdi, rax
0x18001a139  test    rax, rax
0x18001a13c  jz      short loc_18001A18F
0x18001a13e  mov     rcx, [rax]
0x18001a141  lea     rdx, IID_ISWbemPrivilege
0x18001a148  mov     r8, rbx
0x18001a14b  mov     rax, [rcx]
0x18001a14e  mov     rcx, rdi
0x18001a151  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a156  mov     ebx, eax
0x18001a158  test    eax, eax
0x18001a15a  js      short loc_18001A179
0x18001a15c  lea     r8, [rsp+68h+var_48]
0x18001a161  mov     dword ptr [rsp+68h+var_48], esi
0x18001a165  lea     rdx, [rsp+68h+var_38]
0x18001a16a  mov     [rsp+68h+var_40], rdi
0x18001a16f  mov     rcx, r14
0x18001a172  call    ?insert@?$_Tree@V?$_Tmap_traits@W4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@U?$less@H@std@@V?$CWbemAllocator@PEAVCSWbemPrivilege@@@@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@@std@@@std@@@std@@@std@@_N@2@$$QEAU?$pair@$$CBW4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@@2@@Z; std::_Tree<std::_Tmap_traits<WbemPrivilegeEnum,CSWbemPrivilege *,std::less<int>,CWbemAllocator<CSWbemPrivilege *>,0>>::insert(std::pair<WbemPrivilegeEnum const,CSWbemPrivilege *> &&)
0x18001a177  jmp     short loc_18001A1A1
0x18001a179  mov     rax, [rdi]
0x18001a17c  mov     edx, 1
0x18001a181  mov     rcx, rdi
0x18001a184  mov     rax, [rax+60h]
0x18001a188  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a18d  jmp     short loc_18001A1A1
0x18001a18f  mov     ebx, 80041006h
0x18001a194  jmp     short loc_18001A1AC
0x18001a196  call    cs:__imp_GetLastError
0x18001a19c  mov     ebx, 80041008h
0x18001a1a1  test    ebx, ebx
0x18001a1a3  jns     short loc_18001A1B7
0x18001a1a5  jmp     short loc_18001A1AC
0x18001a1a7  mov     ebx, 80041023h
0x18001a1ac  lea     rcx, [rbp+20h]; this
0x18001a1b0  mov     edx, ebx; int
0x18001a1b2  call    ?RaiseException@CDispatchHelp@@QEAAXJ@Z; CDispatchHelp::RaiseException(long)
0x18001a1b7  lea     r11, [rsp+68h+var_28]
0x18001a1bc  mov     eax, ebx
0x18001a1be  mov     rbx, [r11+30h]
0x18001a1c2  mov     rbp, [r11+40h]
0x18001a1c6  mov     rsp, r11
0x18001a1c9  pop     r15
0x18001a1cb  pop     r14
0x18001a1cd  pop     r12
0x18001a1cf  pop     rdi
0x18001a1d0  pop     rsi
0x18001a1d1  retn
```
