# BalanceUpdateDeviceMode

- ea: `0x140005a74`
- end: `0x140005aa3`
- name: `BalanceUpdateDeviceMode`
- size: `47`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140003650`
- `0x140006188`

## callees

- `0x1400049b0`
- `0x140005a74`

## pseudocode

```c
__int64 __fastcall BalanceUpdateDeviceMode(__int64 a1)
{
  __int64 result; // rax
  __int64 v2; // rdx

  result = *(unsigned int *)(a1 + 916);
  if ( *(_DWORD *)(a1 + 924) )
  {
    if ( (_DWORD)result )
      return result;
    v2 = 0;
  }
  else
  {
    if ( !(_DWORD)result )
      return result;
    v2 = 1;
  }
  return BalanceSetDeviceMode(a1, v2);
}

```

## disassembly

```asm
0x140005a74  sub     rsp, 28h
0x140005a78  cmp     dword ptr [rcx+39Ch], 0
0x140005a7f  mov     eax, [rcx+394h]
0x140005a85  jnz     short loc_140005A92
0x140005a87  test    eax, eax
0x140005a89  jz      short loc_140005A9D
0x140005a8b  mov     edx, 1
0x140005a90  jmp     short loc_140005A98
0x140005a92  test    eax, eax
0x140005a94  jnz     short loc_140005A9D
0x140005a96  xor     edx, edx
0x140005a98  call    BalanceSetDeviceMode
0x140005a9d  add     rsp, 28h
0x140005aa1  retn
```
