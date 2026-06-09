# _CShellNotification::ReCreate_::_1_::dtor$0

- ea: `0x18001744a`
- end: `0x180017456`
- name: `_CShellNotification::ReCreate_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180013ef0`

## pseudocode

```c
__int64 __fastcall CShellNotification::ReCreate_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return utl::unique_lock<utl::recursive_mutex>::~unique_lock<utl::recursive_mutex>(a2 + 32);
}

```

## disassembly

```asm
0x18001744a  lea     rcx, [rdx+20h]
0x180017451  jmp     ??1?$unique_lock@Vrecursive_mutex@utl@@@utl@@QEAA@XZ; utl::unique_lock<utl::recursive_mutex>::~unique_lock<utl::recursive_mutex>(void)
```
