# ConstructSecurityDescriptorInternal(ulong,ulong,ulong,ulong,ulong,_SID * *,ulong *,ulong *,ulong,uchar *,ulong,ulong *)

- ea: `0x180054fcc`
- end: `0x1800552fc`
- name: `?ConstructSecurityDescriptorInternal@@YAJKKKKKPEAPEAU_SID@@PEAK1KPEAEK1@Z`
- size: `816`
- prototype: `signed int __fastcall(__int64, __int64, __int64, __int64, unsigned int, struct _SID **, unsigned int *, unsigned int *, unsigned int, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180054c54`

## callees

- `0x180054fcc`
- `0x180055304`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800550c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055102`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005513e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005517a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800551bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800551f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055233`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005526f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800552c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800550c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055102`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005513e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005517a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800551bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800551f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055233`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005526f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800552c9`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800550f8`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180055134`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180055170`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800551b1`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800551ed`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180055229`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180055265`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800552bb`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800550f8`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180055134`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180055170`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800551b1`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800551ed`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180055229`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180055265`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800552bb`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180055012`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180055012`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800550b6`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800550b6`

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
  DWORD v13; // edx
  DWORD v14; // ecx
  struct _ACL *v15; // rdi
  __int64 i; // rbx
  struct _SID *v17; // r9
  DWORD v18; // r8d

  a12 = 0;
  result = WxGetProcessUserSID((struct _SID **)&a12);
  if ( result < 0 )
  {
    HIDWORD(a12) = 1240;
    return result;
  }
  v13 = GetLengthSid(a12) + 148;
  if ( a6 && a8 && *a6 && *a8 )
    v13 += *a7 + 8;
  v14 = v13 + 8;
  if ( !v13 )
    v14 = 0;
  if ( v14 + 20 > 0x190 )
  {
    result = -2147024809;
    HIDWORD(a12) = 1301;
    return result;
  }
  result = 0;
  *(_OWORD *)a10 = 0;
  *((_DWORD *)a10 + 4) = 0;
  *a10 = 1;
  *((_WORD *)a10 + 1) = 0x8000;
  if ( v14 )
  {
    *((_WORD *)a10 + 1) |= 4u;
    v15 = (struct _ACL *)(a10 + 20);
    *((_DWORD *)a10 + 4) = 20;
    if ( !InitializeAcl((PACL)(a10 + 20), v14, 2u) )
    {
      result = GetLastError();
      if ( result > 0 )
        result = (unsigned __int16)result | 0x80070000;
      HIDWORD(a12) = 1338;
LABEL_56:
      if ( result >= 0 )
        return -2147418113;
      return result;
    }
    if ( !AddAccessAllowedAce(v15, 2u, 0x10000000u, a12) )
    {
      result = GetLastError();
      if ( result > 0 )
        result = (unsigned __int16)result | 0x80070000;
      HIDWORD(a12) = 1342;
      goto LABEL_56;
    }
    if ( !AddAccessAllowedAce(v15, 2u, 0x10000000u, c_rgbBuiltinAdministratorsSid) )
    {
      result = GetLastError();
      if ( result > 0 )
        result = (unsigned __int16)result | 0x80070000;
      HIDWORD(a12) = 1347;
      goto LABEL_56;
    }
    if ( !AddAccessAllowedAce(v15, 2u, 0x10000000u, &c_rgbLocalSystemSid) )
    {
      result = GetLastError();
      if ( result > 0 )
        result = (unsigned __int16)result | 0x80070000;
      HIDWORD(a12) = 1352;
      goto LABEL_56;
    }
    if ( !AddAccessAllowedAce(v15, 2u, 0x80000000, c_rgbBuiltinAnyPackageSid) )
    {
      result = GetLastError();
      if ( result > 0 )
        result = (unsigned __int16)result | 0x80070000;
      HIDWORD(a12) = 1357;
      goto LABEL_56;
    }
    if ( !AddAccessAllowedAce(v15, 2u, 0x80000000, c_rgbCapabilityInternetClientSid) )
    {
      result = GetLastError();
      if ( result > 0 )
        result = (unsigned __int16)result | 0x80070000;
      HIDWORD(a12) = 1358;
      goto LABEL_56;
    }
    if ( !AddAccessAllowedAce(v15, 2u, 0x80000000, c_rgbCapabilityInternetClientServerSid) )
    {
      result = GetLastError();
      if ( result > 0 )
        result = (unsigned __int16)result | 0x80070000;
      HIDWORD(a12) = 1359;
      goto LABEL_56;
    }
    if ( !AddAccessAllowedAce(v15, 2u, 0x80000000, c_rgbCapabilityPrivateNetworkClientServerSid) )
    {
      result = GetLastError();
      if ( result > 0 )
        result = (unsigned __int16)result | 0x80070000;
      HIDWORD(a12) = 1360;
      goto LABEL_56;
    }
    result = 0;
    if ( a6 && a8 )
    {
      for ( i = 0; ; i = 1 )
      {
        result = 0;
        if ( (_DWORD)i )
          break;
        v17 = a6[i];
        if ( v17 )
        {
          v18 = a8[i];
          if ( v18 )
          {
            if ( !AddAccessAllowedAce(v15, 2u, v18, v17) )
            {
              result = GetLastError();
              if ( result > 0 )
                result = (unsigned __int16)result | 0x80070000;
              HIDWORD(a12) = 1371;
              goto LABEL_56;
            }
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
0x180054fcc  mov     rax, rsp
0x180054fcf  push    rbx
0x180054fd0  push    rsi
0x180054fd1  push    rdi
0x180054fd2  push    r14
0x180054fd4  push    r15
0x180054fd6  sub     rsp, 20h
0x180054fda  mov     [rsp+48h+arg_5C], 0
0x180054fe5  lea     rcx, [rax+60h]; struct _SID **
0x180054fe9  mov     qword ptr [rax+60h], 0
0x180054ff1  call    ?WxGetProcessUserSID@@YAJPEAPEAU_SID@@@Z; WxGetProcessUserSID(_SID * *)
0x180054ff6  test    eax, eax
0x180054ff8  jns     short loc_18005500A
0x180054ffa  mov     [rsp+48h+arg_5C], 4D8h
0x180055005  jmp     loc_1800552F0
0x18005500a  mov     rcx, [rsp+0A8h]; pSid
0x180055012  call    cs:__imp_GetLengthSid
0x180055018  mov     r14, [rsp+48h+arg_28]
0x18005501d  mov     rsi, [rsp+48h+arg_38]
0x180055025  lea     edx, [rax+94h]
0x18005502b  test    r14, r14
0x18005502e  jz      short loc_18005504F
0x180055030  test    rsi, rsi
0x180055033  jz      short loc_18005504F
0x180055035  cmp     qword ptr [r14], 0
0x180055039  jz      short loc_18005504F
0x18005503b  cmp     dword ptr [rsi], 0
0x18005503e  jz      short loc_18005504F
0x180055040  mov     rax, [rsp+48h+arg_30]
0x180055048  mov     ecx, [rax]
0x18005504a  add     ecx, 8
0x18005504d  add     edx, ecx
0x18005504f  test    edx, edx
0x180055051  lea     ecx, [rdx+8]
0x180055054  cmovz   ecx, edx
0x180055057  lea     eax, [rcx+14h]
0x18005505a  cmp     eax, 190h
0x18005505f  jbe     short loc_180055076
0x180055061  mov     eax, 80070057h
0x180055066  mov     [rsp+48h+arg_5C], 515h
0x180055071  jmp     loc_1800552F0
0x180055076  mov     rdx, [rsp+48h+arg_48]
0x18005507e  xor     eax, eax
0x180055080  xorps   xmm0, xmm0
0x180055083  movups  xmmword ptr [rdx], xmm0
0x180055086  mov     [rdx+10h], eax
0x180055089  mov     byte ptr [rdx], 1
0x18005508c  mov     word ptr [rdx+2], 8000h
0x180055092  test    ecx, ecx
0x180055094  jz      loc_1800552F0
0x18005509a  or      word ptr [rdx+2], 4
0x18005509f  lea     rdi, [rdx+14h]
0x1800550a3  mov     dword ptr [rdx+10h], 14h
0x1800550aa  lea     r15d, [rax+2]
0x1800550ae  mov     edx, ecx; nAclLength
0x1800550b0  mov     r8d, r15d; dwAclRevision
0x1800550b3  mov     rcx, rdi; pAcl
0x1800550b6  call    cs:__imp_InitializeAcl
0x1800550bc  test    eax, eax
0x1800550be  jnz     short loc_1800550E2
0x1800550c0  call    cs:__imp_GetLastError
0x1800550c6  test    eax, eax
0x1800550c8  jle     short loc_1800550D2
0x1800550ca  movzx   eax, ax
0x1800550cd  or      eax, 80070000h
0x1800550d2  mov     [rsp+48h+arg_5C], 53Ah
0x1800550dd  jmp     loc_1800552E6
0x1800550e2  mov     r9, [rsp+0A8h]; pSid
0x1800550ea  mov     ebx, 10000000h
0x1800550ef  mov     r8d, ebx; AccessMask
0x1800550f2  mov     edx, r15d; dwAceRevision
0x1800550f5  mov     rcx, rdi; pAcl
0x1800550f8  call    cs:__imp_AddAccessAllowedAce
0x1800550fe  test    eax, eax
0x180055100  jnz     short loc_180055124
0x180055102  call    cs:__imp_GetLastError
0x180055108  test    eax, eax
0x18005510a  jle     short loc_180055114
0x18005510c  movzx   eax, ax
0x18005510f  or      eax, 80070000h
0x180055114  mov     [rsp+48h+arg_5C], 53Eh
0x18005511f  jmp     loc_1800552E6
0x180055124  lea     r9, c_rgbBuiltinAdministratorsSid; pSid
0x18005512b  mov     r8d, ebx; AccessMask
0x18005512e  mov     edx, r15d; dwAceRevision
0x180055131  mov     rcx, rdi; pAcl
0x180055134  call    cs:__imp_AddAccessAllowedAce
0x18005513a  test    eax, eax
0x18005513c  jnz     short loc_180055160
0x18005513e  call    cs:__imp_GetLastError
0x180055144  test    eax, eax
0x180055146  jle     short loc_180055150
0x180055148  movzx   eax, ax
0x18005514b  or      eax, 80070000h
0x180055150  mov     [rsp+48h+arg_5C], 543h
0x18005515b  jmp     loc_1800552E6
0x180055160  lea     r9, c_rgbLocalSystemSid; pSid
0x180055167  mov     r8d, ebx; AccessMask
0x18005516a  mov     edx, r15d; dwAceRevision
0x18005516d  mov     rcx, rdi; pAcl
0x180055170  call    cs:__imp_AddAccessAllowedAce
0x180055176  test    eax, eax
0x180055178  jnz     short loc_18005519C
0x18005517a  call    cs:__imp_GetLastError
0x180055180  test    eax, eax
0x180055182  jle     short loc_18005518C
0x180055184  movzx   eax, ax
0x180055187  or      eax, 80070000h
0x18005518c  mov     [rsp+48h+arg_5C], 548h
0x180055197  jmp     loc_1800552E6
0x18005519c  mov     ebx, 80000000h
0x1800551a1  lea     r9, c_rgbBuiltinAnyPackageSid; pSid
0x1800551a8  mov     r8d, ebx; AccessMask
0x1800551ab  mov     edx, r15d; dwAceRevision
0x1800551ae  mov     rcx, rdi; pAcl
0x1800551b1  call    cs:__imp_AddAccessAllowedAce
0x1800551b7  test    eax, eax
0x1800551b9  jnz     short loc_1800551DD
0x1800551bb  call    cs:__imp_GetLastError
0x1800551c1  test    eax, eax
0x1800551c3  jle     short loc_1800551CD
0x1800551c5  movzx   eax, ax
0x1800551c8  or      eax, 80070000h
0x1800551cd  mov     [rsp+48h+arg_5C], 54Dh
0x1800551d8  jmp     loc_1800552E6
0x1800551dd  lea     r9, c_rgbCapabilityInternetClientSid; pSid
0x1800551e4  mov     r8d, ebx; AccessMask
0x1800551e7  mov     edx, r15d; dwAceRevision
0x1800551ea  mov     rcx, rdi; pAcl
0x1800551ed  call    cs:__imp_AddAccessAllowedAce
0x1800551f3  test    eax, eax
0x1800551f5  jnz     short loc_180055219
0x1800551f7  call    cs:__imp_GetLastError
0x1800551fd  test    eax, eax
0x1800551ff  jle     short loc_180055209
0x180055201  movzx   eax, ax
0x180055204  or      eax, 80070000h
0x180055209  mov     [rsp+48h+arg_5C], 54Eh
0x180055214  jmp     loc_1800552E6
0x180055219  lea     r9, c_rgbCapabilityInternetClientServerSid; pSid
0x180055220  mov     r8d, ebx; AccessMask
0x180055223  mov     edx, r15d; dwAceRevision
0x180055226  mov     rcx, rdi; pAcl
0x180055229  call    cs:__imp_AddAccessAllowedAce
0x18005522f  test    eax, eax
0x180055231  jnz     short loc_180055255
0x180055233  call    cs:__imp_GetLastError
0x180055239  test    eax, eax
0x18005523b  jle     short loc_180055245
0x18005523d  movzx   eax, ax
0x180055240  or      eax, 80070000h
0x180055245  mov     [rsp+48h+arg_5C], 54Fh
0x180055250  jmp     loc_1800552E6
0x180055255  lea     r9, c_rgbCapabilityPrivateNetworkClientServerSid; pSid
0x18005525c  mov     r8d, ebx; AccessMask
0x18005525f  mov     edx, r15d; dwAceRevision
0x180055262  mov     rcx, rdi; pAcl
0x180055265  call    cs:__imp_AddAccessAllowedAce
0x18005526b  test    eax, eax
0x18005526d  jnz     short loc_18005528E
0x18005526f  call    cs:__imp_GetLastError
0x180055275  test    eax, eax
0x180055277  jle     short loc_180055281
0x180055279  movzx   eax, ax
0x18005527c  or      eax, 80070000h
0x180055281  mov     [rsp+48h+arg_5C], 550h
0x18005528c  jmp     short loc_1800552E6
0x18005528e  xor     eax, eax
0x180055290  test    r14, r14
0x180055293  jz      short loc_1800552F0
0x180055295  test    rsi, rsi
0x180055298  jz      short loc_1800552F0
0x18005529a  xor     ebx, ebx
0x18005529c  xor     eax, eax
0x18005529e  cmp     ebx, 1
0x1800552a1  jnb     short loc_1800552F0
0x1800552a3  mov     r9, [r14+rbx*8]; pSid
0x1800552a7  test    r9, r9
0x1800552aa  jz      short loc_1800552C5
0x1800552ac  mov     r8d, [rsi+rbx*4]; AccessMask
0x1800552b0  test    r8d, r8d
0x1800552b3  jz      short loc_1800552C5
0x1800552b5  mov     edx, r15d; dwAceRevision
0x1800552b8  mov     rcx, rdi; pAcl
0x1800552bb  call    cs:__imp_AddAccessAllowedAce
0x1800552c1  test    eax, eax
0x1800552c3  jz      short loc_1800552C9
0x1800552c5  inc     ebx
0x1800552c7  jmp     short loc_18005529C
0x1800552c9  call    cs:__imp_GetLastError
0x1800552cf  test    eax, eax
0x1800552d1  jle     short loc_1800552DB
0x1800552d3  movzx   eax, ax
0x1800552d6  or      eax, 80070000h
0x1800552db  mov     [rsp+48h+arg_5C], 55Bh
0x1800552e6  test    eax, eax
0x1800552e8  mov     ecx, 8000FFFFh
0x1800552ed  cmovns  eax, ecx
0x1800552f0  add     rsp, 20h
0x1800552f4  pop     r15
0x1800552f6  pop     r14
0x1800552f8  pop     rdi
0x1800552f9  pop     rsi
0x1800552fa  pop     rbx
0x1800552fb  retn
```
