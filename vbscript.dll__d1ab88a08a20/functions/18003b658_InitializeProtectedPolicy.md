# InitializeProtectedPolicy

- ea: `0x18003b658`
- end: `0x18003b6e3`
- name: `InitializeProtectedPolicy`
- size: `139`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18003cf74`

## callees

- `0x18003b658`
- `0x180047442`
- `0x18004744e`

## import_xrefs

- `KERNEL32!VirtualProtect` at `0x18003b6a3`
- `KERNEL32!VirtualProtect` at `0x18003b6d0`
- `KERNEL32!VirtualProtect` at `0x18003b6a3`
- `KERNEL32!VirtualProtect` at `0x18003b6d0`

## string_xrefs

- `0x18003b65e`: `api-ms-win-core-processthreads-l1-1-2.dll`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
int InitializeProtectedPolicy()
{
  HMODULE QueryProtectedPolicy; // rax
  unsigned int (__fastcall *v1)(DummyDispatch *__hidden); // rbx
  DWORD flOldProtect; // [rsp+30h] [rbp+8h] BYREF

  flOldProtect = 0;
  QueryProtectedPolicy = GetModuleHandleW_0(L"api-ms-win-core-processthreads-l1-1-2.dll");
  if ( QueryProtectedPolicy )
  {
    QueryProtectedPolicy = (HMODULE)GetProcAddress_0(QueryProtectedPolicy, "QueryProtectedPolicy");
    v1 = (unsigned int (__fastcall *)(DummyDispatch *__hidden))QueryProtectedPolicy;
    if ( QueryProtectedPolicy )
    {
      LODWORD(QueryProtectedPolicy) = VirtualProtect(&QueryProtectedPolicyPtr, 8u, 4u, &flOldProtect);
      if ( (_DWORD)QueryProtectedPolicy )
      {
        QueryProtectedPolicyPtr = v1;
        LODWORD(QueryProtectedPolicy) = VirtualProtect(&QueryProtectedPolicyPtr, 8u, flOldProtect, &flOldProtect);
      }
    }
  }
  return (int)QueryProtectedPolicy;
}

```

## disassembly

```asm
0x18003b658  push    rbx
0x18003b65a  sub     rsp, 20h
0x18003b65e  lea     rcx, aApiMsWinCorePr; "api-ms-win-core-processthreads-l1-1-2.d"...
0x18003b665  mov     [rsp+28h+flOldProtect], 0
0x18003b66d  call    GetModuleHandleW_0
0x18003b672  test    rax, rax
0x18003b675  jz      short loc_18003B6DC
0x18003b677  lea     rdx, aQueryprotected; "QueryProtectedPolicy"
0x18003b67e  mov     rcx, rax; hModule
0x18003b681  call    GetProcAddress_0
0x18003b686  mov     rbx, rax
0x18003b689  test    rax, rax
0x18003b68c  jz      short loc_18003B6DC
0x18003b68e  mov     edx, 8; dwSize
0x18003b693  lea     r9, [rsp+28h+flOldProtect]; lpflOldProtect
0x18003b698  lea     rcx, QueryProtectedPolicyPtr; lpAddress
0x18003b69f  lea     r8d, [rdx-4]; flNewProtect
0x18003b6a3  call    cs:__imp_VirtualProtect
0x18003b6aa  nop     dword ptr [rax+rax+00h]
0x18003b6af  test    eax, eax
0x18003b6b1  jz      short loc_18003B6DC
0x18003b6b3  mov     r8d, [rsp+28h+flOldProtect]; flNewProtect
0x18003b6b8  lea     r9, [rsp+28h+flOldProtect]; lpflOldProtect
0x18003b6bd  mov     edx, 8; dwSize
0x18003b6c2  mov     cs:QueryProtectedPolicyPtr, rbx
0x18003b6c9  lea     rcx, QueryProtectedPolicyPtr; lpAddress
0x18003b6d0  call    cs:__imp_VirtualProtect
0x18003b6d7  nop     dword ptr [rax+rax+00h]
0x18003b6dc  add     rsp, 20h
0x18003b6e0  pop     rbx
0x18003b6e1  retn
```
