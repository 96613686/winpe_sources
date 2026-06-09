# CreateRemovedProductsList(CList<ushort *,ushort *> * *)

- ea: `0x180029720`
- end: `0x180029a7c`
- name: `?CreateRemovedProductsList@@YAJPEAPEAV?$CList@PEAGPEAG@@@Z`
- size: `860`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001d9e0`

## callees

- `0x180008e48`
- `0x180029158`
- `0x1800292bc`
- `0x180029720`
- `0x180029a84`
- `0x18002a6b4`
- `0x18003fbf2`
- `0x18003fc30`

## import_xrefs

- `msvcrt!wcsnlen` at `0x1800298c6`
- `msvcrt!wcsnlen` at `0x1800298c6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029999`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029999`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029970`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029970`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800298a3`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800298a3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800297e4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800297e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029a51`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029a51`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800298de`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800298de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800299e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800299e3`

## string_xrefs

- `0x1800297d3`: `SOFTWARE\Microsoft\Security Center\ProvidersMigration\WicaAvPaths`

## pseudocode

```c
__int64 __fastcall CreateRemovedProductsList(_QWORD *a1)
{
  _DWORD *v1; // rax
  _DWORD *v2; // rbx
  _DWORD *v3; // rcx
  _QWORD *v4; // rax
  int v5; // eax
  unsigned int v6; // edi
  unsigned int v7; // eax
  DWORD i; // r13d
  LSTATUS v9; // eax
  _WORD *v10; // r15
  unsigned __int64 v11; // rdx
  __int64 v12; // rax
  BYTE *v13; // rcx
  _WORD *v14; // r8
  _WORD *v15; // rcx
  _QWORD *v16; // r14
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchValueName; // [rsp+44h] [rbp-BCh] BYREF
  DWORD Type; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD *v22; // [rsp+58h] [rbp-A8h]
  wchar_t Data[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR ValueName[264]; // [rsp+270h] [rbp+170h] BYREF

  v22 = a1;
  *a1 = 0;
  hKey = 0;
  cchValueName = 0;
  cbData = 0;
  Type = 0;
  v1 = operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
  v2 = v1;
  if ( !v1 )
  {
    v6 = -2147024882;
    goto LABEL_41;
  }
  *v1 = 0;
  v3 = v1;
  v1[12] = 0;
  v4 = v1 + 14;
  *((_QWORD *)v2 + 8) = v4;
  *((_QWORD *)v2 + 9) = v4;
  *v4 = v4;
  v5 = CList<STATUSCHANGENOTIFICATION *,STATUSCHANGENOTIFICATION *>::Initialize(v3);
  v6 = v5;
  if ( v5 )
  {
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
LABEL_31:
    DeleteRemovedProductsList(v2);
    goto LABEL_41;
  }
  v6 = 0;
  v7 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Security Center\\ProvidersMigration\\WicaAvPaths",
         0,
         1u,
         &hKey);
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids, v7);
    }
    goto LABEL_31;
  }
  for ( i = 0; ; ++i )
  {
    cchValueName = 260;
    cbData = 520;
    memset_0(ValueName, 0, 0x208u);
    memset_0(Data, 0, 0x208u);
    v9 = RegEnumValueW(hKey, i, ValueName, &cchValueName, 0, &Type, (LPBYTE)Data, &cbData);
    if ( v9 )
      break;
    if ( Type == 1 && wcsnlen(Data, 0x104u) )
    {
      v10 = LocalAlloc(0x40u, cbData);
      if ( !v10 )
      {
        v6 = -2147024882;
        goto LABEL_31;
      }
      v11 = (unsigned __int64)cbData >> 1;
      if ( !v11 )
      {
        v6 = -2147024809;
        goto LABEL_29;
      }
      v12 = 2147483646;
      v13 = (BYTE *)Data;
      v14 = v10;
      do
      {
        if ( !v12 )
          break;
        if ( !*(_WORD *)v13 )
          break;
        *v14 = *(_WORD *)v13;
        v13 += 2;
        ++v14;
        --v12;
        --v11;
      }
      while ( v11 );
      v15 = v14 - 1;
      if ( v11 )
        v15 = v14;
      *v15 = 0;
      v6 = v11 == 0 ? 0x8007007A : 0;
      if ( !v11 )
        goto LABEL_29;
      v16 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
      if ( !v16 )
      {
        v6 = -2147467259;
LABEL_29:
        LocalFree(v10);
        goto LABEL_31;
      }
      EnterCriticalSection((LPCRITICAL_SECTION)(v2 + 2));
      *v16 = *((_QWORD *)v2 + 7);
      v16[1] = v2 + 14;
      *((_QWORD *)v2 + 7) = v16;
      *(_QWORD *)(*v16 + 8LL) = v16;
      v16[2] = v10;
      ++v2[12];
      LeaveCriticalSection((LPCRITICAL_SECTION)(v2 + 2));
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids, v10);
      }
    }
  }
  if ( v9 != 259 )
  {
    if ( v9 > 0 )
      v6 = (unsigned __int16)v9 | 0x80070000;
    else
      v6 = v9;
  }
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      31,
      WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids,
      (unsigned int)v2[12]);
  *v22 = v2;
LABEL_41:
  RegCloseKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x180029720  push    rbp
0x180029722  push    rbx
0x180029723  push    rsi
0x180029724  push    rdi
0x180029725  push    r12
0x180029727  push    r13
0x180029729  push    r14
0x18002972b  push    r15
0x18002972d  lea     rbp, [rsp-398h]
0x180029735  sub     rsp, 498h
0x18002973c  mov     rax, cs:__security_cookie
0x180029743  xor     rax, rsp
0x180029746  mov     [rbp+3D0h+var_50], rax
0x18002974d  xor     r14d, r14d
0x180029750  mov     [rsp+4D0h+var_478], rcx
0x180029755  mov     [rcx], r14
0x180029758  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002975f  mov     [rsp+4D0h+hKey], r14
0x180029764  mov     [rsp+4D0h+cchValueName], r14d
0x180029769  lea     ecx, [r14+50h]; unsigned __int64
0x18002976d  mov     [rsp+4D0h+cbData], r14d
0x180029772  mov     [rsp+4D0h+Type], r14d
0x180029777  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002977c  mov     rbx, rax
0x18002977f  test    rax, rax
0x180029782  jz      loc_180029A47
0x180029788  mov     [rax], r14d
0x18002978b  mov     rcx, rbx
0x18002978e  mov     [rax+30h], r14d
0x180029792  add     rax, 38h ; '8'
0x180029796  mov     [rbx+40h], rax
0x18002979a  mov     [rbx+48h], rax
0x18002979e  mov     [rax], rax
0x1800297a1  call    ?Initialize@?$CList@PEAUSTATUSCHANGENOTIFICATION@@PEAU1@@@QEAAJXZ; CList<STATUSCHANGENOTIFICATION *,STATUSCHANGENOTIFICATION *>::Initialize(void)
0x1800297a6  mov     edi, eax
0x1800297a8  test    eax, eax
0x1800297aa  jz      short loc_1800297C0
0x1800297ac  jle     loc_1800299F0
0x1800297b2  movzx   edi, ax
0x1800297b5  or      edi, 80070000h
0x1800297bb  jmp     loc_1800299F0
0x1800297c0  lea     rax, [rsp+4D0h+hKey]
0x1800297c5  mov     r9d, 1; samDesired
0x1800297cb  xor     r8d, r8d; ulOptions
0x1800297ce  mov     [rsp+4D0h+phkResult], rax; phkResult
0x1800297d3  lea     rdx, aSoftwareMicros_11; "SOFTWARE\\Microsoft\\Security Center\\P"...
0x1800297da  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800297e1  mov     edi, r14d
0x1800297e4  call    cs:__imp_RegOpenKeyExW
0x1800297ea  test    eax, eax
0x1800297ec  jz      short loc_18002982C
0x1800297ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800297f5  lea     r12, WPP_GLOBAL_Control
0x1800297fc  cmp     rcx, r12
0x1800297ff  jz      loc_1800299F0
0x180029805  test    byte ptr [rcx+1Ch], 4
0x180029809  jz      loc_1800299F0
0x18002980f  mov     rcx, [rcx+10h]
0x180029813  lea     r8, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids
0x18002981a  mov     edx, 1Dh
0x18002981f  mov     r9d, eax
0x180029822  call    WPP_SF_d
0x180029827  jmp     loc_1800299F0
0x18002982c  mov     r13d, r14d
0x18002982f  lea     r12, WPP_GLOBAL_Control
0x180029836  xor     edx, edx; Val
0x180029838  mov     [rsp+4D0h+cchValueName], 104h
0x180029840  mov     r8d, 208h; Size
0x180029846  mov     [rsp+4D0h+cbData], 208h
0x18002984e  lea     rcx, [rbp+3D0h+ValueName]; void *
0x180029855  call    memset_0
0x18002985a  xor     edx, edx; Val
0x18002985c  lea     rcx, [rsp+4D0h+Data]; void *
0x180029861  mov     r8d, 208h; Size
0x180029867  call    memset_0
0x18002986c  mov     rcx, [rsp+4D0h+hKey]; hKey
0x180029871  lea     rax, [rsp+4D0h+cbData]
0x180029876  mov     [rsp+4D0h+lpcbData], rax; lpcbData
0x18002987b  lea     r9, [rsp+4D0h+cchValueName]; lpcchValueName
0x180029880  lea     rax, [rsp+4D0h+Data]
0x180029885  mov     edx, r13d; dwIndex
0x180029888  mov     [rsp+4D0h+lpData], rax; lpData
0x18002988d  lea     r8, [rbp+3D0h+ValueName]; lpValueName
0x180029894  lea     rax, [rsp+4D0h+Type]
0x180029899  mov     [rsp+4D0h+lpType], rax; lpType
0x18002989e  mov     [rsp+4D0h+phkResult], r14; lpReserved
0x1800298a3  call    cs:__imp_RegEnumValueW
0x1800298a9  test    eax, eax
0x1800298ab  jnz     loc_1800299FA
0x1800298b1  cmp     [rsp+4D0h+Type], 1
0x1800298b6  jnz     loc_1800299CC
0x1800298bc  mov     edx, 104h; MaxCount
0x1800298c1  lea     rcx, [rsp+4D0h+Data]; Source
0x1800298c6  call    cs:__imp_wcsnlen
0x1800298cc  test    rax, rax
0x1800298cf  jz      loc_1800299CC
0x1800298d5  mov     edx, [rsp+4D0h+cbData]; uBytes
0x1800298d9  mov     ecx, 40h ; '@'; uFlags
0x1800298de  call    cs:__imp_LocalAlloc
0x1800298e4  mov     r15, rax
0x1800298e7  test    rax, rax
0x1800298ea  jz      loc_1800299EB
0x1800298f0  mov     edx, [rsp+4D0h+cbData]
0x1800298f4  shr     rdx, 1
0x1800298f7  jz      loc_1800299DB
0x1800298fd  mov     eax, 7FFFFFFEh
0x180029902  lea     rcx, [rsp+4D0h+Data]
0x180029907  mov     r8, r15
0x18002990a  test    rax, rax
0x18002990d  jz      short loc_18002992E
0x18002990f  movzx   r9d, word ptr [rcx]
0x180029913  test    r9w, r9w
0x180029917  jz      short loc_18002992E
0x180029919  mov     [r8], r9w
0x18002991d  add     rcx, 2
0x180029921  add     r8, 2
0x180029925  dec     rax
0x180029928  sub     rdx, 1
0x18002992c  jnz     short loc_18002990A
0x18002992e  mov     rax, rdx
0x180029931  lea     rcx, [r8-2]
0x180029935  neg     rax
0x180029938  sbb     edi, edi
0x18002993a  test    rdx, rdx
0x18002993d  not     edi
0x18002993f  cmovnz  rcx, r8
0x180029943  mov     [rcx], r14w
0x180029947  and     edi, 8007007Ah
0x18002994d  js      loc_1800299E0
0x180029953  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002995a  mov     ecx, 18h; unsigned __int64
0x18002995f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180029964  mov     r14, rax
0x180029967  test    rax, rax
0x18002996a  jz      short loc_1800299D4
0x18002996c  lea     rcx, [rbx+8]; lpCriticalSection
0x180029970  call    cs:__imp_EnterCriticalSection
0x180029976  lea     rdx, [rbx+38h]
0x18002997a  mov     rax, [rdx]
0x18002997d  lea     rcx, [rbx+8]; lpCriticalSection
0x180029981  mov     [r14], rax
0x180029984  mov     [r14+8], rdx
0x180029988  mov     [rdx], r14
0x18002998b  mov     rax, [r14]
0x18002998e  mov     [rax+8], r14
0x180029992  mov     [r14+10h], r15
0x180029996  inc     dword ptr [rbx+30h]
0x180029999  call    cs:__imp_LeaveCriticalSection
0x18002999f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800299a6  cmp     rcx, r12
0x1800299a9  jz      short loc_1800299C9
0x1800299ab  test    byte ptr [rcx+1Ch], 4
0x1800299af  jz      short loc_1800299C9
0x1800299b1  mov     rcx, [rcx+10h]
0x1800299b5  lea     r8, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids
0x1800299bc  mov     edx, 1Eh
0x1800299c1  mov     r9, r15
0x1800299c4  call    WPP_SF_S
0x1800299c9  xor     r14d, r14d
0x1800299cc  inc     r13d
0x1800299cf  jmp     loc_180029836
0x1800299d4  mov     edi, 80004005h
0x1800299d9  jmp     short loc_1800299E0
0x1800299db  mov     edi, 80070057h
0x1800299e0  mov     rcx, r15; hMem
0x1800299e3  call    cs:__imp_LocalFree
0x1800299e9  jmp     short loc_1800299F0
0x1800299eb  mov     edi, 8007000Eh
0x1800299f0  mov     rcx, rbx; Block
0x1800299f3  call    ?DeleteRemovedProductsList@@YAXPEAV?$CList@PEAGPEAG@@@Z; DeleteRemovedProductsList(CList<ushort *,ushort *> *)
0x1800299f8  jmp     short loc_180029A4C
0x1800299fa  cmp     eax, 103h
0x1800299ff  jz      short loc_180029A12
0x180029a01  test    eax, eax
0x180029a03  jg      short loc_180029A09
0x180029a05  mov     edi, eax
0x180029a07  jmp     short loc_180029A12
0x180029a09  movzx   edi, ax
0x180029a0c  or      edi, 80070000h
0x180029a12  mov     rcx, cs:WPP_GLOBAL_Control
0x180029a19  cmp     rcx, r12
0x180029a1c  jz      short loc_180029A3D
0x180029a1e  test    byte ptr [rcx+1Ch], 4
0x180029a22  jz      short loc_180029A3D
0x180029a24  mov     r9d, [rbx+30h]
0x180029a28  lea     r8, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids
0x180029a2f  mov     rcx, [rcx+10h]
0x180029a33  mov     edx, 1Fh
0x180029a38  call    WPP_SF_d
0x180029a3d  mov     rax, [rsp+4D0h+var_478]
0x180029a42  mov     [rax], rbx
0x180029a45  jmp     short loc_180029A4C
0x180029a47  mov     edi, 8007000Eh
0x180029a4c  mov     rcx, [rsp+4D0h+hKey]; hKey
0x180029a51  call    cs:__imp_RegCloseKey
0x180029a57  mov     eax, edi
0x180029a59  mov     rcx, [rbp+3D0h+var_50]
0x180029a60  xor     rcx, rsp; StackCookie
0x180029a63  call    __security_check_cookie
0x180029a68  add     rsp, 498h
0x180029a6f  pop     r15
0x180029a71  pop     r14
0x180029a73  pop     r13
0x180029a75  pop     r12
0x180029a77  pop     rdi
0x180029a78  pop     rsi
0x180029a79  pop     rbx
0x180029a7a  pop     rbp
0x180029a7b  retn
```
