# FillServerCertificateInfo

- ea: `0x1800316bc`
- end: `0x180031bdc`
- name: `FillServerCertificateInfo`
- size: `1312`
- prototype: `__int64 __fastcall(const WCHAR *Src, int, __int64, int, HLOCAL *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180031520`

## callees

- `0x180002038`
- `0x180020de8`
- `0x1800214a4`
- `0x1800316bc`
- `0x180031be4`
- `0x1800345b4`
- `0x1800435f8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031722`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003176d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031722`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003176d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031bb8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031bb8`
- `ntdll!RtlFreeUnicodeString` at `0x180031ad4`
- `ntdll!RtlFreeUnicodeString` at `0x180031ad4`
- `ntdll!RtlNtStatusToDosError` at `0x18003198c`
- `ntdll!RtlNtStatusToDosError` at `0x1800319e4`
- `ntdll!RtlNtStatusToDosError` at `0x180031a73`
- `ntdll!RtlNtStatusToDosError` at `0x18003198c`
- `ntdll!RtlNtStatusToDosError` at `0x1800319e4`
- `ntdll!RtlNtStatusToDosError` at `0x180031a73`
- `ntdll!RtlUnicodeStringToInteger` at `0x18003196f`
- `ntdll!RtlUnicodeStringToInteger` at `0x180031a56`
- `ntdll!RtlUnicodeStringToInteger` at `0x18003196f`
- `ntdll!RtlUnicodeStringToInteger` at `0x180031a56`
- `ntdll!RtlInitUnicodeString` at `0x180031797`
- `ntdll!RtlInitUnicodeString` at `0x1800317c8`
- `ntdll!RtlInitUnicodeString` at `0x1800317f9`
- `ntdll!RtlInitUnicodeString` at `0x18003182a`
- `ntdll!RtlInitUnicodeString` at `0x18003185b`
- `ntdll!RtlInitUnicodeString` at `0x18003188c`
- `ntdll!RtlInitUnicodeString` at `0x1800318bd`
- `ntdll!RtlInitUnicodeString` at `0x1800318ee`
- `ntdll!RtlInitUnicodeString` at `0x18003191f`
- `ntdll!RtlInitUnicodeString` at `0x180031a05`
- `ntdll!RtlInitUnicodeString` at `0x180031797`
- `ntdll!RtlInitUnicodeString` at `0x1800317c8`
- `ntdll!RtlInitUnicodeString` at `0x1800317f9`
- `ntdll!RtlInitUnicodeString` at `0x18003182a`
- `ntdll!RtlInitUnicodeString` at `0x18003185b`
- `ntdll!RtlInitUnicodeString` at `0x18003188c`
- `ntdll!RtlInitUnicodeString` at `0x1800318bd`
- `ntdll!RtlInitUnicodeString` at `0x1800318ee`
- `ntdll!RtlInitUnicodeString` at `0x18003191f`
- `ntdll!RtlInitUnicodeString` at `0x180031a05`

## string_xrefs

- `0x1800318e3`: `StoreName`

## pseudocode

```c
__int64 __fastcall FillServerCertificateInfo(const WCHAR *Src, int a2, __int64 a3, int a4, HLOCAL *a5)
{
  HLOCAL *v9; // rdi
  HLOCAL v10; // rax
  __int64 v11; // rdx
  ULONG CertFieldString; // ebx
  __int64 v13; // r14
  __int64 v14; // rax
  SIZE_T v15; // rbx
  HLOCAL v16; // rax
  __int64 v17; // rax
  int v18; // eax
  unsigned int v19; // ebx
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int64 v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // rdx
  __int64 v29; // rdx
  ULONG v30; // [rsp+20h] [rbp-50h] BYREF
  WCHAR *v31; // [rsp+28h] [rbp-48h] BYREF
  WCHAR *v32; // [rsp+30h] [rbp-40h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-38h] BYREF
  UNICODE_STRING String; // [rsp+48h] [rbp-28h] BYREF
  LPCWSTR Strings[3]; // [rsp+58h] [rbp-18h] BYREF
  ULONG Value; // [rsp+B8h] [rbp+48h] BYREF

  Value = 0;
  v31 = 0;
  v30 = 0;
  v32 = 0;
  *(_OWORD *)Strings = 0;
  DestinationString = 0;
  String = 0;
  if ( a4 )
    return 124;
  v9 = a5;
  if ( !*a5 )
  {
    v10 = LocalAlloc(0x40u, 0x60u);
    *v9 = v10;
    if ( !v10 )
      goto LABEL_5;
  }
  if ( a2 != 7 )
    goto LABEL_38;
  v13 = -1;
  v14 = -1;
  do
    ++v14;
  while ( Src[v14] );
  if ( !v14 )
  {
LABEL_38:
    Strings[0] = Src;
    Strings[1] = L"Certs";
    SsLogEvent(0x800009CA, 2u, Strings);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_3d8d68fd59dd345388a9abd81eb39218_Traceguids, Src);
    }
    CertFieldString = 13;
    goto LABEL_43;
  }
  v15 = 2 * v14 + 2;
  v16 = LocalAlloc(0x40u, v15);
  *(_QWORD *)*v9 = v16;
  if ( v16 )
  {
    memcpy_0(v16, Src, v15);
    RtlInitUnicodeString(&DestinationString, L"Subject");
    CertFieldString = SsGetCertFieldString(Src, a3, &DestinationString, (char *)*v9 + 8);
    if ( !CertFieldString )
    {
      RtlInitUnicodeString(&DestinationString, L"Issuer");
      CertFieldString = SsGetCertFieldString(Src, a3, &DestinationString, (char *)*v9 + 16);
      if ( !CertFieldString )
      {
        RtlInitUnicodeString(&DestinationString, L"ThumbPrint");
        CertFieldString = SsGetCertFieldString(Src, a3, &DestinationString, (char *)*v9 + 24);
        if ( !CertFieldString )
        {
          RtlInitUnicodeString(&DestinationString, L"FriendlyName");
          CertFieldString = SsGetCertFieldString(Src, a3, &DestinationString, (char *)*v9 + 32);
          if ( !CertFieldString )
          {
            RtlInitUnicodeString(&DestinationString, L"NotBefore");
            CertFieldString = SsGetCertFieldString(Src, a3, &DestinationString, (char *)*v9 + 40);
            if ( !CertFieldString )
            {
              RtlInitUnicodeString(&DestinationString, L"NotAfter");
              CertFieldString = SsGetCertFieldString(Src, a3, &DestinationString, (char *)*v9 + 48);
              if ( !CertFieldString )
              {
                RtlInitUnicodeString(&DestinationString, L"StoreLocation");
                CertFieldString = SsGetCertFieldString(Src, a3, &DestinationString, (char *)*v9 + 56);
                if ( !CertFieldString )
                {
                  RtlInitUnicodeString(&DestinationString, L"StoreName");
                  CertFieldString = SsGetCertFieldString(Src, a3, &DestinationString, (char *)*v9 + 64);
                  if ( !CertFieldString )
                  {
                    RtlInitUnicodeString(&DestinationString, L"Type");
                    CertFieldString = SsGetCertFieldString(Src, a3, &DestinationString, &v31);
                    if ( !CertFieldString )
                    {
                      v17 = -1;
                      String.Buffer = v31;
                      do
                        ++v17;
                      while ( v31[v17] );
                      String.MaximumLength = 2 * (v17 + 1);
                      String.Length = String.MaximumLength;
                      v18 = RtlUnicodeStringToInteger(&String, 0, &Value);
                      v19 = v18;
                      if ( v18 >= 0 )
                      {
                        *((_DWORD *)*v9 + 20) = Value;
                        RtlInitUnicodeString(&DestinationString, L"Flags");
                        CertFieldString = SsGetCertFieldString(Src, a3, &DestinationString, &v32);
                        if ( CertFieldString )
                          goto LABEL_43;
                        String.Buffer = v32;
                        do
                          ++v13;
                        while ( v32[v13] );
                        String.MaximumLength = 2 * (v13 + 1);
                        String.Length = String.MaximumLength;
                        v22 = RtlUnicodeStringToInteger(&String, 0, &v30);
                        v19 = v22;
                        if ( v22 >= 0 )
                        {
                          *((_DWORD *)*v9 + 21) = v30;
                          RtlFreeUnicodeString(&String);
                          return 0;
                        }
                        Strings[0] = Src;
                        Strings[1] = L"Certs";
                        RtlNtStatusToDosError(v22);
                        SsLogEvent(0x800009CA, 2u, Strings);
                        v20 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
                          || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
                        {
                          goto LABEL_28;
                        }
                        v21 = 31;
                      }
                      else
                      {
                        Strings[0] = Src;
                        Strings[1] = L"Certs";
                        RtlNtStatusToDosError(v18);
                        SsLogEvent(0x800009CA, 2u, Strings);
                        v20 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
                          || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
                        {
                          goto LABEL_28;
                        }
                        v21 = 30;
                      }
                      WPP_SF_d(v20[2], v21, WPP_3d8d68fd59dd345388a9abd81eb39218_Traceguids, v19);
LABEL_28:
                      CertFieldString = RtlNtStatusToDosError(v19);
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  else
  {
LABEL_5:
    CertFieldString = 8;
  }
LABEL_43:
  if ( *v9 )
  {
    LOBYTE(v11) = 1;
    FreeCertField(*v9, v11);
    LOBYTE(v23) = 1;
    FreeCertField((char *)*v9 + 8, v23);
    LOBYTE(v24) = 1;
    FreeCertField((char *)*v9 + 24, v24);
    LOBYTE(v25) = 1;
    FreeCertField((char *)*v9 + 32, v25);
    LOBYTE(v26) = 1;
    FreeCertField((char *)*v9 + 40, v26);
    LOBYTE(v27) = 1;
    FreeCertField((char *)*v9 + 48, v27);
    LOBYTE(v28) = 1;
    FreeCertField((char *)*v9 + 56, v28);
    LOBYTE(v29) = 1;
    FreeCertField((char *)*v9 + 64, v29);
    LocalFree(*v9);
    *v9 = 0;
  }
  return CertFieldString;
}

```

## disassembly

```asm
0x1800316bc  mov     [rsp-28h+arg_0], rbx
0x1800316c1  mov     [rsp-28h+arg_8], rsi
0x1800316c6  push    rbp
0x1800316c7  push    rdi
0x1800316c8  push    r12
0x1800316ca  push    r14
0x1800316cc  push    r15
0x1800316ce  mov     rbp, rsp
0x1800316d1  sub     rsp, 70h
0x1800316d5  xor     r12d, r12d
0x1800316d8  xorps   xmm0, xmm0
0x1800316db  mov     [rbp+Value], r12d
0x1800316df  xorps   xmm1, xmm1
0x1800316e2  mov     [rbp+var_48], r12
0x1800316e6  mov     r15, r8
0x1800316e9  mov     [rbp+var_50], r12d
0x1800316ed  mov     ebx, edx
0x1800316ef  mov     [rbp+var_40], r12
0x1800316f3  mov     rsi, rcx
0x1800316f6  movups  xmmword ptr [rbp+Strings], xmm0
0x1800316fa  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x1800316fe  movups  xmmword ptr [rbp+String.Length], xmm0
0x180031702  test    r9d, r9d
0x180031705  jz      short loc_180031711
0x180031707  lea     eax, [r12+7Ch]
0x18003170c  jmp     loc_180031BC3
0x180031711  mov     rdi, [rbp+arg_20]
0x180031715  cmp     [rdi], r12
0x180031718  jnz     short loc_18003173A
0x18003171a  mov     edx, 60h ; '`'; uBytes
0x18003171f  lea     ecx, [rdx-20h]; uFlags
0x180031722  call    cs:__imp_LocalAlloc
0x180031728  mov     [rdi], rax
0x18003172b  test    rax, rax
0x18003172e  jnz     short loc_18003173A
0x180031730  mov     ebx, 8
0x180031735  jmp     loc_180031B44
0x18003173a  cmp     ebx, 7
0x18003173d  jnz     loc_180031AE1
0x180031743  or      r14, 0FFFFFFFFFFFFFFFFh
0x180031747  mov     rax, r14
0x18003174a  inc     rax
0x18003174d  cmp     [rsi+rax*2], r12w
0x180031752  jnz     short loc_18003174A
0x180031754  test    rax, rax
0x180031757  jz      loc_180031AE1
0x18003175d  lea     rbx, ds:2[rax*2]
0x180031765  mov     ecx, 40h ; '@'; uFlags
0x18003176a  mov     rdx, rbx; uBytes
0x18003176d  call    cs:__imp_LocalAlloc
0x180031773  mov     rcx, [rdi]
0x180031776  mov     [rcx], rax
0x180031779  test    rax, rax
0x18003177c  jz      short loc_180031730
0x18003177e  mov     r8, rbx; Size
0x180031781  mov     rdx, rsi; Src
0x180031784  mov     rcx, rax; void *
0x180031787  call    memcpy_0
0x18003178c  lea     rdx, aSubject; "Subject"
0x180031793  lea     rcx, [rbp+DestinationString]; DestinationString
0x180031797  call    cs:__imp_RtlInitUnicodeString
0x18003179d  mov     r9, [rdi]
0x1800317a0  lea     r8, [rbp+DestinationString]
0x1800317a4  add     r9, 8
0x1800317a8  mov     rdx, r15
0x1800317ab  mov     rcx, rsi
0x1800317ae  call    SsGetCertFieldString
0x1800317b3  mov     ebx, eax
0x1800317b5  test    eax, eax
0x1800317b7  jnz     loc_180031B44
0x1800317bd  lea     rdx, aIssuer; "Issuer"
0x1800317c4  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800317c8  call    cs:__imp_RtlInitUnicodeString
0x1800317ce  mov     r9, [rdi]
0x1800317d1  lea     r8, [rbp+DestinationString]
0x1800317d5  add     r9, 10h
0x1800317d9  mov     rdx, r15
0x1800317dc  mov     rcx, rsi
0x1800317df  call    SsGetCertFieldString
0x1800317e4  mov     ebx, eax
0x1800317e6  test    eax, eax
0x1800317e8  jnz     loc_180031B44
0x1800317ee  lea     rdx, aThumbprint; "ThumbPrint"
0x1800317f5  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800317f9  call    cs:__imp_RtlInitUnicodeString
0x1800317ff  mov     r9, [rdi]
0x180031802  lea     r8, [rbp+DestinationString]
0x180031806  add     r9, 18h
0x18003180a  mov     rdx, r15
0x18003180d  mov     rcx, rsi
0x180031810  call    SsGetCertFieldString
0x180031815  mov     ebx, eax
0x180031817  test    eax, eax
0x180031819  jnz     loc_180031B44
0x18003181f  lea     rdx, aFriendlyname; "FriendlyName"
0x180031826  lea     rcx, [rbp+DestinationString]; DestinationString
0x18003182a  call    cs:__imp_RtlInitUnicodeString
0x180031830  mov     r9, [rdi]
0x180031833  lea     r8, [rbp+DestinationString]
0x180031837  add     r9, 20h ; ' '
0x18003183b  mov     rdx, r15
0x18003183e  mov     rcx, rsi
0x180031841  call    SsGetCertFieldString
0x180031846  mov     ebx, eax
0x180031848  test    eax, eax
0x18003184a  jnz     loc_180031B44
0x180031850  lea     rdx, aNotbefore; "NotBefore"
0x180031857  lea     rcx, [rbp+DestinationString]; DestinationString
0x18003185b  call    cs:__imp_RtlInitUnicodeString
0x180031861  mov     r9, [rdi]
0x180031864  lea     r8, [rbp+DestinationString]
0x180031868  add     r9, 28h ; '('
0x18003186c  mov     rdx, r15
0x18003186f  mov     rcx, rsi
0x180031872  call    SsGetCertFieldString
0x180031877  mov     ebx, eax
0x180031879  test    eax, eax
0x18003187b  jnz     loc_180031B44
0x180031881  lea     rdx, aNotafter; "NotAfter"
0x180031888  lea     rcx, [rbp+DestinationString]; DestinationString
0x18003188c  call    cs:__imp_RtlInitUnicodeString
0x180031892  mov     r9, [rdi]
0x180031895  lea     r8, [rbp+DestinationString]
0x180031899  add     r9, 30h ; '0'
0x18003189d  mov     rdx, r15
0x1800318a0  mov     rcx, rsi
0x1800318a3  call    SsGetCertFieldString
0x1800318a8  mov     ebx, eax
0x1800318aa  test    eax, eax
0x1800318ac  jnz     loc_180031B44
0x1800318b2  lea     rdx, aStorelocation; "StoreLocation"
0x1800318b9  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800318bd  call    cs:__imp_RtlInitUnicodeString
0x1800318c3  mov     r9, [rdi]
0x1800318c6  lea     r8, [rbp+DestinationString]
0x1800318ca  add     r9, 38h ; '8'
0x1800318ce  mov     rdx, r15
0x1800318d1  mov     rcx, rsi
0x1800318d4  call    SsGetCertFieldString
0x1800318d9  mov     ebx, eax
0x1800318db  test    eax, eax
0x1800318dd  jnz     loc_180031B44
0x1800318e3  lea     rdx, aStorename; "StoreName"
0x1800318ea  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800318ee  call    cs:__imp_RtlInitUnicodeString
0x1800318f4  mov     r9, [rdi]
0x1800318f7  lea     r8, [rbp+DestinationString]
0x1800318fb  add     r9, 40h ; '@'
0x1800318ff  mov     rdx, r15
0x180031902  mov     rcx, rsi
0x180031905  call    SsGetCertFieldString
0x18003190a  mov     ebx, eax
0x18003190c  test    eax, eax
0x18003190e  jnz     loc_180031B44
0x180031914  lea     rdx, aType_0; "Type"
0x18003191b  lea     rcx, [rbp+DestinationString]; DestinationString
0x18003191f  call    cs:__imp_RtlInitUnicodeString
0x180031925  lea     r9, [rbp+var_48]
0x180031929  mov     rdx, r15
0x18003192c  lea     r8, [rbp+DestinationString]
0x180031930  mov     rcx, rsi
0x180031933  call    SsGetCertFieldString
0x180031938  mov     ebx, eax
0x18003193a  test    eax, eax
0x18003193c  jnz     loc_180031B44
0x180031942  mov     rcx, [rbp+var_48]
0x180031946  mov     rax, r14
0x180031949  mov     [rbp+String.Buffer], rcx
0x18003194d  inc     rax
0x180031950  cmp     [rcx+rax*2], r12w
0x180031955  jnz     short loc_18003194D
0x180031957  inc     ax
0x18003195a  lea     r8, [rbp+Value]; Value
0x18003195e  add     ax, ax
0x180031961  lea     rcx, [rbp+String]; String
0x180031965  xor     edx, edx; Base
0x180031967  mov     [rbp+String.MaximumLength], ax
0x18003196b  mov     [rbp+String.Length], ax
0x18003196f  call    cs:__imp_RtlUnicodeStringToInteger
0x180031975  mov     ebx, eax
0x180031977  test    eax, eax
0x180031979  jns     short loc_1800319F1
0x18003197b  lea     rcx, aCerts; "Certs"
0x180031982  mov     [rbp+Strings], rsi
0x180031986  mov     [rbp+Strings+8], rcx
0x18003198a  mov     ecx, eax; Status
0x18003198c  call    cs:__imp_RtlNtStatusToDosError
0x180031992  lea     r8, [rbp+Strings]; lpStrings
0x180031996  mov     edx, 2; wNumStrings
0x18003199b  mov     r9d, eax
0x18003199e  mov     ecx, 800009CAh; dwEventID
0x1800319a3  call    SsLogEvent
0x1800319a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800319af  lea     rax, WPP_GLOBAL_Control
0x1800319b6  cmp     rcx, rax
0x1800319b9  jz      short loc_1800319E2
0x1800319bb  test    dword ptr [rcx+1Ch], 100h
0x1800319c2  jz      short loc_1800319E2
0x1800319c4  cmp     byte ptr [rcx+19h], 1
0x1800319c8  jb      short loc_1800319E2
0x1800319ca  mov     edx, 1Eh
0x1800319cf  mov     rcx, [rcx+10h]
0x1800319d3  lea     r8, WPP_3d8d68fd59dd345388a9abd81eb39218_Traceguids
0x1800319da  mov     r9d, ebx
0x1800319dd  call    WPP_SF_d
0x1800319e2  mov     ecx, ebx; Status
0x1800319e4  call    cs:__imp_RtlNtStatusToDosError
0x1800319ea  mov     ebx, eax
0x1800319ec  jmp     loc_180031B44
0x1800319f1  mov     rcx, [rdi]
0x1800319f4  lea     rdx, aFlags; "Flags"
0x1800319fb  mov     eax, [rbp+Value]
0x1800319fe  mov     [rcx+50h], eax
0x180031a01  lea     rcx, [rbp+DestinationString]; DestinationString
0x180031a05  call    cs:__imp_RtlInitUnicodeString
0x180031a0b  lea     r9, [rbp+var_40]
0x180031a0f  mov     rdx, r15
0x180031a12  lea     r8, [rbp+DestinationString]
0x180031a16  mov     rcx, rsi
0x180031a19  call    SsGetCertFieldString
0x180031a1e  mov     ebx, eax
0x180031a20  test    eax, eax
0x180031a22  jnz     loc_180031B44
0x180031a28  mov     rax, [rbp+var_40]
0x180031a2c  mov     [rbp+String.Buffer], rax
0x180031a30  inc     r14
0x180031a33  cmp     [rax+r14*2], r12w
0x180031a38  jnz     short loc_180031A30
0x180031a3a  inc     r14w
0x180031a3e  lea     r8, [rbp+var_50]; Value
0x180031a42  add     r14w, r14w
0x180031a46  lea     rcx, [rbp+String]; String
0x180031a4a  xor     edx, edx; Base
0x180031a4c  mov     [rbp+String.MaximumLength], r14w
0x180031a51  mov     [rbp+String.Length], r14w
0x180031a56  call    cs:__imp_RtlUnicodeStringToInteger
0x180031a5c  mov     ebx, eax
0x180031a5e  test    eax, eax
0x180031a60  jns     short loc_180031AC7
0x180031a62  lea     rcx, aCerts; "Certs"
0x180031a69  mov     [rbp+Strings], rsi
0x180031a6d  mov     [rbp+Strings+8], rcx
0x180031a71  mov     ecx, eax; Status
0x180031a73  call    cs:__imp_RtlNtStatusToDosError
0x180031a79  lea     r8, [rbp+Strings]; lpStrings
0x180031a7d  mov     edx, 2; wNumStrings
0x180031a82  mov     r9d, eax
0x180031a85  mov     ecx, 800009CAh; dwEventID
0x180031a8a  call    SsLogEvent
0x180031a8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180031a96  lea     rax, WPP_GLOBAL_Control
0x180031a9d  cmp     rcx, rax
0x180031aa0  jz      loc_1800319E2
0x180031aa6  test    dword ptr [rcx+1Ch], 100h
0x180031aad  jz      loc_1800319E2
0x180031ab3  cmp     byte ptr [rcx+19h], 1
0x180031ab7  jb      loc_1800319E2
0x180031abd  mov     edx, 1Fh
0x180031ac2  jmp     loc_1800319CF
0x180031ac7  mov     rcx, [rdi]
0x180031aca  mov     eax, [rbp+var_50]
0x180031acd  mov     [rcx+54h], eax
0x180031ad0  lea     rcx, [rbp+String]; UnicodeString
0x180031ad4  call    cs:__imp_RtlFreeUnicodeString
0x180031ada  xor     eax, eax
0x180031adc  jmp     loc_180031BC3
0x180031ae1  lea     rcx, aCerts; "Certs"
0x180031ae8  mov     [rbp+Strings], rsi
0x180031aec  xor     r9d, r9d
0x180031aef  mov     [rbp+Strings+8], rcx
0x180031af3  lea     r8, [rbp+Strings]; lpStrings
0x180031af7  mov     ecx, 800009CAh; dwEventID
0x180031afc  lea     edx, [r9+2]; wNumStrings
0x180031b00  call    SsLogEvent
0x180031b05  mov     rcx, cs:WPP_GLOBAL_Control
0x180031b0c  lea     rax, WPP_GLOBAL_Control
0x180031b13  cmp     rcx, rax
0x180031b16  jz      short loc_180031B3F
0x180031b18  test    dword ptr [rcx+1Ch], 100h
0x180031b1f  jz      short loc_180031B3F
0x180031b21  cmp     byte ptr [rcx+19h], 1
0x180031b25  jb      short loc_180031B3F
0x180031b27  mov     rcx, [rcx+10h]
0x180031b2b  lea     r8, WPP_3d8d68fd59dd345388a9abd81eb39218_Traceguids
0x180031b32  mov     edx, 1Dh
0x180031b37  mov     r9, rsi
0x180031b3a  call    WPP_SF_S
0x180031b3f  mov     ebx, 0Dh
0x180031b44  mov     rcx, [rdi]
0x180031b47  test    rcx, rcx
0x180031b4a  jz      short loc_180031BC1
0x180031b4c  mov     dl, 1
0x180031b4e  call    FreeCertField
0x180031b53  mov     rcx, [rdi]
0x180031b56  mov     dl, 1
0x180031b58  add     rcx, 8
0x180031b5c  call    FreeCertField
0x180031b61  mov     rcx, [rdi]
0x180031b64  mov     dl, 1
0x180031b66  add     rcx, 18h
  ... truncated ...
```
