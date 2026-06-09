# WbioInitiateServiceShutdown

- ea: `0x18003e984`
- end: `0x18003e9f9`
- name: `WbioInitiateServiceShutdown`
- size: `117`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180046480`

## callees

- `0x18003e984`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003e9ee`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003e9ee`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18003e9e1`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18003e9e1`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003e9af`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003e9af`

## pseudocode

```c
signed __int32 WbioInitiateServiceShutdown()
{
  signed __int32 result; // eax

  _m_prefetchw((const void *)&g_ControlFlags);
  result = _InterlockedOr(&g_ControlFlags, 1u);
  if ( (result & 1) == 0 )
  {
    while ( (g_ControlFlags & 2) != 0 )
      Sleep(0x64u);
    *(_QWORD *)&g_ServiceContext.dwCurrentState = 3;
    *(_QWORD *)&g_ServiceContext.dwCheckPoint = 0;
    SetServiceStatus(hServiceStatus, &g_ServiceContext);
    return SetEvent(hObject);
  }
  return result;
}

```

## disassembly

```asm
0x18003e984  sub     rsp, 28h
0x18003e988  prefetchw byte ptr cs:?g_ControlFlags@@3JC; long volatile g_ControlFlags
0x18003e98f  mov     eax, cs:?g_ControlFlags@@3JC; long volatile g_ControlFlags
0x18003e995  mov     ecx, eax
0x18003e997  or      ecx, 1
0x18003e99a  lock cmpxchg cs:?g_ControlFlags@@3JC, ecx; long volatile g_ControlFlags
0x18003e9a2  jnz     short loc_18003E995
0x18003e9a4  test    al, 1
0x18003e9a6  jnz     short loc_18003E9F4
0x18003e9a8  jmp     short loc_18003E9B5
0x18003e9aa  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18003e9af  call    cs:__imp_Sleep
0x18003e9b5  mov     eax, cs:?g_ControlFlags@@3JC; long volatile g_ControlFlags
0x18003e9bb  test    al, 2
0x18003e9bd  jnz     short loc_18003E9AA
0x18003e9bf  mov     rcx, qword ptr cs:hServiceStatus; hServiceStatus
0x18003e9c6  lea     rdx, ?g_ServiceContext@@3U_unnamed_type_g_ServiceContext_@@A; lpServiceStatus
0x18003e9cd  xor     eax, eax
0x18003e9cf  mov     qword ptr cs:?g_ServiceContext@@3U_unnamed_type_g_ServiceContext_@@A.dwCurrentState, 3; _unnamed_type_g_ServiceContext_ g_ServiceContext ...
0x18003e9da  mov     qword ptr cs:?g_ServiceContext@@3U_unnamed_type_g_ServiceContext_@@A.dwCheckPoint, rax; _unnamed_type_g_ServiceContext_ g_ServiceContext ...
0x18003e9e1  call    cs:__imp_SetServiceStatus
0x18003e9e7  mov     rcx, cs:hObject; hEvent
0x18003e9ee  call    cs:__imp_SetEvent
0x18003e9f4  add     rsp, 28h
0x18003e9f8  retn
```
