# wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)

- ea: `0x180006968`
- end: `0x180006984`
- name: `??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ`
- size: `28`
- prototype: `int __fastcall(void **)`
- caller_count: `11`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800068c8`
- `0x180006c10`
- `0x180006cb0`
- `0x180007344`
- `0x1800075f0`
- `0x180007680`
- `0x180007720`
- `0x180007ca0`
- `0x180007d90`
- `0x180007e60`
- `0x18000a054`

## callees

- `0x180006968`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006979`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006979`

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
0x180006968  sub     rsp, 28h
0x18000696c  mov     rcx, [rcx]; hObject
0x18000696f  lea     rax, [rcx-1]
0x180006973  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180006977  ja      short loc_18000697F
0x180006979  call    cs:__imp_CloseHandle
0x18000697f  add     rsp, 28h
0x180006983  retn
```
