# tip2::details::shared_data<1,0,0>::start(void)

- ea: `0x18001cbfc`
- end: `0x18001cd92`
- name: `?start@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ`
- size: `406`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task`

## callers

- `0x18001d900`

## callees

- `0x180005540`
- `0x180005560`
- `0x1800067e0`
- `0x18000697c`
- `0x180008320`
- `0x180014d58`
- `0x18001c9e0`
- `0x18001cbfc`
- `0x18001da38`
- `0x18001db40`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001ccd5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001ccd5`

## string_xrefs

- `0x18001ccce`: `TestCreate`

## pseudocode

```c
_OWORD *__fastcall tip2::details::shared_data<1,0,0>::start(__int64 a1, _OWORD *a2)
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
  if ( (*(_DWORD *)(a1 + 64) & 0x800) != 0 )
    v6 = tip2::details::shared_data<1,0,0>::serialize_data(a1, &v17, 1);
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
0x18001cbfc  mov     [rsp-8+arg_10], rbx
0x18001cc01  push    rbp
0x18001cc02  push    rsi
0x18001cc03  push    rdi
0x18001cc04  push    r12
0x18001cc06  push    r13
0x18001cc08  push    r14
0x18001cc0a  push    r15
0x18001cc0c  lea     rbp, [rsp-790h]
0x18001cc14  sub     rsp, 890h
0x18001cc1b  mov     rax, cs:__security_cookie
0x18001cc22  xor     rax, rsp
0x18001cc25  mov     [rbp+7C0h+var_40], rax
0x18001cc2c  mov     r15, rdx
0x18001cc2f  mov     rbx, rcx
0x18001cc32  lea     rdx, [rcx+0C0h]
0x18001cc39  lea     rcx, [rsp+8C0h+var_878]
0x18001cc3e  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18001cc43  mov     [rsp+8C0h+var_870], 0
0x18001cc4c  mov     [rsp+8C0h+var_868], 0
0x18001cc51  lea     rax, [rsp+8C0h+var_867]
0x18001cc56  mov     [rbp+7C0h+var_60], rax
0x18001cc5d  lea     rax, [rbp+7C0h+var_67]
0x18001cc64  mov     [rbp+7C0h+var_50], rax
0x18001cc6b  mov     [rsp+8C0h+var_867], 80408040h
0x18001cc73  mov     [rsp+8C0h+var_863], 0
0x18001cc78  lea     rax, [rsp+8C0h+var_862]
0x18001cc7d  mov     [rbp+7C0h+var_58], rax
0x18001cc84  lea     rsi, [rbx+90h]
0x18001cc8b  test    dword ptr [rbx+40h], 800h
0x18001cc92  jz      short loc_18001CCAC
0x18001cc94  mov     r8d, 1
0x18001cc9a  lea     rdx, [rsp+8C0h+var_870]
0x18001cc9f  mov     rcx, rbx
0x18001cca2  call    ?serialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<1,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x18001cca7  mov     rdi, rax
0x18001ccaa  jmp     short loc_18001CCAE
0x18001ccac  xor     edi, edi
0x18001ccae  mov     r14d, [rbx+14h]
0x18001ccb2  mov     r12b, [rbx+20h]
0x18001ccb6  mov     r13d, [rbx+10h]
0x18001ccba  mov     rax, cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x18001ccc1  test    rax, rax
0x18001ccc4  jnz     short loc_18001CCF3
0x18001ccc6  call    tip_details_GetKernelBaseModuleHandle
0x18001cccb  mov     rcx, rax; hModule
0x18001ccce  lea     rdx, aTestcreate; "TestCreate"
0x18001ccd5  call    cs:__imp_GetProcAddress
0x18001ccdb  mov     cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA, rax; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x18001cce2  test    rax, rax
0x18001cce5  jnz     short loc_18001CCF3
0x18001cce7  xorps   xmm0, xmm0
0x18001ccea  movdqu  xmmword ptr [rsi], xmm0
0x18001ccee  xor     r14d, r14d
0x18001ccf1  jmp     short loc_18001CD10
0x18001ccf3  mov     [rsp+8C0h+var_898], rsi
0x18001ccf8  mov     [rsp+8C0h+var_8A0], rdi
0x18001ccfd  mov     r9d, r14d
0x18001cd00  mov     r8b, r12b
0x18001cd03  xor     edx, edx
0x18001cd05  mov     ecx, r13d
0x18001cd08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd0d  mov     r14, rax
0x18001cd10  mov     rdi, [rbx+0F0h]
0x18001cd17  test    rdi, rdi
0x18001cd1a  jz      short loc_18001CD38
0x18001cd1c  lea     rcx, [rsp+8C0h+var_880]; this
0x18001cd21  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001cd26  mov     rcx, rdi
0x18001cd29  call    TestClose
0x18001cd2e  lea     rcx, [rsp+8C0h+var_880]; this
0x18001cd33  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001cd38  mov     [rbx+0F0h], r14
0x18001cd3f  mov     dword ptr [rbx+0B8h], 1
0x18001cd49  movups  xmm0, xmmword ptr [rsi]
0x18001cd4c  movdqu  xmmword ptr [r15], xmm0
0x18001cd51  lea     rcx, [rsp+8C0h+var_870]
0x18001cd56  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001cd5b  lea     rcx, [rsp+8C0h+var_878]
0x18001cd60  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18001cd65  mov     rax, r15
0x18001cd68  mov     rcx, [rbp+7C0h+var_40]
0x18001cd6f  xor     rcx, rsp; StackCookie
0x18001cd72  call    __security_check_cookie
0x18001cd77  mov     rbx, [rsp+8C0h+arg_10]
0x18001cd7f  add     rsp, 890h
0x18001cd86  pop     r15
0x18001cd88  pop     r14
0x18001cd8a  pop     r13
0x18001cd8c  pop     r12
0x18001cd8e  pop     rdi
0x18001cd8f  pop     rsi
0x18001cd90  pop     rbp
0x18001cd91  retn
```
