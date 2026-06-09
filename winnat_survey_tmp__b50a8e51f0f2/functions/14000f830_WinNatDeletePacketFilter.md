# WinNatDeletePacketFilter

- ea: `0x14000f830`
- end: `0x14000f8a6`
- name: `WinNatDeletePacketFilter`
- size: `118`
- prototype: `__int64 __fastcall(_BYTE *P)`
- caller_count: `3`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x14000eb50`
- `0x14000f6e0`
- `0x1400113c0`

## callees

- `0x14000f830`
- `0x14000f99c`
- `0x140011870`
- `0x140019528`

## pseudocode

```c
__int64 __fastcall WinNatDeletePacketFilter(_BYTE *P)
{
  char *v1; // rax
  __int64 v2; // rdx
  char **v4; // rcx
  unsigned int updated; // edi
  __int64 v6; // r8

  P[77] |= 1u;
  v1 = P + 16;
  v2 = *((_QWORD *)P + 2);
  if ( *(_BYTE **)(v2 + 8) != P + 16 || (v4 = (char **)*((_QWORD *)P + 3), *v4 != v1) )
    __fastfail(3u);
  *v4 = (char *)v2;
  *(_QWORD *)(v2 + 8) = v4;
  updated = WinNatUpdateWFPFilters(P, 0);
  if ( *((_WORD *)P + 4) != 2 )
  {
    LOBYTE(v6) = P[76];
    WinNatLibNat64RemoveIpv4Prefix(*(_QWORD *)(*((_QWORD *)P + 10) + 888LL), P + 72, v6);
  }
  WinNatDereferencePacketFilter(P);
  return updated;
}

```

## disassembly

```asm
0x14000f830  mov     [rsp+arg_0], rbx
0x14000f835  push    rdi
0x14000f836  sub     rsp, 20h
0x14000f83a  or      byte ptr [rcx+4Dh], 1
0x14000f83e  lea     rax, [rcx+10h]
0x14000f842  mov     rdx, [rax]
0x14000f845  mov     rbx, rcx
0x14000f848  cmp     [rdx+8], rax
0x14000f84c  jnz     short loc_14000F89F
0x14000f84e  mov     rcx, [rax+8]
0x14000f852  cmp     [rcx], rax
0x14000f855  jnz     short loc_14000F89F
0x14000f857  mov     [rcx], rdx
0x14000f85a  mov     [rdx+8], rcx
0x14000f85e  xor     edx, edx
0x14000f860  mov     rcx, rbx
0x14000f863  call    WinNatUpdateWFPFilters
0x14000f868  cmp     word ptr [rbx+8], 2
0x14000f86d  mov     edi, eax
0x14000f86f  jz      short loc_14000F889
0x14000f871  mov     rcx, [rbx+50h]
0x14000f875  lea     rdx, [rbx+48h]
0x14000f879  mov     r8b, [rbx+4Ch]
0x14000f87d  mov     rcx, [rcx+378h]
0x14000f884  call    WinNatLibNat64RemoveIpv4Prefix
0x14000f889  mov     rcx, rbx; P
0x14000f88c  call    WinNatDereferencePacketFilter
0x14000f891  mov     rbx, [rsp+28h+arg_0]
0x14000f896  mov     eax, edi
0x14000f898  add     rsp, 20h
0x14000f89c  pop     rdi
0x14000f89d  retn
0x14000f89f  mov     ecx, 3
0x14000f8a4  int     29h; Win8: RtlFailFast(ecx)
```
