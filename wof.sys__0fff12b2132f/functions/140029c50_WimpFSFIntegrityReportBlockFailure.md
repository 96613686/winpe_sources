# WimpFSFIntegrityReportBlockFailure

- ea: `0x140029c50`
- end: `0x140029d59`
- name: `WimpFSFIntegrityReportBlockFailure`
- size: `265`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140027fac`
- `0x140028ef4`

## callees

- `0x140011560`
- `0x140029594`
- `0x140029c50`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x140029c92`
- `ntoskrnl!EtwEventEnabled` at `0x140029c92`
- `ntoskrnl!EtwWrite` at `0x140029d2a`
- `ntoskrnl!EtwWrite` at `0x140029d2a`

## pseudocode

```c
__int64 __fastcall WimpFSFIntegrityReportBlockFailure(__int64 a1, int a2)
{
  __int64 v3; // rdx
  int v4; // ecx
  __int16 v6; // [rsp+30h] [rbp-9h] BYREF
  int v7; // [rsp+34h] [rbp-5h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+40h] [rbp+7h] BYREF
  __int64 v9; // [rsp+50h] [rbp+17h]
  int v10; // [rsp+58h] [rbp+1Fh]
  int v11; // [rsp+5Ch] [rbp+23h]
  int *v12; // [rsp+60h] [rbp+27h]
  __int64 v13; // [rsp+68h] [rbp+2Fh]
  int *v14; // [rsp+70h] [rbp+37h]
  __int64 v15; // [rsp+78h] [rbp+3Fh]
  int v16; // [rsp+A8h] [rbp+6Fh] BYREF

  v16 = a2;
  v7 = 4096;
  v6 = 0;
  if ( EtwEventEnabled(g_WimIntegrityEtwEventHandle, &WofIntegrityBlockVerificationFailureEventId)
    && _InterlockedIncrement((volatile signed __int32 *)(a1 + 188)) <= 16 )
  {
    v3 = *(_QWORD *)(a1 + 160);
    v6 = *(_WORD *)(v3 + 88) >> 1;
    UserData.Ptr = (ULONGLONG)&v6;
    *(_QWORD *)&UserData.Size = 2;
    v4 = *(unsigned __int16 *)(v3 + 88);
    v9 = *(_QWORD *)(v3 + 96);
    v12 = &v16;
    v14 = &v7;
    v10 = v4;
    v11 = 0;
    v13 = 4;
    v15 = 4;
    EtwWrite(g_WimIntegrityEtwEventHandle, &WofIntegrityBlockVerificationFailureEventId, 0, 4u, &UserData);
  }
  return WimpFSFBreakForIntegrityFailure();
}

```

## disassembly

```asm
0x140029c50  mov     [rsp-8+arg_10], rbx
0x140029c55  mov     [rsp-8+arg_8], edx
0x140029c59  push    rbp
0x140029c5a  lea     rbp, [rsp-57h]
0x140029c5f  sub     rsp, 90h
0x140029c66  mov     rax, cs:__security_cookie
0x140029c6d  xor     rax, rsp
0x140029c70  mov     [rbp+57h+var_10], rax
0x140029c74  mov     rbx, rcx
0x140029c77  mov     [rbp+57h+var_5C], 1000h
0x140029c7e  mov     rcx, cs:g_WimIntegrityEtwEventHandle; RegHandle
0x140029c85  lea     rdx, WofIntegrityBlockVerificationFailureEventId; EventDescriptor
0x140029c8c  xor     eax, eax
0x140029c8e  mov     [rbp+57h+var_60], ax
0x140029c92  call    cs:__imp_EtwEventEnabled
0x140029c99  nop     dword ptr [rax+rax+00h]
0x140029c9e  test    al, al
0x140029ca0  jz      loc_140029D36
0x140029ca6  mov     eax, 1
0x140029cab  lock xadd [rbx+0BCh], eax
0x140029cb3  inc     eax
0x140029cb5  cmp     eax, 10h
0x140029cb8  jg      short loc_140029D36
0x140029cba  mov     rdx, [rbx+0A0h]
0x140029cc1  mov     r9d, 4; UserDataCount
0x140029cc7  xor     r8d, r8d; ActivityId
0x140029cca  movzx   eax, word ptr [rdx+58h]
0x140029cce  shr     ax, 1
0x140029cd1  mov     [rbp+57h+var_60], ax
0x140029cd5  lea     rax, [rbp+57h+var_60]
0x140029cd9  mov     [rbp+57h+var_50.Ptr], rax
0x140029cdd  mov     qword ptr [rbp+57h+var_50.Size], 2
0x140029ce5  mov     rax, [rdx+60h]
0x140029ce9  movzx   ecx, word ptr [rdx+58h]
0x140029ced  lea     rdx, WofIntegrityBlockVerificationFailureEventId; EventDescriptor
0x140029cf4  mov     [rbp+57h+var_40], rax
0x140029cf8  lea     rax, [rbp+57h+arg_8]
0x140029cfc  mov     [rbp+57h+var_30], rax
0x140029d00  lea     rax, [rbp+57h+var_5C]
0x140029d04  mov     [rbp+57h+var_20], rax
0x140029d08  lea     rax, [rbp+57h+var_50]
0x140029d0c  mov     [rbp+57h+var_38], ecx
0x140029d0f  mov     rcx, cs:g_WimIntegrityEtwEventHandle; RegHandle
0x140029d16  mov     [rsp+90h+UserData], rax; UserData
0x140029d1b  mov     [rbp+57h+var_34], 0
0x140029d22  mov     [rbp+57h+var_28], r9
0x140029d26  mov     [rbp+57h+var_18], r9
0x140029d2a  call    cs:__imp_EtwWrite
0x140029d31  nop     dword ptr [rax+rax+00h]
0x140029d36  call    WimpFSFBreakForIntegrityFailure
0x140029d3b  mov     rcx, [rbp+57h+var_10]
0x140029d3f  xor     rcx, rsp; StackCookie
0x140029d42  call    __security_check_cookie
0x140029d47  mov     rbx, [rsp+90h+arg_10]
0x140029d4f  add     rsp, 90h
0x140029d56  pop     rbp
0x140029d57  retn
```
