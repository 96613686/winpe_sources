# DecrementDllReferenceCount

- ea: `0x1400029e0`
- end: `0x140002c97`
- name: `DecrementDllReferenceCount`
- size: `695`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140002940`
- `0x140003cd0`

## callees

- `0x1400029e0`
- `0x140004f90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002a9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002a9a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140002c4c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140002c4c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140002b37`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140002c38`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140002b37`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140002c38`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140002a0c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140002a0c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140002b47`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140002c76`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140002b47`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140002c76`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x140002c86`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x140002c86`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x140002c66`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x140002c66`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x140002a39`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x140002a39`

## pseudocode

```c
void __fastcall DecrementDllReferenceCount(__int64 a1)
{
  char *v2; // rcx
  __int64 v3; // rax
  bool v4; // zf
  int v5; // eax
  DWORD LastError; // eax
  char *v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  DWORD v10; // [rsp+34h] [rbp-35h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-31h] BYREF
  ULONG_PTR Cookie; // [rsp+48h] [rbp-21h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-19h] BYREF
  void *v14; // [rsp+60h] [rbp-9h]
  int v15; // [rsp+68h] [rbp-1h]
  int v16; // [rsp+6Ch] [rbp+3h]
  char *v17; // [rsp+70h] [rbp+7h]
  int v18; // [rsp+78h] [rbp+Fh]
  int v19; // [rsp+7Ch] [rbp+13h]
  DWORD *v20; // [rsp+80h] [rbp+17h]
  __int64 v21; // [rsp+88h] [rbp+1Fh]

  Cookie = 0;
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 32));
  --*(_DWORD *)(a1 + 48);
  if ( !*(_DWORD *)(a1 + 88) || *(_DWORD *)(a1 + 48) )
  {
LABEL_11:
    ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 32));
    return;
  }
  if ( !ActivateActCtx(*(HANDLE *)(*(_QWORD *)(a1 + 8) + 40LL), &Cookie) )
  {
    if ( (unsigned int)dword_14000F000 > 5 )
    {
      v2 = *(char **)a1;
      if ( *(_QWORD *)a1 )
      {
        v3 = -1;
        do
          v4 = *(_WORD *)&v2[2 * v3++ + 2] == 0;
        while ( !v4 );
        v5 = 2 * v3 + 2;
      }
      else
      {
        v2 = "";
        v5 = 2;
      }
      v17 = v2;
      v18 = v5;
      v19 = 0;
      LastError = GetLastError();
      v21 = 4;
      v10 = LastError;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      v20 = &v10;
      *(_DWORD *)&EventDescriptor.Level = 5;
      UserData.Ptr = (ULONGLONG)off_14000F008;
      EventDescriptor.Keyword = 0;
      UserData.Size = *(unsigned __int16 *)off_14000F008;
      v14 = &unk_14000B983;
      UserData.Reserved = 2;
      v15 = 61;
      v16 = 1;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
    }
    goto LABEL_11;
  }
  if ( (unsigned int)dword_14000F000 > 5 )
  {
    v7 = *(char **)(*(_QWORD *)(a1 + 8) + 24LL);
    if ( v7 )
    {
      v8 = -1;
      do
        v4 = *(_WORD *)&v7[2 * v8++ + 2] == 0;
      while ( !v4 );
      v9 = 2 * v8 + 2;
    }
    else
    {
      v7 = "";
      v9 = 2;
    }
    v18 = v9;
    *(_DWORD *)&EventDescriptor.Level = 5;
    UserData.Ptr = (ULONGLONG)off_14000F008;
    v17 = v7;
    v19 = 0;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = *(unsigned __int16 *)off_14000F008;
    v14 = &unk_14000B956;
    UserData.Reserved = 2;
    v15 = 33;
    v16 = 1;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
  }
  FreeLibrary(*(HMODULE *)(*(_QWORD *)(a1 + 8) + 16LL));
  *(_QWORD *)(*(_QWORD *)(a1 + 8) + 16LL) = 0;
  DeactivateActCtx(0, Cookie);
  ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 32));
  WakeAllConditionVariable((PCONDITION_VARIABLE)(a1 + 40));
}

```

## disassembly

```asm
0x1400029e0  push    rbp
0x1400029e2  push    rbx
0x1400029e3  push    rsi
0x1400029e4  push    rdi
0x1400029e5  lea     rbp, [rsp-3Fh]
0x1400029ea  sub     rsp, 0A8h
0x1400029f1  mov     rax, cs:__security_cookie
0x1400029f8  xor     rax, rsp
0x1400029fb  mov     [rbp+57h+var_30], rax
0x1400029ff  mov     rbx, rcx
0x140002a02  xor     esi, esi
0x140002a04  add     rcx, 20h ; ' '; SRWLock
0x140002a08  mov     [rbp+57h+Cookie], rsi
0x140002a0c  call    cs:__imp_AcquireSRWLockExclusive
0x140002a13  nop     dword ptr [rax+rax+00h]
0x140002a18  dec     dword ptr [rbx+30h]
0x140002a1b  cmp     [rbx+58h], esi
0x140002a1e  jz      loc_140002B43
0x140002a24  cmp     [rbx+30h], esi
0x140002a27  jnz     loc_140002B43
0x140002a2d  mov     rcx, [rbx+8]
0x140002a31  lea     rdx, [rbp+57h+Cookie]; lpCookie
0x140002a35  mov     rcx, [rcx+28h]; hActCtx
0x140002a39  call    cs:__imp_ActivateActCtx
0x140002a40  nop     dword ptr [rax+rax+00h]
0x140002a45  test    eax, eax
0x140002a47  mov     eax, cs:dword_14000F000
0x140002a4d  jnz     loc_140002B6C
0x140002a53  cmp     eax, 5
0x140002a56  jbe     loc_140002B43
0x140002a5c  mov     rcx, [rbx]
0x140002a5f  test    rcx, rcx
0x140002a62  jz      short loc_140002A84
0x140002a64  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140002a6b  nop     dword ptr [rax+rax+00h]
0x140002a70  cmp     [rcx+rax*2+2], si
0x140002a75  lea     rax, [rax+1]
0x140002a79  jnz     short loc_140002A70
0x140002a7b  lea     eax, ds:2[rax*2]
0x140002a82  jmp     short loc_140002A90
0x140002a84  lea     rcx, aNourlmimefilte+10h; ""
0x140002a8b  mov     eax, 2
0x140002a90  mov     [rbp+57h+var_50], rcx
0x140002a94  mov     [rbp+57h+var_48], eax
0x140002a97  mov     [rbp+57h+var_44], esi
0x140002a9a  call    cs:__imp_GetLastError
0x140002aa1  nop     dword ptr [rax+rax+00h]
0x140002aa6  mov     [rbp+57h+var_38], 4
0x140002aae  lea     rcx, _TraceLoggingMetadata
0x140002ab5  mov     [rbp+57h+var_8C], eax
0x140002ab8  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x140002abc  lea     rax, [rbp+57h+var_8C]
0x140002ac0  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x140002ac7  mov     [rbp+57h+var_40], rax
0x140002acb  xor     r9d, r9d; RelatedActivityId
0x140002ace  movzx   eax, cs:word_14000B979
0x140002ad5  xor     r8d, r8d; ActivityId
0x140002ad8  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x140002adb  mov     rax, cs:off_14000F008
0x140002ae2  mov     [rbp+57h+var_70.Ptr], rax
0x140002ae6  mov     [rbp+57h+EventDescriptor.Keyword], rsi
0x140002aea  movzx   eax, word ptr [rax]
0x140002aed  mov     [rbp+57h+var_70.Size], eax
0x140002af0  lea     rax, unk_14000B983
0x140002af7  mov     [rbp+57h+var_60], rax
0x140002afb  lea     rax, _TraceLoggingMetadataEnd
0x140002b02  sub     eax, ecx
0x140002b04  mov     dword ptr [rbp+57h+var_70.0Ch], 2
0x140002b0b  mov     [rbp+57h+var_58], 3Dh ; '='
0x140002b12  mov     [rbp+57h+var_54], 1
0x140002b19  mov     [rbp+57h+var_90], eax
0x140002b1c  mov     eax, [rbp+57h+var_90]
0x140002b1f  mov     rcx, cs:RegHandle; RegHandle
0x140002b26  lea     rax, [rbp+57h+var_70]
0x140002b2a  mov     [rsp+0C0h+UserData], rax; UserData
0x140002b2f  mov     [rsp+0C0h+UserDataCount], 4; UserDataCount
0x140002b37  call    cs:__imp_EventWriteTransfer
0x140002b3e  nop     dword ptr [rax+rax+00h]
0x140002b43  lea     rcx, [rbx+20h]; SRWLock
0x140002b47  call    cs:__imp_ReleaseSRWLockExclusive
0x140002b4e  nop     dword ptr [rax+rax+00h]
0x140002b53  mov     rcx, [rbp+57h+var_30]
0x140002b57  xor     rcx, rsp; StackCookie
0x140002b5a  call    __security_check_cookie
0x140002b5f  add     rsp, 0A8h
0x140002b66  pop     rdi
0x140002b67  pop     rsi
0x140002b68  pop     rbx
0x140002b69  pop     rbp
0x140002b6a  retn
0x140002b6c  cmp     eax, 5
0x140002b6f  jbe     loc_140002C44
0x140002b75  mov     rax, [rbx+8]
0x140002b79  mov     rcx, [rax+18h]
0x140002b7d  test    rcx, rcx
0x140002b80  jz      short loc_140002BA4
0x140002b82  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140002b89  nop     dword ptr [rax+00000000h]
0x140002b90  cmp     [rcx+rax*2+2], si
0x140002b95  lea     rax, [rax+1]
0x140002b99  jnz     short loc_140002B90
0x140002b9b  lea     eax, ds:2[rax*2]
0x140002ba2  jmp     short loc_140002BB0
0x140002ba4  lea     rcx, aNourlmimefilte+10h; ""
0x140002bab  mov     eax, 2
0x140002bb0  mov     [rbp+57h+var_48], eax
0x140002bb3  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x140002bb7  movzx   eax, cs:word_14000B94C
0x140002bbe  xor     r9d, r9d; RelatedActivityId
0x140002bc1  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x140002bc4  xor     r8d, r8d; ActivityId
0x140002bc7  mov     rax, cs:off_14000F008
0x140002bce  mov     [rbp+57h+var_70.Ptr], rax
0x140002bd2  mov     [rbp+57h+var_50], rcx
0x140002bd6  lea     rcx, _TraceLoggingMetadata
0x140002bdd  mov     [rbp+57h+var_44], esi
0x140002be0  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x140002be7  mov     [rbp+57h+EventDescriptor.Keyword], rsi
0x140002beb  movzx   eax, word ptr [rax]
0x140002bee  mov     [rbp+57h+var_70.Size], eax
0x140002bf1  lea     rax, unk_14000B956
0x140002bf8  mov     [rbp+57h+var_60], rax
0x140002bfc  lea     rax, _TraceLoggingMetadataEnd
0x140002c03  sub     eax, ecx
0x140002c05  mov     dword ptr [rbp+57h+var_70.0Ch], 2
0x140002c0c  mov     [rbp+57h+var_58], 21h ; '!'
0x140002c13  mov     [rbp+57h+var_54], 1
0x140002c1a  mov     [rbp+57h+var_90], eax
0x140002c1d  mov     eax, [rbp+57h+var_90]
0x140002c20  mov     rcx, cs:RegHandle; RegHandle
0x140002c27  lea     rax, [rbp+57h+var_70]
0x140002c2b  mov     [rsp+0C0h+UserData], rax; UserData
0x140002c30  mov     [rsp+0C0h+UserDataCount], 3; UserDataCount
0x140002c38  call    cs:__imp_EventWriteTransfer
0x140002c3f  nop     dword ptr [rax+rax+00h]
0x140002c44  mov     rcx, [rbx+8]
0x140002c48  mov     rcx, [rcx+10h]; hLibModule
0x140002c4c  call    cs:__imp_FreeLibrary
0x140002c53  nop     dword ptr [rax+rax+00h]
0x140002c58  mov     rax, [rbx+8]
0x140002c5c  xor     ecx, ecx; dwFlags
0x140002c5e  mov     [rax+10h], rsi
0x140002c62  mov     rdx, [rbp+57h+Cookie]; ulCookie
0x140002c66  call    cs:__imp_DeactivateActCtx
0x140002c6d  nop     dword ptr [rax+rax+00h]
0x140002c72  lea     rcx, [rbx+20h]; SRWLock
0x140002c76  call    cs:__imp_ReleaseSRWLockExclusive
0x140002c7d  nop     dword ptr [rax+rax+00h]
0x140002c82  lea     rcx, [rbx+28h]; ConditionVariable
0x140002c86  call    cs:__imp_WakeAllConditionVariable
0x140002c8d  nop     dword ptr [rax+rax+00h]
0x140002c92  jmp     loc_140002B53
```
