# wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(_ITEMIDLIST_ABSOLUTE *)

- ea: `0x18002b180`
- end: `0x18002b19d`
- name: `?reset@?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAU_ITEMIDLIST_ABSOLUTE@@@Z`
- size: `29`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005598`
- `0x18000e4b8`
- `0x18000f430`
- `0x1800292a4`
- `0x180029a38`
- `0x180029ad4`
- `0x180036ba0`
- `0x180036bd0`
- `0x180036c00`
- `0x180036c30`

## callees

- `0x18002b180`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b192`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b192`

## pseudocode

```c
void __fastcall wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
        void **a1,
        void *a2)
{
  void *v2; // rax

  v2 = *a1;
  *a1 = a2;
  if ( v2 )
    CoTaskMemFree(v2);
}

```

## disassembly

```asm
0x18002b180  sub     rsp, 28h
0x18002b184  mov     rax, [rcx]
0x18002b187  mov     [rcx], rdx
0x18002b18a  test    rax, rax
0x18002b18d  jz      short loc_18002B198
0x18002b18f  mov     rcx, rax; pv
0x18002b192  call    cs:__imp_CoTaskMemFree
0x18002b198  add     rsp, 28h
0x18002b19c  retn
```
