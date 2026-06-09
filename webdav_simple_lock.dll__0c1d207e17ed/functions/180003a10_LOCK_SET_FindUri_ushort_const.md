# LOCK_SET::FindUri(ushort const *)

- ea: `0x180003a10`
- end: `0x180003a79`
- name: `?FindUri@LOCK_SET@@UEAAPEAVIPubUriLockList@@PEBG@Z`
- size: `105`
- prototype: `struct IPubUriLockList *(LOCK_SET *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180003614`
- `0x180003a10`
- `0x180004010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180003a3e`
- `msvcrt!_wcsicmp` at `0x180003a3e`

## pseudocode

```c
struct IPubUriLockList *__fastcall LOCK_SET::FindUri(LOCK_SET *this, wchar_t *a2)
{
  char *v2; // rbx
  const wchar_t *v5; // rax
  struct STATIC_WSTRING_HASH_RECORD *Key; // rax

  v2 = (char *)this + 8;
  v5 = (const wchar_t *)(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 1) + 16LL))((char *)this + 8);
  if ( !_wcsicmp(a2, v5) )
    return (struct IPubUriLockList *)v2;
  Key = STATIC_WSTRING_HASH::FindKey((LOCK_SET *)((char *)this + 2888), a2);
  return (struct IPubUriLockList *)(((unsigned __int64)Key - 56) & -(__int64)(Key != 0));
}

```

## disassembly

```asm
0x180003a10  mov     [rsp+arg_0], rbx
0x180003a15  mov     [rsp+arg_8], rsi
0x180003a1a  push    rdi
0x180003a1b  sub     rsp, 20h
0x180003a1f  lea     rbx, [rcx+8]
0x180003a23  mov     rsi, rcx
0x180003a26  mov     r8, [rbx]
0x180003a29  mov     rcx, rbx
0x180003a2c  mov     rdi, rdx
0x180003a2f  mov     rax, [r8+10h]
0x180003a33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a38  mov     rdx, rax; String2
0x180003a3b  mov     rcx, rdi; String1
0x180003a3e  call    cs:__imp__wcsicmp
0x180003a44  test    eax, eax
0x180003a46  jnz     short loc_180003A4D
0x180003a48  mov     rax, rbx
0x180003a4b  jmp     short loc_180003A69
0x180003a4d  lea     rcx, [rsi+0B48h]; this
0x180003a54  mov     rdx, rdi; unsigned __int16 *
0x180003a57  call    ?FindKey@STATIC_WSTRING_HASH@@QEAAPEAUSTATIC_WSTRING_HASH_RECORD@@PEBGH@Z; STATIC_WSTRING_HASH::FindKey(ushort const *,int)
0x180003a5c  lea     rcx, [rax-38h]
0x180003a60  neg     rax
0x180003a63  sbb     rax, rax
0x180003a66  and     rax, rcx
0x180003a69  mov     rbx, [rsp+28h+arg_0]
0x180003a6e  mov     rsi, [rsp+28h+arg_8]
0x180003a73  add     rsp, 20h
0x180003a77  pop     rdi
0x180003a78  retn
```
