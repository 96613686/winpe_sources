# CWSHExtension::AddPages(int (*)(_PSP *,__int64),__int64)

- ea: `0x180009e90`
- end: `0x180009fcc`
- name: `?AddPages@CWSHExtension@@UEAAJP6AHPEAU_PSP@@_J@Z1@Z`
- size: `316`
- prototype: `__int64 __fastcall(CWSHExtension *__hidden this, int (*)(struct _PSP *, __int64), __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003200`
- `0x180007264`
- `0x1800072c4`
- `0x180009e90`
- `0x18000a038`
- `0x18000d1c0`
- `0x18000e010`

## import_xrefs

- `COMCTL32!CreatePropertySheetPageA` at `0x180009f77`
- `COMCTL32!CreatePropertySheetPageA` at `0x180009f77`
- `COMCTL32!DestroyPropertySheetPage` at `0x180009f9a`
- `COMCTL32!DestroyPropertySheetPage` at `0x180009f9a`

## pseudocode

```c
__int64 __fastcall CWSHExtension::AddPages(
        CWSHExtension *this,
        unsigned int (__fastcall *a2)(HPROPSHEETPAGE, __int64),
        __int64 a3)
{
  CPspGeneral *v5; // rax
  CPspGeneral *v6; // rax
  __int64 v7; // rdx
  LPCSTR *v8; // rbx
  int v9; // edi
  HPROPSHEETPAGE v11; // rax
  struct _PSP *v12; // rbx
  PROPSHEETPAGEA_V4 constPropSheetPagePointer; // [rsp+20h] [rbp-2A8h] BYREF
  unsigned __int16 v14[264]; // [rsp+90h] [rbp-238h] BYREF

  get_pathname(*((_QWORD *)this + 8), v14);
  v5 = (CPspGeneral *)operator new(0xAB0u);
  if ( !v5 )
    return 2147942414LL;
  v6 = CPspGeneral::CPspGeneral(v5);
  v8 = (LPCSTR *)v6;
  if ( !v6 )
    return 2147942414LL;
  v9 = CPspGeneral::Init(v6, v7, v14);
  if ( v9 >= 0 )
  {
    constPropSheetPagePointer.dwSize = 104;
    constPropSheetPagePointer.hInstance = Global::g_hResource;
    constPropSheetPagePointer.dwFlags = Global::g_isLanguageBiDi ? 0x10 : 0;
    constPropSheetPagePointer.pszTemplate = v8[3];
    constPropSheetPagePointer.pfnDlgProc = (DLGPROC)CPropertyPage::DialogProc;
    constPropSheetPagePointer.dwFlags |= 0x40u;
    constPropSheetPagePointer.pcRefParent = &g_cRefPropSheet;
    constPropSheetPagePointer.lParam = (LPARAM)v8;
    v11 = CreatePropertySheetPageA(&constPropSheetPagePointer);
    v12 = v11;
    if ( v11 )
    {
      if ( !a2(v11, a3) )
        DestroyPropertySheetPage(v12);
    }
    return 0;
  }
  else
  {
    (*((void (__fastcall **)(LPCSTR *, __int64))*v8 + 1))(v8, 1);
    return (unsigned int)v9;
  }
}

```

## disassembly

```asm
0x180009e90  mov     [rsp+arg_18], rbx
0x180009e95  push    rbp
0x180009e96  push    rsi
0x180009e97  push    rdi
0x180009e98  sub     rsp, 2B0h
0x180009e9f  mov     rax, cs:__security_cookie
0x180009ea6  xor     rax, rsp
0x180009ea9  mov     [rsp+2C8h+var_28], rax
0x180009eb1  mov     rcx, [rcx+40h]
0x180009eb5  mov     rsi, rdx
0x180009eb8  lea     rdx, [rsp+2C8h+var_238]
0x180009ec0  mov     rbp, r8
0x180009ec3  call    get_pathname
0x180009ec8  mov     ecx, 0AB0h; Size
0x180009ecd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009ed2  test    rax, rax
0x180009ed5  jz      loc_180009FA4
0x180009edb  mov     rcx, rax; this
0x180009ede  call    ??0CPspGeneral@@QEAA@XZ; CPspGeneral::CPspGeneral(void)
0x180009ee3  mov     rbx, rax
0x180009ee6  test    rax, rax
0x180009ee9  jz      loc_180009FA4
0x180009eef  lea     r8, [rsp+2C8h+var_238]; unsigned __int16 *
0x180009ef7  mov     rcx, rax; this
0x180009efa  call    ?Init@CPspGeneral@@QEAAJIPEBG@Z; CPspGeneral::Init(uint,ushort const *)
0x180009eff  mov     edi, eax
0x180009f01  test    eax, eax
0x180009f03  jns     short loc_180009F20
0x180009f05  mov     rcx, [rbx]
0x180009f08  mov     edx, 1
0x180009f0d  mov     rax, [rcx+8]
0x180009f11  mov     rcx, rbx
0x180009f14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f19  mov     eax, edi
0x180009f1b  jmp     loc_180009FA9
0x180009f20  mov     al, cs:?g_isLanguageBiDi@Global@@2_NA; bool Global::g_isLanguageBiDi
0x180009f26  neg     al
0x180009f28  mov     [rsp+2C8h+constPropSheetPagePointer.dwSize], 68h ; 'h'
0x180009f30  mov     rax, cs:?g_hResource@Global@@2PEAUHINSTANCE__@@EA; HINSTANCE__ * Global::g_hResource
0x180009f37  sbb     ecx, ecx
0x180009f39  mov     [rsp+2C8h+constPropSheetPagePointer.hInstance], rax
0x180009f3e  and     ecx, 10h
0x180009f41  mov     [rsp+2C8h+constPropSheetPagePointer.dwFlags], ecx
0x180009f45  or      ecx, 40h
0x180009f48  mov     rax, [rbx+18h]
0x180009f4c  mov     qword ptr [rsp+2C8h+constPropSheetPagePointer.10h], rax
0x180009f51  lea     rax, ?DialogProc@CPropertyPage@@KA_JPEAUHWND__@@I_K_J@Z; CPropertyPage::DialogProc(HWND__ *,uint,unsigned __int64,__int64)
0x180009f58  mov     [rsp+2C8h+constPropSheetPagePointer.pfnDlgProc], rax
0x180009f5d  lea     rax, ?g_cRefPropSheet@@3IA; uint g_cRefPropSheet
0x180009f64  mov     [rsp+2C8h+constPropSheetPagePointer.dwFlags], ecx
0x180009f68  lea     rcx, [rsp+2C8h+constPropSheetPagePointer]; constPropSheetPagePointer
0x180009f6d  mov     [rsp+2C8h+constPropSheetPagePointer.pcRefParent], rax
0x180009f72  mov     [rsp+2C8h+constPropSheetPagePointer.lParam], rbx
0x180009f77  call    cs:__imp_CreatePropertySheetPageA
0x180009f7d  mov     rbx, rax
0x180009f80  test    rax, rax
0x180009f83  jz      short loc_180009FA0
0x180009f85  mov     rcx, rax
0x180009f88  mov     rdx, rbp
0x180009f8b  mov     rax, rsi
0x180009f8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f93  test    eax, eax
0x180009f95  jnz     short loc_180009FA0
0x180009f97  mov     rcx, rbx; HPROPSHEETPAGE
0x180009f9a  call    cs:__imp_DestroyPropertySheetPage
0x180009fa0  xor     eax, eax
0x180009fa2  jmp     short loc_180009FA9
0x180009fa4  mov     eax, 8007000Eh
0x180009fa9  mov     rcx, [rsp+2C8h+var_28]
0x180009fb1  xor     rcx, rsp; StackCookie
0x180009fb4  call    __security_check_cookie
0x180009fb9  mov     rbx, [rsp+2C8h+arg_18]
0x180009fc1  add     rsp, 2B0h
0x180009fc8  pop     rdi
0x180009fc9  pop     rsi
0x180009fca  pop     rbp
0x180009fcb  retn
```
