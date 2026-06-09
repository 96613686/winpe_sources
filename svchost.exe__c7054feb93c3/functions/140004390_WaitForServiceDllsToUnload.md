# WaitForServiceDllsToUnload

- ea: `0x140004390`
- end: `0x1400045b5`
- name: `WaitForServiceDllsToUnload`
- size: `549`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x140002a40`

## callees

- `0x140004390`
- `0x140004bd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400044af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400044af`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x14000454c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x14000454c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140004405`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140004405`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140004556`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140004556`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x140004441`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x140004441`

## pseudocode

```c
void WaitForServiceDllsToUnload()
{
  unsigned int i; // ebp
  __int64 v1; // rbx
  __int64 v2; // rax
  char *v3; // rcx
  __int64 v4; // rax
  int v6; // eax
  DWORD LastError; // eax
  _DWORD v8[2]; // [rsp+30h] [rbp-98h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-90h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-78h] BYREF
  char *v11; // [rsp+60h] [rbp-68h]
  int v12; // [rsp+68h] [rbp-60h]
  int v13; // [rsp+6Ch] [rbp-5Ch]
  char *v14; // [rsp+70h] [rbp-58h]
  int v15; // [rsp+78h] [rbp-50h]
  int v16; // [rsp+7Ch] [rbp-4Ch]
  _DWORD *v17; // [rsp+80h] [rbp-48h]
  __int64 v18; // [rsp+88h] [rbp-40h]

  for ( i = 0; i < ServiceCount; ++i )
  {
    v1 = ServiceArray + 96LL * i;
    AcquireSRWLockExclusive((PSRWLOCK)(v1 + 32));
    v2 = *(_QWORD *)(v1 + 8);
    if ( v2 && *(_QWORD *)(v2 + 16) && *(_DWORD *)(v1 + 88) )
    {
      while ( SleepConditionVariableSRW((PCONDITION_VARIABLE)(v1 + 40), (PSRWLOCK)(v1 + 32), 0x1388u, 0) )
      {
        if ( !*(_QWORD *)(*(_QWORD *)(v1 + 8) + 16LL) )
          goto LABEL_15;
      }
      if ( (unsigned int)dword_14000F000 > 5 )
      {
        v3 = *(char **)v1;
        if ( *(_QWORD *)v1 )
        {
          v4 = -1;
          while ( *(_WORD *)&v3[2 * v4++ + 2] != 0 )
            ;
          v6 = 2 * v4 + 2;
        }
        else
        {
          v3 = "";
          v6 = 2;
        }
        v14 = v3;
        v15 = v6;
        v16 = 0;
        LastError = GetLastError();
        v18 = 4;
        v8[0] = LastError;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        v17 = v8;
        *(_DWORD *)&EventDescriptor.Level = 5;
        UserData.Ptr = (ULONGLONG)off_14000F008;
        EventDescriptor.Keyword = 0;
        UserData.Size = (unsigned __int16)*off_14000F008;
        UserData.Reserved = 2;
        v11 = byte_14000B90D;
        v12 = 61;
        v13 = 1;
        v8[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
      }
    }
LABEL_15:
    ReleaseSRWLockExclusive((PSRWLOCK)(v1 + 32));
  }
}

```

## disassembly

```asm
0x140004390  mov     r11, rsp
0x140004393  push    rbp
0x140004394  push    r14
0x140004396  sub     rsp, 0B8h
0x14000439d  mov     rax, cs:__security_cookie
0x1400043a4  xor     rax, rsp
0x1400043a7  mov     [rsp+0C8h+var_38], rax
0x1400043af  xor     r14d, r14d
0x1400043b2  cmp     cs:ServiceCount, r14d
0x1400043b9  mov     ebp, r14d
0x1400043bc  jbe     loc_14000459A
0x1400043c2  mov     [r11+8], rbx
0x1400043c6  mov     [r11+10h], rsi
0x1400043ca  mov     [r11+18h], rdi
0x1400043ce  mov     [r11-18h], r12
0x1400043d2  lea     r12, _TraceLoggingMetadataEnd
0x1400043d9  mov     [r11-20h], r13
0x1400043dd  lea     r13, _TraceLoggingMetadata
0x1400043e4  mov     [r11-28h], r15
0x1400043e8  lea     r15, byte_14000B90D
0x1400043ef  nop
0x1400043f0  mov     eax, ebp
0x1400043f2  lea     rbx, [rax+rax*2]
0x1400043f6  shl     rbx, 5
0x1400043fa  add     rbx, cs:ServiceArray
0x140004401  lea     rcx, [rbx+20h]; SRWLock
0x140004405  call    cs:__imp_AcquireSRWLockExclusive
0x14000440b  mov     rax, [rbx+8]
0x14000440f  test    rax, rax
0x140004412  jz      loc_140004552
0x140004418  cmp     [rax+10h], r14
0x14000441c  jz      loc_140004552
0x140004422  cmp     [rbx+58h], r14d
0x140004426  jz      loc_140004552
0x14000442c  nop     dword ptr [rax+00h]
0x140004430  xor     r9d, r9d; Flags
0x140004433  lea     rdx, [rbx+20h]; SRWLock
0x140004437  mov     r8d, 1388h; dwMilliseconds
0x14000443d  lea     rcx, [rbx+28h]; ConditionVariable
0x140004441  call    cs:__imp_SleepConditionVariableSRW
0x140004447  test    eax, eax
0x140004449  jz      short loc_14000445A
0x14000444b  mov     rax, [rbx+8]
0x14000444f  cmp     [rax+10h], r14
0x140004453  jnz     short loc_140004430
0x140004455  jmp     loc_140004552
0x14000445a  mov     eax, cs:dword_14000F000
0x140004460  cmp     eax, 5
0x140004463  jbe     loc_140004552
0x140004469  mov     rcx, [rbx]
0x14000446c  test    rcx, rcx
0x14000446f  jz      short loc_140004495
0x140004471  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140004478  nop     dword ptr [rax+rax+00000000h]
0x140004480  cmp     [rcx+rax*2+2], r14w
0x140004486  lea     rax, [rax+1]
0x14000448a  jnz     short loc_140004480
0x14000448c  lea     eax, ds:2[rax*2]
0x140004493  jmp     short loc_1400044A1
0x140004495  lea     rcx, aNourlmimefilte+10h; ""
0x14000449c  mov     eax, 2
0x1400044a1  mov     [rsp+0C8h+var_58], rcx
0x1400044a6  mov     [rsp+0C8h+var_50], eax
0x1400044aa  mov     [rsp+0C8h+var_4C], r14d
0x1400044af  call    cs:__imp_GetLastError
0x1400044b5  mov     [rsp+0C8h+var_40], 4
0x1400044c1  lea     rdx, [rsp+0C8h+EventDescriptor]; EventDescriptor
0x1400044c6  mov     [rsp+0C8h+var_98], eax
0x1400044ca  xor     r9d, r9d; RelatedActivityId
0x1400044cd  lea     rax, [rsp+0C8h+var_98]
0x1400044d2  mov     dword ptr [rsp+0C8h+EventDescriptor.Id], 0B000000h
0x1400044da  mov     [rsp+0C8h+var_48], rax
0x1400044e2  xor     r8d, r8d; ActivityId
0x1400044e5  movzx   eax, cs:word_14000B903
0x1400044ec  mov     dword ptr [rsp+0C8h+EventDescriptor.Level], eax
0x1400044f0  mov     rax, cs:off_14000F008
0x1400044f7  mov     [rsp+0C8h+var_78.Ptr], rax
0x1400044fc  mov     [rsp+0C8h+EventDescriptor.Keyword], r14
0x140004501  movzx   eax, word ptr [rax]
0x140004504  mov     [rsp+0C8h+var_78.Size], eax
0x140004508  mov     rax, r12
0x14000450b  sub     eax, r13d
0x14000450e  mov     dword ptr [rsp+0C8h+var_78.0Ch], 2
0x140004516  mov     [rsp+0C8h+var_68], r15
0x14000451b  mov     [rsp+0C8h+var_60], 3Dh ; '='
0x140004523  mov     [rsp+0C8h+var_5C], 1
0x14000452b  mov     [rsp+0C8h+var_94], eax
0x14000452f  mov     eax, [rsp+0C8h+var_94]
0x140004533  mov     rcx, cs:RegHandle; RegHandle
0x14000453a  lea     rax, [rsp+0C8h+var_78]
0x14000453f  mov     [rsp+0C8h+UserData], rax; UserData
0x140004544  mov     [rsp+0C8h+UserDataCount], 4; UserDataCount
0x14000454c  call    cs:__imp_EventWriteTransfer
0x140004552  lea     rcx, [rbx+20h]; SRWLock
0x140004556  call    cs:__imp_ReleaseSRWLockExclusive
0x14000455c  inc     ebp
0x14000455e  cmp     ebp, cs:ServiceCount
0x140004564  jb      loc_1400043F0
0x14000456a  mov     r15, [rsp+0C8h+var_28]
0x140004572  mov     r13, [rsp+0C8h+var_20]
0x14000457a  mov     r12, [rsp+0C8h+var_18]
0x140004582  mov     rdi, [rsp+0C8h+arg_10]
0x14000458a  mov     rsi, [rsp+0C8h+arg_8]
0x140004592  mov     rbx, [rsp+0C8h+arg_0]
0x14000459a  mov     rcx, [rsp+0C8h+var_38]
0x1400045a2  xor     rcx, rsp; StackCookie
0x1400045a5  call    __security_check_cookie
0x1400045aa  add     rsp, 0B8h
0x1400045b1  pop     r14
0x1400045b3  pop     rbp
0x1400045b4  retn
```
