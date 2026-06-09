# PostLogMove(_UNICODE_STRING const *)

- ea: `0x140002868`
- end: `0x140002a93`
- name: `?PostLogMove@@YAJPEBU_UNICODE_STRING@@@Z`
- size: `555`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String1)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14001e808`

## callees

- `0x140002868`
- `0x140002ffc`
- `0x14000fd40`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000298f`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000298f`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140002974`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140002974`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400029bd`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400029d0`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400029bd`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400029d0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002a38`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002a38`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140002933`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140002933`
- `ntoskrnl!KeReleaseMutex` at `0x140002a65`
- `ntoskrnl!KeReleaseMutex` at `0x140002a65`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000289a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000289a`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400028c0`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400028c0`
- `FLTMGR!FltQueueGenericWorkItem` at `0x140002a13`
- `FLTMGR!FltQueueGenericWorkItem` at `0x140002a13`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x1400029e3`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x1400029e3`
- `FLTMGR!FltFreeGenericWorkItem` at `0x140002a50`
- `FLTMGR!FltFreeGenericWorkItem` at `0x140002a50`

## pseudocode

```c
__int64 __fastcall PostLogMove(PCUNICODE_STRING String1)
{
  struct _FLT_GENERIC_WORKITEM *v2; // rsi
  NTSTATUS appended; // edi
  unsigned __int16 Length; // r8
  __int16 v5; // dx
  unsigned int v6; // edi
  wchar_t *PoolWithTag; // rax
  wchar_t *Buffer; // rbx
  struct _FLT_GENERIC_WORKITEM *GenericWorkItem; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-20h] BYREF
  UNICODE_STRING Source; // [rsp+40h] [rbp-10h] BYREF

  DestinationString = 0;
  v2 = 0;
  KeWaitForSingleObject(&Object, Executive, 0, 0, 0);
  if ( !byte_140019588 )
  {
    appended = 0;
    if ( !RtlEqualUnicodeString(String1, &UnicodeString, 1u) )
    {
LABEL_14:
      Buffer = DestinationString.Buffer;
      goto LABEL_15;
    }
  }
  Length = StringOut.Length;
  v5 = String2.Length - StringOut.Length;
  *(_DWORD *)(&Source.MaximumLength + 1) = 0;
  if ( StringOut.Length <= UnicodeString.Length )
    Length = UnicodeString.Length;
  v6 = (unsigned __int16)(v5 + Length);
  Source.Length = String2.Length - StringOut.Length;
  Source.MaximumLength = String2.Length - StringOut.Length;
  DestinationString.MaximumLength = v5 + Length;
  Source.Buffer = &String2.Buffer[(unsigned __int64)StringOut.Length >> 1];
  PoolWithTag = (wchar_t *)ExAllocatePoolWithTag((POOL_TYPE)1025, (unsigned __int16)(v5 + Length), 0x6E6D7377u);
  Buffer = PoolWithTag;
  if ( !ExPoolZeroingNativelySupported && PoolWithTag )
  {
    memset(PoolWithTag, 0, v6);
    DestinationString.Buffer = Buffer;
    goto LABEL_8;
  }
  DestinationString.Buffer = PoolWithTag;
  if ( PoolWithTag )
  {
LABEL_8:
    RtlCopyUnicodeString(&DestinationString, &UnicodeString);
    if ( !Source.Length || (appended = RtlAppendUnicodeStringToString(&DestinationString, &Source), appended >= 0) )
    {
      appended = SetLogPath(&DestinationString, 1);
      if ( appended >= 0 )
      {
        RtlFreeUnicodeString(&UnicodeString);
        RtlFreeUnicodeString(&StringOut);
        byte_140019588 = 0;
        GenericWorkItem = FltAllocateGenericWorkItem();
        v2 = GenericWorkItem;
        if ( GenericWorkItem )
        {
          appended = FltQueueGenericWorkItem(GenericWorkItem, FilterHandle, ResumeLoggingToFile, DelayedWorkQueue, 0);
          if ( appended >= 0 )
            v2 = 0;
        }
      }
    }
    goto LABEL_14;
  }
  appended = -1073741670;
LABEL_15:
  if ( Buffer )
  {
    ExFreePoolWithTag(Buffer, 0x6E6D7377u);
    DestinationString.Buffer = 0;
  }
  if ( v2 )
    FltFreeGenericWorkItem(v2);
  KeReleaseMutex(&Object, 0);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x140002868  push    rbp
0x14000286a  push    rbx
0x14000286b  push    rsi
0x14000286c  push    rdi
0x14000286d  push    r14
0x14000286f  mov     rbp, rsp
0x140002872  sub     rsp, 50h
0x140002876  mov     rbx, rcx
0x140002879  xorps   xmm0, xmm0
0x14000287c  xor     r14d, r14d
0x14000287f  lea     rcx, Object; Object
0x140002886  xor     r9d, r9d; Alertable
0x140002889  mov     [rsp+50h+Timeout], r14; Timeout
0x14000288e  xor     r8d, r8d; WaitMode
0x140002891  xor     edx, edx; WaitReason
0x140002893  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140002897  mov     esi, r14d
0x14000289a  call    cs:__imp_KeWaitForSingleObject
0x1400028a1  nop     dword ptr [rax+rax+00h]
0x1400028a6  mov     al, cs:byte_140019588
0x1400028ac  test    al, al
0x1400028ae  jnz     short loc_1400028D4
0x1400028b0  mov     r8b, 1; CaseInSensitive
0x1400028b3  lea     rdx, UnicodeString; String2
0x1400028ba  mov     rcx, rbx; String1
0x1400028bd  mov     edi, r14d
0x1400028c0  call    cs:__imp_RtlEqualUnicodeString
0x1400028c7  nop     dword ptr [rax+rax+00h]
0x1400028cc  test    al, al
0x1400028ce  jz      loc_140002A27
0x1400028d4  movzx   r8d, cs:StringOut.Length
0x1400028dc  xor     eax, eax
0x1400028de  movzx   edx, cs:String2.Length
0x1400028e5  mov     ecx, r8d
0x1400028e8  sub     dx, r8w
0x1400028ec  shr     rcx, 1
0x1400028ef  cmp     r8w, cs:UnicodeString.Length
0x1400028f7  mov     dword ptr [rbp+Source+4], eax
0x1400028fa  cmovbe  r8w, cs:UnicodeString.Length
0x140002903  mov     rax, cs:String2.Buffer
0x14000290a  add     r8w, dx
0x14000290e  movzx   edi, r8w
0x140002912  mov     r8d, 6E6D7377h; Tag
0x140002918  mov     [rbp+Source.Length], dx
0x14000291c  mov     [rbp+Source.MaximumLength], dx
0x140002920  mov     edx, edi; NumberOfBytes
0x140002922  lea     rcx, [rax+rcx*2]
0x140002926  mov     [rbp+DestinationString.MaximumLength], di
0x14000292a  mov     [rbp+Source.Buffer], rcx
0x14000292e  mov     ecx, 401h; PoolType
0x140002933  call    cs:__imp_ExAllocatePoolWithTag
0x14000293a  nop     dword ptr [rax+rax+00h]
0x14000293f  cmp     cs:ExPoolZeroingNativelySupported, r14b
0x140002946  mov     rbx, rax
0x140002949  jnz     loc_140002A7F
0x14000294f  test    rax, rax
0x140002952  jz      loc_140002A7F
0x140002958  mov     r8d, edi; Size
0x14000295b  xor     edx, edx; Val
0x14000295d  mov     rcx, rax; void *
0x140002960  call    memset
0x140002965  mov     [rbp+DestinationString.Buffer], rbx
0x140002969  lea     rdx, UnicodeString; SourceString
0x140002970  lea     rcx, [rbp+DestinationString]; DestinationString
0x140002974  call    cs:__imp_RtlCopyUnicodeString
0x14000297b  nop     dword ptr [rax+rax+00h]
0x140002980  cmp     [rbp+Source.Length], r14w
0x140002985  jbe     short loc_1400029A5
0x140002987  lea     rdx, [rbp+Source]; Source
0x14000298b  lea     rcx, [rbp+DestinationString]; Destination
0x14000298f  call    cs:__imp_RtlAppendUnicodeStringToString
0x140002996  nop     dword ptr [rax+rax+00h]
0x14000299b  mov     edi, eax
0x14000299d  test    eax, eax
0x14000299f  js      loc_140002A27
0x1400029a5  mov     dl, 1; bool
0x1400029a7  lea     rcx, [rbp+DestinationString]; struct _UNICODE_STRING *
0x1400029ab  call    ?SetLogPath@@YAJPEBU_UNICODE_STRING@@_N@Z; SetLogPath(_UNICODE_STRING const *,bool)
0x1400029b0  mov     edi, eax
0x1400029b2  test    eax, eax
0x1400029b4  js      short loc_140002A27
0x1400029b6  lea     rcx, UnicodeString; UnicodeString
0x1400029bd  call    cs:__imp_RtlFreeUnicodeString
0x1400029c4  nop     dword ptr [rax+rax+00h]
0x1400029c9  lea     rcx, StringOut; UnicodeString
0x1400029d0  call    cs:__imp_RtlFreeUnicodeString
0x1400029d7  nop     dword ptr [rax+rax+00h]
0x1400029dc  mov     cs:byte_140019588, r14b
0x1400029e3  call    cs:__imp_FltAllocateGenericWorkItem
0x1400029ea  nop     dword ptr [rax+rax+00h]
0x1400029ef  mov     rsi, rax
0x1400029f2  test    rax, rax
0x1400029f5  jz      short loc_140002A27
0x1400029f7  mov     rdx, cs:?FilterHandle@@3PEAU_FLT_FILTER@@EA; FltObject
0x1400029fe  lea     r8, ResumeLoggingToFile; WorkerRoutine
0x140002a05  mov     r9d, 1; QueueType
0x140002a0b  mov     [rsp+50h+Timeout], r14; Context
0x140002a10  mov     rcx, rax; FltWorkItem
0x140002a13  call    cs:__imp_FltQueueGenericWorkItem
0x140002a1a  nop     dword ptr [rax+rax+00h]
0x140002a1f  test    eax, eax
0x140002a21  mov     edi, eax
0x140002a23  cmovns  rsi, r14
0x140002a27  mov     rbx, [rbp+DestinationString.Buffer]
0x140002a2b  test    rbx, rbx
0x140002a2e  jz      short loc_140002A48
0x140002a30  mov     edx, 6E6D7377h; Tag
0x140002a35  mov     rcx, rbx; P
0x140002a38  call    cs:__imp_ExFreePoolWithTag
0x140002a3f  nop     dword ptr [rax+rax+00h]
0x140002a44  mov     [rbp+DestinationString.Buffer], r14
0x140002a48  test    rsi, rsi
0x140002a4b  jz      short loc_140002A5C
0x140002a4d  mov     rcx, rsi; FltWorkItem
0x140002a50  call    cs:__imp_FltFreeGenericWorkItem
0x140002a57  nop     dword ptr [rax+rax+00h]
0x140002a5c  xor     edx, edx; Wait
0x140002a5e  lea     rcx, Object; Mutex
0x140002a65  call    cs:__imp_KeReleaseMutex
0x140002a6c  nop     dword ptr [rax+rax+00h]
0x140002a71  mov     eax, edi
0x140002a73  add     rsp, 50h
0x140002a77  pop     r14
0x140002a79  pop     rdi
0x140002a7a  pop     rsi
0x140002a7b  pop     rbx
0x140002a7c  pop     rbp
0x140002a7d  retn
0x140002a7f  mov     [rbp+DestinationString.Buffer], rbx
0x140002a83  test    rbx, rbx
0x140002a86  jnz     loc_140002969
0x140002a8c  mov     edi, 0C000009Ah
0x140002a91  jmp     short loc_140002A2B
```
