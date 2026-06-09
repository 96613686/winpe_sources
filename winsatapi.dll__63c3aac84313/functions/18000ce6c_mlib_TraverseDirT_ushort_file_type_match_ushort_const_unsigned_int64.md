# mlib::TraverseDirT<ushort>::file_type_match(ushort const *,unsigned __int64)

- ea: `0x18000ce6c`
- end: `0x18000cf5e`
- name: `?file_type_match@?$TraverseDirT@G@mlib@@AEBA_NPEBG_K@Z`
- size: `242`
- prototype: `bool __fastcall(__int64, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d1f8`

## callees

- `0x18000ce6c`
- `0x18000d02c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000cf4d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000cf4d`

## pseudocode

```c
bool __fastcall mlib::TraverseDirT<unsigned short>::file_type_match(__int64 a1, __int64 a2, unsigned __int64 a3)
{
  unsigned __int64 v5; // r8
  __int64 v7; // rdi
  _QWORD *v8; // rsi
  unsigned __int64 v10; // r8
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rax
  const WCHAR *lpString2; // rcx

  v5 = *(_QWORD *)(a1 + 576);
  if ( v5 && a3 < v5 )
  {
    v7 = 40 * a3;
    v8 = (_QWORD *)(a1 + 592);
    if ( *(_BYTE *)(*(_QWORD *)(a1 + 592) + 40 * a3 + 33) )
      return 1;
  }
  else
  {
    v7 = 40 * a3;
    v8 = (_QWORD *)(a1 + 592);
  }
  if ( !v5 )
    return 1;
  if ( a3 >= v5 )
    return 1;
  if ( *(_QWORD *)(*v8 + v7 + 24) != 3 )
    return 1;
  v10 = a2 - 2 + 2 * mlib::TRTraitsT<unsigned short>::CStrlen(a2);
  if ( *(_WORD *)v10 == 46 )
    return 1;
  v11 = a2 - 2;
  while ( v10 > v11 )
  {
    if ( *(_WORD *)v10 == 46 )
      goto LABEL_15;
    v10 -= 2LL;
  }
  if ( v10 == v11 )
    return 1;
LABEL_15:
  v12 = *(_QWORD *)(a1 + 576);
  if ( v12 && a3 < v12 )
    lpString2 = *(const WCHAR **)(v7 + *v8 + 8);
  else
    lpString2 = 0;
  return CompareStringW(0x400u, 0x1001u, (PCNZWCH)(v10 + 2), -1, lpString2, -1) == 2;
}

```

## disassembly

```asm
0x18000ce6c  push    rbx
0x18000ce6e  push    rbp
0x18000ce6f  push    rsi
0x18000ce70  push    rdi
0x18000ce71  push    r14
0x18000ce73  sub     rsp, 30h
0x18000ce77  mov     rbx, r8
0x18000ce7a  mov     r14, rdx
0x18000ce7d  mov     r8, [rcx+240h]
0x18000ce84  mov     rbp, rcx
0x18000ce87  test    r8, r8
0x18000ce8a  jz      short loc_18000CEBB
0x18000ce8c  cmp     rbx, r8
0x18000ce8f  jnb     short loc_18000CEBB
0x18000ce91  lea     rax, [rbx+rbx*4]
0x18000ce95  lea     rdi, ds:0[rax*8]
0x18000ce9d  lea     rsi, [rcx+250h]
0x18000cea4  mov     rax, [rsi]
0x18000cea7  cmp     byte ptr [rax+rdi+21h], 0
0x18000ceac  jz      short loc_18000CECA
0x18000ceae  mov     al, 1
0x18000ceb0  add     rsp, 30h
0x18000ceb4  pop     r14
0x18000ceb6  pop     rdi
0x18000ceb7  pop     rsi
0x18000ceb8  pop     rbp
0x18000ceb9  pop     rbx
0x18000ceba  retn
0x18000cebb  lea     rdi, [rbx+rbx*4]
0x18000cebf  shl     rdi, 3
0x18000cec3  lea     rsi, [rcx+250h]
0x18000ceca  mov     rcx, rdi
0x18000cecd  mov     rax, rsi
0x18000ced0  test    r8, r8
0x18000ced3  jz      short loc_18000CEAE
0x18000ced5  cmp     rbx, r8
0x18000ced8  jnb     short loc_18000CEAE
0x18000ceda  mov     rax, [rax]
0x18000cedd  cmp     qword ptr [rax+rcx+18h], 3
0x18000cee3  jnz     short loc_18000CEAE
0x18000cee5  mov     rcx, r14
0x18000cee8  call    ?CStrlen@?$TRTraitsT@G@mlib@@SA_KPEBG_K@Z; mlib::TRTraitsT<ushort>::CStrlen(ushort const *,unsigned __int64)
0x18000ceed  lea     r8, [r14-2]
0x18000cef1  lea     r8, [r8+rax*2]
0x18000cef5  cmp     word ptr [r8], 2Eh ; '.'
0x18000cefa  jz      short loc_18000CEAE
0x18000cefc  lea     rax, [r14-2]
0x18000cf00  jmp     short loc_18000CF0D
0x18000cf02  cmp     word ptr [r8], 2Eh ; '.'
0x18000cf07  jz      short loc_18000CF14
0x18000cf09  sub     r8, 2
0x18000cf0d  cmp     r8, rax
0x18000cf10  ja      short loc_18000CF02
0x18000cf12  jz      short loc_18000CEAE
0x18000cf14  mov     rax, [rbp+240h]
0x18000cf1b  test    rax, rax
0x18000cf1e  jz      short loc_18000CF2F
0x18000cf20  cmp     rbx, rax
0x18000cf23  jnb     short loc_18000CF2F
0x18000cf25  mov     rax, [rsi]
0x18000cf28  mov     rcx, [rdi+rax+8]
0x18000cf2d  jmp     short loc_18000CF31
0x18000cf2f  xor     ecx, ecx
0x18000cf31  or      r9d, 0FFFFFFFFh; cchCount1
0x18000cf35  add     r8, 2; lpString1
0x18000cf39  mov     [rsp+58h+cchCount2], r9d; cchCount2
0x18000cf3e  mov     edx, 1001h; dwCmpFlags
0x18000cf43  mov     [rsp+58h+lpString2], rcx; lpString2
0x18000cf48  mov     ecx, 400h; Locale
0x18000cf4d  call    cs:__imp_CompareStringW
0x18000cf53  cmp     eax, 2
0x18000cf56  setz    al
0x18000cf59  jmp     loc_18000CEB0
```
