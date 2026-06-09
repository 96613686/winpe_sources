# PFSendExchangeCloseHandlesMessage

- ea: `0x14000a994`
- end: `0x14000aa90`
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
- `0x14000a994`
- `0x14000b938`

## import_xrefs

- `FLTMGR!FltSendMessage` at `0x14000aa50`
- `FLTMGR!FltSendMessage` at `0x14000aa50`

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
0x14000a994  push    rbp
0x14000a996  push    rbx
0x14000a997  push    rsi
0x14000a998  push    rdi
0x14000a999  push    r14
0x14000a99b  push    r15
0x14000a99d  lea     rbp, [rsp-2Fh]
0x14000a9a2  sub     rsp, 98h
0x14000a9a9  mov     rax, cs:__security_cookie
0x14000a9b0  xor     rax, rsp
0x14000a9b3  mov     [rbp+57h+var_38], rax
0x14000a9b7  xorps   xmm0, xmm0
0x14000a9ba  mov     [rbp+57h+P], 0
0x14000a9c2  mov     rsi, rcx
0x14000a9c5  mov     [rbp+57h+var_80], 14h
0x14000a9cc  lea     rcx, [rdx+18h]
0x14000a9d0  xor     eax, eax
0x14000a9d2  lea     rdx, [rbp+57h+P]
0x14000a9d6  mov     [rbp+57h+var_40], eax
0x14000a9d9  mov     r15, r9
0x14000a9dc  mov     r14, r8
0x14000a9df  movups  [rbp+57h+SenderBuffer], xmm0
0x14000a9e3  movups  [rbp+57h+var_60], xmm0
0x14000a9e7  movups  [rbp+57h+var_50], xmm0
0x14000a9eb  call    WMCommListGet
0x14000a9f0  mov     rdi, [rbp+57h+P]
0x14000a9f4  mov     ebx, eax
0x14000a9f6  test    eax, eax
0x14000a9f8  js      short loc_14000AA64
0x14000a9fa  mov     eax, 3
0x14000a9ff  mov     dword ptr [rbp+57h+SenderBuffer+0Ch], 9
0x14000aa06  mov     word ptr [rbp+57h+SenderBuffer+4], ax
0x14000aa0a  lea     rdx, [rdi+28h]; ClientPort
0x14000aa0e  mov     eax, 1
0x14000aa13  mov     [rsp+0C0h+Timeout], 0; Timeout
0x14000aa1c  mov     word ptr [rbp+57h+SenderBuffer+6], ax
0x14000aa20  lea     r8, [rbp+57h+SenderBuffer]; SenderBuffer
0x14000aa24  mov     rcx, rsi; Filter
0x14000aa27  mov     dword ptr [rbp+57h+SenderBuffer], 42424242h
0x14000aa2e  mov     qword ptr [rbp+57h+var_60], r14
0x14000aa32  lea     r9d, [rax+1Fh]; SenderBufferLength
0x14000aa36  mov     qword ptr [rbp+57h+var_60+8], r15
0x14000aa3a  lea     rax, [rbp+57h+var_80]
0x14000aa3e  mov     dword ptr [rbp+57h+SenderBuffer+8], r9d
0x14000aa42  mov     [rsp+0C0h+ReplyLength], rax; ReplyLength
0x14000aa47  lea     rax, [rbp+57h+var_50]
0x14000aa4b  mov     [rsp+0C0h+ReplyBuffer], rax; ReplyBuffer
0x14000aa50  call    cs:__imp_FltSendMessage
0x14000aa57  nop     dword ptr [rax+rax+00h]
0x14000aa5c  test    eax, eax
0x14000aa5e  mov     ebx, eax
0x14000aa60  cmovns  ebx, dword ptr [rbp+57h+var_50+0Ch]
0x14000aa64  test    rdi, rdi
0x14000aa67  jz      short loc_14000AA71
0x14000aa69  mov     rcx, rdi; P
0x14000aa6c  call    WMCommListEntryRelease
0x14000aa71  mov     eax, ebx
0x14000aa73  mov     rcx, [rbp+57h+var_38]
0x14000aa77  xor     rcx, rsp; StackCookie
0x14000aa7a  call    __security_check_cookie
0x14000aa7f  add     rsp, 98h
0x14000aa86  pop     r15
0x14000aa88  pop     r14
0x14000aa8a  pop     rdi
0x14000aa8b  pop     rsi
0x14000aa8c  pop     rbx
0x14000aa8d  pop     rbp
0x14000aa8e  retn
```
