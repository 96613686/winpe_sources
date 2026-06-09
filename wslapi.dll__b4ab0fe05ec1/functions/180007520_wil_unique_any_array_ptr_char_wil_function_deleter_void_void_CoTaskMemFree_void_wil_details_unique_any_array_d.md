# wil::unique_any_array_ptr<char *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)

- ea: `0x180007520`
- end: `0x180007588`
- name: `?reset@?$unique_any_array_ptr@PEADU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ`
- size: `104`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000707c`
- `0x18000725c`

## callees

- `0x180003338`
- `0x180003584`
- `0x180007520`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000754e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000756a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000754e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000756a`

## pseudocode

```c
void __fastcall wil::unique_any_array_ptr<char *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>,unsigned __int64>::reset(
        __int64 a1)
{
  void **v1; // rsi
  void **v3; // rbp
  void *v4; // rbx
  _BYTE v5[56]; // [rsp+20h] [rbp-38h] BYREF

  v1 = *(void ***)a1;
  if ( *(_QWORD *)a1 )
  {
    v3 = &v1[*(_QWORD *)(a1 + 8)];
    while ( v1 != v3 )
    {
      v4 = *v1;
      wil::last_error_context::last_error_context((wil::last_error_context *)v5);
      CoTaskMemFree(v4);
      wil::last_error_context::~last_error_context((wil::last_error_context *)v5);
      ++v1;
    }
    CoTaskMemFree(*(LPVOID *)a1);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x180007520  push    rbx
0x180007522  push    rbp
0x180007523  push    rsi
0x180007524  push    rdi
0x180007525  sub     rsp, 38h
0x180007529  mov     rsi, [rcx]
0x18000752c  mov     rdi, rcx
0x18000752f  test    rsi, rsi
0x180007532  jz      short loc_18000757F
0x180007534  mov     rax, [rcx+8]
0x180007538  lea     rbp, [rsi+rax*8]
0x18000753c  jmp     short loc_180007562
0x18000753e  mov     rbx, [rsi]
0x180007541  lea     rcx, [rsp+58h+var_38]; this
0x180007546  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000754b  mov     rcx, rbx; pv
0x18000754e  call    cs:__imp_CoTaskMemFree
0x180007554  lea     rcx, [rsp+58h+var_38]; this
0x180007559  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000755e  add     rsi, 8
0x180007562  cmp     rsi, rbp
0x180007565  jnz     short loc_18000753E
0x180007567  mov     rcx, [rdi]; pv
0x18000756a  call    cs:__imp_CoTaskMemFree
0x180007570  mov     qword ptr [rdi], 0
0x180007577  mov     qword ptr [rdi+8], 0
0x18000757f  add     rsp, 38h
0x180007583  pop     rdi
0x180007584  pop     rsi
0x180007585  pop     rbp
0x180007586  pop     rbx
0x180007587  retn
```
