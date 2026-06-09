# pWorkerThreadFunc

- ea: `0x1800087e0`
- end: `0x180008a64`
- name: `pWorkerThreadFunc`
- size: `644`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update`

## callees

- `0x180001f24`
- `0x180002250`
- `0x180006740`
- `0x18000720c`
- `0x18000859c`
- `0x1800087e0`
- `0x180008a6c`
- `0x180008b00`
- `0x18001dc70`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008929`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800089a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008929`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800089a6`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180008836`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180008836`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800088d4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000890c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008a40`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800088d4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000890c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008a40`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800088a1`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800088a1`

## string_xrefs

- `0x18000896f`: `pWorkerThreadFunc`
- `0x1800089ec`: `pWorkerThreadFunc`
- `0x1800089ba`: `pWorkerThreadFunc -- Stopping`
- `0x18000893d`: `pWorkerThreadFunc -- WaitForMultipleObjects failed`

## pseudocode

```c
__int64 __fastcall pWorkerThreadFunc(char *Parameter)
{
  struct _RTL_CRITICAL_SECTION *v1; // r14
  struct _RTL_CRITICAL_SECTION *v3; // rbp
  DWORD v4; // eax
  __int64 NonDeletedItem; // rax
  _QWORD *v6; // rbx
  unsigned int v7; // edi
  void (__fastcall *v8)(_QWORD, _QWORD *, _QWORD); // rax
  DWORD v9; // ebx
  int *v10; // rax
  DWORD LastError; // ebx
  int *v12; // rax
  int v13; // eax
  HANDLE Handles[2]; // [rsp+60h] [rbp-28h] BYREF
  LPCWSTR lpModuleName; // [rsp+88h] [rbp+0h]
  struct CONTENTS_FILE *v17; // [rsp+90h] [rbp+8h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)(Parameter + 184);
  Handles[0] = *((HANDLE *)Parameter + 30);
  v3 = (struct _RTL_CRITICAL_SECTION *)(Parameter + 184);
  Handles[1] = *((HANDLE *)Parameter + 31);
  v17 = 0;
  while ( 1 )
  {
    v4 = WaitForMultipleObjectsEx(2u, Handles, 0, 0xFFFFFFFF, 0);
    if ( v4 )
      break;
    pLock(Parameter);
    NonDeletedItem = privateGetNonDeletedItem(**((_QWORD **)Parameter + 28), 1);
    v6 = (_QWORD *)NonDeletedItem;
    if ( NonDeletedItem )
    {
      DelinkListItem(*((_QWORD *)Parameter + 28), NonDeletedItem);
      if ( privateGetNonDeletedItem(**((_QWORD **)Parameter + 28), 1) )
        SetEvent(*((HANDLE *)Parameter + 30));
      pSetUILanguage((__int64)Parameter, &v17);
      v3 = (struct _RTL_CRITICAL_SECTION *)(Parameter + 184);
      v7 = CallSubscribers(Parameter);
      LeaveCriticalSection((LPCRITICAL_SECTION)(Parameter + 184));
      v8 = (void (__fastcall *)(_QWORD, _QWORD *, _QWORD))v6[10];
      if ( v8 )
        v8(v7, v6 + 6, v6[11]);
      pDestructEvent(v6);
    }
    else
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)(Parameter + 184));
      v3 = (struct _RTL_CRITICAL_SECTION *)(Parameter + 184);
    }
  }
  if ( v4 == 1 )
  {
    LastError = GetLastError();
    v12 = (int *)ConstructPartialMsgW(0x4000086u, "pWorkerThreadFunc -- Stopping");
    WdsSetupLogMessageW(
      v12,
      589824,
      (__int64)L"D",
      0,
      0x98Du,
      L"onecore\\base\\ntsetup\\panther\\engine\\seq.c",
      L"pWorkerThreadFunc",
      lpModuleName,
      LastError,
      0,
      0);
    pLock(Parameter);
    v13 = *((_DWORD *)Parameter + 58);
    if ( v13 )
      *((_DWORD *)Parameter + 58) = v13 - 1;
    else
      v1 = v3;
    LeaveCriticalSection(v1);
  }
  else
  {
    v9 = GetLastError();
    v10 = (int *)ConstructPartialMsgW(0x2000087u, "pWorkerThreadFunc -- WaitForMultipleObjects failed");
    WdsSetupLogMessageW(
      v10,
      589824,
      (__int64)L"D",
      0,
      0x998u,
      L"onecore\\base\\ntsetup\\panther\\engine\\seq.c",
      L"pWorkerThreadFunc",
      lpModuleName,
      v9,
      0,
      0);
  }
  return 0;
}

```

## disassembly

```asm
0x1800087e0  mov     r11, rsp
0x1800087e3  mov     [r11+10h], rbx
0x1800087e7  mov     [r11+18h], rbp
0x1800087eb  push    rsi
0x1800087ec  push    rdi
0x1800087ed  push    r14
0x1800087ef  sub     rsp, 70h
0x1800087f3  mov     rax, [rcx+0F0h]
0x1800087fa  lea     r14, [rcx+0B8h]
0x180008801  mov     [r11-28h], rax
0x180008805  mov     rsi, rcx
0x180008808  mov     rax, [rcx+0F8h]
0x18000880f  mov     rbp, r14
0x180008812  mov     [r11-20h], rax
0x180008816  mov     qword ptr [r11+8], 0
0x18000881e  xor     r8d, r8d; bWaitAll
0x180008821  mov     [rsp+88h+bAlertable], 0; bAlertable
0x180008829  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18000882d  lea     rdx, [rsp+88h+Handles]; lpHandles
0x180008832  lea     ecx, [r8+2]; nCount
0x180008836  call    cs:__imp_WaitForMultipleObjectsEx
0x18000883d  nop     dword ptr [rax+rax+00h]
0x180008842  test    eax, eax
0x180008844  jnz     loc_180008924
0x18000884a  mov     rcx, rsi
0x18000884d  call    pLock
0x180008852  mov     rcx, [rsi+0E0h]
0x180008859  mov     edx, 1
0x18000885e  mov     rcx, [rcx]
0x180008861  call    privateGetNonDeletedItem
0x180008866  mov     rbx, rax
0x180008869  test    rax, rax
0x18000886c  jz      loc_180008905
0x180008872  mov     rcx, [rsi+0E0h]
0x180008879  mov     rdx, rax
0x18000887c  call    DelinkListItem
0x180008881  mov     rcx, [rsi+0E0h]
0x180008888  mov     edx, 1
0x18000888d  mov     rcx, [rcx]
0x180008890  call    privateGetNonDeletedItem
0x180008895  test    rax, rax
0x180008898  jz      short loc_1800088AD
0x18000889a  mov     rcx, [rsi+0F0h]; hEvent
0x1800088a1  call    cs:__imp_SetEvent
0x1800088a8  nop     dword ptr [rax+rax+00h]
0x1800088ad  lea     rdx, [rsp+88h+arg_0]
0x1800088b5  mov     rcx, rsi
0x1800088b8  call    pSetUILanguage
0x1800088bd  mov     rdx, rbx
0x1800088c0  mov     rcx, rsi
0x1800088c3  call    CallSubscribers
0x1800088c8  lea     rbp, [rsi+0B8h]
0x1800088cf  mov     edi, eax
0x1800088d1  mov     rcx, rbp; lpCriticalSection
0x1800088d4  call    cs:__imp_LeaveCriticalSection
0x1800088db  nop     dword ptr [rax+rax+00h]
0x1800088e0  mov     rax, [rbx+50h]
0x1800088e4  test    rax, rax
0x1800088e7  jz      short loc_1800088F8
0x1800088e9  mov     r8, [rbx+58h]
0x1800088ed  lea     rdx, [rbx+30h]
0x1800088f1  mov     ecx, edi
0x1800088f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088f8  mov     rcx, rbx; lpMem
0x1800088fb  call    pDestructEvent
0x180008900  jmp     loc_18000881E
0x180008905  lea     rcx, [rsi+0B8h]; lpCriticalSection
0x18000890c  call    cs:__imp_LeaveCriticalSection
0x180008913  nop     dword ptr [rax+rax+00h]
0x180008918  lea     rbp, [rsi+0B8h]
0x18000891f  jmp     loc_18000881E
0x180008924  cmp     eax, 1
0x180008927  jz      short loc_1800089A6
0x180008929  call    cs:__imp_GetLastError
0x180008930  nop     dword ptr [rax+rax+00h]
0x180008935  mov     rdi, [rsp+88h]
0x18000893d  lea     rdx, aPworkerthreadf; "pWorkerThreadFunc -- WaitForMultipleObj"...
0x180008944  mov     ecx, 2000087h; unsigned int
0x180008949  mov     ebx, eax
0x18000894b  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180008950  mov     [rsp+88h+var_38], 0; int
0x180008958  lea     r8, aD_1; "D"
0x18000895f  mov     [rsp+88h+var_40], 0; __int64
0x180008968  mov     rcx, rax; int
0x18000896b  mov     [rsp+88h+var_48], ebx; int
0x18000896f  lea     rax, aPworkerthreadf_1; "pWorkerThreadFunc"
0x180008976  mov     [rsp+88h+lpModuleName], rdi; lpModuleName
0x18000897b  xor     r9d, r9d; int
0x18000897e  mov     [rsp+88h+var_58], rax; __int64
0x180008983  mov     edx, 90000h; int
0x180008988  lea     rax, aOnecoreBaseNts_3; "onecore\\base\\ntsetup\\panther\\engine"...
0x18000898f  mov     [rsp+88h+var_60], rax; unsigned __int16 *
0x180008994  mov     [rsp+88h+bAlertable], 998h; int
0x18000899c  call    WdsSetupLogMessageW
0x1800089a1  jmp     loc_180008A4C
0x1800089a6  call    cs:__imp_GetLastError
0x1800089ad  nop     dword ptr [rax+rax+00h]
0x1800089b2  mov     rdi, [rsp+88h]
0x1800089ba  lea     rdx, aPworkerthreadf_0; "pWorkerThreadFunc -- Stopping"
0x1800089c1  mov     ecx, 4000086h; unsigned int
0x1800089c6  mov     ebx, eax
0x1800089c8  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800089cd  mov     [rsp+88h+var_38], 0; int
0x1800089d5  lea     r8, aD_1; "D"
0x1800089dc  mov     [rsp+88h+var_40], 0; __int64
0x1800089e5  mov     rcx, rax; int
0x1800089e8  mov     [rsp+88h+var_48], ebx; int
0x1800089ec  lea     rax, aPworkerthreadf_1; "pWorkerThreadFunc"
0x1800089f3  mov     [rsp+88h+lpModuleName], rdi; lpModuleName
0x1800089f8  xor     r9d, r9d; int
0x1800089fb  mov     [rsp+88h+var_58], rax; __int64
0x180008a00  mov     edx, 90000h; int
0x180008a05  lea     rax, aOnecoreBaseNts_3; "onecore\\base\\ntsetup\\panther\\engine"...
0x180008a0c  mov     [rsp+88h+var_60], rax; unsigned __int16 *
0x180008a11  mov     [rsp+88h+bAlertable], 98Dh; int
0x180008a19  call    WdsSetupLogMessageW
0x180008a1e  mov     rcx, rsi
0x180008a21  call    pLock
0x180008a26  mov     eax, [rsi+0E8h]
0x180008a2c  test    eax, eax
0x180008a2e  jz      short loc_180008A3A
0x180008a30  dec     eax
0x180008a32  mov     [rsi+0E8h], eax
0x180008a38  jmp     short loc_180008A3D
0x180008a3a  mov     r14, rbp
0x180008a3d  mov     rcx, r14; lpCriticalSection
0x180008a40  call    cs:__imp_LeaveCriticalSection
0x180008a47  nop     dword ptr [rax+rax+00h]
0x180008a4c  lea     r11, [rsp+88h+var_18]
0x180008a51  xor     eax, eax
0x180008a53  mov     rbx, [r11+28h]
0x180008a57  mov     rbp, [r11+30h]
0x180008a5b  mov     rsp, r11
0x180008a5e  pop     r14
0x180008a60  pop     rdi
0x180008a61  pop     rsi
0x180008a62  retn
```
