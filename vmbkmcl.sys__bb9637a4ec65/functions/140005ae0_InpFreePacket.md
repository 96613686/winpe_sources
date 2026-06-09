# InpFreePacket

- ea: `0x140005ae0`
- end: `0x140005b54`
- name: `InpFreePacket`
- size: `116`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140004cc0`
- `0x140007f9c`
- `0x1400086b0`
- `0x1400089a8`
- `0x140008c7c`
- `0x14001c34c`

## callees

- `0x140005ae0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140005b18`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005b18`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140005b34`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140005b34`

## pseudocode

```c
void __fastcall InpFreePacket(__int64 a1, __int64 a2)
{
  int v3; // r8d
  _DWORD *v4; // r9
  __int64 v5; // rdx
  __int64 v6; // rdx

  if ( (*(_BYTE *)(a2 + 16) & 1) != 0 )
  {
    if ( a2 != *(_QWORD *)(a1 + 1456) )
    {
LABEL_4:
      ExFreePoolWithTag((PVOID)a2, *(_DWORD *)(a1 + 1644));
      return;
    }
    _InterlockedExchange64((volatile __int64 *)(a1 + 1464), a2);
  }
  else
  {
    v3 = *(_DWORD *)(a2 + 8);
    v4 = *(_DWORD **)(a1 + 1440);
    v5 = (unsigned int)(v3 - 1) >> 10;
    if ( (unsigned int)v5 >= *v4 )
      goto LABEL_4;
    v6 = v5 << 7;
    if ( v3 != *(_DWORD *)((char *)v4 + v6 + 108) )
      goto LABEL_4;
    ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)((char *)v4 + v6 + 64), (PVOID)a2);
  }
}

```

## disassembly

```asm
0x140005ae0  sub     rsp, 28h
0x140005ae4  test    byte ptr [rdx+10h], 1
0x140005ae8  mov     rax, rdx
0x140005aeb  jnz     short loc_140005B42
0x140005aed  mov     r8d, [rdx+8]
0x140005af1  mov     r9, [rcx+5A0h]
0x140005af8  lea     edx, [r8-1]
0x140005afc  shr     edx, 0Ah
0x140005aff  cmp     edx, [r9]
0x140005b02  jnb     short loc_140005B0F
0x140005b04  shl     rdx, 7
0x140005b08  cmp     r8d, [rdx+r9+6Ch]
0x140005b0d  jz      short loc_140005B2A
0x140005b0f  mov     edx, [rcx+66Ch]; Tag
0x140005b15  mov     rcx, rax; P
0x140005b18  call    cs:__imp_ExFreePoolWithTag
0x140005b1f  nop     dword ptr [rax+rax+00h]
0x140005b24  add     rsp, 28h
0x140005b28  retn
0x140005b2a  lea     rcx, [r9+40h]
0x140005b2e  add     rcx, rdx; Lookaside
0x140005b31  mov     rdx, rax; Entry
0x140005b34  call    cs:__imp_ExFreeToNPagedLookasideList
0x140005b3b  nop     dword ptr [rax+rax+00h]
0x140005b40  jmp     short loc_140005B24
0x140005b42  cmp     rax, [rcx+5B0h]
0x140005b49  jnz     short loc_140005B0F
0x140005b4b  xchg    rax, [rcx+5B8h]
0x140005b52  jmp     short loc_140005B24
```
