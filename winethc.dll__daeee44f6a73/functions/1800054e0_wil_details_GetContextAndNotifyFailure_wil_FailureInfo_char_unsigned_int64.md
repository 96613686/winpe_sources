# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800054e0`
- end: `0x1800056f3`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `531`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800054e0`
- `0x180007c60`
- `0x180007d4c`
- `0x18000ae8c`
- `0x18000c3c0`
- `0x180014010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000550a`
- `KERNEL32!GetCurrentThreadId` at `0x1800055d1`
- `KERNEL32!GetCurrentThreadId` at `0x18000550a`
- `KERNEL32!GetCurrentThreadId` at `0x1800055d1`

## pseudocode

```c
void __fastcall wil::details::GetContextAndNotifyFailure(unsigned __int64 this, struct wil::FailureInfo *a2, char *a3)
{
  char v3; // bp
  __int64 v4; // rbx
  wil::details *v7; // rdi
  unsigned __int64 CurrentThreadId; // r9
  __int64 i; // rbx
  struct wil::details::ThreadFailureCallbackHolder *v10; // rbx
  char v11; // al
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
  volatile signed __int32 *v25; // rax

  *(_BYTE *)a2 = 0;
  v3 = 0;
  v4 = wil::details::g_pThreadFailureCallbacks;
  v7 = (wil::details *)this;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    this = 10 * ((CurrentThreadId >> 2) / 0xA);
    for ( i = *(_QWORD *)(v4 + 8 * ((CurrentThreadId >> 2) % 0xA)); i; i = *(_QWORD *)(i + 8) )
    {
      if ( *(_DWORD *)i == (_DWORD)CurrentThreadId )
      {
        i += 16;
        break;
      }
    }
    if ( i && *(_QWORD *)i )
    {
      *(_BYTE *)a2 = 0;
      if ( wil::details::ThreadFailureCallbackHolder::GetThreadContext(
             v7,
             *(struct wil::details::ThreadFailureCallbackHolder **)i,
             (char *)a2,
             (unsigned __int64)a3) )
      {
        *((_QWORD *)v7 + 9) = a2;
      }
      v10 = *(struct wil::details::ThreadFailureCallbackHolder **)i;
      do
      {
        v11 = *((_BYTE *)v10 + 40);
        *((_BYTE *)v10 + 40) = 1;
        if ( !v11 )
        {
          v3 |= (***((__int64 (__fastcall ****)(_QWORD, wil::details *))v10 + 1))(*((_QWORD *)v10 + 1), v7);
          *((_BYTE *)v10 + 40) = 0;
        }
        v10 = (struct wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)v10 + 2);
      }
      while ( v10 );
    }
  }
  if ( wil::details::g_pfnTelemetryCallback )
  {
    if ( v3 || (*((_BYTE *)v7 + 4) & 2) != 0 )
      LOBYTE(this) = 1;
    else
      this = 0;
    wil::details::g_pfnTelemetryCallback(this, v7);
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
LABEL_36:
            v24 = ((unsigned int)*((unsigned __int16 *)v17 + 17) + 1) % *((unsigned __int16 *)v17 + 16);
            v25 = (volatile signed __int32 *)*((_QWORD *)v17 + 1);
            *((_WORD *)v17 + 17) = v24;
            wil::details_abi::ThreadLocalFailureInfo::Set(
              (wil::details_abi::ThreadLocalFailureInfo *)(v21 + 80LL * v24),
              v7,
              _InterlockedIncrement(v25));
          }
          else
          {
            while ( *(_DWORD *)(v22 + 4) <= *((_DWORD *)v17 + 4) || *(_DWORD *)(v22 + 8) != *((_DWORD *)v7 + 2) )
            {
              v22 += 80;
              if ( v22 == v23 )
                goto LABEL_36;
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
0x1800054e0  push    rbx
0x1800054e2  push    rbp
0x1800054e3  push    rsi
0x1800054e4  push    rdi
0x1800054e5  push    r14
0x1800054e7  sub     rsp, 20h
0x1800054eb  mov     byte ptr [rdx], 0
0x1800054ee  xor     bpl, bpl
0x1800054f1  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800054f8  mov     r14, r8
0x1800054fb  mov     rsi, rdx
0x1800054fe  mov     rdi, rcx
0x180005501  test    rbx, rbx
0x180005504  jz      loc_1800055A6
0x18000550a  call    cs:__imp_GetCurrentThreadId
0x180005511  nop     dword ptr [rax+rax+00h]
0x180005516  mov     r8d, eax
0x180005519  mov     r9d, eax
0x18000551c  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005526  shr     r8, 2
0x18000552a  mul     r8
0x18000552d  shr     rdx, 3
0x180005531  lea     rcx, [rdx+rdx*4]
0x180005535  add     rcx, rcx
0x180005538  sub     r8, rcx
0x18000553b  mov     rbx, [rbx+r8*8]
0x18000553f  jmp     short loc_18000554A
0x180005541  cmp     [rbx], r9d
0x180005544  jz      short loc_1800055C1
0x180005546  mov     rbx, [rbx+8]
0x18000554a  test    rbx, rbx
0x18000554d  jnz     short loc_180005541
0x18000554f  test    rbx, rbx
0x180005552  jz      short loc_1800055A6
0x180005554  cmp     qword ptr [rbx], 0
0x180005558  jz      short loc_1800055A6
0x18000555a  mov     [rsi], bpl
0x18000555d  mov     r9, r14; unsigned __int64
0x180005560  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180005563  mov     r8, rsi; char *
0x180005566  mov     rcx, rdi; struct wil::FailureInfo *
0x180005569  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000556e  test    al, al
0x180005570  jz      short loc_180005576
0x180005572  mov     [rdi+48h], rsi
0x180005576  mov     rbx, [rbx]
0x180005579  mov     al, [rbx+28h]
0x18000557c  mov     byte ptr [rbx+28h], 1
0x180005580  test    al, al
0x180005582  jnz     short loc_18000559D
0x180005584  mov     rcx, [rbx+8]
0x180005588  mov     rdx, rdi
0x18000558b  mov     rax, [rcx]
0x18000558e  mov     rax, [rax]
0x180005591  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005596  or      bpl, al
0x180005599  mov     byte ptr [rbx+28h], 0
0x18000559d  mov     rbx, [rbx+10h]
0x1800055a1  test    rbx, rbx
0x1800055a4  jnz     short loc_180005579
0x1800055a6  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800055ad  test    rax, rax
0x1800055b0  jz      short loc_1800055D1
0x1800055b2  test    bpl, bpl
0x1800055b5  jnz     short loc_1800055C7
0x1800055b7  test    byte ptr [rdi+4], 2
0x1800055bb  jnz     short loc_1800055C7
0x1800055bd  xor     ecx, ecx
0x1800055bf  jmp     short loc_1800055C9
0x1800055c1  add     rbx, 10h
0x1800055c5  jmp     short loc_18000554F
0x1800055c7  mov     cl, 1
0x1800055c9  mov     rdx, rdi
0x1800055cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055d1  call    cs:__imp_GetCurrentThreadId
0x1800055d8  nop     dword ptr [rax+rax+00h]
0x1800055dd  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800055e3  cmp     ecx, eax
0x1800055e5  jz      loc_1800056E7
0x1800055eb  mov     ecx, 1
0x1800055f0  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800055f8  inc     ecx; this
0x1800055fa  cmp     ecx, 4
0x1800055fd  jge     loc_1800056E0
0x180005603  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180005609  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18000560e  mov     rbx, rax
0x180005611  test    rax, rax
0x180005614  jz      loc_1800056D6
0x18000561a  cmp     qword ptr [rax+18h], 0
0x18000561f  mov     ebp, 50h ; 'P'
0x180005624  mov     esi, [rax+10h]
0x180005627  jnz     short loc_18000565E
0x180005629  test    esi, esi
0x18000562b  jz      short loc_18000565E
0x18000562d  mov     edx, 190h; dwBytes
0x180005632  lea     ecx, [rbp-48h]; dwFlags
0x180005635  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000563a  mov     [rbx+18h], rax
0x18000563e  test    rax, rax
0x180005641  jz      short loc_18000565E
0x180005643  mov     dword ptr [rbx+20h], 5
0x18000564a  lea     rcx, [rax+190h]
0x180005651  jmp     short loc_180005659
0x180005653  mov     [rax], bp
0x180005656  add     rax, rbp
0x180005659  cmp     rax, rcx
0x18000565c  jnz     short loc_180005653
0x18000565e  mov     r9, [rbx+18h]
0x180005662  test    r9, r9
0x180005665  jz      short loc_1800056D6
0x180005667  test    esi, esi
0x180005669  jz      short loc_18000569C
0x18000566b  movzx   eax, word ptr [rbx+20h]
0x18000566f  mov     rcx, r9
0x180005672  lea     rdx, [rax+rax*4]
0x180005676  shl     rdx, 4
0x18000567a  add     rdx, r9
0x18000567d  cmp     r9, rdx
0x180005680  jz      short loc_18000569C
0x180005682  mov     r8d, [rbx+10h]
0x180005686  cmp     [rcx+4], r8d
0x18000568a  jbe     short loc_180005694
0x18000568c  mov     eax, [rdi+8]
0x18000568f  cmp     [rcx+8], eax
0x180005692  jz      short loc_1800056D6
0x180005694  add     rcx, rbp
0x180005697  cmp     rcx, rdx
0x18000569a  jnz     short loc_180005686
0x18000569c  movzx   eax, word ptr [rbx+22h]
0x1800056a0  xor     edx, edx
0x1800056a2  movzx   ecx, word ptr [rbx+20h]
0x1800056a6  inc     eax
0x1800056a8  div     ecx
0x1800056aa  mov     rax, [rbx+8]
0x1800056ae  mov     r8d, 1
0x1800056b4  mov     [rbx+22h], dx
0x1800056b8  lock xadd [rax], r8d
0x1800056bd  movzx   eax, dx
0x1800056c0  inc     r8d; unsigned int
0x1800056c3  mov     rdx, rdi; struct wil::FailureInfo *
0x1800056c6  lea     rcx, [rax+rax*4]
0x1800056ca  shl     rcx, 4
0x1800056ce  add     rcx, r9; this
0x1800056d1  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x1800056d6  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800056e0  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800056e7  add     rsp, 20h
0x1800056eb  pop     r14
0x1800056ed  pop     rdi
0x1800056ee  pop     rsi
0x1800056ef  pop     rbp
0x1800056f0  pop     rbx
0x1800056f1  retn
```
