# ArchiveDragDropHandler::Initialize(_ITEMIDLIST_ABSOLUTE const *,IDataObject *,HKEY__ *)

- ea: `0x1800310b0`
- end: `0x18003124f`
- name: `?Initialize@ArchiveDragDropHandler@@UEAAJPEBU_ITEMIDLIST_ABSOLUTE@@PEAUIDataObject@@PEAUHKEY__@@@Z`
- size: `415`
- prototype: `int(ArchiveDragDropHandler *__hidden this, const struct _ITEMIDLIST_ABSOLUTE *, struct IDataObject *, HKEY)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800208e0`
- `0x180024a24`
- `0x180030a3c`
- `0x1800310b0`
- `0x180031e94`
- `0x180032480`
- `0x180034760`
- `0x180036f50`
- `0x18004fef0`
- `0x180071010`

## import_xrefs

- `SHELL32!SHGetNameFromIDList` at `0x1800311f7`
- `SHELL32!SHGetNameFromIDList` at `0x1800311f7`
- `SHELL32!SHGetItemFromDataObject` at `0x1800310f9`
- `SHELL32!SHGetItemFromDataObject` at `0x1800310f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800311c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031220`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800311c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031220`

## pseudocode

```c
__int64 __fastcall ArchiveDragDropHandler::Initialize(
        PWSTR *this,
        const ITEMIDLIST *a2,
        struct IDataObject *a3,
        HKEY a4)
{
  void *v6; // rdi
  __int64 (__fastcall *v7)(void *, __int64, LPVOID *); // rbx
  int v8; // eax
  void *v9; // rcx
  HRESULT v10; // ebx
  __int64 v11; // rdx
  __int128 v13; // [rsp+20h] [rbp-50h] BYREF
  _BYTE v14[32]; // [rsp+30h] [rbp-40h] BYREF
  void *ppv; // [rsp+50h] [rbp-20h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-18h] BYREF
  int v17; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  if ( !a3 )
    return 0;
  ppv = 0;
  if ( SHGetItemFromDataObject(a3, DOGIF_NO_URL, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, &ppv) < 0
    || (v17 = 0, (*(unsigned int (__fastcall **)(void *, __int64, int *))(*(_QWORD *)ppv + 48LL))(ppv, 0x400000, &v17)) )
  {
LABEL_19:
    if ( ppv )
      winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&ppv);
    return 0;
  }
  pv = 0;
  v6 = ppv;
  v7 = *(__int64 (__fastcall **)(void *, __int64, LPVOID *))(*(_QWORD *)ppv + 40LL);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pv,
    0);
  v8 = v7(v6, 2147844096LL, &pv);
  v9 = pv;
  if ( v8 < 0 )
  {
LABEL_17:
    if ( v9 )
      CoTaskMemFree(v9);
    goto LABEL_19;
  }
  *(_QWORD *)&v13 = pv;
  *((_QWORD *)&v13 + 1) = std::_WChar_traits<unsigned short>::length(pv);
  v13 = *(_OWORD *)(split_extension(v14, &v13) + 16);
  if ( !(unsigned __int8)matches_name<std::basic_string_view<unsigned short> const (&)[16]>(&v13) )
  {
LABEL_16:
    v9 = pv;
    goto LABEL_17;
  }
  if ( a2 )
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      this + 5,
      0);
    v10 = SHGetNameFromIDList(a2, SIGDN_FILESYSPATH, this + 5);
    if ( v10 < 0 )
    {
      v11 = 56;
      goto LABEL_8;
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      this + 4,
      &pv);
    goto LABEL_16;
  }
  v10 = -2147024809;
  v11 = 55;
LABEL_8:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v11,
    (unsigned int)"shell\\ext\\zip\\archive\\archivedragdrophandler.cpp",
    (const char *)(unsigned int)v10);
  if ( pv )
    CoTaskMemFree(pv);
  if ( ppv )
    winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&ppv);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800310b0  push    rbp
0x1800310b2  push    rbx
0x1800310b3  push    rsi
0x1800310b4  push    rdi
0x1800310b5  push    r14
0x1800310b7  mov     rbp, rsp
0x1800310ba  sub     rsp, 70h
0x1800310be  mov     rax, cs:__security_cookie
0x1800310c5  xor     rax, rsp
0x1800310c8  mov     [rbp+var_8], rax
0x1800310cc  mov     rax, r8
0x1800310cf  mov     rsi, rdx
0x1800310d2  mov     r14, rcx
0x1800310d5  test    r8, r8
0x1800310d8  jz      loc_180031236
0x1800310de  mov     [rbp+ppv], 0
0x1800310e6  lea     r9, [rbp+ppv]; ppv
0x1800310ea  lea     r8, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x1800310f1  mov     edx, 4; dwFlags
0x1800310f6  mov     rcx, rax; pdtobj
0x1800310f9  call    cs:__imp_SHGetItemFromDataObject
0x1800310ff  test    eax, eax
0x180031101  js      loc_180031226
0x180031107  mov     [rbp+var_10], 0
0x18003110e  mov     rcx, [rbp+ppv]
0x180031112  mov     rax, [rcx]
0x180031115  lea     r8, [rbp+var_10]
0x180031119  mov     edx, 400000h
0x18003111e  mov     rax, [rax+30h]
0x180031122  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031127  test    eax, eax
0x180031129  jnz     loc_180031226
0x18003112f  mov     [rbp+pv], 0
0x180031137  mov     rdi, [rbp+ppv]
0x18003113b  mov     rax, [rdi]
0x18003113e  mov     rbx, [rax+28h]
0x180031142  xor     edx, edx
0x180031144  lea     rcx, [rbp+pv]
0x180031148  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18003114d  lea     r8, [rbp+pv]
0x180031151  mov     edx, 80058000h
0x180031156  mov     rcx, rdi
0x180031159  mov     rax, rbx
0x18003115c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031161  mov     rcx, [rbp+pv]
0x180031165  test    eax, eax
0x180031167  js      loc_18003121B
0x18003116d  mov     qword ptr [rbp+var_50], rcx
0x180031171  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180031176  mov     qword ptr [rbp+var_50+8], rax
0x18003117a  lea     rdx, [rbp+var_50]
0x18003117e  lea     rcx, [rbp+var_40]
0x180031182  call    ?split_extension@@YA?AU?$pair@V?$basic_string_view@GU?$char_traits@G@std@@@std@@V12@@std@@V?$basic_string_view@GU?$char_traits@G@std@@@2@@Z; split_extension(std::basic_string_view<ushort>)
0x180031187  movups  xmm0, xmmword ptr [rax+10h]
0x18003118b  movdqu  [rbp+var_50], xmm0
0x180031190  lea     rcx, [rbp+var_50]
0x180031194  call    ??$matches_name@AEAY0BA@$$CBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@@YA_NV?$basic_string_view@GU?$char_traits@G@std@@@std@@AEAY0BA@$$CBV01@@Z; matches_name<std::basic_string_view<ushort> const (&)[16]>(std::basic_string_view<ushort>,std::basic_string_view<ushort> const (&)[16])
0x180031199  test    al, al
0x18003119b  jz      short loc_180031217
0x18003119d  test    rsi, rsi
0x1800311a0  jnz     short loc_1800311E0
0x1800311a2  mov     ebx, 80070057h
0x1800311a7  lea     edx, [rsi+37h]
0x1800311aa  mov     r9d, ebx
0x1800311ad  lea     r8, aShellExtZipArc_5; "shell\\ext\\zip\\archive\\archivedragdr"...
0x1800311b4  mov     rcx, [rbp+28h]
0x1800311b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800311bd  mov     rcx, [rbp+pv]; pv
0x1800311c1  test    rcx, rcx
0x1800311c4  jz      short loc_1800311CC
0x1800311c6  call    cs:__imp_CoTaskMemFree
0x1800311cc  cmp     [rbp+ppv], 0
0x1800311d1  jz      short loc_1800311DC
0x1800311d3  lea     rcx, [rbp+ppv]
0x1800311d7  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x1800311dc  mov     eax, ebx
0x1800311de  jmp     short loc_180031238
0x1800311e0  xor     edx, edx
0x1800311e2  lea     rcx, [r14+28h]
0x1800311e6  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800311eb  lea     r8, [r14+28h]; ppszName
0x1800311ef  mov     edx, 80058000h; sigdnName
0x1800311f4  mov     rcx, rsi; pidl
0x1800311f7  call    cs:__imp_SHGetNameFromIDList
0x1800311fd  mov     ebx, eax
0x1800311ff  test    eax, eax
0x180031201  jns     short loc_18003120A
0x180031203  mov     edx, 38h ; '8'
0x180031208  jmp     short loc_1800311AA
0x18003120a  lea     rcx, [r14+20h]
0x18003120e  lea     rdx, [rbp+pv]
0x180031212  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180031217  mov     rcx, [rbp+pv]; pv
0x18003121b  test    rcx, rcx
0x18003121e  jz      short loc_180031226
0x180031220  call    cs:__imp_CoTaskMemFree
0x180031226  cmp     [rbp+ppv], 0
0x18003122b  jz      short loc_180031236
0x18003122d  lea     rcx, [rbp+ppv]
0x180031231  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x180031236  xor     eax, eax
0x180031238  mov     rcx, [rbp+var_8]
0x18003123c  xor     rcx, rsp; StackCookie
0x18003123f  call    __security_check_cookie
0x180031244  add     rsp, 70h
0x180031248  pop     r14
0x18003124a  pop     rdi
0x18003124b  pop     rsi
0x18003124c  pop     rbx
0x18003124d  pop     rbp
0x18003124e  retn
```
