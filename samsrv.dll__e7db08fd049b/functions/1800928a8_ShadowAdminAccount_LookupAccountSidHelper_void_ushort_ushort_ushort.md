# ShadowAdminAccount::LookupAccountSidHelper(void *,ushort * *,ushort * *,ushort * *)

- ea: `0x1800928a8`
- end: `0x180092b01`
- name: `?LookupAccountSidHelper@ShadowAdminAccount@@CAJPEAXPEAPEAG11@Z`
- size: `601`
- prototype: `__int64 __fastcall(PSID Sid, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180093818`

## callees

- `0x180027e24`
- `0x1800372ac`
- `0x180059afc`
- `0x180091268`
- `0x1800928a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009292d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092a4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009292d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092a4b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800929f1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180092a03`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800929f1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180092a03`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180092984`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009298d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180092996`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180092984`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009298d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180092996`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18009291c`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180092a41`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18009291c`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180092a41`

## pseudocode

```c
__int64 __fastcall ShadowAdminAccount::LookupAccountSidHelper(
        PSID Sid,
        unsigned __int16 **a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4)
{
  unsigned __int16 *v4; // r14
  unsigned __int16 *v9; // rdi
  WCHAR *v10; // r13
  DWORD LastError; // eax
  unsigned int v12; // ebx
  PUNICODE_STRING v13; // rcx
  __int64 v14; // rdx
  WCHAR *ReferencedDomainName; // rax
  int v17; // eax
  unsigned __int16 *v18; // [rsp+40h] [rbp-10h] BYREF
  DWORD cchReferencedDomainName; // [rsp+98h] [rbp+48h] BYREF
  DWORD cchName; // [rsp+A0h] [rbp+50h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+A8h] [rbp+58h] BYREF

  v4 = 0;
  cchName = 0;
  cchReferencedDomainName = 0;
  v18 = 0;
  peUse = 0;
  v9 = 0;
  if ( a2 )
    *a2 = 0;
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  if ( !LookupAccountSidW(0, Sid, 0, &cchName, 0, &cchReferencedDomainName, &peUse) )
  {
    v10 = 0;
    LastError = GetLastError();
    if ( LastError == 1332 )
    {
LABEL_9:
      v12 = -1073741709;
      goto LABEL_16;
    }
    if ( LastError != 122 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x400) == 0
        || HIBYTE(WPP_GLOBAL_Control[4].Length) < 2u )
      {
        goto LABEL_15;
      }
      v14 = 55;
LABEL_14:
      WPP_SF__sid_D(v13[3].Buffer, v14, WPP_99473abb2ee73b6c7cc9b39fb0106789_Traceguids, Sid, LastError);
LABEL_15:
      v12 = -1073741801;
      goto LABEL_16;
    }
  }
  v10 = (WCHAR *)LocalAlloc(0x40u, 2LL * cchName);
  ReferencedDomainName = (WCHAR *)LocalAlloc(0x40u, 2LL * cchReferencedDomainName);
  v4 = ReferencedDomainName;
  if ( !v10 || !ReferencedDomainName )
    goto LABEL_15;
  if ( !LookupAccountSidW(0, Sid, v10, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
  {
    LastError = GetLastError();
    if ( LastError == 1332 )
      goto LABEL_9;
    v13 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x400) == 0
      || HIBYTE(WPP_GLOBAL_Control[4].Length) < 2u )
    {
      goto LABEL_15;
    }
    v14 = 56;
    goto LABEL_14;
  }
  if ( a4 )
  {
    v17 = ShadowAdminAccount::BuildDomainAccountName(v4, v10, &v18);
    v12 = v17;
    if ( v17 < 0 )
    {
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x400) != 0
        && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 57, WPP_99473abb2ee73b6c7cc9b39fb0106789_Traceguids, (unsigned int)v17);
      }
      v9 = v18;
      goto LABEL_16;
    }
    v9 = v18;
  }
  if ( a2 )
  {
    *a2 = v4;
    v4 = 0;
  }
  if ( a3 )
  {
    *a3 = v10;
    v10 = 0;
  }
  if ( a4 )
  {
    *a4 = v9;
    v9 = 0;
  }
  v12 = 0;
LABEL_16:
  LocalFree(v9);
  LocalFree(v4);
  LocalFree(v10);
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 58, WPP_99473abb2ee73b6c7cc9b39fb0106789_Traceguids, v12, v12);
  return v12;
}

```

## disassembly

```asm
0x1800928a8  mov     [rsp-38h+arg_0], rbx
0x1800928ad  push    rbp
0x1800928ae  push    rsi
0x1800928af  push    rdi
0x1800928b0  push    r12
0x1800928b2  push    r13
0x1800928b4  push    r14
0x1800928b6  push    r15
0x1800928b8  mov     rbp, rsp
0x1800928bb  sub     rsp, 50h
0x1800928bf  xor     r14d, r14d
0x1800928c2  mov     rsi, r9
0x1800928c5  mov     [rbp+cchName], r14d
0x1800928c9  mov     r15, r8
0x1800928cc  mov     [rbp+arg_8], r14d
0x1800928d0  mov     r12, rdx
0x1800928d3  mov     [rbp+var_10], r14
0x1800928d7  mov     rbx, rcx
0x1800928da  mov     [rbp+arg_18], r14d
0x1800928de  mov     edi, r14d
0x1800928e1  test    rdx, rdx
0x1800928e4  jz      short loc_1800928E9
0x1800928e6  mov     [rdx], r14
0x1800928e9  test    r15, r15
0x1800928ec  jz      short loc_1800928F1
0x1800928ee  mov     [r8], r14
0x1800928f1  test    rsi, rsi
0x1800928f4  jz      short loc_1800928F9
0x1800928f6  mov     [r9], r14
0x1800928f9  lea     rax, [rbp+arg_18]
0x1800928fd  xor     r8d, r8d; Name
0x180092900  mov     [rsp+50h+peUse], rax; peUse
0x180092905  lea     r9, [rbp+cchName]; cchName
0x180092909  lea     rax, [rbp+arg_8]
0x18009290d  mov     rdx, rbx; Sid
0x180092910  mov     [rsp+50h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180092915  xor     ecx, ecx; lpSystemName
0x180092917  mov     [rsp+50h+ReferencedDomainName], r14; ReferencedDomainName
0x18009291c  call    cs:__imp_LookupAccountSidW
0x180092922  test    eax, eax
0x180092924  jnz     loc_1800929E2
0x18009292a  mov     r13, r14
0x18009292d  call    cs:__imp_GetLastError
0x180092933  cmp     eax, 534h
0x180092938  jnz     short loc_180092941
0x18009293a  mov     ebx, 0C0000073h
0x18009293f  jmp     short loc_180092981
0x180092941  cmp     eax, 7Ah ; 'z'
0x180092944  jz      loc_1800929E2
0x18009294a  mov     rcx, cs:WPP_GLOBAL_Control
0x180092951  test    dword ptr [rcx+44h], 400h
0x180092958  jz      short loc_18009297C
0x18009295a  cmp     byte ptr [rcx+41h], 2
0x18009295e  jb      short loc_18009297C
0x180092960  mov     edx, 37h ; '7'
0x180092965  mov     rcx, [rcx+38h]
0x180092969  lea     r8, WPP_99473abb2ee73b6c7cc9b39fb0106789_Traceguids
0x180092970  mov     r9, rbx
0x180092973  mov     dword ptr [rsp+50h+ReferencedDomainName], eax
0x180092977  call    WPP_SF__sid_D
0x18009297c  mov     ebx, 0C0000017h
0x180092981  mov     rcx, rdi; hMem
0x180092984  call    cs:__imp_LocalFree
0x18009298a  mov     rcx, r14; hMem
0x18009298d  call    cs:__imp_LocalFree
0x180092993  mov     rcx, r13; hMem
0x180092996  call    cs:__imp_LocalFree
0x18009299c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800929a3  test    dword ptr [rcx+44h], 20000h
0x1800929aa  jz      short loc_1800929C8
0x1800929ac  mov     rcx, [rcx+38h]
0x1800929b0  lea     r8, WPP_99473abb2ee73b6c7cc9b39fb0106789_Traceguids
0x1800929b7  mov     edx, 3Ah ; ':'
0x1800929bc  mov     dword ptr [rsp+50h+ReferencedDomainName], ebx
0x1800929c0  mov     r9d, ebx
0x1800929c3  call    WPP_SF_Dd
0x1800929c8  mov     eax, ebx
0x1800929ca  mov     rbx, [rsp+50h+arg_0]
0x1800929d2  add     rsp, 50h
0x1800929d6  pop     r15
0x1800929d8  pop     r14
0x1800929da  pop     r13
0x1800929dc  pop     r12
0x1800929de  pop     rdi
0x1800929df  pop     rsi
0x1800929e0  pop     rbp
0x1800929e1  retn
0x1800929e2  mov     edx, [rbp+cchName]
0x1800929e5  mov     r14d, 40h ; '@'
0x1800929eb  add     rdx, rdx; uBytes
0x1800929ee  mov     ecx, r14d; uFlags
0x1800929f1  call    cs:__imp_LocalAlloc
0x1800929f7  mov     edx, [rbp+arg_8]
0x1800929fa  mov     ecx, r14d; uFlags
0x1800929fd  add     rdx, rdx; uBytes
0x180092a00  mov     r13, rax
0x180092a03  call    cs:__imp_LocalAlloc
0x180092a09  mov     r14, rax
0x180092a0c  test    r13, r13
0x180092a0f  jz      loc_18009297C
0x180092a15  test    rax, rax
0x180092a18  jz      loc_18009297C
0x180092a1e  lea     rax, [rbp+arg_18]
0x180092a22  mov     r8, r13; Name
0x180092a25  mov     [rsp+50h+peUse], rax; peUse
0x180092a2a  lea     r9, [rbp+cchName]; cchName
0x180092a2e  lea     rax, [rbp+arg_8]
0x180092a32  mov     rdx, rbx; Sid
0x180092a35  mov     [rsp+50h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180092a3a  xor     ecx, ecx; lpSystemName
0x180092a3c  mov     [rsp+50h+ReferencedDomainName], r14; ReferencedDomainName
0x180092a41  call    cs:__imp_LookupAccountSidW
0x180092a47  test    eax, eax
0x180092a49  jnz     short loc_180092A84
0x180092a4b  call    cs:__imp_GetLastError
0x180092a51  cmp     eax, 534h
0x180092a56  jz      loc_18009293A
0x180092a5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180092a63  test    dword ptr [rcx+44h], 400h
0x180092a6a  jz      loc_18009297C
0x180092a70  cmp     byte ptr [rcx+41h], 2
0x180092a74  jb      loc_18009297C
0x180092a7a  mov     edx, 38h ; '8'
0x180092a7f  jmp     loc_180092965
0x180092a84  test    rsi, rsi
0x180092a87  jz      short loc_180092AD9
0x180092a89  lea     r8, [rbp+var_10]; unsigned __int16 **
0x180092a8d  mov     rdx, r13; unsigned __int16 *
0x180092a90  mov     rcx, r14; unsigned __int16 *
0x180092a93  call    ?BuildDomainAccountName@ShadowAdminAccount@@CAJPEAG0PEAPEAG@Z; ShadowAdminAccount::BuildDomainAccountName(ushort *,ushort *,ushort * *)
0x180092a98  mov     ebx, eax
0x180092a9a  test    eax, eax
0x180092a9c  jns     short loc_180092AD5
0x180092a9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180092aa5  test    dword ptr [rcx+44h], 400h
0x180092aac  jz      short loc_180092ACC
0x180092aae  cmp     byte ptr [rcx+41h], 2
0x180092ab2  jb      short loc_180092ACC
0x180092ab4  mov     rcx, [rcx+38h]
0x180092ab8  lea     r8, WPP_99473abb2ee73b6c7cc9b39fb0106789_Traceguids
0x180092abf  mov     edx, 39h ; '9'
0x180092ac4  mov     r9d, eax
0x180092ac7  call    WPP_SF_d
0x180092acc  mov     rdi, [rbp+var_10]
0x180092ad0  jmp     loc_180092981
0x180092ad5  mov     rdi, [rbp+var_10]
0x180092ad9  test    r12, r12
0x180092adc  jz      short loc_180092AE5
0x180092ade  mov     [r12], r14
0x180092ae2  xor     r14d, r14d
0x180092ae5  test    r15, r15
0x180092ae8  jz      short loc_180092AF0
0x180092aea  mov     [r15], r13
0x180092aed  xor     r13d, r13d
0x180092af0  test    rsi, rsi
0x180092af3  jz      short loc_180092AFA
0x180092af5  mov     [rsi], rdi
0x180092af8  xor     edi, edi
0x180092afa  xor     ebx, ebx
0x180092afc  jmp     loc_180092981
```
