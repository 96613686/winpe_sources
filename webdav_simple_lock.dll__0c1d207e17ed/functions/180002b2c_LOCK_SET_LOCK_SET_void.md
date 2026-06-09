# LOCK_SET::~LOCK_SET(void)

- ea: `0x180002b2c`
- end: `0x180002c20`
- name: `??1LOCK_SET@@UEAA@XZ`
- size: `244`
- prototype: `void __fastcall(LOCK_SET *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180001c70`
- `0x180002d40`

## callees

- `0x180002b2c`
- `0x180002c28`
- `0x1800037b4`
- `0x180003c06`
- `0x180004010`

## pseudocode

```c
void __fastcall LOCK_SET::~LOCK_SET(LOCK_SET *this)
{
  char *v1; // rdi
  __int64 v3; // r8
  __int64 v4; // rdx
  struct URI_LOCK_LIST *i; // rcx
  __int64 v6; // [rsp+20h] [rbp-18h] BYREF
  int v7; // [rsp+28h] [rbp-10h]
  int v8; // [rsp+2Ch] [rbp-Ch]

  *(_QWORD *)this = &LOCK_SET::`vftable';
  v1 = (char *)this + 2888;
  v8 = 1;
  v3 = 0;
  do
  {
    v4 = *(_QWORD *)&v1[8 * v3];
    if ( v4 )
      break;
    v3 = (unsigned int)(v3 + 1);
  }
  while ( (unsigned int)v3 < 0x83 );
  v7 = v3;
  v6 = v4;
  if ( v4 )
    *(_QWORD *)&v1[8 * v3] = *(_QWORD *)(v4 + 8);
  for ( i = (struct URI_LOCK_LIST *)((v4 - 56) & -(__int64)(v4 != 0));
        i;
        i = LOCK_SET::FindNextAllUri(this, (struct URI_LOCK_LIST_ITER *)&v6) )
  {
    (**(void (__fastcall ***)(struct URI_LOCK_LIST *, __int64))i)(i, 1);
  }
  memset_0((char *)this + 776, 0, 0x418u);
  memset_0((char *)this + 1832, 0, 0x418u);
  memset_0(v1, 0, 0x418u);
  memset_0((char *)this + 3944, 0, 0x418u);
  URI_LOCK_LIST::~URI_LOCK_LIST((LOCK_SET *)((char *)this + 8));
  *(_QWORD *)this = &IPubLockSet::`vftable';
}

```

## disassembly

```asm
0x180002b2c  mov     [rsp+arg_0], rbx
0x180002b31  mov     [rsp+arg_8], rsi
0x180002b36  push    rdi
0x180002b37  sub     rsp, 30h
0x180002b3b  lea     rax, ??_7LOCK_SET@@6B@; const LOCK_SET::`vftable'
0x180002b42  mov     esi, 1
0x180002b47  mov     [rcx], rax
0x180002b4a  lea     rdi, [rcx+0B48h]
0x180002b51  mov     [rsp+38h+var_C], esi
0x180002b55  mov     rbx, rcx
0x180002b58  xor     r8d, r8d
0x180002b5b  mov     rdx, [rdi+r8*8]
0x180002b5f  test    rdx, rdx
0x180002b62  jnz     short loc_180002B70
0x180002b64  add     r8d, esi
0x180002b67  cmp     r8d, 83h
0x180002b6e  jb      short loc_180002B5B
0x180002b70  mov     [rsp+38h+var_10], r8d
0x180002b75  mov     [rsp+38h+var_18], rdx
0x180002b7a  test    rdx, rdx
0x180002b7d  jz      short loc_180002B87
0x180002b7f  mov     rax, [rdx+8]
0x180002b83  mov     [rdi+r8*8], rax
0x180002b87  lea     rax, [rdx-38h]
0x180002b8b  neg     rdx
0x180002b8e  sbb     rcx, rcx
0x180002b91  and     rcx, rax
0x180002b94  jz      short loc_180002BB8
0x180002b96  mov     rax, [rcx]
0x180002b99  mov     edx, esi
0x180002b9b  mov     rax, [rax]
0x180002b9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ba3  lea     rdx, [rsp+38h+var_18]; struct URI_LOCK_LIST_ITER *
0x180002ba8  mov     rcx, rbx; this
0x180002bab  call    ?FindNextAllUri@LOCK_SET@@QEAAPEAVURI_LOCK_LIST@@PEAUURI_LOCK_LIST_ITER@@@Z; LOCK_SET::FindNextAllUri(URI_LOCK_LIST_ITER *)
0x180002bb0  mov     rcx, rax
0x180002bb3  test    rax, rax
0x180002bb6  jnz     short loc_180002B96
0x180002bb8  mov     esi, 418h
0x180002bbd  lea     rcx, [rbx+308h]; void *
0x180002bc4  mov     r8d, esi; Size
0x180002bc7  xor     edx, edx; Val
0x180002bc9  call    memset_0
0x180002bce  lea     rcx, [rbx+728h]; void *
0x180002bd5  mov     r8d, esi; Size
0x180002bd8  xor     edx, edx; Val
0x180002bda  call    memset_0
0x180002bdf  mov     r8d, esi; Size
0x180002be2  xor     edx, edx; Val
0x180002be4  mov     rcx, rdi; void *
0x180002be7  call    memset_0
0x180002bec  lea     rcx, [rbx+0F68h]; void *
0x180002bf3  mov     r8d, esi; Size
0x180002bf6  xor     edx, edx; Val
0x180002bf8  call    memset_0
0x180002bfd  lea     rcx, [rbx+8]; this
0x180002c01  call    ??1URI_LOCK_LIST@@UEAA@XZ; URI_LOCK_LIST::~URI_LOCK_LIST(void)
0x180002c06  mov     rsi, [rsp+38h+arg_8]
0x180002c0b  lea     rax, ??_7IPubLockSet@@6B@; const IPubLockSet::`vftable'
0x180002c12  mov     [rbx], rax
0x180002c15  mov     rbx, [rsp+38h+arg_0]
0x180002c1a  add     rsp, 30h
0x180002c1e  pop     rdi
0x180002c1f  retn
```
