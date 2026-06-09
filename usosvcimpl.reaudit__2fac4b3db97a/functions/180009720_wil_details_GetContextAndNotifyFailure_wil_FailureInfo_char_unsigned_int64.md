# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180009720`
- end: `0x18000992a`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `522`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180007b70`
- `0x1800092bc`
- `0x18000955c`
- `0x18000961c`
- `0x180009720`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009752`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009807`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009752`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009807`

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
0x180009720  mov     [rsp+arg_18], rbx
0x180009725  push    rbp
0x180009726  push    rsi
0x180009727  push    rdi
0x180009728  push    r14
0x18000972a  push    r15
0x18000972c  sub     rsp, 20h
0x180009730  mov     r14, r8
0x180009733  mov     rsi, rdx
0x180009736  mov     rdi, rcx
0x180009739  xor     r15d, r15d
0x18000973c  mov     [rdx], r15b
0x18000973f  mov     bpl, r15b
0x180009742  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180009749  test    rbx, rbx
0x18000974c  jz      loc_1800097DB
0x180009752  call    cs:__imp_GetCurrentThreadId
0x180009758  mov     r9d, eax
0x18000975b  mov     r8d, eax
0x18000975e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180009768  mul     r9
0x18000976b  shr     rdx, 3
0x18000976f  lea     rcx, [rdx+rdx*4]
0x180009773  add     rcx, rcx
0x180009776  sub     r8, rcx
0x180009779  mov     rbx, [rbx+r8*8]
0x18000977d  jmp     short loc_18000978C
0x18000977f  cmp     [rbx], r9d
0x180009782  jz      loc_180009881
0x180009788  mov     rbx, [rbx+8]
0x18000978c  test    rbx, rbx
0x18000978f  jnz     short loc_18000977F
0x180009791  mov     rbx, r15
0x180009794  test    rbx, rbx
0x180009797  jz      short loc_1800097DB
0x180009799  cmp     [rbx], r15
0x18000979c  jz      short loc_1800097DB
0x18000979e  mov     [rsi], r15b
0x1800097a1  mov     r9, r14; unsigned __int64
0x1800097a4  mov     r8, rsi; char *
0x1800097a7  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1800097aa  mov     rcx, rdi; struct wil::FailureInfo *
0x1800097ad  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800097b2  test    al, al
0x1800097b4  jz      short loc_1800097BA
0x1800097b6  mov     [rdi+48h], rsi
0x1800097ba  mov     rbx, [rbx]
0x1800097bd  mov     rcx, [rbx+8]
0x1800097c1  mov     rax, [rcx]
0x1800097c4  mov     rdx, rdi
0x1800097c7  mov     rax, [rax]
0x1800097ca  call    _guard_dispatch_icall
0x1800097cf  or      bpl, al
0x1800097d2  mov     rbx, [rbx+10h]
0x1800097d6  test    rbx, rbx
0x1800097d9  jnz     short loc_1800097BD
0x1800097db  mov     r14d, 1
0x1800097e1  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800097e8  test    rax, rax
0x1800097eb  jz      short loc_180009807
0x1800097ed  test    bpl, bpl
0x1800097f0  jnz     short loc_1800097FB
0x1800097f2  test    byte ptr [rdi+4], 2
0x1800097f6  mov     cl, r15b
0x1800097f9  jz      short loc_1800097FE
0x1800097fb  mov     cl, r14b
0x1800097fe  mov     rdx, rdi
0x180009801  call    _guard_dispatch_icall
0x180009806  nop
0x180009807  call    cs:__imp_GetCurrentThreadId
0x18000980d  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180009813  cmp     ecx, eax
0x180009815  jz      loc_180009919
0x18000981b  mov     ecx, r14d
0x18000981e  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180009826  add     ecx, r14d; this
0x180009829  cmp     ecx, 4
0x18000982c  jge     loc_180009912
0x180009832  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180009838  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18000983d  mov     rbx, rax
0x180009840  test    rax, rax
0x180009843  jz      loc_18000990B
0x180009849  mov     esi, [rax+10h]
0x18000984c  mov     ebp, 50h ; 'P'
0x180009851  cmp     [rax+18h], r15
0x180009855  jnz     short loc_180009895
0x180009857  test    esi, esi
0x180009859  jz      short loc_180009895
0x18000985b  mov     edx, 190h; dwBytes
0x180009860  lea     ecx, [rbp-48h]; dwFlags
0x180009863  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180009868  mov     [rbx+18h], rax
0x18000986c  test    rax, rax
0x18000986f  jz      short loc_180009895
0x180009871  mov     dword ptr [rbx+20h], 5
0x180009878  lea     rcx, [rax+190h]
0x18000987f  jmp     short loc_180009890
0x180009881  add     rbx, 10h
0x180009885  jmp     loc_180009794
0x18000988a  mov     [rax], bp
0x18000988d  add     rax, rbp
0x180009890  cmp     rax, rcx
0x180009893  jnz     short loc_18000988A
0x180009895  mov     r9, [rbx+18h]
0x180009899  test    r9, r9
0x18000989c  jz      short loc_18000990B
0x18000989e  test    esi, esi
0x1800098a0  jz      short loc_1800098D3
0x1800098a2  mov     rcx, r9
0x1800098a5  movzx   eax, word ptr [rbx+20h]
0x1800098a9  lea     rdx, [rax+rax*4]
0x1800098ad  shl     rdx, 4
0x1800098b1  add     rdx, r9
0x1800098b4  cmp     r9, rdx
0x1800098b7  jz      short loc_1800098D3
0x1800098b9  mov     r8d, [rbx+10h]
0x1800098bd  cmp     [rcx+4], r8d
0x1800098c1  jbe     short loc_1800098CB
0x1800098c3  mov     eax, [rdi+8]
0x1800098c6  cmp     [rcx+8], eax
0x1800098c9  jz      short loc_18000990B
0x1800098cb  add     rcx, rbp
0x1800098ce  cmp     rcx, rdx
0x1800098d1  jnz     short loc_1800098BD
0x1800098d3  movzx   eax, word ptr [rbx+22h]
0x1800098d7  add     eax, r14d
0x1800098da  movzx   ecx, word ptr [rbx+20h]
0x1800098de  xor     edx, edx
0x1800098e0  div     ecx
0x1800098e2  mov     [rbx+22h], dx
0x1800098e6  mov     rax, [rbx+8]
0x1800098ea  mov     r8d, r14d
0x1800098ed  lock xadd [rax], r8d
0x1800098f2  add     r8d, r14d; unsigned int
0x1800098f5  movzx   eax, dx
0x1800098f8  lea     rcx, [rax+rax*4]
0x1800098fc  shl     rcx, 4
0x180009900  add     rcx, r9; this
0x180009903  mov     rdx, rdi; struct wil::FailureInfo *
0x180009906  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000990b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, r15d; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180009912  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180009919  mov     rbx, [rsp+48h+arg_18]
0x18000991e  add     rsp, 20h
0x180009922  pop     r15
0x180009924  pop     r14
0x180009926  pop     rdi
0x180009927  pop     rsi
0x180009928  pop     rbp
0x180009929  retn
```
