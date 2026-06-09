# CSamPropStore::_CopyPropertyValueIntoStruct(tagPROPVARIANT *,void *)

- ea: `0x1800161e8`
- end: `0x18001632a`
- name: `?_CopyPropertyValueIntoStruct@CSamPropStore@@AEAAJPEAUtagPROPVARIANT@@PEAX@Z`
- size: `322`
- prototype: `int(CSamPropStore *__hidden this, struct tagPROPVARIANT *, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180015660`

## callees

- `0x1800161e8`
- `0x180016ce9`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180016303`
- `ntdll!RtlInitUnicodeString` at `0x180016303`
- `PROPSYS!PropVariantToFileTime` at `0x180016206`
- `PROPSYS!PropVariantToFileTime` at `0x180016206`
- `PROPSYS!PropVariantToString` at `0x1800162f1`
- `PROPSYS!PropVariantToString` at `0x1800162f1`
- `PROPSYS!PropVariantToUInt64WithDefault` at `0x180016256`
- `PROPSYS!PropVariantToUInt64WithDefault` at `0x180016256`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001630e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001630e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016297`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800162da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016297`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800162da`

## pseudocode

```c
__int64 __fastcall CSamPropStore::_CopyPropertyValueIntoStruct(
        CSamPropStore *this,
        const PROPVARIANT *a2,
        FILETIME *a3)
{
  unsigned int v5; // edi
  LONG v6; // eax
  unsigned int v7; // eax
  void *v8; // rax
  __int64 v9; // rcx
  __int64 v10; // r14
  WCHAR *v11; // rax
  WCHAR *v12; // rbp

  if ( *(_WORD *)a2 == 64 )
    return (unsigned int)PropVariantToFileTime(a2, 0, a3);
  v5 = 0;
  switch ( *(_WORD *)a2 )
  {
    case 0x1F:
    case 8:
      v9 = -1;
      do
        ++v9;
      while ( *(_WORD *)(*((_QWORD *)a2 + 1) + 2 * v9) );
      v10 = v9 + 1;
      if ( v9 != -1 )
      {
        v11 = (WCHAR *)CoTaskMemAlloc(2 * v10);
        v12 = v11;
        if ( v11 )
        {
          v5 = PropVariantToString(a2, v11, v10);
          if ( (v5 & 0x80000000) != 0 )
            CoTaskMemFree(v12);
          else
            RtlInitUnicodeString((PUNICODE_STRING)a3, v12);
        }
        else
        {
          return (unsigned int)-2147024882;
        }
      }
      break;
    case 0x12:
      LOWORD(a3->dwLowDateTime) = *((_WORD *)a2 + 4);
      return v5;
    case 0x13:
      v6 = *((_DWORD *)a2 + 2);
LABEL_13:
      a3->dwLowDateTime = v6;
      return v5;
    case 0x15:
      *a3 = (FILETIME)PropVariantToUInt64WithDefault(a2, 0);
      return v5;
    case 0xB:
      v6 = *((_WORD *)a2 + 4) == 0xFFFF;
      goto LABEL_13;
    case 0x41:
      v7 = *((_DWORD *)a2 + 2);
      v5 = -2147024882;
      a3->dwLowDateTime = v7;
      v8 = CoTaskMemAlloc(v7);
      a3[1] = (FILETIME)v8;
      if ( v8 )
      {
        memcpy_0(v8, *((const void **)a2 + 2), *((unsigned int *)a2 + 2));
        return 0;
      }
      break;
  }
  return v5;
}

```

## disassembly

```asm
0x1800161e8  push    rbx
0x1800161ea  push    rbp
0x1800161eb  push    rsi
0x1800161ec  push    rdi
0x1800161ed  push    r14
0x1800161ef  push    r15
0x1800161f1  sub     rsp, 28h
0x1800161f5  cmp     word ptr [rdx], 40h ; '@'
0x1800161f9  mov     rsi, r8
0x1800161fc  mov     rbx, rdx
0x1800161ff  jnz     short loc_180016213
0x180016201  xor     edx, edx; pstfOut
0x180016203  mov     rcx, rbx; propvar
0x180016206  call    cs:__imp_PropVariantToFileTime
0x18001620c  mov     edi, eax
0x18001620e  jmp     loc_18001631B
0x180016213  xor     r15d, r15d
0x180016216  cmp     word ptr [rdx], 1Fh
0x18001621a  mov     edi, r15d
0x18001621d  jz      loc_1800162BB
0x180016223  cmp     word ptr [rdx], 8
0x180016227  jz      loc_1800162BB
0x18001622d  cmp     word ptr [rdx], 12h
0x180016231  jnz     short loc_180016240
0x180016233  movzx   eax, word ptr [rdx+8]
0x180016237  mov     [r8], ax
0x18001623b  jmp     loc_18001631B
0x180016240  cmp     word ptr [rdx], 13h
0x180016244  jnz     short loc_18001624B
0x180016246  mov     eax, [rdx+8]
0x180016249  jmp     short loc_180016278
0x18001624b  cmp     word ptr [rdx], 15h
0x18001624f  jnz     short loc_180016264
0x180016251  xor     edx, edx; ullDefault
0x180016253  mov     rcx, rbx; propvarIn
0x180016256  call    cs:__imp_PropVariantToUInt64WithDefault
0x18001625c  mov     [rsi], rax
0x18001625f  jmp     loc_18001631B
0x180016264  cmp     word ptr [rdx], 0Bh
0x180016268  jnz     short loc_180016280
0x18001626a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001626e  mov     eax, r15d
0x180016271  cmp     [rdx+8], cx
0x180016275  setz    al
0x180016278  mov     [r8], eax
0x18001627b  jmp     loc_18001631B
0x180016280  cmp     word ptr [rdx], 41h ; 'A'
0x180016284  jnz     loc_18001631B
0x18001628a  mov     eax, [rdx+8]
0x18001628d  mov     edi, 8007000Eh
0x180016292  mov     ecx, eax; cb
0x180016294  mov     [r8], eax
0x180016297  call    cs:__imp_CoTaskMemAlloc
0x18001629d  mov     [rsi+8], rax
0x1800162a1  test    rax, rax
0x1800162a4  jz      short loc_18001631B
0x1800162a6  mov     r8d, [rbx+8]; Size
0x1800162aa  mov     rcx, rax; void *
0x1800162ad  mov     rdx, [rbx+10h]; Src
0x1800162b1  call    memcpy_0
0x1800162b6  mov     edi, r15d
0x1800162b9  jmp     short loc_18001631B
0x1800162bb  mov     rax, [rdx+8]
0x1800162bf  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800162c3  inc     rcx
0x1800162c6  cmp     [rax+rcx*2], r15w
0x1800162cb  jnz     short loc_1800162C3
0x1800162cd  lea     r14, [rcx+1]
0x1800162d1  test    r14, r14
0x1800162d4  jz      short loc_18001631B
0x1800162d6  lea     rcx, [r14+r14]; cb
0x1800162da  call    cs:__imp_CoTaskMemAlloc
0x1800162e0  mov     rbp, rax
0x1800162e3  test    rax, rax
0x1800162e6  jz      short loc_180016316
0x1800162e8  mov     r8d, r14d; cch
0x1800162eb  mov     rdx, rax; psz
0x1800162ee  mov     rcx, rbx; propvar
0x1800162f1  call    cs:__imp_PropVariantToString
0x1800162f7  mov     edi, eax
0x1800162f9  test    eax, eax
0x1800162fb  js      short loc_18001630B
0x1800162fd  mov     rdx, rbp; SourceString
0x180016300  mov     rcx, rsi; DestinationString
0x180016303  call    cs:__imp_RtlInitUnicodeString
0x180016309  jmp     short loc_18001631B
0x18001630b  mov     rcx, rbp; pv
0x18001630e  call    cs:__imp_CoTaskMemFree
0x180016314  jmp     short loc_18001631B
0x180016316  mov     edi, 8007000Eh
0x18001631b  mov     eax, edi
0x18001631d  add     rsp, 28h
0x180016321  pop     r15
0x180016323  pop     r14
0x180016325  pop     rdi
0x180016326  pop     rsi
0x180016327  pop     rbp
0x180016328  pop     rbx
0x180016329  retn
```
