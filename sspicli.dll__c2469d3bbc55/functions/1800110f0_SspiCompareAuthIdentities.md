# SspiCompareAuthIdentities

- ea: `0x1800110f0`
- end: `0x180011393`
- name: `SspiCompareAuthIdentities`
- size: `675`
- prototype: `SECURITY_STATUS __stdcall(PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthIdentity1, PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthIdentity2, PBOOLEAN SameSuppliedUser, PBOOLEAN SameSuppliedIdentity)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180005cc0`
- `0x1800110f0`
- `0x1800113a0`
- `0x180014d38`
- `0x180015068`
- `0x180018600`
- `0x18001fe8c`
- `0x180020080`
- `0x1800202a8`

## pseudocode

```c
SECURITY_STATUS __stdcall SspiCompareAuthIdentities(
        PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthIdentity1,
        PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthIdentity2,
        PBOOLEAN SameSuppliedUser,
        PBOOLEAN SameSuppliedIdentity)
{
  const WCHAR **v4; // rsi
  PCWSTR *v5; // rdi
  SECURITY_STATUS v10; // ebx
  const WCHAR *v11; // rcx
  const WCHAR *v12; // r8
  const WCHAR *v13; // rdx
  PVOID DataBuffer; // [rsp+20h] [rbp-30h] BYREF
  PVOID v16; // [rsp+28h] [rbp-28h] BYREF
  PCWSTR ppszDomainName; // [rsp+30h] [rbp-20h] BYREF
  PCWSTR v18; // [rsp+38h] [rbp-18h] BYREF
  PCWSTR ppszPackedCredentialsString; // [rsp+40h] [rbp-10h] BYREF
  PCWSTR v20; // [rsp+48h] [rbp-8h] BYREF
  enum _CRED_MARSHAL_TYPE v21; // [rsp+90h] [rbp+40h] BYREF
  PCWSTR ppszUserName; // [rsp+A0h] [rbp+50h] BYREF
  PCWSTR v23; // [rsp+A8h] [rbp+58h] BYREF

  v4 = 0;
  ppszUserName = 0;
  v5 = 0;
  ppszDomainName = 0;
  ppszPackedCredentialsString = 0;
  v23 = 0;
  v18 = 0;
  v20 = 0;
  v21 = 0;
  DataBuffer = 0;
  v16 = 0;
  if ( SameSuppliedUser )
    *SameSuppliedUser = 0;
  if ( SameSuppliedIdentity )
    *SameSuppliedIdentity = 0;
  if ( !AuthIdentity1
    || (v10 = SspiEncodeAuthIdentityAsStrings(
                AuthIdentity1,
                &ppszUserName,
                &ppszDomainName,
                &ppszPackedCredentialsString),
        v10 >= 0) )
  {
    if ( !AuthIdentity2 || (v10 = SspiEncodeAuthIdentityAsStrings(AuthIdentity2, &v23, &v18, &v20), v10 >= 0) )
    {
      if ( SspiHelperEqualStrings(ppszUserName, v23, 1u) && SspiHelperEqualStrings(ppszDomainName, v18, 1u) )
      {
        if ( SameSuppliedUser )
          *SameSuppliedUser = 1;
        if ( SameSuppliedIdentity
          && (SspiHelperEqualStrings(ppszPackedCredentialsString, v20, 0)
           || (unsigned int)SspiHelperEqualPackedCredentials(AuthIdentity1, AuthIdentity2)) )
        {
          *SameSuppliedIdentity = 1;
        }
        goto LABEL_39;
      }
      if ( SameSuppliedUser )
      {
        if ( ppszUserName && (unsigned int)LocalCredIsMarshaledCredentialW(ppszUserName) )
        {
          if ( LocalCredUnmarshalCredentialW(ppszUserName, &v21, &DataBuffer) )
          {
            v4 = (const WCHAR **)DataBuffer;
            v10 = -1073741670;
            goto LABEL_40;
          }
          if ( ((v21 - 2) & 0xFFFFFFFD) != 0 )
            SspiLocalFree(DataBuffer);
          else
            v4 = (const WCHAR **)DataBuffer;
        }
        if ( v23 && (unsigned int)LocalCredIsMarshaledCredentialW(v23) )
        {
          if ( LocalCredUnmarshalCredentialW(v23, &v21, &v16) )
          {
            v5 = (PCWSTR *)v16;
            v10 = -1073741670;
            goto LABEL_40;
          }
          if ( ((v21 - 2) & 0xFFFFFFFD) != 0 )
            SspiLocalFree(v16);
          else
            v5 = (PCWSTR *)v16;
        }
        if ( v4 )
        {
          v11 = *v4;
          if ( v5 )
          {
            *SameSuppliedUser = SspiHelperEqualStrings(v11, *v5, 1u);
            goto LABEL_39;
          }
          v12 = v18;
          v13 = v23;
        }
        else
        {
          if ( !v5 )
            goto LABEL_39;
          v12 = ppszDomainName;
          v13 = ppszUserName;
          v11 = *v5;
        }
        v10 = SspiHelperCompareUserNames(v11, v13, v12, SameSuppliedUser);
        if ( v10 < 0 )
          goto LABEL_40;
      }
LABEL_39:
      v10 = 0;
    }
  }
LABEL_40:
  if ( ppszUserName )
    SspiLocalFree((PVOID)ppszUserName);
  if ( ppszDomainName )
    SspiLocalFree((PVOID)ppszDomainName);
  if ( ppszPackedCredentialsString )
    SspiLocalFree((PVOID)ppszPackedCredentialsString);
  if ( v23 )
    SspiLocalFree((PVOID)v23);
  if ( v18 )
    SspiLocalFree((PVOID)v18);
  if ( v20 )
    SspiLocalFree((PVOID)v20);
  if ( v4 )
    SspiLocalFree(v4);
  if ( v5 )
    SspiLocalFree(v5);
  return SspNtStatusToSecStatus((unsigned int)v10);
}

```

## disassembly

```asm
0x1800110f0  mov     [rsp-38h+arg_8], rbx
0x1800110f5  push    rbp
0x1800110f6  push    rsi
0x1800110f7  push    rdi
0x1800110f8  push    r12
0x1800110fa  push    r13
0x1800110fc  push    r14
0x1800110fe  push    r15
0x180011100  mov     rbp, rsp
0x180011103  sub     rsp, 50h
0x180011107  xor     esi, esi
0x180011109  mov     [rbp+ppszUserName], 0
0x180011111  xor     edi, edi
0x180011113  mov     [rbp+ppszDomainName], 0
0x18001111b  mov     [rbp+ppszPackedCredentialsString], 0
0x180011123  mov     r15, r9
0x180011126  mov     [rbp+arg_18], 0
0x18001112e  mov     r14, r8
0x180011131  mov     [rbp+var_18], 0
0x180011139  mov     r12, rdx
0x18001113c  mov     [rbp+var_8], 0
0x180011144  mov     r13, rcx
0x180011147  mov     [rbp+arg_0], 0
0x18001114e  mov     [rbp+DataBuffer], rsi
0x180011152  mov     [rbp+var_28], rdi
0x180011156  test    r8, r8
0x180011159  jz      short loc_18001115E
0x18001115b  mov     [r8], sil
0x18001115e  test    r15, r15
0x180011161  jz      short loc_180011166
0x180011163  mov     [r9], sil
0x180011166  test    r13, r13
0x180011169  jz      short loc_180011186
0x18001116b  lea     r9, [rbp+ppszPackedCredentialsString]; ppszPackedCredentialsString
0x18001116f  lea     r8, [rbp+ppszDomainName]; ppszDomainName
0x180011173  lea     rdx, [rbp+ppszUserName]; ppszUserName
0x180011177  call    SspiEncodeAuthIdentityAsStrings
0x18001117c  mov     ebx, eax
0x18001117e  test    eax, eax
0x180011180  js      loc_180011306
0x180011186  test    r12, r12
0x180011189  jz      short loc_1800111A9
0x18001118b  lea     r9, [rbp+var_8]; ppszPackedCredentialsString
0x18001118f  mov     rcx, r12; pAuthIdentity
0x180011192  lea     r8, [rbp+var_18]; ppszDomainName
0x180011196  lea     rdx, [rbp+arg_18]; ppszUserName
0x18001119a  call    SspiEncodeAuthIdentityAsStrings
0x18001119f  mov     ebx, eax
0x1800111a1  test    eax, eax
0x1800111a3  js      loc_180011306
0x1800111a9  mov     rdx, [rbp+arg_18]; PCWSTR
0x1800111ad  mov     r8b, 1; CaseInsensitive
0x1800111b0  mov     rcx, [rbp+ppszUserName]; SourceString
0x1800111b4  call    ?SspiHelperEqualStrings@@YAEPEBG0E@Z; SspiHelperEqualStrings(ushort const *,ushort const *,uchar)
0x1800111b9  test    al, al
0x1800111bb  jz      short loc_180011213
0x1800111bd  mov     rdx, [rbp+var_18]; PCWSTR
0x1800111c1  mov     r8b, 1; CaseInsensitive
0x1800111c4  mov     rcx, [rbp+ppszDomainName]; SourceString
0x1800111c8  call    ?SspiHelperEqualStrings@@YAEPEBG0E@Z; SspiHelperEqualStrings(ushort const *,ushort const *,uchar)
0x1800111cd  test    al, al
0x1800111cf  jz      short loc_180011213
0x1800111d1  test    r14, r14
0x1800111d4  jz      short loc_1800111DA
0x1800111d6  mov     byte ptr [r14], 1
0x1800111da  test    r15, r15
0x1800111dd  jz      loc_180011304
0x1800111e3  mov     rdx, [rbp+var_8]; PCWSTR
0x1800111e7  xor     r8d, r8d; CaseInsensitive
0x1800111ea  mov     rcx, [rbp+ppszPackedCredentialsString]; SourceString
0x1800111ee  call    ?SspiHelperEqualStrings@@YAEPEBG0E@Z; SspiHelperEqualStrings(ushort const *,ushort const *,uchar)
0x1800111f3  test    al, al
0x1800111f5  jnz     short loc_18001120A
0x1800111f7  mov     rdx, r12; void *
0x1800111fa  mov     rcx, r13; void *
0x1800111fd  call    ?SspiHelperEqualPackedCredentials@@YAHPEAX0@Z; SspiHelperEqualPackedCredentials(void *,void *)
0x180011202  test    eax, eax
0x180011204  jz      loc_180011304
0x18001120a  mov     byte ptr [r15], 1
0x18001120e  jmp     loc_180011304
0x180011213  test    r14, r14
0x180011216  jz      loc_180011304
0x18001121c  mov     rcx, [rbp+ppszUserName]; unsigned __int16 *
0x180011220  mov     ebx, 0FFFFFFFDh
0x180011225  test    rcx, rcx
0x180011228  jz      short loc_18001126F
0x18001122a  call    ?LocalCredIsMarshaledCredentialW@@YAHPEBG@Z; LocalCredIsMarshaledCredentialW(ushort const *)
0x18001122f  test    eax, eax
0x180011231  jz      short loc_18001126F
0x180011233  mov     rcx, [rbp+ppszUserName]; unsigned __int16 *
0x180011237  lea     r8, [rbp+DataBuffer]; void **
0x18001123b  lea     rdx, [rbp+arg_0]; enum _CRED_MARSHAL_TYPE *
0x18001123f  call    ?LocalCredUnmarshalCredentialW@@YAKPEBGPEAW4_CRED_MARSHAL_TYPE@@PEAPEAX@Z; LocalCredUnmarshalCredentialW(ushort const *,_CRED_MARSHAL_TYPE *,void * *)
0x180011244  test    eax, eax
0x180011246  jz      short loc_180011256
0x180011248  mov     rsi, [rbp+DataBuffer]
0x18001124c  mov     ebx, 0C000009Ah
0x180011251  jmp     loc_180011306
0x180011256  mov     eax, [rbp+arg_0]
0x180011259  add     eax, 0FFFFFFFEh
0x18001125c  test    ebx, eax
0x18001125e  jz      short loc_18001126B
0x180011260  mov     rcx, [rbp+DataBuffer]; DataBuffer
0x180011264  call    SspiLocalFree
0x180011269  jmp     short loc_18001126F
0x18001126b  mov     rsi, [rbp+DataBuffer]
0x18001126f  mov     rcx, [rbp+arg_18]; unsigned __int16 *
0x180011273  test    rcx, rcx
0x180011276  jz      short loc_1800112BA
0x180011278  call    ?LocalCredIsMarshaledCredentialW@@YAHPEBG@Z; LocalCredIsMarshaledCredentialW(ushort const *)
0x18001127d  test    eax, eax
0x18001127f  jz      short loc_1800112BA
0x180011281  mov     rcx, [rbp+arg_18]; unsigned __int16 *
0x180011285  lea     r8, [rbp+var_28]; void **
0x180011289  lea     rdx, [rbp+arg_0]; enum _CRED_MARSHAL_TYPE *
0x18001128d  call    ?LocalCredUnmarshalCredentialW@@YAKPEBGPEAW4_CRED_MARSHAL_TYPE@@PEAPEAX@Z; LocalCredUnmarshalCredentialW(ushort const *,_CRED_MARSHAL_TYPE *,void * *)
0x180011292  test    eax, eax
0x180011294  jz      short loc_1800112A1
0x180011296  mov     rdi, [rbp+var_28]
0x18001129a  mov     ebx, 0C000009Ah
0x18001129f  jmp     short loc_180011306
0x1800112a1  mov     eax, [rbp+arg_0]
0x1800112a4  add     eax, 0FFFFFFFEh
0x1800112a7  test    ebx, eax
0x1800112a9  jz      short loc_1800112B6
0x1800112ab  mov     rcx, [rbp+var_28]; DataBuffer
0x1800112af  call    SspiLocalFree
0x1800112b4  jmp     short loc_1800112BA
0x1800112b6  mov     rdi, [rbp+var_28]
0x1800112ba  test    rsi, rsi
0x1800112bd  jz      short loc_1800112E1
0x1800112bf  mov     rcx, [rsi]; SourceString
0x1800112c2  test    rdi, rdi
0x1800112c5  jz      short loc_1800112D7
0x1800112c7  mov     rdx, [rdi]; PCWSTR
0x1800112ca  mov     r8b, 1; CaseInsensitive
0x1800112cd  call    ?SspiHelperEqualStrings@@YAEPEBG0E@Z; SspiHelperEqualStrings(ushort const *,ushort const *,uchar)
0x1800112d2  mov     [r14], al
0x1800112d5  jmp     short loc_180011304
0x1800112d7  mov     r8, [rbp+var_18]
0x1800112db  mov     rdx, [rbp+arg_18]
0x1800112df  jmp     short loc_1800112F6
0x1800112e1  test    rdi, rdi
0x1800112e4  jz      short loc_180011304
0x1800112e6  test    rsi, rsi
0x1800112e9  jnz     short loc_180011304
0x1800112eb  mov     r8, [rbp+ppszDomainName]; PCWSTR
0x1800112ef  mov     rdx, [rbp+ppszUserName]; SourceString
0x1800112f3  mov     rcx, [rdi]; PCWSTR
0x1800112f6  mov     r9, r14; unsigned __int8 *
0x1800112f9  call    ?SspiHelperCompareUserNames@@YAJPEBG00PEAE@Z; SspiHelperCompareUserNames(ushort const *,ushort const *,ushort const *,uchar *)
0x1800112fe  mov     ebx, eax
0x180011300  test    eax, eax
0x180011302  js      short loc_180011306
0x180011304  xor     ebx, ebx
0x180011306  mov     rcx, [rbp+ppszUserName]; DataBuffer
0x18001130a  test    rcx, rcx
0x18001130d  jz      short loc_180011314
0x18001130f  call    SspiLocalFree
0x180011314  mov     rcx, [rbp+ppszDomainName]; DataBuffer
0x180011318  test    rcx, rcx
0x18001131b  jz      short loc_180011322
0x18001131d  call    SspiLocalFree
0x180011322  mov     rcx, [rbp+ppszPackedCredentialsString]; DataBuffer
0x180011326  test    rcx, rcx
0x180011329  jz      short loc_180011330
0x18001132b  call    SspiLocalFree
0x180011330  mov     rcx, [rbp+arg_18]; DataBuffer
0x180011334  test    rcx, rcx
0x180011337  jz      short loc_18001133E
0x180011339  call    SspiLocalFree
0x18001133e  mov     rcx, [rbp+var_18]; DataBuffer
0x180011342  test    rcx, rcx
0x180011345  jz      short loc_18001134C
0x180011347  call    SspiLocalFree
0x18001134c  mov     rcx, [rbp+var_8]; DataBuffer
0x180011350  test    rcx, rcx
0x180011353  jz      short loc_18001135A
0x180011355  call    SspiLocalFree
0x18001135a  test    rsi, rsi
0x18001135d  jz      short loc_180011367
0x18001135f  mov     rcx, rsi; DataBuffer
0x180011362  call    SspiLocalFree
0x180011367  test    rdi, rdi
0x18001136a  jz      short loc_180011374
0x18001136c  mov     rcx, rdi; DataBuffer
0x18001136f  call    SspiLocalFree
0x180011374  mov     ecx, ebx
0x180011376  call    SspNtStatusToSecStatus
0x18001137b  mov     rbx, [rsp+50h+arg_8]
0x180011383  add     rsp, 50h
0x180011387  pop     r15
0x180011389  pop     r14
0x18001138b  pop     r13
0x18001138d  pop     r12
0x18001138f  pop     rdi
0x180011390  pop     rsi
0x180011391  pop     rbp
0x180011392  retn
```
