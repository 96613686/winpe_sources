# CSrmFunctionTracerBase::GetErrorText(void)

- ea: `0x1800718cc`
- end: `0x180071a70`
- name: `?GetErrorText@CSrmFunctionTracerBase@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `420`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180018064`
- `0x180018b04`
- `0x180072b44`
- `0x18009cf88`

## callees

- `0x18000eef4`
- `0x180017fd8`
- `0x1800718cc`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x1800719eb`
- `KERNEL32!FreeLibrary` at `0x1800719eb`
- `KERNEL32!LoadLibraryExW` at `0x1800719a1`
- `KERNEL32!LoadLibraryExW` at `0x1800719a1`
- `KERNEL32!FormatMessageW` at `0x180071984`
- `KERNEL32!FormatMessageW` at `0x1800719d8`
- `KERNEL32!FormatMessageW` at `0x180071984`
- `KERNEL32!FormatMessageW` at `0x1800719d8`

## string_xrefs

- `0x18007199a`: `srm.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall CSrmFunctionTracerBase::GetErrorText(__int64 a1, _QWORD *a2)
{
  HMODULE Library; // rsi
  __int64 v5; // r9
  WCHAR Buffer; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v8[1038]; // [rsp+52h] [rbp-AEh] BYREF
  unsigned __int16 v9; // [rsp+460h] [rbp+360h] BYREF
  _BYTE v10[1086]; // [rsp+462h] [rbp+362h] BYREF

  if ( *(int *)(a1 + 8) < 0 )
  {
    v9 = 0;
    memset_0(v10, 0, 0x43Cu);
    Buffer = 0;
    memset_0(v8, 0, 0x400u);
    if ( !FormatMessageW(0x1200u, 0, *(_DWORD *)(a1 + 8), 0x400u, &Buffer, 0x200u, 0) )
    {
      Buffer = 0;
      Library = LoadLibraryExW(L"srm.dll", 0, 2u);
      if ( Library )
      {
        if ( !FormatMessageW(0xA00u, Library, *(_DWORD *)(a1 + 8), 0x400u, &Buffer, 0x200u, 0) )
          Buffer = 0;
        FreeLibrary(Library);
      }
    }
    v5 = *(unsigned int *)(a1 + 8);
    if ( Buffer )
      StringCchPrintfW(&v9, 0x21Fu, L"0x%08lx, %s", v5, &Buffer);
    else
      StringCchPrintfW(&v9, 0x21Fu, L"0x%08lx", v5);
    std::wstring::wstring(a2, &v9);
  }
  else
  {
    a2[3] = 7;
    a2[2] = 0;
    *(_WORD *)a2 = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x1800718cc  mov     [rsp-8+arg_10], rbx
0x1800718d1  mov     [rsp-8+arg_18], rsi
0x1800718d6  push    rbp
0x1800718d7  push    rdi
0x1800718d8  push    r14
0x1800718da  lea     rbp, [rsp-7B0h]
0x1800718e2  sub     rsp, 8B0h
0x1800718e9  mov     rax, cs:__security_cookie
0x1800718f0  xor     rax, rsp
0x1800718f3  mov     [rbp+7C0h+var_20], rax
0x1800718fa  mov     rbx, rdx
0x1800718fd  mov     rdi, rcx
0x180071900  mov     [rsp+8C0h+var_878], rdx
0x180071905  xor     r14d, r14d
0x180071908  mov     [rsp+8C0h+var_880], r14d
0x18007190d  cmp     [rcx+8], r14d
0x180071911  jl      short loc_180071928
0x180071913  mov     qword ptr [rdx+18h], 7
0x18007191b  mov     [rdx+10h], r14
0x18007191f  mov     [rdx], r14w
0x180071923  jmp     loc_180071A3D
0x180071928  mov     [rbp+7C0h+var_460], r14w
0x180071930  xor     edx, edx; Val
0x180071932  mov     r8d, 43Ch; Size
0x180071938  lea     rcx, [rbp+7C0h+var_45E]; void *
0x18007193f  call    memset_0
0x180071944  mov     [rsp+8C0h+Buffer], r14w
0x18007194a  xor     edx, edx; Val
0x18007194c  mov     r8d, 400h; Size
0x180071952  lea     rcx, [rsp+8C0h+var_86E]; void *
0x180071957  call    memset_0
0x18007195c  mov     [rsp+8C0h+Arguments], r14; Arguments
0x180071961  mov     [rsp+8C0h+nSize], 200h; nSize
0x180071969  lea     rax, [rsp+8C0h+Buffer]
0x18007196e  mov     [rsp+8C0h+lpBuffer], rax; lpBuffer
0x180071973  mov     r9d, 400h; dwLanguageId
0x180071979  mov     r8d, [rdi+8]; dwMessageId
0x18007197d  xor     edx, edx; lpSource
0x18007197f  mov     ecx, 1200h; dwFlags
0x180071984  call    cs:__imp_FormatMessageW
0x18007198a  test    eax, eax
0x18007198c  jnz     short loc_1800719F1
0x18007198e  mov     [rsp+8C0h+Buffer], r14w
0x180071994  xor     edx, edx; hFile
0x180071996  lea     r8d, [rax+2]; dwFlags
0x18007199a  lea     rcx, aSrmDll_0; "srm.dll"
0x1800719a1  call    cs:__imp_LoadLibraryExW
0x1800719a7  mov     rsi, rax
0x1800719aa  test    rax, rax
0x1800719ad  jz      short loc_1800719F1
0x1800719af  mov     [rsp+8C0h+Arguments], r14; Arguments
0x1800719b4  mov     [rsp+8C0h+nSize], 200h; nSize
0x1800719bc  lea     rax, [rsp+8C0h+Buffer]
0x1800719c1  mov     [rsp+8C0h+lpBuffer], rax; lpBuffer
0x1800719c6  mov     r9d, 400h; dwLanguageId
0x1800719cc  mov     r8d, [rdi+8]; dwMessageId
0x1800719d0  mov     rdx, rsi; lpSource
0x1800719d3  mov     ecx, 0A00h; dwFlags
0x1800719d8  call    cs:__imp_FormatMessageW
0x1800719de  test    eax, eax
0x1800719e0  jnz     short loc_1800719E8
0x1800719e2  mov     [rsp+8C0h+Buffer], r14w
0x1800719e8  mov     rcx, rsi; hLibModule
0x1800719eb  call    cs:__imp_FreeLibrary
0x1800719f1  mov     r9d, [rdi+8]
0x1800719f5  mov     edx, 21Fh; unsigned __int64
0x1800719fa  lea     rcx, [rbp+7C0h+var_460]; unsigned __int16 *
0x180071a01  cmp     [rsp+8C0h+Buffer], r14w
0x180071a07  jz      short loc_180071A21
0x180071a09  lea     rax, [rsp+8C0h+Buffer]
0x180071a0e  mov     [rsp+8C0h+lpBuffer], rax
0x180071a13  lea     r8, a0x08lxS; "0x%08lx, %s"
0x180071a1a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180071a1f  jmp     short loc_180071A2D
0x180071a21  lea     r8, a0x08lx; "0x%08lx"
0x180071a28  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180071a2d  lea     rdx, [rbp+7C0h+var_460]
0x180071a34  mov     rcx, rbx; void *
0x180071a37  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180071a3c  nop
0x180071a3d  mov     [rsp+8C0h+var_880], 1
0x180071a45  mov     rax, rbx
0x180071a48  mov     rcx, [rbp+7C0h+var_20]
0x180071a4f  xor     rcx, rsp; StackCookie
0x180071a52  call    __security_check_cookie
0x180071a57  lea     r11, [rsp+8C0h+var_10]
0x180071a5f  mov     rbx, [r11+30h]
0x180071a63  mov     rsi, [r11+38h]
0x180071a67  mov     rsp, r11
0x180071a6a  pop     r14
0x180071a6c  pop     rdi
0x180071a6d  pop     rbp
0x180071a6e  retn
```
