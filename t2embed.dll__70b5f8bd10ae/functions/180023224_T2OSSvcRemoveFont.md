# T2OSSvcRemoveFont

- ea: `0x180023224`
- end: `0x180023378`
- name: `T2OSSvcRemoveFont`
- size: `340`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800190a4`
- `0x18001f620`

## callees

- `0x18001ba0c`
- `0x18001f3e4`
- `0x180022c7c`
- `0x180023224`
- `0x18002a590`
- `0x18002b010`

## import_xrefs

- `KERNEL32!RegOpenKeyExA` at `0x1800232c0`
- `KERNEL32!RegOpenKeyExA` at `0x1800232c0`
- `KERNEL32!RegCloseKey` at `0x1800232df`
- `KERNEL32!RegCloseKey` at `0x1800232df`
- `KERNEL32!RegDeleteValueA` at `0x1800232d4`
- `KERNEL32!RegDeleteValueA` at `0x1800232d4`
- `KERNEL32!GetVersion` at `0x18002328a`
- `KERNEL32!GetVersion` at `0x18002328a`
- `GDI32!RemoveFontResourceA` at `0x18002332d`
- `GDI32!RemoveFontResourceA` at `0x18002332d`
- `USER32!PostMessageA` at `0x180023351`
- `USER32!PostMessageA` at `0x180023351`

## pseudocode

```c
__int64 __fastcall T2OSSvcRemoveFont(__int64 a1, int a2, __int64 a3)
{
  signed int Version; // eax
  const CHAR *v6; // rdx
  bool v8; // cl
  int i; // edi
  bool v10; // zf
  const CHAR *v11; // rcx
  HKEY hKey; // [rsp+30h] [rbp-A8h] BYREF
  char pszDest[96]; // [rsp+40h] [rbp-98h] BYREF

  hKey = 0;
  if ( a2 )
  {
    if ( StringCchCopyA(pszDest, 0x40u, (STRSAFE_LPCSTR)(a3 + 780)) < 0
      || StringCchCatA(pszDest, 0x54u, " (TrueType)") < 0 )
    {
      return 0;
    }
    Version = GetVersion();
    v6 = "SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Fonts";
    if ( Version >= 0 )
      v6 = "SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Fonts";
    if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, v6, 0, 0x2001Fu, &hKey) )
    {
      RegDeleteValueA(hKey, pszDest);
      RegCloseKey(hKey);
    }
  }
  if ( *(_QWORD *)(a3 + 920) )
  {
    if ( fnRemoveFontMemResourceEx )
      fnRemoveFontMemResourceEx();
  }
  else
  {
    v8 = 1;
    for ( i = 0; ; ++i )
    {
      v10 = i >= 5 || !v8;
      v11 = (const CHAR *)a3;
      if ( v10 )
        break;
      if ( !*(_DWORD *)(a3 + 908) )
        v11 = (const CHAR *)(a3 + 260);
      v8 = RemoveFontResourceA(v11);
    }
    T2OSSvcDeleteFontFile((LPCSTR)a3);
  }
  if ( a2 )
    PostMessageA(HWND_BROADCAST, 0x1Du, 0, 0);
  return 1;
}

```

## disassembly

```asm
0x180023224  push    rbx
0x180023226  push    rbp
0x180023227  push    rsi
0x180023228  push    rdi
0x180023229  sub     rsp, 0B8h
0x180023230  mov     rax, cs:__security_cookie
0x180023237  xor     rax, rsp
0x18002323a  mov     [rsp+0D8h+var_38], rax
0x180023242  xor     ebp, ebp
0x180023244  mov     rbx, r8
0x180023247  mov     [rsp+0D8h+hKey], rbp
0x18002324c  mov     esi, edx
0x18002324e  test    edx, edx
0x180023250  jz      loc_1800232E5
0x180023256  add     r8, 30Ch; pszSrc
0x18002325d  lea     edx, [rbp+40h]; cchDest
0x180023260  lea     rcx, [rsp+0D8h+pszDest]; pszDest
0x180023265  call    StringCchCopyA
0x18002326a  test    eax, eax
0x18002326c  js      loc_180023304
0x180023272  lea     r8, pszSrc; " (TrueType)"
0x180023279  lea     edx, [rbp+54h]; cchDest
0x18002327c  lea     rcx, [rsp+0D8h+pszDest]; pszDest
0x180023281  call    StringCchCatA
0x180023286  test    eax, eax
0x180023288  js      short loc_180023304
0x18002328a  call    cs:__imp_GetVersion
0x180023290  shr     eax, 10h
0x180023293  xor     r8d, r8d; ulOptions
0x180023296  test    ax, ax
0x180023299  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800232a0  lea     rax, [rsp+0D8h+hKey]
0x1800232a5  mov     r9d, 2001Fh; samDesired
0x1800232ab  mov     [rsp+0D8h+phkResult], rax; phkResult
0x1800232b0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800232b7  js      short loc_1800232C0
0x1800232b9  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800232c0  call    cs:__imp_RegOpenKeyExA
0x1800232c6  test    eax, eax
0x1800232c8  jnz     short loc_1800232E5
0x1800232ca  mov     rcx, [rsp+0D8h+hKey]; hKey
0x1800232cf  lea     rdx, [rsp+0D8h+pszDest]; lpValueName
0x1800232d4  call    cs:__imp_RegDeleteValueA
0x1800232da  mov     rcx, [rsp+0D8h+hKey]; hKey
0x1800232df  call    cs:__imp_RegCloseKey
0x1800232e5  mov     rcx, [rbx+398h]
0x1800232ec  test    rcx, rcx
0x1800232ef  jz      short loc_180023308
0x1800232f1  mov     rax, cs:fnRemoveFontMemResourceEx
0x1800232f8  test    rax, rax
0x1800232fb  jz      short loc_18002333E
0x1800232fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023302  jmp     short loc_18002333E
0x180023304  xor     eax, eax
0x180023306  jmp     short loc_18002335C
0x180023308  mov     ecx, 1
0x18002330d  mov     edi, ebp
0x18002330f  cmp     edi, 5
0x180023312  mov     eax, ebp
0x180023314  setl    al
0x180023317  test    ecx, eax
0x180023319  mov     rcx, rbx; lpFileName
0x18002331c  jz      short loc_180023339
0x18002331e  cmp     [rbx+38Ch], ebp
0x180023324  jnz     short loc_18002332D
0x180023326  lea     rcx, [rbx+104h]; lpFileName
0x18002332d  call    cs:__imp_RemoveFontResourceA
0x180023333  mov     ecx, eax
0x180023335  inc     edi
0x180023337  jmp     short loc_18002330F
0x180023339  call    T2OSSvcDeleteFontFile
0x18002333e  test    esi, esi
0x180023340  jz      short loc_180023357
0x180023342  xor     r9d, r9d; lParam
0x180023345  xor     r8d, r8d; wParam
0x180023348  mov     ecx, 0FFFFh; hWnd
0x18002334d  lea     edx, [r9+1Dh]; Msg
0x180023351  call    cs:__imp_PostMessageA
0x180023357  mov     eax, 1
0x18002335c  mov     rcx, [rsp+0D8h+var_38]
0x180023364  xor     rcx, rsp; StackCookie
0x180023367  call    __security_check_cookie
0x18002336c  add     rsp, 0B8h
0x180023373  pop     rdi
0x180023374  pop     rsi
0x180023375  pop     rbp
0x180023376  pop     rbx
0x180023377  retn
```
