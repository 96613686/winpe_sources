# Template_qqbqb_ex

- ea: `0x140001bcc`
- end: `0x140001c94`
- name: `Template_qqbqb_ex`
- size: `200`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400010f0`
- `0x140002a10`

## callees

- `0x14002a3e0`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x140001c72`
- `ntoskrnl!EtwWrite` at `0x140001c72`

## pseudocode

```c
NTSTATUS __fastcall Template_qqbqb_ex(
        REGHANDLE a1,
        __int64 a2,
        __int64 a3,
        const GUID *a4,
        char a5,
        int a6,
        __int64 a7,
        int a8,
        __int64 a9)
{
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+30h] [rbp-41h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+40h] [rbp-31h] BYREF
  int *v12; // [rsp+50h] [rbp-21h]
  __int64 v13; // [rsp+58h] [rbp-19h]
  __int64 v14; // [rsp+60h] [rbp-11h]
  int v15; // [rsp+68h] [rbp-9h]
  int v16; // [rsp+6Ch] [rbp-5h]
  int *v17; // [rsp+70h] [rbp-1h]
  __int64 v18; // [rsp+78h] [rbp+7h]
  __int64 v19; // [rsp+80h] [rbp+Fh]
  int v20; // [rsp+88h] [rbp+17h]
  int v21; // [rsp+8Ch] [rbp+1Bh]

  *(_QWORD *)&EventDescriptor.Id = Packet;
  *(_QWORD *)&UserData.Size = 4;
  v13 = 4;
  EventDescriptor.Keyword = a3 | 0x1000040000000000LL;
  UserData.Ptr = (ULONGLONG)&a5;
  v16 = 0;
  v12 = &a6;
  v14 = a7;
  v15 = a6;
  v17 = &a8;
  v19 = a9;
  v20 = a8;
  v21 = 0;
  v18 = 4;
  return EtwWrite(a1, &EventDescriptor, a4, 5u, &UserData);
}

```

## disassembly

```asm
0x140001bcc  push    rbp
0x140001bce  lea     rbp, [rsp-2Fh]
0x140001bd3  sub     rsp, 0A0h
0x140001bda  mov     rax, cs:__security_cookie
0x140001be1  xor     rax, rsp
0x140001be4  mov     [rbp+2Fh+var_10], rax
0x140001be8  mov     rax, cs:Packet
0x140001bef  lea     rdx, [rbp+2Fh+EventDescriptor]; EventDescriptor
0x140001bf3  mov     qword ptr [rbp+2Fh+EventDescriptor.Id], rax
0x140001bf7  mov     r10, r9
0x140001bfa  mov     rax, 1000040000000000h
0x140001c04  mov     qword ptr [rbp+2Fh+var_60.Size], 4
0x140001c0c  or      r8, rax
0x140001c0f  mov     [rbp+2Fh+var_48], 4
0x140001c17  mov     [rbp+2Fh+EventDescriptor.Keyword], r8
0x140001c1b  lea     rax, [rbp+2Fh+arg_20]
0x140001c1f  mov     [rbp+2Fh+var_60.Ptr], rax
0x140001c23  xor     r8d, r8d
0x140001c26  lea     rax, [rbp+2Fh+arg_28]
0x140001c2a  mov     [rbp+2Fh+var_34], r8d
0x140001c2e  mov     [rbp+2Fh+var_50], rax
0x140001c32  mov     rax, [rbp+2Fh+arg_30]
0x140001c36  mov     [rbp+2Fh+var_40], rax
0x140001c3a  lea     r9d, [r8+5]; UserDataCount
0x140001c3e  mov     eax, [rbp+2Fh+arg_28]
0x140001c41  mov     [rbp+2Fh+var_38], eax
0x140001c44  lea     rax, [rbp+2Fh+arg_38]
0x140001c48  mov     [rbp+2Fh+var_30], rax
0x140001c4c  mov     rax, [rbp+2Fh+arg_40]
0x140001c50  mov     [rbp+2Fh+var_20], rax
0x140001c54  mov     eax, [rbp+2Fh+arg_38]
0x140001c57  mov     [rbp+2Fh+var_18], eax
0x140001c5a  lea     rax, [rbp+2Fh+var_60]
0x140001c5e  mov     [rbp+2Fh+var_14], r8d
0x140001c62  mov     r8, r10; ActivityId
0x140001c65  mov     [rsp+0A0h+UserData], rax; UserData
0x140001c6a  mov     [rbp+2Fh+var_28], 4
0x140001c72  call    cs:__imp_EtwWrite
0x140001c79  nop     dword ptr [rax+rax+00h]
0x140001c7e  mov     rcx, [rbp+2Fh+var_10]
0x140001c82  xor     rcx, rsp; StackCookie
0x140001c85  call    __security_check_cookie
0x140001c8a  add     rsp, 0A0h
0x140001c91  pop     rbp
0x140001c92  retn
```
