# os_smartscreen::ux::ExperienceNotification::FromJsonValue(os_smartscreen::ux::jobject &,os_smartscreen::ux::ExperienceNotification *)

- ea: `0x14003c83c`
- end: `0x14003cb51`
- name: `?FromJsonValue@ExperienceNotification@ux@os_smartscreen@@SAJAEAVjobject@23@PEAU123@@Z`
- size: `789`
- prototype: `__int64 __fastcall(struct os_smartscreen::ux::jobject *, struct os_smartscreen::ux::ExperienceNotification *)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400184ac`

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
- `0x1400252c0`
- `0x140025aa0`
- `0x140025ad0`
- `0x140025ee4`
- `0x14002b0e8`
- `0x14002b158`
- `0x140039fe8`
- `0x14003c83c`
- `0x14003cb58`
- `0x14003fa10`
- `0x14003fa3c`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall os_smartscreen::ux::ExperienceNotification::FromJsonValue(
        struct os_smartscreen::ux::jobject *a1,
        struct os_smartscreen::ux::ExperienceNotification *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rcx
  __int64 v6; // rcx
  char *v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rax
  int v13[4]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v14[32]; // [rsp+30h] [rbp-D0h] BYREF
  int v15; // [rsp+50h] [rbp-B0h]
  _BYTE v16[32]; // [rsp+58h] [rbp-A8h] BYREF
  int v17; // [rsp+78h] [rbp-88h]
  _BYTE v18[32]; // [rsp+80h] [rbp-80h] BYREF
  int v19; // [rsp+A0h] [rbp-60h]
  char v20; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v21[32]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v22[32]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v23[16]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v24; // [rsp+100h] [rbp+0h]
  char v25; // [rsp+110h] [rbp+10h]
  _BYTE v26[16]; // [rsp+118h] [rbp+18h] BYREF
  __int64 v27; // [rsp+128h] [rbp+28h]
  char v28; // [rsp+138h] [rbp+38h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  if ( a2 )
  {
    if ( __TSS0__1__FromJsonValue_ExperienceNotification_ux_os_smartscreen__SAJAEAVjobject_34_PEAU234__Z_4HA > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 4LL) )
    {
      Init_thread_header(&__TSS0__1__FromJsonValue_ExperienceNotification_ux_os_smartscreen__SAJAEAVjobject_34_PEAU234__Z_4HA);
      if ( __TSS0__1__FromJsonValue_ExperienceNotification_ux_os_smartscreen__SAJAEAVjobject_34_PEAU234__Z_4HA == -1 )
      {
        std::wstring::wstring(v14, L"error");
        v15 = 0;
        std::wstring::wstring(v16, L"warning");
        v17 = 1;
        std::wstring::wstring(v18, L"information");
        v19 = 2;
        `os_smartscreen::ux::ExperienceNotification::FromJsonValue'::`2'::notify_type_map = 0;
        qword_140085FA8 = 0;
        qword_140085FB0 = 0;
        std::list<std::pair<std::wstring const,enum os_smartscreen::ux::NotificationButtonTarget_t>>::_Alloc_sentinel_and_proxy(&qword_140085FA8);
        std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>>>>(&qword_140085FB8);
        qword_140085FD0 = 7;
        qword_140085FD8 = 8;
        `os_smartscreen::ux::ExperienceNotification::FromJsonValue'::`2'::notify_type_map = 1065353216;
        std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,enum os_smartscreen::ux::NotificationButtonTarget_t>>>>>>::_Assign_grow(
          v5,
          16,
          qword_140085FA8);
        v7 = v14;
        do
        {
          std::_Hash<std::_Umap_traits<std::wstring,enum os_smartscreen::ux::NotificationType_t,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,enum os_smartscreen::ux::NotificationType_t>>,0>>::emplace<std::pair<std::wstring const,enum os_smartscreen::ux::NotificationType_t> const &>(
            v6,
            v13,
            v7);
          v7 += 40;
        }
        while ( v7 != &v20 );
        `eh vector destructor iterator'(v14, 0x28u, 3u, (void (*)(void *))path::~path);
        atexit(`os_smartscreen::ux::ExperienceNotification::FromJsonValue'::`2'::`dynamic atexit destructor for 'notify_type_map'');
        Init_thread_footer(&__TSS0__1__FromJsonValue_ExperienceNotification_ux_os_smartscreen__SAJAEAVjobject_34_PEAU234__Z_4HA);
      }
    }
    os_smartscreen::ux::jobject::Pointer(a1, v13, "type");
    os_smartscreen::ux::jobject::maybe_string(v13, v26);
    if ( v28 && v27 )
    {
      v8 = std::optional<std::wstring>::value(v26);
      v9 = std::wstring::wstring(v21, v8);
      anonymous_namespace_::StringUtil::ToLower(v22, v9);
      std::_Hash<std::_Umap_traits<std::wstring,enum os_smartscreen::ux::NotificationType_t,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,enum os_smartscreen::ux::NotificationType_t>>,0>>::find(
        v10,
        v13,
        v22);
      if ( *(_QWORD *)v13 == qword_140085FA8 )
      {
        v4 = -2147467259;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x173,
          (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\urlrep\\src\\experience.h",
          (const char *)0x80004005LL,
          v13[0]);
      }
      else
      {
        *(_DWORD *)a2 = *(_DWORD *)(*(_QWORD *)v13 + 48LL);
        os_smartscreen::ux::jobject::Pointer(a1, v13, "title");
        os_smartscreen::ux::jobject::maybe_string(v13, v23);
        if ( v25 && v24 )
        {
          v11 = std::optional<std::wstring>::value(v23);
          std::wstring::operator=((char *)a2 + 8, v11);
          os_smartscreen::ux::jobject::Pointer(a1, v13, "body");
          v4 = os_smartscreen::ux::NotificationBody::FromJsonValue(
                 (struct os_smartscreen::ux::jobject *)v13,
                 (struct os_smartscreen::ux::ExperienceNotification *)((char *)a2 + 40));
        }
        else
        {
          v4 = -2147467259;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x177,
            (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\urlrep\\src\\experience.h",
            (const char *)0x80004005LL,
            v13[0]);
        }
        std::optional<std::wstring>::~optional<std::wstring>(v23);
      }
      path::~path((path *)v22);
    }
    else
    {
      v4 = -2147467261;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x16D,
        (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\urlrep\\src\\experience.h",
        (const char *)0x80004003LL,
        v13[0]);
    }
    std::optional<std::wstring>::~optional<std::wstring>(v26);
  }
  else
  {
    v4 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x164,
      (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\urlrep\\src\\experience.h",
      (const char *)0x80004003LL,
      v13[0]);
  }
  return v4;
}

```

## disassembly

```asm
0x14003c83c  mov     [rsp-8+arg_10], rbx
0x14003c841  push    rbp
0x14003c842  push    rsi
0x14003c843  push    rdi
0x14003c844  lea     rbp, [rsp-50h]
0x14003c849  sub     rsp, 150h
0x14003c850  mov     rax, cs:__security_cookie
0x14003c857  xor     rax, rsp
0x14003c85a  mov     [rbp+60h+var_20], rax
0x14003c85e  mov     rdi, rdx
0x14003c861  mov     rsi, rcx
0x14003c864  test    rdx, rdx
0x14003c867  jnz     short loc_14003C88B
0x14003c869  mov     rcx, [rbp+68h]; this
0x14003c86d  mov     ebx, 80004003h
0x14003c872  mov     r9d, ebx; char *
0x14003c875  lea     r8, aOnecoreAmcoreS_3; "onecore\\amcore\\smartscreen\\src\\clie"...
0x14003c87c  mov     edx, 164h; void *
0x14003c881  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003c886  jmp     loc_14003CB30
0x14003c88b  mov     rax, gs:58h
0x14003c894  mov     ecx, 4
0x14003c899  mov     rax, [rax]
0x14003c89c  mov     ecx, [rcx+rax]
0x14003c89f  cmp     cs:?$TSS0@?1??FromJsonValue@ExperienceNotification@ux@os_smartscreen@@SAJAEAVjobject@34@PEAU234@@Z@4HA, ecx
0x14003c8a5  jle     loc_14003C9CB
0x14003c8ab  lea     rcx, ?$TSS0@?1??FromJsonValue@ExperienceNotification@ux@os_smartscreen@@SAJAEAVjobject@34@PEAU234@@Z@4HA
0x14003c8b2  call    _Init_thread_header
0x14003c8b7  cmp     cs:?$TSS0@?1??FromJsonValue@ExperienceNotification@ux@os_smartscreen@@SAJAEAVjobject@34@PEAU234@@Z@4HA, 0FFFFFFFFh
0x14003c8be  jnz     loc_14003C9CB
0x14003c8c4  lea     rdx, aError; "error"
0x14003c8cb  lea     rcx, [rsp+160h+var_130]
0x14003c8d0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14003c8d5  mov     [rsp+160h+var_110], 0
0x14003c8dd  lea     rdx, aWarning; "warning"
0x14003c8e4  lea     rcx, [rsp+160h+var_108]
0x14003c8e9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14003c8ee  mov     [rsp+160h+var_E8], 1
0x14003c8f6  lea     rdx, aInformation_0; "information"
0x14003c8fd  lea     rcx, [rbp+60h+var_E0]
0x14003c901  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14003c906  mov     [rbp+60h+var_C0], 2
0x14003c90d  mov     cs:?notify_type_map@?1??FromJsonValue@ExperienceNotification@ux@os_smartscreen@@SAJAEAVjobject@34@PEAU234@@Z@4V?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationType_t@ux@os_smartscreen@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationType_t@ux@os_smartscreen@@@std@@@2@@std@@A, 0; std::unordered_map<std::wstring,os_smartscreen::ux::NotificationType_t> `os_smartscreen::ux::ExperienceNotification::FromJsonValue(os_smartscreen::ux::jobject &,os_smartscreen::ux::ExperienceNotification *)'::`2'::notify_type_map
0x14003c917  mov     cs:qword_140085FA8, 0
0x14003c922  mov     cs:qword_140085FB0, 0
0x14003c92d  lea     rcx, qword_140085FA8
0x14003c934  call    ?_Alloc_sentinel_and_proxy@?$list@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationButtonTarget_t@ux@os_smartscreen@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationButtonTarget_t@ux@os_smartscreen@@@std@@@2@@std@@AEAAXXZ; std::list<std::pair<std::wstring const,os_smartscreen::ux::NotificationButtonTarget_t>>::_Alloc_sentinel_and_proxy(void)
0x14003c939  nop
0x14003c93a  lea     rcx, qword_140085FB8
0x14003c941  call    ??$?0AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>>>>(std::allocator<std::pair<std::wstring const,std::wstring>> const &)
0x14003c946  nop
0x14003c947  mov     cs:qword_140085FD0, 7
0x14003c952  mov     cs:qword_140085FD8, 8
0x14003c95d  mov     cs:?notify_type_map@?1??FromJsonValue@ExperienceNotification@ux@os_smartscreen@@SAJAEAVjobject@34@PEAU234@@Z@4V?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationType_t@ux@os_smartscreen@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationType_t@ux@os_smartscreen@@@std@@@2@@std@@A, 3F800000h; std::unordered_map<std::wstring,os_smartscreen::ux::NotificationType_t> `os_smartscreen::ux::ExperienceNotification::FromJsonValue(os_smartscreen::ux::jobject &,os_smartscreen::ux::ExperienceNotification *)'::`2'::notify_type_map
0x14003c967  mov     r8, cs:qword_140085FA8
0x14003c96e  mov     edx, 10h
0x14003c973  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationButtonTarget_t@ux@os_smartscreen@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationButtonTarget_t@ux@os_smartscreen@@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,os_smartscreen::ux::NotificationButtonTarget_t>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,os_smartscreen::ux::NotificationButtonTarget_t>>>>)
0x14003c978  nop
0x14003c979  lea     rbx, [rsp+160h+var_130]
0x14003c97e  mov     r8, rbx
0x14003c981  lea     rdx, [rsp+160h+var_140]
0x14003c986  call    ??$emplace@AEBU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationType_t@ux@os_smartscreen@@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationType_t@ux@os_smartscreen@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationType_t@ux@os_smartscreen@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationType_t@ux@os_smartscreen@@@std@@@std@@@std@@@std@@_N@1@AEBU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationType_t@ux@os_smartscreen@@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,os_smartscreen::ux::NotificationType_t,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,os_smartscreen::ux::NotificationType_t>>,0>>::emplace<std::pair<std::wstring const,os_smartscreen::ux::NotificationType_t> const &>(std::pair<std::wstring const,os_smartscreen::ux::NotificationType_t> const &)
0x14003c98b  add     rbx, 28h ; '('
0x14003c98f  lea     rax, [rbp+60h+var_B8]
0x14003c993  cmp     rbx, rax
0x14003c996  jnz     short loc_14003C97E
0x14003c998  lea     r9, ??1path@@QEAA@XZ; void (*)(void *)
0x14003c99f  mov     edx, 28h ; '('; unsigned __int64
0x14003c9a4  lea     r8d, [rdx-25h]; unsigned __int64
0x14003c9a8  lea     rcx, [rsp+160h+var_130]; void *
0x14003c9ad  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x14003c9b2  lea     rcx, ??__Fnotify_type_map@?1??FromJsonValue@ExperienceNotification@ux@os_smartscreen@@SAJAEAVjobject@23@PEAU123@@Z@YAXXZ; void (__cdecl *)()
0x14003c9b9  call    atexit
0x14003c9be  nop
0x14003c9bf  lea     rcx, ?$TSS0@?1??FromJsonValue@ExperienceNotification@ux@os_smartscreen@@SAJAEAVjobject@34@PEAU234@@Z@4HA
0x14003c9c6  call    _Init_thread_footer
0x14003c9cb  lea     r8, aType_0; "type"
0x14003c9d2  lea     rdx, [rsp+160h+var_140]
0x14003c9d7  mov     rcx, rsi
0x14003c9da  call    ?Pointer@jobject@ux@os_smartscreen@@QEBA?AV123@QEBD@Z; os_smartscreen::ux::jobject::Pointer(char const * const)
0x14003c9df  lea     rdx, [rbp+60h+var_48]
0x14003c9e3  lea     rcx, [rsp+160h+var_140]
0x14003c9e8  call    ?maybe_string@jobject@ux@os_smartscreen@@QEBA?AV?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@XZ; os_smartscreen::ux::jobject::maybe_string(void)
0x14003c9ed  nop
0x14003c9ee  cmp     [rbp+60h+var_28], 0
0x14003c9f2  jz      loc_14003CB09
0x14003c9f8  cmp     [rbp+60h+var_38], 0
0x14003c9fd  jz      loc_14003CB09
0x14003ca03  lea     rcx, [rbp+60h+var_48]
0x14003ca07  call    ?value@?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEGBAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::optional<std::wstring>::value(void)
0x14003ca0c  mov     rdx, rax
0x14003ca0f  lea     rcx, [rbp+60h+var_B0]
0x14003ca13  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14003ca18  mov     rdx, rax
0x14003ca1b  lea     rcx, [rbp+60h+var_90]
0x14003ca1f  call    _anonymous_namespace___StringUtil__ToLower
0x14003ca24  nop
0x14003ca25  lea     r8, [rbp+60h+var_90]
0x14003ca29  lea     rdx, [rsp+160h+var_140]
0x14003ca2e  call    ?find@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationType_t@ux@os_smartscreen@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationType_t@ux@os_smartscreen@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationType_t@ux@os_smartscreen@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Umap_traits<std::wstring,os_smartscreen::ux::NotificationType_t,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,os_smartscreen::ux::NotificationType_t>>,0>>::find(std::wstring const &)
0x14003ca33  mov     rax, qword ptr [rsp+160h+var_140]
0x14003ca38  cmp     rax, cs:qword_140085FA8
0x14003ca3f  jnz     short loc_14003CA6D
0x14003ca41  mov     rcx, [rbp+68h]; this
0x14003ca45  mov     ebx, 80004005h
0x14003ca4a  mov     r9d, ebx; char *
0x14003ca4d  lea     r8, aOnecoreAmcoreS_3; "onecore\\amcore\\smartscreen\\src\\clie"...
0x14003ca54  mov     edx, 173h; void *
0x14003ca59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003ca5e  nop
0x14003ca5f  lea     rcx, [rbp+60h+var_90]; this
0x14003ca63  call    ??1path@@QEAA@XZ; path::~path(void)
0x14003ca68  jmp     loc_14003CB27
0x14003ca6d  mov     ecx, [rax+30h]
0x14003ca70  mov     [rdi], ecx
0x14003ca72  lea     r8, aTitle; "title"
0x14003ca79  lea     rdx, [rsp+160h+var_140]
0x14003ca7e  mov     rcx, rsi
0x14003ca81  call    ?Pointer@jobject@ux@os_smartscreen@@QEBA?AV123@QEBD@Z; os_smartscreen::ux::jobject::Pointer(char const * const)
0x14003ca86  lea     rdx, [rbp+60h+var_70]
0x14003ca8a  lea     rcx, [rsp+160h+var_140]
0x14003ca8f  call    ?maybe_string@jobject@ux@os_smartscreen@@QEBA?AV?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@XZ; os_smartscreen::ux::jobject::maybe_string(void)
0x14003ca94  nop
0x14003ca95  cmp     [rbp+60h+var_50], 0
0x14003ca99  jz      short loc_14003CADD
0x14003ca9b  cmp     [rbp+60h+var_60], 0
0x14003caa0  jz      short loc_14003CADD
0x14003caa2  lea     rcx, [rbp+60h+var_70]
0x14003caa6  call    ?value@?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEGBAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::optional<std::wstring>::value(void)
0x14003caab  mov     rdx, rax
0x14003caae  lea     rcx, [rdi+8]
0x14003cab2  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14003cab7  lea     r8, aBody; "body"
0x14003cabe  lea     rdx, [rsp+160h+var_140]
0x14003cac3  mov     rcx, rsi
0x14003cac6  call    ?Pointer@jobject@ux@os_smartscreen@@QEBA?AV123@QEBD@Z; os_smartscreen::ux::jobject::Pointer(char const * const)
0x14003cacb  lea     rdx, [rdi+28h]; struct os_smartscreen::ux::NotificationBody *
0x14003cacf  lea     rcx, [rsp+160h+var_140]; struct os_smartscreen::ux::jobject *
0x14003cad4  call    ?FromJsonValue@NotificationBody@ux@os_smartscreen@@SAJAEAVjobject@23@PEAU123@@Z; os_smartscreen::ux::NotificationBody::FromJsonValue(os_smartscreen::ux::jobject &,os_smartscreen::ux::NotificationBody *)
0x14003cad9  mov     ebx, eax
0x14003cadb  jmp     short loc_14003CAFB
0x14003cadd  mov     rcx, [rbp+68h]; this
0x14003cae1  mov     ebx, 80004005h
0x14003cae6  mov     r9d, ebx; char *
0x14003cae9  lea     r8, aOnecoreAmcoreS_3; "onecore\\amcore\\smartscreen\\src\\clie"...
0x14003caf0  mov     edx, 177h; void *
0x14003caf5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003cafa  nop
0x14003cafb  lea     rcx, [rbp+60h+var_70]
0x14003caff  call    ??1?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x14003cb04  jmp     loc_14003CA5F
0x14003cb09  mov     rcx, [rbp+68h]; this
0x14003cb0d  mov     ebx, 80004003h
0x14003cb12  mov     r9d, ebx; char *
0x14003cb15  lea     r8, aOnecoreAmcoreS_3; "onecore\\amcore\\smartscreen\\src\\clie"...
0x14003cb1c  mov     edx, 16Dh; void *
0x14003cb21  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003cb26  nop
0x14003cb27  lea     rcx, [rbp+60h+var_48]
0x14003cb2b  call    ??1?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x14003cb30  mov     eax, ebx
0x14003cb32  mov     rcx, [rbp+60h+var_20]
0x14003cb36  xor     rcx, rsp; StackCookie
0x14003cb39  call    __security_check_cookie
0x14003cb3e  mov     rbx, [rsp+160h+arg_10]
0x14003cb46  add     rsp, 150h
0x14003cb4d  pop     rdi
0x14003cb4e  pop     rsi
0x14003cb4f  pop     rbp
0x14003cb50  retn
```
