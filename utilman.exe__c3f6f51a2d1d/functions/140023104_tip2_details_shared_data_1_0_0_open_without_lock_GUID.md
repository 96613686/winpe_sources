# tip2::details::shared_data<1,0,0>::open_without_lock(_GUID *)

- ea: `0x140023104`
- end: `0x140023234`
- name: `?open_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@IEAAXPEAU_GUID@@@Z`
- size: `304`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x14001f1e0`
- `0x1400206e8`

## callees

- `0x140002480`
- `0x14000d008`
- `0x14000fce8`
- `0x1400118c4`
- `0x140012f1c`
- `0x140023104`
- `0x140029010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14002315f`
- `KERNEL32!GetProcAddress` at `0x14002315f`
- `ole32!CoTaskMemFree` at `0x140023205`
- `ole32!CoTaskMemFree` at `0x140023205`

## string_xrefs

- `0x140023158`: `TestOpen`

## pseudocode

```c
void __fastcall tip2::details::shared_data<1,0,0>::open_without_lock(__int64 a1, __int64 a2, __int64 a3)
{
  char v5; // si
  unsigned int v6; // r14d
  FARPROC ProcAddress; // rax
  HMODULE KernelBaseModuleHandle; // rax
  __int64 v9; // rax
  __int64 v10; // [rsp+30h] [rbp-40h] BYREF
  __int128 v11; // [rsp+38h] [rbp-38h] BYREF
  LPVOID pv[2]; // [rsp+48h] [rbp-28h]
  __int128 v13; // [rsp+58h] [rbp-18h]

  v11 = 0;
  *(_OWORD *)pv = 0;
  v13 = 0;
  v5 = *(_BYTE *)(a1 + 32);
  v6 = *(_DWORD *)(a1 + 16);
  ProcAddress = (FARPROC)`TestOpen'::`2'::s_pfnTestOpen;
  if ( `TestOpen'::`2'::s_pfnTestOpen
    || (KernelBaseModuleHandle = (HMODULE)tip_details_GetKernelBaseModuleHandle(),
        ProcAddress = GetProcAddress(KernelBaseModuleHandle, "TestOpen"),
        (`TestOpen'::`2'::s_pfnTestOpen = (__int64)ProcAddress) != 0) )
  {
    LOBYTE(a3) = v5;
    v9 = ((__int64 (__fastcall *)(_QWORD, __int64, __int64, __int64, __int128 *))ProcAddress)(v6, 2097154, a3, a2, &v11);
    v10 = v9;
    if ( v9 )
    {
      *(_OWORD *)(a1 + 144) = v11;
      v10 = 0;
      wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&void TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::reset(
        a1 + 240,
        v9);
      *(_DWORD *)(a1 + 64) |= HIDWORD(pv[0]);
      if ( pv[1] )
        tip2::details::shared_data<1,0,0>::deserialize_data(a1, &v11);
      else
        *(_DWORD *)(a1 + 184) = pv[0];
    }
  }
  else
  {
    v11 = 0;
    *(_OWORD *)pv = 0;
    v13 = 0;
    v10 = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&void TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&void TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(&v10);
  CoTaskMemFree(pv[1]);
}

```

## disassembly

```asm
0x140023104  mov     [rsp-18h+arg_10], rbx
0x140023109  mov     [rsp-18h+arg_18], rsi
0x14002310e  push    rbp
0x14002310f  push    rdi
0x140023110  push    r14
0x140023112  mov     rbp, rsp
0x140023115  sub     rsp, 70h
0x140023119  mov     rax, cs:__security_cookie
0x140023120  xor     rax, rsp
0x140023123  mov     [rbp+var_8], rax
0x140023127  mov     rdi, rdx
0x14002312a  mov     rbx, rcx
0x14002312d  xorps   xmm0, xmm0
0x140023130  movups  [rbp+var_38], xmm0
0x140023134  movups  xmmword ptr [rbp+pv], xmm0
0x140023138  movups  [rbp+var_18], xmm0
0x14002313c  mov     sil, [rcx+20h]
0x140023140  mov     r14d, [rcx+10h]
0x140023144  mov     rax, cs:?s_pfnTestOpen@?1??TestOpen@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@PEAU_GUID@@PEAUTestInfo@TestInfo_ODR_guard@@@ZEA; HTIPTEST__ * (*`TestOpen'::`2'::s_pfnTestOpen)(uint,TestRetrievalOptions,TestStorage,_GUID *,TestInfo_ODR_guard::TestInfo *)
0x14002314b  test    rax, rax
0x14002314e  jnz     short loc_14002318C
0x140023150  call    tip_details_GetKernelBaseModuleHandle
0x140023155  mov     rcx, rax; hModule
0x140023158  lea     rdx, aTestopen; "TestOpen"
0x14002315f  call    cs:__imp_GetProcAddress
0x140023166  nop     dword ptr [rax+rax+00h]
0x14002316b  mov     cs:?s_pfnTestOpen@?1??TestOpen@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@PEAU_GUID@@PEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; HTIPTEST__ * (*`TestOpen'::`2'::s_pfnTestOpen)(uint,TestRetrievalOptions,TestStorage,_GUID *,TestInfo_ODR_guard::TestInfo *)
0x140023172  test    rax, rax
0x140023175  jnz     short loc_14002318C
0x140023177  xorps   xmm0, xmm0
0x14002317a  movups  [rbp+var_38], xmm0
0x14002317e  movups  xmmword ptr [rbp+pv], xmm0
0x140023182  movups  [rbp+var_18], xmm0
0x140023186  mov     [rbp+var_40], rax
0x14002318a  jmp     short loc_1400231F8
0x14002318c  lea     rcx, [rbp+var_38]
0x140023190  mov     [rsp+70h+var_50], rcx
0x140023195  mov     r9, rdi
0x140023198  mov     r8b, sil
0x14002319b  mov     edx, 200002h
0x1400231a0  mov     ecx, r14d
0x1400231a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400231a8  mov     [rbp+var_40], rax
0x1400231ac  test    rax, rax
0x1400231af  jz      short loc_1400231F8
0x1400231b1  movups  xmm0, [rbp+var_38]
0x1400231b5  movdqu  xmmword ptr [rbx+90h], xmm0
0x1400231bd  mov     [rbp+var_40], 0
0x1400231c5  lea     rcx, [rbx+0F0h]
0x1400231cc  mov     rdx, rax
0x1400231cf  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHTIPTEST__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::reset(HTIPTEST__ *)
0x1400231d4  mov     eax, dword ptr [rbp+pv+4]
0x1400231d7  or      [rbx+40h], eax
0x1400231da  cmp     [rbp+pv+8], 0
0x1400231df  jz      short loc_1400231EF
0x1400231e1  lea     rdx, [rbp+var_38]
0x1400231e5  mov     rcx, rbx
0x1400231e8  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x1400231ed  jmp     short loc_1400231F8
0x1400231ef  mov     eax, dword ptr [rbp+pv]
0x1400231f2  mov     [rbx+0B8h], eax
0x1400231f8  lea     rcx, [rbp+var_40]
0x1400231fc  call    ??1?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(void)
0x140023201  mov     rcx, [rbp+pv+8]; pv
0x140023205  call    cs:__imp_CoTaskMemFree
0x14002320c  nop     dword ptr [rax+rax+00h]
0x140023211  nop
0x140023212  mov     rcx, [rbp+var_8]
0x140023216  xor     rcx, rsp; StackCookie
0x140023219  call    __security_check_cookie
0x14002321e  lea     r11, [rsp+70h+var_s0]
0x140023223  mov     rbx, [r11+30h]
0x140023227  mov     rsi, [r11+38h]
0x14002322b  mov     rsp, r11
0x14002322e  pop     r14
0x140023230  pop     rdi
0x140023231  pop     rbp
0x140023232  retn
```
