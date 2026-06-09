# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x140002e60`
- end: `0x140003066`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `518`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140002e60`
- `0x140003558`
- `0x14000363c`
- `0x140003eb8`
- `0x1400041f8`
- `0x140015010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140002e8a`
- `KERNEL32!GetCurrentThreadId` at `0x140002f4b`
- `KERNEL32!GetCurrentThreadId` at `0x140002e8a`
- `KERNEL32!GetCurrentThreadId` at `0x140002f4b`

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
0x140002e60  push    rbx
0x140002e62  push    rbp
0x140002e63  push    rsi
0x140002e64  push    rdi
0x140002e65  push    r14
0x140002e67  sub     rsp, 20h
0x140002e6b  mov     byte ptr [rdx], 0
0x140002e6e  xor     bpl, bpl
0x140002e71  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140002e78  mov     r14, r8
0x140002e7b  mov     rsi, rdx
0x140002e7e  mov     rdi, rcx
0x140002e81  test    rbx, rbx
0x140002e84  jz      loc_140002F20
0x140002e8a  call    cs:__imp_GetCurrentThreadId
0x140002e90  mov     r8d, eax
0x140002e93  mov     r9d, eax
0x140002e96  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140002ea0  shr     r8, 2
0x140002ea4  mul     r8
0x140002ea7  shr     rdx, 3
0x140002eab  lea     rcx, [rdx+rdx*4]
0x140002eaf  add     rcx, rcx
0x140002eb2  sub     r8, rcx
0x140002eb5  mov     rbx, [rbx+r8*8]
0x140002eb9  jmp     short loc_140002EC4
0x140002ebb  cmp     [rbx], r9d
0x140002ebe  jz      short loc_140002F3B
0x140002ec0  mov     rbx, [rbx+8]
0x140002ec4  test    rbx, rbx
0x140002ec7  jnz     short loc_140002EBB
0x140002ec9  test    rbx, rbx
0x140002ecc  jz      short loc_140002F20
0x140002ece  cmp     qword ptr [rbx], 0
0x140002ed2  jz      short loc_140002F20
0x140002ed4  mov     [rsi], bpl
0x140002ed7  mov     r9, r14; unsigned __int64
0x140002eda  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x140002edd  mov     r8, rsi; char *
0x140002ee0  mov     rcx, rdi; struct wil::FailureInfo *
0x140002ee3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140002ee8  test    al, al
0x140002eea  jz      short loc_140002EF0
0x140002eec  mov     [rdi+48h], rsi
0x140002ef0  mov     rbx, [rbx]
0x140002ef3  mov     al, [rbx+28h]
0x140002ef6  mov     byte ptr [rbx+28h], 1
0x140002efa  test    al, al
0x140002efc  jnz     short loc_140002F17
0x140002efe  mov     rcx, [rbx+8]
0x140002f02  mov     rdx, rdi
0x140002f05  mov     rax, [rcx]
0x140002f08  mov     rax, [rax]
0x140002f0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002f10  or      bpl, al
0x140002f13  mov     byte ptr [rbx+28h], 0
0x140002f17  mov     rbx, [rbx+10h]
0x140002f1b  test    rbx, rbx
0x140002f1e  jnz     short loc_140002EF3
0x140002f20  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x140002f27  test    rax, rax
0x140002f2a  jz      short loc_140002F4B
0x140002f2c  test    bpl, bpl
0x140002f2f  jnz     short loc_140002F41
0x140002f31  test    byte ptr [rdi+4], 2
0x140002f35  jnz     short loc_140002F41
0x140002f37  xor     ecx, ecx
0x140002f39  jmp     short loc_140002F43
0x140002f3b  add     rbx, 10h
0x140002f3f  jmp     short loc_140002EC9
0x140002f41  mov     cl, 1
0x140002f43  mov     rdx, rdi
0x140002f46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002f4b  call    cs:__imp_GetCurrentThreadId
0x140002f51  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140002f57  cmp     ecx, eax
0x140002f59  jz      loc_14000305B
0x140002f5f  mov     ecx, 1
0x140002f64  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x140002f6c  inc     ecx; this
0x140002f6e  cmp     ecx, 4
0x140002f71  jge     loc_140003054
0x140002f77  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140002f7d  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x140002f82  mov     rbx, rax
0x140002f85  test    rax, rax
0x140002f88  jz      loc_14000304A
0x140002f8e  cmp     qword ptr [rax+18h], 0
0x140002f93  mov     ebp, 50h ; 'P'
0x140002f98  mov     esi, [rax+10h]
0x140002f9b  jnz     short loc_140002FD2
0x140002f9d  test    esi, esi
0x140002f9f  jz      short loc_140002FD2
0x140002fa1  mov     edx, 190h; dwBytes
0x140002fa6  lea     ecx, [rbp-48h]; dwFlags
0x140002fa9  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140002fae  mov     [rbx+18h], rax
0x140002fb2  test    rax, rax
0x140002fb5  jz      short loc_140002FD2
0x140002fb7  mov     dword ptr [rbx+20h], 5
0x140002fbe  lea     rcx, [rax+190h]
0x140002fc5  jmp     short loc_140002FCD
0x140002fc7  mov     [rax], bp
0x140002fca  add     rax, rbp
0x140002fcd  cmp     rax, rcx
0x140002fd0  jnz     short loc_140002FC7
0x140002fd2  mov     r9, [rbx+18h]
0x140002fd6  test    r9, r9
0x140002fd9  jz      short loc_14000304A
0x140002fdb  test    esi, esi
0x140002fdd  jz      short loc_140003010
0x140002fdf  movzx   eax, word ptr [rbx+20h]
0x140002fe3  mov     rcx, r9
0x140002fe6  lea     rdx, [rax+rax*4]
0x140002fea  shl     rdx, 4
0x140002fee  add     rdx, r9
0x140002ff1  cmp     r9, rdx
0x140002ff4  jz      short loc_140003010
0x140002ff6  mov     r8d, [rbx+10h]
0x140002ffa  cmp     [rcx+4], r8d
0x140002ffe  jbe     short loc_140003008
0x140003000  mov     eax, [rdi+8]
0x140003003  cmp     [rcx+8], eax
0x140003006  jz      short loc_14000304A
0x140003008  add     rcx, rbp
0x14000300b  cmp     rcx, rdx
0x14000300e  jnz     short loc_140002FFA
0x140003010  movzx   eax, word ptr [rbx+22h]
0x140003014  xor     edx, edx
0x140003016  movzx   ecx, word ptr [rbx+20h]
0x14000301a  inc     eax
0x14000301c  div     ecx
0x14000301e  mov     rax, [rbx+8]
0x140003022  mov     r8d, 1
0x140003028  mov     [rbx+22h], dx
0x14000302c  lock xadd [rax], r8d
0x140003031  movzx   eax, dx
0x140003034  inc     r8d; unsigned int
0x140003037  mov     rdx, rdi; struct wil::FailureInfo *
0x14000303a  lea     rcx, [rax+rax*4]
0x14000303e  shl     rcx, 4
0x140003042  add     rcx, r9; this
0x140003045  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x14000304a  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140003054  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x14000305b  add     rsp, 20h
0x14000305f  pop     r14
0x140003061  pop     rdi
0x140003062  pop     rsi
0x140003063  pop     rbp
0x140003064  pop     rbx
0x140003065  retn
```
