# wistd::unique_ptr<void,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::~unique_ptr<void,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>(void)

- ea: `0x18001a2f8`
- end: `0x18001a319`
- name: `??1?$unique_ptr@XU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAA@XZ`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002bcb0`

## callees

- `0x18001a2f8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a30e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a30e`

## pseudocode

```c
void __fastcall wistd::unique_ptr<void,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::~unique_ptr<void,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>(
        void **a1)
{
  void *v1; // rax

  v1 = *a1;
  *a1 = 0;
  if ( v1 )
    CoTaskMemFree(v1);
}

```

## disassembly

```asm
0x18001a2f8  sub     rsp, 28h
0x18001a2fc  mov     rax, [rcx]
0x18001a2ff  mov     qword ptr [rcx], 0
0x18001a306  test    rax, rax
0x18001a309  jz      short loc_18001A314
0x18001a30b  mov     rcx, rax; pv
0x18001a30e  call    cs:__imp_CoTaskMemFree
0x18001a314  add     rsp, 28h
0x18001a318  retn
```
