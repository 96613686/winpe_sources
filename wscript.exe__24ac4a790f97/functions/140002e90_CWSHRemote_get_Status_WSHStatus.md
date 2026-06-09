# CWSHRemote::get_Status(WSHStatus *)

- ea: `0x140002e90`
- end: `0x140002ee2`
- name: `?get_Status@CWSHRemote@@UEAAJPEAW4WSHStatus@@@Z`
- size: `82`
- prototype: `__int64 __fastcall(CWSHRemote *__hidden this, enum WSHStatus *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140002e90`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140002ea8`
- `KERNEL32!GetCurrentThreadId` at `0x140002ea8`

## pseudocode

```c
__int64 __fastcall CWSHRemote::get_Status(CWSHRemote *this, enum WSHStatus *a2)
{
  int v2; // ebx

  v2 = *((_DWORD *)this + 10);
  if ( GetCurrentThreadId() != v2 )
    return 2147549183LL;
  if ( !a2 )
    return 2147500035LL;
  *(_DWORD *)a2 = _InterlockedCompareExchange((volatile signed __int32 *)this + 11, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x140002e90  mov     [rsp+arg_0], rbx
0x140002e95  mov     [rsp+arg_8], rsi
0x140002e9a  push    rdi
0x140002e9b  sub     rsp, 20h
0x140002e9f  mov     ebx, [rcx+28h]
0x140002ea2  mov     rdi, rdx
0x140002ea5  mov     rsi, rcx
0x140002ea8  call    cs:__imp_GetCurrentThreadId
0x140002eae  cmp     eax, ebx
0x140002eb0  jz      short loc_140002EB9
0x140002eb2  mov     eax, 8000FFFFh
0x140002eb7  jmp     short loc_140002ED2
0x140002eb9  test    rdi, rdi
0x140002ebc  jnz     short loc_140002EC5
0x140002ebe  mov     eax, 80004003h
0x140002ec3  jmp     short loc_140002ED2
0x140002ec5  xor     ecx, ecx
0x140002ec7  xor     eax, eax
0x140002ec9  lock cmpxchg [rsi+2Ch], ecx
0x140002ece  mov     [rdi], eax
0x140002ed0  xor     eax, eax
0x140002ed2  mov     rbx, [rsp+28h+arg_0]
0x140002ed7  mov     rsi, [rsp+28h+arg_8]
0x140002edc  add     rsp, 20h
0x140002ee0  pop     rdi
0x140002ee1  retn
```
