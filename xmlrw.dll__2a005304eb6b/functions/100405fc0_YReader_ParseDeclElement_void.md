# YReader::ParseDeclElement(void)

- ea: `0x100405fc0`
- end: `0x100406296`
- name: `?ParseDeclElement@YReader@@AEAAXXZ`
- size: `726`
- prototype: `void __fastcall(YReader *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x100408ea0`
- `0x100409110`

## callees

- `0x100401780`
- `0x100405fc0`
- `0x1004062a0`
- `0x10040a020`
- `0x100415560`
- `0x1004169d0`
- `0x100416cb0`
- `0x100417840`
- `0x100423dd0`
- `0x100439df0`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1004060f5`
- `KERNEL32!HeapAlloc` at `0x1004061a0`
- `KERNEL32!HeapAlloc` at `0x1004060f5`
- `KERNEL32!HeapAlloc` at `0x1004061a0`

## pseudocode

```c
void __fastcall YReader::ParseDeclElement(struct IMalloc **this)
{
  unsigned int v2; // eax
  __int64 v3; // rsi
  struct BlockAlloc::Header *v4; // rbx
  __int64 v5; // rdx
  __int64 v6; // rcx
  struct BlockAlloc::Header *v7; // rax
  struct DeclElement *v8; // rax
  struct DeclElement *v9; // rbx
  struct IMalloc *v10; // rbx
  DeclElement *v11; // rax
  __int64 v12; // rax
  struct IMalloc *v13; // rbx
  DeclElement *v14; // rax
  struct IMalloc *v15; // rcx
  int v16; // eax
  int v17; // eax
  int v18; // [rsp+20h] [rbp-38h]
  __int64 v19; // [rsp+40h] [rbp-18h] BYREF
  int v20; // [rsp+48h] [rbp-10h]
  void (__fastcall ***v21)(_QWORD, __int64); // [rsp+68h] [rbp+10h]

  v20 = 0;
  if ( (unsigned int)YReader::GetTokenDeclInner((YReader *)this) != 12 )
  {
    MXRRaiseException(-1072894407);
    if ( v21 )
      (**v21)(v21, 1);
    MXRRaiseException(v18);
    goto LABEL_39;
  }
  v2 = ((__int64 (__fastcall *)(struct IMalloc *))this[13]->lpVtbl[1].Alloc)(this[13]);
  v3 = v2;
  v4 = (struct BlockAlloc::Header *)this[55];
  v5 = *((_QWORD *)v4 + 2);
  if ( *((_DWORD *)v4 + 6) - (int)v5 < v2 )
  {
    v6 = *((_QWORD *)v4 + 1);
    if ( v6 )
    {
      while ( 1 )
      {
        v4 = (struct BlockAlloc::Header *)v6;
        if ( *(_DWORD *)(v6 + 24) - (int)v6 - 32 >= v2 )
          break;
        v6 = *(_QWORD *)(v6 + 8);
        if ( !v6 )
          goto LABEL_6;
      }
      *(_QWORD *)(v6 + 16) = v6 + 32;
    }
    else
    {
LABEL_6:
      _mm_lfence();
      v7 = BlockAlloc::EnqueueBlock((BlockAlloc *)(this + 52), v2, v4);
      *((_QWORD *)v4 + 1) = v7;
      v4 = v7;
    }
    this[55] = (struct IMalloc *)v4;
    v5 = *((_QWORD *)v4 + 2);
  }
  *((_QWORD *)v4 + 2) += v3;
  v19 = v5;
  ((void (__fastcall *)(struct IMalloc *, __int64 *))this[13]->lpVtbl[1].Realloc)(this[13], &v19);
  v8 = DeclDoctype::LookupElement((DeclDoctype *)(this + 157), (struct StringPtr *)&v19);
  v9 = v8;
  if ( !v8 )
  {
    v10 = this[1];
    if ( v10 )
    {
      v11 = (DeclElement *)((__int64 (__fastcall *)(struct IMalloc *, __int64))v10->lpVtbl->Alloc)(this[1], 120);
    }
    else if ( g_pMalloc )
    {
      v11 = (DeclElement *)((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMalloc->lpVtbl->Alloc)(g_pMalloc, 120);
    }
    else
    {
      v11 = (DeclElement *)HeapAlloc(g_hHeap, 0, 0x78u);
    }
    if ( v11 )
    {
      *((_QWORD *)v11 + 1) = v10;
      v9 = DeclElement::DeclElement(v11, this[1], (struct StringPtr *)&v19);
      v12 = (*(__int64 (__fastcall **)(struct DeclElement *))(*(_QWORD *)v9 + 8LL))(v9);
      _htable<DeclNotation>::insert(this + 182, v9, v12);
      goto LABEL_27;
    }
LABEL_39:
    MXRRaiseException(-2147024882);
    __debugbreak();
  }
  if ( *((_QWORD *)v8 + 5) )
  {
    v13 = this[1];
    if ( v13 )
    {
      v14 = (DeclElement *)((__int64 (__fastcall *)(struct IMalloc *, __int64))v13->lpVtbl->Alloc)(this[1], 120);
    }
    else if ( g_pMalloc )
    {
      v14 = (DeclElement *)((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMalloc->lpVtbl->Alloc)(g_pMalloc, 120);
    }
    else
    {
      v14 = (DeclElement *)HeapAlloc(g_hHeap, 0, 0x78u);
    }
    if ( !v14 )
      goto LABEL_39;
    *((_QWORD *)v14 + 1) = v13;
    v9 = DeclElement::DeclElement(v14, this[1], (struct StringPtr *)&CodeStringPtr::empty);
    v15 = this[187];
    if ( v15 )
      ((void (__fastcall *)(struct IMalloc *, __int64))v15->lpVtbl->QueryInterface)(v15, 1);
    this[187] = (struct IMalloc *)v9;
  }
LABEL_27:
  v16 = YReader::GetTokenDeclInner((YReader *)this) - 41;
  if ( !v16 )
  {
    *((_DWORD *)v9 + 8) = 0;
    goto LABEL_33;
  }
  v17 = v16 - 1;
  if ( !v17 )
  {
    *((_DWORD *)v9 + 8) = 1;
LABEL_33:
    YReader::GetTokenDeclInner((YReader *)this);
    goto LABEL_34;
  }
  if ( v17 != 8 )
  {
    MXRRaiseException(-1072894419);
    __debugbreak();
  }
  YReader::ParseDeclElementCp((YReader *)this, v9);
LABEL_34:
  if ( *((_DWORD *)this + 28) != 48 )
  {
    MXRRaiseException(-1072894429);
    JUMPOUT(0x100406296LL);
  }
}

```

## disassembly

```asm
0x100405fc0  mov     [rsp+arg_0], rbx
0x100405fc5  mov     [rsp+arg_10], rsi
0x100405fca  mov     [rsp+arg_18], rdi
0x100405fcf  push    r14
0x100405fd1  sub     rsp, 50h
0x100405fd5  mov     rdi, rcx
0x100405fd8  mov     [rsp+58h+var_10], 0
0x100405fe0  call    ?GetTokenDeclInner@YReader@@AEAAHXZ; YReader::GetTokenDeclInner(void)
0x100405fe5  cmp     eax, 0Ch
0x100405fe8  jnz     loc_100406245
0x100405fee  mov     rcx, [rdi+68h]
0x100405ff2  mov     rax, [rcx]
0x100405ff5  mov     rax, [rax+60h]
0x100405ff9  call    cs:__guard_dispatch_icall_fptr
0x100405fff  mov     esi, eax
0x100406001  mov     rbx, [rdi+1B8h]
0x100406008  mov     rdx, [rbx+10h]
0x10040600c  mov     ecx, [rbx+18h]
0x10040600f  sub     ecx, edx
0x100406011  cmp     ecx, eax
0x100406013  jnb     short loc_100406062
0x100406015  mov     rcx, [rbx+8]
0x100406019  test    rcx, rcx
0x10040601c  jz      short loc_10040603C
0x10040601e  xchg    ax, ax
0x100406020  mov     rbx, rcx
0x100406023  mov     eax, [rcx+18h]
0x100406026  sub     eax, ecx
0x100406028  sub     eax, 20h ; ' '
0x10040602b  cmp     eax, esi
0x10040602d  jnb     loc_1004060BE
0x100406033  mov     rcx, [rcx+8]
0x100406037  test    rcx, rcx
0x10040603a  jnz     short loc_100406020
0x10040603c  lfence
0x10040603f  mov     r8, rbx; struct BlockAlloc::Header *
0x100406042  mov     edx, esi; unsigned int
0x100406044  lea     rcx, [rdi+1A0h]; this
0x10040604b  call    ?EnqueueBlock@BlockAlloc@@AEAAPEAUHeader@1@KPEAU21@@Z; BlockAlloc::EnqueueBlock(ulong,BlockAlloc::Header *)
0x100406050  mov     [rbx+8], rax
0x100406054  mov     rbx, rax
0x100406057  mov     [rdi+1B8h], rbx
0x10040605e  mov     rdx, [rbx+10h]
0x100406062  add     [rbx+10h], rsi
0x100406066  mov     [rsp+58h+var_18], rdx
0x10040606b  mov     rcx, [rdi+68h]
0x10040606f  mov     rax, [rcx]
0x100406072  lea     rdx, [rsp+58h+var_18]
0x100406077  mov     rax, [rax+68h]
0x10040607b  call    cs:__guard_dispatch_icall_fptr
0x100406081  lea     rdx, [rsp+58h+var_18]; struct StringPtr *
0x100406086  lea     rcx, [rdi+4E8h]; this
0x10040608d  call    ?LookupElement@DeclDoctype@@QEAAPEAVDeclElement@@PEAUStringPtr@@@Z; DeclDoctype::LookupElement(StringPtr *)
0x100406092  mov     rbx, rax
0x100406095  test    rax, rax
0x100406098  jnz     loc_100406148
0x10040609e  mov     rbx, [rdi+8]
0x1004060a2  test    rbx, rbx
0x1004060a5  jz      short loc_1004060C8
0x1004060a7  mov     rax, [rbx]
0x1004060aa  mov     edx, 78h ; 'x'
0x1004060af  mov     rcx, rbx
0x1004060b2  mov     rax, [rax+18h]
0x1004060b6  call    cs:__guard_dispatch_icall_fptr
0x1004060bc  jmp     short loc_1004060FB
0x1004060be  lea     rax, [rcx+20h]
0x1004060c2  mov     [rcx+10h], rax
0x1004060c6  jmp     short loc_100406057
0x1004060c8  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x1004060cf  test    rcx, rcx
0x1004060d2  jz      short loc_1004060E8
0x1004060d4  mov     rax, [rcx]
0x1004060d7  mov     edx, 78h ; 'x'
0x1004060dc  mov     rax, [rax+18h]
0x1004060e0  call    cs:__guard_dispatch_icall_fptr
0x1004060e6  jmp     short loc_1004060FB
0x1004060e8  xor     edx, edx; dwFlags
0x1004060ea  lea     r8d, [rdx+78h]; dwBytes
0x1004060ee  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x1004060f5  call    cs:__imp_HeapAlloc
0x1004060fb  test    rax, rax
0x1004060fe  jz      loc_100406275
0x100406104  mov     [rax+8], rbx
0x100406108  lea     r8, [rsp+58h+var_18]; struct StringPtr *
0x10040610d  mov     rdx, [rdi+8]; struct IMalloc *
0x100406111  mov     rcx, rax; this
0x100406114  call    ??0DeclElement@@QEAA@PEAUIMalloc@@PEAUStringPtr@@@Z; DeclElement::DeclElement(IMalloc *,StringPtr *)
0x100406119  mov     rbx, rax
0x10040611c  mov     [rsp+58h+arg_8], rax
0x100406121  mov     rax, [rax]
0x100406124  mov     rcx, rbx
0x100406127  mov     rax, [rax+8]
0x10040612b  call    cs:__guard_dispatch_icall_fptr
0x100406131  mov     r8, rax
0x100406134  lea     rcx, [rdi+5B0h]
0x10040613b  mov     rdx, rbx
0x10040613e  call    ?insert@?$_htable@VDeclNotation@@@@QEAAXPEAVDeclNotation@@PEAUStringPtr@@@Z; _htable<DeclNotation>::insert(DeclNotation *,StringPtr *)
0x100406143  jmp     loc_1004061ED
0x100406148  cmp     qword ptr [rax+28h], 0
0x10040614d  jz      loc_1004061ED
0x100406153  mov     rbx, [rdi+8]
0x100406157  test    rbx, rbx
0x10040615a  jz      short loc_100406173
0x10040615c  mov     rax, [rbx]
0x10040615f  mov     edx, 78h ; 'x'
0x100406164  mov     rcx, rbx
0x100406167  mov     rax, [rax+18h]
0x10040616b  call    cs:__guard_dispatch_icall_fptr
0x100406171  jmp     short loc_1004061A6
0x100406173  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10040617a  test    rcx, rcx
0x10040617d  jz      short loc_100406193
0x10040617f  mov     rax, [rcx]
0x100406182  mov     edx, 78h ; 'x'
0x100406187  mov     rax, [rax+18h]
0x10040618b  call    cs:__guard_dispatch_icall_fptr
0x100406191  jmp     short loc_1004061A6
0x100406193  xor     edx, edx; dwFlags
0x100406195  lea     r8d, [rdx+78h]; dwBytes
0x100406199  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x1004061a0  call    cs:__imp_HeapAlloc
0x1004061a6  test    rax, rax
0x1004061a9  jz      loc_100406275
0x1004061af  mov     [rax+8], rbx
0x1004061b3  lea     r8, ?empty@CodeStringPtr@@2UStringPtr@@A; struct StringPtr *
0x1004061ba  mov     rdx, [rdi+8]; struct IMalloc *
0x1004061be  mov     rcx, rax; this
0x1004061c1  call    ??0DeclElement@@QEAA@PEAUIMalloc@@PEAUStringPtr@@@Z; DeclElement::DeclElement(IMalloc *,StringPtr *)
0x1004061c6  mov     rbx, rax
0x1004061c9  mov     rcx, [rdi+5D8h]
0x1004061d0  test    rcx, rcx
0x1004061d3  jz      short loc_1004061E6
0x1004061d5  mov     rax, [rcx]
0x1004061d8  mov     edx, 1
0x1004061dd  mov     rax, [rax]
0x1004061e0  call    cs:__guard_dispatch_icall_fptr
0x1004061e6  mov     [rdi+5D8h], rbx
0x1004061ed  mov     rcx, rdi; this
0x1004061f0  call    ?GetTokenDeclInner@YReader@@AEAAHXZ; YReader::GetTokenDeclInner(void)
0x1004061f5  sub     eax, 29h ; ')'
0x1004061f8  jz      short loc_10040621A
0x1004061fa  sub     eax, 1
0x1004061fd  jz      short loc_100406211
0x1004061ff  cmp     eax, 8
0x100406202  jnz     short loc_100406280
0x100406204  mov     rdx, rbx; struct DeclElement *
0x100406207  mov     rcx, rdi; this
0x10040620a  call    ?ParseDeclElementCp@YReader@@AEAAXPEAVDeclElement@@@Z; YReader::ParseDeclElementCp(DeclElement *)
0x10040620f  jmp     short loc_100406229
0x100406211  mov     dword ptr [rbx+20h], 1
0x100406218  jmp     short loc_100406221
0x10040621a  mov     dword ptr [rbx+20h], 0
0x100406221  mov     rcx, rdi; this
0x100406224  call    ?GetTokenDeclInner@YReader@@AEAAHXZ; YReader::GetTokenDeclInner(void)
0x100406229  cmp     dword ptr [rdi+70h], 30h ; '0'
0x10040622d  jnz     short loc_10040628B
0x10040622f  mov     rbx, [rsp+58h+arg_0]
0x100406234  mov     rsi, [rsp+58h+arg_10]
0x100406239  mov     rdi, [rsp+58h+arg_18]
0x10040623e  add     rsp, 50h
0x100406242  pop     r14
0x100406244  retn
0x100406245  mov     ecx, 0C00CEE39h; int
0x10040624a  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10040624f  nop
0x100406250  mov     rcx, [rsp+58h+arg_8]
0x100406255  test    rcx, rcx
0x100406258  jz      short loc_10040626B
0x10040625a  mov     rax, [rcx]
0x10040625d  mov     edx, 1
0x100406262  mov     rax, [rax]
0x100406265  call    cs:__guard_dispatch_icall_fptr
0x10040626b  mov     ecx, [rsp+58h+var_38]; int
0x10040626f  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x100406274  nop
0x100406275  mov     ecx, 8007000Eh; int
0x10040627a  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10040627f  int     3; Trap to Debugger
0x100406280  mov     ecx, 0C00CEE2Dh; int
0x100406285  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10040628a  int     3; Trap to Debugger
0x10040628b  mov     ecx, 0C00CEE23h; int
0x100406290  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x100406295  nop
0x100439f20  push    rbp
0x100439f22  sub     rsp, 20h
0x100439f26  mov     rbp, rdx
0x100439f29  mov     [rbp+38h], rcx
0x100439f2d  mov     [rbp+30h], rcx
0x100439f31  mov     rax, [rbp+30h]
0x100439f35  mov     rcx, [rax]
0x100439f38  mov     [rbp+28h], rcx
0x100439f3c  mov     rax, [rbp+28h]
0x100439f40  mov     eax, [rax]
0x100439f42  cmp     eax, 0C0000005h
0x100439f47  jz      short loc_100439F79
0x100439f49  add     eax, 1FFFFFFFh
0x100439f4e  cmp     eax, 1
0x100439f51  ja      short loc_100439F69
0x100439f53  mov     rax, [rbp+28h]
0x100439f57  cmp     dword ptr [rax+18h], 1
0x100439f5b  jnz     short loc_100439F69
0x100439f5d  mov     rax, [rbp+28h]
0x100439f61  mov     ecx, [rax+20h]
0x100439f64  mov     [rbp+20h], ecx
0x100439f67  jmp     short loc_100439F70
0x100439f69  mov     dword ptr [rbp+20h], 8000FFFFh
0x100439f70  mov     dword ptr [rbp+24h], 1
0x100439f77  jmp     short loc_100439F80
0x100439f79  mov     dword ptr [rbp+24h], 0
0x100439f80  mov     eax, [rbp+24h]
0x100439f83  add     rsp, 20h
0x100439f87  pop     rbp
0x100439f88  retn
```
