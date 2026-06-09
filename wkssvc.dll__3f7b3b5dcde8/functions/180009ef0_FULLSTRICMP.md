# FULLSTRICMP

- ea: `0x180009ef0`
- end: `0x180009f6b`
- name: `FULLSTRICMP`
- size: `123`
- prototype: `LONG __fastcall(WCHAR *, WCHAR *)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003b70`
- `0x180009b80`
- `0x18002edfc`

## callees

- `0x180009ef0`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x180009f60`
- `ntdll!RtlCompareUnicodeString` at `0x180009f60`

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
0x180009ef0  sub     rsp, 48h
0x180009ef4  xorps   xmm0, xmm0
0x180009ef7  xorps   xmm1, xmm1
0x180009efa  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180009f01  movups  xmmword ptr [rsp+48h+String1.Length], xmm0
0x180009f06  mov     r8, rax
0x180009f09  movups  xmmword ptr [rsp+48h+String2.Length], xmm1
0x180009f0e  xchg    ax, ax
0x180009f10  inc     r8
0x180009f13  cmp     word ptr [rcx+r8*2], 0
0x180009f19  jnz     short loc_180009F10
0x180009f1b  inc     r8w
0x180009f1f  mov     [rsp+48h+String1.Buffer], rcx
0x180009f24  add     r8w, r8w
0x180009f28  mov     [rsp+48h+String1.MaximumLength], r8w
0x180009f2e  mov     [rsp+48h+String1.Length], r8w
0x180009f34  inc     rax
0x180009f37  cmp     word ptr [rdx+rax*2], 0
0x180009f3c  jnz     short loc_180009F34
0x180009f3e  inc     ax
0x180009f41  mov     [rsp+48h+String2.Buffer], rdx
0x180009f46  add     ax, ax
0x180009f49  lea     rdx, [rsp+48h+String2]; String2
0x180009f4e  mov     r8b, 1; CaseInsensitive
0x180009f51  mov     [rsp+48h+String2.MaximumLength], ax
0x180009f56  lea     rcx, [rsp+48h+String1]; String1
0x180009f5b  mov     [rsp+48h+String2.Length], ax
0x180009f60  call    cs:__imp_RtlCompareUnicodeString
0x180009f66  add     rsp, 48h
0x180009f6a  retn
```
