# SrvLibCheckDesiredAccess

- ea: `0x140056ae8`
- end: `0x140056bd1`
- name: `SrvLibCheckDesiredAccess`
- size: `233`
- prototype: `__int64 __fastcall(int)`
- caller_count: `5`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14004e780`
- `0x14004e7a0`
- `0x14004e7c0`
- `0x14004e7e0`
- `0x14004e800`

## callees

- `0x140009d80`
- `0x14002a3e0`

## import_xrefs

- `ntoskrnl!SeCaptureSubjectContext` at `0x140056b43`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140056b43`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140056ba5`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140056ba5`

## pseudocode

```c
char __fastcall SrvLibCheckDesiredAccess(int a1)
{
  __int64 v3; // [rsp+60h] [rbp+17h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT v4; // [rsp+68h] [rbp+1Fh] BYREF
  __int64 v5; // [rsp+88h] [rbp+3Fh] BYREF
  int v6; // [rsp+90h] [rbp+47h]
  int v7; // [rsp+94h] [rbp+4Bh]

  v3 = 0;
  v5 = 0x12011600120089LL;
  memset(&v4, 0, sizeof(v4));
  v6 = 1179808;
  v7 = 2032127;
  SeCaptureSubjectContext(&v4);
  LOBYTE(a1) = SrvLibSeAccessCheck(
                 (__int64)SrvLibCommonGroupSD,
                 (__int64)&v4,
                 0,
                 a1,
                 0,
                 0,
                 (__int64)&v5,
                 1,
                 (__int64)&v3 + 4,
                 0,
                 (__int64)&v3);
  SeReleaseSubjectContext(&v4);
  return a1;
}

```

## disassembly

```asm
0x140056ae8  mov     [rsp-8+arg_8], rbx
0x140056aed  push    rbp
0x140056aee  lea     rbp, [rsp-57h]
0x140056af3  sub     rsp, 0A0h
0x140056afa  mov     rax, cs:__security_cookie
0x140056b01  xor     rax, rsp
0x140056b04  mov     [rbp+57h+var_8], rax
0x140056b08  xorps   xmm0, xmm0
0x140056b0b  mov     dword ptr [rbp+57h+var_40], 0
0x140056b12  mov     ebx, ecx
0x140056b14  mov     dword ptr [rbp+57h+var_40+4], 0
0x140056b1b  lea     rcx, [rbp+57h+var_38]; SubjectContext
0x140056b1f  mov     dword ptr [rbp+57h+var_18], 120089h
0x140056b26  movups  xmmword ptr [rbp+57h+var_38], xmm0
0x140056b2a  mov     dword ptr [rbp+57h+var_18+4], 120116h
0x140056b31  movups  xmmword ptr [rbp+57h+var_38+10h], xmm0
0x140056b35  mov     [rbp+57h+var_10], 1200A0h
0x140056b3c  mov     [rbp+57h+var_C], 1F01FFh
0x140056b43  call    cs:__imp_SeCaptureSubjectContext
0x140056b4a  nop     dword ptr [rax+rax+00h]
0x140056b4f  mov     rcx, cs:SrvLibCommonGroupSD; int
0x140056b56  lea     rax, [rbp+57h+var_40]
0x140056b5a  mov     [rsp+0A0h+var_50], rax; __int64
0x140056b5f  lea     rdx, [rbp+57h+var_38]; int
0x140056b63  mov     [rsp+0A0h+var_58], 0; void *
0x140056b6c  lea     rax, [rbp+57h+var_40+4]
0x140056b70  mov     [rsp+0A0h+var_60], rax; __int64
0x140056b75  mov     r9d, ebx; int
0x140056b78  mov     [rsp+0A0h+var_68], 1; char
0x140056b7d  lea     rax, [rbp+57h+var_18]
0x140056b81  mov     [rsp+0A0h+var_70], rax; __int64
0x140056b86  xor     r8d, r8d; int
0x140056b89  mov     [rsp+0A0h+var_78], 0; __int64
0x140056b92  mov     [rsp+0A0h+var_80], 0; int
0x140056b9a  call    SrvLibSeAccessCheck
0x140056b9f  lea     rcx, [rbp+57h+var_38]; SubjectContext
0x140056ba3  mov     bl, al
0x140056ba5  call    cs:__imp_SeReleaseSubjectContext
0x140056bac  nop     dword ptr [rax+rax+00h]
0x140056bb1  mov     al, bl
0x140056bb3  mov     rcx, [rbp+57h+var_8]
0x140056bb7  xor     rcx, rsp; StackCookie
0x140056bba  call    __security_check_cookie
0x140056bbf  mov     rbx, [rsp+0A0h+arg_8]
0x140056bc7  add     rsp, 0A0h
0x140056bce  pop     rbp
0x140056bcf  retn
```
