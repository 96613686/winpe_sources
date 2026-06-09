# SetThreadName

- ea: `0x1800273f0`
- end: `0x18002753c`
- name: `SetThreadName`
- size: `332`
- prototype: `__int64 __fastcall(LPCWCH lpWideCharStr)`
- caller_count: `112`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180007280`
- `0x1800077d0`
- `0x18001d1c0`
- `0x18001ea30`
- `0x18001edc0`
- `0x18001f8c0`
- `0x180028180`
- `0x180028c90`
- `0x180028fa0`
- `0x18002b000`
- `0x18002b830`
- `0x18002bf80`
- `0x18002ce80`
- `0x18002d340`
- `0x18002d980`
- `0x18002dbd0`
- `0x18002e740`
- `0x18002ebd0`
- `0x18002f6c0`
- `0x1800328a4`
- `0x180035550`
- `0x180037f50`
- `0x180039020`
- `0x180039db0`
- `0x18003bffc`
- `0x18003cf30`
- `0x18003d2b0`
- `0x18003dd70`
- `0x18003e350`
- `0x180040270`
- `0x18004d5f0`
- `0x18004e820`
- `0x180053680`
- `0x180058558`
- `0x18005c670`
- `0x18005d0c0`
- `0x1800677e0`
- `0x1800683d0`
- `0x180068960`
- `0x1800689e0`
- `0x180068e40`
- `0x180069c30`
- `0x18006cff0`
- `0x18006d4d0`
- `0x18006d5d0`
- `0x18006d7e0`
- `0x18006d890`
- `0x18006e1a0`
- `0x18006e3e0`
- `0x18006f980`

## callees

- `0x1800273f0`
- `0x180027550`
- `0x180080fb0`
- `0x1800b5f04`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180027478`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180027478`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002748a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002748a`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x180027484`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x180027484`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180027422`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180027422`

## pseudocode

```c
int __fastcall SetThreadName(WCHAR *lpWideCharStr)
{
  const wchar_t *v2; // rax
  int v3; // eax
  unsigned __int16 *v4; // rdx
  HANDLE CurrentThread; // rax
  int result; // eax
  APTTYPEQUALIFIER pAptQualifier; // [rsp+30h] [rbp-128h] BYREF
  APTTYPE pAptType[3]; // [rsp+34h] [rbp-124h] BYREF
  unsigned __int16 v9[128]; // [rsp+40h] [rbp-118h] BYREF

  pAptType[0] = APTTYPE_STA;
  pAptQualifier = APTTYPEQUALIFIER_NONE;
  if ( CoGetApartmentType(pAptType, &pAptQualifier) )
    goto LABEL_8;
  if ( pAptType[0] == APTTYPE_MTA )
  {
    v2 = L"MTA";
    if ( pAptQualifier == APTTYPEQUALIFIER_IMPLICIT_MTA )
      v2 = (const wchar_t *)L"MTA Implicit";
    goto LABEL_5;
  }
  if ( pAptType[0] == APTTYPE_STA )
  {
LABEL_13:
    v2 = L"ASTA";
    if ( pAptQualifier != APTTYPEQUALIFIER_APPLICATION_STA )
      v2 = L"STA";
    goto LABEL_5;
  }
  if ( pAptType[0] != APTTYPE_NA )
  {
    if ( pAptType[0] != APTTYPE_MAINSTA )
      goto LABEL_8;
    goto LABEL_13;
  }
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
LABEL_5:
  v3 = StringCchPrintfW(v9, 0x80u, L"%s %s", lpWideCharStr, v2);
  v4 = v9;
  if ( v3 < 0 )
    v4 = lpWideCharStr;
  lpWideCharStr = v4;
LABEL_8:
  CurrentThread = GetCurrentThread();
  SetThreadDescription(CurrentThread, lpWideCharStr);
  result = IsDebuggerPresent();
  if ( result )
    return SetThreadNameViaException(lpWideCharStr);
  return result;
}

```

## disassembly

```asm
0x1800273f0  push    rbx
0x1800273f2  sub     rsp, 150h
0x1800273f9  mov     rax, cs:__security_cookie
0x180027400  xor     rax, rsp
0x180027403  mov     [rsp+158h+var_18], rax
0x18002740b  xor     eax, eax
0x18002740d  lea     rdx, [rsp+158h+pAptQualifier]; pAptQualifier
0x180027412  mov     rbx, rcx
0x180027415  mov     [rsp+158h+pAptType], eax
0x180027419  lea     rcx, [rsp+158h+pAptType]; pAptType
0x18002741e  mov     [rsp+158h+pAptQualifier], eax
0x180027422  call    cs:__imp_CoGetApartmentType
0x180027428  test    eax, eax
0x18002742a  jnz     short loc_180027478
0x18002742c  mov     ecx, [rsp+158h+pAptType]
0x180027430  cmp     ecx, 1
0x180027433  jnz     short loc_1800274B1
0x180027435  cmp     [rsp+158h+pAptQualifier], 1
0x18002743a  lea     rcx, aMtaImplicit; "MTA Implicit"
0x180027441  lea     rax, aMta; "MTA"
0x180027448  cmovz   rax, rcx
0x18002744c  mov     r9, rbx
0x18002744f  mov     [rsp+158h+var_138], rax
0x180027454  lea     r8, aSS_1; "%s %s"
0x18002745b  mov     edx, 80h; unsigned __int64
0x180027460  lea     rcx, [rsp+158h+var_118]; unsigned __int16 *
0x180027465  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002746a  test    eax, eax
0x18002746c  lea     rdx, [rsp+158h+var_118]
0x180027471  cmovs   rdx, rbx
0x180027475  mov     rbx, rdx
0x180027478  call    cs:__imp_GetCurrentThread
0x18002747e  mov     rcx, rax; hThread
0x180027481  mov     rdx, rbx; lpThreadDescription
0x180027484  call    cs:__imp_SetThreadDescription
0x18002748a  call    cs:__imp_IsDebuggerPresent
0x180027490  test    eax, eax
0x180027492  jnz     loc_18002752F
0x180027498  mov     rcx, [rsp+158h+var_18]
0x1800274a0  xor     rcx, rsp; StackCookie
0x1800274a3  call    __security_check_cookie
0x1800274a8  add     rsp, 150h
0x1800274af  pop     rbx
0x1800274b0  retn
0x1800274b1  test    ecx, ecx
0x1800274b3  jz      short loc_1800274BF
0x1800274b5  sub     ecx, 2
0x1800274b8  jz      short loc_1800274DB
0x1800274ba  cmp     ecx, 1
0x1800274bd  jnz     short loc_180027478
0x1800274bf  cmp     [rsp+158h+pAptQualifier], 6
0x1800274c4  lea     rax, aAsta; "ASTA"
0x1800274cb  lea     rcx, aSta; "STA"
0x1800274d2  cmovnz  rax, rcx
0x1800274d6  jmp     loc_18002744C
0x1800274db  mov     ecx, [rsp+158h+pAptQualifier]
0x1800274df  sub     ecx, 2
0x1800274e2  jz      short loc_180027523
0x1800274e4  sub     ecx, 1
0x1800274e7  jz      short loc_180027517
0x1800274e9  sub     ecx, 1
0x1800274ec  jz      short loc_18002750B
0x1800274ee  cmp     ecx, 1
0x1800274f1  jz      short loc_1800274FF
0x1800274f3  lea     rax, aNa; "NA"
0x1800274fa  jmp     loc_18002744C
0x1800274ff  lea     rax, aNaOnMainsta; "NA on MAINSTA"
0x180027506  jmp     loc_18002744C
0x18002750b  lea     rax, aNaOnMtaImplici; "NA on MTA Implicit"
0x180027512  jmp     loc_18002744C
0x180027517  lea     rax, aNaOnSta; "NA on STA"
0x18002751e  jmp     loc_18002744C
0x180027523  lea     rax, aNaOnMta; "NA on MTA"
0x18002752a  jmp     loc_18002744C
0x18002752f  mov     rcx, rbx; lpWideCharStr
0x180027532  call    SetThreadNameViaException
0x180027537  jmp     loc_180027498
```
