# CSrmFunctionTracer::LogUnexpectedErrorAndThrow(CSrmDebugInfo,long,CSrmOutputBuffer &,ushort,ushort const *)

- ea: `0x1800728d8`
- end: `0x180072a79`
- name: `?LogUnexpectedErrorAndThrow@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JAEAVCSrmOutputBuffer@@GPEBG@Z`
- size: `417`
- prototype: `void __noreturn __high(struct CSrmDebugInfo, int, struct CSrmOutputBuffer *, unsigned __int16, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180074af4`
- `0x180074d5c`
- `0x18007508c`

## callees

- `0x18000ac44`
- `0x18006fdf0`
- `0x1800708ac`
- `0x1800711a0`
- `0x180071efc`
- `0x1800728d8`
- `0x180073d04`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180072995`
- `KERNEL32!FreeLibrary` at `0x180072995`
- `KERNEL32!LoadLibraryExW` at `0x180072910`
- `KERNEL32!LoadLibraryExW` at `0x180072910`
- `KERNEL32!FormatMessageW` at `0x180072942`
- `KERNEL32!FormatMessageW` at `0x18007297e`
- `KERNEL32!FormatMessageW` at `0x180072942`
- `KERNEL32!FormatMessageW` at `0x18007297e`

## string_xrefs

- `0x180072909`: `srm.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
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
0x1800728d8  push    rbp
0x1800728da  push    rbx
0x1800728db  push    rsi
0x1800728dc  push    rdi
0x1800728dd  push    r12
0x1800728df  push    r14
0x1800728e1  push    r15
0x1800728e3  lea     rbp, [rsp-400h]
0x1800728eb  sub     rsp, 500h
0x1800728f2  mov     r15, r9
0x1800728f5  mov     edi, r8d
0x1800728f8  mov     rsi, rdx
0x1800728fb  mov     r14, rcx
0x1800728fe  mov     [rsp+530h+var_4E8], rdx
0x180072903  xor     edx, edx; hFile
0x180072905  lea     r8d, [rdx+2]; dwFlags
0x180072909  lea     rcx, aSrmDll_0; "srm.dll"
0x180072910  call    cs:__imp_LoadLibraryExW
0x180072916  mov     rbx, rax
0x180072919  xor     r12d, r12d
0x18007291c  mov     [rsp+530h+Arguments], r12; Arguments
0x180072921  mov     dword ptr [rsp+530h+nSize], 200h; nSize
0x180072929  lea     rax, [rbp+430h+Buffer]
0x18007292d  mov     [rsp+530h+lpBuffer], rax; lpBuffer
0x180072932  mov     r9d, 400h; dwLanguageId
0x180072938  mov     r8d, edi; dwMessageId
0x18007293b  xor     edx, edx; lpSource
0x18007293d  mov     ecx, 1200h; dwFlags
0x180072942  call    cs:__imp_FormatMessageW
0x180072948  test    eax, eax
0x18007294a  jz      short loc_180072957
0x18007294c  lea     rcx, [rbp+430h+Buffer]; unsigned __int16 *
0x180072950  call    ?EraseInsertionStringsFromText@CSrmFunctionTracer@@SAXPEAG@Z; CSrmFunctionTracer::EraseInsertionStringsFromText(ushort *)
0x180072955  jmp     short loc_18007298D
0x180072957  mov     [rsp+530h+Arguments], r12; Arguments
0x18007295c  mov     dword ptr [rsp+530h+nSize], 200h; nSize
0x180072964  lea     rax, [rbp+430h+Buffer]
0x180072968  mov     [rsp+530h+lpBuffer], rax; lpBuffer
0x18007296d  mov     r9d, 400h; dwLanguageId
0x180072973  mov     r8d, edi; dwMessageId
0x180072976  mov     rdx, rbx; lpSource
0x180072979  mov     ecx, 0A00h; dwFlags
0x18007297e  call    cs:__imp_FormatMessageW
0x180072984  test    eax, eax
0x180072986  jnz     short loc_18007298D
0x180072988  mov     [rbp+430h+Buffer], r12w
0x18007298d  test    rbx, rbx
0x180072990  jz      short loc_18007299B
0x180072992  mov     rcx, rbx; hLibModule
0x180072995  call    cs:__imp_FreeLibrary
0x18007299b  mov     r9, [r15]
0x18007299e  lea     rax, [rsp+530h+var_4D8]
0x1800729a3  mov     rdx, rsi; struct CSrmDebugInfo *
0x1800729a6  lea     rcx, [rsp+530h+var_4D8]; this
0x1800729ab  mov     [rsp+530h+var_4F0], rax
0x1800729b0  call    ??0CSrmDebugInfo@@QEAA@AEBU0@@Z; CSrmDebugInfo::CSrmDebugInfo(CSrmDebugInfo const &)
0x1800729b5  cmp     [rbp+430h+Buffer], r12w
0x1800729ba  jz      short loc_1800729E8
0x1800729bc  lea     rcx, [rbp+430h+Buffer]
0x1800729c0  mov     [rsp+530h+Arguments], rcx
0x1800729c5  mov     dword ptr [rsp+530h+nSize], edi
0x1800729c9  mov     [rsp+530h+lpBuffer], r9
0x1800729ce  lea     r9, aS0x08lxS; "%s, 0x%08lx, %s"
0x1800729d5  mov     r8d, 3F0h
0x1800729db  mov     rdx, rax
0x1800729de  mov     rcx, r14
0x1800729e1  call    ?AddErrorSpecificContext@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@IPEBGZZ; CSrmFunctionTracer::AddErrorSpecificContext(CSrmDebugInfo,uint,ushort const *,...)
0x1800729e6  jmp     short loc_180072A09
0x1800729e8  mov     dword ptr [rsp+530h+nSize], edi
0x1800729ec  mov     [rsp+530h+lpBuffer], r9
0x1800729f1  lea     r9, aS0x08lx; "%s, 0x%08lx"
0x1800729f8  mov     r8d, 3F0h
0x1800729fe  mov     rdx, rax
0x180072a01  mov     rcx, r14
0x180072a04  call    ?AddErrorSpecificContext@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@IPEBGZZ; CSrmFunctionTracer::AddErrorSpecificContext(CSrmDebugInfo,uint,ushort const *,...)
0x180072a09  lea     rax, [rsp+530h+var_4D8]
0x180072a0e  mov     [rsp+530h+var_4F0], rax
0x180072a13  mov     rdx, rsi; struct CSrmDebugInfo *
0x180072a16  lea     rcx, [rsp+530h+var_4D8]; this
0x180072a1b  call    ??0CSrmDebugInfo@@QEAA@AEBU0@@Z; CSrmDebugInfo::CSrmDebugInfo(CSrmDebugInfo const &)
0x180072a20  nop
0x180072a21  mov     r9d, 1
0x180072a27  mov     r8, rax
0x180072a2a  mov     edx, 80042005h
0x180072a2f  mov     rcx, r14
0x180072a32  call    ?LogError@CSrmFunctionTracer@@QEAAXKUCSrmDebugInfo@@G@Z; CSrmFunctionTracer::LogError(ulong,CSrmDebugInfo,ushort)
0x180072a37  mov     rcx, r15; this
0x180072a3a  call    ?GetBuffer@CSrmOutputBuffer@@QEAAPEAGXZ; CSrmOutputBuffer::GetBuffer(void)
0x180072a3f  mov     r9, rax
0x180072a42  lea     rax, [rsp+530h+var_4D8]
0x180072a47  mov     [rsp+530h+var_4E0], rax
0x180072a4c  mov     rdx, rsi; struct CSrmDebugInfo *
0x180072a4f  lea     rcx, [rsp+530h+var_4D8]; this
0x180072a54  call    ??0CSrmDebugInfo@@QEAA@AEBU0@@Z; CSrmDebugInfo::CSrmDebugInfo(CSrmDebugInfo const &)
0x180072a59  nop
0x180072a5a  mov     dword ptr [rsp+530h+nSize], edi
0x180072a5e  mov     [rsp+530h+lpBuffer], r9
0x180072a63  lea     r9, aUnexpectedErro; "Unexpected error: %s [hr = 0x%08lx]"
0x180072a6a  mov     r8d, edi
0x180072a6d  mov     rdx, rax
0x180072a70  mov     rcx, r14
0x180072a73  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
```
