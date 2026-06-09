# Wsp::Health::ResClient::~ResClient(void)

- ea: `0x180070bf8`
- end: `0x180070d88`
- name: `??1ResClient@Health@Wsp@@QEAA@XZ`
- size: `400`
- prototype: `void __fastcall(Wsp::Health::ResClient *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180070ed0`

## callees

- `0x180070a14`
- `0x180070bf8`
- `0x180072020`
- `0x1800720e4`
- `0x180072184`

## import_xrefs

- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x180070cba`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x180070d14`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x180070cba`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x180070d14`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180070d3e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180070d3e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180070d58`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180070d58`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180070c11`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180070c11`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180070c55`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180070c55`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180070c80`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180070c80`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180070c6d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180070c6d`

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
0x180070bf8  push    rbp
0x180070bfa  push    rbx
0x180070bfb  push    rsi
0x180070bfc  push    rdi
0x180070bfd  mov     rbp, rsp
0x180070c00  sub     rsp, 58h
0x180070c04  lea     rbx, [rcx+148h]
0x180070c0b  mov     rsi, rcx
0x180070c0e  mov     rcx, rbx; SRWLock
0x180070c11  call    cs:__imp_AcquireSRWLockExclusive
0x180070c18  nop     dword ptr [rax+rax+00h]
0x180070c1d  lea     rax, aResclientGrabb; "~ResClient::Grabbed the Lock"
0x180070c24  lea     rcx, [rbp+arg_0]; wchar_t **
0x180070c28  mov     [rbp+arg_0], rax
0x180070c2c  call    ?LogComment@ResClient@Health@Wsp@@SAXAEBQEB_W@Z; Wsp::Health::ResClient::LogComment(wchar_t const * const &)
0x180070c31  cmp     qword ptr [rsi+158h], 0
0x180070c39  lea     rdi, [rsi+0B0h]
0x180070c40  jz      loc_180070D55
0x180070c46  mov     rcx, [rsi+150h]; pti
0x180070c4d  xor     r9d, r9d; msWindowLength
0x180070c50  xor     r8d, r8d; msPeriod
0x180070c53  xor     edx, edx; pftDueTime
0x180070c55  call    cs:__imp_SetThreadpoolTimer
0x180070c5c  nop     dword ptr [rax+rax+00h]
0x180070c61  mov     rcx, [rsi+150h]; pti
0x180070c68  mov     edx, 1; fCancelPendingCallbacks
0x180070c6d  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180070c74  nop     dword ptr [rax+rax+00h]
0x180070c79  mov     rcx, [rsi+150h]; pti
0x180070c80  call    cs:__imp_CloseThreadpoolTimer
0x180070c87  nop     dword ptr [rax+rax+00h]
0x180070c8c  cmp     dword ptr [rdi+70h], 0
0x180070c90  jbe     loc_180070D37
0x180070c96  xorps   xmm0, xmm0
0x180070c99  mov     [rbp+var_28], 0
0x180070ca1  xorps   xmm1, xmm1
0x180070ca4  mov     [rbp+var_10], rdi
0x180070ca8  lea     rcx, [rdi+8]; Table
0x180070cac  lea     rdx, [rbp+RestartKey]; RestartKey
0x180070cb0  movdqu  xmmword ptr [rbp+var_38], xmm0
0x180070cb5  movdqu  xmmword ptr [rbp+RestartKey], xmm1
0x180070cba  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x180070cc1  nop     dword ptr [rax+rax+00h]
0x180070cc6  movsd   xmm1, [rbp+var_10]
0x180070ccb  mov     [rbp+RestartKey+8], rax
0x180070ccf  movups  xmm0, xmmword ptr [rbp+RestartKey]
0x180070cd3  movsd   [rbp+var_28], xmm1
0x180070cd8  movups  xmmword ptr [rbp+var_38], xmm0
0x180070cdc  cmp     [rbp+var_38], 0
0x180070ce1  jz      short loc_180070D2F
0x180070ce3  mov     rcx, [rbp+var_38+8]
0x180070ce7  test    rcx, rcx
0x180070cea  jz      short loc_180070D2F
0x180070cec  mov     rcx, [rcx+8]; this
0x180070cf0  call    ?Release@RefBase@Health@Wsp@@QEAAKXZ; Wsp::Health::RefBase::Release(void)
0x180070cf5  mov     rcx, [rbp+var_28]
0x180070cf9  test    rcx, rcx
0x180070cfc  jz      short loc_180070CDC
0x180070cfe  cmp     [rbp+var_38], 0
0x180070d03  jz      short loc_180070D2F
0x180070d05  cmp     [rbp+var_38+8], 0
0x180070d0a  jz      short loc_180070CDC
0x180070d0c  add     rcx, 8; Table
0x180070d10  lea     rdx, [rbp+var_38]; RestartKey
0x180070d14  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x180070d1b  nop     dword ptr [rax+rax+00h]
0x180070d20  mov     [rbp+var_38+8], rax
0x180070d24  test    rax, rax
0x180070d27  jnz     short loc_180070CDC
0x180070d29  mov     [rbp+var_38], rax
0x180070d2d  jmp     short loc_180070CDC
0x180070d2f  mov     rcx, rdi; TableContext
0x180070d32  call    ?RemoveAll@?$CMapBase@PEA_WPEAVCHealthConnection@Health@Wsp@@@@QEAAXXZ; CMapBase<wchar_t *,Wsp::Health::CHealthConnection *>::RemoveAll(void)
0x180070d37  mov     rcx, [rsi+158h]; hLibModule
0x180070d3e  call    cs:__imp_FreeLibrary
0x180070d45  nop     dword ptr [rax+rax+00h]
0x180070d4a  mov     qword ptr [rsi+158h], 0
0x180070d55  mov     rcx, rbx; SRWLock
0x180070d58  call    cs:__imp_ReleaseSRWLockExclusive
0x180070d5f  nop     dword ptr [rax+rax+00h]
0x180070d64  lea     rax, aResclientRelea; "~ResClient::Released the Lock"
0x180070d6b  lea     rcx, [rbp+arg_0]; wchar_t **
0x180070d6f  mov     [rbp+arg_0], rax
0x180070d73  call    ?LogComment@ResClient@Health@Wsp@@SAXAEBQEB_W@Z; Wsp::Health::ResClient::LogComment(wchar_t const * const &)
0x180070d78  mov     rcx, rdi; TableContext
0x180070d7b  add     rsp, 58h
0x180070d7f  pop     rdi
0x180070d80  pop     rsi
0x180070d81  pop     rbx
0x180070d82  pop     rbp
0x180070d83  jmp     ??1?$CMap@PEA_WPEAVCHealthConnection@Health@Wsp@@@@UEAA@XZ; CMap<wchar_t *,Wsp::Health::CHealthConnection *>::~CMap<wchar_t *,Wsp::Health::CHealthConnection *>(void)
```
