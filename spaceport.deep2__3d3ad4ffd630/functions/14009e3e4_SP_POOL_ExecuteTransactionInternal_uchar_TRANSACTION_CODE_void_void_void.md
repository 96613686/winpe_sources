# SP_POOL::ExecuteTransactionInternal(uchar,TRANSACTION_CODE,void *,void *,void *)

- ea: `0x14009e3e4`
- end: `0x14009e74a`
- name: `?ExecuteTransactionInternal@SP_POOL@@AEAAJEW4TRANSACTION_CODE@@PEAX11@Z`
- size: `870`
- prototype: ``
- caller_count: `4`
- callee_count: `22`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140097518`
- `0x14009e3b8`
- `0x1400a219c`
- `0x1400afb04`

## callees

- `0x14000200c`
- `0x140002bbc`
- `0x14000eba0`
- `0x14001e4a0`
- `0x14001fe40`
- `0x14002fd40`
- `0x1400308a8`
- `0x140032038`
- `0x1400322e4`
- `0x14003258c`
- `0x140032894`
- `0x140060210`
- `0x14006055c`
- `0x140062d4c`
- `0x1400649f8`
- `0x14009d884`
- `0x14009deb8`
- `0x14009e17c`
- `0x14009e3e4`
- `0x14009efb0`
- `0x14009f768`
- `0x14009f818`

## import_xrefs

- `ntoskrnl!IoGetActivityIdThread` at `0x14009e43c`
- `ntoskrnl!IoGetActivityIdThread` at `0x14009e58d`
- `ntoskrnl!IoGetActivityIdThread` at `0x14009e43c`
- `ntoskrnl!IoGetActivityIdThread` at `0x14009e58d`

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
  SDB_CONFIG **v7; // rdi
  char v12; // bl
  __int64 v13; // rcx
  int ActivityIdThread; // eax
  int v15; // ecx
  __int64 v16; // rbx
  SDB_CONFIG *v17; // rcx
  int v18; // r14d
  __int64 v19; // rbx
  SP_POOL *v20; // rcx
  __int64 v21; // rax
  char v22; // bl
  SDB_CONFIG *v23; // rcx
  int v24; // eax
  char v25; // r15
  char v26; // bl
  __int64 v27; // rcx
  int v28; // eax
  int v29; // edx
  int v30; // ecx
  int v31; // r8d
  __int64 v32; // r9
  char v34; // bl
  SP_POOL *v35; // rcx
  unsigned __int8 v36[4]; // [rsp+60h] [rbp-49h] BYREF
  unsigned int v37; // [rsp+64h] [rbp-45h] BYREF
  struct _SP_DEVICE_CHANGE *v38; // [rsp+68h] [rbp-41h] BYREF
  __int64 v39; // [rsp+70h] [rbp-39h] BYREF
  __int64 v40; // [rsp+78h] [rbp-31h] BYREF
  __int64 v41; // [rsp+80h] [rbp-29h] BYREF
  __int64 v42; // [rsp+88h] [rbp-21h] BYREF
  __int64 v43; // [rsp+90h] [rbp-19h] BYREF
  __int64 v44; // [rsp+98h] [rbp-11h] BYREF
  __int64 v45; // [rsp+A0h] [rbp-9h] BYREF
  __int64 v46; // [rsp+A8h] [rbp-1h] BYREF
  unsigned __int8 v47; // [rsp+100h] [rbp+57h] BYREF

  v6 = 0;
  v7 = (SDB_CONFIG **)(a1 + 48);
  v38 = 0;
  v37 = 0;
  v39 = 0;
  v40 = 0;
  v36[0] = 0;
  v47 = 0;
  if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 0x40) != 0 )
  {
    v12 = SDB_CONFIG::Sequence(*v7);
    ActivityIdThread = IoGetActivityIdThread(v13);
    McTemplateK0jqx_EtwWriteTransfer(v15, (unsigned int)PoolTransactionStart, ActivityIdThread, a1 + 108, a3, v12);
  }
  v16 = MEMORY[0xFFFFF78000000014];
  v17 = *v7;
  v41 = MEMORY[0xFFFFF78000000014];
  SDB_CONFIG::BeginTransaction(v17);
  v18 = SP_POOL::DispatchTransaction(a1, a3, a4, a5, a6);
  if ( v18 < 0 || a2 )
    goto LABEL_10;
  v39 = MEMORY[0xFFFFF78000000014] - v16;
  v19 = MEMORY[0xFFFFF78000000014];
  v18 = SP_POOL::PrepareCommit((SP_POOL *)a1, &v47, &v38, &v37);
  if ( v18 < 0 )
  {
LABEL_9:
    SP_POOL::AbortDevices(v20, v38, v37);
LABEL_10:
    v25 = 0;
    SDB_CONFIG::AbortRecords(*v7);
    goto LABEL_11;
  }
  v21 = MEMORY[0xFFFFF78000000014] - v19;
  v22 = MEMORY[0xFFFFF78000000014];
  v23 = *v7;
  v40 = v21;
  v24 = SDB_CONFIG::CommitTransaction(v23, v36);
  v18 = v24;
  if ( v24 < 0 )
  {
    if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 1) != 0 )
    {
      McTemplateK0jq_EtwWriteTransfer(v20, PoolConfigWriteFailure, 0, a1 + 108, v24);
      v7 = (SDB_CONFIG **)(a1 + 48);
    }
    goto LABEL_9;
  }
  v25 = MEMORY[0xFFFFF78000000014] - v22;
  if ( v47 )
  {
    SP_POOL::PauseTasks((SP_POOL *)a1);
    v7 = (SDB_CONFIG **)(a1 + 48);
  }
  SP_POOL::Commit((SP_POOL *)a1);
  v34 = MEMORY[0xFFFFF78000000014];
  SP_POOL::CommitDevices(v35, v38, v37);
  v6 = MEMORY[0xFFFFF78000000014] - v34;
  if ( v47 )
    SP_POOL::ResumeTasks((SP_POOL *)a1);
  SP_POOL::PostCommitDevices((SP_POOL *)a1, v38, v37);
  SDB_CONFIG::CommitRecords(*v7);
  if ( v36[0] && *(_BYTE *)(a1 + 65) && !SDB_CONFIG::IsWritable(*v7) )
    SP_POOL::Offline(a1, 3);
LABEL_11:
  if ( v38 )
    SC_ENV_ALLOCATOR::operator delete[](v38);
  if ( v18 == -1070071804 )
    SP_POOL::Offline(a1, 3);
  if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 0x40) != 0 )
  {
    v26 = SDB_CONFIG::Sequence(*(SDB_CONFIG **)(a1 + 48));
    v28 = IoGetActivityIdThread(v27);
    McTemplateK0jqqxxxxx_EtwWriteTransfer(v39, v29, v28, a1 + 108, a3, v18, v26, v39, v40, v25, v6);
  }
  if ( (unsigned int)dword_14007F050 > 5 && (unsigned __int8)tlgKeywordOn(&dword_14007F050, 0x400000000000LL) )
  {
    v43 = v32 - v41;
    v44 = v32 - v41;
    v45 = v32 - v41;
    v41 = 0x1000000;
    LODWORD(v39) = v18;
    LODWORD(v40) = a3;
    v42 = a1 + 108;
    v46 = 1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      v30,
      (unsigned int)&dword_1400756D4,
      v31,
      (unsigned int)&v46,
      (__int64)&v45,
      (__int64)&v44,
      (__int64)&v43,
      (__int64)&v42,
      (__int64)&v40,
      (__int64)&v39,
      (__int64)&v41);
  }
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x14009e3e4  push    rbp
0x14009e3e6  push    rbx
0x14009e3e7  push    rsi
0x14009e3e8  push    rdi
0x14009e3e9  push    r12
0x14009e3eb  push    r13
0x14009e3ed  push    r14
0x14009e3ef  push    r15
0x14009e3f1  lea     rbp, [rsp-0Fh]
0x14009e3f6  sub     rsp, 0B8h
0x14009e3fd  xor     r12d, r12d
0x14009e400  lea     rdi, [rcx+30h]
0x14009e404  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 40h
0x14009e40b  mov     r14, r9
0x14009e40e  mov     r13d, r8d
0x14009e411  mov     [rbp+47h+var_88], r12
0x14009e415  mov     r15b, dl
0x14009e418  mov     [rbp+47h+var_8C], r12d
0x14009e41c  mov     rsi, rcx
0x14009e41f  mov     [rbp+47h+var_80], r12
0x14009e423  mov     [rbp+47h+var_78], r12
0x14009e427  mov     [rbp+47h+var_90], r12b
0x14009e42b  mov     [rbp+47h+arg_0], r12b
0x14009e42f  jz      short loc_14009E465
0x14009e431  mov     rcx, [rdi]; this
0x14009e434  call    ?Sequence@SDB_CONFIG@@QEAA_KXZ; SDB_CONFIG::Sequence(void)
0x14009e439  mov     rbx, rax
0x14009e43c  call    cs:__imp_IoGetActivityIdThread
0x14009e443  nop     dword ptr [rax+rax+00h]
0x14009e448  lea     r9, [rsi+6Ch]
0x14009e44c  mov     [rsp+0F0h+var_C8], rbx
0x14009e451  mov     r8, rax
0x14009e454  mov     dword ptr [rsp+0F0h+var_D0], r13d
0x14009e459  lea     rdx, PoolTransactionStart
0x14009e460  call    McTemplateK0jqx_EtwWriteTransfer
0x14009e465  mov     rax, 0FFFFF78000000014h
0x14009e46f  mov     rbx, [rax]
0x14009e472  mov     rcx, [rdi]; this
0x14009e475  mov     [rbp+47h+var_70], rbx
0x14009e479  call    ?BeginTransaction@SDB_CONFIG@@QEAAXXZ; SDB_CONFIG::BeginTransaction(void)
0x14009e47e  mov     rcx, [rbp+47h+arg_28]
0x14009e482  mov     r8, r14
0x14009e485  mov     r9, [rbp+47h+arg_20]
0x14009e489  mov     edx, r13d
0x14009e48c  mov     [rsp+0F0h+var_D0], rcx
0x14009e491  mov     rcx, rsi
0x14009e494  call    ?DispatchTransaction@SP_POOL@@AEAAJW4TRANSACTION_CODE@@PEAX11@Z; SP_POOL::DispatchTransaction(TRANSACTION_CODE,void *,void *,void *)
0x14009e499  mov     r14d, eax
0x14009e49c  test    eax, eax
0x14009e49e  js      loc_14009E542
0x14009e4a4  test    r15b, r15b
0x14009e4a7  jnz     loc_14009E542
0x14009e4ad  mov     rax, ds:0FFFFF78000000014h
0x14009e4b7  lea     r9, [rbp+47h+var_8C]; unsigned int *
0x14009e4bb  sub     rax, rbx
0x14009e4be  lea     r8, [rbp+47h+var_88]; struct _SP_DEVICE_CHANGE **
0x14009e4c2  mov     r15, 0FFFFF78000000014h
0x14009e4cc  mov     [rbp+47h+var_80], rax
0x14009e4d0  lea     rdx, [rbp+47h+arg_0]; unsigned __int8 *
0x14009e4d4  mov     rcx, rsi; this
0x14009e4d7  mov     rbx, [r15]
0x14009e4da  call    ?PrepareCommit@SP_POOL@@AEAAJPEAEPEAPEAU_SP_DEVICE_CHANGE@@PEAK@Z; SP_POOL::PrepareCommit(uchar *,_SP_DEVICE_CHANGE * *,ulong *)
0x14009e4df  mov     r14d, eax
0x14009e4e2  test    eax, eax
0x14009e4e4  js      short loc_14009E535
0x14009e4e6  mov     rax, ds:0FFFFF78000000014h
0x14009e4f0  lea     rdx, [rbp+47h+var_90]; unsigned __int8 *
0x14009e4f4  sub     rax, rbx
0x14009e4f7  mov     rbx, [r15]
0x14009e4fa  mov     rcx, [rdi]; this
0x14009e4fd  mov     [rbp+47h+var_78], rax
0x14009e501  call    ?CommitTransaction@SDB_CONFIG@@QEAAJPEAE@Z; SDB_CONFIG::CommitTransaction(uchar *)
0x14009e506  mov     r14d, eax
0x14009e509  test    eax, eax
0x14009e50b  jns     loc_14009E698
0x14009e511  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 1
0x14009e518  jz      short loc_14009E535
0x14009e51a  lea     r9, [rsi+6Ch]
0x14009e51e  mov     dword ptr [rsp+0F0h+var_D0], eax
0x14009e522  xor     r8d, r8d
0x14009e525  lea     rdx, PoolConfigWriteFailure
0x14009e52c  call    McTemplateK0jq_EtwWriteTransfer
0x14009e531  lea     rdi, [rsi+30h]
0x14009e535  mov     r8d, [rbp+47h+var_8C]; unsigned int
0x14009e539  mov     rdx, [rbp+47h+var_88]; struct _SP_DEVICE_CHANGE *
0x14009e53d  call    ?AbortDevices@SP_POOL@@AEAAXPEAU_SP_DEVICE_CHANGE@@K@Z; SP_POOL::AbortDevices(_SP_DEVICE_CHANGE *,ulong)
0x14009e542  mov     rcx, [rdi]; this
0x14009e545  mov     r15, r12
0x14009e548  call    ?AbortRecords@SDB_CONFIG@@QEAAXXZ; SDB_CONFIG::AbortRecords(void)
0x14009e54d  mov     rcx, [rbp+47h+var_88]; void *
0x14009e551  test    rcx, rcx
0x14009e554  jz      short loc_14009E55B
0x14009e556  call    ??_VSC_ENV_ALLOCATOR@@SAXPEAX@Z; SC_ENV_ALLOCATOR::operator delete[](void *)
0x14009e55b  cmp     r14d, 0C0380004h
0x14009e562  jnz     short loc_14009E574
0x14009e564  mov     r8b, 1
0x14009e567  mov     edx, 3
0x14009e56c  mov     rcx, rsi
0x14009e56f  call    ?Offline@SP_POOL@@QEAAXW4_SP_POOL_READ_ONLY_REASON@@E@Z; SP_POOL::Offline(_SP_POOL_READ_ONLY_REASON,uchar)
0x14009e574  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 40h
0x14009e57b  lea     rdi, [rsi+6Ch]
0x14009e57f  jz      short loc_14009E5CF
0x14009e581  mov     rcx, [rsi+30h]; this
0x14009e585  call    ?Sequence@SDB_CONFIG@@QEAA_KXZ; SDB_CONFIG::Sequence(void)
0x14009e58a  mov     rbx, rax
0x14009e58d  call    cs:__imp_IoGetActivityIdThread
0x14009e594  nop     dword ptr [rax+rax+00h]
0x14009e599  mov     rcx, [rbp+47h+var_78]
0x14009e59d  mov     r9, rdi
0x14009e5a0  mov     [rsp+0F0h+var_A0], r12
0x14009e5a5  mov     r8, rax
0x14009e5a8  mov     [rsp+0F0h+var_A8], r15
0x14009e5ad  mov     [rsp+0F0h+var_B0], rcx
0x14009e5b2  mov     rcx, [rbp+47h+var_80]
0x14009e5b6  mov     [rsp+0F0h+var_B8], rcx
0x14009e5bb  mov     [rsp+0F0h+var_C0], rbx
0x14009e5c0  mov     dword ptr [rsp+0F0h+var_C8], r14d
0x14009e5c5  mov     dword ptr [rsp+0F0h+var_D0], r13d
0x14009e5ca  call    McTemplateK0jqqxxxxx_EtwWriteTransfer
0x14009e5cf  mov     rax, 0FFFFF78000000014h
0x14009e5d9  mov     r9, [rax]
0x14009e5dc  mov     eax, cs:dword_14007F050
0x14009e5e2  cmp     eax, 5
0x14009e5e5  jbe     loc_14009E680
0x14009e5eb  mov     rdx, 400000000000h
0x14009e5f5  lea     rcx, dword_14007F050
0x14009e5fc  call    _tlgKeywordOn
0x14009e601  test    al, al
0x14009e603  jz      short loc_14009E680
0x14009e605  sub     r9, [rbp+47h+var_70]
0x14009e609  lea     rax, [rbp+47h+var_70]
0x14009e60d  mov     [rbp+47h+var_60], r9
0x14009e611  mov     [rsp+0F0h+var_A0], rax
0x14009e616  lea     rdx, dword_1400756D4
0x14009e61d  lea     rax, [rbp+47h+var_80]
0x14009e621  mov     [rbp+47h+var_58], r9
0x14009e625  mov     [rsp+0F0h+var_A8], rax
0x14009e62a  lea     rax, [rbp+47h+var_78]
0x14009e62e  mov     [rsp+0F0h+var_B0], rax
0x14009e633  lea     rax, [rbp+47h+var_68]
0x14009e637  mov     [rsp+0F0h+var_B8], rax
0x14009e63c  lea     rax, [rbp+47h+var_60]
0x14009e640  mov     [rsp+0F0h+var_C0], rax
0x14009e645  lea     rax, [rbp+47h+var_58]
0x14009e649  mov     [rsp+0F0h+var_C8], rax
0x14009e64e  lea     rax, [rbp+47h+var_50]
0x14009e652  mov     [rbp+47h+var_50], r9
0x14009e656  lea     r9, [rbp+47h+var_48]
0x14009e65a  mov     [rsp+0F0h+var_D0], rax
0x14009e65f  mov     [rbp+47h+var_70], 1000000h
0x14009e667  mov     dword ptr [rbp+47h+var_80], r14d
0x14009e66b  mov     dword ptr [rbp+47h+var_78], r13d
0x14009e66f  mov     [rbp+47h+var_68], rdi
0x14009e673  mov     [rbp+47h+var_48], 1
0x14009e67b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U1@U1@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U3@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBX1IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteAgg@@YAJ011I2@ZPEBX@@SAJPEBU_tlgProvider_t@@PEBX1AEBU?$_tlgWrapperByVal@$07@@222AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@42@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,void const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x14009e680  mov     eax, r14d
0x14009e683  add     rsp, 0B8h
0x14009e68a  pop     r15
0x14009e68c  pop     r14
0x14009e68e  pop     r13
0x14009e690  pop     r12
0x14009e692  pop     rdi
0x14009e693  pop     rsi
0x14009e694  pop     rbx
0x14009e695  pop     rbp
0x14009e696  retn
0x14009e698  mov     rax, ds:0FFFFF78000000014h
0x14009e6a2  mov     r15, rax
0x14009e6a5  sub     r15, rbx
0x14009e6a8  cmp     [rbp+47h+arg_0], r12b
0x14009e6ac  jz      short loc_14009E6BA
0x14009e6ae  mov     rcx, rsi; this
0x14009e6b1  call    ?PauseTasks@SP_POOL@@QEAAXXZ; SP_POOL::PauseTasks(void)
0x14009e6b6  lea     rdi, [rsi+30h]
0x14009e6ba  mov     rcx, rsi; this
0x14009e6bd  call    ?Commit@SP_POOL@@QEAAXXZ; SP_POOL::Commit(void)
0x14009e6c2  mov     rbx, 0FFFFF78000000014h
0x14009e6cc  mov     rbx, [rbx]
0x14009e6cf  mov     r8d, [rbp+47h+var_8C]; unsigned int
0x14009e6d3  mov     rdx, [rbp+47h+var_88]; struct _SP_DEVICE_CHANGE *
0x14009e6d7  call    ?CommitDevices@SP_POOL@@AEAAXPEAU_SP_DEVICE_CHANGE@@K@Z; SP_POOL::CommitDevices(_SP_DEVICE_CHANGE *,ulong)
0x14009e6dc  mov     rax, ds:0FFFFF78000000014h
0x14009e6e6  mov     r12, rax
0x14009e6e9  sub     r12, rbx
0x14009e6ec  cmp     [rbp+47h+arg_0], 0
0x14009e6f0  jz      short loc_14009E6FA
0x14009e6f2  mov     rcx, rsi; this
0x14009e6f5  call    ?ResumeTasks@SP_POOL@@QEAAXXZ; SP_POOL::ResumeTasks(void)
0x14009e6fa  mov     r8d, [rbp+47h+var_8C]; unsigned int
0x14009e6fe  mov     rcx, rsi; this
0x14009e701  mov     rdx, [rbp+47h+var_88]; struct _SP_DEVICE_CHANGE *
0x14009e705  call    ?PostCommitDevices@SP_POOL@@AEAAXPEAU_SP_DEVICE_CHANGE@@K@Z; SP_POOL::PostCommitDevices(_SP_DEVICE_CHANGE *,ulong)
0x14009e70a  mov     rcx, [rdi]; this
0x14009e70d  call    ?CommitRecords@SDB_CONFIG@@QEAAXXZ; SDB_CONFIG::CommitRecords(void)
0x14009e712  cmp     [rbp+47h+var_90], 0
0x14009e716  jz      loc_14009E54D
0x14009e71c  cmp     byte ptr [rsi+41h], 0
0x14009e720  jz      loc_14009E54D
0x14009e726  mov     rcx, [rdi]; this
0x14009e729  call    ?IsWritable@SDB_CONFIG@@QEAAEXZ; SDB_CONFIG::IsWritable(void)
0x14009e72e  test    al, al
0x14009e730  jnz     loc_14009E54D
0x14009e736  xor     r8d, r8d
0x14009e739  mov     rcx, rsi
0x14009e73c  lea     edx, [r8+3]
0x14009e740  call    ?Offline@SP_POOL@@QEAAXW4_SP_POOL_READ_ONLY_REASON@@E@Z; SP_POOL::Offline(_SP_POOL_READ_ONLY_REASON,uchar)
0x14009e745  jmp     loc_14009E54D
```
