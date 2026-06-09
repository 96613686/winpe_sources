# wistd::unique_ptr<HSTRING__ * [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::~unique_ptr<HSTRING__ * [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>(void)

- ea: `0x180018198`
- end: `0x1800181b9`
- name: `??1?$unique_ptr@$$BY0A@PEAUHSTRING__@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAA@XZ`
- size: `33`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800981fb`

## callees

- `0x180018198`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800181ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800181ae`

## pseudocode

```c
void __fastcall wistd::unique_ptr<HSTRING__ * [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::~unique_ptr<HSTRING__ * [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>(
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
0x180018198  sub     rsp, 28h
0x18001819c  mov     rax, [rcx]
0x18001819f  mov     qword ptr [rcx], 0
0x1800181a6  test    rax, rax
0x1800181a9  jz      short loc_1800181B4
0x1800181ab  mov     rcx, rax; pv
0x1800181ae  call    cs:__imp_CoTaskMemFree
0x1800181b4  add     rsp, 28h
0x1800181b8  retn
```
