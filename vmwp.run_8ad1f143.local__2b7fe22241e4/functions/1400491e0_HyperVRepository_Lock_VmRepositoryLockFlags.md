# HyperVRepository::Lock(VmRepositoryLockFlags)

- ea: `0x1400491e0`
- end: `0x140049427`
- name: `?Lock@HyperVRepository@@UEAAJW4VmRepositoryLockFlags@@@Z`
- size: `583`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1400b49bc`

## callees

- `0x14002dd88`
- `0x1400491e0`
- `0x14004967c`
- `0x140051fd0`
- `0x14006af58`
- `0x14008c984`
- `0x14009d7cc`
- `0x1400b42d0`
- `0x140132960`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400492ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400493d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400492ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400493d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400493ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400493ac`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140049214`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140049214`

## string_xrefs

- `0x14004929e`: `onecore\vm\common\repository\core\hypervrepository.cpp`
- `0x140049335`: `onecore\vm\common\repository\core\hypervrepository.cpp`
- `0x140049351`: `onecore\vm\common\repository\core\hypervrepository.cpp`
- `0x140049381`: `onecore\vm\common\repository\core\hypervrepository.cpp`
- `0x1400493f6`: `onecore\vm\common\repository\core\hypervrepository.cpp`

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
0x1400491e0  push    rbx
0x1400491e2  push    rsi
0x1400491e3  push    rdi
0x1400491e4  push    r14
0x1400491e6  sub     rsp, 58h
0x1400491ea  mov     rax, cs:__security_cookie
0x1400491f1  xor     rax, rsp
0x1400491f4  mov     [rsp+78h+var_38], rax
0x1400491f9  mov     r14d, edx
0x1400491fc  mov     rbx, rcx
0x1400491ff  cmp     qword ptr [rcx+68h], 0
0x140049204  jz      loc_1400493E9
0x14004920a  mov     eax, [rcx+94h]
0x140049210  mov     [rsp+78h+var_58], eax; int
0x140049214  call    cs:__imp_GetTickCount
0x14004921b  nop     dword ptr [rax+rax+00h]
0x140049220  mov     [rsp+78h+var_54], eax
0x140049224  lea     rdi, [rbx+70h]
0x140049228  mov     rcx, rdi; this
0x14004922b  call    ?AcquireExclusive@VmSlimReaderWriterLock@Vml@@QEAAXXZ; Vml::VmSlimReaderWriterLock::AcquireExclusive(void)
0x140049230  mov     [rsp+78h+var_50], rdi
0x140049235  mov     al, 1
0x140049237  mov     [rsp+78h+var_48], al
0x14004923b  test    al, al
0x14004923d  jz      loc_1400493CF
0x140049243  mov     esi, r14d
0x140049246  and     esi, 1
0x140049249  cmp     dword ptr [rbx+8Ch], 0
0x140049250  jz      short loc_1400492CD
0x140049252  mov     rcx, rbx; this
0x140049255  call    ?ThreadHoldsExclusiveLock@HyperVRepository@@UEBA_NXZ; HyperVRepository::ThreadHoldsExclusiveLock(void)
0x14004925a  test    al, al
0x14004925c  jnz     short loc_1400492CD
0x14004925e  test    esi, esi
0x140049260  jnz     short loc_14004926B
0x140049262  cmp     dword ptr [rbx+8Ch], 1
0x140049269  jz      short loc_1400492CD
0x14004926b  lea     rcx, [rsp+78h+var_58]; this
0x140049270  call    ?GetTimeRemaining@VmTimeoutTimer@Vml@@QEBAKXZ; Vml::VmTimeoutTimer::GetTimeRemaining(void)
0x140049275  mov     r9d, eax; unsigned int
0x140049278  lea     rcx, [rbx+80h]; this
0x14004927f  mov     r8d, 1; int
0x140049285  mov     rdx, rdi; struct Vml::VmSlimReaderWriterLock *
0x140049288  call    ?Sleep@VmConditionVariable@Vml@@QEBAHAEAVVmSlimReaderWriterLock@2@HK@Z; Vml::VmConditionVariable::Sleep(Vml::VmSlimReaderWriterLock &,int,ulong)
0x14004928d  test    eax, eax
0x14004928f  jnz     short loc_140049249
0x140049291  mov     rcx, [rsp+78h]; this
0x140049296  mov     ebx, 800705B4h
0x14004929b  mov     r9d, ebx; char *
0x14004929e  lea     r8, aOnecoreVmCommo_31; "onecore\\vm\\common\\repository\\core\\"...
0x1400492a5  mov     edx, 1E1h; void *
0x1400492aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400492af  nop
0x1400492b0  mov     dword ptr [rdi+8], 0
0x1400492b7  mov     rcx, rdi; SRWLock
0x1400492ba  call    cs:__imp_ReleaseSRWLockExclusive
0x1400492c1  nop     dword ptr [rax+rax+00h]
0x1400492c6  mov     eax, ebx
0x1400492c8  jmp     loc_14004940F
0x1400492cd  cmp     dword ptr [rbx+88h], 0
0x1400492d4  jnz     loc_1400493BE
0x1400492da  mov     [rsp+78h+var_40], 0
0x1400492e2  mov     rcx, [rbx+68h]
0x1400492e6  mov     rax, [rcx]
0x1400492e9  lea     rdx, [rsp+78h+var_40]
0x1400492ee  mov     rax, [rax+108h]
0x1400492f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400492fa  test    eax, eax
0x1400492fc  jns     short loc_140049306
0x1400492fe  xor     eax, eax
0x140049300  mov     [rsp+78h+var_40], eax
0x140049304  jmp     short loc_14004930A
0x140049306  mov     eax, [rsp+78h+var_40]
0x14004930a  test    eax, eax
0x14004930c  jnz     short loc_140049362
0x14004930e  cmp     [rbx+98h], eax
0x140049314  jz      short loc_140049346
0x140049316  mov     rcx, [rbx+68h]
0x14004931a  mov     rax, [rcx]
0x14004931d  mov     rax, [rax+150h]
0x140049324  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140049329  mov     rcx, [rsp+78h]; this
0x14004932e  test    eax, eax
0x140049330  jns     short loc_140049362
0x140049332  mov     r9d, eax; char *
0x140049335  lea     r8, aOnecoreVmCommo_31; "onecore\\vm\\common\\repository\\core\\"...
0x14004933c  mov     edx, 1F6h; void *
0x140049341  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140049346  mov     rcx, [rsp+78h]; this
0x14004934b  mov     r9d, 37h ; '7'; char *
0x140049351  lea     r8, aOnecoreVmCommo_31; "onecore\\vm\\common\\repository\\core\\"...
0x140049358  mov     edx, 1FAh; void *
0x14004935d  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140049362  mov     rcx, [rbx+68h]
0x140049366  mov     rax, [rcx]
0x140049369  mov     dl, sil
0x14004936c  mov     rax, [rax+20h]
0x140049370  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140049375  mov     rcx, [rsp+78h]; this
0x14004937a  test    eax, eax
0x14004937c  jns     short loc_140049392
0x14004937e  mov     r9d, eax; char *
0x140049381  lea     r8, aOnecoreVmCommo_31; "onecore\\vm\\common\\repository\\core\\"...
0x140049388  mov     edx, 1FEh; void *
0x14004938d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140049392  test    esi, esi
0x140049394  jnz     short loc_1400493A2
0x140049396  mov     dword ptr [rbx+8Ch], 1
0x1400493a0  jmp     short loc_1400493BE
0x1400493a2  mov     dword ptr [rbx+8Ch], 0FFFFFFFFh
0x1400493ac  call    cs:__imp_GetCurrentThreadId
0x1400493b3  nop     dword ptr [rax+rax+00h]
0x1400493b8  mov     [rbx+90h], eax
0x1400493be  inc     dword ptr [rbx+88h]
0x1400493c4  xor     al, al
0x1400493c6  mov     [rsp+78h+var_48], al
0x1400493ca  jmp     loc_14004923B
0x1400493cf  mov     dword ptr [rdi+8], 0
0x1400493d6  mov     rcx, rdi; SRWLock
0x1400493d9  call    cs:__imp_ReleaseSRWLockExclusive
0x1400493e0  nop     dword ptr [rax+rax+00h]
0x1400493e5  xor     eax, eax
0x1400493e7  jmp     short loc_14004940F
0x1400493e9  mov     rcx, [rsp+78h]; this
0x1400493ee  mov     ebx, 8000FFFFh
0x1400493f3  mov     r9d, ebx; char *
0x1400493f6  lea     r8, aOnecoreVmCommo_31; "onecore\\vm\\common\\repository\\core\\"...
0x1400493fd  mov     edx, 1C4h; void *
0x140049402  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140049407  mov     eax, ebx
0x140049409  jmp     short loc_14004940F
0x14004940b  mov     eax, [rsp+78h+var_40]
0x14004940f  mov     rcx, [rsp+78h+var_38]
0x140049414  xor     rcx, rsp; StackCookie
0x140049417  call    __security_check_cookie
0x14004941c  add     rsp, 58h
0x140049420  pop     r14
0x140049422  pop     rdi
0x140049423  pop     rsi
0x140049424  pop     rbx
0x140049425  retn
```
