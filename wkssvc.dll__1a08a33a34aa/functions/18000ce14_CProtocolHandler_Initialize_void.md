# CProtocolHandler::Initialize(void)

- ea: `0x18000ce14`
- end: `0x18000cf8b`
- name: `?Initialize@CProtocolHandler@@QEAAKXZ`
- size: `375`
- prototype: `unsigned int __fastcall(CProtocolHandler *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000c978`

## callees

- `0x18000c3e8`
- `0x18000ce14`
- `0x18000cf94`
- `0x180021d0c`
- `0x180024550`
- `0x180035888`
- `0x18003591c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cf19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cf19`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000ce82`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000ce82`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000ce9f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000ce9f`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000cf46`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000cf46`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x18000cf04`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x18000cf04`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned int __fastcall CProtocolHandler::Initialize(CProtocolHandler *this)
{
  CProtocolHandler *v1; // rdi
  unsigned int v2; // eax
  HANDLE EventW; // rax
  unsigned int result; // eax
  HANDLE IoCompletionPort; // rax
  HANDLE Thread; // rax
  struct _RTL_CRITICAL_SECTION *v7; // [rsp+40h] [rbp+8h]
  _OWORD *v8; // [rsp+40h] [rbp+8h]

  v1 = WitnessProtocolHandler;
  v2 = CProtocolHandler::ConfigureRegValue(WitnessProtocolHandler);
  if ( v2
    && WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
    && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) )
  {
    WPP_SF_d(*((_QWORD *)WPP_witness_GLOBAL_Control + 2), 24, &WPP_8c6a6f45ef833141536139e9b45518e8_Traceguids, v2);
  }
  v7 = (struct _RTL_CRITICAL_SECTION *)operator new(0x28u);
  InitializeCriticalSection(v7);
  *((_QWORD *)v1 + 10) = v7;
  EventW = CreateEventW(0, 1, 1, 0);
  *((_QWORD *)v1 + 17) = EventW;
  if ( !EventW )
    return 1450;
  v8 = operator new(0x68u);
  *(_QWORD *)v8 = 0;
  v8[5] = 0;
  *((_QWORD *)v8 + 12) = 0;
  *((_QWORD *)v1 + 7) = v8;
  result = CThreadPool::InitializeThreadPool((CThreadPool *)v8);
  if ( !result )
  {
    IoCompletionPort = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, 0);
    *((_QWORD *)v1 + 8) = IoCompletionPort;
    if ( !IoCompletionPort )
      return GetLastError();
    Thread = CreateThread(0, 0, StartIOProcessing, v1, 0, 0);
    *((_QWORD *)v1 + 9) = Thread;
    if ( Thread == (HANDLE)-1LL )
    {
      return GetLastError();
    }
    else
    {
      result = WitnessOpenRedirector((void **)v1 + 11);
      if ( !result )
      {
        result = CProtocolHandler::GetComputerInformation(v1);
        if ( !result )
          *((_DWORD *)v1 + 32) = 1;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000ce14  mov     [rsp+arg_8], rbx
0x18000ce19  mov     [rsp+arg_0], rcx
0x18000ce1e  push    rdi
0x18000ce1f  sub     rsp, 30h
0x18000ce23  mov     rdi, cs:?WitnessProtocolHandler@@3PEAVCProtocolHandler@@EA; CProtocolHandler * WitnessProtocolHandler
0x18000ce2a  mov     rcx, rdi; this
0x18000ce2d  call    ?ConfigureRegValue@CProtocolHandler@@AEAAKXZ; CProtocolHandler::ConfigureRegValue(void)
0x18000ce32  test    eax, eax
0x18000ce34  jz      short loc_18000CE6D
0x18000ce36  lea     rdx, WPP_witness_GLOBAL_Control
0x18000ce3d  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000ce44  cmp     rcx, rdx
0x18000ce47  jz      short loc_18000CE6D
0x18000ce49  test    byte ptr [rcx+1Ch], 1
0x18000ce4d  jz      short loc_18000CE6D
0x18000ce4f  cmp     byte ptr [rcx+19h], 1
0x18000ce53  jb      short loc_18000CE6D
0x18000ce55  mov     edx, 18h
0x18000ce5a  mov     r9d, eax
0x18000ce5d  lea     r8, WPP_8c6a6f45ef833141536139e9b45518e8_Traceguids
0x18000ce64  mov     rcx, [rcx+10h]
0x18000ce68  call    WPP_SF_d
0x18000ce6d  mov     ecx, 28h ; '('; Size
0x18000ce72  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ce77  mov     rbx, rax
0x18000ce7a  mov     [rsp+38h+arg_0], rax
0x18000ce7f  mov     rcx, rax; lpCriticalSection
0x18000ce82  call    cs:__imp_InitializeCriticalSection
0x18000ce89  nop     dword ptr [rax+rax+00h]
0x18000ce8e  nop
0x18000ce8f  mov     [rdi+50h], rbx
0x18000ce93  xor     r9d, r9d; lpName
0x18000ce96  lea     edx, [r9+1]; bManualReset
0x18000ce9a  xor     ecx, ecx; lpEventAttributes
0x18000ce9c  mov     r8d, edx; bInitialState
0x18000ce9f  call    cs:__imp_CreateEventW
0x18000cea6  nop     dword ptr [rax+rax+00h]
0x18000ceab  mov     [rdi+88h], rax
0x18000ceb2  test    rax, rax
0x18000ceb5  jnz     short loc_18000CEC1
0x18000ceb7  mov     eax, 5AAh
0x18000cebc  jmp     loc_18000CF7F
0x18000cec1  mov     ecx, 68h ; 'h'; Size
0x18000cec6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000cecb  mov     [rsp+38h+arg_0], rax
0x18000ced0  mov     qword ptr [rax], 0
0x18000ced7  xorps   xmm0, xmm0
0x18000ceda  xor     ecx, ecx
0x18000cedc  movups  xmmword ptr [rax+50h], xmm0
0x18000cee0  mov     [rax+60h], rcx
0x18000cee4  mov     [rdi+38h], rax
0x18000cee8  mov     rcx, rax; this
0x18000ceeb  call    ?InitializeThreadPool@CThreadPool@@QEAAKXZ; CThreadPool::InitializeThreadPool(void)
0x18000cef0  test    eax, eax
0x18000cef2  jnz     loc_18000CF7F
0x18000cef8  xor     r9d, r9d; NumberOfConcurrentThreads
0x18000cefb  xor     r8d, r8d; CompletionKey
0x18000cefe  xor     edx, edx; ExistingCompletionPort
0x18000cf00  or      rcx, 0FFFFFFFFFFFFFFFFh; FileHandle
0x18000cf04  call    cs:__imp_CreateIoCompletionPort
0x18000cf0b  nop     dword ptr [rax+rax+00h]
0x18000cf10  mov     [rdi+40h], rax
0x18000cf14  test    rax, rax
0x18000cf17  jnz     short loc_18000CF27
0x18000cf19  call    cs:__imp_GetLastError
0x18000cf20  nop     dword ptr [rax+rax+00h]
0x18000cf25  jmp     short loc_18000CF7F
0x18000cf27  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x18000cf30  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x18000cf38  mov     r9, rdi; lpParameter
0x18000cf3b  lea     r8, ?StartIOProcessing@@YAKPEAX@Z; lpStartAddress
0x18000cf42  xor     edx, edx; dwStackSize
0x18000cf44  xor     ecx, ecx; lpThreadAttributes
0x18000cf46  call    cs:__imp_CreateThread
0x18000cf4d  nop     dword ptr [rax+rax+00h]
0x18000cf52  mov     [rdi+48h], rax
0x18000cf56  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000cf5a  jz      short loc_18000CF19
0x18000cf5c  lea     rcx, [rdi+58h]; void **
0x18000cf60  call    ?WitnessOpenRedirector@@YAKPEAPEAX@Z; WitnessOpenRedirector(void * *)
0x18000cf65  test    eax, eax
0x18000cf67  jnz     short loc_18000CF7F
0x18000cf69  mov     rcx, rdi; this
0x18000cf6c  call    ?GetComputerInformation@CProtocolHandler@@QEAAKXZ; CProtocolHandler::GetComputerInformation(void)
0x18000cf71  test    eax, eax
0x18000cf73  jnz     short loc_18000CF7F
0x18000cf75  mov     dword ptr [rdi+80h], 1
0x18000cf7f  mov     rbx, [rsp+38h+arg_8]
0x18000cf84  add     rsp, 30h
0x18000cf88  pop     rdi
0x18000cf89  retn
```
