# MEM_STORE::DestroyLocksForUriPath(IPubResource *)

- ea: `0x180002270`
- end: `0x18000235d`
- name: `?DestroyLocksForUriPath@MEM_STORE@@UEAAJPEAVIPubResource@@@Z`
- size: `237`
- prototype: `__int64 __fastcall(MEM_STORE *__hidden this, struct IPubResource *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180002270`
- `0x180002a90`
- `0x180004010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800022f6`
- `msvcrt!_wcsicmp` at `0x1800022f6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002299`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002299`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180002337`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180002337`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800022b4`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800022b4`

## pseudocode

```c
__int64 __fastcall MEM_STORE::DestroyLocksForUriPath(MEM_STORE *this, struct IPubResource *a2)
{
  const wchar_t *v4; // r12
  MEM_STORE *v5; // rbx
  char *v6; // rdi
  MEM_STORE *v7; // r15
  const wchar_t *v8; // rax
  MEM_STORE *v9; // rax
  MEM_STORE **v10; // rcx
  unsigned __int64 v12; // [rsp+50h] [rbp+8h] BYREF

  v12 = 0;
  GetSystemTimeAsFileTime((LPFILETIME)&v12);
  v4 = (const wchar_t *)(**(__int64 (__fastcall ***)(struct IPubResource *))a2)(a2);
  CReaderWriterLock3::WriteLock((MEM_STORE *)((char *)this + 88));
  v5 = (MEM_STORE *)*((_QWORD *)this + 9);
  if ( v5 != (MEM_STORE *)((char *)this + 72) )
  {
    do
    {
      v6 = (char *)v5 - 8;
      v7 = *(MEM_STORE **)v5;
      if ( !(unsigned int)MEM_STORE::Scavenge(this, (MEM_STORE *)((char *)v5 - 8), v12) )
      {
        v8 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 32LL))((__int64)v5 - 8);
        if ( !_wcsicmp(v4, v8) )
        {
          v9 = *(MEM_STORE **)v5;
          if ( *(MEM_STORE **)(*(_QWORD *)v5 + 8LL) != v5 || (v10 = (MEM_STORE **)*((_QWORD *)v5 + 1), *v10 != v5) )
            __fastfail(3u);
          *v10 = v9;
          *((_QWORD *)v9 + 1) = v10;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))((__int64)v5 - 8);
          --*((_DWORD *)this + 26);
        }
      }
      v5 = v7;
    }
    while ( v7 != (MEM_STORE *)((char *)this + 72) );
  }
  CReaderWriterLock3::WriteUnlock((MEM_STORE *)((char *)this + 88));
  return 0;
}

```

## disassembly

```asm
0x180002270  mov     rax, rsp
0x180002273  mov     [rax+10h], rbx
0x180002277  mov     [rax+18h], rbp
0x18000227b  push    rsi
0x18000227c  push    rdi
0x18000227d  push    r12
0x18000227f  push    r14
0x180002281  push    r15
0x180002283  sub     rsp, 20h
0x180002287  mov     rsi, rcx
0x18000228a  mov     qword ptr [rax+8], 0
0x180002292  lea     rcx, [rax+8]; lpSystemTimeAsFileTime
0x180002296  mov     rbx, rdx
0x180002299  call    cs:__imp_GetSystemTimeAsFileTime
0x18000229f  mov     rax, [rbx]
0x1800022a2  mov     rcx, rbx
0x1800022a5  mov     rax, [rax]
0x1800022a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022ad  lea     rcx, [rsi+58h]
0x1800022b1  mov     r12, rax
0x1800022b4  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x1800022ba  lea     r14, [rsi+48h]
0x1800022be  mov     rbx, [r14]
0x1800022c1  cmp     rbx, r14
0x1800022c4  jz      short loc_180002333
0x1800022c6  mov     r8, [rsp+48h+arg_0]; unsigned __int64
0x1800022cb  lea     rdi, [rbx-8]
0x1800022cf  mov     r15, [rbx]
0x1800022d2  mov     rdx, rdi; struct MEM_LOCK *
0x1800022d5  mov     rcx, rsi; this
0x1800022d8  call    ?Scavenge@MEM_STORE@@AEAAHPEAVMEM_LOCK@@_K@Z; MEM_STORE::Scavenge(MEM_LOCK *,unsigned __int64)
0x1800022dd  test    eax, eax
0x1800022df  jnz     short loc_18000232B
0x1800022e1  mov     rax, [rdi]
0x1800022e4  mov     rcx, rdi
0x1800022e7  mov     rax, [rax+20h]
0x1800022eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022f0  mov     rdx, rax; String2
0x1800022f3  mov     rcx, r12; String1
0x1800022f6  call    cs:__imp__wcsicmp
0x1800022fc  test    eax, eax
0x1800022fe  jnz     short loc_18000232B
0x180002300  mov     rax, [rbx]
0x180002303  cmp     [rax+8], rbx
0x180002307  jnz     short loc_180002356
0x180002309  mov     rcx, [rbx+8]
0x18000230d  cmp     [rcx], rbx
0x180002310  jnz     short loc_180002356
0x180002312  mov     [rcx], rax
0x180002315  mov     [rax+8], rcx
0x180002319  mov     rcx, rdi
0x18000231c  mov     rax, [rdi]
0x18000231f  mov     rax, [rax+10h]
0x180002323  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002328  dec     dword ptr [rsi+68h]
0x18000232b  mov     rbx, r15
0x18000232e  cmp     r15, r14
0x180002331  jnz     short loc_1800022C6
0x180002333  lea     rcx, [rsi+58h]
0x180002337  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000233d  mov     rbx, [rsp+48h+arg_8]
0x180002342  xor     eax, eax
0x180002344  mov     rbp, [rsp+48h+arg_10]
0x180002349  add     rsp, 20h
0x18000234d  pop     r15
0x18000234f  pop     r14
0x180002351  pop     r12
0x180002353  pop     rdi
0x180002354  pop     rsi
0x180002355  retn
0x180002356  mov     ecx, 3
0x18000235b  int     29h; Win8: RtlFailFast(ecx)
```
