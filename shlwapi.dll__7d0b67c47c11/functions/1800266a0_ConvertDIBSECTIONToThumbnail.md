# ConvertDIBSECTIONToThumbnail

- ea: `0x1800266a0`
- end: `0x1800268e5`
- name: `ConvertDIBSECTIONToThumbnail`
- size: `581`
- prototype: `__int64 __usercall@<rax>(BITMAPINFO *lpbmi@<rcx>, void *@<rdx>, int, HPALETTE, unsigned int, int)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180007710`
- `0x180009db8`
- `0x18000b430`
- `0x1800259ec`
- `0x180025a18`
- `0x180026078`
- `0x18002625c`
- `0x180026464`
- `0x1800266a0`
- `0x1800268f0`
- `0x180026bc0`
- `0x1800369d1`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026872`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026872`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800268cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800268cb`
- `GDI32!DeleteObject` at `0x180026869`
- `GDI32!DeleteObject` at `0x180026869`
- `USER32!GetSysColor` at `0x18002687f`
- `USER32!GetSysColor` at `0x18002687f`

## pseudocode

```c
_BOOL8 __fastcall ConvertDIBSECTIONToThumbnail(
        BITMAPINFO *lpbmi,
        void *a2,
        __int64 a3,
        int *a4,
        unsigned int a5,
        HPALETTE hPal,
        unsigned int a7,
        int a8)
{
  int biHeight; // edx
  BITMAPINFO *v11; // rbx
  int v12; // r13d
  LONG biWidth; // eax
  unsigned int v14; // r15d
  BOOL v15; // r14d
  CThumbnailMaker *v16; // rax
  CThumbnailMaker *v17; // rsi
  int v18; // r8d
  CThumbnailMaker *v19; // rcx
  LONG v20; // eax
  int v21; // r15d
  int SharpenedBITMAPINFO; // eax
  int v23; // r14d
  int v24; // esi
  unsigned int biBitCount; // edx
  HGDIOBJ *v26; // r15
  unsigned int v27; // eax
  HLOCAL v28; // rsi
  COLORREF color; // eax
  void *v31[2]; // [rsp+50h] [rbp-18h] BYREF
  unsigned int v32; // [rsp+B0h] [rbp+48h] BYREF
  LONG v33; // [rsp+B4h] [rbp+4Ch]
  HLOCAL hMem; // [rsp+B8h] [rbp+50h] BYREF
  __int64 v35; // [rsp+C0h] [rbp+58h]
  int *v36; // [rsp+C8h] [rbp+60h]

  v36 = a4;
  v35 = a3;
  hMem = lpbmi;
  biHeight = lpbmi->bmiHeader.biHeight;
  v11 = lpbmi;
  if ( biHeight >= 0 )
  {
    v12 = 0;
  }
  else
  {
    biHeight = -biHeight;
    v12 = 1;
    lpbmi->bmiHeader.biHeight = biHeight;
  }
  biWidth = lpbmi->bmiHeader.biWidth;
  v31[0] = 0;
  v31[1] = (void *)__PAIR64__(biHeight, biWidth);
  CalculateAspectRatio(a4, 1, v31);
  v14 = LODWORD(v31[1]) - LODWORD(v31[0]);
  if ( __PAIR64__(HIDWORD(v31[1]) - HIDWORD(v31[0]), LODWORD(v31[1]) - LODWORD(v31[0])) == *(_QWORD *)&lpbmi->bmiHeader.biWidth )
    goto LABEL_13;
  v15 = 0;
  v16 = (CThumbnailMaker *)operator new(0x20u);
  v17 = v16;
  if ( v16 )
  {
    v18 = HIDWORD(v31[1]);
    *((_QWORD *)v16 + 2) = 0;
    v19 = v16;
    *((_QWORD *)v16 + 3) = 0;
    v20 = -lpbmi->bmiHeader.biHeight;
    if ( lpbmi->bmiHeader.biHeight > 0 )
      v20 = lpbmi->bmiHeader.biHeight;
    v21 = CThumbnailMaker::Init(v19, v14, v18 - HIDWORD(v31[0]), lpbmi->bmiHeader.biWidth, v20);
    if ( v21 >= 0 )
    {
      v21 = CThumbnailMaker::AddDIBSECTION(v17, lpbmi, a2);
      if ( v21 >= 0 )
      {
        v32 = 0;
        SharpenedBITMAPINFO = CThumbnailMaker::GetSharpenedBITMAPINFO(v17, a7, (struct tagBITMAPINFO **)&hMem, &v32);
        v11 = (BITMAPINFO *)hMem;
        v21 = SharpenedBITMAPINFO;
        if ( SharpenedBITMAPINFO >= 0 )
          a2 = (char *)hMem + 40;
      }
    }
    CThumbnailMaker::~CThumbnailMaker(v17);
    operator delete(v17);
    if ( v21 >= 0 )
    {
LABEL_13:
      if ( v12 == 1 )
        v11->bmiHeader.biHeight = -v11->bmiHeader.biHeight;
      v23 = a8;
      v24 = a5;
      if ( a8 && (biBitCount = v11->bmiHeader.biBitCount, biBitCount <= a5) )
      {
        v26 = (HGDIOBJ *)v35;
        v32 = v11->bmiHeader.biWidth;
        v33 = v11->bmiHeader.biHeight;
        v31[0] = 0;
        hMem = 0;
        v15 = CreateSizedDIBSECTION((LONG *)&v32, biBitCount, 0, (__int64)v11, (HBITMAP *)v35, &hMem, (HPALETTE *)v31);
        if ( v15 )
        {
          v27 = CalcBitmapSize(v11);
          v28 = hMem;
          if ( hMem && *((_DWORD *)hMem + 5) >= v27 )
          {
            memcpy_0(v31[0], a2, v27);
          }
          else
          {
            v15 = 0;
            DeleteObject(*v26);
          }
          LocalFree(v28);
        }
      }
      else
      {
        color = GetSysColor(5);
        v15 = FactorAspectRatio(v11, (unsigned __int8 *)a2, v36, (int *)v31, v24, hPal, v23, color, (HGDIOBJ *)v35);
      }
      if ( v11 != lpbmi )
        CoTaskMemFree(v11);
    }
  }
  return v15;
}

```

## disassembly

```asm
0x1800266a0  mov     [rsp-40h+arg_18], r9
0x1800266a5  mov     [rsp-40h+arg_10], r8
0x1800266aa  push    rbp
0x1800266ab  push    rbx
0x1800266ac  push    rsi
0x1800266ad  push    rdi
0x1800266ae  push    r12
0x1800266b0  push    r13
0x1800266b2  push    r14
0x1800266b4  push    r15
0x1800266b6  mov     rbp, rsp
0x1800266b9  sub     rsp, 68h
0x1800266bd  mov     r12, rdx
0x1800266c0  mov     [rbp+hMem], rcx
0x1800266c4  mov     edx, [rcx+8]
0x1800266c7  mov     rdi, rcx
0x1800266ca  mov     rbx, rcx
0x1800266cd  mov     ecx, 1
0x1800266d2  test    edx, edx
0x1800266d4  jns     short loc_1800266E0
0x1800266d6  neg     edx
0x1800266d8  mov     r13d, ecx
0x1800266db  mov     [rbx+8], edx
0x1800266de  jmp     short loc_1800266E3
0x1800266e0  xor     r13d, r13d
0x1800266e3  mov     eax, [rdi+4]
0x1800266e6  lea     r8, [rbp+var_18]
0x1800266ea  mov     dword ptr [rbp+var_18+0Ch], edx
0x1800266ed  mov     edx, ecx
0x1800266ef  mov     rcx, r9
0x1800266f2  mov     [rbp+var_18], 0
0x1800266fa  mov     dword ptr [rbp+var_18+8], eax
0x1800266fd  call    CalculateAspectRatio
0x180026702  mov     r15d, dword ptr [rbp+var_18+8]
0x180026706  sub     r15d, dword ptr [rbp+var_18]
0x18002670a  cmp     r15d, [rdi+4]
0x18002670e  jnz     short loc_18002671F
0x180026710  mov     eax, dword ptr [rbp+var_18+0Ch]
0x180026713  sub     eax, dword ptr [rbp+var_18+4]
0x180026716  cmp     eax, [rdi+8]
0x180026719  jz      loc_1800267BE
0x18002671f  xor     r14d, r14d
0x180026722  lea     ecx, [r14+20h]; unsigned __int64
0x180026726  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002672b  mov     rsi, rax
0x18002672e  test    rax, rax
0x180026731  jz      loc_1800268D1
0x180026737  mov     r8d, dword ptr [rbp+var_18+0Ch]
0x18002673b  mov     edx, r15d; unsigned int
0x18002673e  mov     [rax+10h], r14
0x180026742  mov     rcx, rsi; this
0x180026745  mov     [rax+18h], r14
0x180026749  mov     eax, [rdi+8]
0x18002674c  mov     r9d, [rdi+4]; unsigned int
0x180026750  neg     eax
0x180026752  cmovs   eax, [rdi+8]
0x180026756  sub     r8d, dword ptr [rbp+var_18+4]; unsigned int
0x18002675a  mov     [rsp+68h+var_48], eax; unsigned int
0x18002675e  call    ?Init@CThumbnailMaker@@QEAAJIIII@Z; CThumbnailMaker::Init(uint,uint,uint,uint)
0x180026763  mov     r15d, eax
0x180026766  test    eax, eax
0x180026768  js      short loc_1800267A5
0x18002676a  mov     r8, r12; void *
0x18002676d  mov     rdx, rdi; struct tagBITMAPINFO *
0x180026770  mov     rcx, rsi; this
0x180026773  call    ?AddDIBSECTION@CThumbnailMaker@@QEAAJPEAUtagBITMAPINFO@@PEAX@Z; CThumbnailMaker::AddDIBSECTION(tagBITMAPINFO *,void *)
0x180026778  mov     r15d, eax
0x18002677b  test    eax, eax
0x18002677d  js      short loc_1800267A5
0x18002677f  mov     edx, [rbp+arg_30]; unsigned int
0x180026782  lea     r9, [rbp+arg_0]; unsigned int *
0x180026786  lea     r8, [rbp+hMem]; struct tagBITMAPINFO **
0x18002678a  mov     [rbp+arg_0], r14d
0x18002678e  mov     rcx, rsi; this
0x180026791  call    ?GetSharpenedBITMAPINFO@CThumbnailMaker@@QEAAJIPEAPEAUtagBITMAPINFO@@PEAK@Z; CThumbnailMaker::GetSharpenedBITMAPINFO(uint,tagBITMAPINFO * *,ulong *)
0x180026796  mov     rbx, [rbp+hMem]
0x18002679a  mov     r15d, eax
0x18002679d  test    eax, eax
0x18002679f  js      short loc_1800267A5
0x1800267a1  lea     r12, [rbx+28h]
0x1800267a5  mov     rcx, rsi; this
0x1800267a8  call    ??1CThumbnailMaker@@QEAA@XZ; CThumbnailMaker::~CThumbnailMaker(void)
0x1800267ad  mov     rcx, rsi; lpMem
0x1800267b0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800267b5  test    r15d, r15d
0x1800267b8  js      loc_1800268D1
0x1800267be  cmp     r13d, 1
0x1800267c2  jnz     short loc_1800267CC
0x1800267c4  mov     eax, [rbx+8]
0x1800267c7  neg     eax
0x1800267c9  mov     [rbx+8], eax
0x1800267cc  mov     r14d, [rbp+arg_38]
0x1800267d3  mov     esi, [rbp+arg_20]
0x1800267d6  test    r14d, r14d
0x1800267d9  jz      loc_18002687A
0x1800267df  movzx   edx, word ptr [rbx+0Eh]
0x1800267e3  cmp     edx, esi
0x1800267e5  ja      loc_18002687A
0x1800267eb  mov     eax, [rbx+4]
0x1800267ee  lea     rcx, [rbp+arg_0]
0x1800267f2  mov     r15, [rbp+arg_10]
0x1800267f6  mov     r9, rbx
0x1800267f9  mov     [rbp+arg_0], eax
0x1800267fc  xor     r8d, r8d
0x1800267ff  mov     eax, [rbx+8]
0x180026802  mov     [rbp+arg_4], eax
0x180026805  lea     rax, [rbp+var_18]
0x180026809  mov     qword ptr [rsp+68h+var_38], rax
0x18002680e  lea     rax, [rbp+hMem]
0x180026812  mov     [rsp+68h+hPal], rax
0x180026817  mov     qword ptr [rsp+68h+var_48], r15
0x18002681c  mov     [rbp+var_18], 0
0x180026824  mov     [rbp+hMem], 0
0x18002682c  call    CreateSizedDIBSECTION
0x180026831  mov     r14d, eax
0x180026834  test    eax, eax
0x180026836  jz      loc_1800268C3
0x18002683c  mov     rcx, rbx; struct tagBITMAPINFO *
0x18002683f  call    ?CalcBitmapSize@@YAKPEBUtagBITMAPINFO@@@Z; CalcBitmapSize(tagBITMAPINFO const *)
0x180026844  mov     rsi, [rbp+hMem]
0x180026848  test    rsi, rsi
0x18002684b  jz      short loc_180026863
0x18002684d  cmp     [rsi+14h], eax
0x180026850  jb      short loc_180026863
0x180026852  mov     rcx, [rbp+var_18]; void *
0x180026856  mov     rdx, r12; Src
0x180026859  mov     r8d, eax; Size
0x18002685c  call    memcpy_0
0x180026861  jmp     short loc_18002686F
0x180026863  mov     rcx, [r15]; ho
0x180026866  xor     r14d, r14d
0x180026869  call    cs:__imp_DeleteObject
0x18002686f  mov     rcx, rsi; hMem
0x180026872  call    cs:__imp_LocalFree
0x180026878  jmp     short loc_1800268C3
0x18002687a  mov     ecx, 5; nIndex
0x18002687f  call    cs:__imp_GetSysColor
0x180026885  movaps  xmm0, xmmword ptr [rbp+var_18]
0x180026889  lea     r9, [rbp+var_18]
0x18002688d  mov     r15, [rbp+arg_10]
0x180026891  mov     rdx, r12
0x180026894  mov     r8, [rbp+arg_18]
0x180026898  mov     rcx, rbx; lpbmi
0x18002689b  mov     [rsp+68h+var_28], r15; __int64
0x1800268a0  mov     [rsp+68h+color], eax; color
0x1800268a4  mov     rax, [rbp+arg_28]
0x1800268a8  mov     [rsp+68h+var_38], r14d; int
0x1800268ad  mov     [rsp+68h+hPal], rax; hPal
0x1800268b2  mov     [rsp+68h+var_48], esi; int
0x1800268b6  movdqa  xmmword ptr [rbp+var_18], xmm0
0x1800268bb  call    FactorAspectRatio
0x1800268c0  mov     r14d, eax
0x1800268c3  cmp     rbx, rdi
0x1800268c6  jz      short loc_1800268D1
0x1800268c8  mov     rcx, rbx; pv
0x1800268cb  call    cs:__imp_CoTaskMemFree
0x1800268d1  mov     eax, r14d
0x1800268d4  add     rsp, 68h
0x1800268d8  pop     r15
0x1800268da  pop     r14
0x1800268dc  pop     r13
0x1800268de  pop     r12
0x1800268e0  pop     rdi
0x1800268e1  pop     rsi
0x1800268e2  pop     rbx
0x1800268e3  pop     rbp
0x1800268e4  retn
```
