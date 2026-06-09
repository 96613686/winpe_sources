# GetSDDLFromRestrictionSettings(int,ushort * *)

- ea: `0x180042f38`
- end: `0x18004309c`
- name: `?GetSDDLFromRestrictionSettings@@YAKHPEAPEAG@Z`
- size: `356`
- prototype: `unsigned int(int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002ee10`

## callees

- `0x1800063a0`
- `0x180006934`
- `0x18003af80`
- `0x180042f38`
- `0x1800430a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043011`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043011`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180043007`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180043007`

## pseudocode

```c
__int64 __fastcall GetSDDLFromRestrictionSettings(int a1, unsigned __int16 **a2)
{
  __int64 *v4; // r9
  unsigned int LastError; // eax
  unsigned int v6; // ebx
  union DOT11_OUI_HEADER *v7; // rcx
  __int64 v8; // rdx
  ULONG StringSecurityDescriptorLen; // [rsp+50h] [rbp+8h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+60h] [rbp+18h] BYREF

  SecurityDescriptor = 0;
  StringSecurityDescriptorLen = 0;
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_6182d216504e38fbc7ab7351306d8f7c_Traceguids);
  }
  v4 = qword_180073120;
  if ( !a1 )
    v4 = qword_1800731C0;
  LastError = GetSecurityDescriptor(
                5,
                &qword_180073190,
                10 - (unsigned int)(a1 != 0),
                (const struct _SYMBOLIC_ACE *)v4,
                4u,
                4u,
                &SecurityDescriptor);
  v6 = LastError;
  if ( LastError )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 31;
LABEL_15:
      WPP_SF_d(*((_QWORD *)v7 + 2), v8, WPP_6182d216504e38fbc7ab7351306d8f7c_Traceguids, LastError);
LABEL_16:
      v7 = WPP_GLOBAL_Control;
    }
  }
  else
  {
    if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(
           SecurityDescriptor,
           1u,
           7u,
           a2,
           &StringSecurityDescriptorLen) )
    {
      goto LABEL_16;
    }
    LastError = GetLastError();
    v6 = LastError;
    if ( !LastError )
      goto LABEL_16;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 32;
      goto LABEL_15;
    }
  }
  if ( SecurityDescriptor )
  {
    FreeWLMemory(SecurityDescriptor);
    v7 = WPP_GLOBAL_Control;
  }
  if ( v7 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)v7 + 2), 33, WPP_6182d216504e38fbc7ab7351306d8f7c_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x180042f38  mov     rax, rsp
0x180042f3b  mov     [rax+10h], rbx
0x180042f3f  mov     [rax+20h], rsi
0x180042f43  push    rdi
0x180042f44  sub     rsp, 40h
0x180042f48  mov     rdi, rdx
0x180042f4b  mov     qword ptr [rax+18h], 0
0x180042f53  mov     ebx, ecx
0x180042f55  mov     dword ptr [rax+8], 0
0x180042f5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180042f63  lea     rsi, WPP_GLOBAL_Control
0x180042f6a  cmp     rcx, rsi
0x180042f6d  jz      short loc_180042F8A
0x180042f6f  test    byte ptr [rcx+1Ch], 8
0x180042f73  jz      short loc_180042F8A
0x180042f75  mov     rcx, [rcx+10h]
0x180042f79  lea     r8, WPP_6182d216504e38fbc7ab7351306d8f7c_Traceguids
0x180042f80  mov     edx, 1Eh
0x180042f85  call    WPP_SF_
0x180042f8a  test    ebx, ebx
0x180042f8c  lea     rax, qword_1800731C0
0x180042f93  lea     r9, qword_180073120
0x180042f9a  cmovz   r9, rax; struct _SYMBOLIC_ACE *
0x180042f9e  lea     rdx, qword_180073190; enum WELL_KNOWN_SID_TYPE *
0x180042fa5  lea     rax, [rsp+48h+SecurityDescriptor]
0x180042faa  neg     ebx
0x180042fac  mov     [rsp+48h+var_18], rax; void **
0x180042fb1  mov     eax, 4
0x180042fb6  sbb     r8d, r8d
0x180042fb9  mov     [rsp+48h+var_20], eax; unsigned int
0x180042fbd  add     r8d, 0Ah; unsigned int
0x180042fc1  mov     dword ptr [rsp+48h+StringSecurityDescriptorLen], eax; unsigned int
0x180042fc5  lea     ecx, [rax+1]; unsigned int
0x180042fc8  call    ?GetSecurityDescriptor@@YAKKQEBW4WELL_KNOWN_SID_TYPE@@KPEBU_SYMBOLIC_ACE@@KKPEAPEAX@Z; GetSecurityDescriptor(ulong,WELL_KNOWN_SID_TYPE const * const,ulong,_SYMBOLIC_ACE const *,ulong,ulong,void * *)
0x180042fcd  mov     ebx, eax
0x180042fcf  test    eax, eax
0x180042fd1  jz      short loc_180042FEC
0x180042fd3  mov     rcx, cs:WPP_GLOBAL_Control
0x180042fda  cmp     rcx, rsi
0x180042fdd  jz      short loc_18004304E
0x180042fdf  test    byte ptr [rcx+1Ch], 1
0x180042fe3  jz      short loc_18004304E
0x180042fe5  mov     edx, 1Fh
0x180042fea  jmp     short loc_180043034
0x180042fec  mov     rcx, [rsp+48h+SecurityDescriptor]; SecurityDescriptor
0x180042ff1  lea     rax, [rsp+48h+arg_0]
0x180042ff6  mov     edx, 1; RequestedStringSDRevision
0x180042ffb  mov     [rsp+48h+StringSecurityDescriptorLen], rax; StringSecurityDescriptorLen
0x180043000  mov     r9, rdi; StringSecurityDescriptor
0x180043003  lea     r8d, [rdx+6]; SecurityInformation
0x180043007  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x18004300d  test    eax, eax
0x18004300f  jnz     short loc_180043047
0x180043011  call    cs:__imp_GetLastError
0x180043017  mov     ebx, eax
0x180043019  test    eax, eax
0x18004301b  jz      short loc_180043047
0x18004301d  mov     rcx, cs:WPP_GLOBAL_Control
0x180043024  cmp     rcx, rsi
0x180043027  jz      short loc_18004304E
0x180043029  test    byte ptr [rcx+1Ch], 1
0x18004302d  jz      short loc_18004304E
0x18004302f  mov     edx, 20h ; ' '
0x180043034  mov     rcx, [rcx+10h]
0x180043038  lea     r8, WPP_6182d216504e38fbc7ab7351306d8f7c_Traceguids
0x18004303f  mov     r9d, eax
0x180043042  call    WPP_SF_d
0x180043047  mov     rcx, cs:WPP_GLOBAL_Control
0x18004304e  mov     rax, [rsp+48h+SecurityDescriptor]
0x180043053  test    rax, rax
0x180043056  jz      short loc_180043067
0x180043058  mov     rcx, rax
0x18004305b  call    FreeWLMemory
0x180043060  mov     rcx, cs:WPP_GLOBAL_Control
0x180043067  cmp     rcx, rsi
0x18004306a  jz      short loc_18004308A
0x18004306c  test    byte ptr [rcx+1Ch], 8
0x180043070  jz      short loc_18004308A
0x180043072  mov     rcx, [rcx+10h]
0x180043076  lea     r8, WPP_6182d216504e38fbc7ab7351306d8f7c_Traceguids
0x18004307d  mov     edx, 21h ; '!'
0x180043082  mov     r9d, ebx
0x180043085  call    WPP_SF_d
0x18004308a  mov     rsi, [rsp+48h+arg_18]
0x18004308f  mov     eax, ebx
0x180043091  mov     rbx, [rsp+48h+arg_8]
0x180043096  add     rsp, 40h
0x18004309a  pop     rdi
0x18004309b  retn
```
