# _wsl::util::TryLaunchLiftedWslInstall_::_1_::dtor$3

- ea: `0x18000c240`
- end: `0x18000c24c`
- name: `_wsl::util::TryLaunchLiftedWslInstall_::_1_::dtor$3`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180009ddc`

## pseudocode

```c
__int64 __fastcall wsl::util::TryLaunchLiftedWslInstall_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 312);
}

```

## disassembly

```asm
0x18000c240  lea     rcx, [rdx+138h]
0x18000c247  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
