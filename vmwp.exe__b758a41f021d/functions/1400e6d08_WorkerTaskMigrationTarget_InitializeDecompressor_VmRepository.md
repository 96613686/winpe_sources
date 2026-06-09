# WorkerTaskMigrationTarget::InitializeDecompressor(VmRepository *)

- ea: `0x1400e6d08`
- end: `0x1400e6f40`
- name: `?InitializeDecompressor@WorkerTaskMigrationTarget@@AEAAJPEAVVmRepository@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(WorkerTaskMigrationTarget *__hidden this, struct VmRepository *)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x140217250`

## callees

- `0x1400364a0`
- `0x140053de8`
- `0x140053f10`
- `0x1400544a8`
- `0x140078628`
- `0x14008a328`
- `0x1400c28cc`
- `0x1400e6d08`
- `0x14011ea40`
- `0x14011edec`
- `0x14021601c`
- `0x140216d68`
- `0x1402cb010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1400e6e47`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1400e6e47`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x1400e6f14`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x1400e6f14`

## string_xrefs

- `0x1400e6d5d`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x1400e6d95`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x1400e6e2a`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x1400e6e68`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x1400e6eaf`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x1400e6ee1`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x1400e6d76`: `/migration/compressor_buffer_size`

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
        (void *)0xB41,
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
        (void *)0xB45,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)(unsigned int)v5,
        (int)v13[0]);
    if ( !v15 || (v15 & 0xFFF) != 0 )
    {
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0xB4A,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)0x8000FFFFLL,
        (int)v13[0]);
      if ( (unsigned int)VmlIsDebugTraceEnabled(0) )
        VmlDebugTraceEx(0, &off_1402E4870);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB4B,
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
          (void *)0xB5C,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
          (const char *)(unsigned int)v10,
          (int)v13[0]);
      Block[1] = _aligned_malloc(*((_QWORD *)this + 73), 0x1000u);
      if ( !Block[1] )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xB64,
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
    LODWORD(v15) = Vml::GetHResultFromThrownExceptionAndTrace((Vml *)0x41E2, (unsigned __int16)&off_1402E4940, v6);
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
0x1400e6d08  mov     r11, rsp
0x1400e6d0b  mov     [r11+18h], rbx
0x1400e6d0f  mov     [r11+20h], rsi
0x1400e6d13  push    rdi
0x1400e6d14  sub     rsp, 50h
0x1400e6d18  mov     rax, cs:__security_cookie
0x1400e6d1f  xor     rax, rsp
0x1400e6d22  mov     [rsp+58h+var_10], rax
0x1400e6d27  mov     rsi, rdx
0x1400e6d2a  mov     rbx, rcx
0x1400e6d2d  xorps   xmm0, xmm0
0x1400e6d30  movups  xmmword ptr [rsp+58h+Block], xmm0
0x1400e6d35  xor     edi, edi
0x1400e6d37  mov     [r11-18h], rdi
0x1400e6d3b  movups  xmmword ptr [rsp+58h+var_38], xmm0; int
0x1400e6d40  lea     r8d, [rdi+1]
0x1400e6d44  lea     rcx, [r11-38h]
0x1400e6d48  call    ??0VmRepositoryAutoLock@@QEAA@PEAVVmRepository@@W4VmRepositoryLockFlags@@@Z; VmRepositoryAutoLock::VmRepositoryAutoLock(VmRepository *,VmRepositoryLockFlags)
0x1400e6d4d  nop
0x1400e6d4e  mov     r9d, dword ptr [rsp+58h+var_38+8]; char *
0x1400e6d53  mov     rcx, [rsp+58h]; this
0x1400e6d58  test    r9d, r9d
0x1400e6d5b  jns     short loc_1400E6D6E
0x1400e6d5d  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x1400e6d64  mov     edx, 0B41h; void *
0x1400e6d69  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400e6d6e  mov     rax, [rsi]
0x1400e6d71  lea     r8, [rsp+58h+var_18]
0x1400e6d76  lea     rdx, ?VM_MIGRATION_COMPRESSOR_BUFFER_SIZE_XPATH@@3QBGB; "/migration/compressor_buffer_size"
0x1400e6d7d  mov     rcx, rsi
0x1400e6d80  mov     rax, [rax+78h]
0x1400e6d84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400e6d89  mov     rcx, [rsp+58h]; this
0x1400e6d8e  test    eax, eax
0x1400e6d90  jns     short loc_1400E6DA6
0x1400e6d92  mov     r9d, eax; char *
0x1400e6d95  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x1400e6d9c  mov     edx, 0B45h; void *
0x1400e6da1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400e6da6  mov     rax, [rsp+58h+var_18]
0x1400e6dab  test    rax, rax
0x1400e6dae  jz      loc_1400E6EA2
0x1400e6db4  test    rax, 0FFFh
0x1400e6dba  jnz     loc_1400E6EA2
0x1400e6dc0  mov     [rbx+248h], rax
0x1400e6dc7  lea     rcx, [rsp+58h+var_38]; this
0x1400e6dcc  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x1400e6dd1  xor     esi, esi
0x1400e6dd3  cmp     esi, 40h ; '@'
0x1400e6dd6  jnb     loc_1400E6EA0
0x1400e6ddc  xorps   xmm0, xmm0
0x1400e6ddf  movups  xmmword ptr [rsp+58h+Block], xmm0
0x1400e6de4  mov     ecx, 18h; Size
0x1400e6de9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400e6dee  mov     rcx, rax
0x1400e6df1  xorps   xmm0, xmm0
0x1400e6df4  xor     eax, eax
0x1400e6df6  movups  xmmword ptr [rcx], xmm0
0x1400e6df9  mov     [rcx+10h], rax
0x1400e6dfd  mov     eax, [rbx+1E0h]
0x1400e6e03  shr     eax, 0Ch
0x1400e6e06  and     eax, 1
0x1400e6e09  mov     dword ptr [rcx], 2
0x1400e6e0f  mov     [rcx+8], eax
0x1400e6e12  mov     [rsp+58h+Block], rcx
0x1400e6e17  xor     edx, edx
0x1400e6e19  call    ?Initialize@XpressCompressor@@QEAAJW4XpressCompressorFlags@@@Z; XpressCompressor::Initialize(XpressCompressorFlags)
0x1400e6e1e  mov     rcx, [rsp+58h]; this
0x1400e6e23  test    eax, eax
0x1400e6e25  jns     short loc_1400E6E3B
0x1400e6e27  mov     r9d, eax; char *
0x1400e6e2a  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x1400e6e31  mov     edx, 0B5Ch; void *
0x1400e6e36  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400e6e3b  mov     edx, 1000h; Alignment
0x1400e6e40  mov     rcx, [rbx+248h]; Size
0x1400e6e47  call    cs:__imp__aligned_malloc
0x1400e6e4e  nop     dword ptr [rax+rax+00h]
0x1400e6e53  mov     [rsp+58h+Block+8], rax
0x1400e6e58  test    rax, rax
0x1400e6e5b  jnz     short loc_1400E6E79
0x1400e6e5d  mov     rcx, [rsp+58h]; this
0x1400e6e62  mov     r9d, 8007000Eh; char *
0x1400e6e68  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x1400e6e6f  mov     edx, 0B64h; void *
0x1400e6e74  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400e6e79  lea     rcx, [rbx+1F0h]; int
0x1400e6e80  lea     rdx, [rsp+58h+Block]
0x1400e6e85  call    ??$Enqueue@AEAUDECOMPRESSOR_INFO@WorkerTaskMigrationTarget@@@?$GmoMigrationQueue@UDECOMPRESSOR_INFO@WorkerTaskMigrationTarget@@@@QEAAXAEAUDECOMPRESSOR_INFO@WorkerTaskMigrationTarget@@@Z; GmoMigrationQueue<WorkerTaskMigrationTarget::DECOMPRESSOR_INFO>::Enqueue<WorkerTaskMigrationTarget::DECOMPRESSOR_INFO &>(WorkerTaskMigrationTarget::DECOMPRESSOR_INFO &)
0x1400e6e8a  xorps   xmm0, xmm0
0x1400e6e8d  movdqa  xmmword ptr [rsp+58h+Block], xmm0
0x1400e6e93  inc     dword ptr [rbx+240h]
0x1400e6e99  inc     esi
0x1400e6e9b  jmp     loc_1400E6DD3
0x1400e6ea0  jmp     short loc_1400E6F20
0x1400e6ea2  mov     rcx, [rsp+58h]; this
0x1400e6ea7  mov     ebx, 8000FFFFh
0x1400e6eac  mov     r9d, ebx; char *
0x1400e6eaf  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x1400e6eb6  mov     edx, 0B4Ah; void *
0x1400e6ebb  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1400e6ec0  xor     ecx, ecx
0x1400e6ec2  call    VmlIsDebugTraceEnabled
0x1400e6ec7  test    eax, eax
0x1400e6ec9  jz      short loc_1400E6ED9
0x1400e6ecb  lea     rdx, off_1402E4870; "Unexpected error.\n"
0x1400e6ed2  xor     ecx, ecx
0x1400e6ed4  call    VmlDebugTraceEx
0x1400e6ed9  mov     rcx, [rsp+58h]; this
0x1400e6ede  mov     r9d, ebx; char *
0x1400e6ee1  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x1400e6ee8  mov     edx, 0B4Bh; void *
0x1400e6eed  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400e6ef3  mov     edi, dword ptr [rsp+58h+var_18]
0x1400e6ef7  test    edi, edi
0x1400e6ef9  jns     short loc_1400E6F20
0x1400e6efb  mov     rcx, [rsp+58h+Block]; this
0x1400e6f00  test    rcx, rcx
0x1400e6f03  jz      short loc_1400E6F0A
0x1400e6f05  call    ??_GXpressCompressor@@QEAAPEAXI@Z; XpressCompressor::`scalar deleting destructor'(uint)
0x1400e6f0a  mov     rcx, [rsp+58h+Block+8]; Block
0x1400e6f0f  test    rcx, rcx
0x1400e6f12  jz      short loc_1400E6F20
0x1400e6f14  call    cs:__imp__aligned_free
0x1400e6f1b  nop     dword ptr [rax+rax+00h]
0x1400e6f20  mov     eax, edi
0x1400e6f22  mov     rcx, [rsp+58h+var_10]
0x1400e6f27  xor     rcx, rsp; StackCookie
0x1400e6f2a  call    __security_check_cookie
0x1400e6f2f  mov     rbx, [rsp+58h+arg_10]
0x1400e6f34  mov     rsi, [rsp+58h+arg_18]
0x1400e6f39  add     rsp, 50h
0x1400e6f3d  pop     rdi
0x1400e6f3e  retn
```
