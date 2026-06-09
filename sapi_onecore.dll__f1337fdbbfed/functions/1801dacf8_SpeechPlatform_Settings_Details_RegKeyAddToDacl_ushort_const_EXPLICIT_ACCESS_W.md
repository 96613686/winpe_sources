# SpeechPlatform::Settings::Details::RegKeyAddToDacl(ushort const *,_EXPLICIT_ACCESS_W &)

- ea: `0x1801dacf8`
- end: `0x1801dadde`
- name: `?RegKeyAddToDacl@Details@Settings@SpeechPlatform@@YAJPEBGAEAU_EXPLICIT_ACCESS_W@@@Z`
- size: `230`
- prototype: `__int64 __fastcall(LPWSTR pObjectName, PEXPLICIT_ACCESS_W pListOfExplicitEntries, struct _EXPLICIT_ACCESS_W *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1801da6d8`

## callees

- `0x1801dacf8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801dadae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801dadb9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801dadae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801dadb9`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1801dada1`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1801dada1`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1801dad6d`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1801dad6d`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x1801dad48`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x1801dad48`

## pseudocode

```c
__int64 __fastcall SpeechPlatform::Settings::Details::RegKeyAddToDacl(
        LPWSTR pObjectName,
        PEXPLICIT_ACCESS_W pListOfExplicitEntries,
        struct _EXPLICIT_ACCESS_W *a3)
{
  signed int NamedSecurityInfoW; // ebx
  HLOCAL hMem; // [rsp+40h] [rbp-18h] BYREF
  PACL NewAcl; // [rsp+70h] [rbp+18h] BYREF
  PACL OldAcl; // [rsp+78h] [rbp+20h] BYREF

  hMem = 0;
  OldAcl = 0;
  NamedSecurityInfoW = GetNamedSecurityInfoW(pObjectName, SE_REGISTRY_KEY, 4u, 0, 0, &OldAcl, 0, &hMem);
  if ( !NamedSecurityInfoW )
  {
    NewAcl = 0;
    NamedSecurityInfoW = SetEntriesInAclW(1u, pListOfExplicitEntries, OldAcl, &NewAcl);
    if ( !NamedSecurityInfoW )
    {
      NamedSecurityInfoW = SetNamedSecurityInfoW(pObjectName, SE_REGISTRY_KEY, 4u, 0, 0, NewAcl, 0);
      LocalFree(NewAcl);
    }
    LocalFree(hMem);
  }
  if ( NamedSecurityInfoW > 0 )
    return (unsigned __int16)NamedSecurityInfoW | 0x80070000;
  return (unsigned int)NamedSecurityInfoW;
}

```

## disassembly

```asm
0x1801dacf8  mov     r11, rsp
0x1801dacfb  mov     [r11+8], rbx
0x1801dacff  mov     [r11+10h], rsi
0x1801dad03  push    rdi
0x1801dad04  sub     rsp, 50h
0x1801dad08  lea     rax, [r11-18h]
0x1801dad0c  mov     qword ptr [r11-18h], 0
0x1801dad14  mov     [r11-20h], rax
0x1801dad18  xor     r9d, r9d; ppsidOwner
0x1801dad1b  mov     qword ptr [r11-28h], 0
0x1801dad23  lea     rax, [r11+20h]
0x1801dad27  mov     rsi, rdx
0x1801dad2a  mov     [r11-30h], rax
0x1801dad2e  mov     rdi, rcx
0x1801dad31  mov     qword ptr [r11+20h], 0
0x1801dad39  lea     edx, [r9+4]; ObjectType
0x1801dad3d  mov     qword ptr [r11-38h], 0
0x1801dad45  mov     r8d, edx; SecurityInfo
0x1801dad48  call    cs:__imp_GetNamedSecurityInfoW
0x1801dad4e  mov     ebx, eax
0x1801dad50  test    eax, eax
0x1801dad52  jnz     short loc_1801DADBF
0x1801dad54  mov     r8, [rsp+58h+OldAcl]; OldAcl
0x1801dad59  lea     r9, [rsp+58h+NewAcl]; NewAcl
0x1801dad5e  mov     rdx, rsi; pListOfExplicitEntries
0x1801dad61  mov     [rsp+58h+NewAcl], 0
0x1801dad6a  lea     ecx, [rax+1]; cCountOfExplicitEntries
0x1801dad6d  call    cs:__imp_SetEntriesInAclW
0x1801dad73  mov     ebx, eax
0x1801dad75  test    eax, eax
0x1801dad77  jnz     short loc_1801DADB4
0x1801dad79  mov     rax, [rsp+58h+NewAcl]
0x1801dad7e  lea     edx, [rbx+4]; ObjectType
0x1801dad81  mov     [rsp+58h+pSacl], 0; pSacl
0x1801dad8a  mov     r8d, edx; SecurityInfo
0x1801dad8d  mov     [rsp+58h+pDacl], rax; pDacl
0x1801dad92  xor     r9d, r9d; psidOwner
0x1801dad95  mov     rcx, rdi; pObjectName
0x1801dad98  mov     [rsp+58h+psidGroup], 0; psidGroup
0x1801dada1  call    cs:__imp_SetNamedSecurityInfoW
0x1801dada7  mov     rcx, [rsp+58h+NewAcl]; hMem
0x1801dadac  mov     ebx, eax
0x1801dadae  call    cs:__imp_LocalFree
0x1801dadb4  mov     rcx, [rsp+58h+hMem]; hMem
0x1801dadb9  call    cs:__imp_LocalFree
0x1801dadbf  test    ebx, ebx
0x1801dadc1  jle     short loc_1801DADCC
0x1801dadc3  movzx   ebx, bx
0x1801dadc6  or      ebx, 80070000h
0x1801dadcc  mov     rsi, [rsp+58h+arg_8]
0x1801dadd1  mov     eax, ebx
0x1801dadd3  mov     rbx, [rsp+58h+arg_0]
0x1801dadd8  add     rsp, 50h
0x1801daddc  pop     rdi
0x1801daddd  retn
```
