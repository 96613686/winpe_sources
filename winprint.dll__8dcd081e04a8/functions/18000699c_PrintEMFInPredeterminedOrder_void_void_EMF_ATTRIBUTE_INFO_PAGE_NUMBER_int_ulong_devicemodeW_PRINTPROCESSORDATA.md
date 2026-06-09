# PrintEMFInPredeterminedOrder(void *,void *,_EMF_ATTRIBUTE_INFO *,_PAGE_NUMBER *,int,ulong,_devicemodeW *,_PRINTPROCESSORDATA *)

- ea: `0x18000699c`
- end: `0x180006b63`
- name: `?PrintEMFInPredeterminedOrder@@YAHPEAX0PEAU_EMF_ATTRIBUTE_INFO@@PEAU_PAGE_NUMBER@@HKPEAU_devicemodeW@@PEAU_PRINTPROCESSORDATA@@@Z`
- size: `455`
- prototype: `int(void *, void *, struct _EMF_ATTRIBUTE_INFO *, struct _PAGE_NUMBER *, int, unsigned int, struct _devicemodeW *, struct _PRINTPROCESSORDATA *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180006b6c`

## callees

- `0x1800047f0`
- `0x18000699c`
- `0x180008010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180006a3d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180006a3d`

## pseudocode

```c
__int64 __fastcall PrintEMFInPredeterminedOrder(
        void *a1,
        HDC a2,
        struct _EMF_ATTRIBUTE_INFO *a3,
        struct _PAGE_NUMBER *a4,
        int a5,
        unsigned int a6,
        struct _devicemodeW *a7,
        HANDLE *a8)
{
  unsigned int v8; // esi
  struct _PAGE_NUMBER *v9; // rdi
  unsigned int v12; // r9d
  unsigned int v13; // edx
  unsigned int (__fastcall *v14)(void *, HDC, struct _EMF_ATTRIBUTE_INFO *, struct _PAGE_NUMBER *, int, unsigned int, struct _devicemodeW *); // rbp
  struct _devicemodeW *v15; // r12
  unsigned int i; // r8d
  int v17; // r12d
  struct _PAGE_NUMBER **v18; // rax
  int v20; // [rsp+40h] [rbp-48h]
  void *v21; // [rsp+90h] [rbp+8h]
  unsigned int v22; // [rsp+A0h] [rbp+18h]
  unsigned int v23; // [rsp+A8h] [rbp+20h]

  v21 = a1;
  v8 = 0;
  v9 = a4;
  if ( a4 )
  {
    v12 = *((_DWORD *)a3 + 12);
    v13 = *((_DWORD *)a3 + 11);
    v22 = v12;
    v23 = v13;
    v20 = *((_DWORD *)a3 + 21);
    if ( *((_DWORD *)a3 + 19) )
    {
      v14 = (unsigned int (__fastcall *)(void *, HDC, struct _EMF_ATTRIBUTE_INFO *, struct _PAGE_NUMBER *, int, unsigned int, struct _devicemodeW *))PrintOneSideBookletEMF;
    }
    else
    {
      v14 = (unsigned int (__fastcall *)(void *, HDC, struct _EMF_ATTRIBUTE_INFO *, struct _PAGE_NUMBER *, int, unsigned int, struct _devicemodeW *))PrintOneSideReverseEMF;
      if ( *((_DWORD *)a3 + 9) != 1 )
        v14 = (unsigned int (__fastcall *)(void *, HDC, struct _EMF_ATTRIBUTE_INFO *, struct _PAGE_NUMBER *, int, unsigned int, struct _devicemodeW *))PrintOneSideReverseForDriverEMF;
    }
    v15 = a7;
    while ( v9 )
    {
      if ( ((_BYTE)a8[2] & 8) != 0 )
      {
        WaitForSingleObject(a8[3], 0xFFFFFFFF);
        a1 = v21;
        v13 = v23;
        v12 = v22;
      }
      if ( v20 )
      {
        if ( !v14(a1, a2, a3, v9, a5, a6, v15) )
          return v8;
      }
      else
      {
        for ( i = v13; i; i = v17 )
        {
          v17 = v12 < i ? i - v12 : 0;
          if ( i > v12 )
            i = v12;
          SetDrvCopies(a2, a7, i);
          if ( !v14(v21, a2, a3, v9, a5, a6, a7) )
            return v8;
          v12 = v22;
        }
        v15 = a7;
      }
      v18 = *(struct _PAGE_NUMBER ***)v9;
      a1 = v21;
      v9 = *(struct _PAGE_NUMBER **)v9;
      v13 = v23;
      v12 = v22;
      if ( a5 )
      {
        if ( v18 )
          v9 = *v18;
      }
    }
    return 1;
  }
  return v8;
}

```

## disassembly

```asm
0x18000699c  mov     [rsp+arg_8], rbx
0x1800069a1  mov     [rsp+arg_0], rcx
0x1800069a6  push    rbp
0x1800069a7  push    rsi
0x1800069a8  push    rdi
0x1800069a9  push    r12
0x1800069ab  push    r13
0x1800069ad  push    r14
0x1800069af  push    r15
0x1800069b1  sub     rsp, 50h
0x1800069b5  xor     esi, esi
0x1800069b7  mov     rdi, r9
0x1800069ba  mov     rbx, r8
0x1800069bd  mov     r13, rdx
0x1800069c0  test    r9, r9
0x1800069c3  jz      loc_180006B49
0x1800069c9  mov     r9d, [r8+30h]
0x1800069cd  mov     edx, [r8+2Ch]
0x1800069d1  mov     eax, [r8+54h]
0x1800069d5  mov     [rsp+88h+arg_10], r9d
0x1800069dd  mov     [rsp+88h+arg_18], edx
0x1800069e4  mov     [rsp+88h+var_48], eax
0x1800069e8  cmp     [r8+4Ch], esi
0x1800069ec  jz      short loc_1800069F7
0x1800069ee  lea     rbp, ?PrintOneSideBookletEMF@@YAHPEAX0PEAU_EMF_ATTRIBUTE_INFO@@PEAU_PAGE_NUMBER@@HKPEAU_devicemodeW@@@Z; PrintOneSideBookletEMF(void *,void *,_EMF_ATTRIBUTE_INFO *,_PAGE_NUMBER *,int,ulong,_devicemodeW *)
0x1800069f5  jmp     short loc_180006A0E
0x1800069f7  cmp     dword ptr [r8+24h], 1
0x1800069fc  lea     rbp, ?PrintOneSideReverseEMF@@YAHPEAX0PEAU_EMF_ATTRIBUTE_INFO@@PEAU_PAGE_NUMBER@@HKPEAU_devicemodeW@@@Z; PrintOneSideReverseEMF(void *,void *,_EMF_ATTRIBUTE_INFO *,_PAGE_NUMBER *,int,ulong,_devicemodeW *)
0x180006a03  lea     rax, ?PrintOneSideReverseForDriverEMF@@YAHPEAX0PEAU_EMF_ATTRIBUTE_INFO@@PEAU_PAGE_NUMBER@@HKPEAU_devicemodeW@@@Z; PrintOneSideReverseForDriverEMF(void *,void *,_EMF_ATTRIBUTE_INFO *,_PAGE_NUMBER *,int,ulong,_devicemodeW *)
0x180006a0a  cmovnz  rbp, rax
0x180006a0e  mov     r15, [rsp+88h+arg_38]
0x180006a16  mov     r14d, [rsp+88h+arg_20]
0x180006a1e  mov     r12, [rsp+88h+arg_30]
0x180006a26  test    rdi, rdi
0x180006a29  jz      loc_180006B44
0x180006a2f  test    byte ptr [r15+10h], 8
0x180006a34  jz      short loc_180006A5A
0x180006a36  mov     rcx, [r15+18h]; hHandle
0x180006a3a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180006a3d  call    cs:__imp_WaitForSingleObject
0x180006a43  mov     rcx, [rsp+88h+arg_0]
0x180006a4b  mov     edx, [rsp+88h+arg_18]
0x180006a52  mov     r9d, [rsp+88h+arg_10]
0x180006a5a  cmp     [rsp+88h+var_48], esi
0x180006a5e  jz      short loc_180006A90
0x180006a60  mov     eax, [rsp+88h+arg_28]
0x180006a67  mov     r9, rdi
0x180006a6a  mov     [rsp+88h+var_58], r12
0x180006a6f  mov     r8, rbx
0x180006a72  mov     [rsp+88h+var_60], eax
0x180006a76  mov     rdx, r13
0x180006a79  mov     rax, rbp
0x180006a7c  mov     [rsp+88h+var_68], r14d
0x180006a81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a86  test    eax, eax
0x180006a88  jz      loc_180006B49
0x180006a8e  jmp     short loc_180006B0D
0x180006a90  mov     r8d, edx
0x180006a93  test    r8d, r8d
0x180006a96  jz      short loc_180006B05
0x180006a98  mov     rdx, [rsp+88h+arg_30]; struct _devicemodeW *
0x180006aa0  mov     eax, r8d
0x180006aa3  sub     eax, r9d
0x180006aa6  mov     rcx, r13; hdc
0x180006aa9  cmp     r9d, r8d
0x180006aac  sbb     r12d, r12d
0x180006aaf  and     r12d, eax
0x180006ab2  cmp     r8d, r9d
0x180006ab5  cmova   r8d, r9d; unsigned int
0x180006ab9  call    ?SetDrvCopies@@YAHPEAXPEAU_devicemodeW@@K@Z; SetDrvCopies(void *,_devicemodeW *,ulong)
0x180006abe  mov     rax, [rsp+88h+arg_30]
0x180006ac6  mov     r9, rdi
0x180006ac9  mov     rcx, [rsp+88h+arg_0]
0x180006ad1  mov     r8, rbx
0x180006ad4  mov     [rsp+88h+var_58], rax
0x180006ad9  mov     rdx, r13
0x180006adc  mov     eax, [rsp+88h+arg_28]
0x180006ae3  mov     [rsp+88h+var_60], eax
0x180006ae7  mov     rax, rbp
0x180006aea  mov     [rsp+88h+var_68], r14d
0x180006aef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006af4  test    eax, eax
0x180006af6  jz      short loc_180006B49
0x180006af8  mov     r9d, [rsp+88h+arg_10]
0x180006b00  mov     r8d, r12d
0x180006b03  jmp     short loc_180006A93
0x180006b05  mov     r12, [rsp+88h+arg_30]
0x180006b0d  mov     rax, [rdi]
0x180006b10  mov     rcx, [rsp+88h+arg_0]
0x180006b18  mov     rdi, rax
0x180006b1b  mov     edx, [rsp+88h+arg_18]
0x180006b22  mov     r9d, [rsp+88h+arg_10]
0x180006b2a  test    r14d, r14d
0x180006b2d  jz      loc_180006A26
0x180006b33  test    rax, rax
0x180006b36  jz      loc_180006A26
0x180006b3c  mov     rdi, [rax]
0x180006b3f  jmp     loc_180006A26
0x180006b44  mov     esi, 1
0x180006b49  mov     rbx, [rsp+88h+arg_8]
0x180006b51  mov     eax, esi
0x180006b53  add     rsp, 50h
0x180006b57  pop     r15
0x180006b59  pop     r14
0x180006b5b  pop     r13
0x180006b5d  pop     r12
0x180006b5f  pop     rdi
0x180006b60  pop     rsi
0x180006b61  pop     rbp
0x180006b62  retn
```
