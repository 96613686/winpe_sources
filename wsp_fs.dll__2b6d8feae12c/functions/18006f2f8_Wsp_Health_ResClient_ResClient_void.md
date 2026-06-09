# Wsp::Health::ResClient::~ResClient(void)

- ea: `0x18006f2f8`
- end: `0x18006f458`
- name: `??1ResClient@Health@Wsp@@QEAA@XZ`
- size: `352`
- prototype: `void __fastcall(Wsp::Health::ResClient *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18006f59c`

## callees

- `0x18006f138`
- `0x18006f2f8`
- `0x180070584`
- `0x180070648`
- `0x1800706d8`

## import_xrefs

- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x18006f3a2`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x18006f3f6`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x18006f3a2`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x18006f3f6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006f41a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006f41a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006f42e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006f42e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006f311`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006f311`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18006f34f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18006f34f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18006f36e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18006f36e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18006f361`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18006f361`

## pseudocode

```c
void __fastcall Wsp::Health::ResClient::~ResClient(Wsp::Health::ResClient *this)
{
  RTL_SRWLOCK *v1; // rbx
  PVOID v3[2]; // [rsp+20h] [rbp-38h] BYREF
  char *v4; // [rsp+30h] [rbp-28h]
  PVOID RestartKey[2]; // [rsp+38h] [rbp-20h] BYREF
  char *v6; // [rsp+48h] [rbp-10h]
  wchar_t *v7; // [rsp+80h] [rbp+28h] BYREF

  v1 = (RTL_SRWLOCK *)((char *)this + 328);
  AcquireSRWLockExclusive((PSRWLOCK)this + 41);
  v7 = L"~ResClient::Grabbed the Lock";
  Wsp::Health::ResClient::LogComment((const wchar_t *const *)&v7);
  if ( *((_QWORD *)this + 43) )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 42), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 42), 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 42));
    if ( *((_DWORD *)this + 72) )
    {
      v6 = (char *)this + 176;
      *(_OWORD *)RestartKey = 0;
      RestartKey[1] = RtlEnumerateGenericTableWithoutSplayingAvl((PRTL_AVL_TABLE)((char *)this + 184), RestartKey);
      v4 = v6;
      *(_OWORD *)v3 = *(_OWORD *)RestartKey;
      while ( v3[0] && v3[1] )
      {
        Wsp::Health::RefBase::Release(*((Wsp::Health::RefBase **)v3[1] + 1));
        if ( v4 )
        {
          if ( !v3[0] )
            break;
          if ( v3[1] )
          {
            v3[1] = RtlEnumerateGenericTableWithoutSplayingAvl((PRTL_AVL_TABLE)(v4 + 8), v3);
            if ( !v3[1] )
              v3[0] = 0;
          }
        }
      }
      CMapBase<wchar_t *,Wsp::Health::CHealthConnection *>::RemoveAll((char *)this + 176);
    }
    FreeLibrary(*((HMODULE *)this + 43));
    *((_QWORD *)this + 43) = 0;
  }
  ReleaseSRWLockExclusive(v1);
  v7 = L"~ResClient::Released the Lock";
  Wsp::Health::ResClient::LogComment((const wchar_t *const *)&v7);
  CMap<wchar_t *,Wsp::Health::CHealthConnection *>::~CMap<wchar_t *,Wsp::Health::CHealthConnection *>((char *)this + 176);
}

```

## disassembly

```asm
0x18006f2f8  push    rbp
0x18006f2fa  push    rbx
0x18006f2fb  push    rsi
0x18006f2fc  push    rdi
0x18006f2fd  mov     rbp, rsp
0x18006f300  sub     rsp, 58h
0x18006f304  lea     rbx, [rcx+148h]
0x18006f30b  mov     rsi, rcx
0x18006f30e  mov     rcx, rbx; SRWLock
0x18006f311  call    cs:__imp_AcquireSRWLockExclusive
0x18006f317  lea     rax, aResclientGrabb; "~ResClient::Grabbed the Lock"
0x18006f31e  lea     rcx, [rbp+arg_0]; wchar_t **
0x18006f322  mov     [rbp+arg_0], rax
0x18006f326  call    ?LogComment@ResClient@Health@Wsp@@SAXAEBQEB_W@Z; Wsp::Health::ResClient::LogComment(wchar_t const * const &)
0x18006f32b  cmp     qword ptr [rsi+158h], 0
0x18006f333  lea     rdi, [rsi+0B0h]
0x18006f33a  jz      loc_18006F42B
0x18006f340  mov     rcx, [rsi+150h]; pti
0x18006f347  xor     r9d, r9d; msWindowLength
0x18006f34a  xor     r8d, r8d; msPeriod
0x18006f34d  xor     edx, edx; pftDueTime
0x18006f34f  call    cs:__imp_SetThreadpoolTimer
0x18006f355  mov     rcx, [rsi+150h]; pti
0x18006f35c  mov     edx, 1; fCancelPendingCallbacks
0x18006f361  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18006f367  mov     rcx, [rsi+150h]; pti
0x18006f36e  call    cs:__imp_CloseThreadpoolTimer
0x18006f374  cmp     dword ptr [rdi+70h], 0
0x18006f378  jbe     loc_18006F413
0x18006f37e  xorps   xmm0, xmm0
0x18006f381  mov     [rbp+var_28], 0
0x18006f389  xorps   xmm1, xmm1
0x18006f38c  mov     [rbp+var_10], rdi
0x18006f390  lea     rcx, [rdi+8]; Table
0x18006f394  lea     rdx, [rbp+RestartKey]; RestartKey
0x18006f398  movdqu  xmmword ptr [rbp+var_38], xmm0
0x18006f39d  movdqu  xmmword ptr [rbp+RestartKey], xmm1
0x18006f3a2  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x18006f3a8  movsd   xmm1, [rbp+var_10]
0x18006f3ad  mov     [rbp+RestartKey+8], rax
0x18006f3b1  movups  xmm0, xmmword ptr [rbp+RestartKey]
0x18006f3b5  movsd   [rbp+var_28], xmm1
0x18006f3ba  movups  xmmword ptr [rbp+var_38], xmm0
0x18006f3be  cmp     [rbp+var_38], 0
0x18006f3c3  jz      short loc_18006F40B
0x18006f3c5  mov     rcx, [rbp+var_38+8]
0x18006f3c9  test    rcx, rcx
0x18006f3cc  jz      short loc_18006F40B
0x18006f3ce  mov     rcx, [rcx+8]; this
0x18006f3d2  call    ?Release@RefBase@Health@Wsp@@QEAAKXZ; Wsp::Health::RefBase::Release(void)
0x18006f3d7  mov     rcx, [rbp+var_28]
0x18006f3db  test    rcx, rcx
0x18006f3de  jz      short loc_18006F3BE
0x18006f3e0  cmp     [rbp+var_38], 0
0x18006f3e5  jz      short loc_18006F40B
0x18006f3e7  cmp     [rbp+var_38+8], 0
0x18006f3ec  jz      short loc_18006F3BE
0x18006f3ee  add     rcx, 8; Table
0x18006f3f2  lea     rdx, [rbp+var_38]; RestartKey
0x18006f3f6  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x18006f3fc  mov     [rbp+var_38+8], rax
0x18006f400  test    rax, rax
0x18006f403  jnz     short loc_18006F3BE
0x18006f405  mov     [rbp+var_38], rax
0x18006f409  jmp     short loc_18006F3BE
0x18006f40b  mov     rcx, rdi; TableContext
0x18006f40e  call    ?RemoveAll@?$CMapBase@PEA_WPEAVCHealthConnection@Health@Wsp@@@@QEAAXXZ; CMapBase<wchar_t *,Wsp::Health::CHealthConnection *>::RemoveAll(void)
0x18006f413  mov     rcx, [rsi+158h]; hLibModule
0x18006f41a  call    cs:__imp_FreeLibrary
0x18006f420  mov     qword ptr [rsi+158h], 0
0x18006f42b  mov     rcx, rbx; SRWLock
0x18006f42e  call    cs:__imp_ReleaseSRWLockExclusive
0x18006f434  lea     rax, aResclientRelea; "~ResClient::Released the Lock"
0x18006f43b  lea     rcx, [rbp+arg_0]; wchar_t **
0x18006f43f  mov     [rbp+arg_0], rax
0x18006f443  call    ?LogComment@ResClient@Health@Wsp@@SAXAEBQEB_W@Z; Wsp::Health::ResClient::LogComment(wchar_t const * const &)
0x18006f448  mov     rcx, rdi; TableContext
0x18006f44b  add     rsp, 58h
0x18006f44f  pop     rdi
0x18006f450  pop     rsi
0x18006f451  pop     rbx
0x18006f452  pop     rbp
0x18006f453  jmp     ??1?$CMap@PEA_WPEAVCHealthConnection@Health@Wsp@@@@UEAA@XZ; CMap<wchar_t *,Wsp::Health::CHealthConnection *>::~CMap<wchar_t *,Wsp::Health::CHealthConnection *>(void)
```
