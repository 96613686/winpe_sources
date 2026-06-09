# _GetURLData(IDataObject *,int,ushort *,uint,ushort *,uint)

- ea: `0x1800090d8`
- end: `0x18000932a`
- name: `?_GetURLData@@YAJPEAUIDataObject@@HPEAGI1I@Z`
- size: `594`
- prototype: `int(struct IDataObject *, int, unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x180008810`
- `0x180008a50`

## callees

- `0x180003950`
- `0x1800090d8`
- `0x18001cd88`
- `0x180027718`
- `0x180029280`
- `0x18002a010`

## import_xrefs

- `IEFRAME!__imp_SHRestricted2W` at `0x1800092ee`
- `IEFRAME!__imp_SHRestricted2W` at `0x1800092ee`
- `KERNEL32!GlobalLock` at `0x1800091b1`
- `KERNEL32!GlobalLock` at `0x180009237`
- `KERNEL32!GlobalLock` at `0x1800091b1`
- `KERNEL32!GlobalLock` at `0x180009237`
- `KERNEL32!GlobalUnlock` at `0x180009270`
- `KERNEL32!GlobalUnlock` at `0x1800092c2`
- `KERNEL32!GlobalUnlock` at `0x180009270`
- `KERNEL32!GlobalUnlock` at `0x1800092c2`
- `USER32!RegisterClipboardFormatW` at `0x180009164`
- `USER32!RegisterClipboardFormatW` at `0x180009205`
- `USER32!RegisterClipboardFormatW` at `0x180009164`
- `USER32!RegisterClipboardFormatW` at `0x180009205`
- `SHLWAPI!PathIsURLW` at `0x18000928c`
- `SHLWAPI!PathIsURLW` at `0x18000928c`
- `ole32!ReleaseStgMedium` at `0x18000927b`
- `ole32!ReleaseStgMedium` at `0x1800092cd`
- `ole32!ReleaseStgMedium` at `0x18000927b`
- `ole32!ReleaseStgMedium` at `0x1800092cd`

## string_xrefs

- `0x1800091fe`: `FileGroupDescriptorW`

## pseudocode

```c
__int64 __fastcall _GetURLData(struct IDataObject *a1, int a2, unsigned __int16 *a3, __int64 a4, unsigned __int16 *a5)
{
  struct IDataObjectVtbl *lpVtbl; // rax
  HRESULT (__stdcall *GetData)(IDataObject *, FORMATETC *, STGMEDIUM *); // rax
  int v11; // ebx
  const unsigned __int16 *v12; // rax
  const unsigned __int16 *v13; // rdi
  const unsigned __int16 *v14; // rax
  size_t v15; // rdx
  __int128 v16; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v17; // [rsp+30h] [rbp-D0h]
  STGMEDIUM v18; // [rsp+40h] [rbp-C0h] BYREF
  STGMEDIUM hMem; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR pszPath[264]; // [rsp+70h] [rbp-90h] BYREF

  hMem.pUnkForRelease = 0;
  *a5 = 0;
  *a3 = 0;
  *(_OWORD *)&hMem.tymed = 0;
  v16 = 0;
  v17 = 0;
  if ( a2 == 2 )
  {
    LOWORD(v16) = RegisterClipboardFormatW(L"UniformResourceLocator");
  }
  else
  {
    if ( a2 != 3 )
      return 2147549183LL;
    LOWORD(v16) = 1;
  }
  lpVtbl = a1->lpVtbl;
  *((_QWORD *)&v16 + 1) = 0;
  *(_QWORD *)&v17 = 0xFFFFFFFF00000001uLL;
  GetData = lpVtbl->GetData;
  DWORD2(v17) = 1;
  v11 = ((__int64 (__fastcall *)(struct IDataObject *, __int128 *, STGMEDIUM *))GetData)(a1, &v16, &hMem);
  if ( v11 >= 0 )
  {
    v12 = (const unsigned __int16 *)GlobalLock(hMem.hBitmap);
    v13 = v12;
    if ( v12 )
    {
      if ( a2 == 2 )
      {
        memset(&v18, 0, sizeof(v18));
        StringCchCopyW(a3, 0x824u, v12);
        StringCchCopyW(a5, 0x104u, v13);
        LOWORD(v16) = RegisterClipboardFormatW(L"FileGroupDescriptorW");
        if ( ((int (__fastcall *)(struct IDataObject *, __int128 *, STGMEDIUM *))a1->lpVtbl->GetData)(a1, &v16, &v18) >= 0 )
        {
          v14 = (const unsigned __int16 *)GlobalLock(v18.hBitmap);
          if ( v14 )
          {
            StringCchCopyW(pszPath, 0x104u, v14 + 38);
            PathCchRemoveExtension(pszPath, v15);
            StringCchCopyW(a5, 0x104u, pszPath);
            GlobalUnlock(v18.hBitmap);
          }
          ReleaseStgMedium(&v18);
        }
      }
      else if ( a2 == 3 )
      {
        if ( PathIsURLW(v12) )
        {
          StringCchCopyW(a3, 0x824u, v13);
          StringCchCopyW(a5, 0x104u, v13);
        }
        else
        {
          v11 = -2147467259;
        }
      }
      GlobalUnlock(hMem.hBitmap);
    }
    ReleaseStgMedium(&hMem);
    if ( v11 >= 0 && (!(unsigned int)IsHTTPPrefixed(a3) || (unsigned int)SHRestricted2W(1342177285, a3, 0)) )
      return (unsigned int)-2147467259;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800090d8  mov     [rsp-8+arg_8], rbx
0x1800090dd  mov     [rsp-8+arg_18], rsi
0x1800090e2  push    rbp
0x1800090e3  push    rdi
0x1800090e4  push    r12
0x1800090e6  push    r14
0x1800090e8  push    r15
0x1800090ea  lea     rbp, [rsp-190h]
0x1800090f2  sub     rsp, 290h
0x1800090f9  mov     rax, cs:__security_cookie
0x180009100  xor     rax, rsp
0x180009103  mov     [rbp+1B0h+var_30], rax
0x18000910a  mov     r15, [rbp+1B0h+arg_20]
0x180009111  xor     eax, eax
0x180009113  mov     r12, rcx
0x180009116  mov     [rsp+2B0h+var_248], rax
0x18000911b  xorps   xmm1, xmm1
0x18000911e  mov     ecx, edx
0x180009120  xorps   xmm0, xmm0
0x180009123  mov     rsi, r8
0x180009126  mov     [r15], ax
0x18000912a  mov     r14d, edx
0x18000912d  mov     [r8], ax
0x180009131  lea     ebx, [rax+1]
0x180009134  movups  xmmword ptr [rsp+2B0h+hMem], xmm0
0x180009139  movups  [rsp+2B0h+var_290], xmm1
0x18000913e  movups  [rsp+2B0h+var_280], xmm1
0x180009143  sub     ecx, 2
0x180009146  jz      short loc_18000915D
0x180009148  cmp     ecx, ebx
0x18000914a  jz      short loc_180009156
0x18000914c  mov     eax, 8000FFFFh
0x180009151  jmp     loc_1800092FF
0x180009156  mov     word ptr [rsp+2B0h+var_290], bx
0x18000915b  jmp     short loc_18000916F
0x18000915d  lea     rcx, aUniformresourc; "UniformResourceLocator"
0x180009164  call    cs:__imp_RegisterClipboardFormatW
0x18000916a  mov     word ptr [rsp+2B0h+var_290], ax
0x18000916f  mov     rax, [r12]
0x180009173  lea     r8, [rsp+2B0h+hMem]
0x180009178  lea     rdx, [rsp+2B0h+var_290]
0x18000917d  mov     qword ptr [rsp+2B0h+var_290+8], 0
0x180009186  mov     rcx, r12
0x180009189  mov     dword ptr [rsp+2B0h+var_280], ebx
0x18000918d  mov     dword ptr [rsp+2B0h+var_280+4], 0FFFFFFFFh
0x180009195  mov     rax, [rax+18h]
0x180009199  mov     dword ptr [rsp+2B0h+var_280+8], ebx
0x18000919d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091a2  mov     ebx, eax
0x1800091a4  test    eax, eax
0x1800091a6  js      loc_1800092FD
0x1800091ac  mov     rcx, [rsp+2B0h+hMem+8]; hMem
0x1800091b1  call    cs:__imp_GlobalLock
0x1800091b7  mov     rdi, rax
0x1800091ba  test    rax, rax
0x1800091bd  jz      loc_1800092C8
0x1800091c3  cmp     r14d, 2
0x1800091c7  jnz     loc_180009283
0x1800091cd  xor     eax, eax
0x1800091cf  xorps   xmm0, xmm0
0x1800091d2  mov     r8, rdi; unsigned __int16 *
0x1800091d5  mov     [rsp+2B0h+var_260], rax
0x1800091da  mov     edx, 824h; unsigned __int64
0x1800091df  mov     rcx, rsi; unsigned __int16 *
0x1800091e2  movups  xmmword ptr [rsp+2B0h+var_270], xmm0
0x1800091e7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800091ec  mov     r8, rdi; unsigned __int16 *
0x1800091ef  mov     rcx, r15; unsigned __int16 *
0x1800091f2  mov     edi, 104h
0x1800091f7  mov     edx, edi; unsigned __int64
0x1800091f9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800091fe  lea     rcx, aFilegroupdescr; "FileGroupDescriptorW"
0x180009205  call    cs:__imp_RegisterClipboardFormatW
0x18000920b  mov     word ptr [rsp+2B0h+var_290], ax
0x180009210  lea     r8, [rsp+2B0h+var_270]
0x180009215  mov     rax, [r12]
0x180009219  mov     rcx, r12
0x18000921c  lea     rdx, [rsp+2B0h+var_290]
0x180009221  mov     rax, [rax+18h]
0x180009225  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000922a  test    eax, eax
0x18000922c  js      loc_1800092BD
0x180009232  mov     rcx, [rsp+2B0h+var_270+8]; hMem
0x180009237  call    cs:__imp_GlobalLock
0x18000923d  test    rax, rax
0x180009240  jz      short loc_180009276
0x180009242  lea     r8, [rax+4Ch]; unsigned __int16 *
0x180009246  mov     edx, edi; unsigned __int64
0x180009248  lea     rcx, [rsp+2B0h+pszPath]; unsigned __int16 *
0x18000924d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180009252  lea     rcx, [rsp+2B0h+pszPath]; pszPath
0x180009257  call    PathCchRemoveExtension
0x18000925c  lea     r8, [rsp+2B0h+pszPath]; unsigned __int16 *
0x180009261  mov     edx, edi; unsigned __int64
0x180009263  mov     rcx, r15; unsigned __int16 *
0x180009266  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000926b  mov     rcx, [rsp+2B0h+var_270+8]; hMem
0x180009270  call    cs:__imp_GlobalUnlock
0x180009276  lea     rcx, [rsp+2B0h+var_270]; LPSTGMEDIUM
0x18000927b  call    cs:__imp_ReleaseStgMedium
0x180009281  jmp     short loc_1800092BD
0x180009283  cmp     r14d, 3
0x180009287  jnz     short loc_1800092BD
0x180009289  mov     rcx, rdi; pszPath
0x18000928c  call    cs:__imp_PathIsURLW
0x180009292  test    eax, eax
0x180009294  jz      short loc_1800092B8
0x180009296  mov     r8, rdi; unsigned __int16 *
0x180009299  mov     edx, 824h; unsigned __int64
0x18000929e  mov     rcx, rsi; unsigned __int16 *
0x1800092a1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800092a6  mov     r8, rdi; unsigned __int16 *
0x1800092a9  mov     edx, 104h; unsigned __int64
0x1800092ae  mov     rcx, r15; unsigned __int16 *
0x1800092b1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800092b6  jmp     short loc_1800092BD
0x1800092b8  mov     ebx, 80004005h
0x1800092bd  mov     rcx, [rsp+2B0h+hMem+8]; hMem
0x1800092c2  call    cs:__imp_GlobalUnlock
0x1800092c8  lea     rcx, [rsp+2B0h+hMem]; LPSTGMEDIUM
0x1800092cd  call    cs:__imp_ReleaseStgMedium
0x1800092d3  test    ebx, ebx
0x1800092d5  js      short loc_1800092FD
0x1800092d7  mov     rcx, rsi
0x1800092da  call    IsHTTPPrefixed
0x1800092df  test    eax, eax
0x1800092e1  jz      short loc_1800092F8
0x1800092e3  xor     r8d, r8d
0x1800092e6  mov     rdx, rsi
0x1800092e9  mov     ecx, 50000005h
0x1800092ee  call    cs:__imp_SHRestricted2W
0x1800092f4  test    eax, eax
0x1800092f6  jz      short loc_1800092FD
0x1800092f8  mov     ebx, 80004005h
0x1800092fd  mov     eax, ebx
0x1800092ff  mov     rcx, [rbp+1B0h+var_30]
0x180009306  xor     rcx, rsp; StackCookie
0x180009309  call    __security_check_cookie
0x18000930e  lea     r11, [rsp+2B0h+var_20]
0x180009316  mov     rbx, [r11+38h]
0x18000931a  mov     rsi, [r11+48h]
0x18000931e  mov     rsp, r11
0x180009321  pop     r15
0x180009323  pop     r14
0x180009325  pop     r12
0x180009327  pop     rdi
0x180009328  pop     rbp
0x180009329  retn
```
