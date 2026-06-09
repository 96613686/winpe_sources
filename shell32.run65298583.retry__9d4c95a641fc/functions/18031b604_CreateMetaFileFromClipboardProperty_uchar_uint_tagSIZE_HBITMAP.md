# CreateMetaFileFromClipboardProperty(uchar *,uint,tagSIZE,HBITMAP__ * *)

- ea: `0x18031b604`
- end: `0x18031b88e`
- name: `?CreateMetaFileFromClipboardProperty@@YAJPEAEIUtagSIZE@@PEAPEAUHBITMAP__@@@Z`
- size: `650`
- prototype: `__int64 __fastcall(struct PACKEDMETA *, unsigned int, struct tagSIZE, HBITMAP *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18031b894`

## callees

- `0x180233280`
- `0x18031b1d8`
- `0x18031b604`

## import_xrefs

- `USER32!ReleaseDC` at `0x18031b866`
- `USER32!ReleaseDC` at `0x18031b866`
- `USER32!GetDC` at `0x18031b63f`
- `USER32!GetDC` at `0x18031b63f`
- `GDI32!GetStockObject` at `0x18031b726`
- `GDI32!GetStockObject` at `0x18031b740`
- `GDI32!GetStockObject` at `0x18031b726`
- `GDI32!GetStockObject` at `0x18031b740`
- `GDI32!DeleteObject` at `0x18031b852`
- `GDI32!DeleteObject` at `0x18031b852`
- `GDI32!CreateCompatibleDC` at `0x18031b64b`
- `GDI32!CreateCompatibleDC` at `0x18031b64b`
- `GDI32!SelectObject` at `0x18031b71a`
- `GDI32!SelectObject` at `0x18031b732`
- `GDI32!SelectObject` at `0x18031b74c`
- `GDI32!SelectObject` at `0x18031b774`
- `GDI32!SelectObject` at `0x18031b780`
- `GDI32!SelectObject` at `0x18031b83f`
- `GDI32!SelectObject` at `0x18031b71a`
- `GDI32!SelectObject` at `0x18031b732`
- `GDI32!SelectObject` at `0x18031b74c`
- `GDI32!SelectObject` at `0x18031b774`
- `GDI32!SelectObject` at `0x18031b780`
- `GDI32!SelectObject` at `0x18031b83f`
- `GDI32!DeleteDC` at `0x18031b85b`
- `GDI32!DeleteDC` at `0x18031b85b`
- `GDI32!SetMapMode` at `0x18031b66a`
- `GDI32!SetMapMode` at `0x18031b7e3`
- `GDI32!SetMapMode` at `0x18031b66a`
- `GDI32!SetMapMode` at `0x18031b7e3`
- `GDI32!SetViewportExtEx` at `0x18031b7bd`
- `GDI32!SetViewportExtEx` at `0x18031b7bd`
- `GDI32!SetMetaFileBitsEx` at `0x18031b680`
- `GDI32!SetMetaFileBitsEx` at `0x18031b680`
- `GDI32!Rectangle` at `0x18031b768`
- `GDI32!Rectangle` at `0x18031b768`
- `GDI32!SetViewportOrgEx` at `0x18031b7d5`
- `GDI32!SetViewportOrgEx` at `0x18031b7d5`
- `GDI32!PlayMetaFile` at `0x18031b7ef`
- `GDI32!PlayMetaFile` at `0x18031b7ef`
- `GDI32!DeleteMetaFile` at `0x18031b832`
- `GDI32!DeleteMetaFile` at `0x18031b832`
- `SHLWAPI!__imp_CalculateAspectRatio` at `0x18031b6b7`
- `SHLWAPI!__imp_CalculateAspectRatio` at `0x18031b6b7`
- `SHLWAPI!__imp_CreateSizedDIBSECTION` at `0x18031b705`
- `SHLWAPI!__imp_CreateSizedDIBSECTION` at `0x18031b705`

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
0x18031b604  push    rbp
0x18031b606  push    rbx
0x18031b607  push    rsi
0x18031b608  push    rdi
0x18031b609  push    r12
0x18031b60b  push    r13
0x18031b60d  push    r14
0x18031b60f  push    r15
0x18031b611  lea     rbp, [rsp-1Fh]
0x18031b616  sub     rsp, 88h
0x18031b61d  mov     rax, cs:__security_cookie
0x18031b624  xor     rax, rsp
0x18031b627  mov     [rbp+57h+var_48], rax
0x18031b62b  mov     r13, rcx
0x18031b62e  mov     [rbp+57h+var_80], r9
0x18031b632  xor     ecx, ecx; hWnd
0x18031b634  mov     qword ptr [rbp+57h+pszPath], r8
0x18031b638  mov     ebx, edx
0x18031b63a  mov     esi, 8007000Eh
0x18031b63f  call    cs:__imp_GetDC
0x18031b645  mov     rcx, rax; hdc
0x18031b648  mov     r12, rax
0x18031b64b  call    cs:__imp_CreateCompatibleDC
0x18031b651  xor     edi, edi
0x18031b653  mov     r14, rax
0x18031b656  test    rax, rax
0x18031b659  jz      loc_18031B861
0x18031b65f  lea     edx, [rdi+1]; iMode
0x18031b662  mov     rcx, rax; hdc
0x18031b665  mov     esi, 8004006Ah
0x18031b66a  call    cs:__imp_SetMapMode
0x18031b670  cmp     ebx, 9
0x18031b673  jbe     loc_18031B858
0x18031b679  lea     rdx, [r13+8]; lpData
0x18031b67d  lea     ecx, [rbx-8]; cbBuffer
0x18031b680  call    cs:__imp_SetMetaFileBitsEx
0x18031b686  mov     r15, rax
0x18031b689  test    rax, rax
0x18031b68c  jz      loc_18031B858
0x18031b692  xorps   xmm0, xmm0
0x18031b695  lea     r9, [rbp+57h+var_58]; struct tagRECT *
0x18031b699  lea     r8, [rbp+57h+pszPath]; struct tagSIZE *
0x18031b69d  mov     rdx, r13; struct PACKEDMETA *
0x18031b6a0  mov     rcx, r14; hdc
0x18031b6a3  movups  xmmword ptr [rbp+57h+var_58.left], xmm0
0x18031b6a7  call    ?CalcMetaFileSize@@YAXPEAUHDC__@@PEBUPACKEDMETA@@PEBUtagSIZE@@PEAUtagRECT@@@Z; CalcMetaFileSize(HDC__ *,PACKEDMETA const *,tagSIZE const *,tagRECT *)
0x18031b6ac  lea     r8, [rbp+57h+var_58]
0x18031b6b0  lea     edx, [rdi+1]
0x18031b6b3  lea     rcx, [rbp+57h+pszPath]; pszPath
0x18031b6b7  call    cs:__imp_CalculateAspectRatio
0x18031b6bd  mov     eax, [rbp+57h+var_58.bottom]
0x18031b6c0  lea     edx, [rdi+20h]; pszExt
0x18031b6c3  sub     eax, [rbp+57h+var_58.top]
0x18031b6c6  xor     r9d, r9d
0x18031b6c9  mov     ecx, [rbp+57h+var_58.right]
0x18031b6cc  xor     r8d, r8d
0x18031b6cf  sub     ecx, [rbp+57h+var_58.left]
0x18031b6d2  mov     dword ptr [rbp+57h+pszPath+4], eax
0x18031b6d5  mov     [rbp+57h+var_58.bottom], eax
0x18031b6d8  lea     rax, [rbp+57h+var_68]
0x18031b6dc  mov     [rsp+0C0h+var_90], rax
0x18031b6e1  lea     rax, [rbp+57h+h]
0x18031b6e5  mov     dword ptr [rbp+57h+pszPath], ecx
0x18031b6e8  mov     [rbp+57h+var_58.right], ecx
0x18031b6eb  lea     rcx, [rbp+57h+pszPath]; pszPath
0x18031b6ef  mov     [rsp+0C0h+var_98], rdi
0x18031b6f4  mov     qword ptr [rsp+0C0h+bottom], rax
0x18031b6f9  mov     qword ptr [rbp+57h+var_58.left], rdi
0x18031b6fd  mov     [rbp+57h+h], rdi
0x18031b701  mov     [rbp+57h+var_68], rdi
0x18031b705  call    cs:__imp_CreateSizedDIBSECTION
0x18031b70b  test    eax, eax
0x18031b70d  jz      loc_18031B858
0x18031b713  mov     rdx, [rbp+57h+h]; h
0x18031b717  mov     rcx, r14; hdc
0x18031b71a  call    cs:__imp_SelectObject
0x18031b720  xor     ecx, ecx; i
0x18031b722  mov     [rbp+57h+var_78], rax
0x18031b726  call    cs:__imp_GetStockObject
0x18031b72c  mov     rdx, rax; h
0x18031b72f  mov     rcx, r14; hdc
0x18031b732  call    cs:__imp_SelectObject
0x18031b738  mov     ecx, 6; i
0x18031b73d  mov     rdi, rax
0x18031b740  call    cs:__imp_GetStockObject
0x18031b746  mov     rdx, rax; h
0x18031b749  mov     rcx, r14; hdc
0x18031b74c  call    cs:__imp_SelectObject
0x18031b752  mov     r9d, dword ptr [rbp+57h+pszPath]; right
0x18031b756  xor     r8d, r8d; top
0x18031b759  mov     rbx, rax
0x18031b75c  xor     edx, edx; left
0x18031b75e  mov     eax, dword ptr [rbp+57h+pszPath+4]
0x18031b761  mov     rcx, r14; hdc
0x18031b764  mov     [rsp+0C0h+bottom], eax; bottom
0x18031b768  call    cs:__imp_Rectangle
0x18031b76e  mov     rdx, rdi; h
0x18031b771  mov     rcx, r14; hdc
0x18031b774  call    cs:__imp_SelectObject
0x18031b77a  mov     rdx, rbx; h
0x18031b77d  mov     rcx, r14; hdc
0x18031b780  call    cs:__imp_SelectObject
0x18031b786  mov     r9d, [rbp+57h+var_58.left]
0x18031b78a  xor     edi, edi
0x18031b78c  mov     ecx, [rbp+57h+var_58.top]
0x18031b78f  xor     ebx, ebx
0x18031b791  mov     r8d, [rbp+57h+var_58.bottom]
0x18031b795  test    r9d, r9d
0x18031b798  mov     edx, [rbp+57h+var_58.right]
0x18031b79b  lea     eax, [rdi+1]
0x18031b79e  cmovz   edi, eax
0x18031b7a1  test    ecx, ecx
0x18031b7a3  cmovz   ebx, eax
0x18031b7a6  lea     eax, [rbx+rbx]
0x18031b7a9  sub     r8d, eax
0x18031b7ac  lea     eax, [rdi+rdi]
0x18031b7af  sub     edx, eax
0x18031b7b1  sub     r8d, ecx; y
0x18031b7b4  sub     edx, r9d; x
0x18031b7b7  mov     rcx, r14; hdc
0x18031b7ba  xor     r9d, r9d; lpsz
0x18031b7bd  call    cs:__imp_SetViewportExtEx
0x18031b7c3  mov     r8d, [rbp+57h+var_58.top]
0x18031b7c7  xor     r9d, r9d; lppt
0x18031b7ca  mov     edx, [rbp+57h+var_58.left]
0x18031b7cd  add     r8d, ebx; y
0x18031b7d0  add     edx, edi; x
0x18031b7d2  mov     rcx, r14; hdc
0x18031b7d5  call    cs:__imp_SetViewportOrgEx
0x18031b7db  movzx   edx, word ptr [r13+0]; iMode
0x18031b7e0  mov     rcx, r14; hdc
0x18031b7e3  call    cs:__imp_SetMapMode
0x18031b7e9  mov     rdx, r15; hmf
0x18031b7ec  mov     rcx, r14; hdc
0x18031b7ef  call    cs:__imp_PlayMetaFile
0x18031b7f5  test    eax, eax
0x18031b7f7  jz      short loc_18031B82F
0x18031b7f9  mov     ecx, dword ptr [rbp+57h+pszPath+4]
0x18031b7fc  mov     r8, [rbp+57h+var_68]
0x18031b800  neg     ecx
0x18031b802  cmovs   ecx, dword ptr [rbp+57h+pszPath+4]
0x18031b806  xor     edx, edx
0x18031b808  imul    ecx, dword ptr [rbp+57h+pszPath]
0x18031b80c  test    ecx, ecx
0x18031b80e  jz      short loc_18031B81C
0x18031b810  mov     byte ptr [r8+rdx*4+3], 0FFh
0x18031b816  inc     edx
0x18031b818  cmp     edx, ecx
0x18031b81a  jb      short loc_18031B810
0x18031b81c  mov     rax, [rbp+57h+var_80]
0x18031b820  mov     rcx, [rbp+57h+h]
0x18031b824  mov     [rax], rcx
0x18031b827  xor     eax, eax
0x18031b829  test    rcx, rcx
0x18031b82c  cmovnz  esi, eax
0x18031b82f  mov     rcx, r15; hmf
0x18031b832  call    cs:__imp_DeleteMetaFile
0x18031b838  mov     rdx, [rbp+57h+var_78]; h
0x18031b83c  mov     rcx, r14; hdc
0x18031b83f  call    cs:__imp_SelectObject
0x18031b845  test    esi, esi
0x18031b847  jns     short loc_18031B858
0x18031b849  mov     rcx, [rbp+57h+h]; ho
0x18031b84d  test    rcx, rcx
0x18031b850  jz      short loc_18031B858
0x18031b852  call    cs:__imp_DeleteObject
0x18031b858  mov     rcx, r14; hdc
0x18031b85b  call    cs:__imp_DeleteDC
0x18031b861  mov     rdx, r12; hDC
0x18031b864  xor     ecx, ecx; hWnd
0x18031b866  call    cs:__imp_ReleaseDC
0x18031b86c  mov     eax, esi
0x18031b86e  mov     rcx, [rbp+57h+var_48]
0x18031b872  xor     rcx, rsp; StackCookie
0x18031b875  call    __security_check_cookie
0x18031b87a  add     rsp, 88h
0x18031b881  pop     r15
0x18031b883  pop     r14
0x18031b885  pop     r13
0x18031b887  pop     r12
0x18031b889  pop     rdi
0x18031b88a  pop     rsi
0x18031b88b  pop     rbx
0x18031b88c  pop     rbp
0x18031b88d  retn
```
