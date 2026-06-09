# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800078a0`
- end: `0x180007aa7`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800078a0`
- `0x180007fc8`
- `0x1800080ac`
- `0x180008aec`
- `0x18000a0d4`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800078ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000798c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800078ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000798c`

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

  v5 = (wil::details *)this;
  *(_BYTE *)a2 = 0;
  v6 = 0;
  v7 = wil::details::g_pThreadFailureCallbacks;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    this = 10 * ((CurrentThreadId >> 2) / 0xA);
    for ( i = *(_QWORD *)(v7 + 8 * ((CurrentThreadId >> 2) % 0xA)); i; i = *(_QWORD *)(i + 8) )
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
             v5,
             *(struct wil::details::ThreadFailureCallbackHolder **)i,
             (char *)a2,
             (unsigned __int64)a3) )
      {
        *((_QWORD *)v5 + 9) = a2;
      }
      v10 = *(struct wil::details::ThreadFailureCallbackHolder **)i;
      do
      {
        v11 = *((_BYTE *)v10 + 40);
        *((_BYTE *)v10 + 40) = 1;
        if ( !v11 )
        {
          v6 |= (***((__int64 (__fastcall ****)(_QWORD, wil::details *))v10 + 1))(*((_QWORD *)v10 + 1), v5);
          *((_BYTE *)v10 + 40) = 0;
        }
        v10 = (struct wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)v10 + 2);
      }
      while ( v10 );
    }
  }
  if ( wil::details::g_pfnTelemetryCallback )
  {
    if ( v6 || (*((_BYTE *)v5 + 4) & 2) != 0 )
      LOBYTE(this) = 1;
    else
      this = 0;
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
LABEL_36:
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
0x1800078a0  push    rbx
0x1800078a2  push    rbp
0x1800078a3  push    rsi
0x1800078a4  push    rdi
0x1800078a5  push    r14
0x1800078a7  sub     rsp, 20h
0x1800078ab  mov     r14, r8
0x1800078ae  mov     rsi, rdx
0x1800078b1  mov     rdi, rcx
0x1800078b4  mov     byte ptr [rdx], 0
0x1800078b7  xor     bpl, bpl
0x1800078ba  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800078c1  test    rbx, rbx
0x1800078c4  jz      loc_180007960
0x1800078ca  call    cs:__imp_GetCurrentThreadId
0x1800078d0  mov     r9d, eax
0x1800078d3  mov     r8d, eax
0x1800078d6  shr     r8, 2
0x1800078da  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800078e4  mul     r8
0x1800078e7  shr     rdx, 3
0x1800078eb  lea     rcx, [rdx+rdx*4]
0x1800078ef  add     rcx, rcx
0x1800078f2  sub     r8, rcx
0x1800078f5  mov     rbx, [rbx+r8*8]
0x1800078f9  jmp     short loc_180007904
0x1800078fb  cmp     [rbx], r9d
0x1800078fe  jz      short loc_18000797B
0x180007900  mov     rbx, [rbx+8]
0x180007904  test    rbx, rbx
0x180007907  jnz     short loc_1800078FB
0x180007909  test    rbx, rbx
0x18000790c  jz      short loc_180007960
0x18000790e  cmp     qword ptr [rbx], 0
0x180007912  jz      short loc_180007960
0x180007914  mov     [rsi], bpl
0x180007917  mov     r9, r14; unsigned __int64
0x18000791a  mov     r8, rsi; char *
0x18000791d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180007920  mov     rcx, rdi; struct wil::FailureInfo *
0x180007923  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180007928  test    al, al
0x18000792a  jz      short loc_180007930
0x18000792c  mov     [rdi+48h], rsi
0x180007930  mov     rbx, [rbx]
0x180007933  mov     al, [rbx+28h]
0x180007936  mov     byte ptr [rbx+28h], 1
0x18000793a  test    al, al
0x18000793c  jnz     short loc_180007957
0x18000793e  mov     rcx, [rbx+8]
0x180007942  mov     rax, [rcx]
0x180007945  mov     rdx, rdi
0x180007948  mov     rax, [rax]
0x18000794b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007950  or      bpl, al
0x180007953  mov     byte ptr [rbx+28h], 0
0x180007957  mov     rbx, [rbx+10h]
0x18000795b  test    rbx, rbx
0x18000795e  jnz     short loc_180007933
0x180007960  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180007967  test    rax, rax
0x18000796a  jz      short loc_18000798C
0x18000796c  test    bpl, bpl
0x18000796f  jnz     short loc_180007981
0x180007971  test    byte ptr [rdi+4], 2
0x180007975  jnz     short loc_180007981
0x180007977  xor     ecx, ecx
0x180007979  jmp     short loc_180007983
0x18000797b  add     rbx, 10h
0x18000797f  jmp     short loc_180007909
0x180007981  mov     cl, 1
0x180007983  mov     rdx, rdi
0x180007986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000798b  nop
0x18000798c  call    cs:__imp_GetCurrentThreadId
0x180007992  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180007998  cmp     ecx, eax
0x18000799a  jz      loc_180007A9C
0x1800079a0  mov     ecx, 1
0x1800079a5  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800079ad  inc     ecx; this
0x1800079af  cmp     ecx, 4
0x1800079b2  jge     loc_180007A95
0x1800079b8  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800079be  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1800079c3  mov     rbx, rax
0x1800079c6  test    rax, rax
0x1800079c9  jz      loc_180007A8B
0x1800079cf  mov     esi, [rax+10h]
0x1800079d2  mov     ebp, 50h ; 'P'
0x1800079d7  cmp     qword ptr [rax+18h], 0
0x1800079dc  jnz     short loc_180007A13
0x1800079de  test    esi, esi
0x1800079e0  jz      short loc_180007A13
0x1800079e2  mov     edx, 190h; dwBytes
0x1800079e7  lea     ecx, [rbp-48h]; dwFlags
0x1800079ea  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800079ef  mov     [rbx+18h], rax
0x1800079f3  test    rax, rax
0x1800079f6  jz      short loc_180007A13
0x1800079f8  mov     dword ptr [rbx+20h], 5
0x1800079ff  lea     rcx, [rax+190h]
0x180007a06  jmp     short loc_180007A0E
0x180007a08  mov     [rax], bp
0x180007a0b  add     rax, rbp
0x180007a0e  cmp     rax, rcx
0x180007a11  jnz     short loc_180007A08
0x180007a13  mov     r9, [rbx+18h]
0x180007a17  test    r9, r9
0x180007a1a  jz      short loc_180007A8B
0x180007a1c  test    esi, esi
0x180007a1e  jz      short loc_180007A51
0x180007a20  mov     rcx, r9
0x180007a23  movzx   eax, word ptr [rbx+20h]
0x180007a27  lea     rdx, [rax+rax*4]
0x180007a2b  shl     rdx, 4
0x180007a2f  add     rdx, r9
0x180007a32  cmp     r9, rdx
0x180007a35  jz      short loc_180007A51
0x180007a37  mov     r8d, [rbx+10h]
0x180007a3b  cmp     [rcx+4], r8d
0x180007a3f  jbe     short loc_180007A49
0x180007a41  mov     eax, [rdi+8]
0x180007a44  cmp     [rcx+8], eax
0x180007a47  jz      short loc_180007A8B
0x180007a49  add     rcx, rbp
0x180007a4c  cmp     rcx, rdx
0x180007a4f  jnz     short loc_180007A3B
0x180007a51  movzx   eax, word ptr [rbx+22h]
0x180007a55  inc     eax
0x180007a57  movzx   ecx, word ptr [rbx+20h]
0x180007a5b  xor     edx, edx
0x180007a5d  div     ecx
0x180007a5f  mov     [rbx+22h], dx
0x180007a63  mov     rax, [rbx+8]
0x180007a67  mov     r8d, 1
0x180007a6d  lock xadd [rax], r8d
0x180007a72  inc     r8d; unsigned int
0x180007a75  movzx   eax, dx
0x180007a78  lea     rcx, [rax+rax*4]
0x180007a7c  shl     rcx, 4
0x180007a80  add     rcx, r9; this
0x180007a83  mov     rdx, rdi; struct wil::FailureInfo *
0x180007a86  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180007a8b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180007a95  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180007a9c  add     rsp, 20h
0x180007aa0  pop     r14
0x180007aa2  pop     rdi
0x180007aa3  pop     rsi
0x180007aa4  pop     rbp
0x180007aa5  pop     rbx
0x180007aa6  retn
```
