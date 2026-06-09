# SeqSetNextExecutionGroup

- ea: `0x180004e6c`
- end: `0x1800051cd`
- name: `SeqSetNextExecutionGroup`
- size: `865`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000ddd0`

## callees

- `0x180002250`
- `0x180002344`
- `0x180004e6c`
- `0x180007184`
- `0x18000720c`
- `0x1800072c4`
- `0x180008a6c`
- `0x180008abc`
- `0x180008b00`
- `0x18000bca4`
- `0x18001dc70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ed0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004f8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000500a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800050cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000511a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ed0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004f8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000500a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800050cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000511a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800051ae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800051ae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027d50`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004eb8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004eb8`

## string_xrefs

- `0x180004ede`: `Attempt to use SeqSetNextExecutionGroup from another thread`
- `0x1800050db`: `Failed to backup PERMANENT event during SetNextExecutionGroup!!`
- `0x180005128`: `Successfully backed up PERMANENT event during SetNextExecutionGroup`

## pseudocode

```c
__int64 __fastcall SeqSetNextExecutionGroup(__int64 a1, const char *a2)
{
  unsigned int v4; // edi
  __int64 result; // rax
  int v6; // ebx
  DWORD v7; // ebx
  int v8; // eax
  __int64 v9; // r13
  __int64 NonDeletedItem; // rax
  __int64 v11; // r14
  DWORD v12; // ebx
  int v13; // eax
  DWORD LastError; // ebx
  int v15; // eax
  __int64 i; // rbx
  __int64 v17; // rax
  unsigned int v18; // r10d
  __int64 v19; // rdx
  DWORD v20; // ebx
  int v21; // eax
  DWORD v22; // ebx
  int v23; // eax
  __int64 NextListItem; // [rsp+60h] [rbp-48h]
  LPCWSTR lpModuleName; // [rsp+A8h] [rbp+0h]
  __int64 v27; // [rsp+C8h] [rbp+20h]

  v4 = 0;
  result = IsWorkQueueAccessible(L"WdsSetNextExecutionGroup");
  if ( (_DWORD)result )
  {
    pLock(a1);
    v6 = *(_DWORD *)(a1 + 176);
    if ( GetCurrentThreadId() == v6 )
    {
      v9 = pLookupGroupByName(a1, a2);
      NonDeletedItem = privateGetNonDeletedItem(**(_QWORD **)(a1 + 56), 1);
      v11 = NonDeletedItem;
      if ( !v9 || !NonDeletedItem )
        goto LABEL_23;
      if ( !*(_DWORD *)(a1 + 160) || v9 == NonDeletedItem )
      {
        while ( v11 != v9 )
        {
          if ( !v11 )
          {
            LastError = GetLastError();
            v15 = (unsigned int)ConstructPartialMsgW(0x200007Du, "Group: %s not found! (SEQ5)", a2);
            WdsSetupLogMessageW(
              v15,
              589824,
              (int)L"D",
              0,
              1745,
              L"onecore\\base\\ntsetup\\panther\\engine\\seq.c",
              (__int64)L"SeqSetNextExecutionGroup",
              lpModuleName,
              LastError,
              0,
              0);
            goto LABEL_4;
          }
          NextListItem = GetNextListItem(v11);
          for ( i = privateGetNonDeletedItem(**(_QWORD **)(v11 + 40), 1); i; i = v17 )
          {
            v17 = GetNextListItem(i);
            v27 = v17;
            if ( *(_DWORD *)(i + 96) )
            {
              DelinkListItem(*(_QWORD *)i, i);
              if ( (unsigned int)pInsertEvent(*(_QWORD *)(a1 + 72), v19, v18, 0) )
              {
                v22 = GetLastError();
                v23 = (unsigned int)ConstructPartialMsgW(
                                      0x400007Fu,
                                      "Successfully backed up PERMANENT event during SetNextExecutionGroup");
                WdsSetupLogMessageW(
                  v23,
                  589824,
                  (int)L"D",
                  0,
                  1778,
                  L"onecore\\base\\ntsetup\\panther\\engine\\seq.c",
                  (__int64)L"SeqSetNextExecutionGroup",
                  lpModuleName,
                  v22,
                  0,
                  0);
              }
              else
              {
                v20 = GetLastError();
                v21 = (unsigned int)ConstructPartialMsgW(
                                      0x200007Eu,
                                      "Failed to backup PERMANENT event during SetNextExecutionGroup!!");
                WdsSetupLogMessageW(
                  v21,
                  589824,
                  (int)L"D",
                  0,
                  1774,
                  L"onecore\\base\\ntsetup\\panther\\engine\\seq.c",
                  (__int64)L"SeqSetNextExecutionGroup",
                  lpModuleName,
                  v20,
                  0,
                  0);
              }
              v17 = v27;
            }
          }
          DeleteListItem(*(_QWORD *)(a1 + 56), v11);
          v11 = NextListItem;
        }
        v4 = 1;
        goto LABEL_23;
      }
      v12 = GetLastError();
      v13 = (unsigned int)ConstructPartialMsgW(
                            0x300007Cu,
                            "WdsSetNextExecutionGroup failed - the queue is currently locked");
      WdsSetupLogMessageW(
        v13,
        589824,
        (int)L"D",
        0,
        1737,
        L"onecore\\base\\ntsetup\\panther\\engine\\seq.c",
        (__int64)L"SeqSetNextExecutionGroup",
        lpModuleName,
        v12,
        0,
        0);
    }
    else
    {
      v7 = GetLastError();
      v8 = (unsigned int)ConstructPartialMsgW(0x300007Bu, "Attempt to use SeqSetNextExecutionGroup from another thread");
      WdsSetupLogMessageW(
        v8,
        589824,
        (int)L"D",
        0,
        1723,
        L"onecore\\base\\ntsetup\\panther\\engine\\seq.c",
        (__int64)L"SeqSetNextExecutionGroup",
        lpModuleName,
        v7,
        0,
        0);
    }
LABEL_4:
    v4 = 0;
LABEL_23:
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 184));
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x180004e6c  mov     rax, rsp
0x180004e6f  mov     [rax+10h], rdx
0x180004e73  mov     [rax+8], rcx
0x180004e77  push    rbx
0x180004e78  push    rsi
0x180004e79  push    rdi
0x180004e7a  push    r12
0x180004e7c  push    r13
0x180004e7e  push    r14
0x180004e80  push    r15
0x180004e82  sub     rsp, 70h
0x180004e86  mov     r14, rdx
0x180004e89  mov     rsi, rcx
0x180004e8c  xor     r15d, r15d
0x180004e8f  mov     edi, r15d
0x180004e92  mov     [rax+18h], r15d
0x180004e96  lea     rcx, aWdssetnextexec_1; "WdsSetNextExecutionGroup"
0x180004e9d  call    IsWorkQueueAccessible
0x180004ea2  test    eax, eax
0x180004ea4  jz      loc_1800051BC
0x180004eaa  mov     rcx, rsi
0x180004ead  call    pLock
0x180004eb2  mov     ebx, [rsi+0B0h]
0x180004eb8  call    cs:__imp_GetCurrentThreadId
0x180004ebf  nop     dword ptr [rax+rax+00h]
0x180004ec4  cmp     eax, ebx
0x180004ec6  jz      short loc_180004F45
0x180004ec8  mov     rdi, [rsp+0A8h]
0x180004ed0  call    cs:__imp_GetLastError
0x180004ed7  nop     dword ptr [rax+rax+00h]
0x180004edc  mov     ebx, eax
0x180004ede  lea     rdx, aAttemptToUseSe_1; "Attempt to use SeqSetNextExecutionGroup"...
0x180004ee5  mov     ecx, 300007Bh; unsigned int
0x180004eea  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180004eef  mov     [rsp+0A8h+var_58], r15d; int
0x180004ef4  mov     [rsp+0A8h+var_60], r15; __int64
0x180004ef9  mov     [rsp+0A8h+var_68], ebx; int
0x180004efd  mov     [rsp+0A8h+lpModuleName], rdi; lpModuleName
0x180004f02  lea     r15, aSeqsetnextexec; "SeqSetNextExecutionGroup"
0x180004f09  mov     [rsp+0A8h+var_78], r15; __int64
0x180004f0e  lea     r12, aOnecoreBaseNts_3; "onecore\\base\\ntsetup\\panther\\engine"...
0x180004f15  mov     [rsp+0A8h+var_80], r12; unsigned __int16 *
0x180004f1a  mov     [rsp+0A8h+var_88], 6BBh; int
0x180004f22  mov     rcx, rax; int
0x180004f25  xor     r9d, r9d; int
0x180004f28  lea     r8, aD_1; "D"
0x180004f2f  mov     edx, 90000h; int
0x180004f34  call    WdsSetupLogMessageW
0x180004f39  mov     edi, [rsp+0A8h+arg_10]
0x180004f40  jmp     loc_1800051A7
0x180004f45  mov     rdx, r14
0x180004f48  mov     rcx, rsi
0x180004f4b  call    pLookupGroupByName
0x180004f50  mov     r13, rax
0x180004f53  mov     rcx, [rsi+38h]
0x180004f57  mov     edx, 1
0x180004f5c  mov     rcx, [rcx]
0x180004f5f  call    privateGetNonDeletedItem
0x180004f64  mov     r14, rax
0x180004f67  test    r13, r13
0x180004f6a  jz      loc_1800051A7
0x180004f70  test    rax, rax
0x180004f73  jz      loc_1800051A7
0x180004f79  cmp     [rsi+0A0h], r15d
0x180004f80  jz      short loc_180004FE6
0x180004f82  cmp     r13, rax
0x180004f85  jz      short loc_180004FE6
0x180004f87  mov     rdi, [rsp+0A8h]
0x180004f8f  call    cs:__imp_GetLastError
0x180004f96  nop     dword ptr [rax+rax+00h]
0x180004f9b  mov     ebx, eax
0x180004f9d  lea     rdx, aWdssetnextexec_0; "WdsSetNextExecutionGroup failed - the q"...
0x180004fa4  mov     ecx, 300007Ch; unsigned int
0x180004fa9  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180004fae  mov     [rsp+0A8h+var_58], r15d
0x180004fb3  mov     [rsp+0A8h+var_60], r15
0x180004fb8  mov     [rsp+0A8h+var_68], ebx
0x180004fbc  mov     [rsp+0A8h+lpModuleName], rdi
0x180004fc1  lea     r15, aSeqsetnextexec; "SeqSetNextExecutionGroup"
0x180004fc8  mov     [rsp+0A8h+var_78], r15
0x180004fcd  lea     r12, aOnecoreBaseNts_3; "onecore\\base\\ntsetup\\panther\\engine"...
0x180004fd4  mov     [rsp+0A8h+var_80], r12
0x180004fd9  mov     [rsp+0A8h+var_88], 6C9h
0x180004fe1  jmp     loc_180004F22
0x180004fe6  lea     r15, aSeqsetnextexec; "SeqSetNextExecutionGroup"
0x180004fed  lea     r12, aOnecoreBaseNts_3; "onecore\\base\\ntsetup\\panther\\engine"...
0x180004ff4  cmp     r14, r13
0x180004ff7  jz      loc_1800051A2
0x180004ffd  test    r14, r14
0x180005000  jnz     short loc_18000505B
0x180005002  mov     rdi, [rsp+0A8h]
0x18000500a  call    cs:__imp_GetLastError
0x180005011  nop     dword ptr [rax+rax+00h]
0x180005016  mov     ebx, eax
0x180005018  mov     r8, [rsp+0A8h+arg_8]
0x180005020  lea     rdx, aGroupSNotFound; "Group: %s not found! (SEQ5)"
0x180005027  mov     ecx, 200007Dh; unsigned int
0x18000502c  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180005031  mov     [rsp+0A8h+var_58], r14d
0x180005036  mov     [rsp+0A8h+var_60], r14
0x18000503b  mov     [rsp+0A8h+var_68], ebx
0x18000503f  mov     [rsp+0A8h+lpModuleName], rdi
0x180005044  mov     [rsp+0A8h+var_78], r15
0x180005049  mov     [rsp+0A8h+var_80], r12
0x18000504e  mov     [rsp+0A8h+var_88], 6D1h
0x180005056  jmp     loc_180004F22
0x18000505b  mov     rcx, r14
0x18000505e  call    GetNextListItem
0x180005063  mov     [rsp+0A8h+var_48], rax
0x180005068  mov     rcx, [r14+28h]
0x18000506c  mov     edx, 1
0x180005071  mov     rcx, [rcx]
0x180005074  call    privateGetNonDeletedItem
0x180005079  mov     rbx, rax
0x18000507c  test    rbx, rbx
0x18000507f  jz      loc_18000518C
0x180005085  mov     rcx, rbx
0x180005088  call    GetNextListItem
0x18000508d  mov     [rsp+0A8h+arg_18], rax
0x180005095  cmp     dword ptr [rbx+60h], 0
0x180005099  jz      loc_180005184
0x18000509f  mov     rcx, [rbx+48h]
0x1800050a3  mov     r10d, [rcx+38h]
0x1800050a7  mov     rdx, rbx
0x1800050aa  mov     rcx, [rbx]
0x1800050ad  call    DelinkListItem
0x1800050b2  xor     r9d, r9d
0x1800050b5  mov     r8d, r10d
0x1800050b8  mov     rcx, [rsi+48h]
0x1800050bc  call    pInsertEvent
0x1800050c1  mov     rdi, [rsp+0A8h]
0x1800050c9  test    eax, eax
0x1800050cb  jnz     short loc_18000511A
0x1800050cd  call    cs:__imp_GetLastError
0x1800050d4  nop     dword ptr [rax+rax+00h]
0x1800050d9  mov     ebx, eax
0x1800050db  lea     rdx, aFailedToBackup; "Failed to backup PERMANENT event during"...
0x1800050e2  mov     ecx, 200007Eh; unsigned int
0x1800050e7  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800050ec  mov     [rsp+0A8h+var_58], 0
0x1800050f4  mov     [rsp+0A8h+var_60], 0
0x1800050fd  mov     [rsp+0A8h+var_68], ebx
0x180005101  mov     [rsp+0A8h+lpModuleName], rdi
0x180005106  mov     [rsp+0A8h+var_78], r15
0x18000510b  mov     [rsp+0A8h+var_80], r12
0x180005110  mov     [rsp+0A8h+var_88], 6EEh
0x180005118  jmp     short loc_180005165
0x18000511a  call    cs:__imp_GetLastError
0x180005121  nop     dword ptr [rax+rax+00h]
0x180005126  mov     ebx, eax
0x180005128  lea     rdx, aSuccessfullyBa_0; "Successfully backed up PERMANENT event "...
0x18000512f  mov     ecx, 400007Fh; unsigned int
0x180005134  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180005139  mov     [rsp+0A8h+var_58], 0; int
0x180005141  mov     [rsp+0A8h+var_60], 0; __int64
0x18000514a  mov     [rsp+0A8h+var_68], ebx; int
0x18000514e  mov     [rsp+0A8h+lpModuleName], rdi; lpModuleName
0x180005153  mov     [rsp+0A8h+var_78], r15; __int64
0x180005158  mov     [rsp+0A8h+var_80], r12; unsigned __int16 *
0x18000515d  mov     [rsp+0A8h+var_88], 6F2h; int
0x180005165  xor     r9d, r9d; int
0x180005168  lea     r8, aD_1; "D"
0x18000516f  mov     edx, 90000h; int
0x180005174  mov     rcx, rax; int
0x180005177  call    WdsSetupLogMessageW
0x18000517c  mov     rax, [rsp+0A8h+arg_18]
0x180005184  mov     rbx, rax
0x180005187  jmp     loc_18000507C
0x18000518c  mov     rdx, r14
0x18000518f  mov     rcx, [rsi+38h]
0x180005193  call    DeleteListItem
0x180005198  mov     r14, [rsp+0A8h+var_48]
0x18000519d  jmp     loc_180004FF4
0x1800051a2  mov     edi, 1
0x1800051a7  lea     rcx, [rsi+0B8h]; lpCriticalSection
0x1800051ae  call    cs:__imp_LeaveCriticalSection
0x1800051b5  nop     dword ptr [rax+rax+00h]
0x1800051ba  mov     eax, edi
0x1800051bc  add     rsp, 70h
0x1800051c0  pop     r15
0x1800051c2  pop     r14
0x1800051c4  pop     r13
0x1800051c6  pop     r12
0x1800051c8  pop     rdi
0x1800051c9  pop     rsi
0x1800051ca  pop     rbx
0x1800051cb  retn
0x180027d34  push    rbp
0x180027d36  sub     rsp, 60h
0x180027d3a  mov     rbp, rdx
0x180027d3d  mov     rcx, [rbp+0B0h]
0x180027d44  add     rcx, 0B8h
0x180027d4b  add     rsp, 60h
0x180027d4f  pop     rbp
0x180027d50  jmp     cs:__imp_LeaveCriticalSection
```
