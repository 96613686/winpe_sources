# CSrmFunctionTracer::AddGenericErrorContext(CSrmDebugInfo,long)

- ea: `0x180070a14`
- end: `0x180070bd2`
- name: `?AddGenericErrorContext@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@J@Z`
- size: `446`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x180040f60`
- `0x1800417d0`
- `0x180093344`
- `0x180093aa8`
- `0x18009887c`
- `0x18009f958`
- `0x1800a0428`

## callees

- `0x180001350`
- `0x18001bc58`
- `0x18006fdf0`
- `0x18007006c`
- `0x1800708ac`
- `0x180070a14`
- `0x1800711a0`
- `0x1800b07d0`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180070ae0`
- `KERNEL32!FreeLibrary` at `0x180070ae0`
- `KERNEL32!LoadLibraryExW` at `0x180070a5b`
- `KERNEL32!LoadLibraryExW` at `0x180070a5b`
- `KERNEL32!FormatMessageW` at `0x180070a8d`
- `KERNEL32!FormatMessageW` at `0x180070ac9`
- `KERNEL32!FormatMessageW` at `0x180070a8d`
- `KERNEL32!FormatMessageW` at `0x180070ac9`

## string_xrefs

- `0x180070a54`: `srm.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CSrmFunctionTracer::AddGenericErrorContext(__int64 a1, const struct CSrmDebugInfo *a2, DWORD a3)
{
  HMODULE Library; // rbx
  CSrmDebugInfo *v7; // rax
  CSrmDebugInfo *v8; // rax
  __int64 v9; // r9
  LPWSTR lpBuffer; // [rsp+20h] [rbp-E0h]
  _BYTE v11[144]; // [rsp+50h] [rbp-B0h] BYREF
  void *Block[3]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int64 v13; // [rsp+F8h] [rbp-8h]
  WCHAR Buffer[520]; // [rsp+110h] [rbp+10h] BYREF

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
  if ( Buffer[0] )
  {
    v7 = CSrmDebugInfo::CSrmDebugInfo((CSrmDebugInfo *)v11, a2);
    LODWORD(lpBuffer) = a3;
    CSrmFunctionTracer::AddErrorSpecificContext(a1, v7, 1008, L"(%#x) %s", lpBuffer, Buffer);
  }
  else
  {
    CSrmResource::LoadStringW(Block, 0x40u);
    v8 = CSrmDebugInfo::CSrmDebugInfo((CSrmDebugInfo *)v11, a2);
    LODWORD(lpBuffer) = a3;
    CSrmFunctionTracer::AddErrorSpecificContext(a1, v8, 1008, L"(%#x) %s", lpBuffer, v9);
    if ( v13 >= 8 )
      operator delete(Block[0]);
    v13 = 7;
    Block[2] = 0;
    LOWORD(Block[0]) = 0;
  }
  CSrmDebugInfo::~CSrmDebugInfo(a2);
}

```

## disassembly

```asm
0x180070a14  mov     [rsp-8+arg_18], rbx
0x180070a19  push    rbp
0x180070a1a  push    rsi
0x180070a1b  push    rdi
0x180070a1c  push    r14
0x180070a1e  push    r15
0x180070a20  lea     rbp, [rsp-430h]
0x180070a28  sub     rsp, 530h
0x180070a2f  mov     rax, cs:__security_cookie
0x180070a36  xor     rax, rsp
0x180070a39  mov     [rbp+450h+var_30], rax
0x180070a40  mov     esi, r8d
0x180070a43  mov     rdi, rdx
0x180070a46  mov     r14, rcx
0x180070a49  mov     [rsp+550h+var_508], rdx
0x180070a4e  xor     edx, edx; hFile
0x180070a50  lea     r8d, [rdx+2]; dwFlags
0x180070a54  lea     rcx, aSrmDll_0; "srm.dll"
0x180070a5b  call    cs:__imp_LoadLibraryExW
0x180070a61  mov     rbx, rax
0x180070a64  xor     r15d, r15d
0x180070a67  mov     [rsp+550h+Arguments], r15; Arguments
0x180070a6c  mov     [rsp+550h+nSize], 200h; nSize
0x180070a74  lea     rax, [rbp+450h+Buffer]
0x180070a78  mov     [rsp+550h+lpBuffer], rax; lpBuffer
0x180070a7d  mov     r9d, 400h; dwLanguageId
0x180070a83  mov     r8d, esi; dwMessageId
0x180070a86  xor     edx, edx; lpSource
0x180070a88  mov     ecx, 1200h; dwFlags
0x180070a8d  call    cs:__imp_FormatMessageW
0x180070a93  test    eax, eax
0x180070a95  jz      short loc_180070AA2
0x180070a97  lea     rcx, [rbp+450h+Buffer]; unsigned __int16 *
0x180070a9b  call    ?EraseInsertionStringsFromText@CSrmFunctionTracer@@SAXPEAG@Z; CSrmFunctionTracer::EraseInsertionStringsFromText(ushort *)
0x180070aa0  jmp     short loc_180070AD8
0x180070aa2  mov     [rsp+550h+Arguments], r15; Arguments
0x180070aa7  mov     [rsp+550h+nSize], 200h; nSize
0x180070aaf  lea     rax, [rbp+450h+Buffer]
0x180070ab3  mov     [rsp+550h+lpBuffer], rax; lpBuffer
0x180070ab8  mov     r9d, 400h; dwLanguageId
0x180070abe  mov     r8d, esi; dwMessageId
0x180070ac1  mov     rdx, rbx; lpSource
0x180070ac4  mov     ecx, 0A00h; dwFlags
0x180070ac9  call    cs:__imp_FormatMessageW
0x180070acf  test    eax, eax
0x180070ad1  jnz     short loc_180070AD8
0x180070ad3  mov     [rbp+450h+Buffer], r15w
0x180070ad8  test    rbx, rbx
0x180070adb  jz      short loc_180070AE6
0x180070add  mov     rcx, rbx; hLibModule
0x180070ae0  call    cs:__imp_FreeLibrary
0x180070ae6  cmp     [rbp+450h+Buffer], r15w
0x180070aeb  jz      short loc_180070B2C
0x180070aed  lea     rax, [rsp+550h+var_500]
0x180070af2  mov     [rsp+550h+var_510], rax
0x180070af7  mov     rdx, rdi; struct CSrmDebugInfo *
0x180070afa  lea     rcx, [rsp+550h+var_500]; this
0x180070aff  call    ??0CSrmDebugInfo@@QEAA@AEBU0@@Z; CSrmDebugInfo::CSrmDebugInfo(CSrmDebugInfo const &)
0x180070b04  nop
0x180070b05  lea     rcx, [rbp+450h+Buffer]
0x180070b09  mov     qword ptr [rsp+550h+nSize], rcx
0x180070b0e  mov     dword ptr [rsp+550h+lpBuffer], esi
0x180070b12  lea     r9, aXS; "(%#x) %s"
0x180070b19  mov     r8d, 3F0h
0x180070b1f  mov     rdx, rax
0x180070b22  mov     rcx, r14
0x180070b25  call    ?AddErrorSpecificContext@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@IPEBGZZ; CSrmFunctionTracer::AddErrorSpecificContext(CSrmDebugInfo,uint,ushort const *,...)
0x180070b2a  jmp     short loc_180070BA4
0x180070b2c  mov     edx, 40h ; '@'; uID
0x180070b31  lea     rcx, [rbp+450h+Block]; void *
0x180070b35  call    ?LoadStringW@CSrmResource@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; CSrmResource::LoadStringW(uint)
0x180070b3a  nop
0x180070b3b  lea     r9, [rbp+450h+Block]
0x180070b3f  cmp     [rbp+450h+var_458], 8
0x180070b44  cmovnb  r9, [rbp+450h+Block]
0x180070b49  lea     rax, [rsp+550h+var_500]
0x180070b4e  mov     [rsp+550h+var_510], rax
0x180070b53  mov     rdx, rdi; struct CSrmDebugInfo *
0x180070b56  lea     rcx, [rsp+550h+var_500]; this
0x180070b5b  call    ??0CSrmDebugInfo@@QEAA@AEBU0@@Z; CSrmDebugInfo::CSrmDebugInfo(CSrmDebugInfo const &)
0x180070b60  nop
0x180070b61  mov     qword ptr [rsp+550h+nSize], r9
0x180070b66  mov     dword ptr [rsp+550h+lpBuffer], esi
0x180070b6a  lea     r9, aXS; "(%#x) %s"
0x180070b71  mov     r8d, 3F0h
0x180070b77  mov     rdx, rax
0x180070b7a  mov     rcx, r14
0x180070b7d  call    ?AddErrorSpecificContext@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@IPEBGZZ; CSrmFunctionTracer::AddErrorSpecificContext(CSrmDebugInfo,uint,ushort const *,...)
0x180070b82  nop
0x180070b83  cmp     [rbp+450h+var_458], 8
0x180070b88  jb      short loc_180070B93
0x180070b8a  mov     rcx, [rbp+450h+Block]; Block
0x180070b8e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180070b93  mov     [rbp+450h+var_458], 7
0x180070b9b  mov     [rbp+450h+var_460], r15
0x180070b9f  mov     word ptr [rbp+450h+Block], r15w
0x180070ba4  mov     rcx, rdi; this
0x180070ba7  call    ??1CSrmDebugInfo@@QEAA@XZ; CSrmDebugInfo::~CSrmDebugInfo(void)
0x180070bac  mov     rcx, [rbp+450h+var_30]
0x180070bb3  xor     rcx, rsp; StackCookie
0x180070bb6  call    __security_check_cookie
0x180070bbb  mov     rbx, [rsp+550h+arg_18]
0x180070bc3  add     rsp, 530h
0x180070bca  pop     r15
0x180070bcc  pop     r14
0x180070bce  pop     rdi
0x180070bcf  pop     rsi
0x180070bd0  pop     rbp
0x180070bd1  retn
```
