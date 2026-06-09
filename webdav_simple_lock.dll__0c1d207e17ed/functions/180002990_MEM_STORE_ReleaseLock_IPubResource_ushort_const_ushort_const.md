# MEM_STORE::ReleaseLock(IPubResource *,ushort const *,ushort const *)

- ea: `0x180002990`
- end: `0x180002a88`
- name: `?ReleaseLock@MEM_STORE@@UEAAJPEAVIPubResource@@PEBG1@Z`
- size: `248`
- prototype: `__int64 __fastcall(MEM_STORE *__hidden this, struct IPubResource *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180002364`
- `0x180002990`
- `0x180004010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180002a26`
- `msvcrt!_wcsicmp` at `0x180002a26`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180002a6c`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180002a6c`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800029ad`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800029ad`

## pseudocode

```c
__int64 __fastcall MEM_STORE::ReleaseLock(
        MEM_STORE *this,
        struct IPubResource *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  struct MEM_LOCK *LockByToken; // rax
  struct MEM_LOCK *v9; // rdi
  unsigned int v10; // ebx
  __int64 v11; // rax
  int v12; // edx
  int v13; // ecx
  const wchar_t *v14; // rbx
  const wchar_t *v15; // rax
  struct MEM_LOCK **v16; // rdx
  struct MEM_LOCK **v17; // r8

  CReaderWriterLock3::WriteLock((MEM_STORE *)((char *)this + 88));
  LockByToken = MEM_STORE::FindLockByToken(this, a4);
  v9 = LockByToken;
  if ( LockByToken )
  {
    v11 = (*(__int64 (__fastcall **)(struct MEM_LOCK *))(*(_QWORD *)LockByToken + 48LL))(LockByToken) - (_QWORD)a3;
    do
    {
      v12 = *(const unsigned __int16 *)((char *)a3 + v11);
      v13 = *a3 - v12;
      if ( v13 )
        break;
      ++a3;
    }
    while ( v12 );
    if ( v13 )
    {
      v10 = -1917904592;
    }
    else
    {
      v14 = (const wchar_t *)(*(__int64 (__fastcall **)(struct MEM_LOCK *))(*(_QWORD *)v9 + 32LL))(v9);
      v15 = (const wchar_t *)(**(__int64 (__fastcall ***)(struct IPubResource *))a2)(a2);
      if ( _wcsicmp(v15, v14) )
      {
        v10 = -1917904496;
      }
      else
      {
        v16 = (struct MEM_LOCK **)*((_QWORD *)v9 + 1);
        if ( v16[1] != (struct MEM_LOCK *)((char *)v9 + 8)
          || (v17 = (struct MEM_LOCK **)*((_QWORD *)v9 + 2), *v17 != (struct MEM_LOCK *)((char *)v9 + 8)) )
        {
          __fastfail(3u);
        }
        *v17 = (struct MEM_LOCK *)v16;
        v16[1] = (struct MEM_LOCK *)v17;
        v10 = 0;
        (*(void (__fastcall **)(struct MEM_LOCK *))(*(_QWORD *)v9 + 16LL))(v9);
        --*((_DWORD *)this + 26);
      }
    }
  }
  else
  {
    v10 = -1917904640;
  }
  CReaderWriterLock3::WriteUnlock((MEM_STORE *)((char *)this + 88));
  return v10;
}

```

## disassembly

```asm
0x180002990  push    rbx
0x180002992  push    rbp
0x180002993  push    rsi
0x180002994  push    rdi
0x180002995  push    r14
0x180002997  push    r15
0x180002999  sub     rsp, 28h
0x18000299d  mov     rbp, rcx
0x1800029a0  mov     rbx, r9
0x1800029a3  add     rcx, 58h ; 'X'
0x1800029a7  mov     rsi, r8
0x1800029aa  mov     r15, rdx
0x1800029ad  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x1800029b3  mov     rdx, rbx; unsigned __int16 *
0x1800029b6  mov     rcx, rbp; this
0x1800029b9  call    ?FindLockByToken@MEM_STORE@@AEAAPEAVMEM_LOCK@@PEBG@Z; MEM_STORE::FindLockByToken(ushort const *)
0x1800029be  mov     rdi, rax
0x1800029c1  test    rax, rax
0x1800029c4  jnz     short loc_1800029D0
0x1800029c6  mov     ebx, 8DAF1900h
0x1800029cb  jmp     loc_180002A68
0x1800029d0  mov     rax, [rax]
0x1800029d3  mov     rcx, rdi
0x1800029d6  mov     rax, [rax+30h]
0x1800029da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029df  sub     rax, rsi
0x1800029e2  movzx   ecx, word ptr [rsi]
0x1800029e5  movzx   edx, word ptr [rsi+rax]
0x1800029e9  sub     ecx, edx
0x1800029eb  jnz     short loc_1800029F5
0x1800029ed  add     rsi, 2
0x1800029f1  test    edx, edx
0x1800029f3  jnz     short loc_1800029E2
0x1800029f5  test    ecx, ecx
0x1800029f7  jz      short loc_180002A00
0x1800029f9  mov     ebx, 8DAF1930h
0x1800029fe  jmp     short loc_180002A68
0x180002a00  mov     rax, [rdi]
0x180002a03  mov     rcx, rdi
0x180002a06  mov     rax, [rax+20h]
0x180002a0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a0f  mov     rcx, [r15]
0x180002a12  mov     rbx, rax
0x180002a15  mov     rax, [rcx]
0x180002a18  mov     rcx, r15
0x180002a1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a20  mov     rdx, rbx; String2
0x180002a23  mov     rcx, rax; String1
0x180002a26  call    cs:__imp__wcsicmp
0x180002a2c  test    eax, eax
0x180002a2e  jz      short loc_180002A37
0x180002a30  mov     ebx, 8DAF1990h
0x180002a35  jmp     short loc_180002A68
0x180002a37  lea     rax, [rdi+8]
0x180002a3b  mov     rdx, [rax]
0x180002a3e  cmp     [rdx+8], rax
0x180002a42  jnz     short loc_180002A81
0x180002a44  mov     r8, [rax+8]
0x180002a48  cmp     [r8], rax
0x180002a4b  jnz     short loc_180002A81
0x180002a4d  mov     [r8], rdx
0x180002a50  mov     rcx, rdi
0x180002a53  mov     [rdx+8], r8
0x180002a57  xor     ebx, ebx
0x180002a59  mov     rdx, [rdi]
0x180002a5c  mov     rax, [rdx+10h]
0x180002a60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a65  dec     dword ptr [rbp+68h]
0x180002a68  lea     rcx, [rbp+58h]
0x180002a6c  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180002a72  mov     eax, ebx
0x180002a74  add     rsp, 28h
0x180002a78  pop     r15
0x180002a7a  pop     r14
0x180002a7c  pop     rdi
0x180002a7d  pop     rsi
0x180002a7e  pop     rbp
0x180002a7f  pop     rbx
0x180002a80  retn
0x180002a81  mov     ecx, 3
0x180002a86  int     29h; Win8: RtlFailFast(ecx)
```
