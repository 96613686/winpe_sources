# CEventSink::CreateEventSet(ITypeInfo *)

- ea: `0x180058628`
- end: `0x180058807`
- name: `?CreateEventSet@CEventSink@@AEAAJPEAUITypeInfo@@@Z`
- size: `479`
- prototype: `__int64 __fastcall(CEventSink *__hidden this, struct ITypeInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18005851c`

## callees

- `0x180058628`
- `0x180058aa8`
- `0x180058f0c`
- `0x180076746`
- `0x180077010`

## import_xrefs

- `msvcrt!malloc` at `0x1800586d3`
- `msvcrt!malloc` at `0x1800586d3`

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
0x180058628  mov     [rsp-28h+arg_0], rbx
0x18005862d  push    rbp
0x18005862e  push    rsi
0x18005862f  push    rdi
0x180058630  push    r14
0x180058632  push    r15
0x180058634  mov     rbp, rsp
0x180058637  sub     rsp, 40h
0x18005863b  mov     rax, [rdx]
0x18005863e  mov     rsi, rcx
0x180058641  mov     rcx, rdx
0x180058644  mov     [rbp+arg_8], 0
0x18005864b  mov     r14, rdx
0x18005864e  mov     [rbp+arg_18], 0
0x180058656  mov     [rbp+var_10], 0
0x18005865e  mov     rax, [rax+8]
0x180058662  mov     [rbp+arg_10], 0
0x18005866a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005866f  lea     rdx, [rbp+arg_10]; struct ITypeInfo **
0x180058673  mov     rcx, r14; struct ITypeInfo *
0x180058676  call    ?GetSourceTypeInfo@@YAJPEAUITypeInfo@@PEAPEAU1@@Z; GetSourceTypeInfo(ITypeInfo *,ITypeInfo * *)
0x18005867b  mov     ebx, eax
0x18005867d  test    eax, eax
0x18005867f  js      loc_180058791
0x180058685  mov     rcx, [rbp+arg_10]
0x180058689  lea     rdx, [rbp+var_10]
0x18005868d  mov     rax, [rcx]
0x180058690  mov     rax, [rax+18h]
0x180058694  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058699  mov     ebx, eax
0x18005869b  test    eax, eax
0x18005869d  js      loc_180058791
0x1800586a3  mov     rdi, [rbp+var_10]
0x1800586a7  cmp     dword ptr [rdi+2Ch], 4
0x1800586ab  jz      short loc_1800586B7
0x1800586ad  mov     ebx, 80004002h
0x1800586b2  jmp     loc_180058795
0x1800586b7  movups  xmm0, xmmword ptr [rdi]
0x1800586ba  movdqu  xmmword ptr [rsi+28h], xmm0
0x1800586bf  movzx   eax, word ptr [rdi+30h]
0x1800586c3  mov     [rsi+58h], eax
0x1800586c6  test    eax, eax
0x1800586c8  jz      short loc_1800586AD
0x1800586ca  mov     ebx, eax
0x1800586cc  shl     rbx, 5
0x1800586d0  mov     rcx, rbx; Size
0x1800586d3  call    cs:__imp_malloc
0x1800586d9  mov     [rsi+50h], rax
0x1800586dd  test    rax, rax
0x1800586e0  jnz     short loc_1800586EC
0x1800586e2  mov     ebx, 8007000Eh
0x1800586e7  jmp     loc_180058795
0x1800586ec  mov     r8, rbx; Size
0x1800586ef  xor     edx, edx; Val
0x1800586f1  mov     rcx, rax; void *
0x1800586f4  call    memset_0
0x1800586f9  xor     edi, edi
0x1800586fb  cmp     edi, [rsi+58h]
0x1800586fe  jge     loc_180058787
0x180058704  mov     rcx, [rbp+arg_10]
0x180058708  lea     r8, [rbp+arg_18]
0x18005870c  mov     r15, [rsi+50h]
0x180058710  mov     edx, edi
0x180058712  mov     rax, [rcx]
0x180058715  mov     rax, [rax+28h]
0x180058719  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005871e  mov     ebx, eax
0x180058720  test    eax, eax
0x180058722  js      short loc_180058791
0x180058724  mov     rax, [rbp+arg_18]
0x180058728  lea     r9, [rbp+arg_8]
0x18005872c  mov     [rsp+40h+var_20], r9
0x180058731  mov     r9d, 1
0x180058737  movsxd  r8, edi
0x18005873a  shl     r8, 5
0x18005873e  mov     edx, [rax]
0x180058740  mov     [r8+r15], edx
0x180058744  add     r8, 8
0x180058748  mov     rcx, [rbp+arg_10]
0x18005874c  add     r8, r15
0x18005874f  mov     rax, [rcx]
0x180058752  mov     rax, [rax+38h]
0x180058756  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005875b  mov     ebx, eax
0x18005875d  test    eax, eax
0x18005875f  js      short loc_180058791
0x180058761  mov     rcx, [rbp+arg_10]
0x180058765  mov     rdx, [rbp+arg_18]
0x180058769  mov     rax, [rcx]
0x18005876c  mov     rax, [rax+0A0h]
0x180058773  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058778  inc     edi
0x18005877a  mov     [rbp+arg_18], 0
0x180058782  jmp     loc_1800586FB
0x180058787  xor     ebx, ebx
0x180058789  mov     rcx, rsi; this
0x18005878c  call    ?Sort@CEventSink@@AEAAXXZ; CEventSink::Sort(void)
0x180058791  mov     rdi, [rbp+var_10]
0x180058795  mov     rcx, [rbp+arg_10]
0x180058799  test    rcx, rcx
0x18005879c  jz      short loc_1800587E5
0x18005879e  mov     rdx, [rbp+arg_18]
0x1800587a2  test    rdx, rdx
0x1800587a5  jz      short loc_1800587BE
0x1800587a7  mov     rax, [rcx]
0x1800587aa  mov     rax, [rax+0A0h]
0x1800587b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800587b6  mov     rcx, [rbp+arg_10]
0x1800587ba  mov     rdi, [rbp+var_10]
0x1800587be  test    rdi, rdi
0x1800587c1  jz      short loc_1800587D9
0x1800587c3  mov     rax, [rcx]
0x1800587c6  mov     rdx, rdi
0x1800587c9  mov     rax, [rax+98h]
0x1800587d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800587d5  mov     rcx, [rbp+arg_10]
0x1800587d9  mov     rax, [rcx]
0x1800587dc  mov     rax, [rax+10h]
0x1800587e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800587e5  mov     rax, [r14]
0x1800587e8  mov     rcx, r14
0x1800587eb  mov     rax, [rax+10h]
0x1800587ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800587f4  mov     eax, ebx
0x1800587f6  mov     rbx, [rsp+40h+arg_0]
0x1800587fb  add     rsp, 40h
0x1800587ff  pop     r15
0x180058801  pop     r14
0x180058803  pop     rdi
0x180058804  pop     rsi
0x180058805  pop     rbp
0x180058806  retn
```
