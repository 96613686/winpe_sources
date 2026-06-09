# _wsl::util::OpenInstallMutex_::_1_::dtor$0

- ea: `0x18000c1de`
- end: `0x18000c204`
- name: `_wsl::util::OpenInstallMutex_::_1_::dtor$0`
- size: `38`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callees

- `0x1800068c8`
- `0x18000c1de`

## pseudocode

```c
__int64 __fastcall wsl::util::OpenInstallMutex_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 32) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 32) &= ~1u;
    return wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>(*(_QWORD *)(a2 + 64));
  }
  return result;
}

```

## disassembly

```asm
0x18000c1de  push    rbp
0x18000c1e0  sub     rsp, 20h
0x18000c1e4  mov     rbp, rdx
0x18000c1e7  mov     eax, [rbp+20h]
0x18000c1ea  and     eax, 1
0x18000c1ed  test    eax, eax
0x18000c1ef  jz      short loc_18000C1FE
0x18000c1f1  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x18000c1f5  mov     rcx, [rbp+40h]
0x18000c1f9  call    ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ
0x18000c1fe  add     rsp, 20h
0x18000c202  pop     rbp
0x18000c203  retn
```
