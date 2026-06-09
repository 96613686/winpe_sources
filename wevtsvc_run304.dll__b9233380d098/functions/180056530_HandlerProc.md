# HandlerProc

- ea: `0x180056530`
- end: `0x180056674`
- name: `HandlerProc`
- size: `324`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callees

- `0x180056530`
- `0x180056714`
- `0x180092008`
- `0x1800c2358`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800565fa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800565fa`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180056594`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180056653`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180056594`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180056653`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180056587`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180056587`

## pseudocode

```c
__int64 __fastcall HandlerProc(
        DWORD dwControl,
        DWORD dwEventType,
        struct POWERBROADCAST_SETTING *lpEventData,
        LPVOID lpContext)
{
  PVOID *v6; // rcx
  unsigned int v7; // edi
  RTL_SRWLOCK *v9; // [rsp+20h] [rbp-38h] BYREF
  char v10; // [rsp+28h] [rbp-30h]

  if ( dwControl == 4 )
    return 0;
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, &WPP_c81622dadc0b34ee49a8cc9df4a5609a_Traceguids, dwControl);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  v7 = 0;
  switch ( dwControl )
  {
    case 1u:
      goto LABEL_7;
    case 5u:
      g_systemShutdown = 1;
LABEL_7:
      ServiceStatus.dwCurrentState = 3;
      SetServiceStatus(g_serviceControl, &ServiceStatus);
      SetEvent(hEvent);
LABEL_8:
      v6 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_9;
    case 0xDu:
      OsEventsPowerEvent(lpEventData);
      goto LABEL_8;
    case 0x10u:
      v9 = &stru_180111570;
      AcquireSRWLockShared(&stru_180111570);
      v10 = 1;
      if ( (unsigned __int64)qword_180111560 + 1 > 1 )
        SetEvent(qword_180111560);
      utl::shared_lock<utl::shared_mutex>::~shared_lock<utl::shared_mutex>(&v9);
      goto LABEL_8;
  }
  v7 = 120;
LABEL_9:
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 && *((_BYTE *)v6 + 25) >= 4u )
    WPP_SF_d(v6[2], 64, &WPP_c81622dadc0b34ee49a8cc9df4a5609a_Traceguids, dwControl);
  return v7;
}

```

## disassembly

```asm
0x180056530  push    rbx
0x180056532  push    rbp
0x180056533  push    rsi
0x180056534  push    rdi
0x180056535  sub     rsp, 38h
0x180056539  mov     rsi, r8
0x18005653c  mov     ebx, ecx
0x18005653e  cmp     ecx, 4
0x180056541  jz      short loc_1800565B1
0x180056543  mov     rcx, cs:WPP_GLOBAL_Control
0x18005654a  lea     rbp, WPP_GLOBAL_Control
0x180056551  cmp     rcx, rbp
0x180056554  jz      short loc_180056566
0x180056556  test    byte ptr [rcx+1Ch], 8
0x18005655a  jz      short loc_180056566
0x18005655c  cmp     byte ptr [rcx+19h], 4
0x180056560  jnb     loc_180056625
0x180056566  xor     edi, edi
0x180056568  mov     eax, ebx
0x18005656a  sub     eax, 1
0x18005656d  jnz     short loc_1800565DB
0x18005656f  mov     rcx, cs:?g_serviceControl@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x180056576  lea     rdx, ServiceStatus; lpServiceStatus
0x18005657d  mov     cs:ServiceStatus.dwCurrentState, 3
0x180056587  call    cs:__imp_SetServiceStatus
0x18005658d  mov     rcx, cs:hEvent; hEvent
0x180056594  call    cs:__imp_SetEvent
0x18005659a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800565a1  cmp     rcx, rbp
0x1800565a4  jnz     short loc_1800565B5
0x1800565a6  mov     eax, edi
0x1800565a8  add     rsp, 38h
0x1800565ac  pop     rdi
0x1800565ad  pop     rsi
0x1800565ae  pop     rbp
0x1800565af  pop     rbx
0x1800565b0  retn
0x1800565b1  xor     eax, eax
0x1800565b3  jmp     short loc_1800565A8
0x1800565b5  test    byte ptr [rcx+1Ch], 8
0x1800565b9  jz      short loc_1800565A6
0x1800565bb  cmp     byte ptr [rcx+19h], 4
0x1800565bf  jb      short loc_1800565A6
0x1800565c1  mov     rcx, [rcx+10h]
0x1800565c5  lea     r8, WPP_c81622dadc0b34ee49a8cc9df4a5609a_Traceguids
0x1800565cc  mov     edx, 40h ; '@'
0x1800565d1  mov     r9d, ebx
0x1800565d4  call    WPP_SF_d
0x1800565d9  jmp     short loc_1800565A6
0x1800565db  sub     eax, 4
0x1800565de  jz      loc_180056668
0x1800565e4  sub     eax, 8
0x1800565e7  jz      short loc_18005665B
0x1800565e9  cmp     eax, 3
0x1800565ec  jnz     short loc_180056649
0x1800565ee  lea     rcx, stru_180111570; SRWLock
0x1800565f5  mov     [rsp+58h+var_38], rcx
0x1800565fa  call    cs:__imp_AcquireSRWLockShared
0x180056600  mov     rcx, cs:qword_180111560; hEvent
0x180056607  mov     [rsp+58h+var_30], 1
0x18005660c  lea     rax, [rcx+1]
0x180056610  cmp     rax, 1
0x180056614  ja      short loc_180056653
0x180056616  lea     rcx, [rsp+58h+var_38]
0x18005661b  call    ??1?$shared_lock@Vshared_mutex@utl@@@utl@@QEAA@XZ; utl::shared_lock<utl::shared_mutex>::~shared_lock<utl::shared_mutex>(void)
0x180056620  jmp     loc_18005659A
0x180056625  mov     rcx, [rcx+10h]
0x180056629  lea     r8, WPP_c81622dadc0b34ee49a8cc9df4a5609a_Traceguids
0x180056630  mov     edx, 3Fh ; '?'
0x180056635  mov     r9d, ebx
0x180056638  call    WPP_SF_d
0x18005663d  mov     rcx, cs:WPP_GLOBAL_Control
0x180056644  jmp     loc_180056566
0x180056649  mov     edi, 78h ; 'x'
0x18005664e  jmp     loc_1800565A1
0x180056653  call    cs:__imp_SetEvent
0x180056659  jmp     short loc_180056616
0x18005665b  mov     rcx, rsi; struct POWERBROADCAST_SETTING *
0x18005665e  call    ?OsEventsPowerEvent@@YA_NPEAUPOWERBROADCAST_SETTING@@@Z; OsEventsPowerEvent(POWERBROADCAST_SETTING *)
0x180056663  jmp     loc_18005659A
0x180056668  mov     cs:?g_systemShutdown@@3_NA, 1; bool g_systemShutdown
0x18005666f  jmp     loc_18005656F
```
