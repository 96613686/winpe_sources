# XPerf::Internal::CvDbgInfoFromImage2(ushort const *,void *,ulong,ulong,bool,ulong *,_CVDD *,ulong *,CODEVIEW_INFORMATION_1 *,ulong *,ulong *,ushort *,ulong,bool &,bool,EMBEDDED_PDB_INFORMATION &,bool &,XPerfCore::IErrorMessage *)

- ea: `0x18002fae4`
- end: `0x18002ffc2`
- name: `?CvDbgInfoFromImage2@Internal@XPerf@@YAJPEBGPEAXKK_NPEAKPEAT_CVDD@@3PEAUCODEVIEW_INFORMATION_1@@33PEAGKAEA_N2AEAUEMBEDDED_PDB_INFORMATION@@7PEAVIErrorMessage@XPerfCore@@@Z`
- size: `1246`
- prototype: `__int64 __fastcall(XPerf::Internal *__hidden this, const unsigned __int16 *, void *, unsigned int, unsigned int, unsigned int *, union _CVDD *, union _CVDD *, struct CODEVIEW_INFORMATION_1 *, struct CODEVIEW_INFORMATION_1 *, unsigned int *, unsigned int *, unsigned __int16 *, unsigned int, BOOLEAN MappedAsImage, struct EMBEDDED_PDB_INFORMATION *, struct EMBEDDED_PDB_INFORMATION *, bool *, struct XPerfCore::IErrorMessage *)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180016698`
- `0x18003085c`

## callees

- `0x1800059d8`
- `0x18000abfc`
- `0x180027a64`
- `0x18002fae4`
- `0x18002ffc8`
- `0x1800304c8`
- `0x1800305dc`
- `0x1800307f0`
- `0x1800309b4`
- `0x180034010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18002fed5`
- `msvcrt!wcsrchr` at `0x18002fed5`
- `ntdll!RtlImageDirectoryEntryToData` at `0x18002fcb6`
- `ntdll!RtlImageDirectoryEntryToData` at `0x18002fcb6`

## pseudocode

```c
__int64 __fastcall XPerf::Internal::CvDbgInfoFromImage2(
        XPerf::Internal *this,
        char *a2,
        void *a3,
        __int64 a4,
        unsigned int a5,
        unsigned int *a6,
        union _CVDD *a7,
        union _CVDD *a8,
        struct CODEVIEW_INFORMATION_1 *a9,
        struct CODEVIEW_INFORMATION_1 *a10,
        unsigned int *a11,
        unsigned __int16 *a12,
        unsigned __int16 *a13,
        _BYTE *a14,
        BOOLEAN MappedAsImage,
        struct EMBEDDED_PDB_INFORMATION *a16,
        struct EMBEDDED_PDB_INFORMATION *a17,
        bool *a18)
{
  unsigned int *v18; // r12
  union _CVDD *v19; // rbx
  struct EMBEDDED_PDB_INFORMATION *v20; // r13
  unsigned __int16 *v21; // r14
  __int64 v22; // rax
  int v23; // r9d
  unsigned int *v24; // r10
  struct _IMAGE_NT_HEADERS64 *v25; // rsi
  __int64 result; // rax
  int v27; // eax
  DWORD TimeDateStamp; // edx
  unsigned int SizeOfImage; // ecx
  BOOLEAN v30; // r15
  _BYTE *v31; // rax
  int v32; // eax
  union _CVDD *v33; // rsi
  unsigned int v34; // ecx
  int v35; // r9d
  unsigned int i; // edx
  __int64 v37; // r8
  wchar_t *v38; // rax
  __int64 v39; // rax
  bool v40; // [rsp+20h] [rbp-B8h]
  ULONG Size; // [rsp+70h] [rbp-68h] BYREF
  int v42; // [rsp+74h] [rbp-64h]
  int v43; // [rsp+78h] [rbp-60h]
  unsigned int v44; // [rsp+7Ch] [rbp-5Ch]
  int v45; // [rsp+80h] [rbp-58h]
  DWORD v46; // [rsp+84h] [rbp-54h]
  unsigned int v47; // [rsp+88h] [rbp-50h]
  int v48; // [rsp+8Ch] [rbp-4Ch]
  DWORD v49; // [rsp+90h] [rbp-48h]
  unsigned int v50; // [rsp+94h] [rbp-44h]
  signed __int64 v51; // [rsp+98h] [rbp-40h]
  unsigned int v54; // [rsp+F0h] [rbp+18h]

  v54 = (unsigned int)a3;
  v18 = a6;
  v19 = a7;
  v20 = a16;
  *(_OWORD *)a16 = 0;
  *((_QWORD *)v20 + 2) = 0;
  *(_BYTE *)a17 = 0;
  v21 = a12;
  if ( a12 )
    *a12 = 0;
  v22 = XPerfCore::_SafeImageNtHeader(a2, (unsigned int)a3);
  v25 = (struct _IMAGE_NT_HEADERS64 *)v22;
  if ( !v22 )
  {
    if ( a18 )
      (*(void (__fastcall **)(bool *, const wchar_t *))(*(_QWORD *)a18 + 8LL))(a18, L"Invalid executable format.");
    return ATL::AtlHresultFromWin32(0xC1u);
  }
  v27 = *(_DWORD *)(v22 + 88);
  v45 = v27;
  v48 = v27;
  TimeDateStamp = v25->FileHeader.TimeDateStamp;
  v46 = TimeDateStamp;
  v49 = TimeDateStamp;
  SizeOfImage = v25->OptionalHeader.SizeOfImage;
  v47 = SizeOfImage;
  v50 = SizeOfImage;
  if ( v23 && v27 != v23 )
  {
    if ( a18 )
      (*(void (__fastcall **)(bool *, const wchar_t *))(*(_QWORD *)a18 + 8LL))(a18, L"Invalid image header checksum.");
    return ATL::AtlHresultFromWin32(0xDu);
  }
  if ( a10 )
    *(_DWORD *)a10 = TimeDateStamp;
  if ( a11 )
    *a11 = SizeOfImage;
  if ( v25->OptionalHeader.Magic == 267 )
  {
    *a14 = 0;
  }
  else
  {
    if ( v25->OptionalHeader.Magic != 523 )
      return 2147549183LL;
    *a14 = 1;
  }
  v30 = MappedAsImage;
  if ( (unsigned int)SymCommonNativeResourceOnlyDll(v24, MappedAsImage) )
    goto LABEL_24;
  v43 = v25->FileHeader.Characteristics & 0x200;
  v42 = SymCommonTlbImpManagedDll(a2, v25, v30);
  Size = 0;
  v31 = RtlImageDirectoryEntryToData(a2, v30, 6u, &Size);
  if ( v31 )
  {
    v51 = v31 - a2;
    a5 = -1;
    v33 = a8;
    result = CvInfoFromDbgDir(
               a2,
               v54,
               Size,
               (int)v31 - (int)a2,
               v40,
               &a5,
               v18,
               v19,
               (unsigned int *)a8,
               a9,
               v30,
               v20,
               (bool *)a17);
    if ( (int)result < 0 )
      return result;
    v34 = *v18;
    v35 = v42;
    if ( *v18 > 1 )
    {
      if ( v42 == 1 )
      {
        if ( a18 )
          (*(void (__fastcall **)(bool *, const wchar_t *))(*(_QWORD *)a18 + 8LL))(
            a18,
            L"Multiple CvDbg entries in IL-only image.");
        return ATL::AtlHresultFromWin32(0xC1u);
      }
      for ( i = 0; ; ++i )
      {
        v44 = i;
        if ( i >= v34 )
          break;
        v37 = 1576LL * i;
        if ( *(_DWORD *)((char *)v19 + v37) == 1396986706 && a5 != -1 && i != a5 )
        {
          *(_DWORD *)((char *)v19 + v37) = 3;
          v34 = *v18;
        }
      }
    }
    v32 = *(_DWORD *)v19;
    if ( *(_DWORD *)v19 == 1 )
    {
      v32 = 1;
    }
    else if ( v32 || !v43 )
    {
      if ( v35 == 1 )
      {
        *(_DWORD *)v19 = 3;
        v32 = 3;
      }
    }
    else
    {
      *(_DWORD *)v19 = 2;
      v32 = 2;
    }
  }
  else
  {
    if ( !v43 )
    {
LABEL_24:
      *v18 = 1;
      *(_DWORD *)v19 = 0;
      v32 = 0;
      v33 = a8;
      goto LABEL_47;
    }
    *v18 = 1;
    *(_DWORD *)v19 = 2;
    v32 = 2;
    v33 = a8;
  }
LABEL_47:
  if ( !v32 )
  {
    if ( v33 )
      *(_DWORD *)v33 = 4;
LABEL_62:
    if ( !v21 || !(_DWORD)a13 || (unsigned int)SymGetEstimatedOriginalFilename((unsigned __int16 *)this) )
      return 0;
    goto LABEL_66;
  }
  if ( (unsigned int)(v32 - 1) > 1 )
    goto LABEL_62;
  *((_DWORD *)v19 + 1) = v45;
  *((_DWORD *)v19 + 2) = v46;
  *((_DWORD *)v19 + 3) = v47;
  if ( !(unsigned int)SymGetEstimatedOriginalFilename((unsigned __int16 *)this) )
  {
LABEL_66:
    if ( a18 )
      (*(void (__fastcall **)(bool *, const wchar_t *))(*(_QWORD *)a18 + 8LL))(
        a18,
        L"Failed to obtain the original file name.");
    return 2147500037LL;
  }
  if ( !v21 || (result = StringCchCopyW(v21, (unsigned int)a13, (const unsigned __int16 *)v19 + 8), (int)result >= 0) )
  {
    if ( *(_DWORD *)v19 != 2 )
      goto LABEL_56;
    v38 = wcsrchr((const wchar_t *)v19 + 8, 0x2Eu);
    if ( v38 )
      *v38 = 0;
    result = StringCchCatW((unsigned __int16 *)v19 + 8, 0x30Cu, L".dbg");
    if ( (int)result >= 0 )
    {
LABEL_56:
      if ( v33 )
      {
        v39 = -1;
        do
          ++v39;
        while ( *((_WORD *)v19 + v39 + 8) );
        *(_DWORD *)v33 = 2 * v39 + 18;
      }
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002fae4  mov     [rsp+arg_10], r8d
0x18002fae9  mov     [rsp+BaseAddress], rdx
0x18002faee  mov     [rsp+arg_0], rcx
0x18002faf3  push    rbx
0x18002faf4  push    rsi
0x18002faf5  push    rdi
0x18002faf6  push    r12
0x18002faf8  push    r13
0x18002fafa  push    r14
0x18002fafc  push    r15
0x18002fafe  sub     rsp, 0A0h
0x18002fb05  mov     r10, rdx
0x18002fb08  mov     r12, [rsp+0D8h+arg_28]
0x18002fb10  mov     rbx, [rsp+0D8h+arg_30]
0x18002fb18  xorps   xmm0, xmm0
0x18002fb1b  xor     eax, eax
0x18002fb1d  mov     r13, [rsp+0D8h+arg_78]
0x18002fb25  movups  xmmword ptr [r13+0], xmm0
0x18002fb2a  mov     [r13+10h], rax
0x18002fb2e  mov     rax, [rsp+0D8h+arg_80]
0x18002fb36  mov     byte ptr [rax], 0
0x18002fb39  mov     r14, [rsp+0D8h+arg_58]
0x18002fb41  test    r14, r14
0x18002fb44  jz      short loc_18002FB4C
0x18002fb46  xor     eax, eax
0x18002fb48  mov     [r14], ax
0x18002fb4c  mov     edx, r8d
0x18002fb4f  mov     rcx, r10
0x18002fb52  call    XPerfCore___SafeImageNtHeader
0x18002fb57  mov     rsi, rax
0x18002fb5a  test    rax, rax
0x18002fb5d  jnz     short loc_18002FB8E
0x18002fb5f  mov     rcx, [rsp+0D8h+arg_88]
0x18002fb67  test    rcx, rcx
0x18002fb6a  jz      short loc_18002FB7F
0x18002fb6c  mov     rax, [rcx]
0x18002fb6f  lea     rdx, aInvalidExecuta; "Invalid executable format."
0x18002fb76  mov     rax, [rax+8]
0x18002fb7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fb7f  mov     ecx, 0C1h; unsigned int
0x18002fb84  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18002fb89  jmp     loc_18002FFAE
0x18002fb8e  mov     eax, [rax+58h]
0x18002fb91  mov     [rsp+0D8h+var_58], eax
0x18002fb98  mov     [rsp+0D8h+var_4C], eax
0x18002fb9f  mov     edx, [rsi+8]
0x18002fba2  mov     [rsp+0D8h+var_54], edx
0x18002fba9  mov     [rsp+0D8h+var_48], edx
0x18002fbb0  mov     ecx, [rsi+50h]
0x18002fbb3  mov     [rsp+0D8h+var_50], ecx
0x18002fbba  mov     [rsp+0D8h+var_44], ecx
0x18002fbc1  test    r9d, r9d
0x18002fbc4  jz      short loc_18002FBFA
0x18002fbc6  cmp     eax, r9d
0x18002fbc9  jz      short loc_18002FBFA
0x18002fbcb  mov     rcx, [rsp+0D8h+arg_88]
0x18002fbd3  test    rcx, rcx
0x18002fbd6  jz      short loc_18002FBEB
0x18002fbd8  mov     rax, [rcx]
0x18002fbdb  lea     rdx, aInvalidImageHe; "Invalid image header checksum."
0x18002fbe2  mov     rax, [rax+8]
0x18002fbe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fbeb  mov     ecx, 0Dh; unsigned int
0x18002fbf0  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18002fbf5  jmp     loc_18002FFAE
0x18002fbfa  mov     rax, [rsp+0D8h+arg_48]
0x18002fc02  test    rax, rax
0x18002fc05  jz      short loc_18002FC09
0x18002fc07  mov     [rax], edx
0x18002fc09  mov     rax, [rsp+0D8h+arg_50]
0x18002fc11  test    rax, rax
0x18002fc14  jz      short loc_18002FC18
0x18002fc16  mov     [rax], ecx
0x18002fc18  mov     eax, 10Bh
0x18002fc1d  cmp     [rsi+18h], ax
0x18002fc21  jz      short loc_18002FC4A
0x18002fc23  mov     eax, 20Bh
0x18002fc28  cmp     [rsi+18h], ax
0x18002fc2c  jz      short loc_18002FC38
0x18002fc2e  mov     eax, 8000FFFFh
0x18002fc33  jmp     loc_18002FFAE
0x18002fc38  mov     edi, 1
0x18002fc3d  mov     rax, [rsp+0D8h+arg_68]
0x18002fc45  mov     [rax], dil
0x18002fc48  jmp     short loc_18002FC5A
0x18002fc4a  mov     rax, [rsp+0D8h+arg_68]
0x18002fc52  mov     byte ptr [rax], 0
0x18002fc55  mov     edi, 1
0x18002fc5a  mov     r15b, [rsp+0D8h+MappedAsImage]
0x18002fc62  mov     dl, r15b
0x18002fc65  mov     rcx, r10; BaseAddress
0x18002fc68  call    SymCommonNativeResourceOnlyDll
0x18002fc6d  test    eax, eax
0x18002fc6f  jz      short loc_18002FC76
0x18002fc71  xor     r13d, r13d
0x18002fc74  jmp     short loc_18002FCD4
0x18002fc76  movzx   eax, word ptr [rsi+16h]
0x18002fc7a  and     eax, 200h
0x18002fc7f  mov     [rsp+0D8h+var_60], eax
0x18002fc83  mov     r8b, r15b; MappedAsImage
0x18002fc86  mov     rdx, rsi; NtHeader
0x18002fc89  mov     rsi, [rsp+0D8h+BaseAddress]
0x18002fc91  mov     rcx, rsi; BaseAddress
0x18002fc94  call    SymCommonTlbImpManagedDll
0x18002fc99  mov     [rsp+0D8h+var_64], eax
0x18002fc9d  mov     [rsp+0D8h+Size], 0
0x18002fca5  mov     r8d, 6; Directory
0x18002fcab  lea     r9, [rsp+0D8h+Size]; Size
0x18002fcb0  mov     dl, r15b; MappedAsImage
0x18002fcb3  mov     rcx, rsi; BaseAddress
0x18002fcb6  call    cs:__imp_RtlImageDirectoryEntryToData
0x18002fcbd  nop     dword ptr [rax+rax+00h]
0x18002fcc2  mov     r9, rax
0x18002fcc5  test    rax, rax
0x18002fcc8  jnz     short loc_18002FD17
0x18002fcca  xor     r13d, r13d
0x18002fccd  cmp     [rsp+0D8h+var_60], r13d
0x18002fcd2  jnz     short loc_18002FCF3
0x18002fcd4  mov     [r12], edi
0x18002fcd8  mov     [rbx], r13d
0x18002fcdb  mov     eax, r13d
0x18002fcde  mov     rsi, [rsp+0D8h+arg_38]
0x18002fce6  mov     r15, [rsp+0D8h+BaseAddress]
0x18002fcee  jmp     loc_18002FE50
0x18002fcf3  mov     [r12], edi
0x18002fcf7  mov     dword ptr [rbx], 2
0x18002fcfd  mov     eax, 2
0x18002fd02  mov     rsi, [rsp+0D8h+arg_38]
0x18002fd0a  mov     r15, [rsp+0D8h+BaseAddress]
0x18002fd12  jmp     loc_18002FE50
0x18002fd17  sub     r9, rsi; unsigned int
0x18002fd1a  mov     [rsp+0D8h+var_40], r9
0x18002fd22  mov     [rsp+0D8h+arg_20], 0FFFFFFFFh
0x18002fd2d  mov     rax, [rsp+0D8h+arg_80]
0x18002fd35  mov     [rsp+0D8h+var_78], rax; bool *
0x18002fd3a  mov     [rsp+0D8h+var_80], r13; struct EMBEDDED_PDB_INFORMATION *
0x18002fd3f  mov     [rsp+0D8h+var_88], r15b; bool
0x18002fd44  mov     rax, [rsp+0D8h+arg_40]
0x18002fd4c  mov     [rsp+0D8h+var_90], rax; struct CODEVIEW_INFORMATION_1 *
0x18002fd51  mov     rsi, [rsp+0D8h+arg_38]
0x18002fd59  mov     [rsp+0D8h+var_98], rsi; unsigned int *
0x18002fd5e  mov     [rsp+0D8h+var_A0], rbx; union _CVDD *
0x18002fd63  mov     [rsp+0D8h+var_A8], r12; unsigned int *
0x18002fd68  lea     rax, [rsp+0D8h+arg_20]
0x18002fd70  mov     [rsp+0D8h+var_B0], rax; unsigned int *
0x18002fd75  mov     r8d, [rsp+0D8h+Size]; unsigned int
0x18002fd7a  mov     edx, [rsp+0D8h+arg_10]; unsigned int
0x18002fd81  mov     r15, [rsp+0D8h+BaseAddress]
0x18002fd89  mov     rcx, r15; void *
0x18002fd8c  call    ?CvInfoFromDbgDir@@YAJPEAXKKK_NPEAK2PEAT_CVDD@@2PEAUCODEVIEW_INFORMATION_1@@1AEAUEMBEDDED_PDB_INFORMATION@@AEA_N@Z; CvInfoFromDbgDir(void *,ulong,ulong,ulong,bool,ulong *,ulong *,_CVDD *,ulong *,CODEVIEW_INFORMATION_1 *,bool,EMBEDDED_PDB_INFORMATION &,bool &)
0x18002fd91  xor     r13d, r13d
0x18002fd94  test    eax, eax
0x18002fd96  js      loc_18002FFAE
0x18002fd9c  mov     ecx, [r12]
0x18002fda0  mov     r9d, [rsp+0D8h+var_64]
0x18002fda5  cmp     ecx, edi
0x18002fda7  jbe     short loc_18002FE1E
0x18002fda9  cmp     r9d, edi
0x18002fdac  jnz     short loc_18002FDDD
0x18002fdae  mov     rcx, [rsp+0D8h+arg_88]
0x18002fdb6  test    rcx, rcx
0x18002fdb9  jz      short loc_18002FDCE
0x18002fdbb  mov     rax, [rcx]
0x18002fdbe  lea     rdx, aMultipleCvdbgE; "Multiple CvDbg entries in IL-only image"...
0x18002fdc5  mov     rax, [rax+8]
0x18002fdc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fdce  mov     ecx, 0C1h; unsigned int
0x18002fdd3  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18002fdd8  jmp     loc_18002FFAE
0x18002fddd  mov     edx, r13d
0x18002fde0  mov     [rsp+0D8h+var_5C], edx
0x18002fde4  cmp     edx, ecx
0x18002fde6  jnb     short loc_18002FE1E
0x18002fde8  mov     eax, edx
0x18002fdea  imul    r8, rax, 628h
0x18002fdf1  cmp     dword ptr [r8+rbx], 53445352h
0x18002fdf9  jnz     short loc_18002FE1A
0x18002fdfb  cmp     [rsp+0D8h+arg_20], 0FFFFFFFFh
0x18002fe03  jz      short loc_18002FE1A
0x18002fe05  cmp     edx, [rsp+0D8h+arg_20]
0x18002fe0c  jz      short loc_18002FE1A
0x18002fe0e  mov     dword ptr [r8+rbx], 3
0x18002fe16  mov     ecx, [r12]
0x18002fe1a  add     edx, edi
0x18002fe1c  jmp     short loc_18002FDE0
0x18002fe1e  mov     eax, [rbx]
0x18002fe20  cmp     eax, edi
0x18002fe22  jz      short loc_18002FE4E
0x18002fe24  test    eax, eax
0x18002fe26  jnz     short loc_18002FE3C
0x18002fe28  cmp     [rsp+0D8h+var_60], r13d
0x18002fe2d  jz      short loc_18002FE3C
0x18002fe2f  mov     dword ptr [rbx], 2
0x18002fe35  mov     eax, 2
0x18002fe3a  jmp     short loc_18002FE50
0x18002fe3c  cmp     r9d, edi
0x18002fe3f  jnz     short loc_18002FE4C
0x18002fe41  mov     dword ptr [rbx], 3
0x18002fe47  mov     eax, 3
0x18002fe4c  jmp     short loc_18002FE50
0x18002fe4e  mov     eax, edi
0x18002fe50  test    eax, eax
0x18002fe52  jz      loc_18002FF24
0x18002fe58  sub     eax, 1
0x18002fe5b  jz      short loc_18002FE66
0x18002fe5d  cmp     eax, 1
0x18002fe60  jnz     loc_18002FF2F
0x18002fe66  mov     eax, [rsp+0D8h+var_58]
0x18002fe6d  mov     [rbx+4], eax
0x18002fe70  mov     eax, [rsp+0D8h+var_54]
0x18002fe77  mov     [rbx+8], eax
0x18002fe7a  mov     eax, [rsp+0D8h+var_50]
0x18002fe81  mov     [rbx+0Ch], eax
0x18002fe84  lea     rdi, [rbx+10h]
0x18002fe88  mov     r9, rdi
0x18002fe8b  mov     r8d, 307h
0x18002fe91  mov     rdx, r15
0x18002fe94  mov     rcx, [rsp+0D8h+arg_0]; unsigned __int16 *
0x18002fe9c  call    SymGetEstimatedOriginalFilename
0x18002fea1  test    eax, eax
0x18002fea3  jz      loc_18002FF5C
0x18002fea9  test    r14, r14
0x18002feac  jz      short loc_18002FEC8
0x18002feae  mov     edx, dword ptr [rsp+0D8h+arg_60]; unsigned __int64
0x18002feb5  mov     r8, rdi; unsigned __int16 *
0x18002feb8  mov     rcx, r14; unsigned __int16 *
0x18002febb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002fec0  test    eax, eax
0x18002fec2  js      loc_18002FFAE
0x18002fec8  cmp     dword ptr [rbx], 2
0x18002fecb  jnz     short loc_18002FF06
0x18002fecd  mov     edx, 2Eh ; '.'; Ch
0x18002fed2  mov     rcx, rdi; Str
0x18002fed5  call    cs:__imp_wcsrchr
0x18002fedc  nop     dword ptr [rax+rax+00h]
0x18002fee1  test    rax, rax
0x18002fee4  jz      short loc_18002FEEA
0x18002fee6  mov     [rax], r13w
0x18002feea  lea     r8, aDbg; ".dbg"
0x18002fef1  mov     edx, 30Ch; unsigned __int64
0x18002fef6  mov     rcx, rdi; unsigned __int16 *
0x18002fef9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002fefe  test    eax, eax
0x18002ff00  js      loc_18002FFAE
0x18002ff06  test    rsi, rsi
0x18002ff09  jz      short loc_18002FF58
0x18002ff0b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002ff0f  inc     rax
0x18002ff12  cmp     [rdi+rax*2], r13w
0x18002ff17  jnz     short loc_18002FF0F
0x18002ff19  lea     eax, ds:12h[rax*2]
0x18002ff20  mov     [rsi], eax
0x18002ff22  jmp     short loc_18002FF58
0x18002ff24  test    rsi, rsi
0x18002ff27  jz      short loc_18002FF2F
0x18002ff29  mov     dword ptr [rsi], 4
0x18002ff2f  test    r14, r14
0x18002ff32  jz      short loc_18002FF58
0x18002ff34  mov     r8d, dword ptr [rsp+0D8h+arg_60]
0x18002ff3c  test    r8d, r8d
0x18002ff3f  jz      short loc_18002FF58
0x18002ff41  mov     r9, r14
0x18002ff44  mov     rdx, r15
0x18002ff47  mov     rcx, [rsp+0D8h+arg_0]; unsigned __int16 *
0x18002ff4f  call    SymGetEstimatedOriginalFilename
0x18002ff54  test    eax, eax
0x18002ff56  jz      short loc_18002FF5C
0x18002ff58  xor     eax, eax
0x18002ff5a  jmp     short loc_18002FFAE
0x18002ff5c  mov     rcx, [rsp+0D8h+arg_88]
0x18002ff64  test    rcx, rcx
0x18002ff67  jz      short loc_18002FF7C
0x18002ff69  mov     rax, [rcx]
0x18002ff6c  lea     rdx, aFailedToObtain; "Failed to obtain the original file name"...
0x18002ff73  mov     rax, [rax+8]
0x18002ff77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ff7c  mov     eax, 80004005h
0x18002ff81  jmp     short loc_18002FFAE
0x18002ff83  mov     rcx, [rsp+0D8h+arg_88]
0x18002ff8b  test    rcx, rcx
0x18002ff8e  jz      short loc_18002FFA3
0x18002ff90  mov     rax, [rcx]
0x18002ff93  lea     rdx, aPagingExceptio; "Paging exception occurred while process"...
0x18002ff9a  mov     rax, [rax+8]
0x18002ff9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ffa3  mov     ecx, 3E7h; unsigned int
0x18002ffa8  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18002ffad  nop
0x18002ffae  add     rsp, 0A0h
0x18002ffb5  pop     r15
0x18002ffb7  pop     r14
0x18002ffb9  pop     r13
0x18002ffbb  pop     r12
0x18002ffbd  pop     rdi
0x18002ffbe  pop     rsi
0x18002ffbf  pop     rbx
0x18002ffc0  retn
0x180033c78  push    rbp
0x180033c7a  sub     rsp, 70h
0x180033c7e  mov     rbp, rdx
  ... truncated ...
```
