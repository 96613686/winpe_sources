# SetExtendedPropertyInternal(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x180023208`
- end: `0x180023515`
- name: `?SetExtendedPropertyInternal@@YAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z`
- size: `781`
- prototype: `__int64 __fastcall(LPCWSTR *, const BYTE **)`
- caller_count: `6`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18008c938`
- `0x18009c4d0`
- `0x1800b29b8`
- `0x1800e4580`
- `0x1800e5470`
- `0x180107b00`

## callees

- `0x180019690`
- `0x180019780`
- `0x18001a530`
- `0x18001a9c0`
- `0x180021b28`
- `0x180021bbc`
- `0x180023208`
- `0x180038818`
- `0x1800396e8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800232df`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800232df`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180023421`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180023421`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800232f4`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800232f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800234e3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800234f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800234e3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800234f2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002342f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002342f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023357`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023357`

## string_xrefs

- `0x1800232c1`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18002331c`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18002339a`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x1800234b3`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18002330f`: `Unable to open current user registry, hr = %x.`
- `0x18002338d`: `Unable to write or create registry key '%ls', hr = %x.`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall SetExtendedPropertyInternal(LPCWSTR *a1, const BYTE **a2)
{
  HKEY v4; // r14
  HKEY v5; // rdi
  unsigned __int8 v6; // dl
  PPTraceStatus *v7; // rcx
  char v8; // si
  char v9; // cl
  const unsigned __int16 *String; // rax
  int v11; // eax
  int v12; // eax
  const BYTE *v13; // rcx
  __int64 v14; // rax
  LSTATUS v15; // eax
  unsigned int v16; // ebx
  unsigned __int8 v17; // dl
  PPTraceStatus *v18; // rcx
  const unsigned __int16 *v19; // rax
  unsigned int v20; // ebx
  PHKEY v22; // [rsp+20h] [rbp-89h]
  DWORD cbData[2]; // [rsp+28h] [rbp-81h]
  unsigned int *v24; // [rsp+38h] [rbp-71h]
  _QWORD v25[3]; // [rsp+40h] [rbp-69h] BYREF
  _QWORD v26[2]; // [rsp+58h] [rbp-51h] BYREF
  void *Block; // [rsp+68h] [rbp-41h]
  char v28; // [rsp+70h] [rbp-39h]
  _QWORD v29[3]; // [rsp+78h] [rbp-31h] BYREF
  char v30; // [rsp+90h] [rbp-19h]
  HKEY v31; // [rsp+98h] [rbp-11h]
  __int64 v32; // [rsp+A0h] [rbp-9h]
  __int64 v33; // [rsp+A8h] [rbp-1h]
  _BYTE v34[80]; // [rsp+B0h] [rbp+7h] BYREF
  unsigned int v35; // [rsp+110h] [rbp+67h] BYREF
  HKEY phkResult; // [rsp+118h] [rbp+6Fh] BYREF
  HKEY hKey; // [rsp+120h] [rbp+77h] BYREF

  v35 = 0;
  phkResult = 0;
  v4 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v5 = 0;
  memset(v25, 0, sizeof(v25));
  v8 = 1;
  if ( !PPTraceShouldRedact() || (LOBYTE(v7) = 1, !PPTraceStatus::TraceOnFlag(v7, v6)) )
    v9 = 0;
  v26[0] = &PPRedactedStringW::`vftable';
  v26[1] = *a2;
  Block = 0;
  v28 = v9;
  String = PPRedactedStringW::GetString((PPRedactedStringW *)v26);
  CTraceFuncW<long>::CTraceFuncW<long>(
    v34,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
    8054,
    &v35,
    "SetExtendedPropertyInternal",
    L"wszPropertyName='%ls', wszPropertyValue=%ls",
    *a1,
    String);
  v26[0] = &PPRedactedStringW::`vftable';
  if ( Block )
  {
    free(Block);
    Block = 0;
  }
  v11 = RegOpenCurrentUser(0x20006u, &phkResult);
  if ( v11 )
  {
    if ( v11 > 0 )
      v11 = (unsigned __int16)v11 | 0x80070000;
    v35 = v11;
    LODWORD(v22) = v11;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      0x1F7Du,
      L"Unable to open current user registry, hr = %x.",
      v22);
  }
  else
  {
    v4 = phkResult;
    v31 = phkResult;
    hKey = 0;
    v12 = RegOpenKeyExW(phkResult, L"Software\\Microsoft\\IdentityCRL\\ExtendedProperties", 0, 0x20006u, &hKey);
    if ( v12 )
    {
      if ( v12 == 2 )
      {
        v12 = ATL::CRegKey::Create(
                (ATL::CRegKey *)v25,
                phkResult,
                L"Software\\Microsoft\\IdentityCRL\\ExtendedProperties",
                0,
                0,
                0x20006u,
                0,
                0);
        v5 = (HKEY)v25[0];
      }
    }
    else
    {
      v12 = 0;
      v5 = hKey;
      v25[0] = hKey;
    }
    if ( v12 )
    {
      if ( v12 > 0 )
        v12 = (unsigned __int16)v12 | 0x80070000;
      v35 = v12;
      cbData[0] = v12;
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        0x1F8Cu,
        L"Unable to write or create registry key '%ls', hr = %x.",
        L"Software\\Microsoft\\IdentityCRL\\ExtendedProperties",
        *(_QWORD *)cbData);
    }
    else
    {
      v13 = *a2;
      if ( *a2 && *((_DWORD *)v13 - 4) )
      {
        v14 = -1;
        do
          ++v14;
        while ( *(_WORD *)&v13[2 * v14] );
        v15 = RegSetValueExW(v5, *a1, 0, 1u, v13, 2 * v14 + 2);
      }
      else
      {
        v15 = RegDeleteValueW(v5, *a1);
      }
      v16 = v15;
      if ( v15 )
      {
        if ( v15 > 0 )
          v16 = (unsigned __int16)v15 | 0x80070000;
        v35 = v16;
        if ( !PPTraceShouldRedact() || (LOBYTE(v18) = 1, !PPTraceStatus::TraceOnFlag(v18, v17)) )
          v8 = 0;
        v29[0] = &PPRedactedStringW::`vftable';
        v29[1] = *a2;
        v29[2] = 0;
        v30 = v8;
        v19 = PPRedactedStringW::GetString((PPRedactedStringW *)v29);
        LODWORD(v24) = v16;
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
          0x1F9Cu,
          L"Unable to set string value '%ls'='%ls' under '%ls', hr = 0x%x.",
          *a1,
          v19,
          L"Software\\Microsoft\\IdentityCRL\\ExtendedProperties",
          v24);
        PPRedactedStringW::~PPRedactedStringW((PPRedactedStringW *)v29);
      }
    }
  }
  v20 = v35;
  CTraceFuncW<long>::~CTraceFuncW<long>(v34);
  if ( v5 )
    RegCloseKey(v5);
  if ( v4 )
    RegCloseKey(v4);
  return v20;
}

```

## disassembly

```asm
0x180023208  mov     [rsp-8+arg_18], rbx
0x18002320d  push    rbp
0x18002320e  push    rsi
0x18002320f  push    rdi
0x180023210  push    r12
0x180023212  push    r13
0x180023214  push    r14
0x180023216  push    r15
0x180023218  lea     rbp, [rsp-27h]
0x18002321d  sub     rsp, 0D0h
0x180023224  mov     r12, rdx
0x180023227  mov     r15, rcx
0x18002322a  xor     r13d, r13d
0x18002322d  mov     [rbp+57h+arg_0], r13d
0x180023231  mov     [rbp+57h+phkResult], r13
0x180023235  mov     r14d, r13d
0x180023238  mov     [rbp+57h+var_68], r13
0x18002323c  mov     [rbp+57h+var_60], r13
0x180023240  mov     [rbp+57h+var_58], r13
0x180023244  mov     edi, r13d
0x180023247  mov     [rbp+57h+var_C0], r13
0x18002324b  mov     [rbp+57h+var_B8], r13
0x18002324f  mov     [rbp+57h+var_B0], r13
0x180023253  call    ?PPTraceShouldRedact@@YA_NXZ; PPTraceShouldRedact(void)
0x180023258  lea     esi, [r13+1]
0x18002325c  test    al, al
0x18002325e  jz      short loc_18002326C
0x180023260  mov     cl, sil; this
0x180023263  call    ?TraceOnFlag@PPTraceStatus@@YA_NE@Z; PPTraceStatus::TraceOnFlag(uchar)
0x180023268  test    al, al
0x18002326a  jnz     short loc_18002326F
0x18002326c  mov     cl, r13b
0x18002326f  lea     rbx, ??_7PPRedactedStringW@@6B@; const PPRedactedStringW::`vftable'
0x180023276  mov     [rbp+57h+var_A8], rbx
0x18002327a  mov     rax, [r12]
0x18002327e  mov     [rbp+57h+var_A0], rax
0x180023282  mov     [rbp+57h+Block], r13
0x180023286  mov     [rbp+57h+var_90], cl
0x180023289  lea     rcx, [rbp+57h+var_A8]; this
0x18002328d  call    ?GetString@PPRedactedStringW@@QEAAPEBGXZ; PPRedactedStringW::GetString(void)
0x180023292  mov     [rsp+100h+var_C8], rax
0x180023297  mov     rax, [r15]
0x18002329a  mov     [rsp+100h+var_D0], rax
0x18002329f  lea     rax, aWszpropertynam_1; "wszPropertyName='%ls', wszPropertyValue"...
0x1800232a6  mov     qword ptr [rsp+100h+cbData], rax
0x1800232ab  lea     rax, aSetextendedpro; "SetExtendedPropertyInternal"
0x1800232b2  mov     [rsp+100h+var_E0], rax
0x1800232b7  lea     r9, [rbp+57h+arg_0]
0x1800232bb  mov     r8d, 1F76h
0x1800232c1  lea     rdx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800232c8  lea     rcx, [rbp+57h+var_50]
0x1800232cc  call    ??0?$CTraceFuncW@J@@QEAA@PEBDKAEAJ0PEBGZZ; CTraceFuncW<long>::CTraceFuncW<long>(char const *,ulong,long &,char const *,ushort const *,...)
0x1800232d1  nop
0x1800232d2  mov     [rbp+57h+var_A8], rbx
0x1800232d6  mov     rcx, [rbp+57h+Block]; Block
0x1800232da  test    rcx, rcx
0x1800232dd  jz      short loc_1800232E9
0x1800232df  call    cs:__imp_free
0x1800232e5  mov     [rbp+57h+Block], r13
0x1800232e9  lea     rdx, [rbp+57h+phkResult]; phkResult
0x1800232ed  mov     ebx, 20006h
0x1800232f2  mov     ecx, ebx; samDesired
0x1800232f4  call    cs:__imp_RegOpenCurrentUser
0x1800232fa  test    eax, eax
0x1800232fc  jz      short loc_180023332
0x1800232fe  jle     short loc_180023308
0x180023300  movzx   eax, ax
0x180023303  or      eax, 80070000h
0x180023308  mov     [rbp+57h+arg_0], eax
0x18002330b  mov     dword ptr [rsp+100h+var_E0], eax
0x18002330f  lea     r9, aUnableToOpenCu; "Unable to open current user registry, h"...
0x180023316  mov     r8d, 1F7Dh; unsigned int
0x18002331c  lea     rdx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180023323  mov     ecx, 2; unsigned __int8
0x180023328  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18002332d  jmp     loc_1800234CE
0x180023332  mov     r14, [rbp+57h+phkResult]
0x180023336  mov     [rbp+57h+var_68], r14
0x18002333a  mov     [rbp+57h+hKey], r13
0x18002333e  lea     rax, [rbp+57h+hKey]
0x180023342  mov     [rsp+100h+var_E0], rax; phkResult
0x180023347  mov     r9d, ebx; samDesired
0x18002334a  xor     r8d, r8d; ulOptions
0x18002334d  lea     rdx, aSoftwareMicros_18; "Software\\Microsoft\\IdentityCRL\\Exten"...
0x180023354  mov     rcx, r14; hKey
0x180023357  call    cs:__imp_RegOpenKeyExW
0x18002335d  test    eax, eax
0x18002335f  jnz     short loc_1800233B0
0x180023361  mov     eax, r13d
0x180023364  mov     rdi, [rbp+57h+hKey]
0x180023368  mov     [rbp+57h+var_C0], rdi
0x18002336c  lea     rbx, aSoftwareMicros_18; "Software\\Microsoft\\IdentityCRL\\Exten"...
0x180023373  test    eax, eax
0x180023375  jz      short loc_1800233E8
0x180023377  jle     short loc_180023381
0x180023379  movzx   eax, ax
0x18002337c  or      eax, 80070000h
0x180023381  mov     [rbp+57h+arg_0], eax
0x180023384  mov     [rsp+100h+cbData], eax
0x180023388  mov     [rsp+100h+var_E0], rbx
0x18002338d  lea     r9, aUnableToWriteO; "Unable to write or create registry key "...
0x180023394  mov     r8d, 1F8Ch; unsigned int
0x18002339a  lea     rdx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800233a1  mov     ecx, 2; unsigned __int8
0x1800233a6  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800233ab  jmp     loc_1800234CE
0x1800233b0  cmp     eax, 2
0x1800233b3  jnz     short loc_18002336C
0x1800233b5  mov     [rsp+100h+var_C8], r13; unsigned int *
0x1800233ba  mov     [rsp+100h+var_D0], r13; LPSECURITY_ATTRIBUTES
0x1800233bf  mov     [rsp+100h+cbData], ebx; REGSAM
0x1800233c3  mov     dword ptr [rsp+100h+var_E0], r13d; DWORD
0x1800233c8  xor     r9d, r9d; unsigned __int16 *
0x1800233cb  lea     rbx, aSoftwareMicros_18; "Software\\Microsoft\\IdentityCRL\\Exten"...
0x1800233d2  mov     r8, rbx; lpSubKey
0x1800233d5  mov     rdx, [rbp+57h+phkResult]; hKey
0x1800233d9  lea     rcx, [rbp+57h+var_C0]; this
0x1800233dd  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x1800233e2  mov     rdi, [rbp+57h+var_C0]
0x1800233e6  jmp     short loc_180023373
0x1800233e8  mov     rcx, [r12]
0x1800233ec  test    rcx, rcx
0x1800233ef  jz      short loc_180023429
0x1800233f1  cmp     [rcx-10h], r13d
0x1800233f5  jz      short loc_180023429
0x1800233f7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800233fb  inc     rax
0x1800233fe  cmp     [rcx+rax*2], r13w
0x180023403  jnz     short loc_1800233FB
0x180023405  lea     eax, ds:2[rax*2]
0x18002340c  mov     [rsp+100h+cbData], eax; cbData
0x180023410  mov     [rsp+100h+var_E0], rcx; lpData
0x180023415  mov     r9d, esi; dwType
0x180023418  xor     r8d, r8d; Reserved
0x18002341b  mov     rdx, [r15]; lpValueName
0x18002341e  mov     rcx, rdi; hKey
0x180023421  call    cs:__imp_RegSetValueExW
0x180023427  jmp     short loc_180023435
0x180023429  mov     rdx, [r15]; lpValueName
0x18002342c  mov     rcx, rdi; hKey
0x18002342f  call    cs:__imp_RegDeleteValueW
0x180023435  mov     ebx, eax
0x180023437  test    eax, eax
0x180023439  jz      loc_1800234CE
0x18002343f  jle     short loc_18002344A
0x180023441  movzx   ebx, bx
0x180023444  or      ebx, 80070000h
0x18002344a  mov     [rbp+57h+arg_0], ebx
0x18002344d  call    ?PPTraceShouldRedact@@YA_NXZ; PPTraceShouldRedact(void)
0x180023452  test    al, al
0x180023454  jz      short loc_180023462
0x180023456  mov     cl, sil; this
0x180023459  call    ?TraceOnFlag@PPTraceStatus@@YA_NE@Z; PPTraceStatus::TraceOnFlag(uchar)
0x18002345e  test    al, al
0x180023460  jnz     short loc_180023465
0x180023462  mov     sil, r13b
0x180023465  lea     rax, ??_7PPRedactedStringW@@6B@; const PPRedactedStringW::`vftable'
0x18002346c  mov     [rbp+57h+var_88], rax
0x180023470  mov     rax, [r12]
0x180023474  mov     [rbp+57h+var_80], rax
0x180023478  mov     [rbp+57h+var_78], r13
0x18002347c  mov     [rbp+57h+var_70], sil
0x180023480  lea     rcx, [rbp+57h+var_88]; this
0x180023484  call    ?GetString@PPRedactedStringW@@QEAAPEBGXZ; PPRedactedStringW::GetString(void)
0x180023489  mov     dword ptr [rsp+100h+var_C8], ebx
0x18002348d  lea     rcx, aSoftwareMicros_18; "Software\\Microsoft\\IdentityCRL\\Exten"...
0x180023494  mov     [rsp+100h+var_D0], rcx
0x180023499  mov     qword ptr [rsp+100h+cbData], rax
0x18002349e  mov     rax, [r15]
0x1800234a1  mov     [rsp+100h+var_E0], rax
0x1800234a6  lea     r9, aUnableToSetStr; "Unable to set string value '%ls'='%ls' "...
0x1800234ad  mov     r8d, 1F9Ch; unsigned int
0x1800234b3  lea     rdx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800234ba  mov     ecx, 2; unsigned __int8
0x1800234bf  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800234c4  nop
0x1800234c5  lea     rcx, [rbp+57h+var_88]; this
0x1800234c9  call    ??1PPRedactedStringW@@QEAA@XZ; PPRedactedStringW::~PPRedactedStringW(void)
0x1800234ce  mov     ebx, [rbp+57h+arg_0]
0x1800234d1  lea     rcx, [rbp+57h+var_50]
0x1800234d5  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800234da  nop
0x1800234db  test    rdi, rdi
0x1800234de  jz      short loc_1800234EA
0x1800234e0  mov     rcx, rdi; hKey
0x1800234e3  call    cs:__imp_RegCloseKey
0x1800234e9  nop
0x1800234ea  test    r14, r14
0x1800234ed  jz      short loc_1800234F8
0x1800234ef  mov     rcx, r14; hKey
0x1800234f2  call    cs:__imp_RegCloseKey
0x1800234f8  mov     eax, ebx
0x1800234fa  mov     rbx, [rsp+100h+arg_18]
0x180023502  add     rsp, 0D0h
0x180023509  pop     r15
0x18002350b  pop     r14
0x18002350d  pop     r13
0x18002350f  pop     r12
0x180023511  pop     rdi
0x180023512  pop     rsi
0x180023513  pop     rbp
0x180023514  retn
```
