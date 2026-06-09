# CZipWriteStream::_EnsureStream(void)

- ea: `0x18004666c`
- end: `0x1800467f4`
- name: `?_EnsureStream@CZipWriteStream@@AEAAJXZ`
- size: `392`
- prototype: `__int64 __fastcall(CZipWriteStream *__hidden this)`
- caller_count: `8`
- callee_count: `9`
- tags: ``

## callers

- `0x1800463b0`
- `0x1800463f0`
- `0x1800464b0`
- `0x1800464f0`
- `0x180046540`
- `0x180046580`
- `0x1800465d0`
- `0x180046620`

## callees

- `0x18000f530`
- `0x180010c30`
- `0x18001f080`
- `0x1800248e0`
- `0x180027a40`
- `0x180036f50`
- `0x180037958`
- `0x18004666c`
- `0x180071010`

## import_xrefs

- `SHELL32!SHBindToObject` at `0x180046796`
- `SHELL32!SHBindToObject` at `0x180046796`
- `SHELL32!__imp_SHILCreateFromPath` at `0x180046772`
- `SHELL32!__imp_SHILCreateFromPath` at `0x180046772`
- `SHELL32!__imp_ILFree` at `0x1800467b4`
- `SHELL32!__imp_ILFree` at `0x1800467b4`
- `ole32!CreateBindCtx` at `0x18004670d`
- `ole32!CreateBindCtx` at `0x18004670d`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall CZipWriteStream::_EnsureStream(CZipWriteStream *this)
{
  HRESULT v1; // ebx
  void **ppv; // r14
  CTempFileNameArray *v4; // rcx
  unsigned int v5; // r9d
  const WCHAR *v6; // rsi
  unsigned int v7; // r10d
  int v8; // edi
  CTempFileNameArray *v9; // rcx
  LPBC ppbc; // [rsp+30h] [rbp-D0h] BYREF
  LPITEMIDLIST ppidl; // [rsp+38h] [rbp-C8h] BYREF
  int v13; // [rsp+40h] [rbp-C0h]
  int v14; // [rsp+44h] [rbp-BCh]
  unsigned __int16 v15[264]; // [rsp+50h] [rbp-B0h] BYREF

  v1 = 0;
  ppv = (void **)((char *)this + 1056);
  if ( !*((_QWORD *)this + 132) )
  {
    memset_0(v15, 0, 0x208u);
    CTempFileNameArray::GetTempLocation(v4, (const unsigned __int16 *)this + 268, v15, v5);
    v6 = (const WCHAR *)((char *)this + 1064);
    StringCchCopyW((unsigned __int16 *)this + 532, 0x104u, v15);
    StringCchCatW((unsigned __int16 *)this + 532, v7, (const unsigned __int16 *)this + 8);
    v8 = *((_DWORD *)this + 3);
    ppbc = 0;
    v1 = CreateBindCtx(0, &ppbc);
    if ( v1 >= 0 )
    {
      ppidl = (LPITEMIDLIST)16;
      v13 = v8 | 0x1000;
      v14 = 0;
      v1 = ((__int64 (__fastcall *)(LPBC, LPITEMIDLIST *))ppbc->lpVtbl->SetBindOptions)(ppbc, &ppidl);
      if ( v1 >= 0 )
      {
        ppidl = 0;
        v1 = SHILCreateFromPath(v6, &ppidl, 0);
        if ( v1 >= 0 )
        {
          v1 = SHBindToObject(0, ppidl, ppbc, &GUID_0000000c_0000_0000_c000_000000000046, ppv);
          if ( v1 >= 0 )
            CTempFileNameArray::ReferenceTempFile(v9, v15, v6);
          ILFree(ppidl);
        }
        ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
      }
      else
      {
        SafeRelease<INewMenuClient>(&ppbc);
      }
    }
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18004666c  mov     [rsp-8+arg_8], rbx
0x180046671  mov     [rsp-8+arg_10], rsi
0x180046676  push    rbp
0x180046677  push    rdi
0x180046678  push    r14
0x18004667a  lea     rbp, [rsp-170h]
0x180046682  sub     rsp, 270h
0x180046689  mov     rax, cs:__security_cookie
0x180046690  xor     rax, rsp
0x180046693  mov     [rbp+180h+var_20], rax
0x18004669a  xor     ebx, ebx
0x18004669c  lea     r14, [rcx+420h]
0x1800466a3  mov     rdi, rcx
0x1800466a6  cmp     [r14], rbx
0x1800466a9  jnz     loc_1800467CB
0x1800466af  xor     edx, edx; Val
0x1800466b1  lea     rcx, [rsp+280h+var_230]; void *
0x1800466b6  mov     r8d, 208h; Size
0x1800466bc  call    memset_0
0x1800466c1  lea     rdx, [rdi+218h]; unsigned __int16 *
0x1800466c8  lea     r8, [rsp+280h+var_230]; unsigned __int16 *
0x1800466cd  call    ?GetTempLocation@CTempFileNameArray@@QEAAJPEBGPEAGI@Z; CTempFileNameArray::GetTempLocation(ushort const *,ushort *,uint)
0x1800466d2  mov     r10d, 104h
0x1800466d8  lea     rsi, [rdi+428h]
0x1800466df  mov     edx, r10d; unsigned __int64
0x1800466e2  lea     r8, [rsp+280h+var_230]; unsigned __int16 *
0x1800466e7  mov     rcx, rsi; unsigned __int16 *
0x1800466ea  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800466ef  lea     r8, [rdi+10h]; unsigned __int16 *
0x1800466f3  mov     edx, r10d; unsigned __int64
0x1800466f6  mov     rcx, rsi; unsigned __int16 *
0x1800466f9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800466fe  mov     edi, [rdi+0Ch]
0x180046701  lea     rdx, [rsp+280h+ppbc]; ppbc
0x180046706  xor     ecx, ecx; reserved
0x180046708  mov     [rsp+280h+ppbc], rbx
0x18004670d  call    cs:__imp_CreateBindCtx
0x180046713  mov     ebx, eax
0x180046715  test    eax, eax
0x180046717  js      loc_1800467CB
0x18004671d  mov     rcx, [rsp+280h+ppbc]
0x180046722  lea     rdx, [rsp+280h+ppidl]
0x180046727  mov     [rsp+280h+ppidl], 10h
0x180046730  bts     edi, 0Ch
0x180046734  mov     [rsp+280h+var_240], edi
0x180046738  mov     [rsp+280h+var_23C], 0
0x180046740  mov     rax, [rcx]
0x180046743  mov     rax, [rax+30h]
0x180046747  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004674c  mov     ebx, eax
0x18004674e  test    eax, eax
0x180046750  jns     short loc_18004675E
0x180046752  lea     rcx, [rsp+280h+ppbc]
0x180046757  call    ??$SafeRelease@UINewMenuClient@@@@YAXPEAPEAUINewMenuClient@@@Z; SafeRelease<INewMenuClient>(INewMenuClient * *)
0x18004675c  jmp     short loc_1800467CB
0x18004675e  xor     r8d, r8d; rgfInOut
0x180046761  mov     [rsp+280h+ppidl], 0
0x18004676a  lea     rdx, [rsp+280h+ppidl]; ppidl
0x18004676f  mov     rcx, rsi; pszPath
0x180046772  call    cs:__imp_SHILCreateFromPath
0x180046778  mov     ebx, eax
0x18004677a  test    eax, eax
0x18004677c  js      short loc_1800467BA
0x18004677e  mov     r8, [rsp+280h+ppbc]; pbc
0x180046783  lea     r9, _GUID_0000000c_0000_0000_c000_000000000046; riid
0x18004678a  mov     rdx, [rsp+280h+ppidl]; pidl
0x18004678f  xor     ecx, ecx; psf
0x180046791  mov     [rsp+280h+ppv], r14; ppv
0x180046796  call    cs:__imp_SHBindToObject
0x18004679c  mov     ebx, eax
0x18004679e  test    eax, eax
0x1800467a0  js      short loc_1800467AF
0x1800467a2  mov     r8, rsi; unsigned __int16 *
0x1800467a5  lea     rdx, [rsp+280h+var_230]; unsigned __int16 *
0x1800467aa  call    ?ReferenceTempFile@CTempFileNameArray@@QEAAXPEBG0@Z; CTempFileNameArray::ReferenceTempFile(ushort const *,ushort const *)
0x1800467af  mov     rcx, [rsp+280h+ppidl]; pidl
0x1800467b4  call    cs:__imp_ILFree
0x1800467ba  mov     rcx, [rsp+280h+ppbc]
0x1800467bf  mov     rax, [rcx]
0x1800467c2  mov     rax, [rax+10h]
0x1800467c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800467cb  mov     eax, ebx
0x1800467cd  mov     rcx, [rbp+180h+var_20]
0x1800467d4  xor     rcx, rsp; StackCookie
0x1800467d7  call    __security_check_cookie
0x1800467dc  lea     r11, [rsp+280h+var_10]
0x1800467e4  mov     rbx, [r11+28h]
0x1800467e8  mov     rsi, [r11+30h]
0x1800467ec  mov     rsp, r11
0x1800467ef  pop     r14
0x1800467f1  pop     rdi
0x1800467f2  pop     rbp
0x1800467f3  retn
```
