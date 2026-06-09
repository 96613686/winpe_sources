# _wsl::util::TryLaunchLiftedWslInstall_::_1_::catch$32

- ea: `0x18000c2e2`
- end: `0x18000c312`
- name: `_wsl::util::TryLaunchLiftedWslInstall_::_1_::catch$32`
- size: `48`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18000a028`

## pseudocode

```c
__int64 __fastcall wsl::util::TryLaunchLiftedWslInstall_::_1_::catch_32(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 576) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 664),
                            (void *)a2,
                            a3,
                            a4);
  return 0;
}

```

## disassembly

```asm
0x18000c2e2  mov     [rsp+arg_8], rdx
0x18000c2e7  push    rbp
0x18000c2e8  sub     rsp, 50h
0x18000c2ec  mov     rbp, rdx
0x18000c2ef  mov     rcx, [rbp+298h]; this
0x18000c2f6  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18000c2fb  mov     [rbp+240h], eax
0x18000c301  mov     rax, 0
0x18000c30b  add     rsp, 50h
0x18000c30f  pop     rbp
0x18000c310  retn
```
