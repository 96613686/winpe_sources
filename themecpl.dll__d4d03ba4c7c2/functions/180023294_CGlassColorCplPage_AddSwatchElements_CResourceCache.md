# CGlassColorCplPage::_AddSwatchElements(CResourceCache *)

- ea: `0x180023294`
- end: `0x180023379`
- name: `?_AddSwatchElements@CGlassColorCplPage@@AEAAJPEAVCResourceCache@@@Z`
- size: `229`
- prototype: `__int64 __fastcall(CGlassColorCplPage *__hidden this, struct CResourceCache *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180023aa4`

## callees

- `0x18000fc18`
- `0x180023070`
- `0x180023294`

## import_xrefs

- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x1800232c4`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x1800232c4`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x1800232f2`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x1800232f2`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x18002335d`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x18002335d`

## pseudocode

```c
__int64 __fastcall CGlassColorCplPage::_AddSwatchElements(CGlassColorCplPage *this, struct CResourceCache *a2)
{
  int SwatchPtrAtIndex; // ebx
  unsigned int v5; // edi
  CColorSwatchStore *v6; // rcx
  struct DirectUI::DUIXmlParser *v8; // [rsp+60h] [rbp+18h] BYREF
  struct CColorSwatchConfig *v9; // [rsp+68h] [rbp+20h] BYREF

  v8 = 0;
  SwatchPtrAtIndex = DirectUI::DUIXmlParser::Create(&v8, 0, 0, 0, 0);
  if ( SwatchPtrAtIndex >= 0 )
  {
    SwatchPtrAtIndex = DirectUI::DUIXmlParser::SetXMLFromResource(v8, 0x3EAu, g_hinst, &_ImageBase);
    if ( SwatchPtrAtIndex >= 0 )
    {
      v5 = 0;
      do
      {
        v6 = (CColorSwatchStore *)*((_QWORD *)this + 40);
        if ( !*(_QWORD *)v6 || v5 >= (**(_DWORD **)v6 & 0xFFFFFFFu) )
          break;
        v9 = 0;
        SwatchPtrAtIndex = CColorSwatchStore::GetSwatchPtrAtIndex(v6, v5, &v9);
        if ( SwatchPtrAtIndex >= 0 )
          SwatchPtrAtIndex = CGlassColorCplPage::_AddSwatchElement(this, v8, a2, (const unsigned __int16 **)v9);
        ++v5;
      }
      while ( SwatchPtrAtIndex >= 0 );
    }
    DirectUI::DUIXmlParser::Destroy(v8);
  }
  return (unsigned int)SwatchPtrAtIndex;
}

```

## disassembly

```asm
0x180023294  mov     rax, rsp
0x180023297  mov     [rax+8], rbx
0x18002329b  push    rbp
0x18002329c  push    rsi
0x18002329d  push    rdi
0x18002329e  sub     rsp, 30h
0x1800232a2  mov     rbp, rdx
0x1800232a5  mov     qword ptr [rax+18h], 0
0x1800232ad  mov     rsi, rcx
0x1800232b0  mov     qword ptr [rax-28h], 0
0x1800232b8  xor     edx, edx
0x1800232ba  lea     rcx, [rax+18h]
0x1800232be  xor     r9d, r9d
0x1800232c1  xor     r8d, r8d
0x1800232c4  call    cs:__imp_?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z; DirectUI::DUIXmlParser::Create(DirectUI::DUIXmlParser * *,DirectUI::Value * (*)(ushort const *,void *),void *,void (*)(ushort const *,ushort const *,int,void *),void *)
0x1800232cb  nop     dword ptr [rax+rax+00h]
0x1800232d0  mov     ebx, eax
0x1800232d2  test    eax, eax
0x1800232d4  js      loc_180023369
0x1800232da  mov     r8, cs:g_hinst
0x1800232e1  lea     r9, __ImageBase
0x1800232e8  mov     rcx, [rsp+48h+arg_10]
0x1800232ed  mov     edx, 3EAh
0x1800232f2  call    cs:__imp_?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z; DirectUI::DUIXmlParser::SetXMLFromResource(uint,HINSTANCE__ *,HINSTANCE__ *)
0x1800232f9  nop     dword ptr [rax+rax+00h]
0x1800232fe  mov     ebx, eax
0x180023300  test    eax, eax
0x180023302  js      short loc_180023358
0x180023304  xor     edi, edi
0x180023306  mov     rcx, [rsi+140h]; this
0x18002330d  mov     rax, [rcx]
0x180023310  test    rax, rax
0x180023313  jz      short loc_180023358
0x180023315  mov     eax, [rax]
0x180023317  and     eax, 0FFFFFFFh
0x18002331c  cmp     edi, eax
0x18002331e  jnb     short loc_180023358
0x180023320  lea     r8, [rsp+48h+arg_18]; struct CColorSwatchConfig **
0x180023325  mov     [rsp+48h+arg_18], 0
0x18002332e  mov     edx, edi; unsigned int
0x180023330  call    ?GetSwatchPtrAtIndex@CColorSwatchStore@@QEAAJIPEAPEBVCColorSwatchConfig@@@Z; CColorSwatchStore::GetSwatchPtrAtIndex(uint,CColorSwatchConfig const * *)
0x180023335  mov     ebx, eax
0x180023337  test    eax, eax
0x180023339  js      short loc_180023352
0x18002333b  mov     r9, [rsp+48h+arg_18]; struct CColorSwatchConfig *
0x180023340  mov     r8, rbp; struct CResourceCache *
0x180023343  mov     rdx, [rsp+48h+arg_10]; struct DirectUI::DUIXmlParser *
0x180023348  mov     rcx, rsi; this
0x18002334b  call    ?_AddSwatchElement@CGlassColorCplPage@@AEAAJPEAVDUIXmlParser@DirectUI@@PEAVCResourceCache@@PEBVCColorSwatchConfig@@@Z; CGlassColorCplPage::_AddSwatchElement(DirectUI::DUIXmlParser *,CResourceCache *,CColorSwatchConfig const *)
0x180023350  mov     ebx, eax
0x180023352  inc     edi
0x180023354  test    ebx, ebx
0x180023356  jns     short loc_180023306
0x180023358  mov     rcx, [rsp+48h+arg_10]
0x18002335d  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x180023364  nop     dword ptr [rax+rax+00h]
0x180023369  mov     eax, ebx
0x18002336b  mov     rbx, [rsp+48h+arg_0]
0x180023370  add     rsp, 30h
0x180023374  pop     rdi
0x180023375  pop     rsi
0x180023376  pop     rbp
0x180023377  retn
```
