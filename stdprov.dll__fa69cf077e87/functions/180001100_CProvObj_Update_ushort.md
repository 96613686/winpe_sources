# CProvObj::Update(ushort *)

- ea: `0x180001100`
- end: `0x1800012fe`
- name: `?Update@CProvObj@@QEAAHPEAG@Z`
- size: `510`
- prototype: `__int64 __fastcall(CProvObj *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800038e0`

## callees

- `0x1800010a0`
- `0x180001100`
- `0x1800013d0`
- `0x180001590`
- `0x180002e10`
- `0x180015532`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000126b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000126b`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180001239`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180001239`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800012b9`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800012b9`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800011b9`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800011b9`

## pseudocode

```c
__int64 __fastcall CProvObj::Update(CProvObj *this, unsigned __int16 *a2)
{
  unsigned __int16 *v3; // r8
  __int64 v5; // rdx
  int v6; // r9d
  unsigned __int64 v7; // rax
  __int64 v8; // rax
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // rbx
  __int64 result; // rax
  BOOL v13; // esi
  int v14; // r12d
  __int16 *v15; // r10
  __int16 *v16; // rbx
  const WCHAR *v17; // r13
  __int16 v18; // ax
  PCNZWCH *v19; // rax
  PCNZWCH *v20; // rbp
  void *pExceptionObject; // [rsp+68h] [rbp+10h] BYREF

  v3 = a2;
  v5 = 0x1000000000000041LL;
  v6 = 0;
  while ( 1 )
  {
    v7 = *v3;
    if ( !(_WORD)v7 )
      break;
    if ( (_WORD)v7 == *((_WORD *)this + 50) )
    {
      ++v6;
      ++v3;
    }
    else
    {
      LOWORD(v7) = v7 - 34;
      if ( (unsigned __int16)v7 <= 0x3Cu && _bittest64(&v5, v7) )
        goto LABEL_24;
      ++v3;
    }
  }
  if ( v6 != *((_DWORD *)this + 2) - 1 )
  {
LABEL_24:
    CProvObj::Empty(this);
    CProvObj::Init(this, a2, *((_WORD *)this + 50));
    return 1;
  }
  v8 = -1;
  while ( a2[++v8] != 0 )
    ;
  v10 = 2 * v8 + 1;
  if ( v10 > 0x7FFFFFFF )
  {
    LODWORD(pExceptionObject) = 534;
    throw (SafeIntException *)&pExceptionObject;
  }
  v11 = (int)v10;
  result = (__int64)CWin32DefaultArena::WbemMemAlloc(saturated_mul((int)v10, 2u));
  pExceptionObject = (void *)result;
  if ( result )
  {
    StringCchCopyW((unsigned __int16 *)result, v11, a2);
    v13 = 0;
    v14 = 0;
    v16 = v15;
    v17 = (const WCHAR *)v15;
    do
    {
      v18 = *v16;
      if ( *v16 == *((_WORD *)this + 50) || !v18 )
      {
        v13 = v18 == 0;
        *v16 = 0;
        v19 = (PCNZWCH *)CFlexArray::GetAt((CProvObj *)((char *)this + 8), v14);
        v20 = v19;
        if ( v19 && CompareStringW(0x7Fu, 1u, v17, -1, v19[4], -1) != 2 )
        {
          TString::operator=(v20 + 4, v17);
          TString::operator=(v20 + 2, v17);
        }
        ++v14;
        v17 = (const WCHAR *)++v16;
      }
      else
      {
        ++v16;
      }
    }
    while ( !v13 );
    CWin32DefaultArena::WbemMemFree(pExceptionObject);
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x180001100  push    rsi
0x180001102  push    rdi
0x180001103  sub     rsp, 48h
0x180001107  mov     rsi, rdx
0x18000110a  mov     [rsp+58h+var_28], r15
0x18000110f  mov     r8, rdx
0x180001112  mov     rdi, rcx
0x180001115  mov     rdx, 1000000000000041h
0x18000111f  xor     r9d, r9d
0x180001122  movzx   eax, word ptr [r8]
0x180001126  test    ax, ax
0x180001129  jz      short loc_180001154
0x18000112b  cmp     ax, [rdi+64h]
0x18000112f  jnz     short loc_18000113A
0x180001131  inc     r9d
0x180001134  add     r8, 2
0x180001138  jmp     short loc_180001122
0x18000113a  sub     ax, 22h ; '"'
0x18000113e  cmp     ax, 3Ch ; '<'
0x180001142  ja      short loc_18000114E
0x180001144  bt      rdx, rax
0x180001148  jb      loc_1800012D5
0x18000114e  add     r8, 2
0x180001152  jmp     short loc_180001122
0x180001154  mov     eax, [rdi+8]
0x180001157  dec     eax
0x180001159  cmp     r9d, eax
0x18000115c  jnz     loc_1800012D5
0x180001162  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180001169  mov     rax, rcx
0x18000116c  cmp     word ptr [rsi+rax*2+2], 0
0x180001172  lea     rax, [rax+1]
0x180001176  jnz     short loc_18000116C
0x180001178  lea     rax, ds:1[rax*2]
0x180001180  cmp     rax, 7FFFFFFFh
0x180001186  jbe     short loc_1800011A2
0x180001188  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x18000118f  mov     dword ptr [rsp+58h+pExceptionObject], 216h
0x180001197  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18000119c  call    _CxxThrowException_0
0x1800011a2  mov     [rsp+58h+arg_0], rbx
0x1800011a7  movsxd  rbx, eax
0x1800011aa  mov     eax, 2
0x1800011af  mul     rbx
0x1800011b2  cmovb   rax, rcx
0x1800011b6  mov     rcx, rax
0x1800011b9  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800011bf  mov     [rsp+58h+pExceptionObject], rax
0x1800011c4  mov     r10, rax
0x1800011c7  test    rax, rax
0x1800011ca  jnz     short loc_1800011DD
0x1800011cc  mov     rbx, [rsp+58h+arg_0]
0x1800011d1  mov     r15, [rsp+58h+var_28]
0x1800011d6  add     rsp, 48h
0x1800011da  pop     rdi
0x1800011db  pop     rsi
0x1800011dc  retn
0x1800011dd  mov     [rsp+58h+arg_18], r12
0x1800011e2  mov     r8, rsi; unsigned __int16 *
0x1800011e5  mov     rdx, rbx; unsigned __int64
0x1800011e8  mov     [rsp+58h+var_18], r13
0x1800011ed  mov     rcx, r10; unsigned __int16 *
0x1800011f0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800011f5  xor     esi, esi
0x1800011f7  mov     [rsp+58h+arg_10], rbp
0x1800011fc  xor     r12d, r12d
0x1800011ff  mov     [rsp+58h+var_20], r14
0x180001204  mov     rbx, r10
0x180001207  mov     r13, r10
0x18000120a  nop     word ptr [rax+rax+00h]
0x180001210  movzx   eax, word ptr [rbx]
0x180001213  cmp     ax, [rdi+64h]
0x180001217  jz      short loc_180001224
0x180001219  test    ax, ax
0x18000121c  jz      short loc_180001224
0x18000121e  add     rbx, 2
0x180001222  jmp     short loc_180001298
0x180001224  xor     esi, esi
0x180001226  lea     rcx, [rdi+8]
0x18000122a  test    ax, ax
0x18000122d  mov     edx, r12d
0x180001230  setz    sil
0x180001234  xor     eax, eax
0x180001236  mov     [rbx], ax
0x180001239  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x18000123f  mov     rbp, rax
0x180001242  test    rax, rax
0x180001245  jz      short loc_18000128E
0x180001247  mov     rax, [rax+20h]
0x18000124b  mov     r9d, 0FFFFFFFFh; cchCount1
0x180001251  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x180001259  mov     r8, r13; lpString1
0x18000125c  mov     edx, 1; dwCmpFlags
0x180001261  mov     [rsp+58h+lpString2], rax; lpString2
0x180001266  mov     ecx, 7Fh; Locale
0x18000126b  call    cs:__imp_CompareStringW
0x180001271  cmp     eax, 2
0x180001274  jz      short loc_18000128E
0x180001276  mov     rdx, r13
0x180001279  lea     rcx, [rbp+20h]
0x18000127d  call    ??4TString@@QEAAAEAV0@PEAG@Z; TString::operator=(ushort *)
0x180001282  lea     rcx, [rbp+10h]
0x180001286  mov     rdx, r13
0x180001289  call    ??4TString@@QEAAAEAV0@PEAG@Z; TString::operator=(ushort *)
0x18000128e  inc     r12d
0x180001291  add     rbx, 2
0x180001295  mov     r13, rbx
0x180001298  test    esi, esi
0x18000129a  jz      loc_180001210
0x1800012a0  mov     rcx, [rsp+58h+pExceptionObject]
0x1800012a5  mov     r14, [rsp+58h+var_20]
0x1800012aa  mov     r13, [rsp+58h+var_18]
0x1800012af  mov     r12, [rsp+58h+arg_18]
0x1800012b4  mov     rbp, [rsp+58h+arg_10]
0x1800012b9  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800012bf  mov     rbx, [rsp+58h+arg_0]
0x1800012c4  mov     eax, 1
0x1800012c9  mov     r15, [rsp+58h+var_28]
0x1800012ce  add     rsp, 48h
0x1800012d2  pop     rdi
0x1800012d3  pop     rsi
0x1800012d4  retn
0x1800012d5  mov     rcx, rdi; this
0x1800012d8  call    ?Empty@CProvObj@@QEAAXXZ; CProvObj::Empty(void)
0x1800012dd  movzx   r8d, word ptr [rdi+64h]; unsigned __int16
0x1800012e2  mov     rdx, rsi; unsigned __int16 *
0x1800012e5  mov     rcx, rdi; this
0x1800012e8  call    ?Init@CProvObj@@AEAAXPEBGG@Z; CProvObj::Init(ushort const *,ushort)
0x1800012ed  mov     r15, [rsp+58h+var_28]
0x1800012f2  mov     eax, 1
0x1800012f7  add     rsp, 48h
0x1800012fb  pop     rdi
0x1800012fc  pop     rsi
0x1800012fd  retn
```
