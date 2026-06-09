# ___scrt_acquire_startup_lock

- ea: `0x10003dbe`
- end: `0x10003df2`
- name: `___scrt_acquire_startup_lock`
- size: `52`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x100038db`
- `0x100039eb`

## callees

- `0x10003dbe`
- `0x100044c5`

## pseudocode

```c
char __scrt_acquire_startup_lock()
{
  PVOID StackBase; // edx
  signed __int32 v1; // eax

  if ( __scrt_is_ucrt_dll_in_use() )
  {
    StackBase = NtCurrentTeb()->NtTib.StackBase;
    while ( 1 )
    {
      v1 = _InterlockedCompareExchange(&__scrt_native_startup_lock, (signed __int32)StackBase, 0);
      if ( !v1 )
        break;
      if ( StackBase == (PVOID)v1 )
        return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x10003dbe  mov     edi, edi
0x10003dc0  push    esi
0x10003dc1  call    ___scrt_is_ucrt_dll_in_use
0x10003dc6  test    eax, eax
0x10003dc8  jz      short loc_10003DEA
0x10003dca  mov     eax, large fs:18h
0x10003dd0  mov     esi, offset ___scrt_native_startup_lock
0x10003dd5  mov     edx, [eax+4]
0x10003dd8  jmp     short loc_10003DDE
0x10003dda  cmp     edx, eax
0x10003ddc  jz      short loc_10003DEE
0x10003dde  xor     eax, eax
0x10003de0  mov     ecx, edx
0x10003de2  lock cmpxchg [esi], ecx
0x10003de6  test    eax, eax
0x10003de8  jnz     short loc_10003DDA
0x10003dea  xor     al, al
0x10003dec  pop     esi
0x10003ded  retn
0x10003dee  mov     al, 1
0x10003df0  pop     esi
0x10003df1  retn
```
