# OnDemand::SetInterfaceState(std::shared_ptr<OnDemand::OnDemandInterfaceInfo> &,_WCM_ONDEMAND_STATE)

- ea: `0x1800784bc`
- end: `0x180078985`
- name: `?SetInterfaceState@OnDemand@@AEAAXAEAV?$shared_ptr@UOnDemandInterfaceInfo@OnDemand@@@std@@W4_WCM_ONDEMAND_STATE@@@Z`
- size: `1225`
- prototype: ``
- caller_count: `9`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015974`
- `0x180015e88`
- `0x180064120`
- `0x1800782e0`
- `0x1800903a4`
- `0x180090564`
- `0x180090810`
- `0x1800912f0`
- `0x180092658`

## callees

- `0x180011ddc`
- `0x1800137a0`
- `0x180019434`
- `0x1800277c0`
- `0x1800784bc`
- `0x180083500`
- `0x1800902a8`
- `0x180092bb4`
- `0x180093144`
- `0x1800c3970`
- `0x1800f7010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078739`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800787e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078895`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078739`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800787e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078895`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180078710`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800787d7`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180078710`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800787d7`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18007888b`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18007888b`

## pseudocode

```c
__int64 __fastcall OnDemand::SetInterfaceState(__int64 a1, PVOID *a2, unsigned int a3)
{
  __int64 v6; // rbx
  __int64 v7; // rax
  int v8; // edx
  int v9; // r8d
  int v10; // r15d
  __int64 *v11; // r8
  __int64 *i; // rcx
  __int64 v13; // rdx
  int v14; // eax
  __int64 *v15; // rax
  char v16; // r10
  __int64 v17; // rdx
  char *v18; // r9
  int v19; // ecx
  _QWORD *v20; // rbp
  _QWORD *j; // rbx
  __int64 v22; // rcx
  void (__fastcall *v23)(_QWORD, __int64, _QWORD); // rax
  __int64 v24; // rdx
  void *v25; // rdx
  DWORD LastError; // eax
  _QWORD *v27; // rax
  __int64 v28; // rcx
  void *v29; // rdx
  DWORD v30; // eax
  DWORD DueTime; // ebx
  DWORD v32; // eax
  int v33; // edx
  DWORD v35; // [rsp+80h] [rbp+18h] BYREF

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    v6 = EnumToString(a3);
    v7 = EnumToString(*((unsigned int *)*a2 + 647));
    WPP_SF__guid__guid_ss(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      v8,
      v9,
      (unsigned int)*a2 + 2616,
      (__int64)*a2 + 2600,
      v7,
      v6);
  }
  v10 = *((_DWORD *)*a2 + 647);
  *((_DWORD *)*a2 + 647) = a3;
  if ( a3 - 3 <= 1 )
  {
    v11 = *(__int64 **)(a1 + 72);
    if ( a3 == 4 )
    {
      v15 = *(__int64 **)(a1 + 64);
      v16 = 0;
      if ( v15 != v11 )
      {
        do
        {
          v17 = *v15;
          v18 = (char *)*a2;
          if ( *(PVOID *)(*v15 + 200) == *a2 )
          {
            v19 = *(_DWORD *)(v17 + 216);
            if ( (v19 & 1) != 0 )
            {
              v16 = 1;
              *(_DWORD *)(v17 + 216) = v19 & 0xFFFFFFFE;
              v18 = (char *)*a2;
            }
          }
          v15 += 2;
        }
        while ( v15 != v11 );
        if ( v16 )
        {
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
            && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            WPP_SF__guid_(
              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
              162,
              WPP_7ef1a219358f3e78125012fa23bc8b03_Traceguids,
              v18 + 2600);
          }
          *((_DWORD *)*a2 + 647) = 1;
        }
      }
    }
    else
    {
      for ( i = *(__int64 **)(a1 + 64); i != v11; i += 2 )
      {
        v13 = *i;
        if ( *(PVOID *)(*i + 200) == *a2 )
        {
          v14 = *(_DWORD *)(v13 + 216);
          if ( (v14 & 1) != 0 )
            *(_DWORD *)(v13 + 216) = v14 & 0xFFFFFFFE;
        }
      }
    }
  }
  if ( (unsigned int)(*((_DWORD *)*a2 + 647) - 3) <= 1 )
  {
    v20 = *(_QWORD **)(a1 + 72);
    for ( j = *(_QWORD **)(a1 + 64); j != v20; j += 2 )
    {
      v22 = *j;
      if ( *(PVOID *)(*j + 200LL) == *a2 )
      {
        v23 = *(void (__fastcall **)(_QWORD, __int64, _QWORD))(v22 + 224);
        if ( v23 )
        {
          v24 = *(_QWORD *)(v22 + 232);
          *(_QWORD *)(v22 + 224) = 0;
          *(_QWORD *)(*j + 232LL) = 0;
          v23(*j, v24, *((unsigned int *)*a2 + 786));
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
            && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            WPP_SF_d(
              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
              163,
              WPP_7ef1a219358f3e78125012fa23bc8b03_Traceguids,
              *((unsigned int *)*a2 + 786));
          }
        }
        *((_DWORD *)*a2 + 786) = 0;
      }
    }
    v25 = (void *)*((_QWORD *)*a2 + 396);
    if ( v25 )
    {
      if ( DeleteTimerQueueTimer(0, v25, 0) )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
          && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 165, WPP_7ef1a219358f3e78125012fa23bc8b03_Traceguids);
        }
      }
      else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u
             && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          164,
          WPP_7ef1a219358f3e78125012fa23bc8b03_Traceguids,
          LastError);
      }
      *((_QWORD *)*a2 + 396) = 0;
    }
  }
  v27 = *a2;
  v28 = *((unsigned int *)*a2 + 647);
  if ( (_DWORD)v28 == 1 )
  {
    if ( !v27[395] )
    {
      v35 = 0;
      if ( ConfigManager::GetOnDemandStartTimeout(&v35) || (DueTime = v35) == 0 )
        DueTime = 300000;
      if ( CreateTimerQueueTimer((PHANDLE)*a2 + 395, 0, OnDemand::OnDemandStartTimeoutCallback, *a2, DueTime, 0, 0) )
      {
        v28 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
          && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          WPP_SF_Sd(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            168,
            (unsigned int)WPP_7ef1a219358f3e78125012fa23bc8b03_Traceguids,
            *(_DWORD *)a2 + 532,
            DueTime);
        }
      }
      else
      {
        v32 = GetLastError();
        v28 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *(_BYTE *)(WPP_GLOBAL_Control + 25LL)
          && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 167, WPP_7ef1a219358f3e78125012fa23bc8b03_Traceguids, v32);
        }
      }
    }
  }
  else if ( (_DWORD)v28 != 2 )
  {
    v29 = (void *)v27[395];
    if ( v29 )
    {
      if ( !DeleteTimerQueueTimer(0, v29, 0) )
      {
        v30 = GetLastError();
        v28 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *(_BYTE *)(WPP_GLOBAL_Control + 25LL)
          && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 166, WPP_7ef1a219358f3e78125012fa23bc8b03_Traceguids, v30);
        }
      }
      *((_QWORD *)*a2 + 395) = 0;
    }
  }
  v33 = *((_DWORD *)*a2 + 647);
  if ( v10 != v33 && (Microsoft_Windows_WcmsvcEnableBits & 2) != 0 )
    McTemplateU0qjzzqq_EtwEventWriteTransfer(
      (unsigned int)*a2 + 532,
      v33,
      *(_DWORD *)*a2,
      (unsigned int)*a2 + 2616,
      (__int64)*a2 + 532,
      (__int64)*a2 + 20,
      *((_DWORD *)*a2 + 647));
  if ( a3 == 4 )
    *(GUID *)((char *)*a2 + 2600) = GUID_NULL;
  return OnDemand::LogInterfaceInfo(v28, L"State change called.", a2);
}

```

## disassembly

```asm
0x1800784bc  mov     [rsp+arg_0], rbx
0x1800784c1  mov     [rsp+arg_8], rbp
0x1800784c6  push    rsi
0x1800784c7  push    rdi
0x1800784c8  push    r13
0x1800784ca  push    r14
0x1800784cc  push    r15
0x1800784ce  sub     rsp, 40h
0x1800784d2  mov     r14d, r8d
0x1800784d5  mov     rdi, rdx
0x1800784d8  mov     rsi, rcx
0x1800784db  mov     rax, cs:WPP_GLOBAL_Control
0x1800784e2  lea     rbp, WPP_GLOBAL_Control
0x1800784e9  mov     r13d, 1
0x1800784ef  cmp     rax, rbp
0x1800784f2  jz      short loc_180078549
0x1800784f4  cmp     byte ptr [rax+19h], 4
0x1800784f8  jb      short loc_180078549
0x1800784fa  test    [rax+1Ch], r13b
0x1800784fe  jz      short loc_180078549
0x180078500  mov     ecx, r8d
0x180078503  call    ?EnumToString@@YAPEBDW4_WCM_ONDEMAND_STATE@@@Z; EnumToString(_WCM_ONDEMAND_STATE)
0x180078508  mov     rcx, [rdi]
0x18007850b  mov     rbx, rax
0x18007850e  mov     ecx, [rcx+0A1Ch]
0x180078514  call    ?EnumToString@@YAPEBDW4_WCM_ONDEMAND_STATE@@@Z; EnumToString(_WCM_ONDEMAND_STATE)
0x180078519  mov     r9, [rdi]
0x18007851c  mov     qword ptr [rsp+68h+Flags], rbx
0x180078521  mov     qword ptr [rsp+68h+Period], rax
0x180078526  lea     rcx, [r9+0A28h]
0x18007852d  add     r9, 0A38h
0x180078534  mov     qword ptr [rsp+68h+DueTime], rcx
0x180078539  mov     rcx, cs:WPP_GLOBAL_Control
0x180078540  mov     rcx, [rcx+10h]
0x180078544  call    WPP_SF__guid__guid_ss
0x180078549  mov     rax, [rdi]
0x18007854c  mov     r15d, [rax+0A1Ch]
0x180078553  mov     [rax+0A1Ch], r14d
0x18007855a  lea     eax, [r14-3]
0x18007855e  cmp     eax, r13d
0x180078561  ja      loc_180078629
0x180078567  mov     r8, [rsi+48h]
0x18007856b  cmp     r14d, 4
0x18007856f  jz      short loc_1800785A8
0x180078571  mov     rcx, [rsi+40h]
0x180078575  jmp     short loc_18007859E
0x180078577  mov     rdx, [rcx]
0x18007857a  mov     rax, [rdi]
0x18007857d  cmp     [rdx+0C8h], rax
0x180078584  jnz     short loc_18007859A
0x180078586  mov     eax, [rdx+0D8h]
0x18007858c  test    r13b, al
0x18007858f  jz      short loc_18007859A
0x180078591  and     eax, 0FFFFFFFEh
0x180078594  mov     [rdx+0D8h], eax
0x18007859a  add     rcx, 10h
0x18007859e  cmp     rcx, r8
0x1800785a1  jnz     short loc_180078577
0x1800785a3  jmp     loc_180078629
0x1800785a8  mov     rax, [rsi+40h]
0x1800785ac  xor     r10b, r10b
0x1800785af  cmp     rax, r8
0x1800785b2  jz      short loc_180078629
0x1800785b4  mov     rdx, [rax]
0x1800785b7  mov     r9, [rdi]
0x1800785ba  cmp     [rdx+0C8h], r9
0x1800785c1  jnz     short loc_1800785DD
0x1800785c3  mov     ecx, [rdx+0D8h]
0x1800785c9  test    r13b, cl
0x1800785cc  jz      short loc_1800785DD
0x1800785ce  and     ecx, 0FFFFFFFEh
0x1800785d1  mov     r10b, r13b
0x1800785d4  mov     [rdx+0D8h], ecx
0x1800785da  mov     r9, [rdi]
0x1800785dd  add     rax, 10h
0x1800785e1  cmp     rax, r8
0x1800785e4  jnz     short loc_1800785B4
0x1800785e6  test    r10b, r10b
0x1800785e9  jz      short loc_180078629
0x1800785eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800785f2  cmp     rcx, rbp
0x1800785f5  jz      short loc_18007861F
0x1800785f7  cmp     byte ptr [rcx+19h], 4
0x1800785fb  jb      short loc_18007861F
0x1800785fd  test    [rcx+1Ch], r13b
0x180078601  jz      short loc_18007861F
0x180078603  mov     rcx, [rcx+10h]
0x180078607  lea     r8, WPP_7ef1a219358f3e78125012fa23bc8b03_Traceguids
0x18007860e  add     r9, 0A28h
0x180078615  mov     edx, 0A2h
0x18007861a  call    WPP_SF__guid_
0x18007861f  mov     rax, [rdi]
0x180078622  mov     [rax+0A1Ch], r13d
0x180078629  mov     rax, [rdi]
0x18007862c  mov     ecx, [rax+0A1Ch]
0x180078632  sub     ecx, 3
0x180078635  cmp     ecx, r13d
0x180078638  ja      loc_1800787AB
0x18007863e  mov     rbp, [rsi+48h]
0x180078642  mov     rbx, [rsi+40h]
0x180078646  cmp     rbx, rbp
0x180078649  jz      loc_1800786F8
0x18007864f  lea     rsi, WPP_GLOBAL_Control
0x180078656  mov     rcx, [rbx]
0x180078659  mov     rax, [rdi]
0x18007865c  cmp     [rcx+0C8h], rax
0x180078663  jnz     loc_1800786EB
0x180078669  mov     rax, [rcx+0E0h]
0x180078670  test    rax, rax
0x180078673  jz      short loc_1800786DE
0x180078675  mov     rdx, [rcx+0E8h]
0x18007867c  mov     qword ptr [rcx+0E0h], 0
0x180078687  mov     rcx, [rbx]
0x18007868a  mov     qword ptr [rcx+0E8h], 0
0x180078695  mov     r8, [rdi]
0x180078698  mov     rcx, [rbx]
0x18007869b  mov     r8d, [r8+0C48h]
0x1800786a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800786a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800786ae  cmp     rcx, rsi
0x1800786b1  jz      short loc_1800786DE
0x1800786b3  cmp     byte ptr [rcx+19h], 4
0x1800786b7  jb      short loc_1800786DE
0x1800786b9  test    [rcx+1Ch], r13b
0x1800786bd  jz      short loc_1800786DE
0x1800786bf  mov     r9, [rdi]
0x1800786c2  lea     r8, WPP_7ef1a219358f3e78125012fa23bc8b03_Traceguids
0x1800786c9  mov     rcx, [rcx+10h]
0x1800786cd  mov     edx, 0A3h
0x1800786d2  mov     r9d, [r9+0C48h]
0x1800786d9  call    WPP_SF_d
0x1800786de  mov     rax, [rdi]
0x1800786e1  mov     dword ptr [rax+0C48h], 0
0x1800786eb  add     rbx, 10h
0x1800786ef  cmp     rbx, rbp
0x1800786f2  jnz     loc_180078656
0x1800786f8  mov     rax, [rdi]
0x1800786fb  mov     rdx, [rax+0C60h]; Timer
0x180078702  test    rdx, rdx
0x180078705  jz      loc_1800787A4
0x18007870b  xor     r8d, r8d; CompletionEvent
0x18007870e  xor     ecx, ecx; TimerQueue
0x180078710  call    cs:__imp_DeleteTimerQueueTimer
0x180078716  test    eax, eax
0x180078718  jnz     short loc_180078760
0x18007871a  mov     rax, cs:WPP_GLOBAL_Control
0x180078721  lea     rbp, WPP_GLOBAL_Control
0x180078728  cmp     rax, rbp
0x18007872b  jz      short loc_180078794
0x18007872d  cmp     byte ptr [rax+19h], 3
0x180078731  jb      short loc_180078794
0x180078733  test    [rax+1Ch], r13b
0x180078737  jz      short loc_180078794
0x180078739  call    cs:__imp_GetLastError
0x18007873f  mov     rcx, cs:WPP_GLOBAL_Control
0x180078746  lea     r8, WPP_7ef1a219358f3e78125012fa23bc8b03_Traceguids
0x18007874d  mov     edx, 0A4h
0x180078752  mov     r9d, eax
0x180078755  mov     rcx, [rcx+10h]
0x180078759  call    WPP_SF_d
0x18007875e  jmp     short loc_180078794
0x180078760  mov     rcx, cs:WPP_GLOBAL_Control
0x180078767  lea     rbp, WPP_GLOBAL_Control
0x18007876e  cmp     rcx, rbp
0x180078771  jz      short loc_180078794
0x180078773  cmp     byte ptr [rcx+19h], 4
0x180078777  jb      short loc_180078794
0x180078779  test    [rcx+1Ch], r13b
0x18007877d  jz      short loc_180078794
0x18007877f  mov     rcx, [rcx+10h]
0x180078783  lea     r8, WPP_7ef1a219358f3e78125012fa23bc8b03_Traceguids
0x18007878a  mov     edx, 0A5h
0x18007878f  call    WPP_SF_
0x180078794  mov     rax, [rdi]
0x180078797  mov     qword ptr [rax+0C60h], 0
0x1800787a2  jmp     short loc_1800787AB
0x1800787a4  lea     rbp, WPP_GLOBAL_Control
0x1800787ab  mov     rax, [rdi]
0x1800787ae  mov     ecx, [rax+0A1Ch]
0x1800787b4  cmp     ecx, r13d
0x1800787b7  jz      short loc_18007882A
0x1800787b9  cmp     ecx, 2
0x1800787bc  jz      loc_180078908
0x1800787c2  mov     rdx, [rax+0C58h]; Timer
0x1800787c9  test    rdx, rdx
0x1800787cc  jz      loc_180078908
0x1800787d2  xor     r8d, r8d; CompletionEvent
0x1800787d5  xor     ecx, ecx; TimerQueue
0x1800787d7  call    cs:__imp_DeleteTimerQueueTimer
0x1800787dd  test    eax, eax
0x1800787df  jnz     short loc_180078817
0x1800787e1  call    cs:__imp_GetLastError
0x1800787e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800787ee  cmp     rcx, rbp
0x1800787f1  jz      short loc_180078817
0x1800787f3  cmp     [rcx+19h], r13b
0x1800787f7  jb      short loc_180078817
0x1800787f9  test    [rcx+1Ch], r13b
0x1800787fd  jz      short loc_180078817
0x1800787ff  mov     rcx, [rcx+10h]
0x180078803  lea     r8, WPP_7ef1a219358f3e78125012fa23bc8b03_Traceguids
0x18007880a  mov     edx, 0A6h
0x18007880f  mov     r9d, eax
0x180078812  call    WPP_SF_d
0x180078817  mov     rax, [rdi]
0x18007881a  mov     qword ptr [rax+0C58h], 0
0x180078825  jmp     loc_180078908
0x18007882a  cmp     qword ptr [rax+0C58h], 0
0x180078832  jnz     loc_180078908
0x180078838  lea     rcx, [rsp+68h+arg_10]; unsigned int *
0x180078840  mov     [rsp+68h+arg_10], 0
0x18007884b  call    ?GetOnDemandStartTimeout@ConfigManager@@SAKPEAK@Z; ConfigManager::GetOnDemandStartTimeout(ulong *)
0x180078850  test    eax, eax
0x180078852  jnz     short loc_18007885F
0x180078854  mov     ebx, [rsp+68h+arg_10]
0x18007885b  test    ebx, ebx
0x18007885d  jnz     short loc_180078864
0x18007885f  mov     ebx, 493E0h
0x180078864  mov     r9, [rdi]; Parameter
0x180078867  lea     r8, ?OnDemandStartTimeoutCallback@OnDemand@@CAXPEAXE@Z; Callback
0x18007886e  mov     [rsp+68h+Flags], 0; Flags
0x180078876  xor     edx, edx; TimerQueue
0x180078878  mov     [rsp+68h+Period], 0; Period
0x180078880  mov     [rsp+68h+DueTime], ebx; DueTime
0x180078884  lea     rcx, [r9+0C58h]; phNewTimer
0x18007888b  call    cs:__imp_CreateTimerQueueTimer
0x180078891  test    eax, eax
0x180078893  jnz     short loc_1800788CD
0x180078895  call    cs:__imp_GetLastError
0x18007889b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800788a2  cmp     rcx, rbp
0x1800788a5  jz      short loc_180078908
0x1800788a7  cmp     [rcx+19h], r13b
0x1800788ab  jb      short loc_180078908
0x1800788ad  test    [rcx+1Ch], r13b
0x1800788b1  jz      short loc_180078908
0x1800788b3  mov     rcx, [rcx+10h]
0x1800788b7  lea     r8, WPP_7ef1a219358f3e78125012fa23bc8b03_Traceguids
0x1800788be  mov     edx, 0A7h
0x1800788c3  mov     r9d, eax
0x1800788c6  call    WPP_SF_d
0x1800788cb  jmp     short loc_180078908
0x1800788cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800788d4  cmp     rcx, rbp
0x1800788d7  jz      short loc_180078908
0x1800788d9  cmp     byte ptr [rcx+19h], 4
0x1800788dd  jb      short loc_180078908
0x1800788df  test    [rcx+1Ch], r13b
0x1800788e3  jz      short loc_180078908
0x1800788e5  mov     r9, [rdi]
0x1800788e8  lea     r8, WPP_7ef1a219358f3e78125012fa23bc8b03_Traceguids
0x1800788ef  mov     rcx, [rcx+10h]
0x1800788f3  add     r9, 214h
0x1800788fa  mov     edx, 0A8h
0x1800788ff  mov     [rsp+68h+DueTime], ebx
0x180078903  call    WPP_SF_Sd
0x180078908  mov     r8, [rdi]
0x18007890b  mov     edx, [r8+0A1Ch]
0x180078912  cmp     r15d, edx
0x180078915  jz      short loc_180078948
0x180078917  test    cs:Microsoft_Windows_WcmsvcEnableBits, 2
0x18007891e  jz      short loc_180078948
0x180078920  lea     rax, [r8+14h]
0x180078924  mov     [rsp+68h+Flags], edx
0x180078928  lea     rcx, [r8+214h]
0x18007892f  mov     qword ptr [rsp+68h+Period], rax
0x180078934  lea     r9, [r8+0A38h]
0x18007893b  mov     qword ptr [rsp+68h+DueTime], rcx
0x180078940  mov     r8d, [r8]
0x180078943  call    McTemplateU0qjzzqq_EtwEventWriteTransfer
0x180078948  cmp     r14d, 4
0x18007894c  jnz     short loc_180078960
0x18007894e  mov     rax, [rdi]
0x180078951  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180078958  movdqu  xmmword ptr [rax+0A28h], xmm0
0x180078960  mov     r8, rdi
0x180078963  lea     rdx, aStateChangeCal; "State change called."
0x18007896a  mov     rbx, [rsp+68h+arg_0]
0x18007896f  mov     rbp, [rsp+68h+arg_8]
0x180078974  add     rsp, 40h
0x180078978  pop     r15
0x18007897a  pop     r14
0x18007897c  pop     r13
0x18007897e  pop     rdi
0x18007897f  pop     rsi
0x180078980  jmp     ?LogInterfaceInfo@OnDemand@@AEAAXPEBGAEBV?$shared_ptr@UOnDemandInterfaceInfo@OnDemand@@@std@@@Z; OnDemand::LogInterfaceInfo(ushort const *,std::shared_ptr<OnDemand::OnDemandInterfaceInfo> const &)
```
