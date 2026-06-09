# SspiExcludePackage

- ea: `0x180017410`
- end: `0x180017754`
- name: `SspiExcludePackage`
- size: `836`
- prototype: `SECURITY_STATUS __stdcall(PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthIdentity, PCWSTR pszPackageName, PSEC_WINNT_AUTH_IDENTITY_OPAQUE *ppNewAuthIdentity)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005cc0`
- `0x180008920`
- `0x1800113a0`
- `0x180014520`
- `0x1800152c0`
- `0x180017410`
- `0x180018600`
- `0x1800201e4`
- `0x180022047`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!wcsstr` at `0x180017605`
- `api-ms-win-core-crt-l1-1-0!wcsstr` at `0x180017605`
- `ntdll!RtlInitUnicodeString` at `0x180017526`
- `ntdll!RtlInitUnicodeString` at `0x180017526`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001749f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001754d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800175c4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017629`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001749f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001754d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800175c4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017629`

## pseudocode

```c
SECURITY_STATUS __stdcall SspiExcludePackage(
        PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthIdentity,
        PCWSTR pszPackageName,
        PSEC_WINNT_AUTH_IDENTITY_OPAQUE *ppNewAuthIdentity)
{
  __int64 v3; // r15
  __int64 v4; // r14
  char *Buffer; // rdi
  SECURITY_STATUS v8; // ebx
  char *v9; // rsi
  WCHAR *v10; // rax
  unsigned __int8 *v11; // rcx
  unsigned int v12; // eax
  WCHAR *v13; // rax
  char *v14; // rax
  char *v15; // rax
  WCHAR *v16; // rcx
  __int64 v17; // rax
  PCWSTR ppszPackedCredentialsString; // [rsp+30h] [rbp-30h] BYREF
  PCWSTR SourceString; // [rsp+38h] [rbp-28h] BYREF
  PCWSTR ppszUserName; // [rsp+40h] [rbp-20h] BYREF
  PCWSTR ppszDomainName; // [rsp+48h] [rbp-18h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-10h] BYREF
  unsigned int v24; // [rsp+A0h] [rbp+40h] BYREF
  PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthDataCopy; // [rsp+B8h] [rbp+58h] BYREF

  v3 = -1;
  AuthDataCopy = 0;
  v4 = -1;
  ppszUserName = 0;
  ppszDomainName = 0;
  ppszPackedCredentialsString = 0;
  DestinationString = 0;
  v24 = 0;
  Buffer = 0;
  SourceString = 0;
  do
    ++v4;
  while ( pszPackageName[v4] );
  if ( AuthIdentity )
  {
    v8 = SspiCopyAuthIdentity(AuthIdentity, &AuthDataCopy);
    if ( v8 < 0 )
      goto LABEL_30;
    v9 = (char *)AuthDataCopy;
    if ( *(_DWORD *)AuthDataCopy == 513 )
    {
      if ( *((_WORD *)AuthDataCopy + 22) )
      {
        v10 = (WCHAR *)LocalAlloc(0x40u, *((unsigned __int16 *)AuthDataCopy + 22) + 4LL);
        DestinationString.Buffer = v10;
        if ( !v10 )
        {
LABEL_8:
          v8 = -1073741801;
          goto LABEL_30;
        }
        memcpy_0(v10, &v9[*((unsigned int *)v9 + 10)], *((unsigned __int16 *)v9 + 22));
        DestinationString.Length = *((_WORD *)v9 + 22);
        DestinationString.MaximumLength = DestinationString.Length + 2;
        *((_WORD *)v9 + 22) = 0;
        *((_DWORD *)v9 + 10) = 0;
      }
    }
    else if ( *(_DWORD *)AuthDataCopy == 512 )
    {
      v11 = (unsigned __int8 *)*((_QWORD *)AuthDataCopy + 7);
      if ( v11 )
      {
        v12 = *((_DWORD *)AuthDataCopy + 16);
        if ( (*((_BYTE *)AuthDataCopy + 52) & 1) != 0 )
        {
          v8 = SspiHelperConvertAnsiStringToUnicodeString(v11, v12, &SourceString);
          if ( v8 < 0 )
          {
            Buffer = (char *)SourceString;
            goto LABEL_30;
          }
          RtlInitUnicodeString(&DestinationString, SourceString);
        }
        else if ( v12 )
        {
          v13 = (WCHAR *)LocalAlloc(0x40u, 2 * v12 + 2 + 2LL);
          DestinationString.Buffer = v13;
          if ( !v13 )
            goto LABEL_8;
          memcpy_0(v13, *((const void **)v9 + 7), 2LL * *((unsigned int *)v9 + 16));
          DestinationString.Length = 2 * *((_WORD *)v9 + 32);
          DestinationString.MaximumLength = 2 * (*((_WORD *)v9 + 32) + 1);
        }
        *((_QWORD *)v9 + 7) = 0;
        *((_DWORD *)v9 + 16) = 0;
      }
    }
    v8 = SspiEncodeAuthIdentityAsStrings(AuthDataCopy, &ppszUserName, &ppszDomainName, &ppszPackedCredentialsString);
    if ( v8 < 0 )
      goto LABEL_30;
  }
  v14 = (char *)LocalAlloc(0x40u, (unsigned int)(2 * v4 + 4) + 2LL);
  Buffer = v14;
  if ( !v14 )
    goto LABEL_8;
  *(_WORD *)v14 = 33;
  memcpy_0(v14 + 2, pszPackageName, 2LL * (unsigned int)v4);
  if ( DestinationString.Length )
  {
    if ( wcsstr(DestinationString.Buffer, (const wchar_t *)Buffer) )
    {
      Buffer = (char *)DestinationString.Buffer;
      DestinationString = 0;
    }
    else
    {
      SspiLocalFree(Buffer);
      v15 = (char *)LocalAlloc(0x40u, 2 * (_DWORD)v4 + (unsigned int)DestinationString.Length + 6 + 2LL);
      Buffer = v15;
      if ( !v15 )
      {
        v8 = -1073741801;
        goto LABEL_30;
      }
      memcpy_0(v15, DestinationString.Buffer, DestinationString.Length);
      *(_WORD *)&Buffer[DestinationString.Length & 0xFFFE] = 44;
      *(_WORD *)&Buffer[(DestinationString.Length & 0xFFFE) + 2] = 33;
      memcpy_0(
        &Buffer[2 * ((unsigned __int64)DestinationString.Length >> 1) + 4],
        pszPackageName,
        2LL * (unsigned int)v4);
    }
  }
  v8 = SspiHelperConstructAuthdataExWMarshalledW(
         ppszUserName,
         ppszDomainName,
         ppszPackedCredentialsString,
         (const unsigned __int16 *)Buffer,
         (struct _SEC_WINNT_AUTH_IDENTITY_EXW **)ppNewAuthIdentity,
         &v24);
LABEL_30:
  if ( AuthDataCopy )
    SspiFreeAuthIdentity(AuthDataCopy);
  if ( DestinationString.Buffer )
    SspiLocalFree(DestinationString.Buffer);
  if ( ppszUserName )
    SspiLocalFree((PVOID)ppszUserName);
  if ( ppszDomainName )
    SspiLocalFree((PVOID)ppszDomainName);
  v16 = (WCHAR *)ppszPackedCredentialsString;
  if ( ppszPackedCredentialsString )
  {
    do
      ++v3;
    while ( ppszPackedCredentialsString[v3] );
    v17 = 2 * v3;
    if ( 2 * v3 )
    {
      do
      {
        *(_BYTE *)v16 = 0;
        v16 = (WCHAR *)((char *)v16 + 1);
        --v17;
      }
      while ( v17 );
      v16 = (WCHAR *)ppszPackedCredentialsString;
    }
    SspiLocalFree(v16);
  }
  if ( Buffer )
    SspiLocalFree(Buffer);
  return SspNtStatusToSecStatus((unsigned int)v8);
}

```

## disassembly

```asm
0x180017410  mov     [rsp-38h+arg_8], rbx
0x180017415  push    rbp
0x180017416  push    rsi
0x180017417  push    rdi
0x180017418  push    r12
0x18001741a  push    r13
0x18001741c  push    r14
0x18001741e  push    r15
0x180017420  mov     rbp, rsp
0x180017423  sub     rsp, 60h
0x180017427  xor     esi, esi
0x180017429  xorps   xmm0, xmm0
0x18001742c  or      r15, 0FFFFFFFFFFFFFFFFh
0x180017430  mov     [rbp+AuthDataCopy], rsi
0x180017434  mov     r14, r15
0x180017437  mov     [rbp+ppszUserName], rsi
0x18001743b  mov     r13, r8
0x18001743e  mov     [rbp+ppszDomainName], rsi
0x180017442  mov     r12, rdx
0x180017445  mov     [rbp+ppszPackedCredentialsString], rsi
0x180017449  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18001744d  mov     [rbp+arg_0], esi
0x180017450  mov     edi, esi
0x180017452  mov     [rbp+SourceString], rsi
0x180017456  inc     r14
0x180017459  cmp     [rdx+r14*2], si
0x18001745e  jnz     short loc_180017456
0x180017460  test    rcx, rcx
0x180017463  jz      loc_1800175B4
0x180017469  lea     rdx, [rbp+AuthDataCopy]; AuthDataCopy
0x18001746d  call    SspiCopyAuthIdentity
0x180017472  mov     ebx, eax
0x180017474  test    eax, eax
0x180017476  js      loc_1800176BB
0x18001747c  mov     rsi, [rbp+AuthDataCopy]
0x180017480  cmp     dword ptr [rsi], 201h
0x180017486  jnz     short loc_1800174E9
0x180017488  xor     ebx, ebx
0x18001748a  cmp     [rsi+2Ch], bx
0x18001748e  jz      loc_180017593
0x180017494  movzx   edx, word ptr [rsi+2Ch]
0x180017498  lea     ecx, [rbx+40h]; uFlags
0x18001749b  add     rdx, 4; uBytes
0x18001749f  call    cs:__imp_LocalAlloc
0x1800174a5  mov     [rbp+DestinationString.Buffer], rax
0x1800174a9  test    rax, rax
0x1800174ac  jnz     short loc_1800174BA
0x1800174ae  mov     ebx, 0C0000017h
0x1800174b3  xor     esi, esi
0x1800174b5  jmp     loc_1800176BB
0x1800174ba  mov     edx, [rsi+28h]
0x1800174bd  mov     rcx, rax; void *
0x1800174c0  movzx   r8d, word ptr [rsi+2Ch]; Size
0x1800174c5  add     rdx, rsi; Src
0x1800174c8  call    memcpy_0
0x1800174cd  movzx   eax, word ptr [rsi+2Ch]
0x1800174d1  mov     [rbp+DestinationString.Length], ax
0x1800174d5  add     ax, 2
0x1800174d9  mov     [rbp+DestinationString.MaximumLength], ax
0x1800174dd  mov     [rsi+2Ch], bx
0x1800174e1  mov     [rsi+28h], ebx
0x1800174e4  jmp     loc_180017593
0x1800174e9  cmp     dword ptr [rsi], 200h
0x1800174ef  jnz     loc_180017593
0x1800174f5  mov     rcx, [rsi+38h]; unsigned __int8 *
0x1800174f9  xor     ebx, ebx
0x1800174fb  test    rcx, rcx
0x1800174fe  jz      loc_180017593
0x180017504  test    byte ptr [rsi+34h], 1
0x180017508  mov     eax, [rsi+40h]
0x18001750b  jz      short loc_180017539
0x18001750d  lea     r8, [rbp+SourceString]; unsigned __int16 **
0x180017511  mov     edx, eax; unsigned int
0x180017513  call    ?SspiHelperConvertAnsiStringToUnicodeString@@YAJPEAEKPEAPEBG@Z; SspiHelperConvertAnsiStringToUnicodeString(uchar *,ulong,ushort const * *)
0x180017518  mov     ebx, eax
0x18001751a  test    eax, eax
0x18001751c  js      short loc_180017530
0x18001751e  mov     rdx, [rbp+SourceString]; SourceString
0x180017522  lea     rcx, [rbp+DestinationString]; DestinationString
0x180017526  call    cs:__imp_RtlInitUnicodeString
0x18001752c  xor     ebx, ebx
0x18001752e  jmp     short loc_18001758C
0x180017530  mov     rdi, [rbp+SourceString]
0x180017534  jmp     loc_1800174B3
0x180017539  test    eax, eax
0x18001753b  jz      short loc_18001758C
0x18001753d  lea     edx, ds:2[rax*2]
0x180017544  mov     ecx, 40h ; '@'; uFlags
0x180017549  add     rdx, 2; uBytes
0x18001754d  call    cs:__imp_LocalAlloc
0x180017553  mov     [rbp+DestinationString.Buffer], rax
0x180017557  test    rax, rax
0x18001755a  jz      loc_1800174AE
0x180017560  mov     r8d, [rsi+40h]
0x180017564  mov     rcx, rax; void *
0x180017567  mov     rdx, [rsi+38h]; Src
0x18001756b  add     r8, r8; Size
0x18001756e  call    memcpy_0
0x180017573  movzx   eax, word ptr [rsi+40h]
0x180017577  add     ax, ax
0x18001757a  mov     [rbp+DestinationString.Length], ax
0x18001757e  movzx   eax, word ptr [rsi+40h]
0x180017582  inc     ax
0x180017585  add     ax, ax
0x180017588  mov     [rbp+DestinationString.MaximumLength], ax
0x18001758c  mov     [rsi+38h], rbx
0x180017590  mov     [rsi+40h], ebx
0x180017593  mov     rcx, [rbp+AuthDataCopy]; pAuthIdentity
0x180017597  lea     r9, [rbp+ppszPackedCredentialsString]; ppszPackedCredentialsString
0x18001759b  lea     r8, [rbp+ppszDomainName]; ppszDomainName
0x18001759f  lea     rdx, [rbp+ppszUserName]; ppszUserName
0x1800175a3  call    SspiEncodeAuthIdentityAsStrings
0x1800175a8  xor     esi, esi
0x1800175aa  mov     ebx, eax
0x1800175ac  test    eax, eax
0x1800175ae  js      loc_1800176BB
0x1800175b4  lea     esi, [r14+r14]
0x1800175b8  mov     ecx, 40h ; '@'; uFlags
0x1800175bd  lea     edx, [rsi+4]
0x1800175c0  add     rdx, 2; uBytes
0x1800175c4  call    cs:__imp_LocalAlloc
0x1800175ca  mov     rdi, rax
0x1800175cd  test    rax, rax
0x1800175d0  jz      loc_1800174AE
0x1800175d6  mov     ebx, r14d
0x1800175d9  lea     rcx, [rax+2]; void *
0x1800175dd  add     rbx, rbx
0x1800175e0  mov     word ptr [rax], 21h ; '!'
0x1800175e5  mov     r8, rbx; Size
0x1800175e8  mov     rdx, r12; Src
0x1800175eb  call    memcpy_0
0x1800175f0  xor     r14d, r14d
0x1800175f3  cmp     [rbp+DestinationString.Length], r14w
0x1800175f8  jz      loc_180017695
0x1800175fe  mov     rcx, [rbp+DestinationString.Buffer]; Str
0x180017602  mov     rdx, rdi; SubStr
0x180017605  call    cs:__imp_wcsstr
0x18001760b  test    rax, rax
0x18001760e  jnz     short loc_18001768A
0x180017610  mov     rcx, rdi; DataBuffer
0x180017613  call    SspiLocalFree
0x180017618  movzx   edx, [rbp+DestinationString.Length]
0x18001761c  lea     ecx, [r14+40h]; uFlags
0x180017620  add     edx, 6
0x180017623  add     edx, esi
0x180017625  add     rdx, 2; uBytes
0x180017629  call    cs:__imp_LocalAlloc
0x18001762f  xor     esi, esi
0x180017631  mov     rdi, rax
0x180017634  test    rax, rax
0x180017637  jnz     short loc_180017640
0x180017639  mov     ebx, 0C0000017h
0x18001763e  jmp     short loc_1800176BB
0x180017640  movzx   r8d, [rbp+DestinationString.Length]; Size
0x180017645  mov     rcx, rdi; void *
0x180017648  mov     rdx, [rbp+DestinationString.Buffer]; Src
0x18001764c  call    memcpy_0
0x180017651  movzx   eax, [rbp+DestinationString.Length]
0x180017655  mov     r8, rbx; Size
0x180017658  and     rax, 0FFFFFFFFFFFFFFFEh
0x18001765c  mov     rdx, r12; Src
0x18001765f  mov     word ptr [rax+rdi], 2Ch ; ','
0x180017665  movzx   eax, [rbp+DestinationString.Length]
0x180017669  and     rax, 0FFFFFFFFFFFFFFFEh
0x18001766d  mov     word ptr [rax+rdi+2], 21h ; '!'
0x180017674  movzx   eax, [rbp+DestinationString.Length]
0x180017678  shr     rax, 1
0x18001767b  add     rax, 2
0x18001767f  lea     rcx, [rdi+rax*2]; void *
0x180017683  call    memcpy_0
0x180017688  jmp     short loc_180017697
0x18001768a  mov     rdi, [rbp+DestinationString.Buffer]
0x18001768e  xorps   xmm0, xmm0
0x180017691  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180017695  xor     esi, esi
0x180017697  mov     r8, [rbp+ppszPackedCredentialsString]; unsigned __int16 *
0x18001769b  lea     rax, [rbp+arg_0]
0x18001769f  mov     rdx, [rbp+ppszDomainName]; unsigned __int16 *
0x1800176a3  mov     r9, rdi; unsigned __int16 *
0x1800176a6  mov     rcx, [rbp+ppszUserName]; unsigned __int16 *
0x1800176aa  mov     [rsp+60h+var_38], rax; unsigned int *
0x1800176af  mov     [rsp+60h+var_40], r13; struct _SEC_WINNT_AUTH_IDENTITY_EXW **
0x1800176b4  call    ?SspiHelperConstructAuthdataExWMarshalledW@@YAJPEBG000PEAPEAU_SEC_WINNT_AUTH_IDENTITY_EXW@@PEAK@Z; SspiHelperConstructAuthdataExWMarshalledW(ushort const *,ushort const *,ushort const *,ushort const *,_SEC_WINNT_AUTH_IDENTITY_EXW * *,ulong *)
0x1800176b9  mov     ebx, eax
0x1800176bb  mov     rcx, [rbp+AuthDataCopy]; AuthData
0x1800176bf  test    rcx, rcx
0x1800176c2  jz      short loc_1800176C9
0x1800176c4  call    SspiFreeAuthIdentity
0x1800176c9  mov     rcx, [rbp+DestinationString.Buffer]; DataBuffer
0x1800176cd  test    rcx, rcx
0x1800176d0  jz      short loc_1800176D7
0x1800176d2  call    SspiLocalFree
0x1800176d7  mov     rcx, [rbp+ppszUserName]; DataBuffer
0x1800176db  test    rcx, rcx
0x1800176de  jz      short loc_1800176E5
0x1800176e0  call    SspiLocalFree
0x1800176e5  mov     rcx, [rbp+ppszDomainName]; DataBuffer
0x1800176e9  test    rcx, rcx
0x1800176ec  jz      short loc_1800176F3
0x1800176ee  call    SspiLocalFree
0x1800176f3  mov     rcx, [rbp+ppszPackedCredentialsString]
0x1800176f7  test    rcx, rcx
0x1800176fa  jz      short loc_180017728
0x1800176fc  inc     r15
0x1800176ff  cmp     [rcx+r15*2], si
0x180017704  jnz     short loc_1800176FC
0x180017706  lea     rax, [r15+r15]
0x18001770a  test    rax, rax
0x18001770d  jz      short loc_180017723
0x18001770f  mov     edx, 1
0x180017714  mov     [rcx], sil
0x180017717  add     rcx, rdx
0x18001771a  sub     rax, rdx
0x18001771d  jnz     short loc_180017714
0x18001771f  mov     rcx, [rbp+ppszPackedCredentialsString]; DataBuffer
0x180017723  call    SspiLocalFree
0x180017728  test    rdi, rdi
0x18001772b  jz      short loc_180017735
0x18001772d  mov     rcx, rdi; DataBuffer
0x180017730  call    SspiLocalFree
0x180017735  mov     ecx, ebx
0x180017737  call    SspNtStatusToSecStatus
0x18001773c  mov     rbx, [rsp+60h+arg_8]
0x180017744  add     rsp, 60h
0x180017748  pop     r15
0x18001774a  pop     r14
0x18001774c  pop     r13
0x18001774e  pop     r12
0x180017750  pop     rdi
0x180017751  pop     rsi
0x180017752  pop     rbp
0x180017753  retn
```
