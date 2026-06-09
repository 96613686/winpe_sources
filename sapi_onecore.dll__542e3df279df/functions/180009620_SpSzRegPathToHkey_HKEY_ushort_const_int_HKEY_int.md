# SpSzRegPathToHkey(HKEY__ *,ushort const *,int,HKEY__ * *,int *)

- ea: `0x180009620`
- end: `0x1800099f9`
- name: `?SpSzRegPathToHkey@@YAJPEAUHKEY__@@PEBGHPEAPEAU1@PEAH@Z`
- size: `985`
- prototype: `int(HKEY, const unsigned __int16 *, int, HKEY *, int *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000aaf0`
- `0x18003c7e0`
- `0x1800efed8`

## callees

- `0x180009620`
- `0x18000a420`
- `0x180026508`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800097c3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800097c3`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180009836`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180009836`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000971b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180009808`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000994c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000998d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000971b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180009808`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000994c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000998d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009862`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800099b3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009862`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800099b3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009798`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800099ee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009798`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800099ee`

## string_xrefs

- `0x180009685`: `HKEY_CURRENT_CONFIG\`
- `0x1800098e4`: `onecoreuap\enduser\NUI\OneCore\sapi\sapi\SharedLib\RegistryIsolator.h`
- `0x180009911`: `onecoreuap\enduser\NUI\OneCore\sapi\sapi\SharedLib\RegistryIsolator.h`

## pseudocode

```c
__int64 __fastcall SpSzRegPathToHkey(HKEY a1, unsigned __int16 *a2, int a3, HKEY *a4, int *a5)
{
  HKEY v9; // rsi
  int i; // ebx
  unsigned __int16 *v11; // rdx
  unsigned __int64 j; // rax
  int v13; // eax
  bool v14; // sf
  int InitializedSingleton; // ebx
  HKEY v16; // r11
  HKEY v17; // r8
  unsigned __int64 v18; // rdx
  __int64 v19; // r10
  __int64 v20; // r8
  LSTATUS Key; // eax
  int v22; // esi
  const WCHAR *v23; // rdi
  LSTATUS v24; // eax
  HKEY v26; // rcx
  const WCHAR *v27; // rdx
  int dwOptions; // [rsp+20h] [rbp-71h]
  int dwOptionsa; // [rsp+20h] [rbp-71h]
  HKEY phkResult[2]; // [rsp+50h] [rbp-41h] BYREF
  const wchar_t *v31; // [rsp+60h] [rbp-31h]
  _QWORD v32[15]; // [rsp+68h] [rbp-29h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+57h]
  HKEY hKey; // [rsp+F0h] [rbp+5Fh] BYREF

  v32[0] = 0xFFFFFFFF80000000uLL;
  v32[2] = -2147483646;
  v31 = L"HKEY_CLASSES_ROOT\\";
  v32[4] = -2147483647;
  v32[1] = L"HKEY_LOCAL_MACHINE\\";
  v32[6] = -2147483643;
  v32[3] = L"HKEY_CURRENT_USER\\";
  hKey = 0;
  v32[5] = L"HKEY_CURRENT_CONFIG\\";
  v9 = 0;
  for ( i = 0; i < 4; ++i )
  {
    v20 = -1;
    do
      ++v20;
    while ( *(_WORD *)(v32[2 * i - 1] + 2 * v20) );
    if ( !(unsigned int)_o__wcsnicmp(a2) )
    {
      v9 = (HKEY)v32[2 * i];
      break;
    }
  }
  phkResult[0] = 0;
  if ( (int)CSpRegistryIsolator::GetInitializedSingleton((struct CSpRegistryIsolator **)phkResult, a2) >= 0
    && phkResult[0] )
  {
    hKey = v9;
    for ( j = 0; j < *((_QWORD *)phkResult[0] + 1); ++j )
    {
      v11 = (unsigned __int16 *)(2 * j);
      if ( v9 == *(HKEY *)(*(_QWORD *)phkResult[0] + 16 * j + 8) )
      {
        v13 = RegCreateKeyExW(
                *((HKEY *)phkResult[0] + 3),
                *(LPCWSTR *)(*(_QWORD *)phkResult[0] + 16 * j),
                0,
                0,
                1u,
                0xF003Fu,
                0,
                &hKey,
                0);
        v14 = v13 < 0;
        if ( v13 > 0 )
        {
          v13 = (unsigned __int16)v13 | 0x80070000;
          v14 = v13 < 0;
        }
        if ( v14 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x5F,
            (unsigned int)"onecoreuap\\enduser\\NUI\\OneCore\\sapi\\sapi\\SharedLib\\RegistryIsolator.h",
            (const char *)(unsigned int)v13,
            dwOptions);
          hKey = 0;
          goto LABEL_43;
        }
        break;
      }
    }
  }
  if ( !hKey )
  {
LABEL_43:
    InitializedSingleton = -2147200960;
    goto LABEL_37;
  }
  if ( a1 )
  {
    if ( hKey )
      RegCloseKey(hKey);
    hKey = a1;
  }
  phkResult[0] = 0;
  InitializedSingleton = CSpRegistryIsolator::GetInitializedSingleton((struct CSpRegistryIsolator **)phkResult, v11);
  if ( InitializedSingleton < 0 )
    goto LABEL_37;
  v16 = phkResult[0];
  if ( !phkResult[0] )
  {
    InitializedSingleton = -2147024882;
    goto LABEL_37;
  }
  v17 = hKey;
  v18 = 0;
  phkResult[0] = hKey;
  while ( v18 < *((_QWORD *)v16 + 1) )
  {
    v19 = *(_QWORD *)v16 + 16 * v18;
    if ( hKey == *(HKEY *)(v19 + 8) )
    {
      Key = RegCreateKeyExW(*((HKEY *)v16 + 3), *(LPCWSTR *)v19, 0, 0, 1u, 0xF003Fu, 0, phkResult, 0);
      InitializedSingleton = Key;
      if ( Key > 0 )
        InitializedSingleton = (unsigned __int16)Key | 0x80070000;
      if ( InitializedSingleton < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5F,
          (unsigned int)"onecoreuap\\enduser\\NUI\\OneCore\\sapi\\sapi\\SharedLib\\RegistryIsolator.h",
          (const char *)(unsigned int)InitializedSingleton,
          dwOptionsa);
        goto LABEL_37;
      }
      v17 = phkResult[0];
      break;
    }
    ++v18;
  }
  hKey = v17;
  phkResult[0] = 0;
  v22 = 0;
  v23 = wcschr(a2, 0x5Cu) + 1;
  if ( a3 )
    v24 = RegCreateKeyExW(hKey, v23, 0, 0, 1u, 0x2001Fu, 0, phkResult, 0);
  else
    v24 = RegOpenKeyExW(hKey, v23, 0, 0x2001Fu, phkResult);
  if ( !v24 )
    goto LABEL_34;
  v26 = hKey;
  v22 = 1;
  v27 = v23;
  if ( !a3 )
    goto LABEL_50;
  InitializedSingleton = RegCreateKeyExW(hKey, v23, 0, 0, 1u, 0x20019u, 0, phkResult, 0);
  if ( InitializedSingleton == 5 )
  {
    v26 = hKey;
    v27 = v23;
LABEL_50:
    InitializedSingleton = RegOpenKeyExW(v26, v27, 0, 0x20019u, phkResult);
  }
  if ( !InitializedSingleton )
  {
LABEL_34:
    *a4 = phkResult[0];
    if ( a5 )
      *a5 = v22;
    InitializedSingleton = 0;
    goto LABEL_37;
  }
  if ( InitializedSingleton == 2 || InitializedSingleton == 259 )
  {
    InitializedSingleton = -2147200966;
  }
  else if ( InitializedSingleton > 0 )
  {
    InitializedSingleton = (unsigned __int16)InitializedSingleton | 0x80070000;
  }
LABEL_37:
  if ( hKey != a1 && hKey )
    RegCloseKey(hKey);
  return (unsigned int)InitializedSingleton;
}

```

## disassembly

```asm
0x180009620  push    rbp
0x180009622  push    rbx
0x180009623  push    rsi
0x180009624  push    rdi
0x180009625  push    r12
0x180009627  push    r13
0x180009629  push    r14
0x18000962b  push    r15
0x18000962d  lea     rbp, [rsp-17h]
0x180009632  sub     rsp, 0A8h
0x180009639  xor     edi, edi
0x18000963b  mov     [rbp+4Fh+var_78], 0FFFFFFFF80000000h
0x180009643  lea     rax, aHkeyClassesRoo; "HKEY_CLASSES_ROOT\\"
0x18000964a  mov     [rbp+4Fh+var_68], 0FFFFFFFF80000002h
0x180009652  mov     [rbp+4Fh+var_80], rax
0x180009656  mov     r12, r9
0x180009659  lea     rax, aHkeyLocalMachi_4; "HKEY_LOCAL_MACHINE\\"
0x180009660  mov     [rbp+4Fh+var_58], 0FFFFFFFF80000001h
0x180009668  mov     [rbp+4Fh+var_70], rax
0x18000966c  mov     r13d, r8d
0x18000966f  lea     rax, aHkeyCurrentUse_4; "HKEY_CURRENT_USER\\"
0x180009676  mov     [rbp+4Fh+var_48], 0FFFFFFFF80000005h
0x18000967e  mov     [rbp+4Fh+var_60], rax
0x180009682  mov     r15, rdx
0x180009685  lea     rax, aHkeyCurrentCon; "HKEY_CURRENT_CONFIG\\"
0x18000968c  mov     [rbp+4Fh+hKey], rdi
0x180009690  mov     [rbp+4Fh+var_50], rax
0x180009694  mov     r14, rcx
0x180009697  mov     esi, edi
0x180009699  mov     ebx, edi
0x18000969b  cmp     ebx, 4
0x18000969e  jl      loc_1800097A4
0x1800096a4  xor     edi, edi
0x1800096a6  lea     rcx, [rbp+4Fh+var_90]; struct CSpRegistryIsolator **
0x1800096aa  mov     [rbp+4Fh+var_90], rdi
0x1800096ae  call    ?GetInitializedSingleton@CSpRegistryIsolator@@SAJPEAPEAV1@PEAG@Z; CSpRegistryIsolator::GetInitializedSingleton(CSpRegistryIsolator * *,ushort *)
0x1800096b3  test    eax, eax
0x1800096b5  js      short loc_18000972F
0x1800096b7  mov     r10, [rbp+4Fh+var_90]
0x1800096bb  test    r10, r10
0x1800096be  jz      short loc_18000972F
0x1800096c0  mov     [rbp+4Fh+hKey], rsi
0x1800096c4  mov     eax, edi
0x1800096c6  mov     r8, [r10+8]
0x1800096ca  nop     word ptr [rax+rax+00h]
0x1800096d0  cmp     rax, r8
0x1800096d3  jnb     short loc_18000972F
0x1800096d5  mov     rcx, [r10]
0x1800096d8  mov     rdx, rax
0x1800096db  add     rdx, rdx
0x1800096de  cmp     rsi, [rcx+rdx*8+8]
0x1800096e3  jz      short loc_1800096EA
0x1800096e5  inc     rax
0x1800096e8  jmp     short loc_1800096D0
0x1800096ea  mov     rdx, [rcx+rdx*8]; lpSubKey
0x1800096ee  lea     rax, [rbp+4Fh+hKey]
0x1800096f2  mov     rcx, [r10+18h]; hKey
0x1800096f6  xor     r9d, r9d; lpClass
0x1800096f9  mov     [rsp+0E0h+lpdwDisposition], rdi; lpdwDisposition
0x1800096fe  xor     r8d, r8d; Reserved
0x180009701  mov     [rsp+0E0h+phkResult], rax; phkResult
0x180009706  mov     [rsp+0E0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18000970b  mov     [rsp+0E0h+samDesired], 0F003Fh; samDesired
0x180009713  mov     [rsp+0E0h+dwOptions], 1; int
0x18000971b  call    cs:__imp_RegCreateKeyExW
0x180009721  test    eax, eax
0x180009723  jg      loc_1800098B4
0x180009729  js      loc_1800098E0
0x18000972f  cmp     [rbp+4Fh+hKey], rdi
0x180009733  jz      loc_1800098FC
0x180009739  test    r14, r14
0x18000973c  jnz     short loc_18000978F
0x18000973e  lea     rcx, [rbp+4Fh+var_90]; struct CSpRegistryIsolator **
0x180009742  mov     [rbp+4Fh+var_90], rdi
0x180009746  call    ?GetInitializedSingleton@CSpRegistryIsolator@@SAJPEAPEAV1@PEAG@Z; CSpRegistryIsolator::GetInitializedSingleton(CSpRegistryIsolator * *,ushort *)
0x18000974b  mov     ebx, eax
0x18000974d  test    eax, eax
0x18000974f  js      loc_180009887
0x180009755  mov     r11, [rbp+4Fh+var_90]
0x180009759  test    r11, r11
0x18000975c  jz      loc_180009903
0x180009762  mov     r8, [rbp+4Fh+hKey]
0x180009766  mov     rdx, rdi
0x180009769  mov     [rbp+4Fh+var_90], r8
0x18000976d  mov     r9, [r11+8]
0x180009771  cmp     rdx, r9
0x180009774  jnb     loc_180009824
0x18000977a  mov     r10, rdx
0x18000977d  shl     r10, 4
0x180009781  add     r10, [r11]
0x180009784  cmp     r8, [r10+8]
0x180009788  jz      short loc_1800097D8
0x18000978a  inc     rdx
0x18000978d  jmp     short loc_180009771
0x18000978f  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180009793  test    rcx, rcx
0x180009796  jz      short loc_18000979E
0x180009798  call    cs:__imp_RegCloseKey
0x18000979e  mov     [rbp+4Fh+hKey], r14
0x1800097a2  jmp     short loc_18000973E
0x1800097a4  movsxd  rdi, ebx
0x1800097a7  mov     r8, 0FFFFFFFFFFFFFFFFh
0x1800097ae  add     rdi, rdi
0x1800097b1  mov     rdx, [rbp+rdi*8+4Fh+var_80]
0x1800097b6  inc     r8
0x1800097b9  cmp     [rdx+r8*2], si
0x1800097be  jnz     short loc_1800097B6
0x1800097c0  mov     rcx, r15
0x1800097c3  call    cs:__imp__o__wcsnicmp
0x1800097c9  test    eax, eax
0x1800097cb  jz      loc_1800098AA
0x1800097d1  inc     ebx
0x1800097d3  jmp     loc_18000969B
0x1800097d8  mov     rdx, [r10]; lpSubKey
0x1800097db  lea     rax, [rbp+4Fh+var_90]
0x1800097df  mov     rcx, [r11+18h]; hKey
0x1800097e3  xor     r9d, r9d; lpClass
0x1800097e6  mov     [rsp+0E0h+lpdwDisposition], rdi; lpdwDisposition
0x1800097eb  xor     r8d, r8d; Reserved
0x1800097ee  mov     [rsp+0E0h+phkResult], rax; phkResult
0x1800097f3  mov     [rsp+0E0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x1800097f8  mov     [rsp+0E0h+samDesired], 0F003Fh; samDesired
0x180009800  mov     [rsp+0E0h+dwOptions], 1; int
0x180009808  call    cs:__imp_RegCreateKeyExW
0x18000980e  mov     ebx, eax
0x180009810  test    eax, eax
0x180009812  jg      loc_1800098C3
0x180009818  test    ebx, ebx
0x18000981a  js      loc_18000990D
0x180009820  mov     r8, [rbp+4Fh+var_90]
0x180009824  mov     edx, 5Ch ; '\'; Ch
0x180009829  mov     [rbp+4Fh+hKey], r8
0x18000982d  mov     rcx, r15; Str
0x180009830  mov     [rbp+4Fh+var_90], rdi
0x180009834  mov     esi, edi
0x180009836  call    cs:__imp_wcschr
0x18000983c  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180009840  xor     r8d, r8d; Reserved
0x180009843  lea     rdi, [rax+2]
0x180009847  lea     rax, [rbp+4Fh+var_90]
0x18000984b  mov     rdx, rdi; lpSubKey
0x18000984e  test    r13d, r13d
0x180009851  jnz     loc_18000992A
0x180009857  mov     r9d, 2001Fh; samDesired
0x18000985d  mov     qword ptr [rsp+0E0h+dwOptions], rax; phkResult
0x180009862  call    cs:__imp_RegOpenKeyExW
0x180009868  test    eax, eax
0x18000986a  jnz     loc_180009957
0x180009870  mov     rax, [rbp+4Fh+var_90]
0x180009874  mov     [r12], rax
0x180009878  mov     rax, [rbp+4Fh+arg_20]
0x18000987c  test    rax, rax
0x18000987f  jnz     loc_1800099DE
0x180009885  xor     ebx, ebx
0x180009887  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18000988b  cmp     rcx, r14
0x18000988e  jnz     loc_1800099E5
0x180009894  mov     eax, ebx
0x180009896  add     rsp, 0A8h
0x18000989d  pop     r15
0x18000989f  pop     r14
0x1800098a1  pop     r13
0x1800098a3  pop     r12
0x1800098a5  pop     rdi
0x1800098a6  pop     rsi
0x1800098a7  pop     rbx
0x1800098a8  pop     rbp
0x1800098a9  retn
0x1800098aa  mov     rsi, [rbp+rdi*8+4Fh+var_78]
0x1800098af  jmp     loc_1800096A4
0x1800098b4  movzx   eax, ax
0x1800098b7  or      eax, 80070000h
0x1800098bc  test    eax, eax
0x1800098be  jmp     loc_180009729
0x1800098c3  movzx   ebx, ax
0x1800098c6  or      ebx, 80070000h
0x1800098cc  jmp     loc_180009818
0x1800098d1  test    ebx, ebx
0x1800098d3  jle     short loc_180009887
0x1800098d5  movzx   ebx, bx
0x1800098d8  or      ebx, 80070000h
0x1800098de  jmp     short loc_180009887
0x1800098e0  mov     rcx, [rbp+57h]; this
0x1800098e4  lea     r8, aOnecoreuapEndu_348; "onecoreuap\\enduser\\NUI\\OneCore\\sapi"...
0x1800098eb  mov     r9d, eax; char *
0x1800098ee  mov     edx, 5Fh ; '_'; void *
0x1800098f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800098f8  mov     [rbp+4Fh+hKey], rdi
0x1800098fc  mov     ebx, 80045040h
0x180009901  jmp     short loc_180009887
0x180009903  mov     ebx, 8007000Eh
0x180009908  jmp     loc_180009887
0x18000990d  mov     rcx, [rbp+57h]; this
0x180009911  lea     r8, aOnecoreuapEndu_348; "onecoreuap\\enduser\\NUI\\OneCore\\sapi"...
0x180009918  mov     r9d, ebx; char *
0x18000991b  mov     edx, 5Fh ; '_'; void *
0x180009920  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009925  jmp     loc_180009887
0x18000992a  mov     [rsp+0E0h+lpdwDisposition], rsi; lpdwDisposition
0x18000992f  xor     r9d, r9d; lpClass
0x180009932  mov     [rsp+0E0h+phkResult], rax; phkResult
0x180009937  mov     [rsp+0E0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18000993c  mov     [rsp+0E0h+samDesired], 2001Fh; samDesired
0x180009944  mov     [rsp+0E0h+dwOptions], 1; dwOptions
0x18000994c  call    cs:__imp_RegCreateKeyExW
0x180009952  jmp     loc_180009868
0x180009957  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18000995b  lea     rax, [rbp+4Fh+var_90]
0x18000995f  xor     r8d, r8d; Reserved
0x180009962  mov     esi, 1
0x180009967  mov     rdx, rdi; lpSubKey
0x18000996a  test    r13d, r13d
0x18000996d  jz      short loc_1800099A8
0x18000996f  mov     [rsp+0E0h+lpdwDisposition], r8; lpdwDisposition
0x180009974  xor     r9d, r9d; lpClass
0x180009977  mov     [rsp+0E0h+phkResult], rax; phkResult
0x18000997c  mov     [rsp+0E0h+lpSecurityAttributes], r8; lpSecurityAttributes
0x180009981  mov     [rsp+0E0h+samDesired], 20019h; samDesired
0x180009989  mov     [rsp+0E0h+dwOptions], esi; dwOptions
0x18000998d  call    cs:__imp_RegCreateKeyExW
0x180009993  mov     ebx, eax
0x180009995  cmp     eax, 5
0x180009998  jnz     short loc_1800099BB
0x18000999a  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18000999e  lea     rax, [rbp+4Fh+var_90]
0x1800099a2  xor     r8d, r8d; ulOptions
0x1800099a5  mov     rdx, rdi; lpSubKey
0x1800099a8  mov     r9d, 20019h; samDesired
0x1800099ae  mov     qword ptr [rsp+0E0h+dwOptions], rax; phkResult
0x1800099b3  call    cs:__imp_RegOpenKeyExW
0x1800099b9  mov     ebx, eax
0x1800099bb  test    ebx, ebx
0x1800099bd  jz      loc_180009870
0x1800099c3  cmp     ebx, 2
0x1800099c6  jz      short loc_1800099D4
0x1800099c8  cmp     ebx, 103h
0x1800099ce  jnz     loc_1800098D1
0x1800099d4  mov     ebx, 8004503Ah
0x1800099d9  jmp     loc_180009887
0x1800099de  mov     [rax], esi
0x1800099e0  jmp     loc_180009885
0x1800099e5  test    rcx, rcx
0x1800099e8  jz      loc_180009894
0x1800099ee  call    cs:__imp_RegCloseKey
0x1800099f4  jmp     loc_180009894
```
