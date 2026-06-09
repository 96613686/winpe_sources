# tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(void)

- ea: `0x18002fddc`
- end: `0x18002fe69`
- name: `??1?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA@XZ`
- size: `141`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002fd4c`

## callees

- `0x18002fddc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fe36`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fe36`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fe22`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fe22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fe0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fe0b`

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
0x18002fddc  mov     [rsp+arg_0], rbx
0x18002fde1  mov     [rsp+arg_8], rsi
0x18002fde6  push    rdi
0x18002fde7  sub     rsp, 20h
0x18002fdeb  cmp     qword ptr [rcx], 0
0x18002fdef  lea     rdi, [rcx+10h]
0x18002fdf3  mov     rsi, rcx
0x18002fdf6  jz      short loc_18002FE49
0x18002fdf8  xor     ebx, ebx
0x18002fdfa  cmp     [rdi], rbx
0x18002fdfd  jbe     short loc_18002FE1F
0x18002fdff  mov     rax, [rsi]
0x18002fe02  mov     rcx, [rax+rbx*8]; pv
0x18002fe06  test    rcx, rcx
0x18002fe09  jz      short loc_18002FE17
0x18002fe0b  call    cs:__imp_CoTaskMemFree
0x18002fe12  nop     dword ptr [rax+rax+00h]
0x18002fe17  inc     rbx
0x18002fe1a  cmp     rbx, [rdi]
0x18002fe1d  jb      short loc_18002FDFF
0x18002fe1f  mov     rbx, [rsi]
0x18002fe22  call    cs:__imp_GetProcessHeap
0x18002fe29  nop     dword ptr [rax+rax+00h]
0x18002fe2e  mov     r8, rbx; lpMem
0x18002fe31  xor     edx, edx; dwFlags
0x18002fe33  mov     rcx, rax; hHeap
0x18002fe36  call    cs:__imp_HeapFree
0x18002fe3d  nop     dword ptr [rax+rax+00h]
0x18002fe42  mov     qword ptr [rsi], 0
0x18002fe49  mov     rbx, [rsp+28h+arg_0]
0x18002fe4e  mov     qword ptr [rsi+8], 0
0x18002fe56  mov     rsi, [rsp+28h+arg_8]
0x18002fe5b  mov     qword ptr [rdi], 0
0x18002fe62  add     rsp, 20h
0x18002fe66  pop     rdi
0x18002fe67  retn
```
