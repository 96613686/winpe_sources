# HUBUCX_ComputeUsb20HardwareLpmParameters

- ea: `0x140025ce8`
- end: `0x140025e89`
- name: `HUBUCX_ComputeUsb20HardwareLpmParameters`
- size: `417`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14001f810`
- `0x140029104`

## callees

- `0x140025ce8`
- `0x140045570`

## pseudocode

```c
char __fastcall HUBUCX_ComputeUsb20HardwareLpmParameters(__int64 a1, __int64 a2)
{
  __int64 v4; // r9
  char v5; // dl
  int v6; // eax
  unsigned int v7; // r8d
  unsigned int v8; // r8d
  unsigned int v9; // r10d
  int v10; // r9d

  v4 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         WdfDriverGlobals->Driver,
         off_14006B2C0);
  if ( (*(_DWORD *)(a1 + 1640) & 2) != 0 )
  {
    *(_DWORD *)(a1 + 2232) = 2;
LABEL_3:
    v5 = 0;
    goto LABEL_25;
  }
  if ( (*(_DWORD *)(a1 + 1652) & 0x20000) != 0 )
  {
    *(_DWORD *)(a1 + 2232) = 3;
    goto LABEL_3;
  }
  if ( (*(_DWORD *)(*(_QWORD *)a1 + 40LL) & 0x10000) != 0 )
  {
    *(_DWORD *)(a1 + 2232) = 4;
    goto LABEL_3;
  }
  if ( (*(_DWORD *)(v4 + 4) & 0x8000) == 0 )
  {
    *(_DWORD *)(a1 + 2232) = 5;
    goto LABEL_3;
  }
  v6 = *(_DWORD *)(a1 + 2448);
  v5 = 1;
  if ( (v6 & 1) == 0 )
  {
    *(_DWORD *)(a1 + 2232) = 6;
    goto LABEL_3;
  }
  if ( (v6 & 2) == 0 )
  {
    *(_DWORD *)(a1 + 2232) = 7;
    goto LABEL_3;
  }
  if ( (*(_DWORD *)(*(_QWORD *)(a1 + 8) + 204LL) & 0x40) == 0 )
  {
    *(_DWORD *)(a1 + 2232) = 8;
    goto LABEL_3;
  }
  *(_DWORD *)(a1 + 2232) = 1;
  *(_DWORD *)(a2 + 60) |= 1u;
  *(_DWORD *)(a2 + 24) |= 0x20u;
  v7 = *(_DWORD *)(a2 + 60) & 0xFFF807FF | (*(unsigned __int8 *)(v4 + 72) << 11);
  *(_DWORD *)(a2 + 60) = v7;
  if ( (*(_DWORD *)(a1 + 1652) & 0x40000) == 0 )
    v7 |= 2u;
  v8 = v7 & 0xFFFFF803 | 0x20;
  *(_DWORD *)(a2 + 60) = v8;
  v9 = *(_DWORD *)(a1 + 2448);
  if ( (v9 & 2) != 0 && (*(_DWORD *)(*(_QWORD *)(a1 + 8) + 204LL) & 0x80u) != 0 )
  {
    if ( (v9 & 4) != 0 )
    {
      v10 = v8 ^ ((unsigned __int8)v8 ^ (unsigned __int8)(v9 >> 1)) & 0x78;
      *(_DWORD *)(a2 + 60) = v10;
    }
    else
    {
      v10 = v8;
    }
    if ( (*(_DWORD *)(a1 + 2448) & 8) != 0 )
      *(_DWORD *)(a2 + 60) = v10 | ((*(_DWORD *)(a1 + 2448) & 0xF00 | 8u) >> 1);
  }
LABEL_25:
  if ( (*(_DWORD *)(a1 + 1464) & 0x800) != 0 )
    *(_DWORD *)(a1 + 2232) = 9;
  return v5;
}

```

## disassembly

```asm
0x140025ce8  mov     [rsp+arg_0], rbx
0x140025ced  push    rdi
0x140025cee  sub     rsp, 20h
0x140025cf2  mov     rax, cs:WdfFunctions_01015
0x140025cf9  mov     rbx, rcx
0x140025cfc  mov     rcx, cs:WdfDriverGlobals
0x140025d03  mov     rdi, rdx
0x140025d06  mov     r8, cs:off_14006B2C0
0x140025d0d  mov     rax, [rax+650h]
0x140025d14  mov     rdx, [rcx]
0x140025d17  call    _guard_dispatch_icall
0x140025d1c  mov     r8d, [rbx+668h]
0x140025d23  mov     r10d, 2
0x140025d29  mov     r9, rax
0x140025d2c  test    r10b, r8b
0x140025d2f  jz      short loc_140025D3F
0x140025d31  mov     [rbx+8B8h], r10d
0x140025d38  xor     dl, dl
0x140025d3a  jmp     loc_140025E65
0x140025d3f  test    dword ptr [rbx+674h], 20000h
0x140025d49  jz      short loc_140025D57
0x140025d4b  mov     dword ptr [rbx+8B8h], 3
0x140025d55  jmp     short loc_140025D38
0x140025d57  mov     rax, [rbx]
0x140025d5a  test    dword ptr [rax+28h], 10000h
0x140025d61  jz      short loc_140025D6F
0x140025d63  mov     dword ptr [rbx+8B8h], 4
0x140025d6d  jmp     short loc_140025D38
0x140025d6f  test    dword ptr [r9+4], 8000h
0x140025d77  jnz     short loc_140025D85
0x140025d79  mov     dword ptr [rbx+8B8h], 5
0x140025d83  jmp     short loc_140025D38
0x140025d85  mov     eax, [rbx+990h]
0x140025d8b  mov     edx, 1
0x140025d90  test    dl, al
0x140025d92  jnz     short loc_140025DA0
0x140025d94  mov     dword ptr [rbx+8B8h], 6
0x140025d9e  jmp     short loc_140025D38
0x140025da0  test    r10b, al
0x140025da3  jnz     short loc_140025DB1
0x140025da5  mov     dword ptr [rbx+8B8h], 7
0x140025daf  jmp     short loc_140025D38
0x140025db1  mov     rax, [rbx+8]
0x140025db5  mov     ecx, [rax+0CCh]
0x140025dbb  test    cl, 40h
0x140025dbe  jnz     short loc_140025DCF
0x140025dc0  mov     dword ptr [rbx+8B8h], 8
0x140025dca  jmp     loc_140025D38
0x140025dcf  mov     [rbx+8B8h], edx
0x140025dd5  or      [rdi+3Ch], edx
0x140025dd8  or      dword ptr [rdi+18h], 20h
0x140025ddc  mov     eax, [rdi+3Ch]
0x140025ddf  movzx   r8d, byte ptr [r9+48h]
0x140025de4  and     eax, 0FFF807FFh
0x140025de9  shl     r8d, 0Bh
0x140025ded  or      r8d, eax
0x140025df0  mov     [rdi+3Ch], r8d
0x140025df4  test    dword ptr [rbx+674h], 40000h
0x140025dfe  jnz     short loc_140025E03
0x140025e00  or      r8d, r10d
0x140025e03  and     r8d, 0FFFFF823h
0x140025e0a  or      r8d, 20h
0x140025e0e  mov     [rdi+3Ch], r8d
0x140025e12  mov     r10d, [rbx+990h]
0x140025e19  mov     r9d, r10d
0x140025e1c  shr     r9d, 1
0x140025e1f  test    dl, r9b
0x140025e22  jz      short loc_140025E65
0x140025e24  mov     rax, [rbx+8]
0x140025e28  mov     ecx, [rax+0CCh]
0x140025e2e  test    cl, cl
0x140025e30  jns     short loc_140025E65
0x140025e32  test    r10b, 4
0x140025e36  jz      short loc_140025E48
0x140025e38  xor     r9d, r8d
0x140025e3b  and     r9d, 78h
0x140025e3f  xor     r9d, r8d
0x140025e42  mov     [rdi+3Ch], r9d
0x140025e46  jmp     short loc_140025E4B
0x140025e48  mov     r9d, r8d
0x140025e4b  mov     eax, [rbx+990h]
0x140025e51  test    al, 8
0x140025e53  jz      short loc_140025E65
0x140025e55  and     eax, 0F00h
0x140025e5a  or      eax, 8
0x140025e5d  shr     eax, 1
0x140025e5f  or      eax, r9d
0x140025e62  mov     [rdi+3Ch], eax
0x140025e65  test    dword ptr [rbx+5B8h], 800h
0x140025e6f  jz      short loc_140025E7B
0x140025e71  mov     dword ptr [rbx+8B8h], 9
0x140025e7b  mov     rbx, [rsp+28h+arg_0]
0x140025e80  mov     al, dl
0x140025e82  add     rsp, 20h
0x140025e86  pop     rdi
0x140025e87  retn
```
