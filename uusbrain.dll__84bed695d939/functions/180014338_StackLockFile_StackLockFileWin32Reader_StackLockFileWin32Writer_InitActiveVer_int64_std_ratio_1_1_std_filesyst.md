# _StackLockFile<StackLockFileWin32Reader,StackLockFileWin32Writer>::InitActiveVer<__int64,std::ratio<1,1>>(std::filesystem::path const &,std::chrono::duration<__int64,std::ratio<1,1>> const &,StackLockFileReader &)

- ea: `0x180014338`
- end: `0x180014558`
- name: `??$InitActiveVer@_JU?$ratio@$00$00@std@@@?$_StackLockFile@UStackLockFileWin32Reader@@UStackLockFileWin32Writer@@@@CA_KAEBVpath@filesystem@std@@AEBV?$duration@_JU?$ratio@$00$00@std@@@chrono@3@AEAUStackLockFileReader@@@Z`
- size: `544`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x18000e888`

## callees

- `0x180006614`
- `0x1800096d4`
- `0x180014338`
- `0x18001be84`
- `0x180023960`
- `0x180025610`
- `0x180047a30`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800144ce`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800144ce`

## string_xrefs

- `0x180014539`: `Max retries (%u) / timeout (%ums) when attempting to read UUS version file.`
- `0x1800144ee`: `Somehow we didn't create a read file handle.`

## pseudocode

```c
__int64 __fastcall _StackLockFile<StackLockFileWin32Reader,StackLockFileWin32Writer>::InitActiveVer<__int64,std::ratio<1,1>>(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  __int64 v6; // rbx
  unsigned int v7; // esi
  __int64 v8; // rdi
  _QWORD *v9; // rax
  __int64 result; // rax
  __int64 v12; // rdi
  __int64 v13; // rcx
  __int64 v14; // rdx
  const char *v15; // r9
  const char *v16; // r9
  int v17; // edx
  const char *v18; // [rsp+20h] [rbp-68h]
  char *v19; // [rsp+28h] [rbp-60h]
  int v20; // [rsp+30h] [rbp-58h]
  __int64 v21; // [rsp+40h] [rbp-48h] BYREF
  __int64 v22; // [rsp+48h] [rbp-40h] BYREF
  __int64 v23; // [rsp+50h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  __int64 v25; // [rsp+A8h] [rbp+20h] BYREF

  std::chrono::steady_clock::now(&v22);
  v6 = 0;
  v25 = 0;
  v7 = 0;
  v8 = 0;
  while ( !(**(unsigned __int8 (__fastcall ***)(__int64, __int64))a3)(a3, a1) )
  {
    if ( v8 >= 1000LL * *a2 )
    {
      std::chrono::duration<__int64,std::ratio<1,1000>>::count(&v25);
      v16 = (const char *)(unsigned int)wil::verify_hresult<long>(2147942658LL);
      v20 = v17;
      LODWORD(v19) = v7;
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0xEB,
        (unsigned int)"C:\\__w\\1\\s\\src\\brain\\lib\\StackLockFile.hpp",
        v16,
        (int)"Max retries (%u) / timeout (%ums) when attempting to read UUS version file.",
        v19,
        v20);
    }
    std::chrono::steady_clock::now(&v23);
    if ( v23 >= 0x7FFFFFFFFA0A1EFFLL )
      v12 = 0x7FFFFFFFFFFFFFFFLL;
    else
      v12 = v23 + 100000000;
    while ( 1 )
    {
      std::chrono::steady_clock::now(&v21);
      if ( v21 >= v12 )
        break;
      v13 = v12 - v21;
      if ( v12 - v21 <= 86400000000000LL )
      {
        v14 = v13 / 1000000;
        if ( 1000000 * (v13 / 1000000) < v13 )
          LODWORD(v14) = v14 + 1;
      }
      else
      {
        LODWORD(v14) = 86400000;
      }
      HIBYTE(v25) = 0;
      *(_WORD *)((char *)&v25 + 5) = 0;
      Sleep(v14);
    }
    v6 += 100;
    v8 = v6;
    v25 = v6;
    ++v7;
  }
  if ( v7 )
  {
    v9 = (_QWORD *)std::chrono::steady_clock::now(&v25);
    uus::UndockedUpdateTelemetry::UusReadVersionRetried(v7, (*v9 - v22) / 1000000, 0);
  }
  if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a3 + 8LL))(a3) )
  {
    v15 = (const char *)(unsigned int)wil::verify_hresult<long>(2147549183LL);
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0xFD,
      (unsigned int)"C:\\__w\\1\\s\\src\\brain\\lib\\StackLockFile.hpp",
      v15,
      (int)"Somehow we didn't create a read file handle.",
      v19);
  }
  try
  {
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a3 + 16LL))(a3);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtExceptionMsg(
      retaddr,
      (void *)0x110,
      (unsigned int)"C:\\__w\\1\\s\\src\\brain\\lib\\StackLockFile.hpp",
      "The lock file has an invalid version in it.",
      v18);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180014338  mov     [rsp+arg_0], rbx
0x18001433d  mov     [rsp+arg_8], rsi
0x180014342  push    rdi
0x180014343  push    r12
0x180014345  push    r13
0x180014347  push    r14
0x180014349  push    r15
0x18001434b  sub     rsp, 60h
0x18001434f  mov     r14, r8
0x180014352  mov     r15, rdx
0x180014355  mov     r12, rcx
0x180014358  lea     rcx, [rsp+88h+var_40]
0x18001435d  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x180014362  xor     ebx, ebx
0x180014364  mov     [rsp+88h+arg_18], rbx
0x18001436c  xor     esi, esi
0x18001436e  xor     edi, edi
0x180014370  mov     r13, 431BDE82D7B634DBh
0x18001437a  mov     [rsp+88h+arg_10], esi
0x180014381  mov     rax, [r14]
0x180014384  mov     rdx, r12
0x180014387  mov     rcx, r14
0x18001438a  mov     rax, [rax]
0x18001438d  call    _guard_dispatch_icall
0x180014392  test    al, al
0x180014394  jz      short loc_180014412
0x180014396  test    esi, esi
0x180014398  jz      short loc_1800143CE
0x18001439a  lea     rcx, [rsp+88h+arg_18]
0x1800143a2  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x1800143a7  mov     rdx, [rax]
0x1800143aa  sub     rdx, [rsp+88h+var_40]
0x1800143af  mov     rax, r13
0x1800143b2  imul    rdx
0x1800143b5  sar     rdx, 12h
0x1800143b9  mov     rax, rdx
0x1800143bc  shr     rax, 3Fh
0x1800143c0  add     rdx, rax; __int64
0x1800143c3  xor     r8d, r8d; int
0x1800143c6  mov     ecx, esi; unsigned int
0x1800143c8  call    ?UusReadVersionRetried@UndockedUpdateTelemetry@uus@@SAXI_JJ@Z; uus::UndockedUpdateTelemetry::UusReadVersionRetried(uint,__int64,long)
0x1800143cd  nop
0x1800143ce  mov     rax, [r14]
0x1800143d1  mov     rcx, r14
0x1800143d4  mov     rax, [rax+8]
0x1800143d8  call    _guard_dispatch_icall
0x1800143dd  test    al, al
0x1800143df  jz      loc_1800144D9
0x1800143e5  mov     rax, [r14]
0x1800143e8  mov     rcx, r14
0x1800143eb  mov     rax, [rax+10h]
0x1800143ef  call    _guard_dispatch_icall
0x1800143f4  jmp     short loc_1800143F8
0x1800143f6  xor     eax, eax
0x1800143f8  lea     r11, [rsp+88h+var_28]
0x1800143fd  mov     rbx, [r11+30h]
0x180014401  mov     rsi, [r11+38h]
0x180014405  mov     rsp, r11
0x180014408  pop     r15
0x18001440a  pop     r14
0x18001440c  pop     r13
0x18001440e  pop     r12
0x180014410  pop     rdi
0x180014411  retn
0x180014412  imul    rax, [r15], 3E8h
0x180014419  cmp     rdi, rax
0x18001441c  jge     loc_18001450C
0x180014422  lea     rcx, [rsp+88h+var_38]
0x180014427  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x18001442c  mov     rax, 7FFFFFFFFA0A1EFFh
0x180014436  mov     rdi, [rsp+88h+var_38]
0x18001443b  cmp     rdi, rax
0x18001443e  jge     short loc_180014449
0x180014440  add     rdi, 5F5E100h
0x180014447  jmp     short loc_180014453
0x180014449  mov     rdi, 7FFFFFFFFFFFFFFFh
0x180014453  lea     rcx, [rsp+88h+var_48]
0x180014458  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x18001445d  cmp     [rsp+88h+var_48], rdi
0x180014462  jl      short loc_18001447A
0x180014464  add     rbx, 64h ; 'd'
0x180014468  mov     rdi, rbx
0x18001446b  mov     [rsp+88h+arg_18], rbx
0x180014473  inc     esi
0x180014475  jmp     loc_18001437A
0x18001447a  mov     rcx, rdi
0x18001447d  sub     rcx, [rsp+88h+var_48]
0x180014482  mov     rax, 4E94914F0000h
0x18001448c  cmp     rcx, rax
0x18001448f  jle     short loc_180014498
0x180014491  mov     edx, 5265C00h
0x180014496  jmp     short loc_1800144BB
0x180014498  mov     rax, r13
0x18001449b  imul    rcx
0x18001449e  sar     rdx, 12h
0x1800144a2  mov     rax, rdx
0x1800144a5  shr     rax, 3Fh
0x1800144a9  add     rdx, rax
0x1800144ac  imul    rax, rdx, 0F4240h
0x1800144b3  cmp     rax, rcx
0x1800144b6  jge     short loc_1800144BB
0x1800144b8  inc     rdx
0x1800144bb  xor     eax, eax
0x1800144bd  mov     byte ptr [rsp+88h+arg_18+7], al
0x1800144c4  mov     word ptr [rsp+88h+arg_18+5], ax
0x1800144cc  mov     ecx, edx; dwMilliseconds
0x1800144ce  call    cs:__imp_Sleep
0x1800144d4  jmp     loc_180014453
0x1800144d9  mov     ecx, 8000FFFFh
0x1800144de  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800144e3  mov     r9d, eax; char *
0x1800144e6  mov     rcx, [rsp+88h]; this
0x1800144ee  lea     rax, aSomehowWeDidnT; "Somehow we didn't create a read file ha"...
0x1800144f5  mov     qword ptr [rsp+88h+var_68], rax; int
0x1800144fa  lea     r8, aCW1SSrcBrainLi_3; "C:\\__w\\1\\s\\src\\brain\\lib\\StackLo"...
0x180014501  mov     edx, 0FDh; void *
0x180014506  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001450c  lea     rcx, [rsp+88h+arg_18]
0x180014514  call    ?count@?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@std@@QEBA_JXZ; std::chrono::duration<__int64,std::ratio<1,1000>>::count(void)
0x180014519  mov     rdx, rax
0x18001451c  mov     ecx, 80070102h
0x180014521  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180014526  mov     r9d, eax; char *
0x180014529  mov     rcx, [rsp+88h]; this
0x180014531  mov     [rsp+88h+var_58], edx
0x180014535  mov     dword ptr [rsp+88h+var_60], esi; char *
0x180014539  lea     rax, aMaxRetriesUTim; "Max retries (%u) / timeout (%ums) when "...
0x180014540  mov     qword ptr [rsp+88h+var_68], rax; int
0x180014545  lea     r8, aCW1SSrcBrainLi_3; "C:\\__w\\1\\s\\src\\brain\\lib\\StackLo"...
0x18001454c  mov     edx, 0EBh; void *
0x180014551  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
