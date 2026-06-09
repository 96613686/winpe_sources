# FULLSTRICMP

- ea: `0x18000a730`
- end: `0x18000a7b2`
- name: `FULLSTRICMP`
- size: `130`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003db0`
- `0x18000a3a0`
- `0x1800319cc`

## callees

- `0x18000a730`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x18000a7a0`
- `ntdll!RtlCompareUnicodeString` at `0x18000a7a0`

## pseudocode

```c
LONG __fastcall FULLSTRICMP(WCHAR *a1, WCHAR *a2)
{
  __int64 v2; // rax
  __int64 v3; // r8
  UNICODE_STRING String2; // [rsp+20h] [rbp-28h] BYREF
  UNICODE_STRING String1; // [rsp+30h] [rbp-18h] BYREF

  v2 = -1;
  String1 = 0;
  v3 = -1;
  String2 = 0;
  do
    ++v3;
  while ( a1[v3] );
  String1.Buffer = a1;
  String1.MaximumLength = 2 * (v3 + 1);
  String1.Length = String1.MaximumLength;
  do
    ++v2;
  while ( a2[v2] );
  String2.Buffer = a2;
  String2.MaximumLength = 2 * (v2 + 1);
  String2.Length = String2.MaximumLength;
  return RtlCompareUnicodeString(&String1, &String2, 1u);
}

```

## disassembly

```asm
0x18000a730  sub     rsp, 48h
0x18000a734  xorps   xmm0, xmm0
0x18000a737  xorps   xmm1, xmm1
0x18000a73a  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000a741  movups  xmmword ptr [rsp+48h+String1.Length], xmm0
0x18000a746  mov     r8, rax
0x18000a749  movups  xmmword ptr [rsp+48h+String2.Length], xmm1
0x18000a74e  xchg    ax, ax
0x18000a750  inc     r8
0x18000a753  cmp     word ptr [rcx+r8*2], 0
0x18000a759  jnz     short loc_18000A750
0x18000a75b  inc     r8w
0x18000a75f  mov     [rsp+48h+String1.Buffer], rcx
0x18000a764  add     r8w, r8w
0x18000a768  mov     [rsp+48h+String1.MaximumLength], r8w
0x18000a76e  mov     [rsp+48h+String1.Length], r8w
0x18000a774  inc     rax
0x18000a777  cmp     word ptr [rdx+rax*2], 0
0x18000a77c  jnz     short loc_18000A774
0x18000a77e  inc     ax
0x18000a781  mov     [rsp+48h+String2.Buffer], rdx
0x18000a786  add     ax, ax
0x18000a789  lea     rdx, [rsp+48h+String2]; String2
0x18000a78e  mov     r8b, 1; CaseInsensitive
0x18000a791  mov     [rsp+48h+String2.MaximumLength], ax
0x18000a796  lea     rcx, [rsp+48h+String1]; String1
0x18000a79b  mov     [rsp+48h+String2.Length], ax
0x18000a7a0  call    cs:__imp_RtlCompareUnicodeString
0x18000a7a7  nop     dword ptr [rax+rax+00h]
0x18000a7ac  add     rsp, 48h
0x18000a7b0  retn
```
