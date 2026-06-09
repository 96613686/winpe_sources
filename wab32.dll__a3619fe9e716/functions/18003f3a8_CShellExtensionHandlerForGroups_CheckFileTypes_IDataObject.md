# CShellExtensionHandlerForGroups::_CheckFileTypes(IDataObject *)

- ea: `0x18003f3a8`
- end: `0x18003f52a`
- name: `?_CheckFileTypes@CShellExtensionHandlerForGroups@@AEAAHPEAUIDataObject@@@Z`
- size: `386`
- prototype: `__int64 __fastcall(CShellExtensionHandlerForGroups *__hidden this, struct IDataObject *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18003dfd0`

## callees

- `0x180002818`
- `0x18003f3a8`
- `0x180091eaa`
- `0x180091ef0`
- `0x180093010`

## import_xrefs

- `SHLWAPI!PathFindExtensionW` at `0x18003f4a0`
- `SHLWAPI!PathFindExtensionW` at `0x18003f4a0`
- `SHLWAPI!StrCmpIW` at `0x18003f4b3`
- `SHLWAPI!StrCmpIW` at `0x18003f4c7`
- `SHLWAPI!StrCmpIW` at `0x18003f4b3`
- `SHLWAPI!StrCmpIW` at `0x18003f4c7`
- `SHELL32!DragQueryFileW` at `0x18003f475`
- `SHELL32!DragQueryFileW` at `0x18003f495`
- `SHELL32!DragQueryFileW` at `0x18003f475`
- `SHELL32!DragQueryFileW` at `0x18003f495`
- `KERNEL32!GlobalFree` at `0x18003f503`
- `KERNEL32!GlobalFree` at `0x18003f503`
- `KERNEL32!GlobalUnlock` at `0x18003f4df`
- `KERNEL32!GlobalUnlock` at `0x18003f4df`
- `KERNEL32!GlobalLock` at `0x18003f445`
- `KERNEL32!GlobalLock` at `0x18003f445`

## pseudocode

```c
__int64 __fastcall CShellExtensionHandlerForGroups::_CheckFileTypes(
        CShellExtensionHandlerForGroups *this,
        struct IDataObject *a2)
{
  unsigned int v2; // esi
  HDROP v3; // rdi
  UINT FileW; // r15d
  UINT i; // ebx
  const WCHAR *ExtensionW; // r14
  HGLOBAL hMem[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v9; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v10; // [rsp+38h] [rbp-C8h] BYREF
  int v11; // [rsp+3Ah] [rbp-C6h]
  __int16 v12; // [rsp+3Eh] [rbp-C2h]
  __int64 v13; // [rsp+40h] [rbp-C0h]
  int v14; // [rsp+48h] [rbp-B8h]
  int v15; // [rsp+4Ch] [rbp-B4h]
  __int64 v16; // [rsp+50h] [rbp-B0h]
  WCHAR szFile[264]; // [rsp+60h] [rbp-A0h] BYREF

  v14 = 1;
  v10 = 15;
  v2 = 0;
  v15 = -1;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v16 = 1;
  v9 = 0;
  *(_OWORD *)hMem = 0;
  if ( a2 && ((int (__fastcall *)(struct IDataObject *, __int16 *, HGLOBAL *))a2->lpVtbl->GetData)(a2, &v10, hMem) >= 0 )
  {
    v3 = (HDROP)GlobalLock(hMem[1]);
    if ( v3 )
    {
      memset_0(szFile, 0, 0x208u);
      FileW = DragQueryFileW(v3, 0xFFFFFFFF, 0, 0);
      for ( i = 0; i < FileW; ++i )
      {
        DragQueryFileW(v3, i, szFile, 0x104u);
        ExtensionW = PathFindExtensionW(szFile);
        if ( !StrCmpIW(L".contact", ExtensionW) || !StrCmpIW(L".group", ExtensionW) )
        {
          v2 = 1;
          break;
        }
      }
    }
    GlobalUnlock(hMem[1]);
    if ( v9 )
    {
      OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v9);
    }
    else if ( hMem[1] )
    {
      GlobalFree(hMem[1]);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18003f3a8  push    rbp
0x18003f3aa  push    rbx
0x18003f3ab  push    rsi
0x18003f3ac  push    rdi
0x18003f3ad  push    r14
0x18003f3af  push    r15
0x18003f3b1  lea     rbp, [rsp-188h]
0x18003f3b9  sub     rsp, 288h
0x18003f3c0  mov     rax, cs:__security_cookie
0x18003f3c7  xor     rax, rsp
0x18003f3ca  mov     [rbp+1B0h+var_40], rax
0x18003f3d1  mov     eax, 0Fh
0x18003f3d6  mov     [rsp+2B0h+var_268], 1
0x18003f3de  mov     [rsp+2B0h+var_278], ax
0x18003f3e3  xor     esi, esi
0x18003f3e5  xor     eax, eax
0x18003f3e7  mov     [rsp+2B0h+var_264], 0FFFFFFFFh
0x18003f3ef  mov     [rsp+2B0h+var_276], eax
0x18003f3f3  xorps   xmm0, xmm0
0x18003f3f6  mov     [rsp+2B0h+var_272], ax
0x18003f3fb  mov     r9, rdx
0x18003f3fe  mov     [rsp+2B0h+var_270], rax
0x18003f403  mov     [rsp+2B0h+var_260], 1
0x18003f40c  mov     [rsp+2B0h+var_280], rax
0x18003f411  movups  xmmword ptr [rsp+2B0h+hMem], xmm0
0x18003f416  test    rdx, rdx
0x18003f419  jz      loc_18003F509
0x18003f41f  mov     rax, [rdx]
0x18003f422  lea     r8, [rsp+2B0h+hMem]
0x18003f427  lea     rdx, [rsp+2B0h+var_278]
0x18003f42c  mov     rcx, r9
0x18003f42f  mov     rax, [rax+18h]
0x18003f433  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f438  test    eax, eax
0x18003f43a  js      loc_18003F509
0x18003f440  mov     rcx, [rsp+2B0h+hMem+8]; hMem
0x18003f445  call    cs:__imp_GlobalLock
0x18003f44b  mov     rdi, rax
0x18003f44e  test    rax, rax
0x18003f451  jz      loc_18003F4DA
0x18003f457  xor     edx, edx; Val
0x18003f459  lea     rcx, [rsp+2B0h+szFile]; void *
0x18003f45e  mov     r8d, 208h; Size
0x18003f464  call    memset_0
0x18003f469  xor     r9d, r9d; cch
0x18003f46c  xor     r8d, r8d; lpszFile
0x18003f46f  or      edx, 0FFFFFFFFh; iFile
0x18003f472  mov     rcx, rdi; hDrop
0x18003f475  call    cs:__imp_DragQueryFileW
0x18003f47b  mov     r15d, eax
0x18003f47e  xor     ebx, ebx
0x18003f480  cmp     ebx, r15d
0x18003f483  jnb     short loc_18003F4DA
0x18003f485  mov     r9d, 104h; cch
0x18003f48b  lea     r8, [rsp+2B0h+szFile]; lpszFile
0x18003f490  mov     edx, ebx; iFile
0x18003f492  mov     rcx, rdi; hDrop
0x18003f495  call    cs:__imp_DragQueryFileW
0x18003f49b  lea     rcx, [rsp+2B0h+szFile]; pszPath
0x18003f4a0  call    cs:__imp_PathFindExtensionW
0x18003f4a6  mov     rdx, rax; psz2
0x18003f4a9  lea     rcx, aContact_1; ".contact"
0x18003f4b0  mov     r14, rax
0x18003f4b3  call    cs:__imp_StrCmpIW
0x18003f4b9  test    eax, eax
0x18003f4bb  jz      short loc_18003F4D5
0x18003f4bd  mov     rdx, r14; psz2
0x18003f4c0  lea     rcx, aGroup_0; ".group"
0x18003f4c7  call    cs:__imp_StrCmpIW
0x18003f4cd  test    eax, eax
0x18003f4cf  jz      short loc_18003F4D5
0x18003f4d1  inc     ebx
0x18003f4d3  jmp     short loc_18003F480
0x18003f4d5  mov     esi, 1
0x18003f4da  mov     rcx, [rsp+2B0h+hMem+8]; hMem
0x18003f4df  call    cs:__imp_GlobalUnlock
0x18003f4e5  cmp     [rsp+2B0h+var_280], 0
0x18003f4eb  jz      short loc_18003F4F9
0x18003f4ed  lea     rcx, [rsp+2B0h+var_280]
0x18003f4f2  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18003f4f7  jmp     short loc_18003F509
0x18003f4f9  mov     rcx, [rsp+2B0h+hMem+8]; hMem
0x18003f4fe  test    rcx, rcx
0x18003f501  jz      short loc_18003F509
0x18003f503  call    cs:__imp_GlobalFree
0x18003f509  mov     eax, esi
0x18003f50b  mov     rcx, [rbp+1B0h+var_40]
0x18003f512  xor     rcx, rsp; StackCookie
0x18003f515  call    __security_check_cookie
0x18003f51a  add     rsp, 288h
0x18003f521  pop     r15
0x18003f523  pop     r14
0x18003f525  pop     rdi
0x18003f526  pop     rsi
0x18003f527  pop     rbx
0x18003f528  pop     rbp
0x18003f529  retn
```
