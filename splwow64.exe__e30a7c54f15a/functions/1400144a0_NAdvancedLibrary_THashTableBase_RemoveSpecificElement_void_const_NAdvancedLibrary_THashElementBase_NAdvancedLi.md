# NAdvancedLibrary::THashTableBase::RemoveSpecificElement(void const *,NAdvancedLibrary::THashElementBase *,NAdvancedLibrary::THashElementBase * *,bool *)

- ea: `0x1400144a0`
- end: `0x1400145fd`
- name: `?RemoveSpecificElement@THashTableBase@NAdvancedLibrary@@AEAAXPEBXPEAVTHashElementBase@2@PEAPEAV32@PEA_N@Z`
- size: `349`
- prototype: `void __usercall(NAdvancedLibrary::THashTableBase *__hidden this@<rcx>, const void *@<rdx>, struct NAdvancedLibrary::THashElementBase *@<r8>, struct NAdvancedLibrary::THashElementBase **@<r9>, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140012390`

## callees

- `0x1400144a0`
- `0x140014604`
- `0x140016010`

## pseudocode

```c
void __fastcall NAdvancedLibrary::THashTableBase::RemoveSpecificElement(
        NAdvancedLibrary::THashTableBase *this,
        const void *a2,
        struct NAdvancedLibrary::THashElementBase *a3,
        struct NAdvancedLibrary::THashElementBase **a4,
        bool *a5)
{
  bool v7; // r15
  __int64 v8; // rbp
  unsigned __int64 v9; // r12
  __int64 *v10; // r14
  __int64 v11; // rdi
  __int64 v12; // rbx
  __int64 v13; // rax
  unsigned int v14; // ecx

  v7 = 0;
  v8 = 0;
  (*(void (__fastcall **)(NAdvancedLibrary::THashTableBase *, const void *, struct NAdvancedLibrary::THashElementBase *, struct NAdvancedLibrary::THashElementBase **))(*(_QWORD *)this + 88LL))(
    this,
    a2,
    a3,
    a4);
  (*(void (__fastcall **)(NAdvancedLibrary::THashTableBase *))(*(_QWORD *)this + 24LL))(this);
  v9 = (*(__int64 (__fastcall **)(NAdvancedLibrary::THashTableBase *, const void *))(*(_QWORD *)this + 88LL))(this, a2);
  v10 = (__int64 *)(*((_QWORD *)this + 1) + 8 * (v9 % *((unsigned int *)this + 10)));
  v11 = *v10;
  if ( *v10 )
  {
    do
    {
      if ( *(_QWORD *)(v11 + 24) == v9 )
      {
        v12 = *(_QWORD *)this;
        v13 = (*(__int64 (__fastcall **)(NAdvancedLibrary::THashTableBase *, __int64))(*(_QWORD *)this + 80LL))(
                this,
                v11);
        if ( !(*(unsigned int (__fastcall **)(NAdvancedLibrary::THashTableBase *, const void *, __int64))(v12 + 96))(
                this,
                a2,
                v13) )
          break;
      }
      v10 = (__int64 *)(v11 + 16);
      v11 = *(_QWORD *)(v11 + 16);
    }
    while ( v11 );
    if ( v11
      && !(*(unsigned int (__fastcall **)(NAdvancedLibrary::THashTableBase *, __int64))(*(_QWORD *)this + 72LL))(
            this,
            v11) )
    {
      v7 = 1;
      *v10 = *(_QWORD *)(v11 + 16);
      v14 = --*((_DWORD *)this + 12);
      if ( v14 > *((_DWORD *)this + 11) && v14 < *((_DWORD *)this + 10) >> 2 )
        NAdvancedLibrary::THashTableBase::TryChangeTableSize(this);
      if ( !(*(unsigned int (__fastcall **)(NAdvancedLibrary::THashTableBase *, __int64))(*(_QWORD *)this + 64LL))(
              this,
              v11) )
      {
        v8 = v11;
        **(_QWORD **)(v11 + 8) = *(_QWORD *)v11;
        *(_QWORD *)(*(_QWORD *)v11 + 8LL) = *(_QWORD *)(v11 + 8);
        *(_QWORD *)(v11 + 8) = v11;
        *(_QWORD *)v11 = v11;
      }
    }
  }
  (*(void (__fastcall **)(NAdvancedLibrary::THashTableBase *))(*(_QWORD *)this + 32LL))(this);
  if ( a5 )
    *a5 = v7;
  if ( v8 )
    (*((void (__fastcall **)(__int64))this + 4))(v8);
}

```

## disassembly

```asm
0x1400144a0  push    rbx
0x1400144a2  push    rbp
0x1400144a3  push    rsi
0x1400144a4  push    rdi
0x1400144a5  push    r12
0x1400144a7  push    r13
0x1400144a9  push    r14
0x1400144ab  push    r15
0x1400144ad  sub     rsp, 28h
0x1400144b1  mov     rax, [rcx]
0x1400144b4  mov     r13, rdx
0x1400144b7  mov     rsi, rcx
0x1400144ba  xor     r15b, r15b
0x1400144bd  xor     ebp, ebp
0x1400144bf  mov     rax, [rax+58h]
0x1400144c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400144c8  mov     rax, [rsi]
0x1400144cb  mov     rcx, rsi
0x1400144ce  mov     rax, [rax+18h]
0x1400144d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400144d7  mov     rax, [rsi]
0x1400144da  mov     rdx, r13
0x1400144dd  mov     rcx, rsi
0x1400144e0  mov     rax, [rax+58h]
0x1400144e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400144e9  mov     ecx, [rsi+28h]
0x1400144ec  xor     edx, edx
0x1400144ee  mov     r12, rax
0x1400144f1  div     rcx
0x1400144f4  mov     rcx, [rsi+8]
0x1400144f8  mov     r8d, edx
0x1400144fb  lea     r14, [rcx+r8*8]
0x1400144ff  mov     rdi, [r14]
0x140014502  test    rdi, rdi
0x140014505  jz      loc_1400145BC
0x14001450b  cmp     [rdi+18h], r12
0x14001450f  jnz     short loc_140014539
0x140014511  mov     rbx, [rsi]
0x140014514  mov     rdx, rdi
0x140014517  mov     rcx, rsi
0x14001451a  mov     rax, [rbx+50h]
0x14001451e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014523  mov     r8, rax
0x140014526  mov     rdx, r13
0x140014529  mov     rax, [rbx+60h]
0x14001452d  mov     rcx, rsi
0x140014530  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014535  test    eax, eax
0x140014537  jz      short loc_140014545
0x140014539  lea     r14, [rdi+10h]
0x14001453d  mov     rdi, [r14]
0x140014540  test    rdi, rdi
0x140014543  jnz     short loc_14001450B
0x140014545  test    rdi, rdi
0x140014548  jz      short loc_1400145BC
0x14001454a  mov     rax, [rsi]
0x14001454d  mov     rdx, rdi
0x140014550  mov     rcx, rsi
0x140014553  mov     rax, [rax+48h]
0x140014557  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001455c  test    eax, eax
0x14001455e  jnz     short loc_1400145BC
0x140014560  mov     rax, [rdi+10h]
0x140014564  mov     r15b, 1
0x140014567  mov     [r14], rax
0x14001456a  dec     dword ptr [rsi+30h]
0x14001456d  mov     ecx, [rsi+30h]
0x140014570  cmp     ecx, [rsi+2Ch]
0x140014573  jbe     short loc_140014587
0x140014575  mov     eax, [rsi+28h]
0x140014578  shr     eax, 2
0x14001457b  cmp     ecx, eax
0x14001457d  jnb     short loc_140014587
0x14001457f  mov     rcx, rsi; this
0x140014582  call    ?TryChangeTableSize@THashTableBase@NAdvancedLibrary@@AEAAXXZ; NAdvancedLibrary::THashTableBase::TryChangeTableSize(void)
0x140014587  mov     rax, [rsi]
0x14001458a  mov     rdx, rdi
0x14001458d  mov     rcx, rsi
0x140014590  mov     rax, [rax+40h]
0x140014594  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014599  test    eax, eax
0x14001459b  jnz     short loc_1400145BC
0x14001459d  mov     rcx, [rdi+8]
0x1400145a1  mov     rbp, rdi
0x1400145a4  mov     rax, [rdi]
0x1400145a7  mov     [rcx], rax
0x1400145aa  mov     rcx, [rdi]
0x1400145ad  mov     rax, [rdi+8]
0x1400145b1  mov     [rcx+8], rax
0x1400145b5  mov     [rdi+8], rdi
0x1400145b9  mov     [rdi], rdi
0x1400145bc  mov     rax, [rsi]
0x1400145bf  mov     rcx, rsi
0x1400145c2  mov     rax, [rax+20h]
0x1400145c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400145cb  mov     rax, [rsp+68h+arg_20]
0x1400145d3  test    rax, rax
0x1400145d6  jz      short loc_1400145DB
0x1400145d8  mov     [rax], r15b
0x1400145db  test    rbp, rbp
0x1400145de  jz      short loc_1400145EC
0x1400145e0  mov     rax, [rsi+20h]
0x1400145e4  mov     rcx, rbp
0x1400145e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400145ec  add     rsp, 28h
0x1400145f0  pop     r15
0x1400145f2  pop     r14
0x1400145f4  pop     r13
0x1400145f6  pop     r12
0x1400145f8  pop     rdi
0x1400145f9  pop     rsi
0x1400145fa  pop     rbp
0x1400145fb  pop     rbx
0x1400145fc  retn
```
