# AssocMakeProgid

- ea: `0x18001fd40`
- end: `0x18001ff75`
- name: `AssocMakeProgid`
- size: `565`
- prototype: `__int64 __fastcall(unsigned int, LPCWSTR pszPath)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180012550`
- `0x18001f554`
- `0x18001fd40`
- `0x18001ff80`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ff48`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ff52`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ff48`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ff52`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001fdfa`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001fdfa`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18001fdb4`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18001fdb4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18001fe4a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18001fe82`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18001feeb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18001ff1f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18001fe4a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18001fe82`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18001feeb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18001ff1f`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x18001fe73`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x18001feb0`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x18001ff13`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x18001fe73`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x18001feb0`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x18001ff13`

## pseudocode

```c
__int64 __fastcall AssocMakeProgid(unsigned int a1, LPCWSTR pszPath, __int64 a3, HKEY *a4)
{
  int Shell; // esi
  _WORD *v9; // rax
  LSTATUS v10; // eax
  bool v11; // sf
  const unsigned __int16 *v12; // rdx
  const WCHAR *v13; // rcx
  int v14; // eax
  const WCHAR *v15; // rcx
  int v16; // eax
  __int64 *v17; // r9
  const WCHAR *v18; // rdi
  LSTATUS v19; // r14d
  int v20; // eax
  HKEY hkey; // [rsp+50h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-18h] BYREF

  Shell = -2147024809;
  if ( pszPath )
  {
    if ( a3 )
    {
      if ( *(_DWORD *)a3 >= 0x30u )
      {
        v9 = *(_WORD **)(a3 + 8);
        if ( v9 )
        {
          if ( *v9 )
          {
            hKey = 0;
            if ( (a1 & 0x40) == 0 || PathFileExistsW(pszPath) )
            {
              hKey = 0;
              v10 = RegCreateKeyExW(HKEY_CURRENT_USER, L"Software\\classes", 0, 0, 0, 0x2001Fu, 0, &hKey, 0);
              v11 = v10 < 0;
              if ( v10 > 0 )
                v11 = 1;
              if ( !v11 )
              {
                v12 = *(const unsigned __int16 **)(a3 + 8);
                hkey = 0;
                Shell = _AssocOpenRegKey(hKey, v12, 0x20006u, &hkey, 1);
                if ( Shell >= 0 )
                {
                  v13 = *(const WCHAR **)(a3 + 16);
                  if ( v13 )
                  {
                    v14 = lstrlenW(v13);
                    SHSetValueW(hkey, 0, 0, 1u, *(LPCVOID *)(a3 + 16), 2 * v14 + 2);
                  }
                  v15 = *(const WCHAR **)(a3 + 24);
                  if ( v15 )
                  {
                    v16 = lstrlenW(v15);
                    SHSetValueW(hkey, L"DefaultIcon", 0, 1u, *(LPCVOID *)(a3 + 24), 2 * v16 + 2);
                  }
                  v17 = *(__int64 **)(a3 + 32);
                  if ( v17 )
                  {
                    Shell = AssocMakeShell(a1, hkey, pszPath, v17);
                    if ( Shell < 0 )
                      goto LABEL_25;
                  }
                  v18 = *(const WCHAR **)(a3 + 40);
                  if ( v18 )
                  {
                    v19 = 0;
                    while ( *v18 && !v19 )
                    {
                      v20 = lstrlenW(*(LPCWSTR *)(a3 + 8));
                      v19 = SHSetValueW(hKey, v18, 0, 1u, *(LPCVOID *)(a3 + 8), 2 * v20 + 2);
                      v18 += lstrlenW(v18) + 1;
                    }
                  }
                  if ( !a4 )
LABEL_25:
                    RegCloseKey(hkey);
                  else
                    *a4 = hkey;
                }
                RegCloseKey(hKey);
              }
            }
          }
        }
      }
    }
  }
  return (unsigned int)Shell;
}

```

## disassembly

```asm
0x18001fd40  push    rbp
0x18001fd42  push    rbx
0x18001fd43  push    rsi
0x18001fd44  push    rdi
0x18001fd45  push    r12
0x18001fd47  push    r14
0x18001fd49  push    r15
0x18001fd4b  mov     rbp, rsp
0x18001fd4e  sub     rsp, 70h
0x18001fd52  mov     rax, cs:__security_cookie
0x18001fd59  xor     rax, rsp
0x18001fd5c  mov     [rbp+var_10], rax
0x18001fd60  xor     r12d, r12d
0x18001fd63  mov     r15, r9
0x18001fd66  mov     rbx, r8
0x18001fd69  mov     rdi, rdx
0x18001fd6c  mov     r14d, ecx
0x18001fd6f  mov     esi, 80070057h
0x18001fd74  test    rdx, rdx
0x18001fd77  jz      loc_18001FF58
0x18001fd7d  test    rbx, rbx
0x18001fd80  jz      loc_18001FF58
0x18001fd86  cmp     dword ptr [r8], 30h ; '0'
0x18001fd8a  jb      loc_18001FF58
0x18001fd90  mov     rax, [r8+8]
0x18001fd94  test    rax, rax
0x18001fd97  jz      loc_18001FF58
0x18001fd9d  cmp     [rax], r12w
0x18001fda1  jz      loc_18001FF58
0x18001fda7  mov     [rbp+hKey], r12
0x18001fdab  test    r14b, 40h
0x18001fdaf  jz      short loc_18001FDC2
0x18001fdb1  mov     rcx, rdx; pszPath
0x18001fdb4  call    cs:__imp_PathFileExistsW
0x18001fdba  test    eax, eax
0x18001fdbc  jz      loc_18001FF58
0x18001fdc2  mov     [rsp+70h+lpdwDisposition], r12; lpdwDisposition
0x18001fdc7  lea     rax, [rbp+hKey]
0x18001fdcb  mov     [rsp+70h+phkResult], rax; phkResult
0x18001fdd0  lea     rdx, aSoftwareClasse; "Software\\classes"
0x18001fdd7  mov     [rsp+70h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18001fddc  xor     r9d, r9d; lpClass
0x18001fddf  mov     [rsp+70h+samDesired], 2001Fh; samDesired
0x18001fde7  xor     r8d, r8d; Reserved
0x18001fdea  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18001fdf1  mov     [rsp+70h+dwOptions], r12d; dwOptions
0x18001fdf6  mov     [rbp+hKey], r12
0x18001fdfa  call    cs:__imp_RegCreateKeyExW
0x18001fe00  test    eax, eax
0x18001fe02  jle     short loc_18001FE0E
0x18001fe04  movzx   eax, ax
0x18001fe07  or      eax, 80070000h
0x18001fe0c  test    eax, eax
0x18001fe0e  js      loc_18001FF58
0x18001fe14  mov     rdx, [rbx+8]; unsigned __int16 *
0x18001fe18  lea     r9, [rbp+hkey]; HKEY *
0x18001fe1c  mov     rcx, [rbp+hKey]; HKEY
0x18001fe20  mov     r8d, 20006h; unsigned int
0x18001fe26  mov     [rbp+hkey], r12
0x18001fe2a  mov     [rsp+70h+dwOptions], 1; int
0x18001fe32  call    ?_AssocOpenRegKey@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@H@Z; _AssocOpenRegKey(HKEY__ *,ushort const *,ulong,HKEY__ * *,int)
0x18001fe37  mov     esi, eax
0x18001fe39  test    eax, eax
0x18001fe3b  js      loc_18001FF4E
0x18001fe41  mov     rcx, [rbx+10h]; lpString
0x18001fe45  test    rcx, rcx
0x18001fe48  jz      short loc_18001FE79
0x18001fe4a  call    cs:__imp_lstrlenW
0x18001fe50  mov     rcx, [rbx+10h]
0x18001fe54  mov     r9d, 1; dwType
0x18001fe5a  xor     r8d, r8d; pszValue
0x18001fe5d  xor     edx, edx; pszSubKey
0x18001fe5f  lea     eax, ds:2[rax*2]
0x18001fe66  mov     [rsp+70h+samDesired], eax; cbData
0x18001fe6a  mov     qword ptr [rsp+70h+dwOptions], rcx; pvData
0x18001fe6f  mov     rcx, [rbp+hkey]; hkey
0x18001fe73  call    cs:__imp_SHSetValueW
0x18001fe79  mov     rcx, [rbx+18h]; lpString
0x18001fe7d  test    rcx, rcx
0x18001fe80  jz      short loc_18001FEB6
0x18001fe82  call    cs:__imp_lstrlenW
0x18001fe88  mov     rcx, [rbp+hkey]; hkey
0x18001fe8c  lea     rdx, aDefaulticon; "DefaultIcon"
0x18001fe93  mov     r9d, 1; dwType
0x18001fe99  xor     r8d, r8d; pszValue
0x18001fe9c  lea     eax, ds:2[rax*2]
0x18001fea3  mov     [rsp+70h+samDesired], eax; cbData
0x18001fea7  mov     rax, [rbx+18h]
0x18001feab  mov     qword ptr [rsp+70h+dwOptions], rax; pvData
0x18001feb0  call    cs:__imp_SHSetValueW
0x18001feb6  mov     r9, [rbx+20h]
0x18001feba  test    r9, r9
0x18001febd  jz      short loc_18001FED4
0x18001febf  mov     rdx, [rbp+hkey]; HKEY
0x18001fec3  mov     r8, rdi
0x18001fec6  mov     ecx, r14d; unsigned int
0x18001fec9  call    AssocMakeShell
0x18001fece  mov     esi, eax
0x18001fed0  test    eax, eax
0x18001fed2  js      short loc_18001FF44
0x18001fed4  mov     rdi, [rbx+28h]
0x18001fed8  test    rdi, rdi
0x18001fedb  jz      short loc_18001FF36
0x18001fedd  mov     r14d, r12d
0x18001fee0  jmp     short loc_18001FF30
0x18001fee2  test    r14d, r14d
0x18001fee5  jnz     short loc_18001FF36
0x18001fee7  mov     rcx, [rbx+8]; lpString
0x18001feeb  call    cs:__imp_lstrlenW
0x18001fef1  mov     rcx, [rbp+hKey]; hkey
0x18001fef5  lea     r9d, [r14+1]; dwType
0x18001fef9  xor     r8d, r8d; pszValue
0x18001fefc  mov     rdx, rdi; pszSubKey
0x18001feff  lea     eax, ds:2[rax*2]
0x18001ff06  mov     [rsp+70h+samDesired], eax; cbData
0x18001ff0a  mov     rax, [rbx+8]
0x18001ff0e  mov     qword ptr [rsp+70h+dwOptions], rax; pvData
0x18001ff13  call    cs:__imp_SHSetValueW
0x18001ff19  mov     rcx, rdi; lpString
0x18001ff1c  mov     r14d, eax
0x18001ff1f  call    cs:__imp_lstrlenW
0x18001ff25  movsxd  rcx, eax
0x18001ff28  lea     rdi, [rdi+rcx*2]
0x18001ff2c  add     rdi, 2
0x18001ff30  cmp     [rdi], r12w
0x18001ff34  jnz     short loc_18001FEE2
0x18001ff36  test    r15, r15
0x18001ff39  jz      short loc_18001FF44
0x18001ff3b  mov     rax, [rbp+hkey]
0x18001ff3f  mov     [r15], rax
0x18001ff42  jmp     short loc_18001FF4E
0x18001ff44  mov     rcx, [rbp+hkey]; hKey
0x18001ff48  call    cs:__imp_RegCloseKey
0x18001ff4e  mov     rcx, [rbp+hKey]; hKey
0x18001ff52  call    cs:__imp_RegCloseKey
0x18001ff58  mov     eax, esi
0x18001ff5a  mov     rcx, [rbp+var_10]
0x18001ff5e  xor     rcx, rsp; StackCookie
0x18001ff61  call    __security_check_cookie
0x18001ff66  add     rsp, 70h
0x18001ff6a  pop     r15
0x18001ff6c  pop     r14
0x18001ff6e  pop     r12
0x18001ff70  pop     rdi
0x18001ff71  pop     rsi
0x18001ff72  pop     rbx
0x18001ff73  pop     rbp
0x18001ff74  retn
```
