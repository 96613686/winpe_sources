# wil::details::unique_storage<wil::details::resource_policy<HCMNOTIFICATION__ *,ulong (*)(HCMNOTIFICATION__ *),&CM_Unregister_Notification(HCMNOTIFICATION__ *),wistd::integral_constant<unsigned __int64,0>,HCMNOTIFICATION__ *,HCMNOTIFICATION__ *,0,std::nullptr_t>>::reset(HCMNOTIFICATION__ *)

- ea: `0x180006eac`
- end: `0x180006ef9`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAUHCMNOTIFICATION__@@P6AKPEAU1@@Z$1?CM_Unregister_Notification@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHCMNOTIFICATION__@@@Z`
- size: `77`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180001d30`
- `0x180005940`
- `0x1800071f0`

## callees

- `0x180003e54`
- `0x18000414c`
- `0x180006eac`

## import_xrefs

- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x180006ed6`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x180006ed6`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<HCMNOTIFICATION__ *,unsigned long (*)(HCMNOTIFICATION__ *),&unsigned long CM_Unregister_Notification(HCMNOTIFICATION__ *),wistd::integral_constant<unsigned __int64,0>,HCMNOTIFICATION__ *,HCMNOTIFICATION__ *,0,std::nullptr_t>>::reset(
        __int64 *a1,
        __int64 a2)
{
  __int64 v2; // rdi
  char v5; // [rsp+30h] [rbp+8h] BYREF

  v2 = *a1;
  if ( *a1 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v5);
    CM_Unregister_Notification(v2);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v5);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x180006eac  mov     [rsp+arg_8], rbx
0x180006eb1  mov     [rsp+arg_10], rsi
0x180006eb6  push    rdi
0x180006eb7  sub     rsp, 20h
0x180006ebb  mov     rdi, [rcx]
0x180006ebe  mov     rsi, rdx
0x180006ec1  mov     rbx, rcx
0x180006ec4  test    rdi, rdi
0x180006ec7  jz      short loc_180006EE6
0x180006ec9  lea     rcx, [rsp+28h+arg_0]; this
0x180006ece  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180006ed3  mov     rcx, rdi
0x180006ed6  call    cs:__imp_CM_Unregister_Notification
0x180006edc  lea     rcx, [rsp+28h+arg_0]; this
0x180006ee1  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180006ee6  mov     [rbx], rsi
0x180006ee9  mov     rbx, [rsp+28h+arg_8]
0x180006eee  mov     rsi, [rsp+28h+arg_10]
0x180006ef3  add     rsp, 20h
0x180006ef7  pop     rdi
0x180006ef8  retn
```
