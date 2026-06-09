# wil::details::out_param_ptr_t<uchar * *,wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_ptr_t<uchar * *,wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)

- ea: `0x18000a6c4`
- end: `0x18000a6ee`
- name: `??1?$out_param_ptr_t@PEAPEAEV?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ`
- size: `42`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000f82b`

## callees

- `0x18000a6c4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a6e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a6e3`

## pseudocode

```c
void __fastcall wil::details::out_param_ptr_t<unsigned char * *,wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_ptr_t<unsigned char * *,wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(
        __int64 a1)
{
  void *v1; // r8

  if ( *(_BYTE *)(a1 + 16) )
  {
    v1 = **(void ***)a1;
    **(_QWORD **)a1 = *(_QWORD *)(a1 + 8);
    if ( v1 )
      CoTaskMemFree(v1);
  }
}

```

## disassembly

```asm
0x18000a6c4  sub     rsp, 28h
0x18000a6c8  cmp     byte ptr [rcx+10h], 0
0x18000a6cc  jz      short loc_18000A6E9
0x18000a6ce  mov     rdx, [rcx]
0x18000a6d1  mov     rax, [rcx+8]
0x18000a6d5  mov     r8, [rdx]
0x18000a6d8  mov     [rdx], rax
0x18000a6db  test    r8, r8
0x18000a6de  jz      short loc_18000A6E9
0x18000a6e0  mov     rcx, r8; pv
0x18000a6e3  call    cs:__imp_CoTaskMemFree
0x18000a6e9  add     rsp, 28h
0x18000a6ed  retn
```
