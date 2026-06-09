# Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)

- ea: `0x180019204`
- end: `0x1800193cd`
- name: `?_InitializeFromRegistry@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z`
- size: `457`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180003e90`
- `0x180008a58`

## callees

- `0x1800040b0`
- `0x18000438c`
- `0x180008940`
- `0x180019204`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001924f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800192ca`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001924f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800192ca`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180019304`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180019338`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180019304`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180019338`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_InitializeFromRegistry(
        BYTE **a1,
        HKEY a2,
        const WCHAR *a3)
{
  BYTE *lpData; // rdi
  LSTATUS v7; // eax
  signed int v8; // ebx
  LSTATUS v9; // eax
  __int64 v10; // rsi
  DWORD v11; // eax
  DWORD v12; // ebp
  WCHAR *v13; // rax
  WCHAR *v14; // rsi
  DWORD v15; // eax
  DWORD v16; // r14d
  __int64 v17; // rax
  DWORD Type[14]; // [rsp+30h] [rbp-38h] BYREF
  DWORD cbData; // [rsp+88h] [rbp+20h] BYREF

  Type[0] = 0;
  cbData = 0;
  lpData = 0;
  v7 = RegQueryValueExW(a2, a3, 0, Type, 0, &cbData);
  v8 = v7;
  if ( v7 > 0 )
    v8 = (unsigned __int16)v7 | 0x80070000;
  if ( v8 >= 0 )
  {
    if ( Type[0] - 1 > 1 || !cbData || (cbData & 1) != 0 )
      goto LABEL_24;
    lpData = (BYTE *)Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Alloc(cbData);
    if ( !lpData )
    {
LABEL_14:
      v8 = -2147024882;
      goto LABEL_25;
    }
    v9 = RegQueryValueExW(a2, a3, 0, Type, lpData, &cbData);
    v8 = v9;
    if ( v9 > 0 )
      v8 = (unsigned __int16)v9 | 0x80070000;
    if ( v8 >= 0 )
    {
      v10 = (cbData >> 1) - 1;
      if ( Type[0] == 2 )
      {
        v11 = ExpandEnvironmentStringsW((LPCWSTR)lpData, 0, 0);
        v12 = v11;
        if ( v11 )
        {
          v13 = (WCHAR *)Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Alloc(2LL * v11);
          v14 = v13;
          if ( !v13 )
            goto LABEL_14;
          v15 = ExpandEnvironmentStringsW((LPCWSTR)lpData, v13, v12);
          v16 = v15;
          if ( !v15 || v15 > v12 )
          {
            v8 = -2147024774;
            Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Free(v14);
            goto LABEL_25;
          }
          v8 = 0;
          Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Free(lpData);
          lpData = (BYTE *)v14;
          v10 = v16 - 1;
        }
      }
      if ( !*(_WORD *)&lpData[2 * v10] )
      {
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(a1);
        if ( lpData )
        {
          v17 = (unsigned int)(v10 + 1);
          if ( (_DWORD)v10 != -1 )
          {
            *a1 = lpData;
            a1[1] = (BYTE *)(v17 - 1);
            a1[2] = (BYTE *)(unsigned int)v17;
            *(_WORD *)&lpData[2 * (unsigned int)v17 - 2] = 0;
          }
        }
        lpData = 0;
        goto LABEL_25;
      }
LABEL_24:
      v8 = -2147024883;
    }
  }
LABEL_25:
  Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Free(lpData);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180019204  mov     r11, rsp
0x180019207  mov     [r11+8], rbx
0x18001920b  mov     [r11+10h], rbp
0x18001920f  mov     [r11+20h], r9b
0x180019213  push    rsi
0x180019214  push    rdi
0x180019215  push    r12
0x180019217  push    r14
0x180019219  push    r15
0x18001921b  sub     rsp, 40h
0x18001921f  xor     r12d, r12d
0x180019222  lea     rax, [r11+20h]
0x180019226  mov     rsi, r8
0x180019229  mov     [r11-40h], rax
0x18001922d  mov     rbp, rdx
0x180019230  mov     [r11-48h], r12
0x180019234  mov     r15, rcx
0x180019237  mov     [r11-38h], r12d
0x18001923b  mov     rdx, rsi; lpValueName
0x18001923e  mov     [r11+20h], r12d
0x180019242  mov     rcx, rbp; hKey
0x180019245  lea     r9, [r11-38h]; lpType
0x180019249  xor     r8d, r8d; lpReserved
0x18001924c  mov     edi, r12d
0x18001924f  call    cs:__imp_RegQueryValueExW
0x180019256  nop     dword ptr [rax+rax+00h]
0x18001925b  mov     ebx, eax
0x18001925d  mov     r14d, 80070000h
0x180019263  test    eax, eax
0x180019265  jle     short loc_18001926D
0x180019267  movzx   ebx, ax
0x18001926a  or      ebx, r14d
0x18001926d  test    ebx, ebx
0x18001926f  js      loc_1800193AB
0x180019275  mov     eax, [rsp+68h+Type]
0x180019279  dec     eax
0x18001927b  cmp     eax, 1
0x18001927e  ja      loc_1800193A6
0x180019284  mov     eax, [rsp+68h+cbData]
0x18001928b  test    eax, eax
0x18001928d  jz      loc_1800193A6
0x180019293  test    al, 1
0x180019295  jnz     loc_1800193A6
0x18001929b  mov     ecx, eax
0x18001929d  call    ?Alloc@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAPEAG_K@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Alloc(unsigned __int64)
0x1800192a2  mov     rdi, rax
0x1800192a5  test    rax, rax
0x1800192a8  jz      short loc_180019328
0x1800192aa  lea     rax, [rsp+68h+cbData]
0x1800192b2  xor     r8d, r8d; lpReserved
0x1800192b5  mov     [rsp+68h+lpcbData], rax; lpcbData
0x1800192ba  lea     r9, [rsp+68h+Type]; lpType
0x1800192bf  mov     rdx, rsi; lpValueName
0x1800192c2  mov     [rsp+68h+lpData], rdi; lpData
0x1800192c7  mov     rcx, rbp; hKey
0x1800192ca  call    cs:__imp_RegQueryValueExW
0x1800192d1  nop     dword ptr [rax+rax+00h]
0x1800192d6  mov     ebx, eax
0x1800192d8  test    eax, eax
0x1800192da  jle     short loc_1800192E2
0x1800192dc  movzx   ebx, ax
0x1800192df  or      ebx, r14d
0x1800192e2  test    ebx, ebx
0x1800192e4  js      loc_1800193AB
0x1800192ea  mov     esi, [rsp+68h+cbData]
0x1800192f1  shr     esi, 1
0x1800192f3  dec     esi
0x1800192f5  cmp     [rsp+68h+Type], 2
0x1800192fa  jnz     short loc_180019361
0x1800192fc  xor     r8d, r8d; nSize
0x1800192ff  xor     edx, edx; lpDst
0x180019301  mov     rcx, rdi; lpSrc
0x180019304  call    cs:__imp_ExpandEnvironmentStringsW
0x18001930b  nop     dword ptr [rax+rax+00h]
0x180019310  mov     ebp, eax
0x180019312  test    eax, eax
0x180019314  jz      short loc_180019361
0x180019316  mov     ecx, ebp
0x180019318  add     rcx, rcx
0x18001931b  call    ?Alloc@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAPEAG_K@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Alloc(unsigned __int64)
0x180019320  mov     rsi, rax
0x180019323  test    rax, rax
0x180019326  jnz     short loc_18001932F
0x180019328  mov     ebx, 8007000Eh
0x18001932d  jmp     short loc_1800193AB
0x18001932f  mov     r8d, ebp; nSize
0x180019332  mov     rdx, rsi; lpDst
0x180019335  mov     rcx, rdi; lpSrc
0x180019338  call    cs:__imp_ExpandEnvironmentStringsW
0x18001933f  nop     dword ptr [rax+rax+00h]
0x180019344  mov     r14d, eax
0x180019347  test    eax, eax
0x180019349  jz      short loc_180019397
0x18001934b  cmp     eax, ebp
0x18001934d  ja      short loc_180019397
0x18001934f  mov     rcx, rdi
0x180019352  mov     ebx, r12d
0x180019355  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x18001935a  mov     rdi, rsi
0x18001935d  lea     esi, [r14-1]
0x180019361  cmp     [rdi+rsi*2], r12w
0x180019366  jnz     short loc_1800193A6
0x180019368  mov     rcx, r15
0x18001936b  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180019370  test    rdi, rdi
0x180019373  jz      short loc_180019392
0x180019375  lea     eax, [rsi+1]
0x180019378  mov     ecx, eax
0x18001937a  test    eax, eax
0x18001937c  jz      short loc_180019392
0x18001937e  dec     rax
0x180019381  mov     [r15], rdi
0x180019384  mov     [r15+8], rax
0x180019388  mov     [r15+10h], rcx
0x18001938c  mov     [rdi+rcx*2-2], r12w
0x180019392  mov     rdi, r12
0x180019395  jmp     short loc_1800193AB
0x180019397  mov     rcx, rsi
0x18001939a  mov     ebx, 8007007Ah
0x18001939f  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x1800193a4  jmp     short loc_1800193AB
0x1800193a6  mov     ebx, 8007000Dh
0x1800193ab  mov     rcx, rdi
0x1800193ae  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x1800193b3  mov     rbp, [rsp+68h+arg_8]
0x1800193b8  mov     eax, ebx
0x1800193ba  mov     rbx, [rsp+68h+arg_0]
0x1800193bf  add     rsp, 40h
0x1800193c3  pop     r15
0x1800193c5  pop     r14
0x1800193c7  pop     r12
0x1800193c9  pop     rdi
0x1800193ca  pop     rsi
0x1800193cb  retn
```
