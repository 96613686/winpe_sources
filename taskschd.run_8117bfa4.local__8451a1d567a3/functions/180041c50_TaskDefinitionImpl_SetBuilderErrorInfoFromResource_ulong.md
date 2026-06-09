# TaskDefinitionImpl::SetBuilderErrorInfoFromResource(ulong)

- ea: `0x180041c50`
- end: `0x180041cee`
- name: `?SetBuilderErrorInfoFromResource@TaskDefinitionImpl@@AEAAJK@Z`
- size: `158`
- prototype: `int(TaskDefinitionImpl *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x180004800`
- `0x180012e60`

## callees

- `0x18005260b`
- `0x180052640`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180041c8d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180041c8d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180041ca9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180041ca9`

## string_xrefs

- `0x180041c86`: `taskschd.dll`

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
0x180041c50  mov     [rsp+arg_10], rbx
0x180041c55  push    rdi
0x180041c56  sub     rsp, 230h
0x180041c5d  mov     rax, cs:__security_cookie
0x180041c64  xor     rax, rsp
0x180041c67  mov     [rsp+238h+var_18], rax
0x180041c6f  mov     ebx, edx
0x180041c71  mov     rdi, rcx
0x180041c74  xor     edx, edx; Val
0x180041c76  lea     rcx, [rsp+238h+Buffer]; void *
0x180041c7b  mov     r8d, 200h; Size
0x180041c81  call    memset_0
0x180041c86  lea     rcx, aTaskschdDll_0; "taskschd.dll"
0x180041c8d  call    cs:__imp_GetModuleHandleW
0x180041c94  nop     dword ptr [rax+rax+00h]
0x180041c99  mov     r9d, 100h; cchBufferMax
0x180041c9f  lea     r8, [rsp+238h+Buffer]; lpBuffer
0x180041ca4  mov     rcx, rax; hInstance
0x180041ca7  mov     edx, ebx; uID
0x180041ca9  call    cs:__imp_LoadStringW
0x180041cb0  nop     dword ptr [rax+rax+00h]
0x180041cb5  mov     rax, [rdi]
0x180041cb8  lea     rdx, [rsp+238h+Buffer]
0x180041cbd  mov     rcx, rdi
0x180041cc0  mov     rax, [rax+0A8h]
0x180041cc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041ccc  mov     rcx, [rsp+238h+var_18]
0x180041cd4  xor     rcx, rsp; StackCookie
0x180041cd7  call    __security_check_cookie
0x180041cdc  mov     rbx, [rsp+238h+arg_10]
0x180041ce4  add     rsp, 230h
0x180041ceb  pop     rdi
0x180041cec  retn
```
