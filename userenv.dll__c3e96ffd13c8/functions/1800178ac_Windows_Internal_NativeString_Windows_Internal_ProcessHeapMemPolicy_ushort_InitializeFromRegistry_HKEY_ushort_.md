# Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)

- ea: `0x1800178ac`
- end: `0x180017a5c`
- name: `?_InitializeFromRegistry@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z`
- size: `432`
- prototype: `__int64 __fastcall(BYTE **, HKEY, const WCHAR *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180003d70`
- `0x180007988`

## callees

- `0x180003f60`
- `0x180003fb4`
- `0x1800078a0`
- `0x1800178ac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800178f7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001796c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800178f7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001796c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800179a0`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800179ce`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800179a0`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800179ce`

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
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)a1);
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
0x1800178ac  mov     r11, rsp
0x1800178af  mov     [r11+8], rbx
0x1800178b3  mov     [r11+10h], rbp
0x1800178b7  mov     [r11+20h], r9b
0x1800178bb  push    rsi
0x1800178bc  push    rdi
0x1800178bd  push    r12
0x1800178bf  push    r14
0x1800178c1  push    r15
0x1800178c3  sub     rsp, 40h
0x1800178c7  xor     r12d, r12d
0x1800178ca  lea     rax, [r11+20h]
0x1800178ce  mov     rsi, r8
0x1800178d1  mov     [r11-40h], rax
0x1800178d5  mov     rbp, rdx
0x1800178d8  mov     [r11-48h], r12
0x1800178dc  mov     r15, rcx
0x1800178df  mov     [r11-38h], r12d
0x1800178e3  mov     rdx, rsi; lpValueName
0x1800178e6  mov     [r11+20h], r12d
0x1800178ea  mov     rcx, rbp; hKey
0x1800178ed  lea     r9, [r11-38h]; lpType
0x1800178f1  xor     r8d, r8d; lpReserved
0x1800178f4  mov     edi, r12d
0x1800178f7  call    cs:__imp_RegQueryValueExW
0x1800178fd  mov     ebx, eax
0x1800178ff  mov     r14d, 80070000h
0x180017905  test    eax, eax
0x180017907  jle     short loc_18001790F
0x180017909  movzx   ebx, ax
0x18001790c  or      ebx, r14d
0x18001790f  test    ebx, ebx
0x180017911  js      loc_180017A3B
0x180017917  mov     eax, [rsp+68h+Type]
0x18001791b  dec     eax
0x18001791d  cmp     eax, 1
0x180017920  ja      loc_180017A36
0x180017926  mov     eax, [rsp+68h+cbData]
0x18001792d  test    eax, eax
0x18001792f  jz      loc_180017A36
0x180017935  test    al, 1
0x180017937  jnz     loc_180017A36
0x18001793d  mov     ecx, eax
0x18001793f  call    ?Alloc@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAPEAG_K@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Alloc(unsigned __int64)
0x180017944  mov     rdi, rax
0x180017947  test    rax, rax
0x18001794a  jz      short loc_1800179BE
0x18001794c  lea     rax, [rsp+68h+cbData]
0x180017954  xor     r8d, r8d; lpReserved
0x180017957  mov     [rsp+68h+lpcbData], rax; lpcbData
0x18001795c  lea     r9, [rsp+68h+Type]; lpType
0x180017961  mov     rdx, rsi; lpValueName
0x180017964  mov     [rsp+68h+lpData], rdi; lpData
0x180017969  mov     rcx, rbp; hKey
0x18001796c  call    cs:__imp_RegQueryValueExW
0x180017972  mov     ebx, eax
0x180017974  test    eax, eax
0x180017976  jle     short loc_18001797E
0x180017978  movzx   ebx, ax
0x18001797b  or      ebx, r14d
0x18001797e  test    ebx, ebx
0x180017980  js      loc_180017A3B
0x180017986  mov     esi, [rsp+68h+cbData]
0x18001798d  shr     esi, 1
0x18001798f  dec     esi
0x180017991  cmp     [rsp+68h+Type], 2
0x180017996  jnz     short loc_1800179F1
0x180017998  xor     r8d, r8d; nSize
0x18001799b  xor     edx, edx; lpDst
0x18001799d  mov     rcx, rdi; lpSrc
0x1800179a0  call    cs:__imp_ExpandEnvironmentStringsW
0x1800179a6  mov     ebp, eax
0x1800179a8  test    eax, eax
0x1800179aa  jz      short loc_1800179F1
0x1800179ac  mov     ecx, ebp
0x1800179ae  add     rcx, rcx
0x1800179b1  call    ?Alloc@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAPEAG_K@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Alloc(unsigned __int64)
0x1800179b6  mov     rsi, rax
0x1800179b9  test    rax, rax
0x1800179bc  jnz     short loc_1800179C5
0x1800179be  mov     ebx, 8007000Eh
0x1800179c3  jmp     short loc_180017A3B
0x1800179c5  mov     r8d, ebp; nSize
0x1800179c8  mov     rdx, rsi; lpDst
0x1800179cb  mov     rcx, rdi; lpSrc
0x1800179ce  call    cs:__imp_ExpandEnvironmentStringsW
0x1800179d4  mov     r14d, eax
0x1800179d7  test    eax, eax
0x1800179d9  jz      short loc_180017A27
0x1800179db  cmp     eax, ebp
0x1800179dd  ja      short loc_180017A27
0x1800179df  mov     rcx, rdi
0x1800179e2  mov     ebx, r12d
0x1800179e5  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x1800179ea  mov     rdi, rsi
0x1800179ed  lea     esi, [r14-1]
0x1800179f1  cmp     [rdi+rsi*2], r12w
0x1800179f6  jnz     short loc_180017A36
0x1800179f8  mov     rcx, r15
0x1800179fb  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180017a00  test    rdi, rdi
0x180017a03  jz      short loc_180017A22
0x180017a05  lea     eax, [rsi+1]
0x180017a08  mov     ecx, eax
0x180017a0a  test    eax, eax
0x180017a0c  jz      short loc_180017A22
0x180017a0e  dec     rax
0x180017a11  mov     [r15], rdi
0x180017a14  mov     [r15+8], rax
0x180017a18  mov     [r15+10h], rcx
0x180017a1c  mov     [rdi+rcx*2-2], r12w
0x180017a22  mov     rdi, r12
0x180017a25  jmp     short loc_180017A3B
0x180017a27  mov     rcx, rsi
0x180017a2a  mov     ebx, 8007007Ah
0x180017a2f  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x180017a34  jmp     short loc_180017A3B
0x180017a36  mov     ebx, 8007000Dh
0x180017a3b  mov     rcx, rdi
0x180017a3e  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x180017a43  mov     rbp, [rsp+68h+arg_8]
0x180017a48  mov     eax, ebx
0x180017a4a  mov     rbx, [rsp+68h+arg_0]
0x180017a4f  add     rsp, 40h
0x180017a53  pop     r15
0x180017a55  pop     r14
0x180017a57  pop     r12
0x180017a59  pop     rdi
0x180017a5a  pop     rsi
0x180017a5b  retn
```
