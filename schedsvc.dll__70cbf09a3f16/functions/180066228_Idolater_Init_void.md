# Idolater::Init(void)

- ea: `0x180066228`
- end: `0x1800662d1`
- name: `?Init@Idolater@@QEAAJXZ`
- size: `169`
- prototype: `__int64 __fastcall(Idolater *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x18004f190`

## callees

- `0x180039d00`
- `0x180066228`
- `0x1800662d8`
- `0x1800664a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006625b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006625b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800662b5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800662b5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006623a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006623a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180066298`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180066298`
- `ntdll!EtwEventRegister` at `0x180066285`
- `ntdll!EtwEventRegister` at `0x180066285`

## pseudocode

```c
__int64 __fastcall Idolater::Init(Idolater *this)
{
  HANDLE EventW; // rbx
  signed int LastError; // eax
  signed int v3; // ebx
  bool v4; // cc
  Idolater *v5; // rcx
  bool v6; // dl
  Idolater *v7; // rcx
  __int64 result; // rax

  EventW = CreateEventW(0, 1, 0, 0);
  wmi::AutoHandle::~AutoHandle(&WaitHandle + 1);
  *(&WaitHandle + 1) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    v3 = LastError;
    v4 = LastError <= 0;
    goto LABEL_3;
  }
  LastError = EtwEventRegister(IDLE_TRIGGER_PROVIDER_GUID, 0, 0, &qword_1800BD5C0);
  v3 = LastError;
  v4 = LastError <= 0;
  if ( LastError )
  {
LABEL_3:
    if ( !v4 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_8;
  }
  InitializeCriticalSection(&stru_1800BD590);
  v3 = Idolater::RegisterWithIdleService(v5);
  if ( v3 < 0 )
  {
    Idolater::UnRegisterWithIdleService(v7, v6);
    DeleteCriticalSection(&stru_1800BD590);
  }
LABEL_8:
  result = (unsigned int)v3;
  byte_1800BD5B8 = v3 >= 0;
  return result;
}

```

## disassembly

```asm
0x180066228  push    rbx
0x18006622a  sub     rsp, 20h
0x18006622e  xor     r9d, r9d; lpName
0x180066231  xor     r8d, r8d; bInitialState
0x180066234  xor     ecx, ecx; lpEventAttributes
0x180066236  lea     edx, [r9+1]; bManualReset
0x18006623a  call    cs:__imp_CreateEventW
0x180066240  lea     rcx, WaitHandle+8; this
0x180066247  mov     rbx, rax
0x18006624a  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x18006624f  mov     qword ptr cs:WaitHandle+8, rbx
0x180066256  test    rbx, rbx
0x180066259  jnz     short loc_180066272
0x18006625b  call    cs:__imp_GetLastError
0x180066261  mov     ebx, eax
0x180066263  test    eax, eax
0x180066265  jle     short loc_1800662BB
0x180066267  movzx   ebx, ax
0x18006626a  or      ebx, 80070000h
0x180066270  jmp     short loc_1800662BB
0x180066272  lea     r9, qword_1800BD5C0
0x180066279  xor     r8d, r8d
0x18006627c  xor     edx, edx
0x18006627e  lea     rcx, IDLE_TRIGGER_PROVIDER_GUID
0x180066285  call    cs:__imp_EtwEventRegister
0x18006628b  mov     ebx, eax
0x18006628d  test    eax, eax
0x18006628f  jnz     short loc_180066265
0x180066291  lea     rcx, stru_1800BD590; lpCriticalSection
0x180066298  call    cs:__imp_InitializeCriticalSection
0x18006629e  call    ?RegisterWithIdleService@Idolater@@AEAAJXZ; Idolater::RegisterWithIdleService(void)
0x1800662a3  mov     ebx, eax
0x1800662a5  test    eax, eax
0x1800662a7  jns     short loc_1800662BB
0x1800662a9  call    ?UnRegisterWithIdleService@Idolater@@AEAAJ_N@Z; Idolater::UnRegisterWithIdleService(bool)
0x1800662ae  lea     rcx, stru_1800BD590; lpCriticalSection
0x1800662b5  call    cs:__imp_DeleteCriticalSection
0x1800662bb  mov     ecx, ebx
0x1800662bd  mov     eax, ebx
0x1800662bf  shr     ecx, 1Fh
0x1800662c2  xor     cl, 1
0x1800662c5  mov     cs:byte_1800BD5B8, cl
0x1800662cb  add     rsp, 20h
0x1800662cf  pop     rbx
0x1800662d0  retn
```
