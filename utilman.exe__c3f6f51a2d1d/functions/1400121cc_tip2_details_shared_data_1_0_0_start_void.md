# tip2::details::shared_data<1,0,0>::start(void)

- ea: `0x1400121cc`
- end: `0x140012353`
- name: `?start@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ`
- size: `391`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x14000e72c`

## callees

- `0x140002480`
- `0x140004818`
- `0x1400054fc`
- `0x14000cfc0`
- `0x1400118c4`
- `0x140011ff8`
- `0x1400121cc`
- `0x140012f1c`
- `0x140029010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1400122b2`
- `KERNEL32!GetProcAddress` at `0x1400122b2`

## string_xrefs

- `0x1400122ab`: `TestCreate`

## pseudocode

```c
_OWORD *__fastcall tip2::details::shared_data<1,0,0>::start(__int64 a1, _OWORD *a2)
{
  __int64 v4; // r8
  _OWORD *v5; // rdi
  __int64 v6; // r15
  unsigned int v7; // r13d
  FARPROC ProcAddress; // rax
  HMODULE KernelBaseModuleHandle; // rax
  char v11; // [rsp+40h] [rbp-C0h]
  unsigned int v12; // [rsp+44h] [rbp-BCh]
  _BYTE v13[8]; // [rsp+48h] [rbp-B8h] BYREF
  void *v14; // [rsp+50h] [rbp-B0h] BYREF
  char v15; // [rsp+58h] [rbp-A8h]
  int v16; // [rsp+59h] [rbp-A7h] BYREF
  char v17; // [rsp+5Dh] [rbp-A3h]
  char v18; // [rsp+5Eh] [rbp-A2h] BYREF
  char v19; // [rsp+859h] [rbp+759h] BYREF
  int *v20; // [rsp+860h] [rbp+760h]
  char *v21; // [rsp+868h] [rbp+768h]
  char *v22; // [rsp+870h] [rbp+770h]

  wil::EnterCriticalSection(v13, a1 + 192);
  v14 = 0;
  v15 = 0;
  v20 = &v16;
  v22 = &v19;
  v16 = -2143256512;
  v17 = 0;
  v21 = &v18;
  v5 = (_OWORD *)(a1 + 144);
  if ( (*(_DWORD *)(a1 + 64) & 0x800) != 0 )
    v6 = tip2::details::shared_data<1,0,0>::serialize_data(a1, &v14, 1);
  else
    v6 = 0;
  v7 = *(_DWORD *)(a1 + 20);
  v11 = *(_BYTE *)(a1 + 32);
  v12 = *(_DWORD *)(a1 + 16);
  ProcAddress = (FARPROC)`TestCreate'::`2'::s_pfnTestCreate;
  if ( `TestCreate'::`2'::s_pfnTestCreate
    || (KernelBaseModuleHandle = (HMODULE)tip_details_GetKernelBaseModuleHandle(),
        ProcAddress = GetProcAddress(KernelBaseModuleHandle, "TestCreate"),
        (`TestCreate'::`2'::s_pfnTestCreate = (__int64)ProcAddress) != 0) )
  {
    LOBYTE(v4) = v11;
    ProcAddress = (FARPROC)((__int64 (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD, __int64, _OWORD *))ProcAddress)(
                             v12,
                             0,
                             v4,
                             v7,
                             v6,
                             v5);
  }
  else
  {
    *v5 = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&void TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::reset(
    a1 + 240,
    ProcAddress);
  *(_DWORD *)(a1 + 184) = 1;
  *a2 = *v5;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v14);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v13);
  return a2;
}

```

## disassembly

```asm
0x1400121cc  mov     [rsp-8+arg_10], rbx
0x1400121d1  push    rbp
0x1400121d2  push    rsi
0x1400121d3  push    rdi
0x1400121d4  push    r12
0x1400121d6  push    r13
0x1400121d8  push    r14
0x1400121da  push    r15
0x1400121dc  lea     rbp, [rsp-790h]
0x1400121e4  sub     rsp, 890h
0x1400121eb  mov     rax, cs:__security_cookie
0x1400121f2  xor     rax, rsp
0x1400121f5  mov     [rbp+7C0h+var_40], rax
0x1400121fc  mov     r14, rdx
0x1400121ff  mov     rbx, rcx
0x140012202  lea     rdx, [rcx+0C0h]
0x140012209  lea     rcx, [rsp+8C0h+var_878]
0x14001220e  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x140012213  mov     [rsp+8C0h+var_870], 0
0x14001221c  mov     [rsp+8C0h+var_868], 0
0x140012221  lea     rax, [rsp+8C0h+var_867]
0x140012226  mov     [rbp+7C0h+var_60], rax
0x14001222d  lea     rax, [rbp+7C0h+var_67]
0x140012234  mov     [rbp+7C0h+var_50], rax
0x14001223b  mov     [rsp+8C0h+var_867], 80408040h
0x140012243  mov     [rsp+8C0h+var_863], 0
0x140012248  lea     rax, [rsp+8C0h+var_862]
0x14001224d  mov     [rbp+7C0h+var_58], rax
0x140012254  lea     rdi, [rbx+90h]
0x14001225b  test    dword ptr [rbx+40h], 800h
0x140012262  jz      short loc_14001227C
0x140012264  mov     r8d, 1
0x14001226a  lea     rdx, [rsp+8C0h+var_870]
0x14001226f  mov     rcx, rbx
0x140012272  call    ?serialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<1,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x140012277  mov     r15, rax
0x14001227a  jmp     short loc_14001227F
0x14001227c  xor     r15d, r15d
0x14001227f  mov     rsi, rdi
0x140012282  mov     r12, rdi
0x140012285  mov     r13d, [rbx+14h]
0x140012289  mov     al, [rbx+20h]
0x14001228c  mov     [rsp+8C0h+var_880], al
0x140012290  mov     eax, [rbx+10h]
0x140012293  mov     [rsp+8C0h+var_87C], eax
0x140012297  mov     rax, cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x14001229e  test    rax, rax
0x1400122a1  jnz     short loc_1400122D3
0x1400122a3  call    tip_details_GetKernelBaseModuleHandle
0x1400122a8  mov     rcx, rax; hModule
0x1400122ab  lea     rdx, ProcName; "TestCreate"
0x1400122b2  call    cs:__imp_GetProcAddress
0x1400122b9  nop     dword ptr [rax+rax+00h]
0x1400122be  mov     cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA, rax; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x1400122c5  test    rax, rax
0x1400122c8  jnz     short loc_1400122D3
0x1400122ca  xorps   xmm0, xmm0
0x1400122cd  movdqu  xmmword ptr [rdi], xmm0
0x1400122d1  jmp     short loc_1400122F0
0x1400122d3  mov     [rsp+8C0h+var_898], r12
0x1400122d8  mov     [rsp+8C0h+var_8A0], r15
0x1400122dd  mov     r9d, r13d
0x1400122e0  mov     r8b, [rsp+8C0h+var_880]
0x1400122e5  xor     edx, edx
0x1400122e7  mov     ecx, [rsp+8C0h+var_87C]
0x1400122eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400122f0  lea     rcx, [rbx+0F0h]
0x1400122f7  mov     rdx, rax
0x1400122fa  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHTIPTEST__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::reset(HTIPTEST__ *)
0x1400122ff  mov     dword ptr [rbx+0B8h], 1
0x140012309  movups  xmm0, xmmword ptr [rsi]
0x14001230c  movdqu  xmmword ptr [r14], xmm0
0x140012311  lea     rcx, [rsp+8C0h+var_870]
0x140012316  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14001231b  lea     rcx, [rsp+8C0h+var_878]
0x140012320  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x140012325  mov     rax, r14
0x140012328  mov     rcx, [rbp+7C0h+var_40]
0x14001232f  xor     rcx, rsp; StackCookie
0x140012332  call    __security_check_cookie
0x140012337  mov     rbx, [rsp+8C0h+arg_10]
0x14001233f  add     rsp, 890h
0x140012346  pop     r15
0x140012348  pop     r14
0x14001234a  pop     r13
0x14001234c  pop     r12
0x14001234e  pop     rdi
0x14001234f  pop     rsi
0x140012350  pop     rbp
0x140012351  retn
```
