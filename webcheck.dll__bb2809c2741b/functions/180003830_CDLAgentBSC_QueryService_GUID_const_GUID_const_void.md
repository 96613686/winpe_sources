# CDLAgentBSC::QueryService(_GUID const &,_GUID const &,void * *)

- ea: `0x180003830`
- end: `0x1800038ef`
- name: `?QueryService@CDLAgentBSC@@UEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `191`
- prototype: `__int64 __fastcall(CDLAgentBSC *__hidden this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003830`
- `0x18002a010`

## import_xrefs

- `urlmon!CoInternetCreateSecurityManager` at `0x1800038ab`
- `urlmon!CoInternetCreateSecurityManager` at `0x1800038ab`

## pseudocode

```c
__int64 __fastcall CDLAgentBSC::QueryService(
        IInternetSecurityManager **this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 v7; // rax
  __int64 v8; // rax
  unsigned int SecurityManager; // ebx
  IInternetSecurityManager **v10; // rdi
  _QWORD *v11; // rsi

  if ( !a4 )
    return 2147942487LL;
  *a4 = 0;
  v7 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IInternetHostSecurityManager.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IInternetHostSecurityManager.Data1 )
    v7 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IInternetHostSecurityManager.Data4;
  if ( v7 )
    return (unsigned int)-2147467262;
  v8 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IInternetHostSecurityManager.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IInternetHostSecurityManager.Data1 )
    v8 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IInternetHostSecurityManager.Data4;
  if ( v8 )
    return (unsigned int)-2147467262;
  SecurityManager = 0;
  v10 = this - 1;
  v11 = this + 527;
  if ( !this[527] )
    SecurityManager = CoInternetCreateSecurityManager(0, this + 527, 0);
  if ( !*v11 )
  {
    return (unsigned int)-2147467262;
  }
  else
  {
    *a4 = (void *)((unsigned __int64)(this + 1) & ((unsigned __int128)-(__int128)(unsigned __int64)v10 >> 64));
    ((void (__fastcall *)(IInternetSecurityManager **))(*v10)[1].lpVtbl)(v10);
  }
  return SecurityManager;
}

```

## disassembly

```asm
0x180003830  push    rbx
0x180003832  push    rbp
0x180003833  push    rsi
0x180003834  push    rdi
0x180003835  push    r14
0x180003837  sub     rsp, 20h
0x18000383b  mov     r14, r9
0x18000383e  mov     rbp, rcx
0x180003841  test    r9, r9
0x180003844  jnz     short loc_180003850
0x180003846  mov     eax, 80070057h
0x18000384b  jmp     loc_1800038E4
0x180003850  mov     qword ptr [r9], 0
0x180003857  mov     rax, [rdx]
0x18000385a  mov     r9, qword ptr cs:IID_IInternetHostSecurityManager.Data1
0x180003861  mov     rcx, qword ptr cs:IID_IInternetHostSecurityManager.Data4
0x180003868  sub     rax, r9
0x18000386b  jnz     short loc_180003874
0x18000386d  mov     rax, [rdx+8]
0x180003871  sub     rax, rcx
0x180003874  test    rax, rax
0x180003877  jnz     short loc_1800038DD
0x180003879  mov     rax, [r8]
0x18000387c  sub     rax, r9
0x18000387f  jnz     short loc_180003888
0x180003881  mov     rax, [r8+8]
0x180003885  sub     rax, rcx
0x180003888  test    rax, rax
0x18000388b  jnz     short loc_1800038DD
0x18000388d  xor     ebx, ebx
0x18000388f  lea     rdi, [rbp-8]
0x180003893  lea     rsi, [rbp+1078h]
0x18000389a  cmp     [rdi+1080h], rbx
0x1800038a1  jnz     short loc_1800038B3
0x1800038a3  xor     r8d, r8d; dwReserved
0x1800038a6  mov     rdx, rsi; ppSM
0x1800038a9  xor     ecx, ecx; pSP
0x1800038ab  call    cs:__imp_CoInternetCreateSecurityManager
0x1800038b1  mov     ebx, eax
0x1800038b3  cmp     qword ptr [rsi], 0
0x1800038b7  jz      short loc_1800038DD
0x1800038b9  lea     r8, [rbp+8]
0x1800038bd  mov     rax, rdi
0x1800038c0  neg     rax
0x1800038c3  mov     rcx, rdi
0x1800038c6  sbb     rdx, rdx
0x1800038c9  and     rdx, r8
0x1800038cc  mov     [r14], rdx
0x1800038cf  mov     rax, [rdi]
0x1800038d2  mov     rax, [rax+8]
0x1800038d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038db  jmp     short loc_1800038E2
0x1800038dd  mov     ebx, 80004002h
0x1800038e2  mov     eax, ebx
0x1800038e4  add     rsp, 20h
0x1800038e8  pop     r14
0x1800038ea  pop     rdi
0x1800038eb  pop     rsi
0x1800038ec  pop     rbp
0x1800038ed  pop     rbx
0x1800038ee  retn
```
