# FillElementFromLayout(DirectUI::Element *,DirectUI::DUIXmlParser *,ushort const *)

- ea: `0x18001d920`
- end: `0x18001d9fc`
- name: `?FillElementFromLayout@@YAJPEAVElement@DirectUI@@PEAVDUIXmlParser@2@PEBG@Z`
- size: `220`
- prototype: `__int64 __fastcall(struct DirectUI::Element *, struct DirectUI::DUIXmlParser *, struct DirectUI::Element *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180015480`

## callees

- `0x18001d920`

## import_xrefs

- `DUI70!?SetLayout@Element@DirectUI@@QEAAJPEAVLayout@2@@Z` at `0x18001d95e`
- `DUI70!?SetLayout@Element@DirectUI@@QEAAJPEAVLayout@2@@Z` at `0x18001d95e`
- `DUI70!?Create@FillLayout@DirectUI@@SAJPEAPEAVLayout@2@@Z` at `0x18001d946`
- `DUI70!?Create@FillLayout@DirectUI@@SAJPEAPEAVLayout@2@@Z` at `0x18001d946`
- `DUI70!?Destroy@Layout@DirectUI@@QEAAXXZ` at `0x18001d9e4`
- `DUI70!?Destroy@Layout@DirectUI@@QEAAXXZ` at `0x18001d9e4`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18001d9b3`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18001d9b3`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x18001d99f`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x18001d99f`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18001d9d4`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18001d9d4`

## pseudocode

```c
__int64 __fastcall FillElementFromLayout(
        struct DirectUI::Element *a1,
        struct DirectUI::DUIXmlParser *a2,
        struct DirectUI::Element *a3)
{
  int v5; // ebx
  DirectUI::Element *v6; // rcx
  struct DirectUI::Element *v8; // [rsp+50h] [rbp+18h] BYREF
  struct DirectUI::Layout *v9; // [rsp+58h] [rbp+20h] BYREF

  v8 = a3;
  v9 = 0;
  v5 = DirectUI::FillLayout::Create(&v9);
  if ( v5 >= 0 )
  {
    v5 = DirectUI::Element::SetLayout(a1, v9);
    if ( v5 >= 0 )
    {
      v9 = 0;
      v8 = 0;
      v5 = DirectUI::DUIXmlParser::CreateElement(a2, L"ProgressControl", 0, a1, 0, &v8);
      if ( v5 < 0 || (v5 = DirectUI::Element::Add(a1, v8), v5 < 0) )
      {
        v6 = v8;
      }
      else
      {
        v6 = 0;
        v8 = 0;
      }
      if ( v6 )
        DirectUI::Element::Destroy(v6, 1);
    }
  }
  if ( v9 )
    DirectUI::Layout::Destroy(v9);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001d920  mov     rax, rsp
0x18001d923  mov     [rax+8], rbx
0x18001d927  mov     [rax+10h], rsi
0x18001d92b  mov     [rax+18h], r8
0x18001d92f  push    rdi
0x18001d930  sub     rsp, 30h
0x18001d934  mov     rdi, rcx
0x18001d937  mov     qword ptr [rax+20h], 0
0x18001d93f  lea     rcx, [rax+20h]
0x18001d943  mov     rsi, rdx
0x18001d946  call    cs:__imp_?Create@FillLayout@DirectUI@@SAJPEAPEAVLayout@2@@Z; DirectUI::FillLayout::Create(DirectUI::Layout * *)
0x18001d94c  mov     ebx, eax
0x18001d94e  test    eax, eax
0x18001d950  js      loc_18001D9DA
0x18001d956  mov     rdx, [rsp+38h+arg_18]
0x18001d95b  mov     rcx, rdi
0x18001d95e  call    cs:__imp_?SetLayout@Element@DirectUI@@QEAAJPEAVLayout@2@@Z; DirectUI::Element::SetLayout(DirectUI::Layout *)
0x18001d964  mov     ebx, eax
0x18001d966  test    eax, eax
0x18001d968  js      short loc_18001D9DA
0x18001d96a  lea     rax, [rsp+38h+arg_10]
0x18001d96f  mov     [rsp+38h+arg_18], 0
0x18001d978  mov     [rsp+38h+var_10], rax
0x18001d97d  lea     rdx, aProgresscontro; "ProgressControl"
0x18001d984  mov     r9, rdi
0x18001d987  mov     [rsp+38h+var_18], 0
0x18001d990  xor     r8d, r8d
0x18001d993  mov     [rsp+38h+arg_10], 0
0x18001d99c  mov     rcx, rsi
0x18001d99f  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x18001d9a5  mov     ebx, eax
0x18001d9a7  test    eax, eax
0x18001d9a9  js      short loc_18001D9C8
0x18001d9ab  mov     rdx, [rsp+38h+arg_10]
0x18001d9b0  mov     rcx, rdi
0x18001d9b3  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x18001d9b9  mov     ebx, eax
0x18001d9bb  test    eax, eax
0x18001d9bd  js      short loc_18001D9C8
0x18001d9bf  xor     ecx, ecx
0x18001d9c1  mov     [rsp+38h+arg_10], rcx
0x18001d9c6  jmp     short loc_18001D9CD
0x18001d9c8  mov     rcx, [rsp+38h+arg_10]
0x18001d9cd  test    rcx, rcx
0x18001d9d0  jz      short loc_18001D9DA
0x18001d9d2  mov     dl, 1
0x18001d9d4  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x18001d9da  mov     rcx, [rsp+38h+arg_18]
0x18001d9df  test    rcx, rcx
0x18001d9e2  jz      short loc_18001D9EA
0x18001d9e4  call    cs:__imp_?Destroy@Layout@DirectUI@@QEAAXXZ; DirectUI::Layout::Destroy(void)
0x18001d9ea  mov     rsi, [rsp+38h+arg_8]
0x18001d9ef  mov     eax, ebx
0x18001d9f1  mov     rbx, [rsp+38h+arg_0]
0x18001d9f6  add     rsp, 30h
0x18001d9fa  pop     rdi
0x18001d9fb  retn
```
