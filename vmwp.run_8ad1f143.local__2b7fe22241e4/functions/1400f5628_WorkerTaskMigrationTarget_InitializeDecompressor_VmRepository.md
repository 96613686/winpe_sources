# WorkerTaskMigrationTarget::InitializeDecompressor(VmRepository *)

- ea: `0x1400f5628`
- end: `0x1400f5860`
- name: `?InitializeDecompressor@WorkerTaskMigrationTarget@@AEAAJPEAVVmRepository@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(WorkerTaskMigrationTarget *__hidden this, struct VmRepository *)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x140091c40`

## callees

- `0x140042260`
- `0x1400544a8`
- `0x1400545d0`
- `0x14005497c`
- `0x14006af58`
- `0x140078cb8`
- `0x1400d5c84`
- `0x1400f5628`
- `0x140132960`
- `0x140132d0c`
- `0x14022153c`
- `0x140222108`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1400f5767`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1400f5767`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x1400f5834`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x1400f5834`

## string_xrefs

- `0x1400f567d`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x1400f56b5`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x1400f574a`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x1400f5788`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x1400f57cf`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x1400f5801`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x1400f5696`: `/migration/compressor_buffer_size`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WorkerTaskMigrationTarget::InitializeDecompressor(
        WorkerTaskMigrationTarget *this,
        struct VmRepository *a2)
{
  unsigned int v4; // edi
  int v5; // eax
  const struct Vml::ExceptionTraceParameters *v6; // r8
  unsigned int i; // esi
  _QWORD *v8; // rcx
  int v9; // eax
  int v10; // eax
  unsigned int v12; // edx
  char *v13[2]; // [rsp+20h] [rbp-38h] BYREF
  void *Block[2]; // [rsp+30h] [rbp-28h]
  __int64 v15; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  try
  {
    *(_OWORD *)Block = 0;
    v4 = 0;
    v15 = 0;
    *(_OWORD *)v13 = 0;
    VmRepositoryAutoLock::VmRepositoryAutoLock(v13, a2, 1);
    if ( SLODWORD(v13[1]) < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB09,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)LODWORD(v13[1]),
        (int)v13[0]);
    v5 = (*(__int64 (__fastcall **)(struct VmRepository *, const unsigned __int16 *, __int64 *))(*(_QWORD *)a2 + 120LL))(
           a2,
           L"/migration/compressor_buffer_size",
           &v15);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB0D,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)(unsigned int)v5,
        (int)v13[0]);
    if ( !v15 || (v15 & 0xFFF) != 0 )
    {
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0xB12,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)0x8000FFFFLL,
        (int)v13[0]);
      if ( (unsigned int)VmlIsDebugTraceEnabled(0) )
        VmlDebugTraceEx(0, &off_1402DB340);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB13,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)0x8000FFFFLL,
        (int)v13[0]);
    }
    *((_QWORD *)this + 73) = v15;
    VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v13);
    for ( i = 0; i < 0x40; ++i )
    {
      *(_OWORD *)Block = 0;
      v8 = operator new(0x18u);
      *(_OWORD *)v8 = 0;
      v8[2] = 0;
      v9 = (*((_DWORD *)this + 120) >> 12) & 1;
      *(_DWORD *)v8 = 2;
      *((_DWORD *)v8 + 2) = v9;
      Block[0] = v8;
      v10 = XpressCompressor::Initialize(v8, 0);
      if ( v10 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xB24,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
          (const char *)(unsigned int)v10,
          (int)v13[0]);
      Block[1] = _aligned_malloc(*((_QWORD *)this + 73), 0x1000u);
      if ( !Block[1] )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xB2C,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
          (const char *)0x8007000ELL,
          (int)v13[0]);
      GmoMigrationQueue<WorkerTaskMigrationTarget::DECOMPRESSOR_INFO>::Enqueue<WorkerTaskMigrationTarget::DECOMPRESSOR_INFO &>((_DWORD)this + 496);
      *(_OWORD *)Block = 0;
      ++*((_DWORD *)this + 144);
    }
  }
  catch ( ... )
  {
    LODWORD(v15) = Vml::GetHResultFromThrownExceptionAndTrace((Vml *)0x41E2, (unsigned __int16)&off_1402DB420, v6);
    v4 = v15;
    if ( (int)v15 < 0 )
    {
      if ( Block[0] )
        XpressCompressor::`scalar deleting destructor'((XpressCompressor *)Block[0], v12);
      if ( Block[1] )
        _aligned_free(Block[1]);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1400f5628  mov     r11, rsp
0x1400f562b  mov     [r11+18h], rbx
0x1400f562f  mov     [r11+20h], rsi
0x1400f5633  push    rdi
0x1400f5634  sub     rsp, 50h
0x1400f5638  mov     rax, cs:__security_cookie
0x1400f563f  xor     rax, rsp
0x1400f5642  mov     [rsp+58h+var_10], rax
0x1400f5647  mov     rsi, rdx
0x1400f564a  mov     rbx, rcx
0x1400f564d  xorps   xmm0, xmm0
0x1400f5650  movups  xmmword ptr [rsp+58h+Block], xmm0
0x1400f5655  xor     edi, edi
0x1400f5657  mov     [r11-18h], rdi
0x1400f565b  movups  xmmword ptr [rsp+58h+var_38], xmm0; int
0x1400f5660  lea     r8d, [rdi+1]
0x1400f5664  lea     rcx, [r11-38h]
0x1400f5668  call    ??0VmRepositoryAutoLock@@QEAA@PEAVVmRepository@@W4VmRepositoryLockFlags@@@Z; VmRepositoryAutoLock::VmRepositoryAutoLock(VmRepository *,VmRepositoryLockFlags)
0x1400f566d  nop
0x1400f566e  mov     r9d, dword ptr [rsp+58h+var_38+8]; char *
0x1400f5673  mov     rcx, [rsp+58h]; this
0x1400f5678  test    r9d, r9d
0x1400f567b  jns     short loc_1400F568E
0x1400f567d  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x1400f5684  mov     edx, 0B09h; void *
0x1400f5689  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400f568e  mov     rax, [rsi]
0x1400f5691  lea     r8, [rsp+58h+var_18]
0x1400f5696  lea     rdx, ?VM_MIGRATION_COMPRESSOR_BUFFER_SIZE_XPATH@@3QBGB; "/migration/compressor_buffer_size"
0x1400f569d  mov     rcx, rsi
0x1400f56a0  mov     rax, [rax+78h]
0x1400f56a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400f56a9  mov     rcx, [rsp+58h]; this
0x1400f56ae  test    eax, eax
0x1400f56b0  jns     short loc_1400F56C6
0x1400f56b2  mov     r9d, eax; char *
0x1400f56b5  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x1400f56bc  mov     edx, 0B0Dh; void *
0x1400f56c1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400f56c6  mov     rax, [rsp+58h+var_18]
0x1400f56cb  test    rax, rax
0x1400f56ce  jz      loc_1400F57C2
0x1400f56d4  test    rax, 0FFFh
0x1400f56da  jnz     loc_1400F57C2
0x1400f56e0  mov     [rbx+248h], rax
0x1400f56e7  lea     rcx, [rsp+58h+var_38]; this
0x1400f56ec  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x1400f56f1  xor     esi, esi
0x1400f56f3  cmp     esi, 40h ; '@'
0x1400f56f6  jnb     loc_1400F57C0
0x1400f56fc  xorps   xmm0, xmm0
0x1400f56ff  movups  xmmword ptr [rsp+58h+Block], xmm0
0x1400f5704  mov     ecx, 18h; Size
0x1400f5709  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400f570e  mov     rcx, rax
0x1400f5711  xorps   xmm0, xmm0
0x1400f5714  xor     eax, eax
0x1400f5716  movups  xmmword ptr [rcx], xmm0
0x1400f5719  mov     [rcx+10h], rax
0x1400f571d  mov     eax, [rbx+1E0h]
0x1400f5723  shr     eax, 0Ch
0x1400f5726  and     eax, 1
0x1400f5729  mov     dword ptr [rcx], 2
0x1400f572f  mov     [rcx+8], eax
0x1400f5732  mov     [rsp+58h+Block], rcx
0x1400f5737  xor     edx, edx
0x1400f5739  call    ?Initialize@XpressCompressor@@QEAAJW4XpressCompressorFlags@@@Z; XpressCompressor::Initialize(XpressCompressorFlags)
0x1400f573e  mov     rcx, [rsp+58h]; this
0x1400f5743  test    eax, eax
0x1400f5745  jns     short loc_1400F575B
0x1400f5747  mov     r9d, eax; char *
0x1400f574a  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x1400f5751  mov     edx, 0B24h; void *
0x1400f5756  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400f575b  mov     edx, 1000h; Alignment
0x1400f5760  mov     rcx, [rbx+248h]; Size
0x1400f5767  call    cs:__imp__aligned_malloc
0x1400f576e  nop     dword ptr [rax+rax+00h]
0x1400f5773  mov     [rsp+58h+Block+8], rax
0x1400f5778  test    rax, rax
0x1400f577b  jnz     short loc_1400F5799
0x1400f577d  mov     rcx, [rsp+58h]; this
0x1400f5782  mov     r9d, 8007000Eh; char *
0x1400f5788  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x1400f578f  mov     edx, 0B2Ch; void *
0x1400f5794  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400f5799  lea     rcx, [rbx+1F0h]; int
0x1400f57a0  lea     rdx, [rsp+58h+Block]
0x1400f57a5  call    ??$Enqueue@AEAUDECOMPRESSOR_INFO@WorkerTaskMigrationTarget@@@?$GmoMigrationQueue@UDECOMPRESSOR_INFO@WorkerTaskMigrationTarget@@@@QEAAXAEAUDECOMPRESSOR_INFO@WorkerTaskMigrationTarget@@@Z; GmoMigrationQueue<WorkerTaskMigrationTarget::DECOMPRESSOR_INFO>::Enqueue<WorkerTaskMigrationTarget::DECOMPRESSOR_INFO &>(WorkerTaskMigrationTarget::DECOMPRESSOR_INFO &)
0x1400f57aa  xorps   xmm0, xmm0
0x1400f57ad  movdqa  xmmword ptr [rsp+58h+Block], xmm0
0x1400f57b3  inc     dword ptr [rbx+240h]
0x1400f57b9  inc     esi
0x1400f57bb  jmp     loc_1400F56F3
0x1400f57c0  jmp     short loc_1400F5840
0x1400f57c2  mov     rcx, [rsp+58h]; this
0x1400f57c7  mov     ebx, 8000FFFFh
0x1400f57cc  mov     r9d, ebx; char *
0x1400f57cf  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x1400f57d6  mov     edx, 0B12h; void *
0x1400f57db  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1400f57e0  xor     ecx, ecx
0x1400f57e2  call    VmlIsDebugTraceEnabled
0x1400f57e7  test    eax, eax
0x1400f57e9  jz      short loc_1400F57F9
0x1400f57eb  lea     rdx, off_1402DB340; "Unexpected error.\n"
0x1400f57f2  xor     ecx, ecx
0x1400f57f4  call    VmlDebugTraceEx
0x1400f57f9  mov     rcx, [rsp+58h]; this
0x1400f57fe  mov     r9d, ebx; char *
0x1400f5801  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x1400f5808  mov     edx, 0B13h; void *
0x1400f580d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400f5813  mov     edi, dword ptr [rsp+58h+var_18]
0x1400f5817  test    edi, edi
0x1400f5819  jns     short loc_1400F5840
0x1400f581b  mov     rcx, [rsp+58h+Block]; this
0x1400f5820  test    rcx, rcx
0x1400f5823  jz      short loc_1400F582A
0x1400f5825  call    ??_GXpressCompressor@@QEAAPEAXI@Z; XpressCompressor::`scalar deleting destructor'(uint)
0x1400f582a  mov     rcx, [rsp+58h+Block+8]; Block
0x1400f582f  test    rcx, rcx
0x1400f5832  jz      short loc_1400F5840
0x1400f5834  call    cs:__imp__aligned_free
0x1400f583b  nop     dword ptr [rax+rax+00h]
0x1400f5840  mov     eax, edi
0x1400f5842  mov     rcx, [rsp+58h+var_10]
0x1400f5847  xor     rcx, rsp; StackCookie
0x1400f584a  call    __security_check_cookie
0x1400f584f  mov     rbx, [rsp+58h+arg_10]
0x1400f5854  mov     rsi, [rsp+58h+arg_18]
0x1400f5859  add     rsp, 50h
0x1400f585d  pop     rdi
0x1400f585e  retn
```
