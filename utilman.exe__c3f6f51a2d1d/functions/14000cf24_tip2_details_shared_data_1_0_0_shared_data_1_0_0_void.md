# tip2::details::shared_data<1,0,0>::~shared_data<1,0,0>(void)

- ea: `0x14000cf24`
- end: `0x14000cf5a`
- name: `??1?$shared_data@$00$0A@$0A@@details@tip2@@QEAA@XZ`
- size: `54`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000cec0`

## callees

- `0x14000d008`
- `0x14000d2b0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14000cf34`
- `KERNEL32!DeleteCriticalSection` at `0x14000cf34`

## pseudocode

```c
void __fastcall tip2::details::shared_data<1,0,0>::~shared_data<1,0,0>(__int64 a1)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
  wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&void TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&void TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(a1 + 240);
  tip2::test_state::~test_state((tip2::test_state *)(a1 + 8));
}

```

## disassembly

```asm
0x14000cf24  push    rbx
0x14000cf26  sub     rsp, 20h
0x14000cf2a  mov     rbx, rcx
0x14000cf2d  add     rcx, 0C0h; lpCriticalSection
0x14000cf34  call    cs:__imp_DeleteCriticalSection
0x14000cf3b  nop     dword ptr [rax+rax+00h]
0x14000cf40  lea     rcx, [rbx+0F0h]
0x14000cf47  call    ??1?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(void)
0x14000cf4c  lea     rcx, [rbx+8]; this
0x14000cf50  add     rsp, 20h
0x14000cf54  pop     rbx
0x14000cf55  jmp     ??1test_state@tip2@@QEAA@XZ; tip2::test_state::~test_state(void)
```
