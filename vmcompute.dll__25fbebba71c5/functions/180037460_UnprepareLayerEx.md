# UnprepareLayerEx

- ea: `0x180037460`
- end: `0x1800375d4`
- name: `UnprepareLayerEx`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x180037450`

## callees

- `0x180002f50`
- `0x180006660`
- `0x18000d108`
- `0x180022d10`
- `0x18003012c`
- `0x180030498`
- `0x180036110`
- `0x180037460`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x180037501`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x180037501`
- `wc_storage!WcDetachFilterEx` at `0x180037539`
- `wc_storage!WcDetachFilterEx` at `0x180037539`

## string_xrefs

- `0x18003757c`: `onecore\vm\compute\dll\legacy\src\graphdriver.cpp`
- `0x180037590`: `onecore\vm\compute\dll\legacy\src\graphdriver.cpp`
- `0x1800375ad`: `onecore\vm\compute\dll\legacy\src\graphdriver.cpp`
- `0x1800375c1`: `onecore\vm\compute\dll\legacy\src\graphdriver.cpp`

## pseudocode

```c
__int64 __fastcall UnprepareLayerEx(__int64 a1, __int64 a2, unsigned int a3)
{
  _QWORD *v6; // rax
  int v7; // ebx
  const char *v8; // r9
  int LayerMountPath; // eax
  HRESULT v10; // eax
  __int64 v11; // rax
  int v12; // eax
  __int64 result; // rax
  unsigned int v14[2]; // [rsp+20h] [rbp-278h] BYREF
  _BYTE Src[40]; // [rsp+28h] [rbp-270h] BYREF
  WCHAR pszPath[264]; // [rsp+50h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+0h]

  try
  {
    v6 = (_QWORD *)anonymous_namespace_::LayerDiskPath(Src);
    if ( v6[3] > 7u )
      v6 = (_QWORD *)*v6;
    v7 = anonymous_namespace_::FileExists(v6);
    std::wstring::~wstring(Src);
    if ( v7 )
    {
      *(_QWORD *)v14 = 260;
      pszPath[0] = 0;
      LayerMountPath = GetLayerMountPath(a1, a2, v14, pszPath);
      if ( LayerMountPath < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3BE,
          (unsigned int)"onecore\\vm\\compute\\dll\\legacy\\src\\graphdriver.cpp",
          (const char *)(unsigned int)LayerMountPath,
          v14[0]);
      v10 = PathCchAddBackslash(pszPath, 0x104u);
      if ( v10 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3C0,
          (unsigned int)"onecore\\vm\\compute\\dll\\legacy\\src\\graphdriver.cpp",
          (const char *)(unsigned int)v10,
          v14[0]);
      v11 = -1;
      do
        ++v11;
      while ( pszPath[v11] );
      if ( !v11 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x3C5,
          (unsigned int)"onecore\\vm\\compute\\dll\\legacy\\src\\graphdriver.cpp",
          (const char *)0x15,
          v14[0]);
      v12 = WcDetachFilterEx(pszPath, a3);
      if ( v12 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3C8,
          (unsigned int)"onecore\\vm\\compute\\dll\\legacy\\src\\graphdriver.cpp",
          (const char *)(unsigned int)v12,
          v14[0]);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x3CD,
                           (unsigned int)"onecore\\vm\\compute\\dll\\legacy\\src\\graphdriver.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x180037460  push    rbx
0x180037462  push    rsi
0x180037463  push    rdi
0x180037464  push    r14
0x180037466  push    r15
0x180037468  sub     rsp, 270h
0x18003746f  mov     rax, cs:__security_cookie
0x180037476  xor     rax, rsp
0x180037479  mov     [rsp+298h+var_38], rax
0x180037481  mov     r14d, r8d
0x180037484  mov     rsi, rdx
0x180037487  mov     rdi, rcx
0x18003748a  mov     r8, rdx
0x18003748d  mov     rdx, [rcx+8]
0x180037491  lea     rcx, [rsp+298h+Src]; Src
0x180037496  call    _anonymous_namespace___LayerDiskPath
0x18003749b  cmp     qword ptr [rax+18h], 7
0x1800374a0  jbe     short loc_1800374A5
0x1800374a2  mov     rax, [rax]
0x1800374a5  mov     rcx, rax
0x1800374a8  call    _anonymous_namespace___FileExists
0x1800374ad  mov     ebx, eax
0x1800374af  lea     rcx, [rsp+298h+Src]
0x1800374b4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800374b9  xor     r15d, r15d
0x1800374bc  test    ebx, ebx
0x1800374be  jz      loc_180037551
0x1800374c4  mov     ebx, 104h
0x1800374c9  mov     qword ptr [rsp+298h+var_278], rbx; int
0x1800374ce  mov     [rsp+298h+pszPath], r15w
0x1800374d4  lea     r9, [rsp+298h+pszPath]
0x1800374d9  lea     r8, [rsp+298h+var_278]
0x1800374de  mov     rdx, rsi
0x1800374e1  mov     rcx, rdi
0x1800374e4  call    GetLayerMountPath
0x1800374e9  mov     rcx, [rsp+298h]; this
0x1800374f1  test    eax, eax
0x1800374f3  js      loc_180037579
0x1800374f9  mov     rdx, rbx; cchPath
0x1800374fc  lea     rcx, [rsp+298h+pszPath]; pszPath
0x180037501  call    cs:__imp_PathCchAddBackslash
0x180037508  nop     dword ptr [rax+rax+00h]
0x18003750d  mov     rcx, [rsp+298h]; this
0x180037515  test    eax, eax
0x180037517  js      short loc_18003758D
0x180037519  lea     rcx, [rsp+298h+pszPath]
0x18003751e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180037522  inc     rax
0x180037525  cmp     [rcx+rax*2], r15w
0x18003752a  jnz     short loc_180037522
0x18003752c  test    rax, rax
0x18003752f  jz      short loc_1800375A1
0x180037531  mov     edx, r14d
0x180037534  lea     rcx, [rsp+298h+pszPath]
0x180037539  call    cs:__imp_WcDetachFilterEx
0x180037540  nop     dword ptr [rax+rax+00h]
0x180037545  mov     rcx, [rsp+298h]; this
0x18003754d  test    eax, eax
0x18003754f  js      short loc_1800375BE
0x180037551  xor     eax, eax
0x180037553  jmp     short loc_180037559
0x180037555  mov     eax, [rsp+298h+var_278]
0x180037559  mov     rcx, [rsp+298h+var_38]
0x180037561  xor     rcx, rsp; StackCookie
0x180037564  call    __security_check_cookie
0x180037569  add     rsp, 270h
0x180037570  pop     r15
0x180037572  pop     r14
0x180037574  pop     rdi
0x180037575  pop     rsi
0x180037576  pop     rbx
0x180037577  retn
0x180037579  mov     r9d, eax; char *
0x18003757c  lea     r8, aOnecoreVmCompu_21; "onecore\\vm\\compute\\dll\\legacy\\src"...
0x180037583  mov     edx, 3BEh; void *
0x180037588  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003758d  mov     r9d, eax; char *
0x180037590  lea     r8, aOnecoreVmCompu_21; "onecore\\vm\\compute\\dll\\legacy\\src"...
0x180037597  mov     edx, 3C0h; void *
0x18003759c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800375a1  mov     rcx, [rsp+298h]; this
0x1800375a9  lea     r9d, [rax+15h]; char *
0x1800375ad  lea     r8, aOnecoreVmCompu_21; "onecore\\vm\\compute\\dll\\legacy\\src"...
0x1800375b4  mov     edx, 3C5h; void *
0x1800375b9  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800375be  mov     r9d, eax; char *
0x1800375c1  lea     r8, aOnecoreVmCompu_21; "onecore\\vm\\compute\\dll\\legacy\\src"...
0x1800375c8  mov     edx, 3C8h; void *
0x1800375cd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
