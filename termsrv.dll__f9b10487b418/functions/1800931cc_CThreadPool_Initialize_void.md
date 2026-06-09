# CThreadPool::Initialize(void)

- ea: `0x1800931cc`
- end: `0x180093430`
- name: `?Initialize@CThreadPool@@QEAAJXZ`
- size: `612`
- prototype: `__int64 __fastcall(CThreadPool *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180041a70`
- `0x180042ab0`

## callees

- `0x1800931cc`
- `0x180093550`
- `0x180093714`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800931fc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800931fc`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18009320b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18009320b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093215`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009328a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800932fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800933b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093215`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009328a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800932fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800933b8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x1800933a9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x1800933a9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x1800932f2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x1800932f2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x1800932de`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x1800932de`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18009327b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18009327b`

## pseudocode

```c
__int64 __fastcall CThreadPool::Initialize(CThreadPool *this)
{
  unsigned int v2; // ebx
  void *v3; // rcx
  HANDLE EventW; // rax
  __int64 v5; // r8
  bool v6; // zf
  signed int LastError; // eax
  struct _TP_POOL *Threadpool; // rax
  signed int v9; // eax
  __int64 v10; // r8
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  DWORD v13; // edx
  DWORD v14; // edx
  signed int v15; // eax
  __int64 v16; // rax
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  signed int v18; // eax

  v2 = 0;
  *((_DWORD *)this + 4) = 0;
  v3 = (void *)*((_QWORD *)this + 1);
  if ( v3 )
  {
    v6 = !ResetEvent(v3);
  }
  else
  {
    EventW = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)this + 1) = EventW;
    v6 = EventW == 0;
  }
  if ( v6 )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( (v2 & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, v5, v2);
    }
    goto LABEL_43;
  }
  if ( !*((_DWORD *)this + 38) )
    goto LABEL_30;
  Threadpool = CreateThreadpool(0);
  *((_QWORD *)this + 4) = Threadpool;
  if ( !Threadpool )
  {
    v9 = GetLastError();
    v2 = v9;
    if ( v9 > 0 )
      v2 = (unsigned __int16)v9 | 0x80070000;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = 13;
LABEL_41:
      WPP_SF_d(v11[2], v12, v10, v2);
      goto LABEL_42;
    }
    goto LABEL_42;
  }
  v13 = *((_DWORD *)this + 40);
  if ( v13 )
    SetThreadpoolThreadMaximum(Threadpool, v13);
  v14 = *((_DWORD *)this + 39);
  if ( !v14 || SetThreadpoolThreadMinimum(*((PTP_POOL *)this + 4), v14) )
  {
LABEL_30:
    *((_DWORD *)this + 12) = 3;
    *((_QWORD *)this + 7) = 0;
    *((_QWORD *)this + 8) = 0;
    *((_QWORD *)this + 9) = 0;
    *((_QWORD *)this + 10) = 0;
    *((_QWORD *)this + 11) = 0;
    *((_QWORD *)this + 12) = 0;
    *((_DWORD *)this + 26) = 0;
    *((_DWORD *)this + 27) = 1;
    *((_DWORD *)this + 28) = 72;
    v16 = *((_QWORD *)this + 4);
    if ( v16 )
      *((_QWORD *)this + 7) = v16;
    if ( *((_DWORD *)this + 37) )
      *((_DWORD *)this + 26) |= 1u;
    ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
    *((_QWORD *)this + 5) = ThreadpoolCleanupGroup;
    if ( ThreadpoolCleanupGroup )
    {
      *((_QWORD *)this + 8) = ThreadpoolCleanupGroup;
      *((_QWORD *)this + 9) = 0;
      *((_DWORD *)this + 6) = 1;
      return v2;
    }
    v18 = GetLastError();
    v2 = v18;
    if ( v18 > 0 )
      v2 = (unsigned __int16)v18 | 0x80070000;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = 15;
      goto LABEL_41;
    }
    goto LABEL_42;
  }
  v15 = GetLastError();
  v2 = v15;
  if ( v15 > 0 )
    v2 = (unsigned __int16)v15 | 0x80070000;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v12 = 14;
    goto LABEL_41;
  }
LABEL_42:
  if ( (v2 & 0x80000000) != 0 )
LABEL_43:
    CThreadPool::Terminate(this, 0);
  return v2;
}

```

## disassembly

```asm
0x1800931cc  mov     [rsp+arg_0], rbx
0x1800931d1  mov     [rsp+arg_8], rdi
0x1800931d6  push    r14
0x1800931d8  sub     rsp, 20h
0x1800931dc  mov     rdi, rcx
0x1800931df  xor     ebx, ebx
0x1800931e1  mov     r14d, 80070000h
0x1800931e7  mov     [rcx+10h], ebx
0x1800931ea  mov     rcx, [rcx+8]; hEvent
0x1800931ee  test    rcx, rcx
0x1800931f1  jnz     short loc_18009320B
0x1800931f3  xor     r9d, r9d; lpName
0x1800931f6  lea     edx, [rbx+1]; bManualReset
0x1800931f9  xor     r8d, r8d; bInitialState
0x1800931fc  call    cs:__imp_CreateEventW
0x180093202  mov     [rdi+8], rax
0x180093206  test    rax, rax
0x180093209  jmp     short loc_180093213
0x18009320b  call    cs:__imp_ResetEvent
0x180093211  test    eax, eax
0x180093213  jnz     short loc_180093227
0x180093215  call    cs:__imp_GetLastError
0x18009321b  mov     ebx, eax
0x18009321d  test    eax, eax
0x18009321f  jle     short loc_180093227
0x180093221  movzx   ebx, ax
0x180093224  or      ebx, r14d
0x180093227  test    ebx, ebx
0x180093229  jns     short loc_18009326C
0x18009322b  mov     rcx, cs:WPP_GLOBAL_Control
0x180093232  lea     rax, WPP_GLOBAL_Control
0x180093239  cmp     rcx, rax
0x18009323c  jz      loc_1800933FE
0x180093242  test    byte ptr [rcx+1Ch], 1
0x180093246  jz      loc_1800933FE
0x18009324c  cmp     byte ptr [rcx+19h], 2
0x180093250  jb      loc_1800933FE
0x180093256  mov     rcx, [rcx+10h]
0x18009325a  mov     edx, 0Ch
0x18009325f  mov     r9d, ebx
0x180093262  call    WPP_SF_d
0x180093267  jmp     loc_1800933FE
0x18009326c  cmp     dword ptr [rdi+98h], 0
0x180093273  jz      loc_180093343
0x180093279  xor     ecx, ecx; reserved
0x18009327b  call    cs:__imp_CreateThreadpool
0x180093281  mov     [rdi+20h], rax
0x180093285  test    rax, rax
0x180093288  jnz     short loc_1800932D1
0x18009328a  call    cs:__imp_GetLastError
0x180093290  mov     ebx, eax
0x180093292  test    eax, eax
0x180093294  jle     short loc_18009329C
0x180093296  movzx   ebx, ax
0x180093299  or      ebx, r14d
0x18009329c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800932a3  lea     rax, WPP_GLOBAL_Control
0x1800932aa  cmp     rcx, rax
0x1800932ad  jz      loc_1800933FA
0x1800932b3  test    byte ptr [rcx+1Ch], 1
0x1800932b7  jz      loc_1800933FA
0x1800932bd  cmp     byte ptr [rcx+19h], 2
0x1800932c1  jb      loc_1800933FA
0x1800932c7  mov     edx, 0Dh
0x1800932cc  jmp     loc_1800933EE
0x1800932d1  mov     edx, [rdi+0A0h]; cthrdMost
0x1800932d7  test    edx, edx
0x1800932d9  jz      short loc_1800932E4
0x1800932db  mov     rcx, rax; ptpp
0x1800932de  call    cs:__imp_SetThreadpoolThreadMaximum
0x1800932e4  mov     edx, [rdi+9Ch]; cthrdMic
0x1800932ea  test    edx, edx
0x1800932ec  jz      short loc_180093343
0x1800932ee  mov     rcx, [rdi+20h]; ptpp
0x1800932f2  call    cs:__imp_SetThreadpoolThreadMinimum
0x1800932f8  test    eax, eax
0x1800932fa  jnz     short loc_180093343
0x1800932fc  call    cs:__imp_GetLastError
0x180093302  mov     ebx, eax
0x180093304  test    eax, eax
0x180093306  jle     short loc_18009330E
0x180093308  movzx   ebx, ax
0x18009330b  or      ebx, r14d
0x18009330e  mov     rcx, cs:WPP_GLOBAL_Control
0x180093315  lea     rax, WPP_GLOBAL_Control
0x18009331c  cmp     rcx, rax
0x18009331f  jz      loc_1800933FA
0x180093325  test    byte ptr [rcx+1Ch], 1
0x180093329  jz      loc_1800933FA
0x18009332f  cmp     byte ptr [rcx+19h], 2
0x180093333  jb      loc_1800933FA
0x180093339  mov     edx, 0Eh
0x18009333e  jmp     loc_1800933EE
0x180093343  mov     dword ptr [rdi+30h], 3
0x18009334a  mov     qword ptr [rdi+38h], 0
0x180093352  mov     qword ptr [rdi+40h], 0
0x18009335a  mov     qword ptr [rdi+48h], 0
0x180093362  mov     qword ptr [rdi+50h], 0
0x18009336a  mov     qword ptr [rdi+58h], 0
0x180093372  mov     qword ptr [rdi+60h], 0
0x18009337a  mov     dword ptr [rdi+68h], 0
0x180093381  mov     dword ptr [rdi+6Ch], 1
0x180093388  mov     dword ptr [rdi+70h], 48h ; 'H'
0x18009338f  mov     rax, [rdi+20h]
0x180093393  test    rax, rax
0x180093396  jz      short loc_18009339C
0x180093398  mov     [rdi+38h], rax
0x18009339c  cmp     dword ptr [rdi+94h], 0
0x1800933a3  jz      short loc_1800933A9
0x1800933a5  or      dword ptr [rdi+68h], 1
0x1800933a9  call    cs:__imp_CreateThreadpoolCleanupGroup
0x1800933af  mov     [rdi+28h], rax
0x1800933b3  test    rax, rax
0x1800933b6  jnz     short loc_18009340A
0x1800933b8  call    cs:__imp_GetLastError
0x1800933be  mov     ebx, eax
0x1800933c0  test    eax, eax
0x1800933c2  jle     short loc_1800933CA
0x1800933c4  movzx   ebx, ax
0x1800933c7  or      ebx, r14d
0x1800933ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800933d1  lea     rax, WPP_GLOBAL_Control
0x1800933d8  cmp     rcx, rax
0x1800933db  jz      short loc_1800933FA
0x1800933dd  test    byte ptr [rcx+1Ch], 1
0x1800933e1  jz      short loc_1800933FA
0x1800933e3  cmp     byte ptr [rcx+19h], 2
0x1800933e7  jb      short loc_1800933FA
0x1800933e9  mov     edx, 0Fh
0x1800933ee  mov     rcx, [rcx+10h]
0x1800933f2  mov     r9d, ebx
0x1800933f5  call    WPP_SF_d
0x1800933fa  test    ebx, ebx
0x1800933fc  jns     short loc_18009341D
0x1800933fe  xor     edx, edx; int
0x180093400  mov     rcx, rdi; this
0x180093403  call    ?Terminate@CThreadPool@@QEAAJH@Z; CThreadPool::Terminate(int)
0x180093408  jmp     short loc_18009341D
0x18009340a  mov     [rdi+40h], rax
0x18009340e  mov     qword ptr [rdi+48h], 0
0x180093416  mov     dword ptr [rdi+18h], 1
0x18009341d  mov     rdi, [rsp+28h+arg_8]
0x180093422  mov     eax, ebx
0x180093424  mov     rbx, [rsp+28h+arg_0]
0x180093429  add     rsp, 20h
0x18009342d  pop     r14
0x18009342f  retn
```
