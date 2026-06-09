# DirectUI::CreateAndInit<CCRichEdit,uint>(uint,DirectUI::Element *,ulong *,DirectUI::Element * *)

- ea: `0x18000bda4`
- end: `0x18000be4d`
- name: `??$CreateAndInit@VCCRichEdit@@I@DirectUI@@YAJIPEAVElement@0@PEAKPEAPEAV10@@Z`
- size: `169`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c080`
- `0x18000c268`

## callees

- `0x18000bda4`
- `0x18000c110`

## import_xrefs

- `DUI70!?Initialize@HWNDHost@DirectUI@@QEAAJIIPEAVElement@2@PEAK@Z` at `0x18000be1d`
- `DUI70!?Initialize@HWNDHost@DirectUI@@QEAAJIIPEAVElement@2@PEAK@Z` at `0x18000be1d`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18000be33`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18000be33`
- `DUI70!??0HWNDHost@DirectUI@@QEAA@XZ` at `0x18000bdd7`
- `DUI70!??0HWNDHost@DirectUI@@QEAA@XZ` at `0x18000bdd7`

## pseudocode

```c
__int64 __fastcall DirectUI::CreateAndInit<CCRichEdit,unsigned int>(
        unsigned int a1,
        struct DirectUI::Element *a2,
        unsigned int *a3,
        DirectUI::HWNDHost **a4)
{
  DirectUI::HWNDHost *v8; // rax
  DirectUI::HWNDHost *v9; // rbx
  int v10; // edi

  *a4 = 0;
  v8 = (DirectUI::HWNDHost *)DirectUI::HAllocAndZero((DirectUI *)0x168, (unsigned __int64)a2);
  v9 = v8;
  if ( v8 )
  {
    DirectUI::HWNDHost::HWNDHost(v8);
    *((_DWORD *)v9 + 80) = 1353779396;
    *((_QWORD *)v9 + 41) = L"RichEdit20W";
    *((_QWORD *)v9 + 44) = 0;
    *(_QWORD *)v9 = &CCRichEdit::`vftable';
    v10 = DirectUI::HWNDHost::Initialize(v9, 0x19u, a1, a2, a3);
    if ( v10 < 0 )
      DirectUI::Element::Destroy(v9, 0);
    else
      *a4 = v9;
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000bda4  push    rbx
0x18000bda6  push    rbp
0x18000bda7  push    rsi
0x18000bda8  push    rdi
0x18000bda9  push    r14
0x18000bdab  sub     rsp, 30h
0x18000bdaf  mov     r14d, ecx
0x18000bdb2  mov     qword ptr [r9], 0
0x18000bdb9  mov     ecx, 168h; this
0x18000bdbe  mov     rsi, r9
0x18000bdc1  mov     rdi, r8
0x18000bdc4  mov     rbp, rdx
0x18000bdc7  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x18000bdcc  mov     rbx, rax
0x18000bdcf  test    rax, rax
0x18000bdd2  jz      short loc_18000BE3B
0x18000bdd4  mov     rcx, rax
0x18000bdd7  call    cs:__imp_??0HWNDHost@DirectUI@@QEAA@XZ; DirectUI::HWNDHost::HWNDHost(void)
0x18000bddd  lea     rax, aRichedit20w; "RichEdit20W"
0x18000bde4  mov     dword ptr [rbx+140h], 50B108C4h
0x18000bdee  mov     [rbx+148h], rax
0x18000bdf5  mov     r9, rbp
0x18000bdf8  lea     rax, ??_7CCRichEdit@@6B@; const CCRichEdit::`vftable'
0x18000bdff  mov     qword ptr [rbx+160h], 0
0x18000be0a  mov     r8d, r14d
0x18000be0d  mov     [rbx], rax
0x18000be10  mov     edx, 19h
0x18000be15  mov     [rsp+58h+var_38], rdi
0x18000be1a  mov     rcx, rbx
0x18000be1d  call    cs:__imp_?Initialize@HWNDHost@DirectUI@@QEAAJIIPEAVElement@2@PEAK@Z; DirectUI::HWNDHost::Initialize(uint,uint,DirectUI::Element *,ulong *)
0x18000be23  mov     edi, eax
0x18000be25  test    eax, eax
0x18000be27  js      short loc_18000BE2E
0x18000be29  mov     [rsi], rbx
0x18000be2c  jmp     short loc_18000BE40
0x18000be2e  xor     edx, edx
0x18000be30  mov     rcx, rbx
0x18000be33  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x18000be39  jmp     short loc_18000BE40
0x18000be3b  mov     edi, 8007000Eh
0x18000be40  mov     eax, edi
0x18000be42  add     rsp, 30h
0x18000be46  pop     r14
0x18000be48  pop     rdi
0x18000be49  pop     rsi
0x18000be4a  pop     rbp
0x18000be4b  pop     rbx
0x18000be4c  retn
```
