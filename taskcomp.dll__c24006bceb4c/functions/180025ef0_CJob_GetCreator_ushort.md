# CJob::GetCreator(ushort * *)

- ea: `0x180025ef0`
- end: `0x180025f61`
- name: `?GetCreator@CJob@@UEAAJPEAPEAG@Z`
- size: `113`
- prototype: `__int64 __fastcall(CJob *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003ef0`
- `0x180025ef0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180025f2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180025f2b`

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
0x180025ef0  push    rbx
0x180025ef2  push    rbp
0x180025ef3  push    rsi
0x180025ef4  push    rdi
0x180025ef5  sub     rsp, 28h
0x180025ef9  mov     rax, [rcx+88h]
0x180025f00  lea     rdi, ?wszEmpty@@3PAGA; ushort near * wszEmpty
0x180025f07  xor     ebp, ebp
0x180025f09  mov     rsi, rdx
0x180025f0c  test    rax, rax
0x180025f0f  cmovnz  rdi, rax
0x180025f13  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180025f17  mov     rcx, rbx
0x180025f1a  inc     rcx
0x180025f1d  cmp     [rdi+rcx*2], bp
0x180025f21  jnz     short loc_180025F1A
0x180025f23  lea     rcx, ds:2[rcx*2]; cb
0x180025f2b  call    cs:__imp_CoTaskMemAlloc
0x180025f31  mov     [rsi], rax
0x180025f34  test    rax, rax
0x180025f37  jnz     short loc_180025F40
0x180025f39  mov     eax, 8007000Eh
0x180025f3e  jmp     short loc_180025F58
0x180025f40  inc     rbx
0x180025f43  cmp     [rdi+rbx*2], bp
0x180025f47  jnz     short loc_180025F40
0x180025f49  lea     rdx, [rbx+1]; unsigned __int64
0x180025f4d  mov     r8, rdi; unsigned __int16 *
0x180025f50  mov     rcx, rax; unsigned __int16 *
0x180025f53  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180025f58  add     rsp, 28h
0x180025f5c  pop     rdi
0x180025f5d  pop     rsi
0x180025f5e  pop     rbp
0x180025f5f  pop     rbx
0x180025f60  retn
```
