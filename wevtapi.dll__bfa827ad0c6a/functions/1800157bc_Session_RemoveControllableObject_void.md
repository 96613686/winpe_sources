# Session::RemoveControllableObject(void *)

- ea: `0x1800157bc`
- end: `0x180015855`
- name: `?RemoveControllableObject@Session@@QEAA_NPEAX@Z`
- size: `153`
- prototype: `bool __fastcall(Session *__hidden this, void *)`
- caller_count: `6`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180013e6c`
- `0x180014938`
- `0x180014bb0`
- `0x1800154dc`
- `0x1800156b4`
- `0x180028960`

## callees

- `0x18000a100`
- `0x1800157bc`
- `0x1800171f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800157d5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800157d5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180015813`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180015813`

## pseudocode

```c
bool __fastcall Session::RemoveControllableObject(RTL_SRWLOCK *this, unsigned __int64 a2)
{
  RTL_SRWLOCK *v2; // rbx
  RTL_SRWLOCK *v4; // rsi
  __int64 *Ptr; // rax
  __int64 *v6; // rbp
  __int64 v7; // rcx
  __int64 v8; // rdi

  v2 = this + 8;
  v4 = this + 4;
  AcquireSRWLockExclusive(this + 8);
  if ( v4[2].Ptr == v4 )
    goto LABEL_7;
  Ptr = (__int64 *)v4->Ptr;
  v6 = (__int64 *)v4;
  do
  {
    if ( Ptr[3] >= a2 )
    {
      v6 = Ptr;
      v7 = 1;
    }
    else
    {
      v7 = 2;
    }
    Ptr = (__int64 *)Ptr[v7];
  }
  while ( Ptr != (__int64 *)&utl::_TreeSentinel );
  if ( v6 == (__int64 *)v4 || a2 < v6[3] )
  {
LABEL_7:
    v8 = 0;
  }
  else
  {
    v8 = 1;
    utl::_TreeNodeHeader<void *>::_HeadUnlinkNode(v4, v6);
    --v4[3].Ptr;
    operator delete(v6);
  }
  ReleaseSRWLockExclusive(v2);
  return v8 != 0;
}

```

## disassembly

```asm
0x1800157bc  push    rbx
0x1800157be  push    rbp
0x1800157bf  push    rsi
0x1800157c0  push    rdi
0x1800157c1  push    r14
0x1800157c3  sub     rsp, 20h
0x1800157c7  lea     rbx, [rcx+40h]
0x1800157cb  mov     r14, rdx
0x1800157ce  lea     rsi, [rcx+20h]
0x1800157d2  mov     rcx, rbx; SRWLock
0x1800157d5  call    cs:__imp_AcquireSRWLockExclusive
0x1800157db  cmp     [rsi+10h], rsi
0x1800157df  jz      short loc_180015807
0x1800157e1  mov     rax, [rsi]
0x1800157e4  mov     rbp, rsi
0x1800157e7  cmp     [rax+18h], r14
0x1800157eb  jnb     short loc_180015827
0x1800157ed  mov     ecx, 10h
0x1800157f2  mov     rax, [rcx+rax]
0x1800157f6  lea     rcx, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x1800157fd  cmp     rax, rcx
0x180015800  jnz     short loc_1800157E7
0x180015802  cmp     rbp, rsi
0x180015805  jnz     short loc_180015831
0x180015807  xor     edi, edi
0x180015809  test    rdi, rdi
0x18001580c  mov     rcx, rbx; SRWLock
0x18001580f  setnz   dil
0x180015813  call    cs:__imp_ReleaseSRWLockExclusive
0x180015819  mov     al, dil
0x18001581c  add     rsp, 20h
0x180015820  pop     r14
0x180015822  pop     rdi
0x180015823  pop     rsi
0x180015824  pop     rbp
0x180015825  pop     rbx
0x180015826  retn
0x180015827  mov     rbp, rax
0x18001582a  mov     ecx, 8
0x18001582f  jmp     short loc_1800157F2
0x180015831  cmp     r14, [rbp+18h]
0x180015835  jb      short loc_180015807
0x180015837  mov     rdx, rbp
0x18001583a  mov     rcx, rsi
0x18001583d  mov     edi, 1
0x180015842  call    ?_HeadUnlinkNode@?$_TreeNodeHeader@PEAX@utl@@QEAAXPEAU?$_TreeNode@PEAX@2@@Z; utl::_TreeNodeHeader<void *>::_HeadUnlinkNode(utl::_TreeNode<void *> *)
0x180015847  dec     qword ptr [rsi+18h]
0x18001584b  mov     rcx, rbp; void *
0x18001584e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180015853  jmp     short loc_180015809
```
