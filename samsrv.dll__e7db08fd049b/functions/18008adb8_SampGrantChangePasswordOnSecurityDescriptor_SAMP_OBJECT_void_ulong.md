# SampGrantChangePasswordOnSecurityDescriptor(_SAMP_OBJECT *,void * *,ulong *)

- ea: `0x18008adb8`
- end: `0x18008af74`
- name: `?SampGrantChangePasswordOnSecurityDescriptor@@YAJPEAU_SAMP_OBJECT@@PEAPEAXPEAK@Z`
- size: `444`
- prototype: `__int64 __fastcall(struct _SAMP_OBJECT *, void **, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18008acf0`
- `0x18009f2a4`

## callees

- `0x180027e24`
- `0x18002cd80`
- `0x18005645c`
- `0x18008adb8`

## import_xrefs

- `ntdll!RtlQueryInformationAcl` at `0x18008ae87`
- `ntdll!RtlQueryInformationAcl` at `0x18008ae87`
- `ntdll!RtlGetAce` at `0x18008aed6`
- `ntdll!RtlGetAce` at `0x18008aed6`
- `ntdll!RtlEqualSid` at `0x18008aef6`
- `ntdll!RtlEqualSid` at `0x18008af0c`
- `ntdll!RtlEqualSid` at `0x18008aef6`
- `ntdll!RtlEqualSid` at `0x18008af0c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18008ae60`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18008ae60`

## pseudocode

```c
__int64 __fastcall SampGrantChangePasswordOnSecurityDescriptor(struct _SAMP_OBJECT *a1, void **a2, unsigned int *a3)
{
  bool v4; // zf
  int v6; // ebx
  ULONG i; // edi
  PVOID Ace; // [rsp+30h] [rbp-50h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+38h] [rbp-48h] BYREF
  WINBOOL bDaclPresent; // [rsp+3Ch] [rbp-44h] BYREF
  PACL pDacl; // [rsp+40h] [rbp-40h] BYREF
  __int64 Information; // [rsp+48h] [rbp-38h] BYREF
  int v13; // [rsp+50h] [rbp-30h]
  _OWORD Sid1[2]; // [rsp+58h] [rbp-28h] BYREF

  bDaclPresent = 0;
  bDaclDefaulted = 0;
  pDacl = 0;
  memset(Sid1, 0, 28);
  v4 = (*((_BYTE *)a1 + 192) & 2) == 0;
  Information = 0;
  v13 = 0;
  Ace = 0;
  if ( v4 )
  {
    v6 = 0;
    if ( GetSecurityDescriptorDacl(*a2, &bDaclPresent, &pDacl, &bDaclDefaulted) )
    {
      if ( pDacl )
      {
        v6 = RtlQueryInformationAcl(pDacl, &Information, 0xCu, AclSizeInformation);
        if ( v6 >= 0 )
        {
          v6 = SampBuildNT4FullSid(
                 *((void **)SampDefinedDomains + 170 * *((unsigned int *)a1 + 50) + 1),
                 *((_DWORD *)a1 + 62),
                 Sid1);
          if ( v6 >= 0 )
          {
            for ( i = 0; i < (unsigned int)Information; ++i )
            {
              v6 = RtlGetAce(pDacl, i, &Ace);
              if ( v6 < 0 )
                break;
              if ( !*(_BYTE *)Ace && (RtlEqualSid(SampWorldSid, (char *)Ace + 8) || RtlEqualSid(Sid1, (char *)Ace + 8)) )
                *((_DWORD *)Ace + 1) |= 0x40u;
            }
          }
        }
      }
    }
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 80, WPP_18fb10c206133c98d7a2b000be93359d_Traceguids, (unsigned int)v6, v6);
    return (unsigned int)v6;
  }
  else
  {
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 79, WPP_18fb10c206133c98d7a2b000be93359d_Traceguids, 0, 0);
    return 0;
  }
}

```

## disassembly

```asm
0x18008adb8  mov     [rsp-8+arg_10], rbx
0x18008adbd  mov     [rsp-8+arg_18], rdi
0x18008adc2  push    rbp
0x18008adc3  mov     rbp, rsp
0x18008adc6  sub     rsp, 80h
0x18008adcd  mov     rax, cs:__security_cookie
0x18008add4  xor     rax, rsp
0x18008add7  mov     [rbp+var_8], rax
0x18008addb  mov     rdi, rcx
0x18008adde  mov     [rbp+bDaclPresent], 0
0x18008ade5  xor     ecx, ecx
0x18008ade7  mov     [rbp+bDaclDefaulted], 0
0x18008adee  xorps   xmm0, xmm0
0x18008adf1  mov     [rbp+pDacl], 0
0x18008adf9  movups  [rbp+Sid1], xmm0
0x18008adfd  test    byte ptr [rdi+0C0h], 2
0x18008ae04  mov     rax, rdx
0x18008ae07  mov     [rbp+Information], rcx
0x18008ae0b  mov     [rbp+var_30], ecx
0x18008ae0e  mov     [rbp+Ace], rcx
0x18008ae12  movups  [rbp+Sid1+0Ch], xmm0
0x18008ae16  jz      short loc_18008AE4F
0x18008ae18  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ae1f  test    dword ptr [rcx+44h], 20000h
0x18008ae26  jz      short loc_18008AE48
0x18008ae28  mov     rcx, [rcx+38h]
0x18008ae2c  lea     r8, WPP_18fb10c206133c98d7a2b000be93359d_Traceguids
0x18008ae33  mov     edx, 4Fh ; 'O'
0x18008ae38  mov     [rsp+80h+var_60], 0
0x18008ae40  xor     r9d, r9d
0x18008ae43  call    WPP_SF_Dd
0x18008ae48  xor     eax, eax
0x18008ae4a  jmp     loc_18008AF53
0x18008ae4f  mov     rcx, [rax]; pSecurityDescriptor
0x18008ae52  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x18008ae56  lea     r8, [rbp+pDacl]; pDacl
0x18008ae5a  xor     ebx, ebx
0x18008ae5c  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x18008ae60  call    cs:__imp_GetSecurityDescriptorDacl
0x18008ae66  test    eax, eax
0x18008ae68  jz      loc_18008AF25
0x18008ae6e  mov     rcx, [rbp+pDacl]; Acl
0x18008ae72  test    rcx, rcx
0x18008ae75  jz      loc_18008AF25
0x18008ae7b  lea     r9d, [rbx+2]; InformationClass
0x18008ae7f  lea     r8d, [rbx+0Ch]; InformationLength
0x18008ae83  lea     rdx, [rbp+Information]; Information
0x18008ae87  call    cs:__imp_RtlQueryInformationAcl
0x18008ae8d  mov     ebx, eax
0x18008ae8f  test    eax, eax
0x18008ae91  js      loc_18008AF25
0x18008ae97  mov     eax, [rdi+0C8h]
0x18008ae9d  lea     r8, [rbp+Sid1]
0x18008aea1  mov     rcx, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x18008aea8  mov     edx, [rdi+0F8h]
0x18008aeae  imul    r9, rax, 550h
0x18008aeb5  mov     rcx, [r9+rcx+8]; Src
0x18008aeba  call    SampBuildNT4FullSid
0x18008aebf  mov     ebx, eax
0x18008aec1  test    eax, eax
0x18008aec3  js      short loc_18008AF25
0x18008aec5  xor     edi, edi
0x18008aec7  cmp     dword ptr [rbp+Information], edi
0x18008aeca  jbe     short loc_18008AF25
0x18008aecc  mov     rcx, [rbp+pDacl]; Acl
0x18008aed0  lea     r8, [rbp+Ace]; Ace
0x18008aed4  mov     edx, edi; AceIndex
0x18008aed6  call    cs:__imp_RtlGetAce
0x18008aedc  mov     ebx, eax
0x18008aede  test    eax, eax
0x18008aee0  js      short loc_18008AF25
0x18008aee2  mov     rdx, [rbp+Ace]
0x18008aee6  cmp     byte ptr [rdx], 0
0x18008aee9  jnz     short loc_18008AF1E
0x18008aeeb  mov     rcx, cs:SampWorldSid; Sid1
0x18008aef2  add     rdx, 8; Sid2
0x18008aef6  call    cs:__imp_RtlEqualSid
0x18008aefc  test    al, al
0x18008aefe  jnz     short loc_18008AF16
0x18008af00  mov     rdx, [rbp+Ace]
0x18008af04  lea     rcx, [rbp+Sid1]; Sid1
0x18008af08  add     rdx, 8; Sid2
0x18008af0c  call    cs:__imp_RtlEqualSid
0x18008af12  test    al, al
0x18008af14  jz      short loc_18008AF1E
0x18008af16  mov     rax, [rbp+Ace]
0x18008af1a  or      dword ptr [rax+4], 40h
0x18008af1e  inc     edi
0x18008af20  cmp     edi, dword ptr [rbp+Information]
0x18008af23  jb      short loc_18008AECC
0x18008af25  mov     rcx, cs:WPP_GLOBAL_Control
0x18008af2c  test    dword ptr [rcx+44h], 20000h
0x18008af33  jz      short loc_18008AF51
0x18008af35  mov     rcx, [rcx+38h]
0x18008af39  lea     r8, WPP_18fb10c206133c98d7a2b000be93359d_Traceguids
0x18008af40  mov     edx, 50h ; 'P'
0x18008af45  mov     [rsp+80h+var_60], ebx
0x18008af49  mov     r9d, ebx
0x18008af4c  call    WPP_SF_Dd
0x18008af51  mov     eax, ebx
0x18008af53  mov     rcx, [rbp+var_8]
0x18008af57  xor     rcx, rsp; StackCookie
0x18008af5a  call    __security_check_cookie
0x18008af5f  lea     r11, [rsp+80h+var_s0]
0x18008af67  mov     rbx, [r11+20h]
0x18008af6b  mov     rdi, [r11+28h]
0x18008af6f  mov     rsp, r11
0x18008af72  pop     rbp
0x18008af73  retn
```
