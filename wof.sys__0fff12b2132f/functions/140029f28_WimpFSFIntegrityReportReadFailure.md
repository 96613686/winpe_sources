# WimpFSFIntegrityReportReadFailure

- ea: `0x140029f28`
- end: `0x14002a037`
- name: `WimpFSFIntegrityReportReadFailure`
- size: `271`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140027fac`
- `0x1400295dc`

## callees

- `0x140011560`
- `0x140029594`
- `0x140029f28`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x140029f68`
- `ntoskrnl!EtwEventEnabled` at `0x140029f68`
- `ntoskrnl!EtwWrite` at `0x14002a008`
- `ntoskrnl!EtwWrite` at `0x14002a008`

## pseudocode

```c
__int64 __fastcall WimpFSFIntegrityReportReadFailure(__int64 a1, __int64 a2, int a3)
{
  __int64 v4; // rdx
  int v5; // ecx
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
  int v17; // [rsp+B0h] [rbp+77h] BYREF

  v17 = a3;
  v8 = a2;
  v7 = 0;
  if ( EtwEventEnabled(g_WimIntegrityEtwEventHandle, &WofIntegrityInvalidBlockEventId)
    && _InterlockedIncrement((volatile signed __int32 *)(a1 + 192)) <= 8 )
  {
    v4 = *(_QWORD *)(a1 + 160);
    v7 = *(_WORD *)(v4 + 88) >> 1;
    UserData.Ptr = (ULONGLONG)&v7;
    *(_QWORD *)&UserData.Size = 2;
    v5 = *(unsigned __int16 *)(v4 + 88);
    v10 = *(_QWORD *)(v4 + 96);
    v13 = &v8;
    v15 = &v17;
    v11 = v5;
    v12 = 0;
    v14 = 8;
    v16 = 4;
    EtwWrite(g_WimIntegrityEtwEventHandle, &WofIntegrityInvalidBlockEventId, 0, 4u, &UserData);
  }
  return WimpFSFBreakForIntegrityFailure();
}

```

## disassembly

```asm
0x140029f28  mov     [rsp-8+arg_18], rbx
0x140029f2d  mov     [rsp-8+arg_10], r8d
0x140029f32  push    rbp
0x140029f33  lea     rbp, [rsp-57h]
0x140029f38  sub     rsp, 90h
0x140029f3f  mov     rax, cs:__security_cookie
0x140029f46  xor     rax, rsp
0x140029f49  mov     [rbp+57h+var_10], rax
0x140029f4d  mov     rbx, rcx
0x140029f50  mov     [rbp+57h+var_58], rdx
0x140029f54  mov     rcx, cs:g_WimIntegrityEtwEventHandle; RegHandle
0x140029f5b  lea     rdx, WofIntegrityInvalidBlockEventId; EventDescriptor
0x140029f62  xor     eax, eax
0x140029f64  mov     [rbp+57h+var_60], ax
0x140029f68  call    cs:__imp_EtwEventEnabled
0x140029f6f  nop     dword ptr [rax+rax+00h]
0x140029f74  test    al, al
0x140029f76  jz      loc_14002A014
0x140029f7c  mov     eax, 1
0x140029f81  lock xadd [rbx+0C0h], eax
0x140029f89  inc     eax
0x140029f8b  cmp     eax, 8
0x140029f8e  jg      loc_14002A014
0x140029f94  mov     rdx, [rbx+0A0h]
0x140029f9b  mov     r9d, 4; UserDataCount
0x140029fa1  xor     r8d, r8d; ActivityId
0x140029fa4  movzx   eax, word ptr [rdx+58h]
0x140029fa8  shr     ax, 1
0x140029fab  mov     [rbp+57h+var_60], ax
0x140029faf  lea     rax, [rbp+57h+var_60]
0x140029fb3  mov     [rbp+57h+var_50.Ptr], rax
0x140029fb7  mov     qword ptr [rbp+57h+var_50.Size], 2
0x140029fbf  mov     rax, [rdx+60h]
0x140029fc3  movzx   ecx, word ptr [rdx+58h]
0x140029fc7  lea     rdx, WofIntegrityInvalidBlockEventId; EventDescriptor
0x140029fce  mov     [rbp+57h+var_40], rax
0x140029fd2  lea     rax, [rbp+57h+var_58]
0x140029fd6  mov     [rbp+57h+var_30], rax
0x140029fda  lea     rax, [rbp+57h+arg_10]
0x140029fde  mov     [rbp+57h+var_20], rax
0x140029fe2  lea     rax, [rbp+57h+var_50]
0x140029fe6  mov     [rbp+57h+var_38], ecx
0x140029fe9  mov     rcx, cs:g_WimIntegrityEtwEventHandle; RegHandle
0x140029ff0  mov     [rsp+90h+UserData], rax; UserData
0x140029ff5  mov     [rbp+57h+var_34], 0
0x140029ffc  mov     [rbp+57h+var_28], 8
0x14002a004  mov     [rbp+57h+var_18], r9
0x14002a008  call    cs:__imp_EtwWrite
0x14002a00f  nop     dword ptr [rax+rax+00h]
0x14002a014  call    WimpFSFBreakForIntegrityFailure
0x14002a019  mov     rcx, [rbp+57h+var_10]
0x14002a01d  xor     rcx, rsp; StackCookie
0x14002a020  call    __security_check_cookie
0x14002a025  mov     rbx, [rsp+90h+arg_18]
0x14002a02d  add     rsp, 90h
0x14002a034  pop     rbp
0x14002a035  retn
```
