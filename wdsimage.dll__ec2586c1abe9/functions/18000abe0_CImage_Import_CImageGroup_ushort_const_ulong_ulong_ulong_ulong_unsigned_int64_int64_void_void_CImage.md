# CImage::Import(CImageGroup *,ushort const *,ulong,ulong,ulong (*)(ulong,unsigned __int64,__int64,void *),void *,CImage * *)

- ea: `0x18000abe0`
- end: `0x18000ae5d`
- name: `?Import@CImage@@QEAAJPEAVCImageGroup@@PEBGKKP6AKK_K_JPEAX@Z4PEAPEAV1@@Z`
- size: `637`
- prototype: `__int64 __usercall@<rax>(CImage *__hidden this@<rcx>, struct CImageGroup *@<rdx>, const unsigned __int16 *@<r8>, unsigned int@<r9d>, unsigned int, unsigned int (*)(unsigned int, unsigned __int64, __int64, void *), void *, struct CImage **)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180005680`
- `0x180005ad0`

## callees

- `0x180001588`
- `0x1800039a8`
- `0x18000abe0`
- `0x18000ae64`
- `0x18000c77c`
- `0x18000d0e8`
- `0x18000d5b0`
- `0x18000d6b0`
- `0x180011010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000ae18`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000ae18`
- `KERNEL32!GetFileAttributesW` at `0x18000acad`
- `KERNEL32!GetFileAttributesW` at `0x18000acad`
- `WdsCommonLib!ConcatenatePaths` at `0x18000ac74`
- `WdsCommonLib!ConcatenatePaths` at `0x18000ac74`

## pseudocode

```c
__int64 __fastcall CImage::Import(
        CImage *this,
        struct CImageGroup *a2,
        const unsigned __int16 *a3,
        int a4,
        unsigned int a5,
        unsigned int (*a6)(unsigned int, unsigned __int64, __int64, void *),
        void *a7,
        struct CImage **a8)
{
  bool v8; // zf
  CImage *v13; // rdi
  __int64 v14; // rbx
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rdx
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  __int64 v21; // r9
  __int64 v22; // rcx
  struct CImage **v23; // r15
  CImage *v24; // rax
  CImage *v25; // rax
  struct CImage *v26; // rsi
  __int128 v27; // xmm0
  __int64 v28; // rdx
  unsigned int v29; // eax
  __int128 v31; // [rsp+20h] [rbp-50h] BYREF
  const unsigned __int16 *v32; // [rsp+30h] [rbp-40h]
  __int64 v33; // [rsp+38h] [rbp-38h]
  int v34; // [rsp+40h] [rbp-30h]
  unsigned int (*v35)(unsigned int, unsigned __int64, __int64, void *); // [rsp+48h] [rbp-28h]
  void *v36; // [rsp+50h] [rbp-20h]
  __int64 v37; // [rsp+58h] [rbp-18h]
  __int64 v38; // [rsp+60h] [rbp-10h]
  LPCWSTR lpFileName; // [rsp+A0h] [rbp+30h] BYREF

  v8 = *((_DWORD *)this + 7) == 2;
  lpFileName = 0;
  v31 = 0;
  v32 = 0;
  v13 = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  if ( !v8 && a5 != 256 )
  {
    LODWORD(v14) = -2147024809;
    if ( (int)ElValidateHr_5(2147942487LL, a2, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 2196) < 0 )
      goto LABEL_25;
  }
  v14 = (unsigned int)ConcatenatePaths(*((_QWORD *)a2 + 4), a3, &lpFileName);
  if ( (unsigned int)ElValidateWin32_4(v14, v15, v16, 2206) )
  {
    if ( (int)v14 > 0 )
      LODWORD(v14) = (unsigned __int16)v14 | 0x80070000;
    goto LABEL_25;
  }
  if ( GetFileAttributesW(lpFileName) != -1 )
  {
    LODWORD(v14) = -1056833014;
    if ( (int)ElValidateHr_5(3238134282LL, v17, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 2214) < 0 )
      goto LABEL_25;
  }
  v18 = *((_DWORD *)this + 7);
  v35 = a6;
  v36 = a7;
  *((_QWORD *)&v31 + 1) = *((_QWORD *)a2 + 4);
  v32 = a3;
  LODWORD(v33) = a4;
  v19 = v18 - 1;
  if ( !v19 )
    goto LABEL_22;
  v20 = v19 - 1;
  if ( !v20 )
  {
    v29 = CImage::WimImport(this, (struct WdsImgCopyParams *)&v31, a5);
    v21 = 2233;
LABEL_23:
    LODWORD(v14) = v29;
    v22 = v29;
    goto LABEL_13;
  }
  if ( v20 == 1 )
  {
LABEL_22:
    v29 = CImage::VhdImport(this, (struct WdsImgCopyParams *)&v31);
    v21 = 2239;
    goto LABEL_23;
  }
  LODWORD(v14) = -2147024883;
  v21 = 2245;
  v22 = 2147942413LL;
LABEL_13:
  if ( (int)ElValidateHr_5(v22, v17, "base\\eco\\wds\\wdsimage\\src\\image.cpp", v21) >= 0 )
  {
    v23 = a8;
    if ( a8 )
    {
      v24 = (CImage *)operator new(0x190u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v24 && (v25 = CImage::CImage(v24), v26 = v25, (v13 = v25) != 0) )
      {
        if ( *((_DWORD *)this + 17) )
        {
          v27 = *(_OWORD *)((char *)this + 72);
          *((_DWORD *)v25 + 17) = 1;
          *(_OWORD *)((char *)v25 + 72) = v27;
          *((_DWORD *)this + 17) = 0;
          *(_OWORD *)((char *)this + 72) = 0;
        }
        v14 = (unsigned int)CImage::Initialize(v25, lpFileName, 1, 296);
        if ( (int)ElValidateHr_5(v14, v28, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 2278) >= 0 )
        {
          *v23 = v26;
          v13 = 0;
        }
      }
      else
      {
        LODWORD(v14) = -2147024882;
      }
    }
  }
LABEL_25:
  if ( lpFileName )
  {
    operator delete((void *)lpFileName);
    lpFileName = 0;
  }
  if ( v13 )
    (*(void (__fastcall **)(CImage *))(*(_QWORD *)v13 + 8LL))(v13);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18000abe0  mov     [rsp-28h+arg_8], rbx
0x18000abe5  mov     [rsp-28h+arg_10], rsi
0x18000abea  mov     [rsp-28h+arg_18], rdi
0x18000abef  push    rbp
0x18000abf0  push    r12
0x18000abf2  push    r13
0x18000abf4  push    r14
0x18000abf6  push    r15
0x18000abf8  mov     rbp, rsp
0x18000abfb  sub     rsp, 70h
0x18000abff  xor     r13d, r13d
0x18000ac02  xorps   xmm0, xmm0
0x18000ac05  cmp     dword ptr [rcx+1Ch], 2
0x18000ac09  mov     r12d, r9d
0x18000ac0c  mov     rsi, r8
0x18000ac0f  mov     [rbp+lpFileName], r13
0x18000ac13  mov     r15, rdx
0x18000ac16  movdqa  [rbp+var_50], xmm0
0x18000ac1b  mov     r14, rcx
0x18000ac1e  mov     [rbp+var_40], r13
0x18000ac22  mov     edi, r13d
0x18000ac25  mov     [rbp+var_38], r13
0x18000ac29  mov     [rbp+var_30], r13d
0x18000ac2d  mov     [rbp+var_28], r13
0x18000ac31  mov     [rbp+var_20], r13
0x18000ac35  mov     [rbp+var_18], r13
0x18000ac39  mov     [rbp+var_10], r13
0x18000ac3d  jz      short loc_18000AC69
0x18000ac3f  cmp     [rbp+arg_20], 100h
0x18000ac46  jz      short loc_18000AC69
0x18000ac48  mov     ebx, 80070057h
0x18000ac4d  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x18000ac54  mov     ecx, ebx
0x18000ac56  mov     r9d, 894h
0x18000ac5c  call    ElValidateHr_5
0x18000ac61  test    eax, eax
0x18000ac63  js      loc_18000AE0F
0x18000ac69  mov     rcx, [r15+20h]
0x18000ac6d  lea     r8, [rbp+lpFileName]
0x18000ac71  mov     rdx, rsi
0x18000ac74  call    cs:__imp_ConcatenatePaths
0x18000ac7b  nop     dword ptr [rax+rax+00h]
0x18000ac80  mov     ecx, eax
0x18000ac82  mov     r9d, 89Eh
0x18000ac88  mov     ebx, eax
0x18000ac8a  call    ElValidateWin32_4
0x18000ac8f  test    eax, eax
0x18000ac91  jz      short loc_18000ACA9
0x18000ac93  test    ebx, ebx
0x18000ac95  jle     loc_18000AE0F
0x18000ac9b  movzx   ebx, bx
0x18000ac9e  or      ebx, 80070000h
0x18000aca4  jmp     loc_18000AE0F
0x18000aca9  mov     rcx, [rbp+lpFileName]; lpFileName
0x18000acad  call    cs:__imp_GetFileAttributesW
0x18000acb4  nop     dword ptr [rax+rax+00h]
0x18000acb9  cmp     eax, 0FFFFFFFFh
0x18000acbc  jz      short loc_18000ACDF
0x18000acbe  mov     ebx, 0C102020Ah
0x18000acc3  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x18000acca  mov     ecx, ebx
0x18000accc  mov     r9d, 8A6h
0x18000acd2  call    ElValidateHr_5
0x18000acd7  test    eax, eax
0x18000acd9  js      loc_18000AE0F
0x18000acdf  mov     rax, [rbp+arg_28]
0x18000ace3  mov     ecx, [r14+1Ch]
0x18000ace7  mov     [rbp+var_28], rax
0x18000aceb  mov     rax, [rbp+arg_30]
0x18000acef  mov     [rbp+var_20], rax
0x18000acf3  mov     rax, [r15+20h]
0x18000acf7  mov     qword ptr [rbp+var_50+8], rax
0x18000acfb  mov     [rbp+var_40], rsi
0x18000acff  mov     dword ptr [rbp+var_38], r12d
0x18000ad03  sub     ecx, 1
0x18000ad06  jz      loc_18000ADEF
0x18000ad0c  sub     ecx, 1
0x18000ad0f  jz      loc_18000ADD7
0x18000ad15  cmp     ecx, 1
0x18000ad18  jz      loc_18000ADEF
0x18000ad1e  mov     ebx, 8007000Dh
0x18000ad23  mov     r9d, 8C5h
0x18000ad29  mov     ecx, ebx
0x18000ad2b  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x18000ad32  call    ElValidateHr_5
0x18000ad37  test    eax, eax
0x18000ad39  js      loc_18000AE0F
0x18000ad3f  mov     r15, [rbp+arg_38]
0x18000ad43  test    r15, r15
0x18000ad46  jz      loc_18000AE0F
0x18000ad4c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ad53  mov     ecx, 190h; unsigned __int64
0x18000ad58  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000ad5d  test    rax, rax
0x18000ad60  jz      loc_18000AE0A
0x18000ad66  mov     rcx, rax; this
0x18000ad69  call    ??0CImage@@QEAA@XZ; CImage::CImage(void)
0x18000ad6e  mov     rsi, rax
0x18000ad71  mov     rdi, rax
0x18000ad74  test    rax, rax
0x18000ad77  jz      loc_18000AE0A
0x18000ad7d  mov     r8d, 1; unsigned int
0x18000ad83  cmp     [r14+44h], r13d
0x18000ad87  jz      short loc_18000ADA3
0x18000ad89  movups  xmm0, xmmword ptr [r14+48h]
0x18000ad8e  mov     [rax+44h], r8d
0x18000ad92  movdqu  xmmword ptr [rax+48h], xmm0
0x18000ad97  mov     [r14+44h], r13d
0x18000ad9b  xorps   xmm0, xmm0
0x18000ad9e  movups  xmmword ptr [r14+48h], xmm0
0x18000ada3  mov     rdx, [rbp+lpFileName]; unsigned __int16 *
0x18000ada7  mov     r9d, 128h; unsigned int
0x18000adad  mov     rcx, rsi; this
0x18000adb0  call    ?Initialize@CImage@@QEAAJPEBGKK@Z; CImage::Initialize(ushort const *,ulong,ulong)
0x18000adb5  mov     r9d, 8E6h
0x18000adbb  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x18000adc2  mov     ecx, eax
0x18000adc4  mov     ebx, eax
0x18000adc6  call    ElValidateHr_5
0x18000adcb  test    eax, eax
0x18000adcd  js      short loc_18000AE0F
0x18000adcf  mov     [r15], rsi
0x18000add2  mov     rdi, r13
0x18000add5  jmp     short loc_18000AE0F
0x18000add7  mov     r8d, [rbp+arg_20]; unsigned int
0x18000addb  lea     rdx, [rbp+var_50]; struct WdsImgCopyParams *
0x18000addf  mov     rcx, r14; this
0x18000ade2  call    ?WimImport@CImage@@AEAAJPEAUWdsImgCopyParams@@K@Z; CImage::WimImport(WdsImgCopyParams *,ulong)
0x18000ade7  mov     r9d, 8B9h
0x18000aded  jmp     short loc_18000AE01
0x18000adef  lea     rdx, [rbp+var_50]; struct WdsImgCopyParams *
0x18000adf3  mov     rcx, r14; this
0x18000adf6  call    ?VhdImport@CImage@@AEAAJPEAUWdsImgCopyParams@@@Z; CImage::VhdImport(WdsImgCopyParams *)
0x18000adfb  mov     r9d, 8BFh
0x18000ae01  mov     ebx, eax
0x18000ae03  mov     ecx, eax
0x18000ae05  jmp     loc_18000AD2B
0x18000ae0a  mov     ebx, 8007000Eh
0x18000ae0f  mov     rcx, [rbp+lpFileName]
0x18000ae13  test    rcx, rcx
0x18000ae16  jz      short loc_18000AE28
0x18000ae18  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000ae1f  nop     dword ptr [rax+rax+00h]
0x18000ae24  mov     [rbp+lpFileName], r13
0x18000ae28  test    rdi, rdi
0x18000ae2b  jz      short loc_18000AE3C
0x18000ae2d  mov     rax, [rdi]
0x18000ae30  mov     rcx, rdi
0x18000ae33  mov     rax, [rax+8]
0x18000ae37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae3c  lea     r11, [rsp+70h+var_s0]
0x18000ae41  mov     eax, ebx
0x18000ae43  mov     rbx, [r11+38h]
0x18000ae47  mov     rsi, [r11+40h]
0x18000ae4b  mov     rdi, [r11+48h]
0x18000ae4f  mov     rsp, r11
0x18000ae52  pop     r15
0x18000ae54  pop     r14
0x18000ae56  pop     r13
0x18000ae58  pop     r12
0x18000ae5a  pop     rbp
0x18000ae5b  retn
```
