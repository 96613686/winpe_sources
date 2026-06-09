# tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(void)

- ea: `0x14000d23c`
- end: `0x14000d2b6`
- name: `??1?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA@XZ`
- size: `122`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14000cd58`

## callees

- `0x14000d23c`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x14000d27c`
- `KERNEL32!GetProcessHeap` at `0x14000d27c`
- `KERNEL32!HeapFree` at `0x14000d28a`
- `KERNEL32!HeapFree` at `0x14000d28a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000d26b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000d26b`

## pseudocode

```c
void __fastcall tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(
        _QWORD *a1)
{
  unsigned __int64 *v1; // rdi
  unsigned __int64 i; // rbx
  void *v4; // rcx
  void *v5; // rbx
  HANDLE ProcessHeap; // rax

  v1 = a1 + 2;
  if ( *a1 )
  {
    for ( i = 0; i < *v1; ++i )
    {
      v4 = *(void **)(*a1 + 8 * i);
      if ( v4 )
        CoTaskMemFree(v4);
    }
    v5 = (void *)*a1;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v5);
    *a1 = 0;
  }
  a1[1] = 0;
  *v1 = 0;
}

```

## disassembly

```asm
0x14000d23c  mov     [rsp+arg_0], rbx
0x14000d241  mov     [rsp+arg_8], rsi
0x14000d246  push    rdi
0x14000d247  sub     rsp, 20h
0x14000d24b  cmp     qword ptr [rcx], 0
0x14000d24f  lea     rdi, [rcx+10h]
0x14000d253  mov     rsi, rcx
0x14000d256  jz      short loc_14000D297
0x14000d258  xor     ebx, ebx
0x14000d25a  cmp     [rdi], rbx
0x14000d25d  jbe     short loc_14000D279
0x14000d25f  mov     rax, [rsi]
0x14000d262  mov     rcx, [rax+rbx*8]; pv
0x14000d266  test    rcx, rcx
0x14000d269  jz      short loc_14000D271
0x14000d26b  call    cs:__imp_CoTaskMemFree
0x14000d271  inc     rbx
0x14000d274  cmp     rbx, [rdi]
0x14000d277  jb      short loc_14000D25F
0x14000d279  mov     rbx, [rsi]
0x14000d27c  call    cs:__imp_GetProcessHeap
0x14000d282  mov     r8, rbx; lpMem
0x14000d285  xor     edx, edx; dwFlags
0x14000d287  mov     rcx, rax; hHeap
0x14000d28a  call    cs:__imp_HeapFree
0x14000d290  mov     qword ptr [rsi], 0
0x14000d297  mov     rbx, [rsp+28h+arg_0]
0x14000d29c  mov     qword ptr [rsi+8], 0
0x14000d2a4  mov     rsi, [rsp+28h+arg_8]
0x14000d2a9  mov     qword ptr [rdi], 0
0x14000d2b0  add     rsp, 20h
0x14000d2b4  pop     rdi
0x14000d2b5  retn
```
