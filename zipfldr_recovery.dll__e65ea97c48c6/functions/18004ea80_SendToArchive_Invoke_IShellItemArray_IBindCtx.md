# SendToArchive::Invoke(IShellItemArray *,IBindCtx *)

- ea: `0x18004ea80`
- end: `0x18004ef27`
- name: `?Invoke@SendToArchive@@UEAAJPEAUIShellItemArray@@PEAUIBindCtx@@@Z`
- size: `1191`
- prototype: `__int64 __fastcall(SendToArchive *__hidden this, struct IShellItemArray *, struct IBindCtx *)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180030a3c`
- `0x180031e94`
- `0x18003519c`
- `0x18003534c`
- `0x180036f50`
- `0x18003edd4`
- `0x18004de28`
- `0x18004dfcc`
- `0x18004ea80`
- `0x18004f308`
- `0x18004f418`
- `0x18004f448`
- `0x18005d9e4`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004eb75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ec0d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ec5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004eb75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ec0d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ec5c`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall SendToArchive::Invoke(SendToArchive *this, struct IShellItemArray *a2, struct IBindCtx *a3)
{
  int v5; // eax
  unsigned int v6; // ebx
  unsigned int i; // ebx
  HRESULT (__stdcall *GetItemAt)(IShellItemArray *, DWORD, IShellItem **); // rax
  int v10; // eax
  int v11; // esi
  void *v12; // rcx
  __int64 v13; // rax
  void *v14; // rcx
  void *v15; // rcx
  __int64 v16; // rbx
  __int64 (__fastcall *v17)(__int64, _QWORD, const GUID *, GUID *); // rdi
  int v18; // eax
  int v19; // eax
  unsigned int v20; // ebx
  __int64 v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rcx
  LPVOID *v24; // rax
  int ArchiveAsync; // eax
  LPVOID *p_pv; // [rsp+30h] [rbp-98h] BYREF
  __int64 v27; // [rsp+38h] [rbp-90h] BYREF
  __int64 v28; // [rsp+40h] [rbp-88h]
  _DWORD v29[2]; // [rsp+48h] [rbp-80h] BYREF
  char v30; // [rsp+50h] [rbp-78h]
  char v31; // [rsp+51h] [rbp-77h]
  __int128 v32; // [rsp+58h] [rbp-70h]
  __int64 *v33; // [rsp+68h] [rbp-60h] BYREF
  LPVOID pv; // [rsp+70h] [rbp-58h] BYREF
  unsigned int v35; // [rsp+78h] [rbp-50h] BYREF
  int v36[2]; // [rsp+80h] [rbp-48h] BYREF
  __int64 v37; // [rsp+88h] [rbp-40h] BYREF
  __int128 v38; // [rsp+90h] [rbp-38h] BYREF
  __int64 v39; // [rsp+A0h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v35 = 0;
  v5 = ((__int64 (__fastcall *)(struct IShellItemArray *, unsigned int *))a2->lpVtbl->GetCount)(a2, &v35);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x49,
      (unsigned int)"shell\\ext\\zip\\archive\\sendtoarchive.cpp",
      (const char *)(unsigned int)v5);
    return v6;
  }
  v38 = 0;
  v39 = 0;
  std::vector<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::reserve(
    &v38,
    v35);
  for ( i = 0; ; ++i )
  {
    GetItemAt = a2->lpVtbl->GetItemAt;
    if ( i >= v35 )
      break;
    v33 = 0;
    pv = 0;
    v10 = ((__int64 (__fastcall *)(struct IShellItemArray *, _QWORD, __int64 **))GetItemAt)(a2, i, &v33);
    v11 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x51,
        (unsigned int)"shell\\ext\\zip\\archive\\sendtoarchive.cpp",
        (const char *)(unsigned int)v10);
      v12 = pv;
      pv = 0;
      if ( v12 )
        CoTaskMemFree(v12);
      if ( v33 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v33);
LABEL_10:
      std::vector<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::_Tidy(&v38);
      return (unsigned int)v11;
    }
    v13 = *v33;
    p_pv = &pv;
    v27 = 0;
    LOBYTE(v28) = 1;
    v11 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(v13 + 40))(v33, 2147844096LL, &v27);
    wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x52,
        (unsigned int)"shell\\ext\\zip\\archive\\sendtoarchive.cpp",
        (const char *)(unsigned int)v11);
      v14 = pv;
      pv = 0;
      if ( v14 )
        CoTaskMemFree(v14);
      if ( v33 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v33);
      goto LABEL_10;
    }
    std::vector<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::push_back(
      &v38,
      &pv);
    v15 = pv;
    pv = 0;
    if ( v15 )
      CoTaskMemFree(v15);
    if ( v33 )
      winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v33);
  }
  *(_QWORD *)v36 = 0;
  v37 = 0;
  if ( ((int (__fastcall *)(struct IShellItemArray *, _QWORD, __int64 *))GetItemAt)(a2, 0, &v37) >= 0 )
  {
    v16 = v37;
    v17 = *(__int64 (__fastcall **)(__int64, _QWORD, const GUID *, GUID *))(*(_QWORD *)v37 + 24LL);
    if ( *(_QWORD *)v36 )
      winrt::com_ptr<IShellFolder2>::unconditional_release_ref(v36);
    v18 = v17(v16, 0, &BHID_DataObject, &GUID_0000010e_0000_0000_c000_000000000046);
    if ( v18 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x5A,
        (unsigned int)"shell\\ext\\zip\\archive\\sendtoarchive.cpp",
        (const char *)(unsigned int)v18,
        (int)v36);
  }
  v33 = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &v33,
    0);
  v19 = SendToArchive::CreateTargetFile(this, *(_QWORD *)v36, &v38, &v33);
  v20 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5E,
      (unsigned int)"shell\\ext\\zip\\archive\\sendtoarchive.cpp",
      (const char *)(unsigned int)v19);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v33);
    if ( v37 )
      winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v37);
    if ( *(_QWORD *)v36 )
      winrt::com_ptr<IShellFolder2>::unconditional_release_ref(v36);
LABEL_32:
    std::vector<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::_Tidy(&v38);
    return v20;
  }
  v29[1] = 0;
  v32 = 0;
  v21 = *((_QWORD *)this + 7);
  v29[0] = *(_DWORD *)v21;
  v30 = *(_BYTE *)(v21 + 17);
  v31 = *(_BYTE *)(v21 + 16);
  v22 = v39;
  v39 = 0;
  v23 = *((_QWORD *)&v38 + 1);
  v24 = (LPVOID *)v38;
  v38 = 0u;
  p_pv = v24;
  v27 = v23;
  v28 = v22;
  pv = v33;
  v33 = 0;
  ArchiveAsync = CreateArchiveAsync(
                   (unsigned int)v29,
                   (unsigned int)&pv,
                   (unsigned int)&p_pv,
                   *((_QWORD *)this + 11),
                   0);
  v20 = ArchiveAsync;
  if ( ArchiveAsync < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x65,
      (unsigned int)"shell\\ext\\zip\\archive\\sendtoarchive.cpp",
      (const char *)(unsigned int)ArchiveAsync);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v33);
    if ( v37 )
      winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v37);
    if ( *(_QWORD *)v36 )
      winrt::com_ptr<IShellFolder2>::unconditional_release_ref(v36);
    goto LABEL_32;
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v33);
  if ( v37 )
    winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v37);
  if ( *(_QWORD *)v36 )
    winrt::com_ptr<IShellFolder2>::unconditional_release_ref(v36);
  std::vector<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::_Tidy(&v38);
  return 0;
}

```

## disassembly

```asm
0x18004ea80  mov     r11, rsp
0x18004ea83  mov     [r11+18h], rbx
0x18004ea87  mov     [r11+20h], rsi
0x18004ea8b  push    rdi
0x18004ea8c  push    r14
0x18004ea8e  push    r15
0x18004ea90  sub     rsp, 0B0h
0x18004ea97  mov     rax, cs:__security_cookie
0x18004ea9e  xor     rax, rsp
0x18004eaa1  mov     [rsp+0C8h+var_20], rax
0x18004eaa9  mov     rdi, rdx
0x18004eaac  mov     r14, rcx
0x18004eaaf  xor     r15d, r15d
0x18004eab2  mov     [r11-50h], r15d
0x18004eab6  mov     rax, [rdx]
0x18004eab9  lea     rdx, [r11-50h]
0x18004eabd  mov     rcx, rdi
0x18004eac0  mov     rax, [rax+38h]
0x18004eac4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eac9  mov     ebx, eax
0x18004eacb  test    eax, eax
0x18004eacd  jns     short loc_18004EAF1
0x18004eacf  mov     rcx, [rsp+0C8h]
0x18004ead7  mov     r9d, eax
0x18004eada  lea     r8, aShellExtZipArc_7; "shell\\ext\\zip\\archive\\sendtoarchive"...
0x18004eae1  lea     edx, [r15+49h]
0x18004eae5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004eaea  mov     eax, ebx
0x18004eaec  jmp     loc_18004EEFD
0x18004eaf1  xorps   xmm0, xmm0
0x18004eaf4  movdqu  [rsp+0C8h+var_38], xmm0
0x18004eafd  mov     [rsp+0C8h+var_28], r15
0x18004eb05  mov     edx, [rsp+0C8h+var_50]
0x18004eb09  lea     rcx, [rsp+0C8h+var_38]
0x18004eb11  call    ?reserve@?$vector@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@V?$allocator@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@std@@@std@@QEAAX_K@Z; std::vector<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::reserve(unsigned __int64)
0x18004eb16  mov     ebx, r15d
0x18004eb19  mov     rax, [rdi]
0x18004eb1c  mov     rax, [rax+40h]
0x18004eb20  cmp     ebx, [rsp+0C8h+var_50]
0x18004eb24  jnb     loc_18004EC7B
0x18004eb2a  mov     [rsp+0C8h+var_60], r15
0x18004eb2f  mov     [rsp+0C8h+pv], r15
0x18004eb34  lea     r8, [rsp+0C8h+var_60]
0x18004eb39  mov     edx, ebx
0x18004eb3b  mov     rcx, rdi
0x18004eb3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eb43  mov     esi, eax
0x18004eb45  test    eax, eax
0x18004eb47  jns     short loc_18004EBA2
0x18004eb49  mov     rcx, [rsp+0C8h]
0x18004eb51  mov     r9d, eax
0x18004eb54  lea     r8, aShellExtZipArc_7; "shell\\ext\\zip\\archive\\sendtoarchive"...
0x18004eb5b  mov     edx, 51h ; 'Q'
0x18004eb60  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004eb65  nop
0x18004eb66  mov     rcx, [rsp+0C8h+pv]; pv
0x18004eb6b  mov     [rsp+0C8h+pv], r15
0x18004eb70  test    rcx, rcx
0x18004eb73  jz      short loc_18004EB7C
0x18004eb75  call    cs:__imp_CoTaskMemFree
0x18004eb7b  nop
0x18004eb7c  cmp     [rsp+0C8h+var_60], r15
0x18004eb81  jz      short loc_18004EB8E
0x18004eb83  lea     rcx, [rsp+0C8h+var_60]
0x18004eb88  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x18004eb8d  nop
0x18004eb8e  lea     rcx, [rsp+0C8h+var_38]
0x18004eb96  call    ?_Tidy@?$vector@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@V?$allocator@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@std@@@std@@AEAAXXZ; std::vector<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::_Tidy(void)
0x18004eb9b  mov     eax, esi
0x18004eb9d  jmp     loc_18004EEFD
0x18004eba2  mov     rcx, [rsp+0C8h+var_60]
0x18004eba7  mov     rax, [rcx]
0x18004ebaa  lea     rdx, [rsp+0C8h+pv]
0x18004ebaf  mov     [rsp+0C8h+var_98], rdx
0x18004ebb4  mov     [rsp+0C8h+var_90], r15
0x18004ebb9  mov     byte ptr [rsp+0C8h+var_88], 1
0x18004ebbe  lea     r8, [rsp+0C8h+var_90]
0x18004ebc3  mov     edx, 80058000h
0x18004ebc8  mov     rax, [rax+28h]
0x18004ebcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ebd1  mov     esi, eax
0x18004ebd3  lea     rcx, [rsp+0C8h+var_98]
0x18004ebd8  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18004ebdd  test    esi, esi
0x18004ebdf  jns     short loc_18004EC3A
0x18004ebe1  mov     rcx, [rsp+0C8h]
0x18004ebe9  mov     r9d, esi
0x18004ebec  lea     r8, aShellExtZipArc_7; "shell\\ext\\zip\\archive\\sendtoarchive"...
0x18004ebf3  mov     edx, 52h ; 'R'
0x18004ebf8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ebfd  nop
0x18004ebfe  mov     rcx, [rsp+0C8h+pv]; pv
0x18004ec03  mov     [rsp+0C8h+pv], r15
0x18004ec08  test    rcx, rcx
0x18004ec0b  jz      short loc_18004EC14
0x18004ec0d  call    cs:__imp_CoTaskMemFree
0x18004ec13  nop
0x18004ec14  cmp     [rsp+0C8h+var_60], r15
0x18004ec19  jz      short loc_18004EC26
0x18004ec1b  lea     rcx, [rsp+0C8h+var_60]
0x18004ec20  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x18004ec25  nop
0x18004ec26  lea     rcx, [rsp+0C8h+var_38]
0x18004ec2e  call    ?_Tidy@?$vector@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@V?$allocator@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@std@@@std@@AEAAXXZ; std::vector<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::_Tidy(void)
0x18004ec33  mov     eax, esi
0x18004ec35  jmp     loc_18004EEFD
0x18004ec3a  lea     rdx, [rsp+0C8h+pv]
0x18004ec3f  lea     rcx, [rsp+0C8h+var_38]
0x18004ec47  call    ?push_back@?$vector@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@V?$allocator@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@std@@@std@@QEAAX$$QEAV?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@Z; std::vector<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::push_back(wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &&)
0x18004ec4c  nop
0x18004ec4d  mov     rcx, [rsp+0C8h+pv]; pv
0x18004ec52  mov     [rsp+0C8h+pv], r15
0x18004ec57  test    rcx, rcx
0x18004ec5a  jz      short loc_18004EC63
0x18004ec5c  call    cs:__imp_CoTaskMemFree
0x18004ec62  nop
0x18004ec63  cmp     [rsp+0C8h+var_60], r15
0x18004ec68  jz      short loc_18004EC74
0x18004ec6a  lea     rcx, [rsp+0C8h+var_60]
0x18004ec6f  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x18004ec74  inc     ebx
0x18004ec76  jmp     loc_18004EB19
0x18004ec7b  mov     qword ptr [rsp+0C8h+var_48], r15
0x18004ec83  mov     [rsp+0C8h+var_40], r15
0x18004ec8b  lea     r8, [rsp+0C8h+var_40]
0x18004ec93  xor     edx, edx
0x18004ec95  mov     rcx, rdi
0x18004ec98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ec9d  test    eax, eax
0x18004ec9f  js      short loc_18004ED0F
0x18004eca1  mov     rbx, [rsp+0C8h+var_40]
0x18004eca9  mov     rax, [rbx]
0x18004ecac  mov     rdi, [rax+18h]
0x18004ecb0  cmp     qword ptr [rsp+0C8h+var_48], r15
0x18004ecb8  jz      short loc_18004ECC7
0x18004ecba  lea     rcx, [rsp+0C8h+var_48]
0x18004ecc2  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x18004ecc7  lea     rax, [rsp+0C8h+var_48]
0x18004eccf  mov     qword ptr [rsp+0C8h+var_A8], rax; int
0x18004ecd4  lea     r9, _GUID_0000010e_0000_0000_c000_000000000046
0x18004ecdb  lea     r8, BHID_DataObject
0x18004ece2  xor     edx, edx
0x18004ece4  mov     rcx, rbx
0x18004ece7  mov     rax, rdi
0x18004ecea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ecef  mov     rcx, [rsp+0C8h]; this
0x18004ecf7  test    eax, eax
0x18004ecf9  jns     short loc_18004ED0F
0x18004ecfb  mov     r9d, eax; char *
0x18004ecfe  lea     r8, aShellExtZipArc_7; "shell\\ext\\zip\\archive\\sendtoarchive"...
0x18004ed05  mov     edx, 5Ah ; 'Z'; void *
0x18004ed0a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004ed0f  mov     [rsp+0C8h+var_60], r15
0x18004ed14  xor     edx, edx
0x18004ed16  lea     rcx, [rsp+0C8h+var_60]
0x18004ed1b  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18004ed20  lea     r9, [rsp+0C8h+var_60]
0x18004ed25  lea     r8, [rsp+0C8h+var_38]
0x18004ed2d  mov     rdx, qword ptr [rsp+0C8h+var_48]
0x18004ed35  mov     rcx, r14
0x18004ed38  call    ?CreateTargetFile@SendToArchive@@AEAAJPEAUIDataObject@@AEBV?$vector@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@V?$allocator@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@std@@@std@@PEAPEAX@Z; SendToArchive::CreateTargetFile(IDataObject *,std::vector<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>> const &,void * *)
0x18004ed3d  mov     ebx, eax
0x18004ed3f  test    eax, eax
0x18004ed41  jns     short loc_18004EDAE
0x18004ed43  mov     rcx, [rsp+0C8h]
0x18004ed4b  mov     r9d, eax
0x18004ed4e  lea     r8, aShellExtZipArc_7; "shell\\ext\\zip\\archive\\sendtoarchive"...
0x18004ed55  mov     edx, 5Eh ; '^'
0x18004ed5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ed5f  lea     rcx, [rsp+0C8h+var_60]
0x18004ed64  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004ed69  nop
0x18004ed6a  cmp     [rsp+0C8h+var_40], r15
0x18004ed72  jz      short loc_18004ED82
0x18004ed74  lea     rcx, [rsp+0C8h+var_40]
0x18004ed7c  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x18004ed81  nop
0x18004ed82  cmp     qword ptr [rsp+0C8h+var_48], r15
0x18004ed8a  jz      short loc_18004ED9A
0x18004ed8c  lea     rcx, [rsp+0C8h+var_48]
0x18004ed94  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x18004ed99  nop
0x18004ed9a  lea     rcx, [rsp+0C8h+var_38]
0x18004eda2  call    ?_Tidy@?$vector@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@V?$allocator@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@std@@@std@@AEAAXXZ; std::vector<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::_Tidy(void)
0x18004eda7  mov     eax, ebx
0x18004eda9  jmp     loc_18004EEFD
0x18004edae  mov     [rsp+0C8h+var_7C], r15d
0x18004edb3  xorps   xmm0, xmm0
0x18004edb6  movdqu  [rsp+0C8h+var_70], xmm0
0x18004edbc  mov     rcx, [r14+38h]
0x18004edc0  mov     eax, [rcx]
0x18004edc2  mov     [rsp+0C8h+var_80], eax
0x18004edc6  mov     al, [rcx+11h]
0x18004edc9  mov     [rsp+0C8h+var_78], al
0x18004edcd  mov     al, [rcx+10h]
0x18004edd0  mov     [rsp+0C8h+var_77], al
0x18004edd4  mov     rdx, [rsp+0C8h+var_28]
0x18004eddc  mov     [rsp+0C8h+var_28], r15
0x18004ede4  mov     rcx, qword ptr [rsp+0C8h+var_38+8]
0x18004edec  mov     qword ptr [rsp+0C8h+var_38+8], r15
0x18004edf4  mov     rax, qword ptr [rsp+0C8h+var_38]
0x18004edfc  mov     qword ptr [rsp+0C8h+var_38], r15
0x18004ee04  mov     [rsp+0C8h+var_98], rax
0x18004ee09  mov     [rsp+0C8h+var_90], rcx
0x18004ee0e  mov     [rsp+0C8h+var_88], rdx
0x18004ee13  mov     rax, [rsp+0C8h+var_60]
0x18004ee18  mov     [rsp+0C8h+pv], rax
0x18004ee1d  mov     [rsp+0C8h+var_60], r15
0x18004ee22  mov     byte ptr [rsp+0C8h+var_A8], r15b
0x18004ee27  mov     r9, [r14+58h]
0x18004ee2b  lea     r8, [rsp+0C8h+var_98]
0x18004ee30  lea     rdx, [rsp+0C8h+pv]
0x18004ee35  lea     rcx, [rsp+0C8h+var_80]
0x18004ee3a  call    ?CreateArchiveAsync@@YAJAEBUCreateArchiveOptions@@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@V?$vector@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@V?$allocator@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@std@@@std@@PEAUIUnknown@@_N@Z; CreateArchiveAsync(CreateArchiveOptions const &,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::vector<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>,IUnknown *,bool)
0x18004ee3f  mov     ebx, eax
0x18004ee41  test    eax, eax
0x18004ee43  jns     short loc_18004EEAD
0x18004ee45  mov     rcx, [rsp+0C8h]
0x18004ee4d  mov     r9d, eax
0x18004ee50  lea     r8, aShellExtZipArc_7; "shell\\ext\\zip\\archive\\sendtoarchive"...
0x18004ee57  mov     edx, 65h ; 'e'
0x18004ee5c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ee61  lea     rcx, [rsp+0C8h+var_60]
0x18004ee66  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004ee6b  nop
0x18004ee6c  cmp     [rsp+0C8h+var_40], r15
0x18004ee74  jz      short loc_18004EE84
0x18004ee76  lea     rcx, [rsp+0C8h+var_40]
0x18004ee7e  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x18004ee83  nop
0x18004ee84  cmp     qword ptr [rsp+0C8h+var_48], r15
0x18004ee8c  jz      short loc_18004EE9C
0x18004ee8e  lea     rcx, [rsp+0C8h+var_48]
0x18004ee96  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x18004ee9b  nop
0x18004ee9c  lea     rcx, [rsp+0C8h+var_38]
0x18004eea4  call    ?_Tidy@?$vector@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@V?$allocator@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@std@@@std@@AEAAXXZ; std::vector<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::_Tidy(void)
0x18004eea9  mov     eax, ebx
0x18004eeab  jmp     short loc_18004EEFD
0x18004eead  lea     rcx, [rsp+0C8h+var_60]
0x18004eeb2  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004eeb7  nop
0x18004eeb8  cmp     [rsp+0C8h+var_40], r15
0x18004eec0  jz      short loc_18004EED0
0x18004eec2  lea     rcx, [rsp+0C8h+var_40]
0x18004eeca  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x18004eecf  nop
0x18004eed0  cmp     qword ptr [rsp+0C8h+var_48], r15
0x18004eed8  jz      short loc_18004EEE8
0x18004eeda  lea     rcx, [rsp+0C8h+var_48]
0x18004eee2  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x18004eee7  nop
0x18004eee8  lea     rcx, [rsp+0C8h+var_38]
0x18004eef0  call    ?_Tidy@?$vector@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@V?$allocator@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@std@@@std@@AEAAXXZ; std::vector<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::_Tidy(void)
0x18004eef5  xor     eax, eax
0x18004eef7  jmp     short loc_18004EEFD
0x18004eef9  mov     eax, [rsp+0C8h+var_50]
0x18004eefd  mov     rcx, [rsp+0C8h+var_20]
0x18004ef05  xor     rcx, rsp; StackCookie
0x18004ef08  call    __security_check_cookie
0x18004ef0d  lea     r11, [rsp+0C8h+var_18]
0x18004ef15  mov     rbx, [r11+30h]
0x18004ef19  mov     rsi, [r11+38h]
0x18004ef1d  mov     rsp, r11
0x18004ef20  pop     r15
0x18004ef22  pop     r14
0x18004ef24  pop     rdi
0x18004ef25  retn
```
