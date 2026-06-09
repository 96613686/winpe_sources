# Wsp::Health::ResClient::~ResClient(void)

- ea: `0x180077fc4`
- end: `0x180078124`
- name: `??1ResClient@Health@Wsp@@QEAA@XZ`
- size: `352`
- prototype: `void __fastcall(Wsp::Health::ResClient *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18007825c`

## callees

- `0x180077864`
- `0x180077e44`
- `0x180077fc4`
- `0x1800798c4`
- `0x180079980`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800780e6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800780e6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180077fdd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180077fdd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800780fa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800780fa`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18007803a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18007803a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18007801b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18007801b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18007802d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18007802d`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x18007806e`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1800780c2`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x18007806e`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1800780c2`

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
0x180077fc4  push    rbp
0x180077fc6  push    rbx
0x180077fc7  push    rsi
0x180077fc8  push    rdi
0x180077fc9  mov     rbp, rsp
0x180077fcc  sub     rsp, 58h
0x180077fd0  lea     rbx, [rcx+148h]
0x180077fd7  mov     rsi, rcx
0x180077fda  mov     rcx, rbx; SRWLock
0x180077fdd  call    cs:__imp_AcquireSRWLockExclusive
0x180077fe3  lea     rax, aResclientGrabb; "~ResClient::Grabbed the Lock"
0x180077fea  lea     rcx, [rbp+arg_0]; wchar_t **
0x180077fee  mov     [rbp+arg_0], rax
0x180077ff2  call    ?LogComment@ResClient@Health@Wsp@@SAXAEBQEB_W@Z; Wsp::Health::ResClient::LogComment(wchar_t const * const &)
0x180077ff7  cmp     qword ptr [rsi+158h], 0
0x180077fff  lea     rdi, [rsi+0B0h]
0x180078006  jz      loc_1800780F7
0x18007800c  mov     rcx, [rsi+150h]; pti
0x180078013  xor     r9d, r9d; msWindowLength
0x180078016  xor     r8d, r8d; msPeriod
0x180078019  xor     edx, edx; pftDueTime
0x18007801b  call    cs:__imp_SetThreadpoolTimer
0x180078021  mov     rcx, [rsi+150h]; pti
0x180078028  mov     edx, 1; fCancelPendingCallbacks
0x18007802d  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180078033  mov     rcx, [rsi+150h]; pti
0x18007803a  call    cs:__imp_CloseThreadpoolTimer
0x180078040  cmp     dword ptr [rdi+70h], 0
0x180078044  jbe     loc_1800780DF
0x18007804a  xorps   xmm0, xmm0
0x18007804d  mov     [rbp+var_28], 0
0x180078055  xorps   xmm1, xmm1
0x180078058  mov     [rbp+var_10], rdi
0x18007805c  lea     rcx, [rdi+8]; Table
0x180078060  lea     rdx, [rbp+RestartKey]; RestartKey
0x180078064  movdqu  xmmword ptr [rbp+var_38], xmm0
0x180078069  movdqu  xmmword ptr [rbp+RestartKey], xmm1
0x18007806e  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x180078074  movsd   xmm1, [rbp+var_10]
0x180078079  mov     [rbp+RestartKey+8], rax
0x18007807d  movups  xmm0, xmmword ptr [rbp+RestartKey]
0x180078081  movsd   [rbp+var_28], xmm1
0x180078086  movups  xmmword ptr [rbp+var_38], xmm0
0x18007808a  cmp     [rbp+var_38], 0
0x18007808f  jz      short loc_1800780D7
0x180078091  mov     rcx, [rbp+var_38+8]
0x180078095  test    rcx, rcx
0x180078098  jz      short loc_1800780D7
0x18007809a  mov     rcx, [rcx+8]; this
0x18007809e  call    ?Release@RefBase@Health@Wsp@@QEAAKXZ; Wsp::Health::RefBase::Release(void)
0x1800780a3  mov     rcx, [rbp+var_28]
0x1800780a7  test    rcx, rcx
0x1800780aa  jz      short loc_18007808A
0x1800780ac  cmp     [rbp+var_38], 0
0x1800780b1  jz      short loc_1800780D7
0x1800780b3  cmp     [rbp+var_38+8], 0
0x1800780b8  jz      short loc_18007808A
0x1800780ba  add     rcx, 8; Table
0x1800780be  lea     rdx, [rbp+var_38]; RestartKey
0x1800780c2  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x1800780c8  mov     [rbp+var_38+8], rax
0x1800780cc  test    rax, rax
0x1800780cf  jnz     short loc_18007808A
0x1800780d1  mov     [rbp+var_38], rax
0x1800780d5  jmp     short loc_18007808A
0x1800780d7  mov     rcx, rdi; TableContext
0x1800780da  call    ?RemoveAll@?$CMapBase@PEA_WPEAVCHealthConnection@Health@Wsp@@@@QEAAXXZ; CMapBase<wchar_t *,Wsp::Health::CHealthConnection *>::RemoveAll(void)
0x1800780df  mov     rcx, [rsi+158h]; hLibModule
0x1800780e6  call    cs:__imp_FreeLibrary
0x1800780ec  mov     qword ptr [rsi+158h], 0
0x1800780f7  mov     rcx, rbx; SRWLock
0x1800780fa  call    cs:__imp_ReleaseSRWLockExclusive
0x180078100  lea     rax, aResclientRelea; "~ResClient::Released the Lock"
0x180078107  lea     rcx, [rbp+arg_0]; wchar_t **
0x18007810b  mov     [rbp+arg_0], rax
0x18007810f  call    ?LogComment@ResClient@Health@Wsp@@SAXAEBQEB_W@Z; Wsp::Health::ResClient::LogComment(wchar_t const * const &)
0x180078114  mov     rcx, rdi; TableContext
0x180078117  add     rsp, 58h
0x18007811b  pop     rdi
0x18007811c  pop     rsi
0x18007811d  pop     rbx
0x18007811e  pop     rbp
0x18007811f  jmp     ??1?$CMap@PEA_WPEAVCHealthConnection@Health@Wsp@@@@UEAA@XZ; CMap<wchar_t *,Wsp::Health::CHealthConnection *>::~CMap<wchar_t *,Wsp::Health::CHealthConnection *>(void)
```
