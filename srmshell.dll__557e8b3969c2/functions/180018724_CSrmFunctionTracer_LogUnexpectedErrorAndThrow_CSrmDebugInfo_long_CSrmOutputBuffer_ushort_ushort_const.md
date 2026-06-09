# CSrmFunctionTracer::LogUnexpectedErrorAndThrow(CSrmDebugInfo,long,CSrmOutputBuffer &,ushort,ushort const *)

- ea: `0x180018724`
- end: `0x1800188c5`
- name: `?LogUnexpectedErrorAndThrow@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JAEAVCSrmOutputBuffer@@GPEBG@Z`
- size: `417`
- prototype: `void __fastcall __noreturn(__int64, const struct CSrmDebugInfo *, DWORD, CSrmOutputBuffer *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180019c74`

## callees

- `0x1800054c0`
- `0x180016170`
- `0x180016dd0`
- `0x1800170ec`
- `0x1800180a0`
- `0x180018724`
- `0x1800191ec`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800187e1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800187e1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001875c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001875c`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001878e`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800187ca`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001878e`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800187ca`

## string_xrefs

- `0x180018755`: `srm.dll`

## pseudocode

```c
void __fastcall __noreturn CSrmFunctionTracer::LogUnexpectedErrorAndThrow(
        __int64 a1,
        const struct CSrmDebugInfo *a2,
        DWORD a3,
        CSrmOutputBuffer *a4)
{
  HMODULE Library; // rbx
  CSrmDebugInfo *v9; // rax
  __int64 v10; // r9
  CSrmDebugInfo *v11; // rax
  CSrmDebugInfo *v12; // rax
  __int64 v13; // r9
  __int64 nSize; // [rsp+28h] [rbp-D8h]
  __int64 nSizea; // [rsp+28h] [rbp-D8h]
  _BYTE v16[152]; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR Buffer[544]; // [rsp+F0h] [rbp-10h] BYREF

  Library = LoadLibraryExW(L"srm.dll", 0, 2u);
  if ( FormatMessageW(0x1200u, 0, a3, 0x400u, Buffer, 0x200u, 0) )
  {
    CSrmFunctionTracer::EraseInsertionStringsFromText(Buffer);
  }
  else if ( !FormatMessageW(0xA00u, Library, a3, 0x400u, Buffer, 0x200u, 0) )
  {
    Buffer[0] = 0;
  }
  if ( Library )
    FreeLibrary(Library);
  v9 = CSrmDebugInfo::CSrmDebugInfo((CSrmDebugInfo *)v16, a2);
  LODWORD(nSize) = a3;
  if ( Buffer[0] )
    CSrmFunctionTracer::AddErrorSpecificContext(a1, v9, 1008, L"%s, 0x%08lx, %s", v10, nSize, Buffer);
  else
    CSrmFunctionTracer::AddErrorSpecificContext(a1, v9, 1008, L"%s, 0x%08lx", v10, nSize);
  v11 = CSrmDebugInfo::CSrmDebugInfo((CSrmDebugInfo *)v16, a2);
  CSrmFunctionTracer::LogError(a1, 0x80042005, (__int64)v11, 1u);
  CSrmOutputBuffer::GetBuffer(a4);
  v12 = CSrmDebugInfo::CSrmDebugInfo((CSrmDebugInfo *)v16, a2);
  LODWORD(nSizea) = a3;
  CSrmFunctionTracer::Throw(a1, v12, a3, L"Unexpected error: %s [hr = 0x%08lx]", v13, nSizea);
}

```

## disassembly

```asm
0x180018724  push    rbp
0x180018726  push    rbx
0x180018727  push    rsi
0x180018728  push    rdi
0x180018729  push    r12
0x18001872b  push    r14
0x18001872d  push    r15
0x18001872f  lea     rbp, [rsp-400h]
0x180018737  sub     rsp, 500h
0x18001873e  mov     r15, r9
0x180018741  mov     edi, r8d
0x180018744  mov     rsi, rdx
0x180018747  mov     r14, rcx
0x18001874a  mov     [rsp+530h+var_4E8], rdx
0x18001874f  xor     edx, edx; hFile
0x180018751  lea     r8d, [rdx+2]; dwFlags
0x180018755  lea     rcx, aSrmDll_0; "srm.dll"
0x18001875c  call    cs:__imp_LoadLibraryExW
0x180018762  mov     rbx, rax
0x180018765  xor     r12d, r12d
0x180018768  mov     [rsp+530h+Arguments], r12; Arguments
0x18001876d  mov     dword ptr [rsp+530h+nSize], 200h; nSize
0x180018775  lea     rax, [rbp+430h+Buffer]
0x180018779  mov     [rsp+530h+lpBuffer], rax; lpBuffer
0x18001877e  mov     r9d, 400h; dwLanguageId
0x180018784  mov     r8d, edi; dwMessageId
0x180018787  xor     edx, edx; lpSource
0x180018789  mov     ecx, 1200h; dwFlags
0x18001878e  call    cs:__imp_FormatMessageW
0x180018794  test    eax, eax
0x180018796  jz      short loc_1800187A3
0x180018798  lea     rcx, [rbp+430h+Buffer]; unsigned __int16 *
0x18001879c  call    ?EraseInsertionStringsFromText@CSrmFunctionTracer@@SAXPEAG@Z; CSrmFunctionTracer::EraseInsertionStringsFromText(ushort *)
0x1800187a1  jmp     short loc_1800187D9
0x1800187a3  mov     [rsp+530h+Arguments], r12; Arguments
0x1800187a8  mov     dword ptr [rsp+530h+nSize], 200h; nSize
0x1800187b0  lea     rax, [rbp+430h+Buffer]
0x1800187b4  mov     [rsp+530h+lpBuffer], rax; lpBuffer
0x1800187b9  mov     r9d, 400h; dwLanguageId
0x1800187bf  mov     r8d, edi; dwMessageId
0x1800187c2  mov     rdx, rbx; lpSource
0x1800187c5  mov     ecx, 0A00h; dwFlags
0x1800187ca  call    cs:__imp_FormatMessageW
0x1800187d0  test    eax, eax
0x1800187d2  jnz     short loc_1800187D9
0x1800187d4  mov     [rbp+430h+Buffer], r12w
0x1800187d9  test    rbx, rbx
0x1800187dc  jz      short loc_1800187E7
0x1800187de  mov     rcx, rbx; hLibModule
0x1800187e1  call    cs:__imp_FreeLibrary
0x1800187e7  mov     r9, [r15]
0x1800187ea  lea     rax, [rsp+530h+var_4D8]
0x1800187ef  mov     rdx, rsi; struct CSrmDebugInfo *
0x1800187f2  lea     rcx, [rsp+530h+var_4D8]; this
0x1800187f7  mov     [rsp+530h+var_4F0], rax
0x1800187fc  call    ??0CSrmDebugInfo@@QEAA@AEBU0@@Z; CSrmDebugInfo::CSrmDebugInfo(CSrmDebugInfo const &)
0x180018801  cmp     [rbp+430h+Buffer], r12w
0x180018806  jz      short loc_180018834
0x180018808  lea     rcx, [rbp+430h+Buffer]
0x18001880c  mov     [rsp+530h+Arguments], rcx
0x180018811  mov     dword ptr [rsp+530h+nSize], edi
0x180018815  mov     [rsp+530h+lpBuffer], r9
0x18001881a  lea     r9, aS0x08lxS; "%s, 0x%08lx, %s"
0x180018821  mov     r8d, 3F0h
0x180018827  mov     rdx, rax
0x18001882a  mov     rcx, r14
0x18001882d  call    ?AddErrorSpecificContext@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@IPEBGZZ; CSrmFunctionTracer::AddErrorSpecificContext(CSrmDebugInfo,uint,ushort const *,...)
0x180018832  jmp     short loc_180018855
0x180018834  mov     dword ptr [rsp+530h+nSize], edi
0x180018838  mov     [rsp+530h+lpBuffer], r9
0x18001883d  lea     r9, aS0x08lx; "%s, 0x%08lx"
0x180018844  mov     r8d, 3F0h
0x18001884a  mov     rdx, rax
0x18001884d  mov     rcx, r14
0x180018850  call    ?AddErrorSpecificContext@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@IPEBGZZ; CSrmFunctionTracer::AddErrorSpecificContext(CSrmDebugInfo,uint,ushort const *,...)
0x180018855  lea     rax, [rsp+530h+var_4D8]
0x18001885a  mov     [rsp+530h+var_4F0], rax
0x18001885f  mov     rdx, rsi; struct CSrmDebugInfo *
0x180018862  lea     rcx, [rsp+530h+var_4D8]; this
0x180018867  call    ??0CSrmDebugInfo@@QEAA@AEBU0@@Z; CSrmDebugInfo::CSrmDebugInfo(CSrmDebugInfo const &)
0x18001886c  nop
0x18001886d  mov     r9d, 1
0x180018873  mov     r8, rax
0x180018876  mov     edx, 80042005h
0x18001887b  mov     rcx, r14
0x18001887e  call    ?LogError@CSrmFunctionTracer@@QEAAXKUCSrmDebugInfo@@G@Z; CSrmFunctionTracer::LogError(ulong,CSrmDebugInfo,ushort)
0x180018883  mov     rcx, r15; this
0x180018886  call    ?GetBuffer@CSrmOutputBuffer@@QEAAPEAGXZ; CSrmOutputBuffer::GetBuffer(void)
0x18001888b  mov     r9, rax
0x18001888e  lea     rax, [rsp+530h+var_4D8]
0x180018893  mov     [rsp+530h+var_4E0], rax
0x180018898  mov     rdx, rsi; struct CSrmDebugInfo *
0x18001889b  lea     rcx, [rsp+530h+var_4D8]; this
0x1800188a0  call    ??0CSrmDebugInfo@@QEAA@AEBU0@@Z; CSrmDebugInfo::CSrmDebugInfo(CSrmDebugInfo const &)
0x1800188a5  nop
0x1800188a6  mov     dword ptr [rsp+530h+nSize], edi
0x1800188aa  mov     [rsp+530h+lpBuffer], r9
0x1800188af  lea     r9, aUnexpectedErro; "Unexpected error: %s [hr = 0x%08lx]"
0x1800188b6  mov     r8d, edi
0x1800188b9  mov     rdx, rax
0x1800188bc  mov     rcx, r14
0x1800188bf  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
```
