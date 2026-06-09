# SendToArchive::CreateTargetFile(IDataObject *,std::vector<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>,std::allocator<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>> const &,void * *)

- ea: `0x18004dfcc`
- end: `0x18004e2e8`
- name: `?CreateTargetFile@SendToArchive@@AEAAJPEAUIDataObject@@AEBV?$vector@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@V?$allocator@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@std@@@std@@PEAPEAX@Z`
- size: `796`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004e3d0`
- `0x18004ea80`

## callees

- `0x1800207f8`
- `0x180021f0c`
- `0x180030a3c`
- `0x180031e94`
- `0x180034760`
- `0x180036f50`
- `0x180048858`
- `0x18004dfcc`
- `0x18004eff0`
- `0x18004f174`
- `0x180071010`

## import_xrefs

- `SHELL32!SHBindToObject` at `0x18004e1dd`
- `SHELL32!SHBindToObject` at `0x18004e1dd`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18004e0ac`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18004e0f2`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18004e0ac`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18004e0f2`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18004e073`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18004e073`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SendToArchive::CreateTargetFile(__int64 a1, __int64 a2, LPCWSTR **a3, _QWORD *a4)
{
  unsigned int TargetFileInDesktop; // ebx
  __int64 v9; // rax
  void *v10; // r12
  __int128 v12; // xmm6
  bool v13; // bl
  LPCITEMIDLIST v14; // rsi
  int (__fastcall *v15)(LPCITEMIDLIST, _QWORD, GUID *, void **); // r14
  void *v16; // rsi
  int (__fastcall *v17)(void *, _QWORD, GUID *, void **); // r14
  int v18; // [rsp+28h] [rbp-79h]
  void *v19; // [rsp+38h] [rbp-69h] BYREF
  void *v20; // [rsp+40h] [rbp-61h]
  __int128 v21; // [rsp+48h] [rbp-59h]
  void *ppvOut[2]; // [rsp+58h] [rbp-49h] BYREF
  void *ppv[2]; // [rsp+68h] [rbp-39h] BYREF
  LPCITEMIDLIST pidl[4]; // [rsp+78h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+100h] [rbp+5Fh]

  if ( *a3 == a3[1] )
  {
    TargetFileInDesktop = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10F,
      (unsigned int)"shell\\ext\\zip\\archive\\sendtoarchive.cpp",
      (const char *)0x80070057LL,
      v18);
    return TargetFileInDesktop;
  }
  v9 = -1;
  do
    ++v9;
  while ( (**a3)[v9] );
  ppv[0] = (void *)**a3;
  ppv[1] = (void *)v9;
  split_filename(&v19, ppv);
  v10 = v20;
  if ( !v20 )
    return 2147549183LL;
  v12 = v21;
  if ( (GetFileAttributesW(**a3) & 0x10) == 0 )
  {
    *(_OWORD *)ppv = v12;
    v12 = *(_OWORD *)split_extension(pidl, ppv);
  }
  ppvOut[0] = 0;
  if ( IUnknown_QueryService(
         *(IUnknown **)(a1 + 88),
         &IID_IFolderView,
         &GUID_24d16ee5_10f5_4de3_8766_d23779ba7a6d,
         ppvOut) >= 0
    && (*(int (__fastcall **)(void *, _QWORD))(*(_QWORD *)ppvOut[0] + 24LL))(
         ppvOut[0],
         *(_QWORD *)(*(_QWORD *)(a1 + 56) + 8LL)) < 0 )
  {
    goto LABEL_36;
  }
  ppv[0] = 0;
  v13 = 1;
  if ( IUnknown_QueryService(*(IUnknown **)(a1 + 88), &IID_IFolderView, &GUID_cde725b0_ccc9_4519_917e_325d72fab4ce, ppv) >= 0 )
  {
    pidl[0] = 0;
    if ( (*(int (__fastcall **)(void *, GUID *, LPCITEMIDLIST *))(*(_QWORD *)ppv[0] + 40LL))(
           ppv[0],
           &GUID_000214e6_0000_0000_c000_000000000046,
           pidl) >= 0 )
    {
      v14 = pidl[0];
      v15 = *(int (__fastcall **)(LPCITEMIDLIST, _QWORD, GUID *, void **))(*(_QWORD *)pidl[0] + 64LL);
      if ( ppvOut[0] )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(ppvOut);
      if ( v15(v14, 0, &GUID_24d16ee5_10f5_4de3_8766_d23779ba7a6d, ppvOut) >= 0 )
        v13 = (*(int (__fastcall **)(void *, _QWORD))(*(_QWORD *)ppvOut[0] + 24LL))(
                ppvOut[0],
                *(_QWORD *)(*(_QWORD *)(a1 + 56) + 8LL)) >= 0;
    }
    if ( pidl[0] )
      winrt::com_ptr<IShellFolder2>::unconditional_release_ref(pidl);
  }
  if ( ppv[0] )
    winrt::com_ptr<IShellFolder2>::unconditional_release_ref(ppv);
  if ( !v13 )
    goto LABEL_36;
  if ( a2 )
  {
    pidl[0] = 0;
    if ( (int)DataObj_GetFolderIDList(a2, pidl) >= 0 )
    {
      ppv[0] = 0;
      if ( SHBindToObject(0, pidl[0], 0, &GUID_000214e6_0000_0000_c000_000000000046, ppv) >= 0 )
      {
        v16 = ppv[0];
        v17 = *(int (__fastcall **)(void *, _QWORD, GUID *, void **))(*(_QWORD *)ppv[0] + 64LL);
        if ( ppvOut[0] )
          winrt::com_ptr<IShellFolder2>::unconditional_release_ref(ppvOut);
        if ( v17(v16, 0, &GUID_24d16ee5_10f5_4de3_8766_d23779ba7a6d, ppvOut) >= 0 )
          v13 = (*(int (__fastcall **)(void *, _QWORD))(*(_QWORD *)ppvOut[0] + 24LL))(
                  ppvOut[0],
                  *(_QWORD *)(*(_QWORD *)(a1 + 56) + 8LL)) >= 0;
      }
      if ( ppv[0] )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(ppv);
    }
    wil::details::unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&void ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&void ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>(pidl);
    if ( !v13 )
      goto LABEL_36;
  }
  *(_OWORD *)pidl = v12;
  ppv[0] = v19;
  ppv[1] = v10;
  if ( (int)TryCreateTargetFile((__int64)ppv, pidl, *(_QWORD *)(*(_QWORD *)(a1 + 56) + 8LL), a4) < 0 )
  {
LABEL_36:
    *(_OWORD *)ppv = v12;
    TargetFileInDesktop = SendToArchive::TryCreateTargetFileInDesktop(a1, (__int128 *)ppv, a4);
    if ( ppvOut[0] )
      winrt::com_ptr<IShellFolder2>::unconditional_release_ref(ppvOut);
    return TargetFileInDesktop;
  }
  if ( ppvOut[0] )
    winrt::com_ptr<IShellFolder2>::unconditional_release_ref(ppvOut);
  return 0;
}

```

## disassembly

```asm
0x18004dfcc  mov     rax, rsp
0x18004dfcf  push    rbp
0x18004dfd0  push    rbx
0x18004dfd1  push    rsi
0x18004dfd2  push    rdi
0x18004dfd3  push    r12
0x18004dfd5  push    r13
0x18004dfd7  push    r14
0x18004dfd9  push    r15
0x18004dfdb  lea     rbp, [rax-5Fh]
0x18004dfdf  sub     rsp, 0B8h
0x18004dfe6  movaps  xmmword ptr [rax-58h], xmm6
0x18004dfea  mov     rax, cs:__security_cookie
0x18004dff1  xor     rax, rsp
0x18004dff4  mov     [rbp+57h+var_60], rax
0x18004dff8  mov     r13, r9
0x18004dffb  mov     rbx, r8
0x18004dffe  mov     r15, rdx
0x18004e001  mov     rdi, rcx
0x18004e004  mov     rcx, [r8]
0x18004e007  cmp     rcx, [r8+8]
0x18004e00b  jnz     short loc_18004E02F
0x18004e00d  mov     rcx, [rbp+5Fh]; this
0x18004e011  mov     ebx, 80070057h
0x18004e016  mov     r9d, ebx; char *
0x18004e019  lea     r8, aShellExtZipArc_7; "shell\\ext\\zip\\archive\\sendtoarchive"...
0x18004e020  mov     edx, 10Fh; void *
0x18004e025  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e02a  jmp     loc_18004E2BE
0x18004e02f  mov     rcx, [rcx]
0x18004e032  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004e036  xor     esi, esi
0x18004e038  inc     rax
0x18004e03b  cmp     [rcx+rax*2], si
0x18004e03f  jnz     short loc_18004E038
0x18004e041  mov     [rbp+57h+ppv], rcx
0x18004e045  mov     [rbp+57h+ppv+8], rax
0x18004e049  lea     rdx, [rbp+57h+ppv]
0x18004e04d  lea     rcx, [rbp+57h+var_C0]
0x18004e051  call    ?split_filename@@YA?AU?$pair@V?$basic_string_view@GU?$char_traits@G@std@@@std@@V12@@std@@V?$basic_string_view@GU?$char_traits@G@std@@@2@@Z; split_filename(std::basic_string_view<ushort>)
0x18004e056  mov     r12, [rbp+57h+var_B8]
0x18004e05a  test    r12, r12
0x18004e05d  jnz     short loc_18004E069
0x18004e05f  mov     eax, 8000FFFFh
0x18004e064  jmp     loc_18004E2C0
0x18004e069  movups  xmm6, [rbp+57h+var_B0]
0x18004e06d  mov     rcx, [rbx]
0x18004e070  mov     rcx, [rcx]; lpFileName
0x18004e073  call    cs:__imp_GetFileAttributesW
0x18004e079  test    al, 10h
0x18004e07b  jnz     short loc_18004E092
0x18004e07d  movdqu  xmmword ptr [rbp+57h+ppv], xmm6
0x18004e082  lea     rdx, [rbp+57h+ppv]
0x18004e086  lea     rcx, [rbp+57h+pidl]
0x18004e08a  call    ?split_extension@@YA?AU?$pair@V?$basic_string_view@GU?$char_traits@G@std@@@std@@V12@@std@@V?$basic_string_view@GU?$char_traits@G@std@@@2@@Z; split_extension(std::basic_string_view<ushort>)
0x18004e08f  movups  xmm6, xmmword ptr [rax]
0x18004e092  mov     [rbp+57h+ppvOut], rsi
0x18004e096  lea     r9, [rbp+57h+ppvOut]; ppvOut
0x18004e09a  lea     r8, _GUID_24d16ee5_10f5_4de3_8766_d23779ba7a6d; riid
0x18004e0a1  lea     rdx, IID_IFolderView; guidService
0x18004e0a8  mov     rcx, [rdi+58h]; punk
0x18004e0ac  call    cs:__imp_IUnknown_QueryService
0x18004e0b2  test    eax, eax
0x18004e0b4  js      short loc_18004E0D6
0x18004e0b6  mov     rcx, [rbp+57h+ppvOut]
0x18004e0ba  mov     rax, [rcx]
0x18004e0bd  mov     rdx, [rdi+38h]
0x18004e0c1  mov     rdx, [rdx+8]
0x18004e0c5  mov     rax, [rax+18h]
0x18004e0c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e0ce  test    eax, eax
0x18004e0d0  js      loc_18004E299
0x18004e0d6  mov     [rbp+57h+ppv], rsi
0x18004e0da  mov     bl, 1
0x18004e0dc  lea     r9, [rbp+57h+ppv]; ppvOut
0x18004e0e0  lea     r8, _GUID_cde725b0_ccc9_4519_917e_325d72fab4ce; riid
0x18004e0e7  lea     rdx, IID_IFolderView; guidService
0x18004e0ee  mov     rcx, [rdi+58h]; punk
0x18004e0f2  call    cs:__imp_IUnknown_QueryService
0x18004e0f8  test    eax, eax
0x18004e0fa  js      loc_18004E188
0x18004e100  mov     [rbp+57h+pidl], rsi
0x18004e104  mov     rcx, [rbp+57h+ppv]
0x18004e108  mov     rax, [rcx]
0x18004e10b  lea     r8, [rbp+57h+pidl]
0x18004e10f  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046
0x18004e116  mov     rax, [rax+28h]
0x18004e11a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e11f  test    eax, eax
0x18004e121  js      short loc_18004E179
0x18004e123  mov     rsi, [rbp+57h+pidl]
0x18004e127  mov     rax, [rsi]
0x18004e12a  mov     r14, [rax+40h]
0x18004e12e  cmp     [rbp+57h+ppvOut], 0
0x18004e133  jz      short loc_18004E13E
0x18004e135  lea     rcx, [rbp+57h+ppvOut]
0x18004e139  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x18004e13e  lea     r9, [rbp+57h+ppvOut]
0x18004e142  lea     r8, _GUID_24d16ee5_10f5_4de3_8766_d23779ba7a6d
0x18004e149  xor     edx, edx
0x18004e14b  mov     rcx, rsi
0x18004e14e  mov     rax, r14
0x18004e151  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e156  xor     esi, esi
0x18004e158  test    eax, eax
0x18004e15a  js      short loc_18004E179
0x18004e15c  mov     rcx, [rbp+57h+ppvOut]
0x18004e160  mov     rax, [rcx]
0x18004e163  mov     rdx, [rdi+38h]
0x18004e167  mov     rdx, [rdx+8]
0x18004e16b  mov     rax, [rax+18h]
0x18004e16f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e174  test    eax, eax
0x18004e176  setns   bl
0x18004e179  cmp     [rbp+57h+pidl], rsi
0x18004e17d  jz      short loc_18004E188
0x18004e17f  lea     rcx, [rbp+57h+pidl]
0x18004e183  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x18004e188  cmp     [rbp+57h+ppv], rsi
0x18004e18c  jz      short loc_18004E197
0x18004e18e  lea     rcx, [rbp+57h+ppv]
0x18004e192  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x18004e197  test    bl, bl
0x18004e199  jz      loc_18004E299
0x18004e19f  test    r15, r15
0x18004e1a2  jz      loc_18004E259
0x18004e1a8  mov     [rbp+57h+pidl], rsi
0x18004e1ac  lea     rdx, [rbp+57h+pidl]
0x18004e1b0  mov     rcx, r15
0x18004e1b3  call    DataObj_GetFolderIDList
0x18004e1b8  test    eax, eax
0x18004e1ba  js      loc_18004E24C
0x18004e1c0  mov     [rbp+57h+ppv], rsi
0x18004e1c4  lea     rax, [rbp+57h+ppv]
0x18004e1c8  mov     [rsp+20h], rax; ppv
0x18004e1cd  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x18004e1d4  xor     r8d, r8d; pbc
0x18004e1d7  mov     rdx, [rbp+57h+pidl]; pidl
0x18004e1db  xor     ecx, ecx; psf
0x18004e1dd  call    cs:__imp_SHBindToObject
0x18004e1e3  test    eax, eax
0x18004e1e5  js      short loc_18004E23D
0x18004e1e7  mov     rsi, [rbp+57h+ppv]
0x18004e1eb  mov     rax, [rsi]
0x18004e1ee  mov     r14, [rax+40h]
0x18004e1f2  cmp     [rbp+57h+ppvOut], 0
0x18004e1f7  jz      short loc_18004E202
0x18004e1f9  lea     rcx, [rbp+57h+ppvOut]
0x18004e1fd  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x18004e202  lea     r9, [rbp+57h+ppvOut]
0x18004e206  lea     r8, _GUID_24d16ee5_10f5_4de3_8766_d23779ba7a6d
0x18004e20d  xor     edx, edx
0x18004e20f  mov     rcx, rsi
0x18004e212  mov     rax, r14
0x18004e215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e21a  xor     esi, esi
0x18004e21c  test    eax, eax
0x18004e21e  js      short loc_18004E23D
0x18004e220  mov     rcx, [rbp+57h+ppvOut]
0x18004e224  mov     rax, [rcx]
0x18004e227  mov     rdx, [rdi+38h]
0x18004e22b  mov     rdx, [rdx+8]
0x18004e22f  mov     rax, [rax+18h]
0x18004e233  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e238  test    eax, eax
0x18004e23a  setns   bl
0x18004e23d  cmp     [rbp+57h+ppv], rsi
0x18004e241  jz      short loc_18004E24C
0x18004e243  lea     rcx, [rbp+57h+ppv]
0x18004e247  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x18004e24c  lea     rcx, [rbp+57h+pidl]
0x18004e250  call    ??1?$unique_storage@U?$resource_policy@PEAU_ITEMIDLIST_RELATIVE@@P6AXPEAU1@@Z$1?ILFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>(void)
0x18004e255  test    bl, bl
0x18004e257  jz      short loc_18004E299
0x18004e259  movdqa  xmmword ptr [rbp+57h+pidl], xmm6
0x18004e25e  mov     rax, [rbp+57h+var_C0]
0x18004e262  mov     [rbp+57h+ppv], rax
0x18004e266  mov     [rbp+57h+ppv+8], r12
0x18004e26a  mov     r8, [rdi+38h]
0x18004e26e  mov     r9, r13
0x18004e271  mov     r8, [r8+8]
0x18004e275  lea     rdx, [rbp+57h+pidl]
0x18004e279  lea     rcx, [rbp+57h+ppv]
0x18004e27d  call    ?TryCreateTargetFile@@YAJV?$basic_string_view@GU?$char_traits@G@std@@@std@@0PEBGPEAPEAX@Z; TryCreateTargetFile(std::basic_string_view<ushort>,std::basic_string_view<ushort>,ushort const *,void * *)
0x18004e282  test    eax, eax
0x18004e284  js      short loc_18004E299
0x18004e286  cmp     [rbp+57h+ppvOut], rsi
0x18004e28a  jz      short loc_18004E295
0x18004e28c  lea     rcx, [rbp+57h+ppvOut]
0x18004e290  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x18004e295  xor     eax, eax
0x18004e297  jmp     short loc_18004E2C0
0x18004e299  movdqa  xmmword ptr [rbp+57h+ppv], xmm6
0x18004e29e  mov     r8, r13
0x18004e2a1  lea     rdx, [rbp+57h+ppv]
0x18004e2a5  mov     rcx, rdi
0x18004e2a8  call    ?TryCreateTargetFileInDesktop@SendToArchive@@AEAAJV?$basic_string_view@GU?$char_traits@G@std@@@std@@PEAPEAX@Z; SendToArchive::TryCreateTargetFileInDesktop(std::basic_string_view<ushort>,void * *)
0x18004e2ad  mov     ebx, eax
0x18004e2af  cmp     [rbp+57h+ppvOut], rsi
0x18004e2b3  jz      short loc_18004E2BE
0x18004e2b5  lea     rcx, [rbp+57h+ppvOut]
0x18004e2b9  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x18004e2be  mov     eax, ebx
0x18004e2c0  mov     rcx, [rbp+57h+var_60]
0x18004e2c4  xor     rcx, rsp; StackCookie
0x18004e2c7  call    __security_check_cookie
0x18004e2cc  movaps  xmm6, [rsp+0F0h+var_58+8]
0x18004e2d4  add     rsp, 0B8h
0x18004e2db  pop     r15
0x18004e2dd  pop     r14
0x18004e2df  pop     r13
0x18004e2e1  pop     r12
0x18004e2e3  pop     rdi
0x18004e2e4  pop     rsi
0x18004e2e5  pop     rbx
0x18004e2e6  pop     rbp
0x18004e2e7  retn
```
