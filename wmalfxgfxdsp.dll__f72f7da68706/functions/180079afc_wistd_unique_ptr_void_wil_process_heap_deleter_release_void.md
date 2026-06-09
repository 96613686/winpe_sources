# wistd::unique_ptr<void,wil::process_heap_deleter>::release(void)

- ea: `0x180079afc`
- end: `0x180079b07`
- name: `?release@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAPEAXXZ`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180078694`

## pseudocode

```c
__int64 __fastcall wistd::unique_ptr<void,wil::process_heap_deleter>::release(__int64 *a1)
{
  __int64 result; // rax

  result = *a1;
  *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x180079afc  mov     rax, [rcx]
0x180079aff  mov     qword ptr [rcx], 0
0x180079b06  retn
```
