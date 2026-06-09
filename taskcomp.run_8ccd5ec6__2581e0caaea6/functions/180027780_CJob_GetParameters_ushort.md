# CJob::GetParameters(ushort * *)

- ea: `0x180027780`
- end: `0x1800277f3`
- name: `?GetParameters@CJob@@UEAAJPEAPEAG@Z`
- size: `115`
- prototype: `__int64 __fastcall(CJob *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800040c0`
- `0x180027780`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800277b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800277b6`

## pseudocode

```c
__int64 __fastcall CJob::GetParameters(CJob *this, unsigned __int16 **a2)
{
  const unsigned __int16 *v2; // rdi
  __int64 v4; // rbx
  __int64 v5; // rcx
  unsigned __int16 *v6; // rax

  v2 = (const unsigned __int16 *)&wszEmpty;
  if ( *((_QWORD *)this + 15) )
    v2 = (const unsigned __int16 *)*((_QWORD *)this + 15);
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
0x180027780  push    rbx
0x180027782  push    rbp
0x180027783  push    rsi
0x180027784  push    rdi
0x180027785  sub     rsp, 28h
0x180027789  xor     ebp, ebp
0x18002778b  lea     rdi, ?wszEmpty@@3PAGA; ushort near * wszEmpty
0x180027792  cmp     [rcx+78h], rbp
0x180027796  mov     rsi, rdx
0x180027799  cmovnz  rdi, [rcx+78h]
0x18002779e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800277a2  mov     rcx, rbx
0x1800277a5  inc     rcx
0x1800277a8  cmp     [rdi+rcx*2], bp
0x1800277ac  jnz     short loc_1800277A5
0x1800277ae  lea     rcx, ds:2[rcx*2]; cb
0x1800277b6  call    cs:__imp_CoTaskMemAlloc
0x1800277bd  nop     dword ptr [rax+rax+00h]
0x1800277c2  mov     [rsi], rax
0x1800277c5  test    rax, rax
0x1800277c8  jnz     short loc_1800277D1
0x1800277ca  mov     eax, 8007000Eh
0x1800277cf  jmp     short loc_1800277E9
0x1800277d1  inc     rbx
0x1800277d4  cmp     [rdi+rbx*2], bp
0x1800277d8  jnz     short loc_1800277D1
0x1800277da  lea     rdx, [rbx+1]; unsigned __int64
0x1800277de  mov     r8, rdi; unsigned __int16 *
0x1800277e1  mov     rcx, rax; unsigned __int16 *
0x1800277e4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800277e9  add     rsp, 28h
0x1800277ed  pop     rdi
0x1800277ee  pop     rsi
0x1800277ef  pop     rbp
0x1800277f0  pop     rbx
0x1800277f1  retn
```
