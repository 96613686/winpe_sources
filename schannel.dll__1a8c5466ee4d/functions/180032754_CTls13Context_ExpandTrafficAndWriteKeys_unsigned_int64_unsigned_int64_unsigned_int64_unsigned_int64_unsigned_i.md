# CTls13Context::ExpandTrafficAndWriteKeys(unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *,eSslErrorState *)

- ea: `0x180032754`
- end: `0x1800328d2`
- name: `?ExpandTrafficAndWriteKeys@CTls13Context@@IEAAK_K00PEA_K111PEAW4eSslErrorState@@@Z`
- size: `382`
- prototype: `unsigned int __usercall@<eax>(CTls13Context *__hidden this@<rcx>, unsigned __int64@<rdx>, unsigned __int64@<r8>, unsigned __int64@<r9>, unsigned __int64 *, unsigned __int64 *, unsigned __int64 *, unsigned __int64 *, enum eSslErrorState *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180033188`
- `0x180050f90`

## callees

- `0x180032754`
- `0x180032b20`

## import_xrefs

- `ncrypt!SslExpandTrafficKeys` at `0x180032854`
- `ncrypt!SslExpandTrafficKeys` at `0x180032854`
- `ncrypt!SslExpandWriteKey` at `0x180032887`
- `ncrypt!SslExpandWriteKey` at `0x1800328aa`
- `ncrypt!SslExpandWriteKey` at `0x180032887`
- `ncrypt!SslExpandWriteKey` at `0x1800328aa`
- `ncrypt!SslFreeObject` at `0x18003281f`
- `ncrypt!SslFreeObject` at `0x18003281f`

## pseudocode

```c
__int64 __fastcall CTls13Context::ExpandTrafficAndWriteKeys(
        CTls13Context *this,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned __int64 *a5,
        unsigned __int64 *a6,
        unsigned __int64 *a7,
        unsigned __int64 *a8,
        enum eSslErrorState *a9)
{
  __int64 v12; // rcx
  __int64 result; // rax

  if ( !a2 || !a3 || !a4 || !a5 || !a6 || *a5 || *a6 || !a7 || !a8 || *a7 || *a8 || !a9 )
    return 87;
  CTls13Context::FreeEarlyKey(this);
  v12 = *((_QWORD *)this + 5);
  if ( v12 )
  {
    SslFreeObject(v12, 0);
    *((_QWORD *)this + 5) = 0;
  }
  result = SslExpandTrafficKeys(a2, a3, a4, a5, a6, 0, 0);
  if ( (_DWORD)result )
  {
    *(_DWORD *)a9 = 605;
    return result;
  }
  if ( !*((_BYTE *)this + 201) )
    return 0;
  result = SslExpandWriteKey(a2, *a5, a7, 0, 0);
  if ( (_DWORD)result )
  {
    *(_DWORD *)a9 = 606;
  }
  else
  {
    result = SslExpandWriteKey(a2, *a6, a8, 0, 0);
    if ( !(_DWORD)result )
      return 0;
    *(_DWORD *)a9 = 607;
  }
  return result;
}

```

## disassembly

```asm
0x180032754  mov     [rsp+arg_10], r8
0x180032759  push    rbx
0x18003275a  push    rbp
0x18003275b  push    rsi
0x18003275c  push    rdi
0x18003275d  push    r12
0x18003275f  push    r13
0x180032761  push    r14
0x180032763  push    r15
0x180032765  sub     rsp, 48h
0x180032769  mov     r15, rcx
0x18003276c  mov     r13, r9
0x18003276f  xor     ecx, ecx
0x180032771  mov     rax, r8
0x180032774  mov     r12, rdx
0x180032777  test    rdx, rdx
0x18003277a  jz      loc_1800328BC
0x180032780  test    rax, rax
0x180032783  jz      loc_1800328BC
0x180032789  test    r9, r9
0x18003278c  jz      loc_1800328BC
0x180032792  mov     rdi, [rsp+88h+arg_20]
0x18003279a  test    rdi, rdi
0x18003279d  jz      loc_1800328BC
0x1800327a3  mov     rsi, [rsp+88h+arg_28]
0x1800327ab  test    rsi, rsi
0x1800327ae  jz      loc_1800328BC
0x1800327b4  cmp     [rdi], rcx
0x1800327b7  jnz     loc_1800328BC
0x1800327bd  cmp     [rsi], rcx
0x1800327c0  jnz     loc_1800328BC
0x1800327c6  mov     rbp, [rsp+88h+arg_30]
0x1800327ce  test    rbp, rbp
0x1800327d1  jz      loc_1800328BC
0x1800327d7  mov     r14, [rsp+88h+arg_38]
0x1800327df  test    r14, r14
0x1800327e2  jz      loc_1800328BC
0x1800327e8  cmp     [rbp+0], rcx
0x1800327ec  jnz     loc_1800328BC
0x1800327f2  cmp     [r14], rcx
0x1800327f5  jnz     loc_1800328BC
0x1800327fb  mov     rbx, [rsp+88h+arg_40]
0x180032803  test    rbx, rbx
0x180032806  jz      loc_1800328BC
0x18003280c  mov     rcx, r15; this
0x18003280f  call    ?FreeEarlyKey@CTls13Context@@AEAAXXZ; CTls13Context::FreeEarlyKey(void)
0x180032814  mov     rcx, [r15+28h]
0x180032818  test    rcx, rcx
0x18003281b  jz      short loc_18003282D
0x18003281d  xor     edx, edx
0x18003281f  call    cs:__imp_SslFreeObject
0x180032825  mov     qword ptr [r15+28h], 0
0x18003282d  mov     rdx, [rsp+88h+arg_10]
0x180032835  mov     r9, rdi
0x180032838  mov     [rsp+88h+var_58], 0
0x180032840  mov     r8, r13
0x180032843  mov     [rsp+88h+var_60], 0
0x18003284c  mov     rcx, r12
0x18003284f  mov     [rsp+88h+var_68], rsi
0x180032854  call    cs:__imp_SslExpandTrafficKeys
0x18003285a  xor     r13d, r13d
0x18003285d  test    eax, eax
0x18003285f  jz      short loc_180032869
0x180032861  mov     dword ptr [rbx], 25Dh
0x180032867  jmp     short loc_1800328C1
0x180032869  cmp     [r15+0C9h], r13b
0x180032870  jnz     short loc_180032876
0x180032872  xor     eax, eax
0x180032874  jmp     short loc_1800328C1
0x180032876  mov     rdx, [rdi]
0x180032879  xor     r9d, r9d
0x18003287c  mov     r8, rbp
0x18003287f  mov     dword ptr [rsp+88h+var_68], r13d
0x180032884  mov     rcx, r12
0x180032887  call    cs:__imp_SslExpandWriteKey
0x18003288d  test    eax, eax
0x18003288f  jz      short loc_180032899
0x180032891  mov     dword ptr [rbx], 25Eh
0x180032897  jmp     short loc_1800328C1
0x180032899  mov     rdx, [rsi]
0x18003289c  xor     r9d, r9d
0x18003289f  mov     r8, r14
0x1800328a2  mov     dword ptr [rsp+88h+var_68], r13d
0x1800328a7  mov     rcx, r12
0x1800328aa  call    cs:__imp_SslExpandWriteKey
0x1800328b0  test    eax, eax
0x1800328b2  jz      short loc_180032872
0x1800328b4  mov     dword ptr [rbx], 25Fh
0x1800328ba  jmp     short loc_1800328C1
0x1800328bc  mov     eax, 57h ; 'W'
0x1800328c1  add     rsp, 48h
0x1800328c5  pop     r15
0x1800328c7  pop     r14
0x1800328c9  pop     r13
0x1800328cb  pop     r12
0x1800328cd  pop     rdi
0x1800328ce  pop     rsi
0x1800328cf  pop     rbp
0x1800328d0  pop     rbx
0x1800328d1  retn
```
