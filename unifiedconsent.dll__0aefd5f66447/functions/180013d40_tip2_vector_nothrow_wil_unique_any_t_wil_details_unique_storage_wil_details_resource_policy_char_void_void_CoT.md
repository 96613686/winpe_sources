# tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(void)

- ea: `0x180013d40`
- end: `0x180013dba`
- name: `??1?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA@XZ`
- size: `122`
- prototype: ``
- caller_count: `15`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180013a68`
- `0x1800229ac`
- `0x180022a38`
- `0x180022ac4`
- `0x180022b50`
- `0x180022bdc`
- `0x1800327f8`
- `0x180032890`
- `0x180040674`
- `0x1800515bc`
- `0x1800583f0`
- `0x180058488`
- `0x180058544`
- `0x180060e40`
- `0x180069484`

## callees

- `0x180013d40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013d6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013d6f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013d8e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013d8e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013d80`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013d80`

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
0x180013d40  mov     [rsp+arg_0], rbx
0x180013d45  mov     [rsp+arg_8], rsi
0x180013d4a  push    rdi
0x180013d4b  sub     rsp, 20h
0x180013d4f  cmp     qword ptr [rcx], 0
0x180013d53  lea     rdi, [rcx+10h]
0x180013d57  mov     rsi, rcx
0x180013d5a  jz      short loc_180013D9B
0x180013d5c  xor     ebx, ebx
0x180013d5e  cmp     [rdi], rbx
0x180013d61  jbe     short loc_180013D7D
0x180013d63  mov     rax, [rsi]
0x180013d66  mov     rcx, [rax+rbx*8]; pv
0x180013d6a  test    rcx, rcx
0x180013d6d  jz      short loc_180013D75
0x180013d6f  call    cs:__imp_CoTaskMemFree
0x180013d75  inc     rbx
0x180013d78  cmp     rbx, [rdi]
0x180013d7b  jb      short loc_180013D63
0x180013d7d  mov     rbx, [rsi]
0x180013d80  call    cs:__imp_GetProcessHeap
0x180013d86  mov     r8, rbx; lpMem
0x180013d89  xor     edx, edx; dwFlags
0x180013d8b  mov     rcx, rax; hHeap
0x180013d8e  call    cs:__imp_HeapFree
0x180013d94  mov     qword ptr [rsi], 0
0x180013d9b  mov     rbx, [rsp+28h+arg_0]
0x180013da0  mov     qword ptr [rsi+8], 0
0x180013da8  mov     rsi, [rsp+28h+arg_8]
0x180013dad  mov     qword ptr [rdi], 0
0x180013db4  add     rsp, 20h
0x180013db8  pop     rdi
0x180013db9  retn
```
