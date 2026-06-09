# WinNatLibDereferenceSession

- ea: `0x140006b40`
- end: `0x140006b6e`
- name: `WinNatLibDereferenceSession`
- size: `46`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `14`
- callee_count: `2`
- tags: ``

## callers

- `0x1400020e0`
- `0x140004094`
- `0x140006558`
- `0x140006764`
- `0x14000a9d0`
- `0x14000c47c`
- `0x140013a90`
- `0x140015ad8`
- `0x140015d7c`
- `0x14001b58c`
- `0x14001b9ec`
- `0x14001c6f0`
- `0x14001c9c4`
- `0x14001d3d8`

## callees

- `0x140006b40`
- `0x14001b994`

## pseudocode

```c
__int64 __fastcall WinNatLibDereferenceSession(volatile signed __int64 *a1)
{
  signed __int64 v1; // rax
  bool v2; // cc
  __int64 result; // rax

  v1 = _InterlockedExchangeAdd64(a1, 0xFFFFFFFFFFFFFFFFuLL);
  v2 = v1 <= 1;
  result = v1 - 1;
  if ( v2 )
  {
    if ( result )
      __fastfail(0xEu);
    return WinNatLibCleanupSession(a1);
  }
  return result;
}

```

## disassembly

```asm
0x140006b40  sub     rsp, 28h
0x140006b44  or      rax, 0FFFFFFFFFFFFFFFFh
0x140006b48  lock xadd [rcx], rax
0x140006b4d  sub     rax, 1
0x140006b51  jle     short loc_140006B59
0x140006b53  add     rsp, 28h
0x140006b57  retn
0x140006b59  test    rax, rax
0x140006b5c  jz      short loc_140006B67
0x140006b5e  mov     ecx, 0Eh
0x140006b63  int     29h; Win8: RtlFailFast(ecx)
0x140006b65  jmp     short loc_140006B53
0x140006b67  call    WinNatLibCleanupSession
0x140006b6c  jmp     short loc_140006B53
```
