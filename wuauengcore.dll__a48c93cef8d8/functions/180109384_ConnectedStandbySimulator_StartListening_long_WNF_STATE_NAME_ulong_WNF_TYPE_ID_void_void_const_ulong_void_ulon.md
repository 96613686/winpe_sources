# ConnectedStandbySimulator::StartListening(long (*)(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong),void *,ulong (*)(void *,ulong,void *),void *)

- ea: `0x180109384`
- end: `0x18010952c`
- name: `?StartListening@ConnectedStandbySimulator@@QEAAJP6AJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z2P6AK2K2@Z2@Z`
- size: `424`
- prototype: `__int64 __usercall@<rax>(ConnectedStandbySimulator *__hidden this@<rcx>, int (*)(struct _WNF_STATE_NAME, unsigned int, struct _WNF_TYPE_ID *, void *, const void *, unsigned int)@<rdx>, void *@<r8>, unsigned int (*)(void *, unsigned int, void *)@<r9>, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180107cd4`

## callees

- `0x180109290`
- `0x1801092d8`
- `0x180109384`
- `0x180109534`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801093bc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180109427`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180109491`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801093bc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180109427`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180109491`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801093db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180109446`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801094ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801093db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180109446`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801094ea`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1801094c9`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1801094c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801093cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180109438`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801094a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801094db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801093cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180109438`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801094a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801094db`

## pseudocode

```c
__int64 __fastcall ConnectedStandbySimulator::StartListening(
        HANDLE *this,
        int (*a2)(struct _WNF_STATE_NAME, unsigned int, struct _WNF_TYPE_ID *, void *, const void *, unsigned int),
        void *a3,
        unsigned int (*a4)(void *, unsigned int, void *),
        void *a5)
{
  char *v8; // rsi
  HANDLE EventW; // rbx
  signed int v10; // eax
  signed int v11; // ebx
  HANDLE v12; // rbx
  signed int v13; // eax
  HANDLE v14; // rax
  HANDLE v15; // rcx
  HANDLE v16; // rsi
  HANDLE Thread; // rax
  HANDLE v18; // rcx
  HANDLE v19; // rsi
  signed int LastError; // eax

  if ( *(_BYTE *)this )
    return 0;
  v8 = (char *)(this + 3);
  EventW = CreateEventW(0, 0, 0, L"Global\\CSSIMULATOR_CS");
  if ( *(_QWORD *)v8 )
    CloseHandle(*(HANDLE *)v8);
  *(_QWORD *)v8 = EventW;
  if ( EventW )
  {
    *((_QWORD *)v8 + 2) = a3;
    *((_QWORD *)v8 + 1) = ConnectedStandbyMonitor::StaticWnfStateChangeCallback;
    v12 = CreateEventW(0, 0, 0, L"Global\\CSSIMULATOR_LPE");
    if ( this[8] )
      CloseHandle(this[8]);
    this[8] = v12;
    if ( v12 )
    {
      this[9] = ConnectedStandbyMonitor::StaticPowerSettingCallback;
      this[10] = a5;
      v11 = 0;
      v14 = CreateEventW(0, 0, 0, 0);
      v15 = this[1];
      v16 = v14;
      if ( v15 )
        CloseHandle(v15);
      this[1] = v16;
      if ( v16 )
      {
        Thread = CreateThread(0, 0, ConnectedStandbySimulator::StaticListenThread, this, 0, 0);
        v18 = this[2];
        v19 = Thread;
        if ( v18 )
          CloseHandle(v18);
        this[2] = v19;
        if ( v19 )
        {
          *(_BYTE *)this = 1;
          return (unsigned int)v11;
        }
      }
      LastError = GetLastError();
      v11 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v11 = LastError;
      if ( v11 >= 0 )
        v11 = -2147418113;
    }
    else
    {
      v13 = GetLastError();
      v11 = (unsigned __int16)v13 | 0x80070000;
      if ( v13 <= 0 )
        v11 = v13;
      if ( v11 >= 0 )
        v11 = -2147418113;
      ConnectedStandbySimulator::LowPowerEpochData::Reset((ConnectedStandbySimulator::LowPowerEpochData *)(this + 8));
    }
  }
  else
  {
    v10 = GetLastError();
    v11 = (unsigned __int16)v10 | 0x80070000;
    if ( v10 <= 0 )
      v11 = v10;
    if ( v11 >= 0 )
      v11 = -2147418113;
    ConnectedStandbySimulator::ConnectedStandbyData::Reset((ConnectedStandbySimulator::ConnectedStandbyData *)v8);
  }
  ConnectedStandbySimulator::StopListening((ConnectedStandbySimulator *)this);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180109384  mov     [rsp+arg_0], rbx
0x180109389  mov     [rsp+arg_8], rbp
0x18010938e  mov     [rsp+arg_10], rsi
0x180109393  push    rdi
0x180109394  sub     rsp, 30h
0x180109398  cmp     byte ptr [rcx], 0
0x18010939b  mov     rbp, r8
0x18010939e  mov     rdi, rcx
0x1801093a1  jz      short loc_1801093AA
0x1801093a3  xor     eax, eax
0x1801093a5  jmp     loc_180109517
0x1801093aa  lea     rsi, [rcx+18h]
0x1801093ae  xor     r8d, r8d; bInitialState
0x1801093b1  xor     ecx, ecx; lpEventAttributes
0x1801093b3  lea     r9, Name; "Global\\CSSIMULATOR_CS"
0x1801093ba  xor     edx, edx; bManualReset
0x1801093bc  call    cs:__imp_CreateEventW
0x1801093c2  mov     rcx, [rsi]; hObject
0x1801093c5  mov     rbx, rax
0x1801093c8  test    rcx, rcx
0x1801093cb  jz      short loc_1801093D3
0x1801093cd  call    cs:__imp_CloseHandle
0x1801093d3  mov     [rsi], rbx
0x1801093d6  test    rbx, rbx
0x1801093d9  jnz     short loc_180109406
0x1801093db  call    cs:__imp_GetLastError
0x1801093e1  movzx   ebx, ax
0x1801093e4  mov     rcx, rsi; this
0x1801093e7  or      ebx, 80070000h
0x1801093ed  test    eax, eax
0x1801093ef  cmovle  ebx, eax
0x1801093f2  mov     eax, 8000FFFFh
0x1801093f7  test    ebx, ebx
0x1801093f9  cmovns  ebx, eax
0x1801093fc  call    ?Reset@ConnectedStandbyData@ConnectedStandbySimulator@@QEAAXXZ; ConnectedStandbySimulator::ConnectedStandbyData::Reset(void)
0x180109401  jmp     loc_180109508
0x180109406  lea     rax, ?StaticWnfStateChangeCallback@ConnectedStandbyMonitor@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; ConnectedStandbyMonitor::StaticWnfStateChangeCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x18010940d  mov     [rsi+10h], rbp
0x180109411  mov     [rsi+8], rax
0x180109415  lea     r9, aGlobalCssimula; "Global\\CSSIMULATOR_LPE"
0x18010941c  xor     r8d, r8d; bInitialState
0x18010941f  lea     rsi, [rdi+40h]
0x180109423  xor     edx, edx; bManualReset
0x180109425  xor     ecx, ecx; lpEventAttributes
0x180109427  call    cs:__imp_CreateEventW
0x18010942d  mov     rcx, [rsi]; hObject
0x180109430  mov     rbx, rax
0x180109433  test    rcx, rcx
0x180109436  jz      short loc_18010943E
0x180109438  call    cs:__imp_CloseHandle
0x18010943e  mov     [rsi], rbx
0x180109441  test    rbx, rbx
0x180109444  jnz     short loc_180109471
0x180109446  call    cs:__imp_GetLastError
0x18010944c  movzx   ebx, ax
0x18010944f  mov     rcx, rsi; this
0x180109452  or      ebx, 80070000h
0x180109458  test    eax, eax
0x18010945a  cmovle  ebx, eax
0x18010945d  mov     eax, 8000FFFFh
0x180109462  test    ebx, ebx
0x180109464  cmovns  ebx, eax
0x180109467  call    ?Reset@LowPowerEpochData@ConnectedStandbySimulator@@QEAAXXZ; ConnectedStandbySimulator::LowPowerEpochData::Reset(void)
0x18010946c  jmp     loc_180109508
0x180109471  lea     rax, ?StaticPowerSettingCallback@ConnectedStandbyMonitor@@CAKPEAXK0@Z; ConnectedStandbyMonitor::StaticPowerSettingCallback(void *,ulong,void *)
0x180109478  xor     r9d, r9d; lpName
0x18010947b  mov     [rsi+8], rax
0x18010947f  xor     r8d, r8d; bInitialState
0x180109482  mov     rax, [rsp+38h+arg_20]
0x180109487  xor     edx, edx; bManualReset
0x180109489  xor     ecx, ecx; lpEventAttributes
0x18010948b  mov     [rsi+10h], rax
0x18010948f  xor     ebx, ebx
0x180109491  call    cs:__imp_CreateEventW
0x180109497  mov     rcx, [rdi+8]; hObject
0x18010949b  mov     rsi, rax
0x18010949e  test    rcx, rcx
0x1801094a1  jz      short loc_1801094A9
0x1801094a3  call    cs:__imp_CloseHandle
0x1801094a9  mov     [rdi+8], rsi
0x1801094ad  test    rsi, rsi
0x1801094b0  jz      short loc_1801094EA
0x1801094b2  mov     [rsp+38h+lpThreadId], rbx; lpThreadId
0x1801094b7  lea     r8, ?StaticListenThread@ConnectedStandbySimulator@@CAKPEAX@Z; lpStartAddress
0x1801094be  mov     r9, rdi; lpParameter
0x1801094c1  mov     [rsp+38h+dwCreationFlags], ebx; dwCreationFlags
0x1801094c5  xor     edx, edx; dwStackSize
0x1801094c7  xor     ecx, ecx; lpThreadAttributes
0x1801094c9  call    cs:__imp_CreateThread
0x1801094cf  mov     rcx, [rdi+10h]; hObject
0x1801094d3  mov     rsi, rax
0x1801094d6  test    rcx, rcx
0x1801094d9  jz      short loc_1801094E1
0x1801094db  call    cs:__imp_CloseHandle
0x1801094e1  mov     [rdi+10h], rsi
0x1801094e5  test    rsi, rsi
0x1801094e8  jnz     short loc_180109512
0x1801094ea  call    cs:__imp_GetLastError
0x1801094f0  movzx   ebx, ax
0x1801094f3  or      ebx, 80070000h
0x1801094f9  test    eax, eax
0x1801094fb  cmovle  ebx, eax
0x1801094fe  mov     eax, 8000FFFFh
0x180109503  test    ebx, ebx
0x180109505  cmovns  ebx, eax
0x180109508  mov     rcx, rdi; this
0x18010950b  call    ?StopListening@ConnectedStandbySimulator@@QEAAXXZ; ConnectedStandbySimulator::StopListening(void)
0x180109510  jmp     short loc_180109515
0x180109512  mov     byte ptr [rdi], 1
0x180109515  mov     eax, ebx
0x180109517  mov     rbx, [rsp+38h+arg_0]
0x18010951c  mov     rbp, [rsp+38h+arg_8]
0x180109521  mov     rsi, [rsp+38h+arg_10]
0x180109526  add     rsp, 30h
0x18010952a  pop     rdi
0x18010952b  retn
```
