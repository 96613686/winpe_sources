# tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(void)

- ea: `0x18001016c`
- end: `0x1800101e6`
- name: `??1?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA@XZ`
- size: `122`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000fc3c`
- `0x18000fcd4`

## callees

- `0x18001016c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800101ac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800101ac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800101ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800101ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001019b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001019b`

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
0x18001016c  mov     [rsp+arg_0], rbx
0x180010171  mov     [rsp+arg_8], rsi
0x180010176  push    rdi
0x180010177  sub     rsp, 20h
0x18001017b  cmp     qword ptr [rcx], 0
0x18001017f  lea     rdi, [rcx+10h]
0x180010183  mov     rsi, rcx
0x180010186  jz      short loc_1800101C7
0x180010188  xor     ebx, ebx
0x18001018a  cmp     [rdi], rbx
0x18001018d  jbe     short loc_1800101A9
0x18001018f  mov     rax, [rsi]
0x180010192  mov     rcx, [rax+rbx*8]; pv
0x180010196  test    rcx, rcx
0x180010199  jz      short loc_1800101A1
0x18001019b  call    cs:__imp_CoTaskMemFree
0x1800101a1  inc     rbx
0x1800101a4  cmp     rbx, [rdi]
0x1800101a7  jb      short loc_18001018F
0x1800101a9  mov     rbx, [rsi]
0x1800101ac  call    cs:__imp_GetProcessHeap
0x1800101b2  mov     r8, rbx; lpMem
0x1800101b5  xor     edx, edx; dwFlags
0x1800101b7  mov     rcx, rax; hHeap
0x1800101ba  call    cs:__imp_HeapFree
0x1800101c0  mov     qword ptr [rsi], 0
0x1800101c7  mov     rbx, [rsp+28h+arg_0]
0x1800101cc  mov     qword ptr [rsi+8], 0
0x1800101d4  mov     rsi, [rsp+28h+arg_8]
0x1800101d9  mov     qword ptr [rdi], 0
0x1800101e0  add     rsp, 20h
0x1800101e4  pop     rdi
0x1800101e5  retn
```
