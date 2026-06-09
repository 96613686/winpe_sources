# STATIC_META_STORED_CONTEXT::GetParsedMetadata(IHttpContext *,STATIC_META_STORED_CONTEXT * *,INativeSectionException * *)

- ea: `0x180004590`
- end: `0x1800046fb`
- name: `?GetParsedMetadata@STATIC_META_STORED_CONTEXT@@SAJPEAVIHttpContext@@PEAPEAV1@PEAPEAVINativeSectionException@@@Z`
- size: `363`
- prototype: `__int64 __fastcall(struct IHttpContext *, struct STATIC_META_STORED_CONTEXT **, struct INativeSectionException **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800028e0`

## callees

- `0x180001358`
- `0x180004590`
- `0x180004704`
- `0x180007010`

## import_xrefs

- `iisutil!??0STRU@@QEAA@XZ` at `0x180004638`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180004638`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18000460d`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180004617`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18000462b`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18000460d`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180004617`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18000462b`

## pseudocode

```c
__int64 __fastcall STATIC_META_STORED_CONTEXT::GetParsedMetadata(
        struct IHttpContext *a1,
        struct STATIC_META_STORED_CONTEXT **a2,
        struct INativeSectionException **a3)
{
  __int64 v6; // rax
  __int64 v7; // rsi
  _DWORD *v8; // rbx
  int v9; // edi

  v6 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 160LL))(a1);
  v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 24LL))(v6);
  v8 = (_DWORD *)(**(__int64 (__fastcall ***)(__int64, void *))v7)(v7, g_pStaticFileModuleContext);
  if ( v8 )
    goto LABEL_2;
  v8 = operator new(0x120u);
  if ( v8 )
  {
    *(_QWORD *)v8 = &STATIC_META_STORED_CONTEXT::`vftable';
    STRA::STRA((STRA *)(v8 + 2));
    STRA::STRA((STRA *)(v8 + 16));
    v8[30] = 0;
    STRA::STRA((STRA *)(v8 + 32));
    STRU::STRU((STRU *)(v8 + 46));
    *((_QWORD *)v8 + 32) = 0;
    *((_QWORD *)v8 + 30) = &MIME_MAP::`vftable';
    *((_QWORD *)v8 + 34) = 0;
    v8[71] = 1;
    v9 = STATIC_META_STORED_CONTEXT::Initialize((STATIC_META_STORED_CONTEXT *)v8, a1, a3);
    if ( v9 < 0 )
    {
      (**(void (__fastcall ***)(void *))v8)(v8);
      return (unsigned int)v9;
    }
    v9 = (*(__int64 (__fastcall **)(__int64, _DWORD *, void *))(*(_QWORD *)v7 + 8LL))(
           v7,
           v8,
           g_pStaticFileModuleContext);
    if ( v9 >= 0 )
    {
LABEL_10:
      *a2 = (struct STATIC_META_STORED_CONTEXT *)v8;
      return (unsigned int)v9;
    }
    (**(void (__fastcall ***)(void *))v8)(v8);
    if ( v9 != -2147024811 )
    {
      v8 = 0;
      goto LABEL_10;
    }
    v8 = (_DWORD *)(**(__int64 (__fastcall ***)(__int64, void *))v7)(v7, g_pStaticFileModuleContext);
LABEL_2:
    v9 = 0;
    goto LABEL_10;
  }
  return 2147942408LL;
}

```

## disassembly

```asm
0x180004590  push    rbx
0x180004592  push    rbp
0x180004593  push    rsi
0x180004594  push    rdi
0x180004595  push    r14
0x180004597  sub     rsp, 20h
0x18000459b  mov     rax, [rcx]
0x18000459e  mov     rbp, r8
0x1800045a1  mov     r14, rdx
0x1800045a4  mov     rdi, rcx
0x1800045a7  mov     rax, [rax+0A0h]
0x1800045ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045b3  mov     rcx, rax
0x1800045b6  mov     r9, [rax]
0x1800045b9  mov     rax, [r9+18h]
0x1800045bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045c2  mov     rdx, cs:?g_pStaticFileModuleContext@@3PEAXEA; void * g_pStaticFileModuleContext
0x1800045c9  mov     rsi, rax
0x1800045cc  mov     rcx, [rax]
0x1800045cf  mov     rax, [rcx]
0x1800045d2  mov     rcx, rsi
0x1800045d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045da  mov     rbx, rax
0x1800045dd  test    rax, rax
0x1800045e0  jz      short loc_1800045E9
0x1800045e2  xor     edi, edi
0x1800045e4  jmp     loc_1800046E4
0x1800045e9  mov     ecx, 120h; Size
0x1800045ee  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800045f3  mov     rbx, rax
0x1800045f6  test    rax, rax
0x1800045f9  jz      loc_1800046EB
0x1800045ff  lea     rax, ??_7STATIC_META_STORED_CONTEXT@@6B@; const STATIC_META_STORED_CONTEXT::`vftable'
0x180004606  lea     rcx, [rbx+8]
0x18000460a  mov     [rbx], rax
0x18000460d  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180004613  lea     rcx, [rbx+40h]
0x180004617  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x18000461d  lea     rcx, [rbx+80h]
0x180004624  mov     dword ptr [rbx+78h], 0
0x18000462b  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180004631  lea     rcx, [rbx+0B8h]
0x180004638  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000463e  mov     qword ptr [rbx+100h], 0
0x180004649  lea     rax, ??_7MIME_MAP@@6B@; const MIME_MAP::`vftable'
0x180004650  mov     [rbx+0F0h], rax
0x180004657  mov     r8, rbp; struct INativeSectionException **
0x18000465a  mov     qword ptr [rbx+110h], 0
0x180004665  mov     rdx, rdi; struct IHttpContext *
0x180004668  mov     rcx, rbx; this
0x18000466b  mov     dword ptr [rbx+11Ch], 1
0x180004675  call    ?Initialize@STATIC_META_STORED_CONTEXT@@IEAAJPEAVIHttpContext@@PEAPEAVINativeSectionException@@@Z; STATIC_META_STORED_CONTEXT::Initialize(IHttpContext *,INativeSectionException * *)
0x18000467a  mov     edi, eax
0x18000467c  test    eax, eax
0x18000467e  jns     short loc_180004690
0x180004680  mov     rcx, [rbx]
0x180004683  mov     rax, [rcx]
0x180004686  mov     rcx, rbx
0x180004689  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000468e  jmp     short loc_1800046E7
0x180004690  mov     rax, [rsi]
0x180004693  mov     rdx, rbx
0x180004696  mov     r8, cs:?g_pStaticFileModuleContext@@3PEAXEA; void * g_pStaticFileModuleContext
0x18000469d  mov     rcx, rsi
0x1800046a0  mov     rax, [rax+8]
0x1800046a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046a9  mov     edi, eax
0x1800046ab  test    eax, eax
0x1800046ad  jns     short loc_1800046E4
0x1800046af  mov     rcx, [rbx]
0x1800046b2  mov     rax, [rcx]
0x1800046b5  mov     rcx, rbx
0x1800046b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046bd  cmp     edi, 80070055h
0x1800046c3  jnz     short loc_1800046E2
0x1800046c5  mov     rax, [rsi]
0x1800046c8  mov     rcx, rsi
0x1800046cb  mov     rdx, cs:?g_pStaticFileModuleContext@@3PEAXEA; void * g_pStaticFileModuleContext
0x1800046d2  mov     rax, [rax]
0x1800046d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046da  mov     rbx, rax
0x1800046dd  jmp     loc_1800045E2
0x1800046e2  xor     ebx, ebx
0x1800046e4  mov     [r14], rbx
0x1800046e7  mov     eax, edi
0x1800046e9  jmp     short loc_1800046F0
0x1800046eb  mov     eax, 80070008h
0x1800046f0  add     rsp, 20h
0x1800046f4  pop     r14
0x1800046f6  pop     rdi
0x1800046f7  pop     rsi
0x1800046f8  pop     rbp
0x1800046f9  pop     rbx
0x1800046fa  retn
```
