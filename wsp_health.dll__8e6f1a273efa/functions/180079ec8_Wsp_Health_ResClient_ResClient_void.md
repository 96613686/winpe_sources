# Wsp::Health::ResClient::~ResClient(void)

- ea: `0x180079ec8`
- end: `0x18007a058`
- name: `??1ResClient@Health@Wsp@@QEAA@XZ`
- size: `400`
- prototype: `void __fastcall(Wsp::Health::ResClient *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18007a1a0`

## callees

- `0x180079720`
- `0x180079d30`
- `0x180079ec8`
- `0x18007b990`
- `0x18007ba5c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18007a00e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18007a00e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180079ee1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180079ee1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007a028`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007a028`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180079f50`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180079f50`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180079f25`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180079f25`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180079f3d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180079f3d`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x180079f8a`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x180079fe4`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x180079f8a`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x180079fe4`

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
0x180079ec8  push    rbp
0x180079eca  push    rbx
0x180079ecb  push    rsi
0x180079ecc  push    rdi
0x180079ecd  mov     rbp, rsp
0x180079ed0  sub     rsp, 58h
0x180079ed4  lea     rbx, [rcx+148h]
0x180079edb  mov     rsi, rcx
0x180079ede  mov     rcx, rbx; SRWLock
0x180079ee1  call    cs:__imp_AcquireSRWLockExclusive
0x180079ee8  nop     dword ptr [rax+rax+00h]
0x180079eed  lea     rax, aResclientGrabb; "~ResClient::Grabbed the Lock"
0x180079ef4  lea     rcx, [rbp+arg_0]; wchar_t **
0x180079ef8  mov     [rbp+arg_0], rax
0x180079efc  call    ?LogComment@ResClient@Health@Wsp@@SAXAEBQEB_W@Z; Wsp::Health::ResClient::LogComment(wchar_t const * const &)
0x180079f01  cmp     qword ptr [rsi+158h], 0
0x180079f09  lea     rdi, [rsi+0B0h]
0x180079f10  jz      loc_18007A025
0x180079f16  mov     rcx, [rsi+150h]; pti
0x180079f1d  xor     r9d, r9d; msWindowLength
0x180079f20  xor     r8d, r8d; msPeriod
0x180079f23  xor     edx, edx; pftDueTime
0x180079f25  call    cs:__imp_SetThreadpoolTimer
0x180079f2c  nop     dword ptr [rax+rax+00h]
0x180079f31  mov     rcx, [rsi+150h]; pti
0x180079f38  mov     edx, 1; fCancelPendingCallbacks
0x180079f3d  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180079f44  nop     dword ptr [rax+rax+00h]
0x180079f49  mov     rcx, [rsi+150h]; pti
0x180079f50  call    cs:__imp_CloseThreadpoolTimer
0x180079f57  nop     dword ptr [rax+rax+00h]
0x180079f5c  cmp     dword ptr [rdi+70h], 0
0x180079f60  jbe     loc_18007A007
0x180079f66  xorps   xmm0, xmm0
0x180079f69  mov     [rbp+var_28], 0
0x180079f71  xorps   xmm1, xmm1
0x180079f74  mov     [rbp+var_10], rdi
0x180079f78  lea     rcx, [rdi+8]; Table
0x180079f7c  lea     rdx, [rbp+RestartKey]; RestartKey
0x180079f80  movdqu  xmmword ptr [rbp+var_38], xmm0
0x180079f85  movdqu  xmmword ptr [rbp+RestartKey], xmm1
0x180079f8a  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x180079f91  nop     dword ptr [rax+rax+00h]
0x180079f96  movsd   xmm1, [rbp+var_10]
0x180079f9b  mov     [rbp+RestartKey+8], rax
0x180079f9f  movups  xmm0, xmmword ptr [rbp+RestartKey]
0x180079fa3  movsd   [rbp+var_28], xmm1
0x180079fa8  movups  xmmword ptr [rbp+var_38], xmm0
0x180079fac  cmp     [rbp+var_38], 0
0x180079fb1  jz      short loc_180079FFF
0x180079fb3  mov     rcx, [rbp+var_38+8]
0x180079fb7  test    rcx, rcx
0x180079fba  jz      short loc_180079FFF
0x180079fbc  mov     rcx, [rcx+8]; this
0x180079fc0  call    ?Release@RefBase@Health@Wsp@@QEAAKXZ; Wsp::Health::RefBase::Release(void)
0x180079fc5  mov     rcx, [rbp+var_28]
0x180079fc9  test    rcx, rcx
0x180079fcc  jz      short loc_180079FAC
0x180079fce  cmp     [rbp+var_38], 0
0x180079fd3  jz      short loc_180079FFF
0x180079fd5  cmp     [rbp+var_38+8], 0
0x180079fda  jz      short loc_180079FAC
0x180079fdc  add     rcx, 8; Table
0x180079fe0  lea     rdx, [rbp+var_38]; RestartKey
0x180079fe4  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x180079feb  nop     dword ptr [rax+rax+00h]
0x180079ff0  mov     [rbp+var_38+8], rax
0x180079ff4  test    rax, rax
0x180079ff7  jnz     short loc_180079FAC
0x180079ff9  mov     [rbp+var_38], rax
0x180079ffd  jmp     short loc_180079FAC
0x180079fff  mov     rcx, rdi; TableContext
0x18007a002  call    ?RemoveAll@?$CMapBase@PEA_WPEAVCHealthConnection@Health@Wsp@@@@QEAAXXZ; CMapBase<wchar_t *,Wsp::Health::CHealthConnection *>::RemoveAll(void)
0x18007a007  mov     rcx, [rsi+158h]; hLibModule
0x18007a00e  call    cs:__imp_FreeLibrary
0x18007a015  nop     dword ptr [rax+rax+00h]
0x18007a01a  mov     qword ptr [rsi+158h], 0
0x18007a025  mov     rcx, rbx; SRWLock
0x18007a028  call    cs:__imp_ReleaseSRWLockExclusive
0x18007a02f  nop     dword ptr [rax+rax+00h]
0x18007a034  lea     rax, aResclientRelea; "~ResClient::Released the Lock"
0x18007a03b  lea     rcx, [rbp+arg_0]; wchar_t **
0x18007a03f  mov     [rbp+arg_0], rax
0x18007a043  call    ?LogComment@ResClient@Health@Wsp@@SAXAEBQEB_W@Z; Wsp::Health::ResClient::LogComment(wchar_t const * const &)
0x18007a048  mov     rcx, rdi; TableContext
0x18007a04b  add     rsp, 58h
0x18007a04f  pop     rdi
0x18007a050  pop     rsi
0x18007a051  pop     rbx
0x18007a052  pop     rbp
0x18007a053  jmp     ??1?$CMap@PEA_WPEAVCHealthConnection@Health@Wsp@@@@UEAA@XZ; CMap<wchar_t *,Wsp::Health::CHealthConnection *>::~CMap<wchar_t *,Wsp::Health::CHealthConnection *>(void)
```
