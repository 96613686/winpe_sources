# Idolater::Init(void)

- ea: `0x1800693b4`
- end: `0x18006947c`
- name: `?Init@Idolater@@QEAAJXZ`
- size: `200`
- prototype: `__int64 __fastcall(Idolater *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x1800519e0`

## callees

- `0x180024730`
- `0x1800693b4`
- `0x180069484`
- `0x180069688`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800693ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800693ed`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180069459`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180069459`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800693c6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800693c6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180069436`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180069436`
- `ntdll!EtwEventRegister` at `0x18006941d`
- `ntdll!EtwEventRegister` at `0x18006941d`

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
  wmi::AutoHandle::~AutoHandle((wmi::AutoHandle *)(&WaitHandle + 1));
  *(&WaitHandle + 1) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    v3 = LastError;
    v4 = LastError <= 0;
    goto LABEL_3;
  }
  LastError = EtwEventRegister(IDLE_TRIGGER_PROVIDER_GUID, 0, 0, &qword_1800C16C0);
  v3 = LastError;
  v4 = LastError <= 0;
  if ( LastError )
  {
LABEL_3:
    if ( !v4 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_8;
  }
  InitializeCriticalSection(&stru_1800C1690);
  v3 = Idolater::RegisterWithIdleService(v5);
  if ( v3 < 0 )
  {
    Idolater::UnRegisterWithIdleService(v7, v6);
    DeleteCriticalSection(&stru_1800C1690);
  }
LABEL_8:
  result = (unsigned int)v3;
  byte_1800C16B8 = v3 >= 0;
  return result;
}

```

## disassembly

```asm
0x1800693b4  push    rbx
0x1800693b6  sub     rsp, 20h
0x1800693ba  xor     r9d, r9d; lpName
0x1800693bd  xor     r8d, r8d; bInitialState
0x1800693c0  xor     ecx, ecx; lpEventAttributes
0x1800693c2  lea     edx, [r9+1]; bManualReset
0x1800693c6  call    cs:__imp_CreateEventW
0x1800693cd  nop     dword ptr [rax+rax+00h]
0x1800693d2  lea     rcx, WaitHandle+8; this
0x1800693d9  mov     rbx, rax
0x1800693dc  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x1800693e1  mov     qword ptr cs:WaitHandle+8, rbx
0x1800693e8  test    rbx, rbx
0x1800693eb  jnz     short loc_18006940A
0x1800693ed  call    cs:__imp_GetLastError
0x1800693f4  nop     dword ptr [rax+rax+00h]
0x1800693f9  mov     ebx, eax
0x1800693fb  test    eax, eax
0x1800693fd  jle     short loc_180069465
0x1800693ff  movzx   ebx, ax
0x180069402  or      ebx, 80070000h
0x180069408  jmp     short loc_180069465
0x18006940a  lea     r9, qword_1800C16C0
0x180069411  xor     r8d, r8d
0x180069414  xor     edx, edx
0x180069416  lea     rcx, IDLE_TRIGGER_PROVIDER_GUID
0x18006941d  call    cs:__imp_EtwEventRegister
0x180069424  nop     dword ptr [rax+rax+00h]
0x180069429  mov     ebx, eax
0x18006942b  test    eax, eax
0x18006942d  jnz     short loc_1800693FD
0x18006942f  lea     rcx, stru_1800C1690; lpCriticalSection
0x180069436  call    cs:__imp_InitializeCriticalSection
0x18006943d  nop     dword ptr [rax+rax+00h]
0x180069442  call    ?RegisterWithIdleService@Idolater@@AEAAJXZ; Idolater::RegisterWithIdleService(void)
0x180069447  mov     ebx, eax
0x180069449  test    eax, eax
0x18006944b  jns     short loc_180069465
0x18006944d  call    ?UnRegisterWithIdleService@Idolater@@AEAAJ_N@Z; Idolater::UnRegisterWithIdleService(bool)
0x180069452  lea     rcx, stru_1800C1690; lpCriticalSection
0x180069459  call    cs:__imp_DeleteCriticalSection
0x180069460  nop     dword ptr [rax+rax+00h]
0x180069465  mov     ecx, ebx
0x180069467  mov     eax, ebx
0x180069469  shr     ecx, 1Fh
0x18006946c  xor     cl, 1
0x18006946f  mov     cs:byte_1800C16B8, cl
0x180069475  add     rsp, 20h
0x180069479  pop     rbx
0x18006947a  retn
```
