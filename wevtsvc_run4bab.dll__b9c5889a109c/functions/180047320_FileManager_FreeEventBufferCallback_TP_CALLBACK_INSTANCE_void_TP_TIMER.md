# FileManager::FreeEventBufferCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x180047320`
- end: `0x180047450`
- name: `?FreeEventBufferCallback@FileManager@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `304`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180046938`
- `0x180047320`
- `0x180047458`
- `0x18008c9d8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x180047333`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x180047333`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180047414`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180047414`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180047363`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800473f7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180047363`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800473f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800473ac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004741e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800473ac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004741e`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180047347`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180047347`

## pseudocode

```c
void __fastcall FileManager::FreeEventBufferCallback(
        PTP_CALLBACK_INSTANCE Instance,
        RTL_SRWLOCK *Context,
        PTP_TIMER Timer)
{
  unsigned __int64 v4; // rbp
  __int64 *Ptr; // rbx
  __int64 *v6; // rsi
  PVOID v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rcx
  _QWORD *v10; // rbx
  _QWORD *v11; // rdi
  PVOID v12; // rdx
  __int64 v13; // r8
  struct _TP_TIMER *v14; // rcx
  __int64 v15; // rcx
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-38h] BYREF
  unsigned __int64 UnbiasedTime; // [rsp+68h] [rbp+10h] BYREF
  __int64 v18; // [rsp+78h] [rbp+20h] BYREF

  CallbackMayRunLong(Instance);
  UnbiasedTime = 0;
  QueryUnbiasedInterruptTime(&UnbiasedTime);
  v4 = UnbiasedTime - 3000000000u;
  AcquireSRWLockExclusive(Context + 3);
  Ptr = (__int64 *)Context->Ptr;
  v6 = (__int64 *)Context[1].Ptr;
  while ( Ptr != v6 )
  {
    v18 = *Ptr;
    if ( *(_QWORD *)(v18 + 768) <= v4
      && !(unsigned __int8)utl::vector<wmi::AutoRef<File>,utl::allocator<wmi::AutoRef<File>>>::emplace_back<File * &,0>(
                             &Context[6],
                             &v18) )
    {
      v7 = Context[6].Ptr;
      v8 = (char *)Context[7].Ptr - (char *)v7;
      Context[7].Ptr = v7;
      utl::_RangeDestroyApc<utl::allocator<wmi::AutoRef<File>>>(v15, v7, v8 >> 3);
      break;
    }
    ++Ptr;
  }
  ReleaseSRWLockExclusive(Context + 3);
  v10 = Context[6].Ptr;
  v11 = Context[7].Ptr;
  while ( v10 != v11 )
    File::FullFlush(*v10++, 1);
  v12 = Context[6].Ptr;
  v13 = (char *)Context[7].Ptr - (char *)v12;
  Context[7].Ptr = v12;
  utl::_RangeDestroyApc<utl::allocator<wmi::AutoRef<File>>>(v9, v12, v13 >> 3);
  pftDueTime = (struct _FILETIME)-1500000000LL;
  AcquireSRWLockExclusive(Context + 4);
  v14 = (struct _TP_TIMER *)Context[5].Ptr;
  if ( v14 )
    SetThreadpoolTimer(v14, &pftDueTime, 0, 0xBB8u);
  ReleaseSRWLockExclusive(Context + 4);
}

```

## disassembly

```asm
0x180047320  mov     [rsp+arg_0], rbx
0x180047325  push    rbp
0x180047326  push    rsi
0x180047327  push    rdi
0x180047328  push    r14
0x18004732a  push    r15
0x18004732c  sub     rsp, 30h
0x180047330  mov     r14, rdx
0x180047333  call    cs:__imp_CallbackMayRunLong
0x180047339  lea     rcx, [rsp+58h+UnbiasedTime]; UnbiasedTime
0x18004733e  mov     [rsp+58h+UnbiasedTime], 0
0x180047347  call    cs:__imp_QueryUnbiasedInterruptTime
0x18004734d  mov     rbp, [rsp+58h+UnbiasedTime]
0x180047352  mov     rcx, 0FFFFFFFF4D2FA200h
0x18004735c  add     rbp, rcx
0x18004735f  lea     rcx, [r14+18h]; SRWLock
0x180047363  call    cs:__imp_AcquireSRWLockExclusive
0x180047369  mov     rbx, [r14]
0x18004736c  mov     rsi, [r14+8]
0x180047370  cmp     rbx, rsi
0x180047373  jz      short loc_1800473A8
0x180047375  mov     rax, [rbx]
0x180047378  mov     [rsp+58h+arg_18], rax
0x18004737d  cmp     [rax+300h], rbp
0x180047384  jbe     loc_180047435
0x18004738a  add     rbx, 8
0x18004738e  jmp     short loc_180047370
0x180047390  mov     rdx, [r14+30h]
0x180047394  mov     r8, [r14+38h]
0x180047398  sub     r8, rdx
0x18004739b  mov     [r14+38h], rdx
0x18004739f  sar     r8, 3
0x1800473a3  call    ??$_RangeDestroyApc@V?$allocator@V?$AutoRef@VFile@@@wmi@@@utl@@@utl@@YAXAEAV?$allocator@V?$AutoRef@VFile@@@wmi@@@0@PEAV?$AutoRef@VFile@@@wmi@@_K@Z; utl::_RangeDestroyApc<utl::allocator<wmi::AutoRef<File>>>(utl::allocator<wmi::AutoRef<File>> &,wmi::AutoRef<File> *,unsigned __int64)
0x1800473a8  lea     rcx, [r14+18h]; SRWLock
0x1800473ac  call    cs:__imp_ReleaseSRWLockExclusive
0x1800473b2  mov     rbx, [r14+30h]
0x1800473b6  mov     rdi, [r14+38h]
0x1800473ba  cmp     rbx, rdi
0x1800473bd  jz      short loc_1800473D2
0x1800473bf  mov     rcx, [rbx]
0x1800473c2  mov     edx, 1
0x1800473c7  call    ?FullFlush@File@@QEAAKW4FlushType@@@Z; File::FullFlush(FlushType)
0x1800473cc  add     rbx, 8
0x1800473d0  jmp     short loc_1800473BA
0x1800473d2  mov     rdx, [r14+30h]
0x1800473d6  mov     r8, [r14+38h]
0x1800473da  sub     r8, rdx
0x1800473dd  mov     [r14+38h], rdx
0x1800473e1  sar     r8, 3
0x1800473e5  call    ??$_RangeDestroyApc@V?$allocator@V?$AutoRef@VFile@@@wmi@@@utl@@@utl@@YAXAEAV?$allocator@V?$AutoRef@VFile@@@wmi@@@0@PEAV?$AutoRef@VFile@@@wmi@@_K@Z; utl::_RangeDestroyApc<utl::allocator<wmi::AutoRef<File>>>(utl::allocator<wmi::AutoRef<File>> &,wmi::AutoRef<File> *,unsigned __int64)
0x1800473ea  lea     rcx, [r14+20h]; SRWLock
0x1800473ee  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], 0FFFFFFFFA697D100h
0x1800473f7  call    cs:__imp_AcquireSRWLockExclusive
0x1800473fd  mov     rcx, [r14+28h]; pti
0x180047401  test    rcx, rcx
0x180047404  jz      short loc_18004741A
0x180047406  mov     r9d, 0BB8h; msWindowLength
0x18004740c  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x180047411  xor     r8d, r8d; msPeriod
0x180047414  call    cs:__imp_SetThreadpoolTimer
0x18004741a  lea     rcx, [r14+20h]; SRWLock
0x18004741e  call    cs:__imp_ReleaseSRWLockExclusive
0x180047424  mov     rbx, [rsp+58h+arg_0]
0x180047429  add     rsp, 30h
0x18004742d  pop     r15
0x18004742f  pop     r14
0x180047431  pop     rdi
0x180047432  pop     rsi
0x180047433  pop     rbp
0x180047434  retn
0x180047435  lea     rdx, [rsp+58h+arg_18]
0x18004743a  lea     rcx, [r14+30h]
0x18004743e  call    ??$emplace_back@AEAPEAVFile@@$0A@@?$vector@V?$AutoRef@VFile@@@wmi@@V?$allocator@V?$AutoRef@VFile@@@wmi@@@utl@@@utl@@QEAA_NAEAPEAVFile@@@Z; utl::vector<wmi::AutoRef<File>,utl::allocator<wmi::AutoRef<File>>>::emplace_back<File * &,0>(File * &)
0x180047443  test    al, al
0x180047445  jnz     loc_18004738A
0x18004744b  jmp     loc_180047390
```
