# ConvertListenerConfigFromUnicodeToAnsi

- ea: `0x18000a30c`
- end: `0x18000a487`
- name: `ConvertListenerConfigFromUnicodeToAnsi`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x18000b230`

## callees

- `0x18000a30c`

## import_xrefs

- `ntdll!RtlUnicodeToMultiByteN` at `0x18000a3df`
- `ntdll!RtlUnicodeToMultiByteN` at `0x18000a402`
- `ntdll!RtlUnicodeToMultiByteN` at `0x18000a425`
- `ntdll!RtlUnicodeToMultiByteN` at `0x18000a449`
- `ntdll!RtlUnicodeToMultiByteN` at `0x18000a46d`
- `ntdll!RtlUnicodeToMultiByteN` at `0x18000a3df`
- `ntdll!RtlUnicodeToMultiByteN` at `0x18000a402`
- `ntdll!RtlUnicodeToMultiByteN` at `0x18000a425`
- `ntdll!RtlUnicodeToMultiByteN` at `0x18000a449`
- `ntdll!RtlUnicodeToMultiByteN` at `0x18000a46d`

## pseudocode

```c
__int64 __fastcall ConvertListenerConfigFromUnicodeToAnsi(__int64 a1, __int64 a2)
{
  if ( !a1 || !a2 )
    return 0;
  *(_DWORD *)a2 = *(_DWORD *)a1;
  *(_DWORD *)(a2 + 4) = *(_DWORD *)(a1 + 4);
  *(_DWORD *)(a2 + 8) = *(_DWORD *)(a1 + 8);
  *(_DWORD *)(a2 + 12) = *(_DWORD *)(a1 + 12);
  *(_DWORD *)(a2 + 16) = *(_DWORD *)(a1 + 16);
  *(_DWORD *)(a2 + 20) = *(_DWORD *)(a1 + 20);
  *(_DWORD *)(a2 + 24) = *(_DWORD *)(a1 + 24);
  *(_DWORD *)(a2 + 28) = *(_DWORD *)(a1 + 28);
  *(_DWORD *)(a2 + 32) = *(_DWORD *)(a1 + 32);
  *(_DWORD *)(a2 + 36) = *(_DWORD *)(a1 + 36);
  *(_DWORD *)(a2 + 40) = *(_DWORD *)(a1 + 40);
  *(_DWORD *)(a2 + 44) = *(_DWORD *)(a1 + 44);
  *(_DWORD *)(a2 + 48) = *(_DWORD *)(a1 + 48);
  *(_DWORD *)(a2 + 52) = *(_DWORD *)(a1 + 52);
  *(_DWORD *)(a2 + 56) = *(_DWORD *)(a1 + 56);
  *(_DWORD *)(a2 + 60) = *(_DWORD *)(a1 + 60);
  *(_DWORD *)(a2 + 64) = *(_DWORD *)(a1 + 64);
  *(_DWORD *)(a2 + 68) = *(_DWORD *)(a1 + 68);
  *(_DWORD *)(a2 + 72) = *(_DWORD *)(a1 + 72);
  *(_DWORD *)(a2 + 76) = *(_DWORD *)(a1 + 76);
  *(_DWORD *)(a2 + 80) = *(_DWORD *)(a1 + 80);
  *(_DWORD *)(a2 + 84) = *(_DWORD *)(a1 + 84);
  *(_DWORD *)(a2 + 88) = *(_DWORD *)(a1 + 88);
  *(_DWORD *)(a2 + 92) = *(_DWORD *)(a1 + 92);
  *(_DWORD *)(a2 + 96) = *(_DWORD *)(a1 + 96);
  *(_DWORD *)(a2 + 100) = *(_DWORD *)(a1 + 100);
  RtlUnicodeToMultiByteN((PCHAR)(a2 + 104), 0x3Du, 0, (PCWCH)(a1 + 104), 0x7Au);
  RtlUnicodeToMultiByteN((PCHAR)(a2 + 165), 0x15u, 0, (PCWCH)(a1 + 226), 0x2Au);
  RtlUnicodeToMultiByteN((PCHAR)(a2 + 186), 0x12u, 0, (PCWCH)(a1 + 268), 0x24u);
  RtlUnicodeToMultiByteN((PCHAR)(a2 + 204), 0x105u, 0, (PCWCH)(a1 + 304), 0x20Au);
  RtlUnicodeToMultiByteN((PCHAR)(a2 + 465), 0x105u, 0, (PCWCH)(a1 + 826), 0x20Au);
  return 1;
}

```

## disassembly

```asm
0x18000a30c  mov     [rsp+arg_0], rbx
0x18000a311  push    rdi
0x18000a312  sub     rsp, 30h
0x18000a316  mov     rbx, rdx
0x18000a319  mov     rdi, rcx
0x18000a31c  test    rcx, rcx
0x18000a31f  jz      loc_18000A47A
0x18000a325  test    rdx, rdx
0x18000a328  jz      loc_18000A47A
0x18000a32e  mov     eax, [rcx]
0x18000a330  lea     r9, [rcx+68h]; UnicodeString
0x18000a334  mov     [rdx], eax
0x18000a336  xor     r8d, r8d; ResultSize
0x18000a339  mov     eax, [rcx+4]
0x18000a33c  mov     [rdx+4], eax
0x18000a33f  mov     eax, [rcx+8]
0x18000a342  mov     [rdx+8], eax
0x18000a345  mov     eax, [rcx+0Ch]
0x18000a348  mov     [rdx+0Ch], eax
0x18000a34b  mov     eax, [rcx+10h]
0x18000a34e  mov     [rdx+10h], eax
0x18000a351  mov     eax, [rcx+14h]
0x18000a354  mov     [rdx+14h], eax
0x18000a357  mov     eax, [rcx+18h]
0x18000a35a  mov     [rdx+18h], eax
0x18000a35d  mov     eax, [rcx+1Ch]
0x18000a360  mov     [rdx+1Ch], eax
0x18000a363  mov     eax, [rcx+20h]
0x18000a366  mov     [rdx+20h], eax
0x18000a369  mov     eax, [rcx+24h]
0x18000a36c  mov     [rdx+24h], eax
0x18000a36f  mov     eax, [rcx+28h]
0x18000a372  mov     [rdx+28h], eax
0x18000a375  mov     eax, [rcx+2Ch]
0x18000a378  mov     [rdx+2Ch], eax
0x18000a37b  mov     eax, [rcx+30h]
0x18000a37e  mov     [rdx+30h], eax
0x18000a381  mov     eax, [rcx+34h]
0x18000a384  mov     [rdx+34h], eax
0x18000a387  mov     eax, [rcx+38h]
0x18000a38a  mov     [rdx+38h], eax
0x18000a38d  mov     eax, [rcx+3Ch]
0x18000a390  mov     [rdx+3Ch], eax
0x18000a393  mov     eax, [rcx+40h]
0x18000a396  mov     [rdx+40h], eax
0x18000a399  mov     eax, [rcx+44h]
0x18000a39c  mov     [rdx+44h], eax
0x18000a39f  mov     eax, [rcx+48h]
0x18000a3a2  mov     [rdx+48h], eax
0x18000a3a5  mov     eax, [rcx+4Ch]
0x18000a3a8  mov     [rdx+4Ch], eax
0x18000a3ab  mov     eax, [rcx+50h]
0x18000a3ae  mov     [rdx+50h], eax
0x18000a3b1  mov     eax, [rcx+54h]
0x18000a3b4  mov     [rdx+54h], eax
0x18000a3b7  mov     eax, [rcx+58h]
0x18000a3ba  mov     [rdx+58h], eax
0x18000a3bd  mov     eax, [rcx+5Ch]
0x18000a3c0  mov     [rdx+5Ch], eax
0x18000a3c3  mov     eax, [rcx+60h]
0x18000a3c6  mov     [rdx+60h], eax
0x18000a3c9  mov     eax, [rcx+64h]
0x18000a3cc  lea     rcx, [rdx+68h]; MbString
0x18000a3d0  mov     [rdx+64h], eax
0x18000a3d3  lea     edx, [r8+3Dh]; MbSize
0x18000a3d7  mov     [rsp+38h+UnicodeSize], 7Ah ; 'z'; UnicodeSize
0x18000a3df  call    cs:__imp_RtlUnicodeToMultiByteN
0x18000a3e5  xor     r8d, r8d; ResultSize
0x18000a3e8  mov     [rsp+38h+UnicodeSize], 2Ah ; '*'; UnicodeSize
0x18000a3f0  lea     r9, [rdi+0E2h]; UnicodeString
0x18000a3f7  lea     rcx, [rbx+0A5h]; MbString
0x18000a3fe  lea     edx, [r8+15h]; MbSize
0x18000a402  call    cs:__imp_RtlUnicodeToMultiByteN
0x18000a408  xor     r8d, r8d; ResultSize
0x18000a40b  mov     [rsp+38h+UnicodeSize], 24h ; '$'; UnicodeSize
0x18000a413  lea     r9, [rdi+10Ch]; UnicodeString
0x18000a41a  lea     rcx, [rbx+0BAh]; MbString
0x18000a421  lea     edx, [r8+12h]; MbSize
0x18000a425  call    cs:__imp_RtlUnicodeToMultiByteN
0x18000a42b  lea     r9, [rdi+130h]; UnicodeString
0x18000a432  mov     [rsp+38h+UnicodeSize], 20Ah; UnicodeSize
0x18000a43a  lea     rcx, [rbx+0CCh]; MbString
0x18000a441  xor     r8d, r8d; ResultSize
0x18000a444  mov     edx, 105h; MbSize
0x18000a449  call    cs:__imp_RtlUnicodeToMultiByteN
0x18000a44f  lea     r9, [rdi+33Ah]; UnicodeString
0x18000a456  mov     [rsp+38h+UnicodeSize], 20Ah; UnicodeSize
0x18000a45e  lea     rcx, [rbx+1D1h]; MbString
0x18000a465  xor     r8d, r8d; ResultSize
0x18000a468  mov     edx, 105h; MbSize
0x18000a46d  call    cs:__imp_RtlUnicodeToMultiByteN
0x18000a473  mov     eax, 1
0x18000a478  jmp     short loc_18000A47C
0x18000a47a  xor     eax, eax
0x18000a47c  mov     rbx, [rsp+38h+arg_0]
0x18000a481  add     rsp, 30h
0x18000a485  pop     rdi
0x18000a486  retn
```
