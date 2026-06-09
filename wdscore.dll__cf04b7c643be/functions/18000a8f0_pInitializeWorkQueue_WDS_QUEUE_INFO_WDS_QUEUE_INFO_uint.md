# pInitializeWorkQueue(WDS_QUEUE_INFO *,WDS_QUEUE_INFO *,uint)

- ea: `0x18000a8f0`
- end: `0x18000ad27`
- name: `?pInitializeWorkQueue@@YAHPEAUWDS_QUEUE_INFO@@0I@Z`
- size: `1079`
- prototype: `__int64 __fastcall(struct WDS_QUEUE_INFO *, struct WDS_QUEUE_INFO *, unsigned int)`
- caller_count: `2`
- callee_count: `12`
- tags: `installer_update`

## callers

- `0x18000c1a0`
- `0x18000c850`

## callees

- `0x180002250`
- `0x180002958`
- `0x180002d14`
- `0x180005e18`
- `0x18000a8f0`
- `0x18001dc70`
- `0x180022214`
- `0x180022300`
- `0x1800223a4`
- `0x1800224f8`
- `0x1800274de`
- `0x180027510`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a9c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aa5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aaf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000abc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a9c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aa5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aaf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000abc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac65`

## string_xrefs

- `0x18000a9d9`: `Failed to create online queue name`
- `0x18000abea`: `The names of all offline queues and offline groups must be unique.  '%s' is already used`

## pseudocode

```c
__int64 __fastcall pInitializeWorkQueue(struct WDS_QUEUE_INFO *a1, struct WDS_QUEUE_INFO *a2, int a3)
{
  unsigned int v7; // esi
  DWORD v8; // ebx
  int *v9; // rax
  DWORD v10; // ebx
  int *v11; // rax
  DWORD v12; // ebx
  int *v13; // rax
  __int64 v14; // rdx
  unsigned int v15; // ebx
  __int64 v16; // r14
  unsigned int i; // edi
  __int64 v18; // r15
  DWORD LastError; // ebx
  int *v20; // rax
  DWORD v21; // ebx
  int *v22; // rax
  __int64 v23; // [rsp+70h] [rbp-268h] BYREF
  unsigned __int16 v24[264]; // [rsp+80h] [rbp-258h] BYREF
  LPCWSTR lpModuleName; // [rsp+2D8h] [rbp+0h]

  memset_0(v24, 0, 0x208u);
  if ( !dword_18003B258 )
    return 0;
  v7 = 0;
  if ( g_WorkQueue )
  {
    ++g_WorkQueue;
    return 1;
  }
  else
  {
    if ( (int)StringCchPrintfW(v24, 0x104u, L"%s%s", *(_QWORD *)a1, L"Online") >= 0 )
    {
      lpMem = (LPVOID)SeqConstruct(v24);
      if ( lpMem )
      {
        qword_18003AF70 = (__int64)a2;
        dword_18003AF78 = a3;
        qword_18003AF68 = HtAllocEx(0, 8);
        if ( qword_18003AF68 )
        {
          v14 = qword_18003AF70;
          if ( !qword_18003AF70 )
            goto LABEL_27;
          v15 = 0;
LABEL_17:
          if ( v15 < dword_18003AF78 )
          {
            v16 = 32LL * v15;
            *(_QWORD *)(v16 + v14 + 24) = 0;
            v23 = v16 + v14;
            for ( i = 0; ; ++i )
            {
              if ( i >= *(_DWORD *)(v16 + v14 + 16) )
              {
                ++v15;
                goto LABEL_17;
              }
              v18 = 32LL * v15;
              if ( (unsigned int)HtFindStringExW(qword_18003AF68, *(_QWORD *)(*(_QWORD *)(v16 + v14 + 8) + 8LL * i), 0) )
              {
                _mm_lfence();
                LastError = GetLastError();
                v20 = (int *)ConstructPartialMsgW(
                               0x2000021u,
                               "The names of all offline queues and offline groups must be unique.  '%s' is already used",
                               *(const char **)(*(_QWORD *)(v18 + qword_18003AF70 + 8) + 8LL * i));
                WdsSetupLogMessageW(
                  v20,
                  589824,
                  (__int64)L"D",
                  0,
                  0x538u,
                  L"onecore\\base\\ntsetup\\panther\\engine\\engine.cpp",
                  L"pInitializeWorkQueue",
                  lpModuleName,
                  LastError,
                  0,
                  0);
                goto LABEL_28;
              }
              if ( !(unsigned int)HtAddStringExW(
                                    qword_18003AF68,
                                    *(_QWORD *)(*(_QWORD *)(v18 + qword_18003AF70 + 8) + 8LL * i),
                                    &v23) )
                break;
              v14 = qword_18003AF70;
            }
            if ( g_bEnableDiagnosticMode )
            {
              v21 = GetLastError();
              v22 = (int *)ConstructPartialMsgW(0x6B000000u, "Failed to add to WorkQueue->OfflineQueuesTable");
              WdsSetupLogMessageW(
                v22,
                589824,
                (__int64)L"D",
                0,
                0x541u,
                L"onecore\\base\\ntsetup\\panther\\engine\\engine.cpp",
                L"pInitializeWorkQueue",
                lpModuleName,
                v21,
                0,
                0);
            }
          }
          else
          {
LABEL_27:
            ++g_WorkQueue;
            v7 = 1;
          }
        }
        else if ( g_bEnableDiagnosticMode )
        {
          v12 = GetLastError();
          v13 = (int *)ConstructPartialMsgW(0x6B000000u, "Failed to alloc WorkQueue->OfflineQueuesTable");
          WdsSetupLogMessageW(
            v13,
            589824,
            (__int64)L"D",
            0,
            0x526u,
            L"onecore\\base\\ntsetup\\panther\\engine\\engine.cpp",
            L"pInitializeWorkQueue",
            lpModuleName,
            v12,
            0,
            0);
        }
      }
      else if ( g_bEnableDiagnosticMode )
      {
        v10 = GetLastError();
        v11 = (int *)ConstructPartialMsgW(0x6B000000u, "Failed to initialize SEQ");
        WdsSetupLogMessageW(
          v11,
          589824,
          (__int64)L"D",
          0,
          0x51Cu,
          L"onecore\\base\\ntsetup\\panther\\engine\\engine.cpp",
          L"pInitializeWorkQueue",
          lpModuleName,
          v10,
          0,
          0);
      }
    }
    else if ( g_bEnableDiagnosticMode )
    {
      v8 = GetLastError();
      v9 = (int *)ConstructPartialMsgW(0x6B000000u, "Failed to create online queue name");
      WdsSetupLogMessageW(
        v9,
        589824,
        (__int64)L"D",
        0,
        0x515u,
        L"onecore\\base\\ntsetup\\panther\\engine\\engine.cpp",
        L"pInitializeWorkQueue",
        lpModuleName,
        v8,
        0,
        0);
    }
LABEL_28:
    if ( !v7 )
    {
      if ( lpMem )
      {
        SeqDestruct((char *)lpMem);
        lpMem = 0;
      }
      if ( qword_18003AF68 )
      {
        HtFree(qword_18003AF68);
        qword_18003AF68 = 0;
      }
    }
    return v7;
  }
}

```

## disassembly

```asm
0x18000a8f0  push    rbx
0x18000a8f2  push    rsi
0x18000a8f3  push    rdi
0x18000a8f4  push    r12
0x18000a8f6  push    r13
0x18000a8f8  push    r14
0x18000a8fa  push    r15
0x18000a8fc  sub     rsp, 2A0h
0x18000a903  mov     rax, cs:__security_cookie
0x18000a90a  xor     rax, rsp
0x18000a90d  mov     [rsp+2D8h+var_48], rax
0x18000a915  mov     edi, r8d
0x18000a918  mov     rbx, rdx
0x18000a91b  mov     r14, rcx
0x18000a91e  xor     edx, edx; Val
0x18000a920  mov     r8d, 208h; Size
0x18000a926  lea     rcx, [rsp+2D8h+var_258]; void *
0x18000a92e  call    memset_0
0x18000a933  xor     r13d, r13d
0x18000a936  cmp     cs:dword_18003B258, r13d
0x18000a93d  jnz     short loc_18000A965
0x18000a93f  xor     eax, eax
0x18000a941  mov     rcx, [rsp+2D8h+var_48]
0x18000a949  xor     rcx, rsp; StackCookie
0x18000a94c  call    __security_check_cookie
0x18000a951  add     rsp, 2A0h
0x18000a958  pop     r15
0x18000a95a  pop     r14
0x18000a95c  pop     r13
0x18000a95e  pop     r12
0x18000a960  pop     rdi
0x18000a961  pop     rsi
0x18000a962  pop     rbx
0x18000a963  retn
0x18000a965  mov     esi, r13d
0x18000a968  mov     [rsp+2D8h+var_278], r13d
0x18000a96d  mov     eax, cs:?g_WorkQueue@@3UWORK_QUEUE@@A; WORK_QUEUE g_WorkQueue
0x18000a973  test    eax, eax
0x18000a975  jz      short loc_18000A986
0x18000a977  inc     eax
0x18000a979  mov     cs:?g_WorkQueue@@3UWORK_QUEUE@@A, eax; WORK_QUEUE g_WorkQueue
0x18000a97f  mov     eax, 1
0x18000a984  jmp     short loc_18000A941
0x18000a986  lea     rax, aOnline; "Online"
0x18000a98d  mov     qword ptr [rsp+2D8h+var_2B8], rax
0x18000a992  mov     r9, [r14]
0x18000a995  lea     r8, aSS; "%s%s"
0x18000a99c  mov     edx, 104h; unsigned __int64
0x18000a9a1  lea     rcx, [rsp+2D8h+var_258]; unsigned __int16 *
0x18000a9a9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a9ae  test    eax, eax
0x18000a9b0  jns     loc_18000AA39
0x18000a9b6  cmp     cs:?g_bEnableDiagnosticMode@@3HA, r13d; int g_bEnableDiagnosticMode
0x18000a9bd  jz      loc_18000ACEC
0x18000a9c3  call    cs:__imp_GetLastError
0x18000a9ca  nop     dword ptr [rax+rax+00h]
0x18000a9cf  mov     ebx, eax
0x18000a9d1  mov     rdi, [rsp+2D8h]
0x18000a9d9  lea     rdx, aFailedToCreate; "Failed to create online queue name"
0x18000a9e0  mov     ecx, 6B000000h; unsigned int
0x18000a9e5  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000a9ea  mov     [rsp+2D8h+var_288], r13d; int
0x18000a9ef  mov     [rsp+2D8h+var_290], r13; __int64
0x18000a9f4  mov     [rsp+2D8h+var_298], ebx; int
0x18000a9f8  mov     [rsp+2D8h+lpModuleName], rdi; lpModuleName
0x18000a9fd  lea     rcx, aPinitializewor; "pInitializeWorkQueue"
0x18000aa04  mov     [rsp+2D8h+var_2A8], rcx; __int64
0x18000aa09  lea     rcx, aOnecoreBaseNts_1; "onecore\\base\\ntsetup\\panther\\engine"...
0x18000aa10  mov     [rsp+2D8h+var_2B0], rcx; unsigned __int16 *
0x18000aa15  mov     [rsp+2D8h+var_2B8], 515h; int
0x18000aa1d  xor     r9d, r9d; int
0x18000aa20  lea     r8, aD_1; "D"
0x18000aa27  mov     edx, 90000h; int
0x18000aa2c  mov     rcx, rax; int
0x18000aa2f  call    WdsSetupLogMessageW
0x18000aa34  jmp     loc_18000ACEC
0x18000aa39  lea     rcx, [rsp+2D8h+var_258]; unsigned __int16 *
0x18000aa41  call    SeqConstruct
0x18000aa46  mov     cs:lpMem, rax
0x18000aa4d  test    rax, rax
0x18000aa50  jnz     short loc_18000AABE
0x18000aa52  cmp     cs:?g_bEnableDiagnosticMode@@3HA, r13d; int g_bEnableDiagnosticMode
0x18000aa59  jz      loc_18000ACEC
0x18000aa5f  call    cs:__imp_GetLastError
0x18000aa66  nop     dword ptr [rax+rax+00h]
0x18000aa6b  mov     ebx, eax
0x18000aa6d  mov     rdi, [rsp+2D8h]
0x18000aa75  lea     rdx, aFailedToInitia; "Failed to initialize SEQ"
0x18000aa7c  mov     ecx, 6B000000h; unsigned int
0x18000aa81  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000aa86  mov     [rsp+2D8h+var_288], r13d
0x18000aa8b  mov     [rsp+2D8h+var_290], r13
0x18000aa90  mov     [rsp+2D8h+var_298], ebx
0x18000aa94  mov     [rsp+2D8h+lpModuleName], rdi
0x18000aa99  lea     rcx, aPinitializewor; "pInitializeWorkQueue"
0x18000aaa0  mov     [rsp+2D8h+var_2A8], rcx
0x18000aaa5  lea     rcx, aOnecoreBaseNts_1; "onecore\\base\\ntsetup\\panther\\engine"...
0x18000aaac  mov     [rsp+2D8h+var_2B0], rcx
0x18000aab1  mov     [rsp+2D8h+var_2B8], 51Ch
0x18000aab9  jmp     loc_18000AA1D
0x18000aabe  mov     cs:qword_18003AF70, rbx
0x18000aac5  mov     cs:dword_18003AF78, edi
0x18000aacb  mov     edx, 8
0x18000aad0  xor     ecx, ecx
0x18000aad2  call    HtAllocEx
0x18000aad7  mov     cs:qword_18003AF68, rax
0x18000aade  test    rax, rax
0x18000aae1  jnz     short loc_18000AB4F
0x18000aae3  cmp     cs:?g_bEnableDiagnosticMode@@3HA, r13d; int g_bEnableDiagnosticMode
0x18000aaea  jz      loc_18000ACEC
0x18000aaf0  call    cs:__imp_GetLastError
0x18000aaf7  nop     dword ptr [rax+rax+00h]
0x18000aafc  mov     ebx, eax
0x18000aafe  mov     rdi, [rsp+2D8h]
0x18000ab06  lea     rdx, aFailedToAllocW; "Failed to alloc WorkQueue->OfflineQueue"...
0x18000ab0d  mov     ecx, 6B000000h; unsigned int
0x18000ab12  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000ab17  mov     [rsp+2D8h+var_288], r13d
0x18000ab1c  mov     [rsp+2D8h+var_290], r13
0x18000ab21  mov     [rsp+2D8h+var_298], ebx
0x18000ab25  mov     [rsp+2D8h+lpModuleName], rdi
0x18000ab2a  lea     rcx, aPinitializewor; "pInitializeWorkQueue"
0x18000ab31  mov     [rsp+2D8h+var_2A8], rcx
0x18000ab36  lea     rcx, aOnecoreBaseNts_1; "onecore\\base\\ntsetup\\panther\\engine"...
0x18000ab3d  mov     [rsp+2D8h+var_2B0], rcx
0x18000ab42  mov     [rsp+2D8h+var_2B8], 526h
0x18000ab4a  jmp     loc_18000AA1D
0x18000ab4f  mov     rdx, cs:qword_18003AF70
0x18000ab56  test    rdx, rdx
0x18000ab59  jz      loc_18000ACDD
0x18000ab5f  mov     ebx, r13d
0x18000ab62  mov     [rsp+2D8h+var_270], ebx
0x18000ab66  cmp     ebx, cs:dword_18003AF78
0x18000ab6c  jnb     loc_18000ACDD
0x18000ab72  mov     r14d, ebx
0x18000ab75  shl     r14, 5
0x18000ab79  lea     rax, [r14+rdx]
0x18000ab7d  mov     [rax+18h], r13
0x18000ab81  mov     [rsp+2D8h+var_268], rax
0x18000ab86  mov     edi, r13d
0x18000ab89  mov     [rsp+2D8h+var_274], r13d
0x18000ab8e  cmp     edi, [r14+rdx+10h]
0x18000ab93  jnb     loc_18000ACD6
0x18000ab99  mov     r15d, ebx
0x18000ab9c  shl     r15, 5
0x18000aba0  mov     r12d, edi
0x18000aba3  mov     eax, edi
0x18000aba5  mov     rdx, [r14+rdx+8]
0x18000abaa  xor     r8d, r8d
0x18000abad  mov     rdx, [rdx+rax*8]
0x18000abb1  mov     rcx, cs:qword_18003AF68
0x18000abb8  call    HtFindStringExW
0x18000abbd  test    eax, eax
0x18000abbf  jz      short loc_18000AC33
0x18000abc1  lfence
0x18000abc4  call    cs:__imp_GetLastError
0x18000abcb  nop     dword ptr [rax+rax+00h]
0x18000abd0  mov     ebx, eax
0x18000abd2  mov     rdi, [rsp+2D8h]
0x18000abda  mov     rax, cs:qword_18003AF70
0x18000abe1  mov     r8, [r15+rax+8]
0x18000abe6  mov     r8, [r8+r12*8]
0x18000abea  lea     rdx, aTheNamesOfAllO; "The names of all offline queues and off"...
0x18000abf1  mov     ecx, 2000021h; unsigned int
0x18000abf6  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000abfb  mov     [rsp+2D8h+var_288], r13d
0x18000ac00  mov     [rsp+2D8h+var_290], r13
0x18000ac05  mov     [rsp+2D8h+var_298], ebx
0x18000ac09  mov     [rsp+2D8h+lpModuleName], rdi
0x18000ac0e  lea     rcx, aPinitializewor; "pInitializeWorkQueue"
0x18000ac15  mov     [rsp+2D8h+var_2A8], rcx
0x18000ac1a  lea     rcx, aOnecoreBaseNts_1; "onecore\\base\\ntsetup\\panther\\engine"...
0x18000ac21  mov     [rsp+2D8h+var_2B0], rcx
0x18000ac26  mov     [rsp+2D8h+var_2B8], 538h
0x18000ac2e  jmp     loc_18000AA1D
0x18000ac33  mov     rax, cs:qword_18003AF70
0x18000ac3a  mov     rdx, [r15+rax+8]
0x18000ac3f  lea     r8, [rsp+2D8h+var_268]
0x18000ac44  mov     rdx, [rdx+r12*8]
0x18000ac48  mov     rcx, cs:qword_18003AF68
0x18000ac4f  call    HtAddStringExW
0x18000ac54  test    eax, eax
0x18000ac56  jnz     short loc_18000ACC4
0x18000ac58  cmp     cs:?g_bEnableDiagnosticMode@@3HA, r13d; int g_bEnableDiagnosticMode
0x18000ac5f  jz      loc_18000ACEC
0x18000ac65  call    cs:__imp_GetLastError
0x18000ac6c  nop     dword ptr [rax+rax+00h]
0x18000ac71  mov     ebx, eax
0x18000ac73  mov     rdi, [rsp+2D8h]
0x18000ac7b  lea     rdx, aFailedToAddToW; "Failed to add to WorkQueue->OfflineQueu"...
0x18000ac82  mov     ecx, 6B000000h; unsigned int
0x18000ac87  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000ac8c  mov     [rsp+2D8h+var_288], r13d
0x18000ac91  mov     [rsp+2D8h+var_290], r13
0x18000ac96  mov     [rsp+2D8h+var_298], ebx
0x18000ac9a  mov     [rsp+2D8h+lpModuleName], rdi
0x18000ac9f  lea     rcx, aPinitializewor; "pInitializeWorkQueue"
0x18000aca6  mov     [rsp+2D8h+var_2A8], rcx
0x18000acab  lea     rcx, aOnecoreBaseNts_1; "onecore\\base\\ntsetup\\panther\\engine"...
0x18000acb2  mov     [rsp+2D8h+var_2B0], rcx
0x18000acb7  mov     [rsp+2D8h+var_2B8], 541h
0x18000acbf  jmp     loc_18000AA1D
0x18000acc4  inc     edi
0x18000acc6  mov     [rsp+2D8h+var_274], edi
0x18000acca  mov     rdx, cs:qword_18003AF70
0x18000acd1  jmp     loc_18000AB8E
0x18000acd6  inc     ebx
0x18000acd8  jmp     loc_18000AB62
0x18000acdd  inc     cs:?g_WorkQueue@@3UWORK_QUEUE@@A; WORK_QUEUE g_WorkQueue
0x18000ace3  mov     esi, 1
0x18000ace8  mov     [rsp+2D8h+var_278], esi
0x18000acec  test    esi, esi
0x18000acee  jnz     short loc_18000AD20
0x18000acf0  mov     rcx, cs:lpMem; lpMem
0x18000acf7  test    rcx, rcx
0x18000acfa  jz      short loc_18000AD08
0x18000acfc  call    SeqDestruct
0x18000ad01  mov     cs:lpMem, r13
0x18000ad08  mov     rcx, cs:qword_18003AF68
0x18000ad0f  test    rcx, rcx
0x18000ad12  jz      short loc_18000AD20
0x18000ad14  call    HtFree
0x18000ad19  mov     cs:qword_18003AF68, r13
0x18000ad20  mov     eax, esi
0x18000ad22  jmp     loc_18000A941
0x18002835b  push    rbp
0x18002835d  sub     rsp, 60h
0x180028361  mov     rbp, rdx
0x180028364  cmp     dword ptr [rbp+60h], 0
0x180028368  jnz     short loc_1800283A2
0x18002836a  mov     rcx, cs:lpMem; lpMem
0x180028371  test    rcx, rcx
0x180028374  jz      short loc_180028386
0x180028376  call    SeqDestruct
0x18002837b  mov     cs:lpMem, 0
0x180028386  mov     rcx, cs:qword_18003AF68
0x18002838d  test    rcx, rcx
0x180028390  jz      short loc_1800283A2
0x180028392  call    HtFree
0x180028397  mov     cs:qword_18003AF68, 0
0x1800283a2  add     rsp, 60h
0x1800283a6  pop     rbp
0x1800283a7  retn
```
