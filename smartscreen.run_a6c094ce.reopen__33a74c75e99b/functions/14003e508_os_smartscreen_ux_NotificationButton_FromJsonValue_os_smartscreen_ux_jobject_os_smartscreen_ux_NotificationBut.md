# os_smartscreen::ux::NotificationButton::FromJsonValue(os_smartscreen::ux::jobject &,os_smartscreen::ux::NotificationButton *)

- ea: `0x14003e508`
- end: `0x14003e820`
- name: `?FromJsonValue@NotificationButton@ux@os_smartscreen@@SAJAEAVjobject@23@PEAU123@@Z`
- size: `792`
- prototype: `__int64 __fastcall(struct os_smartscreen::ux::jobject *, struct os_smartscreen::ux::NotificationButton *)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14003c974`

## callees

- `0x140003384`
- `0x140004370`
- `0x140016ca8`
- `0x140017b84`
- `0x1400184f0`
- `0x140019740`
- `0x1400198a0`
- `0x140019f7c`
- `0x14001e2b8`
- `0x140022924`
- `0x140022958`
- `0x1400263dc`
- `0x140026c20`
- `0x140026c50`
- `0x140027064`
- `0x14002c2a8`
- `0x14002c318`
- `0x14003b46c`
- `0x14003c92c`
- `0x14003e508`
- `0x140041144`
- `0x140041170`

## string_xrefs

- `0x14003e6fb`: `actionUri`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall os_smartscreen::ux::NotificationButton::FromJsonValue(
        struct os_smartscreen::ux::jobject *a1,
        struct os_smartscreen::ux::NotificationButton *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rcx
  __int64 v6; // rcx
  _BYTE *v7; // rdi
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rcx
  _QWORD v13[4]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v14[32]; // [rsp+40h] [rbp-C0h] BYREF
  int v15; // [rsp+60h] [rbp-A0h]
  _BYTE v16[32]; // [rsp+68h] [rbp-98h] BYREF
  int v17; // [rsp+88h] [rbp-78h]
  _BYTE v18[16]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v19; // [rsp+A0h] [rbp-60h]
  char v20; // [rsp+B0h] [rbp-50h]
  _BYTE v21[40]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v22[32]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v23[40]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v24[40]; // [rsp+128h] [rbp+28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  if ( a2 )
  {
    if ( __TSS0__1__FromJsonValue_NotificationButton_ux_os_smartscreen__SAJAEAVjobject_34_PEAU234__Z_4HA > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 4LL) )
    {
      Init_thread_header(&__TSS0__1__FromJsonValue_NotificationButton_ux_os_smartscreen__SAJAEAVjobject_34_PEAU234__Z_4HA);
      if ( __TSS0__1__FromJsonValue_NotificationButton_ux_os_smartscreen__SAJAEAVjobject_34_PEAU234__Z_4HA == -1 )
      {
        std::wstring::wstring(v14, L"invisible");
        v15 = 0;
        std::wstring::wstring(v16, L"new_tab");
        v17 = 1;
        `os_smartscreen::ux::NotificationButton::FromJsonValue'::`2'::target_map = 0;
        qword_140087FE8 = 0;
        qword_140087FF0 = 0;
        std::list<std::pair<std::wstring const,enum os_smartscreen::ux::NotificationButtonTarget_t>>::_Alloc_sentinel_and_proxy(&qword_140087FE8);
        std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>>>>(&qword_140087FF8);
        qword_140088010 = 7;
        qword_140088018 = 8;
        `os_smartscreen::ux::NotificationButton::FromJsonValue'::`2'::target_map = 1065353216;
        std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,enum os_smartscreen::ux::NotificationButtonTarget_t>>>>>>::_Assign_grow(
          v5,
          16,
          qword_140087FE8);
        v7 = v14;
        do
        {
          std::_Hash<std::_Umap_traits<std::wstring,enum os_smartscreen::ux::NotificationButtonTarget_t,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,enum os_smartscreen::ux::NotificationButtonTarget_t>>,0>>::emplace<std::pair<std::wstring const,enum os_smartscreen::ux::NotificationButtonTarget_t> const &>(
            v6,
            v13,
            v7);
          v7 += 40;
        }
        while ( v7 != v18 );
        `eh vector destructor iterator'(v14, 0x28u, 2u, (void (*)(void *))path::~path);
        atexit(`os_smartscreen::ux::NotificationButton::FromJsonValue'::`2'::`dynamic atexit destructor for 'target_map'');
        Init_thread_footer(&__TSS0__1__FromJsonValue_NotificationButton_ux_os_smartscreen__SAJAEAVjobject_34_PEAU234__Z_4HA);
      }
    }
    os_smartscreen::ux::jobject::Pointer(a1, v13, "text");
    os_smartscreen::ux::jobject::maybe_string(v13, v18);
    if ( v20 && v19 )
    {
      v8 = std::optional<std::wstring>::value(v18);
      std::wstring::operator=((char *)a2 + 40, v8);
      os_smartscreen::ux::jobject::Pointer(a1, v13, "title");
      os_smartscreen::ux::jobject::maybe_string(v13, v24);
      std::optional<std::wstring>::operator=(a2, v24);
      os_smartscreen::ux::jobject::Pointer(a1, v13, "actionUri");
      os_smartscreen::ux::jobject::maybe_string(v13, v23);
      std::optional<std::wstring>::operator=((char *)a2 + 72, v23);
      os_smartscreen::ux::jobject::Pointer(a1, v13, "target");
      os_smartscreen::ux::jobject::maybe_string(v13, v21);
      if ( v21[32] )
      {
        v9 = std::optional<std::wstring>::value(v21);
        v10 = std::wstring::wstring(v13, v9);
        anonymous_namespace_::StringUtil::ToLower(v22, v10);
        std::_Hash<std::_Umap_traits<std::wstring,enum os_smartscreen::ux::NotificationButtonTarget_t,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,enum os_smartscreen::ux::NotificationButtonTarget_t>>,0>>::find(
          v11,
          v13,
          v22);
        if ( v13[0] != qword_140087FE8 )
        {
          *((_DWORD *)a2 + 28) = *(_DWORD *)(v13[0] + 48LL);
          *((_BYTE *)a2 + 116) = 1;
          *(_WORD *)((char *)a2 + 117) = *(_WORD *)((char *)v13 + 5);
          *((_BYTE *)a2 + 119) = HIBYTE(v13[0]);
        }
        path::~path((path *)v22);
      }
      std::optional<std::wstring>::~optional<std::wstring>(v21);
      std::optional<std::wstring>::~optional<std::wstring>(v23);
      std::optional<std::wstring>::~optional<std::wstring>(v24);
      v4 = 0;
    }
    else
    {
      v4 = -2147467259;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6F,
        (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\urlrep\\src\\experience.h",
        (const char *)0x80004005LL,
        v13[0]);
    }
    std::optional<std::wstring>::~optional<std::wstring>(v18);
  }
  else
  {
    v4 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x67,
      (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\urlrep\\src\\experience.h",
      (const char *)0x80004003LL,
      v13[0]);
  }
  return v4;
}

```

## disassembly

```asm
0x14003e508  mov     [rsp-8+arg_10], rbx
0x14003e50d  push    rbp
0x14003e50e  push    rsi
0x14003e50f  push    rdi
0x14003e510  lea     rbp, [rsp-60h]
0x14003e515  sub     rsp, 160h
0x14003e51c  mov     rax, cs:__security_cookie
0x14003e523  xor     rax, rsp
0x14003e526  mov     [rbp+70h+var_20], rax
0x14003e52a  mov     rbx, rdx
0x14003e52d  mov     rsi, rcx
0x14003e530  test    rdx, rdx
0x14003e533  jnz     short loc_14003E557
0x14003e535  mov     rcx, [rbp+78h]; this
0x14003e539  mov     ebx, 80004003h
0x14003e53e  mov     r9d, ebx; char *
0x14003e541  lea     r8, aOnecoreAmcoreS_3; "onecore\\amcore\\smartscreen\\src\\clie"...
0x14003e548  mov     edx, 67h ; 'g'; void *
0x14003e54d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003e552  jmp     loc_14003E7FE
0x14003e557  mov     rax, gs:58h
0x14003e560  mov     ecx, 4
0x14003e565  mov     rax, [rax]
0x14003e568  mov     eax, [rcx+rax]
0x14003e56b  cmp     cs:?$TSS0@?1??FromJsonValue@NotificationButton@ux@os_smartscreen@@SAJAEAVjobject@34@PEAU234@@Z@4HA, eax
0x14003e571  jle     loc_14003E67F
0x14003e577  lea     rcx, ?$TSS0@?1??FromJsonValue@NotificationButton@ux@os_smartscreen@@SAJAEAVjobject@34@PEAU234@@Z@4HA
0x14003e57e  call    _Init_thread_header
0x14003e583  cmp     cs:?$TSS0@?1??FromJsonValue@NotificationButton@ux@os_smartscreen@@SAJAEAVjobject@34@PEAU234@@Z@4HA, 0FFFFFFFFh
0x14003e58a  jnz     loc_14003E67F
0x14003e590  lea     rdx, aInvisible_0; "invisible"
0x14003e597  lea     rcx, [rsp+170h+var_130]
0x14003e59c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14003e5a1  mov     [rsp+170h+var_110], 0
0x14003e5a9  lea     rdx, aNewTab_0; "new_tab"
0x14003e5b0  lea     rcx, [rsp+170h+var_108]
0x14003e5b5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14003e5ba  mov     [rbp+70h+var_E8], 1
0x14003e5c1  mov     cs:?target_map@?1??FromJsonValue@NotificationButton@ux@os_smartscreen@@SAJAEAVjobject@34@PEAU234@@Z@4V?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationButtonTarget_t@ux@os_smartscreen@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationButtonTarget_t@ux@os_smartscreen@@@std@@@2@@std@@A, 0; std::unordered_map<std::wstring,os_smartscreen::ux::NotificationButtonTarget_t> `os_smartscreen::ux::NotificationButton::FromJsonValue(os_smartscreen::ux::jobject &,os_smartscreen::ux::NotificationButton *)'::`2'::target_map
0x14003e5cb  mov     cs:qword_140087FE8, 0
0x14003e5d6  mov     cs:qword_140087FF0, 0
0x14003e5e1  lea     rcx, qword_140087FE8
0x14003e5e8  call    ?_Alloc_sentinel_and_proxy@?$list@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationButtonTarget_t@ux@os_smartscreen@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationButtonTarget_t@ux@os_smartscreen@@@std@@@2@@std@@AEAAXXZ; std::list<std::pair<std::wstring const,os_smartscreen::ux::NotificationButtonTarget_t>>::_Alloc_sentinel_and_proxy(void)
0x14003e5ed  nop
0x14003e5ee  lea     rcx, qword_140087FF8
0x14003e5f5  call    ??$?0AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>>>>(std::allocator<std::pair<std::wstring const,std::wstring>> const &)
0x14003e5fa  nop
0x14003e5fb  mov     cs:qword_140088010, 7
0x14003e606  mov     cs:qword_140088018, 8
0x14003e611  mov     cs:?target_map@?1??FromJsonValue@NotificationButton@ux@os_smartscreen@@SAJAEAVjobject@34@PEAU234@@Z@4V?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationButtonTarget_t@ux@os_smartscreen@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationButtonTarget_t@ux@os_smartscreen@@@std@@@2@@std@@A, 3F800000h; std::unordered_map<std::wstring,os_smartscreen::ux::NotificationButtonTarget_t> `os_smartscreen::ux::NotificationButton::FromJsonValue(os_smartscreen::ux::jobject &,os_smartscreen::ux::NotificationButton *)'::`2'::target_map
0x14003e61b  mov     r8, cs:qword_140087FE8
0x14003e622  mov     edx, 10h
0x14003e627  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationButtonTarget_t@ux@os_smartscreen@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationButtonTarget_t@ux@os_smartscreen@@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,os_smartscreen::ux::NotificationButtonTarget_t>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,os_smartscreen::ux::NotificationButtonTarget_t>>>>)
0x14003e62c  nop
0x14003e62d  lea     rdi, [rsp+170h+var_130]
0x14003e632  mov     r8, rdi
0x14003e635  lea     rdx, [rsp+170h+var_150]
0x14003e63a  call    ??$emplace@AEBU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationButtonTarget_t@ux@os_smartscreen@@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationButtonTarget_t@ux@os_smartscreen@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationButtonTarget_t@ux@os_smartscreen@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationButtonTarget_t@ux@os_smartscreen@@@std@@@std@@@std@@@std@@_N@1@AEBU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationButtonTarget_t@ux@os_smartscreen@@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,os_smartscreen::ux::NotificationButtonTarget_t,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,os_smartscreen::ux::NotificationButtonTarget_t>>,0>>::emplace<std::pair<std::wstring const,os_smartscreen::ux::NotificationButtonTarget_t> const &>(std::pair<std::wstring const,os_smartscreen::ux::NotificationButtonTarget_t> const &)
0x14003e63f  add     rdi, 28h ; '('
0x14003e643  lea     rax, [rbp+70h+var_E0]
0x14003e647  cmp     rdi, rax
0x14003e64a  jnz     short loc_14003E632
0x14003e64c  lea     r9, ??1path@@QEAA@XZ; void (*)(void *)
0x14003e653  mov     edx, 28h ; '('; unsigned __int64
0x14003e658  lea     r8d, [rdx-26h]; unsigned __int64
0x14003e65c  lea     rcx, [rsp+170h+var_130]; void *
0x14003e661  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x14003e666  lea     rcx, ??__Ftarget_map@?1??FromJsonValue@NotificationButton@ux@os_smartscreen@@SAJAEAVjobject@23@PEAU123@@Z@YAXXZ; void (__cdecl *)()
0x14003e66d  call    atexit
0x14003e672  nop
0x14003e673  lea     rcx, ?$TSS0@?1??FromJsonValue@NotificationButton@ux@os_smartscreen@@SAJAEAVjobject@34@PEAU234@@Z@4HA
0x14003e67a  call    _Init_thread_footer
0x14003e67f  lea     r8, aText; "text"
0x14003e686  lea     rdx, [rsp+170h+var_150]
0x14003e68b  mov     rcx, rsi
0x14003e68e  call    ?Pointer@jobject@ux@os_smartscreen@@QEBA?AV123@QEBD@Z; os_smartscreen::ux::jobject::Pointer(char const * const)
0x14003e693  lea     rdx, [rbp+70h+var_E0]
0x14003e697  lea     rcx, [rsp+170h+var_150]
0x14003e69c  call    ?maybe_string@jobject@ux@os_smartscreen@@QEBA?AV?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@XZ; os_smartscreen::ux::jobject::maybe_string(void)
0x14003e6a1  nop
0x14003e6a2  cmp     [rbp+70h+var_C0], 0
0x14003e6a6  jz      loc_14003E7D7
0x14003e6ac  cmp     [rbp+70h+var_D0], 0
0x14003e6b1  jz      loc_14003E7D7
0x14003e6b7  lea     rcx, [rbp+70h+var_E0]
0x14003e6bb  call    ?value@?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEGBAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::optional<std::wstring>::value(void)
0x14003e6c0  mov     rdx, rax
0x14003e6c3  lea     rcx, [rbx+28h]
0x14003e6c7  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14003e6cc  lea     r8, aTitle; "title"
0x14003e6d3  lea     rdx, [rsp+170h+var_150]
0x14003e6d8  mov     rcx, rsi
0x14003e6db  call    ?Pointer@jobject@ux@os_smartscreen@@QEBA?AV123@QEBD@Z; os_smartscreen::ux::jobject::Pointer(char const * const)
0x14003e6e0  lea     rdx, [rbp+70h+var_48]
0x14003e6e4  lea     rcx, [rsp+170h+var_150]
0x14003e6e9  call    ?maybe_string@jobject@ux@os_smartscreen@@QEBA?AV?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@XZ; os_smartscreen::ux::jobject::maybe_string(void)
0x14003e6ee  nop
0x14003e6ef  lea     rdx, [rbp+70h+var_48]
0x14003e6f3  mov     rcx, rbx
0x14003e6f6  call    ??4?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::optional<std::wstring>::operator=(std::optional<std::wstring> const &)
0x14003e6fb  lea     r8, aActionuri; "actionUri"
0x14003e702  lea     rdx, [rsp+170h+var_150]
0x14003e707  mov     rcx, rsi
0x14003e70a  call    ?Pointer@jobject@ux@os_smartscreen@@QEBA?AV123@QEBD@Z; os_smartscreen::ux::jobject::Pointer(char const * const)
0x14003e70f  lea     rdx, [rbp+70h+var_70]
0x14003e713  lea     rcx, [rsp+170h+var_150]
0x14003e718  call    ?maybe_string@jobject@ux@os_smartscreen@@QEBA?AV?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@XZ; os_smartscreen::ux::jobject::maybe_string(void)
0x14003e71d  nop
0x14003e71e  lea     rcx, [rbx+48h]
0x14003e722  lea     rdx, [rbp+70h+var_70]
0x14003e726  call    ??4?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::optional<std::wstring>::operator=(std::optional<std::wstring> const &)
0x14003e72b  lea     r8, aTarget; "target"
0x14003e732  lea     rdx, [rsp+170h+var_150]
0x14003e737  mov     rcx, rsi
0x14003e73a  call    ?Pointer@jobject@ux@os_smartscreen@@QEBA?AV123@QEBD@Z; os_smartscreen::ux::jobject::Pointer(char const * const)
0x14003e73f  lea     rdx, [rbp+70h+var_B8]
0x14003e743  lea     rcx, [rsp+170h+var_150]
0x14003e748  call    ?maybe_string@jobject@ux@os_smartscreen@@QEBA?AV?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@XZ; os_smartscreen::ux::jobject::maybe_string(void)
0x14003e74d  nop
0x14003e74e  cmp     [rbp+70h+var_98], 0
0x14003e752  jz      short loc_14003E7B6
0x14003e754  lea     rcx, [rbp+70h+var_B8]
0x14003e758  call    ?value@?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEGBAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::optional<std::wstring>::value(void)
0x14003e75d  mov     rdx, rax
0x14003e760  lea     rcx, [rsp+170h+var_150]
0x14003e765  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14003e76a  mov     rdx, rax
0x14003e76d  lea     rcx, [rbp+70h+var_90]
0x14003e771  call    _anonymous_namespace___StringUtil__ToLower
0x14003e776  lea     r8, [rbp+70h+var_90]
0x14003e77a  lea     rdx, [rsp+170h+var_150]
0x14003e77f  call    ?find@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationButtonTarget_t@ux@os_smartscreen@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationButtonTarget_t@ux@os_smartscreen@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationButtonTarget_t@ux@os_smartscreen@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Umap_traits<std::wstring,os_smartscreen::ux::NotificationButtonTarget_t,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,os_smartscreen::ux::NotificationButtonTarget_t>>,0>>::find(std::wstring const &)
0x14003e784  mov     rax, [rsp+170h+var_150]
0x14003e789  cmp     rax, cs:qword_140087FE8
0x14003e790  jz      short loc_14003E7AC
0x14003e792  mov     ecx, [rax+30h]
0x14003e795  mov     [rbx+70h], ecx
0x14003e798  mov     byte ptr [rbx+74h], 1
0x14003e79c  movzx   eax, word ptr [rsp+170h+var_150+5]
0x14003e7a1  mov     [rbx+75h], ax
0x14003e7a5  mov     al, byte ptr [rsp+170h+var_150+7]
0x14003e7a9  mov     [rbx+77h], al
0x14003e7ac  lea     rcx, [rbp+70h+var_90]; this
0x14003e7b0  call    ??1path@@QEAA@XZ; path::~path(void)
0x14003e7b5  nop
0x14003e7b6  lea     rcx, [rbp+70h+var_B8]
0x14003e7ba  call    ??1?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x14003e7bf  nop
0x14003e7c0  lea     rcx, [rbp+70h+var_70]
0x14003e7c4  call    ??1?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x14003e7c9  nop
0x14003e7ca  lea     rcx, [rbp+70h+var_48]
0x14003e7ce  call    ??1?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x14003e7d3  xor     ebx, ebx
0x14003e7d5  jmp     short loc_14003E7F5
0x14003e7d7  mov     rcx, [rbp+78h]; this
0x14003e7db  mov     ebx, 80004005h
0x14003e7e0  mov     r9d, ebx; char *
0x14003e7e3  lea     r8, aOnecoreAmcoreS_3; "onecore\\amcore\\smartscreen\\src\\clie"...
0x14003e7ea  mov     edx, 6Fh ; 'o'; void *
0x14003e7ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003e7f4  nop
0x14003e7f5  lea     rcx, [rbp+70h+var_E0]
0x14003e7f9  call    ??1?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x14003e7fe  mov     eax, ebx
0x14003e800  mov     rcx, [rbp+70h+var_20]
0x14003e804  xor     rcx, rsp; StackCookie
0x14003e807  call    __security_check_cookie
0x14003e80c  mov     rbx, [rsp+170h+arg_10]
0x14003e814  add     rsp, 160h
0x14003e81b  pop     rdi
0x14003e81c  pop     rsi
0x14003e81d  pop     rbp
0x14003e81e  retn
```
