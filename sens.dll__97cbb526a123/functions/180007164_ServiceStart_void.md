# ServiceStart(void)

- ea: `0x180007164`
- end: `0x180007324`
- name: `?ServiceStart@@YAXXZ`
- size: `448`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180007840`

## callees

- `0x180007164`
- `0x180007ecc`
- `0x180008300`
- `0x1800093b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180007291`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180007291`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180007174`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180007174`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800071b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800071b3`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180007248`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180007248`

## pseudocode

```c
void ServiceStart(void)
{
  DWORD LastError; // eax
  _QWORD *v1; // rcx
  __int64 v2; // rdx
  __int64 v3; // rdx

  g_svchostShutdownEvent = CreateEventW(0, 0, 0, 0);
  if ( g_svchostShutdownEvent )
  {
    if ( !(unsigned int)SensInitialize() )
    {
      v1 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return;
      }
      v2 = 11;
      goto LABEL_30;
    }
    gServiceStatus.dwControlsAccepted = 65;
    gServiceStatus.dwCurrentState = 4;
    gServiceStatus.dwWin32ExitCode = 0;
    *(_QWORD *)&gServiceStatus.dwCheckPoint = 0;
    if ( !SetServiceStatus(ghStatusHandle, &gServiceStatus) )
    {
      v1 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return;
      }
      v2 = 12;
      goto LABEL_30;
    }
    if ( ghSensStartedEvent )
    {
      SetEvent(ghSensStartedEvent);
      v1 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
        goto LABEL_26;
      v3 = 13;
    }
    else
    {
      v1 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_26;
      v3 = 14;
    }
    WPP_SF_(v1[2], v3, WPP_0a2071a0e0b23ae9b876091e2aeecbba_Traceguids);
    v1 = WPP_GLOBAL_Control;
LABEL_26:
    if ( v1 == &WPP_GLOBAL_Control || (*((_BYTE *)v1 + 28) & 1) == 0 || *((_BYTE *)v1 + 25) < 4u )
      return;
    v2 = 15;
LABEL_30:
    WPP_SF_(v1[2], v2, WPP_0a2071a0e0b23ae9b876091e2aeecbba_Traceguids);
    return;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    LastError = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_0a2071a0e0b23ae9b876091e2aeecbba_Traceguids, LastError);
  }
}

```

## disassembly

```asm
0x180007164  push    rbx
0x180007166  sub     rsp, 20h
0x18000716a  xor     r9d, r9d; lpName
0x18000716d  xor     r8d, r8d; bInitialState
0x180007170  xor     edx, edx; bManualReset
0x180007172  xor     ecx, ecx; lpEventAttributes
0x180007174  call    cs:__imp_CreateEventW
0x18000717a  xor     ebx, ebx
0x18000717c  mov     cs:?g_svchostShutdownEvent@@3PEAXEA, rax; void * g_svchostShutdownEvent
0x180007183  test    rax, rax
0x180007186  jnz     short loc_1800071DD
0x180007188  mov     rax, cs:WPP_GLOBAL_Control
0x18000718f  lea     rbx, WPP_GLOBAL_Control
0x180007196  cmp     rax, rbx
0x180007199  jz      loc_18000731E
0x18000719f  test    byte ptr [rax+1Ch], 1
0x1800071a3  jz      loc_18000731E
0x1800071a9  cmp     byte ptr [rax+19h], 2
0x1800071ad  jb      loc_18000731E
0x1800071b3  call    cs:__imp_GetLastError
0x1800071b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800071c0  lea     r8, WPP_0a2071a0e0b23ae9b876091e2aeecbba_Traceguids
0x1800071c7  mov     edx, 0Ah
0x1800071cc  mov     r9d, eax
0x1800071cf  mov     rcx, [rcx+10h]
0x1800071d3  add     rsp, 20h
0x1800071d7  pop     rbx
0x1800071d8  jmp     WPP_SF_d
0x1800071dd  call    ?SensInitialize@@YAHXZ; SensInitialize(void)
0x1800071e2  test    eax, eax
0x1800071e4  jnz     short loc_180007219
0x1800071e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800071ed  lea     rbx, WPP_GLOBAL_Control
0x1800071f4  cmp     rcx, rbx
0x1800071f7  jz      loc_18000731E
0x1800071fd  test    byte ptr [rcx+1Ch], 1
0x180007201  jz      loc_18000731E
0x180007207  cmp     byte ptr [rcx+19h], 2
0x18000720b  jb      loc_18000731E
0x180007211  lea     edx, [rax+0Bh]
0x180007214  jmp     loc_18000730E
0x180007219  mov     rcx, cs:?ghStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x180007220  lea     rdx, ?gServiceStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x180007227  mov     cs:?gServiceStatus@@3U_SERVICE_STATUS@@A.dwControlsAccepted, 41h ; 'A'; _SERVICE_STATUS gServiceStatus ...
0x180007231  mov     cs:?gServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 4; _SERVICE_STATUS gServiceStatus ...
0x18000723b  mov     cs:?gServiceStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, ebx; _SERVICE_STATUS gServiceStatus ...
0x180007241  mov     qword ptr cs:?gServiceStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, rbx; _SERVICE_STATUS gServiceStatus ...
0x180007248  call    cs:__imp_SetServiceStatus
0x18000724e  test    eax, eax
0x180007250  jnz     short loc_180007285
0x180007252  mov     rcx, cs:WPP_GLOBAL_Control
0x180007259  lea     rbx, WPP_GLOBAL_Control
0x180007260  cmp     rcx, rbx
0x180007263  jz      loc_18000731E
0x180007269  test    byte ptr [rcx+1Ch], 1
0x18000726d  jz      loc_18000731E
0x180007273  cmp     byte ptr [rcx+19h], 2
0x180007277  jb      loc_18000731E
0x18000727d  lea     edx, [rax+0Ch]
0x180007280  jmp     loc_18000730E
0x180007285  mov     rcx, cs:?ghSensStartedEvent@@3PEAXEA; hEvent
0x18000728c  test    rcx, rcx
0x18000728f  jz      short loc_1800072BD
0x180007291  call    cs:__imp_SetEvent
0x180007297  mov     rcx, cs:WPP_GLOBAL_Control
0x18000729e  lea     rbx, WPP_GLOBAL_Control
0x1800072a5  cmp     rcx, rbx
0x1800072a8  jz      short loc_18000731E
0x1800072aa  test    byte ptr [rcx+1Ch], 1
0x1800072ae  jz      short loc_1800072F8
0x1800072b0  cmp     byte ptr [rcx+19h], 5
0x1800072b4  jb      short loc_1800072F8
0x1800072b6  mov     edx, 0Dh
0x1800072bb  jmp     short loc_1800072E1
0x1800072bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800072c4  lea     rbx, WPP_GLOBAL_Control
0x1800072cb  cmp     rcx, rbx
0x1800072ce  jz      short loc_18000731E
0x1800072d0  test    byte ptr [rcx+1Ch], 1
0x1800072d4  jz      short loc_1800072F8
0x1800072d6  cmp     byte ptr [rcx+19h], 2
0x1800072da  jb      short loc_1800072F8
0x1800072dc  mov     edx, 0Eh
0x1800072e1  mov     rcx, [rcx+10h]
0x1800072e5  lea     r8, WPP_0a2071a0e0b23ae9b876091e2aeecbba_Traceguids
0x1800072ec  call    WPP_SF_
0x1800072f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800072f8  cmp     rcx, rbx
0x1800072fb  jz      short loc_18000731E
0x1800072fd  test    byte ptr [rcx+1Ch], 1
0x180007301  jz      short loc_18000731E
0x180007303  cmp     byte ptr [rcx+19h], 4
0x180007307  jb      short loc_18000731E
0x180007309  mov     edx, 0Fh
0x18000730e  mov     rcx, [rcx+10h]
0x180007312  lea     r8, WPP_0a2071a0e0b23ae9b876091e2aeecbba_Traceguids
0x180007319  call    WPP_SF_
0x18000731e  add     rsp, 20h
0x180007322  pop     rbx
0x180007323  retn
```
