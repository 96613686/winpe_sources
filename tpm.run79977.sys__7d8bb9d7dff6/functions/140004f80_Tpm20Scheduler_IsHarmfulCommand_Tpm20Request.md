# Tpm20Scheduler::IsHarmfulCommand(Tpm20Request *)

- ea: `0x140004f80`
- end: `0x140005070`
- name: `?IsHarmfulCommand@Tpm20Scheduler@@AEAA_NPEAVTpm20Request@@@Z`
- size: `240`
- prototype: `bool(Tpm20Scheduler *__hidden this, struct Tpm20Request *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000463c`

## callees

- `0x140004f80`
- `0x1400110c0`
- `0x14003a060`

## pseudocode

```c
__int64 __fastcall Tpm20Scheduler::IsHarmfulCommand(Tpm20Scheduler *this, struct Tpm20Request *a2)
{
  unsigned __int8 v2; // bl
  __int64 v3; // rax
  __int64 v5; // r8
  _WORD *v6; // rdx
  char *v7; // rcx

  v2 = 0;
  if ( a2 )
  {
    v3 = *((_QWORD *)this + 17);
    if ( *(_QWORD *)(v3 + 172) == 0x100034E544300LL
      && *(_DWORD *)(v3 + 180) == 1
      && *(_DWORD *)((char *)a2 + 6) == 305
      && Tpm20Request::IsPrimaryHandleOfType(a2, 0x4000000Bu)
      && *(_DWORD *)(v5 + 180) >= 0x3Eu )
    {
      v6 = (_WORD *)(_byteswap_ulong(*(_DWORD *)(*(_QWORD *)(v5 + 24) + 14LL)) + *(_QWORD *)(v5 + 24) + 18LL);
      v7 = (char *)v6 + (unsigned __int16)__ROR2__(*v6, 8);
      if ( __ROR2__(*((_WORD *)v7 + 2), 8) == 35
        && __ROR2__(*((_WORD *)v7 + 3), 8) == 11
        && (_byteswap_ulong(*((_DWORD *)v7 + 2)) & 0x70CF6) == 0x300B2
        && __ROR2__(*((_WORD *)v7 + 6), 8) == 32 )
      {
        return memcmp(v7 + 14, &unk_1400474C0, 0x20u) == 0;
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x140004f80  push    rbx
0x140004f82  sub     rsp, 20h
0x140004f86  xor     bl, bl
0x140004f88  mov     r8, rdx
0x140004f8b  test    rdx, rdx
0x140004f8e  jz      short loc_140004FA3
0x140004f90  mov     rax, [rcx+88h]
0x140004f97  cmp     dword ptr [rax+0ACh], 4E544300h
0x140004fa1  jz      short loc_140004FAD
0x140004fa3  movzx   eax, bl
0x140004fa6  add     rsp, 20h
0x140004faa  pop     rbx
0x140004fab  retn
0x140004fad  cmp     dword ptr [rax+0B0h], 10003h
0x140004fb7  jnz     short loc_140004FA3
0x140004fb9  cmp     dword ptr [rax+0B4h], 1
0x140004fc0  jnz     short loc_140004FA3
0x140004fc2  cmp     dword ptr [rdx+6], 131h
0x140004fc9  jnz     short loc_140004FA3
0x140004fcb  mov     edx, 4000000Bh; unsigned int
0x140004fd0  mov     rcx, r8; this
0x140004fd3  call    ?IsPrimaryHandleOfType@Tpm20Request@@QEAA_NI@Z; Tpm20Request::IsPrimaryHandleOfType(uint)
0x140004fd8  test    al, al
0x140004fda  jz      short loc_140004FA3
0x140004fdc  cmp     dword ptr [r8+0B4h], 3Eh ; '>'
0x140004fe4  jb      short loc_140004FA3
0x140004fe6  mov     rcx, [r8+18h]
0x140004fea  mov     eax, [rcx+0Eh]
0x140004fed  lea     rdx, [rcx+12h]
0x140004ff1  bswap   eax
0x140004ff3  mov     eax, eax
0x140004ff5  add     rdx, rax
0x140004ff8  movzx   eax, word ptr [rdx]
0x140004ffb  ror     ax, 8
0x140004fff  movzx   ecx, ax
0x140005002  add     rcx, rdx
0x140005005  movzx   eax, word ptr [rcx+4]
0x140005009  ror     ax, 8
0x14000500d  cmp     ax, 23h ; '#'
0x140005011  jnz     short loc_140004FA3
0x140005013  movzx   eax, word ptr [rcx+6]
0x140005017  ror     ax, 8
0x14000501b  cmp     ax, 0Bh
0x14000501f  jnz     short loc_140004FA3
0x140005021  mov     eax, [rcx+8]
0x140005024  bswap   eax
0x140005026  and     eax, 70CF6h
0x14000502b  cmp     eax, 300B2h
0x140005030  jnz     loc_140004FA3
0x140005036  movzx   eax, word ptr [rcx+0Ch]
0x14000503a  ror     ax, 8
0x14000503e  cmp     ax, 20h ; ' '
0x140005042  jnz     loc_140004FA3
0x140005048  add     rcx, 0Eh; Buf1
0x14000504c  lea     rdx, unk_1400474C0; Buf2
0x140005053  mov     r8d, 20h ; ' '; Size
0x140005059  call    memcmp
0x14000505e  test    eax, eax
0x140005060  movzx   ebx, bl
0x140005063  mov     ecx, 1
0x140005068  cmovz   ebx, ecx
0x14000506b  jmp     loc_140004FA3
```
