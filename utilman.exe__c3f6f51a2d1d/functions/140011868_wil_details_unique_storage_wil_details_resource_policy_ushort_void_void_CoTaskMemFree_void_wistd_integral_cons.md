# wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)

- ea: `0x140011868`
- end: `0x1400118bc`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z`
- size: `84`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x14000bb00`
- `0x14000bba8`

## callees

- `0x1400045a0`
- `0x140004ba4`
- `0x140011868`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x140011892`
- `ole32!CoTaskMemFree` at `0x140011892`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        void **a1,
        void *a2)
{
  void *v2; // rdi
  char v5; // [rsp+30h] [rbp+8h] BYREF

  v2 = *a1;
  if ( *a1 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v5);
    CoTaskMemFree(v2);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v5);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x140011868  mov     [rsp+arg_8], rbx
0x14001186d  mov     [rsp+arg_10], rsi
0x140011872  push    rdi
0x140011873  sub     rsp, 20h
0x140011877  mov     rdi, [rcx]
0x14001187a  mov     rsi, rdx
0x14001187d  mov     rbx, rcx
0x140011880  test    rdi, rdi
0x140011883  jz      short loc_1400118A8
0x140011885  lea     rcx, [rsp+28h+arg_0]; this
0x14001188a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14001188f  mov     rcx, rdi; pv
0x140011892  call    cs:__imp_CoTaskMemFree
0x140011899  nop     dword ptr [rax+rax+00h]
0x14001189e  lea     rcx, [rsp+28h+arg_0]; this
0x1400118a3  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1400118a8  mov     [rbx], rsi
0x1400118ab  mov     rbx, [rsp+28h+arg_8]
0x1400118b0  mov     rsi, [rsp+28h+arg_10]
0x1400118b5  add     rsp, 20h
0x1400118b9  pop     rdi
0x1400118ba  retn
```
