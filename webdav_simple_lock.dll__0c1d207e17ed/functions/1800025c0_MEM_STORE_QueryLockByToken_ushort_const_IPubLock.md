# MEM_STORE::QueryLockByToken(ushort const *,IPubLock * *)

- ea: `0x1800025c0`
- end: `0x180002680`
- name: `?QueryLockByToken@MEM_STORE@@UEAAJPEBGPEAPEAVIPubLock@@@Z`
- size: `192`
- prototype: `_BOOL8 __fastcall(MEM_STORE *this, const unsigned __int16 *, struct IPubLock **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800025c0`
- `0x180002a90`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800025e6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800025e6`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180002661`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180002661`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800025f0`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800025f0`

## pseudocode

```c
_BOOL8 __fastcall MEM_STORE::QueryLockByToken(MEM_STORE *this, const unsigned __int16 *a2, struct IPubLock **a3)
{
  struct IPubLock *v4; // rbx
  MEM_STORE *v7; // rax
  struct IPubLock *v8; // rdi
  MEM_STORE *v9; // r15
  __int64 v10; // rax
  const unsigned __int16 *v11; // rcx
  __int64 v12; // rax
  int v13; // r8d
  int v14; // edx
  struct _FILETIME SystemTimeAsFileTime; // [rsp+70h] [rbp+8h] BYREF

  v4 = 0;
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  CReaderWriterLock3::WriteLock((MEM_STORE *)((char *)this + 88));
  v7 = (MEM_STORE *)*((_QWORD *)this + 9);
  if ( v7 != (MEM_STORE *)((char *)this + 72) )
  {
    while ( 1 )
    {
      v8 = (MEM_STORE *)((char *)v7 - 8);
      v9 = *(MEM_STORE **)v7;
      if ( !(unsigned int)MEM_STORE::Scavenge(this, (MEM_STORE *)((char *)v7 - 8), *(_QWORD *)&SystemTimeAsFileTime) )
      {
        v10 = (*(__int64 (__fastcall **)(struct IPubLock *))(*(_QWORD *)v8 + 24LL))(v8);
        v11 = a2;
        v12 = v10 - (_QWORD)a2;
        do
        {
          v13 = *(const unsigned __int16 *)((char *)v11 + v12);
          v14 = *v11 - v13;
          if ( v14 )
            break;
          ++v11;
        }
        while ( v13 );
        if ( !v14 )
          break;
      }
      v7 = v9;
      if ( v9 == (MEM_STORE *)((char *)this + 72) )
        goto LABEL_10;
    }
    v4 = v8;
  }
LABEL_10:
  *a3 = v4;
  CReaderWriterLock3::WriteUnlock((MEM_STORE *)((char *)this + 88));
  return v4 == 0;
}

```

## disassembly

```asm
0x1800025c0  push    rbx
0x1800025c2  push    rbp
0x1800025c3  push    rsi
0x1800025c4  push    rdi
0x1800025c5  push    r12
0x1800025c7  push    r13
0x1800025c9  push    r14
0x1800025cb  push    r15
0x1800025cd  sub     rsp, 28h
0x1800025d1  mov     rbp, rcx
0x1800025d4  xor     ebx, ebx
0x1800025d6  lea     rcx, [rsp+68h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800025db  mov     qword ptr [rsp+68h+SystemTimeAsFileTime.dwLowDateTime], rbx
0x1800025e0  mov     r12, r8
0x1800025e3  mov     r13, rdx
0x1800025e6  call    cs:__imp_GetSystemTimeAsFileTime
0x1800025ec  lea     rcx, [rbp+58h]
0x1800025f0  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x1800025f6  lea     rsi, [rbp+48h]
0x1800025fa  mov     rax, [rsi]
0x1800025fd  cmp     rax, rsi
0x180002600  jz      short loc_180002659
0x180002602  mov     r8, qword ptr [rsp+68h+SystemTimeAsFileTime.dwLowDateTime]; unsigned __int64
0x180002607  lea     rdi, [rax-8]
0x18000260b  mov     r15, [rax]
0x18000260e  mov     rdx, rdi; struct MEM_LOCK *
0x180002611  mov     rcx, rbp; this
0x180002614  call    ?Scavenge@MEM_STORE@@AEAAHPEAVMEM_LOCK@@_K@Z; MEM_STORE::Scavenge(MEM_LOCK *,unsigned __int64)
0x180002619  test    eax, eax
0x18000261b  jnz     short loc_18000264C
0x18000261d  mov     rax, [rdi]
0x180002620  mov     rcx, rdi
0x180002623  mov     rax, [rax+18h]
0x180002627  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000262c  mov     rcx, r13
0x18000262f  sub     rax, r13
0x180002632  movzx   edx, word ptr [rcx]
0x180002635  movzx   r8d, word ptr [rcx+rax]
0x18000263a  sub     edx, r8d
0x18000263d  jnz     short loc_180002648
0x18000263f  add     rcx, 2
0x180002643  test    r8d, r8d
0x180002646  jnz     short loc_180002632
0x180002648  test    edx, edx
0x18000264a  jz      short loc_180002656
0x18000264c  mov     rax, r15
0x18000264f  cmp     r15, rsi
0x180002652  jnz     short loc_180002602
0x180002654  jmp     short loc_180002659
0x180002656  mov     rbx, rdi
0x180002659  lea     rcx, [rbp+58h]
0x18000265d  mov     [r12], rbx
0x180002661  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180002667  xor     eax, eax
0x180002669  test    rbx, rbx
0x18000266c  setz    al
0x18000266f  add     rsp, 28h
0x180002673  pop     r15
0x180002675  pop     r14
0x180002677  pop     r13
0x180002679  pop     r12
0x18000267b  pop     rdi
0x18000267c  pop     rsi
0x18000267d  pop     rbp
0x18000267e  pop     rbx
0x18000267f  retn
```
