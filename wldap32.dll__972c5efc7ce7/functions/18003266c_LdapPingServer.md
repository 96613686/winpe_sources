# LdapPingServer

- ea: `0x18003266c`
- end: `0x1800327ae`
- name: `LdapPingServer`
- size: `322`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800094a0`

## callees

- `0x18003266c`
- `0x180034510`

## import_xrefs

- `IPHLPAPI!IcmpSendEcho` at `0x1800326f7`
- `IPHLPAPI!IcmpSendEcho` at `0x1800326f7`
- `IPHLPAPI!IcmpCloseHandle` at `0x180032783`
- `IPHLPAPI!IcmpCloseHandle` at `0x180032783`
- `IPHLPAPI!IcmpCreateFile` at `0x1800326ac`
- `IPHLPAPI!IcmpCreateFile` at `0x1800326ac`
- `IPHLPAPI!Icmp6CreateFile` at `0x18003270e`
- `IPHLPAPI!Icmp6CreateFile` at `0x18003270e`
- `IPHLPAPI!Icmp6SendEcho2` at `0x18003276a`
- `IPHLPAPI!Icmp6SendEcho2` at `0x18003276a`

## pseudocode

```c
__int64 __fastcall LdapPingServer(__int64 a1)
{
  DWORD Timeout; // ebp
  unsigned int v2; // ebx
  int v4; // eax
  HANDLE File; // rsi
  IPAddr v6; // edx
  DWORD v7; // eax
  _BYTE RequestData[16]; // [rsp+60h] [rbp-F8h] BYREF
  _BYTE ReplyBuffer[176]; // [rsp+70h] [rbp-E8h] BYREF

  Timeout = *(_DWORD *)(a1 + 492);
  v2 = 0;
  RequestData[0] = 0;
  if ( Timeout )
  {
    v4 = *(_DWORD *)(a1 + 368);
    if ( v4 == 2 )
    {
      File = IcmpCreateFile();
      if ( File == (HANDLE)-1LL )
        return v2;
      v6 = *(_DWORD *)(a1 + 236);
      RequestData[0] = 63;
      v7 = IcmpSendEcho(File, v6, RequestData, 1u, 0, ReplyBuffer, 0xA8u, Timeout);
    }
    else
    {
      if ( v4 != 23 )
        return v2;
      File = Icmp6CreateFile();
      if ( !File )
        return v2;
      v7 = Icmp6SendEcho2(
             File,
             0,
             0,
             0,
             0,
             (struct sockaddr_in6 *)(a1 + 232),
             RequestData,
             1u,
             0,
             ReplyBuffer,
             0xA8u,
             Timeout);
    }
    if ( !v7 )
      v2 = 85;
    IcmpCloseHandle(File);
  }
  return v2;
}

```

## disassembly

```asm
0x18003266c  push    rbx
0x18003266e  push    rbp
0x18003266f  push    rsi
0x180032670  push    rdi
0x180032671  sub     rsp, 138h
0x180032678  mov     rax, cs:__security_cookie
0x18003267f  xor     rax, rsp
0x180032682  mov     [rsp+158h+var_38], rax
0x18003268a  mov     ebp, [rcx+1ECh]
0x180032690  xor     ebx, ebx
0x180032692  mov     [rsp+158h+RequestData], bl
0x180032696  mov     rdi, rcx
0x180032699  test    ebp, ebp
0x18003269b  jz      loc_18003278F
0x1800326a1  mov     eax, [rcx+170h]
0x1800326a7  cmp     eax, 2
0x1800326aa  jnz     short loc_180032705
0x1800326ac  call    cs:__imp_IcmpCreateFile
0x1800326b3  nop     dword ptr [rax+rax+00h]
0x1800326b8  mov     rsi, rax
0x1800326bb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800326bf  jz      loc_18003278F
0x1800326c5  mov     edx, [rdi+0ECh]; DestinationAddress
0x1800326cb  lea     rax, [rsp+158h+var_E8]
0x1800326d0  mov     [rsp+158h+Timeout], ebp; Timeout
0x1800326d4  lea     r9d, [rbx+1]; RequestSize
0x1800326d8  mov     [rsp+158h+ReplySize], 0A8h; ReplySize
0x1800326e0  lea     r8, [rsp+158h+RequestData]; RequestData
0x1800326e5  mov     [rsp+158h+ReplyBuffer], rax; ReplyBuffer
0x1800326ea  mov     rcx, rsi; IcmpHandle
0x1800326ed  mov     [rsp+158h+RequestOptions], rbx; RequestOptions
0x1800326f2  mov     [rsp+158h+RequestData], 3Fh ; '?'
0x1800326f7  call    cs:__imp_IcmpSendEcho
0x1800326fe  nop     dword ptr [rax+rax+00h]
0x180032703  jmp     short loc_180032776
0x180032705  cmp     eax, 17h
0x180032708  jnz     loc_18003278F
0x18003270e  call    cs:__imp_Icmp6CreateFile
0x180032715  nop     dword ptr [rax+rax+00h]
0x18003271a  mov     rsi, rax
0x18003271d  test    rax, rax
0x180032720  jz      short loc_18003278F
0x180032722  mov     [rsp+158h+var_100], ebp; Timeout
0x180032726  lea     rdx, [rsp+158h+var_E8]
0x18003272b  mov     [rsp+158h+var_108], 0A8h; ReplySize
0x180032733  lea     rcx, [rsp+158h+RequestData]
0x180032738  mov     [rsp+158h+var_110], rdx; ReplyBuffer
0x18003273d  lea     rax, [rdi+0E8h]
0x180032744  mov     [rsp+158h+var_118], rbx; RequestOptions
0x180032749  xor     r9d, r9d; ApcContext
0x18003274c  mov     word ptr [rsp+158h+Timeout], 1; RequestSize
0x180032753  xor     r8d, r8d; ApcRoutine
0x180032756  mov     qword ptr [rsp+158h+ReplySize], rcx; RequestData
0x18003275b  xor     edx, edx; Event
0x18003275d  mov     [rsp+158h+ReplyBuffer], rax; DestinationAddress
0x180032762  mov     rcx, rsi; IcmpHandle
0x180032765  mov     [rsp+158h+RequestOptions], rbx; SourceAddress
0x18003276a  call    cs:__imp_Icmp6SendEcho2
0x180032771  nop     dword ptr [rax+rax+00h]
0x180032776  test    eax, eax
0x180032778  mov     ecx, 55h ; 'U'
0x18003277d  cmovz   ebx, ecx
0x180032780  mov     rcx, rsi; IcmpHandle
0x180032783  call    cs:__imp_IcmpCloseHandle
0x18003278a  nop     dword ptr [rax+rax+00h]
0x18003278f  mov     eax, ebx
0x180032791  mov     rcx, [rsp+158h+var_38]
0x180032799  xor     rcx, rsp; StackCookie
0x18003279c  call    __security_check_cookie
0x1800327a1  add     rsp, 138h
0x1800327a8  pop     rdi
0x1800327a9  pop     rsi
0x1800327aa  pop     rbp
0x1800327ab  pop     rbx
0x1800327ac  retn
```
