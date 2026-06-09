# ConstructSecurityDescriptorInternal(ulong,ulong,ulong,ulong,ulong,_SID * *,ulong *,ulong *,ulong,uchar *,ulong,ulong *)

- ea: `0x1800995e8`
- end: `0x1800999c0`
- name: `?ConstructSecurityDescriptorInternal@@YAJKKKKKPEAPEAU_SID@@PEAK1KPEAEK1@Z`
- size: `984`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, struct _SID **, unsigned int *, unsigned int *, unsigned int, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18006b444`

## callees

- `0x180076070`
- `0x1800995e8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180099641`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180099641`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800996e1`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180099777`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800996e1`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180099777`
- `api-ms-win-security-base-l1-1-0!AddMandatoryAce` at `0x180099729`
- `api-ms-win-security-base-l1-1-0!AddMandatoryAce` at `0x180099729`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800997b9`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800997f5`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180099831`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180099872`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800998ae`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800998ea`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180099926`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18009997c`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800997b9`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800997f5`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180099831`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180099872`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800998ae`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800998ea`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180099926`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18009997c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800996eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099733`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099781`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800997c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800997ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009983b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009987c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800998b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800998f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099930`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009998a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800996eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099733`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099781`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800997c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800997ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009983b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009987c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800998b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800998f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099930`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009998a`

## pseudocode

```c
signed int __fastcall ConstructSecurityDescriptorInternal(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        struct _SID **a6,
        unsigned int *a7,
        unsigned int *a8,
        unsigned int a9,
        unsigned __int8 *a10,
        unsigned int a11,
        unsigned int *a12)
{
  signed int result; // eax
  DWORD v13; // ecx
  __int64 i; // rdx
  DWORD v15; // edi
  struct _ACL *v16; // rbx
  __int64 j; // rdi
  struct _SID *v18; // r9
  DWORD v19; // r8d

  a12 = 0;
  result = WxGetProcessUserSID((struct _SID **)&a12);
  if ( result < 0 )
  {
    HIDWORD(a12) = 1240;
    return result;
  }
  v13 = GetLengthSid(a12) + 148;
  if ( a6 && a8 )
  {
    for ( i = 0; i != 4; ++i )
    {
      if ( a6[i] && a8[i] )
        v13 += a7[i] + 8;
    }
  }
  v15 = v13 + 8;
  if ( !v13 )
    v15 = 0;
  if ( v15 + 48 > 0x228 )
  {
    result = -2147024809;
    HIDWORD(a12) = 1301;
    return result;
  }
  *(_OWORD *)a10 = 0;
  *((_WORD *)a10 + 1) = 0x8000;
  *((_WORD *)a10 + 1) = -32752;
  *(_QWORD *)(a10 + 12) = 20;
  *a10 = 1;
  if ( !InitializeAcl((PACL)(a10 + 20), 0x1Cu, 2u) )
  {
    result = GetLastError();
    if ( result > 0 )
      result = (unsigned __int16)result | 0x80070000;
    HIDWORD(a12) = 1321;
LABEL_66:
    if ( result >= 0 )
      return -2147418113;
    return result;
  }
  if ( !AddMandatoryAce((PACL)(a10 + 20), 2u, 0, 1u, c_rgbLowLabelSid) )
  {
    result = GetLastError();
    if ( result > 0 )
      result = (unsigned __int16)result | 0x80070000;
    HIDWORD(a12) = 1325;
    goto LABEL_66;
  }
  result = 0;
  if ( !v15 )
    return result;
  *((_WORD *)a10 + 1) |= 4u;
  *((_DWORD *)a10 + 4) = 48;
  v16 = (struct _ACL *)(a10 + 48);
  if ( !InitializeAcl((PACL)a10 + 6, v15, 2u) )
  {
    result = GetLastError();
    if ( result > 0 )
      result = (unsigned __int16)result | 0x80070000;
    HIDWORD(a12) = 1338;
    goto LABEL_66;
  }
  if ( !AddAccessAllowedAce(v16, 2u, 0x10000000u, a12) )
  {
    result = GetLastError();
    if ( result > 0 )
      result = (unsigned __int16)result | 0x80070000;
    HIDWORD(a12) = 1342;
    goto LABEL_66;
  }
  if ( !AddAccessAllowedAce(v16, 2u, 0x10000000u, c_rgbBuiltinAdministratorsSid) )
  {
    result = GetLastError();
    if ( result > 0 )
      result = (unsigned __int16)result | 0x80070000;
    HIDWORD(a12) = 1347;
    goto LABEL_66;
  }
  if ( !AddAccessAllowedAce(v16, 2u, 0x10000000u, c_rgbLocalSystemSid) )
  {
    result = GetLastError();
    if ( result > 0 )
      result = (unsigned __int16)result | 0x80070000;
    HIDWORD(a12) = 1352;
    goto LABEL_66;
  }
  if ( !AddAccessAllowedAce(v16, 2u, 0xA0100000, c_rgbBuiltinAnyPackageSid) )
  {
    result = GetLastError();
    if ( result > 0 )
      result = (unsigned __int16)result | 0x80070000;
    HIDWORD(a12) = 1357;
    goto LABEL_66;
  }
  if ( !AddAccessAllowedAce(v16, 2u, 0xA0100000, c_rgbCapabilityInternetClientSid) )
  {
    result = GetLastError();
    if ( result > 0 )
      result = (unsigned __int16)result | 0x80070000;
    HIDWORD(a12) = 1358;
    goto LABEL_66;
  }
  if ( !AddAccessAllowedAce(v16, 2u, 0xA0100000, c_rgbCapabilityInternetClientServerSid) )
  {
    result = GetLastError();
    if ( result > 0 )
      result = (unsigned __int16)result | 0x80070000;
    HIDWORD(a12) = 1359;
    goto LABEL_66;
  }
  if ( !AddAccessAllowedAce(v16, 2u, 0xA0100000, c_rgbCapabilityPrivateNetworkClientServerSid) )
  {
    result = GetLastError();
    if ( result > 0 )
      result = (unsigned __int16)result | 0x80070000;
    HIDWORD(a12) = 1360;
    goto LABEL_66;
  }
  result = 0;
  if ( a6 && a8 )
  {
    for ( j = 0; ; j = (unsigned int)(j + 1) )
    {
      result = 0;
      if ( (unsigned int)j >= 4 )
        break;
      v18 = a6[j];
      if ( v18 )
      {
        v19 = a8[j];
        if ( v19 )
        {
          if ( !AddAccessAllowedAce(v16, 2u, v19, v18) )
          {
            result = GetLastError();
            if ( result > 0 )
              result = (unsigned __int16)result | 0x80070000;
            HIDWORD(a12) = 1371;
            goto LABEL_66;
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800995e8  mov     rax, rsp
0x1800995eb  push    rbx
0x1800995ec  push    rbp
0x1800995ed  push    rsi
0x1800995ee  push    rdi
0x1800995ef  push    r12
0x1800995f1  push    r13
0x1800995f3  push    r14
0x1800995f5  sub     rsp, 30h
0x1800995f9  mov     [rsp+68h+arg_5C], 0
0x180099604  lea     rcx, [rax+60h]; struct _SID **
0x180099608  mov     qword ptr [rax+60h], 0
0x180099610  call    ?WxGetProcessUserSID@@YAJPEAPEAU_SID@@@Z; WxGetProcessUserSID(_SID * *)
0x180099615  test    eax, eax
0x180099617  jns     short loc_180099629
0x180099619  mov     [rsp+68h+arg_5C], 4D8h
0x180099624  jmp     loc_1800999B1
0x180099629  mov     rcx, [rsp+0C8h]; pSid
0x180099631  mov     rsi, [rsp+68h+arg_38]
0x180099639  mov     r14, [rsp+68h+arg_28]
0x180099641  call    cs:__imp_GetLengthSid
0x180099647  mov     r13d, 4
0x18009964d  lea     ecx, [rax+94h]
0x180099653  test    r14, r14
0x180099656  jz      short loc_180099683
0x180099658  test    rsi, rsi
0x18009965b  jz      short loc_180099683
0x18009965d  mov     r8, [rsp+68h+arg_30]
0x180099665  xor     edx, edx
0x180099667  cmp     qword ptr [r14+rdx*8], 0
0x18009966c  jz      short loc_18009967B
0x18009966e  cmp     dword ptr [rsi+rdx*4], 0
0x180099672  jz      short loc_18009967B
0x180099674  add     ecx, 8
0x180099677  add     ecx, [r8+rdx*4]
0x18009967b  inc     rdx
0x18009967e  cmp     rdx, r13
0x180099681  jnz     short loc_180099667
0x180099683  test    ecx, ecx
0x180099685  lea     edi, [rcx+8]
0x180099688  cmovz   edi, ecx
0x18009968b  lea     eax, [rdi+30h]
0x18009968e  cmp     eax, 228h
0x180099693  jbe     short loc_1800996AA
0x180099695  mov     eax, 80070057h
0x18009969a  mov     [rsp+68h+arg_5C], 515h
0x1800996a5  jmp     loc_1800999B1
0x1800996aa  mov     rbx, [rsp+68h+arg_48]
0x1800996b2  mov     r12d, 2
0x1800996b8  xorps   xmm0, xmm0
0x1800996bb  mov     r8d, r12d; dwAclRevision
0x1800996be  movups  xmmword ptr [rbx], xmm0
0x1800996c1  mov     word ptr [rbx+2], 8000h
0x1800996c7  lea     edx, [r12+1Ah]; nAclLength
0x1800996cc  lea     rcx, [rbx+14h]; pAcl
0x1800996d0  mov     word ptr [rbx+2], 8010h
0x1800996d6  mov     qword ptr [rbx+0Ch], 14h
0x1800996de  mov     byte ptr [rbx], 1
0x1800996e1  call    cs:__imp_InitializeAcl
0x1800996e7  test    eax, eax
0x1800996e9  jnz     short loc_18009970D
0x1800996eb  call    cs:__imp_GetLastError
0x1800996f1  test    eax, eax
0x1800996f3  jle     short loc_1800996FD
0x1800996f5  movzx   eax, ax
0x1800996f8  or      eax, 80070000h
0x1800996fd  mov     [rsp+68h+arg_5C], 529h
0x180099708  jmp     loc_1800999A7
0x18009970d  lea     rax, c_rgbLowLabelSid
0x180099714  mov     r9d, 1; MandatoryPolicy
0x18009971a  xor     r8d, r8d; AceFlags
0x18009971d  mov     [rsp+68h+pLabelSid], rax; pLabelSid
0x180099722  mov     edx, r12d; dwAceRevision
0x180099725  lea     rcx, [rbx+14h]; pAcl
0x180099729  call    cs:__imp_AddMandatoryAce
0x18009972f  test    eax, eax
0x180099731  jnz     short loc_180099755
0x180099733  call    cs:__imp_GetLastError
0x180099739  test    eax, eax
0x18009973b  jle     short loc_180099745
0x18009973d  movzx   eax, ax
0x180099740  or      eax, 80070000h
0x180099745  mov     [rsp+68h+arg_5C], 52Dh
0x180099750  jmp     loc_1800999A7
0x180099755  xor     eax, eax
0x180099757  test    edi, edi
0x180099759  jz      loc_1800999B1
0x18009975f  or      [rbx+2], r13w
0x180099764  mov     r8d, r12d; dwAclRevision
0x180099767  mov     dword ptr [rbx+10h], 30h ; '0'
0x18009976e  mov     edx, edi; nAclLength
0x180099770  add     rbx, 30h ; '0'
0x180099774  mov     rcx, rbx; pAcl
0x180099777  call    cs:__imp_InitializeAcl
0x18009977d  test    eax, eax
0x18009977f  jnz     short loc_1800997A3
0x180099781  call    cs:__imp_GetLastError
0x180099787  test    eax, eax
0x180099789  jle     short loc_180099793
0x18009978b  movzx   eax, ax
0x18009978e  or      eax, 80070000h
0x180099793  mov     [rsp+68h+arg_5C], 53Ah
0x18009979e  jmp     loc_1800999A7
0x1800997a3  mov     r9, [rsp+0C8h]; pSid
0x1800997ab  mov     edi, 10000000h
0x1800997b0  mov     r8d, edi; AccessMask
0x1800997b3  mov     edx, r12d; dwAceRevision
0x1800997b6  mov     rcx, rbx; pAcl
0x1800997b9  call    cs:__imp_AddAccessAllowedAce
0x1800997bf  test    eax, eax
0x1800997c1  jnz     short loc_1800997E5
0x1800997c3  call    cs:__imp_GetLastError
0x1800997c9  test    eax, eax
0x1800997cb  jle     short loc_1800997D5
0x1800997cd  movzx   eax, ax
0x1800997d0  or      eax, 80070000h
0x1800997d5  mov     [rsp+68h+arg_5C], 53Eh
0x1800997e0  jmp     loc_1800999A7
0x1800997e5  lea     r9, c_rgbBuiltinAdministratorsSid; pSid
0x1800997ec  mov     r8d, edi; AccessMask
0x1800997ef  mov     edx, r12d; dwAceRevision
0x1800997f2  mov     rcx, rbx; pAcl
0x1800997f5  call    cs:__imp_AddAccessAllowedAce
0x1800997fb  test    eax, eax
0x1800997fd  jnz     short loc_180099821
0x1800997ff  call    cs:__imp_GetLastError
0x180099805  test    eax, eax
0x180099807  jle     short loc_180099811
0x180099809  movzx   eax, ax
0x18009980c  or      eax, 80070000h
0x180099811  mov     [rsp+68h+arg_5C], 543h
0x18009981c  jmp     loc_1800999A7
0x180099821  lea     r9, c_rgbLocalSystemSid; pSid
0x180099828  mov     r8d, edi; AccessMask
0x18009982b  mov     edx, r12d; dwAceRevision
0x18009982e  mov     rcx, rbx; pAcl
0x180099831  call    cs:__imp_AddAccessAllowedAce
0x180099837  test    eax, eax
0x180099839  jnz     short loc_18009985D
0x18009983b  call    cs:__imp_GetLastError
0x180099841  test    eax, eax
0x180099843  jle     short loc_18009984D
0x180099845  movzx   eax, ax
0x180099848  or      eax, 80070000h
0x18009984d  mov     [rsp+68h+arg_5C], 548h
0x180099858  jmp     loc_1800999A7
0x18009985d  mov     edi, 0A0100000h
0x180099862  lea     r9, c_rgbBuiltinAnyPackageSid; pSid
0x180099869  mov     r8d, edi; AccessMask
0x18009986c  mov     edx, r12d; dwAceRevision
0x18009986f  mov     rcx, rbx; pAcl
0x180099872  call    cs:__imp_AddAccessAllowedAce
0x180099878  test    eax, eax
0x18009987a  jnz     short loc_18009989E
0x18009987c  call    cs:__imp_GetLastError
0x180099882  test    eax, eax
0x180099884  jle     short loc_18009988E
0x180099886  movzx   eax, ax
0x180099889  or      eax, 80070000h
0x18009988e  mov     [rsp+68h+arg_5C], 54Dh
0x180099899  jmp     loc_1800999A7
0x18009989e  lea     r9, c_rgbCapabilityInternetClientSid; pSid
0x1800998a5  mov     r8d, edi; AccessMask
0x1800998a8  mov     edx, r12d; dwAceRevision
0x1800998ab  mov     rcx, rbx; pAcl
0x1800998ae  call    cs:__imp_AddAccessAllowedAce
0x1800998b4  test    eax, eax
0x1800998b6  jnz     short loc_1800998DA
0x1800998b8  call    cs:__imp_GetLastError
0x1800998be  test    eax, eax
0x1800998c0  jle     short loc_1800998CA
0x1800998c2  movzx   eax, ax
0x1800998c5  or      eax, 80070000h
0x1800998ca  mov     [rsp+68h+arg_5C], 54Eh
0x1800998d5  jmp     loc_1800999A7
0x1800998da  lea     r9, c_rgbCapabilityInternetClientServerSid; pSid
0x1800998e1  mov     r8d, edi; AccessMask
0x1800998e4  mov     edx, r12d; dwAceRevision
0x1800998e7  mov     rcx, rbx; pAcl
0x1800998ea  call    cs:__imp_AddAccessAllowedAce
0x1800998f0  test    eax, eax
0x1800998f2  jnz     short loc_180099916
0x1800998f4  call    cs:__imp_GetLastError
0x1800998fa  test    eax, eax
0x1800998fc  jle     short loc_180099906
0x1800998fe  movzx   eax, ax
0x180099901  or      eax, 80070000h
0x180099906  mov     [rsp+68h+arg_5C], 54Fh
0x180099911  jmp     loc_1800999A7
0x180099916  lea     r9, c_rgbCapabilityPrivateNetworkClientServerSid; pSid
0x18009991d  mov     r8d, edi; AccessMask
0x180099920  mov     edx, r12d; dwAceRevision
0x180099923  mov     rcx, rbx; pAcl
0x180099926  call    cs:__imp_AddAccessAllowedAce
0x18009992c  test    eax, eax
0x18009992e  jnz     short loc_18009994F
0x180099930  call    cs:__imp_GetLastError
0x180099936  test    eax, eax
0x180099938  jle     short loc_180099942
0x18009993a  movzx   eax, ax
0x18009993d  or      eax, 80070000h
0x180099942  mov     [rsp+68h+arg_5C], 550h
0x18009994d  jmp     short loc_1800999A7
0x18009994f  xor     eax, eax
0x180099951  test    r14, r14
0x180099954  jz      short loc_1800999B1
0x180099956  test    rsi, rsi
0x180099959  jz      short loc_1800999B1
0x18009995b  xor     edi, edi
0x18009995d  xor     eax, eax
0x18009995f  cmp     edi, r13d
0x180099962  jnb     short loc_1800999B1
0x180099964  mov     r9, [r14+rdi*8]; pSid
0x180099968  test    r9, r9
0x18009996b  jz      short loc_180099986
0x18009996d  mov     r8d, [rsi+rdi*4]; AccessMask
0x180099971  test    r8d, r8d
0x180099974  jz      short loc_180099986
0x180099976  mov     edx, r12d; dwAceRevision
0x180099979  mov     rcx, rbx; pAcl
0x18009997c  call    cs:__imp_AddAccessAllowedAce
0x180099982  test    eax, eax
0x180099984  jz      short loc_18009998A
0x180099986  inc     edi
0x180099988  jmp     short loc_18009995D
0x18009998a  call    cs:__imp_GetLastError
0x180099990  test    eax, eax
0x180099992  jle     short loc_18009999C
0x180099994  movzx   eax, ax
0x180099997  or      eax, 80070000h
0x18009999c  mov     [rsp+68h+arg_5C], 55Bh
0x1800999a7  test    eax, eax
0x1800999a9  mov     ecx, 8000FFFFh
0x1800999ae  cmovns  eax, ecx
0x1800999b1  add     rsp, 30h
0x1800999b5  pop     r14
0x1800999b7  pop     r13
0x1800999b9  pop     r12
0x1800999bb  pop     rdi
0x1800999bc  pop     rsi
0x1800999bd  pop     rbp
0x1800999be  pop     rbx
0x1800999bf  retn
```
