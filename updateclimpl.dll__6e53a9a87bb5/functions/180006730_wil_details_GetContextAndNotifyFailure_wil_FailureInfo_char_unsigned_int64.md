# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180006730`
- end: `0x18000693a`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `522`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180003584`
- `0x1800062c8`
- `0x180006568`
- `0x180006628`
- `0x180006730`
- `0x1800148e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006762`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006817`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006762`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006817`

## pseudocode

```c
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
0x180006730  mov     [rsp+arg_18], rbx
0x180006735  push    rbp
0x180006736  push    rsi
0x180006737  push    rdi
0x180006738  push    r14
0x18000673a  push    r15
0x18000673c  sub     rsp, 20h
0x180006740  mov     r14, r8
0x180006743  mov     rsi, rdx
0x180006746  mov     rdi, rcx
0x180006749  xor     r15d, r15d
0x18000674c  mov     [rdx], r15b
0x18000674f  mov     bpl, r15b
0x180006752  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180006759  test    rbx, rbx
0x18000675c  jz      loc_1800067EB
0x180006762  call    cs:__imp_GetCurrentThreadId
0x180006768  mov     r9d, eax
0x18000676b  mov     r8d, eax
0x18000676e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180006778  mul     r9
0x18000677b  shr     rdx, 3
0x18000677f  lea     rcx, [rdx+rdx*4]
0x180006783  add     rcx, rcx
0x180006786  sub     r8, rcx
0x180006789  mov     rbx, [rbx+r8*8]
0x18000678d  jmp     short loc_18000679C
0x18000678f  cmp     [rbx], r9d
0x180006792  jz      loc_180006891
0x180006798  mov     rbx, [rbx+8]
0x18000679c  test    rbx, rbx
0x18000679f  jnz     short loc_18000678F
0x1800067a1  mov     rbx, r15
0x1800067a4  test    rbx, rbx
0x1800067a7  jz      short loc_1800067EB
0x1800067a9  cmp     [rbx], r15
0x1800067ac  jz      short loc_1800067EB
0x1800067ae  mov     [rsi], r15b
0x1800067b1  mov     r9, r14; unsigned __int64
0x1800067b4  mov     r8, rsi; char *
0x1800067b7  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1800067ba  mov     rcx, rdi; struct wil::FailureInfo *
0x1800067bd  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800067c2  test    al, al
0x1800067c4  jz      short loc_1800067CA
0x1800067c6  mov     [rdi+48h], rsi
0x1800067ca  mov     rbx, [rbx]
0x1800067cd  mov     rcx, [rbx+8]
0x1800067d1  mov     rax, [rcx]
0x1800067d4  mov     rdx, rdi
0x1800067d7  mov     rax, [rax]
0x1800067da  call    _guard_dispatch_icall
0x1800067df  or      bpl, al
0x1800067e2  mov     rbx, [rbx+10h]
0x1800067e6  test    rbx, rbx
0x1800067e9  jnz     short loc_1800067CD
0x1800067eb  mov     r14d, 1
0x1800067f1  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800067f8  test    rax, rax
0x1800067fb  jz      short loc_180006817
0x1800067fd  test    bpl, bpl
0x180006800  jnz     short loc_18000680B
0x180006802  test    byte ptr [rdi+4], 2
0x180006806  mov     cl, r15b
0x180006809  jz      short loc_18000680E
0x18000680b  mov     cl, r14b
0x18000680e  mov     rdx, rdi
0x180006811  call    _guard_dispatch_icall
0x180006816  nop
0x180006817  call    cs:__imp_GetCurrentThreadId
0x18000681d  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180006823  cmp     ecx, eax
0x180006825  jz      loc_180006929
0x18000682b  mov     ecx, r14d
0x18000682e  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180006836  add     ecx, r14d; this
0x180006839  cmp     ecx, 4
0x18000683c  jge     loc_180006922
0x180006842  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180006848  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18000684d  mov     rbx, rax
0x180006850  test    rax, rax
0x180006853  jz      loc_18000691B
0x180006859  mov     esi, [rax+10h]
0x18000685c  mov     ebp, 50h ; 'P'
0x180006861  cmp     [rax+18h], r15
0x180006865  jnz     short loc_1800068A5
0x180006867  test    esi, esi
0x180006869  jz      short loc_1800068A5
0x18000686b  mov     edx, 190h; dwBytes
0x180006870  lea     ecx, [rbp-48h]; dwFlags
0x180006873  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006878  mov     [rbx+18h], rax
0x18000687c  test    rax, rax
0x18000687f  jz      short loc_1800068A5
0x180006881  mov     dword ptr [rbx+20h], 5
0x180006888  lea     rcx, [rax+190h]
0x18000688f  jmp     short loc_1800068A0
0x180006891  add     rbx, 10h
0x180006895  jmp     loc_1800067A4
0x18000689a  mov     [rax], bp
0x18000689d  add     rax, rbp
0x1800068a0  cmp     rax, rcx
0x1800068a3  jnz     short loc_18000689A
0x1800068a5  mov     r9, [rbx+18h]
0x1800068a9  test    r9, r9
0x1800068ac  jz      short loc_18000691B
0x1800068ae  test    esi, esi
0x1800068b0  jz      short loc_1800068E3
0x1800068b2  mov     rcx, r9
0x1800068b5  movzx   eax, word ptr [rbx+20h]
0x1800068b9  lea     rdx, [rax+rax*4]
0x1800068bd  shl     rdx, 4
0x1800068c1  add     rdx, r9
0x1800068c4  cmp     r9, rdx
0x1800068c7  jz      short loc_1800068E3
0x1800068c9  mov     r8d, [rbx+10h]
0x1800068cd  cmp     [rcx+4], r8d
0x1800068d1  jbe     short loc_1800068DB
0x1800068d3  mov     eax, [rdi+8]
0x1800068d6  cmp     [rcx+8], eax
0x1800068d9  jz      short loc_18000691B
0x1800068db  add     rcx, rbp
0x1800068de  cmp     rcx, rdx
0x1800068e1  jnz     short loc_1800068CD
0x1800068e3  movzx   eax, word ptr [rbx+22h]
0x1800068e7  add     eax, r14d
0x1800068ea  movzx   ecx, word ptr [rbx+20h]
0x1800068ee  xor     edx, edx
0x1800068f0  div     ecx
0x1800068f2  mov     [rbx+22h], dx
0x1800068f6  mov     rax, [rbx+8]
0x1800068fa  mov     r8d, r14d
0x1800068fd  lock xadd [rax], r8d
0x180006902  add     r8d, r14d; unsigned int
0x180006905  movzx   eax, dx
0x180006908  lea     rcx, [rax+rax*4]
0x18000690c  shl     rcx, 4
0x180006910  add     rcx, r9; this
0x180006913  mov     rdx, rdi; struct wil::FailureInfo *
0x180006916  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000691b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, r15d; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180006922  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180006929  mov     rbx, [rsp+48h+arg_18]
0x18000692e  add     rsp, 20h
0x180006932  pop     r15
0x180006934  pop     r14
0x180006936  pop     rdi
0x180006937  pop     rsi
0x180006938  pop     rbp
0x180006939  retn
```
