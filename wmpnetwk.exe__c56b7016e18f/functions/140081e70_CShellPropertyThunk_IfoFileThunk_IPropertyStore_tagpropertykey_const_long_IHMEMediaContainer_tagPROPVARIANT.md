# CShellPropertyThunk::IfoFileThunk(IPropertyStore *,_tagpropertykey const &,long,IHMEMediaContainer *,tagPROPVARIANT *)

- ea: `0x140081e70`
- end: `0x140081fc5`
- name: `?IfoFileThunk@CShellPropertyThunk@@CAJPEAUIPropertyStore@@AEBU_tagpropertykey@@JPEAUIHMEMediaContainer@@PEAUtagPROPVARIANT@@@Z`
- size: `341`
- prototype: `__int64 __fastcall(struct IPropertyStore *, const struct _tagpropertykey *, int, struct IHMEMediaContainer *, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x14002defc`
- `0x140045f20`
- `0x140081e70`
- `0x14009e010`

## import_xrefs

- `KERNEL32!GetFileAttributesExW` at `0x140081f5f`
- `KERNEL32!GetFileAttributesExW` at `0x140081f5f`
- `ole32!PropVariantClear` at `0x140081f92`
- `ole32!PropVariantClear` at `0x140081f92`
- `SHLWAPI!PathCreateFromUrlW` at `0x140081f04`
- `SHLWAPI!PathCreateFromUrlW` at `0x140081f04`

## pseudocode

```c
__int64 __fastcall CShellPropertyThunk::IfoFileThunk(
        struct IPropertyStore *a1,
        const struct _tagpropertykey *a2,
        int a3,
        struct IHMEMediaContainer *a4,
        struct tagPROPVARIANT *a5)
{
  struct IPropertyStoreVtbl *lpVtbl; // rax
  HRESULT inited; // ebx
  DWORD v7; // eax
  DWORD pcchPath; // [rsp+20h] [rbp-E0h] BYREF
  PCWSTR pszUrl[2]; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v11; // [rsp+38h] [rbp-C8h]
  _OWORD FileInformation[2]; // [rsp+40h] [rbp-C0h] BYREF
  int v13; // [rsp+60h] [rbp-A0h]
  WCHAR pszPath[264]; // [rsp+70h] [rbp-90h] BYREF

  if ( a3 )
  {
    return (unsigned int)-2147023728;
  }
  else
  {
    v11 = 0;
    lpVtbl = a1->lpVtbl;
    *(_OWORD *)pszUrl = 0;
    if ( ((int (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PCWSTR *, struct IHMEMediaContainer *))lpVtbl->GetValue)(
           a1,
           &PKEY_ItemUrl,
           pszUrl,
           a4) >= 0
      && LOWORD(pszUrl[0]) == 31
      && (pcchPath = 260, inited = PathCreateFromUrlW(pszUrl[1], pszPath, &pcchPath, 0), inited >= 0)
      && (v7 = pcchPath, pcchPath > 5) )
    {
      pszPath[pcchPath - 3] = 105;
      pszPath[v7 - 2] = 102;
      pszPath[v7 - 1] = 111;
      v13 = 0;
      memset(FileInformation, 0, sizeof(FileInformation));
      if ( GetFileAttributesExW(pszPath, GetFileExInfoStandard, FileInformation) && (FileInformation[0] & 0xA1) != 0 )
        inited = InitPropVariantFromString(pszPath, a5);
      else
        a5->vt = 0;
    }
    else
    {
      inited = -2147023728;
    }
    PropVariantClear((PROPVARIANT *)pszUrl);
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x140081e70  mov     [rsp-8+arg_8], rbx
0x140081e75  mov     [rsp-8+arg_10], rdi
0x140081e7a  push    rbp
0x140081e7b  lea     rbp, [rsp-190h]
0x140081e83  sub     rsp, 290h
0x140081e8a  mov     rax, cs:__security_cookie
0x140081e91  xor     rax, rsp
0x140081e94  mov     [rbp+190h+var_10], rax
0x140081e9b  mov     rdi, [rbp+190h+arg_20]
0x140081ea2  test    r8d, r8d
0x140081ea5  jnz     loc_140081F9A
0x140081eab  xor     eax, eax
0x140081ead  lea     r8, [rsp+290h+pszUrl]
0x140081eb2  mov     [rsp+290h+var_258], rax
0x140081eb7  lea     rdx, PKEY_ItemUrl
0x140081ebe  mov     rax, [rcx]
0x140081ec1  xorps   xmm0, xmm0
0x140081ec4  movups  xmmword ptr [rsp+290h+pszUrl], xmm0
0x140081ec9  mov     rax, [rax+28h]
0x140081ecd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140081ed2  test    eax, eax
0x140081ed4  js      loc_140081F88
0x140081eda  mov     eax, 1Fh
0x140081edf  cmp     ax, word ptr [rsp+290h+pszUrl]
0x140081ee4  jnz     loc_140081F88
0x140081eea  mov     rcx, [rsp+290h+pszUrl+8]; pszUrl
0x140081eef  lea     r8, [rsp+290h+pcchPath]; pcchPath
0x140081ef4  xor     r9d, r9d; dwFlags
0x140081ef7  mov     [rsp+290h+pcchPath], 104h
0x140081eff  lea     rdx, [rsp+290h+pszPath]; pszPath
0x140081f04  call    cs:__imp_PathCreateFromUrlW
0x140081f0a  mov     ebx, eax
0x140081f0c  test    eax, eax
0x140081f0e  js      short loc_140081F88
0x140081f10  mov     eax, [rsp+290h+pcchPath]
0x140081f14  cmp     eax, 5
0x140081f17  jbe     short loc_140081F88
0x140081f19  lea     edx, [rax-3]
0x140081f1c  mov     ecx, 69h ; 'i'
0x140081f21  mov     [rsp+rdx*2+290h+pszPath], cx
0x140081f26  lea     r8, [rsp+290h+FileInformation]; lpFileInformation
0x140081f2b  lea     edx, [rax-2]
0x140081f2e  mov     ecx, 66h ; 'f'
0x140081f33  mov     [rsp+rdx*2+290h+pszPath], cx
0x140081f38  xorps   xmm0, xmm0
0x140081f3b  lea     ecx, [rax-1]
0x140081f3e  xor     edx, edx; fInfoLevelId
0x140081f40  mov     eax, 6Fh ; 'o'
0x140081f45  mov     [rsp+rcx*2+290h+pszPath], ax
0x140081f4a  xor     eax, eax
0x140081f4c  lea     rcx, [rsp+290h+pszPath]; lpFileName
0x140081f51  mov     [rsp+290h+var_230], eax
0x140081f55  movups  [rsp+290h+FileInformation], xmm0
0x140081f5a  movups  [rsp+290h+var_240], xmm0
0x140081f5f  call    cs:__imp_GetFileAttributesExW
0x140081f65  test    eax, eax
0x140081f67  jz      short loc_140081F81
0x140081f69  test    byte ptr [rsp+290h+FileInformation], 0A1h
0x140081f6e  jz      short loc_140081F81
0x140081f70  mov     rdx, rdi; struct tagPROPVARIANT *
0x140081f73  lea     rcx, [rsp+290h+pszPath]; Src
0x140081f78  call    ?InitPropVariantFromString@@YAJPEBGPEAUtagPROPVARIANT@@@Z; InitPropVariantFromString(ushort const *,tagPROPVARIANT *)
0x140081f7d  mov     ebx, eax
0x140081f7f  jmp     short loc_140081F8D
0x140081f81  xor     eax, eax
0x140081f83  mov     [rdi], ax
0x140081f86  jmp     short loc_140081F8D
0x140081f88  mov     ebx, 80070490h
0x140081f8d  lea     rcx, [rsp+290h+pszUrl]; pvar
0x140081f92  call    cs:__imp_PropVariantClear
0x140081f98  jmp     short loc_140081F9F
0x140081f9a  mov     ebx, 80070490h
0x140081f9f  mov     eax, ebx
0x140081fa1  mov     rcx, [rbp+190h+var_10]
0x140081fa8  xor     rcx, rsp; StackCookie
0x140081fab  call    __security_check_cookie
0x140081fb0  lea     r11, [rsp+290h+var_s0]
0x140081fb8  mov     rbx, [r11+18h]
0x140081fbc  mov     rdi, [r11+20h]
0x140081fc0  mov     rsp, r11
0x140081fc3  pop     rbp
0x140081fc4  retn
```
