# LOG_WRITER::AppendIPStringFromSockAddr(sockaddr *,STRU *)

- ea: `0x180002a64`
- end: `0x180002b0e`
- name: `?AppendIPStringFromSockAddr@LOG_WRITER@@AEAAJPEAUsockaddr@@PEAVSTRU@@@Z`
- size: `170`
- prototype: `int __fastcall(LOG_WRITER *this, struct sockaddr *, struct STRU *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180003718`

## callees

- `0x180002a64`
- `0x180004cd4`
- `0x18000e97a`
- `0x18000e9a0`

## import_xrefs

- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002ad3`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002ae7`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002ad3`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002ae7`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180002ac6`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180002ac6`

## pseudocode

```c
int __fastcall LOG_WRITER::AppendIPStringFromSockAddr(LOG_WRITER *this, struct sockaddr *a2, struct STRU *a3)
{
  LOG_WRITER *v5; // rcx
  int result; // eax
  unsigned __int16 v7[64]; // [rsp+30h] [rbp-98h] BYREF

  memset_0(v7, 0, 0x78u);
  if ( LOG_WRITER::GetIPStringAndPort(v5, a2, v7, 0, 0) < 0 )
    return STRU::Append(a3, L"- ", 2u);
  result = STRU::Append(a3, v7);
  if ( result >= 0 )
    return STRU::Append(a3, L" ");
  return result;
}

```

## disassembly

```asm
0x180002a64  mov     [rsp+arg_0], rbx
0x180002a69  push    rdi
0x180002a6a  sub     rsp, 0C0h
0x180002a71  mov     rax, cs:__security_cookie
0x180002a78  xor     rax, rsp
0x180002a7b  mov     [rsp+0C8h+var_18], rax
0x180002a83  mov     rbx, rdx
0x180002a86  lea     rcx, [rsp+0C8h+var_98]; void *
0x180002a8b  xor     edx, edx; Val
0x180002a8d  mov     rdi, r8
0x180002a90  lea     r8d, [rdx+78h]; Size
0x180002a94  call    memset_0
0x180002a99  xor     r9d, r9d; unsigned __int16 *
0x180002a9c  mov     [rsp+0C8h+var_A8], 0; unsigned __int16 *
0x180002aa5  lea     r8, [rsp+0C8h+var_98]; unsigned __int16 *
0x180002aaa  mov     rdx, rbx; struct sockaddr *
0x180002aad  call    ?GetIPStringAndPort@LOG_WRITER@@AEAAJPEAUsockaddr@@PEAG11@Z; LOG_WRITER::GetIPStringAndPort(sockaddr *,ushort *,ushort *,ushort *)
0x180002ab2  mov     rcx, rdi
0x180002ab5  test    eax, eax
0x180002ab7  jns     short loc_180002ACE
0x180002ab9  mov     r8d, 2
0x180002abf  lea     rdx, asc_180012130; "- "
0x180002ac6  call    cs:__imp_?Append@STRU@@QEAAJPEBGK@Z; STRU::Append(ushort const *,ulong)
0x180002acc  jmp     short loc_180002AED
0x180002ace  lea     rdx, [rsp+0C8h+var_98]
0x180002ad3  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180002ad9  test    eax, eax
0x180002adb  js      short loc_180002AED
0x180002add  lea     rdx, asc_180012138; " "
0x180002ae4  mov     rcx, rdi
0x180002ae7  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180002aed  mov     rcx, [rsp+0C8h+var_18]
0x180002af5  xor     rcx, rsp; StackCookie
0x180002af8  call    __security_check_cookie
0x180002afd  mov     rbx, [rsp+0C8h+arg_0]
0x180002b05  add     rsp, 0C0h
0x180002b0c  pop     rdi
0x180002b0d  retn
```
