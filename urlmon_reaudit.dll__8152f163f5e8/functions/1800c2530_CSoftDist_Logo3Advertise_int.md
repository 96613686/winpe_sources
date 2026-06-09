# CSoftDist::Logo3Advertise(int)

- ea: `0x1800c2530`
- end: `0x1800c295e`
- name: `?Logo3Advertise@CSoftDist@@AEAAJH@Z`
- size: `1070`
- prototype: `__int64 __fastcall(CSoftDist *__hidden this, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800bf7c8`

## callees

- `0x18001db50`
- `0x18002fee0`
- `0x18005789c`
- `0x1800c0c44`
- `0x1800c2530`
- `0x180128660`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800c25e1`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800c2629`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800c25e1`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800c2629`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c259e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c264d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c26c8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c259e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c264d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c26c8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800c2784`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800c27d6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800c281e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800c2866`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800c28a8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800c2784`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800c27d6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800c281e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800c2866`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800c28a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c28f3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c2909`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c291f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c28f3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c2909`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c291f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueA` at `0x1800c28ce`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueA` at `0x1800c28ce`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800c268c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800c270b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800c268c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800c270b`

## string_xrefs

- `0x1800c2590`: `Software\Microsoft\Windows\CurrentVersion\Uninstall`
- `0x1800c28c7`: `Precache`

## pseudocode

```c
__int64 __fastcall CSoftDist::Logo3Advertise(CSoftDist *this, int a2)
{
  CHAR *v4; // r14
  LSTATUS v5; // ebx
  __int64 v6; // rsi
  size_t cbMultiByte; // rbx
  CHAR *v8; // rax
  LSTATUS v9; // eax
  bool v10; // cc
  __int64 v11; // rax
  const BYTE *v12; // rcx
  __int64 v13; // rax
  const BYTE *v14; // rcx
  __int64 v15; // rax
  const BYTE *v16; // rcx
  bool v17; // cc
  HKEY v19; // [rsp+50h] [rbp-B0h] BYREF
  BYTE v20[8]; // [rsp+58h] [rbp-A8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  BYTE Data[272]; // [rsp+70h] [rbp-90h] BYREF

  hKey = 0;
  phkResult = 0;
  v19 = 0;
  *(_DWORD *)v20 = 0;
  if ( RegOpenKeyExA(HKEY_LOCAL_MACHINE, "Software\\Microsoft\\Windows\\CurrentVersion\\Uninstall", 0, 0xF003Fu, &hKey) )
  {
    v4 = 0;
    v5 = -2147467259;
    goto LABEL_34;
  }
  v6 = -1;
  cbMultiByte = (unsigned int)WideCharToMultiByte(0, 0x400u, *((LPCWCH *)this + 2), -1, 0, 0, 0, 0);
  v8 = (CHAR *)operator new(cbMultiByte);
  v4 = v8;
  if ( !v8 )
  {
    v5 = -2147024882;
    goto LABEL_34;
  }
  WideCharToMultiByte(0, 0x400u, *((LPCWCH *)this + 2), -1, v8, cbMultiByte, 0, 0);
  if ( RegOpenKeyExA(hKey, v4, 0, 0xF003Fu, &phkResult)
    && (v9 = RegCreateKeyExA(hKey, v4, 0, 0, 0, 0x2000000u, 0, &phkResult, 0), v5 = v9, v10 = v9 <= 0, v9)
    || RegOpenKeyExA(phkResult, "AvailableVersion", 0, 0xF003Fu, &v19)
    && (v9 = RegCreateKeyExA(phkResult, "AvailableVersion", 0, 0, 0, 0x2000000u, 0, &v19, 0), v5 = v9, v10 = v9 <= 0, v9) )
  {
    if ( v10 )
      goto LABEL_34;
    v5 = (unsigned __int16)v9;
LABEL_33:
    v5 |= 0x80070000;
    goto LABEL_34;
  }
  StringCchPrintfA(
    (char *)Data,
    0x104u,
    "%d,%d,%d,%d",
    *((unsigned __int16 *)this + 13),
    *((unsigned __int16 *)this + 12),
    *((unsigned __int16 *)this + 15),
    *((unsigned __int16 *)this + 14));
  v11 = -1;
  do
    ++v11;
  while ( Data[v11] );
  v5 = RegSetValueExA(v19, 0, 0, 1u, Data, v11 + 1);
  if ( a2 || IsAbstractDifferent(v19, *((char **)this + 9)) )
  {
    *(_DWORD *)v20 = 0;
    v5 = RegSetValueExA(v19, "AdState", 0, 4u, v20, 4u);
    if ( v5 )
      goto LABEL_30;
    v12 = (const BYTE *)*((_QWORD *)this + 10);
    if ( v12 )
    {
      v13 = -1;
      do
        ++v13;
      while ( v12[v13] );
      v5 = RegSetValueExA(v19, "HREF", 0, 1u, v12, v13 + 1);
      if ( v5 )
        goto LABEL_30;
    }
    v14 = (const BYTE *)*((_QWORD *)this + 9);
    if ( v14 )
    {
      v15 = -1;
      do
        ++v15;
      while ( v14[v15] );
      v5 = RegSetValueExA(v19, "Abstract", 0, 1u, v14, v15 + 1);
      if ( v5 )
      {
LABEL_30:
        v17 = v5 <= 0;
        goto LABEL_31;
      }
    }
    v16 = (const BYTE *)*((_QWORD *)this + 7);
    if ( !v16 )
      goto LABEL_28;
    do
      ++v6;
    while ( v16[v6] );
    v5 = RegSetValueExA(v19, "Title", 0, 1u, v16, v6 + 1);
  }
  v17 = v5 <= 0;
  if ( v5 )
  {
LABEL_31:
    if ( v17 )
      goto LABEL_34;
    v5 = (unsigned __int16)v5;
    goto LABEL_33;
  }
LABEL_28:
  v5 = 0;
  if ( a2 )
    RegDeleteValueA(v19, "Precache");
LABEL_34:
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v19 )
    RegCloseKey(v19);
  if ( v4 )
    operator delete(v4);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800c2530  push    rbp
0x1800c2532  push    rbx
0x1800c2533  push    rsi
0x1800c2534  push    rdi
0x1800c2535  push    r12
0x1800c2537  push    r13
0x1800c2539  push    r14
0x1800c253b  push    r15
0x1800c253d  lea     rbp, [rsp-98h]
0x1800c2545  sub     rsp, 198h
0x1800c254c  mov     rax, cs:__security_cookie
0x1800c2553  xor     rax, rsp
0x1800c2556  mov     [rbp+0D0h+var_50], rax
0x1800c255d  xor     r12d, r12d
0x1800c2560  lea     rax, [rsp+1D0h+hKey]
0x1800c2565  mov     r15d, edx
0x1800c2568  mov     [rsp+1D0h+hKey], r12
0x1800c256d  mov     rdi, rcx
0x1800c2570  mov     [rsp+1D0h+var_170], r12
0x1800c2575  mov     r13d, 0F003Fh
0x1800c257b  mov     [rsp+1D0h+var_180], r12
0x1800c2580  mov     r9d, r13d; samDesired
0x1800c2583  mov     dword ptr [rsp+1D0h+var_178], r12d
0x1800c2588  xor     r8d, r8d; ulOptions
0x1800c258b  mov     [rsp+1D0h+phkResult], rax; phkResult
0x1800c2590  lea     rdx, aSoftwareMicros_77; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800c2597  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800c259e  call    cs:__imp_RegOpenKeyExA
0x1800c25a5  nop     dword ptr [rax+rax+00h]
0x1800c25aa  test    eax, eax
0x1800c25ac  jz      short loc_1800C25BB
0x1800c25ae  mov     r14d, r12d
0x1800c25b1  mov     ebx, 80004005h
0x1800c25b6  jmp     loc_1800C28E9
0x1800c25bb  mov     r8, [rdi+10h]; lpWideCharStr
0x1800c25bf  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800c25c3  mov     [rsp+1D0h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x1800c25c8  mov     r9d, esi; cchWideChar
0x1800c25cb  mov     [rsp+1D0h+lpDefaultChar], r12; lpDefaultChar
0x1800c25d0  mov     edx, 400h; dwFlags
0x1800c25d5  mov     [rsp+1D0h+cbMultiByte], r12d; cbMultiByte
0x1800c25da  xor     ecx, ecx; CodePage
0x1800c25dc  mov     [rsp+1D0h+phkResult], r12; lpMultiByteStr
0x1800c25e1  call    cs:__imp_WideCharToMultiByte
0x1800c25e8  nop     dword ptr [rax+rax+00h]
0x1800c25ed  mov     ecx, eax; Size
0x1800c25ef  mov     ebx, eax
0x1800c25f1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800c25f6  mov     r14, rax
0x1800c25f9  test    rax, rax
0x1800c25fc  jnz     short loc_1800C2608
0x1800c25fe  mov     ebx, 8007000Eh
0x1800c2603  jmp     loc_1800C28E9
0x1800c2608  mov     r8, [rdi+10h]; lpWideCharStr
0x1800c260c  mov     r9d, esi; cchWideChar
0x1800c260f  mov     [rsp+1D0h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x1800c2614  mov     edx, 400h; dwFlags
0x1800c2619  mov     [rsp+1D0h+lpDefaultChar], r12; lpDefaultChar
0x1800c261e  xor     ecx, ecx; CodePage
0x1800c2620  mov     [rsp+1D0h+cbMultiByte], ebx; cbMultiByte
0x1800c2624  mov     [rsp+1D0h+phkResult], r14; lpMultiByteStr
0x1800c2629  call    cs:__imp_WideCharToMultiByte
0x1800c2630  nop     dword ptr [rax+rax+00h]
0x1800c2635  mov     rcx, [rsp+1D0h+hKey]; hKey
0x1800c263a  lea     rax, [rsp+1D0h+var_170]
0x1800c263f  mov     r9d, r13d; samDesired
0x1800c2642  mov     [rsp+1D0h+phkResult], rax; phkResult
0x1800c2647  xor     r8d, r8d; ulOptions
0x1800c264a  mov     rdx, r14; lpSubKey
0x1800c264d  call    cs:__imp_RegOpenKeyExA
0x1800c2654  nop     dword ptr [rax+rax+00h]
0x1800c2659  test    eax, eax
0x1800c265b  jz      short loc_1800C26AC
0x1800c265d  mov     rcx, [rsp+1D0h+hKey]; hKey
0x1800c2662  lea     rax, [rsp+1D0h+var_170]
0x1800c2667  mov     [rsp+1D0h+lpdwDisposition], r12; lpdwDisposition
0x1800c266c  xor     r9d, r9d; lpClass
0x1800c266f  mov     [rsp+1D0h+lpUsedDefaultChar], rax; phkResult
0x1800c2674  xor     r8d, r8d; Reserved
0x1800c2677  mov     [rsp+1D0h+lpDefaultChar], r12; lpSecurityAttributes
0x1800c267c  mov     rdx, r14; lpSubKey
0x1800c267f  mov     [rsp+1D0h+cbMultiByte], 2000000h; samDesired
0x1800c2687  mov     dword ptr [rsp+1D0h+phkResult], r12d; dwOptions
0x1800c268c  call    cs:__imp_RegCreateKeyExA
0x1800c2693  nop     dword ptr [rax+rax+00h]
0x1800c2698  mov     ebx, eax
0x1800c269a  test    eax, eax
0x1800c269c  jz      short loc_1800C26AC
0x1800c269e  jle     loc_1800C28E9
0x1800c26a4  movzx   ebx, ax
0x1800c26a7  jmp     loc_1800C28E3
0x1800c26ac  mov     rcx, [rsp+1D0h+var_170]; hKey
0x1800c26b1  lea     rax, [rsp+1D0h+var_180]
0x1800c26b6  mov     r9d, r13d; samDesired
0x1800c26b9  mov     [rsp+1D0h+phkResult], rax; phkResult
0x1800c26be  xor     r8d, r8d; ulOptions
0x1800c26c1  lea     rdx, aAvailableversi; "AvailableVersion"
0x1800c26c8  call    cs:__imp_RegOpenKeyExA
0x1800c26cf  nop     dword ptr [rax+rax+00h]
0x1800c26d4  test    eax, eax
0x1800c26d6  jz      short loc_1800C271D
0x1800c26d8  mov     rcx, [rsp+1D0h+var_170]; hKey
0x1800c26dd  lea     rax, [rsp+1D0h+var_180]
0x1800c26e2  mov     [rsp+1D0h+lpdwDisposition], r12; lpdwDisposition
0x1800c26e7  lea     rdx, aAvailableversi; "AvailableVersion"
0x1800c26ee  mov     [rsp+1D0h+lpUsedDefaultChar], rax; phkResult
0x1800c26f3  xor     r9d, r9d; lpClass
0x1800c26f6  mov     [rsp+1D0h+lpDefaultChar], r12; lpSecurityAttributes
0x1800c26fb  xor     r8d, r8d; Reserved
0x1800c26fe  mov     [rsp+1D0h+cbMultiByte], 2000000h; samDesired
0x1800c2706  mov     dword ptr [rsp+1D0h+phkResult], r12d; dwOptions
0x1800c270b  call    cs:__imp_RegCreateKeyExA
0x1800c2712  nop     dword ptr [rax+rax+00h]
0x1800c2717  mov     ebx, eax
0x1800c2719  test    eax, eax
0x1800c271b  jnz     short loc_1800C269E
0x1800c271d  movzx   ecx, word ptr [rdi+1Ch]
0x1800c2721  lea     r8, aDDDD_0; "%d,%d,%d,%d"
0x1800c2728  movzx   edx, word ptr [rdi+1Eh]
0x1800c272c  movzx   eax, word ptr [rdi+18h]
0x1800c2730  movzx   r9d, word ptr [rdi+1Ah]
0x1800c2735  mov     dword ptr [rsp+1D0h+lpDefaultChar], ecx
0x1800c2739  lea     rcx, [rsp+1D0h+Data]; char *
0x1800c273e  mov     [rsp+1D0h+cbMultiByte], edx
0x1800c2742  mov     edx, 104h; unsigned __int64
0x1800c2747  mov     dword ptr [rsp+1D0h+phkResult], eax
0x1800c274b  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800c2750  lea     rcx, [rsp+1D0h+Data]
0x1800c2755  mov     rax, rsi
0x1800c2758  inc     rax
0x1800c275b  cmp     [rcx+rax], r12b
0x1800c275f  jnz     short loc_1800C2758
0x1800c2761  mov     rcx, [rsp+1D0h+var_180]; hKey
0x1800c2766  inc     eax
0x1800c2768  mov     [rsp+1D0h+cbMultiByte], eax; cbData
0x1800c276c  mov     r13d, 1
0x1800c2772  lea     rax, [rsp+1D0h+Data]
0x1800c2777  mov     r9d, r13d; dwType
0x1800c277a  xor     r8d, r8d; Reserved
0x1800c277d  mov     [rsp+1D0h+phkResult], rax; lpData
0x1800c2782  xor     edx, edx; lpValueName
0x1800c2784  call    cs:__imp_RegSetValueExA
0x1800c278b  nop     dword ptr [rax+rax+00h]
0x1800c2790  mov     ebx, eax
0x1800c2792  test    r15d, r15d
0x1800c2795  jnz     short loc_1800C27AD
0x1800c2797  mov     rdx, [rdi+48h]; char *
0x1800c279b  mov     rcx, [rsp+1D0h+var_180]; HKEY
0x1800c27a0  call    ?IsAbstractDifferent@@YAHPEAUHKEY__@@PEAD@Z; IsAbstractDifferent(HKEY__ *,char *)
0x1800c27a5  test    eax, eax
0x1800c27a7  jz      loc_1800C28B6
0x1800c27ad  mov     rcx, [rsp+1D0h+var_180]; hKey
0x1800c27b2  lea     rax, [rsp+1D0h+var_178]
0x1800c27b7  mov     r9d, 4; dwType
0x1800c27bd  mov     dword ptr [rsp+1D0h+var_178], r12d
0x1800c27c2  mov     [rsp+1D0h+cbMultiByte], r9d; cbData
0x1800c27c7  lea     rdx, aAdstate; "AdState"
0x1800c27ce  xor     r8d, r8d; Reserved
0x1800c27d1  mov     [rsp+1D0h+phkResult], rax; lpData
0x1800c27d6  call    cs:__imp_RegSetValueExA
0x1800c27dd  nop     dword ptr [rax+rax+00h]
0x1800c27e2  mov     ebx, eax
0x1800c27e4  test    eax, eax
0x1800c27e6  jnz     loc_1800C28DC
0x1800c27ec  mov     rcx, [rdi+50h]
0x1800c27f0  test    rcx, rcx
0x1800c27f3  jz      short loc_1800C2834
0x1800c27f5  mov     rax, rsi
0x1800c27f8  inc     rax
0x1800c27fb  cmp     [rcx+rax], r12b
0x1800c27ff  jnz     short loc_1800C27F8
0x1800c2801  inc     eax
0x1800c2803  lea     rdx, aHref; "HREF"
0x1800c280a  mov     [rsp+1D0h+cbMultiByte], eax; cbData
0x1800c280e  mov     r9d, r13d; dwType
0x1800c2811  mov     [rsp+1D0h+phkResult], rcx; lpData
0x1800c2816  xor     r8d, r8d; Reserved
0x1800c2819  mov     rcx, [rsp+1D0h+var_180]; hKey
0x1800c281e  call    cs:__imp_RegSetValueExA
0x1800c2825  nop     dword ptr [rax+rax+00h]
0x1800c282a  mov     ebx, eax
0x1800c282c  test    eax, eax
0x1800c282e  jnz     loc_1800C28DC
0x1800c2834  mov     rcx, [rdi+48h]
0x1800c2838  test    rcx, rcx
0x1800c283b  jz      short loc_1800C2878
0x1800c283d  mov     rax, rsi
0x1800c2840  inc     rax
0x1800c2843  cmp     [rcx+rax], r12b
0x1800c2847  jnz     short loc_1800C2840
0x1800c2849  inc     eax
0x1800c284b  lea     rdx, aAbstract_0; "Abstract"
0x1800c2852  mov     [rsp+1D0h+cbMultiByte], eax; cbData
0x1800c2856  mov     r9d, r13d; dwType
0x1800c2859  mov     [rsp+1D0h+phkResult], rcx; lpData
0x1800c285e  xor     r8d, r8d; Reserved
0x1800c2861  mov     rcx, [rsp+1D0h+var_180]; hKey
0x1800c2866  call    cs:__imp_RegSetValueExA
0x1800c286d  nop     dword ptr [rax+rax+00h]
0x1800c2872  mov     ebx, eax
0x1800c2874  test    eax, eax
0x1800c2876  jnz     short loc_1800C28DC
0x1800c2878  mov     rcx, [rdi+38h]
0x1800c287c  test    rcx, rcx
0x1800c287f  jz      short loc_1800C28BA
0x1800c2881  inc     rsi
0x1800c2884  cmp     [rcx+rsi], r12b
0x1800c2888  jnz     short loc_1800C2881
0x1800c288a  lea     eax, [rsi+1]
0x1800c288d  mov     r9d, r13d; dwType
0x1800c2890  mov     [rsp+1D0h+cbMultiByte], eax; cbData
0x1800c2894  lea     rdx, aTitle_2; "Title"
0x1800c289b  mov     [rsp+1D0h+phkResult], rcx; lpData
0x1800c28a0  xor     r8d, r8d; Reserved
0x1800c28a3  mov     rcx, [rsp+1D0h+var_180]; hKey
0x1800c28a8  call    cs:__imp_RegSetValueExA
0x1800c28af  nop     dword ptr [rax+rax+00h]
0x1800c28b4  mov     ebx, eax
0x1800c28b6  test    ebx, ebx
0x1800c28b8  jnz     short loc_1800C28DE
0x1800c28ba  mov     ebx, r12d
0x1800c28bd  test    r15d, r15d
0x1800c28c0  jz      short loc_1800C28E9
0x1800c28c2  mov     rcx, [rsp+1D0h+var_180]; hKey
0x1800c28c7  lea     rdx, aPrecache_0; "Precache"
0x1800c28ce  call    cs:__imp_RegDeleteValueA
0x1800c28d5  nop     dword ptr [rax+rax+00h]
0x1800c28da  jmp     short loc_1800C28E9
0x1800c28dc  test    ebx, ebx
0x1800c28de  jle     short loc_1800C28E9
0x1800c28e0  movzx   ebx, bx
0x1800c28e3  or      ebx, 80070000h
0x1800c28e9  mov     rcx, [rsp+1D0h+hKey]; hKey
0x1800c28ee  test    rcx, rcx
0x1800c28f1  jz      short loc_1800C28FF
0x1800c28f3  call    cs:__imp_RegCloseKey
0x1800c28fa  nop     dword ptr [rax+rax+00h]
0x1800c28ff  mov     rcx, [rsp+1D0h+var_170]; hKey
0x1800c2904  test    rcx, rcx
0x1800c2907  jz      short loc_1800C2915
0x1800c2909  call    cs:__imp_RegCloseKey
0x1800c2910  nop     dword ptr [rax+rax+00h]
0x1800c2915  mov     rcx, [rsp+1D0h+var_180]; hKey
0x1800c291a  test    rcx, rcx
0x1800c291d  jz      short loc_1800C292B
0x1800c291f  call    cs:__imp_RegCloseKey
0x1800c2926  nop     dword ptr [rax+rax+00h]
0x1800c292b  test    r14, r14
0x1800c292e  jz      short loc_1800C2938
0x1800c2930  mov     rcx, r14; void *
0x1800c2933  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800c2938  mov     eax, ebx
0x1800c293a  mov     rcx, [rbp+0D0h+var_50]
0x1800c2941  xor     rcx, rsp; StackCookie
0x1800c2944  call    __security_check_cookie
0x1800c2949  add     rsp, 198h
0x1800c2950  pop     r15
0x1800c2952  pop     r14
0x1800c2954  pop     r13
0x1800c2956  pop     r12
0x1800c2958  pop     rdi
0x1800c2959  pop     rsi
0x1800c295a  pop     rbx
0x1800c295b  pop     rbp
0x1800c295c  retn
```
