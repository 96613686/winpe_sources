# utl::unique_ptr<IHxHelpPane,tlx::release_delete>::~unique_ptr<IHxHelpPane,tlx::release_delete>(void)

- ea: `0x140004a50`
- end: `0x140004a6e`
- name: `??1?$unique_ptr@UIHxHelpPane@@Urelease_delete@tlx@@@utl@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x14001cd25`
- `0x14001cdfd`
- `0x14001ce8f`
- `0x14001ced7`
- `0x14001cefb`

## callees

- `0x140004a50`
- `0x14001e010`

## pseudocode

```c
__int64 __fastcall utl::unique_ptr<IHxHelpPane,tlx::release_delete>::~unique_ptr<IHxHelpPane,tlx::release_delete>(
        __int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return result;
}

```

## disassembly

```asm
0x140004a50  sub     rsp, 28h
0x140004a54  mov     rcx, [rcx]
0x140004a57  test    rcx, rcx
0x140004a5a  jz      short loc_140004A69
0x140004a5c  mov     rax, [rcx]
0x140004a5f  mov     rax, [rax+10h]
0x140004a63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004a68  nop
0x140004a69  add     rsp, 28h
0x140004a6d  retn
```
