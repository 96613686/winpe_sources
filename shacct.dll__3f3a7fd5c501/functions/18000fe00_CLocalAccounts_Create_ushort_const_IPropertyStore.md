# CLocalAccounts::Create(ushort const *,IPropertyStore * *)

- ea: `0x18000fe00`
- end: `0x1800100de`
- name: `?Create@CLocalAccounts@@UEAAJPEBGPEAPEAUIPropertyStore@@@Z`
- size: `734`
- prototype: `int(CLocalAccounts *__hidden this, const unsigned __int16 *, struct IPropertyStore **)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180002bf0`
- `0x1800037e0`
- `0x18000fe00`
- `0x1800126c0`
- `0x180012acc`
- `0x180013130`
- `0x1800131b0`
- `0x180017010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18000fe60`
- `ntdll!RtlInitUnicodeString` at `0x18000fe60`
- `PROPSYS!PropVariantToUInt32WithDefault` at `0x18000ff72`
- `PROPSYS!PropVariantToUInt32WithDefault` at `0x18000ff72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800100bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800100bf`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000fff0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000fffa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000fff0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000fffa`

## pseudocode

```c
__int64 __fastcall CLocalAccounts::Create(CLocalAccounts *this, const unsigned __int16 *a2, struct IPropertyStore **a3)
{
  int v6; // ebx
  int v7; // eax
  void *v8; // r14
  int Group; // eax
  __int64 v10; // rax
  int v11; // eax
  unsigned int v12; // r9d
  int v13; // r8d
  ULONG v14; // eax
  int v15; // r8d
  int v16; // eax
  unsigned int v17; // r9d
  char v18; // al
  int v19; // r8d
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-19h] BYREF
  PROPVARIANT pvar[2]; // [rsp+60h] [rbp-9h] BYREF
  __int64 v23; // [rsp+70h] [rbp+7h]
  PROPVARIANT propvarIn[2]; // [rsp+78h] [rbp+Fh] BYREF
  __int64 v25; // [rsp+88h] [rbp+1Fh]
  LPVOID pv; // [rsp+E0h] [rbp+77h] BYREF

  if ( !a3 || !a2 )
    return (unsigned int)-2147467261;
  pv = 0;
  *a3 = 0;
  v6 = CSGetAccountDomainSid(&pv);
  if ( v6 >= 0 )
  {
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, a2);
    v7 = (*(__int64 (__fastcall **)(CLocalAccounts *))(*(_QWORD *)this + 136LL))(this);
    v8 = pv;
    if ( v7 == 1 )
      Group = CSUpdateOrCreateUser(pv, &DestinationString, 0, 0, 0, 0);
    else
      Group = CSUpdateOrCreateGroup(pv, (__int64)&DestinationString, 0, 0, 0, 0, 0, 0, 0);
    v6 = Group;
    if ( Group < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v18 = (*(__int64 (__fastcall **)(CLocalAccounts *))(*(_QWORD *)this + 136LL))(this);
        WPP_SF_SdD(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, v19, (_DWORD)a2, v18, v6);
      }
      goto LABEL_26;
    }
    if ( (*(unsigned int (__fastcall **)(CLocalAccounts *))(*(_QWORD *)this + 136LL))(this) != 1 )
      goto LABEL_19;
    v10 = *(_QWORD *)this;
    pv = 0;
    v11 = (*(__int64 (__fastcall **)(CLocalAccounts *))(v10 + 136))(this);
    v6 = CSGetAccountPropertyStore(v8, a2, v11, v12, &pv);
    if ( v6 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, v13, (_DWORD)a2, v6);
      goto LABEL_26;
    }
    v25 = 0;
    *(_OWORD *)propvarIn = 0;
    v6 = (*(__int64 (__fastcall **)(LPVOID, __int128 *, PROPVARIANT *))(*(_QWORD *)pv + 40LL))(
           pv,
           &PKEY_SAM_UserAccountControl,
           propvarIn);
    if ( v6 >= 0 )
    {
      *(_OWORD *)pvar = 0;
      v23 = 0;
      v14 = PropVariantToUInt32WithDefault(propvarIn, 0);
      LOWORD(pvar[0]) = 19;
      LODWORD(pvar[1]) = v14 & 0xFFFFFFFE;
      v6 = (*(__int64 (__fastcall **)(LPVOID, __int128 *, PROPVARIANT *))(*(_QWORD *)pv + 48LL))(
             pv,
             &PKEY_SAM_UserAccountControl,
             pvar);
      if ( v6 >= 0 )
      {
        v6 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)pv + 56LL))(pv);
        if ( v6 < 0
          && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v15, (_DWORD)a2, v6);
        }
        PropVariantClear(pvar);
      }
      PropVariantClear(propvarIn);
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
    if ( v6 >= 0 )
    {
LABEL_19:
      v16 = (*(__int64 (__fastcall **)(CLocalAccounts *))(*(_QWORD *)this + 136LL))(this);
      v6 = CSGetAccountPropertyStore(v8, a2, v16, v17, a3);
    }
LABEL_26:
    CoTaskMemFree(v8);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000fe00  push    rbp
0x18000fe02  push    rbx
0x18000fe03  push    rsi
0x18000fe04  push    rdi
0x18000fe05  push    r14
0x18000fe07  push    r15
0x18000fe09  lea     rbp, [rsp-2Fh]
0x18000fe0e  sub     rsp, 98h
0x18000fe15  mov     r15, r8
0x18000fe18  mov     rsi, rdx
0x18000fe1b  mov     rdi, rcx
0x18000fe1e  test    r8, r8
0x18000fe21  jz      loc_1800100C7
0x18000fe27  test    rdx, rdx
0x18000fe2a  jz      loc_1800100C7
0x18000fe30  lea     rcx, [rbp+57h+pv]
0x18000fe34  mov     [rbp+57h+pv], 0
0x18000fe3c  mov     qword ptr [r8], 0
0x18000fe43  call    CSGetAccountDomainSid
0x18000fe48  mov     ebx, eax
0x18000fe4a  test    eax, eax
0x18000fe4c  js      loc_1800100CC
0x18000fe52  xorps   xmm0, xmm0
0x18000fe55  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18000fe59  mov     rdx, rsi; SourceString
0x18000fe5c  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18000fe60  call    cs:__imp_RtlInitUnicodeString
0x18000fe66  mov     rax, [rdi]
0x18000fe69  mov     rcx, rdi
0x18000fe6c  mov     rax, [rax+88h]
0x18000fe73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe78  mov     r14, [rbp+57h+pv]
0x18000fe7c  lea     rdx, [rbp+57h+DestinationString]; struct _UNICODE_STRING *
0x18000fe80  xor     r9d, r9d
0x18000fe83  xor     r8d, r8d
0x18000fe86  mov     rcx, r14; void *
0x18000fe89  cmp     eax, 1
0x18000fe8c  jnz     short loc_18000FE9F
0x18000fe8e  mov     [rsp+0C0h+var_98], r8d; int
0x18000fe93  mov     dword ptr [rsp+0C0h+var_A0], r8d; unsigned int
0x18000fe98  call    CSUpdateOrCreateUser
0x18000fe9d  jmp     short loc_18000FECD
0x18000fe9f  mov     dword ptr [rsp+0C0h+var_80], 0; char
0x18000fea7  mov     [rsp+0C0h+var_88], 0; unsigned int
0x18000feaf  mov     [rsp+0C0h+var_90], 0; int
0x18000feb7  mov     [rsp+0C0h+var_98], 0; unsigned int
0x18000febf  mov     [rsp+0C0h+var_A0], 0; unsigned __int16 **
0x18000fec8  call    CSUpdateOrCreateGroup
0x18000fecd  mov     ebx, eax
0x18000fecf  test    eax, eax
0x18000fed1  js      loc_180010071
0x18000fed7  mov     rax, [rdi]
0x18000feda  mov     rcx, rdi
0x18000fedd  mov     rax, [rax+88h]
0x18000fee4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fee9  cmp     eax, 1
0x18000feec  jnz     loc_180010018
0x18000fef2  mov     rax, [rdi]
0x18000fef5  mov     rcx, rdi
0x18000fef8  mov     [rbp+57h+pv], 0
0x18000ff00  mov     rax, [rax+88h]
0x18000ff07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff0c  lea     rcx, [rbp+57h+pv]
0x18000ff10  mov     r8d, eax
0x18000ff13  mov     [rsp+0C0h+var_A0], rcx
0x18000ff18  mov     rdx, rsi
0x18000ff1b  mov     rcx, r14
0x18000ff1e  call    CSGetAccountPropertyStore
0x18000ff23  mov     ebx, eax
0x18000ff25  test    eax, eax
0x18000ff27  js      loc_180010041
0x18000ff2d  mov     rcx, [rbp+57h+pv]
0x18000ff31  lea     r8, [rbp+57h+propvarIn]
0x18000ff35  xor     eax, eax
0x18000ff37  lea     rdx, PKEY_SAM_UserAccountControl
0x18000ff3e  mov     [rbp+57h+var_38], rax
0x18000ff42  xorps   xmm0, xmm0
0x18000ff45  movups  xmmword ptr [rbp+57h+propvarIn], xmm0
0x18000ff49  mov     rax, [rcx]
0x18000ff4c  mov     rax, [rax+28h]
0x18000ff50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff55  mov     ebx, eax
0x18000ff57  test    eax, eax
0x18000ff59  js      loc_180010000
0x18000ff5f  xorps   xmm0, xmm0
0x18000ff62  lea     rcx, [rbp+57h+propvarIn]; propvarIn
0x18000ff66  xor     eax, eax
0x18000ff68  xor     edx, edx; ulDefault
0x18000ff6a  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x18000ff6e  mov     [rbp+57h+var_50], rax
0x18000ff72  call    cs:__imp_PropVariantToUInt32WithDefault
0x18000ff78  mov     ecx, 13h
0x18000ff7d  lea     r8, [rbp+57h+pvar]
0x18000ff81  and     eax, 0FFFFFFFEh
0x18000ff84  mov     word ptr [rbp+57h+pvar], cx
0x18000ff88  mov     rcx, [rbp+57h+pv]
0x18000ff8c  lea     rdx, PKEY_SAM_UserAccountControl
0x18000ff93  mov     dword ptr [rbp+57h+pvar+8], eax
0x18000ff96  mov     rax, [rcx]
0x18000ff99  mov     rax, [rax+30h]
0x18000ff9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffa2  mov     ebx, eax
0x18000ffa4  test    eax, eax
0x18000ffa6  js      short loc_18000FFF6
0x18000ffa8  mov     rcx, [rbp+57h+pv]
0x18000ffac  mov     rax, [rcx]
0x18000ffaf  mov     rax, [rax+38h]
0x18000ffb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffb8  mov     ebx, eax
0x18000ffba  test    eax, eax
0x18000ffbc  jns     short loc_18000FFEC
0x18000ffbe  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ffc5  lea     rax, WPP_GLOBAL_Control
0x18000ffcc  cmp     rcx, rax
0x18000ffcf  jz      short loc_18000FFEC
0x18000ffd1  test    byte ptr [rcx+1Ch], 2
0x18000ffd5  jz      short loc_18000FFEC
0x18000ffd7  mov     rcx, [rcx+10h]
0x18000ffdb  mov     edx, 0Bh
0x18000ffe0  mov     r9, rsi
0x18000ffe3  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x18000ffe7  call    WPP_SF_SD
0x18000ffec  lea     rcx, [rbp+57h+pvar]; pvar
0x18000fff0  call    cs:__imp_PropVariantClear
0x18000fff6  lea     rcx, [rbp+57h+propvarIn]; pvar
0x18000fffa  call    cs:__imp_PropVariantClear
0x180010000  mov     rcx, [rbp+57h+pv]
0x180010004  mov     rax, [rcx]
0x180010007  mov     rax, [rax+10h]
0x18001000b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010010  test    ebx, ebx
0x180010012  js      loc_1800100BC
0x180010018  mov     rax, [rdi]
0x18001001b  mov     rcx, rdi
0x18001001e  mov     rax, [rax+88h]
0x180010025  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001002a  mov     r8d, eax
0x18001002d  mov     [rsp+0C0h+var_A0], r15
0x180010032  mov     rdx, rsi
0x180010035  mov     rcx, r14
0x180010038  call    CSGetAccountPropertyStore
0x18001003d  mov     ebx, eax
0x18001003f  jmp     short loc_1800100BC
0x180010041  mov     rcx, cs:WPP_GLOBAL_Control
0x180010048  lea     rax, WPP_GLOBAL_Control
0x18001004f  cmp     rcx, rax
0x180010052  jz      short loc_1800100BC
0x180010054  test    byte ptr [rcx+1Ch], 2
0x180010058  jz      short loc_1800100BC
0x18001005a  mov     rcx, [rcx+10h]
0x18001005e  mov     edx, 0Ch
0x180010063  mov     r9, rsi
0x180010066  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x18001006a  call    WPP_SF_SD
0x18001006f  jmp     short loc_1800100BC
0x180010071  mov     rcx, cs:WPP_GLOBAL_Control
0x180010078  lea     rax, WPP_GLOBAL_Control
0x18001007f  cmp     rcx, rax
0x180010082  jz      short loc_1800100BC
0x180010084  test    byte ptr [rcx+1Ch], 2
0x180010088  jz      short loc_1800100BC
0x18001008a  mov     rax, [rdi]
0x18001008d  mov     rcx, rdi
0x180010090  mov     rax, [rax+88h]
0x180010097  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001009c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800100a3  mov     edx, 0Dh
0x1800100a8  mov     [rsp+0C0h+var_98], ebx
0x1800100ac  mov     r9, rsi
0x1800100af  mov     dword ptr [rsp+0C0h+var_A0], eax
0x1800100b3  mov     rcx, [rcx+10h]
0x1800100b7  call    WPP_SF_SdD
0x1800100bc  mov     rcx, r14; pv
0x1800100bf  call    cs:__imp_CoTaskMemFree
0x1800100c5  jmp     short loc_1800100CC
0x1800100c7  mov     ebx, 80004003h
0x1800100cc  mov     eax, ebx
0x1800100ce  add     rsp, 98h
0x1800100d5  pop     r15
0x1800100d7  pop     r14
0x1800100d9  pop     rdi
0x1800100da  pop     rsi
0x1800100db  pop     rbx
0x1800100dc  pop     rbp
0x1800100dd  retn
```
