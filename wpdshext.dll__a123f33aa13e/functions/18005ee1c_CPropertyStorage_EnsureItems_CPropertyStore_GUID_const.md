# CPropertyStorage::_EnsureItems(CPropertyStore *,_GUID const &)

- ea: `0x18005ee1c`
- end: `0x18005f158`
- name: `?_EnsureItems@CPropertyStorage@@AEAAJPEAVCPropertyStore@@AEBU_GUID@@@Z`
- size: `828`
- prototype: `int(CPropertyStorage *__hidden this, struct CPropertyStore *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18005e08c`

## callees

- `0x18000bde4`
- `0x18000d610`
- `0x18000e760`
- `0x18001f680`
- `0x18002ff5c`
- `0x180035590`
- `0x18003912c`
- `0x180039ef8`
- `0x18005e4a4`
- `0x18005ee1c`
- `0x180078010`

## import_xrefs

- `ole32!PropVariantCopy` at `0x18005efe5`
- `ole32!PropVariantCopy` at `0x18005efe5`
- `ole32!PropVariantClear` at `0x18005eff6`
- `ole32!PropVariantClear` at `0x18005f020`
- `ole32!PropVariantClear` at `0x18005f079`
- `ole32!PropVariantClear` at `0x18005eff6`
- `ole32!PropVariantClear` at `0x18005f020`
- `ole32!PropVariantClear` at `0x18005f079`

## pseudocode

```c
__int64 __fastcall CPropertyStorage::_EnsureItems(
        CPropertyStorage *this,
        struct CPropertyStore *a2,
        const struct _GUID *a3)
{
  _QWORD *v3; // r12
  int v7; // ebx
  int Stat; // eax
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  unsigned int i; // esi
  __int64 v13; // rax
  const struct std::nothrow_t *v14; // rdx
  PROPVARIANT *v15; // rdi
  HRESULT v16; // eax
  unsigned int v17; // edx
  __int64 v18; // rdx
  unsigned int v20; // eax
  unsigned int v21; // [rsp+30h] [rbp-99h] BYREF
  PROPVARIANT pvarSrc; // [rsp+38h] [rbp-91h] BYREF
  char *v23; // [rsp+50h] [rbp-79h]
  GUID rguid; // [rsp+58h] [rbp-71h] BYREF
  int v25; // [rsp+68h] [rbp-61h]
  OLECHAR sz[64]; // [rsp+70h] [rbp-59h] BYREF

  v3 = (_QWORD *)((char *)this + 80);
  v25 = 0;
  rguid = 0;
  v21 = 0;
  memset(&pvarSrc, 0, sizeof(pvarSrc));
  if ( *((_QWORD *)this + 10) )
  {
    v7 = -2147418113;
    goto LABEL_34;
  }
  if ( !(unsigned int)CDPA_Base<PROPERTY_ITEM>::Create((char *)this + 80) )
  {
    v7 = -2147024882;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_34;
    v10 = 69;
    v11 = 2147942414LL;
LABEL_9:
    WPP_SF_d(v9[2], v10, WPP_eee6ab0784cc3755dd69d149bd4fe9da_Traceguids, v11);
    goto LABEL_34;
  }
  Stat = CPropertyStore::GetStat(a2, (struct tagSTATPROPSETSTG *)((char *)this + 12));
  v7 = Stat;
  if ( Stat < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_34;
    v10 = 70;
LABEL_8:
    v11 = (unsigned int)Stat;
    goto LABEL_9;
  }
  *(struct _GUID *)((char *)this + 12) = *a3;
  Stat = (*(__int64 (__fastcall **)(struct CPropertyStore *, unsigned int *))(*(_QWORD *)a2 + 24LL))(a2, &v21);
  v7 = Stat;
  if ( Stat < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_34;
    v10 = 71;
    goto LABEL_8;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= v21 )
      goto LABEL_34;
    if ( (*(int (__fastcall **)(struct CPropertyStore *, _QWORD, GUID *))(*(_QWORD *)a2 + 32LL))(a2, i, &rguid) < 0 )
      continue;
    v13 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&rguid.Data1;
    if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&rguid.Data1 )
      v13 = *(_QWORD *)a3->Data4 - *(_QWORD *)rguid.Data4;
    if ( v13 )
      continue;
    v7 = (*(__int64 (__fastcall **)(struct CPropertyStore *, GUID *, PROPVARIANT *))(*(_QWORD *)a2 + 40LL))(
           a2,
           &rguid,
           &pvarSrc);
    if ( v7 < 0 )
      break;
    if ( pvarSrc.vt == 10 || !pvarSrc.vt )
    {
      PropVariantClear(&pvarSrc);
    }
    else
    {
      v23 = (char *)operator new(0x30u, v14);
      v15 = (PROPVARIANT *)v23;
      if ( !v23 )
      {
        v7 = -2147024882;
        goto LABEL_34;
      }
      *(_OWORD *)(v23 + 24) = 0;
      v15[1].bstrblobVal.pData = 0;
      *(GUID *)&v15->vt = rguid;
      *((_DWORD *)&v15->decVal + 4) = v25;
      v16 = PropVariantCopy(v15 + 1, &pvarSrc);
      v7 = v16;
      if ( v16 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            73,
            WPP_eee6ab0784cc3755dd69d149bd4fe9da_Traceguids,
            (unsigned int)v16);
        goto LABEL_32;
      }
      PropVariantClear(&pvarSrc);
      if ( (unsigned int)IsolationAwareDPA_InsertPtr(*v3, v18, v15) == -1 )
      {
        v7 = -2147467259;
LABEL_32:
        PROPERTY_ITEM::`scalar deleting destructor'((PROPERTY_ITEM *)v15, v17);
        goto LABEL_34;
      }
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v20 = (unsigned int)CGuidToString::CGuidToString(sz, &rguid);
    WPP_SF_Sdd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      72,
      (unsigned int)WPP_eee6ab0784cc3755dd69d149bd4fe9da_Traceguids,
      v20,
      v25,
      v7);
  }
LABEL_34:
  PropVariantClear(&pvarSrc);
  if ( v7 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, WPP_eee6ab0784cc3755dd69d149bd4fe9da_Traceguids, (unsigned int)v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18005ee1c  mov     [rsp-8+arg_10], rbx
0x18005ee21  mov     [rsp-8+arg_18], rsi
0x18005ee26  push    rbp
0x18005ee27  push    rdi
0x18005ee28  push    r12
0x18005ee2a  push    r14
0x18005ee2c  push    r15
0x18005ee2e  lea     rbp, [rsp-37h]
0x18005ee33  sub     rsp, 100h
0x18005ee3a  mov     rax, cs:__security_cookie
0x18005ee41  xor     rax, rsp
0x18005ee44  mov     [rbp+57h+var_30], rax
0x18005ee48  xor     eax, eax
0x18005ee4a  lea     r12, [rcx+50h]
0x18005ee4e  lea     rsi, WPP_GLOBAL_Control
0x18005ee55  xorps   xmm0, xmm0
0x18005ee58  mov     r15, r8
0x18005ee5b  mov     r14, rdx
0x18005ee5e  mov     rdi, rcx
0x18005ee61  mov     [rbp+57h+var_B8], eax
0x18005ee64  movups  xmmword ptr [rbp+57h+rguid.Data1], xmm0
0x18005ee68  mov     [rsp+120h+var_F0], eax
0x18005ee6c  movups  xmmword ptr [rsp+120h+pvarSrc], xmm0
0x18005ee71  mov     qword ptr [rsp+120h+pvarSrc+10h], rax
0x18005ee76  cmp     [r12], rax
0x18005ee7a  jz      short loc_18005EE86
0x18005ee7c  mov     ebx, 8000FFFFh
0x18005ee81  jmp     loc_18005F074
0x18005ee86  mov     rcx, r12
0x18005ee89  call    ?Create@?$CDPA_Base@UPROPERTY_ITEM@@@@QEAAHH@Z; CDPA_Base<PROPERTY_ITEM>::Create(int)
0x18005ee8e  test    eax, eax
0x18005ee90  jz      loc_18005F12C
0x18005ee96  lea     rdx, [rdi+0Ch]; struct tagSTATPROPSETSTG *
0x18005ee9a  mov     rcx, r14; this
0x18005ee9d  call    ?GetStat@CPropertyStore@@QEAAJPEAUtagSTATPROPSETSTG@@@Z; CPropertyStore::GetStat(tagSTATPROPSETSTG *)
0x18005eea2  mov     ebx, eax
0x18005eea4  test    eax, eax
0x18005eea6  jns     short loc_18005EEDF
0x18005eea8  mov     rcx, cs:WPP_GLOBAL_Control
0x18005eeaf  cmp     rcx, rsi
0x18005eeb2  jz      loc_18005F074
0x18005eeb8  test    byte ptr [rcx+1Ch], 2
0x18005eebc  jz      loc_18005F074
0x18005eec2  mov     edx, 46h ; 'F'
0x18005eec7  mov     r9d, eax
0x18005eeca  mov     rcx, [rcx+10h]
0x18005eece  lea     r8, WPP_eee6ab0784cc3755dd69d149bd4fe9da_Traceguids
0x18005eed5  call    WPP_SF_d
0x18005eeda  jmp     loc_18005F074
0x18005eedf  movups  xmm0, xmmword ptr [r15]
0x18005eee3  lea     rdx, [rsp+120h+var_F0]
0x18005eee8  mov     rcx, r14
0x18005eeeb  movdqu  xmmword ptr [rdi+0Ch], xmm0
0x18005eef0  mov     rax, [r14]
0x18005eef3  mov     rax, [rax+18h]
0x18005eef7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005eefc  mov     ebx, eax
0x18005eefe  test    eax, eax
0x18005ef00  jns     short loc_18005EF23
0x18005ef02  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ef09  cmp     rcx, rsi
0x18005ef0c  jz      loc_18005F074
0x18005ef12  test    byte ptr [rcx+1Ch], 2
0x18005ef16  jz      loc_18005F074
0x18005ef1c  mov     edx, 47h ; 'G'
0x18005ef21  jmp     short loc_18005EEC7
0x18005ef23  xor     esi, esi
0x18005ef25  cmp     esi, [rsp+120h+var_F0]
0x18005ef29  jnb     loc_18005F06D
0x18005ef2f  mov     rax, [r14]
0x18005ef32  lea     r8, [rbp+57h+rguid]
0x18005ef36  mov     edx, esi
0x18005ef38  mov     rcx, r14
0x18005ef3b  mov     rax, [rax+20h]
0x18005ef3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ef44  test    eax, eax
0x18005ef46  js      loc_18005F026
0x18005ef4c  mov     rax, [r15]
0x18005ef4f  sub     rax, qword ptr [rbp+57h+rguid.Data1]
0x18005ef53  jnz     short loc_18005EF5D
0x18005ef55  mov     rax, [r15+8]
0x18005ef59  sub     rax, qword ptr [rbp+57h+rguid.Data4]
0x18005ef5d  test    rax, rax
0x18005ef60  jnz     loc_18005F026
0x18005ef66  mov     rax, [r14]
0x18005ef69  lea     r8, [rsp+120h+pvarSrc]
0x18005ef6e  lea     rdx, [rbp+57h+rguid]
0x18005ef72  mov     rcx, r14
0x18005ef75  mov     rax, [rax+28h]
0x18005ef79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ef7e  mov     ebx, eax
0x18005ef80  test    eax, eax
0x18005ef82  js      loc_18005F0D7
0x18005ef88  mov     eax, 0Ah
0x18005ef8d  cmp     ax, word ptr [rsp+120h+pvarSrc]
0x18005ef92  jz      loc_18005F01B
0x18005ef98  xor     eax, eax
0x18005ef9a  cmp     ax, word ptr [rsp+120h+pvarSrc]
0x18005ef9f  jz      short loc_18005F01B
0x18005efa1  lea     ecx, [rax+30h]; unsigned __int64
0x18005efa4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18005efa9  mov     [rbp+57h+var_D0], rax
0x18005efad  mov     rdi, rax
0x18005efb0  test    rax, rax
0x18005efb3  jz      loc_18005F068
0x18005efb9  xor     eax, eax
0x18005efbb  xorps   xmm0, xmm0
0x18005efbe  movups  xmmword ptr [rdi+18h], xmm0
0x18005efc2  mov     [rdi+28h], rax
0x18005efc6  test    rdi, rdi
0x18005efc9  jz      loc_18005F068
0x18005efcf  movups  xmm0, xmmword ptr [rbp+57h+rguid.Data1]
0x18005efd3  lea     rcx, [rdi+18h]; pvarDest
0x18005efd7  lea     rdx, [rsp+120h+pvarSrc]; pvarSrc
0x18005efdc  movups  xmmword ptr [rdi], xmm0
0x18005efdf  mov     eax, [rbp+57h+var_B8]
0x18005efe2  mov     [rdi+10h], eax
0x18005efe5  call    cs:__imp_PropVariantCopy
0x18005efeb  mov     ebx, eax
0x18005efed  test    eax, eax
0x18005efef  js      short loc_18005F02D
0x18005eff1  lea     rcx, [rsp+120h+pvarSrc]; pvar
0x18005eff6  call    cs:__imp_PropVariantClear
0x18005effc  mov     rcx, [r12]
0x18005f000  mov     r8, rdi
0x18005f003  call    IsolationAwareDPA_InsertPtr
0x18005f008  cmp     eax, 0FFFFFFFFh
0x18005f00b  jnz     short loc_18005F026
0x18005f00d  mov     ebx, 80004005h
0x18005f012  lea     rsi, WPP_GLOBAL_Control
0x18005f019  jmp     short loc_18005F05E
0x18005f01b  lea     rcx, [rsp+120h+pvarSrc]; pvar
0x18005f020  call    cs:__imp_PropVariantClear
0x18005f026  inc     esi
0x18005f028  jmp     loc_18005EF25
0x18005f02d  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f034  lea     rsi, WPP_GLOBAL_Control
0x18005f03b  cmp     rcx, rsi
0x18005f03e  jz      short loc_18005F05E
0x18005f040  test    byte ptr [rcx+1Ch], 2
0x18005f044  jz      short loc_18005F05E
0x18005f046  mov     rcx, [rcx+10h]
0x18005f04a  lea     r8, WPP_eee6ab0784cc3755dd69d149bd4fe9da_Traceguids
0x18005f051  mov     edx, 49h ; 'I'
0x18005f056  mov     r9d, eax
0x18005f059  call    WPP_SF_d
0x18005f05e  mov     rcx, rdi; this
0x18005f061  call    ??_GPROPERTY_ITEM@@QEAAPEAXI@Z; PROPERTY_ITEM::`scalar deleting destructor'(uint)
0x18005f066  jmp     short loc_18005F074
0x18005f068  mov     ebx, 8007000Eh
0x18005f06d  lea     rsi, WPP_GLOBAL_Control
0x18005f074  lea     rcx, [rsp+120h+pvarSrc]; pvar
0x18005f079  call    cs:__imp_PropVariantClear
0x18005f07f  test    ebx, ebx
0x18005f081  jns     short loc_18005F0AD
0x18005f083  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f08a  cmp     rcx, rsi
0x18005f08d  jz      short loc_18005F0AD
0x18005f08f  test    byte ptr [rcx+1Ch], 2
0x18005f093  jz      short loc_18005F0AD
0x18005f095  mov     rcx, [rcx+10h]
0x18005f099  lea     r8, WPP_eee6ab0784cc3755dd69d149bd4fe9da_Traceguids
0x18005f0a0  mov     edx, 4Ah ; 'J'
0x18005f0a5  mov     r9d, ebx
0x18005f0a8  call    WPP_SF_d
0x18005f0ad  mov     eax, ebx
0x18005f0af  mov     rcx, [rbp+57h+var_30]
0x18005f0b3  xor     rcx, rsp; StackCookie
0x18005f0b6  call    __security_check_cookie
0x18005f0bb  lea     r11, [rsp+120h+var_20]
0x18005f0c3  mov     rbx, [r11+40h]
0x18005f0c7  mov     rsi, [r11+48h]
0x18005f0cb  mov     rsp, r11
0x18005f0ce  pop     r15
0x18005f0d0  pop     r14
0x18005f0d2  pop     r12
0x18005f0d4  pop     rdi
0x18005f0d5  pop     rbp
0x18005f0d6  retn
0x18005f0d7  mov     rax, cs:WPP_GLOBAL_Control
0x18005f0de  lea     rsi, WPP_GLOBAL_Control
0x18005f0e5  cmp     rax, rsi
0x18005f0e8  jz      short loc_18005F074
0x18005f0ea  test    byte ptr [rax+1Ch], 2
0x18005f0ee  jz      short loc_18005F074
0x18005f0f0  lea     rdx, [rbp+57h+rguid]; rguid
0x18005f0f4  lea     rcx, [rbp+57h+sz]; lpsz
0x18005f0f8  call    ??0CGuidToString@@QEAA@AEBU_GUID@@@Z; CGuidToString::CGuidToString(_GUID const &)
0x18005f0fd  mov     ecx, [rbp+57h+var_B8]
0x18005f100  lea     r8, WPP_eee6ab0784cc3755dd69d149bd4fe9da_Traceguids
0x18005f107  mov     [rsp+120h+var_F8], ebx
0x18005f10b  mov     edx, 48h ; 'H'
0x18005f110  mov     [rsp+120h+var_100], ecx
0x18005f114  mov     r9, rax
0x18005f117  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f11e  mov     rcx, [rcx+10h]
0x18005f122  call    WPP_SF_Sdd
0x18005f127  jmp     loc_18005F074
0x18005f12c  mov     ebx, 8007000Eh
0x18005f131  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f138  cmp     rcx, rsi
0x18005f13b  jz      loc_18005F074
0x18005f141  test    byte ptr [rcx+1Ch], 2
0x18005f145  jz      loc_18005F074
0x18005f14b  mov     edx, 45h ; 'E'
0x18005f150  mov     r9d, ebx
0x18005f153  jmp     loc_18005EECA
```
