# os_smartscreen::ux::NotificationButton::FromJsonValue(os_smartscreen::ux::jobject &,os_smartscreen::ux::NotificationButton *)

- ea: `0x14003ce30`
- end: `0x14003d147`
- name: `?FromJsonValue@NotificationButton@ux@os_smartscreen@@SAJAEAVjobject@23@PEAU123@@Z`
- size: `791`
- prototype: `__int64 __fastcall(struct os_smartscreen::ux::jobject *, struct os_smartscreen::ux::NotificationButton *)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14003b2f4`

## callees

- `0x140003258`
- `0x140004190`
- `0x1400160b4`
- `0x140016ce4`
- `0x140017b6c`
- `0x140018a58`
- `0x140018bb4`
- `0x14001928c`
- `0x14001d2d8`
- `0x1400217b4`
- `0x1400217e8`
- `0x140025264`
- `0x140025aa0`
- `0x140025ad0`
- `0x140025ee4`
- `0x14002b0e8`
- `0x14002b158`
- `0x140039e6c`
- `0x14003b2b0`
- `0x14003ce30`
- `0x14003fa10`
- `0x14003fa3c`

## string_xrefs

- `0x14003d023`: `actionUri`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
        qword_140085FF8 = 0;
        qword_140086000 = 0;
        std::list<std::pair<std::wstring const,enum os_smartscreen::ux::NotificationButtonTarget_t>>::_Alloc_sentinel_and_proxy(&qword_140085FF8);
        std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>>>>(&qword_140086008);
        qword_140086020 = 7;
        qword_140086028 = 8;
        `os_smartscreen::ux::NotificationButton::FromJsonValue'::`2'::target_map = 1065353216;
        std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,enum os_smartscreen::ux::NotificationButtonTarget_t>>>>>>::_Assign_grow(
          v5,
          16,
          qword_140085FF8);
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
        if ( v13[0] != qword_140085FF8 )
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
0x14003ce30  mov     [rsp-8+arg_10], rbx
0x14003ce35  push    rbp
0x14003ce36  push    rsi
0x14003ce37  push    rdi
0x14003ce38  lea     rbp, [rsp-60h]
0x14003ce3d  sub     rsp, 160h
0x14003ce44  mov     rax, cs:__security_cookie
0x14003ce4b  xor     rax, rsp
0x14003ce4e  mov     [rbp+70h+var_20], rax
0x14003ce52  mov     rbx, rdx
0x14003ce55  mov     rsi, rcx
0x14003ce58  test    rdx, rdx
0x14003ce5b  jnz     short loc_14003CE7F
0x14003ce5d  mov     rcx, [rbp+78h]; this
0x14003ce61  mov     ebx, 80004003h
0x14003ce66  mov     r9d, ebx; char *
0x14003ce69  lea     r8, aOnecoreAmcoreS_3; "onecore\\amcore\\smartscreen\\src\\clie"...
0x14003ce70  mov     edx, 67h ; 'g'; void *
0x14003ce75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003ce7a  jmp     loc_14003D126
0x14003ce7f  mov     rax, gs:58h
0x14003ce88  mov     ecx, 4
0x14003ce8d  mov     rax, [rax]
0x14003ce90  mov     eax, [rcx+rax]
0x14003ce93  cmp     cs:?$TSS0@?1??FromJsonValue@NotificationButton@ux@os_smartscreen@@SAJAEAVjobject@34@PEAU234@@Z@4HA, eax
0x14003ce99  jle     loc_14003CFA7
0x14003ce9f  lea     rcx, ?$TSS0@?1??FromJsonValue@NotificationButton@ux@os_smartscreen@@SAJAEAVjobject@34@PEAU234@@Z@4HA
0x14003cea6  call    _Init_thread_header
0x14003ceab  cmp     cs:?$TSS0@?1??FromJsonValue@NotificationButton@ux@os_smartscreen@@SAJAEAVjobject@34@PEAU234@@Z@4HA, 0FFFFFFFFh
0x14003ceb2  jnz     loc_14003CFA7
0x14003ceb8  lea     rdx, aInvisible_0; "invisible"
0x14003cebf  lea     rcx, [rsp+170h+var_130]
0x14003cec4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14003cec9  mov     [rsp+170h+var_110], 0
0x14003ced1  lea     rdx, aNewTab_0; "new_tab"
0x14003ced8  lea     rcx, [rsp+170h+var_108]
0x14003cedd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14003cee2  mov     [rbp+70h+var_E8], 1
0x14003cee9  mov     cs:?target_map@?1??FromJsonValue@NotificationButton@ux@os_smartscreen@@SAJAEAVjobject@34@PEAU234@@Z@4V?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationButtonTarget_t@ux@os_smartscreen@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationButtonTarget_t@ux@os_smartscreen@@@std@@@2@@std@@A, 0; std::unordered_map<std::wstring,os_smartscreen::ux::NotificationButtonTarget_t> `os_smartscreen::ux::NotificationButton::FromJsonValue(os_smartscreen::ux::jobject &,os_smartscreen::ux::NotificationButton *)'::`2'::target_map
0x14003cef3  mov     cs:qword_140085FF8, 0
0x14003cefe  mov     cs:qword_140086000, 0
0x14003cf09  lea     rcx, qword_140085FF8
0x14003cf10  call    ?_Alloc_sentinel_and_proxy@?$list@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationButtonTarget_t@ux@os_smartscreen@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationButtonTarget_t@ux@os_smartscreen@@@std@@@2@@std@@AEAAXXZ; std::list<std::pair<std::wstring const,os_smartscreen::ux::NotificationButtonTarget_t>>::_Alloc_sentinel_and_proxy(void)
0x14003cf15  nop
0x14003cf16  lea     rcx, qword_140086008
0x14003cf1d  call    ??$?0AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>>>>(std::allocator<std::pair<std::wstring const,std::wstring>> const &)
0x14003cf22  nop
0x14003cf23  mov     cs:qword_140086020, 7
0x14003cf2e  mov     cs:qword_140086028, 8
0x14003cf39  mov     cs:?target_map@?1??FromJsonValue@NotificationButton@ux@os_smartscreen@@SAJAEAVjobject@34@PEAU234@@Z@4V?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationButtonTarget_t@ux@os_smartscreen@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationButtonTarget_t@ux@os_smartscreen@@@std@@@2@@std@@A, 3F800000h; std::unordered_map<std::wstring,os_smartscreen::ux::NotificationButtonTarget_t> `os_smartscreen::ux::NotificationButton::FromJsonValue(os_smartscreen::ux::jobject &,os_smartscreen::ux::NotificationButton *)'::`2'::target_map
0x14003cf43  mov     r8, cs:qword_140085FF8
0x14003cf4a  mov     edx, 10h
0x14003cf4f  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationButtonTarget_t@ux@os_smartscreen@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationButtonTarget_t@ux@os_smartscreen@@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,os_smartscreen::ux::NotificationButtonTarget_t>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,os_smartscreen::ux::NotificationButtonTarget_t>>>>)
0x14003cf54  nop
0x14003cf55  lea     rdi, [rsp+170h+var_130]
0x14003cf5a  mov     r8, rdi
0x14003cf5d  lea     rdx, [rsp+170h+var_150]
0x14003cf62  call    ??$emplace@AEBU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationButtonTarget_t@ux@os_smartscreen@@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationButtonTarget_t@ux@os_smartscreen@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationButtonTarget_t@ux@os_smartscreen@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationButtonTarget_t@ux@os_smartscreen@@@std@@@std@@@std@@@std@@_N@1@AEBU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationButtonTarget_t@ux@os_smartscreen@@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,os_smartscreen::ux::NotificationButtonTarget_t,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,os_smartscreen::ux::NotificationButtonTarget_t>>,0>>::emplace<std::pair<std::wstring const,os_smartscreen::ux::NotificationButtonTarget_t> const &>(std::pair<std::wstring const,os_smartscreen::ux::NotificationButtonTarget_t> const &)
0x14003cf67  add     rdi, 28h ; '('
0x14003cf6b  lea     rax, [rbp+70h+var_E0]
0x14003cf6f  cmp     rdi, rax
0x14003cf72  jnz     short loc_14003CF5A
0x14003cf74  lea     r9, ??1path@@QEAA@XZ; void (*)(void *)
0x14003cf7b  mov     edx, 28h ; '('; unsigned __int64
0x14003cf80  lea     r8d, [rdx-26h]; unsigned __int64
0x14003cf84  lea     rcx, [rsp+170h+var_130]; void *
0x14003cf89  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x14003cf8e  lea     rcx, ??__Ftarget_map@?1??FromJsonValue@NotificationButton@ux@os_smartscreen@@SAJAEAVjobject@23@PEAU123@@Z@YAXXZ; void (__cdecl *)()
0x14003cf95  call    atexit
0x14003cf9a  nop
0x14003cf9b  lea     rcx, ?$TSS0@?1??FromJsonValue@NotificationButton@ux@os_smartscreen@@SAJAEAVjobject@34@PEAU234@@Z@4HA
0x14003cfa2  call    _Init_thread_footer
0x14003cfa7  lea     r8, aText; "text"
0x14003cfae  lea     rdx, [rsp+170h+var_150]
0x14003cfb3  mov     rcx, rsi
0x14003cfb6  call    ?Pointer@jobject@ux@os_smartscreen@@QEBA?AV123@QEBD@Z; os_smartscreen::ux::jobject::Pointer(char const * const)
0x14003cfbb  lea     rdx, [rbp+70h+var_E0]
0x14003cfbf  lea     rcx, [rsp+170h+var_150]
0x14003cfc4  call    ?maybe_string@jobject@ux@os_smartscreen@@QEBA?AV?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@XZ; os_smartscreen::ux::jobject::maybe_string(void)
0x14003cfc9  nop
0x14003cfca  cmp     [rbp+70h+var_C0], 0
0x14003cfce  jz      loc_14003D0FF
0x14003cfd4  cmp     [rbp+70h+var_D0], 0
0x14003cfd9  jz      loc_14003D0FF
0x14003cfdf  lea     rcx, [rbp+70h+var_E0]
0x14003cfe3  call    ?value@?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEGBAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::optional<std::wstring>::value(void)
0x14003cfe8  mov     rdx, rax
0x14003cfeb  lea     rcx, [rbx+28h]
0x14003cfef  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14003cff4  lea     r8, aTitle; "title"
0x14003cffb  lea     rdx, [rsp+170h+var_150]
0x14003d000  mov     rcx, rsi
0x14003d003  call    ?Pointer@jobject@ux@os_smartscreen@@QEBA?AV123@QEBD@Z; os_smartscreen::ux::jobject::Pointer(char const * const)
0x14003d008  lea     rdx, [rbp+70h+var_48]
0x14003d00c  lea     rcx, [rsp+170h+var_150]
0x14003d011  call    ?maybe_string@jobject@ux@os_smartscreen@@QEBA?AV?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@XZ; os_smartscreen::ux::jobject::maybe_string(void)
0x14003d016  nop
0x14003d017  lea     rdx, [rbp+70h+var_48]
0x14003d01b  mov     rcx, rbx
0x14003d01e  call    ??4?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::optional<std::wstring>::operator=(std::optional<std::wstring> const &)
0x14003d023  lea     r8, aActionuri; "actionUri"
0x14003d02a  lea     rdx, [rsp+170h+var_150]
0x14003d02f  mov     rcx, rsi
0x14003d032  call    ?Pointer@jobject@ux@os_smartscreen@@QEBA?AV123@QEBD@Z; os_smartscreen::ux::jobject::Pointer(char const * const)
0x14003d037  lea     rdx, [rbp+70h+var_70]
0x14003d03b  lea     rcx, [rsp+170h+var_150]
0x14003d040  call    ?maybe_string@jobject@ux@os_smartscreen@@QEBA?AV?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@XZ; os_smartscreen::ux::jobject::maybe_string(void)
0x14003d045  nop
0x14003d046  lea     rcx, [rbx+48h]
0x14003d04a  lea     rdx, [rbp+70h+var_70]
0x14003d04e  call    ??4?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::optional<std::wstring>::operator=(std::optional<std::wstring> const &)
0x14003d053  lea     r8, aTarget; "target"
0x14003d05a  lea     rdx, [rsp+170h+var_150]
0x14003d05f  mov     rcx, rsi
0x14003d062  call    ?Pointer@jobject@ux@os_smartscreen@@QEBA?AV123@QEBD@Z; os_smartscreen::ux::jobject::Pointer(char const * const)
0x14003d067  lea     rdx, [rbp+70h+var_B8]
0x14003d06b  lea     rcx, [rsp+170h+var_150]
0x14003d070  call    ?maybe_string@jobject@ux@os_smartscreen@@QEBA?AV?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@XZ; os_smartscreen::ux::jobject::maybe_string(void)
0x14003d075  nop
0x14003d076  cmp     [rbp+70h+var_98], 0
0x14003d07a  jz      short loc_14003D0DE
0x14003d07c  lea     rcx, [rbp+70h+var_B8]
0x14003d080  call    ?value@?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEGBAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::optional<std::wstring>::value(void)
0x14003d085  mov     rdx, rax
0x14003d088  lea     rcx, [rsp+170h+var_150]
0x14003d08d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14003d092  mov     rdx, rax
0x14003d095  lea     rcx, [rbp+70h+var_90]
0x14003d099  call    _anonymous_namespace___StringUtil__ToLower
0x14003d09e  lea     r8, [rbp+70h+var_90]
0x14003d0a2  lea     rdx, [rsp+170h+var_150]
0x14003d0a7  call    ?find@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationButtonTarget_t@ux@os_smartscreen@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationButtonTarget_t@ux@os_smartscreen@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationButtonTarget_t@ux@os_smartscreen@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Umap_traits<std::wstring,os_smartscreen::ux::NotificationButtonTarget_t,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,os_smartscreen::ux::NotificationButtonTarget_t>>,0>>::find(std::wstring const &)
0x14003d0ac  mov     rax, [rsp+170h+var_150]
0x14003d0b1  cmp     rax, cs:qword_140085FF8
0x14003d0b8  jz      short loc_14003D0D4
0x14003d0ba  mov     ecx, [rax+30h]
0x14003d0bd  mov     [rbx+70h], ecx
0x14003d0c0  mov     byte ptr [rbx+74h], 1
0x14003d0c4  movzx   eax, word ptr [rsp+170h+var_150+5]
0x14003d0c9  mov     [rbx+75h], ax
0x14003d0cd  mov     al, byte ptr [rsp+170h+var_150+7]
0x14003d0d1  mov     [rbx+77h], al
0x14003d0d4  lea     rcx, [rbp+70h+var_90]; this
0x14003d0d8  call    ??1path@@QEAA@XZ; path::~path(void)
0x14003d0dd  nop
0x14003d0de  lea     rcx, [rbp+70h+var_B8]
0x14003d0e2  call    ??1?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x14003d0e7  nop
0x14003d0e8  lea     rcx, [rbp+70h+var_70]
0x14003d0ec  call    ??1?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x14003d0f1  nop
0x14003d0f2  lea     rcx, [rbp+70h+var_48]
0x14003d0f6  call    ??1?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x14003d0fb  xor     ebx, ebx
0x14003d0fd  jmp     short loc_14003D11D
0x14003d0ff  mov     rcx, [rbp+78h]; this
0x14003d103  mov     ebx, 80004005h
0x14003d108  mov     r9d, ebx; char *
0x14003d10b  lea     r8, aOnecoreAmcoreS_3; "onecore\\amcore\\smartscreen\\src\\clie"...
0x14003d112  mov     edx, 6Fh ; 'o'; void *
0x14003d117  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003d11c  nop
0x14003d11d  lea     rcx, [rbp+70h+var_E0]
0x14003d121  call    ??1?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x14003d126  mov     eax, ebx
0x14003d128  mov     rcx, [rbp+70h+var_20]
0x14003d12c  xor     rcx, rsp; StackCookie
0x14003d12f  call    __security_check_cookie
0x14003d134  mov     rbx, [rsp+170h+arg_10]
0x14003d13c  add     rsp, 160h
0x14003d143  pop     rdi
0x14003d144  pop     rsi
0x14003d145  pop     rbp
0x14003d146  retn
```
