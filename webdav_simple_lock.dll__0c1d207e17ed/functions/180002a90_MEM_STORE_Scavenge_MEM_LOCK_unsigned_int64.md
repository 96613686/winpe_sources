# MEM_STORE::Scavenge(MEM_LOCK *,unsigned __int64)

- ea: `0x180002a90`
- end: `0x180002b0b`
- name: `?Scavenge@MEM_STORE@@AEAAHPEAVMEM_LOCK@@_K@Z`
- size: `123`
- prototype: `__int64 __fastcall(MEM_STORE *__hidden this, struct MEM_LOCK *, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002094`
- `0x180002270`
- `0x180002364`
- `0x1800025c0`

## callees

- `0x180002a90`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall MEM_STORE::Scavenge(MEM_STORE *this, struct MEM_LOCK *a2, unsigned __int64 a3)
{
  struct MEM_LOCK **v5; // rdx
  struct MEM_LOCK **v6; // rcx

  if ( (*(__int64 (__fastcall **)(struct MEM_LOCK *))(*(_QWORD *)a2 + 64LL))(a2) > a3 )
    return 0;
  v5 = (struct MEM_LOCK **)*((_QWORD *)a2 + 1);
  if ( v5[1] != (struct MEM_LOCK *)((char *)a2 + 8)
    || (v6 = (struct MEM_LOCK **)*((_QWORD *)a2 + 2), *v6 != (struct MEM_LOCK *)((char *)a2 + 8)) )
  {
    __fastfail(3u);
  }
  *v6 = (struct MEM_LOCK *)v5;
  v5[1] = (struct MEM_LOCK *)v6;
  (*(void (__fastcall **)(struct MEM_LOCK *))(*(_QWORD *)a2 + 16LL))(a2);
  --*((_DWORD *)this + 26);
  return 1;
}

```

## disassembly

```asm
0x180002a90  mov     [rsp+arg_0], rbx
0x180002a95  mov     [rsp+arg_8], rsi
0x180002a9a  push    rdi
0x180002a9b  sub     rsp, 20h
0x180002a9f  mov     rax, [rdx]
0x180002aa2  mov     rsi, rcx
0x180002aa5  mov     rcx, rdx
0x180002aa8  mov     rbx, r8
0x180002aab  mov     rdi, rdx
0x180002aae  mov     rax, [rax+40h]
0x180002ab2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ab7  cmp     rax, rbx
0x180002aba  ja      short loc_180002AF9
0x180002abc  lea     rax, [rdi+8]
0x180002ac0  mov     rdx, [rax]
0x180002ac3  cmp     [rdx+8], rax
0x180002ac7  jnz     short loc_180002AF2
0x180002ac9  mov     rcx, [rax+8]
0x180002acd  cmp     [rcx], rax
0x180002ad0  jnz     short loc_180002AF2
0x180002ad2  mov     [rcx], rdx
0x180002ad5  mov     [rdx+8], rcx
0x180002ad9  mov     rcx, rdi
0x180002adc  mov     rax, [rdi]
0x180002adf  mov     rax, [rax+10h]
0x180002ae3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ae8  dec     dword ptr [rsi+68h]
0x180002aeb  mov     eax, 1
0x180002af0  jmp     short loc_180002AFB
0x180002af2  mov     ecx, 3
0x180002af7  int     29h; Win8: RtlFailFast(ecx)
0x180002af9  xor     eax, eax
0x180002afb  mov     rbx, [rsp+28h+arg_0]
0x180002b00  mov     rsi, [rsp+28h+arg_8]
0x180002b05  add     rsp, 20h
0x180002b09  pop     rdi
0x180002b0a  retn
```
