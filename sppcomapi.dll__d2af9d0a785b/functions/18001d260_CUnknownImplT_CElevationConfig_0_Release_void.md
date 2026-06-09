# CUnknownImplT<CElevationConfig,0>::Release(void)

- ea: `0x18001d260`
- end: `0x18001d29a`
- name: `?Release@?$CUnknownImplT@VCElevationConfig@@$0A@@@UEAAKXZ`
- size: `58`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18001d260`
- `0x18003d010`

## pseudocode

```c
__int64 __fastcall CUnknownImplT<CElevationConfig,0>::Release(volatile signed __int32 *a1)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement(a1 + 40);
  if ( !v1 )
  {
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)a1 + 104LL))(a1, 1);
    _InterlockedDecrement(&CComProcessCounter<0>::g_lServerLockCount);
  }
  return v1;
}

```

## disassembly

```asm
0x18001d260  push    rbx
0x18001d262  sub     rsp, 20h
0x18001d266  or      ebx, 0FFFFFFFFh
0x18001d269  lock xadd [rcx+0A0h], ebx
0x18001d271  sub     ebx, 1
0x18001d274  jnz     short loc_18001D291
0x18001d276  test    rcx, rcx
0x18001d279  jz      short loc_18001D28A
0x18001d27b  mov     rdx, [rcx]
0x18001d27e  mov     rax, [rdx+68h]
0x18001d282  lea     edx, [rbx+1]
0x18001d285  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d28a  lock dec cs:?g_lServerLockCount@?$CComProcessCounter@$0A@@@0JA; long CComProcessCounter<0>::g_lServerLockCount
0x18001d291  mov     eax, ebx
0x18001d293  add     rsp, 20h
0x18001d297  pop     rbx
0x18001d298  retn
```
