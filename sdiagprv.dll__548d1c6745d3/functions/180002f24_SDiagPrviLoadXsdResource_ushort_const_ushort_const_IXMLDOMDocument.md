# SDiagPrviLoadXsdResource(ushort const *,ushort const *,IXMLDOMDocument * *)

- ea: `0x180002f24`
- end: `0x1800031d0`
- name: `?SDiagPrviLoadXsdResource@@YAJPEBG0PEAPEAUIXMLDOMDocument@@@Z`
- size: `684`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, struct IXMLDOMDocument **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d748`

## callees

- `0x180002bf0`
- `0x180002f24`
- `0x1800032ec`
- `0x18000331c`
- `0x1800180a6`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180002fb0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180002fb0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180002fec`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180002fec`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x180003002`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x180003002`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180003021`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180003021`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180002fcf`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180002fcf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000311c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000314b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000311c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000314b`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180003179`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180003179`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180003035`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180003035`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180003080`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180003080`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000304f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000304f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180003143`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180003143`

## pseudocode

```c
__int64 __fastcall SDiagPrviLoadXsdResource(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        struct IXMLDOMDocument **a3)
{
  void *v3; // rdi
  int v5; // ebx
  HRSRC Resource; // rbx
  char *v7; // rcx
  const void *v8; // r15
  DWORD v9; // eax
  DWORD v10; // ebx
  char *v11; // rax
  char *v12; // rax
  char *v13; // rsi
  struct IXMLDOMDocumentVtbl *lpVtbl; // rax
  signed int LastError; // eax
  signed int v16; // eax
  struct IXMLDOMDocument *v18; // [rsp+20h] [rbp-40h] BYREF
  struct tagVARIANT v19; // [rsp+28h] [rbp-38h] BYREF
  struct tagVARIANT v20; // [rsp+40h] [rbp-20h] BYREF
  LPSTREAM ppstm; // [rsp+90h] [rbp+30h] BYREF
  const unsigned __int16 *v22; // [rsp+98h] [rbp+38h] BYREF
  HMODULE phModule; // [rsp+A8h] [rbp+48h] BYREF

  v22 = a2;
  phModule = 0;
  v3 = 0;
  ppstm = 0;
  v18 = 0;
  LOWORD(v22) = -1;
  memset(&v19, 0, sizeof(v19));
  v5 = SDiagPrviVariantInit(&v19);
  if ( v5 >= 0 )
  {
    if ( !a3 )
    {
      v5 = -2147024809;
      goto LABEL_29;
    }
    *a3 = 0;
    v5 = SDiagPrviCreateXmlDocument(&v18);
    if ( v5 < 0 )
      goto LABEL_29;
    if ( !GetModuleHandleExW(2u, L"sdiagprv", &phModule) )
      goto LABEL_25;
    Resource = FindResourceExW(phModule, (LPCWSTR)0xA, L"DiagnosticPackageCatalog.xsd", 0);
    if ( (unsigned __int64)Resource - 1 > 0xFFFFFFFFFFFFFFFDuLL )
      goto LABEL_25;
    v7 = (char *)LoadResource(phModule, Resource);
    if ( (unsigned __int64)(v7 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      goto LABEL_25;
    v8 = LockResource(v7);
    if ( !v8 )
    {
      v5 = -2147467259;
      goto LABEL_29;
    }
    v9 = SizeofResource(phModule, Resource);
    if ( v9
      && (v10 = v9, v11 = (char *)GlobalAlloc(2u, v9), v3 = v11, (unsigned __int64)(v11 - 1) <= 0xFFFFFFFFFFFFFFFDuLL) )
    {
      v12 = (char *)GlobalLock(v11);
      v13 = v12;
      if ( (unsigned __int64)(v12 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        memcpy_0(v12, v8, v10);
        v5 = CreateStreamOnHGlobal(v3, 1, &ppstm);
        if ( v5 >= 0 )
        {
          v19.vt = 13;
          v5 = (**(__int64 (__fastcall ***)(LPSTREAM, GUID *, ULONG *))ppstm)(ppstm, &IID_IUnknown, (ULONG *)&v19.cyVal);
          if ( v5 >= 0 )
          {
            lpVtbl = v18->lpVtbl;
            v20 = v19;
            v5 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, struct tagVARIANT *, const unsigned __int16 **))lpVtbl->load)(
                   v18,
                   &v20,
                   &v22);
            if ( v5 >= 0 )
            {
              if ( (_WORD)v22 )
                v5 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, GUID *, struct IXMLDOMDocument **))v18->lpVtbl->QueryInterface)(
                       v18,
                       &IID_IXMLDOMDocument,
                       a3);
              else
                v5 = -2147467259;
            }
          }
        }
LABEL_24:
        GlobalUnlock(v3);
        goto LABEL_29;
      }
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( v5 >= 0 )
        v5 = -2147467259;
      if ( v13 )
        goto LABEL_24;
    }
    else
    {
LABEL_25:
      v16 = GetLastError();
      v5 = v16;
      if ( v16 > 0 )
        v5 = (unsigned __int16)v16 | 0x80070000;
      if ( v5 >= 0 )
        v5 = -2147467259;
    }
  }
LABEL_29:
  if ( !ppstm && v3 )
    GlobalFree(v3);
  SDiagPrviVariantClear(&v19);
  if ( ppstm )
  {
    (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    ppstm = 0;
  }
  if ( v18 )
    ((void (__fastcall *)(struct IXMLDOMDocument *))v18->lpVtbl->Release)(v18);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180002f24  mov     [rsp-28h+arg_10], rbx
0x180002f29  mov     [rsp-28h+arg_8], rdx
0x180002f2e  mov     [rsp-28h+ppstm], rcx
0x180002f33  push    rbp
0x180002f34  push    rsi
0x180002f35  push    rdi
0x180002f36  push    r14
0x180002f38  push    r15
0x180002f3a  mov     rbp, rsp
0x180002f3d  sub     rsp, 60h
0x180002f41  xor     eax, eax
0x180002f43  lea     rcx, [rbp+var_38]; struct tagVARIANT *
0x180002f47  mov     qword ptr [rbp+var_38+10h], rax
0x180002f4b  xorps   xmm0, xmm0
0x180002f4e  mov     [rbp+phModule], rax
0x180002f52  xor     edi, edi
0x180002f54  mov     [rbp+ppstm], rax
0x180002f58  mov     r14, r8
0x180002f5b  or      eax, 0FFFFFFFFh
0x180002f5e  mov     [rbp+var_40], rdi
0x180002f62  mov     word ptr [rbp+arg_8], ax
0x180002f66  movups  xmmword ptr [rbp+var_38], xmm0
0x180002f6a  call    ?SDiagPrviVariantInit@@YAJPEAUtagVARIANT@@@Z; SDiagPrviVariantInit(tagVARIANT *)
0x180002f6f  mov     ebx, eax
0x180002f71  test    eax, eax
0x180002f73  js      loc_18000316A
0x180002f79  test    r14, r14
0x180002f7c  jnz     short loc_180002F88
0x180002f7e  mov     ebx, 80070057h
0x180002f83  jmp     loc_18000316A
0x180002f88  lea     rcx, [rbp+var_40]; struct IXMLDOMDocument **
0x180002f8c  mov     [r14], rdi
0x180002f8f  call    ?SDiagPrviCreateXmlDocument@@YAJPEAPEAUIXMLDOMDocument@@@Z; SDiagPrviCreateXmlDocument(IXMLDOMDocument * *)
0x180002f94  mov     ebx, eax
0x180002f96  test    eax, eax
0x180002f98  js      loc_18000316A
0x180002f9e  mov     esi, 2
0x180002fa3  lea     r8, [rbp+phModule]; phModule
0x180002fa7  mov     ecx, esi; dwFlags
0x180002fa9  lea     rdx, ModuleName; "sdiagprv"
0x180002fb0  call    cs:__imp_GetModuleHandleExW
0x180002fb6  test    eax, eax
0x180002fb8  jz      loc_18000314B
0x180002fbe  mov     rcx, [rbp+phModule]; hModule
0x180002fc2  lea     r8, Name; "DiagnosticPackageCatalog.xsd"
0x180002fc9  xor     r9d, r9d; wLanguage
0x180002fcc  lea     edx, [rsi+8]; lpType
0x180002fcf  call    cs:__imp_FindResourceExW
0x180002fd5  mov     rbx, rax
0x180002fd8  dec     rax
0x180002fdb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180002fdf  ja      loc_18000314B
0x180002fe5  mov     rcx, [rbp+phModule]; hModule
0x180002fe9  mov     rdx, rbx; hResInfo
0x180002fec  call    cs:__imp_LoadResource
0x180002ff2  mov     rcx, rax; hResData
0x180002ff5  dec     rax
0x180002ff8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180002ffc  ja      loc_18000314B
0x180003002  call    cs:__imp_LockResource
0x180003008  mov     r15, rax
0x18000300b  test    rax, rax
0x18000300e  jnz     short loc_18000301A
0x180003010  mov     ebx, 80004005h
0x180003015  jmp     loc_18000316A
0x18000301a  mov     rcx, [rbp+phModule]; hModule
0x18000301e  mov     rdx, rbx; hResInfo
0x180003021  call    cs:__imp_SizeofResource
0x180003027  test    eax, eax
0x180003029  jz      loc_18000314B
0x18000302f  mov     edx, eax; dwBytes
0x180003031  mov     ecx, esi; uFlags
0x180003033  mov     ebx, eax
0x180003035  call    cs:__imp_GlobalAlloc
0x18000303b  mov     rdi, rax
0x18000303e  lea     rcx, [rax-1]
0x180003042  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180003046  ja      loc_18000314B
0x18000304c  mov     rcx, rax; hMem
0x18000304f  call    cs:__imp_GlobalLock
0x180003055  mov     rsi, rax
0x180003058  lea     rcx, [rax-1]
0x18000305c  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180003060  ja      loc_18000311C
0x180003066  mov     r8d, ebx; Size
0x180003069  mov     rdx, r15; Src
0x18000306c  mov     rcx, rax; void *
0x18000306f  call    memcpy_0
0x180003074  lea     r8, [rbp+ppstm]; ppstm
0x180003078  mov     edx, 1; fDeleteOnRelease
0x18000307d  mov     rcx, rdi; hGlobal
0x180003080  call    cs:__imp_CreateStreamOnHGlobal
0x180003086  mov     ebx, eax
0x180003088  test    eax, eax
0x18000308a  js      loc_180003140
0x180003090  mov     rcx, [rbp+ppstm]
0x180003094  lea     r8, [rbp+var_38+8]
0x180003098  mov     eax, 0Dh
0x18000309d  lea     rdx, IID_IUnknown
0x1800030a4  mov     word ptr [rbp+var_38], ax
0x1800030a8  mov     rax, [rcx]
0x1800030ab  mov     rax, [rax]
0x1800030ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030b3  mov     ebx, eax
0x1800030b5  test    eax, eax
0x1800030b7  js      loc_180003140
0x1800030bd  mov     rcx, [rbp+var_40]
0x1800030c1  lea     r8, [rbp+arg_8]
0x1800030c5  movups  xmm0, xmmword ptr [rbp+var_38]
0x1800030c9  lea     rdx, [rbp+var_20]
0x1800030cd  movsd   xmm1, qword ptr [rbp+var_38+10h]
0x1800030d2  mov     rax, [rcx]
0x1800030d5  movaps  [rbp+var_20], xmm0
0x1800030d9  movsd   [rbp+var_10], xmm1
0x1800030de  mov     rax, [rax+1D0h]
0x1800030e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030ea  mov     ebx, eax
0x1800030ec  test    eax, eax
0x1800030ee  js      short loc_180003140
0x1800030f0  xor     eax, eax
0x1800030f2  cmp     ax, word ptr [rbp+arg_8]
0x1800030f6  jnz     short loc_1800030FF
0x1800030f8  mov     ebx, 80004005h
0x1800030fd  jmp     short loc_180003140
0x1800030ff  mov     rcx, [rbp+var_40]
0x180003103  lea     rdx, IID_IXMLDOMDocument
0x18000310a  mov     r8, r14
0x18000310d  mov     rax, [rcx]
0x180003110  mov     rax, [rax]
0x180003113  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003118  mov     ebx, eax
0x18000311a  jmp     short loc_180003140
0x18000311c  call    cs:__imp_GetLastError
0x180003122  mov     ebx, eax
0x180003124  test    eax, eax
0x180003126  jle     short loc_180003131
0x180003128  movzx   ebx, ax
0x18000312b  or      ebx, 80070000h
0x180003131  test    ebx, ebx
0x180003133  mov     eax, 80004005h
0x180003138  cmovns  ebx, eax
0x18000313b  test    rsi, rsi
0x18000313e  jz      short loc_18000316A
0x180003140  mov     rcx, rdi; hMem
0x180003143  call    cs:__imp_GlobalUnlock
0x180003149  jmp     short loc_18000316A
0x18000314b  call    cs:__imp_GetLastError
0x180003151  mov     ebx, eax
0x180003153  test    eax, eax
0x180003155  jle     short loc_180003160
0x180003157  movzx   ebx, ax
0x18000315a  or      ebx, 80070000h
0x180003160  test    ebx, ebx
0x180003162  mov     eax, 80004005h
0x180003167  cmovns  ebx, eax
0x18000316a  cmp     [rbp+ppstm], 0
0x18000316f  jnz     short loc_18000317F
0x180003171  test    rdi, rdi
0x180003174  jz      short loc_18000317F
0x180003176  mov     rcx, rdi; hMem
0x180003179  call    cs:__imp_GlobalFree
0x18000317f  lea     rcx, [rbp+var_38]; struct tagVARIANT *
0x180003183  call    ?SDiagPrviVariantClear@@YAJPEAUtagVARIANT@@@Z; SDiagPrviVariantClear(tagVARIANT *)
0x180003188  mov     rcx, [rbp+ppstm]
0x18000318c  test    rcx, rcx
0x18000318f  jz      short loc_1800031A5
0x180003191  mov     rax, [rcx]
0x180003194  mov     rax, [rax+10h]
0x180003198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000319d  mov     [rbp+ppstm], 0
0x1800031a5  mov     rcx, [rbp+var_40]
0x1800031a9  test    rcx, rcx
0x1800031ac  jz      short loc_1800031BA
0x1800031ae  mov     rax, [rcx]
0x1800031b1  mov     rax, [rax+10h]
0x1800031b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031ba  mov     eax, ebx
0x1800031bc  mov     rbx, [rsp+60h+arg_10]
0x1800031c4  add     rsp, 60h
0x1800031c8  pop     r15
0x1800031ca  pop     r14
0x1800031cc  pop     rdi
0x1800031cd  pop     rsi
0x1800031ce  pop     rbp
0x1800031cf  retn
```
