# CVssFunctionTracer::AddGenericErrorContext(CVssDebugInfo,long)

- ea: `0x1800348b4`
- end: `0x180034a46`
- name: `?AddGenericErrorContext@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@J@Z`
- size: `402`
- prototype: `void __fastcall(__int64, const struct CVssDebugInfo *, DWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180040cb0`

## callees

- `0x180001580`
- `0x18002e79c`
- `0x1800339c0`
- `0x180033c2c`
- `0x180034754`
- `0x1800348b4`
- `0x180034edc`
- `0x1800356fc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800348fb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800348fb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180034980`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180034980`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18003492d`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180034969`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18003492d`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180034969`

## string_xrefs

- `0x1800348f4`: `vsstrace.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CVssFunctionTracer::AddGenericErrorContext(__int64 a1, const struct CVssDebugInfo *a2, DWORD a3)
{
  HMODULE Library; // rbx
  CVssFunctionTracer *v7; // rcx
  __int64 v8; // rcx
  CVssDebugInfo *v9; // rax
  CVssDebugInfo *v10; // rax
  __int64 v11; // r9
  LPWSTR lpBuffer; // [rsp+20h] [rbp-E0h]
  _BYTE v13[168]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v14[3]; // [rsp+F8h] [rbp-8h] BYREF
  WCHAR Buffer[520]; // [rsp+120h] [rbp+20h] BYREF

  Library = LoadLibraryExW(L"vsstrace.dll", 0, 2u);
  if ( FormatMessageW(0x1200u, 0, a3, 0x400u, Buffer, 0x200u, 0) )
  {
    CVssFunctionTracer::EraseInsertionStringsFromText(v7, Buffer);
  }
  else if ( !FormatMessageW(0xA00u, Library, a3, 0x400u, Buffer, 0x200u, 0) )
  {
    Buffer[0] = 0;
  }
  if ( Library )
    FreeLibrary(Library);
  if ( Buffer[0] )
  {
    v9 = CVssDebugInfo::CVssDebugInfo((CVssDebugInfo *)v13, a2);
    LODWORD(lpBuffer) = a3;
    CVssFunctionTracer::AddErrorSpecificContext(a1, v9, 104, L"(%#x) %s", lpBuffer, Buffer);
  }
  else
  {
    CVssResource::LoadStringW(v8, v14);
    v10 = CVssDebugInfo::CVssDebugInfo((CVssDebugInfo *)v13, a2);
    LODWORD(lpBuffer) = a3;
    CVssFunctionTracer::AddErrorSpecificContext(a1, v10, 104, L"(%#x) %s", lpBuffer, v11);
    std::wstring::_Tidy_deallocate(v14);
  }
  CVssDebugInfo::~CVssDebugInfo(a2);
}

```

## disassembly

```asm
0x1800348b4  mov     [rsp-8+arg_18], rbx
0x1800348b9  push    rbp
0x1800348ba  push    rsi
0x1800348bb  push    rdi
0x1800348bc  push    r14
0x1800348be  push    r15
0x1800348c0  lea     rbp, [rsp-440h]
0x1800348c8  sub     rsp, 540h
0x1800348cf  mov     rax, cs:__security_cookie
0x1800348d6  xor     rax, rsp
0x1800348d9  mov     [rbp+460h+var_30], rax
0x1800348e0  mov     esi, r8d
0x1800348e3  mov     rdi, rdx
0x1800348e6  mov     r14, rcx
0x1800348e9  mov     [rsp+560h+var_518], rdx
0x1800348ee  xor     edx, edx; hFile
0x1800348f0  lea     r8d, [rdx+2]; dwFlags
0x1800348f4  lea     rcx, aVsstraceDll_0; "vsstrace.dll"
0x1800348fb  call    cs:__imp_LoadLibraryExW
0x180034901  mov     rbx, rax
0x180034904  xor     r15d, r15d
0x180034907  mov     [rsp+560h+Arguments], r15; Arguments
0x18003490c  mov     [rsp+560h+nSize], 200h; nSize
0x180034914  lea     rax, [rbp+460h+Buffer]
0x180034918  mov     [rsp+560h+lpBuffer], rax; lpBuffer
0x18003491d  mov     r9d, 400h; dwLanguageId
0x180034923  mov     r8d, esi; dwMessageId
0x180034926  xor     edx, edx; lpSource
0x180034928  mov     ecx, 1200h; dwFlags
0x18003492d  call    cs:__imp_FormatMessageW
0x180034933  test    eax, eax
0x180034935  jz      short loc_180034942
0x180034937  lea     rdx, [rbp+460h+Buffer]; unsigned __int16 *
0x18003493b  call    ?EraseInsertionStringsFromText@CVssFunctionTracer@@AEAAXPEAG@Z; CVssFunctionTracer::EraseInsertionStringsFromText(ushort *)
0x180034940  jmp     short loc_180034978
0x180034942  mov     [rsp+560h+Arguments], r15; Arguments
0x180034947  mov     [rsp+560h+nSize], 200h; nSize
0x18003494f  lea     rax, [rbp+460h+Buffer]
0x180034953  mov     [rsp+560h+lpBuffer], rax; lpBuffer
0x180034958  mov     r9d, 400h; dwLanguageId
0x18003495e  mov     r8d, esi; dwMessageId
0x180034961  mov     rdx, rbx; lpSource
0x180034964  mov     ecx, 0A00h; dwFlags
0x180034969  call    cs:__imp_FormatMessageW
0x18003496f  test    eax, eax
0x180034971  jnz     short loc_180034978
0x180034973  mov     [rbp+460h+Buffer], r15w
0x180034978  test    rbx, rbx
0x18003497b  jz      short loc_180034986
0x18003497d  mov     rcx, rbx; hLibModule
0x180034980  call    cs:__imp_FreeLibrary
0x180034986  cmp     [rbp+460h+Buffer], r15w
0x18003498b  jz      short loc_1800349C1
0x18003498d  mov     rdx, rdi; struct CVssDebugInfo *
0x180034990  lea     rcx, [rsp+560h+var_510]; this
0x180034995  call    ??0CVssDebugInfo@@QEAA@AEBU0@@Z; CVssDebugInfo::CVssDebugInfo(CVssDebugInfo const &)
0x18003499a  lea     rcx, [rbp+460h+Buffer]
0x18003499e  mov     qword ptr [rsp+560h+nSize], rcx
0x1800349a3  mov     dword ptr [rsp+560h+lpBuffer], esi
0x1800349a7  lea     r9, aXS; "(%#x) %s"
0x1800349ae  mov     r8d, 68h ; 'h'
0x1800349b4  mov     rdx, rax
0x1800349b7  mov     rcx, r14
0x1800349ba  call    ?AddErrorSpecificContext@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@IPEBGZZ; CVssFunctionTracer::AddErrorSpecificContext(CVssDebugInfo,uint,ushort const *,...)
0x1800349bf  jmp     short loc_180034A18
0x1800349c1  mov     r8d, 69h ; 'i'
0x1800349c7  lea     rdx, [rbp+460h+var_468]
0x1800349cb  call    ?LoadStringW@CVssResource@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; CVssResource::LoadStringW(uint)
0x1800349d0  nop
0x1800349d1  lea     r9, [rbp+460h+var_468]
0x1800349d5  cmp     [rbp+460h+var_450], 7
0x1800349da  cmova   r9, [rbp+460h+var_468]
0x1800349df  mov     rdx, rdi; struct CVssDebugInfo *
0x1800349e2  lea     rcx, [rsp+560h+var_510]; this
0x1800349e7  call    ??0CVssDebugInfo@@QEAA@AEBU0@@Z; CVssDebugInfo::CVssDebugInfo(CVssDebugInfo const &)
0x1800349ec  mov     qword ptr [rsp+560h+nSize], r9
0x1800349f1  mov     dword ptr [rsp+560h+lpBuffer], esi
0x1800349f5  lea     r9, aXS; "(%#x) %s"
0x1800349fc  mov     r8d, 68h ; 'h'
0x180034a02  mov     rdx, rax
0x180034a05  mov     rcx, r14
0x180034a08  call    ?AddErrorSpecificContext@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@IPEBGZZ; CVssFunctionTracer::AddErrorSpecificContext(CVssDebugInfo,uint,ushort const *,...)
0x180034a0d  nop
0x180034a0e  lea     rcx, [rbp+460h+var_468]
0x180034a12  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180034a17  nop
0x180034a18  mov     rcx, rdi; this
0x180034a1b  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x180034a20  mov     rcx, [rbp+460h+var_30]
0x180034a27  xor     rcx, rsp; StackCookie
0x180034a2a  call    __security_check_cookie
0x180034a2f  mov     rbx, [rsp+560h+arg_18]
0x180034a37  add     rsp, 540h
0x180034a3e  pop     r15
0x180034a40  pop     r14
0x180034a42  pop     rdi
0x180034a43  pop     rsi
0x180034a44  pop     rbp
0x180034a45  retn
```
