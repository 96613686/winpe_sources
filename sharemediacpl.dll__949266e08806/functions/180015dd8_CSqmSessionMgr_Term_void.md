# CSqmSessionMgr::Term(void)

- ea: `0x180015dd8`
- end: `0x180016006`
- name: `?Term@CSqmSessionMgr@@QEAAXXZ`
- size: `558`
- prototype: `void __fastcall(CSqmSessionMgr *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180007e5c`

## callees

- `0x180001954`
- `0x180003888`
- `0x1800144c4`
- `0x18001458c`
- `0x180014aec`
- `0x180014fac`
- `0x180015d70`
- `0x180015dd8`
- `0x180016108`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180015f85`
- `KERNEL32!LeaveCriticalSection` at `0x180015f85`
- `KERNEL32!EnterCriticalSection` at `0x180015dec`
- `KERNEL32!EnterCriticalSection` at `0x180015dec`
- `KERNEL32!SetLastError` at `0x180015feb`
- `KERNEL32!SetLastError` at `0x180015ff3`
- `KERNEL32!SetLastError` at `0x180015feb`
- `KERNEL32!SetLastError` at `0x180015ff3`
- `KERNEL32!DeleteTimerQueueEx` at `0x180015f97`
- `KERNEL32!DeleteTimerQueueEx` at `0x180015f97`
- `KERNEL32!GetLastError` at `0x180015fb3`
- `KERNEL32!GetLastError` at `0x180015fb3`

## pseudocode

```c
void __fastcall CSqmSessionMgr::Term(CSqmSessionMgr *this)
{
  __int64 v1; // rdx
  void *v2; // r14
  char v3; // bp
  unsigned int v4; // r8d
  __int64 v5; // r9
  __int64 v6; // rcx
  __int64 v7; // rbx
  __int64 v8; // rsi
  CSqmSession **v9; // rsi
  CSqmSession *v10; // rdi
  __int64 v11; // r8
  unsigned int v12; // eax
  CSqmSession *v13; // rax
  CSqmSession *v14; // rbx
  signed int LastError; // eax

  EnterCriticalSection(&_Sqm);
  v2 = 0;
  if ( --dword_18002A3E8 )
  {
    v3 = 0;
  }
  else
  {
    v3 = 1;
    if ( qword_18002A360 )
    {
      v2 = (void *)qword_18002A360;
      qword_18002A360 = 0;
    }
    if ( qword_18002A370 )
    {
      v4 = dword_18002A378;
      if ( dword_18002A378 )
      {
        v5 = qword_18002A368;
        v6 = 0;
        while ( 1 )
        {
          v7 = *(_QWORD *)(qword_18002A368 + 8 * v6);
          if ( v7 )
            break;
          v6 = (unsigned int)(v6 + 1);
          if ( (unsigned int)v6 >= dword_18002A378 )
            goto LABEL_26;
        }
        do
        {
          v8 = v7;
          if ( *(_QWORD *)(v7 + 16) )
          {
            v7 = *(_QWORD *)(v7 + 16);
          }
          else
          {
            LODWORD(v1) = *(_DWORD *)(v7 + 24) % v4;
            do
            {
              v1 = (unsigned int)(v1 + 1);
              v7 = 0;
              if ( (unsigned int)v1 >= v4 )
                break;
              v7 = *(_QWORD *)(v5 + 8 * v1);
            }
            while ( !v7 );
          }
          v9 = *(CSqmSession ***)(v8 + 8);
          if ( v9 )
          {
            v10 = v9[3];
            if ( v10 )
            {
              CSqmSession::StopTimer(v9[3], v1);
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              {
                WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v11, v10);
              }
              v12 = CSqmSession::EndSession(v10);
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_ea0197bca44a35f25f9875116037e43b_Traceguids, v12);
              }
              CSqmSession::~CSqmSession(v10);
              operator delete(v10);
            }
            operator delete(v9);
            v4 = dword_18002A378;
            v5 = qword_18002A368;
          }
        }
        while ( v7 );
      }
    }
LABEL_26:
    ATL::CAtlMap<unsigned long,CSqmSessionMgr::SqmSessionContext *,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<CSqmSessionMgr::SqmSessionContext *>>::RemoveAll(&qword_18002A368);
    while ( (_QWORD)xmmword_18002A3C0 )
    {
      v13 = (CSqmSession *)ATL::CAtlList<CSqmSession *,ATL::CElementTraits<CSqmSession *>>::RemoveHead(&xmmword_18002A3B0);
      v14 = v13;
      if ( v13 )
      {
        CSqmSession::~CSqmSession(v13);
        operator delete(v14);
      }
    }
  }
  LeaveCriticalSection(&_Sqm);
  if ( v2
    && !DeleteTimerQueueEx(v2, (HANDLE)0xFFFFFFFFFFFFFFFFLL)
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      &WPP_ea0197bca44a35f25f9875116037e43b_Traceguids,
      (unsigned int)LastError);
  }
  if ( v3 )
  {
    SetLastError(0);
    SetLastError(0);
  }
}

```

## disassembly

```asm
0x180015dd8  push    rbx
0x180015dda  push    rbp
0x180015ddb  push    rsi
0x180015ddc  push    rdi
0x180015ddd  push    r13
0x180015ddf  push    r14
0x180015de1  sub     rsp, 28h
0x180015de5  lea     rcx, ?_Sqm@@3VCSqmSessionMgr@@A; lpCriticalSection
0x180015dec  call    cs:__imp_EnterCriticalSection
0x180015df2  xor     r14d, r14d
0x180015df5  lea     r13, WPP_GLOBAL_Control
0x180015dfc  add     cs:dword_18002A3E8, 0FFFFFFFFh
0x180015e03  jnz     loc_180015F7B
0x180015e09  mov     rax, cs:qword_18002A360
0x180015e10  lea     ebp, [r14+1]
0x180015e14  test    rax, rax
0x180015e17  jz      short loc_180015E27
0x180015e19  mov     r14, rax
0x180015e1c  mov     cs:qword_18002A360, 0
0x180015e27  cmp     cs:qword_18002A370, 0
0x180015e2f  jz      loc_180015F3A
0x180015e35  mov     r8d, cs:dword_18002A378
0x180015e3c  test    r8d, r8d
0x180015e3f  jz      loc_180015F3A
0x180015e45  mov     r9, cs:qword_18002A368
0x180015e4c  xor     ecx, ecx
0x180015e4e  mov     rbx, [r9+rcx*8]
0x180015e52  test    rbx, rbx
0x180015e55  jnz     short loc_180015E63
0x180015e57  add     ecx, ebp
0x180015e59  cmp     ecx, r8d
0x180015e5c  jb      short loc_180015E4E
0x180015e5e  jmp     loc_180015F3A
0x180015e63  mov     rax, [rbx+10h]
0x180015e67  lea     rsi, [rbx]
0x180015e6a  test    rax, rax
0x180015e6d  jz      short loc_180015E74
0x180015e6f  mov     rbx, rax
0x180015e72  jmp     short loc_180015E8E
0x180015e74  mov     eax, [rbx+18h]
0x180015e77  xor     edx, edx
0x180015e79  div     r8d
0x180015e7c  add     edx, ebp; unsigned int
0x180015e7e  xor     ebx, ebx
0x180015e80  cmp     edx, r8d
0x180015e83  jnb     short loc_180015E8E
0x180015e85  mov     rbx, [r9+rdx*8]
0x180015e89  test    rbx, rbx
0x180015e8c  jz      short loc_180015E7C
0x180015e8e  mov     rsi, [rsi+8]
0x180015e92  test    rsi, rsi
0x180015e95  jz      loc_180015F31
0x180015e9b  mov     rdi, [rsi+18h]
0x180015e9f  test    rdi, rdi
0x180015ea2  jz      short loc_180015F16
0x180015ea4  mov     rcx, rdi; this
0x180015ea7  call    ?StopTimer@CSqmSession@@QEAAXK@Z; CSqmSession::StopTimer(ulong)
0x180015eac  mov     rcx, cs:WPP_GLOBAL_Control
0x180015eb3  cmp     rcx, r13
0x180015eb6  jz      short loc_180015ECF
0x180015eb8  test    byte ptr [rcx+1Ch], 8
0x180015ebc  jz      short loc_180015ECF
0x180015ebe  mov     rcx, [rcx+10h]
0x180015ec2  mov     edx, 0Bh
0x180015ec7  mov     r9, rdi
0x180015eca  call    WPP_SF_q
0x180015ecf  mov     rcx, rdi; this
0x180015ed2  call    ?EndSession@CSqmSession@@QEAAJXZ; CSqmSession::EndSession(void)
0x180015ed7  mov     rcx, cs:WPP_GLOBAL_Control
0x180015ede  cmp     rcx, r13
0x180015ee1  jz      short loc_180015F01
0x180015ee3  test    byte ptr [rcx+1Ch], 8
0x180015ee7  jz      short loc_180015F01
0x180015ee9  mov     rcx, [rcx+10h]
0x180015eed  lea     r8, WPP_ea0197bca44a35f25f9875116037e43b_Traceguids
0x180015ef4  mov     edx, 0Ch
0x180015ef9  mov     r9d, eax
0x180015efc  call    WPP_SF_d
0x180015f01  mov     rcx, rdi; this
0x180015f04  call    ??1CSqmSession@@QEAA@XZ; CSqmSession::~CSqmSession(void)
0x180015f09  mov     edx, 88h
0x180015f0e  mov     rcx, rdi; Block
0x180015f11  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180015f16  mov     edx, 28h ; '('
0x180015f1b  mov     rcx, rsi; Block
0x180015f1e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180015f23  mov     r8d, cs:dword_18002A378
0x180015f2a  mov     r9, cs:qword_18002A368
0x180015f31  test    rbx, rbx
0x180015f34  jnz     loc_180015E63
0x180015f3a  lea     rcx, qword_18002A368
0x180015f41  call    ?RemoveAll@?$CAtlMap@KPEAVSqmSessionContext@CSqmSessionMgr@@V?$CElementTraits@K@ATL@@V?$CElementTraits@PEAVSqmSessionContext@CSqmSessionMgr@@@4@@ATL@@QEAAXXZ; ATL::CAtlMap<ulong,CSqmSessionMgr::SqmSessionContext *,ATL::CElementTraits<ulong>,ATL::CElementTraits<CSqmSessionMgr::SqmSessionContext *>>::RemoveAll(void)
0x180015f46  cmp     qword ptr cs:xmmword_18002A3C0, 0
0x180015f4e  jz      short loc_180015F7E
0x180015f50  lea     rcx, xmmword_18002A3B0
0x180015f57  call    ?RemoveHead@?$CAtlList@PEAVCSqmSession@@V?$CElementTraits@PEAVCSqmSession@@@ATL@@@ATL@@QEAAPEAVCSqmSession@@XZ; ATL::CAtlList<CSqmSession *,ATL::CElementTraits<CSqmSession *>>::RemoveHead(void)
0x180015f5c  mov     rbx, rax
0x180015f5f  test    rax, rax
0x180015f62  jz      short loc_180015F46
0x180015f64  mov     rcx, rax; this
0x180015f67  call    ??1CSqmSession@@QEAA@XZ; CSqmSession::~CSqmSession(void)
0x180015f6c  mov     edx, 88h
0x180015f71  mov     rcx, rbx; Block
0x180015f74  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180015f79  jmp     short loc_180015F46
0x180015f7b  xor     bpl, bpl
0x180015f7e  lea     rcx, ?_Sqm@@3VCSqmSessionMgr@@A; lpCriticalSection
0x180015f85  call    cs:__imp_LeaveCriticalSection
0x180015f8b  test    r14, r14
0x180015f8e  jz      short loc_180015FE4
0x180015f90  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180015f94  mov     rcx, r14; TimerQueue
0x180015f97  call    cs:__imp_DeleteTimerQueueEx
0x180015f9d  test    eax, eax
0x180015f9f  jnz     short loc_180015FE4
0x180015fa1  mov     rax, cs:WPP_GLOBAL_Control
0x180015fa8  cmp     rax, r13
0x180015fab  jz      short loc_180015FE4
0x180015fad  test    byte ptr [rax+1Ch], 8
0x180015fb1  jz      short loc_180015FE4
0x180015fb3  call    cs:__imp_GetLastError
0x180015fb9  test    eax, eax
0x180015fbb  jle     short loc_180015FC5
0x180015fbd  movzx   eax, ax
0x180015fc0  or      eax, 80070000h
0x180015fc5  mov     rcx, cs:WPP_GLOBAL_Control
0x180015fcc  lea     r8, WPP_ea0197bca44a35f25f9875116037e43b_Traceguids
0x180015fd3  mov     edx, 0Eh
0x180015fd8  mov     r9d, eax
0x180015fdb  mov     rcx, [rcx+10h]
0x180015fdf  call    WPP_SF_d
0x180015fe4  test    bpl, bpl
0x180015fe7  jz      short loc_180015FF9
0x180015fe9  xor     ecx, ecx; dwErrCode
0x180015feb  call    cs:__imp_SetLastError
0x180015ff1  xor     ecx, ecx; dwErrCode
0x180015ff3  call    cs:__imp_SetLastError
0x180015ff9  add     rsp, 28h
0x180015ffd  pop     r14
0x180015fff  pop     r13
0x180016001  pop     rdi
0x180016002  pop     rsi
0x180016003  pop     rbp
0x180016004  pop     rbx
0x180016005  retn
```
