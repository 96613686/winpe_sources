# CCabDecompressor::DecompressInternal(DATA_TYPE,CSafeBuffer<uchar> *,wchar_t const *,DATA_TYPE,wchar_t const *)

- ea: `0x180015200`
- end: `0x1800152f0`
- name: `?DecompressInternal@CCabDecompressor@@AEAAJW4DATA_TYPE@@PEAV?$CSafeBuffer@E@@PEB_W02@Z`
- size: `240`
- prototype: `__int64 __usercall@<rax>(CCabDecompressor *this@<rcx>, int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180015dfc`

## callees

- `0x180003950`
- `0x180014eb0`
- `0x180015200`

## import_xrefs

- `Cabinet!__imp_FDICopy` at `0x180015267`
- `Cabinet!__imp_FDICopy` at `0x180015267`

## string_xrefs

- `0x1800152aa`: `C:\__w\1\s\src\Client\lib\CabDecompressor\CabDecompressor.cpp`
- `0x1800152cb`: `C:\__w\1\s\src\Client\lib\CabDecompressor\CabDecompressor.cpp`

## pseudocode

```c
__int64 __fastcall CCabDecompressor::DecompressInternal(
        CCabDecompressor *this,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6)
{
  CHAR *v7; // rdx
  BOOL v8; // eax
  int v9; // r8d
  int LastFDIErrorHr; // edi
  int v11; // ebx
  int pfnfdin; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *((_DWORD *)this + 35) = a5;
  *((_DWORD *)this + 34) = a2;
  if ( a2 )
    *((_QWORD *)this + 15) = a4;
  else
    *((_QWORD *)this + 7) = 0;
  v7 = (CHAR *)*((_QWORD *)this + 6);
  *((_QWORD *)this + 16) = a6;
  v8 = FDICopy(*((HFDI *)this + 5), v7, (LPSTR)&pszCabPath, 0, (PFNFDINOTIFY)CCabDecompressor::Notification, 0, this);
  v9 = -2147467260;
  if ( v8 )
  {
    LastFDIErrorHr = 0;
  }
  else
  {
    LastFDIErrorHr = CCabDecompressor::GetLastFDIErrorHr(this);
    if ( LastFDIErrorHr == v9 && *((_DWORD *)this + 42) == -2145124340 )
      return 0;
  }
  if ( LastFDIErrorHr == v9 )
  {
    v11 = *((_DWORD *)this + 42);
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1FE,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\CabDecompressor\\CabDecompressor.cpp",
        (const char *)(unsigned int)v11,
        pfnfdin);
      return (unsigned int)v11;
    }
    goto LABEL_12;
  }
  if ( LastFDIErrorHr < 0 )
  {
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1FF,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\CabDecompressor\\CabDecompressor.cpp",
      (const char *)(unsigned int)LastFDIErrorHr,
      pfnfdin);
    return (unsigned int)LastFDIErrorHr;
  }
  return 0;
}

```

## disassembly

```asm
0x180015200  mov     [rsp+arg_0], rbx
0x180015205  push    rdi
0x180015206  sub     rsp, 40h
0x18001520a  mov     eax, [rsp+48h+arg_20]
0x18001520e  mov     rbx, rcx
0x180015211  mov     [rcx+8Ch], eax
0x180015217  mov     [rcx+88h], edx
0x18001521d  test    edx, edx
0x18001521f  jnz     short loc_18001522B
0x180015221  mov     qword ptr [rcx+38h], 0
0x180015229  jmp     short loc_18001522F
0x18001522b  mov     [rcx+78h], r9
0x18001522f  mov     rax, [rsp+48h+arg_28]
0x180015234  lea     r8, pszCabPath; pszCabPath
0x18001523b  mov     rdx, [rcx+30h]; pszCabinet
0x18001523f  xor     r9d, r9d; flags
0x180015242  mov     [rcx+80h], rax
0x180015249  lea     rax, ?Notification@CCabDecompressor@@CA_JW4FDINOTIFICATIONTYPE@@PEAUFDINOTIFICATION@@@Z; CCabDecompressor::Notification(FDINOTIFICATIONTYPE,FDINOTIFICATION *)
0x180015250  mov     rcx, [rcx+28h]; hfdi
0x180015254  mov     [rsp+48h+pvUser], rbx; pvUser
0x180015259  mov     [rsp+48h+pfnfdid], 0; pfnfdid
0x180015262  mov     [rsp+48h+pfnfdin], rax; int
0x180015267  call    cs:__imp_FDICopy
0x18001526d  mov     r8d, 80004004h
0x180015273  test    eax, eax
0x180015275  jz      short loc_18001527B
0x180015277  xor     edi, edi
0x180015279  jmp     short loc_180015296
0x18001527b  mov     rcx, rbx; this
0x18001527e  call    ?GetLastFDIErrorHr@CCabDecompressor@@QEAAJXZ; CCabDecompressor::GetLastFDIErrorHr(void)
0x180015283  mov     edi, eax
0x180015285  cmp     eax, r8d
0x180015288  jnz     short loc_180015296
0x18001528a  cmp     dword ptr [rbx+0A8h], 8024000Ch
0x180015294  jz      short loc_1800152E3
0x180015296  cmp     edi, r8d
0x180015299  jnz     short loc_1800152C2
0x18001529b  mov     ebx, [rbx+0A8h]
0x1800152a1  test    ebx, ebx
0x1800152a3  jns     short loc_1800152C6
0x1800152a5  mov     rcx, [rsp+48h]; this
0x1800152aa  lea     r8, aCW1SSrcClientL_0; "C:\\__w\\1\\s\\src\\Client\\lib\\CabDec"...
0x1800152b1  mov     r9d, ebx; char *
0x1800152b4  mov     edx, 1FEh; void *
0x1800152b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800152be  mov     eax, ebx
0x1800152c0  jmp     short loc_1800152E5
0x1800152c2  test    edi, edi
0x1800152c4  jns     short loc_1800152E3
0x1800152c6  mov     rcx, [rsp+48h]; this
0x1800152cb  lea     r8, aCW1SSrcClientL_0; "C:\\__w\\1\\s\\src\\Client\\lib\\CabDec"...
0x1800152d2  mov     r9d, edi; char *
0x1800152d5  mov     edx, 1FFh; void *
0x1800152da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800152df  mov     eax, edi
0x1800152e1  jmp     short loc_1800152E5
0x1800152e3  xor     eax, eax
0x1800152e5  mov     rbx, [rsp+48h+arg_0]
0x1800152ea  add     rsp, 40h
0x1800152ee  pop     rdi
0x1800152ef  retn
```
