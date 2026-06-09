# WaitForServiceDllsToUnload

- ea: `0x140004720`
- end: `0x140004958`
- name: `WaitForServiceDllsToUnload`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x140002cb0`

## callees

- `0x140004720`
- `0x140004f90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000483f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000483f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1400048e2`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1400048e2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140004795`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140004795`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400048f2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400048f2`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x1400047d3`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x1400047d3`

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
  void *v11; // [rsp+60h] [rbp-68h]
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
        UserData.Size = *(unsigned __int16 *)off_14000F008;
        UserData.Reserved = 2;
        v11 = &unk_14000B90D;
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
0x140004720  mov     r11, rsp
0x140004723  push    rbp
0x140004724  push    r14
0x140004726  sub     rsp, 0B8h
0x14000472d  mov     rax, cs:__security_cookie
0x140004734  xor     rax, rsp
0x140004737  mov     [rsp+0C8h+var_38], rax
0x14000473f  xor     r14d, r14d
0x140004742  cmp     cs:ServiceCount, r14d
0x140004749  mov     ebp, r14d
0x14000474c  jbe     loc_14000493C
0x140004752  mov     [r11+8], rbx
0x140004756  mov     [r11+10h], rsi
0x14000475a  mov     [r11+18h], rdi
0x14000475e  mov     [r11-18h], r12
0x140004762  lea     r12, _TraceLoggingMetadataEnd
0x140004769  mov     [r11-20h], r13
0x14000476d  lea     r13, _TraceLoggingMetadata
0x140004774  mov     [r11-28h], r15
0x140004778  lea     r15, unk_14000B90D
0x14000477f  nop
0x140004780  mov     eax, ebp
0x140004782  lea     rbx, [rax+rax*2]
0x140004786  shl     rbx, 5
0x14000478a  add     rbx, cs:ServiceArray
0x140004791  lea     rcx, [rbx+20h]; SRWLock
0x140004795  call    cs:__imp_AcquireSRWLockExclusive
0x14000479c  nop     dword ptr [rax+rax+00h]
0x1400047a1  mov     rax, [rbx+8]
0x1400047a5  test    rax, rax
0x1400047a8  jz      loc_1400048EE
0x1400047ae  cmp     [rax+10h], r14
0x1400047b2  jz      loc_1400048EE
0x1400047b8  cmp     [rbx+58h], r14d
0x1400047bc  jz      loc_1400048EE
0x1400047c2  xor     r9d, r9d; Flags
0x1400047c5  lea     rdx, [rbx+20h]; SRWLock
0x1400047c9  mov     r8d, 1388h; dwMilliseconds
0x1400047cf  lea     rcx, [rbx+28h]; ConditionVariable
0x1400047d3  call    cs:__imp_SleepConditionVariableSRW
0x1400047da  nop     dword ptr [rax+rax+00h]
0x1400047df  test    eax, eax
0x1400047e1  jz      short loc_1400047F2
0x1400047e3  mov     rax, [rbx+8]
0x1400047e7  cmp     [rax+10h], r14
0x1400047eb  jnz     short loc_1400047C2
0x1400047ed  jmp     loc_1400048EE
0x1400047f2  mov     eax, cs:dword_14000F000
0x1400047f8  cmp     eax, 5
0x1400047fb  jbe     loc_1400048EE
0x140004801  mov     rcx, [rbx]
0x140004804  test    rcx, rcx
0x140004807  jz      short loc_140004825
0x140004809  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140004810  cmp     [rcx+rax*2+2], r14w
0x140004816  lea     rax, [rax+1]
0x14000481a  jnz     short loc_140004810
0x14000481c  lea     eax, ds:2[rax*2]
0x140004823  jmp     short loc_140004831
0x140004825  lea     rcx, aNourlmimefilte+10h; ""
0x14000482c  mov     eax, 2
0x140004831  mov     [rsp+0C8h+var_58], rcx
0x140004836  mov     [rsp+0C8h+var_50], eax
0x14000483a  mov     [rsp+0C8h+var_4C], r14d
0x14000483f  call    cs:__imp_GetLastError
0x140004846  nop     dword ptr [rax+rax+00h]
0x14000484b  mov     [rsp+0C8h+var_40], 4
0x140004857  lea     rdx, [rsp+0C8h+EventDescriptor]; EventDescriptor
0x14000485c  mov     [rsp+0C8h+var_98], eax
0x140004860  xor     r9d, r9d; RelatedActivityId
0x140004863  lea     rax, [rsp+0C8h+var_98]
0x140004868  mov     dword ptr [rsp+0C8h+EventDescriptor.Id], 0B000000h
0x140004870  mov     [rsp+0C8h+var_48], rax
0x140004878  xor     r8d, r8d; ActivityId
0x14000487b  movzx   eax, cs:word_14000B903
0x140004882  mov     dword ptr [rsp+0C8h+EventDescriptor.Level], eax
0x140004886  mov     rax, cs:off_14000F008
0x14000488d  mov     [rsp+0C8h+var_78.Ptr], rax
0x140004892  mov     [rsp+0C8h+EventDescriptor.Keyword], r14
0x140004897  movzx   eax, word ptr [rax]
0x14000489a  mov     [rsp+0C8h+var_78.Size], eax
0x14000489e  mov     rax, r12
0x1400048a1  sub     eax, r13d
0x1400048a4  mov     dword ptr [rsp+0C8h+var_78.0Ch], 2
0x1400048ac  mov     [rsp+0C8h+var_68], r15
0x1400048b1  mov     [rsp+0C8h+var_60], 3Dh ; '='
0x1400048b9  mov     [rsp+0C8h+var_5C], 1
0x1400048c1  mov     [rsp+0C8h+var_94], eax
0x1400048c5  mov     eax, [rsp+0C8h+var_94]
0x1400048c9  mov     rcx, cs:RegHandle; RegHandle
0x1400048d0  lea     rax, [rsp+0C8h+var_78]
0x1400048d5  mov     [rsp+0C8h+UserData], rax; UserData
0x1400048da  mov     [rsp+0C8h+UserDataCount], 4; UserDataCount
0x1400048e2  call    cs:__imp_EventWriteTransfer
0x1400048e9  nop     dword ptr [rax+rax+00h]
0x1400048ee  lea     rcx, [rbx+20h]; SRWLock
0x1400048f2  call    cs:__imp_ReleaseSRWLockExclusive
0x1400048f9  nop     dword ptr [rax+rax+00h]
0x1400048fe  inc     ebp
0x140004900  cmp     ebp, cs:ServiceCount
0x140004906  jb      loc_140004780
0x14000490c  mov     r15, [rsp+0C8h+var_28]
0x140004914  mov     r13, [rsp+0C8h+var_20]
0x14000491c  mov     r12, [rsp+0C8h+var_18]
0x140004924  mov     rdi, [rsp+0C8h+arg_10]
0x14000492c  mov     rsi, [rsp+0C8h+arg_8]
0x140004934  mov     rbx, [rsp+0C8h+arg_0]
0x14000493c  mov     rcx, [rsp+0C8h+var_38]
0x140004944  xor     rcx, rsp; StackCookie
0x140004947  call    __security_check_cookie
0x14000494c  add     rsp, 0B8h
0x140004953  pop     r14
0x140004955  pop     rbp
0x140004956  retn
```
