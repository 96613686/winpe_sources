# GetProtocolEntry

- ea: `0x18001b548`
- end: `0x18001b580`
- name: `GetProtocolEntry`
- size: `56`
- prototype: ``
- caller_count: `16`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180011850`
- `0x180012800`
- `0x180014200`
- `0x180014580`
- `0x1800176bc`
- `0x180017a44`
- `0x180019094`
- `0x18001928c`
- `0x18001958c`
- `0x180019a1c`
- `0x180019de0`
- `0x18001aa4c`
- `0x18001ad04`
- `0x18001be6c`
- `0x18001c790`
- `0x18001d908`

## callees

- `0x18001b548`

## pseudocode

```c
__int64 __fastcall GetProtocolEntry(_QWORD *a1, int a2, int a3)
{
  _QWORD *v3; // rax
  int v4; // r9d
  unsigned __int64 v5; // r10

  v3 = (_QWORD *)*a1;
  v4 = 0;
  if ( (_QWORD *)*a1 == a1 )
  {
    v5 = 0;
  }
  else
  {
    while ( 1 )
    {
      v5 = (unsigned __int64)v3;
      if ( *((_DWORD *)v3 + 4) == a2 && *((_DWORD *)v3 + 5) == a3 )
        break;
      v3 = (_QWORD *)*v3;
      if ( v3 == a1 )
        return v5 & -(__int64)(v4 != 0);
    }
    v4 = 1;
  }
  return v5 & -(__int64)(v4 != 0);
}

```

## disassembly

```asm
0x18001b548  mov     rax, [rcx]
0x18001b54b  xor     r9d, r9d
0x18001b54e  cmp     rax, rcx
0x18001b551  jz      short loc_18001B573
0x18001b553  mov     r10, rax
0x18001b556  cmp     [rax+10h], edx
0x18001b559  jnz     short loc_18001B561
0x18001b55b  cmp     [rax+14h], r8d
0x18001b55f  jz      short loc_18001B56B
0x18001b561  mov     rax, [rax]
0x18001b564  cmp     rax, rcx
0x18001b567  jnz     short loc_18001B553
0x18001b569  jmp     short loc_18001B576
0x18001b56b  mov     r9d, 1
0x18001b571  jmp     short loc_18001B576
0x18001b573  xor     r10d, r10d
0x18001b576  neg     r9d
0x18001b579  sbb     rax, rax
0x18001b57c  and     rax, r10
0x18001b57f  retn
```
