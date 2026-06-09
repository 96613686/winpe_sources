# EntitlementMgr::Initialize(void)

- ea: `0x18000f498`
- end: `0x18000f5bc`
- name: `?Initialize@EntitlementMgr@@QEAAJXZ`
- size: `292`
- prototype: `__int64 __fastcall(EntitlementMgr *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18001935c`

## callees

- `0x18000bf74`
- `0x18000f498`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000f510`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000f55e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000f510`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000f55e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f4b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f51f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f56d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f4b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f51f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f56d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x18000f4a5`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x18000f4a5`

## pseudocode

```c
__int64 __fastcall EntitlementMgr::Initialize(EntitlementMgr *this)
{
  HANDLE TimerQueue; // rax
  signed int v3; // eax
  unsigned int v4; // ebx
  TetheringServiceTelemetry *v5; // rcx
  __int64 v6; // rdx
  HANDLE EventW; // rax
  signed int v8; // eax
  HANDLE v9; // rax
  signed int LastError; // eax

  TimerQueue = CreateTimerQueue();
  *(_QWORD *)this = TimerQueue;
  if ( TimerQueue )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)this + 2) = EventW;
    if ( EventW )
    {
      v9 = CreateEventW(0, 0, 0, 0);
      *((_QWORD *)this + 3) = v9;
      if ( v9 )
      {
        v4 = 0;
        *((_BYTE *)this + 94) = 1;
        *((_QWORD *)this + 1) = 0;
        return v4;
      }
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v6 = 12;
        goto LABEL_7;
      }
    }
    else
    {
      v8 = GetLastError();
      v4 = v8;
      if ( v8 > 0 )
        v4 = (unsigned __int16)v8 | 0x80070000;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v6 = 11;
        goto LABEL_7;
      }
    }
  }
  else
  {
    v3 = GetLastError();
    v4 = v3;
    if ( v3 > 0 )
      v4 = (unsigned __int16)v3 | 0x80070000;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v6 = 10;
LABEL_7:
      WPP_SF_d(*((_QWORD *)v5 + 2), v6, &WPP_c5412e6d3d8031ad90ef7472f24b0e8b_Traceguids, v4);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18000f498  mov     [rsp+arg_0], rbx
0x18000f49d  push    rdi
0x18000f49e  sub     rsp, 20h
0x18000f4a2  mov     rdi, rcx
0x18000f4a5  call    cs:__imp_CreateTimerQueue
0x18000f4ab  mov     [rdi], rax
0x18000f4ae  test    rax, rax
0x18000f4b1  jnz     short loc_18000F506
0x18000f4b3  call    cs:__imp_GetLastError
0x18000f4b9  mov     ebx, eax
0x18000f4bb  test    eax, eax
0x18000f4bd  jle     short loc_18000F4C8
0x18000f4bf  movzx   ebx, ax
0x18000f4c2  or      ebx, 80070000h
0x18000f4c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f4cf  lea     rax, WPP_GLOBAL_Control
0x18000f4d6  cmp     rcx, rax
0x18000f4d9  jz      loc_18000F5AF
0x18000f4df  test    byte ptr [rcx+1Ch], 1
0x18000f4e3  jz      loc_18000F5AF
0x18000f4e9  mov     edx, 0Ah
0x18000f4ee  mov     rcx, [rcx+10h]
0x18000f4f2  lea     r8, WPP_c5412e6d3d8031ad90ef7472f24b0e8b_Traceguids
0x18000f4f9  mov     r9d, ebx
0x18000f4fc  call    WPP_SF_d
0x18000f501  jmp     loc_18000F5AF
0x18000f506  xor     r9d, r9d; lpName
0x18000f509  xor     r8d, r8d; bInitialState
0x18000f50c  xor     edx, edx; bManualReset
0x18000f50e  xor     ecx, ecx; lpEventAttributes
0x18000f510  call    cs:__imp_CreateEventW
0x18000f516  mov     [rdi+10h], rax
0x18000f51a  test    rax, rax
0x18000f51d  jnz     short loc_18000F554
0x18000f51f  call    cs:__imp_GetLastError
0x18000f525  mov     ebx, eax
0x18000f527  test    eax, eax
0x18000f529  jle     short loc_18000F534
0x18000f52b  movzx   ebx, ax
0x18000f52e  or      ebx, 80070000h
0x18000f534  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f53b  lea     rax, WPP_GLOBAL_Control
0x18000f542  cmp     rcx, rax
0x18000f545  jz      short loc_18000F5AF
0x18000f547  test    byte ptr [rcx+1Ch], 1
0x18000f54b  jz      short loc_18000F5AF
0x18000f54d  mov     edx, 0Bh
0x18000f552  jmp     short loc_18000F4EE
0x18000f554  xor     r9d, r9d; lpName
0x18000f557  xor     r8d, r8d; bInitialState
0x18000f55a  xor     edx, edx; bManualReset
0x18000f55c  xor     ecx, ecx; lpEventAttributes
0x18000f55e  call    cs:__imp_CreateEventW
0x18000f564  mov     [rdi+18h], rax
0x18000f568  test    rax, rax
0x18000f56b  jnz     short loc_18000F5A5
0x18000f56d  call    cs:__imp_GetLastError
0x18000f573  mov     ebx, eax
0x18000f575  test    eax, eax
0x18000f577  jle     short loc_18000F582
0x18000f579  movzx   ebx, ax
0x18000f57c  or      ebx, 80070000h
0x18000f582  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f589  lea     rax, WPP_GLOBAL_Control
0x18000f590  cmp     rcx, rax
0x18000f593  jz      short loc_18000F5AF
0x18000f595  test    byte ptr [rcx+1Ch], 1
0x18000f599  jz      short loc_18000F5AF
0x18000f59b  mov     edx, 0Ch
0x18000f5a0  jmp     loc_18000F4EE
0x18000f5a5  xor     ebx, ebx
0x18000f5a7  mov     byte ptr [rdi+5Eh], 1
0x18000f5ab  mov     [rdi+8], rbx
0x18000f5af  mov     eax, ebx
0x18000f5b1  mov     rbx, [rsp+28h+arg_0]
0x18000f5b6  add     rsp, 20h
0x18000f5ba  pop     rdi
0x18000f5bb  retn
```
