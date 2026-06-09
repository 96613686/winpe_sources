# WimpFSFIntegrityReportIntegrityFileEventWithoutStatus

- ea: `0x140029e4c`
- end: `0x140029f22`
- name: `WimpFSFIntegrityReportIntegrityFileEventWithoutStatus`
- size: `214`
- prototype: `__int64 __fastcall(PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140028488`

## callees

- `0x140011560`
- `0x140029e4c`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x140029e89`
- `ntoskrnl!EtwEventEnabled` at `0x140029e89`
- `ntoskrnl!EtwWrite` at `0x140029ef4`
- `ntoskrnl!EtwWrite` at `0x140029ef4`

## pseudocode

```c
BOOLEAN __fastcall WimpFSFIntegrityReportIntegrityFileEventWithoutStatus(
        PCEVENT_DESCRIPTOR EventDescriptor,
        __int64 a2,
        unsigned __int16 *a3)
{
  BOOLEAN result; // al
  unsigned __int16 v6; // ax
  __int16 v7; // [rsp+30h] [rbp-50h] BYREF
  __int64 v8; // [rsp+38h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+40h] [rbp-40h] BYREF
  __int64 v10; // [rsp+50h] [rbp-30h]
  int v11; // [rsp+58h] [rbp-28h]
  int v12; // [rsp+5Ch] [rbp-24h]
  __int64 *v13; // [rsp+60h] [rbp-20h]
  __int64 v14; // [rsp+68h] [rbp-18h]

  v8 = a2;
  v7 = 0;
  result = EtwEventEnabled(g_WimIntegrityEtwEventHandle, EventDescriptor);
  if ( result )
  {
    v6 = *a3;
    v11 = *a3;
    v7 = v6 >> 1;
    UserData.Ptr = (ULONGLONG)&v7;
    v10 = *((_QWORD *)a3 + 1);
    v13 = &v8;
    *(_QWORD *)&UserData.Size = 2;
    v12 = 0;
    v14 = 8;
    return EtwWrite(g_WimIntegrityEtwEventHandle, EventDescriptor, 0, 3u, &UserData);
  }
  return result;
}

```

## disassembly

```asm
0x140029e4c  mov     [rsp-8+arg_10], rbx
0x140029e51  mov     [rsp-8+arg_18], rdi
0x140029e56  push    rbp
0x140029e57  mov     rbp, rsp
0x140029e5a  sub     rsp, 80h
0x140029e61  mov     rax, cs:__security_cookie
0x140029e68  xor     rax, rsp
0x140029e6b  mov     [rbp+var_10], rax
0x140029e6f  mov     [rbp+var_48], rdx
0x140029e73  mov     rdi, rcx
0x140029e76  mov     rdx, rcx; EventDescriptor
0x140029e79  xor     eax, eax
0x140029e7b  mov     rcx, cs:g_WimIntegrityEtwEventHandle; RegHandle
0x140029e82  mov     rbx, r8
0x140029e85  mov     [rbp+var_50], ax
0x140029e89  call    cs:__imp_EtwEventEnabled
0x140029e90  nop     dword ptr [rax+rax+00h]
0x140029e95  test    al, al
0x140029e97  jz      short loc_140029F00
0x140029e99  movzx   ecx, word ptr [rbx]
0x140029e9c  mov     r9d, 3; UserDataCount
0x140029ea2  movzx   eax, cx
0x140029ea5  mov     [rbp+var_28], ecx
0x140029ea8  mov     rcx, cs:g_WimIntegrityEtwEventHandle; RegHandle
0x140029eaf  xor     r8d, r8d; ActivityId
0x140029eb2  shr     ax, 1
0x140029eb5  mov     rdx, rdi; EventDescriptor
0x140029eb8  mov     [rbp+var_50], ax
0x140029ebc  lea     rax, [rbp+var_50]
0x140029ec0  mov     [rbp+var_40.Ptr], rax
0x140029ec4  mov     rax, [rbx+8]
0x140029ec8  mov     [rbp+var_30], rax
0x140029ecc  lea     rax, [rbp+var_48]
0x140029ed0  mov     [rbp+var_20], rax
0x140029ed4  lea     rax, [rbp+var_40]
0x140029ed8  mov     [rsp+80h+UserData], rax; UserData
0x140029edd  mov     qword ptr [rbp+var_40.Size], 2
0x140029ee5  mov     [rbp+var_24], 0
0x140029eec  mov     [rbp+var_18], 8
0x140029ef4  call    cs:__imp_EtwWrite
0x140029efb  nop     dword ptr [rax+rax+00h]
0x140029f00  mov     rcx, [rbp+var_10]
0x140029f04  xor     rcx, rsp; StackCookie
0x140029f07  call    __security_check_cookie
0x140029f0c  lea     r11, [rsp+80h+var_s0]
0x140029f14  mov     rbx, [r11+20h]
0x140029f18  mov     rdi, [r11+28h]
0x140029f1c  mov     rsp, r11
0x140029f1f  pop     rbp
0x140029f20  retn
```
