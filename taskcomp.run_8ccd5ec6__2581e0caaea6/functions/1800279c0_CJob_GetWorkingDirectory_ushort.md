# CJob::GetWorkingDirectory(ushort * *)

- ea: `0x1800279c0`
- end: `0x180027a38`
- name: `?GetWorkingDirectory@CJob@@UEAAJPEAPEAG@Z`
- size: `120`
- prototype: `__int64 __fastcall(CJob *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800040c0`
- `0x1800279c0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800279fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800279fb`

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
0x1800279c0  push    rbx
0x1800279c2  push    rbp
0x1800279c3  push    rsi
0x1800279c4  push    rdi
0x1800279c5  sub     rsp, 28h
0x1800279c9  mov     rax, [rcx+80h]
0x1800279d0  lea     rdi, ?wszEmpty@@3PAGA; ushort near * wszEmpty
0x1800279d7  xor     ebp, ebp
0x1800279d9  mov     rsi, rdx
0x1800279dc  test    rax, rax
0x1800279df  cmovnz  rdi, rax
0x1800279e3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800279e7  mov     rcx, rbx
0x1800279ea  inc     rcx
0x1800279ed  cmp     [rdi+rcx*2], bp
0x1800279f1  jnz     short loc_1800279EA
0x1800279f3  lea     rcx, ds:2[rcx*2]; cb
0x1800279fb  call    cs:__imp_CoTaskMemAlloc
0x180027a02  nop     dword ptr [rax+rax+00h]
0x180027a07  mov     [rsi], rax
0x180027a0a  test    rax, rax
0x180027a0d  jnz     short loc_180027A16
0x180027a0f  mov     eax, 8007000Eh
0x180027a14  jmp     short loc_180027A2E
0x180027a16  inc     rbx
0x180027a19  cmp     [rdi+rbx*2], bp
0x180027a1d  jnz     short loc_180027A16
0x180027a1f  lea     rdx, [rbx+1]; unsigned __int64
0x180027a23  mov     r8, rdi; unsigned __int16 *
0x180027a26  mov     rcx, rax; unsigned __int16 *
0x180027a29  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180027a2e  add     rsp, 28h
0x180027a32  pop     rdi
0x180027a33  pop     rsi
0x180027a34  pop     rbp
0x180027a35  pop     rbx
0x180027a36  retn
```
