# SsUpdateShares

- ea: `0x180003b00`
- end: `0x180003f4c`
- name: `SsUpdateShares`
- size: `1100`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1800036a0`

## callees

- `0x180003b00`
- `0x180003f60`
- `0x18001deb0`
- `0x180026b40`
- `0x180026c3c`
- `0x1800435f8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003d58`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003dd9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003e1a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003d58`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003dd9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003e1a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003e51`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003eb1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003f04`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003e51`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003eb1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003f04`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180003b68`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180003ba1`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180003c4f`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180003c88`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180003e46`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180003ef9`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180003b68`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180003ba1`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180003c4f`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180003c88`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180003e46`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180003ef9`
- `ntdll!RtlQueryRegistryValuesEx` at `0x180003ea6`
- `ntdll!RtlQueryRegistryValuesEx` at `0x180003ea6`

## pseudocode

```c
_QWORD *SsUpdateShares()
{
  int v0; // r15d
  WCHAR v1; // bx
  unsigned int i; // esi
  UINT DriveTypeW; // edi
  WCHAR v4; // r12
  int v5; // ebx
  unsigned int v6; // edi
  UINT v7; // esi
  int v8; // eax
  int v9; // edx
  int v10; // r8d
  int v11; // r9d
  _QWORD *result; // rax
  void *v13; // rbx
  __int64 v14; // rax
  bool v15; // zf
  size_t v16; // rdi
  WCHAR *v17; // rax
  WCHAR *v18; // r14
  __int64 v19; // rax
  size_t v20; // rsi
  WCHAR *v21; // rax
  WCHAR *v22; // r14
  int v23; // edi
  int v24; // [rsp+50h] [rbp-59h] BYREF
  int v25; // [rsp+54h] [rbp-55h] BYREF
  __int128 *v26; // [rsp+58h] [rbp-51h] BYREF
  __int128 v27; // [rsp+60h] [rbp-49h] BYREF
  __int128 v28; // [rsp+70h] [rbp-39h]
  __int128 v29; // [rsp+80h] [rbp-29h]
  __int64 v30; // [rsp+90h] [rbp-19h]
  WCHAR RootPathName; // [rsp+98h] [rbp-11h] BYREF
  int v32; // [rsp+9Ah] [rbp-Fh]
  __int16 v33; // [rsp+9Eh] [rbp-Bh]
  WCHAR v34; // [rsp+A0h] [rbp-9h] BYREF
  int v35; // [rsp+A2h] [rbp-7h]
  __int16 v36; // [rsp+A6h] [rbp-3h]
  _DWORD v37[2]; // [rsp+A8h] [rbp-1h] BYREF

  v32 = 6029370;
  v25 = 0;
  v24 = 0;
  v0 = 0;
  v33 = 0;
  v1 = 65;
  v37[0] = 65;
  for ( i = 0x80000000; ; i >>= 1 )
  {
    RootPathName = v1;
    DriveTypeW = GetDriveTypeW(&RootPathName);
    if ( DriveTypeW == 1 )
    {
      if ( RootPathName && (_WORD)v32 == 58 )
      {
        v34 = RootPathName;
        v35 = 6029370;
        v36 = 0;
        DriveTypeW = GetDriveTypeW(&v34);
      }
      else
      {
        v14 = -1;
        do
          v15 = *(&RootPathName + ++v14) == 0;
        while ( !v15 );
        v16 = v14;
        v17 = (WCHAR *)LocalAlloc(0x40u, 2 * v14 + 4);
        v18 = v17;
        if ( !v17 )
          goto LABEL_8;
        memcpy_0(v17, &RootPathName, v16 * 2);
        *(_DWORD *)&v18[v16] = 92;
        DriveTypeW = GetDriveTypeW(v18);
        LocalFree(v18);
      }
    }
    if ( DriveTypeW - 2 <= 1 )
      v0 |= i;
LABEL_8:
    if ( ++v1 > 0x5Au )
      break;
  }
  v4 = v37[0];
  v5 = v0 & ~AlreadyAddedBitMask;
  DiskConfiguration = v0;
  v24 = v5;
  v6 = 0x80000000;
  while ( v5 )
  {
    if ( (v6 & v5) == 0 )
      goto LABEL_13;
    if ( dword_18005CCF8 == 1 )
    {
      if ( !dword_18005CD64 )
        goto LABEL_25;
    }
    else if ( !dword_18005CD68 )
    {
      goto LABEL_25;
    }
    v26 = 0;
    RootPathName = v4;
    v30 = 0;
    v27 = 0;
    v32 = 6029370;
    v28 = 0;
    v33 = 0;
    v29 = 0;
    v7 = GetDriveTypeW(&RootPathName);
    if ( v7 != 1 )
      goto LABEL_21;
    if ( RootPathName && (_WORD)v32 == 58 )
    {
      v34 = RootPathName;
      v35 = 6029370;
      v36 = 0;
      v7 = GetDriveTypeW(&v34);
      goto LABEL_21;
    }
    v19 = -1;
    do
      v15 = *(&RootPathName + ++v19) == 0;
    while ( !v15 );
    v20 = v19;
    v21 = (WCHAR *)LocalAlloc(0x40u, 2 * v19 + 4);
    v22 = v21;
    if ( v21 )
    {
      memcpy_0(v21, &RootPathName, v20 * 2);
      *(_DWORD *)&v22[v20] = 92;
      v7 = GetDriveTypeW(v22);
      LocalFree(v22);
LABEL_21:
      if ( v7 == 3 )
      {
        *(_QWORD *)&v27 = v37;
        *(_QWORD *)&v28 = *(_QWORD *)&SsDiskAdminShareRemark;
        *((_QWORD *)&v29 + 1) = &RootPathName;
        v26 = &v27;
        LOWORD(v37[0]) = v4;
        *(_DWORD *)((char *)v37 + 2) = 36;
        DWORD2(v27) = 0x80000000;
        *((_QWORD *)&v28 + 1) = 0xFFFFFFFF00000001uLL;
        LODWORD(v29) = 0;
        v30 = 0;
        v8 = I_NetrShareAdd(0, 2, (wint_t *)&v26, 0, 1, 1, 1u, 0, 0, 0);
        if ( v8 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) )
          {
            WPP_SF_sSD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, v10, v11, v27, v8);
          }
        }
        else
        {
          AlreadyAddedBitMask |= v6;
        }
      }
    }
LABEL_25:
    v5 &= ~v6;
LABEL_13:
    if ( ++v4 > 0x5Au )
      break;
    v6 >>= 1;
  }
  result = LocalAlloc(0x40u, 0x70u);
  v13 = result;
  if ( !result )
    goto LABEL_28;
  *((_DWORD *)result + 2) = 16;
  *result = UpdateStickyShare;
  result[2] = 0;
  result[3] = &v24;
  *((_DWORD *)result + 8) = 0;
  result[5] = 0;
  *((_DWORD *)result + 12) = 0;
  result[7] = 0;
  *((_DWORD *)result + 16) = 0;
  result[9] = 0;
  v23 = RtlQueryRegistryValuesEx(0, &word_18005DDBC, result, &v25, 0);
  result = LocalFree(v13);
  if ( v23 < 0 )
  {
LABEL_28:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
        return (_QWORD *)WPP_SF_sL(*((_QWORD *)WPP_GLOBAL_Control + 2));
    }
  }
  return result;
}

```

## disassembly

```asm
0x180003b00  push    rbp
0x180003b02  push    rbx
0x180003b03  push    rsi
0x180003b04  push    rdi
0x180003b05  push    r12
0x180003b07  push    r13
0x180003b09  push    r14
0x180003b0b  push    r15
0x180003b0d  lea     rbp, [rsp-1Fh]
0x180003b12  sub     rsp, 0C8h
0x180003b19  mov     rax, cs:__security_cookie
0x180003b20  xor     rax, rsp
0x180003b23  mov     [rbp+57h+var_50], rax
0x180003b27  xor     r13d, r13d
0x180003b2a  mov     [rbp+57h+var_66], 5C003Ah
0x180003b31  mov     r12d, 41h ; 'A'
0x180003b37  mov     [rbp+57h+var_AC], r13d
0x180003b3b  mov     [rbp+57h+var_B0], r13d
0x180003b3f  mov     r15d, r13d
0x180003b42  mov     [rbp+57h+var_62], r13w
0x180003b47  movzx   ebx, r12w
0x180003b4b  mov     dword ptr [rbp+57h+var_58], r12d
0x180003b4f  mov     r14d, 5Ch ; '\'
0x180003b55  mov     esi, 80000000h
0x180003b5a  nop     word ptr [rax+rax+00h]
0x180003b60  lea     rcx, [rbp+57h+RootPathName]; lpRootPathName
0x180003b64  mov     [rbp+57h+RootPathName], bx
0x180003b68  call    cs:__imp_GetDriveTypeW
0x180003b6e  mov     edi, eax
0x180003b70  cmp     eax, 1
0x180003b73  jnz     short loc_180003BA9
0x180003b75  movzx   eax, [rbp+57h+RootPathName]
0x180003b79  test    ax, ax
0x180003b7c  jz      loc_180003DB2
0x180003b82  cmp     word ptr [rbp+57h+var_66], 3Ah ; ':'
0x180003b87  jnz     loc_180003DB2
0x180003b8d  lea     rcx, [rbp+57h+var_60]; lpRootPathName
0x180003b91  mov     [rbp+57h+var_60], ax
0x180003b95  mov     [rbp+57h+var_5E], 5C003Ah
0x180003b9c  mov     [rbp+57h+var_5A], r13w
0x180003ba1  call    cs:__imp_GetDriveTypeW
0x180003ba7  mov     edi, eax
0x180003ba9  lea     eax, [rdi-2]
0x180003bac  cmp     eax, 1
0x180003baf  jbe     short loc_180003BBE
0x180003bb1  inc     bx
0x180003bb4  cmp     bx, 5Ah ; 'Z'
0x180003bb8  ja      short loc_180003BC3
0x180003bba  shr     esi, 1
0x180003bbc  jmp     short loc_180003B60
0x180003bbe  or      r15d, esi
0x180003bc1  jmp     short loc_180003BB1
0x180003bc3  mov     ebx, cs:AlreadyAddedBitMask
0x180003bc9  lea     rsi, WPP_GLOBAL_Control
0x180003bd0  mov     r12d, dword ptr [rbp+57h+var_58]
0x180003bd4  not     ebx
0x180003bd6  and     ebx, r15d
0x180003bd9  mov     cs:DiskConfiguration, r15d
0x180003be0  mov     [rbp+57h+var_B0], ebx
0x180003be3  mov     edi, 80000000h
0x180003be8  test    ebx, ebx
0x180003bea  jz      loc_180003D49
0x180003bf0  test    ebx, edi
0x180003bf2  jnz     short loc_180003C07
0x180003bf4  inc     r12w
0x180003bf8  cmp     r12w, 5Ah ; 'Z'
0x180003bfd  ja      loc_180003D49
0x180003c03  shr     edi, 1
0x180003c05  jmp     short loc_180003BE8
0x180003c07  cmp     cs:dword_18005CCF8, 1
0x180003c0e  jnz     loc_180003F15
0x180003c14  cmp     cs:dword_18005CD64, r13d
0x180003c1b  jz      loc_180003D3E
0x180003c21  xorps   xmm0, xmm0
0x180003c24  mov     [rbp+57h+var_A8], r13
0x180003c28  xor     eax, eax
0x180003c2a  mov     [rbp+57h+RootPathName], r12w
0x180003c2f  lea     rcx, [rbp+57h+RootPathName]; lpRootPathName
0x180003c33  mov     [rbp+57h+var_70], rax
0x180003c37  movups  [rbp+57h+var_A0], xmm0
0x180003c3b  mov     [rbp+57h+var_66], 5C003Ah
0x180003c42  movups  [rbp+57h+var_90], xmm0
0x180003c46  mov     [rbp+57h+var_62], r13w
0x180003c4b  movups  [rbp+57h+var_80], xmm0
0x180003c4f  call    cs:__imp_GetDriveTypeW
0x180003c55  mov     esi, eax
0x180003c57  cmp     eax, 1
0x180003c5a  jnz     short loc_180003C90
0x180003c5c  movzx   eax, [rbp+57h+RootPathName]
0x180003c60  test    ax, ax
0x180003c63  jz      loc_180003DF6
0x180003c69  cmp     word ptr [rbp+57h+var_66], 3Ah ; ':'
0x180003c6e  jnz     loc_180003DF6
0x180003c74  lea     rcx, [rbp+57h+var_60]; lpRootPathName
0x180003c78  mov     [rbp+57h+var_60], ax
0x180003c7c  mov     [rbp+57h+var_5E], 5C003Ah
0x180003c83  mov     [rbp+57h+var_5A], r13w
0x180003c88  call    cs:__imp_GetDriveTypeW
0x180003c8e  mov     esi, eax
0x180003c90  cmp     esi, 3
0x180003c93  jnz     loc_180003DA9
0x180003c99  mov     [rsp+100h+var_B8], r13
0x180003c9e  lea     rax, [rbp+57h+var_58]
0x180003ca2  mov     qword ptr [rbp+57h+var_A0], rax
0x180003ca6  lea     r8, [rbp+57h+var_A8]
0x180003caa  mov     rax, cs:SsDiskAdminShareRemark
0x180003cb1  xor     r9d, r9d
0x180003cb4  mov     [rsp+100h+var_C0], r13b
0x180003cb9  mov     edx, 2
0x180003cbe  mov     qword ptr [rbp+57h+var_90], rax
0x180003cc2  xor     ecx, ecx
0x180003cc4  mov     [rsp+100h+var_C8], r13b
0x180003cc9  lea     rax, [rbp+57h+RootPathName]
0x180003ccd  mov     qword ptr [rbp+57h+var_80+8], rax
0x180003cd1  lea     rax, [rbp+57h+var_A0]
0x180003cd5  mov     [rsp+100h+var_D0], 1
0x180003cda  mov     byte ptr [rsp+100h+var_D8], 1
0x180003cdf  mov     [rbp+57h+var_A8], rax
0x180003ce3  mov     word ptr [rbp+57h+var_58], r12w
0x180003ce8  mov     dword ptr [rbp+57h+var_58+2], 24h ; '$'
0x180003cef  mov     dword ptr [rbp+57h+var_A0+8], 80000000h
0x180003cf6  mov     dword ptr [rbp+57h+var_90+8], 1
0x180003cfd  mov     dword ptr [rbp+57h+var_90+0Ch], 0FFFFFFFFh
0x180003d04  mov     dword ptr [rbp+57h+var_80], r13d
0x180003d08  mov     [rbp+57h+var_70], r13
0x180003d0c  mov     byte ptr [rsp+100h+var_E0], 1
0x180003d11  call    I_NetrShareAdd
0x180003d16  test    eax, eax
0x180003d18  jz      loc_180003DA3
0x180003d1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003d25  lea     rsi, WPP_GLOBAL_Control
0x180003d2c  cmp     rcx, rsi
0x180003d2f  jz      short loc_180003D3E
0x180003d31  test    dword ptr [rcx+1Ch], 100h
0x180003d38  jnz     loc_180003F27
0x180003d3e  mov     eax, edi
0x180003d40  not     eax
0x180003d42  and     ebx, eax
0x180003d44  jmp     loc_180003BF4
0x180003d49  mov     edx, 70h ; 'p'; uBytes
0x180003d4e  mov     ecx, 40h ; '@'; uFlags
0x180003d53  mov     edi, 0C000009Ah
0x180003d58  call    cs:__imp_LocalAlloc
0x180003d5e  mov     rbx, rax
0x180003d61  test    rax, rax
0x180003d64  jnz     loc_180003E5C
0x180003d6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180003d71  cmp     rcx, rsi
0x180003d74  jz      loc_180003EBF
0x180003d7a  test    dword ptr [rcx+1Ch], 100h
0x180003d81  jz      loc_180003EBF
0x180003d87  cmp     byte ptr [rcx+19h], 1
0x180003d8b  jb      loc_180003EBF
0x180003d91  mov     rcx, [rcx+10h]
0x180003d95  mov     dword ptr [rsp+100h+var_E0], edi
0x180003d99  call    WPP_SF_sL
0x180003d9e  jmp     loc_180003EBF
0x180003da3  or      cs:AlreadyAddedBitMask, edi
0x180003da9  lea     rsi, WPP_GLOBAL_Control
0x180003db0  jmp     short loc_180003D3E
0x180003db2  lea     rcx, [rbp+57h+RootPathName]
0x180003db6  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180003dbd  nop     dword ptr [rax]
0x180003dc0  cmp     [rcx+rax*2+2], r13w
0x180003dc6  lea     rax, [rax+1]
0x180003dca  jnz     short loc_180003DC0
0x180003dcc  lea     rdi, [rax+rax]
0x180003dd0  mov     ecx, 40h ; '@'; uFlags
0x180003dd5  lea     rdx, [rdi+4]; uBytes
0x180003dd9  call    cs:__imp_LocalAlloc
0x180003ddf  mov     r14, rax
0x180003de2  test    rax, rax
0x180003de5  jnz     loc_180003EDF
0x180003deb  mov     r14d, 5Ch ; '\'
0x180003df1  jmp     loc_180003BB1
0x180003df6  lea     rcx, [rbp+57h+RootPathName]
0x180003dfa  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180003e01  cmp     [rcx+rax*2+2], r13w
0x180003e07  lea     rax, [rax+1]
0x180003e0b  jnz     short loc_180003E01
0x180003e0d  lea     rsi, [rax+rax]
0x180003e11  mov     ecx, 40h ; '@'; uFlags
0x180003e16  lea     rdx, [rsi+4]; uBytes
0x180003e1a  call    cs:__imp_LocalAlloc
0x180003e20  mov     r14, rax
0x180003e23  test    rax, rax
0x180003e26  jz      loc_180003DA9
0x180003e2c  mov     r8, rsi; Size
0x180003e2f  lea     rdx, [rbp+57h+RootPathName]; Src
0x180003e33  mov     rcx, rax; void *
0x180003e36  call    memcpy_0
0x180003e3b  mov     rcx, r14; lpRootPathName
0x180003e3e  mov     dword ptr [rsi+r14], 5Ch ; '\'
0x180003e46  call    cs:__imp_GetDriveTypeW
0x180003e4c  mov     rcx, r14; hMem
0x180003e4f  mov     esi, eax
0x180003e51  call    cs:__imp_LocalFree
0x180003e57  jmp     loc_180003C90
0x180003e5c  lea     rax, UpdateStickyShare
0x180003e63  mov     dword ptr [rbx+8], 10h
0x180003e6a  mov     [rbx], rax
0x180003e6d  lea     r9, [rbp+57h+var_AC]
0x180003e71  lea     rax, [rbp+57h+var_B0]
0x180003e75  mov     [rbx+10h], r13
0x180003e79  mov     r8, rbx
0x180003e7c  mov     [rbx+18h], rax
0x180003e80  lea     rdx, word_18005DDBC
0x180003e87  mov     [rbx+20h], r13d
0x180003e8b  xor     ecx, ecx
0x180003e8d  mov     [rbx+28h], r13
0x180003e91  mov     [rbx+30h], r13d
0x180003e95  mov     [rbx+38h], r13
0x180003e99  mov     [rbx+40h], r13d
0x180003e9d  mov     [rbx+48h], r13
0x180003ea1  mov     [rsp+100h+var_E0], r13
0x180003ea6  call    cs:__imp_RtlQueryRegistryValuesEx
0x180003eac  mov     rcx, rbx; hMem
0x180003eaf  mov     edi, eax
0x180003eb1  call    cs:__imp_LocalFree
0x180003eb7  test    edi, edi
0x180003eb9  js      loc_180003D6A
0x180003ebf  mov     rcx, [rbp+57h+var_50]
0x180003ec3  xor     rcx, rsp; StackCookie
0x180003ec6  call    __security_check_cookie
0x180003ecb  add     rsp, 0C8h
0x180003ed2  pop     r15
0x180003ed4  pop     r14
0x180003ed6  pop     r13
0x180003ed8  pop     r12
0x180003eda  pop     rdi
0x180003edb  pop     rsi
0x180003edc  pop     rbx
0x180003edd  pop     rbp
0x180003ede  retn
0x180003edf  mov     r8, rdi; Size
0x180003ee2  lea     rdx, [rbp+57h+RootPathName]; Src
0x180003ee6  mov     rcx, r14; void *
0x180003ee9  call    memcpy_0
0x180003eee  mov     rcx, r14; lpRootPathName
0x180003ef1  mov     dword ptr [rdi+r14], 5Ch ; '\'
0x180003ef9  call    cs:__imp_GetDriveTypeW
0x180003eff  mov     rcx, r14; hMem
0x180003f02  mov     edi, eax
0x180003f04  call    cs:__imp_LocalFree
0x180003f0a  mov     r14d, 5Ch ; '\'
0x180003f10  jmp     loc_180003BA9
0x180003f15  cmp     cs:dword_18005CD68, r13d
0x180003f1c  jz      loc_180003D3E
0x180003f22  jmp     loc_180003C21
0x180003f27  cmp     byte ptr [rcx+19h], 1
0x180003f2b  jb      loc_180003D3E
0x180003f31  mov     rcx, [rcx+10h]
0x180003f35  mov     [rsp+100h+var_D8], eax
0x180003f39  mov     rax, qword ptr [rbp+57h+var_A0]
0x180003f3d  mov     [rsp+100h+var_E0], rax
0x180003f42  call    WPP_SF_sSD
0x180003f47  jmp     loc_180003D3E
```
