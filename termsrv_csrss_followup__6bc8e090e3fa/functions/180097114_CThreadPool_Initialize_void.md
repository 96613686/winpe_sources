# CThreadPool::Initialize(void)

- ea: `0x180097114`
- end: `0x1800973b5`
- name: `?Initialize@CThreadPool@@QEAAJXZ`
- size: `673`
- prototype: `__int64 __fastcall(CThreadPool *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180043cc0`
- `0x180044ddc`

## callees

- `0x180097114`
- `0x1800974e8`
- `0x1800976e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180097144`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180097144`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180097159`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180097159`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097169`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800971ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009726e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097336`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097169`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800971ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009726e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097336`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180097321`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180097321`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18009725e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18009725e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x180097244`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x180097244`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x1800971d5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x1800971d5`

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
0x180097114  mov     [rsp+arg_0], rbx
0x180097119  mov     [rsp+arg_8], rdi
0x18009711e  push    r14
0x180097120  sub     rsp, 20h
0x180097124  mov     rdi, rcx
0x180097127  xor     ebx, ebx
0x180097129  mov     r14d, 80070000h
0x18009712f  mov     [rcx+10h], ebx
0x180097132  mov     rcx, [rcx+8]; hEvent
0x180097136  test    rcx, rcx
0x180097139  jnz     short loc_180097159
0x18009713b  xor     r9d, r9d; lpName
0x18009713e  lea     edx, [rbx+1]; bManualReset
0x180097141  xor     r8d, r8d; bInitialState
0x180097144  call    cs:__imp_CreateEventW
0x18009714b  nop     dword ptr [rax+rax+00h]
0x180097150  mov     [rdi+8], rax
0x180097154  test    rax, rax
0x180097157  jmp     short loc_180097167
0x180097159  call    cs:__imp_ResetEvent
0x180097160  nop     dword ptr [rax+rax+00h]
0x180097165  test    eax, eax
0x180097167  jnz     short loc_180097181
0x180097169  call    cs:__imp_GetLastError
0x180097170  nop     dword ptr [rax+rax+00h]
0x180097175  mov     ebx, eax
0x180097177  test    eax, eax
0x180097179  jle     short loc_180097181
0x18009717b  movzx   ebx, ax
0x18009717e  or      ebx, r14d
0x180097181  test    ebx, ebx
0x180097183  jns     short loc_1800971C6
0x180097185  mov     rcx, cs:WPP_GLOBAL_Control
0x18009718c  lea     rax, WPP_GLOBAL_Control
0x180097193  cmp     rcx, rax
0x180097196  jz      loc_180097382
0x18009719c  test    byte ptr [rcx+1Ch], 1
0x1800971a0  jz      loc_180097382
0x1800971a6  cmp     byte ptr [rcx+19h], 2
0x1800971aa  jb      loc_180097382
0x1800971b0  mov     rcx, [rcx+10h]
0x1800971b4  mov     edx, 0Ch
0x1800971b9  mov     r9d, ebx
0x1800971bc  call    WPP_SF_d
0x1800971c1  jmp     loc_180097382
0x1800971c6  cmp     dword ptr [rdi+98h], 0
0x1800971cd  jz      loc_1800972BB
0x1800971d3  xor     ecx, ecx; reserved
0x1800971d5  call    cs:__imp_CreateThreadpool
0x1800971dc  nop     dword ptr [rax+rax+00h]
0x1800971e1  mov     [rdi+20h], rax
0x1800971e5  test    rax, rax
0x1800971e8  jnz     short loc_180097237
0x1800971ea  call    cs:__imp_GetLastError
0x1800971f1  nop     dword ptr [rax+rax+00h]
0x1800971f6  mov     ebx, eax
0x1800971f8  test    eax, eax
0x1800971fa  jle     short loc_180097202
0x1800971fc  movzx   ebx, ax
0x1800971ff  or      ebx, r14d
0x180097202  mov     rcx, cs:WPP_GLOBAL_Control
0x180097209  lea     rax, WPP_GLOBAL_Control
0x180097210  cmp     rcx, rax
0x180097213  jz      loc_18009737E
0x180097219  test    byte ptr [rcx+1Ch], 1
0x18009721d  jz      loc_18009737E
0x180097223  cmp     byte ptr [rcx+19h], 2
0x180097227  jb      loc_18009737E
0x18009722d  mov     edx, 0Dh
0x180097232  jmp     loc_180097372
0x180097237  mov     edx, [rdi+0A0h]; cthrdMost
0x18009723d  test    edx, edx
0x18009723f  jz      short loc_180097250
0x180097241  mov     rcx, rax; ptpp
0x180097244  call    cs:__imp_SetThreadpoolThreadMaximum
0x18009724b  nop     dword ptr [rax+rax+00h]
0x180097250  mov     edx, [rdi+9Ch]; cthrdMic
0x180097256  test    edx, edx
0x180097258  jz      short loc_1800972BB
0x18009725a  mov     rcx, [rdi+20h]; ptpp
0x18009725e  call    cs:__imp_SetThreadpoolThreadMinimum
0x180097265  nop     dword ptr [rax+rax+00h]
0x18009726a  test    eax, eax
0x18009726c  jnz     short loc_1800972BB
0x18009726e  call    cs:__imp_GetLastError
0x180097275  nop     dword ptr [rax+rax+00h]
0x18009727a  mov     ebx, eax
0x18009727c  test    eax, eax
0x18009727e  jle     short loc_180097286
0x180097280  movzx   ebx, ax
0x180097283  or      ebx, r14d
0x180097286  mov     rcx, cs:WPP_GLOBAL_Control
0x18009728d  lea     rax, WPP_GLOBAL_Control
0x180097294  cmp     rcx, rax
0x180097297  jz      loc_18009737E
0x18009729d  test    byte ptr [rcx+1Ch], 1
0x1800972a1  jz      loc_18009737E
0x1800972a7  cmp     byte ptr [rcx+19h], 2
0x1800972ab  jb      loc_18009737E
0x1800972b1  mov     edx, 0Eh
0x1800972b6  jmp     loc_180097372
0x1800972bb  mov     dword ptr [rdi+30h], 3
0x1800972c2  mov     qword ptr [rdi+38h], 0
0x1800972ca  mov     qword ptr [rdi+40h], 0
0x1800972d2  mov     qword ptr [rdi+48h], 0
0x1800972da  mov     qword ptr [rdi+50h], 0
0x1800972e2  mov     qword ptr [rdi+58h], 0
0x1800972ea  mov     qword ptr [rdi+60h], 0
0x1800972f2  mov     dword ptr [rdi+68h], 0
0x1800972f9  mov     dword ptr [rdi+6Ch], 1
0x180097300  mov     dword ptr [rdi+70h], 48h ; 'H'
0x180097307  mov     rax, [rdi+20h]
0x18009730b  test    rax, rax
0x18009730e  jz      short loc_180097314
0x180097310  mov     [rdi+38h], rax
0x180097314  cmp     dword ptr [rdi+94h], 0
0x18009731b  jz      short loc_180097321
0x18009731d  or      dword ptr [rdi+68h], 1
0x180097321  call    cs:__imp_CreateThreadpoolCleanupGroup
0x180097328  nop     dword ptr [rax+rax+00h]
0x18009732d  mov     [rdi+28h], rax
0x180097331  test    rax, rax
0x180097334  jnz     short loc_18009738E
0x180097336  call    cs:__imp_GetLastError
0x18009733d  nop     dword ptr [rax+rax+00h]
0x180097342  mov     ebx, eax
0x180097344  test    eax, eax
0x180097346  jle     short loc_18009734E
0x180097348  movzx   ebx, ax
0x18009734b  or      ebx, r14d
0x18009734e  mov     rcx, cs:WPP_GLOBAL_Control
0x180097355  lea     rax, WPP_GLOBAL_Control
0x18009735c  cmp     rcx, rax
0x18009735f  jz      short loc_18009737E
0x180097361  test    byte ptr [rcx+1Ch], 1
0x180097365  jz      short loc_18009737E
0x180097367  cmp     byte ptr [rcx+19h], 2
0x18009736b  jb      short loc_18009737E
0x18009736d  mov     edx, 0Fh
0x180097372  mov     rcx, [rcx+10h]
0x180097376  mov     r9d, ebx
0x180097379  call    WPP_SF_d
0x18009737e  test    ebx, ebx
0x180097380  jns     short loc_1800973A1
0x180097382  xor     edx, edx; int
0x180097384  mov     rcx, rdi; this
0x180097387  call    ?Terminate@CThreadPool@@QEAAJH@Z; CThreadPool::Terminate(int)
0x18009738c  jmp     short loc_1800973A1
0x18009738e  mov     [rdi+40h], rax
0x180097392  mov     qword ptr [rdi+48h], 0
0x18009739a  mov     dword ptr [rdi+18h], 1
0x1800973a1  mov     rdi, [rsp+28h+arg_8]
0x1800973a6  mov     eax, ebx
0x1800973a8  mov     rbx, [rsp+28h+arg_0]
0x1800973ad  add     rsp, 20h
0x1800973b1  pop     r14
0x1800973b3  retn
```
