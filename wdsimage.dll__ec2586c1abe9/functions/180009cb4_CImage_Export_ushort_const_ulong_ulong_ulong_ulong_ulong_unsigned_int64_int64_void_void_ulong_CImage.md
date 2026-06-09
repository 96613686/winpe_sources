# CImage::Export(ushort const *,ulong,ulong,ulong,ulong (*)(ulong,unsigned __int64,__int64,void *),void *,ulong *,CImage * *)

- ea: `0x180009cb4`
- end: `0x18000a016`
- name: `?Export@CImage@@QEAAJPEBGKKKP6AKK_K_JPEAX@Z3PEAKPEAPEAV1@@Z`
- size: `866`
- prototype: `__int64 __usercall@<rax>(CImage *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int, unsigned int (*)(unsigned int, unsigned __int64, __int64, void *), void *, unsigned int *, struct CImage **)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800043d0`

## callees

- `0x180001588`
- `0x1800039a8`
- `0x180009cb4`
- `0x18000ae64`
- `0x18000c35c`
- `0x18000cf80`
- `0x18000d5b0`
- `0x18000d6b0`
- `0x180011010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180009fe6`
- `msvcrt!??3@YAXPEAX@Z` at `0x180009fe6`
- `KERNEL32!DeleteFileW` at `0x180009e37`
- `KERNEL32!DeleteFileW` at `0x180009e37`
- `KERNEL32!GetFileAttributesW` at `0x180009d46`
- `KERNEL32!GetFileAttributesW` at `0x180009d46`
- `KERNEL32!GetLastError` at `0x180009e4b`
- `KERNEL32!GetLastError` at `0x180009e4b`
- `WdsCommonLib!WdsGetParentFolderPathOfFile` at `0x180009dc3`
- `WdsCommonLib!WdsGetParentFolderPathOfFile` at `0x180009dc3`
- `WdsCommonLib!GetFileNameFromPath` at `0x180009e88`
- `WdsCommonLib!GetFileNameFromPath` at `0x180009e88`

## pseudocode

```c
__int64 __fastcall CImage::Export(
        CImage *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int (*a6)(unsigned int, unsigned __int64, __int64, void *),
        void *a7,
        unsigned int *a8,
        struct CImage **a9)
{
  bool v9; // zf
  unsigned int v14; // r15d
  __int64 v15; // rbx
  __int64 v16; // rdx
  int v17; // esi
  __int64 v18; // rdx
  __int64 v19; // r8
  DWORD LastError; // eax
  __int64 v21; // rdx
  __int64 v22; // r8
  int v23; // eax
  __int64 FileNameFromPath; // rax
  __int64 v25; // rdx
  int v26; // ecx
  int v27; // ecx
  int v28; // ecx
  __int64 v29; // rdx
  __int64 v30; // rdx
  CImage *v31; // rax
  CImage *v32; // rax
  struct CImage *v33; // rdi
  __int64 v34; // rdx
  void *v36; // [rsp+20h] [rbp-60h] BYREF
  __int128 v37; // [rsp+30h] [rbp-50h] BYREF
  __int64 v38; // [rsp+40h] [rbp-40h]
  unsigned __int64 v39; // [rsp+48h] [rbp-38h]
  int v40; // [rsp+50h] [rbp-30h]
  unsigned int (*v41)(unsigned int, unsigned __int64, __int64, void *); // [rsp+58h] [rbp-28h]
  void *v42; // [rsp+60h] [rbp-20h]
  __int64 v43; // [rsp+68h] [rbp-18h]
  __int64 v44; // [rsp+70h] [rbp-10h]
  unsigned int v45; // [rsp+B0h] [rbp+30h] BYREF

  v9 = *((_DWORD *)this + 7) == 2;
  v45 = 0;
  v36 = 0;
  v37 = 0;
  v14 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  if ( !v9 && a5 != 256 )
  {
    LODWORD(v15) = -2147024809;
    if ( (int)ElValidateHr_5(2147942487LL, a2, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 2742) < 0 )
      goto LABEL_41;
  }
  if ( GetFileAttributesW(a2) == -1 )
  {
    v17 = 0;
    if ( a3 == 3 )
    {
      LODWORD(v15) = -1056833013;
      if ( (int)ElValidateHr_5(3238134283LL, v16, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 2763) < 0 )
        goto LABEL_41;
      v17 = 0;
    }
    goto LABEL_8;
  }
  v17 = 1;
  if ( a3 == 1 )
  {
    LODWORD(v15) = -1056833014;
    if ( (int)ElValidateHr_5(3238134282LL, v16, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 2757) < 0 )
      goto LABEL_41;
LABEL_8:
    if ( ((*((_DWORD *)this + 7) - 1) & 0xFFFFFFFD) == 0 && a3 == 3 )
    {
      if ( v17 )
      {
        LODWORD(v15) = -1056832995;
        if ( (int)ElValidateHr_5(3238134301LL, v16, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 2786) < 0 )
          goto LABEL_41;
      }
    }
    LODWORD(v15) = WdsGetParentFolderPathOfFile(a2, &v36);
    if ( (unsigned int)ElValidateWin32_4((unsigned int)v15, v18, v19, 2795) )
    {
      if ( (int)v15 > 0 )
        LODWORD(v15) = (unsigned __int16)v15 | 0x80070000;
      goto LABEL_41;
    }
    FileNameFromPath = GetFileNameFromPath(a2);
    v26 = *((_DWORD *)this + 7);
    v38 = FileNameFromPath;
    *((_QWORD *)&v37 + 1) = v36;
    v41 = a6;
    v42 = a7;
    v39 = __PAIR64__(a3, a4);
    v27 = v26 - 1;
    if ( v27 )
    {
      v28 = v27 - 1;
      if ( !v28 )
      {
        LODWORD(v15) = CImage::WimExport(this, (struct WdsImgCopyParams *)&v37, a5, &v45);
        if ( (int)ElValidateHr_5((unsigned int)v15, v29, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 2816) < 0 )
          goto LABEL_41;
        v14 = 1056;
LABEL_33:
        v31 = (CImage *)operator new(0x190u, (const struct std::nothrow_t *)&std::nothrow);
        if ( v31 && (v32 = CImage::CImage(v31), (v33 = v32) != 0) )
        {
          v15 = (unsigned int)CImage::Initialize(v32, a2, v45, v14);
          if ( (int)ElValidateHr_5(v15, v34, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 2857) < 0 )
          {
            (*(void (__fastcall **)(struct CImage *))(*(_QWORD *)v33 + 8LL))(v33);
          }
          else
          {
            if ( a8 )
              *a8 = v17 != 0;
            *a9 = v33;
          }
        }
        else
        {
          LODWORD(v15) = -2147024882;
        }
        goto LABEL_41;
      }
      if ( v28 != 1 )
      {
        LODWORD(v15) = -2147024883;
        if ( (int)ElValidateHr_5(2147942413LL, v25, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 2844) < 0 )
          goto LABEL_41;
        goto LABEL_33;
      }
    }
    LODWORD(v15) = CImage::VhdExport(this, (struct WdsImgCopyParams *)&v37, &v45);
    if ( (int)ElValidateHr_5((unsigned int)v15, v30, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 2829) < 0 )
      goto LABEL_41;
    v14 = 16;
    goto LABEL_33;
  }
  if ( a3 != 2 || DeleteFileW(a2) )
    goto LABEL_8;
  LastError = GetLastError();
  v23 = ElValidateWin32_4(LastError, v21, v22, 2773);
  LODWORD(v15) = v23;
  if ( v23 > 0 )
    LODWORD(v15) = (unsigned __int16)v23 | 0x80070000;
  if ( (int)v15 >= 0 )
    LODWORD(v15) = -2147467259;
LABEL_41:
  if ( v36 )
    operator delete(v36);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180009cb4  mov     [rsp-28h+arg_8], rbx
0x180009cb9  mov     [rsp-28h+arg_10], rsi
0x180009cbe  mov     [rsp-28h+arg_18], rdi
0x180009cc3  push    rbp
0x180009cc4  push    r12
0x180009cc6  push    r13
0x180009cc8  push    r14
0x180009cca  push    r15
0x180009ccc  mov     rbp, rsp
0x180009ccf  sub     rsp, 80h
0x180009cd6  xor     ebx, ebx
0x180009cd8  xorps   xmm0, xmm0
0x180009cdb  cmp     dword ptr [rcx+1Ch], 2
0x180009cdf  mov     r13d, r9d
0x180009ce2  mov     edi, r8d
0x180009ce5  mov     [rbp+arg_0], ebx
0x180009ce8  mov     r12, rdx
0x180009ceb  mov     [rbp+var_60], rbx
0x180009cef  mov     r14, rcx
0x180009cf2  movdqa  [rbp+var_50], xmm0
0x180009cf7  mov     r15d, ebx
0x180009cfa  mov     [rbp+var_40], rbx
0x180009cfe  mov     [rbp+var_38], rbx
0x180009d02  mov     [rbp+var_30], ebx
0x180009d05  mov     [rbp+var_28], rbx
0x180009d09  mov     [rbp+var_20], rbx
0x180009d0d  mov     [rbp+var_18], rbx
0x180009d11  mov     [rbp+var_10], rbx
0x180009d15  jz      short loc_180009D43
0x180009d17  cmp     [rbp+arg_20], 100h
0x180009d1e  jz      short loc_180009D43
0x180009d20  mov     ebx, 80070057h
0x180009d25  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x180009d2c  mov     ecx, ebx
0x180009d2e  mov     r9d, 0AB6h
0x180009d34  call    ElValidateHr_5
0x180009d39  test    eax, eax
0x180009d3b  js      loc_180009FDD
0x180009d41  xor     ebx, ebx
0x180009d43  mov     rcx, r12; lpFileName
0x180009d46  call    cs:__imp_GetFileAttributesW
0x180009d4d  nop     dword ptr [rax+rax+00h]
0x180009d52  cmp     eax, 0FFFFFFFFh
0x180009d55  jnz     loc_180009DFC
0x180009d5b  mov     esi, ebx
0x180009d5d  cmp     edi, 3
0x180009d60  jnz     short loc_180009D85
0x180009d62  mov     ebx, 0C102020Bh
0x180009d67  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x180009d6e  mov     ecx, ebx
0x180009d70  mov     r9d, 0ACBh
0x180009d76  call    ElValidateHr_5
0x180009d7b  test    eax, eax
0x180009d7d  js      loc_180009FDD
0x180009d83  xor     esi, esi
0x180009d85  mov     eax, [r14+1Ch]
0x180009d89  dec     eax
0x180009d8b  test    eax, 0FFFFFFFDh
0x180009d90  jnz     short loc_180009DBC
0x180009d92  cmp     edi, 3
0x180009d95  jnz     short loc_180009DBC
0x180009d97  test    esi, esi
0x180009d99  jz      short loc_180009DBC
0x180009d9b  mov     ebx, 0C102021Dh
0x180009da0  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x180009da7  mov     ecx, ebx
0x180009da9  mov     r9d, 0AE2h
0x180009daf  call    ElValidateHr_5
0x180009db4  test    eax, eax
0x180009db6  js      loc_180009FDD
0x180009dbc  lea     rdx, [rbp+var_60]
0x180009dc0  mov     rcx, r12
0x180009dc3  call    cs:__imp_WdsGetParentFolderPathOfFile
0x180009dca  nop     dword ptr [rax+rax+00h]
0x180009dcf  mov     ecx, eax
0x180009dd1  mov     r9d, 0AEBh
0x180009dd7  mov     ebx, eax
0x180009dd9  call    ElValidateWin32_4
0x180009dde  test    eax, eax
0x180009de0  jz      loc_180009E85
0x180009de6  test    ebx, ebx
0x180009de8  jle     loc_180009FDD
0x180009dee  movzx   ebx, bx
0x180009df1  or      ebx, 80070000h
0x180009df7  jmp     loc_180009FDD
0x180009dfc  mov     esi, 1
0x180009e01  cmp     edi, esi
0x180009e03  jnz     short loc_180009E2B
0x180009e05  mov     ebx, 0C102020Ah
0x180009e0a  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x180009e11  mov     ecx, ebx
0x180009e13  mov     r9d, 0AC5h
0x180009e19  call    ElValidateHr_5
0x180009e1e  test    eax, eax
0x180009e20  js      loc_180009FDD
0x180009e26  jmp     loc_180009D85
0x180009e2b  cmp     edi, 2
0x180009e2e  jnz     loc_180009D85
0x180009e34  mov     rcx, r12; lpFileName
0x180009e37  call    cs:__imp_DeleteFileW
0x180009e3e  nop     dword ptr [rax+rax+00h]
0x180009e43  test    eax, eax
0x180009e45  jnz     loc_180009D85
0x180009e4b  call    cs:__imp_GetLastError
0x180009e52  nop     dword ptr [rax+rax+00h]
0x180009e57  mov     ecx, eax
0x180009e59  mov     r9d, 0AD5h
0x180009e5f  call    ElValidateWin32_4
0x180009e64  mov     ebx, eax
0x180009e66  test    eax, eax
0x180009e68  jle     short loc_180009E73
0x180009e6a  movzx   ebx, ax
0x180009e6d  or      ebx, 80070000h
0x180009e73  test    ebx, ebx
0x180009e75  js      loc_180009FDD
0x180009e7b  mov     ebx, 80004005h
0x180009e80  jmp     loc_180009FDD
0x180009e85  mov     rcx, r12
0x180009e88  call    cs:__imp_GetFileNameFromPath
0x180009e8f  nop     dword ptr [rax+rax+00h]
0x180009e94  mov     ecx, [r14+1Ch]
0x180009e98  mov     [rbp+var_40], rax
0x180009e9c  mov     rax, [rbp+var_60]
0x180009ea0  mov     qword ptr [rbp+var_50+8], rax
0x180009ea4  mov     rax, [rbp+arg_28]
0x180009ea8  mov     [rbp+var_28], rax
0x180009eac  mov     rax, [rbp+arg_30]
0x180009eb0  mov     [rbp+var_20], rax
0x180009eb4  mov     dword ptr [rbp+var_38+4], edi
0x180009eb7  mov     dword ptr [rbp+var_38], r13d
0x180009ebb  sub     ecx, 1
0x180009ebe  jz      short loc_180009F26
0x180009ec0  sub     ecx, 1
0x180009ec3  jz      short loc_180009EEC
0x180009ec5  cmp     ecx, 1
0x180009ec8  jz      short loc_180009F26
0x180009eca  mov     ebx, 8007000Dh
0x180009ecf  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x180009ed6  mov     ecx, ebx
0x180009ed8  mov     r9d, 0B1Ch
0x180009ede  call    ElValidateHr_5
0x180009ee3  test    eax, eax
0x180009ee5  jns     short loc_180009F5A
0x180009ee7  jmp     loc_180009FDD
0x180009eec  mov     r8d, [rbp+arg_20]; unsigned int
0x180009ef0  lea     r9, [rbp+arg_0]; unsigned int *
0x180009ef4  lea     rdx, [rbp+var_50]; struct WdsImgCopyParams *
0x180009ef8  mov     rcx, r14; this
0x180009efb  call    ?WimExport@CImage@@AEAAJPEAUWdsImgCopyParams@@KPEAK@Z; CImage::WimExport(WdsImgCopyParams *,ulong,ulong *)
0x180009f00  mov     r9d, 0B00h
0x180009f06  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x180009f0d  mov     ecx, eax
0x180009f0f  mov     ebx, eax
0x180009f11  call    ElValidateHr_5
0x180009f16  test    eax, eax
0x180009f18  js      loc_180009FDD
0x180009f1e  mov     r15d, 420h
0x180009f24  jmp     short loc_180009F5A
0x180009f26  lea     r8, [rbp+arg_0]; unsigned int *
0x180009f2a  mov     rcx, r14; this
0x180009f2d  lea     rdx, [rbp+var_50]; struct WdsImgCopyParams *
0x180009f31  call    ?VhdExport@CImage@@AEAAJPEAUWdsImgCopyParams@@PEAK@Z; CImage::VhdExport(WdsImgCopyParams *,ulong *)
0x180009f36  mov     r9d, 0B0Dh
0x180009f3c  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x180009f43  mov     ecx, eax
0x180009f45  mov     ebx, eax
0x180009f47  call    ElValidateHr_5
0x180009f4c  test    eax, eax
0x180009f4e  js      loc_180009FDD
0x180009f54  mov     r15d, 10h
0x180009f5a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009f61  mov     ecx, 190h; unsigned __int64
0x180009f66  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180009f6b  test    rax, rax
0x180009f6e  jz      short loc_180009FD8
0x180009f70  mov     rcx, rax; this
0x180009f73  call    ??0CImage@@QEAA@XZ; CImage::CImage(void)
0x180009f78  mov     rdi, rax
0x180009f7b  test    rax, rax
0x180009f7e  jz      short loc_180009FD8
0x180009f80  mov     r8d, [rbp+arg_0]; unsigned int
0x180009f84  mov     r9d, r15d; unsigned int
0x180009f87  mov     rdx, r12; unsigned __int16 *
0x180009f8a  mov     rcx, rax; this
0x180009f8d  call    ?Initialize@CImage@@QEAAJPEBGKK@Z; CImage::Initialize(ushort const *,ulong,ulong)
0x180009f92  mov     r9d, 0B29h
0x180009f98  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x180009f9f  mov     ecx, eax
0x180009fa1  mov     ebx, eax
0x180009fa3  call    ElValidateHr_5
0x180009fa8  test    eax, eax
0x180009faa  js      short loc_180009FC7
0x180009fac  mov     rcx, [rbp+arg_38]
0x180009fb0  test    rcx, rcx
0x180009fb3  jz      short loc_180009FBE
0x180009fb5  xor     eax, eax
0x180009fb7  test    esi, esi
0x180009fb9  setnz   al
0x180009fbc  mov     [rcx], eax
0x180009fbe  mov     rax, [rbp+arg_40]
0x180009fc2  mov     [rax], rdi
0x180009fc5  jmp     short loc_180009FDD
0x180009fc7  mov     rax, [rdi]
0x180009fca  mov     rcx, rdi
0x180009fcd  mov     rax, [rax+8]
0x180009fd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fd6  jmp     short loc_180009FDD
0x180009fd8  mov     ebx, 8007000Eh
0x180009fdd  mov     rcx, [rbp+var_60]
0x180009fe1  test    rcx, rcx
0x180009fe4  jz      short loc_180009FF2
0x180009fe6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180009fed  nop     dword ptr [rax+rax+00h]
0x180009ff2  lea     r11, [rsp+80h+var_s0]
0x180009ffa  mov     eax, ebx
0x180009ffc  mov     rbx, [r11+38h]
0x18000a000  mov     rsi, [r11+40h]
0x18000a004  mov     rdi, [r11+48h]
0x18000a008  mov     rsp, r11
0x18000a00b  pop     r15
0x18000a00d  pop     r14
0x18000a00f  pop     r13
0x18000a011  pop     r12
0x18000a013  pop     rbp
0x18000a014  retn
```
