# CTpSrvClients::OnQCCTimer(void)

- ea: `0x18001038c`
- end: `0x180010506`
- name: `?OnQCCTimer@CTpSrvClients@@AEAAXXZ`
- size: `378`
- prototype: `void __fastcall(CTpSrvClients *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800109f0`

## callees

- `0x18000ff2c`
- `0x18001038c`
- `0x1800107d4`
- `0x180010884`
- `0x180010ac8`
- `0x18001a9a8`
- `0x180025850`
- `0x180026d70`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800104ff`
- `KERNEL32!EnterCriticalSection` at `0x1800103b3`
- `KERNEL32!EnterCriticalSection` at `0x1800103b3`

## string_xrefs

- `0x180010445`: `WDSMCTP[0x%x] Client=0x%x did not complete JOIN handshake. Deleting client info.`

## pseudocode

```c
void __fastcall CTpSrvClients::OnQCCTimer(LPCRITICAL_SECTION *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // r15
  int v3; // r14d
  int v4; // eax
  LPCRITICAL_SECTION v5; // rcx
  int v6; // eax
  __int64 v7; // rbx
  __int64 v8; // r8
  unsigned int v9; // eax
  const char *v10; // rdx
  unsigned int v11; // eax
  const char *v12; // rdx
  __int128 v13; // [rsp+30h] [rbp-20h] BYREF
  __int128 v14; // [rsp+40h] [rbp-10h] BYREF

  v1 = *this;
  v3 = 0;
  EnterCriticalSection(*this);
  v4 = 0;
  v5 = this[18];
  v13 = 0u;
  if ( v5 )
  {
    *((_QWORD *)&v13 + 1) = v5;
  }
  else
  {
    *((_QWORD *)&v13 + 1) = 0;
    CSmHashTable<CTpSrvClients::Client,CNoLock,113>::MoveNext(this + 17, &v13);
    v4 = v13;
  }
  v14 = v13;
  if ( v4 )
    goto LABEL_18;
  v6 = v14;
  do
  {
    v7 = 0;
    if ( !v6 )
      v7 = *((_QWORD *)&v14 + 1);
    if ( *(_DWORD *)(v7 + 3212) )
    {
      CSmHashTable<CTpSrvClients::Client,CNoLock,113>::MoveNext(this + 17, &v14);
    }
    else if ( *(_DWORD *)(v7 + 1152) < 3u )
    {
      v9 = CTpSrvClients::SendJoinAck((CTpSrvClients *)this, (struct CTpSrvClients::Client *)v7);
      ElValidateWin32(v9, v10, "base\\eco\\wds\\transport\\server\\mc\\tpsrvclients.cpp", 0x308u);
      CSmHashTable<CTpSrvClients::Client,CNoLock,113>::MoveNext(this + 17, &v14);
      ++v3;
    }
    else
    {
      if ( g_ErrLibTraceFunctionEx )
      {
        v8 = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)&this[358][55].OwningThread, 0);
        g_ErrLibTraceFunctionEx(
          0x10000u,
          L"WDSMCTP[0x%x] Client=0x%x did not complete JOIN handshake. Deleting client info.",
          v8,
          *(unsigned int *)(v7 + 1148));
      }
      CSmHashTable<CTpSrvClients::Client,CNoLock,113>::EnumRemoveAt(this + 17, &v14);
      operator delete((void *)v7);
    }
    v6 = v14;
  }
  while ( !(_DWORD)v14 );
  if ( !v3 )
  {
LABEL_18:
    *((_DWORD *)this + 18) = 0;
  }
  else
  {
    v11 = CTimer<CTpSrvClients>::Change((__int64)(this + 2));
    ElValidateWin32(v11, v12, "base\\eco\\wds\\transport\\server\\mc\\tpsrvclients.cpp", 0x317u);
  }
  LeaveCriticalSection(v1);
}

```

## disassembly

```asm
0x18001038c  mov     [rsp-18h+arg_0], rbx
0x180010391  mov     [rsp-18h+arg_8], rsi
0x180010396  mov     [rsp-18h+arg_10], rdi
0x18001039b  push    rbp
0x18001039c  push    r14
0x18001039e  push    r15
0x1800103a0  mov     rbp, rsp
0x1800103a3  sub     rsp, 50h
0x1800103a7  mov     r15, [rcx]
0x1800103aa  mov     rdi, rcx
0x1800103ad  mov     rcx, r15; lpCriticalSection
0x1800103b0  xor     r14d, r14d
0x1800103b3  call    cs:__imp_EnterCriticalSection
0x1800103b9  xor     eax, eax
0x1800103bb  lea     rsi, [rdi+88h]
0x1800103c2  mov     rcx, [rsi+8]
0x1800103c6  mov     qword ptr [rbp+var_20], rax
0x1800103ca  mov     qword ptr [rbp+var_20+8], rax
0x1800103ce  test    rcx, rcx
0x1800103d1  jnz     short loc_1800103E9
0x1800103d3  and     qword ptr [rbp+var_20+8], rax
0x1800103d7  lea     rdx, [rbp+var_20]
0x1800103db  mov     rcx, rsi
0x1800103de  call    ?MoveNext@?$CSmHashTable@UClient@CTpSrvClients@@VCNoLock@@$0HB@@@AEAAXAEAU_SMHTPOS@@@Z; CSmHashTable<CTpSrvClients::Client,CNoLock,113>::MoveNext(_SMHTPOS &)
0x1800103e3  mov     rax, qword ptr [rbp+var_20]
0x1800103e7  jmp     short loc_1800103ED
0x1800103e9  mov     qword ptr [rbp+var_20+8], rcx
0x1800103ed  movaps  xmm0, [rbp+var_20]
0x1800103f1  movdqa  [rbp+var_10], xmm0
0x1800103f6  test    eax, eax
0x1800103f8  jnz     loc_1800104DF
0x1800103fe  mov     eax, dword ptr [rbp+var_10]
0x180010401  xor     ebx, ebx
0x180010403  test    eax, eax
0x180010405  jnz     short loc_18001040B
0x180010407  mov     rbx, qword ptr [rbp+var_10+8]
0x18001040b  cmp     dword ptr [rbx+0C8Ch], 0
0x180010412  jnz     loc_1800104A4
0x180010418  cmp     dword ptr [rbx+480h], 3
0x18001041f  jb      short loc_180010474
0x180010421  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180010429  jz      short loc_18001045E
0x18001042b  mov     rax, [rdi+0B30h]
0x180010432  xor     r8d, r8d
0x180010435  lock xadd [rax+8A8h], r8d
0x18001043e  mov     r9d, [rbx+47Ch]
0x180010445  lea     rdx, aWdsmctp0xXClie_0; "WDSMCTP[0x%x] Client=0x%x did not compl"...
0x18001044c  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180010453  mov     ecx, 10000h
0x180010458  call    cs:__guard_dispatch_icall_fptr
0x18001045e  lea     rdx, [rbp+var_10]
0x180010462  mov     rcx, rsi
0x180010465  call    ?EnumRemoveAt@?$CSmHashTable@UClient@CTpSrvClients@@VCNoLock@@$0HB@@@QEAAPEAUClient@CTpSrvClients@@AEAU_SMHTPOS@@@Z; CSmHashTable<CTpSrvClients::Client,CNoLock,113>::EnumRemoveAt(_SMHTPOS &)
0x18001046a  mov     rcx, rbx; void *
0x18001046d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180010472  jmp     short loc_1800104B0
0x180010474  mov     rdx, rbx; struct CTpSrvClients::Client *
0x180010477  mov     rcx, rdi; this
0x18001047a  call    ?SendJoinAck@CTpSrvClients@@AEAAKPEAUClient@1@@Z; CTpSrvClients::SendJoinAck(CTpSrvClients::Client *)
0x18001047f  mov     ecx, eax; unsigned int
0x180010481  lea     r8, aBaseEcoWdsTran_13; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180010488  mov     r9d, 308h; unsigned int
0x18001048e  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180010493  lea     rdx, [rbp+var_10]
0x180010497  mov     rcx, rsi
0x18001049a  call    ?MoveNext@?$CSmHashTable@UClient@CTpSrvClients@@VCNoLock@@$0HB@@@AEAAXAEAU_SMHTPOS@@@Z; CSmHashTable<CTpSrvClients::Client,CNoLock,113>::MoveNext(_SMHTPOS &)
0x18001049f  inc     r14d
0x1800104a2  jmp     short loc_1800104B0
0x1800104a4  lea     rdx, [rbp+var_10]
0x1800104a8  mov     rcx, rsi
0x1800104ab  call    ?MoveNext@?$CSmHashTable@UClient@CTpSrvClients@@VCNoLock@@$0HB@@@AEAAXAEAU_SMHTPOS@@@Z; CSmHashTable<CTpSrvClients::Client,CNoLock,113>::MoveNext(_SMHTPOS &)
0x1800104b0  mov     eax, dword ptr [rbp+var_10]
0x1800104b3  test    eax, eax
0x1800104b5  jz      loc_180010401
0x1800104bb  test    r14d, r14d
0x1800104be  jz      short loc_1800104DF
0x1800104c0  lea     rcx, [rdi+10h]
0x1800104c4  call    ?Change@?$CTimer@VCTpSrvClients@@@@QEAAKKK@Z; CTimer<CTpSrvClients>::Change(ulong,ulong)
0x1800104c9  mov     ecx, eax; unsigned int
0x1800104cb  lea     r8, aBaseEcoWdsTran_13; "base\\eco\\wds\\transport\\server\\mc\\"...
0x1800104d2  mov     r9d, 317h; unsigned int
0x1800104d8  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800104dd  jmp     short loc_1800104E3
0x1800104df  and     dword ptr [rdi+48h], 0
0x1800104e3  mov     rcx, r15
0x1800104e6  lea     r11, [rsp+50h+var_s0]
0x1800104eb  mov     rbx, [r11+20h]
0x1800104ef  mov     rsi, [r11+28h]
0x1800104f3  mov     rdi, [r11+30h]
0x1800104f7  mov     rsp, r11
0x1800104fa  pop     r15
0x1800104fc  pop     r14
0x1800104fe  pop     rbp
0x1800104ff  jmp     cs:__imp_LeaveCriticalSection
```
