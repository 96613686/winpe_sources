# CSCardUserContext::~CSCardUserContext(void)

- ea: `0x180014760`
- end: `0x1800148ba`
- name: `??1CSCardUserContext@@UEAA@XZ`
- size: `346`
- prototype: `void __fastcall(CSCardUserContext *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180014720`

## callees

- `0x180014760`
- `0x180014f50`
- `0x18001685c`
- `0x18001b9b8`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800147f6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800147f6`
- `RPCRT4!RpcBindingFree` at `0x1800148a0`
- `RPCRT4!RpcBindingFree` at `0x1800148a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CSCardUserContext::~CSCardUserContext(CSCardUserContext *this)
{
  char *v2; // rbx
  unsigned int v3; // esi
  unsigned __int64 v4; // rdx
  void *v5; // rcx
  void (__fastcall ***v6)(_QWORD, __int64); // r14

  *(_QWORD *)this = &CSCardUserContext::`vftable';
  v2 = (char *)this + 72;
  (**((void (__fastcall ***)(char *, _QWORD, _QWORD))this + 9))((char *)this + 72, 0, 0);
  v3 = *((_DWORD *)this + 15);
  while ( v3 )
  {
    if ( *((_DWORD *)this + 15) > --v3 )
    {
      _mm_lfence();
      v6 = *(void (__fastcall ****)(_QWORD, __int64))(*((_QWORD *)this + 8) + 8LL * (int)v3);
      if ( v6 )
      {
        CDynamicArray<CSCardSubcontext>::Set((char *)this + 48, v3, 0);
        (**v6)(v6, 1);
      }
    }
  }
  *((_DWORD *)this + 15) = 0;
  if ( (unsigned __int64)(*((_QWORD *)this + 4) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    *((_QWORD *)this + 4) = 0;
  if ( *((_QWORD *)this + 18) )
    RpcBindingFree((RPC_BINDING_HANDLE *)this + 18);
  (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 8LL))(v2);
  *(_QWORD *)v2 = &CCriticalSectionObject::`vftable';
  if ( !*((_DWORD *)v2 + 12) )
    DeleteCriticalSection((LPCRITICAL_SECTION)(v2 + 8));
  *((_QWORD *)this + 6) = &CDynamicArray<CSCardSubcontext>::`vftable';
  v5 = (void *)*((_QWORD *)this + 8);
  if ( v5 )
  {
    operator delete(v5, v4);
    *((_QWORD *)this + 8) = 0;
    *((_QWORD *)this + 7) = 0;
  }
  if ( (unsigned __int64)(*((_QWORD *)this + 4) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    CHandleObject::Close((CSCardUserContext *)((char *)this + 32));
  *(_QWORD *)this = &CHandle::`vftable';
}

```

## disassembly

```asm
0x180014760  mov     [rsp+arg_8], rbx
0x180014765  mov     [rsp+arg_10], rbp
0x18001476a  mov     [rsp+arg_0], rcx
0x18001476f  push    rsi
0x180014770  push    rdi
0x180014771  push    r14
0x180014773  sub     rsp, 30h
0x180014777  mov     rdi, rcx
0x18001477a  lea     rax, ??_7CSCardUserContext@@6B@; const CSCardUserContext::`vftable'
0x180014781  mov     [rcx], rax
0x180014784  lea     rbx, [rcx+48h]
0x180014788  mov     [rsp+48h+var_28], rbx
0x18001478d  mov     rax, [rbx]
0x180014790  xor     r8d, r8d
0x180014793  xor     edx, edx
0x180014795  mov     rcx, rbx
0x180014798  mov     rax, [rax]
0x18001479b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800147a0  nop
0x1800147a1  mov     esi, [rdi+3Ch]
0x1800147a4  test    esi, esi
0x1800147a6  jnz     loc_180014850
0x1800147ac  xor     ebp, ebp
0x1800147ae  mov     [rdi+3Ch], ebp
0x1800147b1  mov     rax, [rdi+20h]
0x1800147b5  dec     rax
0x1800147b8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800147bc  jbe     loc_180014897
0x1800147c2  lea     rcx, [rdi+90h]; Binding
0x1800147c9  cmp     [rcx], rbp
0x1800147cc  jnz     loc_1800148A0
0x1800147d2  mov     rax, [rbx]
0x1800147d5  mov     rcx, rbx
0x1800147d8  mov     rax, [rax+8]
0x1800147dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800147e1  nop
0x1800147e2  lea     rax, ??_7CCriticalSectionObject@@6B@; const CCriticalSectionObject::`vftable'
0x1800147e9  mov     [rbx], rax
0x1800147ec  cmp     dword ptr [rbx+30h], 0
0x1800147f0  jnz     short loc_1800147FD
0x1800147f2  lea     rcx, [rbx+8]; lpCriticalSection
0x1800147f6  call    cs:__imp_DeleteCriticalSection
0x1800147fc  nop
0x1800147fd  lea     rax, ??_7?$CDynamicArray@VCSCardSubcontext@@@@6B@; const CDynamicArray<CSCardSubcontext>::`vftable'
0x180014804  mov     [rdi+30h], rax
0x180014808  mov     rcx, [rdi+40h]; void *
0x18001480c  test    rcx, rcx
0x18001480f  jz      short loc_18001481E
0x180014811  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014816  mov     [rdi+40h], rbp
0x18001481a  mov     [rdi+38h], rbp
0x18001481e  mov     rax, [rdi+20h]
0x180014822  dec     rax
0x180014825  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180014829  jbe     loc_1800148AB
0x18001482f  lea     rax, ??_7CHandle@@6B@; const CHandle::`vftable'
0x180014836  mov     [rdi], rax
0x180014839  mov     rbx, [rsp+48h+arg_8]
0x18001483e  mov     rbp, [rsp+48h+arg_10]
0x180014843  add     rsp, 30h
0x180014847  pop     r14
0x180014849  pop     rdi
0x18001484a  pop     rsi
0x18001484b  retn
0x180014850  lea     rcx, [rdi+30h]
0x180014854  dec     esi
0x180014856  cmp     [rcx+0Ch], esi
0x180014859  jbe     short loc_18001486E
0x18001485b  lfence
0x18001485e  movsxd  rdx, esi
0x180014861  mov     rax, [rcx+10h]
0x180014865  mov     r14, [rax+rdx*8]
0x180014869  test    r14, r14
0x18001486c  jnz     short loc_180014878
0x18001486e  test    esi, esi
0x180014870  jz      loc_1800147AC
0x180014876  jmp     short loc_180014850
0x180014878  xor     r8d, r8d
0x18001487b  mov     edx, esi
0x18001487d  call    ?Set@?$CDynamicArray@VCSCardSubcontext@@@@QEAAPEAVCSCardSubcontext@@HPEAV2@@Z; CDynamicArray<CSCardSubcontext>::Set(int,CSCardSubcontext *)
0x180014882  mov     rax, [r14]
0x180014885  mov     edx, 1
0x18001488a  mov     rcx, r14
0x18001488d  mov     rax, [rax]
0x180014890  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014895  jmp     short loc_18001486E
0x180014897  mov     [rdi+20h], rbp
0x18001489b  jmp     loc_1800147C2
0x1800148a0  call    cs:__imp_RpcBindingFree
0x1800148a6  jmp     loc_1800147D2
0x1800148ab  lea     rcx, [rdi+20h]; this
0x1800148af  call    ?Close@CHandleObject@@QEAAKXZ; CHandleObject::Close(void)
0x1800148b4  jmp     loc_18001482F
```
