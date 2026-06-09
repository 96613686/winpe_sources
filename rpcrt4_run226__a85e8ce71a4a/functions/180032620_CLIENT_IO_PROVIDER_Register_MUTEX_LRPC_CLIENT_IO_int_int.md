# CLIENT_IO_PROVIDER::Register(MUTEX *,LRPC_CLIENT_IO *,int,int)

- ea: `0x180032620`
- end: `0x18003284d`
- name: `?Register@CLIENT_IO_PROVIDER@@QEAAJPEAVMUTEX@@PEAVLRPC_CLIENT_IO@@HH@Z`
- size: `557`
- prototype: `int(CLIENT_IO_PROVIDER *__hidden this, struct MUTEX *, struct LRPC_CLIENT_IO *, int, int)`
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180029798`
- `0x180032074`
- `0x1800637f0`

## callees

- `0x180021ce0`
- `0x180021e70`
- `0x1800274e0`
- `0x1800283bc`
- `0x180028a00`
- `0x180032620`
- `0x180034244`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1800326fa`
- `ntdll!RtlLeaveCriticalSection` at `0x180032755`
- `ntdll!RtlLeaveCriticalSection` at `0x1800327ee`
- `ntdll!RtlLeaveCriticalSection` at `0x180032819`
- `ntdll!RtlLeaveCriticalSection` at `0x1800326fa`
- `ntdll!RtlLeaveCriticalSection` at `0x180032755`
- `ntdll!RtlLeaveCriticalSection` at `0x1800327ee`
- `ntdll!RtlLeaveCriticalSection` at `0x180032819`
- `ntdll!RtlEnterCriticalSection` at `0x180032686`
- `ntdll!RtlEnterCriticalSection` at `0x180032686`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800327ca`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800327ca`

## pseudocode

```c
__int64 __fastcall CLIENT_IO_PROVIDER::Register(
        CLIENT_IO_PROVIDER *this,
        struct _RTL_CRITICAL_SECTION *a2,
        struct LRPC_CLIENT_IO *a3,
        const char *a4,
        int a5)
{
  int v7; // r12d
  int v9; // r8d
  unsigned int i; // ecx
  CLIENT_IO_PROVIDER **v11; // rdx
  int v13; // edx
  EVENT *v14; // rax
  EVENT *v15; // rdi
  __int64 EventW; // rax
  __int64 v17; // rax
  unsigned int v18; // r14d
  unsigned int v19; // edx
  int v20; // [rsp+28h] [rbp-50h]
  int v21; // [rsp+30h] [rbp-48h]

  v7 = (int)a4;
  v9 = (_DWORD)a4 != 0 ? 2 : 0;
  if ( dword_1800F9624 )
  {
    for ( i = 0; i < 4; ++i )
    {
      a4 = "HbBr";
      if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[i] == 80 )
        goto LABEL_8;
    }
    if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
    {
      v13 = v9 | (a5 != 0);
      LOBYTE(a4) = 99;
      LOBYTE(v9) = 80;
      McTemplateU0uuxxx_EtwEventWriteTransfer(i, v13, v9, (_DWORD)a4, (char)this, (char)a3, v13);
    }
  }
LABEL_8:
  RtlEnterCriticalSection(a2);
  if ( (*((_DWORD *)a3 + 6) & 1) != 0 )
  {
    RtlLeaveCriticalSection(a2);
    if ( dword_1800F9624 )
      LogEventToEtw(0x50u, 0x63u, 0, (__int64)a3, 1818);
    RpcpErrorAddRecord(2u, 1818, 0x42Eu, 0, 0);
    return 1818;
  }
  else
  {
    if ( *(_DWORD *)a3 == 1 )
    {
      if ( a5 )
      {
        *((_QWORD *)a3 + 1) = 0;
      }
      else
      {
        v14 = (EVENT *)AllocWrapper(8u);
        v15 = v14;
        if ( !v14 )
        {
          RtlLeaveCriticalSection(a2);
          LogEvent(0x50u, 0x63u, 0, a3, 0xEu, v20, v21);
          return 14;
        }
        *(_QWORD *)v14 = 0;
        EventW = (__int64)CreateEventW(0, 0, 0, 0);
        *(_QWORD *)v15 = EventW;
        v17 = -EventW;
        v18 = v17 == 0 ? 0xE : 0;
        if ( (v17 == 0 ? 0xE : 0) != 0 )
        {
          RtlLeaveCriticalSection(a2);
          EVENT::`scalar deleting destructor'(v15, v19);
          LogEvent(0x50u, 0x63u, 0, a3, v18, v20, v21);
          return v18;
        }
        *((_QWORD *)a3 + 1) = v15;
      }
    }
    v11 = (CLIENT_IO_PROVIDER **)*((_QWORD *)this + 2);
    if ( *v11 != (CLIENT_IO_PROVIDER *)((char *)this + 8) )
      __fastfail(3u);
    *((_QWORD *)a3 + 5) = (char *)this + 8;
    *((_QWORD *)a3 + 6) = v11;
    *v11 = (struct LRPC_CLIENT_IO *)((char *)a3 + 40);
    *((_QWORD *)this + 2) = (char *)a3 + 40;
    if ( a5 )
    {
      *((_BYTE *)this + 25) = 1;
      if ( v7 )
      {
        *((_BYTE *)this + 24) = 1;
      }
      else
      {
        *((_BYTE *)this + 24) = 0;
        *((_DWORD *)a3 + 4) = 1;
      }
    }
    RtlLeaveCriticalSection(a2);
    if ( dword_1800F9624 )
      LogEventToEtw(0x50u, 0x63u, 0, (__int64)a3, 0);
    return 0;
  }
}

```

## disassembly

```asm
0x180032620  push    rbx
0x180032622  push    rbp
0x180032623  push    rsi
0x180032624  push    rdi
0x180032625  push    r12
0x180032627  push    r14
0x180032629  sub     rsp, 48h
0x18003262d  mov     rbx, r8
0x180032630  mov     rbp, rdx
0x180032633  mov     eax, r9d
0x180032636  mov     r12d, r9d
0x180032639  neg     eax
0x18003263b  mov     rsi, rcx
0x18003263e  sbb     r8, r8
0x180032641  xor     edx, edx
0x180032643  and     r8d, 2
0x180032647  cmp     [rsp+78h+arg_20], edx
0x18003264e  setnz   dl
0x180032651  cmp     cs:dword_1800F9624, 0
0x180032658  jz      short loc_180032683
0x18003265a  xor     ecx, ecx
0x18003265c  cmp     ecx, 4
0x18003265f  jnb     short loc_180032676
0x180032661  movsxd  rax, ecx
0x180032664  lea     r9, ?EtwEventSubjectFilter@?1??LogEventToEtw@@YAXEE_J00@Z@4QBEB; "HbBr"
0x18003266b  cmp     byte ptr [rax+r9], 50h ; 'P'
0x180032670  jz      short loc_180032683
0x180032672  inc     ecx
0x180032674  jmp     short loc_18003265C
0x180032676  test    cs:Microsoft_Windows_RPCEnableBits, 8
0x18003267d  jnz     loc_180032730
0x180032683  mov     rcx, rbp; CriticalSection
0x180032686  call    cs:__imp_RtlEnterCriticalSection
0x18003268c  mov     eax, [rbx+18h]
0x18003268f  test    al, 1
0x180032691  jnz     loc_180032752
0x180032697  cmp     dword ptr [rbx], 1
0x18003269a  jnz     short loc_1800326B2
0x18003269c  cmp     [rsp+78h+arg_20], 0
0x1800326a4  jz      loc_1800327A7
0x1800326aa  mov     qword ptr [rbx+8], 0
0x1800326b2  lea     rcx, [rsi+8]
0x1800326b6  mov     rdx, [rcx+8]
0x1800326ba  cmp     [rdx], rcx
0x1800326bd  jnz     loc_180032846
0x1800326c3  cmp     [rsp+78h+arg_20], 0
0x1800326cb  lea     rax, [rbx+28h]
0x1800326cf  mov     [rax], rcx
0x1800326d2  mov     [rax+8], rdx
0x1800326d6  mov     [rdx], rax
0x1800326d9  mov     [rcx+8], rax
0x1800326dd  jz      short loc_1800326F7
0x1800326df  mov     byte ptr [rsi+19h], 1
0x1800326e3  test    r12d, r12d
0x1800326e6  jnz     loc_18003279E
0x1800326ec  mov     [rsi+18h], r12b
0x1800326f0  mov     dword ptr [rbx+10h], 1
0x1800326f7  mov     rcx, rbp; CriticalSection
0x1800326fa  call    cs:__imp_RtlLeaveCriticalSection
0x180032700  cmp     cs:dword_1800F9624, 0
0x180032707  jz      short loc_180032721
0x180032709  mov     r9, rbx; __int64
0x18003270c  mov     [rsp+78h+var_58], 0; __int64
0x180032715  xor     r8d, r8d; __int64
0x180032718  mov     dl, 63h ; 'c'; unsigned __int8
0x18003271a  mov     cl, 50h ; 'P'; unsigned __int8
0x18003271c  call    ?LogEventToEtw@@YAXEE_J00@Z; LogEventToEtw(uchar,uchar,__int64,__int64,__int64)
0x180032721  xor     eax, eax
0x180032723  add     rsp, 48h
0x180032727  pop     r14
0x180032729  pop     r12
0x18003272b  pop     rdi
0x18003272c  pop     rsi
0x18003272d  pop     rbp
0x18003272e  pop     rbx
0x18003272f  retn
0x180032730  or      rdx, r8
0x180032733  mov     r9b, 63h ; 'c'
0x180032736  mov     qword ptr [rsp+78h+var_48], rdx
0x18003273b  mov     r8b, 50h ; 'P'
0x18003273e  mov     [rsp+78h+var_50], rbx
0x180032743  mov     [rsp+78h+var_58], rsi
0x180032748  call    McTemplateU0uuxxx_EtwEventWriteTransfer
0x18003274d  jmp     loc_180032683
0x180032752  mov     rcx, rbp; CriticalSection
0x180032755  call    cs:__imp_RtlLeaveCriticalSection
0x18003275b  cmp     cs:dword_1800F9624, 0
0x180032762  mov     edi, 71Ah
0x180032767  jz      short loc_18003277D
0x180032769  mov     r9, rbx; __int64
0x18003276c  mov     [rsp+78h+var_58], rdi; __int64
0x180032771  xor     r8d, r8d; __int64
0x180032774  mov     dl, 63h ; 'c'; unsigned __int8
0x180032776  mov     cl, 50h ; 'P'; unsigned __int8
0x180032778  call    ?LogEventToEtw@@YAXEE_J00@Z; LogEventToEtw(uchar,uchar,__int64,__int64,__int64)
0x18003277d  xor     r9d, r9d; int
0x180032780  mov     [rsp+78h+var_58], 0; struct tagParam *
0x180032789  mov     r8d, 42Eh; unsigned __int16
0x18003278f  mov     edx, edi; int
0x180032791  lea     ecx, [r9+2]; unsigned int
0x180032795  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x18003279a  mov     eax, edi
0x18003279c  jmp     short loc_180032723
0x18003279e  mov     byte ptr [rsi+18h], 1
0x1800327a2  jmp     loc_1800326F7
0x1800327a7  mov     ecx, 8; dwBytes
0x1800327ac  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x1800327b1  mov     rdi, rax
0x1800327b4  test    rax, rax
0x1800327b7  jz      short loc_1800327EB
0x1800327b9  xor     r9d, r9d; lpName
0x1800327bc  mov     qword ptr [rax], 0
0x1800327c3  xor     r8d, r8d; bInitialState
0x1800327c6  xor     edx, edx; bManualReset
0x1800327c8  xor     ecx, ecx; lpEventAttributes
0x1800327ca  call    cs:__imp_CreateEventW
0x1800327d0  mov     [rdi], rax
0x1800327d3  neg     rax
0x1800327d6  sbb     r14d, r14d
0x1800327d9  not     r14d
0x1800327dc  and     r14d, 0Eh
0x1800327e0  jnz     short loc_180032816
0x1800327e2  mov     [rbx+8], rdi
0x1800327e6  jmp     loc_1800326B2
0x1800327eb  mov     rcx, rbp; CriticalSection
0x1800327ee  call    cs:__imp_RtlLeaveCriticalSection
0x1800327f4  mov     r9, rbx; void *
0x1800327f7  mov     [rsp+78h+var_58], 0Eh; unsigned __int64
0x180032800  xor     r8d, r8d; void *
0x180032803  mov     dl, 63h ; 'c'; unsigned __int8
0x180032805  mov     cl, 50h ; 'P'; unsigned __int8
0x180032807  call    ?LogEvent@@YAXEEPEAX0_KHH@Z; LogEvent(uchar,uchar,void *,void *,unsigned __int64,int,int)
0x18003280c  mov     eax, 0Eh
0x180032811  jmp     loc_180032723
0x180032816  mov     rcx, rbp; CriticalSection
0x180032819  call    cs:__imp_RtlLeaveCriticalSection
0x18003281f  mov     rcx, rdi; this
0x180032822  call    ??_GEVENT@@QEAAPEAXI@Z; EVENT::`scalar deleting destructor'(uint)
0x180032827  mov     ecx, r14d
0x18003282a  mov     r9, rbx; void *
0x18003282d  mov     [rsp+78h+var_58], rcx; unsigned __int64
0x180032832  xor     r8d, r8d; void *
0x180032835  mov     cl, 50h ; 'P'; unsigned __int8
0x180032837  mov     dl, 63h ; 'c'; unsigned __int8
0x180032839  call    ?LogEvent@@YAXEEPEAX0_KHH@Z; LogEvent(uchar,uchar,void *,void *,unsigned __int64,int,int)
0x18003283e  mov     eax, r14d
0x180032841  jmp     loc_180032723
0x180032846  mov     ecx, 3
0x18003284b  int     29h; Win8: RtlFailFast(ecx)
```
