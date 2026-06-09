# IIS_VDIR_CONFIG::~IIS_VDIR_CONFIG(void)

- ea: `0x18001c6ec`
- end: `0x18001c7a1`
- name: `??1IIS_VDIR_CONFIG@@QEAA@XZ`
- size: `181`
- prototype: `void __fastcall(IIS_VDIR_CONFIG *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x18000ffec`

## callees

- `0x180001214`
- `0x180004474`
- `0x18001c610`
- `0x18001c6ec`
- `0x18001c7a8`

## import_xrefs

- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18001c79a`

## pseudocode

```c
void __fastcall IIS_VDIR_CONFIG::~IIS_VDIR_CONFIG(IIS_VDIR_CONFIG *this)
{
  STATIC_WSTRING_HASH *v2; // rsi
  __int64 v3; // rdx
  struct STATIC_WSTRING_HASH_RECORD *Next; // rbx
  void *v5; // rbx
  struct STATIC_WSTRING_HASH_RECORD *v6; // [rsp+20h] [rbp-18h] BYREF
  int v7; // [rsp+28h] [rbp-10h]
  int v8; // [rsp+2Ch] [rbp-Ch]

  v8 = 1;
  v2 = (IIS_VDIR_CONFIG *)((char *)this + 1056);
  v3 = 0;
  do
  {
    Next = (struct STATIC_WSTRING_HASH_RECORD *)*((_QWORD *)v2 + v3);
    if ( Next )
      break;
    v3 = (unsigned int)(v3 + 1);
  }
  while ( (unsigned int)v3 < 0x83 );
  v7 = v3;
  v6 = Next;
  if ( Next )
  {
    *((_QWORD *)v2 + v3) = *((_QWORD *)Next + 1);
    do
    {
      IIS_VDIR_PARENT::~IIS_VDIR_PARENT(Next);
      operator delete(Next);
      Next = STATIC_WSTRING_HASH::FindNext(v2, (struct STATIC_WSTRING_HASH_ITER *)&v6);
    }
    while ( Next );
  }
  v5 = (void *)*((_QWORD *)this + 271);
  if ( v5 )
  {
    IIS_VDIR::~IIS_VDIR(*((IIS_VDIR **)this + 271));
    operator delete(v5);
  }
  *((_QWORD *)this + 271) = 0;
  BUFFER::~BUFFER((IIS_VDIR_CONFIG *)((char *)this + 2112));
}

```

## disassembly

```asm
0x18001c6ec  mov     [rsp+arg_0], rbx
0x18001c6f1  mov     [rsp+arg_8], rsi
0x18001c6f6  push    rdi
0x18001c6f7  sub     rsp, 30h
0x18001c6fb  mov     rdi, rcx
0x18001c6fe  mov     [rsp+38h+var_C], 1
0x18001c706  lea     rsi, [rcx+420h]
0x18001c70d  xor     edx, edx
0x18001c70f  mov     rbx, [rsi+rdx*8]
0x18001c713  test    rbx, rbx
0x18001c716  jnz     short loc_18001C722
0x18001c718  inc     edx
0x18001c71a  cmp     edx, 83h
0x18001c720  jb      short loc_18001C70F
0x18001c722  mov     [rsp+38h+var_10], edx
0x18001c726  mov     [rsp+38h+var_18], rbx
0x18001c72b  test    rbx, rbx
0x18001c72e  jz      short loc_18001C75D
0x18001c730  mov     rax, [rbx+8]
0x18001c734  mov     [rsi+rdx*8], rax
0x18001c738  mov     rcx, rbx; this
0x18001c73b  call    ??1IIS_VDIR_PARENT@@QEAA@XZ; IIS_VDIR_PARENT::~IIS_VDIR_PARENT(void)
0x18001c740  mov     rcx, rbx; Block
0x18001c743  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001c748  lea     rdx, [rsp+38h+var_18]; struct STATIC_WSTRING_HASH_ITER *
0x18001c74d  mov     rcx, rsi; this
0x18001c750  call    ?FindNext@STATIC_WSTRING_HASH@@QEAAPEAUSTATIC_WSTRING_HASH_RECORD@@PEAUSTATIC_WSTRING_HASH_ITER@@@Z; STATIC_WSTRING_HASH::FindNext(STATIC_WSTRING_HASH_ITER *)
0x18001c755  mov     rbx, rax
0x18001c758  test    rax, rax
0x18001c75b  jnz     short loc_18001C738
0x18001c75d  mov     rbx, [rdi+878h]
0x18001c764  test    rbx, rbx
0x18001c767  jz      short loc_18001C779
0x18001c769  mov     rcx, rbx; this
0x18001c76c  call    ??1IIS_VDIR@@QEAA@XZ; IIS_VDIR::~IIS_VDIR(void)
0x18001c771  mov     rcx, rbx; Block
0x18001c774  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001c779  lea     rcx, [rdi+840h]
0x18001c780  mov     qword ptr [rdi+878h], 0
0x18001c78b  mov     rbx, [rsp+38h+arg_0]
0x18001c790  mov     rsi, [rsp+38h+arg_8]
0x18001c795  add     rsp, 30h
0x18001c799  pop     rdi
0x18001c79a  jmp     cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
```
