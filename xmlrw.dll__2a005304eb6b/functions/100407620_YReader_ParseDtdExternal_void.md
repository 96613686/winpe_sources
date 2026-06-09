# YReader::ParseDtdExternal(void)

- ea: `0x100407620`
- end: `0x10040782c`
- name: `?ParseDtdExternal@YReader@@AEAAXXZ`
- size: `524`
- prototype: `void __fastcall(YReader *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x100401780`
- `0x100407620`
- `0x100409390`
- `0x10040a750`
- `0x10040aa00`
- `0x100416970`
- `0x100417060`
- `0x10041db90`
- `0x100439df0`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x100407685`
- `KERNEL32!HeapAlloc` at `0x100407685`

## pseudocode

```c
void __fastcall YReader::ParseDtdExternal(YReader *this)
{
  __int64 v2; // rbx
  DeclEntity *v3; // rax
  __int64 v4; // rbx
  __int64 v5; // rax
  __int64 v6; // rbx
  __int64 v7; // rax
  void (__fastcall *v8)(const void **); // rax
  __int128 v9; // [rsp+50h] [rbp-28h]
  DeclEntity *v10; // [rsp+80h] [rbp+8h]

  v2 = *((_QWORD *)this + 1);
  if ( v2 )
  {
    v3 = (DeclEntity *)(*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v2 + 24LL))(*((_QWORD *)this + 1), 144);
  }
  else if ( g_pMalloc )
  {
    v3 = (DeclEntity *)((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMalloc->lpVtbl->Alloc)(g_pMalloc, 144);
  }
  else
  {
    v3 = (DeclEntity *)HeapAlloc(g_hHeap, 0, 0x90u);
  }
  if ( !v3 )
  {
    MXRRaiseException(-2147024882);
    JUMPOUT(0x10040782CLL);
  }
  *((_QWORD *)v3 + 1) = v2;
  v10 = DeclEntity::DeclEntity(v3, *((struct IMalloc **)this + 1), (struct StringPtr *)&CodeStringPtr::dtd, 1, 0, 0);
  DeclDoctype::InsertEntity((YReader *)((char *)this + 1256), v10);
  v4 = *(_QWORD *)v10;
  v5 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 157) + 24LL))((char *)this + 1256);
  (*(void (__fastcall **)(DeclEntity *, __int64))(v4 + 32))(v10, v5);
  v6 = *(_QWORD *)v10;
  v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 157) + 40LL))((char *)this + 1256);
  (*(void (__fastcall **)(DeclEntity *, __int64))(v6 + 48))(v10, v7);
  *((_BYTE *)v10 + 131) = 1;
  if ( !YReader::HandleEntity(this, v10, this) )
    goto LABEL_11;
  (*((void (__fastcall **)(char *))this + 27))((char *)this + 40);
  if ( *((_DWORD *)this + 28) == 1 )
  {
    YReader::ParseTextDecl(this);
    goto LABEL_14;
  }
  if ( *((_DWORD *)this + 28) != 59 )
  {
LABEL_14:
    *(_QWORD *)&v9 = YReader::ParseProlog;
    DWORD2(v9) = 0;
    *((_OWORD *)this + 95) = v9;
    v8 = YReader::ParseSubsetExternal;
    goto LABEL_12;
  }
  YReader::HandleEntityEnd(this, this);
LABEL_11:
  *((_QWORD *)this + 230) = *(_QWORD *)(*((_QWORD *)this + 55) + 16LL);
  v8 = (void (__fastcall *)(const void **))YReader::ParseProlog;
LABEL_12:
  *(_QWORD *)&v9 = v8;
  DWORD2(v9) = 0;
  *((_OWORD *)this + 94) = v9;
  (*((void (__fastcall **)(char *))this + 188))((char *)this + *((int *)this + 378));
}

```

## disassembly

```asm
0x100407620  mov     [rsp+arg_8], rbx
0x100407625  mov     [rsp+arg_10], rsi
0x10040762a  push    rdi
0x10040762b  push    r14
0x10040762d  push    r15
0x10040762f  sub     rsp, 60h
0x100407633  mov     rdi, rcx
0x100407636  mov     rbx, [rcx+8]
0x10040763a  test    rbx, rbx
0x10040763d  jz      short loc_100407656
0x10040763f  mov     rax, [rbx]
0x100407642  mov     edx, 90h
0x100407647  mov     rcx, rbx
0x10040764a  mov     rax, [rax+18h]
0x10040764e  call    cs:__guard_dispatch_icall_fptr
0x100407654  jmp     short loc_10040768B
0x100407656  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10040765d  test    rcx, rcx
0x100407660  jz      short loc_100407676
0x100407662  mov     rax, [rcx]
0x100407665  mov     edx, 90h
0x10040766a  mov     rax, [rax+18h]
0x10040766e  call    cs:__guard_dispatch_icall_fptr
0x100407674  jmp     short loc_10040768B
0x100407676  xor     edx, edx; dwFlags
0x100407678  mov     r8d, 90h; dwBytes
0x10040767e  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x100407685  call    cs:__imp_HeapAlloc
0x10040768b  test    rax, rax
0x10040768e  jz      loc_100407821
0x100407694  mov     [rax+8], rbx
0x100407698  mov     [rsp+78h+var_50], 0; bool
0x10040769d  xor     r15d, r15d
0x1004076a0  mov     [rsp+78h+var_58], r15; struct StringPtr *
0x1004076a5  mov     r9b, 1; bool
0x1004076a8  lea     r8, ?dtd@CodeStringPtr@@2UStringPtr@@A; struct StringPtr *
0x1004076af  mov     rdx, [rdi+8]; struct IMalloc *
0x1004076b3  mov     rcx, rax; this
0x1004076b6  call    ??0DeclEntity@@QEAA@PEAUIMalloc@@PEAUStringPtr@@_N12@Z; DeclEntity::DeclEntity(IMalloc *,StringPtr *,bool,StringPtr *,bool)
0x1004076bb  mov     rsi, rax
0x1004076be  mov     [rsp+78h+arg_0], rax
0x1004076c6  mov     rdx, rax; struct DeclEntity *
0x1004076c9  lea     rcx, [rdi+4E8h]; this
0x1004076d0  call    ?InsertEntity@DeclDoctype@@QEAAXPEAVDeclEntity@@@Z; DeclDoctype::InsertEntity(DeclEntity *)
0x1004076d5  nop
0x1004076d6  mov     rbx, [rsi]
0x1004076d9  mov     rax, [rdi+4E8h]
0x1004076e0  lea     rcx, [rdi+4E8h]
0x1004076e7  mov     rax, [rax+18h]
0x1004076eb  call    cs:__guard_dispatch_icall_fptr
0x1004076f1  mov     rdx, rax
0x1004076f4  mov     rcx, rsi
0x1004076f7  mov     rax, [rbx+20h]
0x1004076fb  call    cs:__guard_dispatch_icall_fptr
0x100407701  mov     rbx, [rsi]
0x100407704  mov     rax, [rdi+4E8h]
0x10040770b  lea     rcx, [rdi+4E8h]
0x100407712  mov     rax, [rax+28h]
0x100407716  call    cs:__guard_dispatch_icall_fptr
0x10040771c  mov     rdx, rax
0x10040771f  mov     rcx, rsi
0x100407722  mov     rax, [rbx+30h]
0x100407726  call    cs:__guard_dispatch_icall_fptr
0x10040772c  mov     byte ptr [rsi+83h], 1
0x100407733  mov     r8, rdi; void *
0x100407736  mov     rdx, rsi; struct DeclEntity *
0x100407739  mov     rcx, rdi; this
0x10040773c  call    ?HandleEntity@YReader@@AEAAPEAVDeclEntity@@PEAV2@PEAX@Z; YReader::HandleEntity(DeclEntity *,void *)
0x100407741  test    rax, rax
0x100407744  jz      short loc_10040776F
0x100407746  lea     rcx, [rdi+28h]
0x10040774a  mov     rax, [rdi+0D8h]
0x100407751  call    cs:__guard_dispatch_icall_fptr
0x100407757  mov     ecx, [rdi+70h]
0x10040775a  sub     ecx, 1
0x10040775d  jz      short loc_1004077CB
0x10040775f  cmp     ecx, 3Ah ; ':'
0x100407762  jnz     short loc_1004077D3
0x100407764  mov     rdx, rdi; void *
0x100407767  mov     rcx, rdi; this
0x10040776a  call    ?HandleEntityEnd@YReader@@AEAAPEAVDeclEntity@@PEAX@Z; YReader::HandleEntityEnd(void *)
0x10040776f  mov     rax, [rdi+1B8h]
0x100407776  mov     rcx, [rax+10h]
0x10040777a  mov     [rdi+730h], rcx
0x100407781  lea     rax, ?ParseProlog@YReader@@AEAAXXZ; YReader::ParseProlog(void)
0x100407788  mov     qword ptr [rsp+78h+var_28], rax
0x10040778d  mov     dword ptr [rsp+78h+var_28+8], r15d
0x100407792  movups  xmm0, [rsp+78h+var_28]
0x100407797  movups  xmmword ptr [rdi+5E0h], xmm0
0x10040779e  movsxd  rcx, dword ptr [rdi+5E8h]
0x1004077a5  add     rcx, rdi
0x1004077a8  mov     rax, [rdi+5E0h]
0x1004077af  call    cs:__guard_dispatch_icall_fptr
0x1004077b5  lea     r11, [rsp+78h+var_18]
0x1004077ba  mov     rbx, [r11+28h]
0x1004077be  mov     rsi, [r11+30h]
0x1004077c2  mov     rsp, r11
0x1004077c5  pop     r15
0x1004077c7  pop     r14
0x1004077c9  pop     rdi
0x1004077ca  retn
0x1004077cb  mov     rcx, rdi; this
0x1004077ce  call    ?ParseTextDecl@YReader@@AEAAXXZ; YReader::ParseTextDecl(void)
0x1004077d3  lea     rax, ?ParseProlog@YReader@@AEAAXXZ; YReader::ParseProlog(void)
0x1004077da  mov     qword ptr [rsp+78h+var_28], rax
0x1004077df  mov     dword ptr [rsp+78h+var_28+8], r15d
0x1004077e4  movups  xmm0, [rsp+78h+var_28]
0x1004077e9  movups  xmmword ptr [rdi+5F0h], xmm0
0x1004077f0  lea     rax, ?ParseSubsetExternal@YReader@@AEAAXXZ; YReader::ParseSubsetExternal(void)
0x1004077f7  jmp     short loc_100407788
0x1004077f9  mov     rcx, [rsp+78h+arg_0]
0x100407801  test    rcx, rcx
0x100407804  jz      short loc_100407817
0x100407806  mov     rax, [rcx]
0x100407809  mov     edx, 1
0x10040780e  mov     rax, [rax]
0x100407811  call    cs:__guard_dispatch_icall_fptr
0x100407817  mov     ecx, [rsp+78h+var_48]; int
0x10040781b  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x100407820  nop
0x100407821  mov     ecx, 8007000Eh; int
0x100407826  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10040782b  nop
0x100439f90  push    rbp
0x100439f92  sub     rsp, 30h
0x100439f96  mov     rbp, rdx
0x100439f99  mov     [rbp+48h], rcx
0x100439f9d  mov     [rbp+40h], rcx
0x100439fa1  mov     rax, [rbp+40h]
0x100439fa5  mov     rcx, [rax]
0x100439fa8  mov     [rbp+38h], rcx
0x100439fac  mov     rax, [rbp+38h]
0x100439fb0  mov     eax, [rax]
0x100439fb2  cmp     eax, 0C0000005h
0x100439fb7  jz      short loc_100439FE9
0x100439fb9  add     eax, 1FFFFFFFh
0x100439fbe  cmp     eax, 1
0x100439fc1  ja      short loc_100439FD9
0x100439fc3  mov     rax, [rbp+38h]
0x100439fc7  cmp     dword ptr [rax+18h], 1
0x100439fcb  jnz     short loc_100439FD9
0x100439fcd  mov     rax, [rbp+38h]
0x100439fd1  mov     ecx, [rax+20h]
0x100439fd4  mov     [rbp+30h], ecx
0x100439fd7  jmp     short loc_100439FE0
0x100439fd9  mov     dword ptr [rbp+30h], 8000FFFFh
0x100439fe0  mov     dword ptr [rbp+34h], 1
0x100439fe7  jmp     short loc_100439FF0
0x100439fe9  mov     dword ptr [rbp+34h], 0
0x100439ff0  mov     eax, [rbp+34h]
0x100439ff3  add     rsp, 30h
0x100439ff7  pop     rbp
0x100439ff8  retn
```
