# WamRegRegistryConfig::UnRegisterProgID(ushort const *)

- ea: `0x1800053d8`
- end: `0x18000553e`
- name: `?UnRegisterProgID@WamRegRegistryConfig@@AEAAJPEBG@Z`
- size: `358`
- prototype: `int(WamRegRegistryConfig *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x180005138`

## callees

- `0x180001044`
- `0x180001084`
- `0x1800053d8`
- `0x180006850`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800054e3`
- `ADVAPI32!RegCloseKey` at `0x18000551a`
- `ADVAPI32!RegCloseKey` at `0x1800054e3`
- `ADVAPI32!RegCloseKey` at `0x18000551a`
- `ADVAPI32!RegDeleteKeyA` at `0x18000549e`
- `ADVAPI32!RegDeleteKeyA` at `0x1800054fc`
- `ADVAPI32!RegDeleteKeyA` at `0x18000549e`
- `ADVAPI32!RegDeleteKeyA` at `0x1800054fc`
- `ADVAPI32!RegOpenKeyExA` at `0x180005482`
- `ADVAPI32!RegOpenKeyExA` at `0x180005482`
- `ADVAPI32!RegEnumKeyExA` at `0x1800054d4`
- `ADVAPI32!RegEnumKeyExA` at `0x1800054d4`
- `KERNEL32!WideCharToMultiByte` at `0x18000545f`
- `KERNEL32!WideCharToMultiByte` at `0x18000545f`

## pseudocode

```c
__int64 __fastcall WamRegRegistryConfig::UnRegisterProgID(WamRegRegistryConfig *this, const unsigned __int16 *a2)
{
  __int64 v3; // rax
  unsigned int cbMultiByte; // r14d
  CHAR *lpMultiByteStr; // rax
  CHAR *v6; // rdi
  unsigned int v7; // ebx
  DWORD v8; // esi
  DWORD i; // edx
  LSTATUS v10; // eax
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  CHAR SubKey[256]; // [rsp+50h] [rbp-B0h] BYREF

  phkResult = 0;
  v3 = -1;
  cchName = 0;
  do
    ++v3;
  while ( a2[v3] );
  cbMultiByte = 2 * v3 + 1;
  lpMultiByteStr = (CHAR *)operator new(cbMultiByte);
  v6 = lpMultiByteStr;
  if ( lpMultiByteStr )
  {
    v7 = -2147467259;
    WideCharToMultiByte(0, 0, a2, -1, lpMultiByteStr, cbMultiByte, 0, 0);
    if ( !RegOpenKeyExA(HKEY_CLASSES_ROOT, v6, 0, 0x2001Fu, &phkResult) )
    {
      v8 = 0;
      for ( i = 0; ; i = v8 )
      {
        cchName = 255;
        if ( RegEnumKeyExA(phkResult, i, SubKey, &cchName, 0, 0, 0, 0) )
          break;
        if ( RegDeleteKeyA(phkResult, SubKey) )
          goto LABEL_12;
        ++v8;
      }
      v10 = RegCloseKey(phkResult);
      phkResult = 0;
      if ( !v10 )
        v7 = RegDeleteKeyA(HKEY_CLASSES_ROOT, v6) != 0 ? 0x80004005 : 0;
    }
LABEL_12:
    operator delete(v6);
  }
  else
  {
    v7 = -2147024882;
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  return v7;
}

```

## disassembly

```asm
0x1800053d8  push    rbp
0x1800053da  push    rbx
0x1800053db  push    rsi
0x1800053dc  push    rdi
0x1800053dd  push    r14
0x1800053df  push    r15
0x1800053e1  lea     rbp, [rsp-68h]
0x1800053e6  sub     rsp, 168h
0x1800053ed  mov     rax, cs:__security_cookie
0x1800053f4  xor     rax, rsp
0x1800053f7  mov     [rbp+90h+var_40], rax
0x1800053fb  xor     r15d, r15d
0x1800053fe  mov     rsi, rdx
0x180005401  mov     [rsp+190h+phkResult], r15
0x180005406  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000540a  mov     [rsp+190h+cchName], r15d
0x18000540f  inc     rax
0x180005412  cmp     [rdx+rax*2], r15w
0x180005417  jnz     short loc_18000540F
0x180005419  lea     r14d, ds:1[rax*2]
0x180005421  mov     ecx, r14d; Size
0x180005424  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005429  mov     rdi, rax
0x18000542c  test    rax, rax
0x18000542f  jnz     short loc_18000543B
0x180005431  mov     ebx, 8007000Eh
0x180005436  jmp     loc_180005510
0x18000543b  mov     [rsp+190h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x180005440  or      r9d, 0FFFFFFFFh; cchWideChar
0x180005444  mov     [rsp+190h+lpDefaultChar], r15; lpDefaultChar
0x180005449  mov     r8, rsi; lpWideCharStr
0x18000544c  mov     [rsp+190h+cbMultiByte], r14d; cbMultiByte
0x180005451  xor     edx, edx; dwFlags
0x180005453  xor     ecx, ecx; CodePage
0x180005455  mov     [rsp+190h+lpMultiByteStr], rdi; lpMultiByteStr
0x18000545a  mov     ebx, 80004005h
0x18000545f  call    cs:__imp_WideCharToMultiByte
0x180005465  lea     rax, [rsp+190h+phkResult]
0x18000546a  mov     r9d, 2001Fh; samDesired
0x180005470  xor     r8d, r8d; ulOptions
0x180005473  mov     [rsp+190h+lpMultiByteStr], rax; phkResult
0x180005478  mov     rdx, rdi; lpSubKey
0x18000547b  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180005482  call    cs:__imp_RegOpenKeyExA
0x180005488  test    eax, eax
0x18000548a  jnz     short loc_180005508
0x18000548c  mov     esi, r15d
0x18000548f  mov     r14d, 0FFh
0x180005495  xor     edx, edx
0x180005497  jmp     short loc_1800054AC
0x180005499  lea     rdx, [rsp+190h+SubKey]; lpSubKey
0x18000549e  call    cs:__imp_RegDeleteKeyA
0x1800054a4  test    eax, eax
0x1800054a6  jnz     short loc_180005508
0x1800054a8  inc     esi
0x1800054aa  mov     edx, esi; dwIndex
0x1800054ac  mov     rcx, [rsp+190h+phkResult]; hKey
0x1800054b1  lea     r9, [rsp+190h+cchName]; lpcchName
0x1800054b6  mov     [rsp+190h+lpUsedDefaultChar], r15; lpftLastWriteTime
0x1800054bb  lea     r8, [rsp+190h+SubKey]; lpName
0x1800054c0  mov     [rsp+190h+lpDefaultChar], r15; lpcchClass
0x1800054c5  mov     qword ptr [rsp+190h+cbMultiByte], r15; lpClass
0x1800054ca  mov     [rsp+190h+lpMultiByteStr], r15; lpReserved
0x1800054cf  mov     [rsp+190h+cchName], r14d
0x1800054d4  call    cs:__imp_RegEnumKeyExA
0x1800054da  mov     rcx, [rsp+190h+phkResult]; hKey
0x1800054df  test    eax, eax
0x1800054e1  jz      short loc_180005499
0x1800054e3  call    cs:__imp_RegCloseKey
0x1800054e9  mov     [rsp+190h+phkResult], r15
0x1800054ee  test    eax, eax
0x1800054f0  jnz     short loc_180005508
0x1800054f2  mov     rdx, rdi; lpSubKey
0x1800054f5  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800054fc  call    cs:__imp_RegDeleteKeyA
0x180005502  neg     eax
0x180005504  sbb     ecx, ecx
0x180005506  and     ebx, ecx
0x180005508  mov     rcx, rdi; Block
0x18000550b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005510  mov     rcx, [rsp+190h+phkResult]; hKey
0x180005515  test    rcx, rcx
0x180005518  jz      short loc_180005520
0x18000551a  call    cs:__imp_RegCloseKey
0x180005520  mov     eax, ebx
0x180005522  mov     rcx, [rbp+90h+var_40]
0x180005526  xor     rcx, rsp; StackCookie
0x180005529  call    __security_check_cookie
0x18000552e  add     rsp, 168h
0x180005535  pop     r15
0x180005537  pop     r14
0x180005539  pop     rdi
0x18000553a  pop     rsi
0x18000553b  pop     rbx
0x18000553c  pop     rbp
0x18000553d  retn
```
