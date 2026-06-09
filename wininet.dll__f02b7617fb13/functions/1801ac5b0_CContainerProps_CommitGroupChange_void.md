# CContainerProps::CommitGroupChange(void)

- ea: `0x1801ac5b0`
- end: `0x1801ac79d`
- name: `?CommitGroupChange@CContainerProps@@AEAAJXZ`
- size: `493`
- prototype: `__int64 __fastcall(CContainerProps *__hidden this)`
- caller_count: `4`
- callee_count: `9`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1801ac41c`
- `0x1801ac7a4`
- `0x1801ac950`
- `0x1801acde8`

## callees

- `0x180021360`
- `0x18007ec9c`
- `0x180086300`
- `0x1800eed94`
- `0x1800eee94`
- `0x18012ad34`
- `0x1801ac5b0`
- `0x1801e1790`
- `0x1801e3c24`

## import_xrefs

- `ESENT!JetCommitTransaction` at `0x1801ac77c`
- `ESENT!JetCommitTransaction` at `0x1801ac77c`
- `ESENT!JetUpdate` at `0x1801ac75f`
- `ESENT!JetUpdate` at `0x1801ac75f`
- `ESENT!JetPrepareUpdate` at `0x1801ac6eb`
- `ESENT!JetPrepareUpdate` at `0x1801ac741`
- `ESENT!JetPrepareUpdate` at `0x1801ac6eb`
- `ESENT!JetPrepareUpdate` at `0x1801ac741`
- `ESENT!JetRollback` at `0x1801ac6bf`
- `ESENT!JetRollback` at `0x1801ac6bf`
- `ESENT!JetBeginTransaction` at `0x1801ac67d`
- `ESENT!JetBeginTransaction` at `0x1801ac67d`

## pseudocode

```c
__int64 __fastcall CContainerProps::CommitGroupChange(CContainerProps *this)
{
  int v2; // eax
  unsigned int v3; // r9d
  int v4; // ebx
  unsigned int v5; // edi
  JET_SESID *v7; // rsi
  JET_ERR v8; // eax
  int v9; // eax
  JET_ERR v10; // eax
  JET_ERR v11; // eax
  JET_ERR v12; // eax
  struct CJetContext *v13; // [rsp+58h] [rbp+10h] BYREF

  v13 = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_q(1036, 26, WPP_9fc02c8e9bc0336dfd7c0d8da46e805e_Traceguids, this);
  v2 = CCacheStore::AcquireContainerContext(*((CCacheStore **)this + 3), &v13);
  v4 = v2;
  if ( v2 < 0
    || (v7 = (JET_SESID *)v13, v2 = CJetContext::SetCurrentIndex(v13, 0, L"ContainerIdIndex", v3), v4 = v2, v2 < 0)
    || (v8 = JetBeginTransaction(v7[2]), v2 = HRESULTFromJET_ERR(v8, 1), v4 = v2, v2 < 0) )
  {
    v5 = v2;
    goto LABEL_5;
  }
  v9 = SeekToContainer((struct CJetContext *)v7, *((_QWORD *)this + 1));
  v4 = v9;
  if ( v9 < 0 )
    goto LABEL_11;
  if ( v9 )
  {
    v4 = -2147418113;
    v5 = -2147418113;
    goto LABEL_12;
  }
  v10 = JetPrepareUpdate(v7[2], v7[4], 2u);
  v9 = HRESULTFromJET_ERR(v10, 1);
  v4 = v9;
  if ( v9 < 0 )
  {
LABEL_11:
    v5 = v9;
LABEL_12:
    JetRollback(v7[2], 0);
    goto LABEL_5;
  }
  v4 = CJetContext::SetBinaryColumn(
         (CJetContext *)v7,
         0xAu,
         *((const unsigned __int8 **)this + 21),
         288 * *((_DWORD *)this + 44));
  if ( v4 < 0 || (v11 = JetUpdate(v7[2], v7[4], 0, 0, 0), v4 = HRESULTFromJET_ERR(v11, 1), v4 < 0) )
  {
    v5 = v4;
    JetPrepareUpdate(v7[2], v7[4], 3u);
    goto LABEL_12;
  }
  v12 = JetCommitTransaction(v7[2], 1u);
  v4 = HRESULTFromJET_ERR(v12, 1);
  v5 = v4;
  if ( v4 < 0 )
    goto LABEL_12;
LABEL_5:
  CCacheStore::ReleaseContainerContext(*((CCacheStore **)this + 3), &v13);
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 27, WPP_9fc02c8e9bc0336dfd7c0d8da46e805e_Traceguids, (unsigned int)v4);
  return v5;
}

```

## disassembly

```asm
0x1801ac5b0  mov     [rsp+arg_10], rbx
0x1801ac5b5  mov     [rsp+arg_18], rbp
0x1801ac5ba  push    rsi
0x1801ac5bb  push    rdi
0x1801ac5bc  push    r14
0x1801ac5be  sub     rsp, 30h
0x1801ac5c2  xor     edi, edi
0x1801ac5c4  mov     rbp, rcx
0x1801ac5c7  mov     [rsp+48h+arg_4], edi
0x1801ac5cb  mov     [rsp+48h+arg_8], rdi
0x1801ac5d0  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1801ac5d7  jz      short loc_1801AC5F0
0x1801ac5d9  lea     edx, [rdi+1Ah]
0x1801ac5dc  mov     ecx, 40Ch
0x1801ac5e1  mov     r9, rbp
0x1801ac5e4  lea     r8, WPP_9fc02c8e9bc0336dfd7c0d8da46e805e_Traceguids
0x1801ac5eb  call    WPP_SF_q
0x1801ac5f0  mov     rcx, [rbp+18h]; this
0x1801ac5f4  lea     rdx, [rsp+48h+arg_8]; struct CJetContext **
0x1801ac5f9  call    ?AcquireContainerContext@CCacheStore@@QEAAJPEAPEAVCJetContext@@@Z; CCacheStore::AcquireContainerContext(CJetContext * *)
0x1801ac5fe  mov     ebx, eax
0x1801ac600  test    eax, eax
0x1801ac602  jns     short loc_1801AC653
0x1801ac604  mov     [rsp+48h+arg_4], 258h
0x1801ac60c  mov     edi, eax
0x1801ac60e  mov     rcx, [rbp+18h]; this
0x1801ac612  lea     rdx, [rsp+48h+arg_8]; struct CJetContext **
0x1801ac617  call    ?ReleaseContainerContext@CCacheStore@@QEAAXPEAPEAVCJetContext@@@Z; CCacheStore::ReleaseContainerContext(CJetContext * *)
0x1801ac61c  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1801ac623  jz      short loc_1801AC63E
0x1801ac625  mov     edx, 1Bh
0x1801ac62a  lea     r8, WPP_9fc02c8e9bc0336dfd7c0d8da46e805e_Traceguids
0x1801ac631  mov     ecx, 40Ch
0x1801ac636  mov     r9d, ebx
0x1801ac639  call    WPP_SF_d
0x1801ac63e  mov     rbx, [rsp+48h+arg_10]
0x1801ac643  mov     eax, edi
0x1801ac645  mov     rbp, [rsp+48h+arg_18]
0x1801ac64a  add     rsp, 30h
0x1801ac64e  pop     r14
0x1801ac650  pop     rdi
0x1801ac651  pop     rsi
0x1801ac652  retn
0x1801ac653  mov     rsi, [rsp+48h+arg_8]
0x1801ac658  lea     r8, aContaineridind; "ContainerIdIndex"
0x1801ac65f  mov     rcx, rsi; this
0x1801ac662  xor     edx, edx; unsigned int
0x1801ac664  call    ?SetCurrentIndex@CJetContext@@QEAAJKPEBGK@Z; CJetContext::SetCurrentIndex(ulong,ushort const *,ulong)
0x1801ac669  mov     ebx, eax
0x1801ac66b  test    eax, eax
0x1801ac66d  jns     short loc_1801AC679
0x1801ac66f  mov     [rsp+48h+arg_4], 25Ah
0x1801ac677  jmp     short loc_1801AC60C
0x1801ac679  mov     rcx, [rsi+10h]; sesid
0x1801ac67d  call    cs:__imp_JetBeginTransaction
0x1801ac683  mov     r14d, 1
0x1801ac689  mov     ecx, eax; int
0x1801ac68b  mov     edx, r14d; int
0x1801ac68e  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801ac693  mov     ebx, eax
0x1801ac695  test    eax, eax
0x1801ac697  js      loc_1801AC60C
0x1801ac69d  mov     rdx, [rbp+8]; unsigned __int64
0x1801ac6a1  mov     rcx, rsi; struct CJetContext *
0x1801ac6a4  call    ?SeekToContainer@@YAJPEAVCJetContext@@_K@Z; SeekToContainer(CJetContext *,unsigned __int64)
0x1801ac6a9  mov     ebx, eax
0x1801ac6ab  test    eax, eax
0x1801ac6ad  jns     short loc_1801AC6CA
0x1801ac6af  mov     [rsp+48h+arg_4], 264h
0x1801ac6b7  mov     edi, eax
0x1801ac6b9  mov     rcx, [rsi+10h]; sesid
0x1801ac6bd  xor     edx, edx; grbit
0x1801ac6bf  call    cs:__imp_JetRollback
0x1801ac6c5  jmp     loc_1801AC60E
0x1801ac6ca  jz      short loc_1801AC6DD
0x1801ac6cc  mov     ebx, 8000FFFFh
0x1801ac6d1  mov     [rsp+48h+arg_4], 266h
0x1801ac6d9  mov     edi, ebx
0x1801ac6db  jmp     short loc_1801AC6B9
0x1801ac6dd  mov     rdx, [rsi+20h]; tableid
0x1801ac6e1  mov     r8d, 2; prep
0x1801ac6e7  mov     rcx, [rsi+10h]; sesid
0x1801ac6eb  call    cs:__imp_JetPrepareUpdate
0x1801ac6f1  mov     ecx, eax; int
0x1801ac6f3  mov     edx, r14d; int
0x1801ac6f6  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801ac6fb  mov     ebx, eax
0x1801ac6fd  test    eax, eax
0x1801ac6ff  js      short loc_1801AC6B7
0x1801ac701  mov     eax, [rbp+0B0h]
0x1801ac707  mov     edx, 0Ah; unsigned int
0x1801ac70c  mov     r8, [rbp+0A8h]; unsigned __int8 *
0x1801ac713  mov     rcx, rsi; this
0x1801ac716  lea     r9d, [rax+rax*8]
0x1801ac71a  shl     r9d, 5; unsigned int
0x1801ac71e  call    ?SetBinaryColumn@CJetContext@@QEAAJKPEBEK@Z; CJetContext::SetBinaryColumn(ulong,uchar const *,ulong)
0x1801ac723  mov     ebx, eax
0x1801ac725  test    eax, eax
0x1801ac727  jns     short loc_1801AC74C
0x1801ac729  mov     [rsp+48h+arg_4], 26Bh
0x1801ac731  mov     rdx, [rsi+20h]; tableid
0x1801ac735  mov     r8d, 3; prep
0x1801ac73b  mov     rcx, [rsi+10h]; sesid
0x1801ac73f  mov     edi, ebx
0x1801ac741  call    cs:__imp_JetPrepareUpdate
0x1801ac747  jmp     loc_1801AC6B9
0x1801ac74c  mov     rdx, [rsi+20h]; tableid
0x1801ac750  xor     r9d, r9d; cbBookmark
0x1801ac753  mov     rcx, [rsi+10h]; sesid
0x1801ac757  xor     r8d, r8d; pvBookmark
0x1801ac75a  mov     [rsp+48h+pcbActual], rdi; pcbActual
0x1801ac75f  call    cs:__imp_JetUpdate
0x1801ac765  mov     ecx, eax; int
0x1801ac767  mov     edx, r14d; int
0x1801ac76a  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801ac76f  mov     ebx, eax
0x1801ac771  test    eax, eax
0x1801ac773  js      short loc_1801AC731
0x1801ac775  mov     rcx, [rsi+10h]; sesid
0x1801ac779  mov     edx, r14d; grbit
0x1801ac77c  call    cs:__imp_JetCommitTransaction
0x1801ac782  mov     ecx, eax; int
0x1801ac784  mov     edx, r14d; int
0x1801ac787  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801ac78c  mov     ebx, eax
0x1801ac78e  mov     edi, eax
0x1801ac790  test    eax, eax
0x1801ac792  jns     loc_1801AC60E
0x1801ac798  jmp     loc_1801AC6B9
```
