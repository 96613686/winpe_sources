# URI_LOCK_LIST::~URI_LOCK_LIST(void)

- ea: `0x180002c28`
- end: `0x180002d03`
- name: `??1URI_LOCK_LIST@@UEAA@XZ`
- size: `219`
- prototype: `void __fastcall(URI_LOCK_LIST *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180002b2c`
- `0x180002d80`

## callees

- `0x180001048`
- `0x180002c28`
- `0x180004010`

## pseudocode

```c
void __fastcall URI_LOCK_LIST::~URI_LOCK_LIST(URI_LOCK_LIST *this)
{
  char *v1; // rbp
  char *v3; // rsi
  __int64 i; // r14
  __int64 v5; // rbx
  char *v6; // rbx

  v1 = (char *)this + 80;
  v3 = (char *)this + 80;
  *(_QWORD *)this = &URI_LOCK_LIST::`vftable';
  if ( this != (URI_LOCK_LIST *)-80LL )
  {
    do
    {
      for ( i = 0; (unsigned int)i < *((_DWORD *)v3 + 162); *(_QWORD *)&v3[8 * v5] = 0 )
      {
        v5 = 5 * i;
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v3[40 * i] + 16LL))(*(_QWORD *)&v3[40 * i]);
        i = (unsigned int)(i + 1);
      }
      v6 = (char *)*((_QWORD *)v3 + 80);
      *((_QWORD *)v3 + 80) = 0;
      *((_DWORD *)v3 + 162) = 0;
      if ( v3 != v1 )
        operator delete(v3);
      v3 = v6;
    }
    while ( v6 );
  }
  *((_QWORD *)this + 90) = 0;
  *(_QWORD *)this = &IPubUriLockList::`vftable';
  *((_DWORD *)this + 182) = 0;
  *((_QWORD *)this + 92) = v1;
  *((_QWORD *)this + 93) = 0;
  *((_QWORD *)this + 94) = 0;
  *((_QWORD *)this + 95) = 0;
}

```

## disassembly

```asm
0x180002c28  push    rbx
0x180002c2a  push    rbp
0x180002c2b  push    rsi
0x180002c2c  push    rdi
0x180002c2d  push    r14
0x180002c2f  sub     rsp, 20h
0x180002c33  lea     rbp, [rcx+50h]
0x180002c37  mov     rdi, rcx
0x180002c3a  lea     rax, ??_7URI_LOCK_LIST@@6B@; const URI_LOCK_LIST::`vftable'
0x180002c41  mov     rsi, rbp
0x180002c44  mov     [rcx], rax
0x180002c47  test    rbp, rbp
0x180002c4a  jz      short loc_180002CB1
0x180002c4c  xor     r14d, r14d
0x180002c4f  cmp     [rsi+288h], r14d
0x180002c56  jbe     short loc_180002C80
0x180002c58  lea     rbx, [r14+r14*4]
0x180002c5c  mov     rcx, [rsi+rbx*8]
0x180002c60  mov     rax, [rcx]
0x180002c63  mov     rax, [rax+10h]
0x180002c67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c6c  inc     r14d
0x180002c6f  mov     qword ptr [rsi+rbx*8], 0
0x180002c77  cmp     r14d, [rsi+288h]
0x180002c7e  jb      short loc_180002C58
0x180002c80  mov     rbx, [rsi+280h]
0x180002c87  mov     qword ptr [rsi+280h], 0
0x180002c92  mov     dword ptr [rsi+288h], 0
0x180002c9c  cmp     rsi, rbp
0x180002c9f  jz      short loc_180002CA9
0x180002ca1  mov     rcx, rsi; Block
0x180002ca4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002ca9  mov     rsi, rbx
0x180002cac  test    rbx, rbx
0x180002caf  jnz     short loc_180002C4C
0x180002cb1  lea     rax, ??_7IPubUriLockList@@6B@; const IPubUriLockList::`vftable'
0x180002cb8  mov     qword ptr [rdi+2D0h], 0
0x180002cc3  mov     [rdi], rax
0x180002cc6  mov     dword ptr [rdi+2D8h], 0
0x180002cd0  mov     [rdi+2E0h], rbp
0x180002cd7  mov     qword ptr [rdi+2E8h], 0
0x180002ce2  mov     qword ptr [rdi+2F0h], 0
0x180002ced  mov     qword ptr [rdi+2F8h], 0
0x180002cf8  add     rsp, 20h
0x180002cfc  pop     r14
0x180002cfe  pop     rdi
0x180002cff  pop     rsi
0x180002d00  pop     rbp
0x180002d01  pop     rbx
0x180002d02  retn
```
