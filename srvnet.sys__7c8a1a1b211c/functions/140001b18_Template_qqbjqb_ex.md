# Template_qqbjqb_ex

- ea: `0x140001b18`
- end: `0x140001bc3`
- name: `Template_qqbjqb_ex`
- size: `171`
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

- `ntoskrnl!EtwWrite` at `0x140001ba1`
- `ntoskrnl!EtwWrite` at `0x140001ba1`

## pseudocode

```c
NTSTATUS __fastcall Template_qqbjqb_ex(REGHANDLE a1, __int64 a2, __int64 a3, const GUID *a4, int a5, __int64 a6)
{
  __int16 v7; // [rsp+30h] [rbp-50h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+48h] [rbp-38h] BYREF
  int *v10; // [rsp+58h] [rbp-28h]
  __int64 v11; // [rsp+60h] [rbp-20h]
  __int64 v12; // [rsp+68h] [rbp-18h]
  int v13; // [rsp+70h] [rbp-10h]
  int v14; // [rsp+74h] [rbp-Ch]

  *(_QWORD *)&EventDescriptor.Id = PacketFragment;
  v14 = 0;
  v7 = -25536;
  *(_QWORD *)&UserData.Size = 2;
  EventDescriptor.Keyword = a3 | 0x1000040000000000LL;
  UserData.Ptr = (ULONGLONG)&v7;
  v11 = 4;
  v10 = &a5;
  v12 = a6;
  v13 = a5;
  return EtwWrite(a1, &EventDescriptor, a4, 3u, &UserData);
}

```

## disassembly

```asm
0x140001b18  push    rbp
0x140001b1a  mov     rbp, rsp
0x140001b1d  sub     rsp, 80h
0x140001b24  mov     rax, cs:__security_cookie
0x140001b2b  xor     rax, rsp
0x140001b2e  mov     [rbp+var_8], rax
0x140001b32  mov     rax, cs:PacketFragment
0x140001b39  xor     edx, edx
0x140001b3b  mov     qword ptr [rbp+EventDescriptor.Id], rax
0x140001b3f  mov     r10, r9
0x140001b42  mov     eax, 9C40h
0x140001b47  mov     [rbp+var_C], edx
0x140001b4a  mov     [rbp+var_50], ax
0x140001b4e  mov     rax, 1000040000000000h
0x140001b58  or      r8, rax
0x140001b5b  mov     qword ptr [rbp+var_38.Size], 2
0x140001b63  lea     rax, [rbp+var_50]
0x140001b67  mov     [rbp+EventDescriptor.Keyword], r8
0x140001b6b  mov     [rbp+var_38.Ptr], rax
0x140001b6f  lea     r9d, [rdx+3]; UserDataCount
0x140001b73  lea     rax, [rbp+arg_20]
0x140001b77  mov     [rbp+var_20], 4
0x140001b7f  mov     [rbp+var_28], rax
0x140001b83  lea     rdx, [rbp+EventDescriptor]; EventDescriptor
0x140001b87  mov     rax, [rbp+arg_28]
0x140001b8b  mov     r8, r10; ActivityId
0x140001b8e  mov     [rbp+var_18], rax
0x140001b92  mov     eax, [rbp+arg_20]
0x140001b95  mov     [rbp+var_10], eax
0x140001b98  lea     rax, [rbp+var_38]
0x140001b9c  mov     [rsp+80h+UserData], rax; UserData
0x140001ba1  call    cs:__imp_EtwWrite
0x140001ba8  nop     dword ptr [rax+rax+00h]
0x140001bad  mov     rcx, [rbp+var_8]
0x140001bb1  xor     rcx, rsp; StackCookie
0x140001bb4  call    __security_check_cookie
0x140001bb9  add     rsp, 80h
0x140001bc0  pop     rbp
0x140001bc1  retn
```
