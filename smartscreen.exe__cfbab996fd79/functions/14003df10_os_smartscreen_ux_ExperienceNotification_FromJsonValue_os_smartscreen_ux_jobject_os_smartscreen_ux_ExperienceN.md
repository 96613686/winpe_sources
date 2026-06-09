# os_smartscreen::ux::ExperienceNotification::FromJsonValue(os_smartscreen::ux::jobject &,os_smartscreen::ux::ExperienceNotification *)

- ea: `0x14003df10`
- end: `0x14003e226`
- name: `?FromJsonValue@ExperienceNotification@ux@os_smartscreen@@SAJAEAVjobject@23@PEAU123@@Z`
- size: `790`
- prototype: `__int64 __fastcall(struct os_smartscreen::ux::jobject *, struct os_smartscreen::ux::ExperienceNotification *)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140019170`

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
- `0x140026438`
- `0x140026c20`
- `0x140026c50`
- `0x140027064`
- `0x14002c2a8`
- `0x14002c318`
- `0x14003b5e8`
- `0x14003df10`
- `0x14003e22c`
- `0x140041144`
- `0x140041170`

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
        qword_140087FA8 = 0;
        qword_140087FB0 = 0;
        std::list<std::pair<std::wstring const,enum os_smartscreen::ux::NotificationButtonTarget_t>>::_Alloc_sentinel_and_proxy(&qword_140087FA8);
        std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>>>>(&qword_140087FB8);
        qword_140087FD0 = 7;
        qword_140087FD8 = 8;
        `os_smartscreen::ux::ExperienceNotification::FromJsonValue'::`2'::notify_type_map = 1065353216;
        std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,enum os_smartscreen::ux::NotificationButtonTarget_t>>>>>>::_Assign_grow(
          v5,
          16,
          qword_140087FA8);
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
      if ( *(_QWORD *)v13 == qword_140087FA8 )
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
0x14003df10  mov     [rsp-8+arg_10], rbx
0x14003df15  push    rbp
0x14003df16  push    rsi
0x14003df17  push    rdi
0x14003df18  lea     rbp, [rsp-50h]
0x14003df1d  sub     rsp, 150h
0x14003df24  mov     rax, cs:__security_cookie
0x14003df2b  xor     rax, rsp
0x14003df2e  mov     [rbp+60h+var_20], rax
0x14003df32  mov     rdi, rdx
0x14003df35  mov     rsi, rcx
0x14003df38  test    rdx, rdx
0x14003df3b  jnz     short loc_14003DF5F
0x14003df3d  mov     rcx, [rbp+68h]; this
0x14003df41  mov     ebx, 80004003h
0x14003df46  mov     r9d, ebx; char *
0x14003df49  lea     r8, aOnecoreAmcoreS_3; "onecore\\amcore\\smartscreen\\src\\clie"...
0x14003df50  mov     edx, 164h; void *
0x14003df55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003df5a  jmp     loc_14003E204
0x14003df5f  mov     rax, gs:58h
0x14003df68  mov     ecx, 4
0x14003df6d  mov     rax, [rax]
0x14003df70  mov     ecx, [rcx+rax]
0x14003df73  cmp     cs:?$TSS0@?1??FromJsonValue@ExperienceNotification@ux@os_smartscreen@@SAJAEAVjobject@34@PEAU234@@Z@4HA, ecx
0x14003df79  jle     loc_14003E09F
0x14003df7f  lea     rcx, ?$TSS0@?1??FromJsonValue@ExperienceNotification@ux@os_smartscreen@@SAJAEAVjobject@34@PEAU234@@Z@4HA
0x14003df86  call    _Init_thread_header
0x14003df8b  cmp     cs:?$TSS0@?1??FromJsonValue@ExperienceNotification@ux@os_smartscreen@@SAJAEAVjobject@34@PEAU234@@Z@4HA, 0FFFFFFFFh
0x14003df92  jnz     loc_14003E09F
0x14003df98  lea     rdx, aError; "error"
0x14003df9f  lea     rcx, [rsp+160h+var_130]
0x14003dfa4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14003dfa9  mov     [rsp+160h+var_110], 0
0x14003dfb1  lea     rdx, aWarning; "warning"
0x14003dfb8  lea     rcx, [rsp+160h+var_108]
0x14003dfbd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14003dfc2  mov     [rsp+160h+var_E8], 1
0x14003dfca  lea     rdx, aInformation_0; "information"
0x14003dfd1  lea     rcx, [rbp+60h+var_E0]
0x14003dfd5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14003dfda  mov     [rbp+60h+var_C0], 2
0x14003dfe1  mov     cs:?notify_type_map@?1??FromJsonValue@ExperienceNotification@ux@os_smartscreen@@SAJAEAVjobject@34@PEAU234@@Z@4V?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationType_t@ux@os_smartscreen@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationType_t@ux@os_smartscreen@@@std@@@2@@std@@A, 0; std::unordered_map<std::wstring,os_smartscreen::ux::NotificationType_t> `os_smartscreen::ux::ExperienceNotification::FromJsonValue(os_smartscreen::ux::jobject &,os_smartscreen::ux::ExperienceNotification *)'::`2'::notify_type_map
0x14003dfeb  mov     cs:qword_140087FA8, 0
0x14003dff6  mov     cs:qword_140087FB0, 0
0x14003e001  lea     rcx, qword_140087FA8
0x14003e008  call    ?_Alloc_sentinel_and_proxy@?$list@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationButtonTarget_t@ux@os_smartscreen@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationButtonTarget_t@ux@os_smartscreen@@@std@@@2@@std@@AEAAXXZ; std::list<std::pair<std::wstring const,os_smartscreen::ux::NotificationButtonTarget_t>>::_Alloc_sentinel_and_proxy(void)
0x14003e00d  nop
0x14003e00e  lea     rcx, qword_140087FB8
0x14003e015  call    ??$?0AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>>>>(std::allocator<std::pair<std::wstring const,std::wstring>> const &)
0x14003e01a  nop
0x14003e01b  mov     cs:qword_140087FD0, 7
0x14003e026  mov     cs:qword_140087FD8, 8
0x14003e031  mov     cs:?notify_type_map@?1??FromJsonValue@ExperienceNotification@ux@os_smartscreen@@SAJAEAVjobject@34@PEAU234@@Z@4V?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationType_t@ux@os_smartscreen@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationType_t@ux@os_smartscreen@@@std@@@2@@std@@A, 3F800000h; std::unordered_map<std::wstring,os_smartscreen::ux::NotificationType_t> `os_smartscreen::ux::ExperienceNotification::FromJsonValue(os_smartscreen::ux::jobject &,os_smartscreen::ux::ExperienceNotification *)'::`2'::notify_type_map
0x14003e03b  mov     r8, cs:qword_140087FA8
0x14003e042  mov     edx, 10h
0x14003e047  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationButtonTarget_t@ux@os_smartscreen@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationButtonTarget_t@ux@os_smartscreen@@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,os_smartscreen::ux::NotificationButtonTarget_t>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,os_smartscreen::ux::NotificationButtonTarget_t>>>>)
0x14003e04c  nop
0x14003e04d  lea     rbx, [rsp+160h+var_130]
0x14003e052  mov     r8, rbx
0x14003e055  lea     rdx, [rsp+160h+var_140]
0x14003e05a  call    ??$emplace@AEBU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationType_t@ux@os_smartscreen@@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationType_t@ux@os_smartscreen@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationType_t@ux@os_smartscreen@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationType_t@ux@os_smartscreen@@@std@@@std@@@std@@@std@@_N@1@AEBU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationType_t@ux@os_smartscreen@@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,os_smartscreen::ux::NotificationType_t,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,os_smartscreen::ux::NotificationType_t>>,0>>::emplace<std::pair<std::wstring const,os_smartscreen::ux::NotificationType_t> const &>(std::pair<std::wstring const,os_smartscreen::ux::NotificationType_t> const &)
0x14003e05f  add     rbx, 28h ; '('
0x14003e063  lea     rax, [rbp+60h+var_B8]
0x14003e067  cmp     rbx, rax
0x14003e06a  jnz     short loc_14003E052
0x14003e06c  lea     r9, ??1path@@QEAA@XZ; void (*)(void *)
0x14003e073  mov     edx, 28h ; '('; unsigned __int64
0x14003e078  lea     r8d, [rdx-25h]; unsigned __int64
0x14003e07c  lea     rcx, [rsp+160h+var_130]; void *
0x14003e081  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x14003e086  lea     rcx, ??__Fnotify_type_map@?1??FromJsonValue@ExperienceNotification@ux@os_smartscreen@@SAJAEAVjobject@23@PEAU123@@Z@YAXXZ; void (__cdecl *)()
0x14003e08d  call    atexit
0x14003e092  nop
0x14003e093  lea     rcx, ?$TSS0@?1??FromJsonValue@ExperienceNotification@ux@os_smartscreen@@SAJAEAVjobject@34@PEAU234@@Z@4HA
0x14003e09a  call    _Init_thread_footer
0x14003e09f  lea     r8, aType_0; "type"
0x14003e0a6  lea     rdx, [rsp+160h+var_140]
0x14003e0ab  mov     rcx, rsi
0x14003e0ae  call    ?Pointer@jobject@ux@os_smartscreen@@QEBA?AV123@QEBD@Z; os_smartscreen::ux::jobject::Pointer(char const * const)
0x14003e0b3  lea     rdx, [rbp+60h+var_48]
0x14003e0b7  lea     rcx, [rsp+160h+var_140]
0x14003e0bc  call    ?maybe_string@jobject@ux@os_smartscreen@@QEBA?AV?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@XZ; os_smartscreen::ux::jobject::maybe_string(void)
0x14003e0c1  nop
0x14003e0c2  cmp     [rbp+60h+var_28], 0
0x14003e0c6  jz      loc_14003E1DD
0x14003e0cc  cmp     [rbp+60h+var_38], 0
0x14003e0d1  jz      loc_14003E1DD
0x14003e0d7  lea     rcx, [rbp+60h+var_48]
0x14003e0db  call    ?value@?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEGBAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::optional<std::wstring>::value(void)
0x14003e0e0  mov     rdx, rax
0x14003e0e3  lea     rcx, [rbp+60h+var_B0]
0x14003e0e7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14003e0ec  mov     rdx, rax
0x14003e0ef  lea     rcx, [rbp+60h+var_90]
0x14003e0f3  call    _anonymous_namespace___StringUtil__ToLower
0x14003e0f8  nop
0x14003e0f9  lea     r8, [rbp+60h+var_90]
0x14003e0fd  lea     rdx, [rsp+160h+var_140]
0x14003e102  call    ?find@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationType_t@ux@os_smartscreen@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationType_t@ux@os_smartscreen@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4NotificationType_t@ux@os_smartscreen@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Umap_traits<std::wstring,os_smartscreen::ux::NotificationType_t,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,os_smartscreen::ux::NotificationType_t>>,0>>::find(std::wstring const &)
0x14003e107  mov     rax, qword ptr [rsp+160h+var_140]
0x14003e10c  cmp     rax, cs:qword_140087FA8
0x14003e113  jnz     short loc_14003E141
0x14003e115  mov     rcx, [rbp+68h]; this
0x14003e119  mov     ebx, 80004005h
0x14003e11e  mov     r9d, ebx; char *
0x14003e121  lea     r8, aOnecoreAmcoreS_3; "onecore\\amcore\\smartscreen\\src\\clie"...
0x14003e128  mov     edx, 173h; void *
0x14003e12d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003e132  nop
0x14003e133  lea     rcx, [rbp+60h+var_90]; this
0x14003e137  call    ??1path@@QEAA@XZ; path::~path(void)
0x14003e13c  jmp     loc_14003E1FB
0x14003e141  mov     ecx, [rax+30h]
0x14003e144  mov     [rdi], ecx
0x14003e146  lea     r8, aTitle; "title"
0x14003e14d  lea     rdx, [rsp+160h+var_140]
0x14003e152  mov     rcx, rsi
0x14003e155  call    ?Pointer@jobject@ux@os_smartscreen@@QEBA?AV123@QEBD@Z; os_smartscreen::ux::jobject::Pointer(char const * const)
0x14003e15a  lea     rdx, [rbp+60h+var_70]
0x14003e15e  lea     rcx, [rsp+160h+var_140]
0x14003e163  call    ?maybe_string@jobject@ux@os_smartscreen@@QEBA?AV?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@XZ; os_smartscreen::ux::jobject::maybe_string(void)
0x14003e168  nop
0x14003e169  cmp     [rbp+60h+var_50], 0
0x14003e16d  jz      short loc_14003E1B1
0x14003e16f  cmp     [rbp+60h+var_60], 0
0x14003e174  jz      short loc_14003E1B1
0x14003e176  lea     rcx, [rbp+60h+var_70]
0x14003e17a  call    ?value@?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEGBAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::optional<std::wstring>::value(void)
0x14003e17f  mov     rdx, rax
0x14003e182  lea     rcx, [rdi+8]
0x14003e186  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14003e18b  lea     r8, aBody; "body"
0x14003e192  lea     rdx, [rsp+160h+var_140]
0x14003e197  mov     rcx, rsi
0x14003e19a  call    ?Pointer@jobject@ux@os_smartscreen@@QEBA?AV123@QEBD@Z; os_smartscreen::ux::jobject::Pointer(char const * const)
0x14003e19f  lea     rdx, [rdi+28h]; struct os_smartscreen::ux::NotificationBody *
0x14003e1a3  lea     rcx, [rsp+160h+var_140]; struct os_smartscreen::ux::jobject *
0x14003e1a8  call    ?FromJsonValue@NotificationBody@ux@os_smartscreen@@SAJAEAVjobject@23@PEAU123@@Z; os_smartscreen::ux::NotificationBody::FromJsonValue(os_smartscreen::ux::jobject &,os_smartscreen::ux::NotificationBody *)
0x14003e1ad  mov     ebx, eax
0x14003e1af  jmp     short loc_14003E1CF
0x14003e1b1  mov     rcx, [rbp+68h]; this
0x14003e1b5  mov     ebx, 80004005h
0x14003e1ba  mov     r9d, ebx; char *
0x14003e1bd  lea     r8, aOnecoreAmcoreS_3; "onecore\\amcore\\smartscreen\\src\\clie"...
0x14003e1c4  mov     edx, 177h; void *
0x14003e1c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003e1ce  nop
0x14003e1cf  lea     rcx, [rbp+60h+var_70]
0x14003e1d3  call    ??1?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x14003e1d8  jmp     loc_14003E133
0x14003e1dd  mov     rcx, [rbp+68h]; this
0x14003e1e1  mov     ebx, 80004003h
0x14003e1e6  mov     r9d, ebx; char *
0x14003e1e9  lea     r8, aOnecoreAmcoreS_3; "onecore\\amcore\\smartscreen\\src\\clie"...
0x14003e1f0  mov     edx, 16Dh; void *
0x14003e1f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003e1fa  nop
0x14003e1fb  lea     rcx, [rbp+60h+var_48]
0x14003e1ff  call    ??1?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x14003e204  mov     eax, ebx
0x14003e206  mov     rcx, [rbp+60h+var_20]
0x14003e20a  xor     rcx, rsp; StackCookie
0x14003e20d  call    __security_check_cookie
0x14003e212  mov     rbx, [rsp+160h+arg_10]
0x14003e21a  add     rsp, 150h
0x14003e221  pop     rdi
0x14003e222  pop     rsi
0x14003e223  pop     rbp
0x14003e224  retn
```
