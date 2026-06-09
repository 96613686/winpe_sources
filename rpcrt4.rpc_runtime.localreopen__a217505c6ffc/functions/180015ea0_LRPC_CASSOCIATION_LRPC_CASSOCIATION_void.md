# LRPC_CASSOCIATION::~LRPC_CASSOCIATION(void)

- ea: `0x180015ea0`
- end: `0x1800160a7`
- name: `??1LRPC_CASSOCIATION@@UEAA@XZ`
- size: `519`
- prototype: `void __fastcall(LRPC_CASSOCIATION *__hidden this)`
- caller_count: `2`
- callee_count: `12`
- tags: `reparse_path, authz_impersonation, loader_planting`

## callers

- `0x180015cc0`
- `0x1800bd1bc`

## callees

- `0x180015ea0`
- `0x1800160b0`
- `0x1800160dc`
- `0x1800169ec`
- `0x180022e80`
- `0x180023a40`
- `0x180028670`
- `0x180029f90`
- `0x18003227c`
- `0x180088d9c`
- `0x1800bc6e4`
- `0x1800d7010`

## import_xrefs

- `ntdll!NtClose` at `0x180015fa7`
- `ntdll!NtClose` at `0x180015fa7`
- `ntdll!RtlDeleteCriticalSection` at `0x18001605a`
- `ntdll!RtlDeleteCriticalSection` at `0x18001605a`

## pseudocode

```c
void __fastcall LRPC_CASSOCIATION::~LRPC_CASSOCIATION(LRPC_CASSOCIATION *this)
{
  int v2; // ecx
  __int64 v3; // rcx
  LRPC_CASSOCIATION *v4; // rsi
  LRPC_CASSOCIATION *v5; // rbx
  void *v6; // rcx
  unsigned int i; // eax
  __int64 v8; // rcx
  unsigned int v9; // esi
  __int64 v10; // rax
  void *v11; // rdx
  int v12; // ecx
  unsigned int v13; // edx
  RPC_THREAD_POOL_ALPC *v14; // rcx
  LRPC_CASSOCIATION *v15; // rcx
  char *v16; // rbx
  void *v17; // rcx
  LRPC_CASSOCIATION *v18; // rcx
  LRPC_BROKEN_PIPE_DATA *v19; // rbp
  unsigned int v20; // edx
  int v21; // [rsp+28h] [rbp-40h]
  int v22; // [rsp+30h] [rbp-38h]

  *(_QWORD *)this = &LRPC_CASSOCIATION::`vftable';
  v2 = *((_DWORD *)this + 19) - 2;
  if ( v2 )
  {
    v12 = v2 - 2;
    if ( !v12 )
    {
LABEL_19:
      LRPC_CASSOCIATION::TrimCachedViews(this, 1);
      LogEvent(0x4Cu, 0x64u, *((void **)this + 17), 0, 0, v21, v22);
      NtClose(*((HANDLE *)this + 17));
      v14 = (RPC_THREAD_POOL_ALPC *)*((_QWORD *)this + 29);
      *((_QWORD *)this + 17) = 0;
      *((_DWORD *)this + 82) = -1;
      if ( v14 )
      {
        RPC_THREAD_POOL_ALPC::`scalar deleting destructor'(v14, v13);
        *((_QWORD *)this + 29) = 0;
      }
      goto LABEL_5;
    }
    if ( v12 != 1 )
      goto LABEL_5;
  }
  v3 = *((_QWORD *)this + 36);
  if ( v3 )
  {
    FreeEEInfoChain(v3);
    *((_QWORD *)this + 36) = 0;
  }
  if ( *((_DWORD *)this + 19) != 2 )
    goto LABEL_19;
LABEL_5:
  v4 = (LRPC_CASSOCIATION *)*((_QWORD *)this + 38);
  while ( v4 != (LRPC_CASSOCIATION *)((char *)this + 304) )
  {
    v15 = v4;
    v16 = (char *)v4 - 24;
    v4 = *(LRPC_CASSOCIATION **)v4;
    RpcpfRemoveEntryListAndZeroOutLinks(v15);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v16 + 32LL))(v16);
  }
  v5 = (LRPC_CASSOCIATION *)*((_QWORD *)this + 45);
  while ( v5 != (LRPC_CASSOCIATION *)((char *)this + 360) )
  {
    v18 = v5;
    v19 = (LRPC_CASSOCIATION *)((char *)v5 - 24);
    v5 = *(LRPC_CASSOCIATION **)v5;
    RpcpfRemoveEntryListAndZeroOutLinks(v18);
    if ( v19 )
      LRPC_BROKEN_PIPE_DATA::`scalar deleting destructor'(v19, v20);
  }
  v6 = (void *)*((_QWORD *)this + 42);
  if ( v6 )
  {
    FreeWrapper(v6);
    *((_QWORD *)this + 42) = 0;
  }
  for ( i = 0; i < *((_DWORD *)this + 24); i = v9 )
  {
    v8 = i;
    v9 = i + 1;
    v10 = *((_QWORD *)this + 11);
    v11 = *(void **)(v10 + 8 * v8);
    if ( v11 )
    {
      --*((_DWORD *)this + 25);
      *(_QWORD *)(v10 + 8 * v8) = 0;
      FreeWrapper(v11);
    }
  }
  v17 = (void *)*((_QWORD *)this + 10);
  if ( v17 )
  {
    FreeWrapper(v17);
    *((_QWORD *)this + 10) = 0;
  }
  if ( dword_1800FE624 )
    LogEventToEtw(0x61u, 0x64u, (__int64)this, 0, 0);
  LPC_NORMALIZED_SID::FreeOldSid((LRPC_CASSOCIATION *)((char *)this + 192));
  RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 144));
  QUEUE::~QUEUE((LRPC_CASSOCIATION *)((char *)this + 88));
  *((_DWORD *)this + 2) = -1713459815;
}

```

## disassembly

```asm
0x180015ea0  push    rbx
0x180015ea2  push    rbp
0x180015ea3  push    rsi
0x180015ea4  push    rdi
0x180015ea5  push    r14
0x180015ea7  sub     rsp, 40h
0x180015eab  mov     rdi, rcx
0x180015eae  lea     rax, ??_7LRPC_CASSOCIATION@@6B@; const LRPC_CASSOCIATION::`vftable'
0x180015eb5  mov     [rcx], rax
0x180015eb8  mov     ecx, [rcx+4Ch]
0x180015ebb  sub     ecx, 2
0x180015ebe  jnz     loc_180015F64
0x180015ec4  mov     rcx, [rdi+120h]
0x180015ecb  test    rcx, rcx
0x180015ece  jz      short loc_180015EE0
0x180015ed0  call    FreeEEInfoChain
0x180015ed5  mov     qword ptr [rdi+120h], 0
0x180015ee0  cmp     dword ptr [rdi+4Ch], 2
0x180015ee4  jnz     loc_180015F77
0x180015eea  lea     r14, [rdi+130h]
0x180015ef1  mov     rsi, [r14]
0x180015ef4  cmp     rsi, r14
0x180015ef7  jnz     loc_180015FED
0x180015efd  lea     rsi, [rdi+168h]
0x180015f04  mov     rbx, [rsi]
0x180015f07  cmp     rbx, rsi
0x180015f0a  jnz     loc_180016082
0x180015f10  mov     rcx, [rdi+150h]; lpMem
0x180015f17  test    rcx, rcx
0x180015f1a  jnz     short loc_180015F52
0x180015f1c  xor     eax, eax
0x180015f1e  cmp     eax, [rdi+60h]
0x180015f21  jnb     loc_180016010
0x180015f27  mov     ecx, eax
0x180015f29  lea     esi, [rax+1]
0x180015f2c  mov     rax, [rdi+58h]
0x180015f30  mov     rdx, [rax+rcx*8]
0x180015f34  test    rdx, rdx
0x180015f37  jnz     short loc_180015F3D
0x180015f39  mov     eax, esi
0x180015f3b  jmp     short loc_180015F1E
0x180015f3d  dec     dword ptr [rdi+64h]
0x180015f40  mov     qword ptr [rax+rcx*8], 0
0x180015f48  mov     rcx, rdx; lpMem
0x180015f4b  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x180015f50  jmp     short loc_180015F39
0x180015f52  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x180015f57  mov     qword ptr [rdi+150h], 0
0x180015f62  jmp     short loc_180015F1C
0x180015f64  sub     ecx, 2
0x180015f67  jz      short loc_180015F77
0x180015f69  cmp     ecx, 1
0x180015f6c  jnz     loc_180015EEA
0x180015f72  jmp     loc_180015EC4
0x180015f77  mov     edx, 1; int
0x180015f7c  mov     rcx, rdi; this
0x180015f7f  call    ?TrimCachedViews@LRPC_CASSOCIATION@@AEAAXH@Z; LRPC_CASSOCIATION::TrimCachedViews(int)
0x180015f84  mov     r8, [rdi+88h]; void *
0x180015f8b  xor     r9d, r9d; void *
0x180015f8e  mov     dl, 64h ; 'd'; unsigned __int8
0x180015f90  mov     [rsp+68h+var_48], 0; unsigned __int64
0x180015f99  mov     cl, 4Ch ; 'L'; unsigned __int8
0x180015f9b  call    ?LogEvent@@YAXEEPEAX0_KHH@Z; LogEvent(uchar,uchar,void *,void *,unsigned __int64,int,int)
0x180015fa0  mov     rcx, [rdi+88h]; Handle
0x180015fa7  call    cs:__imp_NtClose
0x180015fae  nop     dword ptr [rax+rax+00h]
0x180015fb3  mov     rcx, [rdi+0E8h]; this
0x180015fba  mov     qword ptr [rdi+88h], 0
0x180015fc5  mov     dword ptr [rdi+148h], 0FFFFFFFFh
0x180015fcf  test    rcx, rcx
0x180015fd2  jz      loc_180015EEA
0x180015fd8  call    ??_GRPC_THREAD_POOL_ALPC@@QEAAPEAXI@Z; RPC_THREAD_POOL_ALPC::`scalar deleting destructor'(uint)
0x180015fdd  mov     qword ptr [rdi+0E8h], 0
0x180015fe8  jmp     loc_180015EEA
0x180015fed  mov     rcx, rsi
0x180015ff0  lea     rbx, [rsi-18h]
0x180015ff4  mov     rsi, [rsi]
0x180015ff7  call    RpcpfRemoveEntryListAndZeroOutLinks
0x180015ffc  mov     rax, [rbx]
0x180015fff  mov     rcx, rbx
0x180016002  mov     rax, [rax+20h]
0x180016006  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001600b  jmp     loc_180015EF4
0x180016010  mov     rcx, [rdi+50h]; lpMem
0x180016014  test    rcx, rcx
0x180016017  jz      short loc_180016026
0x180016019  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18001601e  mov     qword ptr [rdi+50h], 0
0x180016026  cmp     cs:dword_1800FE624, 0
0x18001602d  jz      short loc_180016047
0x18001602f  xor     r9d, r9d; __int64
0x180016032  mov     [rsp+68h+var_48], 0; __int64
0x18001603b  mov     r8, rdi; __int64
0x18001603e  mov     dl, 64h ; 'd'; unsigned __int8
0x180016040  mov     cl, 61h ; 'a'; unsigned __int8
0x180016042  call    ?LogEventToEtw@@YAXEE_J00@Z; LogEventToEtw(uchar,uchar,__int64,__int64,__int64)
0x180016047  lea     rcx, [rdi+0C0h]; this
0x18001604e  call    ?FreeOldSid@LPC_NORMALIZED_SID@@AEAAXXZ; LPC_NORMALIZED_SID::FreeOldSid(void)
0x180016053  lea     rcx, [rdi+90h]; CriticalSection
0x18001605a  call    cs:__imp_RtlDeleteCriticalSection
0x180016061  nop     dword ptr [rax+rax+00h]
0x180016066  lea     rcx, [rdi+58h]; this
0x18001606a  call    ??1QUEUE@@QEAA@XZ; QUEUE::~QUEUE(void)
0x18001606f  mov     dword ptr [rdi+8], 99DEAD99h
0x180016076  add     rsp, 40h
0x18001607a  pop     r14
0x18001607c  pop     rdi
0x18001607d  pop     rsi
0x18001607e  pop     rbp
0x18001607f  pop     rbx
0x180016080  retn
0x180016082  mov     rcx, rbx
0x180016085  lea     rbp, [rbx-18h]
0x180016089  mov     rbx, [rbx]
0x18001608c  call    RpcpfRemoveEntryListAndZeroOutLinks
0x180016091  test    rbp, rbp
0x180016094  jz      loc_180015F07
0x18001609a  mov     rcx, rbp; this
0x18001609d  call    ??_GLRPC_BROKEN_PIPE_DATA@@QEAAPEAXI@Z; LRPC_BROKEN_PIPE_DATA::`scalar deleting destructor'(uint)
0x1800160a2  jmp     loc_180015F07
```
