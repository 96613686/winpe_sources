# CWdsMetadata::RenameMatchGroup(ushort const *,ushort * *)

- ea: `0x18000a870`
- end: `0x18000a969`
- name: `?RenameMatchGroup@CWdsMetadata@@AEBAKPEBGPEAPEAG@Z`
- size: `249`
- prototype: `unsigned int __fastcall(CWdsMetadata *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18000b47c`

## callees

- `0x1800085fc`
- `0x18000a7ec`
- `0x18000a870`
- `0x180014ee0`
- `0x1800150b8`
- `0x1800157a4`

## pseudocode

```c
__int64 __fastcall CWdsMetadata::RenameMatchGroup(
        CWdsMetadata *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  __int64 v5; // rbp
  unsigned int v7; // esi
  int v8; // r12d
  unsigned __int64 v9; // rbp
  unsigned __int64 v10; // rax
  wchar_t *v11; // rbx
  int v12; // edi
  const char *v13; // rdx
  __int64 v14; // rcx
  __int64 v16; // [rsp+20h] [rbp-38h]

  v5 = -1;
  v7 = 0;
  v8 = 0;
  do
    ++v5;
  while ( a2[v5] );
  v9 = v5 + 32;
  v10 = 2 * v9;
  if ( !is_mul_ok(v9, 2u) )
    v10 = -1;
  v11 = (wchar_t *)operator new[](v10, (const struct std::nothrow_t *)&std::nothrow);
  if ( v11 )
  {
    while ( 1 )
    {
      LODWORD(v16) = ++v8;
      v12 = StringCchPrintfW(v11, v9, L"%s-%u", a2, v16);
      if ( (int)ElValidateHr(v12, v13, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0xC66u) < 0 )
        break;
      if ( (int)CWdsMetadata::FindGroupIndex(v14, (char *)this + 24, v11) < 0 )
      {
        *a3 = v11;
        v11 = 0;
        goto LABEL_13;
      }
    }
    if ( v12 >= 0 || (v7 = (unsigned __int16)v12, (v12 & 0x1FFF0000) != 0x70000) )
      v7 = v12;
LABEL_13:
    if ( v11 )
      operator delete(v11);
  }
  else
  {
    return 8;
  }
  return v7;
}

```

## disassembly

```asm
0x18000a870  mov     [rsp+arg_0], rbx
0x18000a875  mov     [rsp+arg_8], rbp
0x18000a87a  mov     [rsp+arg_10], rsi
0x18000a87f  push    rdi
0x18000a880  push    r12
0x18000a882  push    r13
0x18000a884  push    r14
0x18000a886  push    r15
0x18000a888  sub     rsp, 30h
0x18000a88c  xor     edi, edi
0x18000a88e  mov     r13, rcx
0x18000a891  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000a895  mov     r15, r8
0x18000a898  mov     rbp, rcx
0x18000a89b  mov     r14, rdx
0x18000a89e  mov     esi, edi
0x18000a8a0  mov     r12d, edi
0x18000a8a3  inc     rbp
0x18000a8a6  cmp     [rdx+rbp*2], di
0x18000a8aa  jnz     short loc_18000A8A3
0x18000a8ac  add     rbp, 20h ; ' '
0x18000a8b0  mov     eax, 2
0x18000a8b5  mul     rbp
0x18000a8b8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a8bf  cmovo   rax, rcx
0x18000a8c3  mov     rcx, rax; unsigned __int64
0x18000a8c6  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000a8cb  mov     rbx, rax
0x18000a8ce  test    rax, rax
0x18000a8d1  jnz     short loc_18000A8D8
0x18000a8d3  lea     esi, [rax+8]
0x18000a8d6  jmp     short loc_18000A94A
0x18000a8d8  inc     r12d
0x18000a8db  lea     r8, aSU; "%s-%u"
0x18000a8e2  mov     r9, r14
0x18000a8e5  mov     dword ptr [rsp+58h+var_38], r12d
0x18000a8ea  mov     rdx, rbp; unsigned __int64
0x18000a8ed  mov     rcx, rbx; Buffer
0x18000a8f0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a8f5  mov     r9d, 0C66h; unsigned int
0x18000a8fb  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x18000a902  mov     ecx, eax; int
0x18000a904  mov     edi, eax
0x18000a906  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000a90b  test    eax, eax
0x18000a90d  js      short loc_18000A926
0x18000a90f  lea     rdx, [r13+18h]
0x18000a913  mov     r8, rbx
0x18000a916  call    ?FindGroupIndex@CWdsMetadata@@AEBAHPEAV?$CDynArray@PEAUCEntryGroup@CWdsMetadata@@VCDeallocatePointer@@@@PEBG@Z; CWdsMetadata::FindGroupIndex(CDynArray<CWdsMetadata::CEntryGroup *,CDeallocatePointer> *,ushort const *)
0x18000a91b  test    eax, eax
0x18000a91d  jns     short loc_18000A8D8
0x18000a91f  mov     [r15], rbx
0x18000a922  xor     ebx, ebx
0x18000a924  jmp     short loc_18000A93D
0x18000a926  test    edi, edi
0x18000a928  jns     short loc_18000A93B
0x18000a92a  mov     eax, edi
0x18000a92c  movzx   esi, di
0x18000a92f  and     eax, 1FFF0000h
0x18000a934  cmp     eax, 70000h
0x18000a939  jz      short loc_18000A93D
0x18000a93b  mov     esi, edi
0x18000a93d  test    rbx, rbx
0x18000a940  jz      short loc_18000A94A
0x18000a942  mov     rcx, rbx; Block
0x18000a945  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a94a  mov     rbx, [rsp+58h+arg_0]
0x18000a94f  mov     eax, esi
0x18000a951  mov     rsi, [rsp+58h+arg_10]
0x18000a956  mov     rbp, [rsp+58h+arg_8]
0x18000a95b  add     rsp, 30h
0x18000a95f  pop     r15
0x18000a961  pop     r14
0x18000a963  pop     r13
0x18000a965  pop     r12
0x18000a967  pop     rdi
0x18000a968  retn
```
