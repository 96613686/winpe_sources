# Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)

- ea: `0x1400063b4`
- end: `0x1400064c3`
- name: `?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z`
- size: `271`
- prototype: `bool __fastcall(Microsoft::WRL::Details *this, struct Microsoft::WRL::Details::ModuleBase *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000381c`
- `0x140003a60`
- `0x14000678c`

## callees

- `0x1400063b4`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140006459`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140006470`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140006459`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140006470`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000643c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000643c`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x140006479`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x140006479`

## pseudocode

```c
bool __fastcall Microsoft::WRL::Details::TerminateMap(
        Microsoft::WRL::Details *this,
        struct Microsoft::WRL::Details::ModuleBase *a2,
        const unsigned __int16 *a3)
{
  char v3; // r15
  unsigned __int64 v5; // rbx
  unsigned __int64 v6; // r14
  RTL_SRWLOCK *v7; // rdi
  void **v8; // rax
  void *v9; // rbp
  PVOID v10; // rax

  v3 = (char)a3;
  v5 = (*(__int64 (__fastcall **)(Microsoft::WRL::Details *, struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)this + 32LL))(
         this,
         a2)
     + 8;
  v6 = (*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 48LL))(this);
  if ( v5 >= v6 )
    return (*(unsigned int (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 24LL))(this) == 0;
  while ( !*(_QWORD *)v5 )
  {
LABEL_12:
    v5 += 8LL;
    if ( v5 >= v6 )
      return (*(unsigned int (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 24LL))(this) == 0;
  }
  if ( !(*(unsigned int (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 24LL))(this) || v3 )
  {
    if ( **(_QWORD **)(*(_QWORD *)v5 + 24LL) )
    {
      v7 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 56LL))(this);
      AcquireSRWLockExclusive(v7);
      v8 = *(void ***)(*(_QWORD *)v5 + 24LL);
      v9 = *v8;
      if ( *v8 )
      {
        *v8 = 0;
        if ( v7 )
          ReleaseSRWLockExclusive(v7);
        v10 = DecodePointer(v9);
        (*(void (__fastcall **)(PVOID))(*(_QWORD *)v10 + 16LL))(v10);
      }
      else if ( v7 )
      {
        ReleaseSRWLockExclusive(v7);
      }
    }
    goto LABEL_12;
  }
  return 0;
}

```

## disassembly

```asm
0x1400063b4  push    rbx
0x1400063b6  push    rbp
0x1400063b7  push    rsi
0x1400063b8  push    rdi
0x1400063b9  push    r14
0x1400063bb  push    r15
0x1400063bd  sub     rsp, 28h
0x1400063c1  mov     rax, [rcx]
0x1400063c4  mov     r15b, r8b
0x1400063c7  mov     rsi, rcx
0x1400063ca  mov     rax, [rax+20h]
0x1400063ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400063d3  mov     rdx, [rsi]
0x1400063d6  mov     rcx, rsi
0x1400063d9  lea     rbx, [rax+8]
0x1400063dd  mov     rax, [rdx+30h]
0x1400063e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400063e6  mov     r14, rax
0x1400063e9  cmp     rbx, rax
0x1400063ec  jnb     loc_14000649E
0x1400063f2  cmp     qword ptr [rbx], 0
0x1400063f6  jz      loc_140006491
0x1400063fc  mov     rcx, [rsi]
0x1400063ff  mov     rax, [rcx+18h]
0x140006403  mov     rcx, rsi
0x140006406  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000640b  test    eax, eax
0x14000640d  jz      short loc_140006418
0x14000640f  test    r15b, r15b
0x140006412  jz      loc_1400064BF
0x140006418  mov     rax, [rbx]
0x14000641b  mov     rcx, [rax+18h]
0x14000641f  mov     rax, [rcx]
0x140006422  test    rax, rax
0x140006425  jz      short loc_140006491
0x140006427  mov     rax, [rsi]
0x14000642a  mov     rcx, rsi
0x14000642d  mov     rax, [rax+38h]
0x140006431  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006436  mov     rcx, rax; SRWLock
0x140006439  mov     rdi, rax
0x14000643c  call    cs:__imp_AcquireSRWLockExclusive
0x140006442  mov     rcx, [rbx]
0x140006445  mov     rax, [rcx+18h]
0x140006449  mov     rbp, [rax]
0x14000644c  test    rbp, rbp
0x14000644f  jnz     short loc_140006461
0x140006451  test    rdi, rdi
0x140006454  jz      short loc_140006491
0x140006456  mov     rcx, rdi; SRWLock
0x140006459  call    cs:__imp_ReleaseSRWLockExclusive
0x14000645f  jmp     short loc_140006491
0x140006461  mov     qword ptr [rax], 0
0x140006468  test    rdi, rdi
0x14000646b  jz      short loc_140006476
0x14000646d  mov     rcx, rdi; SRWLock
0x140006470  call    cs:__imp_ReleaseSRWLockExclusive
0x140006476  mov     rcx, rbp; Ptr
0x140006479  call    cs:__imp_DecodePointer
0x14000647f  mov     rdx, rax
0x140006482  mov     rcx, [rax]
0x140006485  mov     rax, [rcx+10h]
0x140006489  mov     rcx, rdx
0x14000648c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006491  add     rbx, 8
0x140006495  cmp     rbx, r14
0x140006498  jb      loc_1400063F2
0x14000649e  mov     rax, [rsi]
0x1400064a1  mov     rcx, rsi
0x1400064a4  mov     rax, [rax+18h]
0x1400064a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400064ad  test    eax, eax
0x1400064af  setz    al
0x1400064b2  add     rsp, 28h
0x1400064b6  pop     r15
0x1400064b8  pop     r14
0x1400064ba  pop     rdi
0x1400064bb  pop     rsi
0x1400064bc  pop     rbp
0x1400064bd  pop     rbx
0x1400064be  retn
0x1400064bf  xor     al, al
0x1400064c1  jmp     short loc_1400064B2
```
