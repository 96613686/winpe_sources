# CContainerProps::SetEntryMaximumAge(ulong)

- ea: `0x1801aa5cc`
- end: `0x1801aa81c`
- name: `?SetEntryMaximumAge@CContainerProps@@QEAAJK@Z`
- size: `592`
- prototype: `__int64 __fastcall(CContainerProps *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1801a7800`

## callees

- `0x180021360`
- `0x18007ec9c`
- `0x180086300`
- `0x180097e10`
- `0x1800e28e0`
- `0x1800eed94`
- `0x1800fa844`
- `0x18012ad34`
- `0x18014a7a0`
- `0x1801aa5cc`
- `0x1801e1790`
- `0x1801e4988`

## import_xrefs

- `ESENT!JetCommitTransaction` at `0x1801aa7ec`
- `ESENT!JetCommitTransaction` at `0x1801aa7ec`
- `ESENT!JetUpdate` at `0x1801aa7d1`
- `ESENT!JetUpdate` at `0x1801aa7d1`
- `ESENT!JetPrepareUpdate` at `0x1801aa767`
- `ESENT!JetPrepareUpdate` at `0x1801aa7af`
- `ESENT!JetPrepareUpdate` at `0x1801aa767`
- `ESENT!JetPrepareUpdate` at `0x1801aa7af`
- `ESENT!JetRollback` at `0x1801aa73c`
- `ESENT!JetRollback` at `0x1801aa73c`
- `ESENT!JetBeginTransaction` at `0x1801aa6fd`
- `ESENT!JetBeginTransaction` at `0x1801aa6fd`

## pseudocode

```c
__int64 __fastcall CContainerProps::SetEntryMaximumAge(CContainerProps *this, int a2)
{
  CCacheStore **v3; // rsi
  int v4; // ebx
  unsigned int v5; // edi
  int v6; // eax
  unsigned int v7; // r9d
  JET_SESID *v9; // r14
  JET_ERR v10; // eax
  int v11; // eax
  JET_ERR v12; // eax
  JET_ERR v13; // eax
  JET_ERR v14; // eax
  CJetContext *v15; // [rsp+38h] [rbp-28h] BYREF
  char *v16; // [rsp+40h] [rbp-20h] BYREF
  __int64 v17; // [rsp+48h] [rbp-18h]
  int v18; // [rsp+50h] [rbp-10h] BYREF

  v18 = a2;
  v16 = (char *)this + 32;
  v17 = 0;
  v15 = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_qD(1036, 25, WPP_4b302e6b786c3b7f389fd4681ef43772_Traceguids, this, a2);
  AutoCritSec::Lock((AutoCritSec *)&v16);
  v3 = (CCacheStore **)((char *)this + 24);
  if ( v18 == *((_DWORD *)this + 24) )
  {
    v4 = 0;
    v5 = 0;
    goto LABEL_7;
  }
  v6 = CCacheStore::AcquireContainerContext(*v3, &v15);
  v4 = v6;
  if ( v6 < 0
    || (v9 = (JET_SESID *)v15, v6 = CJetContext::SetCurrentIndex(v15, 0, L"ContainerIdIndex", v7), v4 = v6, v6 < 0)
    || (v10 = JetBeginTransaction(v9[2]), v6 = HRESULTFromJET_ERR(v10, 1), v4 = v6, v6 < 0) )
  {
    v5 = v6;
    goto LABEL_7;
  }
  v11 = SeekToContainer((struct CJetContext *)v9, *((_QWORD *)this + 1));
  v4 = v11;
  if ( v11 < 0 )
    goto LABEL_15;
  if ( v11 )
  {
    v4 = -2147418113;
    goto LABEL_19;
  }
  v12 = JetPrepareUpdate(v9[2], v9[4], 2u);
  v11 = HRESULTFromJET_ERR(v12, 1);
  v4 = v11;
  if ( v11 < 0 )
  {
LABEL_15:
    v5 = v11;
LABEL_16:
    JetRollback(v9[2], 0);
    goto LABEL_7;
  }
  v4 = CJetContext::SetBasicColumn((CJetContext *)v9, 0xCu, &v18, 4u);
  if ( v4 < 0 || (v13 = JetUpdate(v9[2], v9[4], 0, 0, 0), v4 = HRESULTFromJET_ERR(v13, 1), v4 < 0) )
  {
    v5 = v4;
    JetPrepareUpdate(v9[2], v9[4], 3u);
    goto LABEL_16;
  }
  v14 = JetCommitTransaction(v9[2], 1u);
  v4 = HRESULTFromJET_ERR(v14, 1);
  if ( v4 < 0 )
  {
LABEL_19:
    v5 = v4;
    goto LABEL_16;
  }
  *((_DWORD *)this + 24) = v18;
  AutoCritSec::Unlock((AutoCritSec *)&v16);
  v5 = v4;
LABEL_7:
  CCacheStore::ReleaseContainerContext(*v3, &v15);
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 26, WPP_4b302e6b786c3b7f389fd4681ef43772_Traceguids, (unsigned int)v4);
  if ( (_DWORD)v17 )
    AutoCritSec::Unlock((AutoCritSec *)&v16);
  return v5;
}

```

## disassembly

```asm
0x1801aa5cc  mov     [rsp-28h+arg_10], rbx
0x1801aa5d1  push    rbp
0x1801aa5d2  push    rsi
0x1801aa5d3  push    rdi
0x1801aa5d4  push    r14
0x1801aa5d6  push    r15
0x1801aa5d8  mov     rbp, rsp
0x1801aa5db  sub     rsp, 60h
0x1801aa5df  mov     rax, cs:__security_cookie
0x1801aa5e6  xor     rax, rsp
0x1801aa5e9  mov     [rbp+var_8], rax
0x1801aa5ed  lea     rax, [rcx+20h]
0x1801aa5f1  mov     [rbp+var_10], edx
0x1801aa5f4  mov     [rbp+var_20], rax
0x1801aa5f8  mov     r8d, edx
0x1801aa5fb  mov     r15, rcx
0x1801aa5fe  mov     [rbp+var_2C], 0
0x1801aa605  mov     [rbp+var_18], 0
0x1801aa60d  mov     [rbp+var_28], 0
0x1801aa615  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1801aa61c  jz      short loc_1801AA63C
0x1801aa61e  mov     dword ptr [rsp+60h+pcbActual], r8d
0x1801aa623  mov     edx, 19h
0x1801aa628  lea     r8, WPP_4b302e6b786c3b7f389fd4681ef43772_Traceguids
0x1801aa62f  mov     ecx, 40Ch
0x1801aa634  mov     r9, r15
0x1801aa637  call    WPP_SF_qD
0x1801aa63c  lea     rcx, [rbp+var_20]; this
0x1801aa640  call    ?Lock@AutoCritSec@@QEAAXXZ; AutoCritSec::Lock(void)
0x1801aa645  mov     eax, [r15+60h]
0x1801aa649  lea     rsi, [r15+18h]
0x1801aa64d  cmp     [rbp+var_10], eax
0x1801aa650  jnz     short loc_1801AA658
0x1801aa652  xor     ebx, ebx
0x1801aa654  xor     edi, edi
0x1801aa656  jmp     short loc_1801AA673
0x1801aa658  mov     rcx, [rsi]; this
0x1801aa65b  lea     rdx, [rbp+var_28]; struct CJetContext **
0x1801aa65f  call    ?AcquireContainerContext@CCacheStore@@QEAAJPEAPEAVCJetContext@@@Z; CCacheStore::AcquireContainerContext(CJetContext * *)
0x1801aa664  mov     ebx, eax
0x1801aa666  test    eax, eax
0x1801aa668  jns     short loc_1801AA6D2
0x1801aa66a  mov     [rbp+var_2C], 2D8h
0x1801aa671  mov     edi, eax
0x1801aa673  mov     rcx, [rsi]; this
0x1801aa676  lea     rdx, [rbp+var_28]; struct CJetContext **
0x1801aa67a  call    ?ReleaseContainerContext@CCacheStore@@QEAAXPEAPEAVCJetContext@@@Z; CCacheStore::ReleaseContainerContext(CJetContext * *)
0x1801aa67f  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1801aa686  jz      short loc_1801AA6A1
0x1801aa688  mov     edx, 1Ah
0x1801aa68d  lea     r8, WPP_4b302e6b786c3b7f389fd4681ef43772_Traceguids
0x1801aa694  mov     ecx, 40Ch
0x1801aa699  mov     r9d, ebx
0x1801aa69c  call    WPP_SF_d
0x1801aa6a1  cmp     dword ptr [rbp+var_18], 0
0x1801aa6a5  jz      short loc_1801AA6B0
0x1801aa6a7  lea     rcx, [rbp+var_20]; this
0x1801aa6ab  call    ?Unlock@AutoCritSec@@QEAAXXZ; AutoCritSec::Unlock(void)
0x1801aa6b0  mov     eax, edi
0x1801aa6b2  mov     rcx, [rbp+var_8]
0x1801aa6b6  xor     rcx, rsp; StackCookie
0x1801aa6b9  call    __security_check_cookie
0x1801aa6be  mov     rbx, [rsp+60h+arg_10]
0x1801aa6c6  add     rsp, 60h
0x1801aa6ca  pop     r15
0x1801aa6cc  pop     r14
0x1801aa6ce  pop     rdi
0x1801aa6cf  pop     rsi
0x1801aa6d0  pop     rbp
0x1801aa6d1  retn
0x1801aa6d2  mov     r14, [rbp+var_28]
0x1801aa6d6  lea     r8, aContaineridind; "ContainerIdIndex"
0x1801aa6dd  mov     rcx, r14; this
0x1801aa6e0  xor     edx, edx; unsigned int
0x1801aa6e2  call    ?SetCurrentIndex@CJetContext@@QEAAJKPEBGK@Z; CJetContext::SetCurrentIndex(ulong,ushort const *,ulong)
0x1801aa6e7  mov     ebx, eax
0x1801aa6e9  test    eax, eax
0x1801aa6eb  jns     short loc_1801AA6F9
0x1801aa6ed  mov     [rbp+var_2C], 2DCh
0x1801aa6f4  jmp     loc_1801AA671
0x1801aa6f9  mov     rcx, [r14+10h]; sesid
0x1801aa6fd  call    cs:__imp_JetBeginTransaction
0x1801aa703  mov     edi, 1
0x1801aa708  mov     ecx, eax; int
0x1801aa70a  mov     edx, edi; int
0x1801aa70c  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801aa711  mov     ebx, eax
0x1801aa713  test    eax, eax
0x1801aa715  js      loc_1801AA671
0x1801aa71b  mov     rdx, [r15+8]; unsigned __int64
0x1801aa71f  mov     rcx, r14; struct CJetContext *
0x1801aa722  call    ?SeekToContainer@@YAJPEAVCJetContext@@_K@Z; SeekToContainer(CJetContext *,unsigned __int64)
0x1801aa727  mov     ebx, eax
0x1801aa729  test    eax, eax
0x1801aa72b  jns     short loc_1801AA747
0x1801aa72d  mov     [rbp+var_2C], 2E6h
0x1801aa734  mov     edi, eax
0x1801aa736  mov     rcx, [r14+10h]; sesid
0x1801aa73a  xor     edx, edx; grbit
0x1801aa73c  call    cs:__imp_JetRollback
0x1801aa742  jmp     loc_1801AA673
0x1801aa747  jz      short loc_1801AA759
0x1801aa749  mov     ebx, 8000FFFFh
0x1801aa74e  mov     [rbp+var_2C], 2E8h
0x1801aa755  mov     edi, ebx
0x1801aa757  jmp     short loc_1801AA736
0x1801aa759  mov     rdx, [r14+20h]; tableid
0x1801aa75d  mov     r8d, 2; prep
0x1801aa763  mov     rcx, [r14+10h]; sesid
0x1801aa767  call    cs:__imp_JetPrepareUpdate
0x1801aa76d  mov     ecx, eax; int
0x1801aa76f  mov     edx, edi; int
0x1801aa771  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801aa776  mov     ebx, eax
0x1801aa778  test    eax, eax
0x1801aa77a  js      short loc_1801AA734
0x1801aa77c  mov     r9d, 4; unsigned int
0x1801aa782  lea     r8, [rbp+var_10]; void *
0x1801aa786  mov     rcx, r14; this
0x1801aa789  lea     edx, [r9+8]; unsigned int
0x1801aa78d  call    ?SetBasicColumn@CJetContext@@QEAAJKPEAXK@Z; CJetContext::SetBasicColumn(ulong,void *,ulong)
0x1801aa792  mov     ebx, eax
0x1801aa794  test    eax, eax
0x1801aa796  jns     short loc_1801AA7BA
0x1801aa798  mov     [rbp+var_2C], 2F1h
0x1801aa79f  mov     rdx, [r14+20h]; tableid
0x1801aa7a3  mov     r8d, 3; prep
0x1801aa7a9  mov     rcx, [r14+10h]; sesid
0x1801aa7ad  mov     edi, ebx
0x1801aa7af  call    cs:__imp_JetPrepareUpdate
0x1801aa7b5  jmp     loc_1801AA736
0x1801aa7ba  mov     rdx, [r14+20h]; tableid
0x1801aa7be  xor     r9d, r9d; cbBookmark
0x1801aa7c1  mov     rcx, [r14+10h]; sesid
0x1801aa7c5  xor     r8d, r8d; pvBookmark
0x1801aa7c8  mov     [rsp+60h+pcbActual], 0; pcbActual
0x1801aa7d1  call    cs:__imp_JetUpdate
0x1801aa7d7  mov     ecx, eax; int
0x1801aa7d9  mov     edx, edi; int
0x1801aa7db  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801aa7e0  mov     ebx, eax
0x1801aa7e2  test    eax, eax
0x1801aa7e4  js      short loc_1801AA79F
0x1801aa7e6  mov     rcx, [r14+10h]; sesid
0x1801aa7ea  mov     edx, edi; grbit
0x1801aa7ec  call    cs:__imp_JetCommitTransaction
0x1801aa7f2  mov     ecx, eax; int
0x1801aa7f4  mov     edx, edi; int
0x1801aa7f6  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801aa7fb  mov     ebx, eax
0x1801aa7fd  test    eax, eax
0x1801aa7ff  js      loc_1801AA755
0x1801aa805  mov     eax, [rbp+var_10]
0x1801aa808  lea     rcx, [rbp+var_20]; this
0x1801aa80c  mov     [r15+60h], eax
0x1801aa810  call    ?Unlock@AutoCritSec@@QEAAXXZ; AutoCritSec::Unlock(void)
0x1801aa815  mov     edi, ebx
0x1801aa817  jmp     loc_1801AA673
```
