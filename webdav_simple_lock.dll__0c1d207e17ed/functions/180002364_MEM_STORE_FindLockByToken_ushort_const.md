# MEM_STORE::FindLockByToken(ushort const *)

- ea: `0x180002364`
- end: `0x180002407`
- name: `?FindLockByToken@MEM_STORE@@AEAAPEAVMEM_LOCK@@PEBG@Z`
- size: `163`
- prototype: `struct MEM_LOCK *__fastcall(MEM_STORE *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180002780`
- `0x180002990`

## callees

- `0x180002364`
- `0x180002a90`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002389`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002389`

## pseudocode

```c
struct MEM_LOCK *__fastcall MEM_STORE::FindLockByToken(MEM_STORE *this, const unsigned __int16 *a2)
{
  MEM_STORE *v4; // rax
  char *v5; // rbx
  MEM_STORE *v6; // rbp
  __int64 v7; // rax
  const unsigned __int16 *v8; // rcx
  __int64 v9; // rax
  int v10; // r8d
  int v11; // edx
  unsigned __int64 v13; // [rsp+40h] [rbp+8h] BYREF

  v13 = 0;
  GetSystemTimeAsFileTime((LPFILETIME)&v13);
  v4 = (MEM_STORE *)*((_QWORD *)this + 9);
  if ( v4 == (MEM_STORE *)((char *)this + 72) )
    return 0;
  while ( 1 )
  {
    v5 = (char *)v4 - 8;
    v6 = *(MEM_STORE **)v4;
    if ( !(unsigned int)MEM_STORE::Scavenge(this, (MEM_STORE *)((char *)v4 - 8), v13) )
    {
      v7 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v5 + 24LL))(v5);
      v8 = a2;
      v9 = v7 - (_QWORD)a2;
      do
      {
        v10 = *(const unsigned __int16 *)((char *)v8 + v9);
        v11 = *v8 - v10;
        if ( v11 )
          break;
        ++v8;
      }
      while ( v10 );
      if ( !v11 )
        break;
    }
    v4 = v6;
    if ( v6 == (MEM_STORE *)((char *)this + 72) )
      return 0;
  }
  return (struct MEM_LOCK *)v5;
}

```

## disassembly

```asm
0x180002364  mov     rax, rsp
0x180002367  mov     [rax+10h], rbx
0x18000236b  mov     [rax+18h], rbp
0x18000236f  push    rsi
0x180002370  push    rdi
0x180002371  push    r14
0x180002373  sub     rsp, 20h
0x180002377  mov     rsi, rcx
0x18000237a  mov     qword ptr [rax+8], 0
0x180002382  lea     rcx, [rax+8]; lpSystemTimeAsFileTime
0x180002386  mov     r14, rdx
0x180002389  call    cs:__imp_GetSystemTimeAsFileTime
0x18000238f  lea     rdi, [rsi+48h]
0x180002393  mov     rax, [rdi]
0x180002396  cmp     rax, rdi
0x180002399  jz      short loc_1800023ED
0x18000239b  mov     r8, [rsp+38h+arg_0]; unsigned __int64
0x1800023a0  lea     rbx, [rax-8]
0x1800023a4  mov     rbp, [rax]
0x1800023a7  mov     rdx, rbx; struct MEM_LOCK *
0x1800023aa  mov     rcx, rsi; this
0x1800023ad  call    ?Scavenge@MEM_STORE@@AEAAHPEAVMEM_LOCK@@_K@Z; MEM_STORE::Scavenge(MEM_LOCK *,unsigned __int64)
0x1800023b2  test    eax, eax
0x1800023b4  jnz     short loc_1800023E5
0x1800023b6  mov     rax, [rbx]
0x1800023b9  mov     rcx, rbx
0x1800023bc  mov     rax, [rax+18h]
0x1800023c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023c5  mov     rcx, r14
0x1800023c8  sub     rax, r14
0x1800023cb  movzx   edx, word ptr [rcx]
0x1800023ce  movzx   r8d, word ptr [rcx+rax]
0x1800023d3  sub     edx, r8d
0x1800023d6  jnz     short loc_1800023E1
0x1800023d8  add     rcx, 2
0x1800023dc  test    r8d, r8d
0x1800023df  jnz     short loc_1800023CB
0x1800023e1  test    edx, edx
0x1800023e3  jz      short loc_180002402
0x1800023e5  mov     rax, rbp
0x1800023e8  cmp     rbp, rdi
0x1800023eb  jnz     short loc_18000239B
0x1800023ed  xor     eax, eax
0x1800023ef  mov     rbx, [rsp+38h+arg_8]
0x1800023f4  mov     rbp, [rsp+38h+arg_10]
0x1800023f9  add     rsp, 20h
0x1800023fd  pop     r14
0x1800023ff  pop     rdi
0x180002400  pop     rsi
0x180002401  retn
0x180002402  mov     rax, rbx
0x180002405  jmp     short loc_1800023EF
```
