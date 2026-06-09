# OsEventsCleanup(bool)

- ea: `0x180087784`
- end: `0x180087951`
- name: `?OsEventsCleanup@@YAJ_N@Z`
- size: `461`
- prototype: `__int64 __fastcall(bool)`
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x18005e4e4`
- `0x180080d50`
- `0x180094248`
- `0x1800c1a08`

## callees

- `0x180003de0`
- `0x18001c320`
- `0x180087784`
- `0x180087958`
- `0x180087a60`
- `0x180087a88`
- `0x180092ee4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800877f9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180087812`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800877f9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180087812`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008782f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008784c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008782f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008784c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800877e5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800877e5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180087865`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180087865`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800878b6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800878b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180087887`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800878a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800878d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800878fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180087887`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800878a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800878d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800878fa`

## pseudocode

```c
__int64 __fastcall OsEventsCleanup(char a1)
{
  HKEY v2; // rcx
  HKEY v3; // rcx
  __int64 v4; // rcx
  HANDLE v5; // rcx
  HANDLE v6; // rcx
  HANDLE v7; // rcx
  HANDLE v8; // rcx
  void *v9; // rcx
  __int64 result; // rax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_2c2d62d8dcc43732bdae633c77dd2d8d_Traceguids);
  }
  if ( a1 )
  {
    OsEventsPublish6006();
    if ( qword_180111DC8 )
    {
      RegDeleteKeyExW(qword_180111DC8, L"RunHistory", 0, 0);
      RegDeleteValueW(qword_180111DC8, L"6005BT");
    }
    if ( hKey )
      RegDeleteValueW(hKey, L"LastAliveStamp");
  }
  v2 = qword_180111DC8;
  qword_180111DC8 = 0;
  if ( v2 )
    RegCloseKey(v2);
  v3 = hKey;
  hKey = 0;
  if ( v3 )
    RegCloseKey(v3);
  OsEventsThreadStop();
  tlx::unique_any<tlx::handle_traits<void *,unsigned long (void *),&unsigned long PowerSettingUnregisterNotification(void *),0>>::reset(
    v4,
    0);
  AcquireSRWLockExclusive(&stru_180111570);
  v5 = hObject;
  hObject = 0;
  if ( (unsigned __int64)v5 + 1 > 1 )
    CloseHandle(v5);
  v6 = qword_180111560;
  qword_180111560 = 0;
  if ( (unsigned __int64)v6 + 1 > 1 )
    CloseHandle(v6);
  ReleaseSRWLockExclusive(&stru_180111570);
  v7 = hTimer;
  hTimer = 0;
  if ( (unsigned __int64)v7 + 1 > 1 )
    CloseHandle(v7);
  v8 = qword_180111550;
  qword_180111550 = 0;
  if ( (unsigned __int64)v8 + 1 > 1 )
    CloseHandle(v8);
  v9 = gNoonEventInfo;
  gNoonEventInfo = 0;
  if ( v9 )
    operator delete(v9);
  qword_180111DE0 = 0;
  qword_180111DE8 = 0;
  wmi::AutoRef<PublisherMetadata>::Release(&g_EventLogPublisher);
  result = 0;
  g_EventLogPublisher = 0;
  return result;
}

```

## disassembly

```asm
0x180087784  push    rbx
0x180087786  sub     rsp, 20h
0x18008778a  mov     bl, cl
0x18008778c  mov     rcx, cs:WPP_GLOBAL_Control
0x180087793  lea     rax, WPP_GLOBAL_Control
0x18008779a  cmp     rcx, rax
0x18008779d  jz      short loc_1800877C3
0x18008779f  test    dword ptr [rcx+1Ch], 4000h
0x1800877a6  jz      short loc_1800877C3
0x1800877a8  cmp     byte ptr [rcx+19h], 4
0x1800877ac  jb      short loc_1800877C3
0x1800877ae  mov     rcx, [rcx+10h]
0x1800877b2  lea     r8, WPP_2c2d62d8dcc43732bdae633c77dd2d8d_Traceguids
0x1800877b9  mov     edx, 36h ; '6'
0x1800877be  call    WPP_SF_
0x1800877c3  test    bl, bl
0x1800877c5  jz      short loc_180087818
0x1800877c7  call    OsEventsPublish6006
0x1800877cc  mov     rcx, cs:qword_180111DC8; hKey
0x1800877d3  test    rcx, rcx
0x1800877d6  jz      short loc_1800877FF
0x1800877d8  xor     r9d, r9d; Reserved
0x1800877db  lea     rdx, aRunhistory; "RunHistory"
0x1800877e2  xor     r8d, r8d; samDesired
0x1800877e5  call    cs:__imp_RegDeleteKeyExW
0x1800877eb  mov     rcx, cs:qword_180111DC8; hKey
0x1800877f2  lea     rdx, a6005bt; "6005BT"
0x1800877f9  call    cs:__imp_RegDeleteValueW
0x1800877ff  mov     rcx, cs:hKey; hKey
0x180087806  test    rcx, rcx
0x180087809  jz      short loc_180087818
0x18008780b  lea     rdx, aLastalivestamp; "LastAliveStamp"
0x180087812  call    cs:__imp_RegDeleteValueW
0x180087818  mov     rcx, cs:qword_180111DC8; hKey
0x18008781f  mov     cs:qword_180111DC8, 0
0x18008782a  test    rcx, rcx
0x18008782d  jz      short loc_180087835
0x18008782f  call    cs:__imp_RegCloseKey
0x180087835  mov     rcx, cs:hKey; hKey
0x18008783c  mov     cs:hKey, 0
0x180087847  test    rcx, rcx
0x18008784a  jz      short loc_180087852
0x18008784c  call    cs:__imp_RegCloseKey
0x180087852  call    OsEventsThreadStop
0x180087857  xor     edx, edx
0x180087859  call    ?reset@?$unique_any@U?$handle_traits@PEAX$$A6AKPEAX@Z$1?PowerSettingUnregisterNotification@@YAK0@Z$0A@@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::handle_traits<void *,ulong (void *),&PowerSettingUnregisterNotification(void *),0>>::reset(void *)
0x18008785e  lea     rcx, stru_180111570; SRWLock
0x180087865  call    cs:__imp_AcquireSRWLockExclusive
0x18008786b  mov     rcx, cs:hObject; hObject
0x180087872  mov     cs:hObject, 0
0x18008787d  lea     rax, [rcx+1]
0x180087881  cmp     rax, 1
0x180087885  jbe     short loc_18008788D
0x180087887  call    cs:__imp_CloseHandle
0x18008788d  mov     rcx, cs:qword_180111560; hObject
0x180087894  mov     cs:qword_180111560, 0
0x18008789f  lea     rax, [rcx+1]
0x1800878a3  cmp     rax, 1
0x1800878a7  jbe     short loc_1800878AF
0x1800878a9  call    cs:__imp_CloseHandle
0x1800878af  lea     rcx, stru_180111570; SRWLock
0x1800878b6  call    cs:__imp_ReleaseSRWLockExclusive
0x1800878bc  mov     rcx, cs:hTimer; hObject
0x1800878c3  mov     cs:hTimer, 0
0x1800878ce  lea     rax, [rcx+1]
0x1800878d2  cmp     rax, 1
0x1800878d6  jbe     short loc_1800878DE
0x1800878d8  call    cs:__imp_CloseHandle
0x1800878de  mov     rcx, cs:qword_180111550; hObject
0x1800878e5  mov     cs:qword_180111550, 0
0x1800878f0  lea     rax, [rcx+1]
0x1800878f4  cmp     rax, 1
0x1800878f8  jbe     short loc_180087900
0x1800878fa  call    cs:__imp_CloseHandle
0x180087900  mov     rcx, cs:?gNoonEventInfo@@3UNoon_Event_Info@@A; void *
0x180087907  mov     cs:?gNoonEventInfo@@3UNoon_Event_Info@@A, 0; Noon_Event_Info gNoonEventInfo
0x180087912  test    rcx, rcx
0x180087915  jz      short loc_18008791C
0x180087917  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18008791c  lea     rcx, ?g_EventLogPublisher@@3V?$AutoRef@VPublisher@@@wmi@@A; wmi::AutoRef<Publisher> g_EventLogPublisher
0x180087923  mov     cs:qword_180111DE0, 0
0x18008792e  mov     cs:qword_180111DE8, 0
0x180087939  call    ?Release@?$AutoRef@VPublisherMetadata@@@wmi@@QEAAXXZ; wmi::AutoRef<PublisherMetadata>::Release(void)
0x18008793e  xor     eax, eax
0x180087940  mov     cs:?g_EventLogPublisher@@3V?$AutoRef@VPublisher@@@wmi@@A, 0; wmi::AutoRef<Publisher> g_EventLogPublisher
0x18008794b  add     rsp, 20h
0x18008794f  pop     rbx
0x180087950  retn
```
