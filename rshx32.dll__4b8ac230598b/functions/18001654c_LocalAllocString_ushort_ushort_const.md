# LocalAllocString(ushort * *,ushort const *)

- ea: `0x18001654c`
- end: `0x1800165de`
- name: `?LocalAllocString@@YAJPEAPEAGPEBG@Z`
- size: `146`
- prototype: `__int64 __fastcall(unsigned __int16 **, const unsigned __int16 *)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180005b00`
- `0x180005fd4`
- `0x180009c90`
- `0x18000a0e4`
- `0x18000a440`
- `0x18000ca38`

## callees

- `0x18001654c`
- `0x180016614`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180016593`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180016593`

## pseudocode

```c
__int64 __fastcall LocalAllocString(unsigned __int16 **a1, const unsigned __int16 *a2)
{
  unsigned __int64 v2; // rdi
  unsigned __int64 v5; // rsi
  unsigned __int16 *v6; // rax
  unsigned int v7; // ebx
  unsigned __int16 **v9; // [rsp+20h] [rbp-38h]
  unsigned __int64 *v10; // [rsp+28h] [rbp-30h]
  unsigned int v11; // [rsp+30h] [rbp-28h]

  v2 = -1;
  do
    ++v2;
  while ( a2[v2] );
  v5 = v2 + 1;
  *a1 = 0;
  if ( v2 + 1 >= v2 && is_mul_ok(v5, 2u) )
  {
    v6 = (unsigned __int16 *)LocalAlloc(0, 2 * v5);
    *a1 = v6;
    v7 = v6 == 0 ? 0x8007000E : 0;
    if ( v6 )
      StringCchCopyNExW(v6, v2 + 1, a2, v2, v9, v10, v11);
  }
  else
  {
    return (unsigned int)-2147024362;
  }
  return v7;
}

```

## disassembly

```asm
0x18001654c  mov     [rsp+arg_8], rbx
0x180016551  mov     [rsp+arg_10], rbp
0x180016556  push    rsi
0x180016557  push    rdi
0x180016558  push    r14
0x18001655a  sub     rsp, 40h
0x18001655e  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180016562  mov     rbp, rdx
0x180016565  xor     r14d, r14d
0x180016568  mov     rbx, rcx
0x18001656b  inc     rdi
0x18001656e  cmp     [rdx+rdi*2], r14w
0x180016573  jnz     short loc_18001656B
0x180016575  lea     rsi, [rdi+1]
0x180016579  mov     [rcx], r14
0x18001657c  cmp     rsi, rdi
0x18001657f  jb      short loc_1800165C4
0x180016581  mov     eax, 2
0x180016586  mul     rsi
0x180016589  test    rdx, rdx
0x18001658c  jnz     short loc_1800165C4
0x18001658e  mov     rdx, rax; uBytes
0x180016591  xor     ecx, ecx; uFlags
0x180016593  call    cs:__imp_LocalAlloc
0x180016599  mov     [rbx], rax
0x18001659c  mov     rcx, rax
0x18001659f  neg     rcx
0x1800165a2  sbb     ebx, ebx
0x1800165a4  not     ebx
0x1800165a6  and     ebx, 8007000Eh
0x1800165ac  test    rax, rax
0x1800165af  jz      short loc_1800165C9
0x1800165b1  mov     r9, rdi; unsigned __int64
0x1800165b4  mov     r8, rbp; unsigned __int16 *
0x1800165b7  mov     rdx, rsi; unsigned __int64
0x1800165ba  mov     rcx, rax; unsigned __int16 *
0x1800165bd  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x1800165c2  jmp     short loc_1800165C9
0x1800165c4  mov     ebx, 80070216h
0x1800165c9  mov     rbp, [rsp+58h+arg_10]
0x1800165ce  mov     eax, ebx
0x1800165d0  mov     rbx, [rsp+58h+arg_8]
0x1800165d5  add     rsp, 40h
0x1800165d9  pop     r14
0x1800165db  pop     rdi
0x1800165dc  pop     rsi
0x1800165dd  retn
```
