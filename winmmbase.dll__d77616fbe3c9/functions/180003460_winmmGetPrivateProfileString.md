# winmmGetPrivateProfileString

- ea: `0x180003460`
- end: `0x1800039bc`
- name: `winmmGetPrivateProfileString`
- size: `1372`
- prototype: `__int64 __fastcall(PCNZWCH lpString1, LPCWSTR lpValue, _WORD *pvData, unsigned int)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180001f30`
- `0x18000296c`
- `0x180002eb0`

## callees

- `0x180003460`
- `0x1800039d0`
- `0x18000f52c`
- `0x18000f5d8`
- `0x1800106c0`
- `0x18001102a`
- `0x180012d08`
- `0x180012d70`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x1800037c8`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x1800037c8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000358f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000380e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000358f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000380e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800035a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003821`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800035a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003821`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180003697`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180003697`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800036dd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800036dd`

## pseudocode

```c
__int64 __fastcall winmmGetPrivateProfileString(PCNZWCH lpString1, LPCWSTR lpValue, _WORD *pvData, unsigned int a4)
{
  unsigned __int64 v5; // r15
  __int64 v8; // r10
  const wchar_t *v9; // rdx
  __int64 v10; // r11
  unsigned __int16 *v11; // r9
  __int64 v12; // rcx
  __int64 v13; // r8
  unsigned __int16 *v14; // rax
  int v15; // esi
  unsigned __int16 *i; // rax
  HANDLE FileW; // rax
  unsigned __int64 v18; // rdx
  __int64 v19; // r10
  LPCWSTR v20; // rcx
  _WORD *v21; // rax
  __int64 v22; // rdi
  PCNZWCH v24; // rdx
  WCHAR *v25; // rcx
  WCHAR *v26; // rax
  __int64 v27; // rdi
  HKEY v28; // rcx
  HKEY v29; // rax
  unsigned __int16 *v30; // rdx
  __int64 v31; // rcx
  HANDLE v32; // rax
  unsigned __int64 v33; // rdx
  __int64 v34; // r10
  LPCWSTR v35; // rcx
  _WORD *v36; // rax
  __int64 v37; // rdi
  DWORD pcbData[2]; // [rsp+40h] [rbp-478h] BYREF
  unsigned __int16 v39[260]; // [rsp+50h] [rbp-468h] BYREF
  WCHAR Buffer[264]; // [rsp+260h] [rbp-258h] BYREF

  v5 = a4;
  memset_0(Buffer, 0, 0x208u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      (unsigned int)WPP_b29debb2a69d34804e2e00aace071994_Traceguids,
      (_DWORD)lpString1,
      (__int64)lpValue);
  }
  if ( !(unsigned int)IsAliasName(lpString1, lpValue) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_b29debb2a69d34804e2e00aace071994_Traceguids, lpValue);
    }
    FileW = CreateFileW(lpValue, 0, 1u, 0, 3u, 0x80u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      *(_QWORD *)pcbData = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_b29debb2a69d34804e2e00aace071994_Traceguids, lpValue);
      }
      if ( !SearchPathW(0, lpValue, 0, 0x104u, Buffer, (LPWSTR *)pcbData) )
        return 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          (unsigned int)WPP_b29debb2a69d34804e2e00aace071994_Traceguids,
          (_DWORD)lpValue,
          (__int64)Buffer);
      }
      v32 = CreateFileW(Buffer, 0, 1u, 0, 3u, 0x80u, 0);
      if ( v32 == (HANDLE)-1LL )
        return 0;
      CloseHandle(v32);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_b29debb2a69d34804e2e00aace071994_Traceguids, Buffer);
      }
      v33 = v5;
      if ( !(_DWORD)v5 )
        return 0;
      if ( v5 <= 0x7FFFFFFF )
      {
        v34 = 2147483646;
        v35 = lpValue;
        do
        {
          if ( !v34 )
            break;
          if ( !*v35 )
            break;
          *pvData++ = *v35++;
          --v34;
          --v33;
        }
        while ( v33 );
        v36 = pvData - 1;
        if ( v33 )
          v36 = pvData;
        *v36 = 0;
        if ( v33 )
        {
          v37 = -1;
          do
            ++v37;
          while ( lpValue[v37] );
          return (unsigned int)v37;
        }
        return 0;
      }
    }
    else
    {
      CloseHandle(FileW);
      v18 = v5;
      if ( !(_DWORD)v5 )
        return 0;
      if ( v5 <= 0x7FFFFFFF )
      {
        v19 = 2147483646;
        v20 = lpValue;
        do
        {
          if ( !v19 )
            break;
          if ( !*v20 )
            break;
          *pvData++ = *v20++;
          --v19;
          --v18;
        }
        while ( v18 );
        v21 = pvData - 1;
        if ( v18 )
          v21 = pvData;
        *v21 = 0;
        if ( v18 )
        {
          v22 = -1;
          do
            ++v22;
          while ( lpValue[v22] );
          return (unsigned int)v22;
        }
        return 0;
      }
    }
    *pvData = 0;
    return 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_b29debb2a69d34804e2e00aace071994_Traceguids);
  }
  v8 = 2147483646;
  v9 = L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\";
  v10 = 260;
  v11 = v39;
  v12 = 2147483646;
  v13 = 260;
  do
  {
    if ( !v12 )
      break;
    if ( !*v9 )
      break;
    *v11++ = *v9++;
    --v12;
    --v13;
  }
  while ( v13 );
  v14 = v11 - 1;
  if ( v13 )
    v14 = v11;
  v15 = 0;
  *v14 = 0;
  if ( !v13 )
    return 0;
  for ( i = v39; *i; ++i )
  {
    if ( !--v10 )
      return 0;
  }
  v24 = lpString1;
  v25 = Buffer - v10 + 3;
  do
  {
    if ( !v8 )
      break;
    if ( !*v24 )
      break;
    *v25++ = *v24++;
    --v8;
    --v10;
  }
  while ( v10 );
  v26 = v25 - 1;
  if ( v10 )
    v26 = v25;
  *v26 = 0;
  if ( !v10 )
    return 0;
  v27 = -1;
  if ( CompareStringW(0x7Fu, 1u, lpString1, -1, wszDrivers, -1) == 2 )
  {
    v29 = Drivers32Handle;
    if ( !Drivers32Handle )
    {
      v29 = mmRegOpenSubkey(v28, v39);
      Drivers32Handle = v29;
      if ( !v29 )
        return 0;
    }
    v30 = 0;
    v31 = (__int64)v29;
  }
  else
  {
    v31 = -2147483646;
    v30 = v39;
  }
  pcbData[0] = v5;
  LOBYTE(v15) = RegGetValueW((HKEY)v31, v30, lpValue, 2u, 0, pvData, pcbData) == 0;
  if ( !v15 )
    return 0;
  do
    ++v27;
  while ( pvData[v27] );
  return (unsigned int)v27;
}

```

## disassembly

```asm
0x180003460  push    rbx
0x180003462  push    rbp
0x180003463  push    rdi
0x180003464  push    r14
0x180003466  push    r15
0x180003468  sub     rsp, 490h
0x18000346f  mov     rax, cs:__security_cookie
0x180003476  xor     rax, rsp
0x180003479  mov     [rsp+4B8h+var_48], rax
0x180003481  mov     rbx, r8
0x180003484  mov     r15d, r9d
0x180003487  mov     rbp, rdx
0x18000348a  mov     r14, rcx
0x18000348d  xor     edx, edx; Val
0x18000348f  lea     rcx, [rsp+4B8h+Buffer]; void *
0x180003497  mov     r8d, 208h; Size
0x18000349d  call    memset_0
0x1800034a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800034a9  lea     rdi, WPP_GLOBAL_Control
0x1800034b0  cmp     rcx, rdi
0x1800034b3  jnz     loc_180003724
0x1800034b9  mov     rdx, rbp; lpValue
0x1800034bc  mov     [rsp+4B8h+var_30], rsi
0x1800034c4  mov     rcx, r14; lpString1
0x1800034c7  call    ?IsAliasName@@YAHPEBG0@Z; IsAliasName(ushort const *,ushort const *)
0x1800034cc  test    eax, eax
0x1800034ce  jz      loc_18000355A
0x1800034d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800034db  cmp     rcx, rdi
0x1800034de  jnz     loc_18000375D
0x1800034e4  mov     r10d, 7FFFFFFEh
0x1800034ea  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800034f1  mov     r11d, 104h
0x1800034f7  lea     r9, [rsp+4B8h+var_468]
0x1800034fc  mov     ecx, r10d
0x1800034ff  mov     r8d, r11d
0x180003502  test    rcx, rcx
0x180003505  jz      short loc_180003524
0x180003507  movzx   eax, word ptr [rdx]
0x18000350a  test    ax, ax
0x18000350d  jz      short loc_180003524
0x18000350f  mov     [r9], ax
0x180003513  add     rdx, 2
0x180003517  add     r9, 2
0x18000351b  dec     rcx
0x18000351e  sub     r8, 1
0x180003522  jnz     short loc_180003502
0x180003524  test    r8, r8
0x180003527  lea     rax, [r9-2]
0x18000352b  cmovnz  rax, r9
0x18000352f  xor     esi, esi
0x180003531  mov     [rax], si
0x180003534  test    r8, r8
0x180003537  jz      loc_180003669
0x18000353d  lea     rax, [rsp+4B8h+var_468]
0x180003542  cmp     [rax], si
0x180003545  jz      loc_180003621
0x18000354b  add     rax, 2
0x18000354f  sub     r11, 1
0x180003553  jnz     short loc_180003542
0x180003555  jmp     loc_180003669
0x18000355a  mov     rcx, cs:WPP_GLOBAL_Control
0x180003561  cmp     rcx, rdi
0x180003564  jnz     loc_1800038D1
0x18000356a  xor     esi, esi
0x18000356c  xor     r9d, r9d; lpSecurityAttributes
0x18000356f  mov     [rsp+4B8h+hTemplateFile], rsi; hTemplateFile
0x180003574  xor     edx, edx; dwDesiredAccess
0x180003576  mov     [rsp+4B8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000357e  mov     r8d, 1; dwShareMode
0x180003584  mov     rcx, rbp; lpFileName
0x180003587  mov     [rsp+4B8h+dwCreationDisposition], 3; dwCreationDisposition
0x18000358f  call    cs:__imp_CreateFileW
0x180003595  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180003599  jz      loc_18000378E
0x18000359f  mov     rcx, rax; hObject
0x1800035a2  call    cs:__imp_CloseHandle
0x1800035a8  mov     rdx, r15
0x1800035ab  test    r15d, r15d
0x1800035ae  jz      loc_180003669
0x1800035b4  cmp     rdx, 7FFFFFFFh
0x1800035bb  ja      loc_1800039B4
0x1800035c1  mov     r10d, 7FFFFFFEh
0x1800035c7  mov     rcx, rbp
0x1800035ca  nop     word ptr [rax+rax+00h]
0x1800035d0  test    r10, r10
0x1800035d3  jz      short loc_1800035F1
0x1800035d5  movzx   eax, word ptr [rcx]
0x1800035d8  test    ax, ax
0x1800035db  jz      short loc_1800035F1
0x1800035dd  mov     [rbx], ax
0x1800035e0  add     rcx, 2
0x1800035e4  add     rbx, 2
0x1800035e8  dec     r10
0x1800035eb  sub     rdx, 1
0x1800035ef  jnz     short loc_1800035D0
0x1800035f1  test    rdx, rdx
0x1800035f4  lea     rax, [rbx-2]
0x1800035f8  cmovnz  rax, rbx
0x1800035fc  mov     [rax], si
0x1800035ff  jz      short loc_180003669
0x180003601  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180003608  nop     dword ptr [rax+rax+00000000h]
0x180003610  inc     rdi
0x180003613  cmp     [rbp+rdi*2+0], si
0x180003618  jnz     short loc_180003610
0x18000361a  mov     eax, edi
0x18000361c  jmp     loc_1800036FD
0x180003621  lea     rax, [r11+r11]
0x180003625  mov     rdx, r14
0x180003628  lea     rcx, [rsp+4B8h+var_260]
0x180003630  sub     rcx, rax
0x180003633  test    r11, r11
0x180003636  jz      short loc_180003659
0x180003638  test    r10, r10
0x18000363b  jz      short loc_180003659
0x18000363d  movzx   eax, word ptr [rdx]
0x180003640  test    ax, ax
0x180003643  jz      short loc_180003659
0x180003645  mov     [rcx], ax
0x180003648  add     rdx, 2
0x18000364c  add     rcx, 2
0x180003650  dec     r10
0x180003653  sub     r11, 1
0x180003657  jnz     short loc_180003638
0x180003659  test    r11, r11
0x18000365c  lea     rax, [rcx-2]
0x180003660  cmovnz  rax, rcx
0x180003664  mov     [rax], si
0x180003667  jnz     short loc_180003670
0x180003669  xor     eax, eax
0x18000366b  jmp     loc_1800036FD
0x180003670  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180003677  lea     rax, wszDrivers; "DRIVERS32"
0x18000367e  mov     [rsp+4B8h+dwFlagsAndAttributes], edi; cchCount2
0x180003682  mov     r9d, edi; cchCount1
0x180003685  mov     r8, r14; lpString1
0x180003688  mov     qword ptr [rsp+4B8h+dwCreationDisposition], rax; lpString2
0x18000368d  mov     edx, 1; dwCmpFlags
0x180003692  mov     ecx, 7Fh; Locale
0x180003697  call    cs:__imp_CompareStringW
0x18000369d  cmp     eax, 2
0x1800036a0  jnz     loc_180003905
0x1800036a6  mov     rax, cs:?Drivers32Handle@@3PEAUHKEY__@@EA; HKEY__ * Drivers32Handle
0x1800036ad  test    rax, rax
0x1800036b0  jz      loc_180003920
0x1800036b6  lea     rcx, [rsp+4B8h+pcbData]
0x1800036bb  xor     edx, edx; lpSubKey
0x1800036bd  mov     [rsp+4B8h+hTemplateFile], rcx; pcbData
0x1800036c2  mov     rcx, rax; hkey
0x1800036c5  mov     qword ptr [rsp+4B8h+dwFlagsAndAttributes], rbx; pvData
0x1800036ca  mov     r9d, 2; dwFlags
0x1800036d0  mov     r8, rbp; lpValue
0x1800036d3  mov     qword ptr [rsp+4B8h+dwCreationDisposition], rsi; pdwType
0x1800036d8  mov     [rsp+4B8h+pcbData], r15d
0x1800036dd  call    cs:__imp_RegGetValueW
0x1800036e3  test    eax, eax
0x1800036e5  setz    sil
0x1800036e9  test    esi, esi
0x1800036eb  jz      loc_180003669
0x1800036f1  inc     rdi
0x1800036f4  cmp     word ptr [rbx+rdi*2], 0
0x1800036f9  jnz     short loc_1800036F1
0x1800036fb  mov     eax, edi
0x1800036fd  mov     rsi, [rsp+4B8h+var_30]
0x180003705  mov     rcx, [rsp+4B8h+var_48]
0x18000370d  xor     rcx, rsp; StackCookie
0x180003710  call    __security_check_cookie
0x180003715  add     rsp, 490h
0x18000371c  pop     r15
0x18000371e  pop     r14
0x180003720  pop     rdi
0x180003721  pop     rbp
0x180003722  pop     rbx
0x180003723  retn
0x180003724  test    dword ptr [rcx+1Ch], 400000h
0x18000372b  jz      loc_1800034B9
0x180003731  cmp     byte ptr [rcx+19h], 5
0x180003735  jb      loc_1800034B9
0x18000373b  mov     rcx, [rcx+10h]
0x18000373f  lea     r8, WPP_b29debb2a69d34804e2e00aace071994_Traceguids
0x180003746  mov     edx, 0Ah
0x18000374b  mov     qword ptr [rsp+4B8h+dwCreationDisposition], rbp
0x180003750  mov     r9, r14
0x180003753  call    WPP_SF_SS
0x180003758  jmp     loc_1800034B9
0x18000375d  test    dword ptr [rcx+1Ch], 400000h
0x180003764  jz      loc_1800034E4
0x18000376a  cmp     byte ptr [rcx+19h], 5
0x18000376e  jb      loc_1800034E4
0x180003774  mov     rcx, [rcx+10h]
0x180003778  lea     r8, WPP_b29debb2a69d34804e2e00aace071994_Traceguids
0x18000377f  mov     edx, 0Bh
0x180003784  call    WPP_SF_
0x180003789  jmp     loc_1800034E4
0x18000378e  mov     qword ptr [rsp+4B8h+pcbData], rsi
0x180003793  mov     rcx, cs:WPP_GLOBAL_Control
0x18000379a  cmp     rcx, rdi
0x18000379d  jnz     loc_18000393F
0x1800037a3  lea     rax, [rsp+4B8h+pcbData]
0x1800037a8  mov     r9d, 104h; nBufferLength
0x1800037ae  mov     qword ptr [rsp+4B8h+dwFlagsAndAttributes], rax; lpFilePart
0x1800037b3  xor     r8d, r8d; lpExtension
0x1800037b6  lea     rax, [rsp+4B8h+Buffer]
0x1800037be  mov     rdx, rbp; lpFileName
0x1800037c1  xor     ecx, ecx; lpPath
0x1800037c3  mov     qword ptr [rsp+4B8h+dwCreationDisposition], rax; lpBuffer
0x1800037c8  call    cs:__imp_SearchPathW
0x1800037ce  test    eax, eax
0x1800037d0  jz      loc_180003669
0x1800037d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800037dd  cmp     rcx, rdi
0x1800037e0  jnz     loc_180003973
0x1800037e6  mov     [rsp+4B8h+hTemplateFile], rsi; hTemplateFile
0x1800037eb  lea     rcx, [rsp+4B8h+Buffer]; lpFileName
0x1800037f3  mov     [rsp+4B8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800037fb  xor     r9d, r9d; lpSecurityAttributes
0x1800037fe  xor     edx, edx; dwDesiredAccess
0x180003800  mov     [rsp+4B8h+dwCreationDisposition], 3; dwCreationDisposition
0x180003808  mov     r8d, 1; dwShareMode
0x18000380e  call    cs:__imp_CreateFileW
0x180003814  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180003818  jz      loc_180003669
0x18000381e  mov     rcx, rax; hObject
0x180003821  call    cs:__imp_CloseHandle
0x180003827  mov     rcx, cs:WPP_GLOBAL_Control
0x18000382e  cmp     rcx, rdi
0x180003831  jz      short loc_18000385F
0x180003833  test    dword ptr [rcx+1Ch], 400000h
0x18000383a  jz      short loc_18000385F
0x18000383c  cmp     byte ptr [rcx+19h], 5
0x180003840  jb      short loc_18000385F
0x180003842  mov     rcx, [rcx+10h]
0x180003846  lea     r9, [rsp+4B8h+Buffer]
0x18000384e  mov     edx, 0Fh
0x180003853  lea     r8, WPP_b29debb2a69d34804e2e00aace071994_Traceguids
0x18000385a  call    WPP_SF_S
0x18000385f  mov     rdx, r15
0x180003862  test    r15d, r15d
0x180003865  jz      loc_180003669
0x18000386b  cmp     rdx, 7FFFFFFFh
0x180003872  ja      loc_1800039B4
0x180003878  mov     r10d, 7FFFFFFEh
0x18000387e  mov     rcx, rbp
0x180003881  test    r10, r10
0x180003884  jz      short loc_1800038A2
0x180003886  movzx   eax, word ptr [rcx]
0x180003889  test    ax, ax
0x18000388c  jz      short loc_1800038A2
0x18000388e  mov     [rbx], ax
0x180003891  add     rcx, 2
0x180003895  add     rbx, 2
0x180003899  dec     r10
0x18000389c  sub     rdx, 1
0x1800038a0  jnz     short loc_180003881
0x1800038a2  test    rdx, rdx
0x1800038a5  lea     rax, [rbx-2]
0x1800038a9  cmovnz  rax, rbx
0x1800038ad  mov     [rax], si
0x1800038b0  jz      loc_180003669
0x1800038b6  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x1800038bd  nop     dword ptr [rax]
0x1800038c0  inc     rdi
0x1800038c3  cmp     [rbp+rdi*2+0], si
0x1800038c8  jnz     short loc_1800038C0
0x1800038ca  mov     eax, edi
0x1800038cc  jmp     loc_1800036FD
0x1800038d1  test    dword ptr [rcx+1Ch], 400000h
0x1800038d8  jz      loc_18000356A
0x1800038de  cmp     byte ptr [rcx+19h], 5
0x1800038e2  jb      loc_18000356A
0x1800038e8  mov     rcx, [rcx+10h]
0x1800038ec  lea     r8, WPP_b29debb2a69d34804e2e00aace071994_Traceguids
0x1800038f3  mov     edx, 0Ch
0x1800038f8  mov     r9, rbp
0x1800038fb  call    WPP_SF_S
0x180003900  jmp     loc_18000356A
0x180003905  lea     rax, [rsp+4B8h+pcbData]
0x18000390a  mov     rcx, 0FFFFFFFF80000002h
0x180003911  mov     [rsp+4B8h+hTemplateFile], rax
0x180003916  lea     rdx, [rsp+4B8h+var_468]
0x18000391b  jmp     loc_1800036C5
0x180003920  lea     rdx, [rsp+4B8h+var_468]; unsigned __int16 *
0x180003925  call    ?mmRegOpenSubkey@@YAPEAUHKEY__@@PEAU1@PEBG@Z; mmRegOpenSubkey(HKEY__ *,ushort const *)
0x18000392a  mov     cs:?Drivers32Handle@@3PEAUHKEY__@@EA, rax; HKEY__ * Drivers32Handle
0x180003931  test    rax, rax
0x180003934  jz      loc_180003669
0x18000393a  jmp     loc_1800036B6
0x18000393f  test    dword ptr [rcx+1Ch], 400000h
0x180003946  jz      loc_1800037A3
0x18000394c  cmp     byte ptr [rcx+19h], 5
0x180003950  jb      loc_1800037A3
0x180003956  mov     rcx, [rcx+10h]
0x18000395a  lea     r8, WPP_b29debb2a69d34804e2e00aace071994_Traceguids
0x180003961  mov     edx, 0Dh
0x180003966  mov     r9, rbp
0x180003969  call    WPP_SF_S
0x18000396e  jmp     loc_1800037A3
0x180003973  test    dword ptr [rcx+1Ch], 400000h
0x18000397a  jz      loc_1800037E6
  ... truncated ...
```
