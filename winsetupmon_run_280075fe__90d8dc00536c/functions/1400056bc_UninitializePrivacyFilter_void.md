# UninitializePrivacyFilter(void)

- ea: `0x1400056bc`
- end: `0x140005907`
- name: `?UninitializePrivacyFilter@@YAXXZ`
- size: `587`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140007800`

## callees

- `0x140003944`
- `0x1400056bc`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140005738`
- `ntoskrnl!ZwClose` at `0x140005738`
- `ntoskrnl!ZwWaitForSingleObject` at `0x14000570d`
- `ntoskrnl!ZwWaitForSingleObject` at `0x14000570d`
- `ntoskrnl!KeClearEvent` at `0x140005756`
- `ntoskrnl!KeClearEvent` at `0x140005769`
- `ntoskrnl!KeClearEvent` at `0x140005756`
- `ntoskrnl!KeClearEvent` at `0x140005769`
- `ntoskrnl!KeSetEvent` at `0x1400056f5`
- `ntoskrnl!KeSetEvent` at `0x1400056f5`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140005832`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140005832`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400057b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400057d5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005856`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000588c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400057b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400057d5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005856`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000588c`
- `FLTMGR!FltDeletePushLock` at `0x1400058c9`
- `FLTMGR!FltDeletePushLock` at `0x1400058dc`
- `FLTMGR!FltDeletePushLock` at `0x1400058ef`
- `FLTMGR!FltDeletePushLock` at `0x1400058c9`
- `FLTMGR!FltDeletePushLock` at `0x1400058dc`
- `FLTMGR!FltDeletePushLock` at `0x1400058ef`
- `FLTMGR!FltReleasePushLockEx` at `0x14000577e`
- `FLTMGR!FltReleasePushLockEx` at `0x1400057f6`
- `FLTMGR!FltReleasePushLockEx` at `0x1400058b6`
- `FLTMGR!FltReleasePushLockEx` at `0x14000577e`
- `FLTMGR!FltReleasePushLockEx` at `0x1400057f6`
- `FLTMGR!FltReleasePushLockEx` at `0x1400058b6`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400056cf`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140005793`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14000580b`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400056cf`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140005793`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14000580b`

## string_xrefs

- `0x140005720`: `Could not wait for profile list watch thread (0x%08X)`

## pseudocode

```c
void UninitializePrivacyFilter(void)
{
  NTSTATUS v0; // eax
  void *v1; // rcx
  unsigned __int64 v2; // rbx
  PUNICODE_STRING *v3; // rcx

  FltAcquirePushLockExclusiveEx(&qword_1400193B0, 0);
  if ( Handle )
  {
    KeSetEvent(&stru_1400193D8, 0, 0);
    v0 = ZwWaitForSingleObject(Handle, 0, 0);
    if ( v0 < 0 )
      WriteLogMessage(3, L"Could not wait for profile list watch thread (0x%08X)", (unsigned int)v0);
    ZwClose(Handle);
    Handle = 0;
    KeClearEvent(&stru_1400193D8);
    KeClearEvent(&Event);
  }
  FltReleasePushLockEx(&qword_1400193B0, 0);
  FltAcquirePushLockExclusiveEx(&PushLock, 0);
  while ( 1 )
  {
    v2 = (unsigned __int64)qword_140019420;
    if ( !qword_140019420 )
      break;
    qword_140019420 = *(PVOID *)qword_140019420;
    v1 = *(void **)(v2 + 16);
    if ( v1 )
    {
      ExFreePoolWithTag(v1, 0x6E6D7377u);
      *(_QWORD *)(v2 + 16) = 0;
    }
    ExFreePoolWithTag((PVOID)v2, 0x6E6D7377u);
  }
  FltReleasePushLockEx(&PushLock, 0);
  FltAcquirePushLockExclusiveEx(&qword_140019400, 0);
  v3 = (PUNICODE_STRING *)qword_140019410;
  if ( dword_140019408 )
  {
    do
    {
      if ( v3[v2] )
      {
        RtlFreeUnicodeString(v3[v2]);
        v3 = (PUNICODE_STRING *)qword_140019410;
      }
      if ( v3[v2] )
      {
        ExFreePoolWithTag(v3[v2], 0x6E6D7377u);
        *((_QWORD *)qword_140019410 + v2) = 0;
        v3 = (PUNICODE_STRING *)qword_140019410;
      }
      v2 = (unsigned int)(v2 + 1);
    }
    while ( (unsigned int)v2 < dword_140019408 );
  }
  if ( v3 )
  {
    ExFreePoolWithTag(v3, 0x6E6D7377u);
    qword_140019410 = 0;
  }
  dword_140019408 = 0;
  FltReleasePushLockEx(&qword_140019400, 0);
  FltDeletePushLock(&PushLock);
  FltDeletePushLock(&qword_140019400);
  FltDeletePushLock(&qword_1400193B0);
}

```

## disassembly

```asm
0x1400056bc  mov     [rsp+arg_0], rbx
0x1400056c1  push    rdi
0x1400056c2  sub     rsp, 20h
0x1400056c6  xor     edx, edx
0x1400056c8  lea     rcx, qword_1400193B0
0x1400056cf  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x1400056d6  nop     dword ptr [rax+rax+00h]
0x1400056db  cmp     cs:Handle, 0
0x1400056e3  jz      loc_140005775
0x1400056e9  xor     r8d, r8d; Wait
0x1400056ec  lea     rcx, stru_1400193D8; Event
0x1400056f3  xor     edx, edx; Increment
0x1400056f5  call    cs:__imp_KeSetEvent
0x1400056fc  nop     dword ptr [rax+rax+00h]
0x140005701  mov     rcx, cs:Handle; Handle
0x140005708  xor     r8d, r8d; Timeout
0x14000570b  xor     edx, edx; Alertable
0x14000570d  call    cs:__imp_ZwWaitForSingleObject
0x140005714  nop     dword ptr [rax+rax+00h]
0x140005719  test    eax, eax
0x14000571b  jns     short loc_140005731
0x14000571d  mov     r8d, eax
0x140005720  lea     rdx, aCouldNotWaitFo_0; "Could not wait for profile list watch t"...
0x140005727  mov     ecx, 3
0x14000572c  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x140005731  mov     rcx, cs:Handle; Handle
0x140005738  call    cs:__imp_ZwClose
0x14000573f  nop     dword ptr [rax+rax+00h]
0x140005744  lea     rcx, stru_1400193D8; Event
0x14000574b  mov     cs:Handle, 0
0x140005756  call    cs:__imp_KeClearEvent
0x14000575d  nop     dword ptr [rax+rax+00h]
0x140005762  lea     rcx, Event; Event
0x140005769  call    cs:__imp_KeClearEvent
0x140005770  nop     dword ptr [rax+rax+00h]
0x140005775  xor     edx, edx
0x140005777  lea     rcx, qword_1400193B0
0x14000577e  call    cs:__imp_FltReleasePushLockEx
0x140005785  nop     dword ptr [rax+rax+00h]
0x14000578a  xor     edx, edx
0x14000578c  lea     rcx, PushLock
0x140005793  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14000579a  nop     dword ptr [rax+rax+00h]
0x14000579f  jmp     short loc_1400057E1
0x1400057a1  mov     rax, [rbx]
0x1400057a4  mov     cs:qword_140019420, rax
0x1400057ab  mov     rcx, [rbx+10h]; P
0x1400057af  test    rcx, rcx
0x1400057b2  jz      short loc_1400057CD
0x1400057b4  mov     edx, 6E6D7377h; Tag
0x1400057b9  call    cs:__imp_ExFreePoolWithTag
0x1400057c0  nop     dword ptr [rax+rax+00h]
0x1400057c5  mov     qword ptr [rbx+10h], 0
0x1400057cd  mov     edx, 6E6D7377h; Tag
0x1400057d2  mov     rcx, rbx; P
0x1400057d5  call    cs:__imp_ExFreePoolWithTag
0x1400057dc  nop     dword ptr [rax+rax+00h]
0x1400057e1  mov     rbx, cs:qword_140019420
0x1400057e8  test    rbx, rbx
0x1400057eb  jnz     short loc_1400057A1
0x1400057ed  xor     edx, edx
0x1400057ef  lea     rcx, PushLock
0x1400057f6  call    cs:__imp_FltReleasePushLockEx
0x1400057fd  nop     dword ptr [rax+rax+00h]
0x140005802  xor     edx, edx
0x140005804  lea     rcx, qword_140019400
0x14000580b  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140005812  nop     dword ptr [rax+rax+00h]
0x140005817  cmp     cs:dword_140019408, ebx
0x14000581d  mov     rcx, cs:qword_140019410
0x140005824  jbe     short loc_140005882
0x140005826  mov     rax, [rcx+rbx*8]
0x14000582a  test    rax, rax
0x14000582d  jz      short loc_140005845
0x14000582f  mov     rcx, rax; UnicodeString
0x140005832  call    cs:__imp_RtlFreeUnicodeString
0x140005839  nop     dword ptr [rax+rax+00h]
0x14000583e  mov     rcx, cs:qword_140019410
0x140005845  mov     rax, [rcx+rbx*8]
0x140005849  test    rax, rax
0x14000584c  jz      short loc_140005878
0x14000584e  mov     edx, 6E6D7377h; Tag
0x140005853  mov     rcx, rax; P
0x140005856  call    cs:__imp_ExFreePoolWithTag
0x14000585d  nop     dword ptr [rax+rax+00h]
0x140005862  mov     rax, cs:qword_140019410
0x140005869  mov     qword ptr [rax+rbx*8], 0
0x140005871  mov     rcx, cs:qword_140019410; P
0x140005878  inc     ebx
0x14000587a  cmp     ebx, cs:dword_140019408
0x140005880  jb      short loc_140005826
0x140005882  test    rcx, rcx
0x140005885  jz      short loc_1400058A3
0x140005887  mov     edx, 6E6D7377h; Tag
0x14000588c  call    cs:__imp_ExFreePoolWithTag
0x140005893  nop     dword ptr [rax+rax+00h]
0x140005898  mov     cs:qword_140019410, 0
0x1400058a3  xor     edx, edx
0x1400058a5  mov     cs:dword_140019408, 0
0x1400058af  lea     rcx, qword_140019400
0x1400058b6  call    cs:__imp_FltReleasePushLockEx
0x1400058bd  nop     dword ptr [rax+rax+00h]
0x1400058c2  lea     rcx, PushLock; PushLock
0x1400058c9  call    cs:__imp_FltDeletePushLock
0x1400058d0  nop     dword ptr [rax+rax+00h]
0x1400058d5  lea     rcx, qword_140019400; PushLock
0x1400058dc  call    cs:__imp_FltDeletePushLock
0x1400058e3  nop     dword ptr [rax+rax+00h]
0x1400058e8  lea     rcx, qword_1400193B0; PushLock
0x1400058ef  call    cs:__imp_FltDeletePushLock
0x1400058f6  nop     dword ptr [rax+rax+00h]
0x1400058fb  mov     rbx, [rsp+28h+arg_0]
0x140005900  add     rsp, 20h
0x140005904  pop     rdi
0x140005905  retn
```
