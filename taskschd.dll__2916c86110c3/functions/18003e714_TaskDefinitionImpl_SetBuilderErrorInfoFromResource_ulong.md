# TaskDefinitionImpl::SetBuilderErrorInfoFromResource(ulong)

- ea: `0x18003e714`
- end: `0x18003e7a5`
- name: `?SetBuilderErrorInfoFromResource@TaskDefinitionImpl@@AEAAJK@Z`
- size: `145`
- prototype: `int(TaskDefinitionImpl *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x180004570`
- `0x180012380`

## callees

- `0x18004e90f`
- `0x18004e950`
- `0x180054010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003e751`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003e751`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18003e767`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18003e767`

## string_xrefs

- `0x18003e74a`: `taskschd.dll`

## pseudocode

```c
__int64 __fastcall TaskDefinitionImpl::SetBuilderErrorInfoFromResource(TaskDefinitionImpl *this, UINT a2)
{
  HMODULE ModuleHandleW; // rax
  WCHAR Buffer[256]; // [rsp+20h] [rbp-218h] BYREF

  memset_0(Buffer, 0, sizeof(Buffer));
  ModuleHandleW = GetModuleHandleW(L"taskschd.dll");
  LoadStringW(ModuleHandleW, a2, Buffer, 256);
  return (*(__int64 (__fastcall **)(TaskDefinitionImpl *, WCHAR *))(*(_QWORD *)this + 168LL))(this, Buffer);
}

```

## disassembly

```asm
0x18003e714  mov     [rsp+arg_10], rbx
0x18003e719  push    rdi
0x18003e71a  sub     rsp, 230h
0x18003e721  mov     rax, cs:__security_cookie
0x18003e728  xor     rax, rsp
0x18003e72b  mov     [rsp+238h+var_18], rax
0x18003e733  mov     ebx, edx
0x18003e735  mov     rdi, rcx
0x18003e738  xor     edx, edx; Val
0x18003e73a  lea     rcx, [rsp+238h+Buffer]; void *
0x18003e73f  mov     r8d, 200h; Size
0x18003e745  call    memset_0
0x18003e74a  lea     rcx, aTaskschdDll_0; "taskschd.dll"
0x18003e751  call    cs:__imp_GetModuleHandleW
0x18003e757  mov     r9d, 100h; cchBufferMax
0x18003e75d  lea     r8, [rsp+238h+Buffer]; lpBuffer
0x18003e762  mov     rcx, rax; hInstance
0x18003e765  mov     edx, ebx; uID
0x18003e767  call    cs:__imp_LoadStringW
0x18003e76d  mov     rax, [rdi]
0x18003e770  lea     rdx, [rsp+238h+Buffer]
0x18003e775  mov     rcx, rdi
0x18003e778  mov     rax, [rax+0A8h]
0x18003e77f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e784  mov     rcx, [rsp+238h+var_18]
0x18003e78c  xor     rcx, rsp; StackCookie
0x18003e78f  call    __security_check_cookie
0x18003e794  mov     rbx, [rsp+238h+arg_10]
0x18003e79c  add     rsp, 230h
0x18003e7a3  pop     rdi
0x18003e7a4  retn
```
