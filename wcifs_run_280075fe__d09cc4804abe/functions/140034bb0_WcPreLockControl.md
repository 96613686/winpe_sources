# WcPreLockControl

- ea: `0x140034bb0`
- end: `0x140034dd5`
- name: `WcPreLockControl`
- size: `549`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x140001500`
- `0x140002264`
- `0x140004198`
- `0x140007c60`
- `0x140023840`
- `0x140034bb0`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140034d06`
- `ntoskrnl!EtwWriteTransfer` at `0x140034d06`
- `FLTMGR!FltReleaseContext` at `0x140034d95`
- `FLTMGR!FltReleaseContext` at `0x140034dab`
- `FLTMGR!FltReleaseContext` at `0x140034d95`
- `FLTMGR!FltReleaseContext` at `0x140034dab`

## pseudocode

```c
__int64 __fastcall WcPreLockControl(PFLT_CALLBACK_DATA CallbackData, __int64 a2, __int64 a3)
{
  struct _FILE_OBJECT *v4; // rdx
  struct _FLT_INSTANCE *v7; // rcx
  int v8; // edx
  unsigned int v9; // ebx
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  __int64 MinorFunction; // rcx
  char v13; // [rsp+40h] [rbp-59h] BYREF
  PFLT_CONTEXT v14; // [rsp+48h] [rbp-51h]
  unsigned int v15; // [rsp+50h] [rbp-49h]
  PFLT_CONTEXT Context; // [rsp+58h] [rbp-41h]
  __int64 v17; // [rsp+60h] [rbp-39h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+68h] [rbp-31h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+80h] [rbp-19h] BYREF
  char *v20; // [rsp+90h] [rbp-9h]
  int v21; // [rsp+98h] [rbp-1h]
  int v22; // [rsp+9Ch] [rbp+3h]
  char *v23; // [rsp+A0h] [rbp+7h]
  __int64 v24; // [rsp+A8h] [rbp+Fh]
  __int64 *v25; // [rsp+B0h] [rbp+17h]
  __int64 v26; // [rsp+B8h] [rbp+1Fh]

  v4 = *(struct _FILE_OBJECT **)(a2 + 32);
  v7 = *(struct _FLT_INSTANCE **)(a2 + 24);
  Context = 0;
  v14 = 0;
  if ( (unsigned __int8)WcGetContextFileObject(v7, v4)
    && (unsigned __int8)WcUsesSourceSectionObjectPointers(*(_QWORD *)(a2 + 32), v14) )
  {
    v9 = 4;
    if ( (unsigned int)dword_14000E060 > 5 )
    {
      v8 = 0;
      if ( (qword_14000E070 & 0x400000000000LL) != 0 && (qword_14000E078 & 0x400000000000LL) == qword_14000E078 )
      {
        v13 = 5;
        v23 = &v13;
        Iopb = CallbackData->Iopb;
        v24 = 1;
        EventDescriptor.Keyword = 0x400000000000LL;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        MinorFunction = Iopb->MinorFunction;
        v25 = &v17;
        *(_DWORD *)&EventDescriptor.Level = 5;
        UserData.Ptr = (ULONGLONG)off_14000E068;
        v17 = MinorFunction;
        v26 = 8;
        UserData.Size = *(unsigned __int16 *)off_14000E068;
        v20 = byte_14000BD65;
        UserData.Reserved = 2;
        v21 = 52;
        v22 = 1;
        v15 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
      }
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = 3;
      WPP_RECORDER_SF_sD(
        WPP_GLOBAL_Control->DeviceExtension,
        v8,
        13,
        68,
        (__int64)WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\wcifs.c",
        233);
    }
    CallbackData->IoStatus.Status = -1073741637;
  }
  else
  {
    v9 = WcSynchronizeExpansionPreopWithReason(CallbackData, 13, a3);
  }
  if ( Context )
    FltReleaseContext(Context);
  if ( v14 )
    FltReleaseContext(v14);
  return v9;
}

```

## disassembly

```asm
0x140034bb0  push    rbp
0x140034bb2  push    rbx
0x140034bb3  push    rsi
0x140034bb4  push    r14
0x140034bb6  push    r15
0x140034bb8  lea     rbp, [rsp-37h]
0x140034bbd  sub     rsp, 0D0h
0x140034bc4  mov     rax, cs:__security_cookie
0x140034bcb  xor     rax, rsp
0x140034bce  mov     [rbp+57h+var_30], rax
0x140034bd2  mov     rbx, rdx
0x140034bd5  lea     r9, [rbp+57h+var_A8]
0x140034bd9  mov     rdx, [rdx+20h]; FileObject
0x140034bdd  mov     r14, r8
0x140034be0  mov     rsi, rcx
0x140034be3  lea     r8, [rbp+57h+Context]
0x140034be7  xor     r15d, r15d
0x140034bea  mov     rcx, [rbx+18h]; Instance
0x140034bee  mov     [rbp+57h+Context], r15
0x140034bf2  mov     [rbp+57h+var_A8], r15
0x140034bf6  call    WcGetContextFileObject
0x140034bfb  test    al, al
0x140034bfd  jz      loc_140034D69
0x140034c03  mov     rdx, [rbp+57h+var_A8]
0x140034c07  mov     rcx, [rbx+20h]
0x140034c0b  call    WcUsesSourceSectionObjectPointers
0x140034c10  test    al, al
0x140034c12  jz      loc_140034D69
0x140034c18  mov     eax, cs:dword_14000E060
0x140034c1e  mov     ebx, 4
0x140034c23  cmp     eax, 5
0x140034c26  jbe     loc_140034D12
0x140034c2c  mov     rcx, cs:qword_14000E078
0x140034c33  mov     rdx, 400000000000h
0x140034c3d  mov     rax, cs:qword_14000E070
0x140034c44  test    rdx, rax
0x140034c47  jz      loc_140034D12
0x140034c4d  mov     rax, rcx
0x140034c50  and     rax, rdx
0x140034c53  cmp     rax, rcx
0x140034c56  jnz     loc_140034D12
0x140034c5c  mov     [rbp+57h+var_B0], 5
0x140034c60  lea     rax, [rbp+57h+var_B0]
0x140034c64  mov     [rbp+57h+var_50], rax
0x140034c68  xor     r9d, r9d; RelatedActivityId
0x140034c6b  mov     rax, [rsi+10h]
0x140034c6f  xor     r8d, r8d; ActivityId
0x140034c72  mov     [rbp+57h+var_48], 1
0x140034c7a  mov     [rbp+57h+EventDescriptor.Keyword], rdx
0x140034c7e  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x140034c82  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x140034c89  movzx   ecx, byte ptr [rax+5]
0x140034c8d  lea     rax, [rbp+57h+var_90]
0x140034c91  mov     [rbp+57h+var_40], rax
0x140034c95  movzx   eax, cs:word_14000BD5B
0x140034c9c  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x140034c9f  mov     rax, cs:off_14000E068
0x140034ca6  mov     [rbp+57h+var_70.Ptr], rax
0x140034caa  mov     [rbp+57h+var_90], rcx
0x140034cae  lea     rcx, _TraceLoggingMetadata
0x140034cb5  mov     [rbp+57h+var_38], 8
0x140034cbd  movzx   eax, word ptr [rax]
0x140034cc0  mov     [rbp+57h+var_70.Size], eax
0x140034cc3  lea     rax, byte_14000BD65
0x140034cca  mov     [rbp+57h+var_60], rax
0x140034cce  lea     rax, _TraceLoggingMetadataEnd
0x140034cd5  sub     eax, ecx
0x140034cd7  mov     dword ptr [rbp+57h+var_70.0Ch], 2
0x140034cde  mov     [rbp+57h+var_58], 34h ; '4'
0x140034ce5  mov     [rbp+57h+var_54], 1
0x140034cec  mov     [rbp+57h+var_A0], eax
0x140034cef  mov     eax, [rbp+57h+var_A0]
0x140034cf2  mov     rcx, cs:RegHandle; RegHandle
0x140034cf9  lea     rax, [rbp+57h+var_70]
0x140034cfd  mov     [rsp+0F0h+UserData], rax; UserData
0x140034d02  mov     [rsp+0F0h+UserDataCount], ebx; UserDataCount
0x140034d06  call    cs:__imp_EtwWriteTransfer
0x140034d0d  nop     dword ptr [rax+rax+00h]
0x140034d12  lea     rax, WPP_RECORDER_INITIALIZED
0x140034d19  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140034d20  jz      short loc_140034D60
0x140034d22  mov     rcx, cs:WPP_GLOBAL_Control
0x140034d29  lea     rax, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\wcifs\\wcifs.c"
0x140034d30  mov     [rsp+0F0h+var_C0], 0BE9h
0x140034d38  mov     r9d, 44h ; 'D'
0x140034d3e  mov     [rsp+0F0h+UserData], rax
0x140034d43  mov     r8d, 0Dh
0x140034d49  lea     rax, WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids
0x140034d50  mov     dl, 3
0x140034d52  mov     rcx, [rcx+40h]
0x140034d56  mov     qword ptr [rsp+0F0h+UserDataCount], rax
0x140034d5b  call    WPP_RECORDER_SF_sD
0x140034d60  mov     dword ptr [rsi+18h], 0C00000BBh
0x140034d67  jmp     short loc_140034D8C
0x140034d69  mov     [rsp+0F0h+UserData], r14; __int64
0x140034d6e  xor     r9d, r9d
0x140034d71  mov     r8d, 1
0x140034d77  mov     [rsp+0F0h+UserDataCount], 0Dh; int
0x140034d7f  mov     rdx, rbx
0x140034d82  mov     rcx, rsi; CallbackData
0x140034d85  call    WcSynchronizeExpansionPreopWithReason
0x140034d8a  mov     ebx, eax
0x140034d8c  mov     rcx, [rbp+57h+Context]; Context
0x140034d90  test    rcx, rcx
0x140034d93  jz      short loc_140034DA1
0x140034d95  call    cs:__imp_FltReleaseContext
0x140034d9c  nop     dword ptr [rax+rax+00h]
0x140034da1  cmp     [rbp+57h+var_A8], r15
0x140034da5  jz      short loc_140034DB7
0x140034da7  mov     rcx, [rbp+57h+var_A8]; Context
0x140034dab  call    cs:__imp_FltReleaseContext
0x140034db2  nop     dword ptr [rax+rax+00h]
0x140034db7  mov     eax, ebx
0x140034db9  mov     rcx, [rbp+57h+var_30]
0x140034dbd  xor     rcx, rsp; StackCookie
0x140034dc0  call    __security_check_cookie
0x140034dc5  add     rsp, 0D0h
0x140034dcc  pop     r15
0x140034dce  pop     r14
0x140034dd0  pop     rsi
0x140034dd1  pop     rbx
0x140034dd2  pop     rbp
0x140034dd3  retn
```
