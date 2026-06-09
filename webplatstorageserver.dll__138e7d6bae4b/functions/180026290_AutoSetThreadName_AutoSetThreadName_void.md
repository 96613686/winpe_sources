# AutoSetThreadName::~AutoSetThreadName(void)

- ea: `0x180026290`
- end: `0x1800263ea`
- name: `??1AutoSetThreadName@@QEAA@XZ`
- size: `346`
- prototype: `void __fastcall(AutoSetThreadName *__hidden this)`
- caller_count: `18`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800256a0`
- `0x1800bcfe6`
- `0x1800bd0a2`
- `0x1800be463`
- `0x1800be5e4`
- `0x1800be930`
- `0x1800bea52`
- `0x1800beba8`
- `0x1800bf9be`
- `0x1800c00ba`
- `0x1800c030d`
- `0x1800c03f2`
- `0x1800c1699`
- `0x1800c18ad`
- `0x1800c19d7`
- `0x1800c1fc2`
- `0x1800c2fc7`
- `0x1800c3fc3`

## callees

- `0x180026290`
- `0x180027550`
- `0x180080fb0`
- `0x1800b5f04`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180026321`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180026321`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180026333`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180026333`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x18002632d`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x18002632d`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800262cc`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800262cc`

## pseudocode

```c
void __fastcall AutoSetThreadName::~AutoSetThreadName(AutoSetThreadName *this)
{
  const WCHAR *v1; // rbx
  const wchar_t *v2; // rax
  int v3; // eax
  unsigned __int16 *v4; // rdx
  HANDLE CurrentThread; // rax
  APTTYPEQUALIFIER pAptQualifier; // [rsp+30h] [rbp-128h] BYREF
  APTTYPE pAptType[3]; // [rsp+34h] [rbp-124h] BYREF
  unsigned __int16 v8[128]; // [rsp+40h] [rbp-118h] BYREF

  v1 = &word_1800D6108;
  pAptType[0] = APTTYPE_STA;
  pAptQualifier = APTTYPEQUALIFIER_NONE;
  if ( CoGetApartmentType(pAptType, &pAptQualifier) )
    goto LABEL_9;
  if ( pAptType[0] == APTTYPE_STA )
    goto LABEL_14;
  if ( pAptType[0] != APTTYPE_MTA )
  {
    if ( pAptType[0] == APTTYPE_NA )
    {
      switch ( pAptQualifier )
      {
        case APTTYPEQUALIFIER_NA_ON_MTA:
          v2 = L"NA on MTA";
          break;
        case APTTYPEQUALIFIER_NA_ON_STA:
          v2 = L"NA on STA";
          break;
        case APTTYPEQUALIFIER_NA_ON_IMPLICIT_MTA:
          v2 = L"NA on MTA Implicit";
          break;
        case APTTYPEQUALIFIER_NA_ON_MAINSTA:
          v2 = L"NA on MAINSTA";
          break;
        default:
          v2 = L"NA";
          break;
      }
      goto LABEL_6;
    }
    if ( pAptType[0] != APTTYPE_MAINSTA )
      goto LABEL_9;
LABEL_14:
    v2 = L"ASTA";
    if ( pAptQualifier != APTTYPEQUALIFIER_APPLICATION_STA )
      v2 = L"STA";
    goto LABEL_6;
  }
  if ( pAptQualifier == APTTYPEQUALIFIER_IMPLICIT_MTA )
    v2 = (const wchar_t *)L"MTA Implicit";
  else
    v2 = L"MTA";
LABEL_6:
  v3 = StringCchPrintfW(v8, 0x80u, L"%s %s", &word_1800D6108, v2);
  v4 = v8;
  if ( v3 < 0 )
    v4 = (unsigned __int16 *)&word_1800D6108;
  v1 = v4;
LABEL_9:
  CurrentThread = GetCurrentThread();
  SetThreadDescription(CurrentThread, v1);
  if ( IsDebuggerPresent() )
    SetThreadNameViaException(v1);
}

```

## disassembly

```asm
0x180026290  push    rbx
0x180026292  sub     rsp, 150h
0x180026299  mov     rax, cs:__security_cookie
0x1800262a0  xor     rax, rsp
0x1800262a3  mov     [rsp+158h+var_18], rax
0x1800262ab  lea     rbx, word_1800D6108
0x1800262b2  mov     [rsp+158h+pAptType], 0
0x1800262ba  mov     [rsp+158h+pAptQualifier], 0
0x1800262c2  lea     rdx, [rsp+158h+pAptQualifier]; pAptQualifier
0x1800262c7  lea     rcx, [rsp+158h+pAptType]; pAptType
0x1800262cc  call    cs:__imp_CoGetApartmentType
0x1800262d2  test    eax, eax
0x1800262d4  jnz     short loc_180026321
0x1800262d6  mov     ecx, [rsp+158h+pAptType]
0x1800262da  test    ecx, ecx
0x1800262dc  jz      loc_18002636D
0x1800262e2  sub     ecx, 1
0x1800262e5  jnz     short loc_180026363
0x1800262e7  cmp     [rsp+158h+pAptQualifier], 1
0x1800262ec  jnz     short loc_18002635A
0x1800262ee  lea     rax, aMtaImplicit; "MTA Implicit"
0x1800262f5  mov     [rsp+158h+var_138], rax
0x1800262fa  mov     r9, rbx
0x1800262fd  lea     r8, aSS_1; "%s %s"
0x180026304  mov     edx, 80h; unsigned __int64
0x180026309  lea     rcx, [rsp+158h+var_118]; unsigned __int16 *
0x18002630e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180026313  lea     rdx, [rsp+158h+var_118]
0x180026318  test    eax, eax
0x18002631a  cmovs   rdx, rbx
0x18002631e  mov     rbx, rdx
0x180026321  call    cs:__imp_GetCurrentThread
0x180026327  mov     rcx, rax; hThread
0x18002632a  mov     rdx, rbx; lpThreadDescription
0x18002632d  call    cs:__imp_SetThreadDescription
0x180026333  call    cs:__imp_IsDebuggerPresent
0x180026339  test    eax, eax
0x18002633b  jnz     loc_1800263DD
0x180026341  mov     rcx, [rsp+158h+var_18]
0x180026349  xor     rcx, rsp; StackCookie
0x18002634c  call    __security_check_cookie
0x180026351  add     rsp, 150h
0x180026358  pop     rbx
0x180026359  retn
0x18002635a  lea     rax, aMta; "MTA"
0x180026361  jmp     short loc_1800262F5
0x180026363  sub     ecx, 1
0x180026366  jz      short loc_180026389
0x180026368  cmp     ecx, 1
0x18002636b  jnz     short loc_180026321
0x18002636d  lea     rax, aAsta; "ASTA"
0x180026374  lea     rcx, aSta; "STA"
0x18002637b  cmp     [rsp+158h+pAptQualifier], 6
0x180026380  cmovnz  rax, rcx
0x180026384  jmp     loc_1800262F5
0x180026389  mov     ecx, [rsp+158h+pAptQualifier]
0x18002638d  sub     ecx, 2
0x180026390  jz      short loc_1800263D1
0x180026392  sub     ecx, 1
0x180026395  jz      short loc_1800263C5
0x180026397  sub     ecx, 1
0x18002639a  jz      short loc_1800263B9
0x18002639c  cmp     ecx, 1
0x18002639f  jz      short loc_1800263AD
0x1800263a1  lea     rax, aNa; "NA"
0x1800263a8  jmp     loc_1800262F5
0x1800263ad  lea     rax, aNaOnMainsta; "NA on MAINSTA"
0x1800263b4  jmp     loc_1800262F5
0x1800263b9  lea     rax, aNaOnMtaImplici; "NA on MTA Implicit"
0x1800263c0  jmp     loc_1800262F5
0x1800263c5  lea     rax, aNaOnSta; "NA on STA"
0x1800263cc  jmp     loc_1800262F5
0x1800263d1  lea     rax, aNaOnMta; "NA on MTA"
0x1800263d8  jmp     loc_1800262F5
0x1800263dd  mov     rcx, rbx; lpWideCharStr
0x1800263e0  call    SetThreadNameViaException
0x1800263e5  jmp     loc_180026341
```
