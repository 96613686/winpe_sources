# ICCInspector::ReadXYZNumber(void *,ulong,CIEXYZNumber *)

- ea: `0x18003cd70`
- end: `0x18003ce77`
- name: `?ReadXYZNumber@ICCInspector@@AEAA_NPEAXKPEAUCIEXYZNumber@@@Z`
- size: `263`
- prototype: `__int64 __fastcall(ICCInspector *this, void *, TAGTYPE, struct CIEXYZNumber *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18003ca60`

## callees

- `0x180036264`
- `0x180036530`
- `0x18003cd70`

## import_xrefs

- `mscms!GetColorProfileElement` at `0x18003cdb5`
- `mscms!GetColorProfileElement` at `0x18003cdf0`
- `mscms!GetColorProfileElement` at `0x18003cdb5`
- `mscms!GetColorProfileElement` at `0x18003cdf0`

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
0x18003cd70  push    rbx
0x18003cd72  push    rbp
0x18003cd73  push    rsi
0x18003cd74  push    rdi
0x18003cd75  push    r14
0x18003cd77  push    r15
0x18003cd79  sub     rsp, 48h
0x18003cd7d  mov     rbp, rcx
0x18003cd80  lea     rax, [rsp+78h+var_44]
0x18003cd85  xor     ecx, ecx
0x18003cd87  mov     [rsp+78h+pbReference], rax; pbReference
0x18003cd8c  mov     r14d, r8d
0x18003cd8f  mov     [rsp+78h+pcbElement], ecx
0x18003cd93  mov     r15, rdx
0x18003cd96  mov     [rsp+78h+var_44], ecx
0x18003cd9a  mov     ebx, ecx
0x18003cd9c  mov     [rsp+78h+pElement], rcx; pElement
0x18003cda1  mov     rsi, r9
0x18003cda4  mov     rcx, r15; hProfile
0x18003cda7  lea     r9, [rsp+78h+pcbElement]; pcbElement
0x18003cdac  xor     r8d, r8d; dwOffset
0x18003cdaf  mov     edx, r14d; tag
0x18003cdb2  xor     dil, dil
0x18003cdb5  call    cs:__imp_GetColorProfileElement
0x18003cdbb  cmp     [rsp+78h+pcbElement], 14h
0x18003cdc0  jnz     loc_18003CE5E
0x18003cdc6  mov     ecx, 14h; unsigned __int64
0x18003cdcb  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18003cdd0  mov     rbx, rax
0x18003cdd3  lea     r9, [rsp+78h+pcbElement]; pcbElement
0x18003cdd8  lea     rax, [rsp+78h+var_44]
0x18003cddd  xor     r8d, r8d; dwOffset
0x18003cde0  mov     [rsp+78h+pbReference], rax; pbReference
0x18003cde5  mov     edx, r14d; tag
0x18003cde8  mov     rcx, r15; hProfile
0x18003cdeb  mov     [rsp+78h+pElement], rbx; pElement
0x18003cdf0  call    cs:__imp_GetColorProfileElement
0x18003cdf6  test    eax, eax
0x18003cdf8  jz      short loc_18003CE5E
0x18003cdfa  cmp     [rbp+0], dil
0x18003cdfe  jz      short loc_18003CE0A
0x18003ce00  cmp     dword ptr [rbx], 205A5958h
0x18003ce06  jz      short loc_18003CE12
0x18003ce08  jmp     short loc_18003CE5E
0x18003ce0a  cmp     dword ptr [rbx], 58595A20h
0x18003ce10  jnz     short loc_18003CE5E
0x18003ce12  movsd   xmm1, cs:__real@3ef0000000000000
0x18003ce1a  mov     dil, 1
0x18003ce1d  mov     eax, [rbx+8]
0x18003ce20  bswap   eax
0x18003ce22  movd    xmm0, eax
0x18003ce26  mov     eax, [rbx+0Ch]
0x18003ce29  cvtdq2pd xmm0, xmm0
0x18003ce2d  bswap   eax
0x18003ce2f  mulsd   xmm0, xmm1
0x18003ce33  movsd   qword ptr [rsi], xmm0
0x18003ce37  movd    xmm0, eax
0x18003ce3b  mov     eax, [rbx+10h]
0x18003ce3e  cvtdq2pd xmm0, xmm0
0x18003ce42  bswap   eax
0x18003ce44  mulsd   xmm0, xmm1
0x18003ce48  movsd   qword ptr [rsi+8], xmm0
0x18003ce4d  movd    xmm0, eax
0x18003ce51  cvtdq2pd xmm0, xmm0
0x18003ce55  mulsd   xmm0, xmm1
0x18003ce59  movsd   qword ptr [rsi+10h], xmm0
0x18003ce5e  mov     rcx, rbx; void *
0x18003ce61  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003ce66  movzx   eax, dil
0x18003ce6a  add     rsp, 48h
0x18003ce6e  pop     r15
0x18003ce70  pop     r14
0x18003ce72  pop     rdi
0x18003ce73  pop     rsi
0x18003ce74  pop     rbp
0x18003ce75  pop     rbx
0x18003ce76  retn
```
