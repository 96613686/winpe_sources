# CMcCoClients::DeleteAllSessionClients(ulong)

- ea: `0x18000bdd4`
- end: `0x18000c01c`
- name: `?DeleteAllSessionClients@CMcCoClients@@QEAAXK@Z`
- size: `584`
- prototype: `void __fastcall(CMcCoClients *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x1800197e0`

## callees

- `0x180003c0c`
- `0x18000bdd4`
- `0x18000c230`
- `0x18000c394`
- `0x18001a9a8`
- `0x1800229c0`
- `0x180024228`
- `0x180026670`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000bfe6`
- `KERNEL32!LeaveCriticalSection` at `0x18000bfe6`
- `KERNEL32!EnterCriticalSection` at `0x18000be27`
- `KERNEL32!EnterCriticalSection` at `0x18000be27`
- `WdsDiag!WdsDiagRecordEvent` at `0x18000bfa0`
- `WdsDiag!WdsDiagRecordEvent` at `0x18000bfa0`

## pseudocode

```c
void __fastcall CMcCoClients::DeleteAllSessionClients(CMcCoClients *this, int a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // r15
  int v5; // esi
  int v6; // eax
  __int64 v7; // rcx
  int v8; // eax
  _DWORD *v9; // rbx
  char *v10; // rcx
  const unsigned __int16 *v11; // r8
  unsigned __int16 *v12; // r9
  __int64 v13; // r12
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // [rsp+28h] [rbp-E0h]
  __int64 v21; // [rsp+50h] [rbp-B8h]
  __int128 v22; // [rsp+88h] [rbp-80h] BYREF
  struct _RTL_CRITICAL_SECTION *v23; // [rsp+98h] [rbp-70h]
  BOOL v24; // [rsp+A8h] [rbp-60h]
  unsigned __int16 v25[70]; // [rsp+ACh] [rbp-5Ch] BYREF
  int v26; // [rsp+138h] [rbp+30h] BYREF
  __int16 v27; // [rsp+13Ch] [rbp+34h] BYREF

  v2 = *(struct _RTL_CRITICAL_SECTION **)this;
  v25[0] = 0;
  v27 = 0;
  v23 = v2;
  v5 = 0;
  EnterCriticalSection(v2);
  v6 = 0;
  v7 = *((_QWORD *)this + 4);
  v22 = 0u;
  if ( v7 )
  {
    *((_QWORD *)&v22 + 1) = v7;
  }
  else
  {
    *((_QWORD *)&v22 + 1) = 0;
    CSmHashTable<CMcCoClients::Client,CNoLock,113>::MoveNext((char *)this + 24, &v22);
    v6 = v22;
  }
  if ( !v6 )
  {
    v8 = v22;
    do
    {
      v9 = 0;
      if ( !v8 )
        v9 = (_DWORD *)*((_QWORD *)&v22 + 1);
      v10 = (char *)this + 24;
      if ( *v9 == a2 )
      {
        CSmHashTable<CMcCoClients::Client,CNoLock,113>::EnumRemoveAt(v10, &v22);
        v24 = HexToString((const unsigned __int8 *)v9 + 60, (unsigned int)v9[19], v25, 0x40u) != 0;
        CIPString::Initialize((CIPString *)&v26, (struct tagWDS_IP_ADDRESS6 *)(v9 + 10));
        v11 = (const unsigned __int16 *)&v27;
        v12 = v25;
        v13 = *((_QWORD *)this + 2);
        if ( v26 )
          v11 = L"<<Failed>>";
        if ( v24 )
          v12 = L"<<Failed>>";
        v14 = -1;
        do
          ++v14;
        while ( *(_WORD *)(*(_QWORD *)(*((_QWORD *)this + 1) + 232LL) + 2 * v14) );
        v15 = -1;
        do
          ++v15;
        while ( *(_WORD *)(v13 + 2 * v15) );
        v16 = 2 * v15 + 2;
        v17 = -1;
        do
          ++v17;
        while ( v11[v17] );
        v18 = 2 * v17 + 2;
        v19 = -1;
        do
          ++v19;
        while ( v12[v19] );
        LODWORD(v21) = 1;
        WdsDiagRecordEvent(2, 24, 4, 1, 2 * v19 + 2, v12, 1, v18, v11, v21, v16, v13, 1);
        operator delete(v9);
        ++v5;
      }
      else
      {
        CSmHashTable<CMcCoClients::Client,CNoLock,113>::MoveNext(v10, &v22);
      }
      v8 = v22;
    }
    while ( !(_DWORD)v22 );
    v2 = v23;
  }
  LODWORD(v20) = v5;
  CPerfCounters::Batch((CPerfCounters *)&qword_1800336A0, 1u, 2, 1, v20);
  LeaveCriticalSection(v2);
}

```

## disassembly

```asm
0x18000bdd4  mov     rax, rsp
0x18000bdd7  mov     [rax+10h], rbx
0x18000bddb  mov     [rax+18h], rsi
0x18000bddf  mov     [rax+20h], rdi
0x18000bde3  push    rbp
0x18000bde4  push    r12
0x18000bde6  push    r13
0x18000bde8  push    r14
0x18000bdea  push    r15
0x18000bdec  lea     rbp, [rax-0F8h]
0x18000bdf3  sub     rsp, 1D0h
0x18000bdfa  mov     rax, cs:__security_cookie
0x18000be01  xor     rax, rsp
0x18000be04  mov     [rbp+0F0h+var_30], rax
0x18000be0b  mov     r15, [rcx]
0x18000be0e  xor     ebx, ebx
0x18000be10  mov     r14, rcx
0x18000be13  mov     [rbp+0F0h+var_14C], bx
0x18000be17  mov     rcx, r15; lpCriticalSection
0x18000be1a  mov     [rbp+0F0h+var_BC], bx
0x18000be1e  mov     r13d, edx
0x18000be21  mov     [rbp+0F0h+var_160], r15
0x18000be25  mov     esi, ebx
0x18000be27  call    cs:__imp_EnterCriticalSection
0x18000be2d  xor     eax, eax
0x18000be2f  lea     rdi, [r14+18h]
0x18000be33  mov     rcx, [rdi+8]
0x18000be37  mov     qword ptr [rbp+0F0h+var_170], rax
0x18000be3b  mov     qword ptr [rbp+0F0h+var_170+8], rax
0x18000be3f  test    rcx, rcx
0x18000be42  jnz     short loc_18000BE5A
0x18000be44  lea     rdx, [rbp+0F0h+var_170]
0x18000be48  mov     qword ptr [rbp+0F0h+var_170+8], rbx
0x18000be4c  mov     rcx, rdi
0x18000be4f  call    ?MoveNext@?$CSmHashTable@UClient@CMcCoClients@@VCNoLock@@$0HB@@@AEAAXAEAU_SMHTPOS@@@Z; CSmHashTable<CMcCoClients::Client,CNoLock,113>::MoveNext(_SMHTPOS &)
0x18000be54  mov     rax, qword ptr [rbp+0F0h+var_170]
0x18000be58  jmp     short loc_18000BE5E
0x18000be5a  mov     qword ptr [rbp+0F0h+var_170+8], rcx
0x18000be5e  movaps  xmm0, [rbp+0F0h+var_170]
0x18000be62  mov     r12d, 1
0x18000be68  movdqa  [rbp+0F0h+var_170], xmm0
0x18000be6d  test    eax, eax
0x18000be6f  jnz     loc_18000BFC7
0x18000be75  mov     eax, dword ptr [rbp+0F0h+var_170]
0x18000be78  xor     r15d, r15d
0x18000be7b  mov     rbx, r15
0x18000be7e  test    eax, eax
0x18000be80  jnz     short loc_18000BE86
0x18000be82  mov     rbx, qword ptr [rbp+0F0h+var_170+8]
0x18000be86  lea     rdx, [rbp+0F0h+var_170]
0x18000be8a  mov     rcx, rdi
0x18000be8d  cmp     [rbx], r13d
0x18000be90  jnz     loc_18000BFB3
0x18000be96  call    ?EnumRemoveAt@?$CSmHashTable@UClient@CMcCoClients@@VCNoLock@@$0HB@@@QEAAPEAUClient@CMcCoClients@@AEAU_SMHTPOS@@@Z; CSmHashTable<CMcCoClients::Client,CNoLock,113>::EnumRemoveAt(_SMHTPOS &)
0x18000be9b  mov     edx, [rbx+4Ch]; unsigned __int64
0x18000be9e  lea     rcx, [rbx+3Ch]; unsigned __int8 *
0x18000bea2  mov     r9d, 40h ; '@'; unsigned __int64
0x18000bea8  lea     r8, [rbp+0F0h+var_14C]; unsigned __int16 *
0x18000beac  call    ?HexToString@@YAKPEBE_KPEAG1@Z; HexToString(uchar const *,unsigned __int64,ushort *,unsigned __int64)
0x18000beb1  mov     ecx, r15d
0x18000beb4  lea     rdx, [rbx+28h]; struct tagWDS_IP_ADDRESS6 *
0x18000beb8  test    eax, eax
0x18000beba  setnz   cl
0x18000bebd  mov     [rbp+0F0h+var_150], ecx
0x18000bec0  lea     rcx, [rbp+0F0h+var_C0]; this
0x18000bec4  call    ?Initialize@CIPString@@QEAAKPEAUtagWDS_IP_ADDRESS6@@@Z; CIPString::Initialize(tagWDS_IP_ADDRESS6 *)
0x18000bec9  cmp     [rbp+0F0h+var_C0], r15d
0x18000becd  lea     r8, [rbp+0F0h+var_BC]
0x18000bed1  mov     rax, [r14+8]
0x18000bed5  lea     r9, [rbp+0F0h+var_14C]
0x18000bed9  mov     r12, [r14+10h]
0x18000bedd  mov     r10, [rax+0E8h]
0x18000bee4  lea     rax, aFailed; "<<Failed>>"
0x18000beeb  cmovnz  r8, rax
0x18000beef  cmp     [rbp+0F0h+var_150], r15d
0x18000bef3  cmovnz  r9, rax
0x18000bef7  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000befb  mov     rax, rcx
0x18000befe  inc     rax
0x18000bf01  cmp     [r10+rax*2], r15w
0x18000bf06  jnz     short loc_18000BEFE
0x18000bf08  lea     r11, ds:2[rax*2]
0x18000bf10  mov     rax, rcx
0x18000bf13  inc     rax
0x18000bf16  cmp     [r12+rax*2], r15w
0x18000bf1b  jnz     short loc_18000BF13
0x18000bf1d  lea     rdx, ds:2[rax*2]
0x18000bf25  mov     rax, rcx
0x18000bf28  inc     rax
0x18000bf2b  cmp     [r8+rax*2], r15w
0x18000bf30  jnz     short loc_18000BF28
0x18000bf32  lea     rcx, ds:2[rax*2]
0x18000bf3a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000bf3e  inc     rax
0x18000bf41  cmp     [r9+rax*2], r15w
0x18000bf46  jnz     short loc_18000BF3E
0x18000bf48  mov     [rsp+1F0h+var_180], r10
0x18000bf4d  lea     rax, ds:2[rax*2]
0x18000bf55  mov     [rsp+1F0h+var_188], r11
0x18000bf5a  mov     dword ptr [rsp+1F0h+var_190], 1
0x18000bf62  mov     qword ptr [rsp+1F0h+var_198], r12
0x18000bf67  mov     r12d, 1
0x18000bf6d  mov     [rsp+1F0h+var_1A0], rdx
0x18000bf72  mov     dword ptr [rsp+1F0h+var_1A8], r12d
0x18000bf77  mov     qword ptr [rsp+1F0h+var_1B0], r8
0x18000bf7c  mov     [rsp+1F0h+var_1B8], rcx
0x18000bf81  lea     edx, [r12+17h]
0x18000bf86  mov     dword ptr [rsp+1F0h+var_1C0], r12d
0x18000bf8b  lea     ecx, [rdx-16h]
0x18000bf8e  mov     qword ptr [rsp+1F0h+var_1C8], r9
0x18000bf93  lea     r8d, [r12+3]
0x18000bf98  mov     r9d, r12d
0x18000bf9b  mov     [rsp+1F0h+var_1D0], rax
0x18000bfa0  call    cs:__imp_?WdsDiagRecordEvent@@YAKW4_WDS_DIAG_MODULE_ID@@W4_WDS_DIAG_EVENT_ID@@KZZ; WdsDiagRecordEvent(_WDS_DIAG_MODULE_ID,_WDS_DIAG_EVENT_ID,ulong,...)
0x18000bfa6  mov     rcx, rbx; void *
0x18000bfa9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000bfae  add     esi, r12d
0x18000bfb1  jmp     short loc_18000BFB8
0x18000bfb3  call    ?MoveNext@?$CSmHashTable@UClient@CMcCoClients@@VCNoLock@@$0HB@@@AEAAXAEAU_SMHTPOS@@@Z; CSmHashTable<CMcCoClients::Client,CNoLock,113>::MoveNext(_SMHTPOS &)
0x18000bfb8  mov     eax, dword ptr [rbp+0F0h+var_170]
0x18000bfbb  test    eax, eax
0x18000bfbd  jz      loc_18000BE7B
0x18000bfc3  mov     r15, [rbp+0F0h+var_160]
0x18000bfc7  mov     r9d, r12d
0x18000bfca  mov     dword ptr [rsp+1F0h+var_1D0], esi
0x18000bfce  mov     r8d, 2
0x18000bfd4  lea     rcx, qword_1800336A0; this
0x18000bfdb  mov     edx, r12d; unsigned int
0x18000bfde  call    ?Batch@CPerfCounters@@QEAAKKZZ; CPerfCounters::Batch(ulong,...)
0x18000bfe3  mov     rcx, r15; lpCriticalSection
0x18000bfe6  call    cs:__imp_LeaveCriticalSection
0x18000bfec  mov     rcx, [rbp+0F0h+var_30]
0x18000bff3  xor     rcx, rsp; StackCookie
0x18000bff6  call    __security_check_cookie
0x18000bffb  lea     r11, [rsp+1F0h+var_20]
0x18000c003  mov     rbx, [r11+38h]
0x18000c007  mov     rsi, [r11+40h]
0x18000c00b  mov     rdi, [r11+48h]
0x18000c00f  mov     rsp, r11
0x18000c012  pop     r15
0x18000c014  pop     r14
0x18000c016  pop     r13
0x18000c018  pop     r12
0x18000c01a  pop     rbp
0x18000c01b  retn
```
