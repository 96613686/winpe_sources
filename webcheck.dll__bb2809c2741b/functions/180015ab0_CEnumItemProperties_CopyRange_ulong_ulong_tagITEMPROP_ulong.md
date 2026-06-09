# CEnumItemProperties::CopyRange(ulong,ulong,_tagITEMPROP *,ulong *)

- ea: `0x180015ab0`
- end: `0x180015bb4`
- name: `?CopyRange@CEnumItemProperties@@QEAAJKKPEAU_tagITEMPROP@@PEAK@Z`
- size: `260`
- prototype: `__int64 __fastcall(CEnumItemProperties *__hidden this, unsigned int, unsigned int, struct _tagITEMPROP *, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800159d0`
- `0x180015f60`

## callees

- `0x180003950`
- `0x180015ab0`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180015b20`
- `ole32!CoTaskMemAlloc` at `0x180015b20`
- `OLEAUT32!__imp_VariantCopy` at `0x180015b4f`
- `OLEAUT32!__imp_VariantCopy` at `0x180015b4f`

## pseudocode

```c
__int64 __fastcall CEnumItemProperties::CopyRange(
        CEnumItemProperties *this,
        unsigned int a2,
        unsigned int a3,
        struct _tagITEMPROP *a4,
        unsigned int *a5)
{
  int v6; // r10d
  unsigned int v7; // ebx
  __int64 v10; // r13
  const unsigned __int16 *v11; // rsi
  struct _tagITEMPROP *v12; // r12
  __int64 v13; // rax
  SIZE_T v14; // r14
  unsigned __int16 *v15; // rax
  VARTYPE v16; // r11
  HRESULT v17; // eax
  struct _tagITEMPROP *v19; // [rsp+88h] [rbp+20h]

  v19 = a4;
  v6 = 0;
  v7 = 0;
  do
  {
    if ( a2 >= *((_DWORD *)this + 4) || v7 >= a3 )
      break;
    v10 = *((_QWORD *)this + 3) + 32LL * a2;
    v11 = *(const unsigned __int16 **)(v10 + 24);
    if ( v11 )
    {
      v12 = &a4[v7];
      v13 = -1;
      do
        ++v13;
      while ( v11[v13] );
      v14 = (unsigned int)(2 * v13 + 2);
      v15 = (unsigned __int16 *)CoTaskMemAlloc(v14);
      v12->pwszName = v15;
      if ( v15 )
      {
        StringCchCopyW(v15, v14 >> 1, v11);
        v12->variantValue.vt = v16;
        v17 = VariantCopy(&v12->variantValue, (const VARIANTARG *)v10);
        a4 = v19;
        v6 = v17;
      }
      else
      {
        a4 = v19;
        v6 = -2147024882;
      }
    }
    else
    {
      v6 = -2147418113;
    }
    ++a2;
    ++v7;
  }
  while ( !v6 );
  *a5 = v7;
  if ( v6 >= 0 )
    return v7 != a3;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180015ab0  mov     [rsp+arg_18], r9
0x180015ab5  push    rbx
0x180015ab6  push    rbp
0x180015ab7  push    rsi
0x180015ab8  push    rdi
0x180015ab9  push    r12
0x180015abb  push    r13
0x180015abd  push    r14
0x180015abf  push    r15
0x180015ac1  sub     rsp, 28h
0x180015ac5  xor     r11d, r11d
0x180015ac8  mov     ebp, r8d
0x180015acb  mov     r10d, r11d
0x180015ace  mov     ebx, r11d
0x180015ad1  mov     edi, edx
0x180015ad3  mov     r15, rcx
0x180015ad6  cmp     edi, [r15+10h]
0x180015ada  jnb     loc_180015B88
0x180015ae0  cmp     ebx, ebp
0x180015ae2  jnb     loc_180015B88
0x180015ae8  mov     r13d, edi
0x180015aeb  shl     r13, 5
0x180015aef  add     r13, [r15+18h]
0x180015af3  mov     rsi, [r13+18h]
0x180015af7  test    rsi, rsi
0x180015afa  jz      short loc_180015B75
0x180015afc  mov     r12d, ebx
0x180015aff  shl     r12, 5
0x180015b03  add     r12, r9
0x180015b06  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015b0a  inc     rax
0x180015b0d  cmp     [rsi+rax*2], r11w
0x180015b12  jnz     short loc_180015B0A
0x180015b14  lea     eax, ds:2[rax*2]
0x180015b1b  mov     ecx, eax; cb
0x180015b1d  mov     r14d, eax
0x180015b20  call    cs:__imp_CoTaskMemAlloc
0x180015b26  xor     r11d, r11d
0x180015b29  mov     [r12+18h], rax
0x180015b2e  test    rax, rax
0x180015b31  jz      short loc_180015B65
0x180015b33  shr     r14, 1
0x180015b36  mov     r8, rsi; unsigned __int16 *
0x180015b39  mov     rdx, r14; unsigned __int64
0x180015b3c  mov     rcx, rax; unsigned __int16 *
0x180015b3f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180015b44  mov     rdx, r13; pvargSrc
0x180015b47  mov     [r12], r11w
0x180015b4c  mov     rcx, r12; pvargDest
0x180015b4f  call    cs:__imp_VariantCopy
0x180015b55  mov     r9, [rsp+68h+arg_18]
0x180015b5d  xor     r11d, r11d
0x180015b60  mov     r10d, eax
0x180015b63  jmp     short loc_180015B7B
0x180015b65  mov     r9, [rsp+68h+arg_18]
0x180015b6d  mov     r10d, 8007000Eh
0x180015b73  jmp     short loc_180015B7B
0x180015b75  mov     r10d, 8000FFFFh
0x180015b7b  inc     edi
0x180015b7d  inc     ebx
0x180015b7f  test    r10d, r10d
0x180015b82  jz      loc_180015AD6
0x180015b88  mov     rax, [rsp+68h+arg_20]
0x180015b90  mov     [rax], ebx
0x180015b92  test    r10d, r10d
0x180015b95  js      short loc_180015BA0
0x180015b97  cmp     ebx, ebp
0x180015b99  mov     r10d, r11d
0x180015b9c  setnz   r10b
0x180015ba0  mov     eax, r10d
0x180015ba3  add     rsp, 28h
0x180015ba7  pop     r15
0x180015ba9  pop     r14
0x180015bab  pop     r13
0x180015bad  pop     r12
0x180015baf  pop     rdi
0x180015bb0  pop     rsi
0x180015bb1  pop     rbp
0x180015bb2  pop     rbx
0x180015bb3  retn
```
