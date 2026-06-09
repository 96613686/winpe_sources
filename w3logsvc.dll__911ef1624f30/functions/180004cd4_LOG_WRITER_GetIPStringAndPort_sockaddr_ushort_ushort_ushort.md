# LOG_WRITER::GetIPStringAndPort(sockaddr *,ushort *,ushort *,ushort *)

- ea: `0x180004cd4`
- end: `0x180004db6`
- name: `?GetIPStringAndPort@LOG_WRITER@@AEAAJPEAUsockaddr@@PEAG11@Z`
- size: `226`
- prototype: `errno_t __fastcall(LOG_WRITER *this, struct sockaddr *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180002a64`
- `0x180003718`

## callees

- `0x180004cd4`

## import_xrefs

- `msvcrt!_itow_s` at `0x180004d3e`
- `msvcrt!_itow_s` at `0x180004d3e`
- `ntdll!RtlIpv6AddressToStringExW` at `0x180004d8c`
- `ntdll!RtlIpv6AddressToStringExW` at `0x180004d8c`
- `ntdll!RtlIpv4AddressToStringExW` at `0x180004d6d`
- `ntdll!RtlIpv4AddressToStringExW` at `0x180004d6d`
- `WS2_32!__imp_ntohs` at `0x180004d16`
- `WS2_32!__imp_ntohs` at `0x180004d16`

## pseudocode

```c
errno_t __fastcall LOG_WRITER::GetIPStringAndPort(
        LOG_WRITER *this,
        struct sockaddr *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5)
{
  u_short v8; // ax
  errno_t result; // eax
  LONG v10; // eax
  LOG_WRITER *AddressStringLength; // [rsp+40h] [rbp+8h] BYREF

  AddressStringLength = this;
  if ( a2->sa_family == 2 )
  {
    LODWORD(AddressStringLength) = 16;
  }
  else
  {
    if ( a2->sa_family != 23 )
      return -2147024883;
    LODWORD(AddressStringLength) = 60;
  }
  v8 = ntohs(*(_WORD *)a2->sa_data);
  if ( !a4 )
    goto LABEL_15;
  if ( a5 )
    *a5 = v8;
  result = _itow_s(v8, a4, 0xCu, 10);
  if ( result )
  {
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
LABEL_15:
    if ( a3
      && (a2->sa_family != 2
        ? (v10 = RtlIpv6AddressToStringExW(
                   (const struct in6_addr *)&a2->sa_data[6],
                   *(_DWORD *)&a2[1].sa_data[6],
                   0,
                   a3,
                   (PULONG)&AddressStringLength))
        : (v10 = RtlIpv4AddressToStringExW((const struct in_addr *)&a2->sa_data[2], 0, a3, (PULONG)&AddressStringLength)),
          v10) )
    {
      return -2147024809;
    }
    else
    {
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180004cd4  mov     rax, rsp
0x180004cd7  mov     [rax+10h], rbx
0x180004cdb  mov     [rax+18h], rsi
0x180004cdf  mov     [rax+8], rcx
0x180004ce3  push    rdi
0x180004ce4  sub     rsp, 30h
0x180004ce8  cmp     word ptr [rdx], 2
0x180004cec  mov     rsi, r9
0x180004cef  mov     rdi, r8
0x180004cf2  mov     rbx, rdx
0x180004cf5  jnz     short loc_180004D00
0x180004cf7  mov     dword ptr [rax+8], 10h
0x180004cfe  jmp     short loc_180004D12
0x180004d00  cmp     word ptr [rdx], 17h
0x180004d04  jnz     loc_180004DA1
0x180004d0a  mov     dword ptr [rsp+38h+AddressStringLength], 3Ch ; '<'
0x180004d12  movzx   ecx, word ptr [rdx+2]; netshort
0x180004d16  call    cs:__imp_ntohs
0x180004d1c  test    rsi, rsi
0x180004d1f  jz      short loc_180004D54
0x180004d21  mov     rcx, [rsp+38h+arg_20]
0x180004d26  test    rcx, rcx
0x180004d29  jz      short loc_180004D2E
0x180004d2b  mov     [rcx], ax
0x180004d2e  mov     r9d, 0Ah; Radix
0x180004d34  movzx   ecx, ax; Value
0x180004d37  mov     rdx, rsi; Buffer
0x180004d3a  lea     r8d, [r9+2]; BufferCount
0x180004d3e  call    cs:__imp__itow_s
0x180004d44  test    eax, eax
0x180004d46  jz      short loc_180004D54
0x180004d48  jle     short loc_180004DA6
0x180004d4a  movzx   eax, ax
0x180004d4d  or      eax, 80070000h
0x180004d52  jmp     short loc_180004DA6
0x180004d54  test    rdi, rdi
0x180004d57  jz      short loc_180004D9D
0x180004d59  cmp     word ptr [rbx], 2
0x180004d5d  jnz     short loc_180004D75
0x180004d5f  xor     edx, edx; Port
0x180004d61  lea     rcx, [rbx+4]; Address
0x180004d65  lea     r9, [rsp+38h+AddressStringLength]; AddressStringLength
0x180004d6a  mov     r8, rdi; AddressString
0x180004d6d  call    cs:__imp_RtlIpv4AddressToStringExW
0x180004d73  jmp     short loc_180004D92
0x180004d75  mov     edx, [rbx+18h]; ScopeId
0x180004d78  lea     rax, [rsp+38h+AddressStringLength]
0x180004d7d  xor     r8d, r8d; Port
0x180004d80  mov     [rsp+38h+var_18], rax; AddressStringLength
0x180004d85  lea     rcx, [rbx+8]; Address
0x180004d89  mov     r9, rdi; AddressString
0x180004d8c  call    cs:__imp_RtlIpv6AddressToStringExW
0x180004d92  test    eax, eax
0x180004d94  jz      short loc_180004D9D
0x180004d96  mov     eax, 80070057h
0x180004d9b  jmp     short loc_180004DA6
0x180004d9d  xor     eax, eax
0x180004d9f  jmp     short loc_180004DA6
0x180004da1  mov     eax, 8007000Dh
0x180004da6  mov     rbx, [rsp+38h+arg_8]
0x180004dab  mov     rsi, [rsp+38h+arg_10]
0x180004db0  add     rsp, 30h
0x180004db4  pop     rdi
0x180004db5  retn
```
