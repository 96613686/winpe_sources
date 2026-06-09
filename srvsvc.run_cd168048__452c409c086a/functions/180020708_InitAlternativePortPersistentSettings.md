# InitAlternativePortPersistentSettings

- ea: `0x180020708`
- end: `0x180020a43`
- name: `InitAlternativePortPersistentSettings`
- size: `827`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180015500`

## callees

- `0x18001deb0`
- `0x180020698`
- `0x180020708`
- `0x180020d74`
- `0x180020dc0`
- `0x180020de8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180020935`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180020935`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800208d2`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800208d2`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800208b7`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800208b7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800207f4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800207f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020a1e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020a1e`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18002087c`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800209fe`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18002087c`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800209fe`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020764`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020764`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020a0f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020a0f`

## string_xrefs

- `0x1800207c7`: `SYSTEM\CurrentControlSet\Services\LanmanServer\AlternativePorts`

## pseudocode

```c
int InitAlternativePortPersistentSettings()
{
  HLOCAL v0; // rax
  void *v1; // rsi
  unsigned int v2; // eax
  DWORD v3; // r12d
  unsigned int v4; // r15d
  int v5; // r13d
  wchar_t *v6; // rax
  unsigned int v7; // r14d
  unsigned int v8; // eax
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  DWORD cchValueName; // [rsp+50h] [rbp-19h] BYREF
  DWORD cbData; // [rsp+54h] [rbp-15h] BYREF
  BYTE Data[4]; // [rsp+58h] [rbp-11h] BYREF
  DWORD Type; // [rsp+5Ch] [rbp-Dh] BYREF
  HKEY hKey; // [rsp+60h] [rbp-9h] BYREF
  wchar_t *Context; // [rsp+68h] [rbp-1h] BYREF
  __int16 v19; // [rsp+70h] [rbp+7h] BYREF
  char v20; // [rsp+72h] [rbp+9h]
  char v21; // [rsp+73h] [rbp+Ah]
  int v22; // [rsp+74h] [rbp+Bh]
  int v23; // [rsp+78h] [rbp+Fh]

  hKey = 0;
  cchValueName = 0x3FFF;
  Type = 0;
  *(_DWORD *)Data = 0;
  cbData = 4;
  Context = 0;
  v0 = LocalAlloc(0x40u, 0x7FFEu);
  v1 = v0;
  if ( v0 )
  {
    v2 = RegCreateKeyExW(
           HKEY_LOCAL_MACHINE,
           L"SYSTEM\\CurrentControlSet\\Services\\LanmanServer\\AlternativePorts",
           0,
           0,
           0,
           1u,
           0,
           &hKey,
           0);
    if ( v2 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_65085b59a2b6395dd5080b9566a77d67_Traceguids, v2);
      }
      goto LABEL_36;
    }
    v3 = 0;
    v4 = 0;
    if ( RegEnumValueW(hKey, 0, (LPWSTR)v1, &cchValueName, 0, &Type, Data, &cbData) )
    {
LABEL_36:
      LODWORD(v0) = (unsigned int)LocalFree(v1);
      goto LABEL_37;
    }
    while ( 1 )
    {
      if ( Type != 4 || cbData != 4 )
      {
        cbData = 4;
        goto LABEL_34;
      }
      v5 = *(_DWORD *)Data;
      v6 = wcstok_s((wchar_t *)v1, L":", &Context);
      v7 = (unsigned __int8)ConvertStringToTransportTypeEnum(v6);
      if ( Context )
        v4 = _o__wtoi();
      if ( (unsigned __int8)v7 >= 5u )
      {
        cchValueName = 0x3FFF;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_65085b59a2b6395dd5080b9566a77d67_Traceguids, v7);
        }
        goto LABEL_35;
      }
      if ( v4 > 0xFFFF || *(_DWORD *)_o__errno() == 34 )
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          goto LABEL_32;
        }
        v10 = 19;
        v11 = v4;
      }
      else
      {
        v19 = v4;
        v20 = v7;
        v21 = 0;
        v22 = v5;
        v23 = 0;
        v8 = ServerAlternativePortUpdate(12, &v19);
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_32;
        }
        v10 = 20;
        v11 = v8;
      }
      WPP_SF_d(v9[2], v10, WPP_65085b59a2b6395dd5080b9566a77d67_Traceguids, v11);
LABEL_32:
      ++v3;
LABEL_34:
      cchValueName = 0x3FFF;
LABEL_35:
      if ( RegEnumValueW(hKey, v3, (LPWSTR)v1, &cchValueName, 0, &Type, Data, &cbData) )
        goto LABEL_36;
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    LODWORD(v0) = WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_65085b59a2b6395dd5080b9566a77d67_Traceguids);
  }
LABEL_37:
  if ( hKey )
    LODWORD(v0) = RegCloseKey(hKey);
  return (int)v0;
}

```

## disassembly

```asm
0x180020708  push    rbp
0x18002070a  push    rbx
0x18002070b  push    rsi
0x18002070c  push    r12
0x18002070e  push    r13
0x180020710  push    r14
0x180020712  push    r15
0x180020714  lea     rbp, [rsp-27h]
0x180020719  sub     rsp, 90h
0x180020720  mov     rax, cs:__security_cookie
0x180020727  xor     rax, rsp
0x18002072a  mov     [rbp+57h+var_40], rax
0x18002072e  mov     edx, 7FFEh; uBytes
0x180020733  mov     [rbp+57h+hKey], 0
0x18002073b  mov     ecx, 40h ; '@'; uFlags
0x180020740  mov     [rbp+57h+cchValueName], 3FFFh
0x180020747  mov     [rbp+57h+Type], 0
0x18002074e  mov     dword ptr [rbp+57h+Data], 0
0x180020755  mov     [rbp+57h+cbData], 4
0x18002075c  mov     [rbp+57h+Context], 0
0x180020764  call    cs:__imp_LocalAlloc
0x18002076a  mov     rsi, rax
0x18002076d  test    rax, rax
0x180020770  jnz     short loc_1800207B5
0x180020772  mov     rcx, cs:WPP_GLOBAL_Control
0x180020779  lea     rbx, WPP_GLOBAL_Control
0x180020780  cmp     rcx, rbx
0x180020783  jz      loc_180020A15
0x180020789  test    byte ptr [rcx+1Ch], 1
0x18002078d  jz      loc_180020A15
0x180020793  cmp     byte ptr [rcx+19h], 1
0x180020797  jb      loc_180020A15
0x18002079d  mov     rcx, [rcx+10h]
0x1800207a1  lea     edx, [rax+10h]
0x1800207a4  lea     r8, WPP_65085b59a2b6395dd5080b9566a77d67_Traceguids
0x1800207ab  call    WPP_SF_
0x1800207b0  jmp     loc_180020A15
0x1800207b5  mov     [rsp+0C0h+lpdwDisposition], 0; lpdwDisposition
0x1800207be  lea     rax, [rbp+57h+hKey]
0x1800207c2  mov     [rsp+0C0h+phkResult], rax; phkResult
0x1800207c7  lea     rdx, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Services\\La"...
0x1800207ce  mov     [rsp+0C0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800207d7  xor     r9d, r9d; lpClass
0x1800207da  mov     [rsp+0C0h+samDesired], 1; samDesired
0x1800207e2  xor     r8d, r8d; Reserved
0x1800207e5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800207ec  mov     [rsp+0C0h+dwOptions], 0; dwOptions
0x1800207f4  call    cs:__imp_RegCreateKeyExW
0x1800207fa  test    eax, eax
0x1800207fc  jz      short loc_180020849
0x1800207fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180020805  lea     rbx, WPP_GLOBAL_Control
0x18002080c  cmp     rcx, rbx
0x18002080f  jz      loc_180020A0C
0x180020815  test    dword ptr [rcx+1Ch], 100h
0x18002081c  jz      loc_180020A0C
0x180020822  cmp     byte ptr [rcx+19h], 1
0x180020826  jb      loc_180020A0C
0x18002082c  mov     rcx, [rcx+10h]
0x180020830  lea     r8, WPP_65085b59a2b6395dd5080b9566a77d67_Traceguids
0x180020837  mov     edx, 11h
0x18002083c  mov     r9d, eax
0x18002083f  call    WPP_SF_d
0x180020844  jmp     loc_180020A0C
0x180020849  mov     rcx, [rbp+57h+hKey]; hKey
0x18002084d  lea     rax, [rbp+57h+cbData]
0x180020851  mov     [rsp+0C0h+phkResult], rax; lpcbData
0x180020856  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x18002085a  lea     rax, [rbp+57h+Data]
0x18002085e  xor     r12d, r12d
0x180020861  mov     [rsp+0C0h+lpSecurityAttributes], rax; lpData
0x180020866  mov     r8, rsi; lpValueName
0x180020869  lea     rax, [rbp+57h+Type]
0x18002086d  xor     edx, edx; dwIndex
0x18002086f  mov     qword ptr [rsp+0C0h+samDesired], rax; lpType
0x180020874  xor     r15d, r15d
0x180020877  mov     qword ptr [rsp+0C0h+dwOptions], r12; lpReserved
0x18002087c  call    cs:__imp_RegEnumValueW
0x180020882  test    eax, eax
0x180020884  jnz     loc_180020A0C
0x18002088a  lea     rbx, WPP_GLOBAL_Control
0x180020891  cmp     [rbp+57h+Type], 4
0x180020895  jnz     loc_1800209BE
0x18002089b  cmp     [rbp+57h+cbData], 4
0x18002089f  jnz     loc_1800209BE
0x1800208a5  mov     r13d, dword ptr [rbp+57h+Data]
0x1800208a9  lea     r8, [rbp+57h+Context]; Context
0x1800208ad  lea     rdx, asc_18004F560; ":"
0x1800208b4  mov     rcx, rsi; String
0x1800208b7  call    cs:__imp_wcstok_s
0x1800208bd  mov     rcx, rax
0x1800208c0  call    ConvertStringToTransportTypeEnum
0x1800208c5  mov     rcx, [rbp+57h+Context]
0x1800208c9  movzx   r14d, al
0x1800208cd  test    rcx, rcx
0x1800208d0  jz      short loc_1800208DB
0x1800208d2  call    cs:__imp__o__wtoi
0x1800208d8  mov     r15d, eax
0x1800208db  cmp     r14b, 5
0x1800208df  jb      short loc_18002092C
0x1800208e1  mov     [rbp+57h+cchValueName], 3FFFh
0x1800208e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800208ef  cmp     rcx, rbx
0x1800208f2  jz      loc_1800209CC
0x1800208f8  test    dword ptr [rcx+1Ch], 100h
0x1800208ff  jz      loc_1800209CC
0x180020905  cmp     byte ptr [rcx+19h], 1
0x180020909  jb      loc_1800209CC
0x18002090f  mov     rcx, [rcx+10h]
0x180020913  lea     r8, WPP_65085b59a2b6395dd5080b9566a77d67_Traceguids
0x18002091a  mov     r9d, r14d
0x18002091d  mov     edx, 12h
0x180020922  call    WPP_SF_d
0x180020927  jmp     loc_1800209CC
0x18002092c  cmp     r15d, 0FFFFh
0x180020933  ja      short loc_180020986
0x180020935  call    cs:__imp__o__errno
0x18002093b  cmp     dword ptr [rax], 22h ; '"'
0x18002093e  jz      short loc_180020986
0x180020940  xor     eax, eax
0x180020942  mov     [rbp+57h+var_50], r15w
0x180020947  lea     rdx, [rbp+57h+var_50]
0x18002094b  mov     [rbp+57h+var_4E], r14b
0x18002094f  mov     [rbp+57h+var_4D], al
0x180020952  mov     [rbp+57h+var_4C], r13d
0x180020956  lea     ecx, [rax+0Ch]
0x180020959  mov     [rbp+57h+var_48], eax
0x18002095c  call    ServerAlternativePortUpdate
0x180020961  mov     rcx, cs:WPP_GLOBAL_Control
0x180020968  cmp     rcx, rbx
0x18002096b  jz      short loc_1800209B9
0x18002096d  test    dword ptr [rcx+1Ch], 100h
0x180020974  jz      short loc_1800209B9
0x180020976  cmp     byte ptr [rcx+19h], 2
0x18002097a  jb      short loc_1800209B9
0x18002097c  mov     edx, 14h
0x180020981  mov     r9d, eax
0x180020984  jmp     short loc_1800209A9
0x180020986  mov     rcx, cs:WPP_GLOBAL_Control
0x18002098d  cmp     rcx, rbx
0x180020990  jz      short loc_1800209B9
0x180020992  test    dword ptr [rcx+1Ch], 100h
0x180020999  jz      short loc_1800209B9
0x18002099b  cmp     byte ptr [rcx+19h], 1
0x18002099f  jb      short loc_1800209B9
0x1800209a1  mov     edx, 13h
0x1800209a6  mov     r9d, r15d
0x1800209a9  mov     rcx, [rcx+10h]
0x1800209ad  lea     r8, WPP_65085b59a2b6395dd5080b9566a77d67_Traceguids
0x1800209b4  call    WPP_SF_d
0x1800209b9  inc     r12d
0x1800209bc  jmp     short loc_1800209C5
0x1800209be  mov     [rbp+57h+cbData], 4
0x1800209c5  mov     [rbp+57h+cchValueName], 3FFFh
0x1800209cc  mov     rcx, [rbp+57h+hKey]; hKey
0x1800209d0  lea     rax, [rbp+57h+cbData]
0x1800209d4  mov     [rsp+0C0h+phkResult], rax; lpcbData
0x1800209d9  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x1800209dd  lea     rax, [rbp+57h+Data]
0x1800209e1  mov     r8, rsi; lpValueName
0x1800209e4  mov     [rsp+0C0h+lpSecurityAttributes], rax; lpData
0x1800209e9  mov     edx, r12d; dwIndex
0x1800209ec  lea     rax, [rbp+57h+Type]
0x1800209f0  mov     qword ptr [rsp+0C0h+samDesired], rax; lpType
0x1800209f5  mov     qword ptr [rsp+0C0h+dwOptions], 0; lpReserved
0x1800209fe  call    cs:__imp_RegEnumValueW
0x180020a04  test    eax, eax
0x180020a06  jz      loc_180020891
0x180020a0c  mov     rcx, rsi; hMem
0x180020a0f  call    cs:__imp_LocalFree
0x180020a15  mov     rcx, [rbp+57h+hKey]; hKey
0x180020a19  test    rcx, rcx
0x180020a1c  jz      short loc_180020A24
0x180020a1e  call    cs:__imp_RegCloseKey
0x180020a24  mov     rcx, [rbp+57h+var_40]
0x180020a28  xor     rcx, rsp; StackCookie
0x180020a2b  call    __security_check_cookie
0x180020a30  add     rsp, 90h
0x180020a37  pop     r15
0x180020a39  pop     r14
0x180020a3b  pop     r13
0x180020a3d  pop     r12
0x180020a3f  pop     rsi
0x180020a40  pop     rbx
0x180020a41  pop     rbp
0x180020a42  retn
```
