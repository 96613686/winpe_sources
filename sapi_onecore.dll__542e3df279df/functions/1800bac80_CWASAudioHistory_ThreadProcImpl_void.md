# CWASAudioHistory::ThreadProcImpl(void *)

- ea: `0x1800bac80`
- end: `0x1800baefd`
- name: `?ThreadProcImpl@CWASAudioHistory@@EEAAJPEAX@Z`
- size: `637`
- prototype: `int(CWASAudioHistory *__hidden this, void *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180013ec0`
- `0x1800a1818`
- `0x1800a18c0`
- `0x1800ba0b8`
- `0x1800ba2c0`
- `0x1800bac80`
- `0x1800baf04`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800bae21`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800bae21`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800bad06`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800bade3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800bae45`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800bae7c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800bad06`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800bade3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800bae45`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800bae7c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bad18`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bae08`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bae99`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800baea3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bad18`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bae08`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bae99`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800baea3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bad72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bad72`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800bad9c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800bad9c`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800bad53`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800bad53`

## string_xrefs

- `0x1800bac9f`: `[%s] Audio processing thread started.`
- `0x1800bac98`: `CWASAudioHistory::ThreadProcImpl`
- `0x1800bacde`: `CWASAudioHistory::ThreadProcImpl`
- `0x1800bad7f`: `CWASAudioHistory::ThreadProcImpl`
- `0x1800badb0`: `CWASAudioHistory::ThreadProcImpl`
- `0x1800baeb8`: `CWASAudioHistory::ThreadProcImpl`
- `0x1800baed3`: `CWASAudioHistory::ThreadProcImpl`
- `0x1800badb7`: `[%s] Unexpected state - timeout occuring`
- `0x1800bace5`: `[%s] AttachThreadToMMCSS. %x, %x`
- `0x1800baebf`: `[%s] DetachThreadFromMMCSS, bResult: %d`
- `0x1800baeda`: `[%s] Audio processing thread finished, hr: %x`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWASAudioHistory::ThreadProcImpl(CWASAudioHistory *this, void *a2)
{
  CWASAudio *v4; // rcx
  int (*v5)(void *); // r12
  char *v6; // rsi
  __int64 v7; // rbx
  unsigned int v8; // r14d
  DWORD v9; // eax
  DWORD v10; // ebx
  DWORD LastError; // eax
  CWASAudio *v12; // rcx
  struct _RTL_CRITICAL_SECTION *v13; // rbx
  unsigned int v14; // r14d
  struct _RTL_CRITICAL_SECTION *v15; // r15
  struct _RTL_CRITICAL_SECTION *v16; // rbx
  int v17; // eax
  HANDLE Handles[2]; // [rsp+30h] [rbp-10h] BYREF
  void *v20; // [rsp+80h] [rbp+40h] BYREF
  int (*v21)(void *); // [rsp+88h] [rbp+48h] BYREF
  unsigned __int64 v22; // [rsp+90h] [rbp+50h]

  DoTraceMessage(8, "[%s] Audio processing thread started.", "CWASAudioHistory::ThreadProcImpl");
  v20 = 0;
  v21 = 0;
  CWASAudio::AttachThreadToMMCSS(v4, &v20, &v21);
  v5 = v21;
  DoTraceMessage(8, "[%s] AttachThreadToMMCSS. %x, %x", "CWASAudioHistory::ThreadProcImpl", (_DWORD)v20, (_DWORD)v21);
  v6 = (char *)this - 32;
  v7 = (__int64)this + 40;
  if ( this == (CWASAudioHistory *)32 )
    v7 = 8;
  EnterCriticalSection((LPCRITICAL_SECTION)v7);
  *((_WORD *)this + 176) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)v7);
  v8 = 0;
  while ( 1 )
  {
    Handles[0] = a2;
    Handles[1] = *((HANDLE *)this + 71);
    if ( *((_WORD *)this + 176) )
      break;
    v9 = WaitForMultipleObjects(2u, Handles, 0, 0x1Eu);
    v10 = v9;
    switch ( v9 )
    {
      case 0u:
        goto LABEL_17;
      case 1u:
LABEL_11:
        v21 = (int (*)(void *))(((unsigned __int64)this + 32)
                              & ((unsigned __int128)-(__int128)(unsigned __int64)v6 >> 64));
        v13 = (struct _RTL_CRITICAL_SECTION *)((char *)v21 + 8);
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)v21 + 8));
        if ( *((_DWORD *)this + 64) == 3 && *((_BYTE *)this + 564) )
          CWASAudioHistory::ProcessDeviceBuffers((CWASAudioHistory *)((char *)this - 32));
        LeaveCriticalSection(v13);
        break;
      case 0x102u:
        DoTraceMessage(8, "[%s] Unexpected state - timeout occuring", "CWASAudioHistory::ThreadProcImpl");
        goto LABEL_11;
      default:
        LastError = GetLastError();
        DoTraceMessage(
          8,
          "[%s] Unexpected state,dwWaitId: %x, GetLastError(): %x",
          "CWASAudioHistory::ThreadProcImpl",
          v10,
          LastError);
        Sleep(0x1Eu);
        if ( v8 > 5 )
        {
          v14 = -2147024809;
          goto LABEL_20;
        }
        ++v8;
        break;
    }
  }
  SetEvent(a2);
LABEL_17:
  v14 = 0;
  v21 = (int (*)(void *))(((unsigned __int64)this + 32) & -(__int64)(this != (CWASAudioHistory *)32));
  v15 = (struct _RTL_CRITICAL_SECTION *)((char *)v21 + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v21 + 8));
  if ( *((int *)this + 64) > 1 )
    CWASAudioHistory::InternalStateChange((CWASAudioHistory *)((char *)this - 32), SPAS_STOP);
  v22 = ((unsigned __int64)this + 32) & -(__int64)(this != (CWASAudioHistory *)32);
  v16 = (struct _RTL_CRITICAL_SECTION *)(v22 + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)(v22 + 8));
  *((_DWORD *)v6 + 72) = 0;
  CWASAudioHistory::UninitializeDevice((CWASAudioHistory *)((char *)this - 32));
  LeaveCriticalSection(v16);
  LeaveCriticalSection(v15);
LABEL_20:
  v17 = CWASAudio::DetachThreadFromMMCSS(v12, v20, v5);
  DoTraceMessage(8, "[%s] DetachThreadFromMMCSS, bResult: %d", "CWASAudioHistory::ThreadProcImpl", v17);
  DoTraceMessage(8, "[%s] Audio processing thread finished, hr: %x", "CWASAudioHistory::ThreadProcImpl", v14);
  return v14;
}

```

## disassembly

```asm
0x1800bac80  push    rbp
0x1800bac82  push    rbx
0x1800bac83  push    rsi
0x1800bac84  push    rdi
0x1800bac85  push    r12
0x1800bac87  push    r14
0x1800bac89  push    r15
0x1800bac8b  mov     rbp, rsp
0x1800bac8e  sub     rsp, 40h
0x1800bac92  mov     r15, rdx
0x1800bac95  mov     rdi, rcx
0x1800bac98  lea     r8, aCwasaudiohisto_2; "CWASAudioHistory::ThreadProcImpl"
0x1800bac9f  lea     rdx, aSAudioProcessi; "[%s] Audio processing thread started."
0x1800baca6  mov     r14d, 8
0x1800bacac  mov     ecx, r14d; int
0x1800bacaf  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1800bacb4  mov     [rbp+arg_0], 0
0x1800bacbc  mov     [rbp+arg_8], 0
0x1800bacc4  lea     r8, [rbp+arg_8]; int (**)(void *)
0x1800bacc8  lea     rdx, [rbp+arg_0]; void **
0x1800baccc  call    ?AttachThreadToMMCSS@CWASAudio@@QEAAXAEAPEAXAEAP6AHPEAX@Z@Z; CWASAudio::AttachThreadToMMCSS(void * &,int (*&)(void *))
0x1800bacd1  mov     r12, [rbp+arg_8]
0x1800bacd5  mov     [rsp+40h+var_20], r12
0x1800bacda  mov     r9, [rbp+arg_0]
0x1800bacde  lea     r8, aCwasaudiohisto_2; "CWASAudioHistory::ThreadProcImpl"
0x1800bace5  lea     rdx, aSAttachthreadt; "[%s] AttachThreadToMMCSS. %x, %x"
0x1800bacec  mov     ecx, r14d; int
0x1800bacef  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1800bacf4  lea     rsi, [rdi-20h]
0x1800bacf8  lea     rbx, [rdi+28h]
0x1800bacfc  test    rsi, rsi
0x1800bacff  cmovz   rbx, r14
0x1800bad03  mov     rcx, rbx; lpCriticalSection
0x1800bad06  call    cs:__imp_EnterCriticalSection
0x1800bad0c  mov     word ptr [rdi+160h], 0
0x1800bad15  mov     rcx, rbx; lpCriticalSection
0x1800bad18  call    cs:__imp_LeaveCriticalSection
0x1800bad1e  xor     r14d, r14d
0x1800bad21  mov     [rbp+Handles], r15
0x1800bad25  mov     rax, [rdi+238h]
0x1800bad2c  mov     [rbp+var_8], rax
0x1800bad30  mov     al, [rdi+161h]
0x1800bad36  or      al, [rdi+160h]
0x1800bad3c  jnz     loc_1800BAE1E
0x1800bad42  mov     r9d, 1Eh; dwMilliseconds
0x1800bad48  xor     r8d, r8d; bWaitAll
0x1800bad4b  lea     rdx, [rbp+Handles]; lpHandles
0x1800bad4f  lea     ecx, [r9-1Ch]; nCount
0x1800bad53  call    cs:__imp_WaitForMultipleObjects
0x1800bad59  mov     ebx, eax
0x1800bad5b  mov     ecx, eax
0x1800bad5d  test    eax, eax
0x1800bad5f  jz      loc_1800BAE27
0x1800bad65  sub     ecx, 1
0x1800bad68  jz      short loc_1800BADC8
0x1800bad6a  cmp     ecx, 101h
0x1800bad70  jz      short loc_1800BADB0
0x1800bad72  call    cs:__imp_GetLastError
0x1800bad78  mov     dword ptr [rsp+40h+var_20], eax
0x1800bad7c  mov     r9d, ebx
0x1800bad7f  lea     r8, aCwasaudiohisto_2; "CWASAudioHistory::ThreadProcImpl"
0x1800bad86  lea     rdx, aSUnexpectedSta_1; "[%s] Unexpected state,dwWaitId: %x, Get"...
0x1800bad8d  mov     ecx, 8; int
0x1800bad92  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1800bad97  mov     ecx, 1Eh; dwMilliseconds
0x1800bad9c  call    cs:__imp_Sleep
0x1800bada2  cmp     r14d, 5
0x1800bada6  ja      short loc_1800BAE13
0x1800bada8  inc     r14d
0x1800badab  jmp     loc_1800BAD21
0x1800badb0  lea     r8, aCwasaudiohisto_2; "CWASAudioHistory::ThreadProcImpl"
0x1800badb7  lea     rdx, aSUnexpectedSta_0; "[%s] Unexpected state - timeout occurin"...
0x1800badbe  mov     ecx, 8; int
0x1800badc3  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1800badc8  mov     rax, rsi
0x1800badcb  lea     rcx, [rdi+20h]
0x1800badcf  neg     rax
0x1800badd2  sbb     rdx, rdx
0x1800badd5  and     rdx, rcx
0x1800badd8  mov     [rbp+arg_8], rdx
0x1800baddc  lea     rbx, [rdx+8]
0x1800bade0  mov     rcx, rbx; lpCriticalSection
0x1800bade3  call    cs:__imp_EnterCriticalSection
0x1800bade9  nop
0x1800badea  cmp     dword ptr [rdi+100h], 3
0x1800badf1  jnz     short loc_1800BAE05
0x1800badf3  cmp     byte ptr [rdi+234h], 0
0x1800badfa  jz      short loc_1800BAE05
0x1800badfc  mov     rcx, rsi; this
0x1800badff  call    ?ProcessDeviceBuffers@CWASAudioHistory@@AEAAJXZ; CWASAudioHistory::ProcessDeviceBuffers(void)
0x1800bae04  nop
0x1800bae05  mov     rcx, rbx; lpCriticalSection
0x1800bae08  call    cs:__imp_LeaveCriticalSection
0x1800bae0e  jmp     loc_1800BAD21
0x1800bae13  mov     r14d, 80070057h
0x1800bae19  jmp     loc_1800BAEA9
0x1800bae1e  mov     rcx, r15; hEvent
0x1800bae21  call    cs:__imp_SetEvent
0x1800bae27  xor     r14d, r14d
0x1800bae2a  mov     rax, rsi
0x1800bae2d  lea     rcx, [rdi+20h]
0x1800bae31  neg     rax
0x1800bae34  sbb     r8, r8
0x1800bae37  and     r8, rcx
0x1800bae3a  mov     [rbp+arg_8], r8
0x1800bae3e  lea     r15, [r8+8]
0x1800bae42  mov     rcx, r15; lpCriticalSection
0x1800bae45  call    cs:__imp_EnterCriticalSection
0x1800bae4b  nop
0x1800bae4c  cmp     dword ptr [rdi+100h], 1
0x1800bae53  jle     short loc_1800BAE61
0x1800bae55  lea     edx, [r14+1]; enum _SPAUDIOSTATE
0x1800bae59  mov     rcx, rsi; this
0x1800bae5c  call    ?InternalStateChange@CWASAudioHistory@@AEAAJW4_SPAUDIOSTATE@@@Z; CWASAudioHistory::InternalStateChange(_SPAUDIOSTATE)
0x1800bae61  mov     rax, rsi
0x1800bae64  lea     rdx, [rsi+40h]
0x1800bae68  neg     rax
0x1800bae6b  sbb     r8, r8
0x1800bae6e  and     r8, rdx
0x1800bae71  mov     [rbp+arg_10], r8
0x1800bae75  lea     rbx, [r8+8]
0x1800bae79  mov     rcx, rbx; lpCriticalSection
0x1800bae7c  call    cs:__imp_EnterCriticalSection
0x1800bae82  nop
0x1800bae83  mov     dword ptr [rsi+120h], 0
0x1800bae8d  mov     rcx, rsi; this
0x1800bae90  call    ?UninitializeDevice@CWASAudioHistory@@AEAAXXZ; CWASAudioHistory::UninitializeDevice(void)
0x1800bae95  nop
0x1800bae96  mov     rcx, rbx; lpCriticalSection
0x1800bae99  call    cs:__imp_LeaveCriticalSection
0x1800bae9f  nop
0x1800baea0  mov     rcx, r15; lpCriticalSection
0x1800baea3  call    cs:__imp_LeaveCriticalSection
0x1800baea9  mov     r8, r12; int (*)(void *)
0x1800baeac  mov     rdx, [rbp+arg_0]; void *
0x1800baeb0  call    ?DetachThreadFromMMCSS@CWASAudio@@QEAAHPEAXP6AH0@Z@Z; CWASAudio::DetachThreadFromMMCSS(void *,int (*)(void *))
0x1800baeb5  mov     r9d, eax
0x1800baeb8  lea     r8, aCwasaudiohisto_2; "CWASAudioHistory::ThreadProcImpl"
0x1800baebf  lea     rdx, aSDetachthreadf; "[%s] DetachThreadFromMMCSS, bResult: %d"
0x1800baec6  mov     ecx, 8; int
0x1800baecb  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1800baed0  mov     r9d, r14d
0x1800baed3  lea     r8, aCwasaudiohisto_2; "CWASAudioHistory::ThreadProcImpl"
0x1800baeda  lea     rdx, aSAudioProcessi_0; "[%s] Audio processing thread finished, "...
0x1800baee1  mov     ecx, 8; int
0x1800baee6  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1800baeeb  mov     eax, r14d
0x1800baeee  add     rsp, 40h
0x1800baef2  pop     r15
0x1800baef4  pop     r14
0x1800baef6  pop     r12
0x1800baef8  pop     rdi
0x1800baef9  pop     rsi
0x1800baefa  pop     rbx
0x1800baefb  pop     rbp
0x1800baefc  retn
```
