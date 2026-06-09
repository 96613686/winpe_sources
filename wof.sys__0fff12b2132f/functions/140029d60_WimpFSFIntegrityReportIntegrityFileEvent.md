# WimpFSFIntegrityReportIntegrityFileEvent

- ea: `0x140029d60`
- end: `0x140029e44`
- name: `WimpFSFIntegrityReportIntegrityFileEvent`
- size: `228`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140028488`
- `0x14002abe8`

## callees

- `0x140011560`
- `0x140029d60`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x140029d9f`
- `ntoskrnl!EtwEventEnabled` at `0x140029d9f`
- `ntoskrnl!EtwWrite` at `0x140029e1a`
- `ntoskrnl!EtwWrite` at `0x140029e1a`

## pseudocode

```c
BOOLEAN __fastcall WimpFSFIntegrityReportIntegrityFileEvent(__int64 a1, int a2, __int64 a3, unsigned __int16 *a4)
{
  BOOLEAN result; // al
  unsigned __int16 v6; // ax
  __int16 v7; // [rsp+30h] [rbp-9h] BYREF
  __int64 v8; // [rsp+38h] [rbp-1h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+40h] [rbp+7h] BYREF
  __int64 v10; // [rsp+50h] [rbp+17h]
  int v11; // [rsp+58h] [rbp+1Fh]
  int v12; // [rsp+5Ch] [rbp+23h]
  __int64 *v13; // [rsp+60h] [rbp+27h]
  __int64 v14; // [rsp+68h] [rbp+2Fh]
  int *v15; // [rsp+70h] [rbp+37h]
  __int64 v16; // [rsp+78h] [rbp+3Fh]
  int v17; // [rsp+A8h] [rbp+6Fh] BYREF

  v17 = a2;
  v8 = a3;
  v7 = 0;
  result = EtwEventEnabled(g_WimIntegrityEtwEventHandle, &WofIntegrityFileOpenFailureEventId);
  if ( result )
  {
    v6 = *a4;
    v11 = *a4;
    v7 = v6 >> 1;
    UserData.Ptr = (ULONGLONG)&v7;
    v10 = *((_QWORD *)a4 + 1);
    v13 = &v8;
    v15 = &v17;
    *(_QWORD *)&UserData.Size = 2;
    v12 = 0;
    v14 = 8;
    v16 = 4;
    return EtwWrite(g_WimIntegrityEtwEventHandle, &WofIntegrityFileOpenFailureEventId, 0, 4u, &UserData);
  }
  return result;
}

```

## disassembly

```asm
0x140029d60  mov     [rsp-8+arg_0], rbx
0x140029d65  mov     [rsp-8+arg_8], edx
0x140029d69  push    rbp
0x140029d6a  lea     rbp, [rsp-57h]
0x140029d6f  sub     rsp, 90h
0x140029d76  mov     rax, cs:__security_cookie
0x140029d7d  xor     rax, rsp
0x140029d80  mov     [rbp+57h+var_10], rax
0x140029d84  mov     rcx, cs:g_WimIntegrityEtwEventHandle; RegHandle
0x140029d8b  lea     rdx, WofIntegrityFileOpenFailureEventId; EventDescriptor
0x140029d92  xor     eax, eax
0x140029d94  mov     [rbp+57h+var_58], r8
0x140029d98  mov     [rbp+57h+var_60], ax
0x140029d9c  mov     rbx, r9
0x140029d9f  call    cs:__imp_EtwEventEnabled
0x140029da6  nop     dword ptr [rax+rax+00h]
0x140029dab  test    al, al
0x140029dad  jz      short loc_140029E26
0x140029daf  movzx   ecx, word ptr [rbx]
0x140029db2  lea     rdx, WofIntegrityFileOpenFailureEventId; EventDescriptor
0x140029db9  movzx   eax, cx
0x140029dbc  mov     [rbp+57h+var_38], ecx
0x140029dbf  mov     rcx, cs:g_WimIntegrityEtwEventHandle; RegHandle
0x140029dc6  mov     r9d, 4; UserDataCount
0x140029dcc  shr     ax, 1
0x140029dcf  xor     r8d, r8d; ActivityId
0x140029dd2  mov     [rbp+57h+var_60], ax
0x140029dd6  lea     rax, [rbp+57h+var_60]
0x140029dda  mov     [rbp+57h+var_50.Ptr], rax
0x140029dde  mov     rax, [rbx+8]
0x140029de2  mov     [rbp+57h+var_40], rax
0x140029de6  lea     rax, [rbp+57h+var_58]
0x140029dea  mov     [rbp+57h+var_30], rax
0x140029dee  lea     rax, [rbp+57h+arg_8]
0x140029df2  mov     [rbp+57h+var_20], rax
0x140029df6  lea     rax, [rbp+57h+var_50]
0x140029dfa  mov     [rsp+90h+UserData], rax; UserData
0x140029dff  mov     qword ptr [rbp+57h+var_50.Size], 2
0x140029e07  mov     [rbp+57h+var_34], 0
0x140029e0e  mov     [rbp+57h+var_28], 8
0x140029e16  mov     [rbp+57h+var_18], r9
0x140029e1a  call    cs:__imp_EtwWrite
0x140029e21  nop     dword ptr [rax+rax+00h]
0x140029e26  mov     rcx, [rbp+57h+var_10]
0x140029e2a  xor     rcx, rsp; StackCookie
0x140029e2d  call    __security_check_cookie
0x140029e32  mov     rbx, [rsp+90h+arg_0]
0x140029e3a  add     rsp, 90h
0x140029e41  pop     rbp
0x140029e42  retn
```
