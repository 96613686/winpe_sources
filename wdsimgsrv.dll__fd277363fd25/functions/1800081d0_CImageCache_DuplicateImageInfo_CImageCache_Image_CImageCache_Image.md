# CImageCache::DuplicateImageInfo(CImageCache::Image *,CImageCache::Image * *)

- ea: `0x1800081d0`
- end: `0x18000835e`
- name: `?DuplicateImageInfo@CImageCache@@SAKPEAUImage@1@PEAPEAU21@@Z`
- size: `398`
- prototype: `unsigned int __fastcall(struct Image *, struct Image **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000891c`

## callees

- `0x1800015d8`
- `0x180002878`
- `0x1800081d0`
- `0x18000ad88`
- `0x18000aeac`

## import_xrefs

- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x180008313`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x180008313`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x180008240`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x180008275`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x1800082a7`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x180008240`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x180008275`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x1800082a7`
- `WdsImage!WdsImgAddReference` at `0x1800082f2`
- `WdsImage!WdsImgAddReference` at `0x1800082f2`

## string_xrefs

- `0x180008252`: `base\eco\wds\wdssrv\wdsimgsrv\src\imagecache.cpp`
- `0x180008287`: `base\eco\wds\wdssrv\wdsimgsrv\src\imagecache.cpp`
- `0x1800082b9`: `base\eco\wds\wdssrv\wdsimgsrv\src\imagecache.cpp`

## pseudocode

```c
__int64 __fastcall CImageCache::DuplicateImageInfo(const unsigned __int16 **a1, unsigned __int16 ***a2)
{
  unsigned __int16 **v4; // rax
  unsigned __int16 **v5; // rbx
  __int64 v6; // rdi
  CImageCache::Image *v7; // rbp
  __int64 v8; // rdx
  unsigned int v9; // edx
  __int64 v10; // rdx
  __int64 v11; // rdx
  unsigned int v12; // ebp
  __int64 v13; // rdx
  __int64 v14; // r8

  v4 = (unsigned __int16 **)operator new(0x48u, (const struct std::nothrow_t *)&std::nothrow);
  v5 = v4;
  if ( !v4 )
  {
    LODWORD(v6) = 8;
    return (unsigned int)v6;
  }
  *v4 = 0;
  v4[2] = 0;
  v4[3] = 0;
  *((_DWORD *)v4 + 8) = 0;
  *((_DWORD *)v4 + 9) = 0;
  *((_DWORD *)v4 + 10) = 0;
  v4[1] = 0;
  *((_DWORD *)v4 + 11) = 0;
  *((_OWORD *)v4 + 3) = 0;
  *((_DWORD *)v4 + 16) = 0;
  LODWORD(v6) = DuplicateStringW(*a1, v4);
  v7 = (CImageCache::Image *)v5;
  if ( !(unsigned int)ElValidateWin32_0(
                        (unsigned int)v6,
                        v8,
                        "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp",
                        1276) )
  {
    LODWORD(v6) = DuplicateStringW(a1[2], v5 + 2);
    if ( !(unsigned int)ElValidateWin32_0(
                          (unsigned int)v6,
                          v10,
                          "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp",
                          1279) )
    {
      v6 = DuplicateStringW(a1[3], v5 + 3);
      if ( !(unsigned int)ElValidateWin32_0(v6, v11, "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp", 1284) )
      {
        *((_DWORD *)v5 + 9) = *((_DWORD *)a1 + 9);
        *((_DWORD *)v5 + 8) = *((_DWORD *)a1 + 8);
        *((_DWORD *)v5 + 16) = *((_DWORD *)a1 + 16);
        *((_DWORD *)v5 + 11) = *((_DWORD *)a1 + 11);
        *((_OWORD *)v5 + 3) = *((_OWORD *)a1 + 3);
        v12 = WdsImgAddReference(a1[1]);
        if ( (int)ElValidateHr_0(v12, v13, v14, 1294) >= 0 )
        {
          v5[1] = (unsigned __int16 *)a1[1];
          *a2 = v5;
          return (unsigned int)v6;
        }
        LODWORD(v6) = WIN32_FROM_HRESULT(v12);
        v7 = (CImageCache::Image *)v5;
      }
    }
  }
  CImageCache::Image::`scalar deleting destructor'(v7, v9);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800081d0  mov     rax, rsp
0x1800081d3  mov     [rax+8], rbx
0x1800081d7  mov     [rax+10h], rbp
0x1800081db  mov     [rax+18h], rsi
0x1800081df  mov     [rax+20h], rdi
0x1800081e3  push    r14
0x1800081e5  sub     rsp, 20h
0x1800081e9  mov     r14, rdx
0x1800081ec  mov     rsi, rcx
0x1800081ef  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800081f6  mov     ecx, 48h ; 'H'; unsigned __int64
0x1800081fb  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180008200  mov     rbx, rax
0x180008203  test    rax, rax
0x180008206  jz      loc_18000833B
0x18000820c  and     qword ptr [rax], 0
0x180008210  xorps   xmm0, xmm0
0x180008213  and     qword ptr [rax+10h], 0
0x180008218  mov     rdx, rax
0x18000821b  and     qword ptr [rax+18h], 0
0x180008220  and     dword ptr [rax+20h], 0
0x180008224  and     dword ptr [rax+24h], 0
0x180008228  and     dword ptr [rax+28h], 0
0x18000822c  and     qword ptr [rax+8], 0
0x180008231  and     dword ptr [rax+2Ch], 0
0x180008235  movups  xmmword ptr [rax+30h], xmm0
0x180008239  and     dword ptr [rax+40h], 0
0x18000823d  mov     rcx, [rsi]
0x180008240  call    cs:__imp_?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x180008247  nop     dword ptr [rax+rax+00h]
0x18000824c  mov     r9d, 4FCh
0x180008252  lea     r8, aBaseEcoWdsWdss_0; "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src"...
0x180008259  mov     ecx, eax
0x18000825b  mov     edi, eax
0x18000825d  mov     rbp, rbx
0x180008260  call    ElValidateWin32_0
0x180008265  test    eax, eax
0x180008267  jnz     loc_180008324
0x18000826d  mov     rcx, [rsi+10h]
0x180008271  lea     rdx, [rbx+10h]
0x180008275  call    cs:__imp_?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x18000827c  nop     dword ptr [rax+rax+00h]
0x180008281  mov     r9d, 4FFh
0x180008287  lea     r8, aBaseEcoWdsWdss_0; "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src"...
0x18000828e  mov     ecx, eax
0x180008290  mov     edi, eax
0x180008292  call    ElValidateWin32_0
0x180008297  test    eax, eax
0x180008299  jnz     loc_180008324
0x18000829f  mov     rcx, [rsi+18h]
0x1800082a3  lea     rdx, [rbx+18h]
0x1800082a7  call    cs:__imp_?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x1800082ae  nop     dword ptr [rax+rax+00h]
0x1800082b3  mov     r9d, 504h
0x1800082b9  lea     r8, aBaseEcoWdsWdss_0; "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src"...
0x1800082c0  mov     ecx, eax
0x1800082c2  mov     edi, eax
0x1800082c4  call    ElValidateWin32_0
0x1800082c9  test    eax, eax
0x1800082cb  jnz     short loc_180008324
0x1800082cd  mov     eax, [rsi+24h]
0x1800082d0  mov     [rbx+24h], eax
0x1800082d3  mov     eax, [rsi+20h]
0x1800082d6  mov     [rbx+20h], eax
0x1800082d9  mov     eax, [rsi+40h]
0x1800082dc  mov     [rbx+40h], eax
0x1800082df  mov     eax, [rsi+2Ch]
0x1800082e2  mov     [rbx+2Ch], eax
0x1800082e5  movups  xmm0, xmmword ptr [rsi+30h]
0x1800082e9  movdqu  xmmword ptr [rbx+30h], xmm0
0x1800082ee  mov     rcx, [rsi+8]
0x1800082f2  call    cs:__imp_WdsImgAddReference
0x1800082f9  nop     dword ptr [rax+rax+00h]
0x1800082fe  mov     ecx, eax
0x180008300  mov     r9d, 50Eh
0x180008306  mov     ebp, eax
0x180008308  call    ElValidateHr_0
0x18000830d  test    eax, eax
0x18000830f  jns     short loc_18000832E
0x180008311  mov     ecx, ebp
0x180008313  call    cs:__imp_?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x18000831a  nop     dword ptr [rax+rax+00h]
0x18000831f  mov     edi, eax
0x180008321  mov     rbp, rbx
0x180008324  mov     rcx, rbp; this
0x180008327  call    ??_GImage@CImageCache@@QEAAPEAXI@Z; CImageCache::Image::`scalar deleting destructor'(uint)
0x18000832c  jmp     short loc_180008340
0x18000832e  mov     rax, [rsi+8]
0x180008332  mov     [rbx+8], rax
0x180008336  mov     [r14], rbx
0x180008339  jmp     short loc_180008340
0x18000833b  mov     edi, 8
0x180008340  mov     rbx, [rsp+28h+arg_0]
0x180008345  mov     eax, edi
0x180008347  mov     rdi, [rsp+28h+arg_18]
0x18000834c  mov     rbp, [rsp+28h+arg_8]
0x180008351  mov     rsi, [rsp+28h+arg_10]
0x180008356  add     rsp, 20h
0x18000835a  pop     r14
0x18000835c  retn
```
