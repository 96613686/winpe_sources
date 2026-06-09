# _CShellNotification::Create_::_1_::dtor$0

- ea: `0x180017438`
- end: `0x180017444`
- name: `_CShellNotification::Create_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180013ef0`

## pseudocode

```c
__int64 __fastcall CShellNotification::Create_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return utl::unique_lock<utl::recursive_mutex>::~unique_lock<utl::recursive_mutex>(a2 + 96);
}

```

## disassembly

```asm
0x180017438  lea     rcx, [rdx+60h]
0x18001743f  jmp     ??1?$unique_lock@Vrecursive_mutex@utl@@@utl@@QEAA@XZ; utl::unique_lock<utl::recursive_mutex>::~unique_lock<utl::recursive_mutex>(void)
```
