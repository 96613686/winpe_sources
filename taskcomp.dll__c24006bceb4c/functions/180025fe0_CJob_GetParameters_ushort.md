# CJob::GetParameters(ushort * *)

- ea: `0x180025fe0`
- end: `0x18002604c`
- name: `?GetParameters@CJob@@UEAAJPEAPEAG@Z`
- size: `108`
- prototype: `__int64 __fastcall(CJob *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003ef0`
- `0x180025fe0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180026016`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180026016`

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
0x180025fe0  push    rbx
0x180025fe2  push    rbp
0x180025fe3  push    rsi
0x180025fe4  push    rdi
0x180025fe5  sub     rsp, 28h
0x180025fe9  xor     ebp, ebp
0x180025feb  lea     rdi, ?wszEmpty@@3PAGA; ushort near * wszEmpty
0x180025ff2  cmp     [rcx+78h], rbp
0x180025ff6  mov     rsi, rdx
0x180025ff9  cmovnz  rdi, [rcx+78h]
0x180025ffe  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180026002  mov     rcx, rbx
0x180026005  inc     rcx
0x180026008  cmp     [rdi+rcx*2], bp
0x18002600c  jnz     short loc_180026005
0x18002600e  lea     rcx, ds:2[rcx*2]; cb
0x180026016  call    cs:__imp_CoTaskMemAlloc
0x18002601c  mov     [rsi], rax
0x18002601f  test    rax, rax
0x180026022  jnz     short loc_18002602B
0x180026024  mov     eax, 8007000Eh
0x180026029  jmp     short loc_180026043
0x18002602b  inc     rbx
0x18002602e  cmp     [rdi+rbx*2], bp
0x180026032  jnz     short loc_18002602B
0x180026034  lea     rdx, [rbx+1]; unsigned __int64
0x180026038  mov     r8, rdi; unsigned __int16 *
0x18002603b  mov     rcx, rax; unsigned __int16 *
0x18002603e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180026043  add     rsp, 28h
0x180026047  pop     rdi
0x180026048  pop     rsi
0x180026049  pop     rbp
0x18002604a  pop     rbx
0x18002604b  retn
```
