# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)

- ea: `0x180032030`
- end: `0x1800321e6`
- name: `?_InitializeFromRegistry@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z`
- size: `438`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000d678`
- `0x18002d334`
- `0x18002dc44`
- `0x18002f1b0`
- `0x18002fdac`
- `0x180031d0c`

## callees

- `0x180012550`
- `0x180031454`
- `0x180032030`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180032121`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180032150`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180032121`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180032150`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180032080`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800320f0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180032080`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800320f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032167`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800321b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800321c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032167`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800321b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800321c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800320c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180032132`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800320c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180032132`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_InitializeFromRegistry(
        BYTE **a1,
        HKEY a2,
        const WCHAR *a3)
{
  BYTE *lpData; // rdi
  LSTATUS Value; // eax
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
  SIZE_T cb; // [rsp+30h] [rbp-48h] BYREF

  cb = 0;
  lpData = 0;
  Value = RegQueryValueExW(a2, a3, 0, (LPDWORD)&cb + 1, 0, (LPDWORD)&cb);
  v8 = Value;
  if ( Value > 0 )
    v8 = (unsigned __int16)Value | 0x80070000;
  if ( v8 >= 0 )
  {
    if ( (unsigned int)(HIDWORD(cb) - 1) > 1 || !(_DWORD)cb || (cb & 1) != 0 )
      goto LABEL_24;
    lpData = (BYTE *)CoTaskMemAlloc((unsigned int)cb);
    if ( !lpData )
    {
LABEL_14:
      v8 = -2147024882;
      goto LABEL_25;
    }
    v9 = RegQueryValueExW(a2, a3, 0, (LPDWORD)&cb + 1, lpData, (LPDWORD)&cb);
    v8 = v9;
    if ( v9 > 0 )
      v8 = (unsigned __int16)v9 | 0x80070000;
    if ( v8 >= 0 )
    {
      v10 = ((unsigned int)cb >> 1) - 1;
      if ( HIDWORD(cb) == 2 )
      {
        v11 = ExpandEnvironmentStringsW((LPCWSTR)lpData, 0, 0);
        v12 = v11;
        if ( v11 )
        {
          v13 = (WCHAR *)CoTaskMemAlloc(2LL * v11);
          v14 = v13;
          if ( !v13 )
            goto LABEL_14;
          v15 = ExpandEnvironmentStringsW((LPCWSTR)lpData, v13, v12);
          v16 = v15;
          if ( !v15 || v15 > v12 )
          {
            v8 = -2147024774;
            CoTaskMemFree(v14);
            goto LABEL_25;
          }
          v8 = 0;
          CoTaskMemFree(lpData);
          lpData = (BYTE *)v14;
          v10 = v16 - 1;
        }
      }
      if ( !*(_WORD *)&lpData[2 * v10] )
      {
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(a1);
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
  CoTaskMemFree(lpData);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180032030  mov     r11, rsp
0x180032033  push    rbx
0x180032034  push    rbp
0x180032035  push    rsi
0x180032036  push    rdi
0x180032037  push    r12
0x180032039  push    r14
0x18003203b  push    r15
0x18003203d  sub     rsp, 40h
0x180032041  mov     rax, cs:__security_cookie
0x180032048  xor     rax, rsp
0x18003204b  mov     [rsp+78h+var_40], rax
0x180032050  xor     r12d, r12d
0x180032053  lea     rax, [r11-48h]
0x180032057  mov     rbp, r8
0x18003205a  mov     [r11-50h], rax
0x18003205e  mov     rsi, rdx
0x180032061  mov     [r11-58h], r12
0x180032065  mov     r15, rcx
0x180032068  mov     [r11-44h], r12d
0x18003206c  mov     rdx, rbp; lpValueName
0x18003206f  mov     [r11-48h], r12d
0x180032073  mov     rcx, rsi; hKey
0x180032076  lea     r9, [r11-44h]; lpType
0x18003207a  xor     r8d, r8d; lpReserved
0x18003207d  mov     edi, r12d
0x180032080  call    cs:__imp_RegQueryValueExW
0x180032086  mov     ebx, eax
0x180032088  mov     r14d, 80070000h
0x18003208e  test    eax, eax
0x180032090  jle     short loc_180032098
0x180032092  movzx   ebx, ax
0x180032095  or      ebx, r14d
0x180032098  test    ebx, ebx
0x18003209a  js      loc_1800321BF
0x1800320a0  mov     eax, dword ptr [rsp+78h+cb+4]
0x1800320a4  dec     eax
0x1800320a6  cmp     eax, 1
0x1800320a9  ja      loc_1800321BA
0x1800320af  mov     eax, dword ptr [rsp+78h+cb]
0x1800320b3  test    eax, eax
0x1800320b5  jz      loc_1800321BA
0x1800320bb  test    al, 1
0x1800320bd  jnz     loc_1800321BA
0x1800320c3  mov     ecx, eax; cb
0x1800320c5  call    cs:__imp_CoTaskMemAlloc
0x1800320cb  mov     rdi, rax
0x1800320ce  test    rax, rax
0x1800320d1  jz      short loc_180032140
0x1800320d3  lea     rax, [rsp+78h+cb]
0x1800320d8  xor     r8d, r8d; lpReserved
0x1800320db  mov     [rsp+78h+lpcbData], rax; lpcbData
0x1800320e0  lea     r9, [rsp+78h+cb+4]; lpType
0x1800320e5  mov     rdx, rbp; lpValueName
0x1800320e8  mov     [rsp+78h+lpData], rdi; lpData
0x1800320ed  mov     rcx, rsi; hKey
0x1800320f0  call    cs:__imp_RegQueryValueExW
0x1800320f6  mov     ebx, eax
0x1800320f8  test    eax, eax
0x1800320fa  jle     short loc_180032102
0x1800320fc  movzx   ebx, ax
0x1800320ff  or      ebx, r14d
0x180032102  test    ebx, ebx
0x180032104  js      loc_1800321BF
0x18003210a  mov     esi, dword ptr [rsp+78h+cb]
0x18003210e  shr     esi, 1
0x180032110  dec     esi
0x180032112  cmp     dword ptr [rsp+78h+cb+4], 2
0x180032117  jnz     short loc_180032174
0x180032119  xor     r8d, r8d; nSize
0x18003211c  xor     edx, edx; lpDst
0x18003211e  mov     rcx, rdi; lpSrc
0x180032121  call    cs:__imp_ExpandEnvironmentStringsW
0x180032127  mov     ebp, eax
0x180032129  test    eax, eax
0x18003212b  jz      short loc_180032174
0x18003212d  mov     ecx, ebp
0x18003212f  add     rcx, rcx; cb
0x180032132  call    cs:__imp_CoTaskMemAlloc
0x180032138  mov     rsi, rax
0x18003213b  test    rax, rax
0x18003213e  jnz     short loc_180032147
0x180032140  mov     ebx, 8007000Eh
0x180032145  jmp     short loc_1800321BF
0x180032147  mov     r8d, ebp; nSize
0x18003214a  mov     rdx, rsi; lpDst
0x18003214d  mov     rcx, rdi; lpSrc
0x180032150  call    cs:__imp_ExpandEnvironmentStringsW
0x180032156  mov     r14d, eax
0x180032159  test    eax, eax
0x18003215b  jz      short loc_1800321AA
0x18003215d  cmp     eax, ebp
0x18003215f  ja      short loc_1800321AA
0x180032161  mov     rcx, rdi; pv
0x180032164  mov     ebx, r12d
0x180032167  call    cs:__imp_CoTaskMemFree
0x18003216d  mov     rdi, rsi
0x180032170  lea     esi, [r14-1]
0x180032174  cmp     [rdi+rsi*2], r12w
0x180032179  jnz     short loc_1800321BA
0x18003217b  mov     rcx, r15
0x18003217e  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180032183  test    rdi, rdi
0x180032186  jz      short loc_1800321A5
0x180032188  lea     eax, [rsi+1]
0x18003218b  mov     ecx, eax
0x18003218d  test    eax, eax
0x18003218f  jz      short loc_1800321A5
0x180032191  dec     rax
0x180032194  mov     [r15], rdi
0x180032197  mov     [r15+8], rax
0x18003219b  mov     [r15+10h], rcx
0x18003219f  mov     [rdi+rcx*2-2], r12w
0x1800321a5  mov     rdi, r12
0x1800321a8  jmp     short loc_1800321BF
0x1800321aa  mov     rcx, rsi; pv
0x1800321ad  mov     ebx, 8007007Ah
0x1800321b2  call    cs:__imp_CoTaskMemFree
0x1800321b8  jmp     short loc_1800321BF
0x1800321ba  mov     ebx, 8007000Dh
0x1800321bf  mov     rcx, rdi; pv
0x1800321c2  call    cs:__imp_CoTaskMemFree
0x1800321c8  mov     eax, ebx
0x1800321ca  mov     rcx, [rsp+78h+var_40]
0x1800321cf  xor     rcx, rsp; StackCookie
0x1800321d2  call    __security_check_cookie
0x1800321d7  add     rsp, 40h
0x1800321db  pop     r15
0x1800321dd  pop     r14
0x1800321df  pop     r12
0x1800321e1  pop     rdi
0x1800321e2  pop     rsi
0x1800321e3  pop     rbp
0x1800321e4  pop     rbx
0x1800321e5  retn
```
