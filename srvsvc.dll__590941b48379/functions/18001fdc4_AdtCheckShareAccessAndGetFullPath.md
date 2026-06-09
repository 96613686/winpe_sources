# AdtCheckShareAccessAndGetFullPath

- ea: `0x18001fdc4`
- end: `0x180020232`
- name: `AdtCheckShareAccessAndGetFullPath`
- size: `1134`
- prototype: `__int64 __fastcall(PCWSTR SourceString, PCWSTR, PCWSTR pszPathIn, PCWSTR *, ACCESS_MASK)`
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180020240`
- `0x180020350`

## callees

- `0x180008930`
- `0x18000a460`
- `0x18001deb0`
- `0x18001fdc4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002016a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002016a`
- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x18002014c`
- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x18002014c`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x1800200c6`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x1800200c6`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x18001ff83`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x18001ff83`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001ffb5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001ffb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff8d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800200a5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020125`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800200a5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020125`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800201e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800201f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020206`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800201e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800201f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020206`
- `ntdll!RtlCopySecurityDescriptor` at `0x18001fec4`
- `ntdll!RtlCopySecurityDescriptor` at `0x18001ff17`
- `ntdll!RtlCopySecurityDescriptor` at `0x18001fec4`
- `ntdll!RtlCopySecurityDescriptor` at `0x18001ff17`
- `ntdll!RtlIsDosDeviceName_U` at `0x180020192`
- `ntdll!RtlIsDosDeviceName_U` at `0x180020192`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x18001ff46`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x18001ff46`
- `ntdll!RtlDeleteSecurityObject` at `0x1800201c7`
- `ntdll!RtlDeleteSecurityObject` at `0x1800201d7`
- `ntdll!RtlDeleteSecurityObject` at `0x1800201c7`
- `ntdll!RtlDeleteSecurityObject` at `0x1800201d7`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18001ff2e`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18001ff2e`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x18001ff5e`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x18001ff5e`
- `ntdll!NtOpenThreadToken` at `0x18001ffad`
- `ntdll!NtOpenThreadToken` at `0x18001ffad`
- `ntdll!NtClose` at `0x18001ffe8`
- `ntdll!NtClose` at `0x18001ffe8`
- `ntdll!RtlSetSecurityObject` at `0x18001ffdc`
- `ntdll!RtlSetSecurityObject` at `0x18001ffdc`

## pseudocode

```c
__int64 __fastcall AdtCheckShareAccessAndGetFullPath(
        PCWSTR SourceString,
        PCWSTR a2,
        PCWSTR pszPathIn,
        PCWSTR *a4,
        ACCESS_MASK a5)
{
  WCHAR *v8; // r12
  unsigned int v9; // eax
  HLOCAL v10; // rdi
  unsigned int LastError; // ebx
  void *v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // r15
  __int64 v15; // r14
  unsigned __int64 v16; // rdx
  unsigned int i; // ecx
  __int64 v18; // rax
  SIZE_T v19; // rbx
  WCHAR *v20; // rax
  const WCHAR *j; // rbx
  __int64 v22; // rax
  SIZE_T v23; // rsi
  WCHAR *v24; // rax
  __int64 v25; // r9
  WCHAR v26; // ax
  int v28; // [rsp+70h] [rbp-90h] BYREF
  PSECURITY_DESCRIPTOR ObjectsSecurityDescriptor; // [rsp+78h] [rbp-88h] BYREF
  PSECURITY_DESCRIPTOR pDestinationSecurityDescriptor; // [rsp+80h] [rbp-80h] BYREF
  void *TokenHandle; // [rsp+88h] [rbp-78h] BYREF
  HLOCAL hMem; // [rsp+90h] [rbp-70h] BYREF
  PCWSTR v33; // [rsp+98h] [rbp-68h] BYREF
  struct _GENERIC_MAPPING *p_GenericMapping; // [rsp+A0h] [rbp-60h]
  PSECURITY_DESCRIPTOR v35; // [rsp+A8h] [rbp-58h]
  __int64 v36; // [rsp+B0h] [rbp-50h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v38; // [rsp+D8h] [rbp-28h]
  struct _GENERIC_MAPPING GenericMapping; // [rsp+E0h] [rbp-20h] BYREF

  v8 = 0;
  v38 = 0;
  *a4 = 0;
  hMem = 0;
  v28 = 0;
  ObjectsSecurityDescriptor = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  pDestinationSecurityDescriptor = 0;
  TokenHandle = 0;
  GenericMapping = 0;
  v9 = ShareEnumCommonEx(505, (int)&hMem, -1, (int)&v28, (__int64)&v36, 0, SourceString, a2, 0, 0, 0, 0, 0);
  v10 = hMem;
  LastError = v9;
  if ( !v9 )
  {
    if ( v28 && hMem )
    {
      if ( !*((_QWORD *)hMem + 5) )
      {
        LastError = 66;
        goto LABEL_55;
      }
      if ( *((_BYTE *)hMem + 8) )
      {
        LastError = 65;
        goto LABEL_55;
      }
      if ( *((_DWORD *)hMem + 6) )
      {
        LastError = RtlCopySecurityDescriptor(
                      (char *)hMem + *((unsigned int *)hMem + 6),
                      &pDestinationSecurityDescriptor);
        if ( !LastError )
        {
          v33 = SourceString;
          p_GenericMapping = (struct _GENERIC_MAPPING *)SsShareConnectMapping;
          v35 = pDestinationSecurityDescriptor;
          LastError = SsCheckAccess((__int64)&v33, SourceString, 1u);
          if ( !LastError )
          {
            v12 = (void *)*((_QWORD *)v10 + 9);
            if ( !v12 )
              goto LABEL_18;
            LastError = RtlCopySecurityDescriptor(v12, &ObjectsSecurityDescriptor);
            if ( LastError )
              goto LABEL_55;
            RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
            RtlSetOwnerSecurityDescriptor(SecurityDescriptor, *(PSID *)(qword_18005CDC0 + 32), 0);
            RtlSetGroupSecurityDescriptor(SecurityDescriptor, *(PSID *)(qword_18005CDC0 + 32), 0);
            GenericMapping.GenericRead = 1179785;
            GenericMapping.GenericWrite = 1179926;
            GenericMapping.GenericExecute = 1179808;
            GenericMapping.GenericAll = 2032127;
            if ( !ImpersonateSelf(SecurityImpersonation) )
            {
              LastError = GetLastError();
              goto LABEL_55;
            }
            LastError = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle);
            RevertToSelf();
            if ( !LastError )
            {
              LastError = RtlSetSecurityObject(
                            3u,
                            SecurityDescriptor,
                            &ObjectsSecurityDescriptor,
                            &GenericMapping,
                            TokenHandle);
              NtClose(TokenHandle);
              if ( !LastError )
              {
                p_GenericMapping = &GenericMapping;
                v35 = ObjectsSecurityDescriptor;
                LastError = SsCheckAccess((__int64)&v33, SourceString, a5);
                if ( !LastError )
                {
LABEL_18:
                  v13 = *((_QWORD *)v10 + 5);
                  v14 = -1;
                  v15 = -1;
                  do
                    ++v15;
                  while ( *(_WORD *)(v13 + 2 * v15) );
                  v16 = -1;
                  do
                    ++v16;
                  while ( pszPathIn[v16] );
                  if ( *(_WORD *)(v13 + 2 * v15 - 2) == 92 )
                    *(_WORD *)(v13 + 2 * v15-- - 2) = 0;
                  for ( i = 0; i < v16; ++i )
                  {
                    if ( pszPathIn[i] == 47 )
                      pszPathIn[i] = 92;
                  }
                  while ( *pszPathIn == 92 )
                    ++pszPathIn;
                  v18 = -1;
                  do
                    ++v18;
                  while ( pszPathIn[v18] );
                  v19 = (unsigned int)(2 * v18 + 2);
                  v20 = (WCHAR *)LocalAlloc(0x40u, v19);
                  v8 = v20;
                  if ( v20 )
                  {
                    if ( PathCchCanonicalizeEx(v20, v19 >> 1, pszPathIn, 0) )
                    {
                      LastError = 161;
                    }
                    else
                    {
                      for ( j = v8; *j == 92; ++j )
                        ;
                      v22 = -1;
                      do
                        ++v22;
                      while ( *(_WORD *)(*((_QWORD *)v10 + 5) + 2 * v22) );
                      do
                        ++v14;
                      while ( j[v14] );
                      v23 = (unsigned int)(2 * (v14 + v22) + 4);
                      v24 = (WCHAR *)LocalAlloc(0x40u, v23);
                      *a4 = v24;
                      if ( v24 )
                      {
                        LastError = PathCchCombineEx(v24, v23 >> 1, *((PCWSTR *)v10 + 5), j, 0);
                        if ( LastError
                          || (unsigned int)_o__wcsnicmp(*a4, *((_QWORD *)v10 + 5), v15, v25)
                          || (v26 = (*a4)[v15], v26 != 92) && v26 != 58 && v26
                          || RtlIsDosDeviceName_U(*a4) )
                        {
                          LastError = 161;
                        }
                      }
                      else
                      {
                        LastError = 8;
                      }
                    }
                  }
                  else
                  {
                    LastError = 8;
                  }
                }
              }
            }
          }
        }
      }
      else
      {
        LastError = 5023;
      }
    }
    else
    {
      LastError = 2310;
    }
  }
LABEL_55:
  if ( ObjectsSecurityDescriptor )
    RtlDeleteSecurityObject(&ObjectsSecurityDescriptor);
  if ( pDestinationSecurityDescriptor )
    RtlDeleteSecurityObject(&pDestinationSecurityDescriptor);
  if ( v10 )
    LocalFree(v10);
  if ( v8 )
    LocalFree(v8);
  if ( LastError && *a4 )
  {
    LocalFree((HLOCAL)*a4);
    *a4 = 0;
  }
  return LastError;
}

```

## disassembly

```asm
0x18001fdc4  push    rbp
0x18001fdc6  push    rbx
0x18001fdc7  push    rsi
0x18001fdc8  push    rdi
0x18001fdc9  push    r12
0x18001fdcb  push    r13
0x18001fdcd  push    r14
0x18001fdcf  push    r15
0x18001fdd1  lea     rbp, [rsp-8]
0x18001fdd6  sub     rsp, 108h
0x18001fddd  mov     rax, cs:__security_cookie
0x18001fde4  xor     rax, rsp
0x18001fde7  mov     [rbp+40h+var_50], rax
0x18001fdeb  xor     r15d, r15d
0x18001fdee  xorps   xmm0, xmm0
0x18001fdf1  mov     [rsp+140h+var_E0], r15d; int
0x18001fdf6  xor     eax, eax
0x18001fdf8  mov     [rsp+140h+var_E8], r15b; char
0x18001fdfd  mov     r13, r9
0x18001fe00  mov     [rsp+140h+var_F0], r15b; char
0x18001fe05  mov     rsi, r8
0x18001fe08  mov     [rsp+140h+var_F8], r15b; char
0x18001fe0d  mov     r14, rcx
0x18001fe10  mov     [rsp+140h+var_100], r15b; char
0x18001fe15  or      r8d, 0FFFFFFFFh; int
0x18001fe19  mov     [rsp+140h+var_108], rdx; PCWSTR
0x18001fe1e  mov     r12d, r15d
0x18001fe21  mov     [rsp+140h+SourceString], rcx; SourceString
0x18001fe26  lea     rdx, [rbp+40h+hMem]; int
0x18001fe2a  mov     [rbp+40h+var_68], rax
0x18001fe2e  mov     ecx, 1F9h; int
0x18001fe33  mov     [r9], r15
0x18001fe36  lea     rax, [rbp+40h+var_90]
0x18001fe3a  mov     [rsp+140h+var_118], r15; __int64
0x18001fe3f  lea     r9, [rsp+140h+var_D0]; int
0x18001fe44  mov     [rsp+140h+Token], rax; __int64
0x18001fe49  mov     [rbp+40h+hMem], r15
0x18001fe4d  mov     [rsp+140h+var_D0], r15d
0x18001fe52  mov     [rsp+140h+ObjectsSecurityDescriptor], r15
0x18001fe57  movups  [rbp+40h+SecurityDescriptor], xmm0
0x18001fe5b  mov     [rbp+40h+pDestinationSecurityDescriptor], r15
0x18001fe5f  movups  [rbp+40h+var_78], xmm0
0x18001fe63  mov     [rbp+40h+TokenHandle], r15
0x18001fe67  movups  xmmword ptr [rbp+40h+GenericMapping.GenericRead], xmm0
0x18001fe6b  call    ShareEnumCommonEx
0x18001fe70  mov     rdi, [rbp+40h+hMem]
0x18001fe74  mov     ebx, eax
0x18001fe76  test    eax, eax
0x18001fe78  jnz     loc_1800201BB
0x18001fe7e  cmp     [rsp+140h+var_D0], r15d
0x18001fe83  jz      loc_1800201B6
0x18001fe89  test    rdi, rdi
0x18001fe8c  jz      loc_1800201B6
0x18001fe92  cmp     [rdi+28h], r15
0x18001fe96  jnz     short loc_18001FEA0
0x18001fe98  lea     ebx, [rax+42h]
0x18001fe9b  jmp     loc_1800201BB
0x18001fea0  cmp     [rdi+8], r15b
0x18001fea4  jz      short loc_18001FEB0
0x18001fea6  mov     ebx, 41h ; 'A'
0x18001feab  jmp     loc_1800201BB
0x18001feb0  cmp     [rdi+18h], r15d
0x18001feb4  jz      loc_1800201AF
0x18001feba  mov     ecx, [rdi+18h]
0x18001febd  lea     rdx, [rbp+40h+pDestinationSecurityDescriptor]; pDestinationSecurityDescriptor
0x18001fec1  add     rcx, rdi; pSourceSecurityDescriptor
0x18001fec4  call    cs:__imp_RtlCopySecurityDescriptor
0x18001feca  mov     ebx, eax
0x18001fecc  test    eax, eax
0x18001fece  jnz     loc_1800201BB
0x18001fed4  lea     rax, SsShareConnectMapping
0x18001fedb  mov     [rbp+40h+var_A8], r14
0x18001fedf  mov     [rbp+40h+var_A0], rax
0x18001fee3  lea     r8d, [rbx+1]
0x18001fee7  mov     rax, [rbp+40h+pDestinationSecurityDescriptor]
0x18001feeb  lea     rcx, [rbp+40h+var_A8]
0x18001feef  mov     rdx, r14
0x18001fef2  mov     [rbp+40h+var_98], rax
0x18001fef6  call    SsCheckAccess
0x18001fefb  mov     ebx, eax
0x18001fefd  test    eax, eax
0x18001feff  jnz     loc_1800201BB
0x18001ff05  mov     rcx, [rdi+48h]; pSourceSecurityDescriptor
0x18001ff09  test    rcx, rcx
0x18001ff0c  jz      loc_180020021
0x18001ff12  lea     rdx, [rsp+140h+ObjectsSecurityDescriptor]; pDestinationSecurityDescriptor
0x18001ff17  call    cs:__imp_RtlCopySecurityDescriptor
0x18001ff1d  mov     ebx, eax
0x18001ff1f  test    eax, eax
0x18001ff21  jnz     loc_1800201BB
0x18001ff27  lea     edx, [rax+1]; Revision
0x18001ff2a  lea     rcx, [rbp+40h+SecurityDescriptor]; SecurityDescriptor
0x18001ff2e  call    cs:__imp_RtlCreateSecurityDescriptor
0x18001ff34  mov     rdx, cs:qword_18005CDC0
0x18001ff3b  lea     rcx, [rbp+40h+SecurityDescriptor]; SecurityDescriptor
0x18001ff3f  xor     r8d, r8d; OwnerDefaulted
0x18001ff42  mov     rdx, [rdx+20h]; Owner
0x18001ff46  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x18001ff4c  mov     rdx, cs:qword_18005CDC0
0x18001ff53  lea     rcx, [rbp+40h+SecurityDescriptor]; SecurityDescriptor
0x18001ff57  xor     r8d, r8d; GroupDefaulted
0x18001ff5a  mov     rdx, [rdx+20h]; Group
0x18001ff5e  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x18001ff64  lea     ecx, [rbx+2]; ImpersonationLevel
0x18001ff67  mov     [rbp+40h+GenericMapping.GenericRead], 120089h
0x18001ff6e  mov     [rbp+40h+GenericMapping.GenericWrite], 120116h
0x18001ff75  mov     [rbp+40h+GenericMapping.GenericExecute], 1200A0h
0x18001ff7c  mov     [rbp+40h+GenericMapping.GenericAll], 1F01FFh
0x18001ff83  call    cs:__imp_ImpersonateSelf
0x18001ff89  test    eax, eax
0x18001ff8b  jnz     short loc_18001FF9A
0x18001ff8d  call    cs:__imp_GetLastError
0x18001ff93  mov     ebx, eax
0x18001ff95  jmp     loc_1800201BB
0x18001ff9a  lea     r9, [rbp+40h+TokenHandle]; TokenHandle
0x18001ff9e  mov     r8b, 1; OpenAsSelf
0x18001ffa1  mov     edx, 8; DesiredAccess
0x18001ffa6  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18001ffad  call    cs:__imp_NtOpenThreadToken
0x18001ffb3  mov     ebx, eax
0x18001ffb5  call    cs:__imp_RevertToSelf
0x18001ffbb  test    ebx, ebx
0x18001ffbd  jnz     loc_1800201BB
0x18001ffc3  mov     rax, [rbp+40h+TokenHandle]
0x18001ffc7  lea     r9, [rbp+40h+GenericMapping]; GenericMapping
0x18001ffcb  lea     r8, [rsp+140h+ObjectsSecurityDescriptor]; ObjectsSecurityDescriptor
0x18001ffd0  mov     [rsp+140h+Token], rax; Token
0x18001ffd5  lea     rdx, [rbp+40h+SecurityDescriptor]; ModificationDescriptor
0x18001ffd9  lea     ecx, [rbx+3]; SecurityInformation
0x18001ffdc  call    cs:__imp_RtlSetSecurityObject
0x18001ffe2  mov     rcx, [rbp+40h+TokenHandle]; Handle
0x18001ffe6  mov     ebx, eax
0x18001ffe8  call    cs:__imp_NtClose
0x18001ffee  test    ebx, ebx
0x18001fff0  jnz     loc_1800201BB
0x18001fff6  mov     r8d, [rbp+40h+arg_20]
0x18001fffa  lea     rax, [rbp+40h+GenericMapping]
0x18001fffe  mov     [rbp+40h+var_A0], rax
0x180020002  lea     rcx, [rbp+40h+var_A8]
0x180020006  mov     rax, [rsp+140h+ObjectsSecurityDescriptor]
0x18002000b  mov     rdx, r14
0x18002000e  mov     [rbp+40h+var_98], rax
0x180020012  call    SsCheckAccess
0x180020017  mov     ebx, eax
0x180020019  test    eax, eax
0x18002001b  jnz     loc_1800201BB
0x180020021  mov     rcx, [rdi+28h]
0x180020025  or      r15, 0FFFFFFFFFFFFFFFFh
0x180020029  mov     r14, r15
0x18002002c  xor     r8d, r8d
0x18002002f  inc     r14
0x180020032  cmp     [rcx+r14*2], r8w
0x180020037  jnz     short loc_18002002F
0x180020039  mov     rdx, r15
0x18002003c  inc     rdx
0x18002003f  cmp     [rsi+rdx*2], r8w
0x180020044  jnz     short loc_18002003C
0x180020046  mov     r9d, 5Ch ; '\'
0x18002004c  cmp     [rcx+r14*2-2], r9w
0x180020052  jnz     short loc_18002005D
0x180020054  mov     [rcx+r14*2-2], r8w
0x18002005a  dec     r14
0x18002005d  mov     ecx, r8d
0x180020060  test    rdx, rdx
0x180020063  jz      short loc_180020082
0x180020065  mov     eax, ecx
0x180020067  cmp     word ptr [rsi+rax*2], 2Fh ; '/'
0x18002006c  jnz     short loc_180020073
0x18002006e  mov     [rsi+rax*2], r9w
0x180020073  inc     ecx
0x180020075  mov     eax, ecx
0x180020077  cmp     rax, rdx
0x18002007a  jb      short loc_180020065
0x18002007c  jmp     short loc_180020082
0x18002007e  add     rsi, 2
0x180020082  cmp     [rsi], r9w
0x180020086  jz      short loc_18002007E
0x180020088  mov     rax, r15
0x18002008b  inc     rax
0x18002008e  cmp     [rsi+rax*2], r8w
0x180020093  jnz     short loc_18002008B
0x180020095  lea     eax, ds:2[rax*2]
0x18002009c  mov     ecx, 40h ; '@'; uFlags
0x1800200a1  mov     edx, eax; uBytes
0x1800200a3  mov     ebx, eax
0x1800200a5  call    cs:__imp_LocalAlloc
0x1800200ab  mov     r12, rax
0x1800200ae  test    rax, rax
0x1800200b1  jz      loc_1800201A5
0x1800200b7  shr     rbx, 1
0x1800200ba  xor     r9d, r9d; dwFlags
0x1800200bd  mov     rdx, rbx; cchPathOut
0x1800200c0  mov     r8, rsi; pszPathIn
0x1800200c3  mov     rcx, rax; pszPathOut
0x1800200c6  call    cs:__imp_PathCchCanonicalizeEx
0x1800200cc  xor     edx, edx
0x1800200ce  test    eax, eax
0x1800200d0  jz      short loc_1800200DF
0x1800200d2  mov     ebx, 0A1h
0x1800200d7  xor     r15d, r15d
0x1800200da  jmp     loc_1800201BB
0x1800200df  mov     eax, 5Ch ; '\'
0x1800200e4  mov     rbx, r12
0x1800200e7  cmp     [r12], ax
0x1800200ec  jnz     short loc_1800200F7
0x1800200ee  add     rbx, 2
0x1800200f2  cmp     [rbx], ax
0x1800200f5  jz      short loc_1800200EE
0x1800200f7  mov     rcx, [rdi+28h]
0x1800200fb  mov     rax, r15
0x1800200fe  inc     rax
0x180020101  cmp     [rcx+rax*2], dx
0x180020105  jnz     short loc_1800200FE
0x180020107  inc     r15
0x18002010a  cmp     [rbx+r15*2], dx
0x18002010f  jnz     short loc_180020107
0x180020111  add     rax, r15
0x180020114  mov     ecx, 40h ; '@'; uFlags
0x180020119  lea     rax, ds:4[rax*2]
0x180020121  mov     edx, eax; uBytes
0x180020123  mov     esi, eax
0x180020125  call    cs:__imp_LocalAlloc
0x18002012b  xor     r15d, r15d
0x18002012e  mov     [r13+0], rax
0x180020132  test    rax, rax
0x180020135  jz      short loc_18002019E
0x180020137  mov     r8, [rdi+28h]; pszPathIn
0x18002013b  mov     r9, rbx; pszMore
0x18002013e  shr     rsi, 1
0x180020141  mov     rcx, rax; pszPathOut
0x180020144  mov     rdx, rsi; cchPathOut
0x180020147  mov     dword ptr [rsp+140h+Token], r15d; dwFlags
0x18002014c  call    cs:__imp_PathCchCombineEx
0x180020152  mov     ebx, eax
0x180020154  test    eax, eax
0x180020156  jz      short loc_18002015F
0x180020158  mov     ebx, 0A1h
0x18002015d  jmp     short loc_1800201BB
0x18002015f  mov     rdx, [rdi+28h]
0x180020163  mov     r8, r14
0x180020166  mov     rcx, [r13+0]
0x18002016a  call    cs:__imp__o__wcsnicmp
0x180020170  test    eax, eax
0x180020172  jnz     short loc_180020158
0x180020174  mov     rcx, [r13+0]; Name
0x180020178  mov     edx, 5Ch ; '\'
0x18002017d  movzx   eax, word ptr [rcx+r14*2]
0x180020182  cmp     ax, dx
0x180020185  jz      short loc_180020192
0x180020187  cmp     ax, 3Ah ; ':'
0x18002018b  jz      short loc_180020192
0x18002018d  test    ax, ax
0x180020190  jnz     short loc_180020158
0x180020192  call    cs:__imp_RtlIsDosDeviceName_U
0x180020198  test    eax, eax
0x18002019a  jz      short loc_1800201BB
0x18002019c  jmp     short loc_180020158
0x18002019e  mov     ebx, 8
0x1800201a3  jmp     short loc_1800201BB
0x1800201a5  mov     ebx, 8
0x1800201aa  jmp     loc_1800200D7
0x1800201af  mov     ebx, 139Fh
0x1800201b4  jmp     short loc_1800201BB
0x1800201b6  mov     ebx, 906h
0x1800201bb  cmp     [rsp+140h+ObjectsSecurityDescriptor], r15
0x1800201c0  jz      short loc_1800201CD
0x1800201c2  lea     rcx, [rsp+140h+ObjectsSecurityDescriptor]; ObjectDescriptor
0x1800201c7  call    cs:__imp_RtlDeleteSecurityObject
0x1800201cd  cmp     [rbp+40h+pDestinationSecurityDescriptor], r15
0x1800201d1  jz      short loc_1800201DD
0x1800201d3  lea     rcx, [rbp+40h+pDestinationSecurityDescriptor]; ObjectDescriptor
0x1800201d7  call    cs:__imp_RtlDeleteSecurityObject
0x1800201dd  test    rdi, rdi
0x1800201e0  jz      short loc_1800201EB
0x1800201e2  mov     rcx, rdi; hMem
0x1800201e5  call    cs:__imp_LocalFree
0x1800201eb  test    r12, r12
0x1800201ee  jz      short loc_1800201F9
0x1800201f0  mov     rcx, r12; hMem
0x1800201f3  call    cs:__imp_LocalFree
0x1800201f9  test    ebx, ebx
0x1800201fb  jz      short loc_180020210
0x1800201fd  mov     rcx, [r13+0]; hMem
0x180020201  test    rcx, rcx
0x180020204  jz      short loc_180020210
0x180020206  call    cs:__imp_LocalFree
0x18002020c  mov     [r13+0], r15
0x180020210  mov     eax, ebx
0x180020212  mov     rcx, [rbp+40h+var_50]
0x180020216  xor     rcx, rsp; StackCookie
0x180020219  call    __security_check_cookie
0x18002021e  add     rsp, 108h
0x180020225  pop     r15
0x180020227  pop     r14
0x180020229  pop     r13
0x18002022b  pop     r12
0x18002022d  pop     rdi
0x18002022e  pop     rsi
0x18002022f  pop     rbx
0x180020230  pop     rbp
  ... truncated ...
```
