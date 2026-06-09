# CMcCoClients::RemoveClient(ulong,ulong)

- ea: `0x18000b8e8`
- end: `0x18000bb05`
- name: `?RemoveClient@CMcCoClients@@QEAAKKK@Z`
- size: `541`
- prototype: `unsigned int __fastcall(CMcCoClients *__hidden this, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180017b50`

## callees

- `0x180003c0c`
- `0x18000b8e8`
- `0x18000c2f0`
- `0x18001a9a8`
- `0x1800229c0`
- `0x180024228`
- `0x180026670`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000b998`
- `KERNEL32!LeaveCriticalSection` at `0x18000b998`
- `KERNEL32!EnterCriticalSection` at `0x18000b92a`
- `KERNEL32!EnterCriticalSection` at `0x18000b92a`
- `WdsDiag!WdsDiagRecordEvent` at `0x18000bad7`
- `WdsDiag!WdsDiagRecordEvent` at `0x18000bad7`

## pseudocode

```c
__int64 __fastcall CMcCoClients::RemoveClient(struct _RTL_CRITICAL_SECTION **this, __int64 a2, unsigned int a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // r15
  unsigned int v5; // ebx
  struct _RTL_CRITICAL_SECTION *v6; // rcx
  struct _RTL_CRITICAL_SECTION **v8; // r8
  struct _RTL_CRITICAL_SECTION *SpinCount; // rax
  struct _RTL_CRITICAL_SECTION *v10; // rcx
  struct _RTL_CRITICAL_SECTION *v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rdi
  const unsigned __int16 *v15; // r8
  unsigned __int16 *v16; // r9
  struct _RTL_CRITICAL_SECTION *v17; // rsi
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // r10
  __int64 v22; // rax
  __int64 v23; // [rsp+20h] [rbp-E0h]
  struct _RTL_CRITICAL_SECTION *v24; // [rsp+80h] [rbp-80h] BYREF
  BOOL v25; // [rsp+90h] [rbp-70h]
  unsigned __int16 v26[70]; // [rsp+94h] [rbp-6Ch] BYREF
  int v27; // [rsp+120h] [rbp+20h] BYREF
  __int16 v28; // [rsp+124h] [rbp+24h] BYREF

  v3 = *this;
  v5 = 0;
  v6 = *this;
  v26[0] = 0;
  v28 = 0;
  EnterCriticalSection(v6);
  v8 = &this[3 * (a3 % 0x71)];
  SpinCount = v8[4];
  if ( !SpinCount )
    goto LABEL_6;
  v24 = v8[4];
  v10 = SpinCount;
  v11 = SpinCount;
  while ( 1 )
  {
    v12 = -(__int64)v10;
    v13 = (unsigned __int64)v11 & -(__int64)(v12 != 0);
    if ( *(_DWORD *)(v13 + 0x878) == a3 && *(_DWORD *)(((unsigned __int64)v11 & -(__int64)(v12 != 0)) + 4) == a3 )
      break;
    SpinCount = (struct _RTL_CRITICAL_SECTION *)SpinCount[53].SpinCount;
    v24 = SpinCount;
    v10 = SpinCount;
    v11 = SpinCount;
    if ( !SpinCount )
      goto LABEL_6;
  }
  CList<CMcCoClients::Client,CNoLock>::DeleteAt(v8 + 4, &v24);
  --*((_DWORD *)this + 686);
  if ( v13 )
  {
    v25 = HexToString((const unsigned __int8 *)(v13 + 60), *(unsigned int *)(v13 + 76), v26, 0x40u) != 0;
    CIPString::Initialize((CIPString *)&v27, (struct tagWDS_IP_ADDRESS6 *)(v13 + 40));
    v15 = (const unsigned __int16 *)&v28;
    v16 = v26;
    v17 = this[2];
    if ( v27 )
      v15 = L"<<Failed>>";
    if ( v25 )
      v16 = L"<<Failed>>";
    v18 = -1;
    v19 = -1;
    do
      ++v19;
    while ( *(_WORD *)(this[1][5].SpinCount + 2 * v19) );
    v20 = -1;
    do
      ++v20;
    while ( *((_WORD *)&v17->DebugInfo + v20) );
    v21 = 2 * v20 + 2;
    v22 = -1;
    do
      ++v22;
    while ( v15[v22] );
    do
      ++v18;
    while ( v16[v18] );
    WdsDiagRecordEvent(2, 24, 4, 1, 2 * v18 + 2, v16, 1, 2 * v22 + 2, v15, 1, v21, v17, 1);
    operator delete((void *)v13);
    LODWORD(v23) = 1;
    CPerfCounters::Batch((CPerfCounters *)&qword_1800336A0, 1u, 2, 1, v23);
  }
  else
  {
LABEL_6:
    v5 = 2;
  }
  LeaveCriticalSection(v3);
  return v5;
}

```

## disassembly

```asm
0x18000b8e8  mov     [rsp-8+arg_8], rbx
0x18000b8ed  push    rbp
0x18000b8ee  push    rsi
0x18000b8ef  push    rdi
0x18000b8f0  push    r14
0x18000b8f2  push    r15
0x18000b8f4  lea     rbp, [rsp-0C0h]
0x18000b8fc  sub     rsp, 1C0h
0x18000b903  mov     rax, cs:__security_cookie
0x18000b90a  xor     rax, rsp
0x18000b90d  mov     [rbp+0E0h+var_30], rax
0x18000b914  mov     r15, [rcx]
0x18000b917  mov     r14, rcx
0x18000b91a  xor     ebx, ebx
0x18000b91c  mov     rcx, r15; lpCriticalSection
0x18000b91f  mov     esi, r8d
0x18000b922  mov     [rbp+0E0h+var_14C], bx
0x18000b926  mov     [rbp+0E0h+var_BC], bx
0x18000b92a  call    cs:__imp_EnterCriticalSection
0x18000b930  mov     eax, 21FB7813h
0x18000b935  mov     ecx, esi
0x18000b937  mul     esi
0x18000b939  mov     eax, esi
0x18000b93b  sub     eax, edx
0x18000b93d  shr     eax, 1
0x18000b93f  add     eax, edx
0x18000b941  shr     eax, 6
0x18000b944  imul    eax, 71h ; 'q'
0x18000b947  sub     ecx, eax
0x18000b949  lea     rcx, [rcx+rcx*2]
0x18000b94d  lea     r8, [r14+rcx*8]
0x18000b951  mov     rax, [r8+20h]
0x18000b955  test    rax, rax
0x18000b958  jz      short loc_18000B990
0x18000b95a  mov     [rbp+0E0h+var_160], rax
0x18000b95e  mov     rcx, rax
0x18000b961  mov     rdx, rax
0x18000b964  neg     rcx
0x18000b967  sbb     rdi, rdi
0x18000b96a  and     rdi, rdx
0x18000b96d  cmp     [rdi+878h], esi
0x18000b973  jnz     short loc_18000B97A
0x18000b975  cmp     [rdi+4], esi
0x18000b978  jz      short loc_18000B9C6
0x18000b97a  mov     rax, [rax+868h]
0x18000b981  mov     [rbp+0E0h+var_160], rax
0x18000b985  mov     rcx, rax
0x18000b988  mov     rdx, rax
0x18000b98b  test    rax, rax
0x18000b98e  jnz     short loc_18000B964
0x18000b990  mov     ebx, 2
0x18000b995  mov     rcx, r15; lpCriticalSection
0x18000b998  call    cs:__imp_LeaveCriticalSection
0x18000b99e  mov     eax, ebx
0x18000b9a0  mov     rcx, [rbp+0E0h+var_30]
0x18000b9a7  xor     rcx, rsp; StackCookie
0x18000b9aa  call    __security_check_cookie
0x18000b9af  mov     rbx, [rsp+1E0h+arg_8]
0x18000b9b7  add     rsp, 1C0h
0x18000b9be  pop     r15
0x18000b9c0  pop     r14
0x18000b9c2  pop     rdi
0x18000b9c3  pop     rsi
0x18000b9c4  pop     rbp
0x18000b9c5  retn
0x18000b9c6  lea     rdx, [rbp+0E0h+var_160]
0x18000b9ca  lea     rcx, [r8+20h]
0x18000b9ce  call    ?DeleteAt@?$CList@UClient@CMcCoClients@@VCNoLock@@@@QEAAPEAUClient@CMcCoClients@@AEAPEAX@Z; CList<CMcCoClients::Client,CNoLock>::DeleteAt(void * &)
0x18000b9d3  dec     dword ptr [r14+0AB8h]
0x18000b9da  test    rdi, rdi
0x18000b9dd  jz      short loc_18000B990
0x18000b9df  mov     edx, [rdi+4Ch]; unsigned __int64
0x18000b9e2  lea     rcx, [rdi+3Ch]; unsigned __int8 *
0x18000b9e6  mov     r9d, 40h ; '@'; unsigned __int64
0x18000b9ec  lea     r8, [rbp+0E0h+var_14C]; unsigned __int16 *
0x18000b9f0  call    ?HexToString@@YAKPEBE_KPEAG1@Z; HexToString(uchar const *,unsigned __int64,ushort *,unsigned __int64)
0x18000b9f5  mov     ecx, ebx
0x18000b9f7  lea     rdx, [rdi+28h]; struct tagWDS_IP_ADDRESS6 *
0x18000b9fb  test    eax, eax
0x18000b9fd  setnz   cl
0x18000ba00  mov     [rbp+0E0h+var_150], ecx
0x18000ba03  lea     rcx, [rbp+0E0h+var_C0]; this
0x18000ba07  call    ?Initialize@CIPString@@QEAAKPEAUtagWDS_IP_ADDRESS6@@@Z; CIPString::Initialize(tagWDS_IP_ADDRESS6 *)
0x18000ba0c  cmp     [rbp+0E0h+var_C0], ebx
0x18000ba0f  lea     r8, [rbp+0E0h+var_BC]
0x18000ba13  mov     rax, [r14+8]
0x18000ba17  lea     r9, [rbp+0E0h+var_14C]
0x18000ba1b  mov     rsi, [r14+10h]
0x18000ba1f  mov     r11, [rax+0E8h]
0x18000ba26  lea     rax, aFailed; "<<Failed>>"
0x18000ba2d  cmovnz  r8, rax
0x18000ba31  cmp     [rbp+0E0h+var_150], ebx
0x18000ba34  cmovnz  r9, rax
0x18000ba38  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000ba3c  mov     rax, rcx
0x18000ba3f  inc     rax
0x18000ba42  cmp     [r11+rax*2], bx
0x18000ba47  jnz     short loc_18000BA3F
0x18000ba49  lea     r14, ds:2[rax*2]
0x18000ba51  mov     rax, rcx
0x18000ba54  inc     rax
0x18000ba57  cmp     [rsi+rax*2], bx
0x18000ba5b  jnz     short loc_18000BA54
0x18000ba5d  lea     r10, ds:2[rax*2]
0x18000ba65  mov     rax, rcx
0x18000ba68  inc     rax
0x18000ba6b  cmp     [r8+rax*2], bx
0x18000ba70  jnz     short loc_18000BA68
0x18000ba72  lea     rdx, ds:2[rax*2]
0x18000ba7a  inc     rcx
0x18000ba7d  cmp     [r9+rcx*2], bx
0x18000ba82  jnz     short loc_18000BA7A
0x18000ba84  mov     [rsp+1E0h+var_170], r11
0x18000ba89  lea     rax, ds:2[rcx*2]
0x18000ba91  mov     [rsp+1E0h+var_178], r14
0x18000ba96  mov     r14d, 1
0x18000ba9c  mov     [rsp+1E0h+var_180], r14d
0x18000baa1  mov     [rsp+1E0h+var_188], rsi
0x18000baa6  mov     [rsp+1E0h+var_190], r10
0x18000baab  mov     [rsp+1E0h+var_198], r14d
0x18000bab0  mov     [rsp+1E0h+var_1A0], r8
0x18000bab5  lea     r8d, [r14+3]
0x18000bab9  mov     [rsp+1E0h+var_1A8], rdx
0x18000babe  lea     edx, [r14+17h]
0x18000bac2  mov     [rsp+1E0h+var_1B0], r14d
0x18000bac7  lea     ecx, [rdx-16h]
0x18000baca  mov     [rsp+1E0h+var_1B8], r9
0x18000bacf  mov     r9d, r14d
0x18000bad2  mov     [rsp+1E0h+var_1C0], rax
0x18000bad7  call    cs:__imp_?WdsDiagRecordEvent@@YAKW4_WDS_DIAG_MODULE_ID@@W4_WDS_DIAG_EVENT_ID@@KZZ; WdsDiagRecordEvent(_WDS_DIAG_MODULE_ID,_WDS_DIAG_EVENT_ID,ulong,...)
0x18000badd  mov     rcx, rdi; void *
0x18000bae0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000bae5  mov     r9d, r14d
0x18000bae8  mov     dword ptr [rsp+1E0h+var_1C0], r14d
0x18000baed  lea     r8d, [r14+1]
0x18000baf1  mov     edx, r14d; unsigned int
0x18000baf4  lea     rcx, qword_1800336A0; this
0x18000bafb  call    ?Batch@CPerfCounters@@QEAAKKZZ; CPerfCounters::Batch(ulong,...)
0x18000bb00  jmp     loc_18000B995
```
