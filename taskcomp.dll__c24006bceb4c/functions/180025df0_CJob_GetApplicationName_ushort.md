# CJob::GetApplicationName(ushort * *)

- ea: `0x180025df0`
- end: `0x180025e5c`
- name: `?GetApplicationName@CJob@@UEAAJPEAPEAG@Z`
- size: `108`
- prototype: `__int64 __fastcall(CJob *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003ef0`
- `0x180025df0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180025e26`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180025e26`

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
0x180025df0  push    rbx
0x180025df2  push    rbp
0x180025df3  push    rsi
0x180025df4  push    rdi
0x180025df5  sub     rsp, 28h
0x180025df9  xor     ebp, ebp
0x180025dfb  lea     rdi, ?wszEmpty@@3PAGA; ushort near * wszEmpty
0x180025e02  cmp     [rcx+70h], rbp
0x180025e06  mov     rsi, rdx
0x180025e09  cmovnz  rdi, [rcx+70h]
0x180025e0e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180025e12  mov     rcx, rbx
0x180025e15  inc     rcx
0x180025e18  cmp     [rdi+rcx*2], bp
0x180025e1c  jnz     short loc_180025E15
0x180025e1e  lea     rcx, ds:2[rcx*2]; cb
0x180025e26  call    cs:__imp_CoTaskMemAlloc
0x180025e2c  mov     [rsi], rax
0x180025e2f  test    rax, rax
0x180025e32  jnz     short loc_180025E3B
0x180025e34  mov     eax, 8007000Eh
0x180025e39  jmp     short loc_180025E53
0x180025e3b  inc     rbx
0x180025e3e  cmp     [rdi+rbx*2], bp
0x180025e42  jnz     short loc_180025E3B
0x180025e44  lea     rdx, [rbx+1]; unsigned __int64
0x180025e48  mov     r8, rdi; unsigned __int16 *
0x180025e4b  mov     rcx, rax; unsigned __int16 *
0x180025e4e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180025e53  add     rsp, 28h
0x180025e57  pop     rdi
0x180025e58  pop     rsi
0x180025e59  pop     rbp
0x180025e5a  pop     rbx
0x180025e5b  retn
```
