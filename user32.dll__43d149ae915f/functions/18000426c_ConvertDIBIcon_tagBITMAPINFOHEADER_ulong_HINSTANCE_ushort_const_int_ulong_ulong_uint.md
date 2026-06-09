# ConvertDIBIcon(tagBITMAPINFOHEADER *,ulong,HINSTANCE__ *,ushort const *,int,ulong,ulong,uint)

- ea: `0x18000426c`
- end: `0x1800048ac`
- name: `?ConvertDIBIcon@@YAPEAUHICON__@@PEAUtagBITMAPINFOHEADER@@KPEAUHINSTANCE__@@PEBGHKKI@Z`
- size: `1600`
- prototype: `HICON __usercall@<rax>(struct tagBITMAPINFOHEADER *@<rcx>, unsigned int@<edx>, HINSTANCE@<r8>, const unsigned __int16 *@<r9>, int, unsigned int nWidth, unsigned int, unsigned int)`
- caller_count: `4`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800013dc`
- `0x180002264`
- `0x1800038b0`
- `0x1800081d4`

## callees

- `0x180003c60`
- `0x180003cbc`
- `0x180003d9c`
- `0x180003f60`
- `0x18000426c`
- `0x180004cd0`
- `0x180005280`
- `0x18001a2b8`
- `0x180096dc5`
- `0x180096e00`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800043f3`
- `ntdll!RtlFreeHeap` at `0x180004445`
- `ntdll!RtlFreeHeap` at `0x1800046e3`
- `ntdll!RtlFreeHeap` at `0x1800047dd`
- `ntdll!RtlFreeHeap` at `0x1800043f3`
- `ntdll!RtlFreeHeap` at `0x180004445`
- `ntdll!RtlFreeHeap` at `0x1800046e3`
- `ntdll!RtlFreeHeap` at `0x1800047dd`
- `ntdll!RtlAllocateHeap` at `0x18000439b`
- `ntdll!RtlAllocateHeap` at `0x18000439b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800047a0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800047a0`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000448b`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800044db`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180004742`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800047ff`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000448b`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800044db`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180004742`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800047ff`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x180004477`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x180004477`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180004455`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180004455`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800044c8`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180004734`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800047f1`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800044c8`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180004734`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800047f1`
- `GDI32!CreateBitmap` at `0x1800046ad`
- `GDI32!CreateBitmap` at `0x1800046ad`
- `GDI32!DeleteObject` at `0x1800047cb`
- `GDI32!DeleteObject` at `0x1800047cb`

## pseudocode

```c
HICON __fastcall ConvertDIBIcon(
        struct tagBITMAPINFOHEADER *a1,
        unsigned int a2,
        HINSTANCE a3,
        const unsigned __int16 *a4,
        int a5,
        unsigned int nWidth,
        unsigned int a7,
        unsigned int a8)
{
  unsigned int v8; // r15d
  LONG v10; // r13d
  unsigned int v11; // r14d
  HICON result; // rax
  HICON v13; // rdi
  void *v14; // rax
  void *v15; // rdi
  char *v16; // rax
  HBITMAP v17; // rax
  HMODULE v18; // rsi
  BITMAPINFO *lpbmi; // rsi
  int v20; // r15d
  int v21; // eax
  WCHAR *v22; // rax
  unsigned int v23; // [rsp+6Ch] [rbp-34Ch] BYREF
  unsigned int v24; // [rsp+70h] [rbp-348h]
  unsigned int v25; // [rsp+78h] [rbp-340h]
  char *v26; // [rsp+80h] [rbp-338h]
  HGLOBAL hMem; // [rsp+88h] [rbp-330h]
  unsigned int v28; // [rsp+90h] [rbp-328h]
  PVOID P; // [rsp+98h] [rbp-320h] BYREF
  struct tagBITMAPINFOHEADER *v30; // [rsp+A0h] [rbp-318h]
  char *v31; // [rsp+A8h] [rbp-310h] BYREF
  HMODULE hModule; // [rsp+B0h] [rbp-308h]
  const unsigned __int16 *v33; // [rsp+B8h] [rbp-300h]
  const unsigned __int16 *v34; // [rsp+D0h] [rbp-2E8h] BYREF
  WCHAR *v35; // [rsp+D8h] [rbp-2E0h]
  __int16 v36; // [rsp+E0h] [rbp-2D8h]
  int v37; // [rsp+E8h] [rbp-2D0h]
  __int16 biSize; // [rsp+ECh] [rbp-2CCh]
  __int16 biSize_high; // [rsp+EEh] [rbp-2CAh]
  void *Bitmap; // [rsp+F0h] [rbp-2C8h]
  HGDIOBJ ho; // [rsp+F8h] [rbp-2C0h]
  int v42; // [rsp+120h] [rbp-298h]
  LONG v43; // [rsp+124h] [rbp-294h]
  int v44; // [rsp+128h] [rbp-290h]
  WCHAR Filename[264]; // [rsp+160h] [rbp-258h] BYREF

  v33 = a4;
  hModule = a3;
  v8 = a2;
  v10 = nWidth;
  v24 = nWidth;
  v25 = a7;
  v11 = a8;
  P = 0;
  v23 = 0;
  if ( a2 < 0x28 )
    return 0;
  v26 = 0;
  hMem = 0;
  if ( (a8 & 0x2000) != 0 )
    v11 = a8 & 0xFFFFD7FF | 0x800;
  memset_0(&v34, 0, 0x88u);
  if ( !a5 )
  {
    biSize = a1->biSize;
    v30 = (struct tagBITMAPINFOHEADER *)((char *)&a1->biSize + 2);
    biSize_high = HIWORD(a1->biSize);
    a1 = (struct tagBITMAPINFOHEADER *)((char *)a1 + 4);
    v30 = a1;
    v8 -= 4;
    v28 = v8;
    if ( v8 < 0x28 )
      return 0;
  }
  if ( a1->biSize != 1196314761 || a1->biWidth != 169478669 )
  {
    result = (HICON)RtlAllocateHeap(pUserHeap, 0, 0x28u);
    v13 = result;
    if ( !result )
      return result;
    *(_OWORD *)result = *(_OWORD *)&a1->biSize;
    *((_OWORD *)result + 1) = *(_OWORD *)&a1->biCompression;
    *((_QWORD *)result + 4) = *(_QWORD *)&a1->biClrUsed;
    if ( *(_DWORD *)result == 12 )
      *((_WORD *)result + 3) >>= 1;
    else
      *((int *)result + 2) /= 2;
    if ( !(unsigned int)CheckImageSize((struct tagBITMAPINFOHEADER *)result, v8) )
    {
      RtlFreeHeap(pUserHeap, 0, v13);
      return 0;
    }
    RtlFreeHeap(pUserHeap, 0, v13);
  }
  v14 = ConvertPNGToDIBIcon((unsigned __int8 *)a1, v8);
  v15 = v14;
  hMem = v14;
  if ( v14 )
  {
    v16 = (char *)GlobalLock(v14);
    v26 = v16;
    if ( v16 )
    {
      a1 = (struct tagBITMAPINFOHEADER *)(v16 + 14);
      v30 = (struct tagBITMAPINFOHEADER *)(v16 + 14);
      v8 = GlobalSize(v15) - 14;
      v28 = v8;
    }
    else
    {
      GlobalFree(v15);
      v15 = 0;
      hMem = 0;
    }
  }
  if ( a1->biPlanes == 1 && a1->biBitCount == 32 )
    v11 |= 0x800u;
  v31 = 0;
  v17 = ConvertDIBBitmap(a1, v8, nWidth, a7, v11, 0, (struct tagBITMAPINFOHEADER **)&P, &v31, &v23);
  ho = v17;
  if ( !v17 )
  {
LABEL_59:
    if ( v26 )
      GlobalUnlock(v15);
    if ( v15 )
      GlobalFree(v15);
    return 0;
  }
  v18 = hModule;
  if ( hModule )
  {
    v37 = 1;
    if ( hModule == hmodUser )
    {
      v22 = (WCHAR *)&szUSER32;
    }
    else
    {
      if ( !GetModuleFileNameW(hModule, Filename, 0x104u) )
        StringCchPrintfW(Filename, 0x104u, &qword_1800A8D38, v18);
      v22 = Filename;
    }
    v35 = v22;
  }
  else
  {
    v35 = 0;
  }
  if ( a5 )
    v36 = 3;
  else
    v36 = 1;
  v34 = v33;
  lpbmi = (BITMAPINFO *)P;
  v42 = *((unsigned __int16 *)P + 6) * *((unsigned __int16 *)P + 7);
  if ( !nWidth )
  {
    v10 = *((_DWORD *)P + 1);
    v24 = v10;
  }
  v20 = a7;
  if ( !a7 )
  {
    v20 = *((_DWORD *)P + 2) / 2;
    v25 = v20;
  }
  if ( a5 )
  {
    biSize = v10 / 2;
    v21 = v20 / 2;
  }
  else
  {
    biSize = (v10 * biSize + *((_DWORD *)P + 1) / 2) / *((_DWORD *)P + 1);
    v21 = (v20 * biSize_high + *((_DWORD *)P + 2) / 2 / 2) / (*((_DWORD *)P + 2) / 2);
  }
  biSize_high = v21;
  ChangeDibColors((struct tagBITMAPINFOHEADER *)P, 1u);
  if ( v31 )
  {
    Bitmap = BitmapFromDIB(
               v10,
               2 * v20,
               1,
               1,
               0,
               lpbmi->bmiHeader.biWidth,
               lpbmi->bmiHeader.biHeight,
               v31,
               v23,
               lpbmi,
               0);
    if ( Bitmap )
      goto LABEL_40;
    Bitmap = CreateBitmap(v10, 2 * v20, 1u, 1u, 0);
    if ( Bitmap )
      goto LABEL_40;
    DeleteObject(ho);
    RtlFreeHeap(pUserHeap, 0, lpbmi);
    goto LABEL_59;
  }
  Bitmap = ho;
  ho = 0;
LABEL_40:
  v43 = v10;
  v44 = 2 * v20;
  RtlFreeHeap(pUserHeap, 0, lpbmi);
  if ( (v11 & 0x8000) != 0 )
    v37 |= 4u;
  if ( (v11 & 0x100) != 0 )
    v37 |= 2u;
  if ( (v11 & 0x400) != 0 )
    v37 |= 0x40u;
  if ( (v11 & 0x40000) != 0 )
    v37 |= 0x1000u;
  if ( v26 )
    GlobalUnlock(v15);
  if ( v15 )
    GlobalFree(v15);
  return CreateIcoCur((struct tagCURSORDATA *)&v34);
}

```

## disassembly

```asm
0x18000426c  push    rsi
0x18000426e  push    rdi
0x18000426f  push    r12
0x180004271  push    r13
0x180004273  push    r14
0x180004275  push    r15
0x180004277  sub     rsp, 388h
0x18000427e  mov     rax, cs:__security_cookie
0x180004285  xor     rax, rsp
0x180004288  mov     [rsp+3B8h+var_48], rax
0x180004290  mov     [rsp+3B8h+var_300], r9
0x180004298  mov     [rsp+3B8h+hModule], r8
0x1800042a0  mov     r15d, edx
0x1800042a3  mov     rsi, rcx
0x1800042a6  mov     r13d, [rsp+3B8h+nWidth]
0x1800042ae  mov     [rsp+3B8h+var_348], r13d
0x1800042b3  mov     eax, [rsp+3B8h+arg_30]
0x1800042ba  mov     [rsp+3B8h+var_350], eax
0x1800042be  mov     [rsp+3B8h+var_340], eax
0x1800042c2  mov     r14d, [rsp+3B8h+arg_38]
0x1800042ca  mov     [rsp+3B8h+var_358], r14d
0x1800042cf  mov     [rsp+3B8h+P], 0
0x1800042db  mov     [rsp+3B8h+var_34C], 0
0x1800042e3  cmp     edx, 28h ; '('
0x1800042e6  jb      loc_180004805
0x1800042ec  mov     [rsp+3B8h+var_338], 0
0x1800042f8  mov     [rsp+3B8h+hMem], 0
0x180004304  bt      r14d, 0Dh
0x180004309  jnb     short loc_18000431A
0x18000430b  btr     r14d, 0Dh
0x180004310  bts     r14d, 0Bh
0x180004315  mov     [rsp+3B8h+var_358], r14d
0x18000431a  xor     edx, edx; Val
0x18000431c  mov     r8d, 88h; Size
0x180004322  lea     rcx, [rsp+3B8h+var_2E8]; void *
0x18000432a  call    memset_0
0x18000432f  nop
0x180004330  mov     r12d, 2
0x180004336  cmp     [rsp+3B8h+arg_20], 0
0x18000433e  jnz     short loc_180004382
0x180004340  movzx   eax, word ptr [rsi]
0x180004343  mov     [rsp+3B8h+var_2CC], ax
0x18000434b  add     rsi, r12
0x18000434e  mov     [rsp+3B8h+var_318], rsi
0x180004356  movzx   eax, word ptr [rsi]
0x180004359  mov     [rsp+3B8h+var_2CA], ax
0x180004361  add     rsi, r12
0x180004364  mov     [rsp+3B8h+var_318], rsi
0x18000436c  add     r15d, 0FFFFFFFCh
0x180004370  mov     [rsp+3B8h+var_328], r15d
0x180004378  cmp     r15d, 28h ; '('
0x18000437c  jb      loc_1800044A9
0x180004382  cmp     dword ptr [rsi], 474E5089h
0x180004388  jz      loc_180004437
0x18000438e  xor     edx, edx; Flags
0x180004390  lea     r8d, [rdx+28h]; Size
0x180004394  mov     rcx, cs:pUserHeap; HeapHandle
0x18000439b  call    cs:__imp_RtlAllocateHeap
0x1800043a1  mov     rdi, rax
0x1800043a4  test    rax, rax
0x1800043a7  jz      loc_1800044B0
0x1800043ad  movups  xmm0, xmmword ptr [rsi]
0x1800043b0  movups  xmmword ptr [rax], xmm0
0x1800043b3  movups  xmm1, xmmword ptr [rsi+10h]
0x1800043b7  movups  xmmword ptr [rax+10h], xmm1
0x1800043bb  movsd   xmm0, qword ptr [rsi+20h]
0x1800043c0  movsd   qword ptr [rax+20h], xmm0
0x1800043c5  cmp     dword ptr [rax], 0Ch
0x1800043c8  jz      loc_1800044A0
0x1800043ce  mov     eax, [rax+8]
0x1800043d1  cdq
0x1800043d2  idiv    r12d
0x1800043d5  mov     [rdi+8], eax
0x1800043d8  mov     edx, r15d; unsigned int
0x1800043db  mov     rcx, rdi; struct tagBITMAPINFOHEADER *
0x1800043de  call    ?CheckImageSize@@YAHPEFAUtagBITMAPINFOHEADER@@K@Z; CheckImageSize(tagBITMAPINFOHEADER *,ulong)
0x1800043e3  mov     r8, rdi; P
0x1800043e6  xor     edx, edx; Flags
0x1800043e8  mov     rcx, cs:pUserHeap; HeapHandle
0x1800043ef  test    eax, eax
0x1800043f1  jz      short loc_180004445
0x1800043f3  call    cs:__imp_RtlFreeHeap
0x1800043f9  mov     edx, r15d; unsigned int
0x1800043fc  mov     rcx, rsi; unsigned __int8 *
0x1800043ff  call    ?ConvertPNGToDIBIcon@@YAPEAXPEAEK@Z; ConvertPNGToDIBIcon(uchar *,ulong)
0x180004404  mov     rdi, rax
0x180004407  mov     [rsp+3B8h+hMem], rax
0x18000440f  test    rax, rax
0x180004412  jnz     short loc_180004452
0x180004414  mov     r12d, 1
0x18000441a  cmp     [rsi+0Ch], r12w
0x18000441f  jnz     short loc_180004432
0x180004421  cmp     word ptr [rsi+0Eh], 20h ; ' '
0x180004426  jnz     short loc_180004432
0x180004428  bts     r14d, 0Bh
0x18000442d  mov     [rsp+3B8h+var_358], r14d
0x180004432  jmp     loc_1800044E8
0x180004437  cmp     dword ptr [rsi+4], 0A1A0A0Dh
0x18000443e  jz      short loc_1800043F9
0x180004440  jmp     loc_18000438E
0x180004445  call    cs:__imp_RtlFreeHeap
0x18000444b  xor     eax, eax
0x18000444d  jmp     loc_180004755
0x180004452  mov     rcx, rdi; hMem
0x180004455  call    cs:__imp_GlobalLock
0x18000445b  mov     [rsp+3B8h+var_338], rax
0x180004463  mov     rcx, rdi; hMem
0x180004466  test    rax, rax
0x180004469  jz      short loc_18000448B
0x18000446b  lea     rsi, [rax+0Eh]
0x18000446f  mov     [rsp+3B8h+var_318], rsi
0x180004477  call    cs:__imp_GlobalSize
0x18000447d  lea     r15d, [rax-0Eh]
0x180004481  mov     [rsp+3B8h+var_328], r15d
0x180004489  jmp     short loc_180004414
0x18000448b  call    cs:__imp_GlobalFree
0x180004491  xor     edi, edi
0x180004493  mov     [rsp+3B8h+hMem], rdi
0x18000449b  jmp     loc_180004414
0x1800044a0  shr     word ptr [rax+6], 1
0x1800044a4  jmp     loc_1800043D8
0x1800044a9  xor     eax, eax
0x1800044ab  jmp     loc_180004755
0x1800044b0  jmp     loc_180004755
0x1800044b5  cmp     [rsp+3B8h+var_338], 0
0x1800044be  jz      short loc_1800044CE
0x1800044c0  mov     rcx, [rsp+3B8h+hMem]; hMem
0x1800044c8  call    cs:__imp_GlobalUnlock
0x1800044ce  mov     rcx, [rsp+3B8h+hMem]; hMem
0x1800044d6  test    rcx, rcx
0x1800044d9  jz      short loc_1800044E1
0x1800044db  call    cs:__imp_GlobalFree
0x1800044e1  xor     eax, eax
0x1800044e3  jmp     loc_180004755
0x1800044e8  mov     [rsp+3B8h+var_310], 0
0x1800044f4  lea     rax, [rsp+3B8h+var_34C]
0x1800044f9  mov     [rsp+3B8h+var_378], rax; unsigned int *
0x1800044fe  lea     rax, [rsp+3B8h+var_310]
0x180004506  mov     [rsp+3B8h+var_380], rax; char **
0x18000450b  lea     rax, [rsp+3B8h+P]
0x180004513  mov     qword ptr [rsp+3B8h+cLines], rax; struct tagBITMAPINFOHEADER **
0x180004518  mov     [rsp+3B8h+var_390], 0; struct tagBITMAPINFOHEADER *
0x180004521  mov     dword ptr [rsp+3B8h+lpBits], r14d; unsigned int
0x180004526  mov     r9d, [rsp+3B8h+var_350]; unsigned int
0x18000452b  mov     r8d, r13d; unsigned int
0x18000452e  mov     edx, r15d; unsigned int
0x180004531  mov     rcx, rsi; struct tagBITMAPINFOHEADER *
0x180004534  call    ?ConvertDIBBitmap@@YAPEAUHBITMAP__@@PEFAUtagBITMAPINFOHEADER@@KKKIPEAU2@PEAPEAU2@PEAPEADPEAK@Z; ConvertDIBBitmap(tagBITMAPINFOHEADER *,ulong,ulong,ulong,uint,tagBITMAPINFOHEADER *,tagBITMAPINFOHEADER * *,char * *,ulong *)
0x180004539  mov     [rsp+3B8h+ho], rax
0x180004541  test    rax, rax
0x180004544  jz      loc_1800047E3
0x18000454a  mov     rsi, [rsp+3B8h+hModule]
0x180004552  test    rsi, rsi
0x180004555  jnz     loc_180004777
0x18000455b  mov     [rsp+3B8h+var_2E0], rsi
0x180004563  cmp     [rsp+3B8h+arg_20], 0
0x18000456b  jz      loc_18000480C
0x180004571  mov     eax, 3
0x180004576  mov     [rsp+3B8h+var_2D8], ax
0x18000457e  mov     rax, [rsp+3B8h+var_300]
0x180004586  mov     [rsp+3B8h+var_2E8], rax
0x18000458e  mov     rsi, [rsp+3B8h+P]
0x180004596  movzx   ecx, word ptr [rsi+0Eh]
0x18000459a  movzx   eax, word ptr [rsi+0Ch]
0x18000459e  imul    ecx, eax
0x1800045a1  mov     [rsp+3B8h+var_298], ecx
0x1800045a8  test    r13d, r13d
0x1800045ab  jnz     short loc_1800045B6
0x1800045ad  mov     r13d, [rsi+4]
0x1800045b1  mov     [rsp+3B8h+var_348], r13d
0x1800045b6  mov     r15d, [rsp+3B8h+var_350]
0x1800045bb  mov     r9d, 2
0x1800045c1  test    r15d, r15d
0x1800045c4  jnz     short loc_1800045D4
0x1800045c6  mov     eax, [rsi+8]
0x1800045c9  cdq
0x1800045ca  idiv    r9d
0x1800045cd  mov     r15d, eax
0x1800045d0  mov     [rsp+3B8h+var_340], eax
0x1800045d4  cmp     [rsp+3B8h+arg_20], 0
0x1800045dc  jz      loc_18000481A
0x1800045e2  mov     eax, r13d
0x1800045e5  cdq
0x1800045e6  idiv    r9d
0x1800045e9  mov     [rsp+3B8h+var_2CC], ax
0x1800045f1  mov     eax, r15d
0x1800045f4  cdq
0x1800045f5  idiv    r9d
0x1800045f8  mov     [rsp+3B8h+var_2CA], ax
0x180004600  mov     edx, r12d; unsigned int
0x180004603  mov     rcx, rsi; struct tagBITMAPINFOHEADER *
0x180004606  call    ?ChangeDibColors@@YAXPEAUtagBITMAPINFOHEADER@@I@Z; ChangeDibColors(tagBITMAPINFOHEADER *,uint)
0x18000460b  mov     rcx, [rsp+3B8h+var_310]
0x180004613  test    rcx, rcx
0x180004616  jz      loc_180004860
0x18000461c  mov     r9d, r12d; unsigned __int16
0x18000461f  mov     r8d, r12d; unsigned __int16
0x180004622  lea     edx, [r15+r15]; int
0x180004626  mov     [rsp+3B8h+var_368], 0; struct tagBITMAPINFO *
0x18000462f  mov     [rsp+3B8h+lpbmi], rsi; lpbmi
0x180004634  mov     eax, [rsp+3B8h+var_34C]
0x180004638  mov     dword ptr [rsp+3B8h+var_378], eax; unsigned int
0x18000463c  mov     [rsp+3B8h+var_380], rcx; char *
0x180004641  mov     eax, [rsi+8]
0x180004644  mov     [rsp+3B8h+cLines], eax; cLines
0x180004648  mov     eax, [rsi+4]
0x18000464b  mov     dword ptr [rsp+3B8h+var_390], eax; int
0x18000464f  mov     dword ptr [rsp+3B8h+lpBits], 0; unsigned int
0x180004657  mov     ecx, r13d; int
0x18000465a  call    ?BitmapFromDIB@@YAPEAUHBITMAP__@@HHGGIHHPEADKPEAUtagBITMAPINFO@@1PEAUHPALETTE__@@@Z; BitmapFromDIB(int,int,ushort,ushort,uint,int,int,char *,ulong,tagBITMAPINFO *,tagBITMAPINFO *,HPALETTE__ *)
0x18000465f  mov     [rsp+3B8h+var_2C8], rax
0x180004667  jmp     short loc_180004696
0x180004669  xor     eax, eax
0x18000466b  mov     [rsp+3B8h+var_2C8], rax
0x180004673  lea     r12d, [rax+1]
0x180004677  mov     rsi, [rsp+3B8h+P]
0x18000467f  mov     rdi, [rsp+3B8h+hMem]
0x180004687  mov     r13d, [rsp+3B8h+var_348]
0x18000468c  mov     r15d, [rsp+3B8h+var_340]
0x180004691  mov     r14d, [rsp+3B8h+var_358]
0x180004696  test    rax, rax
0x180004699  jnz     short loc_1800046C4
0x18000469b  lea     edx, [r15+r15]; nHeight
0x18000469f  mov     [rsp+3B8h+lpBits], rax; lpBits
0x1800046a4  mov     r9d, r12d; nBitCount
0x1800046a7  mov     r8d, r12d; nPlanes
0x1800046aa  mov     ecx, r13d; nWidth
0x1800046ad  call    cs:__imp_CreateBitmap
0x1800046b3  mov     [rsp+3B8h+var_2C8], rax
0x1800046bb  test    rax, rax
0x1800046be  jz      loc_1800047C3
0x1800046c4  mov     [rsp+3B8h+var_294], r13d
0x1800046cc  lea     eax, [r15+r15]
0x1800046d0  mov     [rsp+3B8h+var_290], eax
0x1800046d7  mov     r8, rsi; P
0x1800046da  xor     edx, edx; Flags
0x1800046dc  mov     rcx, cs:pUserHeap; HeapHandle
0x1800046e3  call    cs:__imp_RtlFreeHeap
0x1800046e9  bt      r14d, 0Fh
0x1800046ee  jnb     short loc_1800046F8
0x1800046f0  or      [rsp+3B8h+var_2D0], 4
0x1800046f8  bt      r14d, 8
0x1800046fd  jnb     short loc_180004707
0x1800046ff  or      [rsp+3B8h+var_2D0], 2
0x180004707  bt      r14d, 0Ah
0x18000470c  jnb     short loc_180004716
0x18000470e  or      [rsp+3B8h+var_2D0], 40h
0x180004716  bt      r14d, 12h
0x18000471b  jnb     short loc_180004726
0x18000471d  bts     [rsp+3B8h+var_2D0], 0Ch
0x180004726  cmp     [rsp+3B8h+var_338], 0
0x18000472f  jz      short loc_18000473A
0x180004731  mov     rcx, rdi; hMem
0x180004734  call    cs:__imp_GlobalUnlock
0x18000473a  test    rdi, rdi
0x18000473d  jz      short loc_180004748
0x18000473f  mov     rcx, rdi; hMem
0x180004742  call    cs:__imp_GlobalFree
0x180004748  lea     rcx, [rsp+3B8h+var_2E8]; struct tagCURSORDATA *
0x180004750  call    ?CreateIcoCur@@YAPEAUHICON__@@PEAUtagCURSORDATA@@@Z; CreateIcoCur(tagCURSORDATA *)
0x180004755  mov     rcx, [rsp+3B8h+var_48]
0x18000475d  xor     rcx, rsp; StackCookie
0x180004760  call    __security_check_cookie
0x180004765  add     rsp, 388h
0x18000476c  pop     r15
0x18000476e  pop     r14
0x180004770  pop     r13
0x180004772  pop     r12
0x180004774  pop     rdi
0x180004775  pop     rsi
0x180004776  retn
0x180004777  mov     [rsp+3B8h+var_2D0], r12d
0x18000477f  cmp     rsi, cs:hmodUser
0x180004786  jz      loc_180004881
0x18000478c  mov     r15d, 104h
0x180004792  mov     r8d, r15d; nSize
0x180004795  lea     rdx, [rsp+3B8h+Filename]; lpFilename
0x18000479d  mov     rcx, rsi; hModule
0x1800047a0  call    cs:__imp_GetModuleFileNameW
0x1800047a6  test    eax, eax
0x1800047a8  jz      loc_18000488D
0x1800047ae  lea     rax, [rsp+3B8h+Filename]
0x1800047b6  mov     [rsp+3B8h+var_2E0], rax
0x1800047be  jmp     loc_180004563
0x1800047c3  mov     rcx, [rsp+3B8h+ho]; ho
0x1800047cb  call    cs:__imp_DeleteObject
0x1800047d1  mov     r8, rsi; P
0x1800047d4  xor     edx, edx; Flags
0x1800047d6  mov     rcx, cs:pUserHeap; HeapHandle
0x1800047dd  call    cs:__imp_RtlFreeHeap
0x1800047e3  cmp     [rsp+3B8h+var_338], 0
0x1800047ec  jz      short loc_1800047F7
0x1800047ee  mov     rcx, rdi; hMem
0x1800047f1  call    cs:__imp_GlobalUnlock
0x1800047f7  test    rdi, rdi
0x1800047fa  jz      short loc_180004805
0x1800047fc  mov     rcx, rdi; hMem
0x1800047ff  call    cs:__imp_GlobalFree
0x180004805  xor     eax, eax
0x180004807  jmp     loc_180004755
  ... truncated ...
```
