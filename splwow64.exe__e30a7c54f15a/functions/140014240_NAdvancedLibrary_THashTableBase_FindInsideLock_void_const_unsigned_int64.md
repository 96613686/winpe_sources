# NAdvancedLibrary::THashTableBase::FindInsideLock(void const *,unsigned __int64)

- ea: `0x140014240`
- end: `0x1400142b2`
- name: `?FindInsideLock@THashTableBase@NAdvancedLibrary@@AEBAPEAVTHashElementBase@2@PEBX_K@Z`
- size: `114`
- prototype: `struct NAdvancedLibrary::THashElementBase *__fastcall(NAdvancedLibrary::THashTableBase *__hidden this, const void *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1400141ac`
- `0x140014394`

## callees

- `0x140014240`
- `0x140016010`

## pseudocode

```c
struct NAdvancedLibrary::THashElementBase *__fastcall NAdvancedLibrary::THashTableBase::FindInsideLock(
        NAdvancedLibrary::THashTableBase *this,
        const void *a2,
        unsigned __int64 a3)
{
  __int64 i; // rdi
  __int64 v7; // rbx
  __int64 v8; // rax

  for ( i = *(_QWORD *)(*((_QWORD *)this + 1) + 8 * (a3 % *((unsigned int *)this + 10))); i; i = *(_QWORD *)(i + 16) )
  {
    if ( *(_QWORD *)(i + 24) == a3 )
    {
      v7 = *(_QWORD *)this;
      v8 = (*(__int64 (__fastcall **)(NAdvancedLibrary::THashTableBase *, __int64))(*(_QWORD *)this + 80LL))(this, i);
      if ( !(*(unsigned int (__fastcall **)(NAdvancedLibrary::THashTableBase *, const void *, __int64))(v7 + 96))(
              this,
              a2,
              v8) )
        break;
    }
  }
  return (struct NAdvancedLibrary::THashElementBase *)i;
}

```

## disassembly

```asm
0x140014240  push    rbx
0x140014242  push    rbp
0x140014243  push    rsi
0x140014244  push    rdi
0x140014245  push    r14
0x140014247  sub     rsp, 20h
0x14001424b  mov     r9d, [rcx+28h]
0x14001424f  mov     r14, rdx
0x140014252  xor     edx, edx
0x140014254  mov     rax, r8
0x140014257  div     r9
0x14001425a  mov     rax, [rcx+8]
0x14001425e  mov     rbp, r8
0x140014261  mov     r9d, edx
0x140014264  mov     rsi, rcx
0x140014267  mov     rdi, [rax+r9*8]
0x14001426b  jmp     short loc_14001429F
0x14001426d  cmp     [rdi+18h], rbp
0x140014271  jnz     short loc_14001429B
0x140014273  mov     rbx, [rsi]
0x140014276  mov     rdx, rdi
0x140014279  mov     rcx, rsi
0x14001427c  mov     rax, [rbx+50h]
0x140014280  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014285  mov     r8, rax
0x140014288  mov     rdx, r14
0x14001428b  mov     rax, [rbx+60h]
0x14001428f  mov     rcx, rsi
0x140014292  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014297  test    eax, eax
0x140014299  jz      short loc_1400142A4
0x14001429b  mov     rdi, [rdi+10h]
0x14001429f  test    rdi, rdi
0x1400142a2  jnz     short loc_14001426D
0x1400142a4  mov     rax, rdi
0x1400142a7  add     rsp, 20h
0x1400142ab  pop     r14
0x1400142ad  pop     rdi
0x1400142ae  pop     rsi
0x1400142af  pop     rbp
0x1400142b0  pop     rbx
0x1400142b1  retn
```
