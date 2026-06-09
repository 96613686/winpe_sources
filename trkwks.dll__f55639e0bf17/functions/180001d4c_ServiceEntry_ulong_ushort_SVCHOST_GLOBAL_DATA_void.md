# ServiceEntry(ulong,ushort * *,_SVCHOST_GLOBAL_DATA *,void *)

- ea: `0x180001d4c`
- end: `0x180001e20`
- name: `?ServiceEntry@@YAXKPEAPEAGPEAU_SVCHOST_GLOBAL_DATA@@PEAX@Z`
- size: `212`
- prototype: `void __fastcall(__int64, unsigned __int16 **, struct _SVCHOST_GLOBAL_DATA *, void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000f040`

## callees

- `0x180001d4c`
- `0x180001e28`
- `0x180003684`
- `0x18000a5b0`
- `0x18000d020`
- `0x18000d038`
- `0x18000d268`
- `0x18000dae8`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180001d65`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180001d65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001dfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001dfe`

## pseudocode

```c
void __fastcall ServiceEntry(__int64 a1, unsigned __int16 **a2, struct _SVCHOST_GLOBAL_DATA *a3, void *a4)
{
  int *v4; // rcx
  DWORD LastError; // eax
  CTrkWksSvc *v6; // rax
  struct _SVCHOST_GLOBAL_DATA *v7; // rdx
  CTrkWksSvc *v8; // rbx
  DWORD v9; // eax

  g_stopServiceEvent = CreateEventW(0, 0, 0, 0);
  if ( !g_stopServiceEvent )
  {
    LastError = GetLastError();
    TrkRaiseWin32Error(LastError);
  }
  CommonDllInit(v4);
  v6 = (CTrkWksSvc *)operator new(0x990u);
  if ( v6 )
    v8 = CTrkWksSvc::CTrkWksSvc(v6);
  else
    v8 = 0;
  if ( !v8 )
    TrkRaiseLastError();
  CTrkWksSvc::Initialize(v8, v7);
  if ( (*((unsigned int (__fastcall **)(HANDLE *, const WCHAR *, HANDLE, void (__fastcall *)(void *, unsigned __int8), CTrkWksSvc *, _DWORD))g_svcHostGlobalData
        + 24))(
         &g_waitObject,
         L"TrkWks",
         g_stopServiceEvent,
         ServiceStopCallback,
         v8,
         0) )
  {
    v9 = GetLastError();
    TrkRaiseWin32Error(v9);
  }
}

```

## disassembly

```asm
0x180001d4c  push    rbx
0x180001d4e  sub     rsp, 50h
0x180001d52  mov     [rsp+58h+var_18], 0
0x180001d5b  xor     r9d, r9d; lpName
0x180001d5e  xor     r8d, r8d; bInitialState
0x180001d61  xor     edx, edx; bManualReset
0x180001d63  xor     ecx, ecx; lpEventAttributes
0x180001d65  call    cs:__imp_CreateEventW
0x180001d6b  mov     cs:?g_stopServiceEvent@@3PEAXEA, rax; void * g_stopServiceEvent
0x180001d72  test    rax, rax
0x180001d75  jnz     short loc_180001D84
0x180001d77  call    cs:__imp_GetLastError
0x180001d7d  mov     ecx, eax; int
0x180001d7f  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
0x180001d84  call    ?CommonDllInit@@YAXPEAJ@Z; CommonDllInit(long *)
0x180001d89  mov     ecx, 990h; Size
0x180001d8e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001d93  test    rax, rax
0x180001d96  jz      short loc_180001DA5
0x180001d98  mov     rcx, rax; this
0x180001d9b  call    ??0CTrkWksSvc@@QEAA@XZ; CTrkWksSvc::CTrkWksSvc(void)
0x180001da0  mov     rbx, rax
0x180001da3  jmp     short loc_180001DA7
0x180001da5  xor     ebx, ebx
0x180001da7  mov     [rsp+58h+var_18], rbx
0x180001dac  test    rbx, rbx
0x180001daf  jnz     short loc_180001DB6
0x180001db1  call    ?TrkRaiseLastError@@YAXXZ; TrkRaiseLastError(void)
0x180001db6  mov     rcx, rbx; this
0x180001db9  call    ?Initialize@CTrkWksSvc@@QEAAXPEAU_SVCHOST_GLOBAL_DATA@@@Z; CTrkWksSvc::Initialize(_SVCHOST_GLOBAL_DATA *)
0x180001dbe  mov     rax, cs:?g_svcHostGlobalData@@3PEAU_SVCHOST_GLOBAL_DATA@@EA; _SVCHOST_GLOBAL_DATA * g_svcHostGlobalData
0x180001dc5  mov     [rsp+58h+var_30], 0
0x180001dcd  mov     [rsp+58h+var_38], rbx
0x180001dd2  lea     r9, ?ServiceStopCallback@@YAXPEAXE@Z; ServiceStopCallback(void *,uchar)
0x180001dd9  mov     r8, cs:?g_stopServiceEvent@@3PEAXEA; void * g_stopServiceEvent
0x180001de0  lea     rdx, ServiceName; "TrkWks"
0x180001de7  lea     rcx, ?g_waitObject@@3PEAXEA; void * g_waitObject
0x180001dee  mov     rax, [rax+0C0h]
0x180001df5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001dfa  test    eax, eax
0x180001dfc  jz      short loc_180001E0B
0x180001dfe  call    cs:__imp_GetLastError
0x180001e04  mov     ecx, eax; int
0x180001e06  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
0x180001e0b  jmp     short loc_180001E1A
0x180001e0d  xor     edx, edx; unsigned __int8
0x180001e0f  mov     rcx, [rsp+58h+var_18]; void *
0x180001e14  call    ?ServiceStopCallback@@YAXPEAXE@Z; ServiceStopCallback(void *,uchar)
0x180001e19  nop
0x180001e1a  add     rsp, 50h
0x180001e1e  pop     rbx
0x180001e1f  retn
0x18001116b  push    rbp
0x18001116d  sub     rsp, 40h
0x180011171  mov     rbp, rdx
0x180011174  mov     eax, 1
0x180011179  add     rsp, 40h
0x18001117d  pop     rbp
0x18001117e  retn
```
