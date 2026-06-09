# ServiceMain_Impl(ulong,wchar_t * * const)

- ea: `0x180034f00`
- end: `0x180035252`
- name: `?ServiceMain_Impl@@YAXKQEAPEA_W@Z`
- size: `850`
- prototype: `void __fastcall(int, LPCWSTR *)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, installer_update`

## callees

- `0x1800112d0`
- `0x18001b064`
- `0x18002e168`
- `0x1800349a8`
- `0x180034f00`
- `0x1800353e0`
- `0x180036b80`
- `0x18006ea28`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180034fde`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180034fde`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180034fed`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800350cb`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180034fed`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800350cb`

## string_xrefs

- `0x1800351bc`: `C:\__w\1\s\src\orchestrator\core\USOSvc\Service.cpp`
- `0x18003520d`: `C:\__w\1\s\src\orchestrator\core\USOSvc\Service.cpp`
- `0x180035240`: `C:\__w\1\s\src\orchestrator\core\USOSvc\Service.cpp`
- `0x1800351cd`: `UsoSvc setting service state to: SERVICE_STOPPED`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
void __fastcall ServiceMain_Impl(int a1, LPCWSTR *a2)
{
  LPCWSTR *v2; // r15
  int v3; // r14d
  _QWORD *System; // rax
  _QWORD *v5; // rax
  char v6; // si
  volatile signed __int32 *v7; // rdi
  volatile signed __int32 *v8; // rdi
  int i; // ebx
  const char *v10; // r9
  _QWORD *v11; // rax
  _QWORD *v12; // rax
  char v13; // si
  volatile signed __int32 *v14; // rdi
  volatile signed __int32 *v15; // rdi
  int j; // esi
  _QWORD *v17; // rax
  _QWORD *v18; // rax
  char v19; // r12
  volatile signed __int32 *v20; // rdi
  volatile signed __int32 *v21; // rdi
  int v22; // eax
  unsigned int v23; // ebx
  int v24; // eax
  _QWORD v26[2]; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v27[8]; // [rsp+40h] [rbp-38h] BYREF
  volatile signed __int32 *v28; // [rsp+48h] [rbp-30h]
  _BYTE v29[8]; // [rsp+50h] [rbp-28h] BYREF
  volatile signed __int32 *v30; // [rsp+58h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  try
  {
    v2 = a2;
    v3 = a1;
    v26[0] = a2;
    System = (_QWORD *)SystemInterface::Service::GetSystem(v29);
    v5 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*System + 48LL))(*System, v27);
    v6 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 48LL))(*v5);
    v7 = v28;
    if ( v28 )
    {
      if ( _InterlockedExchangeAdd(v28 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
        if ( !_InterlockedDecrement(v7 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
      }
    }
    v8 = v30;
    if ( v30 )
    {
      if ( !_InterlockedDecrement(v30 + 2) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
        if ( !_InterlockedDecrement(v8 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
      }
    }
    if ( v6 )
    {
      for ( i = 0; i < 200; ++i )
      {
        if ( IsDebuggerPresent() )
          break;
        Sleep(0x3E8u);
      }
    }
    else
    {
      v11 = (_QWORD *)SystemInterface::Service::GetSystem(v27);
      v12 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v11 + 48LL))(*v11, v29);
      v13 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v12 + 56LL))(*v12);
      v14 = v30;
      if ( v30 )
      {
        if ( _InterlockedExchangeAdd(v30 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
          if ( !_InterlockedDecrement(v14 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
        }
      }
      v15 = v28;
      if ( v28 )
      {
        if ( !_InterlockedDecrement(v28 + 2) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
          if ( !_InterlockedDecrement(v15 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
        }
      }
      if ( v13 )
      {
        for ( j = 0; j < 200; ++j )
        {
          Sleep(0x3E8u);
          v17 = (_QWORD *)SystemInterface::Service::GetSystem(v27);
          v18 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v17 + 48LL))(*v17, v29);
          v19 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v18 + 56LL))(*v18);
          v20 = v30;
          if ( v30 )
          {
            if ( _InterlockedExchangeAdd(v30 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
              if ( !_InterlockedDecrement(v20 + 3) )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
            }
          }
          v21 = v28;
          if ( v28 )
          {
            if ( !_InterlockedDecrement(v28 + 2) )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
              if ( !_InterlockedDecrement(v21 + 3) )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
            }
          }
          if ( !v19 )
            break;
        }
      }
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x42D,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\Service.cpp",
      v10);
    v2 = (LPCWSTR *)v26[0];
    v3 = a1;
  }
  if ( !v3 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x430,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\Service.cpp",
      (const char *)0x80070057LL,
      a1);
  try
  {
    v22 = ServiceMain_Internal(*v2);
    v23 = v22;
    if ( v22 >= 0 )
    {
      v24 = ServiceHelpers::CheckCallOnStart();
      if ( v24 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x438,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\Service.cpp",
          (const char *)(unsigned int)v24,
          a1);
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x435,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\Service.cpp",
        (const char *)(unsigned int)v22,
        a1);
      v26[0] = L"UsoSvc setting service state to: SERVICE_STOPPED";
      v26[1] = 48;
      SystemInterface::Log<>(v26);
      ServiceHelpers::UpdateServiceStatus(1u, v23, 0);
    }
  }
  catch ( ... )
  {
    v26[0] = OpenSCManagerW(0, 0, 1u);
    if ( !v26[0] && GetLastError() == 1115 )
      return;
    throw;
  }
}

```

## disassembly

```asm
0x180034f00  mov     rax, rsp
0x180034f03  mov     [rax+8], rbx
0x180034f07  mov     [rax+18h], rsi
0x180034f0b  mov     [rax+20h], rdi
0x180034f0f  push    r12
0x180034f11  push    r14
0x180034f13  push    r15
0x180034f15  sub     rsp, 60h
0x180034f19  mov     r15, rdx
0x180034f1c  mov     r14d, ecx
0x180034f1f  mov     [rsp+78h+var_58], ecx
0x180034f23  mov     [rsp+78h+var_48], rdx
0x180034f28  lea     rcx, [rax-28h]
0x180034f2c  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x180034f31  nop
0x180034f32  mov     rcx, [rax]
0x180034f35  mov     rax, [rcx]
0x180034f38  lea     rdx, [rsp+78h+var_38]
0x180034f3d  mov     rax, [rax+30h]
0x180034f41  call    _guard_dispatch_icall
0x180034f46  nop
0x180034f47  mov     rcx, [rax]
0x180034f4a  mov     rax, [rcx]
0x180034f4d  mov     rax, [rax+30h]
0x180034f51  call    _guard_dispatch_icall
0x180034f56  mov     sil, al
0x180034f59  mov     rdi, [rsp+78h+var_30]
0x180034f5e  or      ebx, 0FFFFFFFFh
0x180034f61  test    rdi, rdi
0x180034f64  jz      short loc_180034F9A
0x180034f66  mov     ecx, ebx
0x180034f68  lock xadd [rdi+8], ecx
0x180034f6d  add     ecx, ebx
0x180034f6f  jnz     short loc_180034F9A
0x180034f71  mov     rax, [rdi]
0x180034f74  mov     rcx, rdi
0x180034f77  mov     rax, [rax]
0x180034f7a  call    _guard_dispatch_icall
0x180034f7f  mov     eax, ebx
0x180034f81  lock xadd [rdi+0Ch], eax
0x180034f86  add     eax, ebx
0x180034f88  jnz     short loc_180034F9A
0x180034f8a  mov     rax, [rdi]
0x180034f8d  mov     rcx, rdi
0x180034f90  mov     rax, [rax+8]
0x180034f94  call    _guard_dispatch_icall
0x180034f99  nop
0x180034f9a  mov     rdi, [rsp+78h+var_20]
0x180034f9f  test    rdi, rdi
0x180034fa2  jz      short loc_180034FD7
0x180034fa4  mov     eax, ebx
0x180034fa6  lock xadd [rdi+8], eax
0x180034fab  add     eax, ebx
0x180034fad  jnz     short loc_180034FD7
0x180034faf  mov     rax, [rdi]
0x180034fb2  mov     rcx, rdi
0x180034fb5  mov     rax, [rax]
0x180034fb8  call    _guard_dispatch_icall
0x180034fbd  mov     eax, ebx
0x180034fbf  lock xadd [rdi+0Ch], eax
0x180034fc4  add     eax, ebx
0x180034fc6  jnz     short loc_180034FD7
0x180034fc8  mov     rax, [rdi]
0x180034fcb  mov     rcx, rdi
0x180034fce  mov     rax, [rax+8]
0x180034fd2  call    _guard_dispatch_icall
0x180034fd7  test    sil, sil
0x180034fda  jz      short loc_180035002
0x180034fdc  xor     ebx, ebx
0x180034fde  call    cs:__imp_IsDebuggerPresent
0x180034fe4  test    eax, eax
0x180034fe6  jnz     short loc_180034FFD
0x180034fe8  mov     ecx, 3E8h; dwMilliseconds
0x180034fed  call    cs:__imp_Sleep
0x180034ff3  inc     ebx
0x180034ff5  cmp     ebx, 0C8h
0x180034ffb  jl      short loc_180034FDE
0x180034ffd  jmp     loc_180035198
0x180035002  lea     rcx, [rsp+78h+var_38]
0x180035007  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x18003500c  nop
0x18003500d  mov     rcx, [rax]
0x180035010  mov     rax, [rcx]
0x180035013  lea     rdx, [rsp+78h+var_28]
0x180035018  mov     rax, [rax+30h]
0x18003501c  call    _guard_dispatch_icall
0x180035021  nop
0x180035022  mov     rcx, [rax]
0x180035025  mov     rax, [rcx]
0x180035028  mov     rax, [rax+38h]
0x18003502c  call    _guard_dispatch_icall
0x180035031  mov     sil, al
0x180035034  mov     rdi, [rsp+78h+var_20]
0x180035039  test    rdi, rdi
0x18003503c  jz      short loc_180035072
0x18003503e  mov     ecx, ebx
0x180035040  lock xadd [rdi+8], ecx
0x180035045  add     ecx, ebx
0x180035047  jnz     short loc_180035072
0x180035049  mov     rax, [rdi]
0x18003504c  mov     rcx, rdi
0x18003504f  mov     rax, [rax]
0x180035052  call    _guard_dispatch_icall
0x180035057  mov     eax, ebx
0x180035059  lock xadd [rdi+0Ch], eax
0x18003505e  add     eax, ebx
0x180035060  jnz     short loc_180035072
0x180035062  mov     rax, [rdi]
0x180035065  mov     rcx, rdi
0x180035068  mov     rax, [rax+8]
0x18003506c  call    _guard_dispatch_icall
0x180035071  nop
0x180035072  mov     rdi, [rsp+78h+var_30]
0x180035077  test    rdi, rdi
0x18003507a  jz      short loc_1800350AF
0x18003507c  mov     eax, ebx
0x18003507e  lock xadd [rdi+8], eax
0x180035083  add     eax, ebx
0x180035085  jnz     short loc_1800350AF
0x180035087  mov     rax, [rdi]
0x18003508a  mov     rcx, rdi
0x18003508d  mov     rax, [rax]
0x180035090  call    _guard_dispatch_icall
0x180035095  mov     eax, ebx
0x180035097  lock xadd [rdi+0Ch], eax
0x18003509c  add     eax, ebx
0x18003509e  jnz     short loc_1800350AF
0x1800350a0  mov     rax, [rdi]
0x1800350a3  mov     rcx, rdi
0x1800350a6  mov     rax, [rax+8]
0x1800350aa  call    _guard_dispatch_icall
0x1800350af  test    sil, sil
0x1800350b2  jz      loc_180034FFD
0x1800350b8  xor     esi, esi
0x1800350ba  cmp     esi, 0C8h
0x1800350c0  jge     loc_180034FFD
0x1800350c6  mov     ecx, 3E8h; dwMilliseconds
0x1800350cb  call    cs:__imp_Sleep
0x1800350d1  lea     rcx, [rsp+78h+var_38]
0x1800350d6  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x1800350db  nop
0x1800350dc  mov     rcx, [rax]
0x1800350df  mov     rax, [rcx]
0x1800350e2  lea     rdx, [rsp+78h+var_28]
0x1800350e7  mov     rax, [rax+30h]
0x1800350eb  call    _guard_dispatch_icall
0x1800350f0  nop
0x1800350f1  mov     rcx, [rax]
0x1800350f4  mov     rax, [rcx]
0x1800350f7  mov     rax, [rax+38h]
0x1800350fb  call    _guard_dispatch_icall
0x180035100  mov     r12b, al
0x180035103  mov     rdi, [rsp+78h+var_20]
0x180035108  test    rdi, rdi
0x18003510b  jz      short loc_180035141
0x18003510d  mov     ecx, ebx
0x18003510f  lock xadd [rdi+8], ecx
0x180035114  add     ecx, ebx
0x180035116  jnz     short loc_180035141
0x180035118  mov     rax, [rdi]
0x18003511b  mov     rcx, rdi
0x18003511e  mov     rax, [rax]
0x180035121  call    _guard_dispatch_icall
0x180035126  mov     eax, ebx
0x180035128  lock xadd [rdi+0Ch], eax
0x18003512d  add     eax, ebx
0x18003512f  jnz     short loc_180035141
0x180035131  mov     rax, [rdi]
0x180035134  mov     rcx, rdi
0x180035137  mov     rax, [rax+8]
0x18003513b  call    _guard_dispatch_icall
0x180035140  nop
0x180035141  mov     rdi, [rsp+78h+var_30]
0x180035146  test    rdi, rdi
0x180035149  jz      short loc_18003517E
0x18003514b  mov     eax, ebx
0x18003514d  lock xadd [rdi+8], eax
0x180035152  add     eax, ebx
0x180035154  jnz     short loc_18003517E
0x180035156  mov     rax, [rdi]
0x180035159  mov     rcx, rdi
0x18003515c  mov     rax, [rax]
0x18003515f  call    _guard_dispatch_icall
0x180035164  mov     eax, ebx
0x180035166  lock xadd [rdi+0Ch], eax
0x18003516b  add     eax, ebx
0x18003516d  jnz     short loc_18003517E
0x18003516f  mov     rax, [rdi]
0x180035172  mov     rcx, rdi
0x180035175  mov     rax, [rax+8]
0x180035179  call    _guard_dispatch_icall
0x18003517e  test    r12b, r12b
0x180035181  jz      loc_180034FFD
0x180035187  inc     esi
0x180035189  jmp     loc_1800350BA
0x18003518e  mov     r15, [rsp+78h+var_48]
0x180035193  mov     r14d, [rsp+78h+var_58]
0x180035198  mov     rcx, [rsp+78h]; this
0x18003519d  test    r14d, r14d
0x1800351a0  jz      loc_18003523A
0x1800351a6  mov     rcx, [r15]; lpServiceName
0x1800351a9  call    ?ServiceMain_Internal@@YAJPEB_W@Z; ServiceMain_Internal(wchar_t const *)
0x1800351ae  mov     ebx, eax
0x1800351b0  mov     rcx, [rsp+78h]; this
0x1800351b5  test    eax, eax
0x1800351b7  jns     short loc_1800351FC
0x1800351b9  mov     r9d, eax; char *
0x1800351bc  lea     r8, aCW1SSrcOrchest_40; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x1800351c3  mov     edx, 435h; void *
0x1800351c8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800351cd  lea     rax, aUsosvcSettingS_0; "UsoSvc setting service state to: SERVIC"...
0x1800351d4  mov     [rsp+78h+var_48], rax
0x1800351d9  mov     [rsp+78h+var_40], 30h ; '0'
0x1800351e2  lea     rcx, [rsp+78h+var_48]
0x1800351e7  call    ??$Log@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::Log<>(std::wstring_view)
0x1800351ec  xor     r8d, r8d; unsigned int
0x1800351ef  mov     edx, ebx; unsigned int
0x1800351f1  lea     ecx, [r8+1]; unsigned int
0x1800351f5  call    ?UpdateServiceStatus@ServiceHelpers@@SAJKKK@Z; ServiceHelpers::UpdateServiceStatus(ulong,ulong,ulong)
0x1800351fa  jmp     short loc_18003521F
0x1800351fc  call    ?CheckCallOnStart@ServiceHelpers@@SAJXZ; ServiceHelpers::CheckCallOnStart(void)
0x180035201  mov     rcx, [rsp+78h]; this
0x180035206  test    eax, eax
0x180035208  jns     short loc_18003521F
0x18003520a  mov     r9d, eax; char *
0x18003520d  lea     r8, aCW1SSrcOrchest_40; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x180035214  mov     edx, 438h; void *
0x180035219  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003521e  nop
0x18003521f  lea     r11, [rsp+78h+var_18]
0x180035224  mov     rbx, [r11+20h]
0x180035228  mov     rsi, [r11+30h]
0x18003522c  mov     rdi, [r11+38h]
0x180035230  mov     rsp, r11
0x180035233  pop     r15
0x180035235  pop     r14
0x180035237  pop     r12
0x180035239  retn
0x18003523a  mov     r9d, 80070057h; char *
0x180035240  lea     r8, aCW1SSrcOrchest_40; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x180035247  mov     edx, 430h; void *
0x18003524c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
