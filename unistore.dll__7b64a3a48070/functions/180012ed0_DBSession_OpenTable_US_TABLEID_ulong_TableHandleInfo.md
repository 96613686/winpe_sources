# DBSession::_OpenTable(US_TABLEID,ulong,TableHandleInfo * *)

- ea: `0x180012ed0`
- end: `0x1800131c0`
- name: `?_OpenTable@DBSession@@IEAAJW4US_TABLEID@@KPEAPEAUTableHandleInfo@@@Z`
- size: `752`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e8b0`

## callees

- `0x1800068f0`
- `0x18000f530`
- `0x180011ed0`
- `0x180012ed0`
- `0x18001323c`
- `0x1800132ac`
- `0x180013484`
- `0x180013504`
- `0x1800135f4`
- `0x1800737b4`
- `0x180073b28`
- `0x180078a4c`
- `0x180079030`
- `0x18007d9c8`
- `0x1800ac89c`
- `0x1800c50f0`

## import_xrefs

- `ESENT!JetSetCurrentIndex2A` at `0x180012fcd`
- `ESENT!JetSetCurrentIndex2A` at `0x180012fcd`
- `ESENT!JetOpenTableW` at `0x180012f5f`
- `ESENT!JetOpenTableW` at `0x180012f5f`

## string_xrefs

- `0x18001305f`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbsession.cpp`
- `0x1800130bb`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbsession.cpp`
- `0x180013115`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbsession.cpp`
- `0x180013168`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbsession.cpp`
- `0x1800131a9`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbsession.cpp`

## pseudocode

```c
__int64 __fastcall DBSession::_OpenTable(__int64 a1, int a2, int a3, TableHandleInfo **a4)
{
  __int64 v5; // r15
  unsigned int HresultFromJetError; // ebx
  unsigned int TableClassGrBit; // eax
  JET_ERR v10; // ebx
  __int64 v11; // rax
  unsigned __int64 *v12; // r14
  __int64 v13; // rsi
  int v14; // eax
  JET_ERR v15; // ebx
  TableHandleInfo *v16; // rax
  TableHandleInfo *v17; // rax
  __int64 v18; // rdx
  TableHandleInfo *v19; // rbx
  JET_TABLEID v20; // rcx
  __int64 v21; // rsi
  _QWORD *v22; // rax
  __int64 v23; // rdi
  unsigned int v24; // edx
  __int64 v26; // r9
  __int64 v27; // rdx
  __int64 v28; // rcx
  _QWORD *v29; // rcx
  unsigned int v30; // ecx
  int v31; // eax
  JET_TABLEID tableid; // [rsp+40h] [rbp-39h] BYREF
  _QWORD v33[2]; // [rsp+48h] [rbp-31h] BYREF
  char v34; // [rsp+58h] [rbp-21h]
  _BYTE v35[16]; // [rsp+60h] [rbp-19h] BYREF
  char szIndexName[16]; // [rsp+70h] [rbp-9h] BYREF

  v5 = a2;
  HresultFromJetError = DBSession::_EnsureDBOpened((DBSession *)a1);
  if ( (HresultFromJetError & 0x80000000) != 0 )
  {
    v26 = 1340;
    v27 = 1;
    v28 = HresultFromJetError;
    goto LABEL_14;
  }
  tableid = -1;
  TableClassGrBit = GetTableClassGrBit(v5);
  v10 = JetOpenTableW(
          *(_QWORD *)(a1 + 216),
          *(_DWORD *)(a1 + 224),
          (&g_rgTableInfo)[12 * v5],
          0,
          0,
          TableClassGrBit | 0x8048,
          &tableid);
  CheckCorruption(v10);
  if ( v10 < 0 )
  {
    HresultFromJetError = MakeHresultFromJetError(v10);
    v26 = 1352;
    v27 = 0;
    v28 = HresultFromJetError;
LABEL_14:
    Log_UnistoreHREvent_0(
      v28,
      v27,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbsession.cpp",
      v26);
    return HresultFromJetError;
  }
  v11 = lambda_dccbdc39c4ad1f310d5283ee7cfdf5a7_::_lambda_dccbdc39c4ad1f310d5283ee7cfdf5a7_(v35, &tableid, a1);
  v34 = 1;
  v12 = *(unsigned __int64 **)v11;
  v13 = *(_QWORD *)(v11 + 8);
  v33[0] = *(_QWORD *)v11;
  v33[1] = v13;
  v14 = StringCchPrintfA(szIndexName, 9u, "%08x", a3);
  HresultFromJetError = v14;
  if ( v14 < 0 )
  {
    Log_UnistoreHREvent_0(
      (unsigned int)v14,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbsession.cpp",
      1363);
    if ( *v12 != -1 )
      CommsESE_JetCloseTable(*(_QWORD *)(v13 + 216), *v12);
    return HresultFromJetError;
  }
  v15 = JetSetCurrentIndex2A(*(_QWORD *)(a1 + 216), tableid, szIndexName, 0);
  CheckCorruption(v15);
  if ( v15 < 0 )
  {
    v23 = (unsigned int)MakeHresultFromJetError(v15);
    Log_UnistoreHREvent_0(
      v23,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbsession.cpp",
      1365);
    goto LABEL_11;
  }
  v16 = (TableHandleInfo *)operator new(0x50u);
  if ( !v16 || (v17 = TableHandleInfo::TableHandleInfo(v16), (v19 = v17) == 0) )
  {
    LODWORD(v23) = -2147024882;
    Log_UnistoreHREvent_0(
      2147942414LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbsession.cpp",
      1368);
    if ( *v12 != -1 )
      CommsESE_JetCloseTable(*(_QWORD *)(v13 + 216), *v12);
    return (unsigned int)v23;
  }
  *((_QWORD *)v17 + 1) = *(_QWORD *)(a1 + 216);
  v20 = tableid;
  *((_QWORD *)v17 + 2) = tableid;
  *(_DWORD *)v17 = v5;
  *((_DWORD *)v17 + 1) = a3;
  *((_DWORD *)v17 + 6) = 0;
  if ( v20 == -1 )
    Log_AssertionEvent_3(-1, v18, 1377);
  v21 = *(_QWORD *)(a1 + 232);
  v22 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v22 )
  {
    LODWORD(v23) = -2147024882;
    Log_UnistoreHREvent_0(
      2147942414LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbsession.cpp",
      1379);
    tlx::_delete<TableHandleInfo>(v19, v24);
LABEL_11:
    tlx::_UndoSolo__lambda_0587ad0ebb2bc45fb6853097835fe23f___::__UndoSolo__lambda_0587ad0ebb2bc45fb6853097835fe23f___(v33);
    return (unsigned int)v23;
  }
  v22[2] = v19;
  v29 = *(_QWORD **)(v21 + 8);
  v22[1] = v29;
  *v22 = v21;
  *v29 = v22;
  *(_QWORD *)(v21 + 8) = v22;
  ++*(_QWORD *)(a1 + 248);
  v30 = *(_DWORD *)(a1 + 248);
  if ( g_perfStatEnabled )
  {
    _InterlockedIncrement(&dword_18010DB34);
    _InterlockedAdd(&dword_18010DB2C, v30);
    do
      v31 = dword_18010DB30;
    while ( dword_18010DB30 < v30 && v31 != _InterlockedCompareExchange(&dword_18010DB30, v30, dword_18010DB30) );
  }
  *a4 = v19;
  return 0;
}

```

## disassembly

```asm
0x180012ed0  push    rbp
0x180012ed2  push    rbx
0x180012ed3  push    rsi
0x180012ed4  push    rdi
0x180012ed5  push    r12
0x180012ed7  push    r13
0x180012ed9  push    r14
0x180012edb  push    r15
0x180012edd  lea     rbp, [rsp-1Fh]
0x180012ee2  sub     rsp, 98h
0x180012ee9  mov     rax, cs:__security_cookie
0x180012ef0  xor     rax, rsp
0x180012ef3  mov     [rbp+57h+var_50], rax
0x180012ef7  mov     r13, r9
0x180012efa  movsxd  r15, edx
0x180012efd  mov     r12d, r8d
0x180012f00  mov     rdi, rcx
0x180012f03  call    ?_EnsureDBOpened@DBSession@@AEAAJXZ; DBSession::_EnsureDBOpened(void)
0x180012f08  mov     ebx, eax
0x180012f0a  test    eax, eax
0x180012f0c  js      loc_180013100
0x180012f12  mov     ecx, r15d; unsigned int
0x180012f15  mov     [rbp+57h+tableid], 0FFFFFFFFFFFFFFFFh
0x180012f1d  call    ?GetTableClassGrBit@@YAKK@Z; GetTableClassGrBit(ulong)
0x180012f22  lea     rdx, ?g_rgTableInfo@@3QBUUSTableInfo@@B; USTableInfo const near * const g_rgTableInfo
0x180012f29  or      eax, 8048h
0x180012f2e  lea     rcx, [rbp+57h+tableid]
0x180012f32  xor     r9d, r9d; pvParameters
0x180012f35  mov     [rsp+0D0h+ptableid], rcx; ptableid
0x180012f3a  lea     r8, [r15+r15*2]
0x180012f3e  mov     rcx, [rdi+0D8h]; sesid
0x180012f45  shl     r8, 5
0x180012f49  mov     [rsp+0D0h+grbit], eax; grbit
0x180012f4d  mov     [rsp+0D0h+cbParameters], 0; cbParameters
0x180012f55  mov     r8, [r8+rdx]; szTableName
0x180012f59  mov     edx, [rdi+0E0h]; dbid
0x180012f5f  call    cs:__imp_JetOpenTableW
0x180012f65  mov     ecx, eax; int
0x180012f67  mov     ebx, eax
0x180012f69  call    ?CheckCorruption@@YAXJ@Z; CheckCorruption(long)
0x180012f6e  test    ebx, ebx
0x180012f70  js      loc_1800130A8
0x180012f76  mov     r8, rdi
0x180012f79  lea     rdx, [rbp+57h+tableid]
0x180012f7d  lea     rcx, [rbp+57h+var_70]
0x180012f81  call    _lambda_dccbdc39c4ad1f310d5283ee7cfdf5a7____lambda_dccbdc39c4ad1f310d5283ee7cfdf5a7_
0x180012f86  mov     r9d, r12d
0x180012f89  mov     [rbp+57h+var_78], 1
0x180012f8d  lea     r8, a08x; "%08x"
0x180012f94  mov     edx, 9; unsigned __int64
0x180012f99  lea     rcx, [rbp+57h+szIndexName]; char *
0x180012f9d  mov     r14, [rax]
0x180012fa0  mov     rsi, [rax+8]
0x180012fa4  mov     [rbp+57h+var_88], r14
0x180012fa8  mov     [rbp+57h+var_80], rsi
0x180012fac  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180012fb1  mov     ebx, eax
0x180012fb3  test    eax, eax
0x180012fb5  js      loc_18001310F
0x180012fbb  mov     rdx, [rbp+57h+tableid]; tableid
0x180012fbf  lea     r8, [rbp+57h+szIndexName]; szIndexName
0x180012fc3  mov     rcx, [rdi+0D8h]; sesid
0x180012fca  xor     r9d, r9d; grbit
0x180012fcd  call    cs:__imp_JetSetCurrentIndex2A
0x180012fd3  mov     ecx, eax; int
0x180012fd5  mov     ebx, eax
0x180012fd7  call    ?CheckCorruption@@YAXJ@Z; CheckCorruption(long)
0x180012fdc  test    ebx, ebx
0x180012fde  js      loc_18001319C
0x180012fe4  mov     ecx, 50h ; 'P'; Size
0x180012fe9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012fee  test    rax, rax
0x180012ff1  jz      loc_180013163
0x180012ff7  mov     rcx, rax; this
0x180012ffa  call    ??0TableHandleInfo@@QEAA@XZ; TableHandleInfo::TableHandleInfo(void)
0x180012fff  mov     rbx, rax
0x180013002  test    rax, rax
0x180013005  jz      loc_180013163
0x18001300b  mov     rcx, [rdi+0D8h]
0x180013012  mov     [rax+8], rcx
0x180013016  mov     rcx, [rbp+57h+tableid]
0x18001301a  mov     [rax+10h], rcx
0x18001301e  mov     [rax], r15d
0x180013021  mov     [rax+4], r12d
0x180013025  mov     dword ptr [rax+18h], 0
0x18001302c  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180013030  jnz     short loc_18001303D
0x180013032  mov     r8d, 561h
0x180013038  call    Log_AssertionEvent_3
0x18001303d  mov     rsi, [rdi+0E8h]
0x180013044  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001304b  mov     ecx, 18h; unsigned __int64
0x180013050  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180013055  test    rax, rax
0x180013058  jnz     short loc_1800130CB
0x18001305a  mov     edi, 8007000Eh
0x18001305f  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180013066  mov     ecx, edi
0x180013068  mov     r9d, 563h
0x18001306e  xor     edx, edx
0x180013070  call    Log_UnistoreHREvent_0
0x180013075  mov     rcx, rbx
0x180013078  call    ??$_delete@UTableHandleInfo@@@tlx@@YAXPEAUTableHandleInfo@@@Z; tlx::_delete<TableHandleInfo>(TableHandleInfo *)
0x18001307d  lea     rcx, [rbp+57h+var_88]
0x180013081  call    tlx___UndoSolo__lambda_0587ad0ebb2bc45fb6853097835fe23f_______UndoSolo__lambda_0587ad0ebb2bc45fb6853097835fe23f___
0x180013086  mov     eax, edi
0x180013088  mov     rcx, [rbp+57h+var_50]
0x18001308c  xor     rcx, rsp; StackCookie
0x18001308f  call    __security_check_cookie
0x180013094  add     rsp, 98h
0x18001309b  pop     r15
0x18001309d  pop     r14
0x18001309f  pop     r13
0x1800130a1  pop     r12
0x1800130a3  pop     rdi
0x1800130a4  pop     rsi
0x1800130a5  pop     rbx
0x1800130a6  pop     rbp
0x1800130a7  retn
0x1800130a8  mov     ecx, ebx; int
0x1800130aa  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x1800130af  mov     ebx, eax
0x1800130b1  mov     r9d, 548h
0x1800130b7  xor     edx, edx
0x1800130b9  mov     ecx, eax
0x1800130bb  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800130c2  call    Log_UnistoreHREvent_0
0x1800130c7  mov     eax, ebx
0x1800130c9  jmp     short loc_180013088
0x1800130cb  mov     [rax+10h], rbx
0x1800130cf  mov     rcx, [rsi+8]
0x1800130d3  mov     [rax+8], rcx
0x1800130d7  mov     [rax], rsi
0x1800130da  mov     [rcx], rax
0x1800130dd  mov     [rsi+8], rax
0x1800130e1  inc     qword ptr [rdi+0F8h]
0x1800130e8  mov     eax, cs:?g_perfStatEnabled@@3KC; ulong volatile g_perfStatEnabled
0x1800130ee  mov     ecx, [rdi+0F8h]
0x1800130f4  test    eax, eax
0x1800130f6  jnz     short loc_18001313F
0x1800130f8  mov     [r13+0], rbx
0x1800130fc  xor     eax, eax
0x1800130fe  jmp     short loc_180013088
0x180013100  mov     r9d, 53Ch
0x180013106  mov     edx, 1
0x18001310b  mov     ecx, ebx
0x18001310d  jmp     short loc_1800130BB
0x18001310f  mov     r9d, 553h
0x180013115  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001311c  mov     edx, 1
0x180013121  mov     ecx, ebx
0x180013123  call    Log_UnistoreHREvent_0
0x180013128  cmp     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x18001312c  jz      short loc_1800130C7
0x18001312e  mov     rdx, [r14]; unsigned __int64
0x180013131  mov     rcx, [rsi+0D8h]; unsigned __int64
0x180013138  call    ?CommsESE_JetCloseTable@@YAJ_K0@Z; CommsESE_JetCloseTable(unsigned __int64,unsigned __int64)
0x18001313d  jmp     short loc_1800130C7
0x18001313f  lock inc cs:dword_18010DB34
0x180013146  lock add cs:dword_18010DB2C, ecx
0x18001314d  mov     eax, cs:dword_18010DB30
0x180013153  cmp     eax, ecx
0x180013155  jnb     short loc_1800130F8
0x180013157  lock cmpxchg cs:dword_18010DB30, ecx
0x18001315f  jnz     short loc_18001314D
0x180013161  jmp     short loc_1800130F8
0x180013163  mov     edi, 8007000Eh
0x180013168  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001316f  mov     ecx, edi
0x180013171  mov     r9d, 558h
0x180013177  xor     edx, edx
0x180013179  call    Log_UnistoreHREvent_0
0x18001317e  cmp     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x180013182  jz      loc_180013086
0x180013188  mov     rdx, [r14]; unsigned __int64
0x18001318b  mov     rcx, [rsi+0D8h]; unsigned __int64
0x180013192  call    ?CommsESE_JetCloseTable@@YAJ_K0@Z; CommsESE_JetCloseTable(unsigned __int64,unsigned __int64)
0x180013197  jmp     loc_180013086
0x18001319c  mov     ecx, ebx; int
0x18001319e  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x1800131a3  mov     r9d, 555h
0x1800131a9  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800131b0  xor     edx, edx
0x1800131b2  mov     ecx, eax
0x1800131b4  mov     edi, eax
0x1800131b6  call    Log_UnistoreHREvent_0
0x1800131bb  jmp     loc_18001307D
```
