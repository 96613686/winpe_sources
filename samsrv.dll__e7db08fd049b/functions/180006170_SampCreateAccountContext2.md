# SampCreateAccountContext2

- ea: `0x180006170`
- end: `0x1800066e8`
- name: `SampCreateAccountContext2`
- size: `1400`
- prototype: ``
- caller_count: `18`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180001760`
- `0x180003d40`
- `0x180005a80`
- `0x180011a00`
- `0x180013ee0`
- `0x180015c50`
- `0x180015e90`
- `0x180022440`
- `0x180056510`
- `0x180056c30`
- `0x1800573f0`
- `0x180062e58`
- `0x180063830`
- `0x180063f50`
- `0x1800683fc`
- `0x18008f330`
- `0x18009acf8`
- `0x1800a1d78`

## callees

- `0x180006170`
- `0x1800066f0`
- `0x180006800`
- `0x180007080`
- `0x180027e24`
- `0x18002cd80`
- `0x18002d720`

## import_xrefs

- `ntdll!RtlpNtOpenKey` at `0x1800063bb`
- `ntdll!RtlpNtOpenKey` at `0x1800063bb`
- `ntdll!RtlInitUnicodeString` at `0x1800066b2`
- `ntdll!RtlInitUnicodeString` at `0x1800066b2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180006579`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180006579`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x1800065c9`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x1800065c9`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtCreateAccountContext` at `0x180006661`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtCreateAccountContext` at `0x180006661`

## string_xrefs

- `0x18000654e`: `DirectoryServiceExtPt`
- `0x180006569`: `SYSTEM\CurrentControlSet\Services\NTDS`

## pseudocode

```c
__int64 __fastcall SampCreateAccountContext2(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        int a6,
        unsigned __int8 a7,
        char a8,
        char a9,
        char a10,
        char a11,
        char a12,
        __int64 a13,
        __int64 *a14)
{
  int v15; // r13d
  unsigned int v17; // ebp
  char v18; // di
  __int64 Context; // rax
  __int64 v20; // rbx
  char v21; // di
  unsigned int v22; // ecx
  NTSTATUS AccountContext; // edi
  __int64 v25; // rdi
  int pdwType; // [rsp+20h] [rbp-338h]
  int pvData; // [rsp+28h] [rbp-330h]
  int pcbData; // [rsp+30h] [rbp-328h]
  int lpReserved; // [rsp+38h] [rbp-320h]
  int lParam; // [rsp+40h] [rbp-318h]
  unsigned int v31; // [rsp+84h] [rbp-2D4h]
  DWORD v32; // [rsp+88h] [rbp-2D0h] BYREF
  __int64 v33; // [rsp+90h] [rbp-2C8h]
  __int64 v34; // [rsp+98h] [rbp-2C0h]
  __int64 v35; // [rsp+A0h] [rbp-2B8h]
  __int64 v36; // [rsp+A8h] [rbp-2B0h]
  __int64 v37; // [rsp+B0h] [rbp-2A8h]
  __int64 *v38; // [rsp+B8h] [rbp-2A0h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+C0h] [rbp-298h] BYREF
  WCHAR String1[264]; // [rsp+F0h] [rbp-268h] BYREF

  v36 = a5;
  v15 = -1073741724;
  v35 = a13;
  v38 = a14;
  v37 = a4;
  v31 = a3;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( a1 )
  {
    v17 = *(_DWORD *)(a1 + 200);
    v18 = *(_BYTE *)(a1 + 28) >> 6;
  }
  else
  {
    v17 = SampTransactionDomainIndexGlobal;
    v18 = 0;
  }
  v34 = 1360LL * v17;
  v33 = *(_QWORD *)((char *)SampDefinedDomains + v34);
  if ( a2 == 2 )
  {
    v15 = -1073741722;
  }
  else if ( a2 == 3 )
  {
    v15 = -1073741487;
  }
  if ( a8 )
  {
    LOBYTE(a3) = 1;
    LODWORD(a4) = 1;
  }
  else
  {
    if ( ((a2 - 2) & 0xFFFFFFFD) == 0 || (LOBYTE(a3) = 0, a2 == 3) )
      LOBYTE(a3) = 1;
    LOBYTE(a4) = 0;
  }
  Context = SampCreateContextEx(a2, a7, a3, a4, a4, a4, a4, 0, v17);
  v20 = Context;
  if ( !Context )
  {
    AccountContext = -1073741670;
    goto LABEL_22;
  }
  *(_BYTE *)(Context + 20) &= ~0x80u;
  *(_BYTE *)(Context + 20) |= a8 << 7;
  v21 = (*(_BYTE *)(Context + 28) ^ (v18 << 6)) & 0x40;
  *(_DWORD *)(Context + 204) = a6;
  *(_BYTE *)(Context + 28) ^= v21;
  *(_BYTE *)(Context + 856) = a12;
  if ( a2 == 2 || a2 == 3 )
  {
    v22 = v31;
    *(_DWORD *)(Context + 248) = v31;
  }
  else if ( a2 == 4 )
  {
    *(_DWORD *)(Context + 248) = v31;
    v22 = v31;
    if ( !a10 )
      *(_BYTE *)(Context + 326) = a9;
  }
  else
  {
    v22 = v31;
  }
  if ( (*(_BYTE *)(v33 + 192) & 2) != 0 )
  {
    memset_0(String1, 0, 0x208u);
    v32 = 520;
    if ( SampDsStopped )
    {
      AccountContext = -1073741146;
    }
    else
    {
      v25 = *(_QWORD *)((char *)SampDefinedDomains + v34 + 8);
      if ( g_ShouldCallNtdsaApiset )
      {
LABEL_40:
        LOBYTE(lParam) = a11;
        LOBYTE(lpReserved) = a10;
        LOBYTE(pcbData) = a9;
        LOBYTE(pvData) = a8;
        LOBYTE(pdwType) = a7;
        AccountContext = NtdsaExtCreateAccountContext(
                           a2,
                           v31,
                           v37,
                           v36,
                           pdwType,
                           pvData,
                           pcbData,
                           lpReserved,
                           lParam,
                           v20,
                           v33,
                           v25,
                           v17,
                           0,
                           v15,
                           v35);
        goto LABEL_20;
      }
      if ( !RegGetValueW(
              HKEY_LOCAL_MACHINE,
              L"SYSTEM\\CurrentControlSet\\Services\\NTDS",
              L"DirectoryServiceExtPt",
              6u,
              0,
              String1,
              &v32)
        && (CompareStringEx(&Annotation, 1u, String1, -1, &Annotation, -1, 0, 0, 0) & 0xFFFFFFFD) != 0 )
      {
        g_ShouldCallNtdsaApiset = 1;
        goto LABEL_40;
      }
      AccountContext = 0;
    }
LABEL_20:
    if ( AccountContext < 0 )
    {
LABEL_21:
      SampDeleteContext((PVOID)v20);
LABEL_22:
      v20 = 0;
      goto LABEL_23;
    }
    goto LABEL_30;
  }
  AccountContext = SampBuildAccountSubKeyName(a2, Context + 160, v22);
  if ( AccountContext < 0 )
  {
    RtlInitUnicodeString((PUNICODE_STRING)(v20 + 160), 0);
    goto LABEL_21;
  }
  if ( a10 )
  {
    ObjectAttributes.RootDirectory = SampKey;
    ObjectAttributes.Length = 48;
    ObjectAttributes.Attributes = 64;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)(v20 + 160);
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    AccountContext = RtlpNtOpenKey((HANDLE)(v20 + 152), 0x2001Fu, &ObjectAttributes, 0);
    if ( AccountContext < 0 )
    {
      *(_QWORD *)(v20 + 152) = -1;
      AccountContext = v15;
      goto LABEL_20;
    }
  }
LABEL_30:
  if ( a1 && *(_DWORD *)(a1 + 16) == 1 && (*(_BYTE *)(a1 + 192) & 2) == 0 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 144));
    *(_QWORD *)(v20 + 1440) = a1;
  }
LABEL_23:
  *v38 = v20;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control[3].Buffer,
      124,
      WPP_48bf36016493398285a8dbc678e80a21_Traceguids,
      (unsigned int)AccountContext,
      AccountContext);
  return (unsigned int)AccountContext;
}

```

## disassembly

```asm
0x180006170  mov     r11, rsp
0x180006173  push    rdi
0x180006174  sub     rsp, 350h
0x18000617b  mov     rax, cs:__security_cookie
0x180006182  xor     rax, rsp
0x180006185  mov     [rsp+358h+var_58], rax
0x18000618d  mov     rax, [rsp+358h+arg_20]
0x180006195  xorps   xmm0, xmm0
0x180006198  mov     [r11-10h], rbx
0x18000619c  mov     [r11-18h], rbp
0x1800061a0  mov     [r11-20h], rsi
0x1800061a4  mov     esi, edx
0x1800061a6  movzx   edx, [rsp+358h+arg_30]
0x1800061ae  mov     [rsp+358h+var_2B0], rax
0x1800061b6  mov     rax, [rsp+358h+arg_60]
0x1800061be  mov     [r11-28h], r12
0x1800061c2  mov     [r11-30h], r13
0x1800061c6  mov     r13d, 0C0000064h
0x1800061cc  mov     [rsp+358h+var_2B8], rax
0x1800061d4  mov     rax, [rsp+358h+arg_68]
0x1800061dc  mov     [r11-38h], r14
0x1800061e0  mov     r14, rcx
0x1800061e3  mov     [rsp+358h+var_2A0], rax
0x1800061eb  mov     [rsp+358h+var_2A8], r9
0x1800061f3  mov     [rsp+358h+var_2D4], r8d
0x1800061fb  mov     [rsp+358h+var_2D8], dl
0x180006202  movups  xmmword ptr [rsp+358h+ObjectAttributes.Length], xmm0
0x18000620a  movups  xmmword ptr [rsp+358h+ObjectAttributes.ObjectName], xmm0
0x180006212  movups  xmmword ptr [rsp+358h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000621a  test    rcx, rcx
0x18000621d  jnz     loc_18000648D
0x180006223  mov     ebp, cs:?SampTransactionDomainIndexGlobal@@3KA; ulong SampTransactionDomainIndexGlobal
0x180006229  xor     dil, dil
0x18000622c  mov     eax, ebp
0x18000622e  imul    rcx, rax, 550h
0x180006235  mov     rax, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x18000623c  mov     [rsp+358h+var_2C0], rcx
0x180006244  mov     rax, [rcx+rax]
0x180006248  mov     ecx, esi
0x18000624a  mov     [rsp+358h+var_2C8], rax
0x180006252  sub     ecx, 2
0x180006255  jz      loc_1800064E2
0x18000625b  sub     ecx, 1
0x18000625e  jz      loc_18000666E
0x180006264  movzx   r12d, [rsp+358h+arg_38]
0x18000626d  test    r12b, r12b
0x180006270  jnz     loc_1800064A0
0x180006276  lea     eax, [rsi-2]
0x180006279  test    eax, 0FFFFFFFDh
0x18000627e  jnz     loc_180006679
0x180006284  mov     r8b, 1
0x180006287  xor     r9b, r9b
0x18000628a  mov     dword ptr [rsp+358h+lParam], ebp
0x18000628e  mov     ecx, esi
0x180006290  mov     byte ptr [rsp+358h+lpReserved], 0
0x180006295  mov     byte ptr [rsp+358h+pcbData], r9b
0x18000629a  mov     byte ptr [rsp+358h+pvData], r9b
0x18000629f  mov     byte ptr [rsp+358h+pdwType], r9b
0x1800062a4  mov     [rsp+358h+var_40], r15
0x1800062ac  call    SampCreateContextEx
0x1800062b1  mov     rbx, rax
0x1800062b4  test    rax, rax
0x1800062b7  jz      loc_1800066BD
0x1800062bd  and     byte ptr [rax+14h], 7Fh
0x1800062c1  mov     ecx, esi
0x1800062c3  movzx   r15d, [rsp+358h+arg_48]
0x1800062cc  movzx   eax, r12b
0x1800062d0  shl     al, 7
0x1800062d3  or      [rbx+14h], al
0x1800062d6  mov     eax, [rsp+358h+arg_28]
0x1800062dd  shl     dil, 6
0x1800062e1  xor     dil, [rbx+1Ch]
0x1800062e5  and     dil, 40h
0x1800062e9  mov     [rbx+0CCh], eax
0x1800062ef  xor     [rbx+1Ch], dil
0x1800062f3  movzx   eax, [rsp+358h+arg_58]
0x1800062fb  mov     [rbx+358h], al
0x180006301  sub     ecx, 2
0x180006304  jz      loc_18000668A
0x18000630a  sub     ecx, 1
0x18000630d  jz      loc_18000668A
0x180006313  cmp     ecx, 1
0x180006316  jz      loc_18000645D
0x18000631c  cmp     esi, 4
0x18000631f  jz      loc_18000646A
0x180006325  mov     ecx, [rsp+358h+var_2D4]
0x18000632c  mov     rax, [rsp+358h+var_2C8]
0x180006334  test    byte ptr [rax+0C0h], 2
0x18000633b  jnz     loc_1800064ED
0x180006341  mov     r8d, ecx
0x180006344  lea     rbp, [rbx+0A0h]
0x18000634b  mov     rdx, rbp
0x18000634e  xor     r9d, r9d
0x180006351  mov     ecx, esi
0x180006353  call    ?SampBuildAccountSubKeyName@@YAJW4_SAMP_OBJECT_TYPE@@PEAU_UNICODE_STRING@@K1@Z; SampBuildAccountSubKeyName(_SAMP_OBJECT_TYPE,_UNICODE_STRING *,ulong,_UNICODE_STRING *)
0x180006358  mov     edi, eax
0x18000635a  test    eax, eax
0x18000635c  js      loc_1800066AD
0x180006362  test    r15b, r15b
0x180006365  jz      loc_1800064AC
0x18000636b  mov     rax, cs:SampKey
0x180006372  lea     r8, [rsp+358h+ObjectAttributes]; ObjectAttributes
0x18000637a  xorps   xmm0, xmm0
0x18000637d  mov     [rsp+358h+ObjectAttributes.RootDirectory], rax
0x180006385  xor     r9d, r9d; Unused
0x180006388  mov     [rsp+358h+ObjectAttributes.Length], 30h ; '0'
0x180006393  mov     edx, 2001Fh; DesiredAccess
0x180006398  mov     [rsp+358h+ObjectAttributes.Attributes], 40h ; '@'
0x1800063a3  lea     rcx, [rbx+98h]; KeyHandle
0x1800063aa  mov     [rsp+358h+ObjectAttributes.ObjectName], rbp
0x1800063b2  movdqu  xmmword ptr [rsp+358h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800063bb  call    cs:__imp_RtlpNtOpenKey
0x1800063c1  mov     edi, eax
0x1800063c3  test    eax, eax
0x1800063c5  jns     loc_1800064AC
0x1800063cb  mov     qword ptr [rbx+98h], 0FFFFFFFFFFFFFFFFh
0x1800063d6  mov     edi, r13d
0x1800063d9  test    edi, edi
0x1800063db  jns     loc_1800064AC
0x1800063e1  mov     rcx, rbx; HandleId
0x1800063e4  call    SampDeleteContext
0x1800063e9  xor     ebx, ebx
0x1800063eb  mov     rax, [rsp+358h+var_2A0]
0x1800063f3  mov     [rax], rbx
0x1800063f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800063fd  mov     r15, [rsp+358h+var_40]
0x180006405  mov     r14, [rsp+358h+var_38]
0x18000640d  mov     r13, [rsp+358h+var_30]
0x180006415  test    dword ptr [rcx+44h], 20000h
0x18000641c  mov     r12, [rsp+358h+var_28]
0x180006424  mov     rsi, [rsp+358h+var_20]
0x18000642c  mov     rbp, [rsp+358h+var_18]
0x180006434  mov     rbx, [rsp+358h+var_10]
0x18000643c  jnz     loc_1800066C7
0x180006442  mov     eax, edi
0x180006444  mov     rcx, [rsp+358h+var_58]
0x18000644c  xor     rcx, rsp; StackCookie
0x18000644f  call    __security_check_cookie
0x180006454  add     rsp, 350h
0x18000645b  pop     rdi
0x18000645c  retn
0x18000645d  mov     edx, [rsp+358h+var_2D4]
0x180006464  mov     [rbx+0F8h], edx
0x18000646a  mov     ecx, [rsp+358h+var_2D4]
0x180006471  test    r15b, r15b
0x180006474  jnz     loc_18000632C
0x18000647a  movzx   eax, [rsp+358h+arg_40]
0x180006482  mov     [rbx+146h], al
0x180006488  jmp     loc_18000632C
0x18000648d  movzx   edi, byte ptr [rcx+1Ch]
0x180006491  mov     ebp, [rcx+0C8h]
0x180006497  shr     dil, 6
0x18000649b  jmp     loc_18000622C
0x1800064a0  mov     r8b, 1
0x1800064a3  movzx   r9d, r8b
0x1800064a7  jmp     loc_18000628A
0x1800064ac  test    r14, r14
0x1800064af  jz      loc_1800063EB
0x1800064b5  cmp     dword ptr [r14+10h], 1
0x1800064ba  jnz     loc_1800063EB
0x1800064c0  test    byte ptr [r14+0C0h], 2
0x1800064c8  jnz     loc_1800063EB
0x1800064ce  lock inc dword ptr [r14+90h]
0x1800064d6  mov     [rbx+5A0h], r14
0x1800064dd  jmp     loc_1800063EB
0x1800064e2  mov     r13d, 0C0000066h
0x1800064e8  jmp     loc_180006264
0x1800064ed  xor     edx, edx; Val
0x1800064ef  lea     rcx, [rsp+358h+String1]; void *
0x1800064f7  mov     r8d, 208h; Size
0x1800064fd  call    memset_0
0x180006502  cmp     cs:?SampDsStopped@@3EA, 0; uchar SampDsStopped
0x180006509  mov     [rsp+358h+var_2D0], 208h
0x180006514  jnz     loc_18000669C
0x18000651a  cmp     cs:?g_ShouldCallNtdsaApiset@@3HA, 0; int g_ShouldCallNtdsaApiset
0x180006521  mov     rax, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x180006528  mov     rdi, [rsp+358h+var_2C0]
0x180006530  mov     rdi, [rdi+rax+8]
0x180006535  jnz     loc_1800065E4
0x18000653b  lea     rax, [rsp+358h+var_2D0]
0x180006543  mov     r9d, 6; dwFlags
0x180006549  mov     [rsp+358h+pcbData], rax; pcbData
0x18000654e  lea     r8, Value; "DirectoryServiceExtPt"
0x180006555  lea     rax, [rsp+358h+String1]
0x18000655d  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180006564  mov     [rsp+358h+pvData], rax; pvData
0x180006569  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\NT"...
0x180006570  mov     [rsp+358h+pdwType], 0; pdwType
0x180006579  call    cs:__imp_RegGetValueW
0x18000657f  test    eax, eax
0x180006581  jnz     loc_1800066A6
0x180006587  mov     [rsp+358h+lParam], 0; lParam
0x180006590  lea     rcx, Annotation; lpLocaleName
0x180006597  mov     [rsp+358h+lpReserved], 0; lpReserved
0x1800065a0  lea     r8, [rsp+358h+String1]; lpString1
0x1800065a8  mov     [rsp+358h+pcbData], 0; lpVersionInformation
0x1800065b1  mov     r9d, 0FFFFFFFFh; cchCount1
0x1800065b7  mov     dword ptr [rsp+358h+pvData], 0FFFFFFFFh; cchCount2
0x1800065bf  mov     edx, 1; dwCmpFlags
0x1800065c4  mov     [rsp+358h+pdwType], rcx; lpString2
0x1800065c9  call    cs:__imp_CompareStringEx
0x1800065cf  test    eax, 0FFFFFFFDh
0x1800065d4  jz      loc_1800066A6
0x1800065da  mov     cs:?g_ShouldCallNtdsaApiset@@3HA, 1; int g_ShouldCallNtdsaApiset
0x1800065e4  mov     rax, [rsp+358h+var_2B8]
0x1800065ec  mov     ecx, esi
0x1800065ee  mov     r9, [rsp+358h+var_2B0]
0x1800065f6  mov     r8, [rsp+358h+var_2A8]
0x1800065fe  mov     edx, [rsp+358h+var_2D4]
0x180006605  mov     [rsp+358h+var_2E0], rax
0x18000660a  mov     rax, [rsp+358h+var_2C8]
0x180006612  mov     [rsp+358h+var_2E8], r13d
0x180006617  mov     [rsp+358h+var_2F0], 0
0x180006620  mov     [rsp+358h+var_2F8], ebp
0x180006624  mov     [rsp+358h+var_300], rdi
0x180006629  mov     [rsp+358h+var_308], rax
0x18000662e  movzx   eax, [rsp+358h+arg_50]
0x180006636  mov     [rsp+358h+var_310], rbx
0x18000663b  mov     byte ptr [rsp+358h+lParam], al
0x18000663f  movzx   eax, [rsp+358h+arg_40]
0x180006647  mov     byte ptr [rsp+358h+lpReserved], r15b
0x18000664c  mov     byte ptr [rsp+358h+pcbData], al
0x180006650  movzx   eax, [rsp+358h+var_2D8]
0x180006658  mov     byte ptr [rsp+358h+pvData], r12b
0x18000665d  mov     byte ptr [rsp+358h+pdwType], al
0x180006661  call    cs:__imp_NtdsaExtCreateAccountContext
0x180006667  mov     edi, eax
0x180006669  jmp     loc_1800063D9
0x18000666e  mov     r13d, 0C0000151h
0x180006674  jmp     loc_180006264
0x180006679  xor     r8b, r8b
0x18000667c  cmp     esi, 3
0x18000667f  jnz     loc_180006287
0x180006685  jmp     loc_180006284
0x18000668a  mov     ecx, [rsp+358h+var_2D4]
0x180006691  mov     [rbx+0F8h], ecx
0x180006697  jmp     loc_18000632C
0x18000669c  mov     edi, 0C00002A6h
0x1800066a1  jmp     loc_1800063D9
0x1800066a6  xor     edi, edi
0x1800066a8  jmp     loc_1800063D9
0x1800066ad  xor     edx, edx; SourceString
0x1800066af  mov     rcx, rbp; DestinationString
0x1800066b2  call    cs:__imp_RtlInitUnicodeString
0x1800066b8  jmp     loc_1800063E1
0x1800066bd  mov     edi, 0C000009Ah
0x1800066c2  jmp     loc_1800063E9
0x1800066c7  mov     rcx, [rcx+38h]
0x1800066cb  lea     r8, WPP_48bf36016493398285a8dbc678e80a21_Traceguids
0x1800066d2  mov     edx, 7Ch ; '|'
0x1800066d7  mov     dword ptr [rsp+358h+pdwType], edi
0x1800066db  mov     r9d, edi
0x1800066de  call    WPP_SF_Dd
0x1800066e3  jmp     loc_180006442
```
