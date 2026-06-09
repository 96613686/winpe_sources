# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x140004710`
- end: `0x14000491a`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `522`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140002ea8`
- `0x1400042b0`
- `0x140004550`
- `0x140004610`
- `0x140004710`
- `0x1400206e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004742`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400047f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004742`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400047f7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::GetContextAndNotifyFailure(unsigned __int64 this, struct wil::FailureInfo *a2, char *a3)
{
  wil::details *v5; // rdi
  char v6; // bp
  __int64 v7; // rbx
  unsigned __int64 CurrentThreadId; // r9
  __int64 i; // rbx
  struct wil::details::ThreadFailureCallbackHolder **v10; // rbx
  struct wil::details::ThreadFailureCallbackHolder *v11; // rbx
  DWORD v12; // eax
  bool v13; // dl
  wil::details_abi *v14; // rcx
  struct wil::details_abi::ThreadLocalData *ThreadLocalDataCache; // rax
  unsigned __int64 v16; // r8
  struct wil::details_abi::ThreadLocalData *v17; // rbx
  int v18; // esi
  _WORD *v19; // rax
  _WORD *v20; // rcx
  __int64 v21; // r9
  __int64 v22; // rcx
  __int64 v23; // rdx
  unsigned __int16 v24; // dx

  v5 = (wil::details *)this;
  *(_BYTE *)a2 = 0;
  v6 = 0;
  v7 = wil::details::g_pThreadFailureCallbacks;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    this = 10 * (CurrentThreadId / 0xA);
    for ( i = *(_QWORD *)(v7 + 8 * (CurrentThreadId % 0xA)); ; i = *(_QWORD *)(i + 8) )
    {
      if ( !i )
      {
        v10 = 0;
        goto LABEL_7;
      }
      if ( *(_DWORD *)i == (_DWORD)CurrentThreadId )
        break;
    }
    v10 = (struct wil::details::ThreadFailureCallbackHolder **)(i + 16);
LABEL_7:
    if ( v10 && *v10 )
    {
      *(_BYTE *)a2 = 0;
      if ( wil::details::ThreadFailureCallbackHolder::GetThreadContext(v5, *v10, (char *)a2, (unsigned __int64)a3) )
        *((_QWORD *)v5 + 9) = a2;
      v11 = *v10;
      do
      {
        v6 |= (***((__int64 (__fastcall ****)(_QWORD, wil::details *))v11 + 1))(*((_QWORD *)v11 + 1), v5);
        v11 = (struct wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)v11 + 2);
      }
      while ( v11 );
    }
  }
  if ( wil::details::g_pfnTelemetryCallback )
  {
    if ( v6 || (LOBYTE(this) = 0, (*((_BYTE *)v5 + 4) & 2) != 0) )
      LOBYTE(this) = 1;
    wil::details::g_pfnTelemetryCallback(this, v5);
  }
  v12 = GetCurrentThreadId();
  if ( `wil::SetLastError'::`2'::lastThread != v12 )
  {
    v14 = (wil::details_abi *)(unsigned int)_InterlockedIncrement(&`wil::SetLastError'::`5'::depth);
    if ( (int)v14 < 4 )
    {
      `wil::SetLastError'::`2'::lastThread = v12;
      ThreadLocalDataCache = wil::details_abi::GetThreadLocalDataCache(v14, v13);
      v17 = ThreadLocalDataCache;
      if ( ThreadLocalDataCache )
      {
        v18 = *((_DWORD *)ThreadLocalDataCache + 4);
        if ( !*((_QWORD *)ThreadLocalDataCache + 3) )
        {
          if ( v18 )
          {
            v19 = wil::details::ProcessHeapAlloc(8u, 0x190u, v16);
            *((_QWORD *)v17 + 3) = v19;
            if ( v19 )
            {
              *((_DWORD *)v17 + 8) = 5;
              v20 = v19 + 200;
              while ( v19 != v20 )
              {
                *v19 = 80;
                v19 += 40;
              }
            }
          }
        }
        v21 = *((_QWORD *)v17 + 3);
        if ( v21 )
        {
          if ( !v18 || (v22 = *((_QWORD *)v17 + 3), v23 = v21 + 80LL * *((unsigned __int16 *)v17 + 16), v21 == v23) )
          {
LABEL_34:
            v24 = ((unsigned int)*((unsigned __int16 *)v17 + 17) + 1) % *((unsigned __int16 *)v17 + 16);
            *((_WORD *)v17 + 17) = v24;
            wil::details_abi::ThreadLocalFailureInfo::Set(
              (wil::details_abi::ThreadLocalFailureInfo *)(v21 + 80LL * v24),
              v5,
              _InterlockedIncrement(*((volatile signed __int32 **)v17 + 1)));
          }
          else
          {
            while ( *(_DWORD *)(v22 + 4) <= *((_DWORD *)v17 + 4) || *(_DWORD *)(v22 + 8) != *((_DWORD *)v5 + 2) )
            {
              v22 += 80;
              if ( v22 == v23 )
                goto LABEL_34;
            }
          }
        }
      }
      `wil::SetLastError'::`2'::lastThread = 0;
    }
    _InterlockedDecrement(&`wil::SetLastError'::`5'::depth);
  }
}

```

## disassembly

```asm
0x140004710  mov     [rsp+arg_18], rbx
0x140004715  push    rbp
0x140004716  push    rsi
0x140004717  push    rdi
0x140004718  push    r14
0x14000471a  push    r15
0x14000471c  sub     rsp, 20h
0x140004720  mov     r14, r8
0x140004723  mov     rsi, rdx
0x140004726  mov     rdi, rcx
0x140004729  xor     r15d, r15d
0x14000472c  mov     [rdx], r15b
0x14000472f  mov     bpl, r15b
0x140004732  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140004739  test    rbx, rbx
0x14000473c  jz      loc_1400047CB
0x140004742  call    cs:__imp_GetCurrentThreadId
0x140004748  mov     r9d, eax
0x14000474b  mov     r8d, eax
0x14000474e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140004758  mul     r9
0x14000475b  shr     rdx, 3
0x14000475f  lea     rcx, [rdx+rdx*4]
0x140004763  add     rcx, rcx
0x140004766  sub     r8, rcx
0x140004769  mov     rbx, [rbx+r8*8]
0x14000476d  jmp     short loc_14000477C
0x14000476f  cmp     [rbx], r9d
0x140004772  jz      loc_140004871
0x140004778  mov     rbx, [rbx+8]
0x14000477c  test    rbx, rbx
0x14000477f  jnz     short loc_14000476F
0x140004781  mov     rbx, r15
0x140004784  test    rbx, rbx
0x140004787  jz      short loc_1400047CB
0x140004789  cmp     [rbx], r15
0x14000478c  jz      short loc_1400047CB
0x14000478e  mov     [rsi], r15b
0x140004791  mov     r9, r14; unsigned __int64
0x140004794  mov     r8, rsi; char *
0x140004797  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x14000479a  mov     rcx, rdi; struct wil::FailureInfo *
0x14000479d  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1400047a2  test    al, al
0x1400047a4  jz      short loc_1400047AA
0x1400047a6  mov     [rdi+48h], rsi
0x1400047aa  mov     rbx, [rbx]
0x1400047ad  mov     rcx, [rbx+8]
0x1400047b1  mov     rax, [rcx]
0x1400047b4  mov     rdx, rdi
0x1400047b7  mov     rax, [rax]
0x1400047ba  call    _guard_dispatch_icall
0x1400047bf  or      bpl, al
0x1400047c2  mov     rbx, [rbx+10h]
0x1400047c6  test    rbx, rbx
0x1400047c9  jnz     short loc_1400047AD
0x1400047cb  mov     r14d, 1
0x1400047d1  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1400047d8  test    rax, rax
0x1400047db  jz      short loc_1400047F7
0x1400047dd  test    bpl, bpl
0x1400047e0  jnz     short loc_1400047EB
0x1400047e2  test    byte ptr [rdi+4], 2
0x1400047e6  mov     cl, r15b
0x1400047e9  jz      short loc_1400047EE
0x1400047eb  mov     cl, r14b
0x1400047ee  mov     rdx, rdi
0x1400047f1  call    _guard_dispatch_icall
0x1400047f6  nop
0x1400047f7  call    cs:__imp_GetCurrentThreadId
0x1400047fd  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140004803  cmp     ecx, eax
0x140004805  jz      loc_140004909
0x14000480b  mov     ecx, r14d
0x14000480e  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x140004816  add     ecx, r14d; this
0x140004819  cmp     ecx, 4
0x14000481c  jge     loc_140004902
0x140004822  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140004828  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x14000482d  mov     rbx, rax
0x140004830  test    rax, rax
0x140004833  jz      loc_1400048FB
0x140004839  mov     esi, [rax+10h]
0x14000483c  mov     ebp, 50h ; 'P'
0x140004841  cmp     [rax+18h], r15
0x140004845  jnz     short loc_140004885
0x140004847  test    esi, esi
0x140004849  jz      short loc_140004885
0x14000484b  mov     edx, 190h; dwBytes
0x140004850  lea     ecx, [rbp-48h]; dwFlags
0x140004853  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140004858  mov     [rbx+18h], rax
0x14000485c  test    rax, rax
0x14000485f  jz      short loc_140004885
0x140004861  mov     dword ptr [rbx+20h], 5
0x140004868  lea     rcx, [rax+190h]
0x14000486f  jmp     short loc_140004880
0x140004871  add     rbx, 10h
0x140004875  jmp     loc_140004784
0x14000487a  mov     [rax], bp
0x14000487d  add     rax, rbp
0x140004880  cmp     rax, rcx
0x140004883  jnz     short loc_14000487A
0x140004885  mov     r9, [rbx+18h]
0x140004889  test    r9, r9
0x14000488c  jz      short loc_1400048FB
0x14000488e  test    esi, esi
0x140004890  jz      short loc_1400048C3
0x140004892  mov     rcx, r9
0x140004895  movzx   eax, word ptr [rbx+20h]
0x140004899  lea     rdx, [rax+rax*4]
0x14000489d  shl     rdx, 4
0x1400048a1  add     rdx, r9
0x1400048a4  cmp     r9, rdx
0x1400048a7  jz      short loc_1400048C3
0x1400048a9  mov     r8d, [rbx+10h]
0x1400048ad  cmp     [rcx+4], r8d
0x1400048b1  jbe     short loc_1400048BB
0x1400048b3  mov     eax, [rdi+8]
0x1400048b6  cmp     [rcx+8], eax
0x1400048b9  jz      short loc_1400048FB
0x1400048bb  add     rcx, rbp
0x1400048be  cmp     rcx, rdx
0x1400048c1  jnz     short loc_1400048AD
0x1400048c3  movzx   eax, word ptr [rbx+22h]
0x1400048c7  add     eax, r14d
0x1400048ca  movzx   ecx, word ptr [rbx+20h]
0x1400048ce  xor     edx, edx
0x1400048d0  div     ecx
0x1400048d2  mov     [rbx+22h], dx
0x1400048d6  mov     rax, [rbx+8]
0x1400048da  mov     r8d, r14d
0x1400048dd  lock xadd [rax], r8d
0x1400048e2  add     r8d, r14d; unsigned int
0x1400048e5  movzx   eax, dx
0x1400048e8  lea     rcx, [rax+rax*4]
0x1400048ec  shl     rcx, 4
0x1400048f0  add     rcx, r9; this
0x1400048f3  mov     rdx, rdi; struct wil::FailureInfo *
0x1400048f6  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x1400048fb  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, r15d; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140004902  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x140004909  mov     rbx, [rsp+48h+arg_18]
0x14000490e  add     rsp, 20h
0x140004912  pop     r15
0x140004914  pop     r14
0x140004916  pop     rdi
0x140004917  pop     rsi
0x140004918  pop     rbp
0x140004919  retn
```
