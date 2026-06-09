# tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(void)

- ea: `0x180006f04`
- end: `0x180006f7e`
- name: `??1?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA@XZ`
- size: `122`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180005950`

## callees

- `0x180006f04`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006f33`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006f33`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006f52`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006f52`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006f44`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006f44`

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
0x180006f04  mov     [rsp+arg_0], rbx
0x180006f09  mov     [rsp+arg_8], rsi
0x180006f0e  push    rdi
0x180006f0f  sub     rsp, 20h
0x180006f13  cmp     qword ptr [rcx], 0
0x180006f17  lea     rdi, [rcx+10h]
0x180006f1b  mov     rsi, rcx
0x180006f1e  jz      short loc_180006F5F
0x180006f20  xor     ebx, ebx
0x180006f22  cmp     [rdi], rbx
0x180006f25  jbe     short loc_180006F41
0x180006f27  mov     rax, [rsi]
0x180006f2a  mov     rcx, [rax+rbx*8]; pv
0x180006f2e  test    rcx, rcx
0x180006f31  jz      short loc_180006F39
0x180006f33  call    cs:__imp_CoTaskMemFree
0x180006f39  inc     rbx
0x180006f3c  cmp     rbx, [rdi]
0x180006f3f  jb      short loc_180006F27
0x180006f41  mov     rbx, [rsi]
0x180006f44  call    cs:__imp_GetProcessHeap
0x180006f4a  mov     r8, rbx; lpMem
0x180006f4d  xor     edx, edx; dwFlags
0x180006f4f  mov     rcx, rax; hHeap
0x180006f52  call    cs:__imp_HeapFree
0x180006f58  mov     qword ptr [rsi], 0
0x180006f5f  mov     rbx, [rsp+28h+arg_0]
0x180006f64  mov     qword ptr [rsi+8], 0
0x180006f6c  mov     rsi, [rsp+28h+arg_8]
0x180006f71  mov     qword ptr [rdi], 0
0x180006f78  add     rsp, 20h
0x180006f7c  pop     rdi
0x180006f7d  retn
```
