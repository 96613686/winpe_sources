# TetheringSettingsGenerateDefaultPrivateConnectionSettingsInternal(void)

- ea: `0x18002a640`
- end: `0x18002ace2`
- name: `?TetheringSettingsGenerateDefaultPrivateConnectionSettingsInternal@@YAJXZ`
- size: `1698`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001c75c`
- `0x18002b2dc`

## callees

- `0x180002590`
- `0x180002c00`
- `0x180003088`
- `0x180009384`
- `0x180009448`
- `0x18000bf4c`
- `0x18000bf74`
- `0x180029b64`
- `0x18002a2a0`
- `0x18002a640`
- `0x18002c034`
- `0x18002d66c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002a76a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002a76a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002a749`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002a749`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002ac46`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002ac46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a714`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ac4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a714`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ac4e`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18002a6da`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18002a6da`
- `bcrypt!BCryptGenRandom` at `0x18002a88f`
- `bcrypt!BCryptGenRandom` at `0x18002a88f`

## string_xrefs

- `0x18002a73c`: `TetheringService.dll`

## pseudocode

```c
__int64 TetheringSettingsGenerateDefaultPrivateConnectionSettingsInternal(void)
{
  __int64 v0; // r14
  HMODULE v1; // rsi
  TetheringServiceTelemetry *v2; // rcx
  signed int LastError; // eax
  __int64 v4; // rdx
  __int64 v5; // r9
  HMODULE Library; // rax
  __int64 v7; // rcx
  WCHAR *v8; // r9
  __int64 v9; // rdx
  WCHAR *v10; // r8
  WCHAR *v11; // rcx
  unsigned int v12; // ebx
  __int64 v13; // rax
  int v14; // edi
  int v15; // eax
  TetheringServiceTelemetry *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r9
  __int64 v19; // rcx
  unsigned int v20; // edi
  __int64 v21; // rdx
  __int64 v22; // r8
  DWORD v23; // r10d
  __int64 i; // r9
  __int64 v25; // rax
  unsigned __int64 v26; // rcx
  int v27; // edi
  int Rand; // eax
  __int64 v29; // rax
  __int64 v30; // rdx
  int v31; // eax
  unsigned __int16 *v32; // rcx
  __int64 v33; // rdx
  char *v34; // rax
  char *v35; // rcx
  signed int v36; // eax
  _BYTE v38[4]; // [rsp+20h] [rbp-E0h] BYREF
  UCHAR pbBuffer[4]; // [rsp+24h] [rbp-DCh] BYREF
  DWORD nSize; // [rsp+28h] [rbp-D8h] BYREF
  int v41; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v42[33]; // [rsp+34h] [rbp-CCh] BYREF
  char v43; // [rsp+76h] [rbp-8Ah] BYREF
  int v44; // [rsp+F8h] [rbp-8h]
  int v45; // [rsp+FCh] [rbp-4h]
  unsigned __int16 v46[4]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v47; // [rsp+108h] [rbp+8h]
  __int16 v48; // [rsp+110h] [rbp+10h]
  WCHAR Buffer[40]; // [rsp+120h] [rbp+20h] BYREF
  WCHAR v50[40]; // [rsp+170h] [rbp+70h] BYREF

  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 141, &WPP_526e2569a9333f836f2472508a4e2fa1_Traceguids);
  }
  memset_0(Buffer, 0, 0x42u);
  *(_QWORD *)v46 = 0;
  v47 = 0;
  nSize = 33;
  memset_0(v50, 0, 0x42u);
  v0 = 2147483646;
  if ( GetComputerNameExW(ComputerNamePhysicalNetBIOS, Buffer, &nSize) && Buffer[0] )
  {
    v1 = 0;
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v2 = WPP_GLOBAL_Control;
      v4 = 145;
      v5 = (unsigned int)LastError;
      goto LABEL_23;
    }
    goto LABEL_24;
  }
  Library = LoadLibraryExW(L"TetheringService.dll", 0, 0x802u);
  v1 = Library;
  if ( Library )
  {
    if ( !LoadStringW(Library, 0x100Fu, v50, 33) )
    {
      v12 = -2147024894;
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          143,
          &WPP_526e2569a9333f836f2472508a4e2fa1_Traceguids,
          2147942402LL);
      }
      goto LABEL_95;
    }
    v7 = 2147483646;
    v8 = v50;
    v9 = 33;
    v10 = Buffer;
    do
    {
      if ( !v7 )
        break;
      if ( !*v8 )
        break;
      *v10++ = *v8++;
      --v7;
      --v9;
    }
    while ( v9 );
    v11 = v10 - 1;
    v12 = v9 == 0 ? 0x8007007A : 0;
    if ( v9 )
      v11 = v10;
    *v11 = 0;
    if ( v9 )
    {
LABEL_95:
      FreeLibrary(v1);
LABEL_101:
      v16 = WPP_GLOBAL_Control;
      goto LABEL_102;
    }
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v4 = 142;
      v5 = v12;
LABEL_23:
      WPP_SF_d(*((_QWORD *)v2 + 2), v4, &WPP_526e2569a9333f836f2472508a4e2fa1_Traceguids, v5);
      v2 = WPP_GLOBAL_Control;
    }
LABEL_24:
    v13 = -1;
    do
      ++v13;
    while ( Buffer[v13] );
    nSize = v13;
    v14 = 32 - v13;
    if ( (unsigned int)(32 - v13) > 1 )
    {
      v15 = StringCchCatW(Buffer, 0x1Cu, L" ");
      v12 = v15;
      if ( v15 < 0 )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v17 = 146;
LABEL_31:
          v18 = (unsigned int)v15;
LABEL_88:
          WPP_SF_d(*((_QWORD *)v16 + 2), v17, &WPP_526e2569a9333f836f2472508a4e2fa1_Traceguids, v18);
LABEL_89:
          v16 = WPP_GLOBAL_Control;
          goto LABEL_90;
        }
        goto LABEL_90;
      }
      v19 = nSize + 1;
      v20 = v14 - 1;
      ++nSize;
      if ( v20 > 4 )
        v20 = 4;
      BCryptGenRandom(0, (PUCHAR)&Buffer[v19], 2 * v20, 2u);
      v23 = nSize;
      for ( i = 0; (unsigned int)i < v20; Buffer[(unsigned int)v25] = Buffer[v25] % 0xAu + 48 )
      {
        v25 = (unsigned int)i + v23;
        i = (unsigned int)(i + 1);
        v22 = (unsigned int)v25;
        v21 = Buffer[v25] / 0xAu;
      }
      v26 = 2LL * (v20 + v23);
      if ( v26 >= 0x42 )
        _report_rangecheckfailure(v26, v21, v22, i);
      Buffer[v20 + v23] = 0;
      v2 = WPP_GLOBAL_Control;
    }
    if ( v2 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)v2 + 2), 134, &WPP_526e2569a9333f836f2472508a4e2fa1_Traceguids);
    *(_DWORD *)pbBuffer = 0;
    v27 = 0;
    v48 = 0;
    while ( 1 )
    {
      Rand = GetRand(pbBuffer);
      v12 = Rand;
      if ( Rand < 0 )
        break;
      v29 = (unsigned int)v27++;
      v46[v29] = *(_DWORD *)pbBuffer % 0xAu + 48;
      if ( v27 > 4 )
      {
        while ( 1 )
        {
          Rand = GetRand(pbBuffer);
          v12 = Rand;
          if ( Rand < 0 )
            break;
          WORD1(v47) = *(_DWORD *)pbBuffer % 0x1Au + 65;
          if ( *(_DWORD *)pbBuffer % 0x1Au != 8 )
          {
            do
            {
              Rand = GetRand(pbBuffer);
              v12 = Rand;
              if ( Rand < 0 )
              {
                v16 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
                  goto LABEL_90;
                if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  v30 = 137;
                  goto LABEL_65;
                }
                goto LABEL_67;
              }
              WORD2(v47) = *(_DWORD *)pbBuffer % 0x1Au + 97;
            }
            while ( *(_DWORD *)pbBuffer % 0x1Au == 11 );
            Rand = GetRand(pbBuffer);
            v12 = Rand;
            if ( Rand < 0 )
            {
              v16 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
                goto LABEL_90;
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v30 = 138;
                goto LABEL_65;
              }
              goto LABEL_67;
            }
            HIWORD(v47) = g_Symbols[*(unsigned int *)pbBuffer % 0x1AuLL];
            Rand = Randomize(v46, *(_DWORD *)pbBuffer / 0x1Au);
            v12 = Rand;
            if ( Rand >= 0 )
              goto LABEL_66;
            v16 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
            {
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                goto LABEL_67;
              v30 = 139;
              goto LABEL_65;
            }
            goto LABEL_90;
          }
        }
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
          goto LABEL_90;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v30 = 136;
          goto LABEL_65;
        }
        goto LABEL_67;
      }
    }
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
      goto LABEL_90;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v30 = 135;
LABEL_65:
      WPP_SF_d(*((_QWORD *)v16 + 2), v30, &WPP_526e2569a9333f836f2472508a4e2fa1_Traceguids, (unsigned int)Rand);
LABEL_66:
      v16 = WPP_GLOBAL_Control;
    }
LABEL_67:
    if ( v16 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 8) != 0 )
    {
      WPP_SF_d(*((_QWORD *)v16 + 2), 140, &WPP_526e2569a9333f836f2472508a4e2fa1_Traceguids, v12);
      v16 = WPP_GLOBAL_Control;
    }
    if ( (v12 & 0x80000000) != 0 )
    {
      if ( v16 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 1) != 0 )
      {
        v17 = 147;
        v18 = v12;
        goto LABEL_88;
      }
    }
    else
    {
      v38[0] = 0;
      memset_0(v42, 0, 0xC4u);
      v41 = 1;
      v44 = 3;
      v45 = 1;
      if ( (int)TetheringIsAuthSupportedInternal(2, v38) >= 0 )
      {
        v31 = v45;
        if ( v38[0] )
          v31 = 2;
        v45 = v31;
      }
      StringCchCopyW(v42, 0x21u, Buffer);
      v32 = v46;
      v33 = 9;
      v34 = &v43;
      do
      {
        if ( !v0 )
          break;
        if ( !*v32 )
          break;
        *(_WORD *)v34 = *v32++;
        v34 += 2;
        --v0;
        --v33;
      }
      while ( v33 );
      v35 = v34 - 2;
      if ( v33 )
        v35 = v34;
      *(_WORD *)v35 = 0;
      v15 = TetheringSettingsSaveSettingGlobalInternal(7, &v41, 208);
      v12 = v15;
      if ( v15 >= 0 )
        goto LABEL_89;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v17 = 148;
        goto LABEL_31;
      }
    }
LABEL_90:
    if ( v1 )
      goto LABEL_95;
LABEL_102:
    if ( v16 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)v16 + 2), 149, &WPP_526e2569a9333f836f2472508a4e2fa1_Traceguids, v12);
    return v12;
  }
  v36 = GetLastError();
  v12 = v36;
  if ( v36 > 0 )
    v12 = (unsigned __int16)v36 | 0x80070000;
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 144, &WPP_526e2569a9333f836f2472508a4e2fa1_Traceguids, v12);
      goto LABEL_101;
    }
    goto LABEL_102;
  }
  return v12;
}

```

## disassembly

```asm
0x18002a640  push    rbp
0x18002a642  push    rbx
0x18002a643  push    rsi
0x18002a644  push    rdi
0x18002a645  push    r12
0x18002a647  push    r13
0x18002a649  push    r14
0x18002a64b  push    r15
0x18002a64d  lea     rbp, [rsp-0D8h]
0x18002a655  sub     rsp, 1D8h
0x18002a65c  mov     rax, cs:__security_cookie
0x18002a663  xor     rax, rsp
0x18002a666  mov     [rbp+110h+var_50], rax
0x18002a66d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a674  lea     r13, WPP_GLOBAL_Control
0x18002a67b  cmp     rcx, r13
0x18002a67e  jz      short loc_18002A69B
0x18002a680  test    byte ptr [rcx+1Ch], 8
0x18002a684  jz      short loc_18002A69B
0x18002a686  mov     rcx, [rcx+10h]
0x18002a68a  lea     r8, WPP_526e2569a9333f836f2472508a4e2fa1_Traceguids
0x18002a691  mov     edx, 8Dh
0x18002a696  call    WPP_SF_
0x18002a69b  mov     ebx, 42h ; 'B'
0x18002a6a0  lea     rcx, [rbp+110h+Buffer]; void *
0x18002a6a4  mov     r8d, ebx; Size
0x18002a6a7  xor     edx, edx; Val
0x18002a6a9  call    memset_0
0x18002a6ae  xor     r15d, r15d
0x18002a6b1  lea     edi, [rbx-21h]
0x18002a6b4  mov     r8d, ebx; Size
0x18002a6b7  mov     qword ptr [rbp+110h+var_110], r15
0x18002a6bb  xor     edx, edx; Val
0x18002a6bd  mov     [rbp+110h+var_108], r15
0x18002a6c1  lea     rcx, [rbp+110h+var_A0]; void *
0x18002a6c5  mov     [rsp+210h+nSize], edi
0x18002a6c9  call    memset_0
0x18002a6ce  lea     r8, [rsp+210h+nSize]; nSize
0x18002a6d3  lea     rdx, [rbp+110h+Buffer]; lpBuffer
0x18002a6d7  lea     ecx, [rbx-3Eh]; NameType
0x18002a6da  call    cs:__imp_GetComputerNameExW
0x18002a6e0  lea     ebx, [rdi-1Fh]
0x18002a6e3  mov     r14d, 7FFFFFFEh
0x18002a6e9  lea     r12d, [r15+1]
0x18002a6ed  test    eax, eax
0x18002a6ef  jz      short loc_18002A73A
0x18002a6f1  cmp     [rbp+110h+Buffer], r15w
0x18002a6f6  jz      short loc_18002A73A
0x18002a6f8  mov     esi, r15d
0x18002a6fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a702  cmp     rcx, r13
0x18002a705  jz      loc_18002A7FC
0x18002a70b  test    [rcx+1Ch], bl
0x18002a70e  jz      loc_18002A7FC
0x18002a714  call    cs:__imp_GetLastError
0x18002a71a  test    eax, eax
0x18002a71c  jle     short loc_18002A726
0x18002a71e  movzx   eax, ax
0x18002a721  or      eax, 80070000h
0x18002a726  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a72d  mov     edx, 91h
0x18002a732  mov     r9d, eax
0x18002a735  jmp     loc_18002A7E5
0x18002a73a  xor     edx, edx; hFile
0x18002a73c  lea     rcx, LibFileName; "TetheringService.dll"
0x18002a743  mov     r8d, 802h; dwFlags
0x18002a749  call    cs:__imp_LoadLibraryExW
0x18002a74f  mov     rsi, rax
0x18002a752  test    rax, rax
0x18002a755  jz      loc_18002AC4E
0x18002a75b  mov     r9d, edi; cchBufferMax
0x18002a75e  lea     r8, [rbp+110h+var_A0]; lpBuffer
0x18002a762  mov     edx, 100Fh; uID
0x18002a767  mov     rcx, rax; hInstance
0x18002a76a  call    cs:__imp_LoadStringW
0x18002a770  test    eax, eax
0x18002a772  jz      loc_18002AC14
0x18002a778  mov     rcx, r14
0x18002a77b  lea     r9, [rbp+110h+var_A0]
0x18002a77f  mov     rdx, rdi
0x18002a782  lea     r8, [rbp+110h+Buffer]
0x18002a786  test    rcx, rcx
0x18002a789  jz      short loc_18002A7A6
0x18002a78b  movzx   eax, word ptr [r9]
0x18002a78f  test    ax, ax
0x18002a792  jz      short loc_18002A7A6
0x18002a794  mov     [r8], ax
0x18002a798  add     r9, rbx
0x18002a79b  add     r8, rbx
0x18002a79e  sub     rcx, r12
0x18002a7a1  sub     rdx, r12
0x18002a7a4  jnz     short loc_18002A786
0x18002a7a6  mov     rax, rdx
0x18002a7a9  lea     rcx, [r8-2]
0x18002a7ad  neg     rax
0x18002a7b0  sbb     ebx, ebx
0x18002a7b2  not     ebx
0x18002a7b4  and     ebx, 8007007Ah
0x18002a7ba  test    rdx, rdx
0x18002a7bd  cmovnz  rcx, r8
0x18002a7c1  mov     [rcx], r15w
0x18002a7c5  jnz     loc_18002AC43
0x18002a7cb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a7d2  cmp     rcx, r13
0x18002a7d5  jz      short loc_18002A7FC
0x18002a7d7  test    [rcx+1Ch], r12b
0x18002a7db  jz      short loc_18002A7FC
0x18002a7dd  mov     edx, 8Eh
0x18002a7e2  mov     r9d, ebx
0x18002a7e5  mov     rcx, [rcx+10h]
0x18002a7e9  lea     r8, WPP_526e2569a9333f836f2472508a4e2fa1_Traceguids
0x18002a7f0  call    WPP_SF_d
0x18002a7f5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a7fc  lea     rdx, [rbp+110h+Buffer]
0x18002a800  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002a804  inc     rax
0x18002a807  cmp     [rdx+rax*2], r15w
0x18002a80c  jnz     short loc_18002A804
0x18002a80e  mov     edi, 20h ; ' '
0x18002a813  mov     [rsp+210h+nSize], eax
0x18002a817  sub     edi, eax
0x18002a819  cmp     edi, r12d
0x18002a81c  jbe     loc_18002A8EE
0x18002a822  lea     r8, asc_1800380B0; " "
0x18002a829  mov     edx, 1Ch; unsigned __int64
0x18002a82e  lea     rcx, [rbp+110h+Buffer]; unsigned __int16 *
0x18002a832  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002a837  mov     ebx, eax
0x18002a839  test    eax, eax
0x18002a83b  jns     short loc_18002A864
0x18002a83d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a844  cmp     rcx, r13
0x18002a847  jz      loc_18002AC09
0x18002a84d  test    [rcx+1Ch], r12b
0x18002a851  jz      loc_18002AC09
0x18002a857  mov     edx, 92h
0x18002a85c  mov     r9d, eax
0x18002a85f  jmp     loc_18002ABF2
0x18002a864  mov     eax, [rsp+210h+nSize]
0x18002a868  lea     rdx, [rbp+110h+Buffer]
0x18002a86c  add     eax, r12d
0x18002a86f  mov     ecx, eax
0x18002a871  dec     edi
0x18002a873  mov     [rsp+210h+nSize], eax
0x18002a877  mov     eax, 4
0x18002a87c  cmp     edi, eax
0x18002a87e  cmova   edi, eax
0x18002a881  lea     rdx, [rdx+rcx*2]; pbBuffer
0x18002a885  xor     ecx, ecx; hAlgorithm
0x18002a887  lea     r9d, [rax-2]; dwFlags
0x18002a88b  lea     r8d, [rdi+rdi]; cbBuffer
0x18002a88f  call    cs:__imp_BCryptGenRandom
0x18002a895  mov     r10d, [rsp+210h+nSize]
0x18002a89a  mov     r9d, r15d
0x18002a89d  test    edi, edi
0x18002a89f  jz      short loc_18002A8D0
0x18002a8a1  lea     eax, [r9+r10]
0x18002a8a5  add     r9d, r12d
0x18002a8a8  movzx   ecx, [rbp+rax*2+110h+Buffer]
0x18002a8ad  mov     r8d, eax
0x18002a8b0  mov     eax, 0CCCCCCCDh
0x18002a8b5  mul     ecx
0x18002a8b7  shr     edx, 3
0x18002a8ba  lea     eax, [rdx+rdx*4]
0x18002a8bd  add     eax, eax
0x18002a8bf  sub     ecx, eax
0x18002a8c1  add     cx, 30h ; '0'
0x18002a8c5  mov     [rbp+r8*2+110h+Buffer], cx
0x18002a8cb  cmp     r9d, edi
0x18002a8ce  jb      short loc_18002A8A1
0x18002a8d0  lea     ecx, [rdi+r10]
0x18002a8d4  add     rcx, rcx
0x18002a8d7  cmp     rcx, 42h ; 'B'
0x18002a8db  jnb     loc_18002ACDC
0x18002a8e1  mov     [rbp+rcx+110h+Buffer], r15w
0x18002a8e7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a8ee  cmp     rcx, r13
0x18002a8f1  jz      short loc_18002A90E
0x18002a8f3  test    byte ptr [rcx+1Ch], 8
0x18002a8f7  jz      short loc_18002A90E
0x18002a8f9  mov     rcx, [rcx+10h]
0x18002a8fd  lea     r8, WPP_526e2569a9333f836f2472508a4e2fa1_Traceguids
0x18002a904  mov     edx, 86h
0x18002a909  call    WPP_SF_
0x18002a90e  mov     dword ptr [rsp+210h+pbBuffer], r15d
0x18002a913  mov     edi, r15d
0x18002a916  mov     [rbp+110h+var_100], r15w
0x18002a91b  lea     rcx, [rsp+210h+pbBuffer]; pbBuffer
0x18002a920  call    ?GetRand@@YAJPEAI@Z; GetRand(uint *)
0x18002a925  mov     ebx, eax
0x18002a927  test    eax, eax
0x18002a929  js      loc_18002AAA6
0x18002a92f  mov     ecx, dword ptr [rsp+210h+pbBuffer]
0x18002a933  mov     eax, 0CCCCCCCDh
0x18002a938  mul     ecx
0x18002a93a  shr     edx, 3
0x18002a93d  movzx   eax, dx
0x18002a940  shl     ax, 2
0x18002a944  add     dx, ax
0x18002a947  mov     eax, edi
0x18002a949  add     dx, dx
0x18002a94c  add     edi, r12d
0x18002a94f  sub     cx, dx
0x18002a952  add     cx, 30h ; '0'
0x18002a956  mov     [rbp+rax*2+110h+var_110], cx
0x18002a95b  cmp     edi, 4
0x18002a95e  jle     short loc_18002A91B
0x18002a960  mov     edi, 4EC4EC4Fh
0x18002a965  lea     rcx, [rsp+210h+pbBuffer]; pbBuffer
0x18002a96a  call    ?GetRand@@YAJPEAI@Z; GetRand(uint *)
0x18002a96f  mov     ebx, eax
0x18002a971  test    eax, eax
0x18002a973  js      loc_18002AA89
0x18002a979  mov     r8d, dword ptr [rsp+210h+pbBuffer]
0x18002a97e  mov     eax, edi
0x18002a980  mul     r8d
0x18002a983  shr     edx, 3
0x18002a986  movzx   eax, dx
0x18002a989  imul    ecx, eax, 1Ah
0x18002a98c  sub     r8w, cx
0x18002a990  add     r8w, 41h ; 'A'
0x18002a995  mov     word ptr [rbp+110h+var_108+2], r8w
0x18002a99a  cmp     r8w, 49h ; 'I'
0x18002a99f  jz      short loc_18002A965
0x18002a9a1  lea     rcx, [rsp+210h+pbBuffer]; pbBuffer
0x18002a9a6  call    ?GetRand@@YAJPEAI@Z; GetRand(uint *)
0x18002a9ab  mov     ebx, eax
0x18002a9ad  test    eax, eax
0x18002a9af  js      loc_18002AA6C
0x18002a9b5  mov     r8d, dword ptr [rsp+210h+pbBuffer]
0x18002a9ba  mov     eax, edi
0x18002a9bc  mul     r8d
0x18002a9bf  shr     edx, 3
0x18002a9c2  movzx   eax, dx
0x18002a9c5  imul    ecx, eax, 1Ah
0x18002a9c8  sub     r8w, cx
0x18002a9cc  add     r8w, 61h ; 'a'
0x18002a9d1  mov     word ptr [rbp+110h+var_108+4], r8w
0x18002a9d6  cmp     r8w, 6Ch ; 'l'
0x18002a9db  jz      short loc_18002A9A1
0x18002a9dd  lea     rcx, [rsp+210h+pbBuffer]; pbBuffer
0x18002a9e2  call    ?GetRand@@YAJPEAI@Z; GetRand(uint *)
0x18002a9e7  mov     ebx, eax
0x18002a9e9  test    eax, eax
0x18002a9eb  jns     short loc_18002AA11
0x18002a9ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a9f4  cmp     rcx, r13
0x18002a9f7  jz      loc_18002AC09
0x18002a9fd  test    [rcx+1Ch], r12b
0x18002aa01  jz      loc_18002AADB
0x18002aa07  mov     edx, 8Ah
0x18002aa0c  jmp     loc_18002AAC1
0x18002aa11  mov     ecx, dword ptr [rsp+210h+pbBuffer]
0x18002aa15  mov     rax, 4EC4EC4EC4EC4EC5h
0x18002aa1f  mul     rcx
0x18002aa22  shr     rdx, 3; int
0x18002aa26  imul    rax, rdx, 1Ah
0x18002aa2a  sub     rcx, rax
0x18002aa2d  lea     rax, ?g_Symbols@@3PAGA; "!@#$%^&*()-+=[]{}|\\<>?/:;,"
0x18002aa34  movzx   eax, word ptr [rax+rcx*2]
0x18002aa38  lea     rcx, [rbp+110h+var_110]; unsigned __int16 *
0x18002aa3c  mov     word ptr [rbp+110h+var_108+6], ax
0x18002aa40  call    ?Randomize@@YAJPEAGH@Z; Randomize(ushort *,int)
0x18002aa45  mov     ebx, eax
0x18002aa47  test    eax, eax
0x18002aa49  jns     loc_18002AAD4
0x18002aa4f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aa56  cmp     rcx, r13
0x18002aa59  jz      loc_18002AC09
0x18002aa5f  test    [rcx+1Ch], r12b
0x18002aa63  jz      short loc_18002AADB
0x18002aa65  mov     edx, 8Bh
0x18002aa6a  jmp     short loc_18002AAC1
0x18002aa6c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aa73  cmp     rcx, r13
0x18002aa76  jz      loc_18002AC09
0x18002aa7c  test    [rcx+1Ch], r12b
0x18002aa80  jz      short loc_18002AADB
0x18002aa82  mov     edx, 89h
0x18002aa87  jmp     short loc_18002AAC1
0x18002aa89  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aa90  cmp     rcx, r13
0x18002aa93  jz      loc_18002AC09
0x18002aa99  test    [rcx+1Ch], r12b
0x18002aa9d  jz      short loc_18002AADB
0x18002aa9f  mov     edx, 88h
0x18002aaa4  jmp     short loc_18002AAC1
0x18002aaa6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aaad  cmp     rcx, r13
0x18002aab0  jz      loc_18002AC09
0x18002aab6  test    [rcx+1Ch], r12b
0x18002aaba  jz      short loc_18002AADB
0x18002aabc  mov     edx, 87h
0x18002aac1  mov     rcx, [rcx+10h]
0x18002aac5  lea     r8, WPP_526e2569a9333f836f2472508a4e2fa1_Traceguids
0x18002aacc  mov     r9d, eax
0x18002aacf  call    WPP_SF_d
0x18002aad4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aadb  cmp     rcx, r13
0x18002aade  jz      short loc_18002AB05
  ... truncated ...
```
