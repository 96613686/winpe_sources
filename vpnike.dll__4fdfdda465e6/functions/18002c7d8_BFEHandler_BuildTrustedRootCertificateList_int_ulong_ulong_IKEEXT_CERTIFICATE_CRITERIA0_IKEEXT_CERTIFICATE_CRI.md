# BFEHandler::BuildTrustedRootCertificateList(int,ulong &,ulong &,IKEEXT_CERTIFICATE_CRITERIA0_ * *,IKEEXT_CERTIFICATE_CRITERIA0_ * *)

- ea: `0x18002c7d8`
- end: `0x18002ccbc`
- name: `?BuildTrustedRootCertificateList@BFEHandler@@KAKHAEAK0PEAPEAUIKEEXT_CERTIFICATE_CRITERIA0_@@1@Z`
- size: `1252`
- prototype: `__int64 __fastcall(int, unsigned int *, unsigned int *, struct IKEEXT_CERTIFICATE_CRITERIA0_ **, struct IKEEXT_CERTIFICATE_CRITERIA0_ **)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180032690`
- `0x18003bdb4`

## callees

- `0x180007590`
- `0x1800077bc`
- `0x180007894`
- `0x18002c7d8`
- `0x180030880`
- `0x180030930`
- `0x180067dac`
- `0x180074cc8`
- `0x1800751f4`
- `0x1800768d4`
- `0x180076b60`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002c920`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002c920`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002cc40`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002cc40`

## string_xrefs

- `0x18002c946`: `OpenIkev2ConfigKey failed: %d`
- `0x18002c9fd`: `GetIkev2ConfigParams failed: %d`
- `0x18002c912`: `SYSTEM\CurrentControlSet\Services\RemoteAccess\Parameters\Ikev2`

## pseudocode

```c
__int64 __fastcall BFEHandler::BuildTrustedRootCertificateList(
        int a1,
        unsigned int *a2,
        unsigned int *a3,
        struct IKEEXT_CERTIFICATE_CRITERIA0_ **a4,
        struct IKEEXT_CERTIFICATE_CRITERIA0_ **a5)
{
  struct IKEEXT_CERTIFICATE_CRITERIA0_ **v5; // r15
  _DWORD *v9; // rbx
  unsigned int v10; // eax
  __int64 v11; // r9
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  unsigned int Ikev2ConfigParams; // eax
  unsigned int v15; // r8d
  unsigned int i; // eax
  __int64 v17; // rdx
  unsigned int v18; // eax
  HKEY v19; // rcx
  unsigned int v20; // ebx
  unsigned int v22; // [rsp+80h] [rbp-80h] BYREF
  DWORD dwDisposition; // [rsp+84h] [rbp-7Ch] BYREF
  HKEY hKey; // [rsp+88h] [rbp-78h] BYREF
  __int64 v25; // [rsp+90h] [rbp-70h] BYREF
  __int128 v26; // [rsp+98h] [rbp-68h]
  __int128 v27; // [rsp+A8h] [rbp-58h]
  __int64 v28; // [rsp+B8h] [rbp-48h]
  int v29; // [rsp+C0h] [rbp-40h]
  int v30; // [rsp+C4h] [rbp-3Ch]
  _BYTE v31[20]; // [rsp+D0h] [rbp-30h] BYREF
  int v32; // [rsp+E4h] [rbp-1Ch]
  __int64 v33; // [rsp+E8h] [rbp-18h]
  unsigned int v34; // [rsp+110h] [rbp+10h]
  __int64 v35; // [rsp+118h] [rbp+18h]
  int v36; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v37[2044]; // [rsp+144h] [rbp+44h] BYREF

  v5 = a4;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    LOBYTE(a4) = a1 != 0;
    WPP_SF_c(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, &WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids, a4);
  }
  v36 = 0;
  memset_0(v37, 0, sizeof(v37));
  v22 = 0;
  memset_0(v31, 0, 0x68u);
  hKey = 0;
  v9 = 0;
  v26 = 0;
  v25 = 0;
  v27 = 0;
  v28 = 0;
  v29 = -1;
  v30 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v25,
      L"BFEHandler::BuildTrustedRootCertificateList",
      &v22,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunction);
  memset_0(v31, 0, 0x68u);
  dwDisposition = 0;
  v10 = RegCreateKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Services\\RemoteAccess\\Parameters\\Ikev2",
          0,
          0,
          0,
          0xF003Fu,
          0,
          &hKey,
          &dwDisposition);
  v11 = v10;
  v22 = v10;
  if ( v10 )
  {
    if ( (byte_1800AA941 & 4) != 0 )
    {
      LOWORD(v36) = 0;
      FormatRRASErrorString(&v36, L"OpenIkev2ConfigKey failed: %d", v10);
      if ( (byte_1800AA941 & 4) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v36);
      v11 = v22;
    }
    if ( (_DWORD)v11 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v13 = 95;
LABEL_17:
        WPP_SF_d(v12[2], v13, &WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids, v11);
      }
    }
  }
  else
  {
    Ikev2ConfigParams = GetIkev2ConfigParams(hKey);
    v11 = Ikev2ConfigParams;
    v22 = Ikev2ConfigParams;
    if ( Ikev2ConfigParams )
    {
      if ( (byte_1800AA941 & 4) != 0 )
      {
        LOWORD(v36) = 0;
        FormatRRASErrorString(&v36, L"GetIkev2ConfigParams failed: %d", Ikev2ConfigParams);
        if ( (byte_1800AA941 & 4) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v36);
        v11 = v22;
      }
      if ( (_DWORD)v11 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v13 = 96;
          goto LABEL_17;
        }
      }
    }
    else
    {
      v9 = VpnikeMalloc(16 * v34);
      if ( v9 )
      {
        v15 = 0;
        for ( i = v34; v15 < v34; i = v34 )
        {
          v17 = 2LL * v15;
          v9[2 * v17] = *(_DWORD *)(v35 + 16LL * v15 + 4);
          v9[2 * v17 + 1] = *(_DWORD *)(v35 + 16LL * v15);
          *(_QWORD *)&v9[2 * v17 + 2] = *(_QWORD *)(v35 + 16LL * v15++ + 8);
        }
        v18 = BuildIpsecTrustedRootCertificateList(
                a1 == 0,
                v32,
                v33,
                v32,
                v33,
                0,
                0,
                i,
                (__int64)v9,
                (__int64)a2,
                (__int64)a3,
                (__int64)v5,
                (__int64)a5,
                (unsigned int)VpnikeMalloc,
                (__int64)VpnikeFree);
        v11 = v18;
        v22 = v18;
        if ( v18 )
        {
          if ( (byte_1800AA941 & 4) != 0 )
          {
            LOWORD(v36) = 0;
            FormatRRASErrorString(&v36, L"BuildIpsecTrustedRootCertificateList failed: %d", v18);
            if ( (byte_1800AA941 & 4) != 0 )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v36);
            v11 = v22;
          }
          if ( (_DWORD)v11 )
          {
            v12 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v13 = 98;
              goto LABEL_17;
            }
          }
        }
      }
      else
      {
        v11 = 14;
        v22 = 14;
        if ( (byte_1800AA941 & 4) == 0 )
          goto LABEL_35;
        LOWORD(v36) = 0;
        FormatRRASErrorString(&v36, L"Malloc failed: %d", 14);
        if ( (byte_1800AA941 & 4) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v36);
        v11 = v22;
        if ( v22 )
        {
LABEL_35:
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v13 = 97;
            goto LABEL_17;
          }
        }
      }
    }
  }
  v19 = hKey;
  if ( hKey )
    RegCloseKey(hKey);
  FreeIkev2ConfigParams(v19, v31);
  if ( v9 )
    VpnikeFree(v9);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 99, &WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids, v22);
  }
  v20 = v22;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v25);
  return v20;
}

```

## disassembly

```asm
0x18002c7d8  push    rbp
0x18002c7da  push    rbx
0x18002c7db  push    rsi
0x18002c7dc  push    rdi
0x18002c7dd  push    r12
0x18002c7df  push    r14
0x18002c7e1  push    r15
0x18002c7e3  lea     rbp, [rsp-850h]
0x18002c7eb  sub     rsp, 950h
0x18002c7f2  mov     rax, cs:__security_cookie
0x18002c7f9  xor     rax, rsp
0x18002c7fc  mov     [rbp+880h+var_40], rax
0x18002c803  mov     r15, r9
0x18002c806  mov     r14, r8
0x18002c809  mov     rsi, rdx
0x18002c80c  mov     edi, ecx
0x18002c80e  mov     r12, [rbp+880h+arg_20]
0x18002c815  lea     rax, WPP_GLOBAL_Control
0x18002c81c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c823  cmp     rcx, rax
0x18002c826  jz      short loc_18002C84F
0x18002c828  test    byte ptr [rcx+1Ch], 1
0x18002c82c  jz      short loc_18002C84F
0x18002c82e  cmp     byte ptr [rcx+19h], 6
0x18002c832  jb      short loc_18002C84F
0x18002c834  test    edi, edi
0x18002c836  setnz   r9b
0x18002c83a  mov     edx, 5Eh ; '^'
0x18002c83f  lea     r8, WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids
0x18002c846  mov     rcx, [rcx+10h]
0x18002c84a  call    WPP_SF_c
0x18002c84f  xor     eax, eax
0x18002c851  mov     [rbp+880h+var_840], eax
0x18002c854  xor     edx, edx; Val
0x18002c856  mov     r8d, 7FCh; Size
0x18002c85c  lea     rcx, [rbp+880h+var_83C]; void *
0x18002c860  call    memset_0
0x18002c865  mov     [rbp+880h+var_900], 0
0x18002c86c  xor     edx, edx; Val
0x18002c86e  lea     r8d, [rdx+68h]; Size
0x18002c872  lea     rcx, [rbp+880h+var_8B0]; void *
0x18002c876  call    memset_0
0x18002c87b  mov     [rbp+880h+hKey], 0
0x18002c883  xor     ebx, ebx
0x18002c885  xorps   xmm0, xmm0
0x18002c888  movdqu  [rbp+880h+var_8E8], xmm0
0x18002c88d  mov     [rbp+880h+var_8F0], rbx
0x18002c891  xorps   xmm1, xmm1
0x18002c894  movdqu  [rbp+880h+var_8D8], xmm1
0x18002c899  mov     [rbp+880h+var_8C8], rbx
0x18002c89d  mov     [rbp+880h+var_8C0], 0FFFFFFFFh
0x18002c8a4  mov     [rbp+880h+var_8BC], ebx
0x18002c8a7  test    cs:byte_1800AA941, 8
0x18002c8ae  jz      short loc_18002C8CB
0x18002c8b0  lea     r9, ?RasVpnIkeTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x18002c8b7  lea     r8, [rbp+880h+var_900]; unsigned int *
0x18002c8bb  lea     rdx, aBfehandlerBuil_0; "BFEHandler::BuildTrustedRootCertificate"...
0x18002c8c2  lea     rcx, [rbp+880h+var_8F0]; this
0x18002c8c6  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x18002c8cb  xor     edx, edx; Val
0x18002c8cd  lea     r8d, [rdx+68h]; Size
0x18002c8d1  lea     rcx, [rbp+880h+var_8B0]; void *
0x18002c8d5  call    memset_0
0x18002c8da  mov     [rbp+880h+dwDisposition], 0
0x18002c8e1  lea     rax, [rbp+880h+dwDisposition]
0x18002c8e5  mov     [rsp+980h+lpdwDisposition], rax; lpdwDisposition
0x18002c8ea  lea     rax, [rbp+880h+hKey]
0x18002c8ee  mov     [rsp+980h+phkResult], rax; phkResult
0x18002c8f3  mov     [rsp+980h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18002c8fc  mov     [rsp+980h+samDesired], 0F003Fh; samDesired
0x18002c904  mov     [rsp+980h+dwOptions], 0; dwOptions
0x18002c90c  xor     r9d, r9d; lpClass
0x18002c90f  xor     r8d, r8d; Reserved
0x18002c912  lea     rdx, aSystemCurrentc_5; "SYSTEM\\CurrentControlSet\\Services\\Re"...
0x18002c919  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002c920  call    cs:__imp_RegCreateKeyExW
0x18002c926  mov     r9d, eax
0x18002c929  mov     [rbp+880h+var_900], eax
0x18002c92c  test    eax, eax
0x18002c92e  jz      loc_18002C9C8
0x18002c934  test    cs:byte_1800AA941, 4
0x18002c93b  jz      short loc_18002C97A
0x18002c93d  xor     eax, eax
0x18002c93f  mov     word ptr [rbp+880h+var_840], ax
0x18002c943  mov     r8d, r9d
0x18002c946  lea     rdx, aOpenikev2confi; "OpenIkev2ConfigKey failed: %d"
0x18002c94d  lea     rcx, [rbp+880h+var_840]
0x18002c951  call    FormatRRASErrorString
0x18002c956  test    cs:byte_1800AA941, 4
0x18002c95d  jz      short loc_18002C976
0x18002c95f  lea     r8, [rbp+880h+var_840]
0x18002c963  lea     rdx, RasVpnIkeTraceError
0x18002c96a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002c971  call    McTemplateU0z_EventWriteTransfer
0x18002c976  mov     r9d, [rbp+880h+var_900]
0x18002c97a  test    r9d, r9d
0x18002c97d  jz      loc_18002CC30
0x18002c983  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c98a  lea     rdi, WPP_GLOBAL_Control
0x18002c991  cmp     rcx, rdi
0x18002c994  jz      loc_18002CC37
0x18002c99a  test    byte ptr [rcx+1Ch], 1
0x18002c99e  jz      loc_18002CC37
0x18002c9a4  cmp     byte ptr [rcx+19h], 2
0x18002c9a8  jb      loc_18002CC37
0x18002c9ae  mov     edx, 5Fh ; '_'
0x18002c9b3  lea     r8, WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids
0x18002c9ba  mov     rcx, [rcx+10h]
0x18002c9be  call    WPP_SF_d
0x18002c9c3  jmp     loc_18002CC37
0x18002c9c8  mov     r9d, 68h ; 'h'
0x18002c9ce  lea     r8, [rbp+880h+var_8B0]
0x18002c9d2  mov     dl, 5
0x18002c9d4  mov     rcx, [rbp+880h+hKey]; hkey
0x18002c9d8  call    GetIkev2ConfigParams
0x18002c9dd  mov     r9d, eax
0x18002c9e0  mov     [rbp+880h+var_900], eax
0x18002c9e3  test    eax, eax
0x18002c9e5  jz      loc_18002CA6F
0x18002c9eb  test    cs:byte_1800AA941, 4
0x18002c9f2  jz      short loc_18002CA31
0x18002c9f4  xor     eax, eax
0x18002c9f6  mov     word ptr [rbp+880h+var_840], ax
0x18002c9fa  mov     r8d, r9d
0x18002c9fd  lea     rdx, aGetikev2config; "GetIkev2ConfigParams failed: %d"
0x18002ca04  lea     rcx, [rbp+880h+var_840]
0x18002ca08  call    FormatRRASErrorString
0x18002ca0d  test    cs:byte_1800AA941, 4
0x18002ca14  jz      short loc_18002CA2D
0x18002ca16  lea     r8, [rbp+880h+var_840]
0x18002ca1a  lea     rdx, RasVpnIkeTraceError
0x18002ca21  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002ca28  call    McTemplateU0z_EventWriteTransfer
0x18002ca2d  mov     r9d, [rbp+880h+var_900]
0x18002ca31  test    r9d, r9d
0x18002ca34  jz      loc_18002CC30
0x18002ca3a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ca41  lea     rdi, WPP_GLOBAL_Control
0x18002ca48  cmp     rcx, rdi
0x18002ca4b  jz      loc_18002CC37
0x18002ca51  test    byte ptr [rcx+1Ch], 1
0x18002ca55  jz      loc_18002CC37
0x18002ca5b  cmp     byte ptr [rcx+19h], 2
0x18002ca5f  jb      loc_18002CC37
0x18002ca65  mov     edx, 60h ; '`'
0x18002ca6a  jmp     loc_18002C9B3
0x18002ca6f  mov     ecx, [rbp+880h+var_870]
0x18002ca72  shl     ecx, 4; unsigned int
0x18002ca75  call    ?VpnikeMalloc@@YAPEAXK@Z; VpnikeMalloc(ulong)
0x18002ca7a  mov     rbx, rax
0x18002ca7d  test    rax, rax
0x18002ca80  jnz     loc_18002CB12
0x18002ca86  lea     r9d, [rax+0Eh]
0x18002ca8a  mov     [rbp+880h+var_900], r9d
0x18002ca8e  test    cs:byte_1800AA941, 4
0x18002ca95  jz      short loc_18002CADD
0x18002ca97  xor     ecx, ecx
0x18002ca99  mov     word ptr [rbp+880h+var_840], cx
0x18002ca9d  mov     r8d, r9d
0x18002caa0  lea     rdx, aMallocFailedD; "Malloc failed: %d"
0x18002caa7  lea     rcx, [rbp+880h+var_840]
0x18002caab  call    FormatRRASErrorString
0x18002cab0  test    cs:byte_1800AA941, 4
0x18002cab7  jz      short loc_18002CAD0
0x18002cab9  lea     r8, [rbp+880h+var_840]
0x18002cabd  lea     rdx, RasVpnIkeTraceError
0x18002cac4  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002cacb  call    McTemplateU0z_EventWriteTransfer
0x18002cad0  mov     r9d, [rbp+880h+var_900]
0x18002cad4  test    r9d, r9d
0x18002cad7  jz      loc_18002CC30
0x18002cadd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cae4  lea     rdi, WPP_GLOBAL_Control
0x18002caeb  cmp     rcx, rdi
0x18002caee  jz      loc_18002CC37
0x18002caf4  test    byte ptr [rcx+1Ch], 1
0x18002caf8  jz      loc_18002CC37
0x18002cafe  cmp     byte ptr [rcx+19h], 2
0x18002cb02  jb      loc_18002CC37
0x18002cb08  mov     edx, 61h ; 'a'
0x18002cb0d  jmp     loc_18002C9B3
0x18002cb12  xor     r8d, r8d
0x18002cb15  mov     eax, [rbp+880h+var_870]
0x18002cb18  test    eax, eax
0x18002cb1a  jz      short loc_18002CB51
0x18002cb1c  mov     edx, r8d
0x18002cb1f  add     rdx, rdx
0x18002cb22  mov     rax, [rbp+880h+var_868]
0x18002cb26  mov     ecx, [rax+rdx*8+4]
0x18002cb2a  mov     [rbx+rdx*8], ecx
0x18002cb2d  mov     rax, [rbp+880h+var_868]
0x18002cb31  mov     ecx, [rax+rdx*8]
0x18002cb34  mov     [rbx+rdx*8+4], ecx
0x18002cb38  mov     rax, [rbp+880h+var_868]
0x18002cb3c  mov     rcx, [rax+rdx*8+8]
0x18002cb41  mov     [rbx+rdx*8+8], rcx
0x18002cb46  inc     r8d
0x18002cb49  mov     eax, [rbp+880h+var_870]
0x18002cb4c  cmp     r8d, eax
0x18002cb4f  jb      short loc_18002CB1C
0x18002cb51  xor     ecx, ecx
0x18002cb53  test    edi, edi
0x18002cb55  setz    cl
0x18002cb58  lea     rdx, ?VpnikeFree@@YAHPEAX@Z; VpnikeFree(void *)
0x18002cb5f  mov     [rsp+980h+var_910], rdx
0x18002cb64  lea     rdx, ?VpnikeMalloc@@YAPEAXK@Z; VpnikeMalloc(ulong)
0x18002cb6b  mov     [rsp+980h+var_918], rdx
0x18002cb70  mov     [rsp+980h+var_920], r12
0x18002cb75  mov     [rsp+980h+var_928], r15
0x18002cb7a  mov     [rsp+980h+var_930], r14
0x18002cb7f  mov     [rsp+980h+var_938], rsi
0x18002cb84  mov     [rsp+980h+lpdwDisposition], rbx
0x18002cb89  mov     dword ptr [rsp+980h+phkResult], eax
0x18002cb8d  mov     [rsp+980h+lpSecurityAttributes], 0
0x18002cb96  mov     [rsp+980h+samDesired], 0
0x18002cb9e  mov     r8, [rbp+880h+var_898]
0x18002cba2  mov     qword ptr [rsp+980h+dwOptions], r8
0x18002cba7  mov     edx, [rbp+880h+var_89C]
0x18002cbaa  mov     r9d, edx
0x18002cbad  call    BuildIpsecTrustedRootCertificateList
0x18002cbb2  mov     r9d, eax
0x18002cbb5  mov     [rbp+880h+var_900], eax
0x18002cbb8  test    eax, eax
0x18002cbba  jz      short loc_18002CC30
0x18002cbbc  test    cs:byte_1800AA941, 4
0x18002cbc3  jz      short loc_18002CC02
0x18002cbc5  xor     eax, eax
0x18002cbc7  mov     word ptr [rbp+880h+var_840], ax
0x18002cbcb  mov     r8d, r9d
0x18002cbce  lea     rdx, aBuildipsectrus; "BuildIpsecTrustedRootCertificateList fa"...
0x18002cbd5  lea     rcx, [rbp+880h+var_840]
0x18002cbd9  call    FormatRRASErrorString
0x18002cbde  test    cs:byte_1800AA941, 4
0x18002cbe5  jz      short loc_18002CBFE
0x18002cbe7  lea     r8, [rbp+880h+var_840]
0x18002cbeb  lea     rdx, RasVpnIkeTraceError
0x18002cbf2  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002cbf9  call    McTemplateU0z_EventWriteTransfer
0x18002cbfe  mov     r9d, [rbp+880h+var_900]
0x18002cc02  test    r9d, r9d
0x18002cc05  jz      short loc_18002CC30
0x18002cc07  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cc0e  lea     rdi, WPP_GLOBAL_Control
0x18002cc15  cmp     rcx, rdi
0x18002cc18  jz      short loc_18002CC37
0x18002cc1a  test    byte ptr [rcx+1Ch], 1
0x18002cc1e  jz      short loc_18002CC37
0x18002cc20  cmp     byte ptr [rcx+19h], 2
0x18002cc24  jb      short loc_18002CC37
0x18002cc26  mov     edx, 62h ; 'b'
0x18002cc2b  jmp     loc_18002C9B3
0x18002cc30  lea     rdi, WPP_GLOBAL_Control
0x18002cc37  mov     rcx, [rbp+880h+hKey]; hKey
0x18002cc3b  test    rcx, rcx
0x18002cc3e  jz      short loc_18002CC46
0x18002cc40  call    cs:__imp_RegCloseKey
0x18002cc46  lea     rdx, [rbp+880h+var_8B0]
0x18002cc4a  call    FreeIkev2ConfigParams
0x18002cc4f  test    rbx, rbx
0x18002cc52  jz      short loc_18002CC5C
0x18002cc54  mov     rcx, rbx; lpMem
0x18002cc57  call    ?VpnikeFree@@YAHPEAX@Z; VpnikeFree(void *)
0x18002cc5c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cc63  cmp     rcx, rdi
0x18002cc66  jz      short loc_18002CC8D
0x18002cc68  test    byte ptr [rcx+1Ch], 1
0x18002cc6c  jz      short loc_18002CC8D
0x18002cc6e  cmp     byte ptr [rcx+19h], 6
0x18002cc72  jb      short loc_18002CC8D
0x18002cc74  mov     edx, 63h ; 'c'
0x18002cc79  mov     r9d, [rbp+880h+var_900]
0x18002cc7d  lea     r8, WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids
0x18002cc84  mov     rcx, [rcx+10h]
0x18002cc88  call    WPP_SF_d
0x18002cc8d  mov     ebx, [rbp+880h+var_900]
0x18002cc90  lea     rcx, [rbp+880h+var_8F0]; this
0x18002cc94  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18002cc99  mov     eax, ebx
0x18002cc9b  mov     rcx, [rbp+880h+var_40]
0x18002cca2  xor     rcx, rsp; StackCookie
0x18002cca5  call    __security_check_cookie
0x18002ccaa  add     rsp, 950h
0x18002ccb1  pop     r15
0x18002ccb3  pop     r14
0x18002ccb5  pop     r12
0x18002ccb7  pop     rdi
0x18002ccb8  pop     rsi
0x18002ccb9  pop     rbx
0x18002ccba  pop     rbp
0x18002ccbb  retn
```
