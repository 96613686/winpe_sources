# SeqEnableExit

- ea: `0x180002f5c`
- end: `0x180003101`
- name: `SeqEnableExit`
- size: `421`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18000c080`
- `0x18000c0a0`

## callees

- `0x180002250`
- `0x180002f5c`
- `0x18000720c`
- `0x180008a6c`
- `0x18000bca4`
- `0x18001dc70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000303f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000303f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800030e9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800030e9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800030d6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800030d6`

## string_xrefs

- `0x180002fa6`: `WdsEnableExit already called`

## pseudocode

```c
void __fastcall SeqEnableExit(__int64 a1, int a2)
{
  DWORD LastError; // ebx
  int *v5; // rax
  __int64 *v6; // rcx
  __int64 NonDeletedItem; // rax
  unsigned int v8; // ebx
  DWORD v9; // eax
  const wchar_t *v10; // r9
  int v11; // edi
  int *v12; // rax
  LPCWSTR lpModuleName; // [rsp+88h] [rbp+0h]

  if ( IsWorkQueueAccessible((const char *)L"WdsEnableExit") )
  {
    pLock(a1);
    if ( *(_DWORD *)(a1 + 144) )
    {
      LastError = GetLastError();
      v5 = (int *)ConstructPartialMsgW(0x4000092u, "WdsEnableExit already called");
      WdsSetupLogMessageW(
        v5,
        589824,
        (__int64)L"D",
        0,
        0xAF9u,
        L"onecore\\base\\ntsetup\\panther\\engine\\seq.c",
        L"SeqEnableExit",
        lpModuleName,
        LastError,
        0,
        0);
    }
    else
    {
      v6 = *(__int64 **)(a1 + 56);
      *(_DWORD *)(a1 + 144) = 1;
      *(_DWORD *)(a1 + 156) = a2;
      NonDeletedItem = privateGetNonDeletedItem(*v6, 1);
      if ( NonDeletedItem )
      {
        v8 = *(_DWORD *)(NonDeletedItem + 56);
        *(_DWORD *)(a1 + 152) = v8;
        v9 = GetLastError();
        v10 = L"will";
        v11 = v9;
        if ( !a2 )
          v10 = L"won't";
        v12 = (int *)ConstructPartialMsgW(
                       0x4000093u,
                       "WdsEnableExit called!  When group #%d is empty, execution will stop, and the queue %s be saved.",
                       v8,
                       v10);
        WdsSetupLogMessageW(
          v12,
          589824,
          (__int64)L"D",
          0,
          0xB0Fu,
          L"onecore\\base\\ntsetup\\panther\\engine\\seq.c",
          L"SeqEnableExit",
          lpModuleName,
          v11,
          0,
          0);
        SetEvent(*(HANDLE *)(a1 + 168));
      }
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 184));
  }
}

```

## disassembly

```asm
0x180002f5c  push    rbx
0x180002f5e  push    rbp
0x180002f5f  push    rsi
0x180002f60  push    rdi
0x180002f61  push    r14
0x180002f63  sub     rsp, 60h
0x180002f67  mov     rbp, rcx
0x180002f6a  mov     r14d, edx
0x180002f6d  lea     rcx, aWdsenableexit_0; "WdsEnableExit"
0x180002f74  call    IsWorkQueueAccessible
0x180002f79  test    eax, eax
0x180002f7b  jz      loc_1800030F5
0x180002f81  mov     rcx, rbp
0x180002f84  call    pLock
0x180002f89  cmp     dword ptr [rbp+90h], 0
0x180002f90  jz      short loc_18000300F
0x180002f92  call    cs:__imp_GetLastError
0x180002f99  nop     dword ptr [rax+rax+00h]
0x180002f9e  mov     rdi, [rsp+88h]
0x180002fa6  lea     rdx, aWdsenableexitA; "WdsEnableExit already called"
0x180002fad  mov     ecx, 4000092h; unsigned int
0x180002fb2  mov     ebx, eax
0x180002fb4  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180002fb9  mov     [rsp+88h+var_38], 0; int
0x180002fc1  lea     r8, aD_1; "D"
0x180002fc8  mov     [rsp+88h+var_40], 0; __int64
0x180002fd1  mov     rcx, rax; int
0x180002fd4  mov     [rsp+88h+var_48], ebx; int
0x180002fd8  lea     rax, aSeqenableexit; "SeqEnableExit"
0x180002fdf  mov     [rsp+88h+lpModuleName], rdi; lpModuleName
0x180002fe4  xor     r9d, r9d; int
0x180002fe7  mov     [rsp+88h+var_58], rax; __int64
0x180002fec  mov     edx, 90000h; int
0x180002ff1  lea     rax, aOnecoreBaseNts_3; "onecore\\base\\ntsetup\\panther\\engine"...
0x180002ff8  mov     [rsp+88h+var_60], rax; unsigned __int16 *
0x180002ffd  mov     [rsp+88h+var_68], 0AF9h; int
0x180003005  call    WdsSetupLogMessageW
0x18000300a  jmp     loc_1800030E2
0x18000300f  mov     rcx, [rbp+38h]
0x180003013  mov     edx, 1
0x180003018  mov     [rbp+90h], edx
0x18000301e  mov     [rbp+9Ch], r14d
0x180003025  mov     rcx, [rcx]
0x180003028  call    privateGetNonDeletedItem
0x18000302d  test    rax, rax
0x180003030  jz      loc_1800030E2
0x180003036  mov     ebx, [rax+38h]
0x180003039  mov     [rbp+98h], ebx
0x18000303f  call    cs:__imp_GetLastError
0x180003046  nop     dword ptr [rax+rax+00h]
0x18000304b  mov     rsi, [rsp+88h]
0x180003053  lea     r9, aWill; "will"
0x18000305a  mov     edi, eax
0x18000305c  lea     rdx, aWdsenableexitC; "WdsEnableExit called!  When group #%d i"...
0x180003063  lea     rax, aWonT; "won't"
0x18000306a  test    r14d, r14d
0x18000306d  mov     r8d, ebx
0x180003070  mov     ecx, 4000093h; unsigned int
0x180003075  cmovz   r9, rax
0x180003079  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000307e  mov     [rsp+88h+var_38], 0; int
0x180003086  lea     r8, aD_1; "D"
0x18000308d  mov     [rsp+88h+var_40], 0; __int64
0x180003096  mov     rcx, rax; int
0x180003099  mov     [rsp+88h+var_48], edi; int
0x18000309d  lea     rax, aSeqenableexit; "SeqEnableExit"
0x1800030a4  mov     [rsp+88h+lpModuleName], rsi; lpModuleName
0x1800030a9  xor     r9d, r9d; int
0x1800030ac  mov     [rsp+88h+var_58], rax; __int64
0x1800030b1  mov     edx, 90000h; int
0x1800030b6  lea     rax, aOnecoreBaseNts_3; "onecore\\base\\ntsetup\\panther\\engine"...
0x1800030bd  mov     [rsp+88h+var_60], rax; unsigned __int16 *
0x1800030c2  mov     [rsp+88h+var_68], 0B0Fh; int
0x1800030ca  call    WdsSetupLogMessageW
0x1800030cf  mov     rcx, [rbp+0A8h]; hEvent
0x1800030d6  call    cs:__imp_SetEvent
0x1800030dd  nop     dword ptr [rax+rax+00h]
0x1800030e2  lea     rcx, [rbp+0B8h]; lpCriticalSection
0x1800030e9  call    cs:__imp_LeaveCriticalSection
0x1800030f0  nop     dword ptr [rax+rax+00h]
0x1800030f5  add     rsp, 60h
0x1800030f9  pop     r14
0x1800030fb  pop     rdi
0x1800030fc  pop     rsi
0x1800030fd  pop     rbp
0x1800030fe  pop     rbx
0x1800030ff  retn
```
