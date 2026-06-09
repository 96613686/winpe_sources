# _wsl::util::TryLaunchLiftedWslInstall_::_1_::dtor$5

- ea: `0x18000c264`
- end: `0x18000c270`
- name: `_wsl::util::TryLaunchLiftedWslInstall_::_1_::dtor$5`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180009ddc`

## pseudocode

```c
__int64 __fastcall wsl::util::TryLaunchLiftedWslInstall_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 248);
}

```

## disassembly

```asm
0x18000c264  lea     rcx, [rdx+0F8h]
0x18000c26b  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
