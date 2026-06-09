# CompatibilityAdapter::MonitorThread(void *)

- ea: `0x180011880`
- end: `0x180011a92`
- name: `?MonitorThread@CompatibilityAdapter@@SAJPEAX@Z`
- size: `530`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180002b90`
- `0x1800055d0`
- `0x1800058f0`
- `0x1800060e0`
- `0x18000c760`
- `0x18000e274`
- `0x180011880`
- `0x180011a98`
- `0x18001225c`
- `0x18002e5b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001196a`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001196a`
- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x180011a15`
- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x180011a15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011a37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011a37`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800118dc`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800118dc`

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
    EventManager::EvtReport(g_pEventManager, &COMPAT_DIRECTORY_MONITOR_FAILED, (unsigned int)v4, v5);
    return v6;
  }
  v7 = CoInitializeEx(0, 0);
  v9 = v7;
  if ( v7 < 0 )
  {
    EventManager::EvtReport(g_pEventManager, &COMPAT_DIRECTORY_MONITOR_FAILED, (unsigned int)v7, v8);
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
0x180011880  push    rbx
0x180011882  push    rsi
0x180011883  push    rdi
0x180011884  push    r14
0x180011886  sub     rsp, 68h
0x18001188a  mov     rax, cs:__security_cookie
0x180011891  xor     rax, rsp
0x180011894  mov     [rsp+88h+var_30], rax
0x180011899  call    ?GetAdapter@CompatibilityAdapter@@SAPEAV1@XZ; CompatibilityAdapter::GetAdapter(void)
0x18001189e  mov     rsi, rax
0x1800118a1  test    rax, rax
0x1800118a4  jnz     short loc_1800118B0
0x1800118a6  mov     eax, 80004005h
0x1800118ab  jmp     loc_1800119F3
0x1800118b0  call    ?ResetStatus@CompatibilityAdapter@@QEAAJXZ; CompatibilityAdapter::ResetStatus(void)
0x1800118b5  mov     ebx, eax
0x1800118b7  test    eax, eax
0x1800118b9  jns     short loc_1800118D8
0x1800118bb  mov     rcx, cs:?g_pEventManager@@3PEAVEventManager@@EA; this
0x1800118c2  lea     rdx, COMPAT_DIRECTORY_MONITOR_FAILED; struct _EVENT_DESCRIPTOR *
0x1800118c9  mov     r8d, eax; unsigned int
0x1800118cc  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@KPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ulong,void *,_GUID const *)
0x1800118d1  mov     eax, ebx
0x1800118d3  jmp     loc_1800119F3
0x1800118d8  xor     edx, edx; dwCoInit
0x1800118da  xor     ecx, ecx; pvReserved
0x1800118dc  call    cs:__imp_CoInitializeEx
0x1800118e2  mov     edi, eax
0x1800118e4  test    eax, eax
0x1800118e6  jns     short loc_180011903
0x1800118e8  mov     rcx, cs:?g_pEventManager@@3PEAVEventManager@@EA; this
0x1800118ef  lea     rdx, COMPAT_DIRECTORY_MONITOR_FAILED; struct _EVENT_DESCRIPTOR *
0x1800118f6  mov     r8d, eax; unsigned int
0x1800118f9  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@KPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ulong,void *,_GUID const *)
0x1800118fe  jmp     loc_1800119F1
0x180011903  mov     rcx, cs:?s_pReader@JournalReader@@0PEAV1@EA; JournalReader * JournalReader::s_pReader
0x18001190a  lea     r14, WPP_GLOBAL_Control
0x180011911  xor     eax, eax
0x180011913  xorps   xmm0, xmm0
0x180011916  movups  xmmword ptr [rsp+88h+Handles], xmm0
0x18001191b  mov     [rsp+88h+var_38], rax
0x180011920  movups  [rsp+88h+var_48], xmm0
0x180011925  mov     rax, [rcx+8]
0x180011929  mov     [rsp+88h+Handles], rax
0x18001192e  mov     rax, [rsi+50h]
0x180011932  mov     [rsp+88h+Handles+8], rax
0x180011937  mov     rax, [rsi+58h]
0x18001193b  mov     qword ptr [rsp+88h+var_48], rax
0x180011940  mov     rax, [rcx+40h]
0x180011944  mov     qword ptr [rsp+88h+var_48+8], rax
0x180011949  mov     rax, [rcx+48h]
0x18001194d  mov     [rsp+88h+var_38], rax
0x180011952  xor     r8d, r8d; bWaitAll
0x180011955  mov     [rsp+88h+bAlertable], 0; bAlertable
0x18001195d  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180011961  lea     rdx, [rsp+88h+Handles]; lpHandles
0x180011966  lea     ecx, [r8+5]; nCount
0x18001196a  call    cs:__imp_WaitForMultipleObjectsEx
0x180011970  mov     ebx, eax
0x180011972  mov     rcx, cs:WPP_GLOBAL_Control
0x180011979  cmp     rcx, r14
0x18001197c  jz      short loc_1800119A2
0x18001197e  test    byte ptr [rcx+1Ch], 2
0x180011982  jz      short loc_1800119A2
0x180011984  cmp     byte ptr [rcx+19h], 4
0x180011988  jb      short loc_1800119A2
0x18001198a  mov     rcx, [rcx+10h]
0x18001198e  lea     r8, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids
0x180011995  mov     edx, 10h
0x18001199a  mov     r9d, eax
0x18001199d  call    WPP_SF_d
0x1800119a2  test    ebx, ebx
0x1800119a4  jz      loc_180011A7F
0x1800119aa  cmp     ebx, 1
0x1800119ad  jz      short loc_1800119E7
0x1800119af  cmp     ebx, 2
0x1800119b2  jz      loc_180011A72
0x1800119b8  cmp     ebx, 3
0x1800119bb  jz      loc_180011A61
0x1800119c1  cmp     ebx, 4
0x1800119c4  jz      short loc_180011A0A
0x1800119c6  cmp     ebx, 80h
0x1800119cc  jz      short loc_1800119E7
0x1800119ce  cmp     ebx, 81h
0x1800119d4  jz      short loc_1800119E7
0x1800119d6  cmp     ebx, 82h
0x1800119dc  jz      short loc_1800119E7
0x1800119de  cmp     ebx, 0FFFFFFFFh
0x1800119e1  jnz     loc_180011952
0x1800119e7  mov     ecx, 1; int
0x1800119ec  call    ?Cleanup@CompatibilityAdapter@@SAJH@Z; CompatibilityAdapter::Cleanup(int)
0x1800119f1  mov     eax, edi
0x1800119f3  mov     rcx, [rsp+88h+var_30]
0x1800119f8  xor     rcx, rsp; StackCookie
0x1800119fb  call    __security_check_cookie
0x180011a00  add     rsp, 68h
0x180011a04  pop     r14
0x180011a06  pop     rdi
0x180011a07  pop     rsi
0x180011a08  pop     rbx
0x180011a09  retn
0x180011a0a  mov     rbx, cs:?s_pReader@JournalReader@@0PEAV1@EA; JournalReader * JournalReader::s_pReader
0x180011a11  mov     rcx, [rbx+40h]; hTimer
0x180011a15  call    cs:__imp_CancelWaitableTimer
0x180011a1b  test    eax, eax
0x180011a1d  jnz     short loc_180011A5C
0x180011a1f  mov     rax, cs:WPP_GLOBAL_Control
0x180011a26  cmp     rax, r14
0x180011a29  jz      short loc_180011A5C
0x180011a2b  test    byte ptr [rax+1Ch], 2
0x180011a2f  jz      short loc_180011A5C
0x180011a31  cmp     byte ptr [rax+19h], 2
0x180011a35  jb      short loc_180011A5C
0x180011a37  call    cs:__imp_GetLastError
0x180011a3d  mov     rcx, cs:WPP_GLOBAL_Control
0x180011a44  lea     r8, WPP_880a4eb608c037d792798d7e53d23858_Traceguids
0x180011a4b  mov     edx, 23h ; '#'
0x180011a50  mov     r9d, eax
0x180011a53  mov     rcx, [rcx+10h]
0x180011a57  call    WPP_SF_d
0x180011a5c  mov     rcx, rbx
0x180011a5f  jmp     short loc_180011A68
0x180011a61  mov     rcx, cs:?s_pReader@JournalReader@@0PEAV1@EA; this
0x180011a68  call    ?HandleWaitTimer@JournalReader@@QEAAJXZ; JournalReader::HandleWaitTimer(void)
0x180011a6d  jmp     loc_180011952
0x180011a72  mov     rcx, rsi; this
0x180011a75  call    ?ProcessJobStatus@CompatibilityAdapter@@QEAAXXZ; CompatibilityAdapter::ProcessJobStatus(void)
0x180011a7a  jmp     loc_180011952
0x180011a7f  mov     rcx, cs:?s_pReader@JournalReader@@0PEAV1@EA; this
0x180011a86  xor     edx, edx; int
0x180011a88  call    ?_ReadUsnJournal@JournalReader@@AEAAJH@Z; JournalReader::_ReadUsnJournal(int)
0x180011a8d  jmp     loc_180011952
```
