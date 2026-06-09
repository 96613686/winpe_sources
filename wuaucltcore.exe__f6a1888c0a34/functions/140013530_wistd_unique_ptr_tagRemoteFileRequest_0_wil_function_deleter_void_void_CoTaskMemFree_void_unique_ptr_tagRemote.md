# wistd::unique_ptr<tagRemoteFileRequest [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::~unique_ptr<tagRemoteFileRequest [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>(void)

- ea: `0x140013530`
- end: `0x140013551`
- name: `??1?$unique_ptr@$$BY0A@UtagRemoteFileRequest@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAA@XZ`
- size: `33`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400218d3`
- `0x14002193f`

## callees

- `0x140013530`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140013546`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140013546`

## pseudocode

```c
void __fastcall wistd::unique_ptr<tagRemoteFileRequest [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::~unique_ptr<tagRemoteFileRequest [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>(
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
0x140013530  sub     rsp, 28h
0x140013534  mov     rax, [rcx]
0x140013537  mov     qword ptr [rcx], 0
0x14001353e  test    rax, rax
0x140013541  jz      short loc_14001354C
0x140013543  mov     rcx, rax; pv
0x140013546  call    cs:__imp_CoTaskMemFree
0x14001354c  add     rsp, 28h
0x140013550  retn
```
