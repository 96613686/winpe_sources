# CUtils::IsAppServerInstalled(int &)

- ea: `0x1800a260c`
- end: `0x1800a27cf`
- name: `?IsAppServerInstalled@CUtils@@SAJAEAH@Z`
- size: `451`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18009102c`
- `0x180092fd8`
- `0x1800938f0`
- `0x1800a235c`

## callees

- `0x18000542c`
- `0x180005a24`
- `0x1800a260c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a26ec`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a26ec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a27b6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a27b6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a264a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a264a`

## string_xrefs

- `0x1800a2667`: `Unable to open TS key in HKLM`
- `0x1800a2731`: `Successfully read APPCOMPAT key`
- `0x1800a26c3`: `TSAppCompat`
- `0x1800a2772`: `Unable to read APPCOMPAT key`

## pseudocode

```c
__int64 __fastcall CUtils::IsAppServerInstalled(int *a1)
{
  int v2; // ebx
  LSTATUS v3; // ecx
  int v4; // r8d
  int v5; // r9d
  const char *v7; // [rsp+40h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-20h] BYREF
  const WCHAR *v9; // [rsp+50h] [rbp-18h] BYREF
  const char *v10; // [rsp+58h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+90h] [rbp+28h] BYREF
  DWORD Type; // [rsp+98h] [rbp+30h] BYREF
  int Data; // [rsp+A0h] [rbp+38h] BYREF
  int v14; // [rsp+A8h] [rbp+40h] BYREF

  *a1 = 0;
  hKey = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Terminal Server", 0, 0x20019u, &hKey);
  if ( v2 )
  {
    if ( (unsigned int)dword_18012E170 > 2 )
    {
      v14 = v2;
      v7 = "Unable to open TS key in HKLM";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_18012E170,
        (unsigned int)&word_180119BBE,
        0,
        0,
        (__int64)&v7,
        (__int64)&v14);
    }
    if ( v2 > 0 )
      v2 = (unsigned __int16)v2 | 0x80070000;
  }
  else
  {
    cbData = 4;
    v2 = 0;
    Type = 0;
    Data = 0;
    v3 = RegQueryValueExW(hKey, L"TSAppCompat", 0, &Type, (LPBYTE)&Data, &cbData);
    if ( !v3 && cbData == 4 && Type == 4 )
    {
      *a1 = Data;
      if ( (unsigned int)dword_18012E170 > 4 )
      {
        v14 = *a1;
        v7 = "Successfully read APPCOMPAT key";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          (unsigned int)&dword_18012E170,
          (unsigned int)&word_180119BE6,
          0,
          0,
          (__int64)&v7,
          (__int64)&v14);
      }
    }
    else if ( (unsigned int)dword_18012E170 > 4 )
    {
      v14 = *a1;
      v10 = "Unable to read APPCOMPAT key";
      v9 = L"TSAppCompat";
      LODWORD(v7) = v3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        v3,
        (unsigned int)word_180119C12,
        v4,
        v5,
        (__int64)&v10,
        (__int64)&v7,
        (__int64)&v14,
        (__int64)&v9);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800a260c  push    rbp
0x1800a260e  push    rbx
0x1800a260f  push    rdi
0x1800a2610  push    r15
0x1800a2612  mov     rbp, rsp
0x1800a2615  sub     rsp, 68h
0x1800a2619  mov     rdi, rcx
0x1800a261c  mov     dword ptr [rcx], 0
0x1800a2622  lea     rax, [rbp+hKey]
0x1800a2626  mov     [rbp+hKey], 0
0x1800a262e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800a2635  mov     [rsp+68h+phkResult], rax; phkResult
0x1800a263a  mov     r9d, 20019h; samDesired
0x1800a2640  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Ter"...
0x1800a2647  xor     r8d, r8d; ulOptions
0x1800a264a  call    cs:__imp_RegOpenKeyExW
0x1800a2651  nop     dword ptr [rax+rax+00h]
0x1800a2656  mov     ebx, eax
0x1800a2658  test    eax, eax
0x1800a265a  jz      short loc_1800A26B6
0x1800a265c  mov     eax, cs:dword_18012E170
0x1800a2662  cmp     eax, 2
0x1800a2665  jbe     short loc_1800A26A0
0x1800a2667  lea     rax, aUnableToOpenTs; "Unable to open TS key in HKLM"
0x1800a266e  mov     [rbp+arg_18], ebx
0x1800a2671  mov     [rbp+var_28], rax
0x1800a2675  lea     rdx, word_180119BBE
0x1800a267c  lea     rax, [rbp+arg_18]
0x1800a2680  xor     r9d, r9d
0x1800a2683  mov     [rsp+68h+lpcbData], rax
0x1800a2688  lea     rcx, dword_18012E170
0x1800a268f  lea     rax, [rbp+var_28]
0x1800a2693  xor     r8d, r8d
0x1800a2696  mov     [rsp+68h+phkResult], rax
0x1800a269b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800a26a0  test    ebx, ebx
0x1800a26a2  jle     loc_1800A27AD
0x1800a26a8  movzx   ebx, bx
0x1800a26ab  or      ebx, 80070000h
0x1800a26b1  jmp     loc_1800A27AD
0x1800a26b6  mov     rcx, [rbp+hKey]; hKey
0x1800a26ba  lea     rax, [rbp+cbData]
0x1800a26be  mov     [rsp+68h+lpcbData], rax; lpcbData
0x1800a26c3  lea     r15, aTsappcompat; "TSAppCompat"
0x1800a26ca  lea     rax, [rbp+Data]
0x1800a26ce  mov     [rbp+cbData], 4
0x1800a26d5  xor     ebx, ebx
0x1800a26d7  mov     [rsp+68h+phkResult], rax; lpData
0x1800a26dc  lea     r9, [rbp+Type]; lpType
0x1800a26e0  mov     [rbp+Type], ebx
0x1800a26e3  xor     r8d, r8d; lpReserved
0x1800a26e6  mov     [rbp+Data], ebx
0x1800a26e9  mov     rdx, r15; lpValueName
0x1800a26ec  call    cs:__imp_RegQueryValueExW
0x1800a26f3  nop     dword ptr [rax+rax+00h]
0x1800a26f8  mov     ecx, eax
0x1800a26fa  test    eax, eax
0x1800a26fc  jnz     short loc_1800A275B
0x1800a26fe  cmp     [rbp+cbData], 4
0x1800a2702  jnz     short loc_1800A275B
0x1800a2704  cmp     [rbp+Type], 4
0x1800a2708  jnz     short loc_1800A275B
0x1800a270a  mov     eax, [rbp+Data]
0x1800a270d  mov     [rdi], eax
0x1800a270f  mov     eax, cs:dword_18012E170
0x1800a2715  cmp     eax, 4
0x1800a2718  jbe     loc_1800A27AD
0x1800a271e  mov     eax, [rdi]
0x1800a2720  lea     rdx, word_180119BE6
0x1800a2727  mov     [rbp+arg_18], eax
0x1800a272a  lea     rcx, dword_18012E170
0x1800a2731  lea     rax, aSuccessfullyRe_0; "Successfully read APPCOMPAT key"
0x1800a2738  xor     r9d, r9d
0x1800a273b  mov     [rbp+var_28], rax
0x1800a273f  xor     r8d, r8d
0x1800a2742  lea     rax, [rbp+arg_18]
0x1800a2746  mov     [rsp+68h+lpcbData], rax
0x1800a274b  lea     rax, [rbp+var_28]
0x1800a274f  mov     [rsp+68h+phkResult], rax
0x1800a2754  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800a2759  jmp     short loc_1800A27AD
0x1800a275b  mov     eax, cs:dword_18012E170
0x1800a2761  cmp     eax, 4
0x1800a2764  jbe     short loc_1800A27AD
0x1800a2766  mov     eax, [rdi]
0x1800a2768  lea     rdx, word_180119C12
0x1800a276f  mov     [rbp+arg_18], eax
0x1800a2772  lea     rax, aUnableToReadAp; "Unable to read APPCOMPAT key"
0x1800a2779  mov     [rbp+var_10], rax
0x1800a277d  lea     rax, [rbp+var_18]
0x1800a2781  mov     [rsp+68h+var_30], rax
0x1800a2786  lea     rax, [rbp+arg_18]
0x1800a278a  mov     [rsp+68h+var_38], rax
0x1800a278f  lea     rax, [rbp+var_28]
0x1800a2793  mov     [rsp+68h+lpcbData], rax
0x1800a2798  lea     rax, [rbp+var_10]
0x1800a279c  mov     [rsp+68h+phkResult], rax
0x1800a27a1  mov     [rbp+var_18], r15
0x1800a27a5  mov     dword ptr [rbp+var_28], ecx
0x1800a27a8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x1800a27ad  mov     rcx, [rbp+hKey]; hKey
0x1800a27b1  test    rcx, rcx
0x1800a27b4  jz      short loc_1800A27C2
0x1800a27b6  call    cs:__imp_RegCloseKey
0x1800a27bd  nop     dword ptr [rax+rax+00h]
0x1800a27c2  mov     eax, ebx
0x1800a27c4  add     rsp, 68h
0x1800a27c8  pop     r15
0x1800a27ca  pop     rdi
0x1800a27cb  pop     rbx
0x1800a27cc  pop     rbp
0x1800a27cd  retn
```
