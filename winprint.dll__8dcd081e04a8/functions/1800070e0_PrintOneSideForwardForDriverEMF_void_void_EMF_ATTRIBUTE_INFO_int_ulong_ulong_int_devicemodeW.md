# PrintOneSideForwardForDriverEMF(void *,void *,_EMF_ATTRIBUTE_INFO *,int,ulong,ulong,int *,_devicemodeW *)

- ea: `0x1800070e0`
- end: `0x1800071fb`
- name: `?PrintOneSideForwardForDriverEMF@@YAKPEAX0PEAU_EMF_ATTRIBUTE_INFO@@HKKPEAHPEAU_devicemodeW@@@Z`
- size: `283`
- prototype: `unsigned int(void *, void *, struct _EMF_ATTRIBUTE_INFO *, int, unsigned int, unsigned int, int *, struct _devicemodeW *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x1800065e8`
- `0x180006bcc`
- `0x1800070e0`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800071db`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800071db`

## pseudocode

```c
__int64 __fastcall PrintOneSideForwardForDriverEMF(
        void *a1,
        void *a2,
        struct _EMF_ATTRIBUTE_INFO *a3,
        int a4,
        unsigned int a5,
        unsigned int a6,
        int *a7,
        struct _devicemodeW *a8)
{
  int *v8; // r14
  __int64 result; // rax
  unsigned int v12; // ebp
  struct _devicemodeW *v13; // r13
  unsigned int v14; // r15d
  unsigned int v15; // ebx
  BOOL v16; // esi
  struct _PAGE_NUMBER *v17; // [rsp+40h] [rbp-48h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-40h] BYREF
  int v21; // [rsp+A0h] [rbp+18h] BYREF

  v8 = a7;
  result = 0;
  hMem = 0;
  v17 = 0;
  v21 = 0;
  *a7 = 0;
  v12 = *((_DWORD *)a3 + 9);
  if ( v12 > 1 && *((_DWORD *)a3 + 8) <= 1u && *((_DWORD *)a3 + 15) )
  {
    v13 = a8;
    v14 = a6;
    v15 = 0;
    v16 = a4 != 0;
    if ( (unsigned int)GetStartPageListForwardForDriver(a3, a8, (struct _PAGE_NUMBER **)&hMem, &v17, a6)
      && (unsigned int)PrintOneSheetPreDeterminedForDriverEMF(a1, a2, a3, a4, v17, a5, &v21, v13) )
    {
      if ( v21 )
        *v8 = 1;
      else
        v15 = v14 + v12 * (v16 + 1);
    }
    LocalFree(hMem);
    return v15;
  }
  return result;
}

```

## disassembly

```asm
0x1800070e0  mov     r11, rsp
0x1800070e3  mov     [r11+20h], rbx
0x1800070e7  mov     [r11+10h], rdx
0x1800070eb  mov     [r11+8], rcx
0x1800070ef  push    rbp
0x1800070f0  push    rsi
0x1800070f1  push    rdi
0x1800070f2  push    r12
0x1800070f4  push    r13
0x1800070f6  push    r14
0x1800070f8  push    r15
0x1800070fa  sub     rsp, 50h
0x1800070fe  mov     r14, [rsp+88h+arg_30]
0x180007106  xor     eax, eax
0x180007108  mov     r12d, r9d
0x18000710b  mov     [r11-40h], rax
0x18000710f  mov     rdi, r8
0x180007112  mov     [r11-48h], rax
0x180007116  mov     [r11+18h], eax
0x18000711a  mov     [r14], eax
0x18000711d  mov     ebp, [r8+24h]
0x180007121  cmp     ebp, 1
0x180007124  jbe     loc_1800071E3
0x18000712a  cmp     dword ptr [r8+20h], 1
0x18000712f  ja      loc_1800071E3
0x180007135  cmp     [r8+3Ch], eax
0x180007139  jz      loc_1800071E3
0x18000713f  mov     r13, [rsp+88h+arg_38]
0x180007147  lea     r8, [r11-40h]; struct _PAGE_NUMBER **
0x18000714b  mov     r15d, [rsp+88h+arg_28]
0x180007153  mov     ebx, eax
0x180007155  mov     eax, r9d
0x180007158  mov     [r11-68h], r15d
0x18000715c  neg     eax
0x18000715e  lea     r9, [r11-48h]; struct _PAGE_NUMBER **
0x180007162  mov     rdx, r13; struct _devicemodeW *
0x180007165  mov     rcx, rdi; struct _EMF_ATTRIBUTE_INFO *
0x180007168  sbb     esi, esi
0x18000716a  neg     esi
0x18000716c  call    ?GetStartPageListForwardForDriver@@YAHPEAU_EMF_ATTRIBUTE_INFO@@PEAU_devicemodeW@@PEAPEAU_PAGE_NUMBER@@2K@Z; GetStartPageListForwardForDriver(_EMF_ATTRIBUTE_INFO *,_devicemodeW *,_PAGE_NUMBER * *,_PAGE_NUMBER * *,ulong)
0x180007171  test    eax, eax
0x180007173  jz      short loc_1800071D6
0x180007175  mov     rdx, [rsp+88h+arg_8]; void *
0x18000717d  lea     rax, [rsp+88h+arg_10]
0x180007185  mov     rcx, [rsp+88h+SpoolFileHandle]; SpoolFileHandle
0x18000718d  mov     r9d, r12d; int
0x180007190  mov     [rsp+88h+var_50], r13; struct _devicemodeW *
0x180007195  mov     r8, rdi; struct _EMF_ATTRIBUTE_INFO *
0x180007198  mov     [rsp+88h+var_58], rax; int *
0x18000719d  mov     eax, [rsp+88h+arg_20]
0x1800071a4  mov     [rsp+88h+var_60], eax; unsigned int
0x1800071a8  mov     rax, [rsp+88h+var_48]
0x1800071ad  mov     [rsp+88h+var_68], rax; struct _PAGE_NUMBER *
0x1800071b2  call    ?PrintOneSheetPreDeterminedForDriverEMF@@YAHPEAX0PEAU_EMF_ATTRIBUTE_INFO@@HPEAU_PAGE_NUMBER@@KPEAHPEAU_devicemodeW@@@Z; PrintOneSheetPreDeterminedForDriverEMF(void *,void *,_EMF_ATTRIBUTE_INFO *,int,_PAGE_NUMBER *,ulong,int *,_devicemodeW *)
0x1800071b7  test    eax, eax
0x1800071b9  jz      short loc_1800071D6
0x1800071bb  cmp     [rsp+88h+arg_10], ebx
0x1800071c2  jz      short loc_1800071CD
0x1800071c4  mov     dword ptr [r14], 1
0x1800071cb  jmp     short loc_1800071D6
0x1800071cd  lea     ebx, [rsi+1]
0x1800071d0  imul    ebx, ebp
0x1800071d3  add     ebx, r15d
0x1800071d6  mov     rcx, [rsp+88h+hMem]; hMem
0x1800071db  call    cs:__imp_LocalFree
0x1800071e1  mov     eax, ebx
0x1800071e3  mov     rbx, [rsp+88h+arg_18]
0x1800071eb  add     rsp, 50h
0x1800071ef  pop     r15
0x1800071f1  pop     r14
0x1800071f3  pop     r13
0x1800071f5  pop     r12
0x1800071f7  pop     rdi
0x1800071f8  pop     rsi
0x1800071f9  pop     rbp
0x1800071fa  retn
```
