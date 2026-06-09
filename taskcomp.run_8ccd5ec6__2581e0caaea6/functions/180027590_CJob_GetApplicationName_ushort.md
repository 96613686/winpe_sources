# CJob::GetApplicationName(ushort * *)

- ea: `0x180027590`
- end: `0x180027603`
- name: `?GetApplicationName@CJob@@UEAAJPEAPEAG@Z`
- size: `115`
- prototype: `__int64 __fastcall(CJob *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800040c0`
- `0x180027590`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800275c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800275c6`

## pseudocode

```c
__int64 __fastcall CJob::GetApplicationName(CJob *this, unsigned __int16 **a2)
{
  const unsigned __int16 *v2; // rdi
  __int64 v4; // rbx
  __int64 v5; // rcx
  unsigned __int16 *v6; // rax

  v2 = (const unsigned __int16 *)&wszEmpty;
  if ( *((_QWORD *)this + 14) )
    v2 = (const unsigned __int16 *)*((_QWORD *)this + 14);
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
0x180027590  push    rbx
0x180027592  push    rbp
0x180027593  push    rsi
0x180027594  push    rdi
0x180027595  sub     rsp, 28h
0x180027599  xor     ebp, ebp
0x18002759b  lea     rdi, ?wszEmpty@@3PAGA; ushort near * wszEmpty
0x1800275a2  cmp     [rcx+70h], rbp
0x1800275a6  mov     rsi, rdx
0x1800275a9  cmovnz  rdi, [rcx+70h]
0x1800275ae  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800275b2  mov     rcx, rbx
0x1800275b5  inc     rcx
0x1800275b8  cmp     [rdi+rcx*2], bp
0x1800275bc  jnz     short loc_1800275B5
0x1800275be  lea     rcx, ds:2[rcx*2]; cb
0x1800275c6  call    cs:__imp_CoTaskMemAlloc
0x1800275cd  nop     dword ptr [rax+rax+00h]
0x1800275d2  mov     [rsi], rax
0x1800275d5  test    rax, rax
0x1800275d8  jnz     short loc_1800275E1
0x1800275da  mov     eax, 8007000Eh
0x1800275df  jmp     short loc_1800275F9
0x1800275e1  inc     rbx
0x1800275e4  cmp     [rdi+rbx*2], bp
0x1800275e8  jnz     short loc_1800275E1
0x1800275ea  lea     rdx, [rbx+1]; unsigned __int64
0x1800275ee  mov     r8, rdi; unsigned __int16 *
0x1800275f1  mov     rcx, rax; unsigned __int16 *
0x1800275f4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800275f9  add     rsp, 28h
0x1800275fd  pop     rdi
0x1800275fe  pop     rsi
0x1800275ff  pop     rbp
0x180027600  pop     rbx
0x180027601  retn
```
