# tip2::details::shared_data<0,0,0>::start(void)

- ea: `0x180061c10`
- end: `0x180061dbc`
- name: `?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ`
- size: `428`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task`

## callers

- `0x180061dc4`

## callees

- `0x18003fdec`
- `0x18003fe7c`
- `0x180043a30`
- `0x18004c7dc`
- `0x18004d1fc`
- `0x18005e950`
- `0x1800619f4`
- `0x180061c10`
- `0x180062160`
- `0x180062328`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180061cf8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180061cf8`

## string_xrefs

- `0x180061cf1`: `TestCreate`

## pseudocode

```c
_OWORD *__fastcall tip2::details::shared_data<0,0,0>::start(__int64 a1, _OWORD *a2)
{
  __int64 v4; // r8
  _OWORD *v5; // rsi
  __int64 v6; // rdi
  unsigned int v7; // r14d
  char v8; // r12
  unsigned int v9; // r13d
  FARPROC ProcAddress; // rax
  HMODULE KernelBaseModuleHandle; // rax
  __int64 v12; // r14
  __int64 v13; // rdi
  _BYTE v15[8]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v16[8]; // [rsp+48h] [rbp-B8h] BYREF
  void *v17; // [rsp+50h] [rbp-B0h] BYREF
  char v18; // [rsp+58h] [rbp-A8h]
  int v19; // [rsp+59h] [rbp-A7h] BYREF
  char v20; // [rsp+5Dh] [rbp-A3h]
  char v21; // [rsp+5Eh] [rbp-A2h] BYREF
  char v22; // [rsp+859h] [rbp+759h] BYREF
  int *v23; // [rsp+860h] [rbp+760h]
  char *v24; // [rsp+868h] [rbp+768h]
  char *v25; // [rsp+870h] [rbp+770h]

  wil::EnterCriticalSection(v16, a1 + 192);
  v17 = 0;
  v18 = 0;
  v23 = &v19;
  v25 = &v22;
  v19 = -2143256512;
  v20 = 0;
  v24 = &v21;
  v5 = (_OWORD *)(a1 + 144);
  if ( (*(_DWORD *)(a1 + 64) & 0x800) != 0 && (*(_DWORD *)(a1 + 20) & 0x8000) == 0 )
    v6 = tip2::details::shared_data<0,0,0>::serialize_data(a1, &v17, 1);
  else
    v6 = 0;
  v7 = *(_DWORD *)(a1 + 20);
  v8 = *(_BYTE *)(a1 + 32);
  v9 = *(_DWORD *)(a1 + 16);
  ProcAddress = (FARPROC)`TestCreate'::`2'::s_pfnTestCreate;
  if ( `TestCreate'::`2'::s_pfnTestCreate
    || (KernelBaseModuleHandle = (HMODULE)tip_details_GetKernelBaseModuleHandle(),
        ProcAddress = GetProcAddress(KernelBaseModuleHandle, "TestCreate"),
        (`TestCreate'::`2'::s_pfnTestCreate = (__int64)ProcAddress) != 0) )
  {
    LOBYTE(v4) = v8;
    v12 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD, __int64, __int64))ProcAddress)(
            v9,
            0,
            v4,
            v7,
            v6,
            a1 + 144);
  }
  else
  {
    *v5 = 0;
    v12 = 0;
  }
  v13 = *(_QWORD *)(a1 + 240);
  if ( v13 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v15);
    TestClose(v13);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v15);
  }
  *(_QWORD *)(a1 + 240) = v12;
  *(_DWORD *)(a1 + 184) = 1;
  *a2 = *v5;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v17);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v16);
  return a2;
}

```

## disassembly

```asm
0x180061c10  mov     [rsp-8+arg_10], rbx
0x180061c15  push    rbp
0x180061c16  push    rsi
0x180061c17  push    rdi
0x180061c18  push    r12
0x180061c1a  push    r13
0x180061c1c  push    r14
0x180061c1e  push    r15
0x180061c20  lea     rbp, [rsp-790h]
0x180061c28  sub     rsp, 890h
0x180061c2f  mov     rax, cs:__security_cookie
0x180061c36  xor     rax, rsp
0x180061c39  mov     [rbp+7C0h+var_40], rax
0x180061c40  mov     r15, rdx
0x180061c43  mov     rbx, rcx
0x180061c46  lea     rdx, [rcx+0C0h]
0x180061c4d  lea     rcx, [rsp+8C0h+var_878]
0x180061c52  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180061c57  mov     [rsp+8C0h+var_870], 0
0x180061c60  mov     [rsp+8C0h+var_868], 0
0x180061c65  lea     rax, [rsp+8C0h+var_867]
0x180061c6a  mov     [rbp+7C0h+var_60], rax
0x180061c71  lea     rax, [rbp+7C0h+var_67]
0x180061c78  mov     [rbp+7C0h+var_50], rax
0x180061c7f  mov     [rsp+8C0h+var_867], 80408040h
0x180061c87  mov     [rsp+8C0h+var_863], 0
0x180061c8c  lea     rax, [rsp+8C0h+var_862]
0x180061c91  mov     [rbp+7C0h+var_58], rax
0x180061c98  lea     rsi, [rbx+90h]
0x180061c9f  test    dword ptr [rbx+40h], 800h
0x180061ca6  setnz   cl
0x180061ca9  test    dword ptr [rbx+14h], 8000h
0x180061cb0  setz    al
0x180061cb3  test    al, cl
0x180061cb5  jz      short loc_180061CCF
0x180061cb7  mov     r8d, 1
0x180061cbd  lea     rdx, [rsp+8C0h+var_870]
0x180061cc2  mov     rcx, rbx
0x180061cc5  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x180061cca  mov     rdi, rax
0x180061ccd  jmp     short loc_180061CD1
0x180061ccf  xor     edi, edi
0x180061cd1  mov     r14d, [rbx+14h]
0x180061cd5  mov     r12b, [rbx+20h]
0x180061cd9  mov     r13d, [rbx+10h]
0x180061cdd  mov     rax, cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x180061ce4  test    rax, rax
0x180061ce7  jnz     short loc_180061D1C
0x180061ce9  call    tip_details_GetKernelBaseModuleHandle
0x180061cee  mov     rcx, rax; hModule
0x180061cf1  lea     rdx, aTestcreate; "TestCreate"
0x180061cf8  call    cs:__imp_GetProcAddress
0x180061cff  nop     dword ptr [rax+rax+00h]
0x180061d04  mov     cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA, rax; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x180061d0b  test    rax, rax
0x180061d0e  jnz     short loc_180061D1C
0x180061d10  xorps   xmm0, xmm0
0x180061d13  movdqu  xmmword ptr [rsi], xmm0
0x180061d17  xor     r14d, r14d
0x180061d1a  jmp     short loc_180061D39
0x180061d1c  mov     [rsp+8C0h+var_898], rsi
0x180061d21  mov     [rsp+8C0h+var_8A0], rdi
0x180061d26  mov     r9d, r14d
0x180061d29  mov     r8b, r12b
0x180061d2c  xor     edx, edx
0x180061d2e  mov     ecx, r13d
0x180061d31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061d36  mov     r14, rax
0x180061d39  mov     rdi, [rbx+0F0h]
0x180061d40  test    rdi, rdi
0x180061d43  jz      short loc_180061D61
0x180061d45  lea     rcx, [rsp+8C0h+var_880]; this
0x180061d4a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180061d4f  mov     rcx, rdi
0x180061d52  call    TestClose
0x180061d57  lea     rcx, [rsp+8C0h+var_880]; this
0x180061d5c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180061d61  mov     [rbx+0F0h], r14
0x180061d68  mov     dword ptr [rbx+0B8h], 1
0x180061d72  movups  xmm0, xmmword ptr [rsi]
0x180061d75  movdqu  xmmword ptr [r15], xmm0
0x180061d7a  lea     rcx, [rsp+8C0h+var_870]
0x180061d7f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180061d84  lea     rcx, [rsp+8C0h+var_878]
0x180061d89  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180061d8e  mov     rax, r15
0x180061d91  mov     rcx, [rbp+7C0h+var_40]
0x180061d98  xor     rcx, rsp; StackCookie
0x180061d9b  call    __security_check_cookie
0x180061da0  mov     rbx, [rsp+8C0h+arg_10]
0x180061da8  add     rsp, 890h
0x180061daf  pop     r15
0x180061db1  pop     r14
0x180061db3  pop     r13
0x180061db5  pop     r12
0x180061db7  pop     rdi
0x180061db8  pop     rsi
0x180061db9  pop     rbp
0x180061dba  retn
```
