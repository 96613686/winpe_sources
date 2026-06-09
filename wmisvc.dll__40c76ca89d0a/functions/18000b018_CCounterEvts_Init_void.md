# CCounterEvts::Init(void)

- ea: `0x18000b018`
- end: `0x18000b13d`
- name: `?Init@CCounterEvts@@QEAAKXZ`
- size: `293`
- prototype: `DWORD __fastcall(CCounterEvts *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000b2b4`

## callees

- `0x18000b018`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000b060`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000b083`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000b0a6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000b0c5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000b0ef`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000b111`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000b060`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000b083`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000b0a6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000b0c5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000b0ef`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000b111`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b12c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b12c`

## string_xrefs

- `0x18000b0de`: `Global\WMI_ProcessIdleTasksStart`
- `0x18000b103`: `Global\WMI_ProcessIdleTasksComplete`

## pseudocode

```c
DWORD __fastcall CCounterEvts::Init(CCounterEvts *this)
{
  HANDLE v3; // rax
  HANDLE v4; // rax
  HANDLE v5; // rax
  HANDLE v6; // rax
  HANDLE v7; // rax
  HANDLE v8; // rax
  _SECURITY_ATTRIBUTES EventAttributes; // [rsp+20h] [rbp-20h] BYREF

  if ( !*((_DWORD *)this + 12) )
    return 0;
  *(_QWORD *)&EventAttributes.nLength = 24;
  EventAttributes.lpSecurityDescriptor = &g_LocalSystemAdminsSD;
  *(_QWORD *)&EventAttributes.bInheritHandle = 0;
  v3 = CreateEventW(&EventAttributes, 0, 0, L"Global\\WMI_SysEvent_LodCtr");
  *((_QWORD *)this + 2) = v3;
  if ( v3 )
  {
    v4 = CreateEventW(&EventAttributes, 0, 0, L"Global\\WMI_SysEvent_UnLodCtr");
    *((_QWORD *)this + 3) = v4;
    if ( v4 )
    {
      v5 = CreateEventW(&EventAttributes, 0, 0, L"Global\\WMI_RevAdap_Set");
      *((_QWORD *)this + 7) = v5;
      if ( v5 )
      {
        v6 = CreateEventW(&EventAttributes, 0, 0, L"Global\\WMI_RevAdap_ACK");
        *((_QWORD *)this + 8) = v6;
        if ( v6 )
        {
          EventAttributes.lpSecurityDescriptor = &g_LocalSystemSD;
          v7 = CreateEventW(&EventAttributes, 0, 0, L"Global\\WMI_ProcessIdleTasksStart");
          *((_QWORD *)this + 10) = v7;
          if ( v7 )
          {
            v8 = CreateEventW(&EventAttributes, 1, 1, L"Global\\WMI_ProcessIdleTasksComplete");
            *((_QWORD *)this + 11) = v8;
            if ( v8 )
            {
              *((_DWORD *)this + 12) = 0;
              return 0;
            }
          }
        }
      }
    }
  }
  return GetLastError();
}

```

## disassembly

```asm
0x18000b018  mov     [rsp-8+arg_0], rbx
0x18000b01d  push    rbp
0x18000b01e  mov     rbp, rsp
0x18000b021  sub     rsp, 40h
0x18000b025  cmp     dword ptr [rcx+30h], 0
0x18000b029  mov     rbx, rcx
0x18000b02c  jnz     short loc_18000B035
0x18000b02e  xor     eax, eax
0x18000b030  jmp     loc_18000B132
0x18000b035  lea     rax, ?g_LocalSystemAdminsSD@@3PAKA; ulong near * g_LocalSystemAdminsSD
0x18000b03c  mov     qword ptr [rbp+EventAttributes.nLength], 18h
0x18000b044  lea     r9, aGlobalWmiSysev_0; "Global\\WMI_SysEvent_LodCtr"
0x18000b04b  mov     [rbp+EventAttributes.lpSecurityDescriptor], rax
0x18000b04f  xor     r8d, r8d; bInitialState
0x18000b052  mov     qword ptr [rbp+EventAttributes.bInheritHandle], 0
0x18000b05a  xor     edx, edx; bManualReset
0x18000b05c  lea     rcx, [rbp+EventAttributes]; lpEventAttributes
0x18000b060  call    cs:__imp_CreateEventW
0x18000b066  mov     [rbx+10h], rax
0x18000b06a  test    rax, rax
0x18000b06d  jz      loc_18000B12C
0x18000b073  lea     r9, aGlobalWmiSysev; "Global\\WMI_SysEvent_UnLodCtr"
0x18000b07a  xor     r8d, r8d; bInitialState
0x18000b07d  xor     edx, edx; bManualReset
0x18000b07f  lea     rcx, [rbp+EventAttributes]; lpEventAttributes
0x18000b083  call    cs:__imp_CreateEventW
0x18000b089  mov     [rbx+18h], rax
0x18000b08d  test    rax, rax
0x18000b090  jz      loc_18000B12C
0x18000b096  lea     r9, aGlobalWmiRevad_0; "Global\\WMI_RevAdap_Set"
0x18000b09d  xor     r8d, r8d; bInitialState
0x18000b0a0  xor     edx, edx; bManualReset
0x18000b0a2  lea     rcx, [rbp+EventAttributes]; lpEventAttributes
0x18000b0a6  call    cs:__imp_CreateEventW
0x18000b0ac  mov     [rbx+38h], rax
0x18000b0b0  test    rax, rax
0x18000b0b3  jz      short loc_18000B12C
0x18000b0b5  lea     r9, aGlobalWmiRevad; "Global\\WMI_RevAdap_ACK"
0x18000b0bc  xor     r8d, r8d; bInitialState
0x18000b0bf  xor     edx, edx; bManualReset
0x18000b0c1  lea     rcx, [rbp+EventAttributes]; lpEventAttributes
0x18000b0c5  call    cs:__imp_CreateEventW
0x18000b0cb  mov     [rbx+40h], rax
0x18000b0cf  test    rax, rax
0x18000b0d2  jz      short loc_18000B12C
0x18000b0d4  lea     rax, ?g_LocalSystemSD@@3PAKA; ulong near * g_LocalSystemSD
0x18000b0db  xor     r8d, r8d; bInitialState
0x18000b0de  lea     r9, aGlobalWmiProce; "Global\\WMI_ProcessIdleTasksStart"
0x18000b0e5  mov     [rbp+EventAttributes.lpSecurityDescriptor], rax
0x18000b0e9  xor     edx, edx; bManualReset
0x18000b0eb  lea     rcx, [rbp+EventAttributes]; lpEventAttributes
0x18000b0ef  call    cs:__imp_CreateEventW
0x18000b0f5  mov     [rbx+50h], rax
0x18000b0f9  test    rax, rax
0x18000b0fc  jz      short loc_18000B12C
0x18000b0fe  mov     edx, 1; bManualReset
0x18000b103  lea     r9, aGlobalWmiProce_0; "Global\\WMI_ProcessIdleTasksComplete"
0x18000b10a  mov     r8d, edx; bInitialState
0x18000b10d  lea     rcx, [rbp+EventAttributes]; lpEventAttributes
0x18000b111  call    cs:__imp_CreateEventW
0x18000b117  mov     [rbx+58h], rax
0x18000b11b  test    rax, rax
0x18000b11e  jz      short loc_18000B12C
0x18000b120  mov     dword ptr [rbx+30h], 0
0x18000b127  jmp     loc_18000B02E
0x18000b12c  call    cs:__imp_GetLastError
0x18000b132  mov     rbx, [rsp+40h+arg_0]
0x18000b137  add     rsp, 40h
0x18000b13b  pop     rbp
0x18000b13c  retn
```
