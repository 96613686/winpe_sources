# _anonymous_namespace_::IsUntrustedLocation

- ea: `0x180017c18`
- end: `0x180017c8f`
- name: `_anonymous_namespace_::IsUntrustedLocation`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003810`

## callees

- `0x180017c18`

## import_xrefs

- `SHLWAPI!PathIsNetworkPathW` at `0x180017c27`
- `SHLWAPI!PathIsNetworkPathW` at `0x180017c27`
- `SHLWAPI!__imp_ZoneCheckUrlExW` at `0x180017c72`
- `SHLWAPI!__imp_ZoneCheckUrlExW` at `0x180017c72`

## pseudocode

```c
bool __fastcall anonymous_namespace_::IsUntrustedLocation(const WCHAR *a1, __int64 a2)
{
  bool result; // al
  int v4; // [rsp+58h] [rbp+10h] BYREF
  int v5; // [rsp+60h] [rbp+18h] BYREF

  result = (*(_BYTE *)(a2 + 16) & 2) != 0
        && PathIsNetworkPathW(a1)
        && (v4 = 0, v5 = 0, (int)ZoneCheckUrlExW(a1, &v4, 4, &v5, 4, 6162, 4611, 0) >= 0)
        && (v4 & 0xF) != 0;
  return result;
}

```

## disassembly

```asm
0x180017c18  push    rbx
0x180017c1a  sub     rsp, 40h
0x180017c1e  test    byte ptr [rdx+10h], 2
0x180017c22  mov     rbx, rcx
0x180017c25  jz      short loc_180017C87
0x180017c27  call    cs:__imp_PathIsNetworkPathW
0x180017c2d  test    eax, eax
0x180017c2f  jz      short loc_180017C87
0x180017c31  mov     [rsp+48h+var_10], 0
0x180017c3a  lea     r9, [rsp+48h+arg_10]
0x180017c3f  mov     [rsp+48h+var_18], 1203h
0x180017c47  lea     rdx, [rsp+48h+arg_8]
0x180017c4c  mov     r8d, 4
0x180017c52  mov     [rsp+48h+var_20], 1812h
0x180017c5a  mov     rcx, rbx
0x180017c5d  mov     [rsp+48h+var_28], r8d
0x180017c62  mov     [rsp+48h+arg_8], 0
0x180017c6a  mov     [rsp+48h+arg_10], 0
0x180017c72  call    cs:__imp_ZoneCheckUrlExW
0x180017c78  test    eax, eax
0x180017c7a  js      short loc_180017C87
0x180017c7c  mov     eax, [rsp+48h+arg_8]
0x180017c80  test    al, 0Fh
0x180017c82  setnz   al
0x180017c85  jmp     short loc_180017C89
0x180017c87  xor     al, al
0x180017c89  add     rsp, 40h
0x180017c8d  pop     rbx
0x180017c8e  retn
```
