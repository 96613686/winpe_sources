# WcPreWrite

- ea: `0x140003930`
- end: `0x140003f37`
- name: `WcPreWrite`
- size: `1543`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x140001b00`
- `0x140002294`
- `0x140003930`
- `0x140004198`
- `0x140007c60`
- `0x140014008`
- `0x14002893c`

## import_xrefs

- `ntoskrnl!PsIsHostSilo` at `0x140003bcf`
- `ntoskrnl!PsIsHostSilo` at `0x140003bcf`
- `ntoskrnl!IoGetSilo` at `0x140003bc0`
- `ntoskrnl!IoGetSilo` at `0x140003bc0`
- `ntoskrnl!EtwWriteTransfer` at `0x140003a83`
- `ntoskrnl!EtwWriteTransfer` at `0x140003a83`
- `ntoskrnl!ExAcquireFastMutex` at `0x140003b63`
- `ntoskrnl!ExAcquireFastMutex` at `0x140003d3f`
- `ntoskrnl!ExAcquireFastMutex` at `0x140003d6b`
- `ntoskrnl!ExAcquireFastMutex` at `0x140003b63`
- `ntoskrnl!ExAcquireFastMutex` at `0x140003d3f`
- `ntoskrnl!ExAcquireFastMutex` at `0x140003d6b`
- `ntoskrnl!ExReleaseFastMutex` at `0x140003b7f`
- `ntoskrnl!ExReleaseFastMutex` at `0x140003d2f`
- `ntoskrnl!ExReleaseFastMutex` at `0x140003d5b`
- `ntoskrnl!ExReleaseFastMutex` at `0x140003d83`
- `ntoskrnl!ExReleaseFastMutex` at `0x140003da2`
- `ntoskrnl!ExReleaseFastMutex` at `0x140003ed1`
- `ntoskrnl!ExReleaseFastMutex` at `0x140003b7f`
- `ntoskrnl!ExReleaseFastMutex` at `0x140003d2f`
- `ntoskrnl!ExReleaseFastMutex` at `0x140003d5b`
- `ntoskrnl!ExReleaseFastMutex` at `0x140003d83`
- `ntoskrnl!ExReleaseFastMutex` at `0x140003da2`
- `ntoskrnl!ExReleaseFastMutex` at `0x140003ed1`
- `FLTMGR!FltGetFileContext` at `0x140003b25`
- `FLTMGR!FltGetFileContext` at `0x140003b25`
- `FLTMGR!FltGetStreamContext` at `0x140003b4b`
- `FLTMGR!FltGetStreamContext` at `0x140003b4b`
- `FLTMGR!FltReleaseContext` at `0x140003ee5`
- `FLTMGR!FltReleaseContext` at `0x140003ef4`
- `FLTMGR!FltReleaseContext` at `0x140003ee5`
- `FLTMGR!FltReleaseContext` at `0x140003ef4`

## string_xrefs

- `0x140003aa6`: `onecore\base\fs\wci\wcifs\readwrite.c`
- `0x140003c25`: `onecore\base\fs\wci\wcifs\readwrite.c`
- `0x140003cc2`: `onecore\base\fs\wci\wcifs\readwrite.c`
- `0x140003e1b`: `onecore\base\fs\wci\wcifs\readwrite.c`
- `0x140003e77`: `onecore\base\fs\wci\wcifs\readwrite.c`

## pseudocode

```c
__int64 __fastcall WcPreWrite(PFLT_CALLBACK_DATA CallbackData, __int64 a2)
{
  int v4; // edx
  __int64 result; // rax
  struct _FILE_OBJECT *v6; // rsi
  struct _FLT_INSTANCE *v7; // r14
  unsigned int v8; // r12d
  char *v9; // r13
  _QWORD *v10; // r14
  struct _FAST_MUTEX *v11; // rcx
  __int64 v12; // rcx
  __int16 v13; // ax
  __int64 v14; // rcx
  __int64 Silo; // rax
  int v16; // edx
  NTSTATUS v17; // eax
  struct _FAST_MUTEX *v18; // rcx
  struct _FAST_MUTEX *v19; // rcx
  int v20; // edx
  __int64 v21; // rcx
  NTSTATUS v22; // eax
  char v23; // [rsp+40h] [rbp-69h] BYREF
  __int128 v24; // [rsp+48h] [rbp-61h] BYREF
  PFLT_CONTEXT Context; // [rsp+58h] [rbp-51h] BYREF
  PFLT_CONTEXT v26; // [rsp+60h] [rbp-49h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+68h] [rbp-41h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+80h] [rbp-29h] BYREF
  char *v29; // [rsp+90h] [rbp-19h]
  int v30; // [rsp+98h] [rbp-11h]
  int v31; // [rsp+9Ch] [rbp-Dh]
  char *v32; // [rsp+A0h] [rbp-9h]
  __int64 v33; // [rsp+A8h] [rbp-1h]
  PFLT_CONTEXT *v34; // [rsp+B0h] [rbp+7h]
  __int64 v35; // [rsp+B8h] [rbp+Fh]

  v24 = 0;
  if ( BYTE2(qword_14000E6A2)
    || (*(_DWORD *)(*(_QWORD *)(a2 + 32) + 80LL) & 0x400000) == 0
    || CallbackData->RequestorMode != 1
    || !(unsigned __int8)WcIsSiloFileObject(*(_QWORD *)(a2 + 24)) )
  {
    v6 = *(struct _FILE_OBJECT **)(a2 + 32);
    v7 = *(struct _FLT_INSTANCE **)(a2 + 24);
    v8 = 1;
    Context = 0;
    v26 = 0;
    if ( FltGetFileContext(v7, v6, &Context) < 0 )
      return v8;
    FltGetStreamContext(v7, v6, &v26);
    v9 = (char *)Context;
    v10 = v26;
    ExAcquireFastMutex((PFAST_MUTEX)((char *)Context + 8));
    v11 = (struct _FAST_MUTEX *)(v9 + 8);
    if ( (*((_DWORD *)v9 + 22) & 2) != 0 )
    {
      ExReleaseFastMutex(v11);
      if ( v10 && (v10[3] & 0x10) == 0 )
      {
        v12 = *((_QWORD *)v9 + 8);
        *((_QWORD *)&v24 + 1) = v12 + 34;
        WORD1(v24) = *(_WORD *)(v12 + 32);
        v13 = *(_WORD *)(v12 + 32);
        v14 = *(_QWORD *)(a2 + 32);
        LOWORD(v24) = v13;
        Silo = IoGetSilo(v14);
        if ( (unsigned __int8)PsIsHostSilo(Silo) && *(_DWORD *)(v10[5] + 28LL) == 3 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_sDZ(
              WPP_GLOBAL_Control->DeviceExtension,
              2,
              2,
              13,
              (__int64)WPP_74e98403bd0930425909d23d2522dfc9_Traceguids,
              (__int64)"onecore\\base\\fs\\wci\\wcifs\\readwrite.c",
              191,
              (__int64)&v24);
        }
        else if ( (CallbackData->Iopb->IrpFlags & 2) != 0 )
        {
          if ( (*(_DWORD *)(*(_QWORD *)(a2 + 32) + 80LL) & 0x100) == 0
            && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v16) = 3;
            WPP_RECORDER_SF_sDZ(
              WPP_GLOBAL_Control->DeviceExtension,
              v16,
              2,
              14,
              (__int64)WPP_74e98403bd0930425909d23d2522dfc9_Traceguids,
              (__int64)"onecore\\base\\fs\\wci\\wcifs\\readwrite.c",
              222,
              (__int64)&v24);
          }
        }
        else
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_sDZ(
              WPP_GLOBAL_Control->DeviceExtension,
              2,
              2,
              15,
              (__int64)WPP_74e98403bd0930425909d23d2522dfc9_Traceguids,
              (__int64)"onecore\\base\\fs\\wci\\wcifs\\readwrite.c",
              235,
              (__int64)&v24);
          v17 = WcExpandAndWait(CallbackData, *(PVOID *)(a2 + 24), *(PVOID *)(a2 + 32), 1, 18);
          if ( v17 < 0 )
          {
            CallbackData->IoStatus.Status = v17;
            v8 = 4;
            CallbackData->IoStatus.Information = 0;
          }
        }
        goto LABEL_47;
      }
    }
    else
    {
      ExReleaseFastMutex(v11);
    }
    ExAcquireFastMutex((PFAST_MUTEX)(v9 + 8));
    v18 = (struct _FAST_MUTEX *)(v9 + 8);
    if ( (*((_DWORD *)v9 + 22) & 2) != 0 )
    {
      ExReleaseFastMutex(v18);
      ExAcquireFastMutex((PFAST_MUTEX)(v9 + 8));
      v19 = (struct _FAST_MUTEX *)(v9 + 8);
      if ( (*((_DWORD *)v9 + 22) & 2) != 0 )
      {
        ExReleaseFastMutex(v19);
        if ( v10 && (v10[3] & 0x10) != 0 )
          goto LABEL_47;
      }
      else
      {
        ExReleaseFastMutex(v19);
      }
      v21 = *((_QWORD *)v9 + 8);
      if ( (*(_DWORD *)(v21 + 12) & 2) == 0 )
      {
        *((_QWORD *)&v24 + 1) = v21 + 34;
        WORD1(v24) = *(_WORD *)(v21 + 32);
        LOWORD(v24) = *(_WORD *)(v21 + 32);
        if ( (CallbackData->Iopb->IrpFlags & 2) != 0 )
        {
          if ( (*(_DWORD *)(*(_QWORD *)(a2 + 32) + 80LL) & 0x100) == 0
            && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v20) = 3;
            WPP_RECORDER_SF_sDZ(
              WPP_GLOBAL_Control->DeviceExtension,
              v20,
              2,
              16,
              (__int64)WPP_74e98403bd0930425909d23d2522dfc9_Traceguids,
              (__int64)"onecore\\base\\fs\\wci\\wcifs\\readwrite.c",
              22,
              (__int64)&v24);
          }
        }
        else
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v20) = 3;
            WPP_RECORDER_SF_sDZ(
              WPP_GLOBAL_Control->DeviceExtension,
              v20,
              2,
              17,
              (__int64)WPP_74e98403bd0930425909d23d2522dfc9_Traceguids,
              (__int64)"onecore\\base\\fs\\wci\\wcifs\\readwrite.c",
              35,
              (__int64)&v24);
          }
          v22 = WcSetPlaceHolderFlagsSynchronized(CallbackData, *(PVOID *)(a2 + 24), *(PVOID *)(a2 + 32));
          if ( v22 < 0 )
          {
            CallbackData->IoStatus.Status = v22;
            v8 = 4;
            CallbackData->IoStatus.Information = 0;
          }
        }
      }
    }
    else
    {
      ExReleaseFastMutex(v18);
    }
    if ( !v10 )
    {
LABEL_48:
      FltReleaseContext(v9);
      return v8;
    }
LABEL_47:
    FltReleaseContext(v10);
    goto LABEL_48;
  }
  if ( (unsigned int)dword_14000E060 > 5 )
  {
    v4 = 0;
    if ( (qword_14000E070 & 0x400000000000LL) != 0 && (qword_14000E078 & 0x400000000000LL) == qword_14000E078 )
    {
      EventDescriptor.Keyword = 0x400000000000LL;
      v32 = &v23;
      v23 = 2;
      v34 = &v26;
      *(_DWORD *)&EventDescriptor.Level = 5;
      UserData.Ptr = (ULONGLONG)off_14000E068;
      v33 = 1;
      v26 = (PFLT_CONTEXT)4;
      v35 = 8;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      UserData.Size = *(unsigned __int16 *)off_14000E068;
      v29 = byte_14000B823;
      UserData.Reserved = 2;
      v30 = 52;
      v31 = 1;
      LODWORD(Context) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
    }
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v4) = 3;
    WPP_RECORDER_SF_sD(
      WPP_GLOBAL_Control->DeviceExtension,
      v4,
      2,
      12,
      (__int64)WPP_74e98403bd0930425909d23d2522dfc9_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\wcifs\\readwrite.c",
      153);
  }
  CallbackData->IoStatus.Status = -1073741637;
  result = 4;
  CallbackData->IoStatus.Information = 0;
  return result;
}

```

## disassembly

```asm
0x140003930  push    rbp
0x140003932  push    rbx
0x140003933  push    rdi
0x140003934  push    r12
0x140003936  push    r15
0x140003938  lea     rbp, [rsp-37h]
0x14000393d  sub     rsp, 0E0h
0x140003944  mov     rax, cs:__security_cookie
0x14000394b  xor     rax, rsp
0x14000394e  mov     [rbp+57h+var_40], rax
0x140003952  cmp     byte ptr cs:qword_14000E6A2+2, 0
0x140003959  xorps   xmm0, xmm0
0x14000395c  movups  [rbp+57h+var_B8], xmm0
0x140003960  mov     rdi, rdx
0x140003963  mov     rbx, rcx
0x140003966  jnz     loc_140003AF2
0x14000396c  mov     rdx, [rdx+20h]
0x140003970  test    dword ptr [rdx+50h], 400000h
0x140003977  jz      loc_140003AF2
0x14000397d  cmp     byte ptr [rcx+50h], 1
0x140003981  jnz     loc_140003AF2
0x140003987  mov     rcx, [rdi+18h]
0x14000398b  call    WcIsSiloFileObject
0x140003990  test    al, al
0x140003992  jz      loc_140003AF2
0x140003998  mov     eax, cs:dword_14000E060
0x14000399e  xor     r15d, r15d
0x1400039a1  cmp     eax, 5
0x1400039a4  jbe     loc_140003A8F
0x1400039aa  mov     rcx, cs:qword_14000E078
0x1400039b1  mov     rdx, 400000000000h
0x1400039bb  mov     rax, cs:qword_14000E070
0x1400039c2  test    rdx, rax
0x1400039c5  jz      loc_140003A8F
0x1400039cb  mov     rax, rcx
0x1400039ce  and     rax, rdx
0x1400039d1  cmp     rax, rcx
0x1400039d4  jnz     loc_140003A8F
0x1400039da  mov     [rbp+57h+EventDescriptor.Keyword], rdx
0x1400039de  lea     rax, [rbp+57h+var_C0]
0x1400039e2  mov     [rbp+57h+var_60], rax
0x1400039e6  lea     rcx, _TraceLoggingMetadata
0x1400039ed  lea     rax, [rbp+57h+var_A0]
0x1400039f1  mov     [rbp+57h+var_C0], 2
0x1400039f5  mov     [rbp+57h+var_50], rax
0x1400039f9  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x1400039fd  movzx   eax, cs:word_14000B819
0x140003a04  mov     r12d, 1
0x140003a0a  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x140003a0d  xor     r9d, r9d; RelatedActivityId
0x140003a10  mov     rax, cs:off_14000E068
0x140003a17  xor     r8d, r8d; ActivityId
0x140003a1a  mov     [rbp+57h+var_80.Ptr], rax
0x140003a1e  mov     [rbp+57h+var_58], r12
0x140003a22  mov     [rbp+57h+var_A0], 4
0x140003a2a  mov     [rbp+57h+var_48], 8
0x140003a32  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x140003a39  movzx   eax, word ptr [rax]
0x140003a3c  mov     [rbp+57h+var_80.Size], eax
0x140003a3f  lea     rax, byte_14000B823
0x140003a46  mov     [rbp+57h+var_70], rax
0x140003a4a  lea     rax, _TraceLoggingMetadataEnd
0x140003a51  sub     eax, ecx
0x140003a53  mov     dword ptr [rbp+57h+var_80.0Ch], 2
0x140003a5a  mov     [rbp+57h+var_68], 34h ; '4'
0x140003a61  mov     [rbp+57h+var_64], r12d
0x140003a65  mov     dword ptr [rbp+57h+Context], eax
0x140003a68  mov     eax, dword ptr [rbp+57h+Context]
0x140003a6b  mov     rcx, cs:RegHandle; RegHandle
0x140003a72  lea     rax, [rbp+57h+var_80]
0x140003a76  mov     [rsp+100h+UserData], rax; UserData
0x140003a7b  mov     [rsp+100h+UserDataCount], 4; UserDataCount
0x140003a83  call    cs:__imp_EtwWriteTransfer
0x140003a8a  nop     dword ptr [rax+rax+00h]
0x140003a8f  lea     rax, WPP_RECORDER_INITIALIZED
0x140003a96  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140003a9d  jz      short loc_140003ADD
0x140003a9f  mov     rcx, cs:WPP_GLOBAL_Control
0x140003aa6  lea     rax, aOnecoreBaseFsW_7; "onecore\\base\\fs\\wci\\wcifs\\readwrit"...
0x140003aad  mov     [rsp+100h+var_D0], 199h
0x140003ab5  mov     r9d, 0Ch
0x140003abb  mov     [rsp+100h+UserData], rax
0x140003ac0  mov     r8d, 2
0x140003ac6  lea     rax, WPP_74e98403bd0930425909d23d2522dfc9_Traceguids
0x140003acd  mov     dl, 3
0x140003acf  mov     rcx, [rcx+40h]
0x140003ad3  mov     qword ptr [rsp+100h+UserDataCount], rax
0x140003ad8  call    WPP_RECORDER_SF_sD
0x140003add  mov     dword ptr [rbx+18h], 0C00000BBh
0x140003ae4  mov     eax, 4
0x140003ae9  mov     [rbx+20h], r15
0x140003aed  jmp     loc_140003F1B
0x140003af2  mov     [rsp+100h+arg_10], rsi
0x140003afa  lea     r8, [rbp+57h+Context]; Context
0x140003afe  mov     rsi, [rdi+20h]
0x140003b02  xor     r15d, r15d
0x140003b05  mov     [rsp+100h+var_30], r14
0x140003b0d  mov     rdx, rsi; FileObject
0x140003b10  mov     r14, [rdi+18h]
0x140003b14  mov     r12d, 1
0x140003b1a  mov     rcx, r14; Instance
0x140003b1d  mov     [rbp+57h+Context], r15
0x140003b21  mov     [rbp+57h+var_A0], r15
0x140003b25  call    cs:__imp_FltGetFileContext
0x140003b2c  nop     dword ptr [rax+rax+00h]
0x140003b31  test    eax, eax
0x140003b33  js      loc_140003F08
0x140003b39  lea     r8, [rbp+57h+var_A0]; Context
0x140003b3d  mov     [rsp+100h+var_28], r13
0x140003b45  mov     rdx, rsi; FileObject
0x140003b48  mov     rcx, r14; Instance
0x140003b4b  call    cs:__imp_FltGetStreamContext
0x140003b52  nop     dword ptr [rax+rax+00h]
0x140003b57  mov     r13, [rbp+57h+Context]
0x140003b5b  mov     r14, [rbp+57h+var_A0]
0x140003b5f  lea     rcx, [r13+8]; FastMutex
0x140003b63  call    cs:__imp_ExAcquireFastMutex
0x140003b6a  nop     dword ptr [rax+rax+00h]
0x140003b6f  mov     eax, [r13+58h]
0x140003b73  lea     rcx, [r13+8]; FastMutex
0x140003b77  test    al, 2
0x140003b79  jz      loc_140003D2F
0x140003b7f  call    cs:__imp_ExReleaseFastMutex
0x140003b86  nop     dword ptr [rax+rax+00h]
0x140003b8b  test    r14, r14
0x140003b8e  jz      loc_140003D3B
0x140003b94  mov     eax, [r14+18h]
0x140003b98  test    al, 10h
0x140003b9a  jnz     loc_140003D3B
0x140003ba0  mov     rcx, [r13+40h]
0x140003ba4  lea     rax, [rcx+22h]
0x140003ba8  mov     qword ptr [rbp+57h+var_B8+8], rax
0x140003bac  movzx   eax, word ptr [rcx+20h]
0x140003bb0  mov     word ptr [rbp+57h+var_B8+2], ax
0x140003bb4  movzx   eax, word ptr [rcx+20h]
0x140003bb8  mov     rcx, [rdi+20h]
0x140003bbc  mov     word ptr [rbp+57h+var_B8], ax
0x140003bc0  call    cs:__imp_IoGetSilo
0x140003bc7  nop     dword ptr [rax+rax+00h]
0x140003bcc  mov     rcx, rax
0x140003bcf  call    cs:__imp_PsIsHostSilo
0x140003bd6  nop     dword ptr [rax+rax+00h]
0x140003bdb  test    al, al
0x140003bdd  jz      short loc_140003C4B
0x140003bdf  mov     rax, [r14+28h]
0x140003be3  cmp     dword ptr [rax+1Ch], 3
0x140003be7  jnz     short loc_140003C4B
0x140003be9  lea     rax, WPP_RECORDER_INITIALIZED
0x140003bf0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140003bf7  jz      loc_140003EE2
0x140003bfd  lea     rax, [rbp+57h+var_B8]
0x140003c01  mov     r8d, 2
0x140003c07  mov     [rsp+100h+var_C8], rax
0x140003c0c  mov     r9d, 0Dh
0x140003c12  mov     [rsp+100h+var_D0], 1BFh
0x140003c1a  movzx   edx, r8b
0x140003c1e  mov     rcx, cs:WPP_GLOBAL_Control
0x140003c25  lea     rax, aOnecoreBaseFsW_7; "onecore\\base\\fs\\wci\\wcifs\\readwrit"...
0x140003c2c  mov     [rsp+100h+UserData], rax
0x140003c31  lea     rax, WPP_74e98403bd0930425909d23d2522dfc9_Traceguids
0x140003c38  mov     qword ptr [rsp+100h+UserDataCount], rax
0x140003c3d  mov     rcx, [rcx+40h]
0x140003c41  call    WPP_RECORDER_SF_sDZ
0x140003c46  jmp     loc_140003EE2
0x140003c4b  mov     rax, [rbx+10h]
0x140003c4f  mov     ecx, [rax]
0x140003c51  test    cl, 2
0x140003c54  jz      short loc_140003C9C
0x140003c56  mov     rax, [rdi+20h]
0x140003c5a  test    dword ptr [rax+50h], 100h
0x140003c61  jnz     loc_140003EE2
0x140003c67  lea     rax, WPP_RECORDER_INITIALIZED
0x140003c6e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140003c75  jz      loc_140003EE2
0x140003c7b  lea     rax, [rbp+57h+var_B8]
0x140003c7f  mov     r9d, 0Eh
0x140003c85  mov     [rsp+100h+var_C8], rax
0x140003c8a  mov     r8d, 2
0x140003c90  mov     [rsp+100h+var_D0], 1DEh
0x140003c98  mov     dl, 3
0x140003c9a  jmp     short loc_140003C1E
0x140003c9c  lea     rax, WPP_RECORDER_INITIALIZED
0x140003ca3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140003caa  jz      short loc_140003CF5
0x140003cac  mov     rcx, cs:WPP_GLOBAL_Control
0x140003cb3  lea     rax, [rbp+57h+var_B8]
0x140003cb7  mov     [rsp+100h+var_C8], rax
0x140003cbc  mov     r8d, 2
0x140003cc2  lea     rax, aOnecoreBaseFsW_7; "onecore\\base\\fs\\wci\\wcifs\\readwrit"...
0x140003cc9  mov     [rsp+100h+var_D0], 1EBh
0x140003cd1  mov     [rsp+100h+UserData], rax
0x140003cd6  mov     r9d, 0Fh
0x140003cdc  mov     rcx, [rcx+40h]
0x140003ce0  lea     rax, WPP_74e98403bd0930425909d23d2522dfc9_Traceguids
0x140003ce7  movzx   edx, r8b
0x140003ceb  mov     qword ptr [rsp+100h+UserDataCount], rax
0x140003cf0  call    WPP_RECORDER_SF_sDZ
0x140003cf5  mov     r8, [rdi+20h]; Object
0x140003cf9  mov     r9, r13
0x140003cfc  mov     rdx, [rdi+18h]; FltObject
0x140003d00  mov     rcx, rbx; CallbackData
0x140003d03  mov     dword ptr [rsp+100h+UserData], 12h; int
0x140003d0b  mov     [rsp+100h+UserDataCount], r12d; int
0x140003d10  call    WcExpandAndWait
0x140003d15  test    eax, eax
0x140003d17  jns     loc_140003EE2
0x140003d1d  mov     [rbx+18h], eax
0x140003d20  mov     r12d, 4
0x140003d26  mov     [rbx+20h], r15
0x140003d2a  jmp     loc_140003EE2
0x140003d2f  call    cs:__imp_ExReleaseFastMutex
0x140003d36  nop     dword ptr [rax+rax+00h]
0x140003d3b  lea     rcx, [r13+8]; FastMutex
0x140003d3f  call    cs:__imp_ExAcquireFastMutex
0x140003d46  nop     dword ptr [rax+rax+00h]
0x140003d4b  mov     eax, [r13+58h]
0x140003d4f  lea     rcx, [r13+8]; FastMutex
0x140003d53  test    al, 2
0x140003d55  jz      loc_140003ED1
0x140003d5b  call    cs:__imp_ExReleaseFastMutex
0x140003d62  nop     dword ptr [rax+rax+00h]
0x140003d67  lea     rcx, [r13+8]; FastMutex
0x140003d6b  call    cs:__imp_ExAcquireFastMutex
0x140003d72  nop     dword ptr [rax+rax+00h]
0x140003d77  mov     eax, [r13+58h]
0x140003d7b  lea     rcx, [r13+8]; FastMutex
0x140003d7f  test    al, 2
0x140003d81  jz      short loc_140003DA2
0x140003d83  call    cs:__imp_ExReleaseFastMutex
0x140003d8a  nop     dword ptr [rax+rax+00h]
0x140003d8f  test    r14, r14
0x140003d92  jz      short loc_140003DAE
0x140003d94  mov     eax, [r14+18h]
0x140003d98  test    al, 10h
0x140003d9a  jnz     loc_140003EE2
0x140003da0  jmp     short loc_140003DAE
0x140003da2  call    cs:__imp_ExReleaseFastMutex
0x140003da9  nop     dword ptr [rax+rax+00h]
0x140003dae  mov     rcx, [r13+40h]
0x140003db2  mov     eax, [rcx+0Ch]
0x140003db5  test    al, 2
0x140003db7  jnz     loc_140003EDD
0x140003dbd  lea     rax, [rcx+22h]
0x140003dc1  mov     qword ptr [rbp+57h+var_B8+8], rax
0x140003dc5  movzx   eax, word ptr [rcx+20h]
0x140003dc9  mov     word ptr [rbp+57h+var_B8+2], ax
0x140003dcd  movzx   eax, word ptr [rcx+20h]
0x140003dd1  mov     word ptr [rbp+57h+var_B8], ax
0x140003dd5  mov     rax, [rbx+10h]
0x140003dd9  mov     ecx, [rax]
0x140003ddb  test    cl, 2
0x140003dde  jz      short loc_140003E51
0x140003de0  mov     rax, [rdi+20h]
0x140003de4  test    dword ptr [rax+50h], 100h
0x140003deb  jnz     loc_140003EDD
0x140003df1  lea     rax, WPP_RECORDER_INITIALIZED
0x140003df8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140003dff  jz      loc_140003EDD
0x140003e05  mov     rcx, cs:WPP_GLOBAL_Control
0x140003e0c  lea     rax, [rbp+57h+var_B8]
0x140003e10  mov     [rsp+100h+var_C8], rax
0x140003e15  mov     r9d, 10h
0x140003e1b  lea     rax, aOnecoreBaseFsW_7; "onecore\\base\\fs\\wci\\wcifs\\readwrit"...
0x140003e22  mov     [rsp+100h+var_D0], 216h
0x140003e2a  mov     [rsp+100h+UserData], rax
0x140003e2f  mov     r8d, 2
0x140003e35  mov     rcx, [rcx+40h]
0x140003e39  lea     rax, WPP_74e98403bd0930425909d23d2522dfc9_Traceguids
0x140003e40  mov     dl, 3
0x140003e42  mov     qword ptr [rsp+100h+UserDataCount], rax
0x140003e47  call    WPP_RECORDER_SF_sDZ
0x140003e4c  jmp     loc_140003EDD
0x140003e51  lea     rax, WPP_RECORDER_INITIALIZED
0x140003e58  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140003e5f  jz      short loc_140003EA8
0x140003e61  mov     rcx, cs:WPP_GLOBAL_Control
0x140003e68  lea     rax, [rbp+57h+var_B8]
0x140003e6c  mov     [rsp+100h+var_C8], rax
0x140003e71  mov     r9d, 11h
0x140003e77  lea     rax, aOnecoreBaseFsW_7; "onecore\\base\\fs\\wci\\wcifs\\readwrit"...
0x140003e7e  mov     [rsp+100h+var_D0], 223h
0x140003e86  mov     [rsp+100h+UserData], rax
0x140003e8b  mov     r8d, 2
0x140003e91  mov     rcx, [rcx+40h]
0x140003e95  lea     rax, WPP_74e98403bd0930425909d23d2522dfc9_Traceguids
0x140003e9c  mov     dl, 3
0x140003e9e  mov     qword ptr [rsp+100h+UserDataCount], rax
0x140003ea3  call    WPP_RECORDER_SF_sDZ
0x140003ea8  mov     r8, [rdi+20h]; Object
0x140003eac  mov     r9d, 2
0x140003eb2  mov     rdx, [rdi+18h]; FltObject
0x140003eb6  mov     rcx, rbx; CallbackData
0x140003eb9  call    WcSetPlaceHolderFlagsSynchronized
0x140003ebe  test    eax, eax
0x140003ec0  jns     short loc_140003EDD
0x140003ec2  mov     [rbx+18h], eax
0x140003ec5  mov     r12d, 4
0x140003ecb  mov     [rbx+20h], r15
0x140003ecf  jmp     short loc_140003EDD
0x140003ed1  call    cs:__imp_ExReleaseFastMutex
  ... truncated ...
```
