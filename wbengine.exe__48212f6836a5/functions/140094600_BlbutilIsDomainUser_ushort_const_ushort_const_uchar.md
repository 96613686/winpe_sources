# BlbutilIsDomainUser(ushort const *,ushort const *,uchar *)

- ea: `0x140094600`
- end: `0x140094a10`
- name: `?BlbutilIsDomainUser@@YAJPEBG0PEAE@Z`
- size: `1040`
- prototype: `__int64 __fastcall(LPCWSTR lpAccountName, LPCWSTR lpSystemName, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, service_task`

## callers

- `0x14008e584`
- `0x1400940f0`
- `0x1400efa40`

## callees

- `0x140007ad3`
- `0x14000bb24`
- `0x14000bb4c`
- `0x140014260`
- `0x140094600`
- `0x140134d20`

## import_xrefs

- `ADVAPI32!IsValidSid` at `0x140094780`
- `ADVAPI32!IsValidSid` at `0x140094780`
- `ADVAPI32!LookupAccountNameW` at `0x1400947b5`
- `ADVAPI32!LookupAccountNameW` at `0x1400948a4`
- `ADVAPI32!LookupAccountNameW` at `0x1400947b5`
- `ADVAPI32!LookupAccountNameW` at `0x1400948a4`
- `ADVAPI32!LsaFreeMemory` at `0x1400949bf`
- `ADVAPI32!LsaFreeMemory` at `0x1400949bf`
- `ADVAPI32!EqualSid` at `0x14009496c`
- `ADVAPI32!EqualSid` at `0x14009496c`
- `ADVAPI32!GetWindowsAccountDomainSid` at `0x140094904`
- `ADVAPI32!GetWindowsAccountDomainSid` at `0x140094904`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x14009473c`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x14009473c`
- `ADVAPI32!LsaOpenPolicy` at `0x1400946ca`
- `ADVAPI32!LsaOpenPolicy` at `0x1400946ca`
- `ADVAPI32!LsaClose` at `0x1400949cf`
- `ADVAPI32!LsaClose` at `0x1400949cf`
- `KERNEL32!GetLastError` at `0x1400947bf`
- `KERNEL32!GetLastError` at `0x1400947ca`
- `KERNEL32!GetLastError` at `0x1400948ae`
- `KERNEL32!GetLastError` at `0x14009490e`
- `KERNEL32!GetLastError` at `0x1400947bf`
- `KERNEL32!GetLastError` at `0x1400947ca`
- `KERNEL32!GetLastError` at `0x1400948ae`
- `KERNEL32!GetLastError` at `0x14009490e`
- `ntdll!RtlNtStatusToDosError` at `0x14009470f`
- `ntdll!RtlNtStatusToDosError` at `0x14009470f`
- `ole32!CoTaskMemAlloc` at `0x14009482f`
- `ole32!CoTaskMemAlloc` at `0x14009485d`
- `ole32!CoTaskMemAlloc` at `0x14009482f`
- `ole32!CoTaskMemAlloc` at `0x14009485d`
- `ole32!CoTaskMemFree` at `0x1400949d8`
- `ole32!CoTaskMemFree` at `0x1400949e1`
- `ole32!CoTaskMemFree` at `0x1400949d8`
- `ole32!CoTaskMemFree` at `0x1400949e1`

## pseudocode

```c
__int64 __fastcall BlbutilIsDomainUser(LPCWSTR lpAccountName, LPCWSTR lpSystemName, bool *a3)
{
  void *v6; // rsi
  WCHAR *ReferencedDomainName; // r12
  struct _LSA_UNICODE_STRING *v8; // rbx
  __int64 v9; // rax
  int v10; // ebx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  signed int v13; // eax
  unsigned int v14; // ebx
  void *v15; // rcx
  signed int v16; // eax
  _QWORD *v17; // rcx
  int v18; // edx
  void *v19; // rax
  WCHAR *v20; // rax
  signed int v21; // eax
  signed int LastError; // eax
  DWORD cchReferencedDomainName; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbSid; // [rsp+44h] [rbp-BCh] BYREF
  enum _SID_NAME_USE peUse; // [rsp+48h] [rbp-B8h] BYREF
  PVOID Buffer; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbDomainSid; // [rsp+58h] [rbp-A8h] BYREF
  PVOID PolicyHandle; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v30; // [rsp+68h] [rbp-98h] BYREF
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-88h] BYREF
  _BYTE pDomainSid[80]; // [rsp+B0h] [rbp-50h] BYREF

  peUse = SidTypeUnknown;
  *a3 = 0;
  PolicyHandle = 0;
  Buffer = 0;
  cbSid = 0;
  cchReferencedDomainName = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v6 = 0;
  ReferencedDomainName = 0;
  v8 = 0;
  memset_0(pDomainSid, 0, 0x48u);
  cbDomainSid = 68;
  v30 = 0;
  if ( lpSystemName )
  {
    v9 = -1;
    do
      ++v9;
    while ( lpSystemName[v9] );
    *((_QWORD *)&v30 + 1) = lpSystemName;
    LOWORD(v30) = 2 * v9;
    v8 = (struct _LSA_UNICODE_STRING *)&v30;
    WORD1(v30) = 2 * v9;
  }
  v10 = LsaOpenPolicy(v8, &ObjectAttributes, 1u, &PolicyHandle);
  if ( v10 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = 18;
LABEL_10:
      WPP_SF_d(v11[2], v12, WPP_a9db3353c5e53f9a1655ee2f19169839_Traceguids);
      goto LABEL_11;
    }
    goto LABEL_11;
  }
  v10 = LsaQueryInformationPolicy(PolicyHandle, PolicyAccountDomainInformation, &Buffer);
  if ( v10 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = 19;
      goto LABEL_10;
    }
LABEL_11:
    v13 = RtlNtStatusToDosError(v10);
    v14 = v13;
    if ( v13 > 0 )
      v14 = (unsigned __int16)v13 | 0x80070000;
    goto LABEL_52;
  }
  v15 = (void *)*((_QWORD *)Buffer + 2);
  if ( v15 && IsValidSid(v15) )
  {
    if ( LookupAccountNameW(lpSystemName, lpAccountName, 0, &cbSid, 0, &cchReferencedDomainName, &peUse)
      || GetLastError() == 122 )
    {
      v19 = CoTaskMemAlloc(cbSid);
      v6 = v19;
      if ( !v19
        || (memset_0(v19, 0, cbSid),
            v20 = (WCHAR *)CoTaskMemAlloc(2LL * cchReferencedDomainName),
            (ReferencedDomainName = v20) == 0) )
      {
        v14 = -2147024882;
        goto LABEL_52;
      }
      memset_0(v20, 0, 2LL * cchReferencedDomainName);
      if ( LookupAccountNameW(
             lpSystemName,
             lpAccountName,
             v6,
             &cbSid,
             ReferencedDomainName,
             &cchReferencedDomainName,
             &peUse) )
      {
        if ( GetWindowsAccountDomainSid(v6, pDomainSid, &cbDomainSid) )
        {
          v14 = 0;
          *a3 = !EqualSid(*((PSID *)Buffer + 2), pDomainSid);
        }
        else
        {
          LastError = GetLastError();
          v14 = LastError;
          if ( LastError > 0 )
            v14 = (unsigned __int16)LastError | 0x80070000;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_a9db3353c5e53f9a1655ee2f19169839_Traceguids);
          }
        }
      }
      else
      {
        v21 = GetLastError();
        v14 = v21;
        if ( v21 > 0 )
          v14 = (unsigned __int16)v21 | 0x80070000;
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v18 = 22;
          goto LABEL_28;
        }
      }
    }
    else
    {
      v16 = GetLastError();
      v14 = v16;
      if ( v16 > 0 )
        v14 = (unsigned __int16)v16 | 0x80070000;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v18 = 21;
LABEL_28:
        WPP_SF_Sd(
          v17[2],
          v18,
          (unsigned int)WPP_a9db3353c5e53f9a1655ee2f19169839_Traceguids,
          (_DWORD)lpAccountName,
          v14);
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_a9db3353c5e53f9a1655ee2f19169839_Traceguids);
    }
    v14 = -2147418113;
  }
LABEL_52:
  if ( Buffer )
    LsaFreeMemory(Buffer);
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  CoTaskMemFree(ReferencedDomainName);
  CoTaskMemFree(v6);
  return v14;
}

```

## disassembly

```asm
0x140094600  mov     [rsp-8+arg_18], rbx
0x140094605  push    rbp
0x140094606  push    rsi
0x140094607  push    rdi
0x140094608  push    r12
0x14009460a  push    r13
0x14009460c  push    r14
0x14009460e  push    r15
0x140094610  lea     rbp, [rsp-10h]
0x140094615  sub     rsp, 110h
0x14009461c  mov     rax, cs:__security_cookie
0x140094623  xor     rax, rsp
0x140094626  mov     [rbp+40h+var_40], rax
0x14009462a  xor     r13d, r13d
0x14009462d  mov     [rsp+140h+var_F8], 8
0x140094635  xorps   xmm0, xmm0
0x140094638  mov     [r8], r13b
0x14009463b  mov     r15, r8
0x14009463e  mov     [rsp+140h+PolicyHandle], r13
0x140094643  mov     rdi, rdx
0x140094646  mov     [rsp+140h+Buffer], r13
0x14009464b  mov     r14, rcx
0x14009464e  mov     [rsp+140h+cbSid], r13d
0x140094653  lea     r8d, [r13+48h]; Size
0x140094657  mov     [rsp+140h+var_100], r13d
0x14009465c  xor     edx, edx; Val
0x14009465e  lea     rcx, [rbp+40h+pDomainSid]; void *
0x140094662  movups  xmmword ptr [rsp+140h+ObjectAttributes.Length], xmm0
0x140094667  mov     esi, r13d
0x14009466a  mov     r12d, r13d
0x14009466d  movups  xmmword ptr [rbp+40h+ObjectAttributes.ObjectName], xmm0
0x140094671  mov     ebx, r13d
0x140094674  movups  xmmword ptr [rbp+40h+ObjectAttributes.SecurityDescriptor], xmm0
0x140094678  call    memset_0
0x14009467d  mov     [rsp+140h+cbDomainSid], 44h ; 'D'
0x140094685  xorps   xmm0, xmm0
0x140094688  movups  [rsp+140h+var_D8], xmm0
0x14009468d  test    rdi, rdi
0x140094690  jz      short loc_1400946B7
0x140094692  or      rax, 0FFFFFFFFFFFFFFFFh
0x140094696  inc     rax
0x140094699  cmp     [rdi+rax*2], r13w
0x14009469e  jnz     short loc_140094696
0x1400946a0  add     ax, ax
0x1400946a3  mov     qword ptr [rsp+140h+var_D8+8], rdi
0x1400946a8  mov     word ptr [rsp+140h+var_D8], ax
0x1400946ad  lea     rbx, [rsp+140h+var_D8]
0x1400946b2  mov     word ptr [rsp+140h+var_D8+2], ax
0x1400946b7  lea     r9, [rsp+140h+PolicyHandle]; PolicyHandle
0x1400946bc  mov     r8d, 1; DesiredAccess
0x1400946c2  lea     rdx, [rsp+140h+ObjectAttributes]; ObjectAttributes
0x1400946c7  mov     rcx, rbx; SystemName
0x1400946ca  call    cs:__imp_LsaOpenPolicy
0x1400946d0  mov     ebx, eax
0x1400946d2  test    eax, eax
0x1400946d4  jns     short loc_14009472D
0x1400946d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400946dd  lea     rax, WPP_GLOBAL_Control
0x1400946e4  cmp     rcx, rax
0x1400946e7  jz      short loc_14009470D
0x1400946e9  test    byte ptr [rcx+1Ch], 1
0x1400946ed  jz      short loc_14009470D
0x1400946ef  cmp     byte ptr [rcx+19h], 2
0x1400946f3  jb      short loc_14009470D
0x1400946f5  mov     edx, 12h
0x1400946fa  mov     rcx, [rcx+10h]
0x1400946fe  lea     r8, WPP_a9db3353c5e53f9a1655ee2f19169839_Traceguids
0x140094705  mov     r9d, ebx
0x140094708  call    WPP_SF_d
0x14009470d  mov     ecx, ebx; Status
0x14009470f  call    cs:__imp_RtlNtStatusToDosError
0x140094715  mov     ebx, eax
0x140094717  test    eax, eax
0x140094719  jle     loc_1400949B5
0x14009471f  movzx   ebx, ax
0x140094722  or      ebx, 80070000h
0x140094728  jmp     loc_1400949B5
0x14009472d  mov     rcx, [rsp+140h+PolicyHandle]; PolicyHandle
0x140094732  lea     r8, [rsp+140h+Buffer]; Buffer
0x140094737  mov     edx, 5; InformationClass
0x14009473c  call    cs:__imp_LsaQueryInformationPolicy
0x140094742  mov     ebx, eax
0x140094744  test    eax, eax
0x140094746  jns     short loc_14009476E
0x140094748  mov     rcx, cs:WPP_GLOBAL_Control
0x14009474f  lea     rax, WPP_GLOBAL_Control
0x140094756  cmp     rcx, rax
0x140094759  jz      short loc_14009470D
0x14009475b  test    byte ptr [rcx+1Ch], 1
0x14009475f  jz      short loc_14009470D
0x140094761  cmp     byte ptr [rcx+19h], 2
0x140094765  jb      short loc_14009470D
0x140094767  mov     edx, 13h
0x14009476c  jmp     short loc_1400946FA
0x14009476e  mov     rax, [rsp+140h+Buffer]
0x140094773  mov     rcx, [rax+10h]; pSid
0x140094777  test    rcx, rcx
0x14009477a  jz      loc_14009497C
0x140094780  call    cs:__imp_IsValidSid
0x140094786  test    eax, eax
0x140094788  jz      loc_14009497C
0x14009478e  lea     rax, [rsp+140h+var_F8]
0x140094793  xor     r8d, r8d; Sid
0x140094796  mov     [rsp+140h+peUse], rax; peUse
0x14009479b  lea     r9, [rsp+140h+cbSid]; cbSid
0x1400947a0  lea     rax, [rsp+140h+var_100]
0x1400947a5  mov     rdx, r14; lpAccountName
0x1400947a8  mov     [rsp+140h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1400947ad  mov     rcx, rdi; lpSystemName
0x1400947b0  mov     [rsp+140h+ReferencedDomainName], r13; ReferencedDomainName
0x1400947b5  call    cs:__imp_LookupAccountNameW
0x1400947bb  test    eax, eax
0x1400947bd  jnz     short loc_14009482B
0x1400947bf  call    cs:__imp_GetLastError
0x1400947c5  cmp     eax, 7Ah ; 'z'
0x1400947c8  jz      short loc_14009482B
0x1400947ca  call    cs:__imp_GetLastError
0x1400947d0  mov     ebx, eax
0x1400947d2  test    eax, eax
0x1400947d4  jle     short loc_1400947DF
0x1400947d6  movzx   ebx, ax
0x1400947d9  or      ebx, 80070000h
0x1400947df  mov     rcx, cs:WPP_GLOBAL_Control
0x1400947e6  lea     rax, WPP_GLOBAL_Control
0x1400947ed  cmp     rcx, rax
0x1400947f0  jz      loc_1400949B5
0x1400947f6  test    byte ptr [rcx+1Ch], 1
0x1400947fa  jz      loc_1400949B5
0x140094800  cmp     byte ptr [rcx+19h], 2
0x140094804  jb      loc_1400949B5
0x14009480a  mov     edx, 15h
0x14009480f  mov     rcx, [rcx+10h]
0x140094813  lea     r8, WPP_a9db3353c5e53f9a1655ee2f19169839_Traceguids
0x14009481a  mov     r9, r14
0x14009481d  mov     dword ptr [rsp+140h+ReferencedDomainName], ebx
0x140094821  call    WPP_SF_Sd
0x140094826  jmp     loc_1400949B5
0x14009482b  mov     ecx, [rsp+140h+cbSid]; cb
0x14009482f  call    cs:__imp_CoTaskMemAlloc
0x140094835  mov     rsi, rax
0x140094838  test    rax, rax
0x14009483b  jnz     short loc_140094847
0x14009483d  mov     ebx, 8007000Eh
0x140094842  jmp     loc_1400949B5
0x140094847  mov     r8d, [rsp+140h+cbSid]; Size
0x14009484c  xor     edx, edx; Val
0x14009484e  mov     rcx, rsi; void *
0x140094851  call    memset_0
0x140094856  mov     ecx, [rsp+140h+var_100]
0x14009485a  add     rcx, rcx; cb
0x14009485d  call    cs:__imp_CoTaskMemAlloc
0x140094863  mov     r12, rax
0x140094866  test    rax, rax
0x140094869  jz      short loc_14009483D
0x14009486b  mov     r8d, [rsp+140h+var_100]
0x140094870  xor     edx, edx; Val
0x140094872  add     r8, r8; Size
0x140094875  mov     rcx, rax; void *
0x140094878  call    memset_0
0x14009487d  lea     rax, [rsp+140h+var_F8]
0x140094882  mov     r8, rsi; Sid
0x140094885  mov     [rsp+140h+peUse], rax; peUse
0x14009488a  lea     r9, [rsp+140h+cbSid]; cbSid
0x14009488f  lea     rax, [rsp+140h+var_100]
0x140094894  mov     rdx, r14; lpAccountName
0x140094897  mov     [rsp+140h+cchReferencedDomainName], rax; cchReferencedDomainName
0x14009489c  mov     rcx, rdi; lpSystemName
0x14009489f  mov     [rsp+140h+ReferencedDomainName], r12; ReferencedDomainName
0x1400948a4  call    cs:__imp_LookupAccountNameW
0x1400948aa  test    eax, eax
0x1400948ac  jnz     short loc_1400948F8
0x1400948ae  call    cs:__imp_GetLastError
0x1400948b4  mov     ebx, eax
0x1400948b6  test    eax, eax
0x1400948b8  jle     short loc_1400948C3
0x1400948ba  movzx   ebx, ax
0x1400948bd  or      ebx, 80070000h
0x1400948c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400948ca  lea     rax, WPP_GLOBAL_Control
0x1400948d1  cmp     rcx, rax
0x1400948d4  jz      loc_1400949B5
0x1400948da  test    byte ptr [rcx+1Ch], 1
0x1400948de  jz      loc_1400949B5
0x1400948e4  cmp     byte ptr [rcx+19h], 2
0x1400948e8  jb      loc_1400949B5
0x1400948ee  mov     edx, 16h
0x1400948f3  jmp     loc_14009480F
0x1400948f8  lea     r8, [rsp+140h+cbDomainSid]; cbDomainSid
0x1400948fd  mov     rcx, rsi; pSid
0x140094900  lea     rdx, [rbp+40h+pDomainSid]; pDomainSid
0x140094904  call    cs:__imp_GetWindowsAccountDomainSid
0x14009490a  test    eax, eax
0x14009490c  jnz     short loc_14009495C
0x14009490e  call    cs:__imp_GetLastError
0x140094914  mov     ebx, eax
0x140094916  test    eax, eax
0x140094918  jle     short loc_140094923
0x14009491a  movzx   ebx, ax
0x14009491d  or      ebx, 80070000h
0x140094923  mov     rcx, cs:WPP_GLOBAL_Control
0x14009492a  lea     rax, WPP_GLOBAL_Control
0x140094931  cmp     rcx, rax
0x140094934  jz      short loc_1400949B5
0x140094936  test    byte ptr [rcx+1Ch], 1
0x14009493a  jz      short loc_1400949B5
0x14009493c  cmp     byte ptr [rcx+19h], 2
0x140094940  jb      short loc_1400949B5
0x140094942  mov     rcx, [rcx+10h]
0x140094946  lea     r8, WPP_a9db3353c5e53f9a1655ee2f19169839_Traceguids
0x14009494d  mov     edx, 17h
0x140094952  mov     r9d, ebx
0x140094955  call    WPP_SF_d
0x14009495a  jmp     short loc_1400949B5
0x14009495c  mov     rcx, [rsp+140h+Buffer]
0x140094961  lea     rdx, [rbp+40h+pDomainSid]; pSid2
0x140094965  mov     ebx, r13d
0x140094968  mov     rcx, [rcx+10h]; pSid1
0x14009496c  call    cs:__imp_EqualSid
0x140094972  test    eax, eax
0x140094974  setz    al
0x140094977  mov     [r15], al
0x14009497a  jmp     short loc_1400949B5
0x14009497c  mov     rcx, cs:WPP_GLOBAL_Control
0x140094983  lea     rax, WPP_GLOBAL_Control
0x14009498a  cmp     rcx, rax
0x14009498d  jz      short loc_1400949B0
0x14009498f  test    byte ptr [rcx+1Ch], 1
0x140094993  jz      short loc_1400949B0
0x140094995  cmp     byte ptr [rcx+19h], 2
0x140094999  jb      short loc_1400949B0
0x14009499b  mov     rcx, [rcx+10h]
0x14009499f  lea     r8, WPP_a9db3353c5e53f9a1655ee2f19169839_Traceguids
0x1400949a6  mov     edx, 14h
0x1400949ab  call    WPP_SF_
0x1400949b0  mov     ebx, 8000FFFFh
0x1400949b5  mov     rcx, [rsp+140h+Buffer]; Buffer
0x1400949ba  test    rcx, rcx
0x1400949bd  jz      short loc_1400949C5
0x1400949bf  call    cs:__imp_LsaFreeMemory
0x1400949c5  mov     rcx, [rsp+140h+PolicyHandle]; ObjectHandle
0x1400949ca  test    rcx, rcx
0x1400949cd  jz      short loc_1400949D5
0x1400949cf  call    cs:__imp_LsaClose
0x1400949d5  mov     rcx, r12; pv
0x1400949d8  call    cs:__imp_CoTaskMemFree
0x1400949de  mov     rcx, rsi; pv
0x1400949e1  call    cs:__imp_CoTaskMemFree
0x1400949e7  mov     eax, ebx
0x1400949e9  mov     rcx, [rbp+40h+var_40]
0x1400949ed  xor     rcx, rsp; StackCookie
0x1400949f0  call    __security_check_cookie
0x1400949f5  mov     rbx, [rsp+140h+arg_18]
0x1400949fd  add     rsp, 110h
0x140094a04  pop     r15
0x140094a06  pop     r14
0x140094a08  pop     r13
0x140094a0a  pop     r12
0x140094a0c  pop     rdi
0x140094a0d  pop     rsi
0x140094a0e  pop     rbp
0x140094a0f  retn
```
