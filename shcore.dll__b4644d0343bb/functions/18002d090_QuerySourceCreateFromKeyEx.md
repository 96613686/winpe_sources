# QuerySourceCreateFromKeyEx

- ea: `0x18002d090`
- end: `0x18002d3bc`
- name: `QuerySourceCreateFromKeyEx`
- size: `812`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, LPCWSTR lpSubKey@<rdx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002d050`

## callees

- `0x18002d090`
- `0x18002d3c4`
- `0x18002d3d8`
- `0x18002d5b0`
- `0x180066910`
- `0x180068d9c`
- `0x1800933b0`
- `0x180095010`

## import_xrefs

- `ntdll!NtQuerySystemInformationEx` at `0x18002d255`
- `ntdll!NtQuerySystemInformationEx` at `0x18002d2b3`
- `ntdll!NtQuerySystemInformationEx` at `0x18002d255`
- `ntdll!NtQuerySystemInformationEx` at `0x18002d2b3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002d37b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002d39e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002d37b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002d39e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d1b4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d31b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d1b4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d31b`
- `api-ms-win-core-wow64-l1-1-1!Wow64SetThreadDefaultGuestMachine` at `0x18002d2ee`
- `api-ms-win-core-wow64-l1-1-1!Wow64SetThreadDefaultGuestMachine` at `0x18002d327`
- `api-ms-win-core-wow64-l1-1-1!Wow64SetThreadDefaultGuestMachine` at `0x18002d2ee`
- `api-ms-win-core-wow64-l1-1-1!Wow64SetThreadDefaultGuestMachine` at `0x18002d327`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall QuerySourceCreateFromKeyEx(HKEY hKey, LPCWSTR lpSubKey, int a3, int a4, __int64 a5, _QWORD *a6)
{
  _QWORD *v10; // rax
  _QWORD *v11; // rbx
  HKEY *phkResult; // rax
  REGSAM v13; // r14d
  LSTATUS Key; // eax
  signed int v15; // esi
  bool v16; // sf
  unsigned __int64 v18; // rcx
  unsigned __int64 v19; // rcx
  void *v20; // rsp
  void *v21; // rsp
  __int64 v22; // rcx
  _WORD *v23; // rdx
  int v24; // r8d
  REGSAM samDesired; // ecx
  HKEY *v26; // rax
  LSTATUS v27; // eax
  _WORD v28[2]; // [rsp+50h] [rbp+0h] BYREF
  unsigned int v29; // [rsp+54h] [rbp+4h] BYREF
  int v30; // [rsp+58h] [rbp+8h]
  __int64 v31; // [rsp+60h] [rbp+10h] BYREF
  _WORD *v32; // [rsp+68h] [rbp+18h]

  *a6 = 0;
  v10 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v11 = v10;
  if ( !v10 )
    return 2147942414LL;
  v10[5] = 0;
  v10[6] = 0;
  v10[7] = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IQuerySource,IObjectWithRegistryKey,Windows::Internal::Shell::FileAssociations::IAssociationQuerySource>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IQuerySource,IObjectWithRegistryKey,Windows::Internal::Shell::FileAssociations::IAssociationQuerySource>(v10);
  *v11 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IQuerySource,IObjectWithRegistryKey,Windows::Internal::Shell::FileAssociations::IAssociationQuerySource>::`vftable';
  v11[1] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IQuerySource,IObjectWithRegistryKey,Windows::Internal::Shell::FileAssociations::IAssociationQuerySource>::`vftable'{for `IQuerySource'};
  v11[2] = &CRegistrySource::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,IObjectWithRegistryKey,Windows::Internal::Shell::FileAssociations::IAssociationQuerySource>'};
  v11[3] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IQuerySource,IObjectWithRegistryKey,Windows::Internal::Shell::FileAssociations::IAssociationQuerySource>::`vftable'{for `IObjectWithRegistryKey'};
  v11[4] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IQuerySource,IObjectWithRegistryKey,Windows::Internal::Shell::FileAssociations::IAssociationQuerySource>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Internal::Shell::FileAssociations::IAssociationQuerySource>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *v11 = &CRegistrySource::`vftable';
  v11[1] = &CRegistrySource::`vftable'{for `IQuerySource'};
  v11[2] = &CRegistrySource::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,IObjectWithRegistryKey,Windows::Internal::Shell::FileAssociations::IAssociationQuerySource>'};
  v11[3] = &CRegistrySource::`vftable'{for `IObjectWithRegistryKey'};
  v11[4] = &CRegistrySource::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Internal::Shell::FileAssociations::IAssociationQuerySource>'};
  phkResult = (HKEY *)(v11 + 7);
  v11[7] = 0;
  if ( (a4 & 0x200) == 0 )
  {
LABEL_5:
    v13 = a4 | 0x20019;
    if ( a3 )
      Key = RegCreateKeyExW(hKey, lpSubKey, 0, 0, 0, v13, 0, phkResult, 0);
    else
      Key = RegOpenKeyExW(hKey, lpSubKey, 0, v13, phkResult);
    v15 = Key;
LABEL_8:
    v16 = v15 < 0;
    if ( v15 <= 0 )
      goto LABEL_10;
    goto LABEL_9;
  }
  if ( (NtCurrentTeb()->SpareUlong0 & 0x80000000) != 0 )
  {
    phkResult = (HKEY *)(v11 + 7);
    goto LABEL_5;
  }
  v15 = 2;
  v29 = 0;
  v31 = 0;
  if ( (unsigned int)NtQuerySystemInformationEx(230, &v31, 8, 0, 0, &v29) == -1073741789 )
  {
    v18 = v29 + 15LL;
    if ( v18 <= v29 )
      v18 = 0xFFFFFFFFFFFFFF0LL;
    v19 = v18 & 0xFFFFFFFFFFFFFFF0uLL;
    v20 = alloca(v19);
    v21 = alloca(v19);
    v32 = v28;
    if ( (int)NtQuerySystemInformationEx(230, &v31, 8, v28, v29, &v29) >= 0 )
    {
      LODWORD(v22) = 0;
      v30 = 0;
      v23 = v32;
      if ( *v32 )
      {
        while ( 1 )
        {
          v24 = *(_DWORD *)&v23[2 * (unsigned int)v22];
          if ( (v24 & 0x160000) == 0x120000 )
          {
            v28[0] = Wow64SetThreadDefaultGuestMachine((unsigned __int16)v24);
            samDesired = a4 | 0x20019;
            v26 = (HKEY *)(v11 + 7);
            if ( a3 )
              v27 = RegCreateKeyExW(hKey, lpSubKey, 0, 0, 0, samDesired, 0, v26, 0);
            else
              v27 = RegOpenKeyExW(hKey, lpSubKey, 0, samDesired, v26);
            v15 = v27;
            Wow64SetThreadDefaultGuestMachine(v28[0]);
            v16 = v15 < 0;
            if ( !v15 )
              goto LABEL_10;
            LODWORD(v22) = v30;
            v23 = v32;
          }
          v22 = (unsigned int)(v22 + 1);
          v30 = v22;
          if ( !v23[2 * v22] )
            goto LABEL_8;
        }
      }
    }
  }
LABEL_9:
  v15 = (unsigned __int16)v15 | 0x80070000;
  v16 = v15 < 0;
LABEL_10:
  if ( !v16 )
    v15 = Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IQuerySource,IObjectWithRegistryKey,Windows::Internal::Shell::FileAssociations::IAssociationQuerySource>>(
            v11,
            a5,
            a6);
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IQuerySource,IObjectWithRegistryKey,Windows::Internal::Shell::FileAssociations::IAssociationQuerySource>::Release(v11);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18002d090  push    rbp
0x18002d092  push    rbx
0x18002d093  push    rsi
0x18002d094  push    rdi
0x18002d095  push    r12
0x18002d097  push    r13
0x18002d099  push    r14
0x18002d09b  push    r15
0x18002d09d  sub     rsp, 88h
0x18002d0a4  lea     rbp, [rsp+50h]
0x18002d0a9  mov     rax, cs:__security_cookie
0x18002d0b0  xor     rax, rbp
0x18002d0b3  mov     [rbp+70h+var_50], rax
0x18002d0b7  mov     r14d, r9d
0x18002d0ba  mov     r15d, r8d
0x18002d0bd  mov     r12, rdx
0x18002d0c0  mov     r13, rcx
0x18002d0c3  xor     esi, esi
0x18002d0c5  mov     rdi, [rbp+70h+arg_28]
0x18002d0cc  mov     [rdi], rsi
0x18002d0cf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002d0d6  mov     ecx, 40h ; '@'; unsigned __int64
0x18002d0db  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002d0e0  mov     rbx, rax
0x18002d0e3  test    rax, rax
0x18002d0e6  jz      loc_18002D3B2
0x18002d0ec  mov     [rax+28h], rsi
0x18002d0f0  mov     [rax+30h], rsi
0x18002d0f4  mov     [rax+38h], rsi
0x18002d0f8  mov     rcx, rax
0x18002d0fb  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIQuerySource@@UIObjectWithRegistryKey@@UIAssociationQuerySource@FileAssociations@Shell@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IQuerySource,IObjectWithRegistryKey,Windows::Internal::Shell::FileAssociations::IAssociationQuerySource>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IQuerySource,IObjectWithRegistryKey,Windows::Internal::Shell::FileAssociations::IAssociationQuerySource>(void)
0x18002d100  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIQuerySource@@UIObjectWithRegistryKey@@UIAssociationQuerySource@FileAssociations@Shell@Internal@Windows@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IQuerySource,IObjectWithRegistryKey,Windows::Internal::Shell::FileAssociations::IAssociationQuerySource>::`vftable'
0x18002d107  mov     [rbx], rcx
0x18002d10a  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIQuerySource@@UIObjectWithRegistryKey@@UIAssociationQuerySource@FileAssociations@Shell@Internal@Windows@@@WRL@Microsoft@@6BIQuerySource@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IQuerySource,IObjectWithRegistryKey,Windows::Internal::Shell::FileAssociations::IAssociationQuerySource>::`vftable'{for `IQuerySource'}
0x18002d111  mov     [rbx+8], rax
0x18002d115  lea     rax, ??_7CRegistrySource@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@UIObjectWithRegistryKey@@UIAssociationQuerySource@FileAssociations@Shell@Internal@Windows@@@Details@WRL@Microsoft@@@; const CRegistrySource::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,IObjectWithRegistryKey,Windows::Internal::Shell::FileAssociations::IAssociationQuerySource>'}
0x18002d11c  mov     [rbx+10h], rax
0x18002d120  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIQuerySource@@UIObjectWithRegistryKey@@UIAssociationQuerySource@FileAssociations@Shell@Internal@Windows@@@WRL@Microsoft@@6BIObjectWithRegistryKey@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IQuerySource,IObjectWithRegistryKey,Windows::Internal::Shell::FileAssociations::IAssociationQuerySource>::`vftable'{for `IObjectWithRegistryKey'}
0x18002d127  mov     [rbx+18h], rax
0x18002d12b  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIQuerySource@@UIObjectWithRegistryKey@@UIAssociationQuerySource@FileAssociations@Shell@Internal@Windows@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIAssociationQuerySource@FileAssociations@Shell@Internal@Windows@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IQuerySource,IObjectWithRegistryKey,Windows::Internal::Shell::FileAssociations::IAssociationQuerySource>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Internal::Shell::FileAssociations::IAssociationQuerySource>'}
0x18002d132  mov     [rbx+20h], rax
0x18002d136  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18002d13d  test    rcx, rcx
0x18002d140  jz      short loc_18002D14F
0x18002d142  mov     rax, [rcx]
0x18002d145  mov     rax, [rax+8]
0x18002d149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d14e  nop
0x18002d14f  lea     rax, ??_7CRegistrySource@@6B@; const CRegistrySource::`vftable'
0x18002d156  mov     [rbx], rax
0x18002d159  lea     rax, ??_7CRegistrySource@@6BIQuerySource@@@; const CRegistrySource::`vftable'{for `IQuerySource'}
0x18002d160  mov     [rbx+8], rax
0x18002d164  lea     rax, ??_7CRegistrySource@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@UIObjectWithRegistryKey@@UIAssociationQuerySource@FileAssociations@Shell@Internal@Windows@@@Details@WRL@Microsoft@@@; const CRegistrySource::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,IObjectWithRegistryKey,Windows::Internal::Shell::FileAssociations::IAssociationQuerySource>'}
0x18002d16b  mov     [rbx+10h], rax
0x18002d16f  lea     rax, ??_7CRegistrySource@@6BIObjectWithRegistryKey@@@; const CRegistrySource::`vftable'{for `IObjectWithRegistryKey'}
0x18002d176  mov     [rbx+18h], rax
0x18002d17a  lea     rax, ??_7CRegistrySource@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIAssociationQuerySource@FileAssociations@Shell@Internal@Windows@@@Details@WRL@Microsoft@@@; const CRegistrySource::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Internal::Shell::FileAssociations::IAssociationQuerySource>'}
0x18002d181  mov     [rbx+20h], rax
0x18002d185  lea     rax, [rbx+38h]
0x18002d189  mov     [rax], rsi
0x18002d18c  bt      r14d, 9
0x18002d191  jb      short loc_18002D208
0x18002d193  or      r14d, 20019h
0x18002d19a  xor     r8d, r8d; Reserved
0x18002d19d  mov     rdx, r12; lpSubKey
0x18002d1a0  mov     rcx, r13; hKey
0x18002d1a3  test    r15d, r15d
0x18002d1a6  jnz     loc_18002D383
0x18002d1ac  mov     [rsp+0C0h+phkResult], rax; phkResult
0x18002d1b1  mov     r9d, r14d; samDesired
0x18002d1b4  call    cs:__imp_RegOpenKeyExW
0x18002d1ba  mov     esi, eax
0x18002d1bc  test    esi, esi
0x18002d1be  jle     short loc_18002D1CB
0x18002d1c0  movzx   esi, si
0x18002d1c3  or      esi, 80070000h
0x18002d1c9  test    esi, esi
0x18002d1cb  js      short loc_18002D1E1
0x18002d1cd  mov     r8, rdi
0x18002d1d0  mov     rdx, [rbp+70h+arg_20]
0x18002d1d7  mov     rcx, rbx
0x18002d1da  call    ??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIQuerySource@@UIObjectWithRegistryKey@@UIAssociationQuerySource@FileAssociations@Shell@Internal@Windows@@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$02@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIQuerySource@@UIObjectWithRegistryKey@@UIAssociationQuerySource@FileAssociations@Shell@Internal@Windows@@@123@AEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IQuerySource,IObjectWithRegistryKey,Windows::Internal::Shell::FileAssociations::IAssociationQuerySource>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IQuerySource,IObjectWithRegistryKey,Windows::Internal::Shell::FileAssociations::IAssociationQuerySource> *,_GUID const &,void * *)
0x18002d1df  mov     esi, eax
0x18002d1e1  mov     rcx, rbx
0x18002d1e4  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIQuerySource@@UIObjectWithRegistryKey@@UIAssociationQuerySource@FileAssociations@Shell@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IQuerySource,IObjectWithRegistryKey,Windows::Internal::Shell::FileAssociations::IAssociationQuerySource>::Release(void)
0x18002d1e9  mov     eax, esi
0x18002d1eb  mov     rcx, [rbp+70h+var_50]
0x18002d1ef  xor     rcx, rbp; StackCookie
0x18002d1f2  call    __security_check_cookie
0x18002d1f7  lea     rsp, [rbp+38h]
0x18002d1fb  pop     r15
0x18002d1fd  pop     r14
0x18002d1ff  pop     r13
0x18002d201  pop     r12
0x18002d203  pop     rdi
0x18002d204  pop     rsi
0x18002d205  pop     rbx
0x18002d206  pop     rbp
0x18002d207  retn
0x18002d208  mov     rax, gs:30h
0x18002d211  cmp     dword ptr [rax+180Ch], 0
0x18002d218  jl      loc_18002D3A9
0x18002d21e  mov     esi, 2
0x18002d223  mov     [rbp+70h+var_6C], 0
0x18002d22a  mov     [rbp+70h+var_60], 0
0x18002d232  lea     rax, [rbp+70h+var_6C]
0x18002d236  mov     qword ptr [rsp+0C0h+samDesired], rax
0x18002d23b  mov     dword ptr [rsp+0C0h+phkResult], 0
0x18002d243  xor     r9d, r9d
0x18002d246  mov     r8d, 8
0x18002d24c  lea     rdx, [rbp+70h+var_60]
0x18002d250  mov     ecx, 0E6h
0x18002d255  call    cs:__imp_NtQuerySystemInformationEx
0x18002d25b  cmp     eax, 0C0000023h
0x18002d260  jnz     loc_18002D1C0
0x18002d266  mov     edx, [rbp+70h+var_6C]
0x18002d269  lea     rcx, [rdx+0Fh]
0x18002d26d  cmp     rcx, rdx
0x18002d270  ja      short loc_18002D27C
0x18002d272  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18002d27c  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18002d280  mov     rax, rcx
0x18002d283  call    _alloca_probe
0x18002d288  sub     rsp, rcx
0x18002d28b  lea     rax, [rsp+0C0h+var_70]
0x18002d290  mov     [rbp+70h+var_58], rax
0x18002d294  lea     r9, [rbp+70h+var_6C]
0x18002d298  mov     qword ptr [rsp+0C0h+samDesired], r9
0x18002d29d  mov     dword ptr [rsp+0C0h+phkResult], edx
0x18002d2a1  mov     r9, rax
0x18002d2a4  mov     r8d, 8
0x18002d2aa  lea     rdx, [rbp+70h+var_60]
0x18002d2ae  mov     ecx, 0E6h
0x18002d2b3  call    cs:__imp_NtQuerySystemInformationEx
0x18002d2b9  test    eax, eax
0x18002d2bb  js      loc_18002D1C0
0x18002d2c1  xor     ecx, ecx
0x18002d2c3  mov     [rbp+70h+var_68], ecx
0x18002d2c6  mov     rdx, [rbp+70h+var_58]
0x18002d2ca  movzx   eax, word ptr [rdx]
0x18002d2cd  test    eax, eax
0x18002d2cf  jz      loc_18002D1C0
0x18002d2d5  mov     eax, ecx
0x18002d2d7  mov     r8d, [rdx+rax*4]
0x18002d2db  mov     eax, r8d
0x18002d2de  and     eax, 160000h
0x18002d2e3  cmp     eax, 120000h
0x18002d2e8  jnz     short loc_18002D33C
0x18002d2ea  movzx   ecx, r8w
0x18002d2ee  call    cs:__imp_Wow64SetThreadDefaultGuestMachine
0x18002d2f4  mov     [rbp+70h+var_70], ax
0x18002d2f8  mov     ecx, r14d
0x18002d2fb  or      ecx, 20019h
0x18002d301  lea     rax, [rbx+38h]
0x18002d305  xor     r8d, r8d; Reserved
0x18002d308  mov     rdx, r12; lpSubKey
0x18002d30b  test    r15d, r15d
0x18002d30e  jnz     short loc_18002D352
0x18002d310  mov     [rsp+0C0h+phkResult], rax; phkResult
0x18002d315  mov     r9d, ecx; samDesired
0x18002d318  mov     rcx, r13; hKey
0x18002d31b  call    cs:__imp_RegOpenKeyExW
0x18002d321  mov     esi, eax
0x18002d323  movzx   ecx, [rbp+70h+var_70]
0x18002d327  call    cs:__imp_Wow64SetThreadDefaultGuestMachine
0x18002d32d  test    esi, esi
0x18002d32f  jz      loc_18002D1CB
0x18002d335  mov     ecx, [rbp+70h+var_68]
0x18002d338  mov     rdx, [rbp+70h+var_58]
0x18002d33c  inc     ecx
0x18002d33e  mov     [rbp+70h+var_68], ecx
0x18002d341  movzx   ecx, word ptr [rdx+rcx*4]
0x18002d345  test    ecx, ecx
0x18002d347  mov     ecx, [rbp+70h+var_68]
0x18002d34a  jz      loc_18002D1BC
0x18002d350  jmp     short loc_18002D2D5
0x18002d352  mov     [rsp+0C0h+lpdwDisposition], 0; lpdwDisposition
0x18002d35b  mov     [rsp+0C0h+var_88], rax; phkResult
0x18002d360  mov     [rsp+0C0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18002d369  mov     [rsp+0C0h+samDesired], ecx; samDesired
0x18002d36d  mov     dword ptr [rsp+0C0h+phkResult], 0; dwOptions
0x18002d375  xor     r9d, r9d; lpClass
0x18002d378  mov     rcx, r13; hKey
0x18002d37b  call    cs:__imp_RegCreateKeyExW
0x18002d381  jmp     short loc_18002D321
0x18002d383  mov     [rsp+0C0h+lpdwDisposition], rsi; lpdwDisposition
0x18002d388  mov     [rsp+0C0h+var_88], rax; phkResult
0x18002d38d  mov     [rsp+0C0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18002d392  mov     [rsp+0C0h+samDesired], r14d; samDesired
0x18002d397  mov     dword ptr [rsp+0C0h+phkResult], esi; dwOptions
0x18002d39b  xor     r9d, r9d; lpClass
0x18002d39e  call    cs:__imp_RegCreateKeyExW
0x18002d3a4  jmp     loc_18002D1BA
0x18002d3a9  lea     rax, [rbx+38h]
0x18002d3ad  jmp     loc_18002D193
0x18002d3b2  mov     eax, 8007000Eh
0x18002d3b7  jmp     loc_18002D1EB
```
