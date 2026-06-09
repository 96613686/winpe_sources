# tip2::details::shared_data<0,0,0>::start(void)

- ea: `0x14005f760`
- end: `0x14005f905`
- name: `?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ`
- size: `421`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task`

## callers

- `0x14005b34c`

## callees

- `0x14000a2d4`
- `0x14000a7b0`
- `0x14000a834`
- `0x14000f7e0`
- `0x140045fe8`
- `0x140046a00`
- `0x14004b8d8`
- `0x140052fe0`
- `0x14005f544`
- `0x14005f760`
- `0x140067010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14005f848`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14005f848`

## string_xrefs

- `0x14005f841`: `TestCreate`

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
0x14005f760  mov     [rsp-8+arg_10], rbx
0x14005f765  push    rbp
0x14005f766  push    rsi
0x14005f767  push    rdi
0x14005f768  push    r12
0x14005f76a  push    r13
0x14005f76c  push    r14
0x14005f76e  push    r15
0x14005f770  lea     rbp, [rsp-790h]
0x14005f778  sub     rsp, 890h
0x14005f77f  mov     rax, cs:__security_cookie
0x14005f786  xor     rax, rsp
0x14005f789  mov     [rbp+7C0h+var_40], rax
0x14005f790  mov     r15, rdx
0x14005f793  mov     rbx, rcx
0x14005f796  lea     rdx, [rcx+0C0h]
0x14005f79d  lea     rcx, [rsp+8C0h+var_878]
0x14005f7a2  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x14005f7a7  mov     [rsp+8C0h+var_870], 0
0x14005f7b0  mov     [rsp+8C0h+var_868], 0
0x14005f7b5  lea     rax, [rsp+8C0h+var_867]
0x14005f7ba  mov     [rbp+7C0h+var_60], rax
0x14005f7c1  lea     rax, [rbp+7C0h+var_67]
0x14005f7c8  mov     [rbp+7C0h+var_50], rax
0x14005f7cf  mov     [rsp+8C0h+var_867], 80408040h
0x14005f7d7  mov     [rsp+8C0h+var_863], 0
0x14005f7dc  lea     rax, [rsp+8C0h+var_862]
0x14005f7e1  mov     [rbp+7C0h+var_58], rax
0x14005f7e8  lea     rsi, [rbx+90h]
0x14005f7ef  test    dword ptr [rbx+40h], 800h
0x14005f7f6  setnz   cl
0x14005f7f9  test    dword ptr [rbx+14h], 8000h
0x14005f800  setz    al
0x14005f803  test    al, cl
0x14005f805  jz      short loc_14005F81F
0x14005f807  mov     r8d, 1
0x14005f80d  lea     rdx, [rsp+8C0h+var_870]
0x14005f812  mov     rcx, rbx
0x14005f815  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x14005f81a  mov     rdi, rax
0x14005f81d  jmp     short loc_14005F821
0x14005f81f  xor     edi, edi
0x14005f821  mov     r14d, [rbx+14h]
0x14005f825  mov     r12b, [rbx+20h]
0x14005f829  mov     r13d, [rbx+10h]
0x14005f82d  mov     rax, cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x14005f834  test    rax, rax
0x14005f837  jnz     short loc_14005F866
0x14005f839  call    tip_details_GetKernelBaseModuleHandle
0x14005f83e  mov     rcx, rax; hModule
0x14005f841  lea     rdx, aTestcreate; "TestCreate"
0x14005f848  call    cs:__imp_GetProcAddress
0x14005f84e  mov     cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA, rax; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x14005f855  test    rax, rax
0x14005f858  jnz     short loc_14005F866
0x14005f85a  xorps   xmm0, xmm0
0x14005f85d  movdqu  xmmword ptr [rsi], xmm0
0x14005f861  xor     r14d, r14d
0x14005f864  jmp     short loc_14005F883
0x14005f866  mov     [rsp+8C0h+var_898], rsi
0x14005f86b  mov     [rsp+8C0h+var_8A0], rdi
0x14005f870  mov     r9d, r14d
0x14005f873  mov     r8b, r12b
0x14005f876  xor     edx, edx
0x14005f878  mov     ecx, r13d
0x14005f87b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005f880  mov     r14, rax
0x14005f883  mov     rdi, [rbx+0F0h]
0x14005f88a  test    rdi, rdi
0x14005f88d  jz      short loc_14005F8AB
0x14005f88f  lea     rcx, [rsp+8C0h+var_880]; this
0x14005f894  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14005f899  mov     rcx, rdi
0x14005f89c  call    TestClose
0x14005f8a1  lea     rcx, [rsp+8C0h+var_880]; this
0x14005f8a6  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14005f8ab  mov     [rbx+0F0h], r14
0x14005f8b2  mov     dword ptr [rbx+0B8h], 1
0x14005f8bc  movups  xmm0, xmmword ptr [rsi]
0x14005f8bf  movdqu  xmmword ptr [r15], xmm0
0x14005f8c4  lea     rcx, [rsp+8C0h+var_870]
0x14005f8c9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14005f8ce  lea     rcx, [rsp+8C0h+var_878]
0x14005f8d3  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x14005f8d8  mov     rax, r15
0x14005f8db  mov     rcx, [rbp+7C0h+var_40]
0x14005f8e2  xor     rcx, rsp; StackCookie
0x14005f8e5  call    __security_check_cookie
0x14005f8ea  mov     rbx, [rsp+8C0h+arg_10]
0x14005f8f2  add     rsp, 890h
0x14005f8f9  pop     r15
0x14005f8fb  pop     r14
0x14005f8fd  pop     r13
0x14005f8ff  pop     r12
0x14005f901  pop     rdi
0x14005f902  pop     rsi
0x14005f903  pop     rbp
0x14005f904  retn
```
