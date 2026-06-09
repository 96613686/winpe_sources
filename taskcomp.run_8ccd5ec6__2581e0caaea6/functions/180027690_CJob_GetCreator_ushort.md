# CJob::GetCreator(ushort * *)

- ea: `0x180027690`
- end: `0x180027708`
- name: `?GetCreator@CJob@@UEAAJPEAPEAG@Z`
- size: `120`
- prototype: `__int64 __fastcall(CJob *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800040c0`
- `0x180027690`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800276cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800276cb`

## pseudocode

```c
__int64 __fastcall CJob::GetCreator(CJob *this, unsigned __int16 **a2)
{
  const unsigned __int16 *v2; // rdi
  __int64 v4; // rbx
  __int64 v5; // rcx
  unsigned __int16 *v6; // rax

  v2 = (const unsigned __int16 *)&wszEmpty;
  if ( *((_QWORD *)this + 17) )
    v2 = (const unsigned __int16 *)*((_QWORD *)this + 17);
  v4 = -1;
  v5 = -1;
  do
    ++v5;
  while ( v2[v5] );
  v6 = (unsigned __int16 *)CoTaskMemAlloc(2 * v5 + 2);
  *a2 = v6;
  if ( !v6 )
    return 2147942414LL;
  do
    ++v4;
  while ( v2[v4] );
  return StringCchCopyW(v6, v4 + 1, v2);
}

```

## disassembly

```asm
0x180027690  push    rbx
0x180027692  push    rbp
0x180027693  push    rsi
0x180027694  push    rdi
0x180027695  sub     rsp, 28h
0x180027699  mov     rax, [rcx+88h]
0x1800276a0  lea     rdi, ?wszEmpty@@3PAGA; ushort near * wszEmpty
0x1800276a7  xor     ebp, ebp
0x1800276a9  mov     rsi, rdx
0x1800276ac  test    rax, rax
0x1800276af  cmovnz  rdi, rax
0x1800276b3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800276b7  mov     rcx, rbx
0x1800276ba  inc     rcx
0x1800276bd  cmp     [rdi+rcx*2], bp
0x1800276c1  jnz     short loc_1800276BA
0x1800276c3  lea     rcx, ds:2[rcx*2]; cb
0x1800276cb  call    cs:__imp_CoTaskMemAlloc
0x1800276d2  nop     dword ptr [rax+rax+00h]
0x1800276d7  mov     [rsi], rax
0x1800276da  test    rax, rax
0x1800276dd  jnz     short loc_1800276E6
0x1800276df  mov     eax, 8007000Eh
0x1800276e4  jmp     short loc_1800276FE
0x1800276e6  inc     rbx
0x1800276e9  cmp     [rdi+rbx*2], bp
0x1800276ed  jnz     short loc_1800276E6
0x1800276ef  lea     rdx, [rbx+1]; unsigned __int64
0x1800276f3  mov     r8, rdi; unsigned __int16 *
0x1800276f6  mov     rcx, rax; unsigned __int16 *
0x1800276f9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800276fe  add     rsp, 28h
0x180027702  pop     rdi
0x180027703  pop     rsi
0x180027704  pop     rbp
0x180027705  pop     rbx
0x180027706  retn
```
