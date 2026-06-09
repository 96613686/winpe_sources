# DAV_SITE_CONFIG::Initialize(INativeConfigurationElement *,INativeSectionException * *)

- ea: `0x18000fcc4`
- end: `0x18000ffe6`
- name: `?Initialize@DAV_SITE_CONFIG@@QEAAJPEAVINativeConfigurationElement@@PEAPEAVINativeSectionException@@@Z`
- size: `802`
- prototype: `__int64 __fastcall(DAV_SITE_CONFIG *__hidden this, struct INativeConfigurationElement *, struct INativeSectionException **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010384`

## callees

- `0x18000fcc4`
- `0x180023010`

## string_xrefs

- `0x18000fd4a`: `compatFlags`
- `0x18000fd81`: `maxAllowedXmlRequestLength`
- `0x18000fe4d`: `readBufferSize`

## pseudocode

```c
__int64 __fastcall DAV_SITE_CONFIG::Initialize(
        DAV_SITE_CONFIG *this,
        struct INativeConfigurationElement *a2,
        struct INativeSectionException **a3)
{
  __int64 v3; // rax
  int v6; // ebx
  struct INativeSectionException **v7; // rcx
  struct INativeSectionException **v9; // [rsp+80h] [rbp+48h] BYREF

  v9 = a3;
  v3 = *(_QWORD *)a2;
  v9 = 0;
  v6 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, char *, _QWORD, _QWORD))(v3 + 72))(
         a2,
         L"enabled",
         (char *)this + 8,
         0,
         0);
  if ( v6 < 0 )
    goto LABEL_22;
  if ( !*((_DWORD *)this + 2) )
    goto LABEL_22;
  v6 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)a2 + 72LL))(
         a2,
         L"requireSsl",
         (char *)this + 12,
         0,
         0);
  if ( v6 < 0 )
    goto LABEL_22;
  v6 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, DAV_SITE_CONFIG *, _QWORD, _QWORD))(*(_QWORD *)a2 + 48LL))(
         a2,
         L"compatFlags",
         this,
         0,
         0);
  if ( v6 < 0 )
    goto LABEL_22;
  v6 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)a2 + 48LL))(
         a2,
         L"maxAllowedXmlRequestLength",
         (char *)this + 4,
         0,
         0);
  if ( v6 < 0 )
    goto LABEL_22;
  v6 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, struct INativeSectionException ***))(*(_QWORD *)a2 + 32LL))(
         a2,
         L"fileSystem",
         &v9);
  if ( v6 < 0 )
    goto LABEL_22;
  v6 = (*((__int64 (__fastcall **)(struct INativeSectionException **, const wchar_t *, char *, _QWORD, _QWORD))*v9 + 9))(
         v9,
         L"allowHiddenFiles",
         (char *)this + 16,
         0,
         0);
  if ( v6 >= 0 )
  {
    v6 = (*((__int64 (__fastcall **)(struct INativeSectionException **, const wchar_t *, char *, _QWORD, _QWORD))*v9 + 9))(
           v9,
           L"useTransactionalIo",
           (char *)this + 20,
           0,
           0);
    if ( v6 >= 0 )
    {
      v6 = (*((__int64 (__fastcall **)(struct INativeSectionException **, const wchar_t *, char *, _QWORD, _QWORD))*v9
            + 9))(
             v9,
             L"hideChildVirtualDirectories",
             (char *)this + 24,
             0,
             0);
      if ( v6 >= 0 )
        v6 = (*((__int64 (__fastcall **)(struct INativeSectionException **, const wchar_t *, char *, _QWORD, _QWORD))*v9
              + 6))(
               v9,
               L"readBufferSize",
               (char *)this + 28,
               0,
               0);
    }
  }
  (*((void (__fastcall **)(struct INativeSectionException **))*v9 + 2))(v9);
  v9 = 0;
  if ( v6 >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, struct INativeSectionException ***))(*(_QWORD *)a2 + 32LL))(
           a2,
           L"properties",
           &v9);
    if ( v6 < 0 )
      goto LABEL_22;
    v6 = (*((__int64 (__fastcall **)(struct INativeSectionException **, const wchar_t *, char *, _QWORD, _QWORD))*v9 + 9))(
           v9,
           L"allowAnonymousPropfind",
           (char *)this + 32,
           0,
           0);
    if ( v6 >= 0 )
    {
      v6 = (*((__int64 (__fastcall **)(struct INativeSectionException **, const wchar_t *, char *, _QWORD, _QWORD))*v9
            + 9))(
             v9,
             L"allowInfinitePropfindDepth",
             (char *)this + 36,
             0,
             0);
      if ( v6 >= 0 )
        v6 = (*((__int64 (__fastcall **)(struct INativeSectionException **, const wchar_t *, char *, _QWORD, _QWORD))*v9
              + 9))(
               v9,
               L"allowCustomProperties",
               (char *)this + 40,
               0,
               0);
    }
    (*((void (__fastcall **)(struct INativeSectionException **))*v9 + 2))(v9);
    v9 = 0;
    if ( v6 >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, struct INativeSectionException ***))(*(_QWORD *)a2 + 32LL))(
             a2,
             L"locks",
             &v9);
      if ( v6 >= 0 )
      {
        v6 = (*((__int64 (__fastcall **)(struct INativeSectionException **, const wchar_t *, char *, _QWORD, _QWORD))*v9
              + 9))(
               v9,
               L"enabled",
               (char *)this + 44,
               0,
               0);
        if ( v6 >= 0 && *((_DWORD *)this + 11) )
          v6 = (*((__int64 (__fastcall **)(struct INativeSectionException **, const wchar_t *, char *, _QWORD, _QWORD))*v9
                + 9))(
                 v9,
                 L"requireLockForWriting",
                 (char *)this + 48,
                 0,
                 0);
        (*((void (__fastcall **)(struct INativeSectionException **))*v9 + 2))(v9);
        v7 = 0;
        v9 = 0;
        goto LABEL_23;
      }
LABEL_22:
      v7 = v9;
LABEL_23:
      if ( v7 )
        (*((void (__fastcall **)(struct INativeSectionException **))*v7 + 2))(v7);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000fcc4  mov     [rsp-30h+arg_10], r8
0x18000fcc9  push    rbp
0x18000fcca  push    rbx
0x18000fccb  push    rsi
0x18000fccc  push    rdi
0x18000fccd  push    r14
0x18000fccf  push    r15
0x18000fcd1  mov     rbp, rsp
0x18000fcd4  sub     rsp, 38h
0x18000fcd8  mov     rax, [rdx]
0x18000fcdb  lea     r8, [rcx+8]
0x18000fcdf  mov     rdi, rdx
0x18000fce2  mov     rsi, rcx
0x18000fce5  xor     r15d, r15d
0x18000fce8  lea     rdx, aEnabled; "enabled"
0x18000fcef  xor     r9d, r9d
0x18000fcf2  mov     [rbp+arg_10], r15
0x18000fcf6  mov     rax, [rax+48h]
0x18000fcfa  mov     rcx, rdi
0x18000fcfd  mov     [rsp+38h+var_18], r15
0x18000fd02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd07  mov     ebx, eax
0x18000fd09  test    eax, eax
0x18000fd0b  js      loc_18000FFC2
0x18000fd11  cmp     [rsi+8], r15d
0x18000fd15  jz      loc_18000FFC2
0x18000fd1b  mov     rax, [rdi]
0x18000fd1e  lea     r8, [rsi+0Ch]
0x18000fd22  xor     r9d, r9d
0x18000fd25  mov     [rsp+38h+var_18], r15
0x18000fd2a  lea     rdx, aRequiressl; "requireSsl"
0x18000fd31  mov     rcx, rdi
0x18000fd34  mov     rax, [rax+48h]
0x18000fd38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd3d  mov     ebx, eax
0x18000fd3f  test    eax, eax
0x18000fd41  js      loc_18000FFC2
0x18000fd47  mov     rax, [rdi]
0x18000fd4a  lea     rdx, aCompatflags; "compatFlags"
0x18000fd51  xor     r9d, r9d
0x18000fd54  mov     [rsp+38h+var_18], r15
0x18000fd59  mov     r8, rsi
0x18000fd5c  mov     rcx, rdi
0x18000fd5f  mov     rax, [rax+30h]
0x18000fd63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd68  mov     ebx, eax
0x18000fd6a  test    eax, eax
0x18000fd6c  js      loc_18000FFC2
0x18000fd72  mov     rax, [rdi]
0x18000fd75  lea     r8, [rsi+4]
0x18000fd79  xor     r9d, r9d
0x18000fd7c  mov     [rsp+38h+var_18], r15
0x18000fd81  lea     rdx, aMaxallowedxmlr; "maxAllowedXmlRequestLength"
0x18000fd88  mov     rcx, rdi
0x18000fd8b  mov     rax, [rax+30h]
0x18000fd8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd94  mov     ebx, eax
0x18000fd96  test    eax, eax
0x18000fd98  js      loc_18000FFC2
0x18000fd9e  mov     rax, [rdi]
0x18000fda1  lea     r8, [rbp+arg_10]
0x18000fda5  lea     rdx, aFilesystem; "fileSystem"
0x18000fdac  mov     rcx, rdi
0x18000fdaf  mov     rax, [rax+20h]
0x18000fdb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fdb8  mov     ebx, eax
0x18000fdba  test    eax, eax
0x18000fdbc  js      loc_18000FFC2
0x18000fdc2  mov     rcx, [rbp+arg_10]
0x18000fdc6  lea     r8, [rsi+10h]
0x18000fdca  xor     r9d, r9d
0x18000fdcd  mov     [rsp+38h+var_18], r15
0x18000fdd2  lea     rdx, aAllowhiddenfil; "allowHiddenFiles"
0x18000fdd9  mov     rax, [rcx]
0x18000fddc  mov     rax, [rax+48h]
0x18000fde0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fde5  mov     ebx, eax
0x18000fde7  test    eax, eax
0x18000fde9  js      short loc_18000FE62
0x18000fdeb  mov     rcx, [rbp+arg_10]
0x18000fdef  lea     r8, [rsi+14h]
0x18000fdf3  xor     r9d, r9d
0x18000fdf6  mov     [rsp+38h+var_18], r15
0x18000fdfb  lea     rdx, aUsetransaction; "useTransactionalIo"
0x18000fe02  mov     rax, [rcx]
0x18000fe05  mov     rax, [rax+48h]
0x18000fe09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe0e  mov     ebx, eax
0x18000fe10  test    eax, eax
0x18000fe12  js      short loc_18000FE62
0x18000fe14  mov     rcx, [rbp+arg_10]
0x18000fe18  lea     r8, [rsi+18h]
0x18000fe1c  xor     r9d, r9d
0x18000fe1f  mov     [rsp+38h+var_18], r15
0x18000fe24  lea     rdx, aHidechildvirtu; "hideChildVirtualDirectories"
0x18000fe2b  mov     rax, [rcx]
0x18000fe2e  mov     rax, [rax+48h]
0x18000fe32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe37  mov     ebx, eax
0x18000fe39  test    eax, eax
0x18000fe3b  js      short loc_18000FE62
0x18000fe3d  mov     rcx, [rbp+arg_10]
0x18000fe41  lea     r8, [rsi+1Ch]
0x18000fe45  xor     r9d, r9d
0x18000fe48  mov     [rsp+38h+var_18], r15
0x18000fe4d  lea     rdx, aReadbuffersize; "readBufferSize"
0x18000fe54  mov     rax, [rcx]
0x18000fe57  mov     rax, [rax+30h]
0x18000fe5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe60  mov     ebx, eax
0x18000fe62  mov     rcx, [rbp+arg_10]
0x18000fe66  mov     rax, [rcx]
0x18000fe69  mov     rax, [rax+10h]
0x18000fe6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe72  mov     [rbp+arg_10], r15
0x18000fe76  test    ebx, ebx
0x18000fe78  js      loc_18000FFD7
0x18000fe7e  mov     rax, [rdi]
0x18000fe81  lea     r8, [rbp+arg_10]
0x18000fe85  lea     rdx, aProperties; "properties"
0x18000fe8c  mov     rcx, rdi
0x18000fe8f  mov     rax, [rax+20h]
0x18000fe93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe98  mov     ebx, eax
0x18000fe9a  test    eax, eax
0x18000fe9c  js      loc_18000FFC2
0x18000fea2  mov     rcx, [rbp+arg_10]
0x18000fea6  lea     r8, [rsi+20h]
0x18000feaa  xor     r9d, r9d
0x18000fead  mov     [rsp+38h+var_18], r15
0x18000feb2  lea     rdx, aAllowanonymous; "allowAnonymousPropfind"
0x18000feb9  mov     rax, [rcx]
0x18000febc  mov     rax, [rax+48h]
0x18000fec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fec5  mov     ebx, eax
0x18000fec7  test    eax, eax
0x18000fec9  js      short loc_18000FF19
0x18000fecb  mov     rcx, [rbp+arg_10]
0x18000fecf  lea     r8, [rsi+24h]
0x18000fed3  xor     r9d, r9d
0x18000fed6  mov     [rsp+38h+var_18], r15
0x18000fedb  lea     rdx, aAllowinfinitep; "allowInfinitePropfindDepth"
0x18000fee2  mov     rax, [rcx]
0x18000fee5  mov     rax, [rax+48h]
0x18000fee9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000feee  mov     ebx, eax
0x18000fef0  test    eax, eax
0x18000fef2  js      short loc_18000FF19
0x18000fef4  mov     rcx, [rbp+arg_10]
0x18000fef8  lea     r8, [rsi+28h]
0x18000fefc  xor     r9d, r9d
0x18000feff  mov     [rsp+38h+var_18], r15
0x18000ff04  lea     rdx, aAllowcustompro; "allowCustomProperties"
0x18000ff0b  mov     rax, [rcx]
0x18000ff0e  mov     rax, [rax+48h]
0x18000ff12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff17  mov     ebx, eax
0x18000ff19  mov     rcx, [rbp+arg_10]
0x18000ff1d  mov     rax, [rcx]
0x18000ff20  mov     rax, [rax+10h]
0x18000ff24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff29  mov     [rbp+arg_10], r15
0x18000ff2d  test    ebx, ebx
0x18000ff2f  js      loc_18000FFD7
0x18000ff35  mov     rax, [rdi]
0x18000ff38  lea     r8, [rbp+arg_10]
0x18000ff3c  lea     rdx, aLocks; "locks"
0x18000ff43  mov     rcx, rdi
0x18000ff46  mov     rax, [rax+20h]
0x18000ff4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff4f  mov     ebx, eax
0x18000ff51  test    eax, eax
0x18000ff53  js      short loc_18000FFC2
0x18000ff55  mov     rcx, [rbp+arg_10]
0x18000ff59  lea     r8, [rsi+2Ch]
0x18000ff5d  xor     r9d, r9d
0x18000ff60  mov     [rsp+38h+var_18], r15
0x18000ff65  lea     rdx, aEnabled; "enabled"
0x18000ff6c  mov     rax, [rcx]
0x18000ff6f  mov     rax, [rax+48h]
0x18000ff73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff78  mov     ebx, eax
0x18000ff7a  test    eax, eax
0x18000ff7c  js      short loc_18000FFA9
0x18000ff7e  cmp     [rsi+2Ch], r15d
0x18000ff82  jz      short loc_18000FFA9
0x18000ff84  mov     rcx, [rbp+arg_10]
0x18000ff88  lea     r8, [rsi+30h]
0x18000ff8c  xor     r9d, r9d
0x18000ff8f  mov     [rsp+38h+var_18], r15
0x18000ff94  lea     rdx, aRequirelockfor; "requireLockForWriting"
0x18000ff9b  mov     rax, [rcx]
0x18000ff9e  mov     rax, [rax+48h]
0x18000ffa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffa7  mov     ebx, eax
0x18000ffa9  mov     rcx, [rbp+arg_10]
0x18000ffad  mov     rax, [rcx]
0x18000ffb0  mov     rax, [rax+10h]
0x18000ffb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffb9  mov     rcx, r15
0x18000ffbc  mov     [rbp+arg_10], rcx
0x18000ffc0  jmp     short loc_18000FFC6
0x18000ffc2  mov     rcx, [rbp+arg_10]
0x18000ffc6  test    rcx, rcx
0x18000ffc9  jz      short loc_18000FFD7
0x18000ffcb  mov     rax, [rcx]
0x18000ffce  mov     rax, [rax+10h]
0x18000ffd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffd7  mov     eax, ebx
0x18000ffd9  add     rsp, 38h
0x18000ffdd  pop     r15
0x18000ffdf  pop     r14
0x18000ffe1  pop     rdi
0x18000ffe2  pop     rsi
0x18000ffe3  pop     rbx
0x18000ffe4  pop     rbp
0x18000ffe5  retn
```
