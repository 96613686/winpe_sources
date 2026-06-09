# File::WriteRecord(BinXmlReader &)

- ea: `0x1800335f4`
- end: `0x1800337c4`
- name: `?WriteRecord@File@@QEAAKAEAVBinXmlReader@@@Z`
- size: `464`
- prototype: `unsigned int __fastcall(File *__hidden this, struct BinXmlReader *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180027570`

## callees

- `0x180030e4c`
- `0x1800310b4`
- `0x180031f14`
- `0x180032a7c`
- `0x18003316c`
- `0x1800335f4`
- `0x18003c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180033652`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180033652`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003375f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003375f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall File::WriteRecord(File *this, struct BinXmlReader *a2)
{
  void (__fastcall ***v5)(_QWORD, LPCWSTR, __int64); // r15
  unsigned int v6; // ebx
  __int64 v7; // rdx
  int v8; // r14d
  __int64 v9; // [rsp+38h] [rbp-40h] BYREF
  char v10; // [rsp+40h] [rbp-38h]
  __int64 v11; // [rsp+98h] [rbp+20h] BYREF

  if ( (*((_BYTE *)this + 825) & 4) != 0 )
    return 19;
  v5 = (void (__fastcall ***)(_QWORD, LPCWSTR, __int64))*((_QWORD *)a2 + 22);
  ((void (__fastcall *)(void (__fastcall ***)(_QWORD, LPCWSTR, __int64), __int64 *))(*v5)[3])(v5, &v11);
  v9 = (__int64)this + 664;
  AcquireSRWLockExclusive((PSRWLOCK)this + 83);
  v10 = 1;
  while ( *((_BYTE *)this + 838) )
    utl::condition_variable_any::wait<utl::unique_lock<utl::shared_mutex>>((PCONDITION_VARIABLE)this + 93);
  v6 = File::WriteOneEventToBuffer((LPCWSTR *)this, a2, v5, v11, (const char *)&v9);
  if ( v6 != 111 )
    goto LABEL_16;
  v7 = *(_QWORD *)(*((_QWORD *)this + 20) + 16LL);
  if ( v7 == -1 )
  {
    v6 = 87;
    goto LABEL_16;
  }
  v6 = File::GrowFileInPlace(this, v7 + 1, (__int64)&v9);
  if ( !v6 )
    goto LABEL_15;
  if ( (*((_BYTE *)this + 825) & 1) != 0 )
  {
LABEL_18:
    v6 = 1502;
    goto LABEL_16;
  }
  if ( (*((_BYTE *)this + 825) & 2) != 0 )
  {
    SetLastError(0x5DEu);
    goto LABEL_18;
  }
  if ( v6 == 1502 || v6 == 112 )
  {
    v6 = File::OverwriteOldestChunk(this, *(_QWORD *)(*((_QWORD *)this + 20) + 16LL) + 1LL);
    if ( !v6 )
    {
LABEL_15:
      v8 = *((_DWORD *)this + 204);
      v6 = File::WriteOneEventToBuffer((LPCWSTR *)this, a2, v5, v11, (const char *)&v9);
      *((_DWORD *)this + 204) = v8;
    }
  }
LABEL_16:
  utl::unique_lock<utl::shared_mutex>::~unique_lock<utl::shared_mutex>(&v9);
  if ( v6 && *((_BYTE *)this + 835) )
  {
    if ( *((_BYTE *)this + 834) )
      return 111;
  }
  return v6;
}

```

## disassembly

```asm
0x1800335f4  mov     [rsp+arg_8], rbx
0x1800335f9  mov     [rsp+arg_0], rcx
0x1800335fe  push    rsi
0x1800335ff  push    rdi
0x180033600  push    r13
0x180033602  push    r14
0x180033604  push    r15
0x180033606  sub     rsp, 50h
0x18003360a  mov     r13, rdx
0x18003360d  mov     rdi, rcx
0x180033610  test    byte ptr [rcx+339h], 4
0x180033617  jz      short loc_180033623
0x180033619  mov     eax, 13h
0x18003361e  jmp     loc_1800337AF
0x180033623  mov     r15, [rdx+0B0h]
0x18003362a  mov     rax, [r15]
0x18003362d  lea     rdx, [rsp+78h+arg_18]
0x180033635  mov     rcx, r15
0x180033638  mov     rax, [rax+18h]
0x18003363c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033641  lea     rcx, [rdi+298h]; SRWLock
0x180033648  mov     [rsp+78h+var_40], rcx
0x18003364d  mov     [rsp+78h+var_38], 0
0x180033652  call    cs:__imp_AcquireSRWLockExclusive
0x180033658  mov     [rsp+78h+var_38], 1
0x18003365d  cmp     byte ptr [rdi+346h], 0
0x180033664  jz      short loc_180033679
0x180033666  lea     rdx, [rsp+78h+var_40]
0x18003366b  lea     rcx, [rdi+2E8h]; ConditionVariable
0x180033672  call    ??$wait@V?$unique_lock@Vshared_mutex@utl@@@utl@@@condition_variable_any@utl@@QEAAXAEAV?$unique_lock@Vshared_mutex@utl@@@1@@Z; utl::condition_variable_any::wait<utl::unique_lock<utl::shared_mutex>>(utl::unique_lock<utl::shared_mutex> &)
0x180033677  jmp     short loc_18003365D
0x180033679  lea     rax, [rsp+78h+var_40]
0x18003367e  mov     [rsp+78h+var_58], rax; __int64
0x180033683  mov     r9, [rsp+78h+arg_18]
0x18003368b  mov     r8, r15
0x18003368e  mov     rdx, r13
0x180033691  mov     rcx, rdi; this
0x180033694  call    ?WriteOneEventToBuffer@File@@AEAAKAEAVBinXmlReader@@PEAVAbstractPublishedEventRecord@@U_FILETIME@@AEAV?$unique_lock@Vshared_mutex@utl@@@utl@@@Z; File::WriteOneEventToBuffer(BinXmlReader &,AbstractPublishedEventRecord *,_FILETIME,utl::unique_lock<utl::shared_mutex> &)
0x180033699  mov     ebx, eax
0x18003369b  mov     esi, 6Fh ; 'o'
0x1800336a0  cmp     eax, esi
0x1800336a2  jnz     loc_18003374D
0x1800336a8  mov     rax, [rdi+0A0h]
0x1800336af  mov     rdx, [rax+10h]
0x1800336b3  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x1800336b7  jnz     short loc_1800336C1
0x1800336b9  lea     ebx, [rsi-18h]
0x1800336bc  jmp     loc_18003374D
0x1800336c1  inc     rdx; unsigned __int64
0x1800336c4  lea     r8, [rsp+78h+var_40]; __int64
0x1800336c9  mov     rcx, rdi; this
0x1800336cc  call    ?GrowFileInPlace@File@@AEAAK_KAEAV?$unique_lock@Vshared_mutex@utl@@@utl@@@Z; File::GrowFileInPlace(unsigned __int64,utl::unique_lock<utl::shared_mutex> &)
0x1800336d1  mov     ebx, eax
0x1800336d3  test    eax, eax
0x1800336d5  jz      short loc_18003371D
0x1800336d7  mov     cl, [rdi+339h]
0x1800336dd  mov     al, cl
0x1800336df  and     al, 1
0x1800336e1  mov     byte ptr [rsp+78h+arg_10], al
0x1800336e8  jnz     short loc_180033765
0x1800336ea  test    cl, 2
0x1800336ed  jnz     short loc_18003375A
0x1800336ef  cmp     ebx, 5DEh
0x1800336f5  jz      short loc_1800336FC
0x1800336f7  cmp     ebx, 70h ; 'p'
0x1800336fa  jnz     short loc_18003374D
0x1800336fc  mov     rax, [rdi+0A0h]
0x180033703  mov     rdx, [rax+10h]
0x180033707  inc     rdx; unsigned __int64
0x18003370a  lea     r8, [rsp+78h+var_40]
0x18003370f  mov     rcx, rdi; this
0x180033712  call    ?OverwriteOldestChunk@File@@AEAAK_KAEAV?$unique_lock@Vshared_mutex@utl@@@utl@@@Z; File::OverwriteOldestChunk(unsigned __int64,utl::unique_lock<utl::shared_mutex> &)
0x180033717  mov     ebx, eax
0x180033719  test    eax, eax
0x18003371b  jnz     short loc_18003374D
0x18003371d  mov     r14d, [rdi+330h]
0x180033724  lea     rax, [rsp+78h+var_40]
0x180033729  mov     [rsp+78h+var_58], rax; __int64
0x18003372e  mov     r9, [rsp+78h+arg_18]
0x180033736  mov     r8, r15
0x180033739  mov     rdx, r13
0x18003373c  mov     rcx, rdi; this
0x18003373f  call    ?WriteOneEventToBuffer@File@@AEAAKAEAVBinXmlReader@@PEAVAbstractPublishedEventRecord@@U_FILETIME@@AEAV?$unique_lock@Vshared_mutex@utl@@@utl@@@Z; File::WriteOneEventToBuffer(BinXmlReader &,AbstractPublishedEventRecord *,_FILETIME,utl::unique_lock<utl::shared_mutex> &)
0x180033744  mov     ebx, eax
0x180033746  mov     [rdi+330h], r14d
0x18003374d  lea     rcx, [rsp+78h+var_40]
0x180033752  call    ??1?$unique_lock@Vshared_mutex@utl@@@utl@@QEAA@XZ; utl::unique_lock<utl::shared_mutex>::~unique_lock<utl::shared_mutex>(void)
0x180033757  nop
0x180033758  jmp     short loc_180033780
0x18003375a  mov     ecx, 5DEh; dwErrCode
0x18003375f  call    cs:__imp_SetLastError
0x180033765  mov     ebx, 5DEh
0x18003376a  jmp     short loc_18003374D
0x18003376c  mov     esi, 6Fh ; 'o'
0x180033771  mov     rdi, [rsp+78h+arg_0]
0x180033779  mov     ebx, [rsp+78h+arg_10]
0x180033780  test    ebx, ebx
0x180033782  jz      short loc_1800337AD
0x180033784  jmp     short loc_18003379A
0x180033786  mov     esi, 6Fh ; 'o'
0x18003378b  mov     rdi, [rsp+78h+arg_0]
0x180033793  mov     ebx, [rsp+78h+arg_10]
0x18003379a  cmp     byte ptr [rdi+343h], 0
0x1800337a1  jz      short loc_1800337AD
0x1800337a3  cmp     byte ptr [rdi+342h], 0
0x1800337aa  cmovnz  ebx, esi
0x1800337ad  mov     eax, ebx
0x1800337af  mov     rbx, [rsp+78h+arg_8]
0x1800337b7  add     rsp, 50h
0x1800337bb  pop     r15
0x1800337bd  pop     r14
0x1800337bf  pop     r13
0x1800337c1  pop     rdi
0x1800337c2  pop     rsi
0x1800337c3  retn
```
