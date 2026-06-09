# PrintMessage(_PrintInfo *)

- ea: `0x1800781bc`
- end: `0x1800783ef`
- name: `?PrintMessage@@YAJPEAU_PrintInfo@@@Z`
- size: `563`
- prototype: `__int64 __fastcall(struct _PrintInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180079b60`

## callees

- `0x180077c74`
- `0x1800781bc`
- `0x180078560`

## import_xrefs

- `GDI32!GetTextExtentPointW` at `0x180078271`
- `GDI32!GetTextExtentPointW` at `0x180078271`
- `GDI32!GetStockObject` at `0x180078215`
- `GDI32!GetStockObject` at `0x18007822f`
- `GDI32!GetStockObject` at `0x180078215`
- `GDI32!GetStockObject` at `0x18007822f`
- `GDI32!TextOutW` at `0x180078345`
- `GDI32!TextOutW` at `0x180078345`
- `GDI32!Rectangle` at `0x180078366`
- `GDI32!Rectangle` at `0x180078366`
- `GDI32!MoveToEx` at `0x180078378`
- `GDI32!MoveToEx` at `0x180078378`
- `GDI32!SelectObject` at `0x180078207`
- `GDI32!SelectObject` at `0x180078221`
- `GDI32!SelectObject` at `0x18007823b`
- `GDI32!SelectObject` at `0x1800783b4`
- `GDI32!SelectObject` at `0x1800783c5`
- `GDI32!SelectObject` at `0x1800783d6`
- `GDI32!SelectObject` at `0x180078207`
- `GDI32!SelectObject` at `0x180078221`
- `GDI32!SelectObject` at `0x18007823b`
- `GDI32!SelectObject` at `0x1800783b4`
- `GDI32!SelectObject` at `0x1800783c5`
- `GDI32!SelectObject` at `0x1800783d6`
- `GDI32!LineTo` at `0x18007838b`
- `GDI32!LineTo` at `0x18007838b`
- `USER32!IsRectEmpty` at `0x1800781e0`
- `USER32!IsRectEmpty` at `0x1800781e0`

## pseudocode

```c
__int64 __fastcall PrintMessage(struct _PrintInfo *a1)
{
  unsigned int NextBand; // edi
  HGDIOBJ v3; // r13
  HGDIOBJ StockObject; // rax
  HGDIOBJ v5; // r12
  HGDIOBJ v6; // rax
  HGDIOBJ v7; // rax
  const WCHAR *v8; // rdx
  __int64 c; // rsi
  void *v10; // rbp
  __int64 v11; // r8
  LONG cy; // r8d
  int v13; // r15d
  int v14; // ecx
  int v15; // r15d
  int v16; // r10d
  const WCHAR *v17; // r9
  int v18; // r14d
  int v19; // edi
  LONG v20; // edx
  int bottom; // [rsp+80h] [rbp+8h]
  int left; // [rsp+88h] [rbp+10h]
  int x; // [rsp+90h] [rbp+18h]
  struct tagSIZE sz; // [rsp+98h] [rbp+20h] BYREF

  sz = 0;
  NextBand = 0;
  if ( IsRectEmpty((const RECT *)((char *)a1 + 40)) )
  {
    NextBand = GetNextBand(a1, 1);
    if ( NextBand )
      return NextBand;
  }
  v3 = SelectObject(*(HDC *)a1, *((HGDIOBJ *)a1 + 14));
  StockObject = GetStockObject(4);
  v5 = SelectObject(*(HDC *)a1, StockObject);
  v6 = GetStockObject(7);
  v7 = SelectObject(*(HDC *)a1, v6);
  v8 = (const WCHAR *)*((_QWORD *)a1 + 19);
  c = -1;
  v10 = v7;
  if ( v8 )
  {
    v11 = -1;
    do
      ++v11;
    while ( v8[v11] );
  }
  else
  {
    LODWORD(v11) = 0;
  }
  GetTextExtentPointW(*(HDC *)a1, v8, v11, &sz);
  cy = sz.cy;
  v13 = *((_DWORD *)a1 + 7) / 24 + 2 * sz.cy + 1;
  if ( v13 + *((_DWORD *)a1 + 11) <= *((_DWORD *)a1 + 27) )
    goto LABEL_12;
  if ( v13 + *((_DWORD *)a1 + 3) <= *((_DWORD *)a1 + 27) )
  {
    NextBand = GetNextBand(a1, 1);
    if ( !NextBand )
    {
      cy = sz.cy;
LABEL_12:
      v14 = *((_DWORD *)a1 + 11);
      v15 = v14 + v13;
      v16 = *((_DWORD *)a1 + 10);
      v17 = (const WCHAR *)*((_QWORD *)a1 + 19);
      v18 = v16 + sz.cx;
      x = *((_DWORD *)a1 + 12);
      v19 = v14 + cy;
      left = v16;
      bottom = v14 + cy + *((_DWORD *)a1 + 7) / 24;
      if ( v17 )
      {
        do
          ++c;
        while ( v17[c] );
      }
      else
      {
        LODWORD(c) = 0;
      }
      TextOutW(*(HDC *)a1, v16, v14, v17, c);
      Rectangle(*(HDC *)a1, left, v19, v18, bottom);
      MoveToEx(*(HDC *)a1, v18, v19, 0);
      LineTo(*(HDC *)a1, x, v19);
      v20 = sz.cy;
      *((_DWORD *)a1 + 11) = v15 + 1;
      NextBand = ScPrintBody(a1, v20);
    }
  }
  if ( v3 )
    SelectObject(*(HDC *)a1, v3);
  if ( v5 )
    SelectObject(*(HDC *)a1, v5);
  if ( v10 )
    SelectObject(*(HDC *)a1, v10);
  return NextBand;
}

```

## disassembly

```asm
0x1800781bc  mov     rax, rsp
0x1800781bf  push    rbx
0x1800781c0  push    rbp
0x1800781c1  push    rsi
0x1800781c2  push    rdi
0x1800781c3  push    r12
0x1800781c5  push    r13
0x1800781c7  push    r14
0x1800781c9  push    r15
0x1800781cb  sub     rsp, 38h
0x1800781cf  mov     rbx, rcx
0x1800781d2  xor     r15d, r15d
0x1800781d5  add     rcx, 28h ; '('; lprc
0x1800781d9  mov     [rax+20h], r15
0x1800781dd  mov     edi, r15d
0x1800781e0  call    cs:__imp_IsRectEmpty
0x1800781e6  test    eax, eax
0x1800781e8  jz      short loc_180078200
0x1800781ea  lea     edx, [r15+1]; int
0x1800781ee  mov     rcx, rbx; struct _PrintInfo *
0x1800781f1  call    ?GetNextBand@@YAJPEAU_PrintInfo@@H@Z; GetNextBand(_PrintInfo *,int)
0x1800781f6  mov     edi, eax
0x1800781f8  test    eax, eax
0x1800781fa  jnz     loc_1800783DC
0x180078200  mov     rdx, [rbx+70h]; h
0x180078204  mov     rcx, [rbx]; hdc
0x180078207  call    cs:__imp_SelectObject
0x18007820d  mov     ecx, 4; i
0x180078212  mov     r13, rax
0x180078215  call    cs:__imp_GetStockObject
0x18007821b  mov     rcx, [rbx]; hdc
0x18007821e  mov     rdx, rax; h
0x180078221  call    cs:__imp_SelectObject
0x180078227  mov     ecx, 7; i
0x18007822c  mov     r12, rax
0x18007822f  call    cs:__imp_GetStockObject
0x180078235  mov     rcx, [rbx]; hdc
0x180078238  mov     rdx, rax; h
0x18007823b  call    cs:__imp_SelectObject
0x180078241  mov     rdx, [rbx+98h]; lpString
0x180078248  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18007824c  mov     rbp, rax
0x18007824f  test    rdx, rdx
0x180078252  jz      short loc_180078263
0x180078254  mov     r8, rsi
0x180078257  inc     r8
0x18007825a  cmp     [rdx+r8*2], r15w
0x18007825f  jnz     short loc_180078257
0x180078261  jmp     short loc_180078266
0x180078263  mov     r8, r15; c
0x180078266  mov     rcx, [rbx]; hdc
0x180078269  lea     r9, [rsp+78h+sz]; lpsz
0x180078271  call    cs:__imp_GetTextExtentPointW
0x180078277  mov     r8d, [rsp+78h+sz.cy]
0x18007827f  mov     eax, 2AAAAAABh
0x180078284  imul    dword ptr [rbx+1Ch]
0x180078287  mov     ecx, [rbx+2Ch]
0x18007828a  lea     r15d, ds:1[r8*2]
0x180078292  sar     edx, 2
0x180078295  mov     eax, edx
0x180078297  shr     eax, 1Fh
0x18007829a  add     edx, eax
0x18007829c  add     r15d, edx
0x18007829f  add     ecx, r15d
0x1800782a2  cmp     ecx, [rbx+6Ch]
0x1800782a5  jle     short loc_1800782D5
0x1800782a7  mov     ecx, [rbx+0Ch]
0x1800782aa  add     ecx, r15d
0x1800782ad  cmp     ecx, [rbx+6Ch]
0x1800782b0  jg      loc_1800783A9
0x1800782b6  mov     edx, 1; int
0x1800782bb  mov     rcx, rbx; struct _PrintInfo *
0x1800782be  call    ?GetNextBand@@YAJPEAU_PrintInfo@@H@Z; GetNextBand(_PrintInfo *,int)
0x1800782c3  mov     edi, eax
0x1800782c5  test    eax, eax
0x1800782c7  jnz     loc_1800783A9
0x1800782cd  mov     r8d, [rsp+78h+sz.cy]
0x1800782d5  mov     eax, [rbx+30h]
0x1800782d8  mov     ecx, [rbx+2Ch]
0x1800782db  add     r15d, ecx
0x1800782de  mov     r10d, [rbx+28h]
0x1800782e2  mov     r14d, [rsp+78h+sz.cx]
0x1800782ea  mov     r9, [rbx+98h]; lpString
0x1800782f1  add     r14d, r10d
0x1800782f4  mov     [rsp+78h+x], eax
0x1800782fb  lea     edi, [rcx+r8]
0x1800782ff  mov     eax, 2AAAAAABh
0x180078304  mov     [rsp+78h+left], r10d
0x18007830c  imul    dword ptr [rbx+1Ch]
0x18007830f  sar     edx, 2
0x180078312  mov     eax, edx
0x180078314  shr     eax, 1Fh
0x180078317  add     eax, edx
0x180078319  add     eax, edi
0x18007831b  mov     [rsp+78h+bottom], eax
0x180078322  xor     eax, eax
0x180078324  test    r9, r9
0x180078327  jz      short loc_180078335
0x180078329  inc     rsi
0x18007832c  cmp     [r9+rsi*2], ax
0x180078331  jnz     short loc_180078329
0x180078333  jmp     short loc_180078338
0x180078335  mov     rsi, rax
0x180078338  mov     r8d, ecx; y
0x18007833b  mov     [rsp+78h+c], esi; c
0x18007833f  mov     rcx, [rbx]; hdc
0x180078342  mov     edx, r10d; x
0x180078345  call    cs:__imp_TextOutW
0x18007834b  mov     eax, [rsp+78h+bottom]
0x180078352  mov     r9d, r14d; right
0x180078355  mov     edx, [rsp+78h+left]; left
0x18007835c  mov     r8d, edi; top
0x18007835f  mov     rcx, [rbx]; hdc
0x180078362  mov     [rsp+78h+c], eax; bottom
0x180078366  call    cs:__imp_Rectangle
0x18007836c  mov     rcx, [rbx]; hdc
0x18007836f  xor     r9d, r9d; lppt
0x180078372  mov     r8d, edi; y
0x180078375  mov     edx, r14d; x
0x180078378  call    cs:__imp_MoveToEx
0x18007837e  mov     edx, [rsp+78h+x]; x
0x180078385  mov     r8d, edi; y
0x180078388  mov     rcx, [rbx]; hdc
0x18007838b  call    cs:__imp_LineTo
0x180078391  mov     edx, [rsp+78h+sz.cy]; int
0x180078398  lea     eax, [r15+1]
0x18007839c  mov     rcx, rbx; struct _PrintInfo *
0x18007839f  mov     [rbx+2Ch], eax
0x1800783a2  call    ?ScPrintBody@@YAJPEAU_PrintInfo@@H@Z; ScPrintBody(_PrintInfo *,int)
0x1800783a7  mov     edi, eax
0x1800783a9  test    r13, r13
0x1800783ac  jz      short loc_1800783BA
0x1800783ae  mov     rcx, [rbx]; hdc
0x1800783b1  mov     rdx, r13; h
0x1800783b4  call    cs:__imp_SelectObject
0x1800783ba  test    r12, r12
0x1800783bd  jz      short loc_1800783CB
0x1800783bf  mov     rcx, [rbx]; hdc
0x1800783c2  mov     rdx, r12; h
0x1800783c5  call    cs:__imp_SelectObject
0x1800783cb  test    rbp, rbp
0x1800783ce  jz      short loc_1800783DC
0x1800783d0  mov     rcx, [rbx]; hdc
0x1800783d3  mov     rdx, rbp; h
0x1800783d6  call    cs:__imp_SelectObject
0x1800783dc  mov     eax, edi
0x1800783de  add     rsp, 38h
0x1800783e2  pop     r15
0x1800783e4  pop     r14
0x1800783e6  pop     r13
0x1800783e8  pop     r12
0x1800783ea  pop     rdi
0x1800783eb  pop     rsi
0x1800783ec  pop     rbp
0x1800783ed  pop     rbx
0x1800783ee  retn
```
