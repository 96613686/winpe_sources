# wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)

- ea: `0x1800017e0`
- end: `0x1800017fe`
- name: `??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800012b0`
- `0x180001b84`
- `0x180001d30`

## callees

- `0x1800017e0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800017f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800017f6`

## pseudocode

```c
int __fastcall wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(
        void **a1)
{
  char *v1; // rcx
  int result; // eax

  v1 = (char *)*a1;
  result = (_DWORD)v1 - 1;
  if ( (unsigned __int64)(v1 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    return CloseHandle(v1);
  return result;
}

```

## disassembly

```asm
0x1800017e0  sub     rsp, 28h
0x1800017e4  mov     rcx, [rcx]; hObject
0x1800017e7  lea     rax, [rcx-1]
0x1800017eb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800017ef  jbe     short loc_1800017F6
0x1800017f1  add     rsp, 28h
0x1800017f5  retn
0x1800017f6  call    cs:__imp_CloseHandle
0x1800017fc  jmp     short loc_1800017F1
```
