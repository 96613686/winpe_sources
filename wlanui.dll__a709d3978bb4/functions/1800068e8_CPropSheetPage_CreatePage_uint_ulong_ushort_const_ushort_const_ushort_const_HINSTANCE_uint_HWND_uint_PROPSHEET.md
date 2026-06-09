# CPropSheetPage::CreatePage(uint,ulong,ushort const *,ushort const *,ushort const *,HINSTANCE__ *,uint (*)(HWND__ *,uint,_PROPSHEETPAGEW *))

- ea: `0x1800068e8`
- end: `0x180006955`
- name: `?CreatePage@CPropSheetPage@@QEAAPEAU_PSP@@IKPEBG00PEAUHINSTANCE__@@P6AIPEAUHWND__@@IPEAU_PROPSHEETPAGEW@@@Z@Z`
- size: `109`
- prototype: `struct _PSP *__fastcall(CPropSheetPage *__hidden this, unsigned int, unsigned int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, HINSTANCE, unsigned int (*)(HWND, unsigned int, struct _PROPSHEETPAGEW *))`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180007604`
- `0x1800104cc`

## callees

- `0x180014cdc`

## pseudocode

```c
HPROPSHEETPAGE __fastcall CPropSheetPage::CreatePage(
        CPropSheetPage *this,
        unsigned __int16 a2,
        __int64 a3,
        const unsigned __int16 *a4)
{
  PROPSHEETPAGEW_V4 constPropSheetPagePointer; // [rsp+20h] [rbp-39h] BYREF

  constPropSheetPagePointer.lParam = (LPARAM)this;
  constPropSheetPagePointer.hIcon = 0;
  constPropSheetPagePointer.hInstance = hModule;
  constPropSheetPagePointer.pszTemplate = (LPCWSTR)a2;
  constPropSheetPagePointer.pfnDlgProc = (DLGPROC)CPropSheetPage::DialogProc;
  *(_QWORD *)&constPropSheetPagePointer.dwSize = 104;
  memset(&constPropSheetPagePointer.pfnCallback, 0, 48);
  constPropSheetPagePointer.pszTitle = 0;
  return CreatePropertySheetPageW(&constPropSheetPagePointer);
}

```

## disassembly

```asm
0x1800068e8  push    rbp
0x1800068ea  lea     rbp, [rsp-37h]
0x1800068ef  sub     rsp, 90h
0x1800068f6  xor     eax, eax
0x1800068f8  mov     [rbp+37h+constPropSheetPagePointer.lParam], rcx
0x1800068fc  xor     r8d, r8d
0x1800068ff  mov     qword ptr [rbp+37h+constPropSheetPagePointer.18h], rax
0x180006903  mov     [rbp+37h+constPropSheetPagePointer.pcRefParent], rax
0x180006907  lea     rcx, [rbp+37h+constPropSheetPagePointer]; constPropSheetPagePointer
0x18000690b  mov     rax, cs:hModule
0x180006912  xorps   xmm0, xmm0
0x180006915  mov     [rbp+37h+constPropSheetPagePointer.hInstance], rax
0x180006919  movzx   eax, dx
0x18000691c  mov     qword ptr [rbp+37h+constPropSheetPagePointer.10h], rax
0x180006920  lea     rax, ?DialogProc@CPropSheetPage@@SA_JPEAUHWND__@@I_K_J@Z; CPropSheetPage::DialogProc(HWND__ *,uint,unsigned __int64,__int64)
0x180006927  mov     [rbp+37h+constPropSheetPagePointer.pfnDlgProc], rax
0x18000692b  movups  xmmword ptr [rbp+37h+constPropSheetPagePointer.hActCtx], xmm0
0x18000692f  mov     qword ptr [rbp+37h+constPropSheetPagePointer.dwSize], 68h ; 'h'
0x180006937  mov     [rbp+37h+constPropSheetPagePointer.pfnCallback], r8
0x18000693b  mov     [rbp+37h+constPropSheetPagePointer.pszHeaderTitle], r8
0x18000693f  mov     [rbp+37h+constPropSheetPagePointer.pszHeaderSubTitle], r8
0x180006943  mov     [rbp+37h+constPropSheetPagePointer.pszTitle], r8
0x180006947  call    CreatePropertySheetPageW
0x18000694c  add     rsp, 90h
0x180006953  pop     rbp
0x180006954  retn
```
