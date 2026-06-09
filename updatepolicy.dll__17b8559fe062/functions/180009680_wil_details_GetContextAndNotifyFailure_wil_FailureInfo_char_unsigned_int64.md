# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180009680`
- end: `0x18000988a`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `522`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180007d40`
- `0x180009220`
- `0x1800094c0`
- `0x180009580`
- `0x180009680`
- `0x180015430`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800096b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009767`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800096b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009767`

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
0x180009680  mov     [rsp+arg_18], rbx
0x180009685  push    rbp
0x180009686  push    rsi
0x180009687  push    rdi
0x180009688  push    r14
0x18000968a  push    r15
0x18000968c  sub     rsp, 20h
0x180009690  mov     r14, r8
0x180009693  mov     rsi, rdx
0x180009696  mov     rdi, rcx
0x180009699  xor     r15d, r15d
0x18000969c  mov     [rdx], r15b
0x18000969f  mov     bpl, r15b
0x1800096a2  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800096a9  test    rbx, rbx
0x1800096ac  jz      loc_18000973B
0x1800096b2  call    cs:__imp_GetCurrentThreadId
0x1800096b8  mov     r9d, eax
0x1800096bb  mov     r8d, eax
0x1800096be  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800096c8  mul     r9
0x1800096cb  shr     rdx, 3
0x1800096cf  lea     rcx, [rdx+rdx*4]
0x1800096d3  add     rcx, rcx
0x1800096d6  sub     r8, rcx
0x1800096d9  mov     rbx, [rbx+r8*8]
0x1800096dd  jmp     short loc_1800096EC
0x1800096df  cmp     [rbx], r9d
0x1800096e2  jz      loc_1800097E1
0x1800096e8  mov     rbx, [rbx+8]
0x1800096ec  test    rbx, rbx
0x1800096ef  jnz     short loc_1800096DF
0x1800096f1  mov     rbx, r15
0x1800096f4  test    rbx, rbx
0x1800096f7  jz      short loc_18000973B
0x1800096f9  cmp     [rbx], r15
0x1800096fc  jz      short loc_18000973B
0x1800096fe  mov     [rsi], r15b
0x180009701  mov     r9, r14; unsigned __int64
0x180009704  mov     r8, rsi; char *
0x180009707  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x18000970a  mov     rcx, rdi; struct wil::FailureInfo *
0x18000970d  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180009712  test    al, al
0x180009714  jz      short loc_18000971A
0x180009716  mov     [rdi+48h], rsi
0x18000971a  mov     rbx, [rbx]
0x18000971d  mov     rcx, [rbx+8]
0x180009721  mov     rax, [rcx]
0x180009724  mov     rdx, rdi
0x180009727  mov     rax, [rax]
0x18000972a  call    _guard_dispatch_icall
0x18000972f  or      bpl, al
0x180009732  mov     rbx, [rbx+10h]
0x180009736  test    rbx, rbx
0x180009739  jnz     short loc_18000971D
0x18000973b  mov     r14d, 1
0x180009741  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180009748  test    rax, rax
0x18000974b  jz      short loc_180009767
0x18000974d  test    bpl, bpl
0x180009750  jnz     short loc_18000975B
0x180009752  test    byte ptr [rdi+4], 2
0x180009756  mov     cl, r15b
0x180009759  jz      short loc_18000975E
0x18000975b  mov     cl, r14b
0x18000975e  mov     rdx, rdi
0x180009761  call    _guard_dispatch_icall
0x180009766  nop
0x180009767  call    cs:__imp_GetCurrentThreadId
0x18000976d  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180009773  cmp     ecx, eax
0x180009775  jz      loc_180009879
0x18000977b  mov     ecx, r14d
0x18000977e  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180009786  add     ecx, r14d; this
0x180009789  cmp     ecx, 4
0x18000978c  jge     loc_180009872
0x180009792  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180009798  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18000979d  mov     rbx, rax
0x1800097a0  test    rax, rax
0x1800097a3  jz      loc_18000986B
0x1800097a9  mov     esi, [rax+10h]
0x1800097ac  mov     ebp, 50h ; 'P'
0x1800097b1  cmp     [rax+18h], r15
0x1800097b5  jnz     short loc_1800097F5
0x1800097b7  test    esi, esi
0x1800097b9  jz      short loc_1800097F5
0x1800097bb  mov     edx, 190h; dwBytes
0x1800097c0  lea     ecx, [rbp-48h]; dwFlags
0x1800097c3  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800097c8  mov     [rbx+18h], rax
0x1800097cc  test    rax, rax
0x1800097cf  jz      short loc_1800097F5
0x1800097d1  mov     dword ptr [rbx+20h], 5
0x1800097d8  lea     rcx, [rax+190h]
0x1800097df  jmp     short loc_1800097F0
0x1800097e1  add     rbx, 10h
0x1800097e5  jmp     loc_1800096F4
0x1800097ea  mov     [rax], bp
0x1800097ed  add     rax, rbp
0x1800097f0  cmp     rax, rcx
0x1800097f3  jnz     short loc_1800097EA
0x1800097f5  mov     r9, [rbx+18h]
0x1800097f9  test    r9, r9
0x1800097fc  jz      short loc_18000986B
0x1800097fe  test    esi, esi
0x180009800  jz      short loc_180009833
0x180009802  mov     rcx, r9
0x180009805  movzx   eax, word ptr [rbx+20h]
0x180009809  lea     rdx, [rax+rax*4]
0x18000980d  shl     rdx, 4
0x180009811  add     rdx, r9
0x180009814  cmp     r9, rdx
0x180009817  jz      short loc_180009833
0x180009819  mov     r8d, [rbx+10h]
0x18000981d  cmp     [rcx+4], r8d
0x180009821  jbe     short loc_18000982B
0x180009823  mov     eax, [rdi+8]
0x180009826  cmp     [rcx+8], eax
0x180009829  jz      short loc_18000986B
0x18000982b  add     rcx, rbp
0x18000982e  cmp     rcx, rdx
0x180009831  jnz     short loc_18000981D
0x180009833  movzx   eax, word ptr [rbx+22h]
0x180009837  add     eax, r14d
0x18000983a  movzx   ecx, word ptr [rbx+20h]
0x18000983e  xor     edx, edx
0x180009840  div     ecx
0x180009842  mov     [rbx+22h], dx
0x180009846  mov     rax, [rbx+8]
0x18000984a  mov     r8d, r14d
0x18000984d  lock xadd [rax], r8d
0x180009852  add     r8d, r14d; unsigned int
0x180009855  movzx   eax, dx
0x180009858  lea     rcx, [rax+rax*4]
0x18000985c  shl     rcx, 4
0x180009860  add     rcx, r9; this
0x180009863  mov     rdx, rdi; struct wil::FailureInfo *
0x180009866  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000986b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, r15d; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180009872  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180009879  mov     rbx, [rsp+48h+arg_18]
0x18000987e  add     rsp, 20h
0x180009882  pop     r15
0x180009884  pop     r14
0x180009886  pop     rdi
0x180009887  pop     rsi
0x180009888  pop     rbp
0x180009889  retn
```
