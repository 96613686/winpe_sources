# PFSendExchangeCloseHandlesMessage

- ea: `0x14000aa34`
- end: `0x14000ab30`
- name: `PFSendExchangeCloseHandlesMessage`
- size: `252`
- prototype: `__int64 __fastcall(PFLT_FILTER Filter)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000223c`

## callees

- `0x140002a94`
- `0x140002bb0`
- `0x14000aa34`
- `0x14000b9d8`

## import_xrefs

- `FLTMGR!FltSendMessage` at `0x14000aaf0`
- `FLTMGR!FltSendMessage` at `0x14000aaf0`

## pseudocode

```c
__int64 __fastcall PFSendExchangeCloseHandlesMessage(PFLT_FILTER Filter, __int64 a2, __int64 a3, __int64 a4)
{
  int v7; // eax
  PVOID v8; // rdi
  NTSTATUS v9; // ebx
  ULONG ReplyLength; // [rsp+40h] [rbp-29h] BYREF
  PVOID P; // [rsp+48h] [rbp-21h] BYREF
  __int128 SenderBuffer; // [rsp+50h] [rbp-19h] BYREF
  __int128 v14; // [rsp+60h] [rbp-9h]
  __int128 ReplyBuffer; // [rsp+70h] [rbp+7h] BYREF
  int v16; // [rsp+80h] [rbp+17h]

  P = 0;
  ReplyLength = 20;
  v16 = 0;
  SenderBuffer = 0;
  v14 = 0;
  ReplyBuffer = 0;
  v7 = WMCommListGet(a2 + 24, &P);
  v8 = P;
  v9 = v7;
  if ( v7 >= 0 )
  {
    *(_QWORD *)&SenderBuffer = 0x1000342424242LL;
    *(_QWORD *)&v14 = a3;
    *((_QWORD *)&v14 + 1) = a4;
    *((_QWORD *)&SenderBuffer + 1) = 0x900000020LL;
    v9 = FltSendMessage(Filter, (PFLT_PORT *)P + 5, &SenderBuffer, 0x20u, &ReplyBuffer, &ReplyLength, 0);
    if ( v9 >= 0 )
      v9 = HIDWORD(ReplyBuffer);
  }
  if ( v8 )
    WMCommListEntryRelease(v8);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14000aa34  push    rbp
0x14000aa36  push    rbx
0x14000aa37  push    rsi
0x14000aa38  push    rdi
0x14000aa39  push    r14
0x14000aa3b  push    r15
0x14000aa3d  lea     rbp, [rsp-2Fh]
0x14000aa42  sub     rsp, 98h
0x14000aa49  mov     rax, cs:__security_cookie
0x14000aa50  xor     rax, rsp
0x14000aa53  mov     [rbp+57h+var_38], rax
0x14000aa57  xorps   xmm0, xmm0
0x14000aa5a  mov     [rbp+57h+P], 0
0x14000aa62  mov     rsi, rcx
0x14000aa65  mov     [rbp+57h+var_80], 14h
0x14000aa6c  lea     rcx, [rdx+18h]
0x14000aa70  xor     eax, eax
0x14000aa72  lea     rdx, [rbp+57h+P]
0x14000aa76  mov     [rbp+57h+var_40], eax
0x14000aa79  mov     r15, r9
0x14000aa7c  mov     r14, r8
0x14000aa7f  movups  [rbp+57h+SenderBuffer], xmm0
0x14000aa83  movups  [rbp+57h+var_60], xmm0
0x14000aa87  movups  [rbp+57h+var_50], xmm0
0x14000aa8b  call    WMCommListGet
0x14000aa90  mov     rdi, [rbp+57h+P]
0x14000aa94  mov     ebx, eax
0x14000aa96  test    eax, eax
0x14000aa98  js      short loc_14000AB04
0x14000aa9a  mov     eax, 3
0x14000aa9f  mov     dword ptr [rbp+57h+SenderBuffer+0Ch], 9
0x14000aaa6  mov     word ptr [rbp+57h+SenderBuffer+4], ax
0x14000aaaa  lea     rdx, [rdi+28h]; ClientPort
0x14000aaae  mov     eax, 1
0x14000aab3  mov     [rsp+0C0h+Timeout], 0; Timeout
0x14000aabc  mov     word ptr [rbp+57h+SenderBuffer+6], ax
0x14000aac0  lea     r8, [rbp+57h+SenderBuffer]; SenderBuffer
0x14000aac4  mov     rcx, rsi; Filter
0x14000aac7  mov     dword ptr [rbp+57h+SenderBuffer], 42424242h
0x14000aace  mov     qword ptr [rbp+57h+var_60], r14
0x14000aad2  lea     r9d, [rax+1Fh]; SenderBufferLength
0x14000aad6  mov     qword ptr [rbp+57h+var_60+8], r15
0x14000aada  lea     rax, [rbp+57h+var_80]
0x14000aade  mov     dword ptr [rbp+57h+SenderBuffer+8], r9d
0x14000aae2  mov     [rsp+0C0h+ReplyLength], rax; ReplyLength
0x14000aae7  lea     rax, [rbp+57h+var_50]
0x14000aaeb  mov     [rsp+0C0h+ReplyBuffer], rax; ReplyBuffer
0x14000aaf0  call    cs:__imp_FltSendMessage
0x14000aaf7  nop     dword ptr [rax+rax+00h]
0x14000aafc  test    eax, eax
0x14000aafe  mov     ebx, eax
0x14000ab00  cmovns  ebx, dword ptr [rbp+57h+var_50+0Ch]
0x14000ab04  test    rdi, rdi
0x14000ab07  jz      short loc_14000AB11
0x14000ab09  mov     rcx, rdi; P
0x14000ab0c  call    WMCommListEntryRelease
0x14000ab11  mov     eax, ebx
0x14000ab13  mov     rcx, [rbp+57h+var_38]
0x14000ab17  xor     rcx, rsp; StackCookie
0x14000ab1a  call    __security_check_cookie
0x14000ab1f  add     rsp, 98h
0x14000ab26  pop     r15
0x14000ab28  pop     r14
0x14000ab2a  pop     rdi
0x14000ab2b  pop     rsi
0x14000ab2c  pop     rbx
0x14000ab2d  pop     rbp
0x14000ab2e  retn
```
