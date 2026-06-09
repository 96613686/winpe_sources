# CSecurityManager::MapUrlToZonePrivate(ushort const *,ulong *,ulong,ulong,ulong *)

- ea: `0x1800800d8`
- end: `0x1800803d0`
- name: `?MapUrlToZonePrivate@CSecurityManager@@AEAAJPEBGPEAKKK1@Z`
- size: `760`
- prototype: `__int64 __fastcall(CSecurityManager *__hidden this, wchar_t *Source, unsigned int *, unsigned int, unsigned int, unsigned int *)`
- caller_count: `3`
- callee_count: `13`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x1800800b0`
- `0x1800a4aa0`
- `0x180109320`

## callees

- `0x180018c50`
- `0x18001db50`
- `0x18002fee0`
- `0x18003e100`
- `0x18005bb74`
- `0x180070da0`
- `0x18007823c`
- `0x1800800d8`
- `0x180080e44`
- `0x1800940e4`
- `0x18009fdd0`
- `0x180109e30`
- `0x180129010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1800802ab`
- `msvcrt!_wcsnicmp` at `0x1800802cb`
- `msvcrt!_wcsnicmp` at `0x1800802ab`
- `msvcrt!_wcsnicmp` at `0x1800802cb`
- `msvcrt!wcscpy_s` at `0x180080276`
- `msvcrt!wcscpy_s` at `0x180080276`
- `iertutil!CreateUri` at `0x18008015b`
- `iertutil!CreateUri` at `0x180080317`
- `iertutil!CreateUri` at `0x18008015b`
- `iertutil!CreateUri` at `0x180080317`
- `iertutil!IsDriveAndNotIPv6` at `0x1800802de`
- `iertutil!IsDriveAndNotIPv6` at `0x1800802de`
- `iertutil!__imp_?IECompatLogURICreationFailure@@YAXPEBGJ@Z` at `0x1800803a6`
- `iertutil!__imp_?IECompatLogURICreationFailure@@YAXPEBGJ@Z` at `0x1800803a6`

## pseudocode

```c
__int64 __fastcall CSecurityManager::MapUrlToZonePrivate(
        CSecurityManager *this,
        wchar_t *Source,
        unsigned int *a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int *a6)
{
  unsigned int *v10; // rbx
  unsigned int v11; // r12d
  DWORD v12; // eax
  int ZoneFromUrlPrivateForWebPlatform; // edi
  IUri *v14; // rbx
  __int64 v15; // rcx
  __int64 v16; // rax
  unsigned int v17; // ebx
  wchar_t *v18; // rbx
  const wchar_t *v19; // rcx
  DWORD v20; // eax
  struct IUri *v21; // rdx
  IUri *v22; // rbx
  char v23; // al
  wchar_t *String1; // [rsp+40h] [rbp-49h] BYREF
  IUri *v26; // [rsp+48h] [rbp-41h] BYREF
  _QWORD v27[2]; // [rsp+50h] [rbp-39h] BYREF
  unsigned int v28; // [rsp+60h] [rbp-29h]
  _QWORD v29[2]; // [rsp+70h] [rbp-19h] BYREF
  unsigned int v30; // [rsp+80h] [rbp-9h]
  unsigned int v31; // [rsp+84h] [rbp-5h]
  unsigned int *v32; // [rsp+88h] [rbp-1h]
  IUri *ppURI; // [rsp+F0h] [rbp+67h] BYREF

  if ( a3 )
  {
    v10 = a6;
    *a3 = -1;
    if ( v10 )
      *v10 = 0;
    if ( Source )
    {
      v11 = a5;
      if ( *((_QWORD *)this + 12) )
      {
        ppURI = 0;
        v12 = HelperAddUriDefaultFlags(50342784, (a4 & 0x80 | 0x100) >> 6);
        ZoneFromUrlPrivateForWebPlatform = CreateUri(Source, v12, 0, &ppURI);
        if ( ZoneFromUrlPrivateForWebPlatform >= 0 )
        {
          v14 = ppURI;
          ZoneFromUrlPrivateForWebPlatform = GetZoneFromUrlPrivateForWebPlatform(
                                               *((_QWORD *)this + 12),
                                               (__int64)ppURI,
                                               (__int64)a3,
                                               a4,
                                               0,
                                               0,
                                               v11,
                                               a6);
          ((void (__fastcall *)(IUri *))v14->lpVtbl->Release)(v14);
          v10 = a6;
        }
      }
      else
      {
        v15 = *((_QWORD *)this + 11);
        if ( !v15 )
        {
          v15 = *((_QWORD *)this + 10);
          if ( !v15 )
          {
            v15 = *((_QWORD *)this + 9);
            if ( !v15 )
              goto LABEL_13;
          }
        }
        ZoneFromUrlPrivateForWebPlatform = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 40LL))(v15);
      }
      if ( ZoneFromUrlPrivateForWebPlatform != -2146697199 )
        return (unsigned int)ZoneFromUrlPrivateForWebPlatform;
LABEL_13:
      v29[0] = Source;
      v29[1] = a3;
      v30 = a4;
      v31 = v11;
      v32 = v10;
      v27[0] = Source;
      v27[1] = a3;
      v28 = a4;
      ZoneFromUrlPrivateForWebPlatform = DelegateToPermanentInternetSecurityManager__lambda_c9c11ee15d238092b8212aff358d1032___lambda_5d01d400cbea2bfdeac2e9d78a9e82ef_(
                                           (__int64)v27,
                                           (__int64)v29);
      if ( ZoneFromUrlPrivateForWebPlatform == -2146697199 )
      {
        v26 = 0;
        v16 = -1;
        do
          ++v16;
        while ( Source[v16] );
        LODWORD(ppURI) = v16 + 1;
        v17 = v16 + 1;
        String1 = (wchar_t *)operator new(saturated_mul((unsigned int)(v16 + 1), 2u));
        wcscpy_s(String1, v17, Source);
        ConvertFileUrlToDOSPath((PCWSTR *)&String1, (unsigned int *)&ppURI);
        v18 = String1;
        NormalizePathPrefix((__int64)String1, (unsigned int)ppURI);
        if ( !_wcsnicmp(v19, L"\\\\.\\", 4u) || !_wcsnicmp(v18, L"\\\\;", 3u) || IsDriveAndNotIPv6(v18) )
        {
          GetFullPathNameWWrapper((LPCWSTR *)&String1, (unsigned int *)&ppURI);
          v18 = String1;
        }
        v20 = HelperAddUriDefaultFlags(50342784, (a4 & 0x80 | 0x100) >> 6);
        ZoneFromUrlPrivateForWebPlatform = CreateUri(v18, v20, 0, &v26);
        operator delete(v18);
        if ( ZoneFromUrlPrivateForWebPlatform < 0 )
        {
          if ( g_cmptlgs != 1 && (unsigned int)IECompatLoggingEnabled() )
            IECompatLogURICreationFailure(Source, ZoneFromUrlPrivateForWebPlatform);
        }
        else
        {
          v21 = v26;
          v22 = v26;
          if ( (v11 & 0x40000000) != 0 )
          {
            v23 = IsAllowedSchemeForProxyAgnostic(v26);
            v21 = v26;
            if ( !v23 )
              v11 &= ~0x40000000u;
          }
          ZoneFromUrlPrivateForWebPlatform = CSecurityManager::GetZoneFromUriInternal(this, v21, a3, a4, 0, 0, v11, a6);
          ((void (__fastcall *)(IUri *))v22->lpVtbl->Release)(v22);
        }
      }
      return (unsigned int)ZoneFromUrlPrivateForWebPlatform;
    }
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800800d8  push    rbp
0x1800800da  push    rbx
0x1800800db  push    rsi
0x1800800dc  push    rdi
0x1800800dd  push    r12
0x1800800df  push    r13
0x1800800e1  push    r14
0x1800800e3  push    r15
0x1800800e5  lea     rbp, [rsp-0Fh]
0x1800800ea  sub     rsp, 98h
0x1800800f1  xor     eax, eax
0x1800800f3  mov     r15d, r9d
0x1800800f6  mov     r14, r8
0x1800800f9  mov     rsi, rdx
0x1800800fc  mov     r13, rcx
0x1800800ff  test    r8, r8
0x180080102  jz      loc_1800803B6
0x180080108  mov     rbx, [rbp+47h+arg_28]
0x18008010c  mov     dword ptr [r8], 0FFFFFFFFh
0x180080113  test    rbx, rbx
0x180080116  jz      short loc_18008011A
0x180080118  mov     [rbx], eax
0x18008011a  test    rsi, rsi
0x18008011d  jz      loc_1800803B6
0x180080123  mov     r12d, [rbp+47h+arg_20]
0x180080127  cmp     [rcx+60h], rax
0x18008012b  jz      loc_1800801B4
0x180080131  mov     edx, r15d
0x180080134  mov     [rbp+47h+ppURI], rax
0x180080138  and     edx, 80h
0x18008013e  mov     ecx, 3002B80h; unsigned int
0x180080143  bts     edx, 8
0x180080147  shr     edx, 6; unsigned int
0x18008014a  call    ?HelperAddUriDefaultFlags@@YAKKK@Z; HelperAddUriDefaultFlags(ulong,ulong)
0x18008014f  mov     edx, eax; dwFlags
0x180080151  lea     r9, [rbp+47h+ppURI]; ppURI
0x180080155  mov     rcx, rsi; pwzURI
0x180080158  xor     r8d, r8d; dwReserved
0x18008015b  call    cs:__imp_CreateUri
0x180080162  nop     dword ptr [rax+rax+00h]
0x180080167  xor     ecx, ecx
0x180080169  mov     edi, eax
0x18008016b  test    eax, eax
0x18008016d  js      short loc_1800801DD
0x18008016f  mov     rax, [rbp+47h+arg_28]
0x180080173  mov     r9d, r15d
0x180080176  mov     rbx, [rbp+47h+ppURI]
0x18008017a  mov     r8, r14
0x18008017d  mov     [rsp+0D0h+var_98], rax
0x180080182  mov     rdx, rbx
0x180080185  mov     [rsp+0D0h+var_A0], r12d
0x18008018a  mov     [rsp+0D0h+var_A8], rcx
0x18008018f  mov     [rsp+0D0h+var_B0], rcx
0x180080194  mov     rcx, [r13+60h]
0x180080198  call    GetZoneFromUrlPrivateForWebPlatform
0x18008019d  mov     edi, eax
0x18008019f  mov     rcx, rbx
0x1800801a2  mov     rax, [rbx]
0x1800801a5  mov     rax, [rax+10h]
0x1800801a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800801ae  mov     rbx, [rbp+47h+arg_28]
0x1800801b2  jmp     short loc_1800801DD
0x1800801b4  mov     rcx, [rcx+58h]
0x1800801b8  test    rcx, rcx
0x1800801bb  jnz     short loc_1800801CF
0x1800801bd  mov     rcx, [r13+50h]
0x1800801c1  test    rcx, rcx
0x1800801c4  jnz     short loc_1800801CF
0x1800801c6  mov     rcx, [r13+48h]
0x1800801ca  test    rcx, rcx
0x1800801cd  jz      short loc_1800801E9
0x1800801cf  mov     rax, [rcx]
0x1800801d2  mov     rax, [rax+28h]
0x1800801d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800801db  mov     edi, eax
0x1800801dd  cmp     edi, 800C0011h
0x1800801e3  jnz     loc_1800803B2
0x1800801e9  mov     eax, [rbp+47h+var_6C]
0x1800801ec  lea     rdx, [rbp+47h+var_60]
0x1800801f0  lea     rcx, [rbp+47h+var_80]
0x1800801f4  mov     [rbp+47h+var_6C], eax
0x1800801f7  mov     [rbp+47h+var_60], rsi
0x1800801fb  mov     [rbp+47h+var_58], r14
0x1800801ff  mov     [rbp+47h+var_50], r15d
0x180080203  mov     [rbp+47h+var_4C], r12d
0x180080207  mov     [rbp+47h+var_48], rbx
0x18008020b  mov     [rbp+47h+var_80], rsi
0x18008020f  mov     [rbp+47h+var_78], r14
0x180080213  mov     [rbp+47h+var_70], r15d
0x180080217  call    DelegateToPermanentInternetSecurityManager__lambda_c9c11ee15d238092b8212aff358d1032___lambda_5d01d400cbea2bfdeac2e9d78a9e82ef___; DelegateToPermanentInternetSecurityManager__lambda_c9c11ee15d238092b8212aff358d1032___lambda_5d01d400cbea2bfdeac2e9d78a9e82ef_
0x18008021c  mov     edi, eax
0x18008021e  cmp     eax, 800C0011h
0x180080223  jnz     loc_1800803B2
0x180080229  xor     ecx, ecx
0x18008022b  mov     edi, r15d
0x18008022e  and     edi, 80h
0x180080234  mov     [rbp+47h+var_88], rcx
0x180080238  bts     edi, 8
0x18008023c  shr     edi, 6
0x18008023f  or      r8, 0FFFFFFFFFFFFFFFFh
0x180080243  mov     rax, r8
0x180080246  inc     rax
0x180080249  cmp     [rsi+rax*2], cx
0x18008024d  jnz     short loc_180080246
0x18008024f  inc     eax
0x180080251  mov     dword ptr [rbp+47h+ppURI], eax
0x180080254  mov     ebx, eax
0x180080256  mov     eax, 2
0x18008025b  mul     rbx
0x18008025e  cmovb   rax, r8
0x180080262  mov     rcx, rax; Size
0x180080265  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008026a  mov     r8, rsi; Source
0x18008026d  mov     [rbp+47h+String1], rax
0x180080271  mov     edx, ebx; SizeInWords
0x180080273  mov     rcx, rax; Destination
0x180080276  call    cs:__imp_wcscpy_s
0x18008027d  nop     dword ptr [rax+rax+00h]
0x180080282  lea     rdx, [rbp+47h+ppURI]; unsigned int *
0x180080286  lea     rcx, [rbp+47h+String1]; unsigned __int16 **
0x18008028a  call    ?ConvertFileUrlToDOSPath@@YAXAEAPEAGAEAK@Z; ConvertFileUrlToDOSPath(ushort * &,ulong &)
0x18008028f  mov     rbx, [rbp+47h+String1]
0x180080293  mov     edx, dword ptr [rbp+47h+ppURI]
0x180080296  mov     rcx, rbx
0x180080299  call    NormalizePathPrefix
0x18008029e  mov     r8d, 4; MaxCount
0x1800802a4  lea     rdx, ?DosDevicePrefix@@3QBGB; "\\\\.\\"
0x1800802ab  call    cs:__imp__wcsnicmp
0x1800802b2  nop     dword ptr [rax+rax+00h]
0x1800802b7  test    eax, eax
0x1800802b9  jz      short loc_1800802EE
0x1800802bb  mov     r8d, 3; MaxCount
0x1800802c1  lea     rdx, ?RedirectorPrefix@@3QBGB; "\\\\;"
0x1800802c8  mov     rcx, rbx; String1
0x1800802cb  call    cs:__imp__wcsnicmp
0x1800802d2  nop     dword ptr [rax+rax+00h]
0x1800802d7  test    eax, eax
0x1800802d9  jz      short loc_1800802EE
0x1800802db  mov     rcx, rbx
0x1800802de  call    cs:__imp_?IsDriveAndNotIPv6@@YAHPEBG@Z; IsDriveAndNotIPv6(ushort const *)
0x1800802e5  nop     dword ptr [rax+rax+00h]
0x1800802ea  test    eax, eax
0x1800802ec  jz      short loc_1800802FF
0x1800802ee  lea     rdx, [rbp+47h+ppURI]; unsigned int *
0x1800802f2  lea     rcx, [rbp+47h+String1]; unsigned __int16 **
0x1800802f6  call    ?GetFullPathNameWWrapper@@YAXAEAPEAGAEAK@Z; GetFullPathNameWWrapper(ushort * &,ulong &)
0x1800802fb  mov     rbx, [rbp+47h+String1]
0x1800802ff  mov     edx, edi; unsigned int
0x180080301  mov     ecx, 3002B80h; unsigned int
0x180080306  call    ?HelperAddUriDefaultFlags@@YAKKK@Z; HelperAddUriDefaultFlags(ulong,ulong)
0x18008030b  mov     edx, eax; dwFlags
0x18008030d  lea     r9, [rbp+47h+var_88]; ppURI
0x180080311  mov     rcx, rbx; pwzURI
0x180080314  xor     r8d, r8d; dwReserved
0x180080317  call    cs:__imp_CreateUri
0x18008031e  nop     dword ptr [rax+rax+00h]
0x180080323  mov     rcx, rbx; void *
0x180080326  mov     edi, eax
0x180080328  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18008032d  test    edi, edi
0x18008032f  js      short loc_18008038F
0x180080331  mov     rdx, [rbp+47h+var_88]
0x180080335  mov     rbx, rdx
0x180080338  bt      r12d, 1Eh
0x18008033d  jnb     short loc_180080354
0x18008033f  mov     rcx, rdx; struct IUri *
0x180080342  call    ?IsAllowedSchemeForProxyAgnostic@@YA_NPEAUIUri@@@Z; IsAllowedSchemeForProxyAgnostic(IUri *)
0x180080347  mov     rdx, [rbp+47h+var_88]; struct IUri *
0x18008034b  test    al, al
0x18008034d  jnz     short loc_180080354
0x18008034f  btr     r12d, 1Eh
0x180080354  mov     rax, [rbp+47h+arg_28]
0x180080358  mov     r9d, r15d; unsigned int
0x18008035b  mov     [rsp+0D0h+var_98], rax; unsigned int *
0x180080360  mov     r8, r14; unsigned int *
0x180080363  xor     eax, eax
0x180080365  mov     [rsp+0D0h+var_A0], r12d; unsigned int
0x18008036a  mov     [rsp+0D0h+var_A8], rax; unsigned int *
0x18008036f  mov     rcx, r13; this
0x180080372  mov     [rsp+0D0h+var_B0], rax; unsigned __int16 **
0x180080377  call    ?GetZoneFromUriInternal@CSecurityManager@@AEAAJPEAUIUri@@PEAKKPEAPEAG1K1@Z; CSecurityManager::GetZoneFromUriInternal(IUri *,ulong *,ulong,ushort * *,ulong *,ulong,ulong *)
0x18008037c  mov     edi, eax
0x18008037e  mov     rcx, rbx
0x180080381  mov     rax, [rbx]
0x180080384  mov     rax, [rax+10h]
0x180080388  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008038d  jmp     short loc_1800803B2
0x18008038f  cmp     cs:?g_cmptlgs@@3W4CMPTLGS@@A, 1; CMPTLGS g_cmptlgs
0x180080396  jz      short loc_1800803B2
0x180080398  call    ?IECompatLoggingEnabled@@YAHXZ; IECompatLoggingEnabled(void)
0x18008039d  test    eax, eax
0x18008039f  jz      short loc_1800803B2
0x1800803a1  mov     edx, edi
0x1800803a3  mov     rcx, rsi
0x1800803a6  call    cs:__imp_?IECompatLogURICreationFailure@@YAXPEBGJ@Z; IECompatLogURICreationFailure(ushort const *,long)
0x1800803ad  nop     dword ptr [rax+rax+00h]
0x1800803b2  mov     eax, edi
0x1800803b4  jmp     short loc_1800803BB
0x1800803b6  mov     eax, 80070057h
0x1800803bb  add     rsp, 98h
0x1800803c2  pop     r15
0x1800803c4  pop     r14
0x1800803c6  pop     r13
0x1800803c8  pop     r12
0x1800803ca  pop     rdi
0x1800803cb  pop     rsi
0x1800803cc  pop     rbx
0x1800803cd  pop     rbp
0x1800803ce  retn
```
