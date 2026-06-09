# CSQLSatelliteConnection::CloseSNIConnection(void)

- ea: `0x100473630`
- end: `0x1004737d3`
- name: `?CloseSNIConnection@CSQLSatelliteConnection@@QEAAKXZ`
- size: `419`
- prototype: `unsigned int __fastcall(CSQLSatelliteConnection *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x100473620`
- `0x100475aa0`

## callees

- `0x10041d750`
- `0x100426760`
- `0x1004269b0`
- `0x100473630`
- `0x1004781c0`

## import_xrefs

- `sqldk!?ReleaseLock@SOS_RWLock@@QEAAXW4RWLockMode@@@Z` at `0x100473798`
- `sqldk!?ReleaseLock@SOS_RWLock@@QEAAXW4RWLockMode@@@Z` at `0x100473798`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1004736ac`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1004736ac`
- `sqldk!SystemThread_TlsIndex` at `0x1004736ca`
- `sqldk!SystemThread_TlsOffset` at `0x1004736d3`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004736ee`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004736ee`

## string_xrefs

- `0x10047369a`: `"Sql\\Ntdbms\\extensibility\\common\\src\\communisatellite.cpp"`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSQLSatelliteConnection::CloseSNIConnection(
        CSQLSatelliteConnection *this,
        __int64 a2,
        __int64 a3,
        const wchar_t *a4)
{
  __int64 v5; // rcx
  unsigned int v6; // r15d
  __int64 v7; // r13
  __int64 v8; // r14
  __int64 v9; // rbx
  __int64 v10; // rsi
  int v11; // ebp
  unsigned int v12; // ebx
  CSQLSatelliteConnection *v14; // [rsp+90h] [rbp+8h] BYREF

  v5 = *((_QWORD *)this + 8);
  if ( !v5 || *((_BYTE *)this + 948) == 1 )
    return 0;
  v6 = 0;
  v14 = 0;
  SNIGetInfo(v5, 2, (__int64)&v14, a4);
  if ( v14 != this )
    utassert_fail(
      1u,
      "pAssocConn == this",
      "\"Sql\\\\Ntdbms\\\\extensibility\\\\common\\\\src\\\\communisatellite.cpp\"",
      4108,
      0);
  v7 = *((_QWORD *)this + 8);
  LODWORD(v8) = 12;
  v9 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v10 = *(_QWORD *)(v9 + 256);
  if ( !v10 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v10 = *(_QWORD *)(v9 + 256);
  }
  v11 = !(*(_BYTE *)(v10 + 616) & 1);
  *(_DWORD *)(v10 + 616) |= 1u;
  if ( !(unsigned int)SOS_RWLock::GetLock((char *)this + 192, 2, 0xFFFFFFFFLL, (char *)this + 224) )
    v6 = 2;
  if ( !*((_BYTE *)this + 948) )
  {
    v12 = *(_DWORD *)(v7 + 12832);
    v8 = (unsigned int)SNICloseEx(v7, 0);
    *((_BYTE *)this + 948) = 1;
    TracePrintSatellite(L"Close the SNI connection 0x%x, with total ref count %d, for error code %d.\n", v7, v12, v8);
  }
  if ( v6 )
    SOS_RWLock::ReleaseLock((char *)this + 192, v6);
  *(_DWORD *)(v10 + 616) &= ~v11;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x100473630  mov     rax, rsp
0x100473633  push    rdi
0x100473634  push    r12
0x100473636  push    r13
0x100473638  push    r14
0x10047363a  push    r15
0x10047363c  sub     rsp, 60h
0x100473640  mov     qword ptr [rax-58h], 0FFFFFFFFFFFFFFFEh
0x100473648  mov     [rax+10h], rbx
0x10047364c  mov     [rax+18h], rbp
0x100473650  mov     [rax+20h], rsi
0x100473654  mov     rdi, rcx
0x100473657  mov     rcx, [rcx+40h]
0x10047365b  test    rcx, rcx
0x10047365e  jz      loc_1004737B3
0x100473664  cmp     byte ptr [rdi+3B4h], 1
0x10047366b  jz      loc_1004737B3
0x100473671  xor     r15d, r15d
0x100473674  mov     [rax+8], r15
0x100473678  lea     r8, [rax+8]
0x10047367c  lea     edx, [r15+2]
0x100473680  call    SNIGetInfo
0x100473685  cmp     [rsp+88h+arg_0], rdi
0x10047368d  jz      short loc_1004736B2
0x10047368f  mov     [rsp+88h+var_68], r15
0x100473694  mov     r9d, 100Ch
0x10047369a  lea     r8, aSqlNtdbmsExten_13; "\"Sql\\\\Ntdbms\\\\extensibility\\\\com"...
0x1004736a1  lea     rdx, aPassocconnThis; "pAssocConn == this"
0x1004736a8  lea     ecx, [r15+1]
0x1004736ac  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x1004736b2  mov     r13, [rdi+40h]
0x1004736b6  mov     r14d, 0Ch
0x1004736bc  mov     [rsp+88h+var_40], r15d
0x1004736c1  mov     rdx, gs:58h
0x1004736ca  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004736d1  mov     ecx, [rax]
0x1004736d3  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004736da  mov     ebx, [rax]
0x1004736dc  add     rbx, [rdx+rcx*8]
0x1004736e0  mov     rsi, [rbx+100h]
0x1004736e7  test    rsi, rsi
0x1004736ea  jnz     short loc_1004736FB
0x1004736ec  xor     ecx, ecx
0x1004736ee  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004736f4  mov     rsi, [rbx+100h]
0x1004736fb  mov     [rsp+88h+var_38], rsi
0x100473700  mov     eax, [rsi+268h]
0x100473706  mov     ebp, eax
0x100473708  and     ebp, 1
0x10047370b  xor     ebp, 1
0x10047370e  mov     [rsp+88h+var_40], ebp
0x100473712  or      eax, 1
0x100473715  mov     [rsi+268h], eax
0x10047371b  lea     r12, [rdi+0C0h]
0x100473722  mov     [rsp+88h+var_50], r12
0x100473727  mov     [rsp+88h+var_48], r15d
0x10047372c  lea     r9, [rdi+0E0h]
0x100473733  mov     ebx, 2
0x100473738  mov     r8d, 0FFFFFFFFh
0x10047373e  mov     edx, ebx
0x100473740  mov     rcx, r12
0x100473743  call    ?GetLock@SOS_RWLock@@QEAA?AW4SOS_RESULT@@W4RWLockMode@@KPEBVSOS_WaitInfo@@@Z; SOS_RWLock::GetLock(RWLockMode,ulong,SOS_WaitInfo const *)
0x100473748  test    eax, eax
0x10047374a  cmovz   r15d, ebx
0x10047374e  mov     [rsp+88h+var_48], r15d
0x100473753  cmp     byte ptr [rdi+3B4h], 0
0x10047375a  jnz     short loc_10047378D
0x10047375c  mov     ebx, [r13+3220h]
0x100473763  xor     edx, edx
0x100473765  mov     rcx, r13
0x100473768  call    SNICloseEx
0x10047376d  mov     r14d, eax
0x100473770  mov     byte ptr [rdi+3B4h], 1
0x100473777  mov     r9d, eax
0x10047377a  mov     r8d, ebx
0x10047377d  mov     rdx, r13
0x100473780  lea     rcx, aCloseTheSniCon; "Close the SNI connection 0x%x, with tot"...
0x100473787  call    ?TracePrintSatellite@@YAXPEB_WZZ; TracePrintSatellite(wchar_t const *,...)
0x10047378c  nop
0x10047378d  test    r15d, r15d
0x100473790  jz      short loc_1004737A6
0x100473792  mov     edx, r15d
0x100473795  mov     rcx, r12
0x100473798  call    cs:__imp_?ReleaseLock@SOS_RWLock@@QEAAXW4RWLockMode@@@Z; SOS_RWLock::ReleaseLock(RWLockMode)
0x10047379e  mov     [rsp+88h+var_48], 0
0x1004737a6  not     ebp
0x1004737a8  and     [rsi+268h], ebp
0x1004737ae  mov     eax, r14d
0x1004737b1  jmp     short loc_1004737B5
0x1004737b3  xor     eax, eax
0x1004737b5  lea     r11, [rsp+88h+var_28]
0x1004737ba  mov     rbx, [r11+38h]
0x1004737be  mov     rbp, [r11+40h]
0x1004737c2  mov     rsi, [r11+48h]
0x1004737c6  mov     rsp, r11
0x1004737c9  pop     r15
0x1004737cb  pop     r14
0x1004737cd  pop     r13
0x1004737cf  pop     r12
0x1004737d1  pop     rdi
0x1004737d2  retn
```
