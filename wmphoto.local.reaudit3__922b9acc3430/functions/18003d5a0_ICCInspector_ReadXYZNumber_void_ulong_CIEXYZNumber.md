# ICCInspector::ReadXYZNumber(void *,ulong,CIEXYZNumber *)

- ea: `0x18003d5a0`
- end: `0x18003d6b4`
- name: `?ReadXYZNumber@ICCInspector@@AEAA_NPEAXKPEAUCIEXYZNumber@@@Z`
- size: `276`
- prototype: `__int64 __fastcall(ICCInspector *this, void *, TAGTYPE, struct CIEXYZNumber *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18003d270`

## callees

- `0x180036834`
- `0x180036b00`
- `0x18003d5a0`

## import_xrefs

- `mscms!GetColorProfileElement` at `0x18003d5e5`
- `mscms!GetColorProfileElement` at `0x18003d626`
- `mscms!GetColorProfileElement` at `0x18003d5e5`
- `mscms!GetColorProfileElement` at `0x18003d626`

## pseudocode

```c
__int64 __fastcall ICCInspector::ReadXYZNumber(ICCInspector *this, void *a2, TAGTYPE a3, struct CIEXYZNumber *a4)
{
  _DWORD *pElement; // rbx
  unsigned __int8 v9; // di
  unsigned __int64 v10; // rdx
  int v11; // eax
  double v12; // xmm0_8
  int v13; // eax
  DWORD pcbElement; // [rsp+30h] [rbp-48h] BYREF
  BOOL pbReference[17]; // [rsp+34h] [rbp-44h] BYREF

  pcbElement = 0;
  pbReference[0] = 0;
  pElement = 0;
  v9 = 0;
  GetColorProfileElement(a2, a3, 0, &pcbElement, 0, pbReference);
  if ( pcbElement == 20 )
  {
    pElement = operator new[](0x14u);
    if ( GetColorProfileElement(a2, a3, 0, &pcbElement, pElement, pbReference) )
    {
      if ( *(_BYTE *)this )
      {
        if ( *pElement != 542792024 )
          goto LABEL_8;
        goto LABEL_7;
      }
      if ( *pElement == 1482250784 )
      {
LABEL_7:
        v9 = 1;
        v11 = _byteswap_ulong(pElement[3]);
        *(double *)a4 = (double)(int)_byteswap_ulong(pElement[2]) * 0.0000152587890625;
        v12 = (double)v11;
        v13 = _byteswap_ulong(pElement[4]);
        *((double *)a4 + 1) = v12 * 0.0000152587890625;
        *((double *)a4 + 2) = (double)v13 * 0.0000152587890625;
      }
    }
  }
LABEL_8:
  operator delete(pElement, v10);
  return v9;
}

```

## disassembly

```asm
0x18003d5a0  push    rbx
0x18003d5a2  push    rbp
0x18003d5a3  push    rsi
0x18003d5a4  push    rdi
0x18003d5a5  push    r14
0x18003d5a7  push    r15
0x18003d5a9  sub     rsp, 48h
0x18003d5ad  mov     rbp, rcx
0x18003d5b0  lea     rax, [rsp+78h+var_44]
0x18003d5b5  xor     ecx, ecx
0x18003d5b7  mov     [rsp+78h+pbReference], rax; pbReference
0x18003d5bc  mov     r14d, r8d
0x18003d5bf  mov     [rsp+78h+pcbElement], ecx
0x18003d5c3  mov     r15, rdx
0x18003d5c6  mov     [rsp+78h+var_44], ecx
0x18003d5ca  mov     ebx, ecx
0x18003d5cc  mov     [rsp+78h+pElement], rcx; pElement
0x18003d5d1  mov     rsi, r9
0x18003d5d4  mov     rcx, r15; hProfile
0x18003d5d7  lea     r9, [rsp+78h+pcbElement]; pcbElement
0x18003d5dc  xor     r8d, r8d; dwOffset
0x18003d5df  mov     edx, r14d; tag
0x18003d5e2  xor     dil, dil
0x18003d5e5  call    cs:__imp_GetColorProfileElement
0x18003d5ec  nop     dword ptr [rax+rax+00h]
0x18003d5f1  cmp     [rsp+78h+pcbElement], 14h
0x18003d5f6  jnz     loc_18003D69A
0x18003d5fc  mov     ecx, 14h; unsigned __int64
0x18003d601  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18003d606  mov     rbx, rax
0x18003d609  lea     r9, [rsp+78h+pcbElement]; pcbElement
0x18003d60e  lea     rax, [rsp+78h+var_44]
0x18003d613  xor     r8d, r8d; dwOffset
0x18003d616  mov     [rsp+78h+pbReference], rax; pbReference
0x18003d61b  mov     edx, r14d; tag
0x18003d61e  mov     rcx, r15; hProfile
0x18003d621  mov     [rsp+78h+pElement], rbx; pElement
0x18003d626  call    cs:__imp_GetColorProfileElement
0x18003d62d  nop     dword ptr [rax+rax+00h]
0x18003d632  test    eax, eax
0x18003d634  jz      short loc_18003D69A
0x18003d636  cmp     [rbp+0], dil
0x18003d63a  jz      short loc_18003D646
0x18003d63c  cmp     dword ptr [rbx], 205A5958h
0x18003d642  jz      short loc_18003D64E
0x18003d644  jmp     short loc_18003D69A
0x18003d646  cmp     dword ptr [rbx], 58595A20h
0x18003d64c  jnz     short loc_18003D69A
0x18003d64e  movsd   xmm1, cs:__real@3ef0000000000000
0x18003d656  mov     dil, 1
0x18003d659  mov     eax, [rbx+8]
0x18003d65c  bswap   eax
0x18003d65e  movd    xmm0, eax
0x18003d662  mov     eax, [rbx+0Ch]
0x18003d665  cvtdq2pd xmm0, xmm0
0x18003d669  bswap   eax
0x18003d66b  mulsd   xmm0, xmm1
0x18003d66f  movsd   qword ptr [rsi], xmm0
0x18003d673  movd    xmm0, eax
0x18003d677  mov     eax, [rbx+10h]
0x18003d67a  cvtdq2pd xmm0, xmm0
0x18003d67e  bswap   eax
0x18003d680  mulsd   xmm0, xmm1
0x18003d684  movsd   qword ptr [rsi+8], xmm0
0x18003d689  movd    xmm0, eax
0x18003d68d  cvtdq2pd xmm0, xmm0
0x18003d691  mulsd   xmm0, xmm1
0x18003d695  movsd   qword ptr [rsi+10h], xmm0
0x18003d69a  mov     rcx, rbx; void *
0x18003d69d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003d6a2  movzx   eax, dil
0x18003d6a6  add     rsp, 48h
0x18003d6aa  pop     r15
0x18003d6ac  pop     r14
0x18003d6ae  pop     rdi
0x18003d6af  pop     rsi
0x18003d6b0  pop     rbp
0x18003d6b1  pop     rbx
0x18003d6b2  retn
```
