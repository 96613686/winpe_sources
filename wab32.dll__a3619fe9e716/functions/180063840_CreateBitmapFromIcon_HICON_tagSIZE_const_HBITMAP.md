# CreateBitmapFromIcon(HICON__ *,tagSIZE const *,HBITMAP__ * *)

- ea: `0x180063840`
- end: `0x180063a33`
- name: `?CreateBitmapFromIcon@@YAJPEAUHICON__@@PEBUtagSIZE@@PEAPEAUHBITMAP__@@@Z`
- size: `499`
- prototype: `__int64 __fastcall(HICON hicon, const struct tagSIZE *, HBITMAP *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18003c690`

## callees

- `0x180063840`
- `0x18006b26c`
- `0x18008f158`
- `0x18008f1c8`
- `0x18008f230`
- `0x18008f304`
- `0x180091eaa`
- `0x180091ef0`
- `0x180093010`

## import_xrefs

- `GDI32!DeleteObject` at `0x180063a04`
- `GDI32!DeleteObject` at `0x180063a04`
- `GDI32!CreateCompatibleDC` at `0x180063897`
- `GDI32!CreateCompatibleDC` at `0x180063897`
- `GDI32!SetBkColor` at `0x1800638d5`
- `GDI32!SetBkColor` at `0x1800638d5`
- `GDI32!ExtTextOutW` at `0x1800638ff`
- `GDI32!ExtTextOutW` at `0x1800638ff`
- `GDI32!DeleteDC` at `0x1800639f5`
- `GDI32!DeleteDC` at `0x1800639f5`
- `GDI32!SelectObject` at `0x1800638b0`
- `GDI32!SelectObject` at `0x1800639e6`
- `GDI32!SelectObject` at `0x1800638b0`
- `GDI32!SelectObject` at `0x1800639e6`

## pseudocode

```c
__int64 __fastcall CreateBitmapFromIcon(HICON hicon, const struct tagSIZE *a2, HBITMAP *a3)
{
  int v6; // ebx
  HDC CompatibleDC; // rax
  HDC v8; // rdi
  HGDIOBJ v9; // rax
  HRESULT v10; // r12d
  struct _IMAGELIST *v11; // rax
  struct _IMAGELIST *v12; // r14
  int v13; // ebx
  void *v14; // rcx
  void *ppv; // [rsp+40h] [rbp-79h] BYREF
  HGDIOBJ h; // [rsp+48h] [rbp-71h] BYREF
  HGDIOBJ v18; // [rsp+50h] [rbp-69h]
  __int64 v19; // [rsp+60h] [rbp-59h] BYREF
  _BYTE v20[8]; // [rsp+68h] [rbp-51h] BYREF
  int v21; // [rsp+70h] [rbp-49h]
  HDC v22; // [rsp+78h] [rbp-41h]
  LONG cx; // [rsp+88h] [rbp-31h]
  LONG cy; // [rsp+8Ch] [rbp-2Dh]
  int v25; // [rsp+98h] [rbp-21h]
  int v26; // [rsp+9Ch] [rbp-1Dh]
  int v27; // [rsp+A0h] [rbp-19h]
  RECT rect; // [rsp+C0h] [rbp+7h] BYREF

  *a3 = 0;
  h = 0;
  v6 = Create32BitHBITMAP(hicon, a2, a3, &h);
  if ( v6 >= 0 )
  {
    v6 = -2147467259;
    CompatibleDC = CreateCompatibleDC(0);
    v8 = CompatibleDC;
    if ( CompatibleDC )
    {
      v9 = SelectObject(CompatibleDC, h);
      rect.right = a2->cx;
      rect.bottom = a2->cy;
      v18 = v9;
      *(_QWORD *)&rect.left = 0;
      ppv = 0;
      SetBkColor(v8, 0xFFFFFFFF);
      ExtTextOutW(v8, 0, 0, 2u, &rect, 0, 0, 0);
      v10 = -2147024882;
      v11 = ImageList_Create(a2->cx, a2->cy, 0x21u, 1, 1);
      v12 = v11;
      if ( v11 )
      {
        v13 = ImageList_ReplaceIcon(v11, -1, hicon);
        if ( v13 != -1 )
          v10 = HIMAGELIST_QueryInterface(v12, &GUID_192b9d83_50fc_457b_90a0_2b82a8b5dae1, &ppv);
        ImageList_Destroy(v12);
      }
      else
      {
        v13 = 0;
      }
      if ( v10 >= 0 )
      {
        v19 = 88;
        memset_0(v20, 0, 0x50u);
        cx = a2->cx;
        cy = a2->cy;
        v25 = -16777216;
        v26 = -16777216;
        v21 = v13 & 0xFFFFFF;
        v22 = v8;
        v27 = 8193;
        (*(void (__fastcall **)(void *, __int64 *))(*(_QWORD *)ppv + 64LL))(ppv, &v19);
      }
      v14 = ppv;
      if ( ppv )
      {
        ppv = 0;
        (*(void (__fastcall **)(void *))(*(_QWORD *)v14 + 16LL))(v14);
      }
      *a3 = (HBITMAP)SelectObject(v8, v18);
      v6 = 0;
      DeleteDC(v8);
    }
    if ( !*a3 )
      DeleteObject(h);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180063840  mov     [rsp-8+arg_18], rbx
0x180063845  push    rbp
0x180063846  push    rsi
0x180063847  push    rdi
0x180063848  push    r12
0x18006384a  push    r13
0x18006384c  push    r14
0x18006384e  push    r15
0x180063850  lea     rbp, [rsp-27h]
0x180063855  sub     rsp, 0E0h
0x18006385c  mov     rax, cs:__security_cookie
0x180063863  xor     rax, rsp
0x180063866  mov     [rbp+57h+var_40], rax
0x18006386a  xor     r14d, r14d
0x18006386d  lea     r9, [rbp+57h+h]
0x180063871  mov     [r8], r14
0x180063874  mov     rsi, r8
0x180063877  mov     [rbp+57h+h], r14
0x18006387b  mov     r15, rdx
0x18006387e  mov     r13, rcx
0x180063881  call    _Create32BitHBITMAP
0x180063886  mov     ebx, eax
0x180063888  test    eax, eax
0x18006388a  js      loc_180063A0A
0x180063890  xor     ecx, ecx; hdc
0x180063892  mov     ebx, 80004005h
0x180063897  call    cs:__imp_CreateCompatibleDC
0x18006389d  mov     rdi, rax
0x1800638a0  test    rax, rax
0x1800638a3  jz      loc_1800639FB
0x1800638a9  mov     rdx, [rbp+57h+h]; h
0x1800638ad  mov     rcx, rax; hdc
0x1800638b0  call    cs:__imp_SelectObject
0x1800638b6  mov     ecx, [r15]
0x1800638b9  or      edx, 0FFFFFFFFh; color
0x1800638bc  mov     [rbp+57h+rect.right], ecx
0x1800638bf  mov     ecx, [r15+4]
0x1800638c3  mov     [rbp+57h+rect.bottom], ecx
0x1800638c6  mov     rcx, rdi; hdc
0x1800638c9  mov     [rbp+57h+var_C0], rax
0x1800638cd  mov     qword ptr [rbp+57h+rect.left], r14
0x1800638d1  mov     [rbp+57h+ppv], r14
0x1800638d5  call    cs:__imp_SetBkColor
0x1800638db  mov     [rsp+110h+lpDx], r14; lpDx
0x1800638e0  lea     rax, [rbp+57h+rect]
0x1800638e4  mov     [rsp+110h+c], r14d; c
0x1800638e9  lea     r9d, [r14+2]; options
0x1800638ed  mov     [rsp+110h+lpString], r14; lpString
0x1800638f2  xor     r8d, r8d; y
0x1800638f5  xor     edx, edx; x
0x1800638f7  mov     [rsp+110h+lprect], rax; lprect
0x1800638fc  mov     rcx, rdi; hdc
0x1800638ff  call    cs:__imp_ExtTextOutW
0x180063905  mov     edx, [r15+4]; cy
0x180063909  lea     r9d, [r14+1]; cInitial
0x18006390d  mov     ecx, [r15]; cx
0x180063910  lea     r8d, [r14+21h]; flags
0x180063914  mov     dword ptr [rsp+110h+lprect], r9d; cGrow
0x180063919  mov     r12d, 8007000Eh
0x18006391f  call    ImageList_Create
0x180063924  mov     r14, rax
0x180063927  test    rax, rax
0x18006392a  jz      short loc_180063964
0x18006392c  mov     r8, r13; hicon
0x18006392f  or      edx, 0FFFFFFFFh; i
0x180063932  mov     rcx, rax; himl
0x180063935  call    ImageList_ReplaceIcon
0x18006393a  mov     ebx, eax
0x18006393c  cmp     eax, 0FFFFFFFFh
0x18006393f  jz      short loc_180063957
0x180063941  lea     r8, [rbp+57h+ppv]; ppv
0x180063945  mov     rcx, r14; himl
0x180063948  lea     rdx, _GUID_192b9d83_50fc_457b_90a0_2b82a8b5dae1; riid
0x18006394f  call    HIMAGELIST_QueryInterface
0x180063954  mov     r12d, eax
0x180063957  mov     rcx, r14; himl
0x18006395a  call    ImageList_Destroy
0x18006395f  xor     r14d, r14d
0x180063962  jmp     short loc_18006396A
0x180063964  xor     r14d, r14d
0x180063967  mov     ebx, r14d
0x18006396a  test    r12d, r12d
0x18006396d  js      short loc_1800639C6
0x18006396f  xor     edx, edx; Val
0x180063971  mov     [rbp+57h+var_B0], 58h ; 'X'
0x180063979  lea     rcx, [rbp+57h+var_A8]; void *
0x18006397d  lea     r8d, [rdx+50h]; Size
0x180063981  call    memset_0
0x180063986  mov     eax, [r15]
0x180063989  lea     rdx, [rbp+57h+var_B0]
0x18006398d  mov     rcx, [rbp+57h+ppv]
0x180063991  and     ebx, 0FFFFFFh
0x180063997  mov     [rbp+57h+var_88], eax
0x18006399a  mov     eax, [r15+4]
0x18006399e  mov     [rbp+57h+var_84], eax
0x1800639a1  mov     eax, 0FF000000h
0x1800639a6  mov     [rbp+57h+var_78], eax
0x1800639a9  mov     [rbp+57h+var_74], eax
0x1800639ac  mov     [rbp+57h+var_A0], ebx
0x1800639af  mov     [rbp+57h+var_98], rdi
0x1800639b3  mov     [rbp+57h+var_70], 2001h
0x1800639ba  mov     rax, [rcx]
0x1800639bd  mov     rax, [rax+40h]
0x1800639c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800639c6  mov     rcx, [rbp+57h+ppv]
0x1800639ca  test    rcx, rcx
0x1800639cd  jz      short loc_1800639DF
0x1800639cf  mov     [rbp+57h+ppv], r14
0x1800639d3  mov     rax, [rcx]
0x1800639d6  mov     rax, [rax+10h]
0x1800639da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800639df  mov     rdx, [rbp+57h+var_C0]; h
0x1800639e3  mov     rcx, rdi; hdc
0x1800639e6  call    cs:__imp_SelectObject
0x1800639ec  mov     rcx, rdi; hdc
0x1800639ef  mov     [rsi], rax
0x1800639f2  mov     ebx, r14d
0x1800639f5  call    cs:__imp_DeleteDC
0x1800639fb  cmp     [rsi], r14
0x1800639fe  jnz     short loc_180063A0A
0x180063a00  mov     rcx, [rbp+57h+h]; ho
0x180063a04  call    cs:__imp_DeleteObject
0x180063a0a  mov     eax, ebx
0x180063a0c  mov     rcx, [rbp+57h+var_40]
0x180063a10  xor     rcx, rsp; StackCookie
0x180063a13  call    __security_check_cookie
0x180063a18  mov     rbx, [rsp+110h+arg_18]
0x180063a20  add     rsp, 0E0h
0x180063a27  pop     r15
0x180063a29  pop     r14
0x180063a2b  pop     r13
0x180063a2d  pop     r12
0x180063a2f  pop     rdi
0x180063a30  pop     rsi
0x180063a31  pop     rbp
0x180063a32  retn
```
