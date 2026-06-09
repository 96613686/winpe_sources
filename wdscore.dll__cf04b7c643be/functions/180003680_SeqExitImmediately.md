# SeqExitImmediately

- ea: `0x180003680`
- end: `0x1800037fc`
- name: `SeqExitImmediately`
- size: `380`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18000cff0`
- `0x18000d010`

## callees

- `0x180002250`
- `0x180003680`
- `0x18000720c`
- `0x18000bca4`
- `0x18001dc70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800036b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003740`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800036b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003740`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800037e6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800037e6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800037d3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800037d3`

## string_xrefs

- `0x1800036c7`: `WdsExitImmediate already called`

## pseudocode

```c
void __fastcall SeqExitImmediately(__int64 a1, int a2)
{
  DWORD LastError; // ebx
  int *v5; // rax
  DWORD v6; // eax
  const wchar_t *v7; // r8
  int v8; // ebx
  int *v9; // rax
  LPCWSTR lpModuleName; // [rsp+88h] [rbp+0h]

  if ( IsWorkQueueAccessible((const char *)L"WdsExitImmediate") )
  {
    pLock(a1);
    if ( *(_DWORD *)(a1 + 148) )
    {
      LastError = GetLastError();
      v5 = (int *)ConstructPartialMsgW(0x4000094u, "WdsExitImmediate already called");
      WdsSetupLogMessageW(
        v5,
        589824,
        (__int64)L"D",
        0,
        0xB28u,
        L"onecore\\base\\ntsetup\\panther\\engine\\seq.c",
        L"SeqExitImmediately",
        lpModuleName,
        LastError,
        0,
        0);
    }
    else
    {
      *(_DWORD *)(a1 + 148) = 1;
      *(_DWORD *)(a1 + 156) = a2;
      v6 = GetLastError();
      v7 = L"will";
      v8 = v6;
      if ( !a2 )
        v7 = L"won't";
      v9 = (int *)ConstructPartialMsgW(
                    0x4000095u,
                    "WdsExitImmediate called!  Execution will stop, and the queue %s be saved.",
                    v7);
      WdsSetupLogMessageW(
        v9,
        589824,
        (__int64)L"D",
        0,
        0xB35u,
        L"onecore\\base\\ntsetup\\panther\\engine\\seq.c",
        L"SeqExitImmediately",
        lpModuleName,
        v8,
        0,
        0);
      SetEvent(*(HANDLE *)(a1 + 168));
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 184));
  }
}

```

## disassembly

```asm
0x180003680  push    rbx
0x180003682  push    rbp
0x180003683  push    rsi
0x180003684  push    rdi
0x180003685  sub     rsp, 68h
0x180003689  mov     rsi, rcx
0x18000368c  mov     ebp, edx
0x18000368e  lea     rcx, aWdsexitimmedia_3; "WdsExitImmediate"
0x180003695  call    IsWorkQueueAccessible
0x18000369a  test    eax, eax
0x18000369c  jz      loc_1800037F2
0x1800036a2  mov     rcx, rsi
0x1800036a5  call    pLock
0x1800036aa  cmp     dword ptr [rsi+94h], 0
0x1800036b1  jz      short loc_180003730
0x1800036b3  call    cs:__imp_GetLastError
0x1800036ba  nop     dword ptr [rax+rax+00h]
0x1800036bf  mov     rdi, [rsp+88h]
0x1800036c7  lea     rdx, aWdsexitimmedia_4; "WdsExitImmediate already called"
0x1800036ce  mov     ecx, 4000094h; unsigned int
0x1800036d3  mov     ebx, eax
0x1800036d5  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800036da  mov     [rsp+88h+var_38], 0; int
0x1800036e2  lea     r8, aD_1; "D"
0x1800036e9  mov     [rsp+88h+var_40], 0; __int64
0x1800036f2  mov     rcx, rax; int
0x1800036f5  mov     [rsp+88h+var_48], ebx; int
0x1800036f9  lea     rax, aSeqexitimmedia; "SeqExitImmediately"
0x180003700  mov     [rsp+88h+lpModuleName], rdi; lpModuleName
0x180003705  xor     r9d, r9d; int
0x180003708  mov     [rsp+88h+var_58], rax; __int64
0x18000370d  mov     edx, 90000h; int
0x180003712  lea     rax, aOnecoreBaseNts_3; "onecore\\base\\ntsetup\\panther\\engine"...
0x180003719  mov     [rsp+88h+var_60], rax; unsigned __int16 *
0x18000371e  mov     [rsp+88h+var_68], 0B28h; int
0x180003726  call    WdsSetupLogMessageW
0x18000372b  jmp     loc_1800037DF
0x180003730  mov     dword ptr [rsi+94h], 1
0x18000373a  mov     [rsi+9Ch], ebp
0x180003740  call    cs:__imp_GetLastError
0x180003747  nop     dword ptr [rax+rax+00h]
0x18000374c  mov     rdi, [rsp+88h]
0x180003754  lea     r8, aWill; "will"
0x18000375b  mov     ebx, eax
0x18000375d  lea     rdx, aWdsexitimmedia_2; "WdsExitImmediate called!  Execution wil"...
0x180003764  lea     rax, aWonT; "won't"
0x18000376b  test    ebp, ebp
0x18000376d  mov     ecx, 4000095h; unsigned int
0x180003772  cmovz   r8, rax
0x180003776  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000377b  mov     [rsp+88h+var_38], 0; int
0x180003783  lea     r8, aD_1; "D"
0x18000378a  mov     [rsp+88h+var_40], 0; __int64
0x180003793  mov     rcx, rax; int
0x180003796  mov     [rsp+88h+var_48], ebx; int
0x18000379a  lea     rax, aSeqexitimmedia; "SeqExitImmediately"
0x1800037a1  mov     [rsp+88h+lpModuleName], rdi; lpModuleName
0x1800037a6  xor     r9d, r9d; int
0x1800037a9  mov     [rsp+88h+var_58], rax; __int64
0x1800037ae  mov     edx, 90000h; int
0x1800037b3  lea     rax, aOnecoreBaseNts_3; "onecore\\base\\ntsetup\\panther\\engine"...
0x1800037ba  mov     [rsp+88h+var_60], rax; unsigned __int16 *
0x1800037bf  mov     [rsp+88h+var_68], 0B35h; int
0x1800037c7  call    WdsSetupLogMessageW
0x1800037cc  mov     rcx, [rsi+0A8h]; hEvent
0x1800037d3  call    cs:__imp_SetEvent
0x1800037da  nop     dword ptr [rax+rax+00h]
0x1800037df  lea     rcx, [rsi+0B8h]; lpCriticalSection
0x1800037e6  call    cs:__imp_LeaveCriticalSection
0x1800037ed  nop     dword ptr [rax+rax+00h]
0x1800037f2  add     rsp, 68h
0x1800037f6  pop     rdi
0x1800037f7  pop     rsi
0x1800037f8  pop     rbp
0x1800037f9  pop     rbx
0x1800037fa  retn
```
