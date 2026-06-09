# joyGetDevCapsA

- ea: `0x18000e6e0`
- end: `0x18000e9d0`
- name: `joyGetDevCapsA`
- size: `752`
- prototype: `MMRESULT __stdcall(UINT_PTR uJoyID, LPJOYCAPSA pjc, UINT cbjc)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x18000c990`
- `0x18000d470`
- `0x18000e6e0`
- `0x18000e9e0`
- `0x18001a811`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000e827`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000e85e`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000e899`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000e827`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000e85e`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000e899`

## string_xrefs

- `0x18000e755`: `DINPUT.DLL`

## pseudocode

```c
MMRESULT __stdcall joyGetDevCapsA(UINT_PTR uJoyID, LPJOYCAPSA pjc, UINT cbjc)
{
  size_t v3; // rsi
  size_t v6; // rdi
  MMRESULT DevCapsW; // r15d
  char *v9; // rdx
  __int64 v10; // rax
  CHAR *szRegKey; // rcx
  __int64 v12; // rbx
  CHAR *v13; // rax
  size_t v14; // r8
  _WORD Src[2]; // [rsp+40h] [rbp-C0h] BYREF
  CHAR MultiByteStr[32]; // [rsp+44h] [rbp-BCh] BYREF
  UINT wXmin; // [rsp+64h] [rbp-9Ch]
  UINT wXmax; // [rsp+68h] [rbp-98h]
  UINT wYmin; // [rsp+6Ch] [rbp-94h]
  UINT wYmax; // [rsp+70h] [rbp-90h]
  UINT wZmin; // [rsp+74h] [rbp-8Ch]
  UINT wZmax; // [rsp+78h] [rbp-88h]
  UINT wNumButtons; // [rsp+7Ch] [rbp-84h]
  UINT wPeriodMin; // [rsp+80h] [rbp-80h]
  UINT wPeriodMax; // [rsp+84h] [rbp-7Ch]
  UINT wRmin; // [rsp+88h] [rbp-78h]
  UINT wRmax; // [rsp+8Ch] [rbp-74h]
  UINT wUmin; // [rsp+90h] [rbp-70h]
  UINT wUmax; // [rsp+94h] [rbp-6Ch]
  UINT wVmin; // [rsp+98h] [rbp-68h]
  UINT wVmax; // [rsp+9Ch] [rbp-64h]
  UINT wCaps; // [rsp+A0h] [rbp-60h]
  UINT wMaxAxes; // [rsp+A4h] [rbp-5Ch]
  UINT wNumAxes; // [rsp+A8h] [rbp-58h]
  UINT wMaxButtons; // [rsp+ACh] [rbp-54h]
  CHAR lpMultiByteStr[32]; // [rsp+B0h] [rbp-50h] BYREF
  CHAR v37[260]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v38; // [rsp+1D4h] [rbp+D4h]
  __int128 v39; // [rsp+1E4h] [rbp+E4h]
  __int128 v40; // [rsp+1F4h] [rbp+F4h]
  tagJOYCAPSW pjca; // [rsp+210h] [rbp+110h] BYREF
  __int128 v42; // [rsp+4E8h] [rbp+3E8h]
  __int128 v43; // [rsp+4F8h] [rbp+3F8h]
  __int128 v44; // [rsp+508h] [rbp+408h]

  v3 = cbjc;
  v6 = 452;
  memset_0(Src, 0, 0x1C4u);
  if ( !pjc )
    return 11;
  if ( (_DWORD)v3 != 404 && (_DWORD)v3 != 452 )
    return 165;
  if ( uJoyID == -1 )
  {
    DevCapsW = 0;
    v9 = aDinputDll_1;
    v10 = 2147483646;
    szRegKey = pjc->szRegKey;
    v12 = 32;
    do
    {
      if ( !v10 )
        break;
      if ( !*v9 )
        break;
      *szRegKey++ = *v9++;
      --v10;
      --v12;
    }
    while ( v12 );
    v13 = szRegKey - 1;
    if ( v12 )
      v13 = szRegKey;
    *v13 = 0;
  }
  else
  {
    if ( uJoyID >= 0x10 )
      return 6;
    v14 = 452;
    if ( (unsigned int)v3 < 0x1C4 )
      v14 = v3;
    memset_0(pjc, 0, v14);
    memset_0(&pjca, 0, 0x308u);
    DevCapsW = joyGetDevCapsW(uJoyID, &pjca, 0x308u);
    if ( !DevCapsW )
    {
      WideCharToMultiByte(0, 0x400u, pjca.szPname, -1, MultiByteStr, 32, 0, 0);
      WideCharToMultiByte(0, 0x400u, pjca.szRegKey, -1, lpMultiByteStr, 32, 0, 0);
      WideCharToMultiByte(0, 0x400u, pjca.szOEMVxD, -1, v37, 260, 0, 0);
      Src[0] = pjca.wMid;
      if ( (unsigned int)v3 < 0x1C4 )
        v6 = v3;
      Src[1] = pjca.wPid;
      wXmin = pjca.wXmin;
      wXmax = pjca.wXmax;
      wYmin = pjca.wYmin;
      wYmax = pjca.wYmax;
      wZmin = pjca.wZmin;
      wZmax = pjca.wZmax;
      wNumButtons = pjca.wNumButtons;
      wPeriodMin = pjca.wPeriodMin;
      wPeriodMax = pjca.wPeriodMax;
      wRmin = pjca.wRmin;
      wRmax = pjca.wRmax;
      wUmin = pjca.wUmin;
      wUmax = pjca.wUmax;
      wVmin = pjca.wVmin;
      wVmax = pjca.wVmax;
      wCaps = pjca.wCaps;
      wMaxAxes = pjca.wMaxAxes;
      v38 = v42;
      wNumAxes = pjca.wNumAxes;
      wMaxButtons = pjca.wMaxButtons;
      v39 = v43;
      v40 = v44;
      memcpy_0(pjc, Src, v6);
    }
  }
  return DevCapsW;
}

```

## disassembly

```asm
0x18000e6e0  push    rbp
0x18000e6e2  push    rbx
0x18000e6e3  push    rsi
0x18000e6e4  push    rdi
0x18000e6e5  push    r12
0x18000e6e7  push    r14
0x18000e6e9  push    r15
0x18000e6eb  lea     rbp, [rsp-430h]
0x18000e6f3  sub     rsp, 530h
0x18000e6fa  mov     rax, cs:__security_cookie
0x18000e701  xor     rax, rsp
0x18000e704  mov     [rbp+460h+var_40], rax
0x18000e70b  mov     esi, r8d
0x18000e70e  mov     r14, rdx
0x18000e711  mov     rbx, rcx
0x18000e714  mov     edi, 1C4h
0x18000e719  mov     r8d, edi; Size
0x18000e71c  lea     rcx, [rsp+560h+Src]; void *
0x18000e721  xor     edx, edx; Val
0x18000e723  call    memset_0
0x18000e728  test    r14, r14
0x18000e72b  jnz     short loc_18000E736
0x18000e72d  lea     eax, [r14+0Bh]
0x18000e731  jmp     loc_18000E9AF
0x18000e736  cmp     esi, 194h
0x18000e73c  jz      short loc_18000E74C
0x18000e73e  cmp     esi, edi
0x18000e740  jz      short loc_18000E74C
0x18000e742  mov     eax, 0A5h
0x18000e747  jmp     loc_18000E9AF
0x18000e74c  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000e750  jnz     short loc_18000E79B
0x18000e752  xor     r15d, r15d
0x18000e755  lea     rdx, aDinputDll_1; "DINPUT.DLL"
0x18000e75c  mov     eax, 7FFFFFFEh
0x18000e761  lea     rcx, [r14+70h]
0x18000e765  lea     ebx, [r15+20h]
0x18000e769  test    rax, rax
0x18000e76c  jz      short loc_18000E788
0x18000e76e  mov     r8b, [rdx]
0x18000e771  test    r8b, r8b
0x18000e774  jz      short loc_18000E788
0x18000e776  mov     [rcx], r8b
0x18000e779  inc     rdx
0x18000e77c  inc     rcx
0x18000e77f  dec     rax
0x18000e782  sub     rbx, 1
0x18000e786  jnz     short loc_18000E769
0x18000e788  test    rbx, rbx
0x18000e78b  lea     rax, [rcx-1]
0x18000e78f  cmovnz  rax, rcx
0x18000e793  mov     [rax], r15b
0x18000e796  jmp     loc_18000E9AC
0x18000e79b  cmp     rbx, 10h
0x18000e79f  jb      short loc_18000E7AB
0x18000e7a1  mov     eax, 6
0x18000e7a6  jmp     loc_18000E9AF
0x18000e7ab  cmp     esi, edi
0x18000e7ad  mov     r8, rdi
0x18000e7b0  mov     rcx, r14; void *
0x18000e7b3  cmovb   r8, rsi; Size
0x18000e7b7  xor     edx, edx; Val
0x18000e7b9  call    memset_0
0x18000e7be  mov     r15d, 308h
0x18000e7c4  lea     rcx, [rbp+460h+pjc]; void *
0x18000e7cb  mov     r8d, r15d; Size
0x18000e7ce  xor     edx, edx; Val
0x18000e7d0  call    memset_0
0x18000e7d5  mov     r8d, r15d; cbjc
0x18000e7d8  lea     rdx, [rbp+460h+pjc]; pjc
0x18000e7df  mov     rcx, rbx; uJoyID
0x18000e7e2  call    joyGetDevCapsW
0x18000e7e7  mov     r15d, eax
0x18000e7ea  test    eax, eax
0x18000e7ec  jnz     loc_18000E9AC
0x18000e7f2  mov     [rsp+560h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18000e7fb  lea     ebx, [rax+20h]
0x18000e7fe  mov     [rsp+560h+lpDefaultChar], 0; lpDefaultChar
0x18000e807  lea     rax, [rsp+560h+MultiByteStr]
0x18000e80c  mov     [rsp+560h+cbMultiByte], ebx; cbMultiByte
0x18000e810  lea     r8, [rbp+460h+pjc.szPname]; lpWideCharStr
0x18000e817  or      r9d, 0FFFFFFFFh; cchWideChar
0x18000e81b  mov     [rsp+560h+lpMultiByteStr], rax; lpMultiByteStr
0x18000e820  mov     edx, 400h; dwFlags
0x18000e825  xor     ecx, ecx; CodePage
0x18000e827  call    cs:__imp_WideCharToMultiByte
0x18000e82d  mov     [rsp+560h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18000e836  lea     rax, [rbp+460h+var_4B0]
0x18000e83a  mov     [rsp+560h+lpDefaultChar], 0; lpDefaultChar
0x18000e843  lea     r8, [rbp+460h+pjc.szRegKey]; lpWideCharStr
0x18000e84a  mov     [rsp+560h+cbMultiByte], ebx; cbMultiByte
0x18000e84e  or      r9d, 0FFFFFFFFh; cchWideChar
0x18000e852  mov     edx, 400h; dwFlags
0x18000e857  mov     [rsp+560h+lpMultiByteStr], rax; lpMultiByteStr
0x18000e85c  xor     ecx, ecx; CodePage
0x18000e85e  call    cs:__imp_WideCharToMultiByte
0x18000e864  mov     [rsp+560h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18000e86d  lea     rax, [rbp+460h+var_490]
0x18000e871  mov     [rsp+560h+lpDefaultChar], 0; lpDefaultChar
0x18000e87a  lea     r8, [rbp+460h+pjc.szOEMVxD]; lpWideCharStr
0x18000e881  mov     [rsp+560h+cbMultiByte], 104h; cbMultiByte
0x18000e889  or      r9d, 0FFFFFFFFh; cchWideChar
0x18000e88d  mov     edx, 400h; dwFlags
0x18000e892  mov     [rsp+560h+lpMultiByteStr], rax; lpMultiByteStr
0x18000e897  xor     ecx, ecx; CodePage
0x18000e899  call    cs:__imp_WideCharToMultiByte
0x18000e89f  movzx   eax, [rbp+460h+pjc.wMid]
0x18000e8a6  cmp     esi, edi
0x18000e8a8  movups  xmm0, [rbp+460h+var_78]
0x18000e8af  mov     [rsp+560h+Src], ax
0x18000e8b4  cmovb   rdi, rsi
0x18000e8b8  movzx   eax, [rbp+460h+pjc.wPid]
0x18000e8bf  movups  xmm1, [rbp+460h+var_68]
0x18000e8c6  mov     [rsp+560h+var_51E], ax
0x18000e8cb  mov     eax, [rbp+460h+pjc.wXmin]
0x18000e8d1  mov     [rsp+560h+var_4FC], eax
0x18000e8d5  mov     eax, [rbp+460h+pjc.wXmax]
0x18000e8db  mov     [rsp+560h+var_4F8], eax
0x18000e8df  mov     eax, [rbp+460h+pjc.wYmin]
0x18000e8e5  mov     [rsp+560h+var_4F4], eax
0x18000e8e9  mov     eax, [rbp+460h+pjc.wYmax]
0x18000e8ef  mov     [rsp+560h+var_4F0], eax
0x18000e8f3  mov     eax, [rbp+460h+pjc.wZmin]
0x18000e8f9  mov     [rsp+560h+var_4EC], eax
0x18000e8fd  mov     eax, [rbp+460h+pjc.wZmax]
0x18000e903  mov     [rsp+560h+var_4E8], eax
0x18000e907  mov     eax, [rbp+460h+pjc.wNumButtons]
0x18000e90d  mov     [rsp+560h+var_4E4], eax
0x18000e911  mov     eax, [rbp+460h+pjc.wPeriodMin]
0x18000e917  mov     [rbp+460h+var_4E0], eax
0x18000e91a  mov     eax, [rbp+460h+pjc.wPeriodMax]
0x18000e920  mov     [rbp+460h+var_4DC], eax
0x18000e923  mov     eax, [rbp+460h+pjc.wRmin]
0x18000e929  mov     [rbp+460h+var_4D8], eax
0x18000e92c  mov     eax, [rbp+460h+pjc.wRmax]
0x18000e932  mov     [rbp+460h+var_4D4], eax
0x18000e935  mov     eax, [rbp+460h+pjc.wUmin]
0x18000e93b  mov     [rbp+460h+var_4D0], eax
0x18000e93e  mov     eax, [rbp+460h+pjc.wUmax]
0x18000e944  mov     [rbp+460h+var_4CC], eax
0x18000e947  mov     eax, [rbp+460h+pjc.wVmin]
0x18000e94d  mov     [rbp+460h+var_4C8], eax
0x18000e950  mov     eax, [rbp+460h+pjc.wVmax]
0x18000e956  mov     [rbp+460h+var_4C4], eax
0x18000e959  mov     eax, [rbp+460h+pjc.wCaps]
0x18000e95f  mov     [rbp+460h+var_4C0], eax
0x18000e962  mov     eax, [rbp+460h+pjc.wMaxAxes]
0x18000e968  mov     [rbp+460h+var_4BC], eax
0x18000e96b  mov     eax, [rbp+460h+pjc.wNumAxes]
0x18000e971  movdqu  [rbp+460h+var_38C], xmm0
0x18000e979  mov     [rbp+460h+var_4B8], eax
0x18000e97c  movups  xmm0, [rbp+460h+var_58]
0x18000e983  mov     eax, [rbp+460h+pjc.wMaxButtons]
0x18000e989  mov     [rbp+460h+var_4B4], eax
0x18000e98c  movdqu  [rbp+460h+var_37C], xmm1
0x18000e994  movdqu  [rbp+460h+var_36C], xmm0
0x18000e99c  mov     r8, rdi; Size
0x18000e99f  lea     rdx, [rsp+560h+Src]; Src
0x18000e9a4  mov     rcx, r14; void *
0x18000e9a7  call    memcpy_0
0x18000e9ac  mov     eax, r15d
0x18000e9af  mov     rcx, [rbp+460h+var_40]
0x18000e9b6  xor     rcx, rsp; StackCookie
0x18000e9b9  call    __security_check_cookie
0x18000e9be  add     rsp, 530h
0x18000e9c5  pop     r15
0x18000e9c7  pop     r14
0x18000e9c9  pop     r12
0x18000e9cb  pop     rdi
0x18000e9cc  pop     rsi
0x18000e9cd  pop     rbx
0x18000e9ce  pop     rbp
0x18000e9cf  retn
```
