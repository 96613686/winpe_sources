# CEventSink::CreateEventSet(ITypeInfo *)

- ea: `0x18005a128`
- end: `0x18005a30e`
- name: `?CreateEventSet@CEventSink@@AEAAJPEAUITypeInfo@@@Z`
- size: `486`
- prototype: `__int64 __fastcall(CEventSink *__hidden this, struct ITypeInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18005a014`

## callees

- `0x18005a128`
- `0x18005a5b0`
- `0x18005aa2c`
- `0x180079436`
- `0x18007a010`

## import_xrefs

- `msvcrt!malloc` at `0x18005a1d3`
- `msvcrt!malloc` at `0x18005a1d3`

## pseudocode

```c
__int64 __fastcall CEventSink::CreateEventSet(CEventSink *this, struct ITypeInfo *a2)
{
  struct ITypeInfoVtbl *lpVtbl; // rax
  ULONG (__stdcall *AddRef)(ITypeInfo *); // rax
  int SourceTypeInfo; // ebx
  __int64 v7; // rdi
  unsigned int v8; // eax
  size_t v9; // rbx
  void *v10; // rax
  unsigned int i; // edi
  __int64 v12; // r15
  __int64 v13; // r8
  __int64 v14; // rdx
  struct ITypeInfo *v15; // rcx
  __int64 v17; // [rsp+30h] [rbp-10h] BYREF
  int v18; // [rsp+78h] [rbp+38h] BYREF
  struct ITypeInfo *v19; // [rsp+80h] [rbp+40h] BYREF
  unsigned int *v20; // [rsp+88h] [rbp+48h] BYREF

  lpVtbl = a2->lpVtbl;
  v18 = 0;
  v20 = 0;
  v17 = 0;
  AddRef = lpVtbl->AddRef;
  v19 = 0;
  ((void (__fastcall *)(struct ITypeInfo *))AddRef)(a2);
  SourceTypeInfo = GetSourceTypeInfo(a2, &v19);
  if ( SourceTypeInfo >= 0 )
  {
    SourceTypeInfo = ((__int64 (__fastcall *)(struct ITypeInfo *, __int64 *))v19->lpVtbl->GetTypeAttr)(v19, &v17);
    if ( SourceTypeInfo >= 0 )
    {
      v7 = v17;
      if ( *(_DWORD *)(v17 + 44) != 4
        || (*(_OWORD *)((char *)this + 40) = *(_OWORD *)v17,
            v8 = *(unsigned __int16 *)(v7 + 48),
            (*((_DWORD *)this + 22) = v8) == 0) )
      {
        SourceTypeInfo = -2147467262;
        goto LABEL_15;
      }
      v9 = 32LL * v8;
      v10 = malloc(v9);
      *((_QWORD *)this + 10) = v10;
      if ( !v10 )
      {
        SourceTypeInfo = -2147024882;
        goto LABEL_15;
      }
      memset_0(v10, 0, v9);
      for ( i = 0; (signed int)i < *((_DWORD *)this + 22); ++i )
      {
        v12 = *((_QWORD *)this + 10);
        SourceTypeInfo = ((__int64 (__fastcall *)(struct ITypeInfo *, _QWORD, unsigned int **))v19->lpVtbl->GetFuncDesc)(
                           v19,
                           i,
                           &v20);
        if ( SourceTypeInfo < 0 )
          goto LABEL_14;
        v13 = 32LL * (int)i;
        v14 = *v20;
        *(_DWORD *)(v13 + v12) = v14;
        SourceTypeInfo = ((__int64 (__fastcall *)(struct ITypeInfo *, __int64, __int64, __int64, int *))v19->lpVtbl->GetNames)(
                           v19,
                           v14,
                           v12 + v13 + 8,
                           1,
                           &v18);
        if ( SourceTypeInfo < 0 )
          goto LABEL_14;
        ((void (__fastcall *)(struct ITypeInfo *, unsigned int *))v19->lpVtbl->ReleaseFuncDesc)(v19, v20);
        v20 = 0;
      }
      SourceTypeInfo = 0;
      CEventSink::Sort(this);
    }
  }
LABEL_14:
  v7 = v17;
LABEL_15:
  v15 = v19;
  if ( v19 )
  {
    if ( v20 )
    {
      ((void (*)(void))v19->lpVtbl->ReleaseFuncDesc)();
      v15 = v19;
      v7 = v17;
    }
    if ( v7 )
    {
      ((void (__fastcall *)(struct ITypeInfo *, __int64))v15->lpVtbl->ReleaseTypeAttr)(v15, v7);
      v15 = v19;
    }
    ((void (__fastcall *)(struct ITypeInfo *))v15->lpVtbl->Release)(v15);
  }
  ((void (__fastcall *)(struct ITypeInfo *))a2->lpVtbl->Release)(a2);
  return (unsigned int)SourceTypeInfo;
}

```

## disassembly

```asm
0x18005a128  mov     [rsp-28h+arg_0], rbx
0x18005a12d  push    rbp
0x18005a12e  push    rsi
0x18005a12f  push    rdi
0x18005a130  push    r14
0x18005a132  push    r15
0x18005a134  mov     rbp, rsp
0x18005a137  sub     rsp, 40h
0x18005a13b  mov     rax, [rdx]
0x18005a13e  mov     rsi, rcx
0x18005a141  mov     rcx, rdx
0x18005a144  mov     [rbp+arg_8], 0
0x18005a14b  mov     r14, rdx
0x18005a14e  mov     [rbp+arg_18], 0
0x18005a156  mov     [rbp+var_10], 0
0x18005a15e  mov     rax, [rax+8]
0x18005a162  mov     [rbp+arg_10], 0
0x18005a16a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a16f  lea     rdx, [rbp+arg_10]; struct ITypeInfo **
0x18005a173  mov     rcx, r14; struct ITypeInfo *
0x18005a176  call    ?GetSourceTypeInfo@@YAJPEAUITypeInfo@@PEAPEAU1@@Z; GetSourceTypeInfo(ITypeInfo *,ITypeInfo * *)
0x18005a17b  mov     ebx, eax
0x18005a17d  test    eax, eax
0x18005a17f  js      loc_18005A297
0x18005a185  mov     rcx, [rbp+arg_10]
0x18005a189  lea     rdx, [rbp+var_10]
0x18005a18d  mov     rax, [rcx]
0x18005a190  mov     rax, [rax+18h]
0x18005a194  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a199  mov     ebx, eax
0x18005a19b  test    eax, eax
0x18005a19d  js      loc_18005A297
0x18005a1a3  mov     rdi, [rbp+var_10]
0x18005a1a7  cmp     dword ptr [rdi+2Ch], 4
0x18005a1ab  jz      short loc_18005A1B7
0x18005a1ad  mov     ebx, 80004002h
0x18005a1b2  jmp     loc_18005A29B
0x18005a1b7  movups  xmm0, xmmword ptr [rdi]
0x18005a1ba  movdqu  xmmword ptr [rsi+28h], xmm0
0x18005a1bf  movzx   eax, word ptr [rdi+30h]
0x18005a1c3  mov     [rsi+58h], eax
0x18005a1c6  test    eax, eax
0x18005a1c8  jz      short loc_18005A1AD
0x18005a1ca  mov     ebx, eax
0x18005a1cc  shl     rbx, 5
0x18005a1d0  mov     rcx, rbx; Size
0x18005a1d3  call    cs:__imp_malloc
0x18005a1da  nop     dword ptr [rax+rax+00h]
0x18005a1df  mov     [rsi+50h], rax
0x18005a1e3  test    rax, rax
0x18005a1e6  jnz     short loc_18005A1F2
0x18005a1e8  mov     ebx, 8007000Eh
0x18005a1ed  jmp     loc_18005A29B
0x18005a1f2  mov     r8, rbx; Size
0x18005a1f5  xor     edx, edx; Val
0x18005a1f7  mov     rcx, rax; void *
0x18005a1fa  call    memset_0
0x18005a1ff  xor     edi, edi
0x18005a201  cmp     edi, [rsi+58h]
0x18005a204  jge     loc_18005A28D
0x18005a20a  mov     rcx, [rbp+arg_10]
0x18005a20e  lea     r8, [rbp+arg_18]
0x18005a212  mov     r15, [rsi+50h]
0x18005a216  mov     edx, edi
0x18005a218  mov     rax, [rcx]
0x18005a21b  mov     rax, [rax+28h]
0x18005a21f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a224  mov     ebx, eax
0x18005a226  test    eax, eax
0x18005a228  js      short loc_18005A297
0x18005a22a  mov     rax, [rbp+arg_18]
0x18005a22e  lea     r9, [rbp+arg_8]
0x18005a232  mov     [rsp+40h+var_20], r9
0x18005a237  mov     r9d, 1
0x18005a23d  movsxd  r8, edi
0x18005a240  shl     r8, 5
0x18005a244  mov     edx, [rax]
0x18005a246  mov     [r8+r15], edx
0x18005a24a  add     r8, 8
0x18005a24e  mov     rcx, [rbp+arg_10]
0x18005a252  add     r8, r15
0x18005a255  mov     rax, [rcx]
0x18005a258  mov     rax, [rax+38h]
0x18005a25c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a261  mov     ebx, eax
0x18005a263  test    eax, eax
0x18005a265  js      short loc_18005A297
0x18005a267  mov     rcx, [rbp+arg_10]
0x18005a26b  mov     rdx, [rbp+arg_18]
0x18005a26f  mov     rax, [rcx]
0x18005a272  mov     rax, [rax+0A0h]
0x18005a279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a27e  inc     edi
0x18005a280  mov     [rbp+arg_18], 0
0x18005a288  jmp     loc_18005A201
0x18005a28d  xor     ebx, ebx
0x18005a28f  mov     rcx, rsi; this
0x18005a292  call    ?Sort@CEventSink@@AEAAXXZ; CEventSink::Sort(void)
0x18005a297  mov     rdi, [rbp+var_10]
0x18005a29b  mov     rcx, [rbp+arg_10]
0x18005a29f  test    rcx, rcx
0x18005a2a2  jz      short loc_18005A2EB
0x18005a2a4  mov     rdx, [rbp+arg_18]
0x18005a2a8  test    rdx, rdx
0x18005a2ab  jz      short loc_18005A2C4
0x18005a2ad  mov     rax, [rcx]
0x18005a2b0  mov     rax, [rax+0A0h]
0x18005a2b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a2bc  mov     rcx, [rbp+arg_10]
0x18005a2c0  mov     rdi, [rbp+var_10]
0x18005a2c4  test    rdi, rdi
0x18005a2c7  jz      short loc_18005A2DF
0x18005a2c9  mov     rax, [rcx]
0x18005a2cc  mov     rdx, rdi
0x18005a2cf  mov     rax, [rax+98h]
0x18005a2d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a2db  mov     rcx, [rbp+arg_10]
0x18005a2df  mov     rax, [rcx]
0x18005a2e2  mov     rax, [rax+10h]
0x18005a2e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a2eb  mov     rax, [r14]
0x18005a2ee  mov     rcx, r14
0x18005a2f1  mov     rax, [rax+10h]
0x18005a2f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a2fa  mov     eax, ebx
0x18005a2fc  mov     rbx, [rsp+40h+arg_0]
0x18005a301  add     rsp, 40h
0x18005a305  pop     r15
0x18005a307  pop     r14
0x18005a309  pop     rdi
0x18005a30a  pop     rsi
0x18005a30b  pop     rbp
0x18005a30c  retn
```
