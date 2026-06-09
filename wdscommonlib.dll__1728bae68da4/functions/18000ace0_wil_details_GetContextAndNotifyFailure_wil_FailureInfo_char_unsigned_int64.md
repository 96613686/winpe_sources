# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18000ace0`
- end: `0x18000ae3e`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `350`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000ace0`
- `0x18000b364`
- `0x18000b464`
- `0x18000d784`
- `0x180031010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000ad18`
- `KERNEL32!GetCurrentThreadId` at `0x18000adcc`
- `KERNEL32!GetCurrentThreadId` at `0x18000ad18`
- `KERNEL32!GetCurrentThreadId` at `0x18000adcc`

## pseudocode

```c
void __fastcall wil::details::GetContextAndNotifyFailure(unsigned __int64 this, struct wil::FailureInfo *a2, char *a3)
{
  char v3; // bp
  __int64 v4; // rbx
  wil::details *v7; // rdi
  unsigned __int64 CurrentThreadId; // r10
  __int64 i; // rbx
  struct wil::details::ThreadFailureCallbackHolder *v10; // rbx
  char v11; // al
  DWORD v12; // eax
  bool v13; // dl
  wil::details_abi *v14; // rcx
  wil::details_abi::ThreadLocalData *ThreadLocalDataCache; // rax

  *(_BYTE *)a2 = 0;
  v3 = 0;
  v4 = wil::details::g_pThreadFailureCallbacks;
  v7 = (wil::details *)this;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    this = 10 * (CurrentThreadId / 0xA);
    for ( i = *(_QWORD *)(v4 + 8 * (CurrentThreadId % 0xA)); i; i = *(_QWORD *)(i + 8) )
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
        v11 = (***((__int64 (__fastcall ****)(_QWORD, wil::details *))v10 + 1))(*((_QWORD *)v10 + 1), v7);
        v10 = (struct wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)v10 + 2);
        v3 |= v11;
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
      if ( ThreadLocalDataCache )
        wil::details_abi::ThreadLocalData::SetLastError(ThreadLocalDataCache, v7);
      `wil::SetLastError'::`2'::lastThread = 0;
    }
    _InterlockedDecrement(&`wil::SetLastError'::`5'::depth);
  }
}

```

## disassembly

```asm
0x18000ace0  mov     rax, rsp
0x18000ace3  mov     [rax+8], rbx
0x18000ace7  mov     [rax+10h], rbp
0x18000aceb  mov     [rax+18h], rsi
0x18000acef  mov     [rax+20h], rdi
0x18000acf3  push    r14
0x18000acf5  sub     rsp, 20h
0x18000acf9  mov     byte ptr [rdx], 0
0x18000acfc  xor     bpl, bpl
0x18000acff  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000ad06  mov     r14, r8
0x18000ad09  mov     rsi, rdx
0x18000ad0c  mov     rdi, rcx
0x18000ad0f  test    rbx, rbx
0x18000ad12  jz      loc_18000ADA1
0x18000ad18  call    cs:__imp_GetCurrentThreadId
0x18000ad1f  nop     dword ptr [rax+rax+00h]
0x18000ad24  mov     r9d, eax
0x18000ad27  mov     r10d, eax
0x18000ad2a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000ad34  mul     r10
0x18000ad37  shr     rdx, 3
0x18000ad3b  lea     rcx, [rdx+rdx*4]
0x18000ad3f  add     rcx, rcx
0x18000ad42  sub     r9, rcx
0x18000ad45  mov     rbx, [rbx+r9*8]
0x18000ad49  jmp     short loc_18000AD54
0x18000ad4b  cmp     [rbx], r10d
0x18000ad4e  jz      short loc_18000ADBC
0x18000ad50  mov     rbx, [rbx+8]
0x18000ad54  test    rbx, rbx
0x18000ad57  jnz     short loc_18000AD4B
0x18000ad59  test    rbx, rbx
0x18000ad5c  jz      short loc_18000ADA1
0x18000ad5e  cmp     qword ptr [rbx], 0
0x18000ad62  jz      short loc_18000ADA1
0x18000ad64  mov     [rsi], bpl
0x18000ad67  mov     r9, r14; unsigned __int64
0x18000ad6a  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x18000ad6d  mov     r8, rsi; char *
0x18000ad70  mov     rcx, rdi; struct wil::FailureInfo *
0x18000ad73  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000ad78  test    al, al
0x18000ad7a  jz      short loc_18000AD80
0x18000ad7c  mov     [rdi+48h], rsi
0x18000ad80  mov     rbx, [rbx]
0x18000ad83  mov     rcx, [rbx+8]
0x18000ad87  mov     rdx, rdi
0x18000ad8a  mov     rax, [rcx]
0x18000ad8d  mov     rax, [rax]
0x18000ad90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad95  mov     rbx, [rbx+10h]
0x18000ad99  or      bpl, al
0x18000ad9c  test    rbx, rbx
0x18000ad9f  jnz     short loc_18000AD83
0x18000ada1  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000ada8  test    rax, rax
0x18000adab  jz      short loc_18000ADCC
0x18000adad  test    bpl, bpl
0x18000adb0  jnz     short loc_18000ADC2
0x18000adb2  test    byte ptr [rdi+4], 2
0x18000adb6  jnz     short loc_18000ADC2
0x18000adb8  xor     ecx, ecx
0x18000adba  jmp     short loc_18000ADC4
0x18000adbc  add     rbx, 10h
0x18000adc0  jmp     short loc_18000AD59
0x18000adc2  mov     cl, 1
0x18000adc4  mov     rdx, rdi
0x18000adc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adcc  call    cs:__imp_GetCurrentThreadId
0x18000add3  nop     dword ptr [rax+rax+00h]
0x18000add8  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000adde  cmp     ecx, eax
0x18000ade0  jz      short loc_18000AE22
0x18000ade2  mov     ecx, 1
0x18000ade7  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000adef  inc     ecx; this
0x18000adf1  cmp     ecx, 4
0x18000adf4  jge     short loc_18000AE1B
0x18000adf6  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000adfc  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18000ae01  test    rax, rax
0x18000ae04  jz      short loc_18000AE11
0x18000ae06  mov     rdx, rdi; struct wil::FailureInfo *
0x18000ae09  mov     rcx, rax; this
0x18000ae0c  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x18000ae11  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000ae1b  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000ae22  mov     rbx, [rsp+28h+arg_0]
0x18000ae27  mov     rbp, [rsp+28h+arg_8]
0x18000ae2c  mov     rsi, [rsp+28h+arg_10]
0x18000ae31  mov     rdi, [rsp+28h+arg_18]
0x18000ae36  add     rsp, 20h
0x18000ae3a  pop     r14
0x18000ae3c  retn
```
