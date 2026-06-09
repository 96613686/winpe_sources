# ConvertListenerConfigFromAnsiToUnicode

- ea: `0x18000a188`
- end: `0x18000a303`
- name: `ConvertListenerConfigFromAnsiToUnicode`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x18000a490`

## callees

- `0x18000a188`

## import_xrefs

- `ntdll!RtlMultiByteToUnicodeN` at `0x18000a25b`
- `ntdll!RtlMultiByteToUnicodeN` at `0x18000a27e`
- `ntdll!RtlMultiByteToUnicodeN` at `0x18000a2a1`
- `ntdll!RtlMultiByteToUnicodeN` at `0x18000a2c5`
- `ntdll!RtlMultiByteToUnicodeN` at `0x18000a2e9`
- `ntdll!RtlMultiByteToUnicodeN` at `0x18000a25b`
- `ntdll!RtlMultiByteToUnicodeN` at `0x18000a27e`
- `ntdll!RtlMultiByteToUnicodeN` at `0x18000a2a1`
- `ntdll!RtlMultiByteToUnicodeN` at `0x18000a2c5`
- `ntdll!RtlMultiByteToUnicodeN` at `0x18000a2e9`

## pseudocode

```c
__int64 __fastcall ConvertListenerConfigFromAnsiToUnicode(__int64 a1, __int64 a2)
{
  if ( !a2 || !a1 )
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
  RtlMultiByteToUnicodeN((PWCH)(a2 + 104), 0x7Au, 0, (const CHAR *)(a1 + 104), 0x3Du);
  RtlMultiByteToUnicodeN((PWCH)(a2 + 226), 0x2Au, 0, (const CHAR *)(a1 + 165), 0x15u);
  RtlMultiByteToUnicodeN((PWCH)(a2 + 268), 0x24u, 0, (const CHAR *)(a1 + 186), 0x12u);
  RtlMultiByteToUnicodeN((PWCH)(a2 + 304), 0x20Au, 0, (const CHAR *)(a1 + 204), 0x105u);
  RtlMultiByteToUnicodeN((PWCH)(a2 + 826), 0x20Au, 0, (const CHAR *)(a1 + 465), 0x105u);
  return 1;
}

```

## disassembly

```asm
0x18000a188  mov     [rsp+arg_0], rbx
0x18000a18d  push    rdi
0x18000a18e  sub     rsp, 30h
0x18000a192  mov     rdi, rdx
0x18000a195  mov     rbx, rcx
0x18000a198  test    rdx, rdx
0x18000a19b  jz      loc_18000A2F6
0x18000a1a1  test    rcx, rcx
0x18000a1a4  jz      loc_18000A2F6
0x18000a1aa  mov     eax, [rcx]
0x18000a1ac  lea     r9, [rcx+68h]; MultiByteString
0x18000a1b0  mov     [rdx], eax
0x18000a1b2  xor     r8d, r8d; BytesInUnicodeString
0x18000a1b5  mov     eax, [rcx+4]
0x18000a1b8  mov     [rdx+4], eax
0x18000a1bb  mov     eax, [rcx+8]
0x18000a1be  mov     [rdx+8], eax
0x18000a1c1  mov     eax, [rcx+0Ch]
0x18000a1c4  mov     [rdx+0Ch], eax
0x18000a1c7  mov     eax, [rcx+10h]
0x18000a1ca  mov     [rdx+10h], eax
0x18000a1cd  mov     eax, [rcx+14h]
0x18000a1d0  mov     [rdx+14h], eax
0x18000a1d3  mov     eax, [rcx+18h]
0x18000a1d6  mov     [rdx+18h], eax
0x18000a1d9  mov     eax, [rcx+1Ch]
0x18000a1dc  mov     [rdx+1Ch], eax
0x18000a1df  mov     eax, [rcx+20h]
0x18000a1e2  mov     [rdx+20h], eax
0x18000a1e5  mov     eax, [rcx+24h]
0x18000a1e8  mov     [rdx+24h], eax
0x18000a1eb  mov     eax, [rcx+28h]
0x18000a1ee  mov     [rdx+28h], eax
0x18000a1f1  mov     eax, [rcx+2Ch]
0x18000a1f4  mov     [rdx+2Ch], eax
0x18000a1f7  mov     eax, [rcx+30h]
0x18000a1fa  mov     [rdx+30h], eax
0x18000a1fd  mov     eax, [rcx+34h]
0x18000a200  mov     [rdx+34h], eax
0x18000a203  mov     eax, [rcx+38h]
0x18000a206  mov     [rdx+38h], eax
0x18000a209  mov     eax, [rcx+3Ch]
0x18000a20c  mov     [rdx+3Ch], eax
0x18000a20f  mov     eax, [rcx+40h]
0x18000a212  mov     [rdx+40h], eax
0x18000a215  mov     eax, [rcx+44h]
0x18000a218  mov     [rdx+44h], eax
0x18000a21b  mov     eax, [rcx+48h]
0x18000a21e  mov     [rdx+48h], eax
0x18000a221  mov     eax, [rcx+4Ch]
0x18000a224  mov     [rdx+4Ch], eax
0x18000a227  mov     eax, [rcx+50h]
0x18000a22a  mov     [rdx+50h], eax
0x18000a22d  mov     eax, [rcx+54h]
0x18000a230  mov     [rdx+54h], eax
0x18000a233  mov     eax, [rcx+58h]
0x18000a236  mov     [rdx+58h], eax
0x18000a239  mov     eax, [rcx+5Ch]
0x18000a23c  mov     [rdx+5Ch], eax
0x18000a23f  mov     eax, [rcx+60h]
0x18000a242  mov     [rdx+60h], eax
0x18000a245  mov     eax, [rcx+64h]
0x18000a248  lea     rcx, [rdx+68h]; UnicodeString
0x18000a24c  mov     [rdx+64h], eax
0x18000a24f  lea     edx, [r8+7Ah]; MaxBytesInUnicodeString
0x18000a253  mov     [rsp+38h+BytesInMultiByteString], 3Dh ; '='; BytesInMultiByteString
0x18000a25b  call    cs:__imp_RtlMultiByteToUnicodeN
0x18000a261  xor     r8d, r8d; BytesInUnicodeString
0x18000a264  mov     [rsp+38h+BytesInMultiByteString], 15h; BytesInMultiByteString
0x18000a26c  lea     r9, [rbx+0A5h]; MultiByteString
0x18000a273  lea     rcx, [rdi+0E2h]; UnicodeString
0x18000a27a  lea     edx, [r8+2Ah]; MaxBytesInUnicodeString
0x18000a27e  call    cs:__imp_RtlMultiByteToUnicodeN
0x18000a284  xor     r8d, r8d; BytesInUnicodeString
0x18000a287  mov     [rsp+38h+BytesInMultiByteString], 12h; BytesInMultiByteString
0x18000a28f  lea     r9, [rbx+0BAh]; MultiByteString
0x18000a296  lea     rcx, [rdi+10Ch]; UnicodeString
0x18000a29d  lea     edx, [r8+24h]; MaxBytesInUnicodeString
0x18000a2a1  call    cs:__imp_RtlMultiByteToUnicodeN
0x18000a2a7  lea     r9, [rbx+0CCh]; MultiByteString
0x18000a2ae  mov     [rsp+38h+BytesInMultiByteString], 105h; BytesInMultiByteString
0x18000a2b6  lea     rcx, [rdi+130h]; UnicodeString
0x18000a2bd  xor     r8d, r8d; BytesInUnicodeString
0x18000a2c0  mov     edx, 20Ah; MaxBytesInUnicodeString
0x18000a2c5  call    cs:__imp_RtlMultiByteToUnicodeN
0x18000a2cb  lea     r9, [rbx+1D1h]; MultiByteString
0x18000a2d2  mov     [rsp+38h+BytesInMultiByteString], 105h; BytesInMultiByteString
0x18000a2da  lea     rcx, [rdi+33Ah]; UnicodeString
0x18000a2e1  xor     r8d, r8d; BytesInUnicodeString
0x18000a2e4  mov     edx, 20Ah; MaxBytesInUnicodeString
0x18000a2e9  call    cs:__imp_RtlMultiByteToUnicodeN
0x18000a2ef  mov     eax, 1
0x18000a2f4  jmp     short loc_18000A2F8
0x18000a2f6  xor     eax, eax
0x18000a2f8  mov     rbx, [rsp+38h+arg_0]
0x18000a2fd  add     rsp, 30h
0x18000a301  pop     rdi
0x18000a302  retn
```
