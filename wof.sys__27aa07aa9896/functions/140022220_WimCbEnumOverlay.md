# WimCbEnumOverlay

- ea: `0x140022220`
- end: `0x1400224f9`
- name: `WimCbEnumOverlay`
- size: `729`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int *, unsigned int, char, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140026fb0`

## callees

- `0x14000fb90`
- `0x140011590`
- `0x1400115b0`
- `0x140022220`
- `0x140022500`
- `0x140022fcc`
- `0x1400230a8`
- `0x140023150`
- `0x140023198`
- `0x1400231dc`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002229e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400223f1`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140022418`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140022451`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002229e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400223f1`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140022418`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140022451`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140022255`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400222ae`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140022430`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140022255`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400222ae`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140022430`

## pseudocode

```c
__int64 __fastcall WimCbEnumOverlay(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int *a4,
        unsigned int a5,
        char a6,
        unsigned int *a7)
{
  int v8; // r15d
  unsigned int v9; // r12d
  unsigned int *v10; // rbx
  __int64 i; // rdi
  unsigned int v12; // r15d
  _QWORD *v13; // rcx
  unsigned int v14; // eax
  unsigned int *v15; // rcx
  unsigned int v16; // eax
  unsigned int *v17; // rcx
  size_t v18; // r8
  void *v19; // rdx
  void *v20; // rcx
  _WORD *v21; // rcx
  void *v22; // rdx
  void *v23; // rcx
  __int64 v24; // r8
  unsigned int v25; // edi
  int v27; // [rsp+60h] [rbp+8h]

  v8 = 0;
  v27 = 0;
  v9 = 0;
  v10 = 0;
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a1 - (unsigned int)dword_14001A2FC));
  for ( i = *(_QWORD *)(a1 + 16); i != a1 + 8; i = *(_QWORD *)(i + 8) )
  {
    if ( (*(_DWORD *)(i + 40) & 6) == 0 )
    {
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a1 - (unsigned int)dword_14001A2FC));
      ExAcquireFastMutexUnsafe((PFAST_MUTEX)(i + 112));
      v12 = (*(unsigned __int16 *)(i + 56) + 57) & 0xFFFFFFF8;
      v9 += v12;
      if ( v9 <= a5 )
      {
        v10 = a4;
        a4 = (unsigned int *)((char *)a4 + v12);
        if ( a6 )
          RtlSetUserMemory(v10);
        else
          RtlSetVolatileMemory(v10, 0, 0x30u);
        if ( a6 )
          RtlWriteULongToUser(v10, v12);
        else
          *v10 = v12;
        v13 = v10 + 2;
        if ( a6 )
          RtlWriteULong64ToUser(v13, *(_QWORD *)(i + 88));
        else
          *v13 = *(_QWORD *)(i + 88);
        v14 = *(_DWORD *)(i + 52);
        v15 = v10 + 10;
        if ( a6 )
          RtlWriteULongToUser(v15, v14);
        else
          *v15 = v14;
        v16 = *(_DWORD *)(i + 48);
        v17 = v10 + 9;
        if ( a6 )
          RtlWriteULongToUser(v17, v16);
        else
          *v17 = v16;
        if ( a6 )
          RtlWriteULongToUser(v10 + 8, 48);
        else
          v10[8] = 48;
        v18 = *(unsigned __int16 *)(i + 56);
        v19 = *(void **)(i + 64);
        v20 = v10 + 12;
        if ( a6 )
          RtlCopyToUser(v20, v19, v18);
        else
          RtlCopyVolatileMemory(v20, v19, v18);
        v21 = (_WORD *)v10 + ((unsigned __int64)*(unsigned __int16 *)(i + 56) >> 1) + 24;
        if ( a6 )
          RtlWriteUShortToUser(v21, 0);
        else
          *v21 = 0;
        v22 = (void *)(i + 72);
        v23 = v10 + 4;
        if ( a6 )
          RtlCopyToUser(v23, v22, 0x10u);
        else
          RtlCopyVolatileMemory(v23, v22, 0x10u);
        LOBYTE(v24) = a6;
        WimFSFGetOverlayFlags(i, v10 + 11, v24);
      }
      v8 = ++v27;
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)(i + 112));
      ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a1 - (unsigned int)dword_14001A2FC));
    }
  }
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a1 - (unsigned int)dword_14001A2FC));
  if ( v8 )
  {
    v25 = a5 < v9 ? 0xC0000023 : 0;
    if ( v9 <= a5 && v10 )
    {
      if ( a6 )
        RtlWriteULongToUser(v10, 0);
      else
        *v10 = 0;
    }
    *a7 = v9;
  }
  else
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_Z(
        WPP_GLOBAL_Control->AttachedDevice,
        18,
        WPP_ea753fa6f9d83b7566c7b1a5ff90ffd6_Traceguids,
        a1 - (unsigned int)dword_14001A2FC + 64,
        i);
    return (unsigned int)-1073741809;
  }
  return v25;
}

```

## disassembly

```asm
0x140022220  mov     [rsp+arg_8], rbx
0x140022225  mov     [rsp+arg_10], rsi
0x14002222a  mov     [rsp+arg_18], r9
0x14002222f  push    rdi
0x140022230  push    r12
0x140022232  push    r13
0x140022234  push    r14
0x140022236  push    r15
0x140022238  sub     rsp, 30h
0x14002223c  mov     r14, rcx
0x14002223f  xor     r15d, r15d
0x140022242  mov     [rsp+58h+arg_0], r15d
0x140022247  xor     r12d, r12d
0x14002224a  xor     ebx, ebx
0x14002224c  mov     eax, cs:dword_14001A2FC
0x140022252  sub     rcx, rax; FastMutex
0x140022255  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14002225c  nop     dword ptr [rax+rax+00h]
0x140022261  mov     rdi, [r14+10h]
0x140022265  mov     sil, [rsp+58h+arg_28]
0x14002226d  mov     r13d, [rsp+58h+arg_20]
0x140022275  mov     [rsp+58h+var_38], rdi
0x14002227a  lea     rax, [r14+8]
0x14002227e  cmp     rdi, rax
0x140022281  jz      loc_140022445
0x140022287  mov     eax, [rdi+28h]
0x14002228a  test    al, 6
0x14002228c  jnz     loc_14002243C
0x140022292  mov     eax, cs:dword_14001A2FC
0x140022298  mov     rcx, r14
0x14002229b  sub     rcx, rax; FastMutex
0x14002229e  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1400222a5  nop     dword ptr [rax+rax+00h]
0x1400222aa  lea     rcx, [rdi+70h]; FastMutex
0x1400222ae  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1400222b5  nop     dword ptr [rax+rax+00h]
0x1400222ba  movzx   r15d, word ptr [rdi+38h]
0x1400222bf  add     r15d, 39h ; '9'
0x1400222c3  and     r15d, 0FFFFFFF8h
0x1400222c7  add     r12d, r15d
0x1400222ca  cmp     r12d, r13d
0x1400222cd  ja      loc_140022407
0x1400222d3  mov     rcx, [rsp+58h+arg_18]
0x1400222d8  mov     rbx, rcx
0x1400222db  mov     eax, r15d
0x1400222de  add     rcx, rax
0x1400222e1  mov     [rsp+58h+arg_18], rcx
0x1400222e6  xor     edx, edx; Val
0x1400222e8  lea     r8d, [rdx+30h]; Size
0x1400222ec  mov     rcx, rbx; void *
0x1400222ef  test    sil, sil
0x1400222f2  jz      short loc_1400222FB
0x1400222f4  call    RtlSetUserMemory
0x1400222f9  jmp     short loc_140022300
0x1400222fb  call    RtlSetVolatileMemory
0x140022300  test    sil, sil
0x140022303  jz      short loc_140022312
0x140022305  mov     edx, r15d
0x140022308  mov     rcx, rbx
0x14002230b  call    RtlWriteULongToUser
0x140022310  jmp     short loc_140022315
0x140022312  mov     [rbx], r15d
0x140022315  mov     rax, [rdi+58h]
0x140022319  lea     rcx, [rbx+8]
0x14002231d  test    sil, sil
0x140022320  jz      short loc_14002232C
0x140022322  mov     rdx, rax
0x140022325  call    RtlWriteULong64ToUser
0x14002232a  jmp     short loc_14002232F
0x14002232c  mov     [rcx], rax
0x14002232f  mov     eax, [rdi+34h]
0x140022332  lea     rcx, [rbx+28h]
0x140022336  test    sil, sil
0x140022339  jz      short loc_140022344
0x14002233b  mov     edx, eax
0x14002233d  call    RtlWriteULongToUser
0x140022342  jmp     short loc_140022346
0x140022344  mov     [rcx], eax
0x140022346  mov     eax, [rdi+30h]
0x140022349  lea     rcx, [rbx+24h]
0x14002234d  test    sil, sil
0x140022350  jz      short loc_14002235B
0x140022352  mov     edx, eax
0x140022354  call    RtlWriteULongToUser
0x140022359  jmp     short loc_14002235D
0x14002235b  mov     [rcx], eax
0x14002235d  test    sil, sil
0x140022360  jz      short loc_140022372
0x140022362  mov     edx, 30h ; '0'
0x140022367  lea     rcx, [rbx+20h]
0x14002236b  call    RtlWriteULongToUser
0x140022370  jmp     short loc_140022379
0x140022372  mov     dword ptr [rbx+20h], 30h ; '0'
0x140022379  lea     r15, [rbx+30h]
0x14002237d  movzx   r8d, word ptr [rdi+38h]; Size
0x140022382  mov     rdx, [rdi+40h]; Src
0x140022386  mov     rcx, r15; void *
0x140022389  test    sil, sil
0x14002238c  jz      short loc_140022395
0x14002238e  call    RtlCopyToUser
0x140022393  jmp     short loc_14002239A
0x140022395  call    RtlCopyVolatileMemory
0x14002239a  movzx   eax, word ptr [rdi+38h]
0x14002239e  shr     rax, 1
0x1400223a1  lea     rcx, [r15+rax*2]
0x1400223a5  test    sil, sil
0x1400223a8  jz      short loc_1400223B3
0x1400223aa  xor     edx, edx
0x1400223ac  call    RtlWriteUShortToUser
0x1400223b1  jmp     short loc_1400223B8
0x1400223b3  xor     eax, eax
0x1400223b5  mov     [rcx], ax
0x1400223b8  lea     rdx, [rdi+48h]; Src
0x1400223bc  lea     rcx, [rbx+10h]; void *
0x1400223c0  mov     r8d, 10h; Size
0x1400223c6  test    sil, sil
0x1400223c9  jz      short loc_1400223D2
0x1400223cb  call    RtlCopyToUser
0x1400223d0  jmp     short loc_1400223D7
0x1400223d2  call    RtlCopyVolatileMemory
0x1400223d7  lea     rdx, [rbx+2Ch]
0x1400223db  mov     r8b, sil
0x1400223de  mov     rcx, rdi
0x1400223e1  call    WimFSFGetOverlayFlags
0x1400223e6  jmp     short loc_140022407
0x1400223e8  mov     rcx, [rsp+58h+var_38]
0x1400223ed  add     rcx, 70h ; 'p'; FastMutex
0x1400223f1  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1400223f8  nop     dword ptr [rax+rax+00h]
0x1400223fd  mov     edi, 0C00000E8h
0x140022402  jmp     loc_1400224DE
0x140022407  mov     r15d, [rsp+58h+arg_0]
0x14002240c  inc     r15d
0x14002240f  mov     [rsp+58h+arg_0], r15d
0x140022414  lea     rcx, [rdi+70h]; FastMutex
0x140022418  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14002241f  nop     dword ptr [rax+rax+00h]
0x140022424  mov     eax, cs:dword_14001A2FC
0x14002242a  mov     rcx, r14
0x14002242d  sub     rcx, rax; FastMutex
0x140022430  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140022437  nop     dword ptr [rax+rax+00h]
0x14002243c  mov     rdi, [rdi+8]
0x140022440  jmp     loc_140022275
0x140022445  mov     eax, cs:dword_14001A2FC
0x14002244b  mov     rcx, r14
0x14002244e  sub     rcx, rax; FastMutex
0x140022451  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140022458  nop     dword ptr [rax+rax+00h]
0x14002245d  test    r15d, r15d
0x140022460  jnz     short loc_14002249E
0x140022462  mov     rcx, cs:WPP_GLOBAL_Control
0x140022469  mov     eax, [rcx+2Ch]
0x14002246c  test    al, 8
0x14002246e  jz      short loc_140022497
0x140022470  cmp     byte ptr [rcx+29h], 4
0x140022474  jb      short loc_140022497
0x140022476  mov     eax, cs:dword_14001A2FC
0x14002247c  sub     r14, rax
0x14002247f  lea     r9, [r14+40h]
0x140022483  lea     edx, [r15+12h]
0x140022487  lea     r8, WPP_ea753fa6f9d83b7566c7b1a5ff90ffd6_Traceguids
0x14002248e  mov     rcx, [rcx+18h]
0x140022492  call    WPP_SF_Z
0x140022497  mov     edi, 0C000000Fh
0x14002249c  jmp     short loc_1400224DE
0x14002249e  cmp     r13d, r12d
0x1400224a1  sbb     edi, edi
0x1400224a3  and     edi, 0C0000023h
0x1400224a9  cmp     r12d, r13d
0x1400224ac  ja      short loc_1400224D3
0x1400224ae  test    rbx, rbx
0x1400224b1  jz      short loc_1400224CA
0x1400224b3  test    sil, sil
0x1400224b6  jz      short loc_1400224C4
0x1400224b8  xor     edx, edx
0x1400224ba  mov     rcx, rbx
0x1400224bd  call    RtlWriteULongToUser
0x1400224c2  jmp     short loc_1400224CA
0x1400224c4  mov     dword ptr [rbx], 0
0x1400224ca  jmp     short loc_1400224D3
0x1400224cc  mov     edi, 0C00000E8h
0x1400224d1  jmp     short loc_1400224DE
0x1400224d3  mov     rcx, [rsp+58h+arg_30]
0x1400224db  mov     [rcx], r12d
0x1400224de  mov     eax, edi
0x1400224e0  mov     rbx, [rsp+58h+arg_8]
0x1400224e5  mov     rsi, [rsp+58h+arg_10]
0x1400224ea  add     rsp, 30h
0x1400224ee  pop     r15
0x1400224f0  pop     r14
0x1400224f2  pop     r13
0x1400224f4  pop     r12
0x1400224f6  pop     rdi
0x1400224f7  retn
```
