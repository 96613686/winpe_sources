# UXFrameHelpers::HandleLaunch(UXFrameHelpers::UXFrameArgs const &)

- ea: `0x1400574e0`
- end: `0x14005756d`
- name: `?HandleLaunch@UXFrameHelpers@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBUUXFrameArgs@1@@Z`
- size: `141`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x140057e34`

## callees

- `0x1400574e0`
- `0x14005eafc`
- `0x140067010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140057533`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140057533`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14005751e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14005751e`

## string_xrefs

- `0x140057517`: `UXFrame.dll`

## pseudocode

```c
_QWORD *__fastcall UXFrameHelpers::HandleLaunch(_QWORD *a1, __int64 a2)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rdi

  *a1 = 0;
  Library = LoadLibraryExW(L"UXFrame.dll", 0, 0x800u);
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "UXFrameMain");
    if ( ProcAddress )
    {
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        a1,
        0);
      ((void (__fastcall *)(__int64, _QWORD *))ProcAddress)(a2, a1);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1400574e0  mov     rax, rsp
0x1400574e3  mov     [rax+10h], rbx
0x1400574e7  mov     [rax+18h], rsi
0x1400574eb  mov     [rax+8], rcx
0x1400574ef  push    rdi
0x1400574f0  sub     rsp, 30h
0x1400574f4  mov     rsi, rdx
0x1400574f7  mov     rbx, rcx
0x1400574fa  mov     dword ptr [rax-18h], 0
0x140057501  mov     qword ptr [rcx], 0
0x140057508  mov     dword ptr [rax-18h], 1
0x14005750f  xor     edx, edx; hFile
0x140057511  mov     r8d, 800h; dwFlags
0x140057517  lea     rcx, aUxframeDll; "UXFrame.dll"
0x14005751e  call    cs:__imp_LoadLibraryExW
0x140057524  test    rax, rax
0x140057527  jz      short loc_140057559
0x140057529  lea     rdx, aUxframemain; "UXFrameMain"
0x140057530  mov     rcx, rax; hModule
0x140057533  call    cs:__imp_GetProcAddress
0x140057539  mov     rdi, rax
0x14005753c  test    rax, rax
0x14005753f  jz      short loc_140057559
0x140057541  xor     edx, edx
0x140057543  mov     rcx, rbx
0x140057546  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x14005754b  mov     rdx, rbx
0x14005754e  mov     rcx, rsi
0x140057551  mov     rax, rdi
0x140057554  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140057559  mov     rax, rbx
0x14005755c  mov     rbx, [rsp+38h+arg_8]
0x140057561  mov     rsi, [rsp+38h+arg_10]
0x140057566  add     rsp, 30h
0x14005756a  pop     rdi
0x14005756b  retn
```
