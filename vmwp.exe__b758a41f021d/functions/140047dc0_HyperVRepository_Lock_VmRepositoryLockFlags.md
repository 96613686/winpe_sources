# HyperVRepository::Lock(VmRepositoryLockFlags)

- ea: `0x140047dc0`
- end: `0x140048007`
- name: `?Lock@HyperVRepository@@UEAAJW4VmRepositoryLockFlags@@@Z`
- size: `583`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1400e63d8`

## callees

- `0x14003e2b8`
- `0x140047dc0`
- `0x14004825c`
- `0x140050440`
- `0x14006d540`
- `0x140078628`
- `0x1400a06d0`
- `0x1400ba144`
- `0x14011ea40`
- `0x1402cb010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140047e9a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140047fb9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140047e9a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140047fb9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140047f8c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140047f8c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140047df4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140047df4`

## string_xrefs

- `0x140047e7e`: `onecore\vm\common\repository\core\hypervrepository.cpp`
- `0x140047f15`: `onecore\vm\common\repository\core\hypervrepository.cpp`
- `0x140047f31`: `onecore\vm\common\repository\core\hypervrepository.cpp`
- `0x140047f61`: `onecore\vm\common\repository\core\hypervrepository.cpp`
- `0x140047fd6`: `onecore\vm\common\repository\core\hypervrepository.cpp`

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
0x140047dc0  push    rbx
0x140047dc2  push    rsi
0x140047dc3  push    rdi
0x140047dc4  push    r14
0x140047dc6  sub     rsp, 58h
0x140047dca  mov     rax, cs:__security_cookie
0x140047dd1  xor     rax, rsp
0x140047dd4  mov     [rsp+78h+var_38], rax
0x140047dd9  mov     r14d, edx
0x140047ddc  mov     rbx, rcx
0x140047ddf  cmp     qword ptr [rcx+68h], 0
0x140047de4  jz      loc_140047FC9
0x140047dea  mov     eax, [rcx+94h]
0x140047df0  mov     [rsp+78h+var_58], eax; int
0x140047df4  call    cs:__imp_GetTickCount
0x140047dfb  nop     dword ptr [rax+rax+00h]
0x140047e00  mov     [rsp+78h+var_54], eax
0x140047e04  lea     rdi, [rbx+70h]
0x140047e08  mov     rcx, rdi; this
0x140047e0b  call    ?AcquireExclusive@VmSlimReaderWriterLock@Vml@@QEAAXXZ; Vml::VmSlimReaderWriterLock::AcquireExclusive(void)
0x140047e10  mov     [rsp+78h+var_50], rdi
0x140047e15  mov     al, 1
0x140047e17  mov     [rsp+78h+var_48], al
0x140047e1b  test    al, al
0x140047e1d  jz      loc_140047FAF
0x140047e23  mov     esi, r14d
0x140047e26  and     esi, 1
0x140047e29  cmp     dword ptr [rbx+8Ch], 0
0x140047e30  jz      short loc_140047EAD
0x140047e32  mov     rcx, rbx; this
0x140047e35  call    ?ThreadHoldsExclusiveLock@HyperVRepository@@UEBA_NXZ; HyperVRepository::ThreadHoldsExclusiveLock(void)
0x140047e3a  test    al, al
0x140047e3c  jnz     short loc_140047EAD
0x140047e3e  test    esi, esi
0x140047e40  jnz     short loc_140047E4B
0x140047e42  cmp     dword ptr [rbx+8Ch], 1
0x140047e49  jz      short loc_140047EAD
0x140047e4b  lea     rcx, [rsp+78h+var_58]; this
0x140047e50  call    ?GetTimeRemaining@VmTimeoutTimer@Vml@@QEBAKXZ; Vml::VmTimeoutTimer::GetTimeRemaining(void)
0x140047e55  mov     r9d, eax; unsigned int
0x140047e58  lea     rcx, [rbx+80h]; this
0x140047e5f  mov     r8d, 1; int
0x140047e65  mov     rdx, rdi; struct Vml::VmSlimReaderWriterLock *
0x140047e68  call    ?Sleep@VmConditionVariable@Vml@@QEBAHAEAVVmSlimReaderWriterLock@2@HK@Z; Vml::VmConditionVariable::Sleep(Vml::VmSlimReaderWriterLock &,int,ulong)
0x140047e6d  test    eax, eax
0x140047e6f  jnz     short loc_140047E29
0x140047e71  mov     rcx, [rsp+78h]; this
0x140047e76  mov     ebx, 800705B4h
0x140047e7b  mov     r9d, ebx; char *
0x140047e7e  lea     r8, aOnecoreVmCommo_30; "onecore\\vm\\common\\repository\\core\\"...
0x140047e85  mov     edx, 1E1h; void *
0x140047e8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140047e8f  nop
0x140047e90  mov     dword ptr [rdi+8], 0
0x140047e97  mov     rcx, rdi; SRWLock
0x140047e9a  call    cs:__imp_ReleaseSRWLockExclusive
0x140047ea1  nop     dword ptr [rax+rax+00h]
0x140047ea6  mov     eax, ebx
0x140047ea8  jmp     loc_140047FEF
0x140047ead  cmp     dword ptr [rbx+88h], 0
0x140047eb4  jnz     loc_140047F9E
0x140047eba  mov     [rsp+78h+var_40], 0
0x140047ec2  mov     rcx, [rbx+68h]
0x140047ec6  mov     rax, [rcx]
0x140047ec9  lea     rdx, [rsp+78h+var_40]
0x140047ece  mov     rax, [rax+108h]
0x140047ed5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140047eda  test    eax, eax
0x140047edc  jns     short loc_140047EE6
0x140047ede  xor     eax, eax
0x140047ee0  mov     [rsp+78h+var_40], eax
0x140047ee4  jmp     short loc_140047EEA
0x140047ee6  mov     eax, [rsp+78h+var_40]
0x140047eea  test    eax, eax
0x140047eec  jnz     short loc_140047F42
0x140047eee  cmp     [rbx+98h], eax
0x140047ef4  jz      short loc_140047F26
0x140047ef6  mov     rcx, [rbx+68h]
0x140047efa  mov     rax, [rcx]
0x140047efd  mov     rax, [rax+150h]
0x140047f04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140047f09  mov     rcx, [rsp+78h]; this
0x140047f0e  test    eax, eax
0x140047f10  jns     short loc_140047F42
0x140047f12  mov     r9d, eax; char *
0x140047f15  lea     r8, aOnecoreVmCommo_30; "onecore\\vm\\common\\repository\\core\\"...
0x140047f1c  mov     edx, 1F6h; void *
0x140047f21  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140047f26  mov     rcx, [rsp+78h]; this
0x140047f2b  mov     r9d, 37h ; '7'; char *
0x140047f31  lea     r8, aOnecoreVmCommo_30; "onecore\\vm\\common\\repository\\core\\"...
0x140047f38  mov     edx, 1FAh; void *
0x140047f3d  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140047f42  mov     rcx, [rbx+68h]
0x140047f46  mov     rax, [rcx]
0x140047f49  mov     dl, sil
0x140047f4c  mov     rax, [rax+20h]
0x140047f50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140047f55  mov     rcx, [rsp+78h]; this
0x140047f5a  test    eax, eax
0x140047f5c  jns     short loc_140047F72
0x140047f5e  mov     r9d, eax; char *
0x140047f61  lea     r8, aOnecoreVmCommo_30; "onecore\\vm\\common\\repository\\core\\"...
0x140047f68  mov     edx, 1FEh; void *
0x140047f6d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140047f72  test    esi, esi
0x140047f74  jnz     short loc_140047F82
0x140047f76  mov     dword ptr [rbx+8Ch], 1
0x140047f80  jmp     short loc_140047F9E
0x140047f82  mov     dword ptr [rbx+8Ch], 0FFFFFFFFh
0x140047f8c  call    cs:__imp_GetCurrentThreadId
0x140047f93  nop     dword ptr [rax+rax+00h]
0x140047f98  mov     [rbx+90h], eax
0x140047f9e  inc     dword ptr [rbx+88h]
0x140047fa4  xor     al, al
0x140047fa6  mov     [rsp+78h+var_48], al
0x140047faa  jmp     loc_140047E1B
0x140047faf  mov     dword ptr [rdi+8], 0
0x140047fb6  mov     rcx, rdi; SRWLock
0x140047fb9  call    cs:__imp_ReleaseSRWLockExclusive
0x140047fc0  nop     dword ptr [rax+rax+00h]
0x140047fc5  xor     eax, eax
0x140047fc7  jmp     short loc_140047FEF
0x140047fc9  mov     rcx, [rsp+78h]; this
0x140047fce  mov     ebx, 8000FFFFh
0x140047fd3  mov     r9d, ebx; char *
0x140047fd6  lea     r8, aOnecoreVmCommo_30; "onecore\\vm\\common\\repository\\core\\"...
0x140047fdd  mov     edx, 1C4h; void *
0x140047fe2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140047fe7  mov     eax, ebx
0x140047fe9  jmp     short loc_140047FEF
0x140047feb  mov     eax, [rsp+78h+var_40]
0x140047fef  mov     rcx, [rsp+78h+var_38]
0x140047ff4  xor     rcx, rsp; StackCookie
0x140047ff7  call    __security_check_cookie
0x140047ffc  add     rsp, 58h
0x140048000  pop     r14
0x140048002  pop     rdi
0x140048003  pop     rsi
0x140048004  pop     rbx
0x140048005  retn
```
