# WdsImgCreateImageGroup

- ea: `0x1800068e0`
- end: `0x180006a1a`
- name: `WdsImgCreateImageGroup`
- size: `314`
- prototype: `__int64 __usercall@<rax>(struct CImageStore *@<rcx>, unsigned __int16 *@<rdx>, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180001588`
- `0x1800062a0`
- `0x180006714`
- `0x1800068e0`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall WdsImgCreateImageGroup(struct CImageStore *a1, unsigned __int16 *a2, __int64 a3, int a4, _QWORD *a5)
{
  _DWORD *v7; // rdi
  __int64 Initialize; // rbx
  int v9; // r9d
  int v10; // r9d
  int v11; // r9d
  _DWORD *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // r8

  v7 = 0;
  if ( !a2 || !*a2 || !a5 || !a1 )
  {
    LODWORD(Initialize) = -2147024809;
    return (unsigned int)Initialize;
  }
  if ( *((_DWORD *)a1 + 4) == 1 )
  {
    v9 = a4 - 256;
    if ( !v9 || (v10 = v9 - 1) == 0 || (v11 = v10 - 1) == 0 || (LODWORD(Initialize) = -1056833008, v11 == 1) )
      LODWORD(Initialize) = 0;
    if ( (int)ElValidateHr_1((unsigned int)Initialize, a2, a3, 523) >= 0 )
    {
      v12 = operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
      v7 = v12;
      if ( !v12 )
      {
        LODWORD(Initialize) = -2147024882;
        return (unsigned int)Initialize;
      }
      v12[2] = 1;
      v12[4] = 2;
      *((_QWORD *)v12 + 4) = 0;
      *(_QWORD *)v12 = &CImageGroup::`vftable';
      *((_QWORD *)v12 + 3) = 0;
      *((_QWORD *)v12 + 5) = 0;
      Initialize = (unsigned int)CImageGroup::CreateInitialize((CImageGroup *)v12, a1, a2);
      if ( (int)ElValidateHr_1(Initialize, v13, v14, 532) >= 0 )
        *a5 = v7;
    }
    if ( (int)Initialize < 0 && v7 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v7 + 16LL))(v7, 1);
  }
  else
  {
    LODWORD(Initialize) = -1056833019;
  }
  return (unsigned int)Initialize;
}

```

## disassembly

```asm
0x1800068e0  mov     [rsp+arg_0], rbx
0x1800068e5  mov     [rsp+arg_8], rbp
0x1800068ea  mov     [rsp+arg_10], rsi
0x1800068ef  push    rdi
0x1800068f0  push    r14
0x1800068f2  push    r15
0x1800068f4  sub     rsp, 20h
0x1800068f8  xor     r15d, r15d
0x1800068fb  mov     rbp, rdx
0x1800068fe  mov     rsi, rcx
0x180006901  mov     edi, r15d
0x180006904  test    rdx, rdx
0x180006907  jz      loc_1800069F9
0x18000690d  cmp     [rdx], r15w
0x180006911  jz      loc_1800069F9
0x180006917  mov     r14, [rsp+38h+arg_20]
0x18000691c  test    r14, r14
0x18000691f  jz      loc_1800069F9
0x180006925  test    rcx, rcx
0x180006928  jz      loc_1800069F9
0x18000692e  cmp     dword ptr [rcx+10h], 1
0x180006932  jz      short loc_18000693E
0x180006934  mov     ebx, 0C1020205h
0x180006939  jmp     loc_1800069FE
0x18000693e  sub     r9d, 100h
0x180006945  jz      short loc_18000695E
0x180006947  sub     r9d, 1
0x18000694b  jz      short loc_18000695E
0x18000694d  sub     r9d, 1
0x180006951  jz      short loc_18000695E
0x180006953  mov     ebx, 0C1020210h
0x180006958  cmp     r9d, 1
0x18000695c  jnz     short loc_180006961
0x18000695e  mov     ebx, r15d
0x180006961  mov     r9d, 20Bh
0x180006967  mov     ecx, ebx
0x180006969  call    ElValidateHr_1
0x18000696e  test    eax, eax
0x180006970  js      short loc_1800069D3
0x180006972  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006979  mov     ecx, 30h ; '0'; unsigned __int64
0x18000697e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180006983  mov     rdi, rax
0x180006986  test    rax, rax
0x180006989  jz      short loc_1800069F2
0x18000698b  mov     dword ptr [rax+8], 1
0x180006992  mov     r8, rbp; unsigned __int16 *
0x180006995  mov     dword ptr [rax+10h], 2
0x18000699c  mov     rdx, rsi; struct CImageStore *
0x18000699f  lea     rax, ??_7CImageGroup@@6B@; const CImageGroup::`vftable'
0x1800069a6  mov     [rdi+20h], r15
0x1800069aa  mov     rcx, rdi; this
0x1800069ad  mov     [rdi], rax
0x1800069b0  mov     [rdi+18h], r15
0x1800069b4  mov     [rdi+28h], r15
0x1800069b8  call    ?CreateInitialize@CImageGroup@@QEAAJPEAVCImageStore@@PEBG@Z; CImageGroup::CreateInitialize(CImageStore *,ushort const *)
0x1800069bd  mov     r9d, 214h
0x1800069c3  mov     ecx, eax
0x1800069c5  mov     ebx, eax
0x1800069c7  call    ElValidateHr_1
0x1800069cc  test    eax, eax
0x1800069ce  js      short loc_1800069D3
0x1800069d0  mov     [r14], rdi
0x1800069d3  test    ebx, ebx
0x1800069d5  jns     short loc_1800069FE
0x1800069d7  test    rdi, rdi
0x1800069da  jz      short loc_1800069FE
0x1800069dc  mov     rax, [rdi]
0x1800069df  mov     edx, 1
0x1800069e4  mov     rcx, rdi
0x1800069e7  mov     rax, [rax+10h]
0x1800069eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069f0  jmp     short loc_1800069FE
0x1800069f2  mov     ebx, 8007000Eh
0x1800069f7  jmp     short loc_1800069FE
0x1800069f9  mov     ebx, 80070057h
0x1800069fe  mov     rbp, [rsp+38h+arg_8]
0x180006a03  mov     eax, ebx
0x180006a05  mov     rbx, [rsp+38h+arg_0]
0x180006a0a  mov     rsi, [rsp+38h+arg_10]
0x180006a0f  add     rsp, 20h
0x180006a13  pop     r15
0x180006a15  pop     r14
0x180006a17  pop     rdi
0x180006a18  retn
```
