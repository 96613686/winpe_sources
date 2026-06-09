# DecrementDllReferenceCount

- ea: `0x1400027b0`
- end: `0x140002a29`
- name: `DecrementDllReferenceCount`
- size: `633`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140002720`
- `0x1400039f0`

## callees

- `0x1400027b0`
- `0x140004bd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000285a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000285a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400029f6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400029f6`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1400028f1`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1400029e8`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1400028f1`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1400029e8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400027dc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400027dc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400028fb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140002a14`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400028fb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140002a14`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x140002a1e`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x140002a1e`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x140002a0a`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x140002a0a`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x140002803`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x140002803`

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
  __int16 *v14; // [rsp+60h] [rbp-9h]
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
      UserData.Size = (unsigned __int16)*off_14000F008;
      v14 = (__int16 *)byte_14000B983;
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
    UserData.Size = (unsigned __int16)*off_14000F008;
    v14 = &word_14000B956;
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
0x1400027b0  push    rbp
0x1400027b2  push    rbx
0x1400027b3  push    rsi
0x1400027b4  push    rdi
0x1400027b5  lea     rbp, [rsp-3Fh]
0x1400027ba  sub     rsp, 0A8h
0x1400027c1  mov     rax, cs:__security_cookie
0x1400027c8  xor     rax, rsp
0x1400027cb  mov     [rbp+57h+var_30], rax
0x1400027cf  mov     rbx, rcx
0x1400027d2  xor     esi, esi
0x1400027d4  add     rcx, 20h ; ' '; SRWLock
0x1400027d8  mov     [rbp+57h+Cookie], rsi
0x1400027dc  call    cs:__imp_AcquireSRWLockExclusive
0x1400027e2  dec     dword ptr [rbx+30h]
0x1400027e5  cmp     [rbx+58h], esi
0x1400027e8  jz      loc_1400028F7
0x1400027ee  cmp     [rbx+30h], esi
0x1400027f1  jnz     loc_1400028F7
0x1400027f7  mov     rcx, [rbx+8]
0x1400027fb  lea     rdx, [rbp+57h+Cookie]; lpCookie
0x1400027ff  mov     rcx, [rcx+28h]; hActCtx
0x140002803  call    cs:__imp_ActivateActCtx
0x140002809  test    eax, eax
0x14000280b  mov     eax, cs:dword_14000F000
0x140002811  jnz     loc_140002919
0x140002817  cmp     eax, 5
0x14000281a  jbe     loc_1400028F7
0x140002820  mov     rcx, [rbx]
0x140002823  test    rcx, rcx
0x140002826  jz      short loc_140002844
0x140002828  mov     rax, 0FFFFFFFFFFFFFFFFh
0x14000282f  nop
0x140002830  cmp     [rcx+rax*2+2], si
0x140002835  lea     rax, [rax+1]
0x140002839  jnz     short loc_140002830
0x14000283b  lea     eax, ds:2[rax*2]
0x140002842  jmp     short loc_140002850
0x140002844  lea     rcx, aNourlmimefilte+10h; ""
0x14000284b  mov     eax, 2
0x140002850  mov     [rbp+57h+var_50], rcx
0x140002854  mov     [rbp+57h+var_48], eax
0x140002857  mov     [rbp+57h+var_44], esi
0x14000285a  call    cs:__imp_GetLastError
0x140002860  mov     [rbp+57h+var_38], 4
0x140002868  lea     rcx, _TraceLoggingMetadata
0x14000286f  mov     [rbp+57h+var_8C], eax
0x140002872  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x140002876  lea     rax, [rbp+57h+var_8C]
0x14000287a  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x140002881  mov     [rbp+57h+var_40], rax
0x140002885  xor     r9d, r9d; RelatedActivityId
0x140002888  movzx   eax, cs:word_14000B979
0x14000288f  xor     r8d, r8d; ActivityId
0x140002892  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x140002895  mov     rax, cs:off_14000F008
0x14000289c  mov     [rbp+57h+var_70.Ptr], rax
0x1400028a0  mov     [rbp+57h+EventDescriptor.Keyword], rsi
0x1400028a4  movzx   eax, word ptr [rax]
0x1400028a7  mov     [rbp+57h+var_70.Size], eax
0x1400028aa  lea     rax, byte_14000B983
0x1400028b1  mov     [rbp+57h+var_60], rax
0x1400028b5  lea     rax, _TraceLoggingMetadataEnd
0x1400028bc  sub     eax, ecx
0x1400028be  mov     dword ptr [rbp+57h+var_70.0Ch], 2
0x1400028c5  mov     [rbp+57h+var_58], 3Dh ; '='
0x1400028cc  mov     [rbp+57h+var_54], 1
0x1400028d3  mov     [rbp+57h+var_90], eax
0x1400028d6  mov     eax, [rbp+57h+var_90]
0x1400028d9  mov     rcx, cs:RegHandle; RegHandle
0x1400028e0  lea     rax, [rbp+57h+var_70]
0x1400028e4  mov     [rsp+0C0h+UserData], rax; UserData
0x1400028e9  mov     [rsp+0C0h+UserDataCount], 4; UserDataCount
0x1400028f1  call    cs:__imp_EventWriteTransfer
0x1400028f7  lea     rcx, [rbx+20h]; SRWLock
0x1400028fb  call    cs:__imp_ReleaseSRWLockExclusive
0x140002901  mov     rcx, [rbp+57h+var_30]
0x140002905  xor     rcx, rsp; StackCookie
0x140002908  call    __security_check_cookie
0x14000290d  add     rsp, 0A8h
0x140002914  pop     rdi
0x140002915  pop     rsi
0x140002916  pop     rbx
0x140002917  pop     rbp
0x140002918  retn
0x140002919  cmp     eax, 5
0x14000291c  jbe     loc_1400029EE
0x140002922  mov     rax, [rbx+8]
0x140002926  mov     rcx, [rax+18h]
0x14000292a  test    rcx, rcx
0x14000292d  jz      short loc_140002954
0x14000292f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140002936  nop     word ptr [rax+rax+00000000h]
0x140002940  cmp     [rcx+rax*2+2], si
0x140002945  lea     rax, [rax+1]
0x140002949  jnz     short loc_140002940
0x14000294b  lea     eax, ds:2[rax*2]
0x140002952  jmp     short loc_140002960
0x140002954  lea     rcx, aNourlmimefilte+10h; ""
0x14000295b  mov     eax, 2
0x140002960  mov     [rbp+57h+var_48], eax
0x140002963  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x140002967  movzx   eax, cs:word_14000B94C
0x14000296e  xor     r9d, r9d; RelatedActivityId
0x140002971  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x140002974  xor     r8d, r8d; ActivityId
0x140002977  mov     rax, cs:off_14000F008
0x14000297e  mov     [rbp+57h+var_70.Ptr], rax
0x140002982  mov     [rbp+57h+var_50], rcx
0x140002986  lea     rcx, _TraceLoggingMetadata
0x14000298d  mov     [rbp+57h+var_44], esi
0x140002990  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x140002997  mov     [rbp+57h+EventDescriptor.Keyword], rsi
0x14000299b  movzx   eax, word ptr [rax]
0x14000299e  mov     [rbp+57h+var_70.Size], eax
0x1400029a1  lea     rax, word_14000B956
0x1400029a8  mov     [rbp+57h+var_60], rax
0x1400029ac  lea     rax, _TraceLoggingMetadataEnd
0x1400029b3  sub     eax, ecx
0x1400029b5  mov     dword ptr [rbp+57h+var_70.0Ch], 2
0x1400029bc  mov     [rbp+57h+var_58], 21h ; '!'
0x1400029c3  mov     [rbp+57h+var_54], 1
0x1400029ca  mov     [rbp+57h+var_90], eax
0x1400029cd  mov     eax, [rbp+57h+var_90]
0x1400029d0  mov     rcx, cs:RegHandle; RegHandle
0x1400029d7  lea     rax, [rbp+57h+var_70]
0x1400029db  mov     [rsp+0C0h+UserData], rax; UserData
0x1400029e0  mov     [rsp+0C0h+UserDataCount], 3; UserDataCount
0x1400029e8  call    cs:__imp_EventWriteTransfer
0x1400029ee  mov     rcx, [rbx+8]
0x1400029f2  mov     rcx, [rcx+10h]; hLibModule
0x1400029f6  call    cs:__imp_FreeLibrary
0x1400029fc  mov     rax, [rbx+8]
0x140002a00  xor     ecx, ecx; dwFlags
0x140002a02  mov     [rax+10h], rsi
0x140002a06  mov     rdx, [rbp+57h+Cookie]; ulCookie
0x140002a0a  call    cs:__imp_DeactivateActCtx
0x140002a10  lea     rcx, [rbx+20h]; SRWLock
0x140002a14  call    cs:__imp_ReleaseSRWLockExclusive
0x140002a1a  lea     rcx, [rbx+28h]; ConditionVariable
0x140002a1e  call    cs:__imp_WakeAllConditionVariable
0x140002a24  jmp     loc_140002901
```
