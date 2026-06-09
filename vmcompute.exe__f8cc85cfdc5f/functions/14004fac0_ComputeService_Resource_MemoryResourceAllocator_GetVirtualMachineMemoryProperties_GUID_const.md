# ComputeService::Resource::MemoryResourceAllocator::GetVirtualMachineMemoryProperties(_GUID const &)

- ea: `0x14004fac0`
- end: `0x14004fdf3`
- name: `?GetVirtualMachineMemoryProperties@MemoryResourceAllocator@Resource@ComputeService@@UEAA?AUMemoryInformationForVm@System@Responses@Schema@@AEBU_GUID@@@Z`
- size: `819`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1400162e8`
- `0x14001bce0`
- `0x14002d888`
- `0x140037618`
- `0x14004fac0`
- `0x14004fdfc`
- `0x14004ff10`
- `0x1400c40e0`
- `0x1401332f0`
- `0x1402c4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14004fc6d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14004fd72`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14004fc6d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14004fd72`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14004fb04`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14004fb04`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14004fbc9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14004fbc9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14004fc49`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14004fca2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14004fc49`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14004fca2`
- `RPCRT4!UuidCompare` at `0x14004fb48`
- `RPCRT4!UuidCompare` at `0x14004fb77`
- `RPCRT4!UuidCompare` at `0x14004fb48`
- `RPCRT4!UuidCompare` at `0x14004fb77`

## string_xrefs

- `0x14004fdce`: `onecore\vm\compute\management\resources\memory\memoryresourceallocator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ComputeService::Resource::MemoryResourceAllocator::GetVirtualMachineMemoryProperties(
        RTL_SRWLOCK *a1,
        __int64 a2,
        UUID *a3)
{
  RTL_SRWLOCK *v6; // rdi
  PVOID Ptr; // rbx
  UUID *v8; // rsi
  char v9; // al
  __int64 v10; // rbx
  struct _RTL_CRITICAL_SECTION *v11; // rsi
  __int64 v12; // rdi
  struct _RTL_CRITICAL_SECTION *v13; // rsi
  unsigned __int8 v14; // r14
  __int64 v15; // rcx
  __int128 v17; // [rsp+20h] [rbp-79h] BYREF
  __int64 v18; // [rsp+30h] [rbp-69h]
  UUID Uuid2; // [rsp+38h] [rbp-61h] BYREF
  int v20; // [rsp+5Ch] [rbp-3Dh]
  RPC_STATUS Status; // [rsp+68h] [rbp-31h] BYREF
  unsigned __int8 v22; // [rsp+70h] [rbp-29h]
  int v23; // [rsp+71h] [rbp-28h]
  __int16 v24; // [rsp+75h] [rbp-24h]
  char v25; // [rsp+77h] [rbp-22h]
  int v26; // [rsp+78h] [rbp-21h]
  int v27; // [rsp+7Ch] [rbp-1Dh]
  __int64 v28; // [rsp+80h] [rbp-19h]
  __int64 v29; // [rsp+88h] [rbp-11h]
  char v30; // [rsp+90h] [rbp-9h]
  bool v31; // [rsp+91h] [rbp-8h]
  bool v32; // [rsp+92h] [rbp-7h]
  int v33; // [rsp+93h] [rbp-6h]
  char v34; // [rsp+97h] [rbp-2h]
  char v35[8]; // [rsp+98h] [rbp-1h] BYREF
  _OWORD *v36; // [rsp+A0h] [rbp+7h]
  _OWORD *v37; // [rsp+A8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v18 = 0;
  v6 = a1 + 1;
  AcquireSRWLockExclusive(a1 + 1);
  *(_QWORD *)&v17 = v6;
  Uuid2 = *a3;
  Ptr = a1[2].Ptr;
  v8 = (UUID *)*((_QWORD *)Ptr + 1);
  v20 = 0;
  while ( !v8[1].Data4[1] )
  {
    Status = 0;
    if ( UuidCompare(v8 + 2, &Uuid2, &Status) < 0 )
      ++v8;
    else
      Ptr = v8;
    v8 = *(UUID **)&v8->Data1;
  }
  if ( *((_BYTE *)Ptr + 25) || (Status = 0, UuidCompare(&Uuid2, (UUID *)Ptr + 2, &Status) < 0) )
  {
    Ptr = a1[2].Ptr;
  }
  else if ( Ptr != a1[2].Ptr )
  {
    v9 = 0;
    goto LABEL_11;
  }
  v9 = 1;
LABEL_11:
  if ( v9 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3B9,
      (unsigned int)"onecore\\vm\\compute\\management\\resources\\memory\\memoryresourceallocator.cpp",
      (const char *)0x800710D8LL,
      v17);
  v10 = *((_QWORD *)Ptr + 6);
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v10 + 24) + 8LL))(v10 + 24);
  v18 = v10;
  if ( v6 )
    ReleaseSRWLockExclusive(v6);
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v29 = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(v35);
  v26 = *(_DWORD *)(v10 + 496);
  v27 = *(_DWORD *)(v10 + 500);
  v30 = *(_BYTE *)(v10 + 504);
  v28 = *(_QWORD *)(v10 + 64);
  v31 = *(_DWORD *)(v10 + 56) != 0;
  v32 = (unsigned int)DmWorkerProcessTracker::IsDmOperationInProgress((DmWorkerProcessTracker *)v10) != 0;
  v29 = 0;
  v11 = *(struct _RTL_CRITICAL_SECTION **)(v10 + 384);
  if ( v11 )
    EnterCriticalSection(*(LPCRITICAL_SECTION *)(v10 + 384));
  v12 = (__int64)(unsigned int)(*(_DWORD *)(v10 + 520) - *(_DWORD *)(v10 + 512)) >> 3;
  if ( v11 )
    LeaveCriticalSection(v11);
  v22 = v12;
  Uuid2 = 0;
  v13 = *(struct _RTL_CRITICAL_SECTION **)(v10 + 384);
  *(_QWORD *)&Uuid2.Data1 = &Vml::VmAutoLock::`vftable';
  *(_QWORD *)Uuid2.Data4 = v13;
  if ( v13 )
  {
    EnterCriticalSection(v13);
    LOBYTE(v12) = v22;
  }
  v14 = 0;
  if ( (_BYTE)v12 )
  {
    do
    {
      v15 = *(_QWORD *)(*(_QWORD *)(v10 + 512) + 8LL * v14);
      LOWORD(v17) = *(_WORD *)(v15 + 349);
      DWORD1(v17) = *(_DWORD *)(v15 + 344);
      *((_QWORD *)&v17 + 1) = DmVirtualNumaNode::GetConsumedPhysicalMemory((DmVirtualNumaNode *)v15);
      v29 += *((_QWORD *)&v17 + 1);
      if ( v36 == v37 )
        std::vector<Schema::Resources::Processor::CpuGroupProperty>::_Emplace_reallocate<Schema::Resources::Processor::CpuGroupProperty const &>(
          v35,
          v36,
          &v17);
      else
        *v36++ = v17;
      ++v14;
      LOBYTE(v12) = v22;
    }
    while ( v14 < v22 );
  }
  *(_BYTE *)a2 = v12;
  *(_DWORD *)(a2 + 8) = v26;
  *(_DWORD *)(a2 + 12) = v27;
  *(_QWORD *)(a2 + 16) = v28;
  *(_QWORD *)(a2 + 24) = v29;
  *(_BYTE *)(a2 + 32) = v30;
  *(_BYTE *)(a2 + 33) = v31;
  *(_BYTE *)(a2 + 34) = v32;
  *(_DWORD *)(a2 + 35) = v33;
  *(_BYTE *)(a2 + 39) = v34;
  std::vector<Schema::Resources::ProcessorCache::ProcessorCacheMonitor>::vector<Schema::Resources::ProcessorCache::ProcessorCacheMonitor>(
    a2 + 40,
    v35);
  if ( v13 )
    LeaveCriticalSection(v13);
  std::vector<_HV_SUBNODE>::_Tidy(v35);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(v10 + 24) + 16LL))(v10 + 24);
  return a2;
}

```

## disassembly

```asm
0x14004fac0  mov     [rsp-8+arg_8], rdx
0x14004fac5  push    rbp
0x14004fac6  push    rbx
0x14004fac7  push    rsi
0x14004fac8  push    rdi
0x14004fac9  push    r12
0x14004facb  push    r14
0x14004facd  push    r15
0x14004facf  lea     rbp, [rsp-27h]
0x14004fad4  sub     rsp, 0C0h
0x14004fadb  mov     rax, cs:__security_cookie
0x14004fae2  xor     rax, rsp
0x14004fae5  mov     [rbp+57h+var_40], rax
0x14004fae9  mov     rbx, r8
0x14004faec  mov     r15, rdx
0x14004faef  mov     r14, rcx
0x14004faf2  mov     [rbp+57h+var_C0], rdx
0x14004faf6  xor     r12d, r12d
0x14004faf9  mov     [rbp+57h+var_C0], r12
0x14004fafd  lea     rdi, [rcx+8]
0x14004fb01  mov     rcx, rdi; SRWLock
0x14004fb04  call    cs:__imp_AcquireSRWLockExclusive
0x14004fb0b  nop     dword ptr [rax+rax+00h]
0x14004fb10  mov     qword ptr [rbp+57h+var_D0], rdi
0x14004fb14  movups  xmm0, xmmword ptr [rbx]
0x14004fb17  movdqu  xmmword ptr [rbp+57h+Uuid2.Data1], xmm0
0x14004fb1c  mov     rbx, [r14+10h]
0x14004fb20  mov     rsi, [rbx+8]
0x14004fb24  xor     eax, eax
0x14004fb26  mov     [rbp+57h+var_94], eax
0x14004fb29  jmp     short loc_14004FB32
0x14004fb2b  add     rsi, 10h
0x14004fb2f  mov     rsi, [rsi]
0x14004fb32  cmp     [rsi+19h], r12b
0x14004fb36  jnz     short loc_14004FB5D
0x14004fb38  mov     [rbp+57h+Status], r12d
0x14004fb3c  lea     rcx, [rsi+20h]; Uuid1
0x14004fb40  lea     r8, [rbp+57h+Status]; Status
0x14004fb44  lea     rdx, [rbp+57h+Uuid2]; Uuid2
0x14004fb48  call    cs:__imp_UuidCompare
0x14004fb4f  nop     dword ptr [rax+rax+00h]
0x14004fb54  test    eax, eax
0x14004fb56  js      short loc_14004FB2B
0x14004fb58  mov     rbx, rsi
0x14004fb5b  jmp     short loc_14004FB2F
0x14004fb5d  cmp     [rbx+19h], r12b
0x14004fb61  jnz     loc_14004FDC2
0x14004fb67  mov     [rbp+57h+Status], r12d
0x14004fb6b  lea     rdx, [rbx+20h]; Uuid2
0x14004fb6f  lea     r8, [rbp+57h+Status]; Status
0x14004fb73  lea     rcx, [rbp+57h+Uuid2]; Uuid1
0x14004fb77  call    cs:__imp_UuidCompare
0x14004fb7e  nop     dword ptr [rax+rax+00h]
0x14004fb83  test    eax, eax
0x14004fb85  js      loc_14004FDC2
0x14004fb8b  cmp     rbx, [r14+10h]
0x14004fb8f  jz      loc_14004FDBB
0x14004fb95  mov     al, r12b
0x14004fb98  mov     rcx, [rbp+5Fh]; this
0x14004fb9c  test    al, al
0x14004fb9e  jnz     loc_14004FDC8
0x14004fba4  mov     rbx, [rbx+30h]
0x14004fba8  test    rbx, rbx
0x14004fbab  jz      short loc_14004FBBD
0x14004fbad  lea     rcx, [rbx+18h]
0x14004fbb1  mov     rax, [rcx]
0x14004fbb4  mov     rax, [rax+8]
0x14004fbb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004fbbd  mov     [rbp+57h+var_C0], rbx
0x14004fbc1  test    rdi, rdi
0x14004fbc4  jz      short loc_14004FBD5
0x14004fbc6  mov     rcx, rdi; SRWLock
0x14004fbc9  call    cs:__imp_ReleaseSRWLockExclusive
0x14004fbd0  nop     dword ptr [rax+rax+00h]
0x14004fbd5  mov     [rbp+57h+var_80], r12b
0x14004fbd9  xor     eax, eax
0x14004fbdb  mov     [rbp+57h+var_7F], eax
0x14004fbde  mov     [rbp+57h+var_7B], ax
0x14004fbe2  mov     [rbp+57h+var_79], al
0x14004fbe5  mov     [rbp+57h+var_68], r12
0x14004fbe9  mov     [rbp+57h+var_5E], r12b
0x14004fbed  mov     [rbp+57h+var_5D], eax
0x14004fbf0  mov     [rbp+57h+var_59], al
0x14004fbf3  lea     rcx, [rbp+57h+var_58]
0x14004fbf7  call    ??0?$vector@UVpSubnodeMetadata@VirtualMachine@Config@@V?$allocator@UVpSubnodeMetadata@VirtualMachine@Config@@@std@@@std@@QEAA@XZ; std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(void)
0x14004fbfc  nop
0x14004fbfd  mov     eax, [rbx+1F0h]
0x14004fc03  mov     [rbp+57h+var_78], eax
0x14004fc06  mov     eax, [rbx+1F4h]
0x14004fc0c  mov     [rbp+57h+var_74], eax
0x14004fc0f  mov     al, [rbx+1F8h]
0x14004fc15  mov     [rbp+57h+var_60], al
0x14004fc18  mov     rax, [rbx+40h]
0x14004fc1c  mov     [rbp+57h+var_70], rax
0x14004fc20  cmp     [rbx+38h], r12d
0x14004fc24  setnz   [rbp+57h+var_5F]
0x14004fc28  mov     rcx, rbx; this
0x14004fc2b  call    ?IsDmOperationInProgress@DmWorkerProcessTracker@@QEAAHXZ; DmWorkerProcessTracker::IsDmOperationInProgress(void)
0x14004fc30  test    eax, eax
0x14004fc32  setnz   [rbp+57h+var_5E]
0x14004fc36  mov     [rbp+57h+var_68], r12
0x14004fc3a  mov     rsi, [rbx+180h]
0x14004fc41  test    rsi, rsi
0x14004fc44  jz      short loc_14004FC55
0x14004fc46  mov     rcx, rsi; lpCriticalSection
0x14004fc49  call    cs:__imp_EnterCriticalSection
0x14004fc50  nop     dword ptr [rax+rax+00h]
0x14004fc55  mov     edi, [rbx+208h]
0x14004fc5b  sub     edi, [rbx+200h]
0x14004fc61  sar     rdi, 3
0x14004fc65  test    rsi, rsi
0x14004fc68  jz      short loc_14004FC79
0x14004fc6a  mov     rcx, rsi; lpCriticalSection
0x14004fc6d  call    cs:__imp_LeaveCriticalSection
0x14004fc74  nop     dword ptr [rax+rax+00h]
0x14004fc79  mov     [rbp+57h+var_80], dil
0x14004fc7d  xorps   xmm0, xmm0
0x14004fc80  movups  xmmword ptr [rbp+57h+Uuid2.Data1], xmm0
0x14004fc84  mov     rsi, [rbx+180h]
0x14004fc8b  lea     rax, ??_7VmAutoLock@Vml@@6B@; const Vml::VmAutoLock::`vftable'
0x14004fc92  mov     qword ptr [rbp+57h+Uuid2.Data1], rax
0x14004fc96  mov     qword ptr [rbp+57h+Uuid2.Data4], rsi
0x14004fc9a  test    rsi, rsi
0x14004fc9d  jz      short loc_14004FCB2
0x14004fc9f  mov     rcx, rsi; lpCriticalSection
0x14004fca2  call    cs:__imp_EnterCriticalSection
0x14004fca9  nop     dword ptr [rax+rax+00h]
0x14004fcae  mov     dil, [rbp+57h+var_80]
0x14004fcb2  mov     r14b, r12b
0x14004fcb5  test    dil, dil
0x14004fcb8  jz      short loc_14004FD18
0x14004fcba  movzx   ecx, r14b
0x14004fcbe  mov     rax, [rbx+200h]
0x14004fcc5  mov     rcx, [rax+rcx*8]; this
0x14004fcc9  mov     al, [rcx+15Dh]
0x14004fccf  mov     byte ptr [rbp+57h+var_D0], al
0x14004fcd2  mov     al, [rcx+15Eh]
0x14004fcd8  mov     byte ptr [rbp+57h+var_D0+1], al
0x14004fcdb  mov     eax, [rcx+158h]
0x14004fce1  mov     dword ptr [rbp+57h+var_D0+4], eax
0x14004fce4  call    ?GetConsumedPhysicalMemory@DmVirtualNumaNode@@UEBA_KXZ; DmVirtualNumaNode::GetConsumedPhysicalMemory(void)
0x14004fce9  mov     qword ptr [rbp+57h+var_D0+8], rax
0x14004fced  add     [rbp+57h+var_68], rax
0x14004fcf1  mov     rdx, [rbp+57h+var_50]
0x14004fcf5  cmp     rdx, [rbp+57h+var_48]
0x14004fcf9  jz      loc_14004FDE0
0x14004fcff  movups  xmm0, [rbp+57h+var_D0]
0x14004fd03  movdqu  xmmword ptr [rdx], xmm0
0x14004fd07  add     [rbp+57h+var_50], 10h
0x14004fd0c  inc     r14b
0x14004fd0f  mov     dil, [rbp+57h+var_80]
0x14004fd13  cmp     r14b, dil
0x14004fd16  jb      short loc_14004FCBA
0x14004fd18  mov     [r15], dil
0x14004fd1b  mov     eax, [rbp+57h+var_78]
0x14004fd1e  mov     [r15+8], eax
0x14004fd22  mov     eax, [rbp+57h+var_74]
0x14004fd25  mov     [r15+0Ch], eax
0x14004fd29  mov     rax, [rbp+57h+var_70]
0x14004fd2d  mov     [r15+10h], rax
0x14004fd31  mov     rax, [rbp+57h+var_68]
0x14004fd35  mov     [r15+18h], rax
0x14004fd39  mov     al, [rbp+57h+var_60]
0x14004fd3c  mov     [r15+20h], al
0x14004fd40  mov     al, [rbp+57h+var_5F]
0x14004fd43  mov     [r15+21h], al
0x14004fd47  mov     al, [rbp+57h+var_5E]
0x14004fd4a  mov     [r15+22h], al
0x14004fd4e  mov     eax, [rbp+57h+var_5D]
0x14004fd51  mov     [r15+23h], eax
0x14004fd55  mov     al, [rbp+57h+var_59]
0x14004fd58  mov     [r15+27h], al
0x14004fd5c  lea     rcx, [r15+28h]
0x14004fd60  lea     rdx, [rbp+57h+var_58]
0x14004fd64  call    ??0?$vector@UProcessorCacheMonitor@ProcessorCache@Resources@Schema@@V?$allocator@UProcessorCacheMonitor@ProcessorCache@Resources@Schema@@@std@@@std@@QEAA@$$QEAV01@@Z; std::vector<Schema::Resources::ProcessorCache::ProcessorCacheMonitor>::vector<Schema::Resources::ProcessorCache::ProcessorCacheMonitor>(std::vector<Schema::Resources::ProcessorCache::ProcessorCacheMonitor> &&)
0x14004fd69  nop
0x14004fd6a  test    rsi, rsi
0x14004fd6d  jz      short loc_14004FD7F
0x14004fd6f  mov     rcx, rsi; lpCriticalSection
0x14004fd72  call    cs:__imp_LeaveCriticalSection
0x14004fd79  nop     dword ptr [rax+rax+00h]
0x14004fd7e  nop
0x14004fd7f  lea     rcx, [rbp+57h+var_58]
0x14004fd83  call    ?_Tidy@?$vector@U_HV_SUBNODE@@V?$allocator@U_HV_SUBNODE@@@std@@@std@@AEAAXXZ; std::vector<_HV_SUBNODE>::_Tidy(void)
0x14004fd88  nop
0x14004fd89  lea     rcx, [rbx+18h]
0x14004fd8d  mov     rdx, [rcx]
0x14004fd90  mov     rax, [rdx+10h]
0x14004fd94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004fd99  mov     rax, r15
0x14004fd9c  mov     rcx, [rbp+57h+var_40]
0x14004fda0  xor     rcx, rsp; StackCookie
0x14004fda3  call    __security_check_cookie
0x14004fda8  add     rsp, 0C0h
0x14004fdaf  pop     r15
0x14004fdb1  pop     r14
0x14004fdb3  pop     r12
0x14004fdb5  pop     rdi
0x14004fdb6  pop     rsi
0x14004fdb7  pop     rbx
0x14004fdb8  pop     rbp
0x14004fdb9  retn
0x14004fdbb  mov     al, 1
0x14004fdbd  jmp     loc_14004FB98
0x14004fdc2  mov     rbx, [r14+10h]
0x14004fdc6  jmp     short loc_14004FDBB
0x14004fdc8  mov     r9d, 800710D8h; char *
0x14004fdce  lea     r8, aOnecoreVmCompu_48; "onecore\\vm\\compute\\management\\resou"...
0x14004fdd5  mov     edx, 3B9h; void *
0x14004fdda  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14004fde0  lea     r8, [rbp+57h+var_D0]
0x14004fde4  lea     rcx, [rbp+57h+var_58]
0x14004fde8  call    ??$_Emplace_reallocate@AEBUCpuGroupProperty@Processor@Resources@Schema@@@?$vector@UCpuGroupProperty@Processor@Resources@Schema@@V?$allocator@UCpuGroupProperty@Processor@Resources@Schema@@@std@@@std@@AEAAPEAUCpuGroupProperty@Processor@Resources@Schema@@QEAU2345@AEBU2345@@Z; std::vector<Schema::Resources::Processor::CpuGroupProperty>::_Emplace_reallocate<Schema::Resources::Processor::CpuGroupProperty const &>(Schema::Resources::Processor::CpuGroupProperty * const,Schema::Resources::Processor::CpuGroupProperty const &)
0x14004fded  jmp     loc_14004FD0C
```
