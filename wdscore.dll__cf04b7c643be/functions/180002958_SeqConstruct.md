# SeqConstruct

- ea: `0x180002958`
- end: `0x180002c45`
- name: `SeqConstruct`
- size: `749`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `2`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x18000a6b8`
- `0x18000a8f0`

## callees

- `0x1800021c4`
- `0x180002218`
- `0x180002250`
- `0x180002958`
- `0x180002d14`
- `0x180009a04`
- `0x180009aec`
- `0x18001dc70`
- `0x180021ed8`
- `0x180022300`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800029c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002bbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800029c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002bbe`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002a33`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002aea`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002b09`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002a33`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002aea`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002b09`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800029ac`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800029ac`

## pseudocode

```c
__int64 __fastcall SeqConstruct(unsigned __int16 *a1)
{
  __int64 v2; // r14
  __int64 v3; // rsi
  __int64 v4; // rax
  DWORD LastError; // ebx
  int v6; // eax
  __int64 v7; // rax
  __int64 v8; // rax
  int v9; // ebx
  DWORD v10; // ebx
  int v11; // eax
  LPCWSTR lpModuleName; // [rsp+98h] [rbp+0h]

  v2 = 0;
  v3 = ConstructListItem(272);
  if ( v3 )
  {
    v4 = DuplicateTextW(a1);
    *(_QWORD *)(v3 + 264) = v4;
    if ( v4 )
    {
      InitializeCriticalSection((LPCRITICAL_SECTION)(v3 + 184));
      LastError = GetLastError();
      v6 = (unsigned int)ConstructPartialMsgW(0x4000000u, "InitializedCriticalSection for pExecQueue->csLock;");
      WdsSetupLogMessageW(
        v6,
        589824,
        (int)L"D",
        0,
        1862,
        L"onecore\\base\\ntsetup\\panther\\engine\\seq.c",
        (__int64)L"SeqConstruct",
        lpModuleName,
        LastError,
        0,
        0);
      *(_QWORD *)(v3 + 168) = CreateEventW(0, 0, 0, 0);
      v7 = ConstructList(pDestructModule, pSerializeModule);
      *(_QWORD *)(v3 + 40) = v7;
      if ( v7 )
      {
        v8 = ConstructList(pDestructGroup, pSerializeGroup);
        *(_QWORD *)(v3 + 56) = v8;
        if ( v8 )
        {
          *(_DWORD *)(v8 + 36) = 1;
          *(_QWORD *)(v3 + 64) = HtAllocEx(0, 8);
          *(_QWORD *)(v3 + 72) = ConstructList(pDestructGroup, pSerializeGroup);
          *(_QWORD *)(v3 + 80) = HtAllocEx(0, 8);
          v9 = SC_Construct(v3 + 104);
          *(_QWORD *)(v3 + 128) = HtAllocEx(1, 8);
          *(_QWORD *)(v3 + 240) = CreateEventW(0, 0, 0, 0);
          *(_QWORD *)(v3 + 248) = CreateEventW(0, 1, 1, 0);
          *(_QWORD *)(v3 + 224) = ConstructList(pDestructEvent, pSerializeEvent);
          *(_DWORD *)(v3 + 232) = 0;
          if ( *(_QWORD *)(v3 + 264)
            && *(_QWORD *)(v3 + 168)
            && *(_QWORD *)(v3 + 40)
            && *(_QWORD *)(v3 + 56)
            && *(_QWORD *)(v3 + 64)
            && *(_QWORD *)(v3 + 72)
            && *(_QWORD *)(v3 + 80)
            && *(_QWORD *)(v3 + 128)
            && v9
            && *(_QWORD *)(v3 + 240)
            && *(_QWORD *)(v3 + 248)
            && *(_QWORD *)(v3 + 224)
            && (unsigned int)SC_GetID(v3 + 104, L"SEQ Control") )
          {
            v2 = v3;
            v3 = 0;
          }
          else
          {
            v10 = GetLastError();
            v11 = (unsigned int)ConstructPartialMsgW(
                                  0x2000080u,
                                  "There was a problem creating a PEXEC_QUEUE_LIST_ITEM member");
            WdsSetupLogMessageW(
              v11,
              589824,
              (int)L"D",
              0,
              1944,
              L"onecore\\base\\ntsetup\\panther\\engine\\seq.c",
              (__int64)L"SeqConstruct",
              lpModuleName,
              v10,
              0,
              0);
          }
        }
      }
    }
  }
  if ( v3 )
    SeqDestruct((LPVOID)v3);
  return v2;
}

```

## disassembly

```asm
0x180002958  push    rbx
0x18000295a  push    rsi
0x18000295b  push    rdi
0x18000295c  push    r13
0x18000295e  push    r14
0x180002960  sub     rsp, 70h
0x180002964  mov     rbx, rcx
0x180002967  xor     r13d, r13d
0x18000296a  mov     [rsp+98h+var_38], r13
0x18000296f  mov     r14d, r13d
0x180002972  mov     ecx, 110h
0x180002977  call    ConstructListItem
0x18000297c  mov     rsi, rax
0x18000297f  mov     [rsp+98h+var_38], rax
0x180002984  test    rax, rax
0x180002987  jz      loc_180002C28
0x18000298d  mov     rcx, rbx; unsigned __int16 *
0x180002990  call    DuplicateTextW
0x180002995  mov     [rsi+108h], rax
0x18000299c  test    rax, rax
0x18000299f  jz      loc_180002C28
0x1800029a5  lea     rcx, [rsi+0B8h]; lpCriticalSection
0x1800029ac  call    cs:__imp_InitializeCriticalSection
0x1800029b3  nop     dword ptr [rax+rax+00h]
0x1800029b8  mov     rdi, [rsp+98h]
0x1800029c0  call    cs:__imp_GetLastError
0x1800029c7  nop     dword ptr [rax+rax+00h]
0x1800029cc  mov     ebx, eax
0x1800029ce  lea     rdx, aInitializedcri; "InitializedCriticalSection for pExecQue"...
0x1800029d5  mov     ecx, 4000000h; unsigned int
0x1800029da  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800029df  mov     rcx, rax; int
0x1800029e2  mov     [rsp+98h+var_48], r13d; int
0x1800029e7  mov     [rsp+98h+var_50], r13; __int64
0x1800029ec  mov     [rsp+98h+var_58], ebx; int
0x1800029f0  mov     [rsp+98h+lpModuleName], rdi; lpModuleName
0x1800029f5  lea     rax, aSeqconstruct; "SeqConstruct"
0x1800029fc  mov     [rsp+98h+var_68], rax; __int64
0x180002a01  lea     rax, aOnecoreBaseNts_3; "onecore\\base\\ntsetup\\panther\\engine"...
0x180002a08  mov     [rsp+98h+var_70], rax; unsigned __int16 *
0x180002a0d  mov     [rsp+98h+var_78], 746h; int
0x180002a15  xor     r9d, r9d; int
0x180002a18  lea     r8, aD_1; "D"
0x180002a1f  mov     edx, 90000h; int
0x180002a24  call    WdsSetupLogMessageW
0x180002a29  xor     r9d, r9d; lpName
0x180002a2c  xor     r8d, r8d; bInitialState
0x180002a2f  xor     edx, edx; bManualReset
0x180002a31  xor     ecx, ecx; lpEventAttributes
0x180002a33  call    cs:__imp_CreateEventW
0x180002a3a  nop     dword ptr [rax+rax+00h]
0x180002a3f  mov     [rsi+0A8h], rax
0x180002a46  lea     rdx, pSerializeModule
0x180002a4d  lea     rcx, pDestructModule
0x180002a54  call    ConstructList
0x180002a59  mov     [rsi+28h], rax
0x180002a5d  test    rax, rax
0x180002a60  jz      loc_180002C28
0x180002a66  lea     rdx, pSerializeGroup
0x180002a6d  lea     rcx, pDestructGroup
0x180002a74  call    ConstructList
0x180002a79  mov     [rsi+38h], rax
0x180002a7d  test    rax, rax
0x180002a80  jz      loc_180002C28
0x180002a86  mov     dword ptr [rax+24h], 1
0x180002a8d  lea     edx, [r13+8]
0x180002a91  xor     ecx, ecx
0x180002a93  call    HtAllocEx
0x180002a98  mov     [rsi+40h], rax
0x180002a9c  lea     rdx, pSerializeGroup
0x180002aa3  lea     rcx, pDestructGroup
0x180002aaa  call    ConstructList
0x180002aaf  mov     [rsi+48h], rax
0x180002ab3  lea     edx, [r13+8]
0x180002ab7  xor     ecx, ecx
0x180002ab9  call    HtAllocEx
0x180002abe  mov     [rsi+50h], rax
0x180002ac2  lea     rcx, [rsi+68h]
0x180002ac6  call    SC_Construct
0x180002acb  mov     ebx, eax
0x180002acd  lea     edx, [r13+8]
0x180002ad1  lea     ecx, [rdx-7]
0x180002ad4  call    HtAllocEx
0x180002ad9  mov     [rsi+80h], rax
0x180002ae0  xor     r9d, r9d; lpName
0x180002ae3  xor     r8d, r8d; bInitialState
0x180002ae6  xor     edx, edx; bManualReset
0x180002ae8  xor     ecx, ecx; lpEventAttributes
0x180002aea  call    cs:__imp_CreateEventW
0x180002af1  nop     dword ptr [rax+rax+00h]
0x180002af6  mov     [rsi+0F0h], rax
0x180002afd  xor     r9d, r9d; lpName
0x180002b00  lea     edx, [r13+1]; bManualReset
0x180002b04  xor     ecx, ecx; lpEventAttributes
0x180002b06  mov     r8d, edx; bInitialState
0x180002b09  call    cs:__imp_CreateEventW
0x180002b10  nop     dword ptr [rax+rax+00h]
0x180002b15  mov     [rsi+0F8h], rax
0x180002b1c  lea     rdx, pSerializeEvent
0x180002b23  lea     rcx, pDestructEvent
0x180002b2a  call    ConstructList
0x180002b2f  mov     [rsi+0E0h], rax
0x180002b36  mov     [rsi+0E8h], r13d
0x180002b3d  cmp     [rsi+108h], r13
0x180002b44  jz      short loc_180002BB6
0x180002b46  cmp     [rsi+0A8h], r13
0x180002b4d  jz      short loc_180002BB6
0x180002b4f  cmp     [rsi+28h], r13
0x180002b53  jz      short loc_180002BB6
0x180002b55  cmp     [rsi+38h], r13
0x180002b59  jz      short loc_180002BB6
0x180002b5b  cmp     [rsi+40h], r13
0x180002b5f  jz      short loc_180002BB6
0x180002b61  cmp     [rsi+48h], r13
0x180002b65  jz      short loc_180002BB6
0x180002b67  cmp     [rsi+50h], r13
0x180002b6b  jz      short loc_180002BB6
0x180002b6d  cmp     [rsi+80h], r13
0x180002b74  jz      short loc_180002BB6
0x180002b76  test    ebx, ebx
0x180002b78  jz      short loc_180002BB6
0x180002b7a  cmp     [rsi+0F0h], r13
0x180002b81  jz      short loc_180002BB6
0x180002b83  cmp     [rsi+0F8h], r13
0x180002b8a  jz      short loc_180002BB6
0x180002b8c  cmp     [rsi+0E0h], r13
0x180002b93  jz      short loc_180002BB6
0x180002b95  lea     rdx, aSeqControl; "SEQ Control"
0x180002b9c  lea     rcx, [rsi+68h]
0x180002ba0  call    SC_GetID
0x180002ba5  test    eax, eax
0x180002ba7  jz      short loc_180002BB6
0x180002ba9  mov     r14, rsi
0x180002bac  mov     esi, r13d
0x180002baf  mov     [rsp+98h+var_38], r13
0x180002bb4  jmp     short loc_180002C28
0x180002bb6  mov     rdi, [rsp+98h]
0x180002bbe  call    cs:__imp_GetLastError
0x180002bc5  nop     dword ptr [rax+rax+00h]
0x180002bca  mov     ebx, eax
0x180002bcc  lea     rdx, aThereWasAProbl; "There was a problem creating a PEXEC_QU"...
0x180002bd3  mov     ecx, 2000080h; unsigned int
0x180002bd8  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180002bdd  mov     rcx, rax; int
0x180002be0  mov     [rsp+98h+var_48], r13d; int
0x180002be5  mov     [rsp+98h+var_50], r13; __int64
0x180002bea  mov     [rsp+98h+var_58], ebx; int
0x180002bee  mov     [rsp+98h+lpModuleName], rdi; lpModuleName
0x180002bf3  lea     rax, aSeqconstruct; "SeqConstruct"
0x180002bfa  mov     [rsp+98h+var_68], rax; __int64
0x180002bff  lea     rax, aOnecoreBaseNts_3; "onecore\\base\\ntsetup\\panther\\engine"...
0x180002c06  mov     [rsp+98h+var_70], rax; unsigned __int16 *
0x180002c0b  mov     [rsp+98h+var_78], 798h; int
0x180002c13  xor     r9d, r9d; int
0x180002c16  lea     r8, aD_1; "D"
0x180002c1d  mov     edx, 90000h; int
0x180002c22  call    WdsSetupLogMessageW
0x180002c27  nop
0x180002c28  test    rsi, rsi
0x180002c2b  jz      short loc_180002C35
0x180002c2d  mov     rcx, rsi; lpMem
0x180002c30  call    SeqDestruct
0x180002c35  mov     rax, r14
0x180002c38  add     rsp, 70h
0x180002c3c  pop     r14
0x180002c3e  pop     r13
0x180002c40  pop     rdi
0x180002c41  pop     rsi
0x180002c42  pop     rbx
0x180002c43  retn
0x180027a91  push    rbp
0x180027a93  sub     rsp, 60h
0x180027a97  mov     rbp, rdx
0x180027a9a  mov     rcx, [rbp+60h]; lpMem
0x180027a9e  test    rcx, rcx
0x180027aa1  jz      short loc_180027AA9
0x180027aa3  call    SeqDestruct
0x180027aa8  nop
0x180027aa9  add     rsp, 60h
0x180027aad  pop     rbp
0x180027aae  retn
```
