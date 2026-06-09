# CJob::GetComment(ushort * *)

- ea: `0x180027610`
- end: `0x180027688`
- name: `?GetComment@CJob@@UEAAJPEAPEAG@Z`
- size: `120`
- prototype: `__int64 __fastcall(CJob *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800040c0`
- `0x180027610`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002764b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002764b`

## pseudocode

```c
__int64 __fastcall CJob::GetComment(CJob *this, unsigned __int16 **a2)
{
  const unsigned __int16 *v2; // rdi
  __int64 v4; // rbx
  __int64 v5; // rcx
  unsigned __int16 *v6; // rax

  v2 = (const unsigned __int16 *)&wszEmpty;
  if ( *((_QWORD *)this + 18) )
    v2 = (const unsigned __int16 *)*((_QWORD *)this + 18);
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
0x180027610  push    rbx
0x180027612  push    rbp
0x180027613  push    rsi
0x180027614  push    rdi
0x180027615  sub     rsp, 28h
0x180027619  mov     rax, [rcx+90h]
0x180027620  lea     rdi, ?wszEmpty@@3PAGA; ushort near * wszEmpty
0x180027627  xor     ebp, ebp
0x180027629  mov     rsi, rdx
0x18002762c  test    rax, rax
0x18002762f  cmovnz  rdi, rax
0x180027633  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180027637  mov     rcx, rbx
0x18002763a  inc     rcx
0x18002763d  cmp     [rdi+rcx*2], bp
0x180027641  jnz     short loc_18002763A
0x180027643  lea     rcx, ds:2[rcx*2]; cb
0x18002764b  call    cs:__imp_CoTaskMemAlloc
0x180027652  nop     dword ptr [rax+rax+00h]
0x180027657  mov     [rsi], rax
0x18002765a  test    rax, rax
0x18002765d  jnz     short loc_180027666
0x18002765f  mov     eax, 8007000Eh
0x180027664  jmp     short loc_18002767E
0x180027666  inc     rbx
0x180027669  cmp     [rdi+rbx*2], bp
0x18002766d  jnz     short loc_180027666
0x18002766f  lea     rdx, [rbx+1]; unsigned __int64
0x180027673  mov     r8, rdi; unsigned __int16 *
0x180027676  mov     rcx, rax; unsigned __int16 *
0x180027679  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002767e  add     rsp, 28h
0x180027682  pop     rdi
0x180027683  pop     rsi
0x180027684  pop     rbp
0x180027685  pop     rbx
0x180027686  retn
```
