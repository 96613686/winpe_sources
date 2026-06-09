# CWallpaperCore::_LoadUserPath(int,_ITEMIDLIST_ABSOLUTE * *)

- ea: `0x180041f98`
- end: `0x18004214b`
- name: `?_LoadUserPath@CWallpaperCore@@CAJHPEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z`
- size: `435`
- prototype: `static int(int, struct _ITEMIDLIST_ABSOLUTE **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180041b10`

## callees

- `0x180002280`
- `0x180008110`
- `0x18003e978`
- `0x18003edb8`
- `0x180041f98`
- `0x180057010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x180041fd9`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x180041fd9`
- `SHELL32!__imp_ILLoadFromStreamEx` at `0x180042087`
- `SHELL32!__imp_ILLoadFromStreamEx` at `0x180042087`
- `SHLWAPI!SHDeleteValueW` at `0x1800420cb`
- `SHLWAPI!SHDeleteValueW` at `0x1800420cb`
- `SHLWAPI!__imp_SHCreateMemStream` at `0x180042052`
- `SHLWAPI!__imp_SHCreateMemStream` at `0x180042052`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800420a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800420a8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180042099`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180042099`

## pseudocode

```c
__int64 __fastcall CWallpaperCore::_LoadUserPath(__int64 a1, LPITEMIDLIST *a2)
{
  int v3; // r14d
  HRESULT v4; // ebx
  const unsigned __int16 *v5; // rdx
  HKEY v6; // rcx
  int v7; // r9d
  void *v8; // rsi
  IStream *v9; // rax
  __int64 v10; // rcx
  IStream *v11; // rdi
  unsigned int *v13; // [rsp+28h] [rbp-48h]
  LPVOID pv; // [rsp+30h] [rbp-40h] BYREF
  IStream *pstm[2]; // [rsp+38h] [rbp-38h] BYREF
  __int64 v16; // [rsp+48h] [rbp-28h]
  _BYTE v17[8]; // [rsp+50h] [rbp-20h] BYREF
  WCHAR pszValue[8]; // [rsp+58h] [rbp-18h] BYREF

  *a2 = 0;
  v3 = a1;
  v4 = -2147467259;
  if ( (unsigned int)_o__itow_s(a1, v17, 3) || (int)StringCchPrintfW(pszValue, 6u, L"ID%s", v17) < 0 )
    return (unsigned int)v4;
  pv = 0;
  v4 = SHRegAllocData(v6, v5, pszValue, v7, &pv, v13);
  if ( v4 >= 0 )
  {
    v8 = pv;
    v16 = 0;
    *(_OWORD *)pstm = 0;
    v4 = -2147024809;
    if ( *(_WORD *)pv )
    {
      v9 = SHCreateMemStream(0, 0x400u);
      v11 = v9;
      if ( v9 )
      {
        v4 = TextToBinary(v10, v8, v9);
        if ( v4 >= 0 )
          v4 = (**(__int64 (__fastcall ***)(IStream *, GUID *, IStream **))v11)(
                 v11,
                 &GUID_0000000c_0000_0000_c000_000000000046,
                 &pstm[1]);
        (*(void (__fastcall **)(IStream *))(*(_QWORD *)v11 + 16LL))(v11);
        if ( v4 >= 0 )
        {
          LOWORD(pstm[0]) = 66;
          v4 = ILLoadFromStreamEx(pstm[1], a2);
          PropVariantClear((PROPVARIANT *)pstm);
          goto LABEL_9;
        }
      }
      else
      {
        v4 = -2147024882;
      }
    }
    v16 = 0;
    *(_OWORD *)pstm = 0;
LABEL_9:
    CoTaskMemFree(v8);
  }
  if ( v3 < 0 )
    SHDeleteValueW(
      HKEY_CURRENT_USER,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Wallpapers\\Images",
      pszValue);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180041f98  mov     [rsp-28h+arg_10], rbx
0x180041f9d  push    rbp
0x180041f9e  push    rsi
0x180041f9f  push    rdi
0x180041fa0  push    r14
0x180041fa2  push    r15
0x180041fa4  mov     rbp, rsp
0x180041fa7  sub     rsp, 70h
0x180041fab  mov     rax, cs:__security_cookie
0x180041fb2  xor     rax, rsp
0x180041fb5  mov     [rbp+var_8], rax
0x180041fb9  mov     r9d, 0Ah
0x180041fbf  mov     qword ptr [rdx], 0
0x180041fc6  mov     r15, rdx
0x180041fc9  mov     r14d, ecx
0x180041fcc  lea     rdx, [rbp+var_20]
0x180041fd0  mov     ebx, 80004005h
0x180041fd5  lea     r8d, [r9-7]
0x180041fd9  call    cs:__imp__o__itow_s
0x180041fe0  nop     dword ptr [rax+rax+00h]
0x180041fe5  test    eax, eax
0x180041fe7  jnz     loc_1800420D7
0x180041fed  lea     r9, [rbp+var_20]
0x180041ff1  lea     r8, aIdS; "ID%s"
0x180041ff8  lea     edx, [rax+6]; unsigned __int64
0x180041ffb  lea     rcx, [rbp+pszValue]; unsigned __int16 *
0x180041fff  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180042004  test    eax, eax
0x180042006  js      loc_1800420D7
0x18004200c  lea     rax, [rbp+pv]
0x180042010  mov     [rbp+pv], 0
0x180042018  lea     r8, [rbp+pszValue]; unsigned __int16 *
0x18004201c  mov     [rsp+70h+var_50], rax; void **
0x180042021  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x180042026  mov     ebx, eax
0x180042028  test    eax, eax
0x18004202a  js      loc_1800420B4
0x180042030  mov     rsi, [rbp+pv]
0x180042034  xor     eax, eax
0x180042036  xorps   xmm0, xmm0
0x180042039  mov     [rbp+var_28], rax
0x18004203d  movups  xmmword ptr [rbp+pstm], xmm0
0x180042041  mov     ebx, 80070057h
0x180042046  cmp     ax, [rsi]
0x180042049  jz      short loc_18004206F
0x18004204b  mov     edx, 400h; cbInit
0x180042050  xor     ecx, ecx; pInit
0x180042052  call    cs:__imp_SHCreateMemStream
0x180042059  nop     dword ptr [rax+rax+00h]
0x18004205e  mov     rdi, rax
0x180042061  test    rax, rax
0x180042064  jnz     loc_1800420FA
0x18004206a  mov     ebx, 8007000Eh
0x18004206f  xor     eax, eax
0x180042071  xorps   xmm0, xmm0
0x180042074  mov     [rbp+var_28], rax
0x180042078  movups  xmmword ptr [rbp+pstm], xmm0
0x18004207c  test    ebx, ebx
0x18004207e  js      short loc_1800420A5
0x180042080  mov     rcx, [rbp+pstm+8]; pstm
0x180042084  mov     rdx, r15; pidl
0x180042087  call    cs:__imp_ILLoadFromStreamEx
0x18004208e  nop     dword ptr [rax+rax+00h]
0x180042093  lea     rcx, [rbp+pstm]; pvar
0x180042097  mov     ebx, eax
0x180042099  call    cs:__imp_PropVariantClear
0x1800420a0  nop     dword ptr [rax+rax+00h]
0x1800420a5  mov     rcx, rsi; pv
0x1800420a8  call    cs:__imp_CoTaskMemFree
0x1800420af  nop     dword ptr [rax+rax+00h]
0x1800420b4  test    r14d, r14d
0x1800420b7  jns     short loc_1800420D7
0x1800420b9  lea     r8, [rbp+pszValue]; pszValue
0x1800420bd  mov     rcx, 0FFFFFFFF80000001h; hkey
0x1800420c4  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800420cb  call    cs:__imp_SHDeleteValueW
0x1800420d2  nop     dword ptr [rax+rax+00h]
0x1800420d7  mov     eax, ebx
0x1800420d9  mov     rcx, [rbp+var_8]
0x1800420dd  xor     rcx, rsp; StackCookie
0x1800420e0  call    __security_check_cookie
0x1800420e5  mov     rbx, [rsp+70h+arg_10]
0x1800420ed  add     rsp, 70h
0x1800420f1  pop     r15
0x1800420f3  pop     r14
0x1800420f5  pop     rdi
0x1800420f6  pop     rsi
0x1800420f7  pop     rbp
0x1800420f8  retn
0x1800420fa  mov     r8, rdi
0x1800420fd  mov     rdx, rsi
0x180042100  call    ?TextToBinary@@YAJW4BINARY_TEXT_ENCODE_SCHEME@@PEBGPEAUIStream@@@Z; TextToBinary(BINARY_TEXT_ENCODE_SCHEME,ushort const *,IStream *)
0x180042105  mov     ebx, eax
0x180042107  test    eax, eax
0x180042109  js      short loc_180042126
0x18004210b  mov     rax, [rdi]
0x18004210e  lea     r8, [rbp+pstm+8]
0x180042112  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x180042119  mov     rcx, rdi
0x18004211c  mov     rax, [rax]
0x18004211f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042124  mov     ebx, eax
0x180042126  mov     rax, [rdi]
0x180042129  mov     rcx, rdi
0x18004212c  mov     rax, [rax+10h]
0x180042130  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042135  test    ebx, ebx
0x180042137  js      loc_18004206F
0x18004213d  mov     eax, 42h ; 'B'
0x180042142  mov     word ptr [rbp+pstm], ax
0x180042146  jmp     loc_180042080
```
