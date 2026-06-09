# wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)

- ea: `0x18003bf18`
- end: `0x18003bf42`
- name: `??1?$out_param_t@V?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ`
- size: `42`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003c080`

## callees

- `0x18003bf18`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bf37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bf37`

## pseudocode

```c
void __fastcall wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(
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
0x18003bf18  sub     rsp, 28h
0x18003bf1c  cmp     byte ptr [rcx+10h], 0
0x18003bf20  jz      short loc_18003BF3D
0x18003bf22  mov     rdx, [rcx]
0x18003bf25  mov     rax, [rcx+8]
0x18003bf29  mov     r8, [rdx]
0x18003bf2c  mov     [rdx], rax
0x18003bf2f  test    r8, r8
0x18003bf32  jz      short loc_18003BF3D
0x18003bf34  mov     rcx, r8; pv
0x18003bf37  call    cs:__imp_CoTaskMemFree
0x18003bf3d  add     rsp, 28h
0x18003bf41  retn
```
