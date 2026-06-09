# ECSetFont(tagED *,HFONT__ *,int)

- ea: `0x180035670`
- end: `0x180035ae1`
- name: `?ECSetFont@@YAXPEAUtagED@@PEAUHFONT__@@H@Z`
- size: `1137`
- prototype: `void __fastcall(struct tagED *, HFONT, int)`
- caller_count: `4`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180033af0`
- `0x180035670`
- `0x180063e8c`
- `0x18007ead4`

## callees

- `0x180033e80`
- `0x180035330`
- `0x180035450`
- `0x180035670`
- `0x180035ae8`
- `0x1800374d0`
- `0x180037558`
- `0x180037790`
- `0x1800798dc`
- `0x180079d6c`
- `0x18007a12c`
- `0x1800968f4`
- `0x180096e00`
- `0x1800a2010`

## import_xrefs

- `win32u!NtUserShowCaret` at `0x18009bfd8`
- `win32u!NtUserShowCaret` at `0x18009bfd8`
- `win32u!NtUserCreateCaret` at `0x18009bfce`
- `win32u!NtUserCreateCaret` at `0x18009bfce`
- `win32u!NtUserDestroyCaret` at `0x18009bf88`
- `win32u!NtUserDestroyCaret` at `0x18009bf88`
- `win32u!NtUserHideCaret` at `0x18009bf82`
- `win32u!NtUserHideCaret` at `0x18009bf82`
- `win32u!NtUserGetDC` at `0x1800356be`
- `win32u!NtUserGetDC` at `0x1800356be`
- `ntdll!RtlReAllocateHeap` at `0x18009bea9`
- `ntdll!RtlReAllocateHeap` at `0x18009bea9`
- `ntdll!RtlFreeHeap` at `0x180035a87`
- `ntdll!RtlFreeHeap` at `0x18009bec7`
- `ntdll!RtlFreeHeap` at `0x18009bf45`
- `ntdll!RtlFreeHeap` at `0x180035a87`
- `ntdll!RtlFreeHeap` at `0x18009bec7`
- `ntdll!RtlFreeHeap` at `0x18009bf45`
- `ntdll!RtlAllocateHeap` at `0x18009bed6`
- `ntdll!RtlAllocateHeap` at `0x18009bed6`
- `GDI32!SelectObject` at `0x1800356d9`
- `GDI32!SelectObject` at `0x1800358b4`
- `GDI32!SelectObject` at `0x180035a49`
- `GDI32!SelectObject` at `0x1800356d9`
- `GDI32!SelectObject` at `0x1800358b4`
- `GDI32!SelectObject` at `0x180035a49`
- `GDI32!GetCharWidthInfo` at `0x180035a65`
- `GDI32!GetCharWidthInfo` at `0x180035a65`
- `GDI32!GetCharWidthA` at `0x18009bf2b`
- `GDI32!GetCharWidthA` at `0x18009bf2b`

## pseudocode

```c
void __fastcall ECSetFont(struct tagED *a1, HFONT a2, int a3)
{
  __int64 v4; // rcx
  HDC DC; // rax
  __int64 v8; // rcx
  HDC v9; // rdi
  HGDIOBJ v10; // rsi
  int CharDimensions; // eax
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 DpiServerInfoForCurrentThread; // rax
  LONG tmOverhang; // eax
  int v16; // eax
  int v17; // eax
  __int64 i; // rdx
  int v19; // r8d
  int v20; // r8d
  unsigned int v21; // ecx
  int v22; // r9d
  int v23; // r8d
  unsigned int v24; // r10d
  unsigned int v25; // r11d
  unsigned int v26; // r14d
  int v27; // eax
  unsigned int v28; // eax
  unsigned int v29; // et2
  unsigned int v30; // edx
  int v31; // ecx
  int v32; // eax
  void *v33; // r8
  int v34; // ecx
  unsigned int v35; // ecx
  void *v36; // r14
  SIZE_T v37; // r8
  PVOID Heap; // rax
  PVOID v39; // rax
  int v40; // eax
  __int64 v41; // rdx
  __int64 v42; // rcx
  __int64 v43; // rax
  __int64 v44; // r9
  __int64 v45; // r8
  __int64 v46; // [rsp+30h] [rbp-39h] BYREF
  unsigned int v47; // [rsp+38h] [rbp-31h]
  struct tagTEXTMETRICW tm; // [rsp+40h] [rbp-29h] BYREF

  v46 = 0;
  v4 = *((_QWORD *)a1 + 8);
  v47 = 0;
  memset(&tm, 0, sizeof(tm));
  DC = (HDC)NtUserGetDC(v4);
  *((_QWORD *)a1 + 24) = a2;
  v9 = DC;
  if ( a2 )
  {
    v10 = SelectObject(DC, a2);
    if ( !v10 )
    {
      *((_QWORD *)a1 + 24) = 0;
      a2 = 0;
    }
    CharDimensions = UserGetCharDimensionsEx(v9, a2, &tm, (LONG *)a1 + 51);
    *((_DWORD *)a1 + 50) = CharDimensions;
    if ( !CharDimensions )
    {
      if ( v10 )
        SelectObject(v9, v10);
      ECSetFont(a1, 0, a3);
      return;
    }
  }
  else
  {
    v10 = 0;
    v12 = *(unsigned int *)(GetDpiServerInfoForCurrentThread(v8) + 32);
    *((_DWORD *)a1 + 50) = v12;
    v13 = *(unsigned int *)(GetDpiServerInfoForCurrentThread(v12) + 36);
    *((_DWORD *)a1 + 51) = v13;
    DpiServerInfoForCurrentThread = GetDpiServerInfoForCurrentThread(v13);
    *(_OWORD *)&tm.tmHeight = *(_OWORD *)(DpiServerInfoForCurrentThread + 40);
    *(_OWORD *)&tm.tmExternalLeading = *(_OWORD *)(DpiServerInfoForCurrentThread + 56);
    *(_OWORD *)&tm.tmOverhang = *(_OWORD *)(DpiServerInfoForCurrentThread + 72);
    *(_OWORD *)&tm.tmFirstChar = *(_OWORD *)(DpiServerInfoForCurrentThread + 84);
  }
  tmOverhang = tm.tmOverhang;
  *((_DWORD *)a1 + 29) &= ~0x40u;
  *((_DWORD *)a1 + 52) = tmOverhang;
  LOBYTE(tmOverhang) = ~tm.tmPitchAndFamily;
  *(_QWORD *)((char *)a1 + 260) = 0;
  *(_QWORD *)((char *)a1 + 252) = 0;
  *((_DWORD *)a1 + 29) |= (tmOverhang & 1) << 6;
  v16 = *((_DWORD *)a1 + 29);
  if ( (v16 & 0x1000000) != 0 && (tm.tmPitchAndFamily & 4) != 0 )
    *((_DWORD *)a1 + 29) ^= (*((_DWORD *)a1 + 29) ^ ((unsigned int)GetCharWidthInfo(v9, &v46) << 21)) & 0x200000;
  else
    *((_DWORD *)a1 + 29) = v16 & 0xFFDFFFFF;
  v17 = ECGetDBCSVector(a1, v9, tm.tmCharSet);
  v19 = (*((_DWORD *)a1 + 29) ^ (v17 << 12)) & 0x1000;
  *((_BYTE *)a1 + 248) = tm.tmCharSet;
  v20 = *((_DWORD *)a1 + 29) ^ v19;
  *((_DWORD *)a1 + 29) = v20;
  if ( (v17 & 1) == 0 )
  {
    if ( (v20 & 1) != 0 || *((_QWORD *)a1 + 36) )
      goto LABEL_13;
    v36 = (void *)*((_QWORD *)a1 + 30);
    v37 = (v20 & 0x200000 | 0x100000uLL) >> 11;
    if ( v36 )
    {
      Heap = RtlReAllocateHeap(pUserHeap, 8u, *((PVOID *)a1 + 30), v37);
      *((_QWORD *)a1 + 30) = Heap;
      if ( Heap )
      {
LABEL_59:
        if ( (*((_DWORD *)a1 + 29) & 0x200000) == 0
          || (v40 = *((_DWORD *)a1 + 29) ^ (*((_DWORD *)a1 + 29) ^ (GetNegABCwidthInfo(a1, v9) << 21)) & 0x200000,
              *((_DWORD *)a1 + 29) = v40,
              (v40 & 0x200000) == 0) )
        {
          if ( GetCharWidthA(v9, 0, 0x7Fu, *((LPINT *)a1 + 30)) )
          {
            for ( i = 0; i != 128; ++i )
              *(_DWORD *)(*((_QWORD *)a1 + 30) + 4 * i) -= *((_DWORD *)a1 + 52);
          }
          else
          {
            RtlFreeHeap(pUserHeap, 0, *((PVOID *)a1 + 30));
            *((_QWORD *)a1 + 30) = 0;
          }
        }
        goto LABEL_13;
      }
      RtlFreeHeap(pUserHeap, 0, v36);
      v39 = (PVOID)*((_QWORD *)a1 + 30);
    }
    else
    {
      v39 = RtlAllocateHeap(pUserHeap, 8u, v37);
      *((_QWORD *)a1 + 30) = v39;
    }
    if ( !v39 )
      goto LABEL_13;
    goto LABEL_59;
  }
  v33 = (void *)*((_QWORD *)a1 + 30);
  if ( v33 )
  {
    RtlFreeHeap(pUserHeap, 0, v33);
    *((_QWORD *)a1 + 30) = 0;
  }
  v34 = *((_DWORD *)a1 + 29);
  if ( (v34 & 0x40) != 0 && 2 * *((_DWORD *)a1 + 50) == tm.tmMaxCharWidth )
    v35 = v34 | 0x80;
  else
    v35 = v34 & 0xFFFFFF7F;
  *((_DWORD *)a1 + 29) = v35;
LABEL_13:
  v21 = *(unsigned __int16 *)(gpsi + 4996) | (*(unsigned __int16 *)(gpsi + 5000) << 16);
  if ( (*((_DWORD *)a1 + 29) & 0x200000) != 0 )
  {
    if ( (int)v46 >= 0 )
      v22 = 0;
    else
      v22 = -(int)v46;
    *((_DWORD *)a1 + 63) = v22;
    if ( v46 >= 0 )
      v23 = 0;
    else
      v23 = -HIDWORD(v46);
    *((_DWORD *)a1 + 65) = v23;
    v24 = v47;
    if ( v47 )
    {
      v25 = (v47 - 1 + v22) / v47;
      *((_DWORD *)a1 + 64) = v25;
      i = (v24 - 1 + v23) % v24;
      v26 = (v24 - 1 + v23) / v24;
      *((_DWORD *)a1 + 66) = v26;
      v27 = v23 + v22;
      if ( v23 + v22 > v24 )
      {
        v29 = (v27 - 1) % v24;
        v28 = (v27 - 1) / v24;
        i = v29;
        *((_DWORD *)a1 + 66) = v26 + v28;
        *((_DWORD *)a1 + 64) = v28 + v25;
      }
      goto LABEL_21;
    }
    goto LABEL_35;
  }
  v32 = *((_DWORD *)a1 + 52);
  if ( v32 )
  {
    *((_DWORD *)a1 + 65) = v32;
    *((_DWORD *)a1 + 63) = v32;
LABEL_35:
    *((_DWORD *)a1 + 66) = HIWORD(v21);
    *((_DWORD *)a1 + 64) = (unsigned __int16)v21;
  }
LABEL_21:
  if ( a2 )
  {
    if ( v10 )
      SelectObject(v9, v10);
  }
  else
  {
    *((_DWORD *)a1 + 53) = *((_DWORD *)a1 + 50);
    *((_DWORD *)a1 + 54) = *((_DWORD *)a1 + 51);
  }
  if ( (*((_BYTE *)a1 + 116) & 8) != 0 )
  {
    NtUserHideCaret(*((_QWORD *)a1 + 8), i);
    NtUserDestroyCaret(v42, v41);
    v43 = *((_QWORD *)a1 + 36);
    v44 = *((unsigned int *)a1 + 51);
    v45 = *(unsigned int *)(gpsi + 7008);
    if ( v43 )
      (*(void (__fastcall **)(struct tagED *, HDC, __int64, __int64, _DWORD))(v43 + 96))(a1, v9, v45, v44, 0);
    else
      NtUserCreateCaret(*((_QWORD *)a1 + 8), 0, v45, v44);
    NtUserShowCaret(*((_QWORD *)a1 + 8));
  }
  ReleaseDC(*((HWND *)a1 + 8), v9);
  v30 = *((_DWORD *)a1 + 13);
  if ( v30 )
    ECSetPasswordChar(a1, v30);
  v31 = *((_DWORD *)a1 + 29);
  if ( (v31 & 0x200000) != 0 && LODWORD(NtCurrentTeb()->Win32ClientInfo[2]) >= 0x400 )
  {
    if ( (v31 & 0x1000) != 0 )
      ECCalcMarginForDBCSFont(a1, a3);
    else
      ECSetMargin(a1, 3u, -1, a3);
  }
  if ( (*((_DWORD *)a1 + 29) & 0x4001) == 0 )
    MLBuildchLines(a1, 0, 0, 0, 0, 0);
  ECSize(a1, 0, a3);
  if ( (*((_BYTE *)a1 + 116) & 8) != 0
    && ((unsigned int (__fastcall *)(SIZE_T))off_1800C85E0[0])(NtCurrentTeb()->Win32ClientInfo[18]) )
  {
    ECImmSetCompositionFont(a1);
  }
}

```

## disassembly

```asm
0x180035670  push    rbp
0x180035672  push    rbx
0x180035673  push    rsi
0x180035674  push    rdi
0x180035675  push    r12
0x180035677  push    r14
0x180035679  push    r15
0x18003567b  lea     rbp, [rsp-27h]
0x180035680  sub     rsp, 90h
0x180035687  mov     rax, cs:__security_cookie
0x18003568e  xor     rax, rsp
0x180035691  mov     [rbp+57h+var_40], rax
0x180035695  xorps   xmm0, xmm0
0x180035698  xor     eax, eax
0x18003569a  mov     rbx, rcx
0x18003569d  mov     [rbp+57h+var_90], rax
0x1800356a1  mov     rcx, [rcx+40h]
0x1800356a5  mov     r12d, r8d
0x1800356a8  movups  xmmword ptr [rbp+57h+tm.tmOverhang], xmm0
0x1800356ac  mov     r15, rdx
0x1800356af  mov     [rbp+57h+var_88], eax
0x1800356b2  movups  xmmword ptr [rbp+57h+tm.tmFirstChar], xmm0
0x1800356b6  movups  xmmword ptr [rbp+57h+tm.tmHeight], xmm0
0x1800356ba  movups  xmmword ptr [rbp+57h+tm.tmExternalLeading], xmm0
0x1800356be  call    cs:__imp_NtUserGetDC
0x1800356c4  mov     [rbx+0C0h], r15
0x1800356cb  mov     rdi, rax
0x1800356ce  test    r15, r15
0x1800356d1  jz      short loc_180035726
0x1800356d3  mov     rdx, r15; h
0x1800356d6  mov     rcx, rax; hdc
0x1800356d9  call    cs:__imp_SelectObject
0x1800356df  mov     rsi, rax
0x1800356e2  test    rax, rax
0x1800356e5  jz      loc_180035A30
0x1800356eb  lea     r9, [rbx+0CCh]; LONG *
0x1800356f2  mov     rdx, r15; h
0x1800356f5  lea     r8, [rbp+57h+tm]; lptm
0x1800356f9  mov     rcx, rdi; hdc
0x1800356fc  call    ?UserGetCharDimensionsEx@@YAHPEAUHDC__@@PEAUHFONT__@@PEAUtagTEXTMETRICW@@PEAH@Z; UserGetCharDimensionsEx(HDC__ *,HFONT__ *,tagTEXTMETRICW *,int *)
0x180035701  mov     [rbx+0C8h], eax
0x180035707  test    eax, eax
0x180035709  jnz     short loc_180035769
0x18003570b  test    rsi, rsi
0x18003570e  jnz     loc_180035A43
0x180035714  mov     r8d, r12d; int
0x180035717  xor     edx, edx; HFONT
0x180035719  mov     rcx, rbx; struct tagED *
0x18003571c  call    ?ECSetFont@@YAXPEAUtagED@@PEAUHFONT__@@H@Z; ECSetFont(tagED *,HFONT__ *,int)
0x180035721  jmp     loc_180035926
0x180035726  xor     esi, esi
0x180035728  call    GetDpiServerInfoForCurrentThread
0x18003572d  mov     ecx, [rax+20h]
0x180035730  mov     [rbx+0C8h], ecx
0x180035736  call    GetDpiServerInfoForCurrentThread
0x18003573b  mov     ecx, [rax+24h]
0x18003573e  mov     [rbx+0CCh], ecx
0x180035744  call    GetDpiServerInfoForCurrentThread
0x180035749  movups  xmm0, xmmword ptr [rax+28h]
0x18003574d  movups  xmmword ptr [rbp+57h+tm.tmHeight], xmm0
0x180035751  movups  xmm1, xmmword ptr [rax+38h]
0x180035755  movups  xmmword ptr [rbp+57h+tm.tmExternalLeading], xmm1
0x180035759  movups  xmm0, xmmword ptr [rax+48h]
0x18003575d  movups  xmmword ptr [rbp+57h+tm.tmOverhang], xmm0
0x180035761  movups  xmm1, xmmword ptr [rax+54h]
0x180035765  movups  xmmword ptr [rbp+57h+tm.tmFirstChar], xmm1
0x180035769  mov     eax, [rbp+57h+tm.tmOverhang]
0x18003576c  and     dword ptr [rbx+74h], 0FFFFFFBFh
0x180035770  mov     [rbx+0D0h], eax
0x180035776  mov     al, [rbp+57h+tm.tmPitchAndFamily]
0x180035779  not     al
0x18003577b  mov     qword ptr [rbx+104h], 0
0x180035786  and     eax, 1
0x180035789  mov     qword ptr [rbx+0FCh], 0
0x180035794  shl     eax, 6
0x180035797  or      [rbx+74h], eax
0x18003579a  mov     eax, [rbx+74h]
0x18003579d  bt      eax, 18h
0x1800357a1  jb      loc_180035A54
0x1800357a7  btr     eax, 15h
0x1800357ab  mov     [rbx+74h], eax
0x1800357ae  mov     r8b, [rbp+57h+tm.tmCharSet]; unsigned __int8
0x1800357b2  mov     rdx, rdi; HDC
0x1800357b5  mov     rcx, rbx; struct tagED *
0x1800357b8  call    ?ECGetDBCSVector@@YAHPEAUtagED@@PEAUHDC__@@E@Z; ECGetDBCSVector(tagED *,HDC__ *,uchar)
0x1800357bd  mov     cl, [rbp+57h+tm.tmCharSet]
0x1800357c0  mov     r8d, eax
0x1800357c3  shl     r8d, 0Ch
0x1800357c7  xor     r8d, [rbx+74h]
0x1800357cb  and     r8d, 1000h
0x1800357d2  mov     [rbx+0F8h], cl
0x1800357d8  xor     r8d, [rbx+74h]
0x1800357dc  mov     ecx, 8
0x1800357e1  mov     [rbx+74h], r8d
0x1800357e5  test    al, 1
0x1800357e7  jnz     loc_180035975
0x1800357ed  test    r8b, 1
0x1800357f1  jz      loc_18009BE70
0x1800357f7  mov     rax, cs:gpsi
0x1800357fe  movzx   ecx, word ptr [rax+1388h]
0x180035805  movzx   eax, word ptr [rax+1384h]
0x18003580c  shl     ecx, 10h
0x18003580f  or      ecx, eax
0x180035811  test    dword ptr [rbx+74h], 200000h
0x180035818  jz      loc_180035944
0x18003581e  mov     r9d, dword ptr [rbp+57h+var_90]
0x180035822  test    r9d, r9d
0x180035825  jns     loc_180035AB7
0x18003582b  neg     r9d
0x18003582e  mov     [rbx+0FCh], r9d
0x180035835  mov     r8d, dword ptr [rbp+57h+var_90+4]
0x180035839  test    r8d, r8d
0x18003583c  jns     loc_180035ABF
0x180035842  neg     r8d
0x180035845  mov     [rbx+104h], r8d
0x18003584c  mov     r10d, [rbp+57h+var_88]
0x180035850  test    r10d, r10d
0x180035853  jz      loc_18003595E
0x180035859  xor     edx, edx
0x18003585b  lea     ecx, [r10-1]
0x18003585f  lea     eax, [rcx+r9]
0x180035863  div     r10d
0x180035866  xor     edx, edx
0x180035868  mov     r11d, eax
0x18003586b  mov     [rbx+100h], eax
0x180035871  lea     eax, [rcx+r8]
0x180035875  div     r10d
0x180035878  mov     r14d, eax
0x18003587b  mov     [rbx+108h], eax
0x180035881  lea     eax, [r8+r9]
0x180035885  cmp     eax, r10d
0x180035888  jbe     short loc_1800358A4
0x18003588a  dec     eax
0x18003588c  xor     edx, edx
0x18003588e  div     r10d
0x180035891  lea     ecx, [rax+r11]
0x180035895  add     eax, r14d
0x180035898  mov     [rbx+108h], eax
0x18003589e  mov     [rbx+100h], ecx
0x1800358a4  test    r15, r15
0x1800358a7  jz      short loc_1800358BC
0x1800358a9  test    rsi, rsi
0x1800358ac  jz      short loc_1800358D4
0x1800358ae  mov     rdx, rsi; h
0x1800358b1  mov     rcx, rdi; hdc
0x1800358b4  call    cs:__imp_SelectObject
0x1800358ba  jmp     short loc_1800358D4
0x1800358bc  mov     eax, [rbx+0C8h]
0x1800358c2  mov     [rbx+0D4h], eax
0x1800358c8  mov     eax, [rbx+0CCh]
0x1800358ce  mov     [rbx+0D8h], eax
0x1800358d4  test    byte ptr [rbx+74h], 8
0x1800358d8  jnz     loc_18009BF7E
0x1800358de  mov     rcx, [rbx+40h]; hWnd
0x1800358e2  mov     rdx, rdi; hDC
0x1800358e5  call    ReleaseDC
0x1800358ea  mov     edx, [rbx+34h]; unsigned int
0x1800358ed  test    edx, edx
0x1800358ef  jnz     loc_180035AC7
0x1800358f5  mov     ecx, [rbx+74h]
0x1800358f8  bt      ecx, 15h
0x1800358fc  jb      loc_18003599D
0x180035902  test    dword ptr [rbx+74h], 4001h
0x180035909  jz      loc_1800359D8
0x18003590f  mov     r8d, r12d; int
0x180035912  xor     edx, edx; struct tagRECT *
0x180035914  mov     rcx, rbx; struct tagED *
0x180035917  call    ?ECSize@@YAXPEAUtagED@@PEAUtagRECT@@H@Z; ECSize(tagED *,tagRECT *,int)
0x18003591c  test    byte ptr [rbx+74h], 8
0x180035920  jnz     loc_1800359FF
0x180035926  mov     rcx, [rbp+57h+var_40]
0x18003592a  xor     rcx, rsp; StackCookie
0x18003592d  call    __security_check_cookie
0x180035932  add     rsp, 90h
0x180035939  pop     r15
0x18003593b  pop     r14
0x18003593d  pop     r12
0x18003593f  pop     rdi
0x180035940  pop     rsi
0x180035941  pop     rbx
0x180035942  pop     rbp
0x180035943  retn
0x180035944  mov     eax, [rbx+0D0h]
0x18003594a  test    eax, eax
0x18003594c  jz      loc_1800358A4
0x180035952  mov     [rbx+104h], eax
0x180035958  mov     [rbx+0FCh], eax
0x18003595e  movzx   eax, cx
0x180035961  shr     ecx, 10h
0x180035964  mov     [rbx+108h], ecx
0x18003596a  mov     [rbx+100h], eax
0x180035970  jmp     loc_1800358A4
0x180035975  mov     r8, [rbx+0F0h]; P
0x18003597c  test    r8, r8
0x18003597f  jnz     loc_180035A7E
0x180035985  mov     ecx, [rbx+74h]
0x180035988  test    cl, 40h
0x18003598b  jnz     loc_180035A9D
0x180035991  btr     ecx, 7
0x180035995  mov     [rbx+74h], ecx
0x180035998  jmp     loc_1800357F7
0x18003599d  mov     rax, gs:30h
0x1800359a6  cmp     dword ptr [rax+810h], 400h
0x1800359b0  jb      loc_180035902
0x1800359b6  bt      ecx, 0Ch
0x1800359ba  mov     rcx, rbx; struct tagED *
0x1800359bd  jb      loc_180035AD4
0x1800359c3  or      r8d, 0FFFFFFFFh; int
0x1800359c7  mov     r9d, r12d; int
0x1800359ca  lea     edx, [r8+4]; unsigned int
0x1800359ce  call    ?ECSetMargin@@YAXPEAUtagED@@IJH@Z; ECSetMargin(tagED *,uint,long,int)
0x1800359d3  jmp     loc_180035902
0x1800359d8  mov     [rsp+0C0h+var_98], 0; int *
0x1800359e1  xor     r9d, r9d; int
0x1800359e4  xor     r8d, r8d; int
0x1800359e7  mov     [rsp+0C0h+var_A0], 0; int *
0x1800359f0  xor     edx, edx; unsigned int
0x1800359f2  mov     rcx, rbx; struct tagED *
0x1800359f5  call    ?MLBuildchLines@@YAXPEAUtagED@@KHHPEAJ1@Z; MLBuildchLines(tagED *,ulong,int,int,long *,long *)
0x1800359fa  jmp     loc_18003590F
0x1800359ff  mov     rcx, gs:30h
0x180035a08  mov     rax, cs:off_1800C85E0
0x180035a0f  mov     rcx, [rcx+890h]
0x180035a16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035a1b  test    eax, eax
0x180035a1d  jz      loc_180035926
0x180035a23  mov     rcx, rbx; struct tagED *
0x180035a26  call    ?ECImmSetCompositionFont@@YAXPEAUtagED@@@Z; ECImmSetCompositionFont(tagED *)
0x180035a2b  jmp     loc_180035926
0x180035a30  mov     qword ptr [rbx+0C0h], 0
0x180035a3b  xor     r15d, r15d
0x180035a3e  jmp     loc_1800356EB
0x180035a43  mov     rdx, rsi; h
0x180035a46  mov     rcx, rdi; hdc
0x180035a49  call    cs:__imp_SelectObject
0x180035a4f  jmp     loc_180035714
0x180035a54  test    [rbp+57h+tm.tmPitchAndFamily], 4
0x180035a58  jz      loc_1800357A7
0x180035a5e  lea     rdx, [rbp+57h+var_90]
0x180035a62  mov     rcx, rdi
0x180035a65  call    cs:__imp_GetCharWidthInfo
0x180035a6b  shl     eax, 15h
0x180035a6e  xor     eax, [rbx+74h]
0x180035a71  and     eax, 200000h
0x180035a76  xor     [rbx+74h], eax
0x180035a79  jmp     loc_1800357AE
0x180035a7e  mov     rcx, cs:pUserHeap; HeapHandle
0x180035a85  xor     edx, edx; Flags
0x180035a87  call    cs:__imp_RtlFreeHeap
0x180035a8d  mov     qword ptr [rbx+0F0h], 0
0x180035a98  jmp     loc_180035985
0x180035a9d  mov     eax, [rbx+0C8h]
0x180035aa3  add     eax, eax
0x180035aa5  cmp     eax, [rbp+57h+tm.tmMaxCharWidth]
0x180035aa8  jnz     loc_180035991
0x180035aae  bts     ecx, 7
0x180035ab2  jmp     loc_180035995
0x180035ab7  xor     r9d, r9d
0x180035aba  jmp     loc_18003582E
0x180035abf  xor     r8d, r8d
0x180035ac2  jmp     loc_180035845
0x180035ac7  mov     rcx, rbx; struct tagED *
0x180035aca  call    ?ECSetPasswordChar@@YAXPEAUtagED@@I@Z; ECSetPasswordChar(tagED *,uint)
0x180035acf  jmp     loc_1800358F5
0x180035ad4  mov     edx, r12d; int
0x180035ad7  call    ?ECCalcMarginForDBCSFont@@YAXPEAUtagED@@H@Z; ECCalcMarginForDBCSFont(tagED *,int)
0x180035adc  jmp     loc_180035902
0x18009be70  cmp     qword ptr [rbx+120h], 0
0x18009be78  jnz     loc_1800357F7
0x18009be7e  mov     r14, [rbx+0F0h]
0x18009be85  and     r8d, 200000h
0x18009be8c  bts     r8, 14h
0x18009be91  mov     edx, ecx; Flags
0x18009be93  mov     rcx, cs:pUserHeap; HeapHandle
0x18009be9a  shr     r8, 0Bh; Size
0x18009be9e  test    r14, r14
0x18009bea1  jz      short loc_18009BED6
0x18009bea3  mov     r9, r8; Size
0x18009bea6  mov     r8, r14; Ptr
0x18009bea9  call    cs:__imp_RtlReAllocateHeap
0x18009beaf  mov     [rbx+0F0h], rax
0x18009beb6  test    rax, rax
0x18009beb9  jnz     short loc_18009BEEC
0x18009bebb  mov     rcx, cs:pUserHeap; HeapHandle
0x18009bec2  mov     r8, r14; P
0x18009bec5  xor     edx, edx; Flags
0x18009bec7  call    cs:__imp_RtlFreeHeap
0x18009becd  mov     rax, [rbx+0F0h]
0x18009bed4  jmp     short loc_18009BEE3
0x18009bed6  call    cs:__imp_RtlAllocateHeap
0x18009bedc  mov     [rbx+0F0h], rax
0x18009bee3  test    rax, rax
0x18009bee6  jz      loc_1800357F7
0x18009beec  mov     eax, [rbx+74h]
0x18009beef  bt      eax, 15h
0x18009bef3  jnb     short loc_18009BF1B
0x18009bef5  mov     rdx, rdi; HDC
0x18009bef8  mov     rcx, rbx; struct tagED *
0x18009befb  call    ?GetNegABCwidthInfo@@YAHPEAUtagED@@PEAUHDC__@@@Z; GetNegABCwidthInfo(tagED *,HDC__ *)
0x18009bf00  shl     eax, 15h
  ... truncated ...
```
