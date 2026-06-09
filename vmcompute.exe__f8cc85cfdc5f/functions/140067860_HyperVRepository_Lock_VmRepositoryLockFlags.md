# HyperVRepository::Lock(VmRepositoryLockFlags)

- ea: `0x140067860`
- end: `0x140067aa7`
- name: `?Lock@HyperVRepository@@UEAAJW4VmRepositoryLockFlags@@@Z`
- size: `583`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1401dfa44`

## callees

- `0x140022ca0`
- `0x140067860`
- `0x1400a6578`
- `0x1400c40e0`
- `0x1400c4154`
- `0x1400f92ac`
- `0x1400fff1c`
- `0x1401332f0`
- `0x1402429c0`
- `0x1402c4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14006793a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140067a59`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14006793a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140067a59`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140067a2c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140067a2c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140067894`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140067894`

## string_xrefs

- `0x14006791e`: `onecore\vm\common\repository\core\hypervrepository.cpp`
- `0x1400679b5`: `onecore\vm\common\repository\core\hypervrepository.cpp`
- `0x1400679d1`: `onecore\vm\common\repository\core\hypervrepository.cpp`
- `0x140067a01`: `onecore\vm\common\repository\core\hypervrepository.cpp`
- `0x140067a76`: `onecore\vm\common\repository\core\hypervrepository.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HyperVRepository::Lock(__int64 a1, char a2)
{
  char v4; // al
  unsigned int TimeRemaining; // eax
  const char *v6; // r9
  __int64 result; // rax
  __int64 v8; // rdx
  int v9; // eax
  int v10; // eax
  int v11; // eax
  unsigned int v12[2]; // [rsp+20h] [rbp-58h] BYREF
  __int64 v13; // [rsp+28h] [rbp-50h]
  char v14; // [rsp+30h] [rbp-48h]
  int v15; // [rsp+38h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  try
  {
    if ( *(_QWORD *)(a1 + 104) )
    {
      v12[0] = *(_DWORD *)(a1 + 148);
      v12[1] = GetTickCount();
      Vml::VmSlimReaderWriterLock::AcquireExclusive((Vml::VmSlimReaderWriterLock *)(a1 + 112));
      v13 = a1 + 112;
      v4 = 1;
      v14 = 1;
      while ( v4 )
      {
        while ( *(_DWORD *)(a1 + 140)
             && !HyperVRepository::ThreadHoldsExclusiveLock((HyperVRepository *)a1)
             && ((a2 & 1) != 0 || *(_DWORD *)(a1 + 140) != 1) )
        {
          TimeRemaining = Vml::VmTimeoutTimer::GetTimeRemaining((Vml::VmTimeoutTimer *)v12);
          if ( !Vml::VmConditionVariable::Sleep(
                  (Vml::VmConditionVariable *)(a1 + 128),
                  (struct Vml::VmSlimReaderWriterLock *)(a1 + 112),
                  1,
                  TimeRemaining) )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1E1,
              (unsigned int)"onecore\\vm\\common\\repository\\core\\hypervrepository.cpp",
              (const char *)0x800705B4LL,
              v12[0]);
            *(_DWORD *)(a1 + 120) = 0;
            ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 112));
            return 2147943860LL;
          }
        }
        if ( !*(_DWORD *)(a1 + 136) )
        {
          v15 = 0;
          if ( (*(int (__fastcall **)(_QWORD, int *))(**(_QWORD **)(a1 + 104) + 264LL))(*(_QWORD *)(a1 + 104), &v15) >= 0 )
          {
            v9 = v15;
          }
          else
          {
            v9 = 0;
            v15 = 0;
          }
          if ( !v9 )
          {
            if ( !*(_DWORD *)(a1 + 152) )
              wil::details::in1diag3::Throw_Win32(
                retaddr,
                (void *)0x1FA,
                (unsigned int)"onecore\\vm\\common\\repository\\core\\hypervrepository.cpp",
                (const char *)0x37,
                v12[0]);
            v10 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 104) + 336LL))(*(_QWORD *)(a1 + 104));
            if ( v10 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x1F6,
                (unsigned int)"onecore\\vm\\common\\repository\\core\\hypervrepository.cpp",
                (const char *)(unsigned int)v10,
                v12[0]);
          }
          LOBYTE(v8) = a2 & 1;
          v11 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 104) + 32LL))(*(_QWORD *)(a1 + 104), v8);
          if ( v11 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x1FE,
              (unsigned int)"onecore\\vm\\common\\repository\\core\\hypervrepository.cpp",
              (const char *)(unsigned int)v11,
              v12[0]);
          if ( (a2 & 1) != 0 )
          {
            *(_DWORD *)(a1 + 140) = -1;
            *(_DWORD *)(a1 + 144) = GetCurrentThreadId();
          }
          else
          {
            *(_DWORD *)(a1 + 140) = 1;
          }
        }
        ++*(_DWORD *)(a1 + 136);
        v4 = 0;
        v14 = 0;
      }
      *(_DWORD *)(a1 + 120) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 112));
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C4,
        (unsigned int)"onecore\\vm\\common\\repository\\core\\hypervrepository.cpp",
        (const char *)0x8000FFFFLL,
        v12[0]);
      result = 2147549183LL;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x213,
                           (unsigned int)"onecore\\vm\\common\\repository\\core\\hypervrepository.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x140067860  push    rbx
0x140067862  push    rsi
0x140067863  push    rdi
0x140067864  push    r14
0x140067866  sub     rsp, 58h
0x14006786a  mov     rax, cs:__security_cookie
0x140067871  xor     rax, rsp
0x140067874  mov     [rsp+78h+var_38], rax
0x140067879  mov     r14d, edx
0x14006787c  mov     rbx, rcx
0x14006787f  cmp     qword ptr [rcx+68h], 0
0x140067884  jz      loc_140067A69
0x14006788a  mov     eax, [rcx+94h]
0x140067890  mov     [rsp+78h+var_58], eax; int
0x140067894  call    cs:__imp_GetTickCount
0x14006789b  nop     dword ptr [rax+rax+00h]
0x1400678a0  mov     [rsp+78h+var_54], eax
0x1400678a4  lea     rdi, [rbx+70h]
0x1400678a8  mov     rcx, rdi; this
0x1400678ab  call    ?AcquireExclusive@VmSlimReaderWriterLock@Vml@@QEAAXXZ; Vml::VmSlimReaderWriterLock::AcquireExclusive(void)
0x1400678b0  mov     [rsp+78h+var_50], rdi
0x1400678b5  mov     al, 1
0x1400678b7  mov     [rsp+78h+var_48], al
0x1400678bb  test    al, al
0x1400678bd  jz      loc_140067A4F
0x1400678c3  mov     esi, r14d
0x1400678c6  and     esi, 1
0x1400678c9  cmp     dword ptr [rbx+8Ch], 0
0x1400678d0  jz      short loc_14006794D
0x1400678d2  mov     rcx, rbx; this
0x1400678d5  call    ?ThreadHoldsExclusiveLock@HyperVRepository@@UEBA_NXZ; HyperVRepository::ThreadHoldsExclusiveLock(void)
0x1400678da  test    al, al
0x1400678dc  jnz     short loc_14006794D
0x1400678de  test    esi, esi
0x1400678e0  jnz     short loc_1400678EB
0x1400678e2  cmp     dword ptr [rbx+8Ch], 1
0x1400678e9  jz      short loc_14006794D
0x1400678eb  lea     rcx, [rsp+78h+var_58]; this
0x1400678f0  call    ?GetTimeRemaining@VmTimeoutTimer@Vml@@QEBAKXZ; Vml::VmTimeoutTimer::GetTimeRemaining(void)
0x1400678f5  mov     r9d, eax; unsigned int
0x1400678f8  lea     rcx, [rbx+80h]; this
0x1400678ff  mov     r8d, 1; int
0x140067905  mov     rdx, rdi; struct Vml::VmSlimReaderWriterLock *
0x140067908  call    ?Sleep@VmConditionVariable@Vml@@QEBAHAEAVVmSlimReaderWriterLock@2@HK@Z; Vml::VmConditionVariable::Sleep(Vml::VmSlimReaderWriterLock &,int,ulong)
0x14006790d  test    eax, eax
0x14006790f  jnz     short loc_1400678C9
0x140067911  mov     rcx, [rsp+78h]; this
0x140067916  mov     ebx, 800705B4h
0x14006791b  mov     r9d, ebx; char *
0x14006791e  lea     r8, aOnecoreVmCommo_18; "onecore\\vm\\common\\repository\\core\\"...
0x140067925  mov     edx, 1E1h; void *
0x14006792a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006792f  nop
0x140067930  mov     dword ptr [rdi+8], 0
0x140067937  mov     rcx, rdi; SRWLock
0x14006793a  call    cs:__imp_ReleaseSRWLockExclusive
0x140067941  nop     dword ptr [rax+rax+00h]
0x140067946  mov     eax, ebx
0x140067948  jmp     loc_140067A8F
0x14006794d  cmp     dword ptr [rbx+88h], 0
0x140067954  jnz     loc_140067A3E
0x14006795a  mov     [rsp+78h+var_40], 0
0x140067962  mov     rcx, [rbx+68h]
0x140067966  mov     rax, [rcx]
0x140067969  lea     rdx, [rsp+78h+var_40]
0x14006796e  mov     rax, [rax+108h]
0x140067975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006797a  test    eax, eax
0x14006797c  jns     short loc_140067986
0x14006797e  xor     eax, eax
0x140067980  mov     [rsp+78h+var_40], eax
0x140067984  jmp     short loc_14006798A
0x140067986  mov     eax, [rsp+78h+var_40]
0x14006798a  test    eax, eax
0x14006798c  jnz     short loc_1400679E2
0x14006798e  cmp     [rbx+98h], eax
0x140067994  jz      short loc_1400679C6
0x140067996  mov     rcx, [rbx+68h]
0x14006799a  mov     rax, [rcx]
0x14006799d  mov     rax, [rax+150h]
0x1400679a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400679a9  mov     rcx, [rsp+78h]; this
0x1400679ae  test    eax, eax
0x1400679b0  jns     short loc_1400679E2
0x1400679b2  mov     r9d, eax; char *
0x1400679b5  lea     r8, aOnecoreVmCommo_18; "onecore\\vm\\common\\repository\\core\\"...
0x1400679bc  mov     edx, 1F6h; void *
0x1400679c1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400679c6  mov     rcx, [rsp+78h]; this
0x1400679cb  mov     r9d, 37h ; '7'; char *
0x1400679d1  lea     r8, aOnecoreVmCommo_18; "onecore\\vm\\common\\repository\\core\\"...
0x1400679d8  mov     edx, 1FAh; void *
0x1400679dd  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400679e2  mov     rcx, [rbx+68h]
0x1400679e6  mov     rax, [rcx]
0x1400679e9  mov     dl, sil
0x1400679ec  mov     rax, [rax+20h]
0x1400679f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400679f5  mov     rcx, [rsp+78h]; this
0x1400679fa  test    eax, eax
0x1400679fc  jns     short loc_140067A12
0x1400679fe  mov     r9d, eax; char *
0x140067a01  lea     r8, aOnecoreVmCommo_18; "onecore\\vm\\common\\repository\\core\\"...
0x140067a08  mov     edx, 1FEh; void *
0x140067a0d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140067a12  test    esi, esi
0x140067a14  jnz     short loc_140067A22
0x140067a16  mov     dword ptr [rbx+8Ch], 1
0x140067a20  jmp     short loc_140067A3E
0x140067a22  mov     dword ptr [rbx+8Ch], 0FFFFFFFFh
0x140067a2c  call    cs:__imp_GetCurrentThreadId
0x140067a33  nop     dword ptr [rax+rax+00h]
0x140067a38  mov     [rbx+90h], eax
0x140067a3e  inc     dword ptr [rbx+88h]
0x140067a44  xor     al, al
0x140067a46  mov     [rsp+78h+var_48], al
0x140067a4a  jmp     loc_1400678BB
0x140067a4f  mov     dword ptr [rdi+8], 0
0x140067a56  mov     rcx, rdi; SRWLock
0x140067a59  call    cs:__imp_ReleaseSRWLockExclusive
0x140067a60  nop     dword ptr [rax+rax+00h]
0x140067a65  xor     eax, eax
0x140067a67  jmp     short loc_140067A8F
0x140067a69  mov     rcx, [rsp+78h]; this
0x140067a6e  mov     ebx, 8000FFFFh
0x140067a73  mov     r9d, ebx; char *
0x140067a76  lea     r8, aOnecoreVmCommo_18; "onecore\\vm\\common\\repository\\core\\"...
0x140067a7d  mov     edx, 1C4h; void *
0x140067a82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140067a87  mov     eax, ebx
0x140067a89  jmp     short loc_140067A8F
0x140067a8b  mov     eax, [rsp+78h+var_40]
0x140067a8f  mov     rcx, [rsp+78h+var_38]
0x140067a94  xor     rcx, rsp; StackCookie
0x140067a97  call    __security_check_cookie
0x140067a9c  add     rsp, 58h
0x140067aa0  pop     r14
0x140067aa2  pop     rdi
0x140067aa3  pop     rsi
0x140067aa4  pop     rbx
0x140067aa5  retn
```
