# SidToBuffer

- ea: `0x1800d182c`
- end: `0x1800d18f6`
- name: `SidToBuffer`
- size: `202`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001df70`
- `0x1800d1978`

## callees

- `0x180066ec4`
- `0x1800672e4`
- `0x18009aee0`
- `0x18009bb88`
- `0x1800d182c`
- `0x1800d3370`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d18bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d18bb`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800d188d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800d188d`

## pseudocode

```c
__int64 __fastcall SidToBuffer(void *Src, unsigned __int16 a2, __int64 *a3)
{
  unsigned int v3; // ebx
  __int64 v6; // r8
  LPWSTR StringSid; // [rsp+20h] [rbp-88h] BYREF
  _BYTE Sid[80]; // [rsp+30h] [rbp-78h] BYREF

  v3 = a2;
  StringSid = 0;
  if ( a2 > 0x44u )
    return HexBinaryToBuffer((__int64)Src, v3, a3);
  memset_0(Sid, 0, 0x44u);
  memcpy_0(Sid, Src, v3);
  ConvertSidToStringSidW(Sid, &StringSid);
  if ( !StringSid )
    return HexBinaryToBuffer((__int64)Src, v3, a3);
  v6 = -1;
  do
    ++v6;
  while ( StringSid[v6] );
  EmdStringBuffer::AppendWide((EmdStringBuffer *)a3, StringSid, v6 + 1);
  LocalFree(StringSid);
  return 0;
}

```

## disassembly

```asm
0x1800d182c  mov     [rsp+arg_18], rbx
0x1800d1831  push    rbp
0x1800d1832  push    rsi
0x1800d1833  push    rdi
0x1800d1834  sub     rsp, 90h
0x1800d183b  mov     rax, cs:__security_cookie
0x1800d1842  xor     rax, rsp
0x1800d1845  mov     [rsp+0A8h+var_28], rax
0x1800d184d  xor     ebp, ebp
0x1800d184f  movzx   ebx, dx
0x1800d1852  mov     rdi, r8
0x1800d1855  mov     [rsp+0A8h+StringSid], rbp
0x1800d185a  mov     rsi, rcx
0x1800d185d  lea     r8d, [rbp+44h]; Size
0x1800d1861  cmp     bx, r8w
0x1800d1865  ja      short loc_1800D18C5
0x1800d1867  xor     edx, edx; Val
0x1800d1869  lea     rcx, [rsp+0A8h+Sid]; void *
0x1800d186e  call    memset_0
0x1800d1873  mov     r8d, ebx; Size
0x1800d1876  lea     rcx, [rsp+0A8h+Sid]; void *
0x1800d187b  mov     rdx, rsi; Src
0x1800d187e  call    memcpy_0
0x1800d1883  lea     rdx, [rsp+0A8h+StringSid]; StringSid
0x1800d1888  lea     rcx, [rsp+0A8h+Sid]; Sid
0x1800d188d  call    cs:__imp_ConvertSidToStringSidW
0x1800d1893  mov     rdx, [rsp+0A8h+StringSid]; wchar_t *
0x1800d1898  test    rdx, rdx
0x1800d189b  jz      short loc_1800D18C5
0x1800d189d  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800d18a1  inc     r8
0x1800d18a4  cmp     [rdx+r8*2], bp
0x1800d18a9  jnz     short loc_1800D18A1
0x1800d18ab  inc     r8d; unsigned int
0x1800d18ae  mov     rcx, rdi; this
0x1800d18b1  call    ?AppendWide@EmdStringBuffer@@QEAAXPEB_WK@Z; EmdStringBuffer::AppendWide(wchar_t const *,ulong)
0x1800d18b6  mov     rcx, [rsp+0A8h+StringSid]; hMem
0x1800d18bb  call    cs:__imp_LocalFree
0x1800d18c1  xor     eax, eax
0x1800d18c3  jmp     short loc_1800D18D3
0x1800d18c5  mov     r8, rdi
0x1800d18c8  movzx   edx, bx
0x1800d18cb  mov     rcx, rsi
0x1800d18ce  call    HexBinaryToBuffer
0x1800d18d3  mov     rcx, [rsp+0A8h+var_28]
0x1800d18db  xor     rcx, rsp; StackCookie
0x1800d18de  call    __security_check_cookie
0x1800d18e3  mov     rbx, [rsp+0A8h+arg_18]
0x1800d18eb  add     rsp, 90h
0x1800d18f2  pop     rdi
0x1800d18f3  pop     rsi
0x1800d18f4  pop     rbp
0x1800d18f5  retn
```
