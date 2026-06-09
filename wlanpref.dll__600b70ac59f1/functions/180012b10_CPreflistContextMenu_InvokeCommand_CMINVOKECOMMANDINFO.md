# CPreflistContextMenu::InvokeCommand(_CMINVOKECOMMANDINFO *)

- ea: `0x180012b10`
- end: `0x180012d46`
- name: `?InvokeCommand@CPreflistContextMenu@@UEAAJPEAU_CMINVOKECOMMANDINFO@@@Z`
- size: `566`
- prototype: `__int64 __fastcall(CPreflistContextMenu *__hidden this, struct _CMINVOKECOMMANDINFO *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x1800036ac`
- `0x18000dd14`
- `0x180012534`
- `0x180012b10`
- `0x180012d4c`
- `0x1800132ec`
- `0x18002d81a`
- `0x180030010`

## import_xrefs

- `ntdll!WinSqmIncrementDWORD` at `0x180012c69`
- `ntdll!WinSqmIncrementDWORD` at `0x180012c69`

## string_xrefs

- `0x180012bb9`: `delete`
- `0x180012bd1`: `moveup`
- `0x180012bec`: `movedown`
- `0x180012b79`: `security`
- `0x180012b8c`: `securityproperties`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPreflistContextMenu::InvokeCommand(HWND *this, struct _CMINVOKECOMMANDINFO *a2)
{
  int lpVerb_low; // edi
  wchar_t *v4; // rbx
  enum _WL_DISPLAY_PAGES v6; // r8d
  unsigned int v7; // ebx
  char *v8; // rsi
  int v9; // ebx
  int v10; // eax
  __int64 v11; // r8
  wchar_t *String1; // [rsp+58h] [rbp+10h] BYREF

  if ( WORD1(a2->lpVerb) )
  {
    WTL::CString::CString((WTL::CString *)&String1, a2->lpVerb);
    WTL::CString::MakeLower((WTL::CString *)&String1);
    v4 = String1;
    if ( !wcscmp_0(String1, L"open") || !wcscmp_0(v4, L"properties") )
    {
      lpVerb_low = 0;
    }
    else if ( !wcscmp_0(v4, L"security") || !wcscmp_0(v4, L"securityproperties") )
    {
      lpVerb_low = 4096;
    }
    else if ( !wcscmp_0(v4, L"advancedproperties") )
    {
      lpVerb_low = 4097;
    }
    else if ( !wcscmp_0(v4, L"delete") )
    {
      lpVerb_low = 1;
    }
    else if ( !wcscmp_0(v4, L"moveup") )
    {
      lpVerb_low = 3;
    }
    else
    {
      lpVerb_low = -1;
      if ( !wcscmp_0(v4, L"movedown") )
        lpVerb_low = 4;
    }
    WTL::CString::~CString((WTL::CString *)&String1);
  }
  else
  {
    lpVerb_low = LOWORD(a2->lpVerb);
  }
  if ( (unsigned int)(lpVerb_low - 3) <= 1 )
  {
    v8 = (char *)(this + 13);
    if ( v8[81] )
      return 2147942487LL;
    v9 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)CSingletonPtr<CWlanProfileStore>::s_pInstance + 64LL))(
           CSingletonPtr<CWlanProfileStore>::s_pInstance,
           v8);
    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)CSingletonPtr<CWlanProfileStore>::s_pInstance + 48LL))(CSingletonPtr<CWlanProfileStore>::s_pInstance);
    if ( v9 == -1 )
      return 2147942487LL;
    if ( lpVerb_low == 3 )
    {
      if ( !v9 )
        return 2147942487LL;
      v11 = (unsigned int)(v9 - 1);
    }
    else
    {
      if ( lpVerb_low != 4 )
      {
LABEL_40:
        v7 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)CSingletonPtr<CWlanProfileStore>::s_pInstance + 184LL))(CSingletonPtr<CWlanProfileStore>::s_pInstance);
        return v7;
      }
      if ( v9 == v10 - 1 )
        return 2147942487LL;
      v11 = (unsigned int)(v9 + 1);
    }
    (*(void (__fastcall **)(__int64, char *, __int64))(*(_QWORD *)CSingletonPtr<CWlanProfileStore>::s_pInstance + 160LL))(
      CSingletonPtr<CWlanProfileStore>::s_pInstance,
      v8,
      v11);
    goto LABEL_40;
  }
  if ( lpVerb_low != 1 )
  {
    v6 = WLAdvPage;
    if ( lpVerb_low == 2 )
      return 0;
    if ( lpVerb_low )
    {
      if ( lpVerb_low == 4096 )
      {
        v6 = WLSecurityPage;
      }
      else if ( lpVerb_low != 4097 )
      {
        return 2147942487LL;
      }
    }
    else
    {
      WinSqmIncrementDWORD(0, 6145, 1);
      v6 = WLConnectionPage;
    }
    return (unsigned int)ShowWlanProfileDialog(this[24], (const struct CProfile *)(this + 13), v6);
  }
  if ( !*((_BYTE *)this + 185) )
    return (unsigned int)DeleteProfileWithUI(this[24], this + 12, this + 13);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180012b10  push    rbx
0x180012b12  push    rbp
0x180012b13  push    rsi
0x180012b14  push    rdi
0x180012b15  sub     rsp, 28h
0x180012b19  mov     rsi, rcx
0x180012b1c  xor     ebp, ebp
0x180012b1e  cmp     [rdx+12h], bp
0x180012b22  jnz     short loc_180012B2D
0x180012b24  movzx   edi, word ptr [rdx+10h]
0x180012b28  jmp     loc_180012C17
0x180012b2d  mov     rdx, [rdx+10h]; lpMultiByteStr
0x180012b31  lea     rcx, [rsp+48h+String1]; this
0x180012b36  call    ??0CString@WTL@@QEAA@PEBD@Z; WTL::CString::CString(char const *)
0x180012b3b  nop
0x180012b3c  lea     rcx, [rsp+48h+String1]; this
0x180012b41  call    ?MakeLower@CString@WTL@@QEAAXXZ; WTL::CString::MakeLower(void)
0x180012b46  lea     rdx, aOpen; "open"
0x180012b4d  mov     rbx, [rsp+48h+String1]
0x180012b52  mov     rcx, rbx; String1
0x180012b55  call    wcscmp_0
0x180012b5a  test    eax, eax
0x180012b5c  jz      loc_180012C0B
0x180012b62  lea     rdx, aProperties; "properties"
0x180012b69  mov     rcx, rbx; String1
0x180012b6c  call    wcscmp_0
0x180012b71  test    eax, eax
0x180012b73  jz      loc_180012C0B
0x180012b79  lea     rdx, aSecurity_1; "security"
0x180012b80  mov     rcx, rbx; String1
0x180012b83  call    wcscmp_0
0x180012b88  test    eax, eax
0x180012b8a  jz      short loc_180012C04
0x180012b8c  lea     rdx, aSecurityproper; "securityproperties"
0x180012b93  mov     rcx, rbx; String1
0x180012b96  call    wcscmp_0
0x180012b9b  test    eax, eax
0x180012b9d  jz      short loc_180012C04
0x180012b9f  lea     rdx, aAdvancedproper; "advancedproperties"
0x180012ba6  mov     rcx, rbx; String1
0x180012ba9  call    wcscmp_0
0x180012bae  test    eax, eax
0x180012bb0  jnz     short loc_180012BB9
0x180012bb2  mov     edi, 1001h
0x180012bb7  jmp     short loc_180012C0D
0x180012bb9  lea     rdx, aDelete; "delete"
0x180012bc0  mov     rcx, rbx; String1
0x180012bc3  call    wcscmp_0
0x180012bc8  test    eax, eax
0x180012bca  jnz     short loc_180012BD1
0x180012bcc  lea     edi, [rax+1]
0x180012bcf  jmp     short loc_180012C0D
0x180012bd1  lea     rdx, aMoveup_0; "moveup"
0x180012bd8  mov     rcx, rbx; String1
0x180012bdb  call    wcscmp_0
0x180012be0  test    eax, eax
0x180012be2  jnz     short loc_180012BE9
0x180012be4  lea     edi, [rax+3]
0x180012be7  jmp     short loc_180012C0D
0x180012be9  or      edi, 0FFFFFFFFh
0x180012bec  lea     rdx, aMovedown_0; "movedown"
0x180012bf3  mov     rcx, rbx; String1
0x180012bf6  call    wcscmp_0
0x180012bfb  test    eax, eax
0x180012bfd  jnz     short loc_180012C0D
0x180012bff  lea     edi, [rax+4]
0x180012c02  jmp     short loc_180012C0D
0x180012c04  mov     edi, 1000h
0x180012c09  jmp     short loc_180012C0D
0x180012c0b  mov     edi, ebp
0x180012c0d  lea     rcx, [rsp+48h+String1]; this
0x180012c12  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x180012c17  lea     eax, [rdi-3]
0x180012c1a  cmp     eax, 1
0x180012c1d  jbe     loc_180012CA7
0x180012c23  cmp     edi, 1
0x180012c26  jnz     short loc_180012C48
0x180012c28  lea     r8, [rsi+68h]
0x180012c2c  cmp     [r8+51h], bpl
0x180012c30  jnz     loc_180012D38
0x180012c36  lea     rdx, [rsi+60h]
0x180012c3a  mov     rcx, [rsi+0C0h]
0x180012c41  call    ?DeleteProfileWithUI@@YAJPEAUHWND__@@AEAV?$CSingletonPtr@VCWlanProfileStore@@@@AEAVCProfile@@@Z; DeleteProfileWithUI(HWND__ *,CSingletonPtr<CWlanProfileStore> &,CProfile &)
0x180012c46  jmp     short loc_180012CA0
0x180012c48  mov     r8d, 2; enum _WL_DISPLAY_PAGES
0x180012c4e  cmp     edi, r8d
0x180012c51  jnz     short loc_180012C5A
0x180012c53  mov     ebx, ebp
0x180012c55  jmp     loc_180012D34
0x180012c5a  test    edi, edi
0x180012c5c  jnz     short loc_180012C74
0x180012c5e  mov     edx, 1801h
0x180012c63  xor     ecx, ecx
0x180012c65  lea     r8d, [rdi+1]
0x180012c69  call    cs:__imp_WinSqmIncrementDWORD
0x180012c6f  xor     r8d, r8d
0x180012c72  jmp     short loc_180012C90
0x180012c74  cmp     edi, 1000h
0x180012c7a  jnz     short loc_180012C84
0x180012c7c  mov     r8d, 1
0x180012c82  jmp     short loc_180012C90
0x180012c84  cmp     edi, 1001h
0x180012c8a  jnz     loc_180012D38
0x180012c90  lea     rdx, [rsi+68h]; struct CProfile *
0x180012c94  mov     rcx, [rsi+0C0h]; hWnd
0x180012c9b  call    ?ShowWlanProfileDialog@@YAJPEAUHWND__@@AEBVCProfile@@W4_WL_DISPLAY_PAGES@@@Z; ShowWlanProfileDialog(HWND__ *,CProfile const &,_WL_DISPLAY_PAGES)
0x180012ca0  mov     ebx, eax
0x180012ca2  jmp     loc_180012D34
0x180012ca7  add     rsi, 68h ; 'h'
0x180012cab  cmp     [rsi+51h], bpl
0x180012caf  jnz     loc_180012D38
0x180012cb5  mov     rcx, cs:?s_pInstance@?$CSingletonPtr@VCWlanProfileStore@@@@0PEAVCWlanProfileStore@@EA; CWlanProfileStore * CSingletonPtr<CWlanProfileStore>::s_pInstance
0x180012cbc  mov     rax, [rcx]
0x180012cbf  mov     rdx, rsi
0x180012cc2  mov     rax, [rax+40h]
0x180012cc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ccb  mov     ebx, eax
0x180012ccd  mov     rcx, cs:?s_pInstance@?$CSingletonPtr@VCWlanProfileStore@@@@0PEAVCWlanProfileStore@@EA; CWlanProfileStore * CSingletonPtr<CWlanProfileStore>::s_pInstance
0x180012cd4  mov     rdx, [rcx]
0x180012cd7  mov     rax, [rdx+30h]
0x180012cdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ce0  cmp     ebx, 0FFFFFFFFh
0x180012ce3  jz      short loc_180012D38
0x180012ce5  cmp     edi, 3
0x180012ce8  jnz     short loc_180012CF4
0x180012cea  test    ebx, ebx
0x180012cec  jz      short loc_180012D38
0x180012cee  lea     r8d, [rbx-1]
0x180012cf2  jmp     short loc_180012D03
0x180012cf4  cmp     edi, 4
0x180012cf7  jnz     short loc_180012D1C
0x180012cf9  dec     eax
0x180012cfb  cmp     ebx, eax
0x180012cfd  jz      short loc_180012D38
0x180012cff  lea     r8d, [rbx+1]
0x180012d03  mov     rcx, cs:?s_pInstance@?$CSingletonPtr@VCWlanProfileStore@@@@0PEAVCWlanProfileStore@@EA; CWlanProfileStore * CSingletonPtr<CWlanProfileStore>::s_pInstance
0x180012d0a  mov     rax, [rcx]
0x180012d0d  mov     rdx, rsi
0x180012d10  mov     rax, [rax+0A0h]
0x180012d17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d1c  mov     ebx, ebp
0x180012d1e  mov     rcx, cs:?s_pInstance@?$CSingletonPtr@VCWlanProfileStore@@@@0PEAVCWlanProfileStore@@EA; CWlanProfileStore * CSingletonPtr<CWlanProfileStore>::s_pInstance
0x180012d25  mov     rax, [rcx]
0x180012d28  mov     rax, [rax+0B8h]
0x180012d2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d34  mov     eax, ebx
0x180012d36  jmp     short loc_180012D3D
0x180012d38  mov     eax, 80070057h
0x180012d3d  add     rsp, 28h
0x180012d41  pop     rdi
0x180012d42  pop     rsi
0x180012d43  pop     rbp
0x180012d44  pop     rbx
0x180012d45  retn
```
