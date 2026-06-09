# GetExtraTzInformation(uint,EXTRATZINFO *,int)

- ea: `0x18000f3b4`
- end: `0x18000f5ef`
- name: `?GetExtraTzInformation@@YAHIPEAUEXTRATZINFO@@H@Z`
- size: `571`
- prototype: `__int64 __fastcall(unsigned int, struct EXTRATZINFO *, int)`
- caller_count: `6`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18000f138`
- `0x18000f1c8`
- `0x18000f32c`
- `0x18000feec`
- `0x18001314c`
- `0x1800131b0`

## callees

- `0x1800089c8`
- `0x180008a0c`
- `0x18000f3b4`
- `0x18000f5f8`
- `0x180028f2e`
- `0x180028f60`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f444`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f444`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000f48d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000f4e9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000f587`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000f48d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000f4e9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000f587`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f5ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f5ae`

## pseudocode

```c
__int64 __fastcall GetExtraTzInformation(unsigned int a1, struct EXTRATZINFO *a2, int a3)
{
  unsigned int v5; // ebx
  __int64 v6; // rdi
  HKEY v7; // rcx
  LSTATUS ValueW; // eax
  __int64 v9; // rcx
  _WORD *v10; // rdx
  struct EXTRATZINFO *v11; // rax
  struct EXTRATZINFO *v12; // rcx
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  int pvData; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  _OWORD v17[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v18[128]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SubKey[256]; // [rsp+170h] [rbp+70h] BYREF

  v5 = 0;
  if ( a1 - 1 <= 1 )
  {
    if ( a2 )
    {
      if ( StringCchPrintfW(SubKey, 0x100u, L"Control Panel\\TimeDate\\AdditionalClocks\\%u", a1) >= 0 )
      {
        hkey = 0;
        if ( !RegOpenKeyExW(HKEY_CURRENT_USER, SubKey, 0, 0x20019u, &hkey) )
        {
          v6 = 16;
          pvData = 0;
          pcbData = 4;
          if ( !RegGetValueW(hkey, 0, L"Enable", 0x10u, 0, &pvData, &pcbData) )
          {
            v7 = hkey;
            pcbData = 32;
            *((_DWORD *)a2 + 8) = pvData != 0;
            memset(v17, 0, sizeof(v17));
            ValueW = RegGetValueW(v7, 0, L"DisplayName", 2u, 0, v17, &pcbData);
            if ( !ValueW || ValueW == 234 )
            {
              v9 = 15;
              v10 = v17;
              v11 = a2;
              do
              {
                if ( !v9 )
                  break;
                if ( !*v10 )
                  break;
                *(_WORD *)v11 = *v10++;
                v11 = (struct EXTRATZINFO *)((char *)v11 + 2);
                --v9;
                --v6;
              }
              while ( v6 );
              v12 = (struct EXTRATZINFO *)((char *)v11 - 2);
              if ( v6 )
                v12 = v11;
              *(_WORD *)v12 = 0;
              if ( v6 )
              {
                memset_0(v18, 0, sizeof(v18));
                pcbData = 256;
                if ( !RegGetValueW(hkey, 0, L"TzRegKeyName", 2u, 0, v18, &pcbData) )
                  LOBYTE(v5) = StringCchCopyW((unsigned __int16 *)a2 + 18, 0x80u, v18) >= 0;
              }
            }
          }
          RegCloseKey(hkey);
          if ( v5 && a3 )
            return (unsigned int)IsValidExtraTz(a2);
        }
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18000f3b4  mov     [rsp-8+arg_10], rbx
0x18000f3b9  push    rbp
0x18000f3ba  push    rsi
0x18000f3bb  push    rdi
0x18000f3bc  push    r14
0x18000f3be  push    r15
0x18000f3c0  lea     rbp, [rsp-280h]
0x18000f3c8  sub     rsp, 380h
0x18000f3cf  mov     rax, cs:__security_cookie
0x18000f3d6  xor     rax, rsp
0x18000f3d9  mov     [rbp+2A0h+var_30], rax
0x18000f3e0  xor     r15d, r15d
0x18000f3e3  lea     eax, [rcx-1]
0x18000f3e6  mov     r14d, r8d
0x18000f3e9  mov     rsi, rdx
0x18000f3ec  mov     ebx, r15d
0x18000f3ef  cmp     eax, 1
0x18000f3f2  ja      loc_18000F5C7
0x18000f3f8  test    rdx, rdx
0x18000f3fb  jz      loc_18000F5C7
0x18000f401  mov     r9d, ecx
0x18000f404  lea     r8, aControlPanelTi; "Control Panel\\TimeDate\\AdditionalCloc"...
0x18000f40b  lea     rcx, [rbp+2A0h+SubKey]; unsigned __int16 *
0x18000f40f  mov     edx, 100h; unsigned __int64
0x18000f414  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000f419  test    eax, eax
0x18000f41b  js      loc_18000F5C7
0x18000f421  lea     rax, [rsp+3A0h+hkey]
0x18000f426  mov     [rsp+3A0h+hkey], r15
0x18000f42b  mov     r9d, 20019h; samDesired
0x18000f431  mov     [rsp+3A0h+phkResult], rax; phkResult
0x18000f436  xor     r8d, r8d; ulOptions
0x18000f439  lea     rdx, [rbp+2A0h+SubKey]; lpSubKey
0x18000f43d  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18000f444  call    cs:__imp_RegOpenKeyExW
0x18000f44a  test    eax, eax
0x18000f44c  jnz     loc_18000F5C7
0x18000f452  mov     rcx, [rsp+3A0h+hkey]; hkey
0x18000f457  lea     rax, [rsp+3A0h+var_360]
0x18000f45c  mov     [rsp+3A0h+pcbData], rax; pcbData
0x18000f461  lea     edi, [r15+10h]
0x18000f465  lea     rax, [rsp+3A0h+var_35C]
0x18000f46a  mov     [rsp+3A0h+var_35C], r15d
0x18000f46f  mov     [rsp+3A0h+pvData], rax; pvData
0x18000f474  lea     r8, ValueName; "Enable"
0x18000f47b  mov     r9d, edi; dwFlags
0x18000f47e  mov     [rsp+3A0h+phkResult], r15; pdwType
0x18000f483  xor     edx, edx; lpSubKey
0x18000f485  mov     [rsp+3A0h+var_360], 4
0x18000f48d  call    cs:__imp_RegGetValueW
0x18000f493  test    eax, eax
0x18000f495  jnz     loc_18000F5A9
0x18000f49b  cmp     [rsp+3A0h+var_35C], r15d
0x18000f4a0  lea     r9d, [r15+2]; dwFlags
0x18000f4a4  mov     rcx, [rsp+3A0h+hkey]; hkey
0x18000f4a9  lea     r8, aDisplayname; "DisplayName"
0x18000f4b0  mov     eax, r15d
0x18000f4b3  mov     [rsp+3A0h+var_360], 20h ; ' '
0x18000f4bb  setnz   al
0x18000f4be  xorps   xmm0, xmm0
0x18000f4c1  mov     [rsi+20h], eax
0x18000f4c4  xor     edx, edx; lpSubKey
0x18000f4c6  lea     rax, [rsp+3A0h+var_360]
0x18000f4cb  mov     [rsp+3A0h+pcbData], rax; pcbData
0x18000f4d0  lea     rax, [rsp+3A0h+var_350]
0x18000f4d5  mov     [rsp+3A0h+pvData], rax; pvData
0x18000f4da  mov     [rsp+3A0h+phkResult], r15; pdwType
0x18000f4df  movups  [rsp+3A0h+var_350], xmm0
0x18000f4e4  movups  [rsp+3A0h+var_340], xmm0
0x18000f4e9  call    cs:__imp_RegGetValueW
0x18000f4ef  test    eax, eax
0x18000f4f1  jz      short loc_18000F4FE
0x18000f4f3  cmp     eax, 0EAh
0x18000f4f8  jnz     loc_18000F5A9
0x18000f4fe  mov     ecx, 0Fh
0x18000f503  lea     rdx, [rsp+3A0h+var_350]
0x18000f508  mov     rax, rsi
0x18000f50b  test    rcx, rcx
0x18000f50e  jz      short loc_18000F52F
0x18000f510  movzx   r8d, word ptr [rdx]
0x18000f514  test    r8w, r8w
0x18000f518  jz      short loc_18000F52F
0x18000f51a  mov     [rax], r8w
0x18000f51e  add     rdx, 2
0x18000f522  add     rax, 2
0x18000f526  dec     rcx
0x18000f529  sub     rdi, 1
0x18000f52d  jnz     short loc_18000F50B
0x18000f52f  test    rdi, rdi
0x18000f532  lea     rcx, [rax-2]
0x18000f536  cmovnz  rcx, rax
0x18000f53a  mov     [rcx], r15w
0x18000f53e  jz      short loc_18000F5A9
0x18000f540  xor     edx, edx; Val
0x18000f542  lea     rcx, [rsp+3A0h+var_330]; void *
0x18000f547  mov     r8d, 100h; Size
0x18000f54d  call    memset_0
0x18000f552  mov     rcx, [rsp+3A0h+hkey]; hkey
0x18000f557  lea     rax, [rsp+3A0h+var_360]
0x18000f55c  mov     [rsp+3A0h+pcbData], rax; pcbData
0x18000f561  lea     r8, aTzregkeyname; "TzRegKeyName"
0x18000f568  lea     rax, [rsp+3A0h+var_330]
0x18000f56d  mov     [rsp+3A0h+var_360], 100h
0x18000f575  mov     [rsp+3A0h+pvData], rax; pvData
0x18000f57a  mov     r9d, 2; dwFlags
0x18000f580  xor     edx, edx; lpSubKey
0x18000f582  mov     [rsp+3A0h+phkResult], r15; pdwType
0x18000f587  call    cs:__imp_RegGetValueW
0x18000f58d  test    eax, eax
0x18000f58f  jnz     short loc_18000F5A9
0x18000f591  lea     rcx, [rsi+24h]; unsigned __int16 *
0x18000f595  mov     edx, 80h; unsigned __int64
0x18000f59a  lea     r8, [rsp+3A0h+var_330]; unsigned __int16 *
0x18000f59f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f5a4  test    eax, eax
0x18000f5a6  setns   bl
0x18000f5a9  mov     rcx, [rsp+3A0h+hkey]; hKey
0x18000f5ae  call    cs:__imp_RegCloseKey
0x18000f5b4  test    ebx, ebx
0x18000f5b6  jz      short loc_18000F5C7
0x18000f5b8  test    r14d, r14d
0x18000f5bb  jz      short loc_18000F5C7
0x18000f5bd  mov     rcx, rsi; struct EXTRATZINFO *
0x18000f5c0  call    ?IsValidExtraTz@@YAHPEBUEXTRATZINFO@@@Z; IsValidExtraTz(EXTRATZINFO const *)
0x18000f5c5  mov     ebx, eax
0x18000f5c7  mov     eax, ebx
0x18000f5c9  mov     rcx, [rbp+2A0h+var_30]
0x18000f5d0  xor     rcx, rsp; StackCookie
0x18000f5d3  call    __security_check_cookie
0x18000f5d8  mov     rbx, [rsp+3A0h+arg_10]
0x18000f5e0  add     rsp, 380h
0x18000f5e7  pop     r15
0x18000f5e9  pop     r14
0x18000f5eb  pop     rdi
0x18000f5ec  pop     rsi
0x18000f5ed  pop     rbp
0x18000f5ee  retn
```
