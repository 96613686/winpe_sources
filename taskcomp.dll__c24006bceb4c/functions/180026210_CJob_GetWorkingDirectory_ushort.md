# CJob::GetWorkingDirectory(ushort * *)

- ea: `0x180026210`
- end: `0x180026281`
- name: `?GetWorkingDirectory@CJob@@UEAAJPEAPEAG@Z`
- size: `113`
- prototype: `__int64 __fastcall(CJob *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003ef0`
- `0x180026210`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002624b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002624b`

## pseudocode

```c
__int64 __fastcall CJob::GetWorkingDirectory(CJob *this, unsigned __int16 **a2)
{
  const unsigned __int16 *v2; // rdi
  __int64 v4; // rbx
  __int64 v5; // rcx
  unsigned __int16 *v6; // rax

  v2 = (const unsigned __int16 *)&wszEmpty;
  if ( *((_QWORD *)this + 16) )
    v2 = (const unsigned __int16 *)*((_QWORD *)this + 16);
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
0x180026210  push    rbx
0x180026212  push    rbp
0x180026213  push    rsi
0x180026214  push    rdi
0x180026215  sub     rsp, 28h
0x180026219  mov     rax, [rcx+80h]
0x180026220  lea     rdi, ?wszEmpty@@3PAGA; ushort near * wszEmpty
0x180026227  xor     ebp, ebp
0x180026229  mov     rsi, rdx
0x18002622c  test    rax, rax
0x18002622f  cmovnz  rdi, rax
0x180026233  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180026237  mov     rcx, rbx
0x18002623a  inc     rcx
0x18002623d  cmp     [rdi+rcx*2], bp
0x180026241  jnz     short loc_18002623A
0x180026243  lea     rcx, ds:2[rcx*2]; cb
0x18002624b  call    cs:__imp_CoTaskMemAlloc
0x180026251  mov     [rsi], rax
0x180026254  test    rax, rax
0x180026257  jnz     short loc_180026260
0x180026259  mov     eax, 8007000Eh
0x18002625e  jmp     short loc_180026278
0x180026260  inc     rbx
0x180026263  cmp     [rdi+rbx*2], bp
0x180026267  jnz     short loc_180026260
0x180026269  lea     rdx, [rbx+1]; unsigned __int64
0x18002626d  mov     r8, rdi; unsigned __int16 *
0x180026270  mov     rcx, rax; unsigned __int16 *
0x180026273  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180026278  add     rsp, 28h
0x18002627c  pop     rdi
0x18002627d  pop     rsi
0x18002627e  pop     rbp
0x18002627f  pop     rbx
0x180026280  retn
```
