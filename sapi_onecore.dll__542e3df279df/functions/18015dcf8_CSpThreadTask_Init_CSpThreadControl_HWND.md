# CSpThreadTask::Init(CSpThreadControl *,HWND__ * *)

- ea: `0x18015dcf8`
- end: `0x18015dead`
- name: `?Init@CSpThreadTask@@QEAAJPEAVCSpThreadControl@@PEAPEAUHWND__@@@Z`
- size: `437`
- prototype: `__int64 __fastcall(CSpThreadTask *__hidden this, struct CSpThreadControl *, HWND *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18015e420`

## callees

- `0x180045938`
- `0x180094190`
- `0x18015dcf8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18015ddbb`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18015ddbb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18015de2f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18015de3f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18015de6f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18015de2f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18015de3f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18015de6f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18015de4f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18015de7b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18015de8a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18015de4f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18015de7b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18015de8a`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18015dde3`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18015ddf0`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18015dde3`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18015ddf0`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18015de01`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18015de01`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18015de12`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18015de12`

## pseudocode

```c
__int64 __fastcall CSpThreadTask::Init(CSpThreadTask *this, struct _SECURITY_ATTRIBUTES *a2, HWND *a3)
{
  struct _SECURITY_ATTRIBUTES *v6; // rdx
  int inited; // edi
  struct _SECURITY_ATTRIBUTES *v8; // rdx
  __int64 v9; // rax
  void *v10; // rcx
  void *v11; // rdi
  int lpSecurityDescriptor; // r14d
  int Win32Error; // eax
  void *v14; // rcx
  HANDLE *v15; // r14
  const unsigned __int16 *v17; // [rsp+20h] [rbp-28h]
  const unsigned __int16 *v18; // [rsp+20h] [rbp-28h]
  const unsigned __int16 *v19; // [rsp+20h] [rbp-28h]
  int v20; // [rsp+50h] [rbp+8h] BYREF

  *((_QWORD *)this + 3) = a2;
  if ( a3 )
    *a3 = 0;
  *(_DWORD *)this = a3 != 0;
  a2[5].bInheritHandle = 0;
  if ( !*((_QWORD *)this + 11) )
  {
    inited = CSpAutoEvent::InitEvent((CSpThreadTask *)((char *)this + 32), a2, 1, 0, v17);
    if ( inited < 0 )
      goto LABEL_19;
    inited = CSpAutoEvent::InitEvent((CSpThreadTask *)((char *)this + 48), v6, 0, 0, v18);
    if ( inited < 0 )
      goto LABEL_19;
    inited = CSpAutoEvent::InitEvent((CSpThreadTask *)((char *)this + 64), v8, 0, 0, v19);
    if ( inited < 0 )
      goto LABEL_19;
    v20 = 0;
    v9 = _o__beginthreadex(0, 0, CSpThreadTask::ThreadProc, this, 0, &v20);
    *((_QWORD *)this + 11) = v9;
    if ( !v9 )
    {
      inited = -2147024882;
LABEL_19:
      *((_QWORD *)this + 3) = 0;
      return (unsigned int)inited;
    }
    *((_DWORD *)this + 4) = v20;
  }
  v10 = (void *)*((_QWORD *)this + 5);
  *((_DWORD *)this + 1) = 1;
  ResetEvent(v10);
  ResetEvent(a2[5].lpSecurityDescriptor);
  v11 = (void *)*((_QWORD *)this + 11);
  lpSecurityDescriptor = (int)a2[3].lpSecurityDescriptor;
  if ( GetThreadPriority(v11) == lpSecurityDescriptor || SetThreadPriority(v11, lpSecurityDescriptor) )
  {
    SetEvent(*((HANDLE *)this + 7));
    v15 = (HANDLE *)((char *)this + 72);
    WaitForSingleObject(*((HANDLE *)this + 9), 0xFFFFFFFF);
    inited = a2[5].bInheritHandle;
  }
  else
  {
    Win32Error = SpHrFromLastWin32Error();
    v14 = (void *)*((_QWORD *)this + 7);
    inited = Win32Error;
    *((_QWORD *)this + 3) = 0;
    SetEvent(v14);
    v15 = (HANDLE *)((char *)this + 72);
  }
  if ( inited < 0 )
  {
    WaitForSingleObject(*((HANDLE *)this + 11), 0xFFFFFFFF);
    goto LABEL_19;
  }
  if ( a3 )
    *a3 = (HWND)*((_QWORD *)this + 1);
  SetEvent(*((HANDLE *)this + 7));
  WaitForSingleObject(*v15, 0xFFFFFFFF);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18015dcf8  mov     [rsp+arg_8], rbx
0x18015dcfd  mov     [rsp+arg_10], rbp
0x18015dd02  push    rsi
0x18015dd03  push    rdi
0x18015dd04  push    r14
0x18015dd06  sub     rsp, 30h
0x18015dd0a  mov     [rcx+18h], rdx
0x18015dd0e  mov     rsi, r8
0x18015dd11  mov     rbp, rdx
0x18015dd14  mov     rbx, rcx
0x18015dd17  test    r8, r8
0x18015dd1a  jz      short loc_18015DD23
0x18015dd1c  mov     qword ptr [r8], 0
0x18015dd23  xor     eax, eax
0x18015dd25  mov     r14d, 1
0x18015dd2b  test    rsi, rsi
0x18015dd2e  setnz   al
0x18015dd31  mov     [rcx], eax
0x18015dd33  mov     dword ptr [rdx+88h], 0
0x18015dd3d  cmp     qword ptr [rcx+58h], 0
0x18015dd42  jnz     loc_18015DDDB
0x18015dd48  add     rcx, 20h ; ' '; this
0x18015dd4c  xor     r9d, r9d; int
0x18015dd4f  mov     r8d, r14d; int
0x18015dd52  call    ?InitEvent@CSpAutoEvent@@QEAAJPEAU_SECURITY_ATTRIBUTES@@HHPEBG@Z; CSpAutoEvent::InitEvent(_SECURITY_ATTRIBUTES *,int,int,ushort const *)
0x18015dd57  mov     edi, eax
0x18015dd59  test    eax, eax
0x18015dd5b  js      loc_18015DE90
0x18015dd61  lea     rcx, [rbx+30h]; this
0x18015dd65  xor     r9d, r9d; int
0x18015dd68  xor     r8d, r8d; int
0x18015dd6b  call    ?InitEvent@CSpAutoEvent@@QEAAJPEAU_SECURITY_ATTRIBUTES@@HHPEBG@Z; CSpAutoEvent::InitEvent(_SECURITY_ATTRIBUTES *,int,int,ushort const *)
0x18015dd70  mov     edi, eax
0x18015dd72  test    eax, eax
0x18015dd74  js      loc_18015DE90
0x18015dd7a  lea     rcx, [rbx+40h]; this
0x18015dd7e  xor     r9d, r9d; int
0x18015dd81  xor     r8d, r8d; int
0x18015dd84  call    ?InitEvent@CSpAutoEvent@@QEAAJPEAU_SECURITY_ATTRIBUTES@@HHPEBG@Z; CSpAutoEvent::InitEvent(_SECURITY_ATTRIBUTES *,int,int,ushort const *)
0x18015dd89  mov     edi, eax
0x18015dd8b  test    eax, eax
0x18015dd8d  js      loc_18015DE90
0x18015dd93  lea     rax, [rsp+48h+arg_0]
0x18015dd98  mov     [rsp+48h+arg_0], 0
0x18015dda0  mov     [rsp+48h+var_20], rax
0x18015dda5  lea     r8, ?ThreadProc@CSpThreadTask@@SAIPEAX@Z; CSpThreadTask::ThreadProc(void *)
0x18015ddac  mov     r9, rbx
0x18015ddaf  mov     dword ptr [rsp+48h+var_28], 0
0x18015ddb7  xor     edx, edx
0x18015ddb9  xor     ecx, ecx
0x18015ddbb  call    cs:__imp__o__beginthreadex
0x18015ddc1  mov     [rbx+58h], rax
0x18015ddc5  test    rax, rax
0x18015ddc8  jnz     short loc_18015DDD4
0x18015ddca  mov     edi, 8007000Eh
0x18015ddcf  jmp     loc_18015DE90
0x18015ddd4  mov     eax, [rsp+48h+arg_0]
0x18015ddd8  mov     [rbx+10h], eax
0x18015dddb  mov     rcx, [rbx+28h]; hEvent
0x18015dddf  mov     [rbx+4], r14d
0x18015dde3  call    cs:__imp_ResetEvent
0x18015dde9  mov     rcx, [rbp+80h]; hEvent
0x18015ddf0  call    cs:__imp_ResetEvent
0x18015ddf6  mov     rdi, [rbx+58h]
0x18015ddfa  mov     r14d, [rbp+50h]
0x18015ddfe  mov     rcx, rdi; hThread
0x18015de01  call    cs:__imp_GetThreadPriority
0x18015de07  cmp     eax, r14d
0x18015de0a  jz      short loc_18015DE3B
0x18015de0c  mov     edx, r14d; nPriority
0x18015de0f  mov     rcx, rdi; hThread
0x18015de12  call    cs:__imp_SetThreadPriority
0x18015de18  test    eax, eax
0x18015de1a  jnz     short loc_18015DE3B
0x18015de1c  call    ?SpHrFromLastWin32Error@@YAJXZ; SpHrFromLastWin32Error(void)
0x18015de21  mov     rcx, [rbx+38h]; hEvent
0x18015de25  mov     edi, eax
0x18015de27  mov     qword ptr [rbx+18h], 0
0x18015de2f  call    cs:__imp_SetEvent
0x18015de35  lea     r14, [rbx+48h]
0x18015de39  jmp     short loc_18015DE5B
0x18015de3b  mov     rcx, [rbx+38h]; hEvent
0x18015de3f  call    cs:__imp_SetEvent
0x18015de45  lea     r14, [rbx+48h]
0x18015de49  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18015de4c  mov     rcx, [r14]; hHandle
0x18015de4f  call    cs:__imp_WaitForSingleObject
0x18015de55  mov     edi, [rbp+88h]
0x18015de5b  test    edi, edi
0x18015de5d  js      short loc_18015DE83
0x18015de5f  test    rsi, rsi
0x18015de62  jz      short loc_18015DE6B
0x18015de64  mov     rax, [rbx+8]
0x18015de68  mov     [rsi], rax
0x18015de6b  mov     rcx, [rbx+38h]; hEvent
0x18015de6f  call    cs:__imp_SetEvent
0x18015de75  mov     rcx, [r14]; hHandle
0x18015de78  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18015de7b  call    cs:__imp_WaitForSingleObject
0x18015de81  jmp     short loc_18015DE98
0x18015de83  mov     rcx, [rbx+58h]; hHandle
0x18015de87  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18015de8a  call    cs:__imp_WaitForSingleObject
0x18015de90  mov     qword ptr [rbx+18h], 0
0x18015de98  mov     rbx, [rsp+48h+arg_8]
0x18015de9d  mov     eax, edi
0x18015de9f  mov     rbp, [rsp+48h+arg_10]
0x18015dea4  add     rsp, 30h
0x18015dea8  pop     r14
0x18015deaa  pop     rdi
0x18015deab  pop     rsi
0x18015deac  retn
```
