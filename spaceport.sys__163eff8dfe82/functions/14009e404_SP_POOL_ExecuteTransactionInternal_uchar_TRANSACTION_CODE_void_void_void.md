# SP_POOL::ExecuteTransactionInternal(uchar,TRANSACTION_CODE,void *,void *,void *)

- ea: `0x14009e404`
- end: `0x14009e75b`
- name: `?ExecuteTransactionInternal@SP_POOL@@AEAAJEW4TRANSACTION_CODE@@PEAX11@Z`
- size: `855`
- prototype: ``
- caller_count: `4`
- callee_count: `22`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140097518`
- `0x14009e3d8`
- `0x1400a22cc`
- `0x1400afca4`

## callees

- `0x14000200c`
- `0x140002bbc`
- `0x14000eba0`
- `0x14001e4a0`
- `0x14001fe40`
- `0x14002fdb0`
- `0x1400320a8`
- `0x140032354`
- `0x1400325fc`
- `0x140032904`
- `0x140060360`
- `0x1400606ac`
- `0x140062e9c`
- `0x140064b48`
- `0x14009d8a4`
- `0x14009ded8`
- `0x14009e19c`
- `0x14009e404`
- `0x14009efc4`
- `0x14009f77c`
- `0x14009f82c`
- `0x1400a04f4`

## import_xrefs

- `ntoskrnl!IoGetActivityIdThread` at `0x14009e58a`
- `ntoskrnl!IoGetActivityIdThread` at `0x14009e58a`

## pseudocode

```c
__int64 __fastcall SP_POOL::ExecuteTransactionInternal(
        __int64 a1,
        char a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  char v6; // r12
  __int64 v11; // r15
  int v12; // esi
  __int64 v13; // rbx
  SP_POOL *v14; // rcx
  __int64 v15; // rax
  char v16; // bl
  SDB_CONFIG *v17; // rcx
  int v18; // eax
  char v19; // r15
  void *v20; // r14
  char v21; // bl
  __int64 v22; // rcx
  int ActivityIdThread; // eax
  unsigned int v24; // ebx
  int v25; // edx
  char v26; // bl
  SP_POOL *v27; // rcx
  int v28; // ecx
  int v29; // r8d
  __int64 v30; // r9
  char v32; // [rsp+30h] [rbp-69h]
  unsigned __int8 v33[4]; // [rsp+60h] [rbp-39h] BYREF
  unsigned int v34; // [rsp+64h] [rbp-35h] BYREF
  struct _SP_DEVICE_CHANGE *v35; // [rsp+68h] [rbp-31h] BYREF
  __int64 v36; // [rsp+70h] [rbp-29h] BYREF
  void *v37; // [rsp+78h] [rbp-21h] BYREF
  __int64 v38; // [rsp+80h] [rbp-19h] BYREF
  __int64 v39; // [rsp+88h] [rbp-11h] BYREF
  __int64 v40; // [rsp+90h] [rbp-9h] BYREF
  __int64 v41; // [rsp+98h] [rbp-1h] BYREF
  __int64 v42; // [rsp+A0h] [rbp+7h] BYREF
  __int64 v43; // [rsp+A8h] [rbp+Fh] BYREF
  unsigned __int8 v44; // [rsp+F0h] [rbp+57h] BYREF
  unsigned int v45; // [rsp+100h] [rbp+67h]

  v45 = a3;
  v6 = 0;
  v35 = 0;
  v34 = 0;
  v44 = 0;
  v38 = 0;
  v36 = 0;
  v37 = 0;
  v11 = MEMORY[0xFFFFF78000000014];
  v39 = MEMORY[0xFFFFF78000000014];
  v33[0] = 0;
  SpGetTransactionTargetIds(a3, a4, a5);
  SDB_CONFIG::BeginTransaction(*(SDB_CONFIG **)(a1 + 48));
  v12 = SP_POOL::DispatchTransaction(a1, a3, a4, a5, a6);
  if ( v12 < 0 || a2 )
    goto LABEL_8;
  v13 = MEMORY[0xFFFFF78000000014];
  v38 = MEMORY[0xFFFFF78000000014] - v11;
  v12 = SP_POOL::PrepareCommit((SP_POOL *)a1, &v44, &v35, &v34);
  if ( v12 < 0 )
  {
LABEL_7:
    SP_POOL::AbortDevices(v14, v35, v34);
LABEL_8:
    v19 = 0;
    SDB_CONFIG::AbortRecords(*(SDB_CONFIG **)(a1 + 48));
    goto LABEL_9;
  }
  v15 = MEMORY[0xFFFFF78000000014] - v13;
  v16 = MEMORY[0xFFFFF78000000014];
  v17 = *(SDB_CONFIG **)(a1 + 48);
  v36 = v15;
  v18 = SDB_CONFIG::CommitTransaction(v17, v33);
  v12 = v18;
  if ( v18 < 0 )
  {
    if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 1) != 0 )
      McTemplateK0jq_EtwWriteTransfer(v14, PoolConfigWriteFailure, 0, a1 + 108, v18);
    goto LABEL_7;
  }
  v19 = MEMORY[0xFFFFF78000000014] - v16;
  if ( v44 )
    SP_POOL::PauseTasks((KSPIN_LOCK *)a1);
  SP_POOL::Commit((SP_POOL *)a1);
  v26 = MEMORY[0xFFFFF78000000014];
  SP_POOL::CommitDevices(v27, v35, v34);
  v6 = MEMORY[0xFFFFF78000000014] - v26;
  if ( v44 )
    SP_POOL::ResumeTasks((SP_POOL *)a1);
  SP_POOL::PostCommitDevices((SP_POOL *)a1, v35, v34);
  SDB_CONFIG::CommitRecords(*(SDB_CONFIG **)(a1 + 48));
  if ( v33[0] && *(_BYTE *)(a1 + 65) && !SDB_CONFIG::IsWritable(*(SDB_CONFIG **)(a1 + 48)) )
    SP_POOL::Offline(a1, 3);
LABEL_9:
  if ( v35 )
    SC_ENV_ALLOCATOR::operator delete[](v35);
  if ( v12 == -1070071804 )
    SP_POOL::Offline(a1, 3);
  v20 = v37;
  if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 0x40) != 0 )
  {
    v21 = SDB_CONFIG::Sequence(*(SDB_CONFIG **)(a1 + 48));
    ActivityIdThread = IoGetActivityIdThread(v22);
    v32 = v21;
    v24 = v45;
    McTemplateK0jqqxxxxxz_EtwWriteTransfer(
      v38,
      v25,
      ActivityIdThread,
      a1 + 108,
      v45,
      v12,
      v32,
      v38,
      v36,
      v19,
      v6,
      (__int64)v20);
  }
  else
  {
    v24 = v45;
  }
  if ( v20 )
    SC_ENV_ALLOCATOR::operator delete[](v20);
  if ( (unsigned int)dword_14007F050 > 5 && (unsigned __int8)tlgKeywordOn(&dword_14007F050, 0x400000000000LL) )
  {
    v40 = v30 - v39;
    v41 = v30 - v39;
    v42 = v30 - v39;
    v39 = 0x1000000;
    LODWORD(v36) = v12;
    LODWORD(v37) = v24;
    v38 = a1 + 108;
    v43 = 1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      v28,
      (unsigned int)&word_140075816,
      v29,
      (unsigned int)&v43,
      (__int64)&v42,
      (__int64)&v41,
      (__int64)&v40,
      (__int64)&v38,
      (__int64)&v37,
      (__int64)&v36,
      (__int64)&v39);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14009e404  mov     [rsp-8+arg_8], rbx
0x14009e409  mov     [rsp-8+arg_10], r8d
0x14009e40e  push    rbp
0x14009e40f  push    rsi
0x14009e410  push    rdi
0x14009e411  push    r12
0x14009e413  push    r13
0x14009e415  push    r14
0x14009e417  push    r15
0x14009e419  lea     rbp, [rsp-17h]
0x14009e41e  sub     rsp, 0B0h
0x14009e425  xor     r12d, r12d
0x14009e428  lea     rax, [rbp+47h+var_68]
0x14009e42c  mov     esi, r8d
0x14009e42f  mov     [rbp+47h+var_78], r12
0x14009e433  mov     r8, [rbp+47h+arg_20]
0x14009e437  mov     r14b, dl
0x14009e43a  mov     [rbp+47h+var_7C], r12d
0x14009e43e  mov     rdi, rcx
0x14009e441  mov     [rbp+47h+arg_0], r12b
0x14009e445  mov     r13, 0FFFFF78000000014h
0x14009e44f  mov     rdx, r9
0x14009e452  mov     [rbp+47h+var_60], r12
0x14009e456  mov     ecx, esi
0x14009e458  mov     [rbp+47h+var_70], r12
0x14009e45c  mov     rbx, r9
0x14009e45f  mov     [rbp+47h+var_68], r12
0x14009e463  mov     r15, [r13+0]
0x14009e467  mov     [rbp+47h+var_58], r15
0x14009e46b  mov     [rbp+47h+var_80], r12b
0x14009e46f  mov     [rsp+0E0h+var_C0], rax
0x14009e474  call    ?SpGetTransactionTargetIds@@YAXW4TRANSACTION_CODE@@PEAX11PEAPEAG@Z; SpGetTransactionTargetIds(TRANSACTION_CODE,void *,void *,void *,ushort * *)
0x14009e479  mov     rcx, [rdi+30h]; this
0x14009e47d  call    ?BeginTransaction@SDB_CONFIG@@QEAAXXZ; SDB_CONFIG::BeginTransaction(void)
0x14009e482  mov     rcx, [rbp+47h+arg_28]
0x14009e486  mov     r8, rbx
0x14009e489  mov     r9, [rbp+47h+arg_20]
0x14009e48d  mov     edx, esi
0x14009e48f  mov     [rsp+0E0h+var_C0], rcx
0x14009e494  mov     rcx, rdi
0x14009e497  call    ?DispatchTransaction@SP_POOL@@AEAAJW4TRANSACTION_CODE@@PEAX11@Z; SP_POOL::DispatchTransaction(TRANSACTION_CODE,void *,void *,void *)
0x14009e49c  mov     esi, eax
0x14009e49e  test    eax, eax
0x14009e4a0  js      loc_14009E537
0x14009e4a6  test    r14b, r14b
0x14009e4a9  jnz     loc_14009E537
0x14009e4af  mov     rax, ds:0FFFFF78000000014h
0x14009e4b9  lea     r9, [rbp+47h+var_7C]; unsigned int *
0x14009e4bd  mov     rbx, [r13+0]
0x14009e4c1  lea     r8, [rbp+47h+var_78]; struct _SP_DEVICE_CHANGE **
0x14009e4c5  sub     rax, r15
0x14009e4c8  lea     rdx, [rbp+47h+arg_0]; unsigned __int8 *
0x14009e4cc  mov     rcx, rdi; this
0x14009e4cf  mov     [rbp+47h+var_60], rax
0x14009e4d3  call    ?PrepareCommit@SP_POOL@@AEAAJPEAEPEAPEAU_SP_DEVICE_CHANGE@@PEAK@Z; SP_POOL::PrepareCommit(uchar *,_SP_DEVICE_CHANGE * *,ulong *)
0x14009e4d8  mov     esi, eax
0x14009e4da  test    eax, eax
0x14009e4dc  js      short loc_14009E52A
0x14009e4de  mov     rax, ds:0FFFFF78000000014h
0x14009e4e8  lea     rdx, [rbp+47h+var_80]; unsigned __int8 *
0x14009e4ec  sub     rax, rbx
0x14009e4ef  mov     rbx, [r13+0]
0x14009e4f3  mov     rcx, [rdi+30h]; this
0x14009e4f7  mov     [rbp+47h+var_70], rax
0x14009e4fb  call    ?CommitTransaction@SDB_CONFIG@@QEAAJPEAE@Z; SDB_CONFIG::CommitTransaction(uchar *)
0x14009e500  mov     esi, eax
0x14009e502  test    eax, eax
0x14009e504  jns     loc_14009E5D7
0x14009e50a  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 1
0x14009e511  jz      short loc_14009E52A
0x14009e513  lea     r9, [rdi+6Ch]
0x14009e517  mov     dword ptr [rsp+0E0h+var_C0], eax
0x14009e51b  xor     r8d, r8d
0x14009e51e  lea     rdx, PoolConfigWriteFailure
0x14009e525  call    McTemplateK0jq_EtwWriteTransfer
0x14009e52a  mov     r8d, [rbp+47h+var_7C]; unsigned int
0x14009e52e  mov     rdx, [rbp+47h+var_78]; struct _SP_DEVICE_CHANGE *
0x14009e532  call    ?AbortDevices@SP_POOL@@AEAAXPEAU_SP_DEVICE_CHANGE@@K@Z; SP_POOL::AbortDevices(_SP_DEVICE_CHANGE *,ulong)
0x14009e537  mov     rcx, [rdi+30h]; this
0x14009e53b  mov     r15, r12
0x14009e53e  call    ?AbortRecords@SDB_CONFIG@@QEAAXXZ; SDB_CONFIG::AbortRecords(void)
0x14009e543  mov     rcx, [rbp+47h+var_78]; void *
0x14009e547  test    rcx, rcx
0x14009e54a  jz      short loc_14009E551
0x14009e54c  call    ??_VSC_ENV_ALLOCATOR@@SAXPEAX@Z; SC_ENV_ALLOCATOR::operator delete[](void *)
0x14009e551  cmp     esi, 0C0380004h
0x14009e557  jnz     short loc_14009E569
0x14009e559  mov     r8b, 1
0x14009e55c  mov     edx, 3
0x14009e561  mov     rcx, rdi
0x14009e564  call    ?Offline@SP_POOL@@QEAAXW4_SP_POOL_READ_ONLY_REASON@@E@Z; SP_POOL::Offline(_SP_POOL_READ_ONLY_REASON,uchar)
0x14009e569  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 40h
0x14009e570  lea     r13, [rdi+6Ch]
0x14009e574  mov     r14, [rbp+47h+var_68]
0x14009e578  jz      loc_14009E67E
0x14009e57e  mov     rcx, [rdi+30h]; this
0x14009e582  call    ?Sequence@SDB_CONFIG@@QEAA_KXZ; SDB_CONFIG::Sequence(void)
0x14009e587  mov     rbx, rax
0x14009e58a  call    cs:__imp_IoGetActivityIdThread
0x14009e591  nop     dword ptr [rax+rax+00h]
0x14009e596  mov     rcx, [rbp+47h+var_70]
0x14009e59a  mov     r9, r13
0x14009e59d  mov     [rsp+0E0h+var_88], r14
0x14009e5a2  mov     r8, rax
0x14009e5a5  mov     [rsp+0E0h+var_90], r12
0x14009e5aa  mov     [rsp+0E0h+var_98], r15
0x14009e5af  mov     [rsp+0E0h+var_A0], rcx
0x14009e5b4  mov     rcx, [rbp+47h+var_60]
0x14009e5b8  mov     [rsp+0E0h+var_A8], rcx
0x14009e5bd  mov     [rsp+0E0h+var_B0], rbx
0x14009e5c2  mov     ebx, [rbp+47h+arg_10]
0x14009e5c5  mov     dword ptr [rsp+0E0h+var_B8], esi
0x14009e5c9  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x14009e5cd  call    McTemplateK0jqqxxxxxz_EtwWriteTransfer
0x14009e5d2  jmp     loc_14009E681
0x14009e5d7  mov     rax, ds:0FFFFF78000000014h
0x14009e5e1  mov     r15, rax
0x14009e5e4  sub     r15, rbx
0x14009e5e7  cmp     [rbp+47h+arg_0], r12b
0x14009e5eb  jz      short loc_14009E5F5
0x14009e5ed  mov     rcx, rdi; this
0x14009e5f0  call    ?PauseTasks@SP_POOL@@QEAAXXZ; SP_POOL::PauseTasks(void)
0x14009e5f5  mov     rcx, rdi; this
0x14009e5f8  call    ?Commit@SP_POOL@@QEAAXXZ; SP_POOL::Commit(void)
0x14009e5fd  mov     rbx, [r13+0]
0x14009e601  mov     r8d, [rbp+47h+var_7C]; unsigned int
0x14009e605  mov     rdx, [rbp+47h+var_78]; struct _SP_DEVICE_CHANGE *
0x14009e609  call    ?CommitDevices@SP_POOL@@AEAAXPEAU_SP_DEVICE_CHANGE@@K@Z; SP_POOL::CommitDevices(_SP_DEVICE_CHANGE *,ulong)
0x14009e60e  mov     rax, ds:0FFFFF78000000014h
0x14009e618  mov     r12, rax
0x14009e61b  sub     r12, rbx
0x14009e61e  cmp     [rbp+47h+arg_0], 0
0x14009e622  jz      short loc_14009E62C
0x14009e624  mov     rcx, rdi; this
0x14009e627  call    ?ResumeTasks@SP_POOL@@QEAAXXZ; SP_POOL::ResumeTasks(void)
0x14009e62c  mov     r8d, [rbp+47h+var_7C]; unsigned int
0x14009e630  mov     rcx, rdi; this
0x14009e633  mov     rdx, [rbp+47h+var_78]; struct _SP_DEVICE_CHANGE *
0x14009e637  call    ?PostCommitDevices@SP_POOL@@AEAAXPEAU_SP_DEVICE_CHANGE@@K@Z; SP_POOL::PostCommitDevices(_SP_DEVICE_CHANGE *,ulong)
0x14009e63c  mov     rcx, [rdi+30h]; this
0x14009e640  call    ?CommitRecords@SDB_CONFIG@@QEAAXXZ; SDB_CONFIG::CommitRecords(void)
0x14009e645  cmp     [rbp+47h+var_80], 0
0x14009e649  jz      loc_14009E543
0x14009e64f  cmp     byte ptr [rdi+41h], 0
0x14009e653  jz      loc_14009E543
0x14009e659  mov     rcx, [rdi+30h]; this
0x14009e65d  call    ?IsWritable@SDB_CONFIG@@QEAAEXZ; SDB_CONFIG::IsWritable(void)
0x14009e662  test    al, al
0x14009e664  jnz     loc_14009E543
0x14009e66a  xor     r8d, r8d
0x14009e66d  mov     rcx, rdi
0x14009e670  lea     edx, [r8+3]
0x14009e674  call    ?Offline@SP_POOL@@QEAAXW4_SP_POOL_READ_ONLY_REASON@@E@Z; SP_POOL::Offline(_SP_POOL_READ_ONLY_REASON,uchar)
0x14009e679  jmp     loc_14009E543
0x14009e67e  mov     ebx, [rbp+47h+arg_10]
0x14009e681  test    r14, r14
0x14009e684  jz      short loc_14009E68E
0x14009e686  mov     rcx, r14; void *
0x14009e689  call    ??_VSC_ENV_ALLOCATOR@@SAXPEAX@Z; SC_ENV_ALLOCATOR::operator delete[](void *)
0x14009e68e  mov     r9, 0FFFFF78000000014h
0x14009e698  mov     r9, [r9]
0x14009e69b  mov     eax, cs:dword_14007F050
0x14009e6a1  cmp     eax, 5
0x14009e6a4  jbe     loc_14009E73D
0x14009e6aa  mov     rdx, 400000000000h
0x14009e6b4  lea     rcx, dword_14007F050
0x14009e6bb  call    _tlgKeywordOn
0x14009e6c0  test    al, al
0x14009e6c2  jz      short loc_14009E73D
0x14009e6c4  sub     r9, [rbp+47h+var_58]
0x14009e6c8  lea     rax, [rbp+47h+var_58]
0x14009e6cc  mov     [rbp+47h+var_50], r9
0x14009e6d0  mov     [rsp+0E0h+var_90], rax
0x14009e6d5  lea     rdx, word_140075816
0x14009e6dc  lea     rax, [rbp+47h+var_70]
0x14009e6e0  mov     [rbp+47h+var_48], r9
0x14009e6e4  mov     [rsp+0E0h+var_98], rax
0x14009e6e9  lea     rax, [rbp+47h+var_68]
0x14009e6ed  mov     [rsp+0E0h+var_A0], rax
0x14009e6f2  lea     rax, [rbp+47h+var_60]
0x14009e6f6  mov     [rsp+0E0h+var_A8], rax
0x14009e6fb  lea     rax, [rbp+47h+var_50]
0x14009e6ff  mov     [rsp+0E0h+var_B0], rax
0x14009e704  lea     rax, [rbp+47h+var_48]
0x14009e708  mov     [rsp+0E0h+var_B8], rax
0x14009e70d  lea     rax, [rbp+47h+var_40]
0x14009e711  mov     [rbp+47h+var_40], r9
0x14009e715  lea     r9, [rbp+47h+var_38]
0x14009e719  mov     [rsp+0E0h+var_C0], rax
0x14009e71e  mov     [rbp+47h+var_58], 1000000h
0x14009e726  mov     dword ptr [rbp+47h+var_70], esi
0x14009e729  mov     dword ptr [rbp+47h+var_68], ebx
0x14009e72c  mov     [rbp+47h+var_60], r13
0x14009e730  mov     [rbp+47h+var_38], 1
0x14009e738  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U1@U1@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U3@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBX1IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteAgg@@YAJ011I2@ZPEBX@@SAJPEBU_tlgProvider_t@@PEBX1AEBU?$_tlgWrapperByVal@$07@@222AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@42@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,void const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x14009e73d  mov     rbx, [rsp+0E0h+arg_8]
0x14009e745  mov     eax, esi
0x14009e747  add     rsp, 0B0h
0x14009e74e  pop     r15
0x14009e750  pop     r14
0x14009e752  pop     r13
0x14009e754  pop     r12
0x14009e756  pop     rdi
0x14009e757  pop     rsi
0x14009e758  pop     rbp
0x14009e759  retn
```
