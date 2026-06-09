# utl::unique_ptr<void,werstring_deleter>::~unique_ptr<void,werstring_deleter>(void)

- ea: `0x140004ad0`
- end: `0x140004af1`
- name: `??1?$unique_ptr@XUwerstring_deleter@@@utl@@QEAA@XZ`
- size: `33`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001cc3b`

## callees

- `0x140004ad0`

## import_xrefs

- `wer!WerpDestroyWerString` at `0x140004ae6`
- `wer!WerpDestroyWerString` at `0x140004ae6`

## pseudocode

```c
__int64 __fastcall utl::unique_ptr<void,werstring_deleter>::~unique_ptr<void,werstring_deleter>(__int64 *a1)
{
  __int64 result; // rax
  __int64 v2; // [rsp+30h] [rbp+8h] BYREF

  result = *a1;
  if ( *a1 )
  {
    v2 = *a1;
    return WerpDestroyWerString(&v2);
  }
  return result;
}

```

## disassembly

```asm
0x140004ad0  sub     rsp, 28h
0x140004ad4  mov     rax, [rcx]
0x140004ad7  test    rax, rax
0x140004ada  jz      short loc_140004AEC
0x140004adc  lea     rcx, [rsp+28h+arg_0]
0x140004ae1  mov     [rsp+28h+arg_0], rax
0x140004ae6  call    cs:__imp_WerpDestroyWerString
0x140004aec  add     rsp, 28h
0x140004af0  retn
```
