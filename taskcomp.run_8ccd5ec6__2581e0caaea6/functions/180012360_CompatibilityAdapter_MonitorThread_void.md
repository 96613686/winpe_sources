# CompatibilityAdapter::MonitorThread(void *)

- ea: `0x180012360`
- end: `0x18001258b`
- name: `?MonitorThread@CompatibilityAdapter@@SAJPEAX@Z`
- size: `555`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180002cb0`
- `0x180005894`
- `0x180005c10`
- `0x180006498`
- `0x18000cf80`
- `0x18000eb64`
- `0x180012360`
- `0x180012594`
- `0x180012d8c`
- `0x180030700`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180012450`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180012450`
- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x180012502`
- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x180012502`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001252a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001252a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800123bc`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800123bc`

## pseudocode

```c
__int64 __fastcall CompatibilityAdapter::MonitorThread(PVOID Parameter)
{
  CompatibilityAdapter *v1; // rcx
  struct CompatibilityAdapter *Adapter; // rsi
  int v4; // eax
  void *v5; // r9
  unsigned int v6; // ebx
  HRESULT v7; // eax
  void *v8; // r9
  unsigned int v9; // edi
  DWORD v10; // eax
  __int64 v11; // r8
  DWORD v12; // ebx
  JournalReader *v13; // rbx
  DWORD LastError; // eax
  JournalReader *v15; // rcx
  HANDLE Handles[2]; // [rsp+30h] [rbp-58h] BYREF
  __int128 v17; // [rsp+40h] [rbp-48h]
  __int64 v18; // [rsp+50h] [rbp-38h]

  Adapter = CompatibilityAdapter::GetAdapter();
  if ( !Adapter )
    return 2147500037LL;
  v4 = CompatibilityAdapter::ResetStatus(v1);
  v6 = v4;
  if ( v4 < 0 )
  {
    EventManager::EvtReport(g_pEventManager, &COMPAT_DIRECTORY_MONITOR_FAILED, v4, v5);
    return v6;
  }
  v7 = CoInitializeEx(0, 0);
  v9 = v7;
  if ( v7 < 0 )
  {
    EventManager::EvtReport(g_pEventManager, &COMPAT_DIRECTORY_MONITOR_FAILED, v7, v8);
    return v9;
  }
  *(_OWORD *)Handles = 0;
  v18 = 0;
  v17 = 0;
  Handles[0] = *((HANDLE *)JournalReader::s_pReader + 1);
  Handles[1] = *((HANDLE *)Adapter + 10);
  *(_QWORD *)&v17 = *((_QWORD *)Adapter + 11);
  *((_QWORD *)&v17 + 1) = *((_QWORD *)JournalReader::s_pReader + 8);
  v18 = *((_QWORD *)JournalReader::s_pReader + 9);
  while ( 1 )
  {
    while ( 1 )
    {
      v10 = WaitForMultipleObjectsEx(5u, Handles, 0, 0xFFFFFFFF, 0);
      v12 = v10;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids, v10);
      }
      if ( v12 )
        break;
      JournalReader::_ReadUsnJournal(JournalReader::s_pReader, 0, v11);
    }
    if ( v12 == 1 )
      break;
    switch ( v12 )
    {
      case 2u:
        CompatibilityAdapter::ProcessJobStatus(Adapter);
        break;
      case 3u:
        v15 = JournalReader::s_pReader;
        goto LABEL_30;
      case 4u:
        v13 = JournalReader::s_pReader;
        if ( !CancelWaitableTimer(*((HANDLE *)JournalReader::s_pReader + 8))
          && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          LastError = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_880a4eb608c037d792798d7e53d23858_Traceguids, LastError);
        }
        v15 = v13;
LABEL_30:
        JournalReader::HandleWaitTimer(v15);
        break;
      case 0x80u:
      case 0x81u:
      case 0x82u:
      case 0xFFFFFFFF:
        goto LABEL_21;
    }
  }
LABEL_21:
  CompatibilityAdapter::Cleanup(1);
  return v9;
}

```

## disassembly

```asm
0x180012360  push    rbx
0x180012362  push    rsi
0x180012363  push    rdi
0x180012364  push    r14
0x180012366  sub     rsp, 68h
0x18001236a  mov     rax, cs:__security_cookie
0x180012371  xor     rax, rsp
0x180012374  mov     [rsp+88h+var_30], rax
0x180012379  call    ?GetAdapter@CompatibilityAdapter@@SAPEAV1@XZ; CompatibilityAdapter::GetAdapter(void)
0x18001237e  mov     rsi, rax
0x180012381  test    rax, rax
0x180012384  jnz     short loc_180012390
0x180012386  mov     eax, 80004005h
0x18001238b  jmp     loc_1800124DF
0x180012390  call    ?ResetStatus@CompatibilityAdapter@@QEAAJXZ; CompatibilityAdapter::ResetStatus(void)
0x180012395  mov     ebx, eax
0x180012397  test    eax, eax
0x180012399  jns     short loc_1800123B8
0x18001239b  mov     rcx, cs:?g_pEventManager@@3PEAVEventManager@@EA; this
0x1800123a2  lea     rdx, COMPAT_DIRECTORY_MONITOR_FAILED; struct _EVENT_DESCRIPTOR *
0x1800123a9  mov     r8d, eax; unsigned int
0x1800123ac  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@KPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ulong,void *,_GUID const *)
0x1800123b1  mov     eax, ebx
0x1800123b3  jmp     loc_1800124DF
0x1800123b8  xor     edx, edx; dwCoInit
0x1800123ba  xor     ecx, ecx; pvReserved
0x1800123bc  call    cs:__imp_CoInitializeEx
0x1800123c3  nop     dword ptr [rax+rax+00h]
0x1800123c8  mov     edi, eax
0x1800123ca  test    eax, eax
0x1800123cc  jns     short loc_1800123E9
0x1800123ce  mov     rcx, cs:?g_pEventManager@@3PEAVEventManager@@EA; this
0x1800123d5  lea     rdx, COMPAT_DIRECTORY_MONITOR_FAILED; struct _EVENT_DESCRIPTOR *
0x1800123dc  mov     r8d, eax; unsigned int
0x1800123df  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@KPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ulong,void *,_GUID const *)
0x1800123e4  jmp     loc_1800124DD
0x1800123e9  mov     rcx, cs:?s_pReader@JournalReader@@0PEAV1@EA; JournalReader * JournalReader::s_pReader
0x1800123f0  lea     r14, WPP_GLOBAL_Control
0x1800123f7  xor     eax, eax
0x1800123f9  xorps   xmm0, xmm0
0x1800123fc  movups  xmmword ptr [rsp+88h+Handles], xmm0
0x180012401  mov     [rsp+88h+var_38], rax
0x180012406  movups  [rsp+88h+var_48], xmm0
0x18001240b  mov     rax, [rcx+8]
0x18001240f  mov     [rsp+88h+Handles], rax
0x180012414  mov     rax, [rsi+50h]
0x180012418  mov     [rsp+88h+Handles+8], rax
0x18001241d  mov     rax, [rsi+58h]
0x180012421  mov     qword ptr [rsp+88h+var_48], rax
0x180012426  mov     rax, [rcx+40h]
0x18001242a  mov     qword ptr [rsp+88h+var_48+8], rax
0x18001242f  mov     rax, [rcx+48h]
0x180012433  mov     [rsp+88h+var_38], rax
0x180012438  xor     r8d, r8d; bWaitAll
0x18001243b  mov     [rsp+88h+bAlertable], 0; bAlertable
0x180012443  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180012447  lea     rdx, [rsp+88h+Handles]; lpHandles
0x18001244c  lea     ecx, [r8+5]; nCount
0x180012450  call    cs:__imp_WaitForMultipleObjectsEx
0x180012457  nop     dword ptr [rax+rax+00h]
0x18001245c  mov     ebx, eax
0x18001245e  mov     rcx, cs:WPP_GLOBAL_Control
0x180012465  cmp     rcx, r14
0x180012468  jz      short loc_18001248E
0x18001246a  test    byte ptr [rcx+1Ch], 2
0x18001246e  jz      short loc_18001248E
0x180012470  cmp     byte ptr [rcx+19h], 4
0x180012474  jb      short loc_18001248E
0x180012476  mov     rcx, [rcx+10h]
0x18001247a  lea     r8, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids
0x180012481  mov     edx, 10h
0x180012486  mov     r9d, eax
0x180012489  call    WPP_SF_d
0x18001248e  test    ebx, ebx
0x180012490  jz      loc_180012578
0x180012496  cmp     ebx, 1
0x180012499  jz      short loc_1800124D3
0x18001249b  cmp     ebx, 2
0x18001249e  jz      loc_18001256B
0x1800124a4  cmp     ebx, 3
0x1800124a7  jz      loc_18001255A
0x1800124ad  cmp     ebx, 4
0x1800124b0  jz      short loc_1800124F7
0x1800124b2  cmp     ebx, 80h
0x1800124b8  jz      short loc_1800124D3
0x1800124ba  cmp     ebx, 81h
0x1800124c0  jz      short loc_1800124D3
0x1800124c2  cmp     ebx, 82h
0x1800124c8  jz      short loc_1800124D3
0x1800124ca  cmp     ebx, 0FFFFFFFFh
0x1800124cd  jnz     loc_180012438
0x1800124d3  mov     ecx, 1; int
0x1800124d8  call    ?Cleanup@CompatibilityAdapter@@SAJH@Z; CompatibilityAdapter::Cleanup(int)
0x1800124dd  mov     eax, edi
0x1800124df  mov     rcx, [rsp+88h+var_30]
0x1800124e4  xor     rcx, rsp; StackCookie
0x1800124e7  call    __security_check_cookie
0x1800124ec  add     rsp, 68h
0x1800124f0  pop     r14
0x1800124f2  pop     rdi
0x1800124f3  pop     rsi
0x1800124f4  pop     rbx
0x1800124f5  retn
0x1800124f7  mov     rbx, cs:?s_pReader@JournalReader@@0PEAV1@EA; JournalReader * JournalReader::s_pReader
0x1800124fe  mov     rcx, [rbx+40h]; hTimer
0x180012502  call    cs:__imp_CancelWaitableTimer
0x180012509  nop     dword ptr [rax+rax+00h]
0x18001250e  test    eax, eax
0x180012510  jnz     short loc_180012555
0x180012512  mov     rax, cs:WPP_GLOBAL_Control
0x180012519  cmp     rax, r14
0x18001251c  jz      short loc_180012555
0x18001251e  test    byte ptr [rax+1Ch], 2
0x180012522  jz      short loc_180012555
0x180012524  cmp     byte ptr [rax+19h], 2
0x180012528  jb      short loc_180012555
0x18001252a  call    cs:__imp_GetLastError
0x180012531  nop     dword ptr [rax+rax+00h]
0x180012536  mov     rcx, cs:WPP_GLOBAL_Control
0x18001253d  lea     r8, WPP_880a4eb608c037d792798d7e53d23858_Traceguids
0x180012544  mov     edx, 23h ; '#'
0x180012549  mov     r9d, eax
0x18001254c  mov     rcx, [rcx+10h]
0x180012550  call    WPP_SF_d
0x180012555  mov     rcx, rbx
0x180012558  jmp     short loc_180012561
0x18001255a  mov     rcx, cs:?s_pReader@JournalReader@@0PEAV1@EA; this
0x180012561  call    ?HandleWaitTimer@JournalReader@@QEAAJXZ; JournalReader::HandleWaitTimer(void)
0x180012566  jmp     loc_180012438
0x18001256b  mov     rcx, rsi; this
0x18001256e  call    ?ProcessJobStatus@CompatibilityAdapter@@QEAAXXZ; CompatibilityAdapter::ProcessJobStatus(void)
0x180012573  jmp     loc_180012438
0x180012578  mov     rcx, cs:?s_pReader@JournalReader@@0PEAV1@EA; this
0x18001257f  xor     edx, edx; int
0x180012581  call    ?_ReadUsnJournal@JournalReader@@AEAAJH@Z; JournalReader::_ReadUsnJournal(int)
0x180012586  jmp     loc_180012438
```
