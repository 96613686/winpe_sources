# CreateMetaFileFromClipboardProperty(uchar *,uint,tagSIZE,HBITMAP__ * *)

- ea: `0x18033b34c`
- end: `0x18033b661`
- name: `?CreateMetaFileFromClipboardProperty@@YAJPEAEIUtagSIZE@@PEAPEAUHBITMAP__@@@Z`
- size: `789`
- prototype: `__int64 __fastcall(struct PACKEDMETA *, unsigned int, struct tagSIZE, HBITMAP *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18033b668`

## callees

- `0x180249490`
- `0x18033aecc`
- `0x18033b34c`

## import_xrefs

- `USER32!ReleaseDC` at `0x18033b632`
- `USER32!ReleaseDC` at `0x18033b632`
- `USER32!GetDC` at `0x18033b387`
- `USER32!GetDC` at `0x18033b387`
- `GDI32!GetStockObject` at `0x18033b498`
- `GDI32!GetStockObject` at `0x18033b4be`
- `GDI32!GetStockObject` at `0x18033b498`
- `GDI32!GetStockObject` at `0x18033b4be`
- `GDI32!DeleteObject` at `0x18033b612`
- `GDI32!DeleteObject` at `0x18033b612`
- `GDI32!CreateCompatibleDC` at `0x18033b399`
- `GDI32!CreateCompatibleDC` at `0x18033b399`
- `GDI32!SelectObject` at `0x18033b486`
- `GDI32!SelectObject` at `0x18033b4aa`
- `GDI32!SelectObject` at `0x18033b4d0`
- `GDI32!SelectObject` at `0x18033b504`
- `GDI32!SelectObject` at `0x18033b516`
- `GDI32!SelectObject` at `0x18033b5f9`
- `GDI32!SelectObject` at `0x18033b486`
- `GDI32!SelectObject` at `0x18033b4aa`
- `GDI32!SelectObject` at `0x18033b4d0`
- `GDI32!SelectObject` at `0x18033b504`
- `GDI32!SelectObject` at `0x18033b516`
- `GDI32!SelectObject` at `0x18033b5f9`
- `GDI32!DeleteDC` at `0x18033b621`
- `GDI32!DeleteDC` at `0x18033b621`
- `GDI32!SetMapMode` at `0x18033b3be`
- `GDI32!SetMapMode` at `0x18033b58b`
- `GDI32!SetMapMode` at `0x18033b3be`
- `GDI32!SetMapMode` at `0x18033b58b`
- `GDI32!SetViewportExtEx` at `0x18033b559`
- `GDI32!SetViewportExtEx` at `0x18033b559`
- `GDI32!SetMetaFileBitsEx` at `0x18033b3da`
- `GDI32!SetMetaFileBitsEx` at `0x18033b3da`
- `GDI32!Rectangle` at `0x18033b4f2`
- `GDI32!Rectangle` at `0x18033b4f2`
- `GDI32!SetViewportOrgEx` at `0x18033b577`
- `GDI32!SetViewportOrgEx` at `0x18033b577`
- `GDI32!PlayMetaFile` at `0x18033b59d`
- `GDI32!PlayMetaFile` at `0x18033b59d`
- `GDI32!DeleteMetaFile` at `0x18033b5e6`
- `GDI32!DeleteMetaFile` at `0x18033b5e6`
- `SHLWAPI!__imp_CalculateAspectRatio` at `0x18033b417`
- `SHLWAPI!__imp_CalculateAspectRatio` at `0x18033b417`
- `SHLWAPI!__imp_CreateSizedDIBSECTION` at `0x18033b46b`
- `SHLWAPI!__imp_CreateSizedDIBSECTION` at `0x18033b46b`

## pseudocode

```c
__int64 __fastcall CreateMetaFileFromClipboardProperty(const BYTE *a1, unsigned int a2, struct tagSIZE a3, HBITMAP *a4)
{
  unsigned int v6; // esi
  HDC DC; // r12
  HDC CompatibleDC; // rax
  HDC v9; // r14
  HMETAFILE v10; // r15
  HGDIOBJ StockObject; // rax
  HGDIOBJ v12; // rdi
  HGDIOBJ v13; // rax
  HGDIOBJ v14; // rbx
  int v15; // ecx
  __int64 v16; // rdx
  unsigned int v17; // ecx
  HGDIOBJ v20; // [rsp+48h] [rbp-21h]
  WCHAR pszPath[4]; // [rsp+60h] [rbp-9h] BYREF
  struct tagRECT v22; // [rsp+68h] [rbp-1h] BYREF

  *(struct tagSIZE *)pszPath = a3;
  v6 = -2147024882;
  DC = GetDC(0);
  CompatibleDC = CreateCompatibleDC(DC);
  v9 = CompatibleDC;
  if ( CompatibleDC )
  {
    v6 = -2147221398;
    SetMapMode(CompatibleDC, 1);
    if ( a2 > 9 )
    {
      v10 = SetMetaFileBitsEx(a2 - 8, a1 + 8);
      if ( v10 )
      {
        v22 = 0;
        CalcMetaFileSize(v9, (const struct PACKEDMETA *)a1, (const struct tagSIZE *)pszPath, &v22);
        CalculateAspectRatio(pszPath);
        *(_DWORD *)&pszPath[2] = v22.bottom - v22.top;
        v22.bottom -= v22.top;
        *(_DWORD *)pszPath = v22.right - v22.left;
        v22.right -= v22.left;
        *(_QWORD *)&v22.left = 0;
        if ( CreateSizedDIBSECTION(pszPath, (LPCWSTR)0x20) )
        {
          v20 = SelectObject(v9, 0);
          StockObject = GetStockObject(0);
          v12 = SelectObject(v9, StockObject);
          v13 = GetStockObject(6);
          v14 = SelectObject(v9, v13);
          Rectangle(v9, 0, 0, *(int *)pszPath, *(int *)&pszPath[2]);
          SelectObject(v9, v12);
          SelectObject(v9, v14);
          LODWORD(v12) = v22.left == 0;
          LODWORD(v14) = v22.top == 0;
          SetViewportExtEx(v9, v22.right - 2 * (_DWORD)v12 - v22.left, v22.bottom - 2 * (_DWORD)v14 - v22.top, 0);
          SetViewportOrgEx(v9, (_DWORD)v12 + v22.left, (_DWORD)v14 + v22.top, 0);
          SetMapMode(v9, *(unsigned __int16 *)a1);
          if ( PlayMetaFile(v9, v10) )
          {
            v15 = -*(_DWORD *)&pszPath[2];
            if ( *(int *)&pszPath[2] > 0 )
              v15 = *(_DWORD *)&pszPath[2];
            v16 = 0;
            v17 = *(_DWORD *)pszPath * v15;
            if ( v17 )
            {
              do
              {
                *(_BYTE *)(4 * v16 + 3) = -1;
                v16 = (unsigned int)(v16 + 1);
              }
              while ( (unsigned int)v16 < v17 );
            }
            *a4 = 0;
          }
          DeleteMetaFile(v10);
          SelectObject(v9, v20);
        }
      }
    }
    DeleteDC(v9);
  }
  ReleaseDC(0, DC);
  return v6;
}

```

## disassembly

```asm
0x18033b34c  push    rbp
0x18033b34e  push    rbx
0x18033b34f  push    rsi
0x18033b350  push    rdi
0x18033b351  push    r12
0x18033b353  push    r13
0x18033b355  push    r14
0x18033b357  push    r15
0x18033b359  lea     rbp, [rsp-1Fh]
0x18033b35e  sub     rsp, 88h
0x18033b365  mov     rax, cs:__security_cookie
0x18033b36c  xor     rax, rsp
0x18033b36f  mov     [rbp+57h+var_48], rax
0x18033b373  mov     r13, rcx
0x18033b376  mov     [rbp+57h+var_80], r9
0x18033b37a  xor     ecx, ecx; hWnd
0x18033b37c  mov     qword ptr [rbp+57h+pszPath], r8
0x18033b380  mov     ebx, edx
0x18033b382  mov     esi, 8007000Eh
0x18033b387  call    cs:__imp_GetDC
0x18033b38e  nop     dword ptr [rax+rax+00h]
0x18033b393  mov     rcx, rax; hdc
0x18033b396  mov     r12, rax
0x18033b399  call    cs:__imp_CreateCompatibleDC
0x18033b3a0  nop     dword ptr [rax+rax+00h]
0x18033b3a5  xor     edi, edi
0x18033b3a7  mov     r14, rax
0x18033b3aa  test    rax, rax
0x18033b3ad  jz      loc_18033B62D
0x18033b3b3  lea     edx, [rdi+1]; iMode
0x18033b3b6  mov     rcx, rax; hdc
0x18033b3b9  mov     esi, 8004006Ah
0x18033b3be  call    cs:__imp_SetMapMode
0x18033b3c5  nop     dword ptr [rax+rax+00h]
0x18033b3ca  cmp     ebx, 9
0x18033b3cd  jbe     loc_18033B61E
0x18033b3d3  lea     rdx, [r13+8]; lpData
0x18033b3d7  lea     ecx, [rbx-8]; cbBuffer
0x18033b3da  call    cs:__imp_SetMetaFileBitsEx
0x18033b3e1  nop     dword ptr [rax+rax+00h]
0x18033b3e6  mov     r15, rax
0x18033b3e9  test    rax, rax
0x18033b3ec  jz      loc_18033B61E
0x18033b3f2  xorps   xmm0, xmm0
0x18033b3f5  lea     r9, [rbp+57h+var_58]; struct tagRECT *
0x18033b3f9  lea     r8, [rbp+57h+pszPath]; struct tagSIZE *
0x18033b3fd  mov     rdx, r13; struct PACKEDMETA *
0x18033b400  mov     rcx, r14; hdc
0x18033b403  movups  xmmword ptr [rbp+57h+var_58.left], xmm0
0x18033b407  call    ?CalcMetaFileSize@@YAXPEAUHDC__@@PEBUPACKEDMETA@@PEBUtagSIZE@@PEAUtagRECT@@@Z; CalcMetaFileSize(HDC__ *,PACKEDMETA const *,tagSIZE const *,tagRECT *)
0x18033b40c  lea     r8, [rbp+57h+var_58]
0x18033b410  lea     edx, [rdi+1]
0x18033b413  lea     rcx, [rbp+57h+pszPath]; pszPath
0x18033b417  call    cs:__imp_CalculateAspectRatio
0x18033b41e  nop     dword ptr [rax+rax+00h]
0x18033b423  mov     eax, [rbp+57h+var_58.bottom]
0x18033b426  lea     edx, [rdi+20h]; pszExt
0x18033b429  sub     eax, [rbp+57h+var_58.top]
0x18033b42c  xor     r9d, r9d
0x18033b42f  mov     ecx, [rbp+57h+var_58.right]
0x18033b432  xor     r8d, r8d
0x18033b435  sub     ecx, [rbp+57h+var_58.left]
0x18033b438  mov     dword ptr [rbp+57h+pszPath+4], eax
0x18033b43b  mov     [rbp+57h+var_58.bottom], eax
0x18033b43e  lea     rax, [rbp+57h+var_68]
0x18033b442  mov     [rsp+0C0h+var_90], rax
0x18033b447  lea     rax, [rbp+57h+h]
0x18033b44b  mov     dword ptr [rbp+57h+pszPath], ecx
0x18033b44e  mov     [rbp+57h+var_58.right], ecx
0x18033b451  lea     rcx, [rbp+57h+pszPath]; pszPath
0x18033b455  mov     [rsp+0C0h+var_98], rdi
0x18033b45a  mov     qword ptr [rsp+0C0h+bottom], rax
0x18033b45f  mov     qword ptr [rbp+57h+var_58.left], rdi
0x18033b463  mov     [rbp+57h+h], rdi
0x18033b467  mov     [rbp+57h+var_68], rdi
0x18033b46b  call    cs:__imp_CreateSizedDIBSECTION
0x18033b472  nop     dword ptr [rax+rax+00h]
0x18033b477  test    eax, eax
0x18033b479  jz      loc_18033B61E
0x18033b47f  mov     rdx, [rbp+57h+h]; h
0x18033b483  mov     rcx, r14; hdc
0x18033b486  call    cs:__imp_SelectObject
0x18033b48d  nop     dword ptr [rax+rax+00h]
0x18033b492  xor     ecx, ecx; i
0x18033b494  mov     [rbp+57h+var_78], rax
0x18033b498  call    cs:__imp_GetStockObject
0x18033b49f  nop     dword ptr [rax+rax+00h]
0x18033b4a4  mov     rdx, rax; h
0x18033b4a7  mov     rcx, r14; hdc
0x18033b4aa  call    cs:__imp_SelectObject
0x18033b4b1  nop     dword ptr [rax+rax+00h]
0x18033b4b6  mov     ecx, 6; i
0x18033b4bb  mov     rdi, rax
0x18033b4be  call    cs:__imp_GetStockObject
0x18033b4c5  nop     dword ptr [rax+rax+00h]
0x18033b4ca  mov     rdx, rax; h
0x18033b4cd  mov     rcx, r14; hdc
0x18033b4d0  call    cs:__imp_SelectObject
0x18033b4d7  nop     dword ptr [rax+rax+00h]
0x18033b4dc  mov     r9d, dword ptr [rbp+57h+pszPath]; right
0x18033b4e0  xor     r8d, r8d; top
0x18033b4e3  mov     rbx, rax
0x18033b4e6  xor     edx, edx; left
0x18033b4e8  mov     eax, dword ptr [rbp+57h+pszPath+4]
0x18033b4eb  mov     rcx, r14; hdc
0x18033b4ee  mov     [rsp+0C0h+bottom], eax; bottom
0x18033b4f2  call    cs:__imp_Rectangle
0x18033b4f9  nop     dword ptr [rax+rax+00h]
0x18033b4fe  mov     rdx, rdi; h
0x18033b501  mov     rcx, r14; hdc
0x18033b504  call    cs:__imp_SelectObject
0x18033b50b  nop     dword ptr [rax+rax+00h]
0x18033b510  mov     rdx, rbx; h
0x18033b513  mov     rcx, r14; hdc
0x18033b516  call    cs:__imp_SelectObject
0x18033b51d  nop     dword ptr [rax+rax+00h]
0x18033b522  mov     r9d, [rbp+57h+var_58.left]
0x18033b526  xor     edi, edi
0x18033b528  mov     ecx, [rbp+57h+var_58.top]
0x18033b52b  xor     ebx, ebx
0x18033b52d  mov     r8d, [rbp+57h+var_58.bottom]
0x18033b531  test    r9d, r9d
0x18033b534  mov     edx, [rbp+57h+var_58.right]
0x18033b537  lea     eax, [rdi+1]
0x18033b53a  cmovz   edi, eax
0x18033b53d  test    ecx, ecx
0x18033b53f  cmovz   ebx, eax
0x18033b542  lea     eax, [rbx+rbx]
0x18033b545  sub     r8d, eax
0x18033b548  lea     eax, [rdi+rdi]
0x18033b54b  sub     edx, eax
0x18033b54d  sub     r8d, ecx; y
0x18033b550  sub     edx, r9d; x
0x18033b553  mov     rcx, r14; hdc
0x18033b556  xor     r9d, r9d; lpsz
0x18033b559  call    cs:__imp_SetViewportExtEx
0x18033b560  nop     dword ptr [rax+rax+00h]
0x18033b565  mov     r8d, [rbp+57h+var_58.top]
0x18033b569  xor     r9d, r9d; lppt
0x18033b56c  mov     edx, [rbp+57h+var_58.left]
0x18033b56f  add     r8d, ebx; y
0x18033b572  add     edx, edi; x
0x18033b574  mov     rcx, r14; hdc
0x18033b577  call    cs:__imp_SetViewportOrgEx
0x18033b57e  nop     dword ptr [rax+rax+00h]
0x18033b583  movzx   edx, word ptr [r13+0]; iMode
0x18033b588  mov     rcx, r14; hdc
0x18033b58b  call    cs:__imp_SetMapMode
0x18033b592  nop     dword ptr [rax+rax+00h]
0x18033b597  mov     rdx, r15; hmf
0x18033b59a  mov     rcx, r14; hdc
0x18033b59d  call    cs:__imp_PlayMetaFile
0x18033b5a4  nop     dword ptr [rax+rax+00h]
0x18033b5a9  test    eax, eax
0x18033b5ab  jz      short loc_18033B5E3
0x18033b5ad  mov     ecx, dword ptr [rbp+57h+pszPath+4]
0x18033b5b0  mov     r8, [rbp+57h+var_68]
0x18033b5b4  neg     ecx
0x18033b5b6  cmovs   ecx, dword ptr [rbp+57h+pszPath+4]
0x18033b5ba  xor     edx, edx
0x18033b5bc  imul    ecx, dword ptr [rbp+57h+pszPath]
0x18033b5c0  test    ecx, ecx
0x18033b5c2  jz      short loc_18033B5D0
0x18033b5c4  mov     byte ptr [r8+rdx*4+3], 0FFh
0x18033b5ca  inc     edx
0x18033b5cc  cmp     edx, ecx
0x18033b5ce  jb      short loc_18033B5C4
0x18033b5d0  mov     rax, [rbp+57h+var_80]
0x18033b5d4  mov     rcx, [rbp+57h+h]
0x18033b5d8  mov     [rax], rcx
0x18033b5db  xor     eax, eax
0x18033b5dd  test    rcx, rcx
0x18033b5e0  cmovnz  esi, eax
0x18033b5e3  mov     rcx, r15; hmf
0x18033b5e6  call    cs:__imp_DeleteMetaFile
0x18033b5ed  nop     dword ptr [rax+rax+00h]
0x18033b5f2  mov     rdx, [rbp+57h+var_78]; h
0x18033b5f6  mov     rcx, r14; hdc
0x18033b5f9  call    cs:__imp_SelectObject
0x18033b600  nop     dword ptr [rax+rax+00h]
0x18033b605  test    esi, esi
0x18033b607  jns     short loc_18033B61E
0x18033b609  mov     rcx, [rbp+57h+h]; ho
0x18033b60d  test    rcx, rcx
0x18033b610  jz      short loc_18033B61E
0x18033b612  call    cs:__imp_DeleteObject
0x18033b619  nop     dword ptr [rax+rax+00h]
0x18033b61e  mov     rcx, r14; hdc
0x18033b621  call    cs:__imp_DeleteDC
0x18033b628  nop     dword ptr [rax+rax+00h]
0x18033b62d  mov     rdx, r12; hDC
0x18033b630  xor     ecx, ecx; hWnd
0x18033b632  call    cs:__imp_ReleaseDC
0x18033b639  nop     dword ptr [rax+rax+00h]
0x18033b63e  mov     eax, esi
0x18033b640  mov     rcx, [rbp+57h+var_48]
0x18033b644  xor     rcx, rsp; StackCookie
0x18033b647  call    __security_check_cookie
0x18033b64c  add     rsp, 88h
0x18033b653  pop     r15
0x18033b655  pop     r14
0x18033b657  pop     r13
0x18033b659  pop     r12
0x18033b65b  pop     rdi
0x18033b65c  pop     rsi
0x18033b65d  pop     rbx
0x18033b65e  pop     rbp
0x18033b65f  retn
```
