# CJob::GetComment(ushort * *)

- ea: `0x180025e70`
- end: `0x180025ee1`
- name: `?GetComment@CJob@@UEAAJPEAPEAG@Z`
- size: `113`
- prototype: `__int64 __fastcall(CJob *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003ef0`
- `0x180025e70`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180025eab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180025eab`

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
0x180025e70  push    rbx
0x180025e72  push    rbp
0x180025e73  push    rsi
0x180025e74  push    rdi
0x180025e75  sub     rsp, 28h
0x180025e79  mov     rax, [rcx+90h]
0x180025e80  lea     rdi, ?wszEmpty@@3PAGA; ushort near * wszEmpty
0x180025e87  xor     ebp, ebp
0x180025e89  mov     rsi, rdx
0x180025e8c  test    rax, rax
0x180025e8f  cmovnz  rdi, rax
0x180025e93  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180025e97  mov     rcx, rbx
0x180025e9a  inc     rcx
0x180025e9d  cmp     [rdi+rcx*2], bp
0x180025ea1  jnz     short loc_180025E9A
0x180025ea3  lea     rcx, ds:2[rcx*2]; cb
0x180025eab  call    cs:__imp_CoTaskMemAlloc
0x180025eb1  mov     [rsi], rax
0x180025eb4  test    rax, rax
0x180025eb7  jnz     short loc_180025EC0
0x180025eb9  mov     eax, 8007000Eh
0x180025ebe  jmp     short loc_180025ED8
0x180025ec0  inc     rbx
0x180025ec3  cmp     [rdi+rbx*2], bp
0x180025ec7  jnz     short loc_180025EC0
0x180025ec9  lea     rdx, [rbx+1]; unsigned __int64
0x180025ecd  mov     r8, rdi; unsigned __int16 *
0x180025ed0  mov     rcx, rax; unsigned __int16 *
0x180025ed3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180025ed8  add     rsp, 28h
0x180025edc  pop     rdi
0x180025edd  pop     rsi
0x180025ede  pop     rbp
0x180025edf  pop     rbx
0x180025ee0  retn
```
