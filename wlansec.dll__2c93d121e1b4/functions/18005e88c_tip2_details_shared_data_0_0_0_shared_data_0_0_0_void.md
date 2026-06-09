# tip2::details::shared_data<0,0,0>::~shared_data<0,0,0>(void)

- ea: `0x18005e88c`
- end: `0x18005e8c2`
- name: `??1?$shared_data@$0A@$0A@$0A@@details@tip2@@QEAA@XZ`
- size: `54`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18005e7e0`

## callees

- `0x18005e974`
- `0x18005ea84`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005e89c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005e89c`

## pseudocode

```c
void __fastcall tip2::details::shared_data<0,0,0>::~shared_data<0,0,0>(__int64 a1)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
  wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&void TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&void TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(a1 + 240);
  tip2::test_state::~test_state((tip2::test_state *)(a1 + 8));
}

```

## disassembly

```asm
0x18005e88c  push    rbx
0x18005e88e  sub     rsp, 20h
0x18005e892  mov     rbx, rcx
0x18005e895  add     rcx, 0C0h; lpCriticalSection
0x18005e89c  call    cs:__imp_DeleteCriticalSection
0x18005e8a3  nop     dword ptr [rax+rax+00h]
0x18005e8a8  lea     rcx, [rbx+0F0h]
0x18005e8af  call    ??1?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(void)
0x18005e8b4  lea     rcx, [rbx+8]; this
0x18005e8b8  add     rsp, 20h
0x18005e8bc  pop     rbx
0x18005e8bd  jmp     ??1test_state@tip2@@QEAA@XZ; tip2::test_state::~test_state(void)
```
