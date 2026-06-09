# CImageCache::EnumImageGroups(void *)

- ea: `0x180008364`
- end: `0x18000848e`
- name: `?EnumImageGroups@CImageCache@@AEAAKPEAX@Z`
- size: `298`
- prototype: `unsigned int __fastcall(CImageCache *__hidden this, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180009490`

## callees

- `0x180008364`
- `0x180008494`
- `0x18000ad88`
- `0x18000aeac`
- `0x180017010`

## import_xrefs

- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x180008457`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x180008457`
- `WdsImage!WdsImgGroupGetName` at `0x1800083c8`
- `WdsImage!WdsImgGroupGetName` at `0x1800083c8`
- `WdsImage!WdsImgFindFirstImageGroup` at `0x18000838d`
- `WdsImage!WdsImgFindFirstImageGroup` at `0x18000838d`
- `WdsImage!WdsImgFindNextImageGroup` at `0x180008435`
- `WdsImage!WdsImgFindNextImageGroup` at `0x180008435`
- `WdsImage!WdsImgClose` at `0x18000846f`
- `WdsImage!WdsImgClose` at `0x18000846f`

## string_xrefs

- `0x18000841c`: `base\eco\wds\wdssrv\wdsimgsrv\src\imagecache.cpp`
- `0x1800083f8`: `ImageCache: Enumerating Group [%s]`

## pseudocode

```c
__int64 __fastcall CImageCache::EnumImageGroups(CImageCache *this, void *a2)
{
  __int64 v3; // rbx
  __int64 v4; // rdx
  unsigned int FirstImageGroup; // edi
  __int64 v6; // r8
  __int64 i; // r9
  unsigned int v8; // ecx
  __int64 Name; // rbx
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rdx
  void *v14; // [rsp+40h] [rbp+18h] BYREF
  unsigned __int16 *v15; // [rsp+48h] [rbp+20h] BYREF

  LODWORD(v3) = 0;
  v14 = 0;
  v15 = 0;
  FirstImageGroup = WdsImgFindFirstImageGroup(a2, 0, &v14);
  if ( FirstImageGroup != -1056833018 )
  {
    for ( i = 1205; ; i = 1234 )
    {
      if ( (int)ElValidateHr_0(FirstImageGroup, v4, v6, i) < 0 )
      {
        v8 = FirstImageGroup;
        goto LABEL_12;
      }
      Name = (unsigned int)WdsImgGroupGetName(v14, &v15);
      if ( (int)ElValidateHr_0(Name, v10, v11, 1214) < 0 )
        break;
      if ( g_ErrLibTraceFunction )
        g_ErrLibTraceFunction(L"ImageCache: Enumerating Group [%s]", v15);
      v3 = (unsigned int)CImageCache::EnumImages(this, v14, v15);
      if ( (unsigned int)ElValidateWin32_0(v3, v12, "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp", 1222) )
        goto LABEL_13;
      FirstImageGroup = WdsImgFindNextImageGroup(v14);
      if ( FirstImageGroup == -1056833017 )
        goto LABEL_13;
    }
    v8 = Name;
LABEL_12:
    LODWORD(v3) = WIN32_FROM_HRESULT(v8);
  }
LABEL_13:
  if ( v14 )
    WdsImgClose();
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180008364  mov     r11, rsp
0x180008367  mov     [r11+8], rbx
0x18000836b  mov     [r11+10h], rsi
0x18000836f  push    rdi
0x180008370  sub     rsp, 20h
0x180008374  mov     rax, rdx
0x180008377  lea     r8, [r11+18h]
0x18000837b  mov     rsi, rcx
0x18000837e  xor     ebx, ebx
0x180008380  and     [r11+18h], rbx
0x180008384  mov     rcx, rax
0x180008387  and     [r11+20h], rbx
0x18000838b  xor     edx, edx
0x18000838d  call    cs:__imp_WdsImgFindFirstImageGroup
0x180008394  nop     dword ptr [rax+rax+00h]
0x180008399  mov     edi, eax
0x18000839b  cmp     eax, 0C1020206h
0x1800083a0  jz      loc_180008465
0x1800083a6  mov     r9d, 4B5h
0x1800083ac  mov     ecx, edi
0x1800083ae  call    ElValidateHr_0
0x1800083b3  test    eax, eax
0x1800083b5  jns     short loc_1800083BE
0x1800083b7  mov     ecx, edi
0x1800083b9  jmp     loc_180008457
0x1800083be  mov     rcx, [rsp+28h+arg_10]
0x1800083c3  lea     rdx, [rsp+28h+arg_18]
0x1800083c8  call    cs:__imp_WdsImgGroupGetName
0x1800083cf  nop     dword ptr [rax+rax+00h]
0x1800083d4  mov     ecx, eax
0x1800083d6  mov     r9d, 4BEh
0x1800083dc  mov     ebx, eax
0x1800083de  call    ElValidateHr_0
0x1800083e3  test    eax, eax
0x1800083e5  js      short loc_180008455
0x1800083e7  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800083ee  test    rax, rax
0x1800083f1  jz      short loc_180008404
0x1800083f3  mov     rdx, [rsp+28h+arg_18]
0x1800083f8  lea     rcx, aImagecacheEnum; "ImageCache: Enumerating Group [%s]"
0x1800083ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008404  mov     r8, [rsp+28h+arg_18]; unsigned __int16 *
0x180008409  mov     rcx, rsi; this
0x18000840c  mov     rdx, [rsp+28h+arg_10]; void *
0x180008411  call    ?EnumImages@CImageCache@@AEAAKPEAXPEBG@Z; CImageCache::EnumImages(void *,ushort const *)
0x180008416  mov     r9d, 4C6h
0x18000841c  lea     r8, aBaseEcoWdsWdss_0; "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src"...
0x180008423  mov     ecx, eax
0x180008425  mov     ebx, eax
0x180008427  call    ElValidateWin32_0
0x18000842c  test    eax, eax
0x18000842e  jnz     short loc_180008465
0x180008430  mov     rcx, [rsp+28h+arg_10]
0x180008435  call    cs:__imp_WdsImgFindNextImageGroup
0x18000843c  nop     dword ptr [rax+rax+00h]
0x180008441  mov     edi, eax
0x180008443  cmp     eax, 0C1020207h
0x180008448  jz      short loc_180008465
0x18000844a  mov     r9d, 4D2h
0x180008450  jmp     loc_1800083AC
0x180008455  mov     ecx, ebx
0x180008457  call    cs:__imp_?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x18000845e  nop     dword ptr [rax+rax+00h]
0x180008463  mov     ebx, eax
0x180008465  mov     rcx, [rsp+28h+arg_10]
0x18000846a  test    rcx, rcx
0x18000846d  jz      short loc_18000847B
0x18000846f  call    cs:__imp_WdsImgClose
0x180008476  nop     dword ptr [rax+rax+00h]
0x18000847b  mov     rsi, [rsp+28h+arg_8]
0x180008480  mov     eax, ebx
0x180008482  mov     rbx, [rsp+28h+arg_0]
0x180008487  add     rsp, 20h
0x18000848b  pop     rdi
0x18000848c  retn
```
