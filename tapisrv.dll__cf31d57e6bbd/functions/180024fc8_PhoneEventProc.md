# PhoneEventProc

- ea: `0x180024fc8`
- end: `0x18002574e`
- name: `PhoneEventProc`
- size: `1926`
- prototype: ``
- caller_count: `3`
- callee_count: `23`
- tags: ``

## callers

- `0x180025760`
- `0x180028b00`
- `0x18002c4d0`

## callees

- `0x180001f50`
- `0x1800068ac`
- `0x18001b4c4`
- `0x18001c208`
- `0x18001c7c0`
- `0x18001ea48`
- `0x18001f494`
- `0x180020b64`
- `0x180021640`
- `0x180024fc8`
- `0x180025760`
- `0x180025c28`
- `0x18002a508`
- `0x18002ba10`
- `0x18002c8d4`
- `0x18002f778`
- `0x18002ff78`
- `0x180032fc8`
- `0x1800342d4`
- `0x18003dc84`
- `0x18003e15c`
- `0x18003e3b4`
- `0x180040010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1800253df`
- `KERNEL32!HeapAlloc` at `0x1800253df`
- `KERNEL32!CloseHandle` at `0x18002517f`
- `KERNEL32!CloseHandle` at `0x18002517f`
- `KERNEL32!DuplicateHandle` at `0x1800250ef`
- `KERNEL32!DuplicateHandle` at `0x1800250ef`
- `KERNEL32!ReleaseMutex` at `0x180025174`
- `KERNEL32!ReleaseMutex` at `0x180025174`
- `KERNEL32!GetCurrentThreadId` at `0x180025086`
- `KERNEL32!GetCurrentThreadId` at `0x180025102`
- `KERNEL32!GetCurrentThreadId` at `0x1800251c0`
- `KERNEL32!GetCurrentThreadId` at `0x1800251fb`
- `KERNEL32!GetCurrentThreadId` at `0x18002524f`
- `KERNEL32!GetCurrentThreadId` at `0x1800252b2`
- `KERNEL32!GetCurrentThreadId` at `0x18002539c`
- `KERNEL32!GetCurrentThreadId` at `0x180025502`
- `KERNEL32!GetCurrentThreadId` at `0x180025547`
- `KERNEL32!GetCurrentThreadId` at `0x180025086`
- `KERNEL32!GetCurrentThreadId` at `0x180025102`
- `KERNEL32!GetCurrentThreadId` at `0x1800251c0`
- `KERNEL32!GetCurrentThreadId` at `0x1800251fb`
- `KERNEL32!GetCurrentThreadId` at `0x18002524f`
- `KERNEL32!GetCurrentThreadId` at `0x1800252b2`
- `KERNEL32!GetCurrentThreadId` at `0x18002539c`
- `KERNEL32!GetCurrentThreadId` at `0x180025502`
- `KERNEL32!GetCurrentThreadId` at `0x180025547`
- `KERNEL32!WaitForSingleObject` at `0x180025146`
- `KERNEL32!WaitForSingleObject` at `0x180025146`
- `KERNEL32!CreateMutexW` at `0x180025427`
- `KERNEL32!CreateMutexW` at `0x180025427`
- `KERNEL32!LeaveCriticalSection` at `0x180025120`
- `KERNEL32!LeaveCriticalSection` at `0x180025219`
- `KERNEL32!LeaveCriticalSection` at `0x18002526d`
- `KERNEL32!LeaveCriticalSection` at `0x1800253ba`
- `KERNEL32!LeaveCriticalSection` at `0x180025520`
- `KERNEL32!LeaveCriticalSection` at `0x180025635`
- `KERNEL32!LeaveCriticalSection` at `0x180025120`
- `KERNEL32!LeaveCriticalSection` at `0x180025219`
- `KERNEL32!LeaveCriticalSection` at `0x18002526d`
- `KERNEL32!LeaveCriticalSection` at `0x1800253ba`
- `KERNEL32!LeaveCriticalSection` at `0x180025520`
- `KERNEL32!LeaveCriticalSection` at `0x180025635`
- `KERNEL32!EnterCriticalSection` at `0x180025076`
- `KERNEL32!EnterCriticalSection` at `0x1800251b0`
- `KERNEL32!EnterCriticalSection` at `0x1800252a2`
- `KERNEL32!EnterCriticalSection` at `0x180025537`
- `KERNEL32!EnterCriticalSection` at `0x180025076`
- `KERNEL32!EnterCriticalSection` at `0x1800251b0`
- `KERNEL32!EnterCriticalSection` at `0x1800252a2`
- `KERNEL32!EnterCriticalSection` at `0x180025537`

## string_xrefs

- `0x18002505d`: `PhoneEventProc: got a PHONE_REMOVE`
- `0x180025273`: `PhoneEventProc: phone entry already removed`
- `0x180025159`: `PhoneEventProc: marking the phone entry removed`
- `0x18002521f`: `PhoneEventProc: sending PHONE_REMOVE to all apps`

## pseudocode

```c
void __fastcall PhoneEventProc(__int64 a1, int a2, unsigned __int64 a3, __int64 a4, __int64 a5)
{
  int v5; // r15d
  __int64 v9; // rcx
  size_t v10; // rdx
  char *PhoneLookupEntry; // rax
  char *v12; // rdi
  BOOL v13; // r12d
  void *v14; // rdx
  size_t v15; // rdx
  const char *v16; // rdx
  __int64 v17; // rcx
  size_t v18; // rdx
  size_t v19; // rdx
  int v20; // r9d
  size_t v21; // rdx
  size_t v22; // rdx
  _QWORD *i; // r10
  unsigned int *v24; // r12
  _QWORD *v25; // rdi
  unsigned __int64 v26; // rax
  ULONG v27; // ecx
  unsigned __int64 v28; // r10
  ULONG v29; // edx
  size_t v30; // rdx
  _DWORD *v31; // rax
  _QWORD *v32; // r12
  unsigned int v33; // r13d
  HANDLE MutexW; // rax
  unsigned int ClientList; // r13d
  unsigned int *v36; // r12
  __int64 (__fastcall *v37)(_QWORD, __int64, __int64, HANDLE); // rax
  size_t v38; // rdx
  size_t v39; // rdx
  unsigned __int64 v40; // rsi
  __int64 j; // rdi
  unsigned int v42; // ecx
  unsigned int v43; // r8d
  ULONG v44; // r9d
  _DWORD *v45; // rax
  __int64 v46; // rcx
  __int64 v47; // rax
  int dwDesiredAccess; // [rsp+20h] [rbp-D8h]
  HANDLE TargetHandle; // [rsp+40h] [rbp-B8h] BYREF
  _DWORD *v50; // [rsp+48h] [rbp-B0h] BYREF
  __int64 v51; // [rsp+50h] [rbp-A8h] BYREF
  int v52; // [rsp+58h] [rbp-A0h]
  __int64 v53; // [rsp+5Ch] [rbp-9Ch]
  __int64 v54; // [rsp+64h] [rbp-94h]
  int v55; // [rsp+6Ch] [rbp-8Ch]
  __int64 v56; // [rsp+70h] [rbp-88h]
  _DWORD *v57; // [rsp+78h] [rbp-80h]
  _BYTE Mem[4]; // [rsp+80h] [rbp-78h] BYREF
  int v59; // [rsp+84h] [rbp-74h]
  ULONG pulResult; // [rsp+108h] [rbp+10h] BYREF
  __int64 v61; // [rsp+118h] [rbp+20h]

  v61 = a4;
  v5 = a4;
  TRACELogPrint(524290, "PhoneEventProc: entered");
  switch ( a2 )
  {
    case 14:
      goto LABEL_73;
    case 15:
      v45 = (_DWORD *)ReferenceObject(v9, (unsigned int)a1, 0);
      if ( !v45 )
        return;
      if ( *v45 == 1330139209 )
      {
        PhoneEventProcSP(a1, 15, 0, 0, 3735928559LL);
      }
      else if ( *v45 == 1313818704 )
      {
        DestroytPhone(v45, 1);
      }
      goto LABEL_75;
    case 16:
    case 18:
LABEL_73:
      v47 = ReferenceObject(v9, (unsigned int)a1, 1313818704);
      if ( !v47 )
      {
        if ( a2 == 18 && !a1 && (a3 & 0x200000) != 0 )
          SendReinitMsgToAllXxxApps();
        return;
      }
      SendMsgToPhoneClients(v47, 0, a2, a3, v5, a5);
LABEL_75:
      DereferenceObject(v46, a1, 1);
      return;
    case 20:
      v50 = *(_DWORD **)(a3 + 952);
      v57 = v50;
      EnterCriticalSection(&CriticalSection);
      dword_1800519E0 = 2089;
      dword_1800519E4 = GetCurrentThreadId();
      StringCbCopyA(pszDest, v22, "\\server\\phone.c");
      for ( i = qword_180051910; i; i = (_QWORD *)i[6] )
      {
        if ( i == (_QWORD *)a3 )
          goto LABEL_28;
      }
      if ( a3 )
      {
        dword_1800519F8 = 2100;
        goto LABEL_40;
      }
LABEL_28:
      if ( !gbQueueSPEvents )
      {
        dword_1800519F8 = 2110;
LABEL_40:
        dword_1800519FC = GetCurrentThreadId();
        StringCbCopyA(byte_1800519E8, v30, "\\server\\phone.c");
        LeaveCriticalSection(&CriticalSection);
        return;
      }
      v24 = (unsigned int *)qword_180051930;
      v25 = qword_180051930;
      if ( qword_180051930 )
      {
        do
        {
          if ( *((_DWORD *)v25 + 1) < *(_DWORD *)v25 )
            break;
          v24 = (unsigned int *)v25;
          v25 = (_QWORD *)v25[1];
        }
        while ( v25 );
      }
      if ( !v25 )
      {
        v26 = 2LL * *v24;
        v27 = 2 * *v24;
        if ( v26 > 0xFFFFFFFF )
          v27 = -1;
        pulResult = v27;
        if ( v26 > 0xFFFFFFFF
          || ULongSub(v27, 1u, &pulResult) < 0
          || (v29 = 40 * pulResult, 40 * (unsigned __int64)pulResult > v28)
          || v29 + 56 < v29
          || (v31 = HeapAlloc(ghTapisrvHeap, 8u, v29 + 56), (v25 = v31) == 0) )
        {
          dword_1800519F8 = 2133;
          goto LABEL_40;
        }
        *((_QWORD *)v24 + 1) = v31;
        *v31 = 2 * *v24;
      }
      TargetHandle = &v25[4 * *((unsigned int *)v25 + 1) + 2 + *((unsigned int *)v25 + 1)];
      v32 = TargetHandle;
      v33 = dword_18005192C;
      pulResult = dword_18005192C;
      MutexW = CreateMutexW(0, 0, 0);
      *((_QWORD *)TargetHandle + 2) = MutexW;
      if ( MutexW )
      {
        v32[3] = a3;
        ClientList = ((__int64 (__fastcall *)(__int64, _QWORD))v50)(v61, v33);
        if ( !ClientList )
        {
          v59 = 0;
          memset_0(Mem, 0, 0x44u);
          v36 = (unsigned int *)Mem;
          v50 = Mem;
          v37 = *(__int64 (__fastcall **)(_QWORD, __int64, __int64, HANDLE))(a3 + 848);
          if ( v37 )
          {
            ClientList = v37(pulResult, 65539, 196609, TargetHandle);
            if ( !ClientList )
            {
              v51 = 40;
              v53 = 0;
              v54 = 0;
              v56 = 0;
              GetPermPhoneIDAndInsertInTable(a3, pulResult, *(unsigned int *)TargetHandle);
              ++*((_DWORD *)v25 + 1);
              ++dword_18005192C;
              dword_1800519F8 = 2201;
              dword_1800519FC = GetCurrentThreadId();
              StringCbCopyA(byte_1800519E8, v38, "\\server\\phone.c");
              LeaveCriticalSection(&CriticalSection);
              AppendNewDeviceInfo(0, pulResult);
              EnterCriticalSection(&CriticalSection);
              dword_1800519E0 = 2203;
              dword_1800519E4 = GetCurrentThreadId();
              StringCbCopyA(pszDest, v39, "\\server\\phone.c");
              v52 = 0;
              v55 = 0;
              ClientList = GetClientList(((unsigned int)dword_180051900 >> 1) & 1, &v50);
              v36 = v50;
              if ( !ClientList )
              {
                ClientList = 0;
                if ( *v50 )
                {
                  do
                  {
                    v40 = *(_QWORD *)&v36[2 * ClientList + 2];
                    if ( WaitForExclusiveClientAccess(v40) )
                    {
                      for ( j = *(_QWORD *)(v40 + 176); j; j = *(_QWORD *)(j + 40) )
                      {
                        v42 = *(_DWORD *)(j + 64);
                        if ( v42 == 65539 )
                        {
                          v43 = 18;
                          v44 = 0x200000;
                        }
                        else
                        {
                          v43 = 20;
                          v44 = pulResult;
                        }
                        HIDWORD(v54) = v44;
                        HIDWORD(v53) = v43;
                        if ( !(unsigned int)FMsgDisabled(v42, j + 76, v43) )
                        {
                          HIDWORD(v51) = *(_DWORD *)(j + 16);
                          WriteEventBuffer(v40, (unsigned int *)&v51);
                        }
                      }
                      LeaveCriticalSection((LPCRITICAL_SECTION)gLockTable + ((unsigned int)gdwPointerToLockTableIndexBits
                                                                           & (v40 >> 4)));
                    }
                    ++ClientList;
                  }
                  while ( ClientList < *v36 );
                  ClientList = 0;
                }
              }
            }
          }
          if ( v36 != (unsigned int *)Mem )
            ServerFree(v36);
          v32 = TargetHandle;
        }
        if ( ClientList )
          MyCloseMutex(v32[2]);
      }
      dword_1800519F8 = 2282;
      goto LABEL_40;
  }
  if ( a2 != 26 )
  {
    TRACELogPrint(65538, "PhoneEventProc: unknown msg, dwMsg=%ld", a2);
    return;
  }
  TargetHandle = 0;
  TRACELogPrint(524290, "PhoneEventProc: got a PHONE_REMOVE");
  EnterCriticalSection(&CriticalSection);
  dword_1800519E0 = 2292;
  dword_1800519E4 = GetCurrentThreadId();
  StringCbCopyA(pszDest, v10, "\\server\\phone.c");
  PhoneLookupEntry = GetPhoneLookupEntry(a3);
  v12 = PhoneLookupEntry;
  if ( !PhoneLookupEntry || *((_DWORD *)PhoneLookupEntry + 8) )
  {
    dword_1800519F8 = 2296;
    dword_1800519FC = GetCurrentThreadId();
    StringCbCopyA(byte_1800519E8, v21, "\\server\\phone.c");
    LeaveCriticalSection(&CriticalSection);
    v16 = "PhoneEventProc: phone entry already removed";
    v17 = 524290;
    goto LABEL_21;
  }
  v13 = 0;
  v14 = (void *)*((_QWORD *)PhoneLookupEntry + 2);
  if ( v14 )
    v13 = DuplicateHandle(hSourceProcessHandle, v14, hSourceProcessHandle, &TargetHandle, 0, 0, 2u);
  dword_1800519F8 = 2314;
  dword_1800519FC = GetCurrentThreadId();
  StringCbCopyA(byte_1800519E8, v15, "\\server\\phone.c");
  LeaveCriticalSection(&CriticalSection);
  if ( !v13 )
  {
    v16 = "PhoneEventProc: can't duplicate handle";
LABEL_14:
    v17 = 65538;
LABEL_21:
    TRACELogPrint(v17, v16);
    return;
  }
  if ( WaitForSingleObject(TargetHandle, 0xFFFFFFFF) )
  {
    v16 = "PhoneEventProc: error in WaitForSingleObject on the duplicate handle";
    goto LABEL_14;
  }
  TRACELogPrint(524290, "PhoneEventProc: marking the phone entry removed");
  *((_DWORD *)v12 + 8) = 1;
  ReleaseMutex(TargetHandle);
  CloseHandle(TargetHandle);
  TargetHandle = 0;
  if ( *((_QWORD *)v12 + 1) )
  {
    TRACELogPrint(524290, "PhoneEventProc: calling DestroytPhone");
    DestroytPhone(*((_QWORD *)v12 + 1), 1);
  }
  EnterCriticalSection(&CriticalSection);
  dword_1800519E0 = 2352;
  dword_1800519E4 = GetCurrentThreadId();
  StringCbCopyA(pszDest, v18, "\\server\\phone.c");
  MyCloseMutex(*((_QWORD *)v12 + 2));
  *((_QWORD *)v12 + 2) = 0;
  RemoveDeviceInfoEntry(0, (unsigned int)a3);
  dword_1800519F8 = 2362;
  dword_1800519FC = GetCurrentThreadId();
  StringCbCopyA(byte_1800519E8, v19, "\\server\\phone.c");
  LeaveCriticalSection(&CriticalSection);
  TRACELogPrint(524290, "PhoneEventProc: sending PHONE_REMOVE to all apps");
  SendAMsgToAllPhoneApps(-2147352576, 26, a3, v20, dwDesiredAccess);
}

```

## disassembly

```asm
0x180024fc8  mov     [rsp+arg_0], rbx
0x180024fcd  mov     [rsp+arg_10], rsi
0x180024fd2  mov     [rsp+arg_18], r9
0x180024fd7  push    rdi
0x180024fd8  push    r12
0x180024fda  push    r13
0x180024fdc  push    r14
0x180024fde  push    r15
0x180024fe0  sub     rsp, 0D0h
0x180024fe7  mov     r15, r9
0x180024fea  mov     rsi, r8
0x180024fed  mov     r14d, edx
0x180024ff0  mov     rdi, rcx
0x180024ff3  lea     rdx, aPhoneeventproc_8; "PhoneEventProc: entered"
0x180024ffa  mov     r13d, 80002h
0x180025000  mov     ecx, r13d
0x180025003  call    TRACELogPrint
0x180025008  mov     eax, r14d
0x18002500b  sub     eax, 0Eh
0x18002500e  jz      loc_1800256D8
0x180025014  sub     eax, 1
0x180025017  jz      loc_180025688
0x18002501d  sub     eax, 1
0x180025020  jz      loc_1800256D8
0x180025026  sub     eax, 2
0x180025029  jz      loc_1800256D8
0x18002502f  sub     eax, 2
0x180025032  jz      loc_180025287
0x180025038  cmp     eax, 6
0x18002503b  jz      short loc_180025056
0x18002503d  mov     r8d, r14d
0x180025040  lea     rdx, aPhoneeventproc_3; "PhoneEventProc: unknown msg, dwMsg=%ld"
0x180025047  mov     ecx, 10002h
0x18002504c  call    TRACELogPrint
0x180025051  jmp     loc_180025731
0x180025056  xor     ebx, ebx
0x180025058  mov     [rsp+0F8h+TargetHandle], rbx
0x18002505d  lea     rdx, aPhoneeventproc; "PhoneEventProc: got a PHONE_REMOVE"
0x180025064  mov     ecx, r13d
0x180025067  call    TRACELogPrint
0x18002506c  lea     r14, CriticalSection
0x180025073  mov     rcx, r14; lpCriticalSection
0x180025076  call    cs:__imp_EnterCriticalSection
0x18002507c  mov     cs:dword_1800519E0, 8F4h
0x180025086  call    cs:__imp_GetCurrentThreadId
0x18002508c  mov     cs:dword_1800519E4, eax
0x180025092  lea     r15, aPrintscanTapiS_2+0Eh; "\\server\\phone.c"
0x180025099  mov     r8, r15; pszSrc
0x18002509c  lea     rcx, pszDest; pszDest
0x1800250a3  call    StringCbCopyA
0x1800250a8  mov     ecx, esi
0x1800250aa  call    GetPhoneLookupEntry
0x1800250af  mov     rdi, rax
0x1800250b2  test    rax, rax
0x1800250b5  jz      loc_180025245
0x1800250bb  cmp     [rax+20h], ebx
0x1800250be  jnz     loc_180025245
0x1800250c4  mov     r12d, ebx
0x1800250c7  mov     rdx, [rax+10h]; hSourceHandle
0x1800250cb  test    rdx, rdx
0x1800250ce  jz      short loc_1800250F8
0x1800250d0  mov     [rsp+0F8h+dwOptions], 2; dwOptions
0x1800250d8  mov     [rsp+0F8h+bInheritHandle], ebx; bInheritHandle
0x1800250dc  mov     [rsp+0F8h+dwDesiredAccess], ebx; dwDesiredAccess
0x1800250e0  lea     r9, [rsp+0F8h+TargetHandle]; lpTargetHandle
0x1800250e5  mov     rcx, cs:hSourceProcessHandle; hSourceProcessHandle
0x1800250ec  mov     r8, rcx; hTargetProcessHandle
0x1800250ef  call    cs:__imp_DuplicateHandle
0x1800250f5  mov     r12d, eax
0x1800250f8  mov     cs:dword_1800519F8, 90Ah
0x180025102  call    cs:__imp_GetCurrentThreadId
0x180025108  mov     cs:dword_1800519FC, eax
0x18002510e  mov     r8, r15; pszSrc
0x180025111  lea     rcx, byte_1800519E8; pszDest
0x180025118  call    StringCbCopyA
0x18002511d  mov     rcx, r14; lpCriticalSection
0x180025120  call    cs:__imp_LeaveCriticalSection
0x180025126  test    r12d, r12d
0x180025129  jnz     short loc_18002513C
0x18002512b  lea     rdx, aPhoneeventproc_4; "PhoneEventProc: can't duplicate handle"
0x180025132  mov     ecx, 10002h
0x180025137  jmp     loc_18002527D
0x18002513c  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180025141  mov     rcx, [rsp+0F8h+TargetHandle]; hHandle
0x180025146  call    cs:__imp_WaitForSingleObject
0x18002514c  test    eax, eax
0x18002514e  jz      short loc_180025159
0x180025150  lea     rdx, aPhoneeventproc_7; "PhoneEventProc: error in WaitForSingleO"...
0x180025157  jmp     short loc_180025132
0x180025159  lea     rdx, aPhoneeventproc_2; "PhoneEventProc: marking the phone entry"...
0x180025160  mov     ecx, r13d
0x180025163  call    TRACELogPrint
0x180025168  mov     dword ptr [rdi+20h], 1
0x18002516f  mov     rcx, [rsp+0F8h+TargetHandle]; hMutex
0x180025174  call    cs:__imp_ReleaseMutex
0x18002517a  mov     rcx, [rsp+0F8h+TargetHandle]; hObject
0x18002517f  call    cs:__imp_CloseHandle
0x180025185  mov     [rsp+0F8h+TargetHandle], rbx
0x18002518a  cmp     [rdi+8], rbx
0x18002518e  jz      short loc_1800251AD
0x180025190  lea     rdx, aPhoneeventproc_1; "PhoneEventProc: calling DestroytPhone"
0x180025197  mov     ecx, r13d
0x18002519a  call    TRACELogPrint
0x18002519f  mov     edx, 1
0x1800251a4  mov     rcx, [rdi+8]
0x1800251a8  call    DestroytPhone
0x1800251ad  mov     rcx, r14; lpCriticalSection
0x1800251b0  call    cs:__imp_EnterCriticalSection
0x1800251b6  mov     cs:dword_1800519E0, 930h
0x1800251c0  call    cs:__imp_GetCurrentThreadId
0x1800251c6  mov     cs:dword_1800519E4, eax
0x1800251cc  mov     r8, r15; pszSrc
0x1800251cf  lea     rcx, pszDest; pszDest
0x1800251d6  call    StringCbCopyA
0x1800251db  mov     rcx, [rdi+10h]
0x1800251df  call    MyCloseMutex
0x1800251e4  mov     [rdi+10h], rbx
0x1800251e8  mov     edx, esi
0x1800251ea  xor     ecx, ecx
0x1800251ec  call    RemoveDeviceInfoEntry
0x1800251f1  mov     cs:dword_1800519F8, 93Ah
0x1800251fb  call    cs:__imp_GetCurrentThreadId
0x180025201  mov     cs:dword_1800519FC, eax
0x180025207  mov     r8, r15; pszSrc
0x18002520a  lea     rcx, byte_1800519E8; pszDest
0x180025211  call    StringCbCopyA
0x180025216  mov     rcx, r14; lpCriticalSection
0x180025219  call    cs:__imp_LeaveCriticalSection
0x18002521f  lea     rdx, aPhoneeventproc_5; "PhoneEventProc: sending PHONE_REMOVE to"...
0x180025226  mov     ecx, r13d
0x180025229  call    TRACELogPrint
0x18002522e  mov     r8d, esi
0x180025231  mov     edx, 1Ah
0x180025236  mov     ecx, 80020000h
0x18002523b  call    SendAMsgToAllPhoneApps
0x180025240  jmp     loc_180025731
0x180025245  mov     cs:dword_1800519F8, 8F8h
0x18002524f  call    cs:__imp_GetCurrentThreadId
0x180025255  mov     cs:dword_1800519FC, eax
0x18002525b  mov     r8, r15; pszSrc
0x18002525e  lea     rcx, byte_1800519E8; pszDest
0x180025265  call    StringCbCopyA
0x18002526a  mov     rcx, r14; lpCriticalSection
0x18002526d  call    cs:__imp_LeaveCriticalSection
0x180025273  lea     rdx, aPhoneeventproc_0; "PhoneEventProc: phone entry already rem"...
0x18002527a  mov     ecx, r13d
0x18002527d  call    TRACELogPrint
0x180025282  jmp     loc_180025731
0x180025287  mov     rax, [rsi+3B8h]
0x18002528e  mov     [rsp+0F8h+var_B0], rax
0x180025293  mov     [rsp+0F8h+var_80], rax
0x180025298  lea     r14, CriticalSection
0x18002529f  mov     rcx, r14; lpCriticalSection
0x1800252a2  call    cs:__imp_EnterCriticalSection
0x1800252a8  mov     cs:dword_1800519E0, 829h
0x1800252b2  call    cs:__imp_GetCurrentThreadId
0x1800252b8  mov     cs:dword_1800519E4, eax
0x1800252be  lea     r15, aPrintscanTapiS_2+0Eh; "\\server\\phone.c"
0x1800252c5  mov     r8, r15; pszSrc
0x1800252c8  lea     rcx, pszDest; pszDest
0x1800252cf  call    StringCbCopyA
0x1800252d4  mov     r10, cs:qword_180051910
0x1800252db  xor     ebx, ebx
0x1800252dd  jmp     short loc_1800252E8
0x1800252df  cmp     r10, rsi
0x1800252e2  jz      short loc_180025301
0x1800252e4  mov     r10, [r10+30h]
0x1800252e8  test    r10, r10
0x1800252eb  jnz     short loc_1800252DF
0x1800252ed  cmp     r10, rsi
0x1800252f0  jz      short loc_180025301
0x1800252f2  mov     cs:dword_1800519F8, 834h
0x1800252fc  jmp     loc_18002539C
0x180025301  cmp     cs:gbQueueSPEvents, ebx
0x180025307  jnz     short loc_180025318
0x180025309  mov     cs:dword_1800519F8, 83Eh
0x180025313  jmp     loc_18002539C
0x180025318  mov     r12, cs:qword_180051930
0x18002531f  mov     rdi, r12
0x180025322  test    r12, r12
0x180025325  jz      short loc_18002533A
0x180025327  mov     eax, [rdi]
0x180025329  cmp     [rdi+4], eax
0x18002532c  jb      short loc_18002533A
0x18002532e  mov     r12, rdi
0x180025331  mov     rdi, [rdi+8]
0x180025335  test    rdi, rdi
0x180025338  jnz     short loc_180025327
0x18002533a  test    rdi, rdi
0x18002533d  jnz     loc_1800253FA
0x180025343  mov     eax, [r12]
0x180025347  add     rax, rax
0x18002534a  mov     r10d, 0FFFFFFFFh
0x180025350  cmp     rax, r10
0x180025353  mov     ecx, eax
0x180025355  jbe     short loc_18002535A
0x180025357  mov     ecx, r10d; ulMinuend
0x18002535a  mov     [rsp+0F8h+pulResult], ecx
0x180025361  ja      short loc_180025392
0x180025363  lea     r8, [rsp+0F8h+pulResult]; pulResult
0x18002536b  mov     edx, 1; ulSubtrahend
0x180025370  call    ULongSub
0x180025375  test    eax, eax
0x180025377  js      short loc_180025392
0x180025379  mov     eax, [rsp+0F8h+pulResult]
0x180025380  lea     rcx, [rax+rax*4]
0x180025384  shl     rcx, 3
0x180025388  cmp     rcx, r10
0x18002538b  mov     edx, ecx
0x18002538d  jbe     short loc_1800253C5
0x18002538f  mov     edx, r10d
0x180025392  mov     cs:dword_1800519F8, 855h
0x18002539c  call    cs:__imp_GetCurrentThreadId
0x1800253a2  mov     cs:dword_1800519FC, eax
0x1800253a8  mov     r8, r15; pszSrc
0x1800253ab  lea     rcx, byte_1800519E8; pszDest
0x1800253b2  call    StringCbCopyA
0x1800253b7  mov     rcx, r14; lpCriticalSection
0x1800253ba  call    cs:__imp_LeaveCriticalSection
0x1800253c0  jmp     loc_180025731
0x1800253c5  lea     eax, [rdx+38h]
0x1800253c8  cmp     eax, edx
0x1800253ca  cmovnb  r10d, eax
0x1800253ce  jb      short loc_180025392
0x1800253d0  mov     r8d, r10d; dwBytes
0x1800253d3  mov     edx, 8; dwFlags
0x1800253d8  mov     rcx, cs:ghTapisrvHeap; hHeap
0x1800253df  call    cs:__imp_HeapAlloc
0x1800253e5  mov     rdi, rax
0x1800253e8  test    rax, rax
0x1800253eb  jz      short loc_180025392
0x1800253ed  mov     [r12+8], rax
0x1800253f2  mov     ecx, [r12]
0x1800253f6  add     ecx, ecx
0x1800253f8  mov     [rax], ecx
0x1800253fa  mov     eax, [rdi+4]
0x1800253fd  lea     rcx, ds:2[rax*4]
0x180025405  add     rcx, rax
0x180025408  lea     r12, [rdi+rcx*8]
0x18002540c  mov     [rsp+0F8h+TargetHandle], r12
0x180025411  mov     r13d, cs:dword_18005192C
0x180025418  mov     [rsp+0F8h+pulResult], r13d
0x180025420  xor     r8d, r8d; lpName
0x180025423  xor     edx, edx; bInitialOwner
0x180025425  xor     ecx, ecx; lpMutexAttributes
0x180025427  call    cs:__imp_CreateMutexW
0x18002542d  mov     [r12+10h], rax
0x180025432  test    rax, rax
0x180025435  jz      loc_180025674
0x18002543b  mov     [r12+18h], rsi
0x180025440  mov     edx, r13d
0x180025443  mov     rcx, [rsp+0F8h+arg_18]
0x18002544b  mov     rax, [rsp+0F8h+var_B0]
0x180025450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025455  mov     r13d, eax
0x180025458  test    eax, eax
0x18002545a  jnz     loc_180025665
0x180025460  xor     eax, eax
0x180025462  mov     [rsp+0F8h+var_74], eax
0x180025469  xor     edx, edx; Val
0x18002546b  lea     r8d, [r13+44h]; Size
0x18002546f  lea     rcx, [rsp+0F8h+Mem]; void *
0x180025477  call    memset_0
0x18002547c  lea     r12, [rsp+0F8h+Mem]
0x180025484  mov     [rsp+0F8h+var_B0], r12
0x180025489  mov     rax, [rsi+350h]
0x180025490  test    rax, rax
0x180025493  jz      loc_18002564B
0x180025499  mov     r9, [rsp+0F8h+TargetHandle]
0x18002549e  mov     edx, 10003h
0x1800254a3  mov     r8d, 30001h
0x1800254a9  mov     ecx, [rsp+0F8h+pulResult]
0x1800254b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800254b5  mov     r13d, eax
0x1800254b8  test    eax, eax
0x1800254ba  jnz     loc_18002564B
0x1800254c0  mov     [rsp+0F8h+var_A8], 28h ; '('
0x1800254c9  mov     [rsp+0F8h+var_9C], rbx
0x1800254ce  mov     [rsp+0F8h+var_94], rbx
0x1800254d3  mov     [rsp+0F8h+var_88], rbx
0x1800254d8  mov     rax, [rsp+0F8h+TargetHandle]
0x1800254dd  mov     r8d, [rax]
0x1800254e0  mov     edx, [rsp+0F8h+pulResult]
0x1800254e7  mov     rcx, rsi
0x1800254ea  call    GetPermPhoneIDAndInsertInTable
0x1800254ef  inc     dword ptr [rdi+4]
0x1800254f2  inc     cs:dword_18005192C
0x1800254f8  mov     cs:dword_1800519F8, 899h
0x180025502  call    cs:__imp_GetCurrentThreadId
0x180025508  mov     cs:dword_1800519FC, eax
0x18002550e  mov     r8, r15; pszSrc
0x180025511  lea     rcx, byte_1800519E8; pszDest
0x180025518  call    StringCbCopyA
0x18002551d  mov     rcx, r14; lpCriticalSection
0x180025520  call    cs:__imp_LeaveCriticalSection
0x180025526  mov     edx, [rsp+0F8h+pulResult]
0x18002552d  xor     ecx, ecx
0x18002552f  call    AppendNewDeviceInfo
0x180025534  mov     rcx, r14; lpCriticalSection
0x180025537  call    cs:__imp_EnterCriticalSection
  ... truncated ...
```
