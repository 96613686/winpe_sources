# WcPreLockControl

- ea: `0x140034c00`
- end: `0x140034e25`
- name: `WcPreLockControl`
- size: `549`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, __int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x140001500`
- `0x140002264`
- `0x140004198`
- `0x140007c60`
- `0x140023890`
- `0x140034c00`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140034d56`
- `ntoskrnl!EtwWriteTransfer` at `0x140034d56`
- `FLTMGR!FltReleaseContext` at `0x140034de5`
- `FLTMGR!FltReleaseContext` at `0x140034dfb`
- `FLTMGR!FltReleaseContext` at `0x140034de5`
- `FLTMGR!FltReleaseContext` at `0x140034dfb`

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
  PFLT_CONTEXT v14; // [rsp+48h] [rbp-51h] BYREF
  unsigned int v15; // [rsp+50h] [rbp-49h]
  PFLT_CONTEXT Context; // [rsp+58h] [rbp-41h] BYREF
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
  if ( WcGetContextFileObject(v7, v4, &Context, &v14)
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
        wil_details_featureDescriptors_a->DeviceExtension,
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
0x140034c00  push    rbp
0x140034c02  push    rbx
0x140034c03  push    rsi
0x140034c04  push    r14
0x140034c06  push    r15
0x140034c08  lea     rbp, [rsp-37h]
0x140034c0d  sub     rsp, 0D0h
0x140034c14  mov     rax, cs:__security_cookie
0x140034c1b  xor     rax, rsp
0x140034c1e  mov     [rbp+57h+var_30], rax
0x140034c22  mov     rbx, rdx
0x140034c25  lea     r9, [rbp+57h+var_A8]
0x140034c29  mov     rdx, [rdx+20h]; FileObject
0x140034c2d  mov     r14, r8
0x140034c30  mov     rsi, rcx
0x140034c33  lea     r8, [rbp+57h+Context]
0x140034c37  xor     r15d, r15d
0x140034c3a  mov     rcx, [rbx+18h]; Instance
0x140034c3e  mov     [rbp+57h+Context], r15
0x140034c42  mov     [rbp+57h+var_A8], r15
0x140034c46  call    WcGetContextFileObject
0x140034c4b  test    al, al
0x140034c4d  jz      loc_140034DB9
0x140034c53  mov     rdx, [rbp+57h+var_A8]
0x140034c57  mov     rcx, [rbx+20h]
0x140034c5b  call    WcUsesSourceSectionObjectPointers
0x140034c60  test    al, al
0x140034c62  jz      loc_140034DB9
0x140034c68  mov     eax, cs:dword_14000E060
0x140034c6e  mov     ebx, 4
0x140034c73  cmp     eax, 5
0x140034c76  jbe     loc_140034D62
0x140034c7c  mov     rcx, cs:qword_14000E078
0x140034c83  mov     rdx, 400000000000h
0x140034c8d  mov     rax, cs:qword_14000E070
0x140034c94  test    rdx, rax
0x140034c97  jz      loc_140034D62
0x140034c9d  mov     rax, rcx
0x140034ca0  and     rax, rdx
0x140034ca3  cmp     rax, rcx
0x140034ca6  jnz     loc_140034D62
0x140034cac  mov     [rbp+57h+var_B0], 5
0x140034cb0  lea     rax, [rbp+57h+var_B0]
0x140034cb4  mov     [rbp+57h+var_50], rax
0x140034cb8  xor     r9d, r9d; RelatedActivityId
0x140034cbb  mov     rax, [rsi+10h]
0x140034cbf  xor     r8d, r8d; ActivityId
0x140034cc2  mov     [rbp+57h+var_48], 1
0x140034cca  mov     [rbp+57h+EventDescriptor.Keyword], rdx
0x140034cce  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x140034cd2  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x140034cd9  movzx   ecx, byte ptr [rax+5]
0x140034cdd  lea     rax, [rbp+57h+var_90]
0x140034ce1  mov     [rbp+57h+var_40], rax
0x140034ce5  movzx   eax, cs:word_14000BD5B
0x140034cec  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x140034cef  mov     rax, cs:off_14000E068
0x140034cf6  mov     [rbp+57h+var_70.Ptr], rax
0x140034cfa  mov     [rbp+57h+var_90], rcx
0x140034cfe  lea     rcx, _TraceLoggingMetadata
0x140034d05  mov     [rbp+57h+var_38], 8
0x140034d0d  movzx   eax, word ptr [rax]
0x140034d10  mov     [rbp+57h+var_70.Size], eax
0x140034d13  lea     rax, byte_14000BD65
0x140034d1a  mov     [rbp+57h+var_60], rax
0x140034d1e  lea     rax, _TraceLoggingMetadataEnd
0x140034d25  sub     eax, ecx
0x140034d27  mov     dword ptr [rbp+57h+var_70.0Ch], 2
0x140034d2e  mov     [rbp+57h+var_58], 34h ; '4'
0x140034d35  mov     [rbp+57h+var_54], 1
0x140034d3c  mov     [rbp+57h+var_A0], eax
0x140034d3f  mov     eax, [rbp+57h+var_A0]
0x140034d42  mov     rcx, cs:RegHandle; RegHandle
0x140034d49  lea     rax, [rbp+57h+var_70]
0x140034d4d  mov     [rsp+0F0h+UserData], rax; UserData
0x140034d52  mov     [rsp+0F0h+UserDataCount], ebx; UserDataCount
0x140034d56  call    cs:__imp_EtwWriteTransfer
0x140034d5d  nop     dword ptr [rax+rax+00h]
0x140034d62  lea     rax, WPP_RECORDER_INITIALIZED
0x140034d69  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140034d70  jz      short loc_140034DB0
0x140034d72  mov     rcx, cs:wil_details_featureDescriptors_a
0x140034d79  lea     rax, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\wcifs\\wcifs.c"
0x140034d80  mov     [rsp+0F0h+var_C0], 0BE9h
0x140034d88  mov     r9d, 44h ; 'D'
0x140034d8e  mov     [rsp+0F0h+UserData], rax
0x140034d93  mov     r8d, 0Dh
0x140034d99  lea     rax, WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids
0x140034da0  mov     dl, 3
0x140034da2  mov     rcx, [rcx+40h]
0x140034da6  mov     qword ptr [rsp+0F0h+UserDataCount], rax
0x140034dab  call    WPP_RECORDER_SF_sD
0x140034db0  mov     dword ptr [rsi+18h], 0C00000BBh
0x140034db7  jmp     short loc_140034DDC
0x140034db9  mov     [rsp+0F0h+UserData], r14; __int64
0x140034dbe  xor     r9d, r9d
0x140034dc1  mov     r8d, 1
0x140034dc7  mov     [rsp+0F0h+UserDataCount], 0Dh; int
0x140034dcf  mov     rdx, rbx
0x140034dd2  mov     rcx, rsi; CallbackData
0x140034dd5  call    WcSynchronizeExpansionPreopWithReason
0x140034dda  mov     ebx, eax
0x140034ddc  mov     rcx, [rbp+57h+Context]; Context
0x140034de0  test    rcx, rcx
0x140034de3  jz      short loc_140034DF1
0x140034de5  call    cs:__imp_FltReleaseContext
0x140034dec  nop     dword ptr [rax+rax+00h]
0x140034df1  cmp     [rbp+57h+var_A8], r15
0x140034df5  jz      short loc_140034E07
0x140034df7  mov     rcx, [rbp+57h+var_A8]; Context
0x140034dfb  call    cs:__imp_FltReleaseContext
0x140034e02  nop     dword ptr [rax+rax+00h]
0x140034e07  mov     eax, ebx
0x140034e09  mov     rcx, [rbp+57h+var_30]
0x140034e0d  xor     rcx, rsp; StackCookie
0x140034e10  call    __security_check_cookie
0x140034e15  add     rsp, 0D0h
0x140034e1c  pop     r15
0x140034e1e  pop     r14
0x140034e20  pop     rsi
0x140034e21  pop     rbx
0x140034e22  pop     rbp
0x140034e23  retn
```
