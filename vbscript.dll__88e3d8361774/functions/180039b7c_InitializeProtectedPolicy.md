# InitializeProtectedPolicy

- ea: `0x180039b7c`
- end: `0x180039bfa`
- name: `InitializeProtectedPolicy`
- size: `126`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18003d5fc`

## callees

- `0x180039b7c`
- `0x180046032`
- `0x18004603e`

## import_xrefs

- `KERNEL32!VirtualProtect` at `0x180039bc7`
- `KERNEL32!VirtualProtect` at `0x180039bee`
- `KERNEL32!VirtualProtect` at `0x180039bc7`
- `KERNEL32!VirtualProtect` at `0x180039bee`

## string_xrefs

- `0x180039b82`: `api-ms-win-core-processthreads-l1-1-2.dll`

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
0x180039b7c  push    rbx
0x180039b7e  sub     rsp, 20h
0x180039b82  lea     rcx, aApiMsWinCorePr; "api-ms-win-core-processthreads-l1-1-2.d"...
0x180039b89  mov     [rsp+28h+flOldProtect], 0
0x180039b91  call    GetModuleHandleW_0
0x180039b96  test    rax, rax
0x180039b99  jz      short loc_180039BF4
0x180039b9b  lea     rdx, aQueryprotected; "QueryProtectedPolicy"
0x180039ba2  mov     rcx, rax; hModule
0x180039ba5  call    GetProcAddress_0
0x180039baa  mov     rbx, rax
0x180039bad  test    rax, rax
0x180039bb0  jz      short loc_180039BF4
0x180039bb2  mov     edx, 8; dwSize
0x180039bb7  lea     r9, [rsp+28h+flOldProtect]; lpflOldProtect
0x180039bbc  lea     rcx, QueryProtectedPolicyPtr; lpAddress
0x180039bc3  lea     r8d, [rdx-4]; flNewProtect
0x180039bc7  call    cs:__imp_VirtualProtect
0x180039bcd  test    eax, eax
0x180039bcf  jz      short loc_180039BF4
0x180039bd1  mov     r8d, [rsp+28h+flOldProtect]; flNewProtect
0x180039bd6  lea     r9, [rsp+28h+flOldProtect]; lpflOldProtect
0x180039bdb  mov     edx, 8; dwSize
0x180039be0  mov     cs:QueryProtectedPolicyPtr, rbx
0x180039be7  lea     rcx, QueryProtectedPolicyPtr; lpAddress
0x180039bee  call    cs:__imp_VirtualProtect
0x180039bf4  add     rsp, 20h
0x180039bf8  pop     rbx
0x180039bf9  retn
```
