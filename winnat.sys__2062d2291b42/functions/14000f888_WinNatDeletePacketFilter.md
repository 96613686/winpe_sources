# WinNatDeletePacketFilter

- ea: `0x14000f888`
- end: `0x14000f8fe`
- name: `WinNatDeletePacketFilter`
- size: `118`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `3`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x14000eb80`
- `0x14000f738`
- `0x140011420`

## callees

- `0x14000f888`
- `0x14000f9f4`
- `0x1400118d0`
- `0x140019a08`

## pseudocode

```c
__int64 __fastcall WinNatDeletePacketFilter(char *P)
{
  char *v1; // rax
  __int64 v2; // rdx
  char **v4; // rcx
  unsigned int updated; // edi

  P[77] |= 1u;
  v1 = P + 16;
  v2 = *((_QWORD *)P + 2);
  if ( *(char **)(v2 + 8) != P + 16 || (v4 = (char **)*((_QWORD *)P + 3), *v4 != v1) )
    __fastfail(3u);
  *v4 = (char *)v2;
  *(_QWORD *)(v2 + 8) = v4;
  updated = WinNatUpdateWFPFilters((__int64)P, 0);
  if ( *((_WORD *)P + 4) != 2 )
    WinNatLibNat64RemoveIpv4Prefix(*(_QWORD *)(*((_QWORD *)P + 10) + 888LL), (__int64)(P + 72), P[76]);
  WinNatDereferencePacketFilter(P);
  return updated;
}

```

## disassembly

```asm
0x14000f888  mov     [rsp+arg_0], rbx
0x14000f88d  push    rdi
0x14000f88e  sub     rsp, 20h
0x14000f892  or      byte ptr [rcx+4Dh], 1
0x14000f896  lea     rax, [rcx+10h]
0x14000f89a  mov     rdx, [rax]
0x14000f89d  mov     rbx, rcx
0x14000f8a0  cmp     [rdx+8], rax
0x14000f8a4  jnz     short loc_14000F8F7
0x14000f8a6  mov     rcx, [rax+8]
0x14000f8aa  cmp     [rcx], rax
0x14000f8ad  jnz     short loc_14000F8F7
0x14000f8af  mov     [rcx], rdx
0x14000f8b2  mov     [rdx+8], rcx
0x14000f8b6  xor     edx, edx
0x14000f8b8  mov     rcx, rbx
0x14000f8bb  call    WinNatUpdateWFPFilters
0x14000f8c0  cmp     word ptr [rbx+8], 2
0x14000f8c5  mov     edi, eax
0x14000f8c7  jz      short loc_14000F8E1
0x14000f8c9  mov     rcx, [rbx+50h]
0x14000f8cd  lea     rdx, [rbx+48h]
0x14000f8d1  mov     r8b, [rbx+4Ch]
0x14000f8d5  mov     rcx, [rcx+378h]
0x14000f8dc  call    WinNatLibNat64RemoveIpv4Prefix
0x14000f8e1  mov     rcx, rbx; P
0x14000f8e4  call    WinNatDereferencePacketFilter
0x14000f8e9  mov     rbx, [rsp+28h+arg_0]
0x14000f8ee  mov     eax, edi
0x14000f8f0  add     rsp, 20h
0x14000f8f4  pop     rdi
0x14000f8f5  retn
0x14000f8f7  mov     ecx, 3
0x14000f8fc  int     29h; Win8: RtlFailFast(ecx)
```
