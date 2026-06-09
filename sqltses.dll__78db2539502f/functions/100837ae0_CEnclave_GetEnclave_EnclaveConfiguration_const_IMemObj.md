# CEnclave::GetEnclave(EnclaveConfiguration const &,IMemObj *)

- ea: `0x100837ae0`
- end: `0x100837e6b`
- name: `?GetEnclave@CEnclave@@SAPEAV1@AEBUEnclaveConfiguration@@PEAVIMemObj@@@Z`
- size: `907`
- prototype: `struct CEnclave *__fastcall(const struct EnclaveConfiguration *, struct IMemObj *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callers

- `0x100832e40`

## callees

- `0x100401170`
- `0x1004011fc`
- `0x1004c7420`
- `0x1008376b0`
- `0x100837ae0`
- `0x1008385d0`
- `0x100838f00`
- `0x1008392b0`

## import_xrefs

- `sqldk!?EnqueueTask@SOS_OS@@SA?AW4SOS_RESULT@@P6APEAXPEAX@Z0KPEAPEAVSOS_Task@@_K@Z` at `0x100837dae`
- `sqldk!?EnqueueTask@SOS_OS@@SA?AW4SOS_RESULT@@P6APEAXPEAX@Z0KPEAPEAVSOS_Task@@_K@Z` at `0x100837dae`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100837b67`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100837c7a`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100837cc5`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100837d0e`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100837b67`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100837c7a`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100837cc5`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100837d0e`
- `sqldk!??_V@YAXPEAX@Z` at `0x100837c4a`
- `sqldk!??_V@YAXPEAX@Z` at `0x100837c4a`
- `sqldk!SystemThread_TlsIndex` at `0x100837ba0`
- `sqldk!SystemThread_TlsOffset` at `0x100837ba9`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100837bc4`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100837bc4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100837dd6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100837dd6`
- `sgx_urts!sgx_create_enclavew` at `0x100837c22`
- `sgx_urts!sgx_create_enclavew` at `0x100837c22`

## string_xrefs

- `0x100837bd8`: `\aetm-enclave.sgx.pkg\aetm-sgx-enclave-Simulator.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
struct CEnclave *__fastcall CEnclave::GetEnclave(const struct EnclaveConfiguration *a1, struct IMemObj *a2)
{
  const wchar_t *v4; // r14
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  CSimulatorEnclave *v8; // rax
  CVSMEnclave *v9; // rbx
  CSimulatorEnclave *EnclavePath; // rbp
  unsigned int v11; // eax
  CSimulatorEnclave *v12; // rax
  CSGXEnclave *v13; // rax
  CVSMEnclave *v14; // rax
  int i; // ebp
  __int64 v17; // rdx
  int v19; // [rsp+34h] [rbp-454h] BYREF
  CSimulatorEnclave *v20; // [rsp+38h] [rbp-450h]
  _QWORD v21[4]; // [rsp+40h] [rbp-448h] BYREF
  _BYTE v22[1024]; // [rsp+60h] [rbp-428h] BYREF

  v21[1] = -2;
  v21[2] = a2;
  v4 = L"SGX Simulator";
  v5 = *(_DWORD *)a1 - 1;
  if ( v5 )
  {
    v6 = v5 - 1;
    if ( v6 )
    {
      v7 = v6 - 1;
      if ( v7 )
      {
        if ( v7 != 1 )
          goto LABEL_33;
        v8 = (CSimulatorEnclave *)operator new(0x120u, a2, "Sql\\Ntdbms\\aetmhost\\enclavewrapper.cpp", 280, 6u);
        v9 = v8;
        v21[3] = v8;
        if ( v8 )
        {
          CSimulatorEnclave::CSimulatorEnclave(v8, a1, a2);
          *(_QWORD *)v9 = &CSgxSimulatorEnclave::`vftable';
          if ( !*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                          + SystemThread_TlsOffset
                          + 256LL) )
            SystemThread::MakeMiniSOSThread(0);
          EnclavePath = (CSimulatorEnclave *)GetEnclavePath((wchar_t *)L"\\aetm-enclave.sgx.pkg\\aetm-sgx-enclave-Simulator.dll");
          v20 = EnclavePath;
          memset_0(v22, 0, sizeof(v22));
          v19 = 0;
          v11 = sgx_create_enclavew(EnclavePath, 0, v22, &v19, v21, 0);
          if ( v11 )
            scierrlog(0x91BAu, L"SGX Simulator", v11);
          else
            *((_QWORD *)v9 + 2) = v21[0];
          operator delete[](EnclavePath);
        }
        else
        {
          v9 = 0;
        }
      }
      else
      {
        v12 = (CSimulatorEnclave *)operator new(0x118u, a2, "Sql\\Ntdbms\\aetmhost\\enclavewrapper.cpp", 284, 6u);
        v20 = v12;
        if ( v12 )
          v9 = CSimulatorEnclave::CSimulatorEnclave(v12, a1, a2);
        else
          v9 = 0;
      }
    }
    else
    {
      v13 = (CSGXEnclave *)operator new(0x110u, a2, "Sql\\Ntdbms\\aetmhost\\enclavewrapper.cpp", 276, 6u);
      v20 = v13;
      if ( v13 )
        v9 = CSGXEnclave::CSGXEnclave(v13, a1, a2);
      else
        v9 = 0;
    }
  }
  else
  {
    v14 = (CVSMEnclave *)operator new(0x190u, a2, "Sql\\Ntdbms\\aetmhost\\enclavewrapper.cpp", 272, 6u);
    v20 = v14;
    if ( v14 )
      v9 = CVSMEnclave::CVSMEnclave(v14, a1, a2);
    else
      v9 = 0;
  }
  if ( v9 )
  {
    if ( !(((*((_DWORD *)v9 + 6) - 1) & 0xFFFFFFFD) != 0 ? *((_QWORD *)v9 + 2) == 0 : *((_QWORD *)v9 + 1) == 0) )
    {
      if ( !*((_BYTE *)a1 + 8) )
      {
        for ( i = 0; i < *((_DWORD *)a1 + 1); ++i )
        {
          v17 = *((_QWORD *)v9 + 22) + 16520LL * i;
          if ( (unsigned int)SOS_OS::EnqueueTask(CEnclave::DoEnclaveWorkS, v17, 18, v17 + 16512, -1) )
            utassert_fail(1u, "SOS_OK == status", "enclavewrapper.cpp", 306, 0);
        }
      }
      return v9;
    }
  }
LABEL_33:
  if ( *(_DWORD *)a1 )
  {
    switch ( *(_DWORD *)a1 )
    {
      case 1:
        v4 = L"VBS";
        break;
      case 2:
        v4 = L"SGX";
        break;
      case 3:
        v4 = L"Simulator";
        break;
      default:
        if ( *(_DWORD *)a1 != 4 )
          v4 = L"Unknown";
        break;
    }
  }
  else
  {
    v4 = L"No";
  }
  scierrlog(0x91BBu, v4, L"GetEnclave");
  return 0;
}

```

## disassembly

```asm
0x100837ae0  mov     rax, rsp
0x100837ae3  push    rsi
0x100837ae4  push    rdi
0x100837ae5  push    r14
0x100837ae7  sub     rsp, 470h
0x100837aee  mov     [rsp+488h+var_440], 0FFFFFFFFFFFFFFFEh
0x100837af7  mov     [rax+18h], rbx
0x100837afb  mov     [rax+20h], rbp
0x100837aff  mov     rax, cs:__security_cookie
0x100837b06  xor     rax, rsp
0x100837b09  mov     [rsp+488h+var_28], rax
0x100837b11  mov     rbp, rdx
0x100837b14  mov     rdi, rcx
0x100837b17  mov     [rsp+488h+var_438], rdx
0x100837b1c  mov     ecx, [rcx]
0x100837b1e  lea     r14, aSgxSimulator; "SGX Simulator"
0x100837b25  sub     ecx, 1
0x100837b28  jz      loc_100837CEF
0x100837b2e  sub     ecx, 1
0x100837b31  jz      loc_100837CA7
0x100837b37  sub     ecx, 1
0x100837b3a  jz      loc_100837C5C
0x100837b40  cmp     ecx, 1
0x100837b43  jnz     loc_100837DE8
0x100837b49  mov     [rsp+488h+var_458], 118h
0x100837b51  mov     byte ptr [rsp+488h+var_468], 6
0x100837b56  mov     r9d, 118h
0x100837b5c  lea     r8, aSqlNtdbmsAetmh; "Sql\\Ntdbms\\aetmhost\\enclavewrapper.c"...
0x100837b63  lea     ecx, [r9+8]
0x100837b67  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new(unsigned __int64,IMemObj *,char const *,int,uchar)
0x100837b6d  mov     rbx, rax
0x100837b70  mov     [rsp+488h+var_430], rax
0x100837b75  test    rax, rax
0x100837b78  jz      loc_100837C53
0x100837b7e  mov     r8, rbp; struct IMemObj *
0x100837b81  mov     rdx, rdi; struct EnclaveConfiguration *
0x100837b84  mov     rcx, rax; this
0x100837b87  call    ??0CSimulatorEnclave@@QEAA@AEBUEnclaveConfiguration@@PEAVIMemObj@@@Z; CSimulatorEnclave::CSimulatorEnclave(EnclaveConfiguration const &,IMemObj *)
0x100837b8c  nop
0x100837b8d  lea     rax, ??_7CSgxSimulatorEnclave@@6B@; const CSgxSimulatorEnclave::`vftable'
0x100837b94  mov     [rbx], rax
0x100837b97  mov     rdx, gs:58h
0x100837ba0  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100837ba7  mov     ecx, [rax]
0x100837ba9  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100837bb0  mov     esi, [rax]
0x100837bb2  add     rsi, [rdx+rcx*8]
0x100837bb6  mov     rdx, [rsi+100h]
0x100837bbd  test    rdx, rdx
0x100837bc0  jnz     short loc_100837BD1
0x100837bc2  xor     ecx, ecx
0x100837bc4  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100837bca  mov     rdx, [rsi+100h]
0x100837bd1  mov     rdx, [rdx+3E8h]
0x100837bd8  lea     rcx, aAetmEnclaveSgx_0; "\\aetm-enclave.sgx.pkg\\aetm-sgx-enclav"...
0x100837bdf  call    GetEnclavePath
0x100837be4  mov     rbp, rax
0x100837be7  mov     [rsp+488h+var_450], rax
0x100837bec  xor     edx, edx; Val
0x100837bee  mov     r8d, 400h; Size
0x100837bf4  lea     rcx, [rsp+488h+var_428]; void *
0x100837bf9  call    memset_0
0x100837bfe  xor     esi, esi
0x100837c00  mov     [rsp+488h+var_454], esi
0x100837c04  mov     [rsp+488h+var_460], rsi
0x100837c09  lea     rax, [rsp+488h+var_448]
0x100837c0e  mov     [rsp+488h+var_468], rax
0x100837c13  lea     r9, [rsp+488h+var_454]
0x100837c18  lea     r8, [rsp+488h+var_428]
0x100837c1d  xor     edx, edx
0x100837c1f  mov     rcx, rbp
0x100837c22  call    cs:__imp_sgx_create_enclavew
0x100837c28  test    eax, eax
0x100837c2a  jz      short loc_100837C3E
0x100837c2c  mov     r8d, eax
0x100837c2f  mov     rdx, r14
0x100837c32  mov     ecx, 91BAh; unsigned int
0x100837c37  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x100837c3c  jmp     short loc_100837C47
0x100837c3e  mov     rax, [rsp+488h+var_448]
0x100837c43  mov     [rbx+10h], rax
0x100837c47  mov     rcx, rbp
0x100837c4a  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x100837c50  nop
0x100837c51  jmp     short loc_100837C57
0x100837c53  xor     esi, esi
0x100837c55  mov     ebx, esi
0x100837c57  jmp     loc_100837D36
0x100837c5c  mov     [rsp+488h+var_458], 11Ch
0x100837c64  mov     byte ptr [rsp+488h+var_468], 6
0x100837c69  mov     r9d, 11Ch
0x100837c6f  lea     r8, aSqlNtdbmsAetmh; "Sql\\Ntdbms\\aetmhost\\enclavewrapper.c"...
0x100837c76  lea     ecx, [r9-4]
0x100837c7a  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new(unsigned __int64,IMemObj *,char const *,int,uchar)
0x100837c80  mov     [rsp+488h+var_450], rax
0x100837c85  xor     esi, esi
0x100837c87  test    rax, rax
0x100837c8a  jz      short loc_100837C9F
0x100837c8c  mov     r8, rbp; struct IMemObj *
0x100837c8f  mov     rdx, rdi; struct EnclaveConfiguration *
0x100837c92  mov     rcx, rax; this
0x100837c95  call    ??0CSimulatorEnclave@@QEAA@AEBUEnclaveConfiguration@@PEAVIMemObj@@@Z; CSimulatorEnclave::CSimulatorEnclave(EnclaveConfiguration const &,IMemObj *)
0x100837c9a  mov     rbx, rax
0x100837c9d  jmp     short loc_100837CA2
0x100837c9f  mov     rbx, rsi
0x100837ca2  jmp     loc_100837D36
0x100837ca7  mov     [rsp+488h+var_458], 114h
0x100837caf  mov     byte ptr [rsp+488h+var_468], 6
0x100837cb4  mov     r9d, 114h
0x100837cba  lea     r8, aSqlNtdbmsAetmh; "Sql\\Ntdbms\\aetmhost\\enclavewrapper.c"...
0x100837cc1  lea     ecx, [r9-4]
0x100837cc5  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new(unsigned __int64,IMemObj *,char const *,int,uchar)
0x100837ccb  mov     [rsp+488h+var_450], rax
0x100837cd0  xor     esi, esi
0x100837cd2  test    rax, rax
0x100837cd5  jz      short loc_100837CEA
0x100837cd7  mov     r8, rbp; struct IMemObj *
0x100837cda  mov     rdx, rdi; struct EnclaveConfiguration *
0x100837cdd  mov     rcx, rax; this
0x100837ce0  call    ??0CSGXEnclave@@QEAA@AEBUEnclaveConfiguration@@PEAVIMemObj@@@Z; CSGXEnclave::CSGXEnclave(EnclaveConfiguration const &,IMemObj *)
0x100837ce5  mov     rbx, rax
0x100837ce8  jmp     short loc_100837CED
0x100837cea  mov     rbx, rsi
0x100837ced  jmp     short loc_100837D36
0x100837cef  mov     [rsp+488h+var_458], 110h
0x100837cf7  mov     byte ptr [rsp+488h+var_468], 6
0x100837cfc  mov     r9d, 110h
0x100837d02  lea     r8, aSqlNtdbmsAetmh; "Sql\\Ntdbms\\aetmhost\\enclavewrapper.c"...
0x100837d09  mov     ecx, 190h
0x100837d0e  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new(unsigned __int64,IMemObj *,char const *,int,uchar)
0x100837d14  mov     [rsp+488h+var_450], rax
0x100837d19  xor     esi, esi
0x100837d1b  test    rax, rax
0x100837d1e  jz      short loc_100837D33
0x100837d20  mov     r8, rbp; struct IMemObj *
0x100837d23  mov     rdx, rdi; struct EnclaveConfiguration *
0x100837d26  mov     rcx, rax; this
0x100837d29  call    ??0CVSMEnclave@@QEAA@AEBUEnclaveConfiguration@@PEAVIMemObj@@@Z; CVSMEnclave::CVSMEnclave(EnclaveConfiguration const &,IMemObj *)
0x100837d2e  mov     rbx, rax
0x100837d31  jmp     short loc_100837D36
0x100837d33  mov     rbx, rsi
0x100837d36  test    rbx, rbx
0x100837d39  jz      loc_100837DE8
0x100837d3f  mov     eax, [rbx+18h]
0x100837d42  dec     eax
0x100837d44  test    eax, 0FFFFFFFDh
0x100837d49  jz      short loc_100837D52
0x100837d4b  cmp     qword ptr [rbx+10h], 0
0x100837d50  jmp     short loc_100837D57
0x100837d52  cmp     qword ptr [rbx+8], 0
0x100837d57  setnz   al
0x100837d5a  test    al, al
0x100837d5c  jz      loc_100837DE8
0x100837d62  cmp     byte ptr [rdi+8], 0
0x100837d66  jnz     short loc_100837DE3
0x100837d68  mov     ebp, esi
0x100837d6a  cmp     dword ptr [rdi+4], 0
0x100837d6e  jle     short loc_100837DE3
0x100837d70  nop     dword ptr [rax]
0x100837d73  nop     dword ptr [rax+00h]
0x100837d77  nop     word ptr [rax+rax+00000000h]
0x100837d80  movsxd  rax, ebp
0x100837d83  imul    rdx, rax, 4088h
0x100837d8a  add     rdx, [rbx+0B0h]
0x100837d91  lea     r9, [rdx+4080h]
0x100837d98  mov     [rsp+488h+var_468], 0FFFFFFFFFFFFFFFFh
0x100837da1  mov     r8d, 12h
0x100837da7  lea     rcx, ?DoEnclaveWorkS@CEnclave@@CAPEAXPEAX@Z; CEnclave::DoEnclaveWorkS(void *)
0x100837dae  call    cs:__imp_?EnqueueTask@SOS_OS@@SA?AW4SOS_RESULT@@P6APEAXPEAX@Z0KPEAPEAVSOS_Task@@_K@Z; SOS_OS::EnqueueTask(void * (*)(void *),void *,ulong,SOS_Task * *,unsigned __int64)
0x100837db4  test    eax, eax
0x100837db6  jz      short loc_100837DDC
0x100837db8  mov     [rsp+488h+var_468], rsi
0x100837dbd  mov     r9d, 132h
0x100837dc3  lea     r8, aEnclavewrapper; "enclavewrapper.cpp"
0x100837dca  lea     rdx, aSosOkStatus; "SOS_OK == status"
0x100837dd1  mov     ecx, 1
0x100837dd6  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x100837ddc  inc     ebp
0x100837dde  cmp     ebp, [rdi+4]
0x100837de1  jl      short loc_100837D80
0x100837de3  mov     rax, rbx
0x100837de6  jmp     short loc_100837E43
0x100837de8  mov     ecx, [rdi]
0x100837dea  test    ecx, ecx
0x100837dec  jz      short loc_100837E26
0x100837dee  sub     ecx, 1
0x100837df1  jz      short loc_100837E1D
0x100837df3  sub     ecx, 1
0x100837df6  jz      short loc_100837E14
0x100837df8  sub     ecx, 1
0x100837dfb  jz      short loc_100837E0B
0x100837dfd  cmp     ecx, 1
0x100837e00  jz      short loc_100837E2D
0x100837e02  lea     r14, aUnknown_0; "Unknown"
0x100837e09  jmp     short loc_100837E2D
0x100837e0b  lea     r14, aSimulator; "Simulator"
0x100837e12  jmp     short loc_100837E2D
0x100837e14  lea     r14, aSgx; "SGX"
0x100837e1b  jmp     short loc_100837E2D
0x100837e1d  lea     r14, aVbs; "VBS"
0x100837e24  jmp     short loc_100837E2D
0x100837e26  lea     r14, aNo; "No"
0x100837e2d  lea     r8, aGetenclave; "GetEnclave"
0x100837e34  mov     rdx, r14
0x100837e37  mov     ecx, 91BBh; unsigned int
0x100837e3c  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x100837e41  xor     eax, eax
0x100837e43  mov     rcx, [rsp+488h+var_28]
0x100837e4b  xor     rcx, rsp; StackCookie
0x100837e4e  call    __security_check_cookie
0x100837e53  lea     r11, [rsp+488h+var_18]
0x100837e5b  mov     rbx, [r11+30h]
0x100837e5f  mov     rbp, [r11+38h]
0x100837e63  mov     rsp, r11
0x100837e66  pop     r14
0x100837e68  pop     rdi
0x100837e69  pop     rsi
0x100837e6a  retn
```
