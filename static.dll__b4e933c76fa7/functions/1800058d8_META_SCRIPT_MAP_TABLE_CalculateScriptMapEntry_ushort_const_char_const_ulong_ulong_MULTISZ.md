# META_SCRIPT_MAP_TABLE::CalculateScriptMapEntry(ushort const *,char const *,ulong,ulong *,MULTISZ *)

- ea: `0x1800058d8`
- end: `0x1800059b3`
- name: `?CalculateScriptMapEntry@META_SCRIPT_MAP_TABLE@@QEAAPEAVMETA_SCRIPT_MAP_ENTRY@@PEBGPEBDKPEAKPEAVMULTISZ@@@Z`
- size: `219`
- prototype: `struct META_SCRIPT_MAP_ENTRY *__fastcall(META_SCRIPT_MAP_TABLE *this, const unsigned __int16 *, const char *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180002dd8`

## callees

- `0x1800058d8`
- `0x18000657c`
- `0x180007010`

## pseudocode

```c
struct META_SCRIPT_MAP_ENTRY *__fastcall META_SCRIPT_MAP_TABLE::CalculateScriptMapEntry(
        META_SCRIPT_MAP_TABLE *this,
        const unsigned __int16 *a2,
        const char *a3,
        unsigned int a4,
        unsigned int *a5)
{
  __int64 v6; // rdi
  char *v9; // rsi
  char *i; // rcx
  struct META_SCRIPT_MAP_ENTRY *v11; // rbx
  unsigned int v13; // [rsp+60h] [rbp+8h] BYREF

  v13 = 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v9 = (char *)this + 8;
  for ( i = (char *)*((_QWORD *)this + 1); ; i = (char *)*((_QWORD *)v11 + 1) )
  {
    v11 = (struct META_SCRIPT_MAP_ENTRY *)(i - 8);
    if ( i == v9 )
      v11 = 0;
    if ( !v11 )
      return 0;
    if ( !*(_WORD *)(*(__int64 (__fastcall **)(struct META_SCRIPT_MAP_ENTRY *, _QWORD))(*(_QWORD *)v11 + 24LL))(v11, 0) )
      (*(void (__fastcall **)(struct META_SCRIPT_MAP_ENTRY *))(*(_QWORD *)v11 + 80LL))(v11);
    (**(void (__fastcall ***)(struct META_SCRIPT_MAP_ENTRY *))v11)(v11);
    if ( ProcessScriptMapEntry(v11, a2, v6, a3, a4, &v13) )
      break;
  }
  if ( a5 )
    *a5 = v13;
  return v11;
}

```

## disassembly

```asm
0x1800058d8  mov     [rsp+arg_8], rbx
0x1800058dd  mov     [rsp+arg_10], rbp
0x1800058e2  push    rsi
0x1800058e3  push    rdi
0x1800058e4  push    r12
0x1800058e6  push    r14
0x1800058e8  push    r15
0x1800058ea  sub     rsp, 30h
0x1800058ee  xor     r12d, r12d
0x1800058f1  mov     r14d, r9d
0x1800058f4  mov     [rsp+58h+arg_0], r12d
0x1800058f9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800058fd  mov     r15, r8
0x180005900  mov     rbp, rdx
0x180005903  inc     rdi
0x180005906  cmp     [rdx+rdi*2], r12w
0x18000590b  jnz     short loc_180005903
0x18000590d  lea     rsi, [rcx+8]
0x180005911  mov     rcx, [rsi]
0x180005914  cmp     rcx, rsi
0x180005917  lea     rbx, [rcx-8]
0x18000591b  cmovz   rbx, r12
0x18000591f  test    rbx, rbx
0x180005922  jz      short loc_18000599A
0x180005924  mov     rax, [rbx]
0x180005927  xor     edx, edx
0x180005929  mov     rcx, rbx
0x18000592c  mov     rax, [rax+18h]
0x180005930  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005935  cmp     [rax], r12w
0x180005939  jnz     short loc_18000594A
0x18000593b  mov     rax, [rbx]
0x18000593e  mov     rcx, rbx
0x180005941  mov     rax, [rax+50h]
0x180005945  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000594a  mov     rax, [rbx]
0x18000594d  mov     rcx, rbx
0x180005950  mov     rax, [rax]
0x180005953  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005958  lea     rax, [rsp+58h+arg_0]
0x18000595d  mov     r9, r15; char *
0x180005960  mov     [rsp+58h+var_30], rax; unsigned int *
0x180005965  mov     r8d, edi; unsigned int
0x180005968  mov     rdx, rbp; unsigned __int16 *
0x18000596b  mov     [rsp+58h+var_38], r14d; unsigned int
0x180005970  mov     rcx, rbx; struct META_SCRIPT_MAP_ENTRY *
0x180005973  call    ?ProcessScriptMapEntry@@YAHPEAVMETA_SCRIPT_MAP_ENTRY@@PEBGKPEBDKPEAK@Z; ProcessScriptMapEntry(META_SCRIPT_MAP_ENTRY *,ushort const *,ulong,char const *,ulong,ulong *)
0x180005978  test    eax, eax
0x18000597a  jnz     short loc_180005982
0x18000597c  mov     rcx, [rbx+8]
0x180005980  jmp     short loc_180005914
0x180005982  mov     rax, [rsp+58h+arg_20]
0x18000598a  test    rax, rax
0x18000598d  jz      short loc_180005995
0x18000598f  mov     ecx, [rsp+58h+arg_0]
0x180005993  mov     [rax], ecx
0x180005995  mov     rax, rbx
0x180005998  jmp     short loc_18000599C
0x18000599a  xor     eax, eax
0x18000599c  mov     rbx, [rsp+58h+arg_8]
0x1800059a1  mov     rbp, [rsp+58h+arg_10]
0x1800059a6  add     rsp, 30h
0x1800059aa  pop     r15
0x1800059ac  pop     r14
0x1800059ae  pop     r12
0x1800059b0  pop     rdi
0x1800059b1  pop     rsi
0x1800059b2  retn
```
