# AddInterfaceToInterfaceStateNameList(_WNF_STATE_NAME,_GUID,_WNF_STATE_NAME *)

- ea: `0x18008be10`
- end: `0x18008c034`
- name: `?AddInterfaceToInterfaceStateNameList@@YAJU_WNF_STATE_NAME@@U_GUID@@PEAU1@@Z`
- size: `548`
- prototype: `__int64 __fastcall(struct _WNF_STATE_NAME, struct _GUID *__struct_ptr, struct _WNF_STATE_NAME *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18011babc`

## callees

- `0x18008be10`
- `0x18008c03c`
- `0x18008c2dc`
- `0x1800cb1a0`
- `0x180106340`
- `0x1801d8854`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008bf18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008bf18`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18008bf9f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18008bf9f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008bf6d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008bf6d`
- `ntdll!NtCreateWnfStateName` at `0x18008bf54`
- `ntdll!NtCreateWnfStateName` at `0x18008bf54`
- `ntdll!NtDeleteWnfStateName` at `0x18008c009`
- `ntdll!NtDeleteWnfStateName` at `0x18008c009`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18008bf0e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18008bf0e`

## pseudocode

```c
__int64 __fastcall AddInterfaceToInterfaceStateNameList(
        struct _WNF_STATE_NAME a1,
        struct _GUID *a2,
        struct _WNF_STATE_NAME *a3)
{
  int InterfaceStateEntryFromInterfaceGuid; // eax
  int v7; // esi
  struct _WNF_STATE_NAME v8; // rbx
  int v9; // eax
  signed int LastError; // eax
  int v11; // eax
  __int64 v12; // xmm0_8
  unsigned int v13; // r8d
  int v14; // eax
  unsigned int v15; // eax
  unsigned int v17; // [rsp+40h] [rbp-39h] BYREF
  ULONG SecurityDescriptorSize[3]; // [rsp+44h] [rbp-35h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor[2]; // [rsp+50h] [rbp-29h] BYREF
  _BYTE v20[32]; // [rsp+60h] [rbp-19h] BYREF
  struct _WNF_STATE_NAME v21; // [rsp+80h] [rbp+7h] BYREF
  _QWORD v22[4]; // [rsp+88h] [rbp+Fh] BYREF

  memset(&v20[4], 0, 28);
  memset(v22, 0, sizeof(v22));
  v21 = 0;
  v17 = 0;
  while ( 1 )
  {
    while ( 1 )
    {
      *(struct _GUID *)SecurityDescriptor = *a2;
      InterfaceStateEntryFromInterfaceGuid = GetInterfaceStateEntryFromInterfaceGuid(
                                               a1,
                                               (struct _GUID *)SecurityDescriptor,
                                               (struct InterfaceStateEntry *)v20,
                                               &v17);
      v7 = InterfaceStateEntryFromInterfaceGuid;
      if ( InterfaceStateEntryFromInterfaceGuid == -2147023728 )
        break;
      if ( InterfaceStateEntryFromInterfaceGuid < 0 )
        goto LABEL_24;
      v8 = *(struct _WNF_STATE_NAME *)&v20[16];
      v9 = CheckStateNameExists(*(struct _WNF_STATE_NAME *)&v20[16]);
      v7 = v9;
      if ( v9 < 0 )
        goto LABEL_24;
      if ( !v9 )
      {
        v7 = -2147024713;
        if ( a3 )
          *a3 = v8;
LABEL_24:
        v15 = NullWnfStateName;
        goto LABEL_28;
      }
      if ( v9 != 1 )
        break;
      *(struct _GUID *)SecurityDescriptor = *a2;
      v7 = RemoveInterfaceFromInterfaceStateNameList(a1, (struct _GUID *)SecurityDescriptor);
      if ( v7 < 0 )
        goto LABEL_24;
    }
    if ( v21 == NullWnfStateName )
    {
      SecurityDescriptor[0] = 0;
      SecurityDescriptorSize[0] = 0;
      if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
             L"D:(A;;0x10003;;;SY)(A;;0x10002;;;S-1-5-80-1428027539-3309602793-2678353003-1498846795-3763184142)(A;;0x1000"
              "2;;;S-1-5-80-3787436395-2174616005-3003730137-1094982900-1570567328)(A;;1;;;IU)(A;;1;;;S-1-5-80-4155767994"
              "-3874329934-3800885181-2130851812-726865888)",
             1u,
             SecurityDescriptor,
             SecurityDescriptorSize) )
      {
        v7 = 0;
        v11 = NtCreateWnfStateName(&v21, 3, 0, 0, 0, 4096, SecurityDescriptor[0]);
        if ( v11 < 0 )
          v7 = v11 | 0x10000000;
      }
      else
      {
        LastError = GetLastError();
        v7 = LastError;
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
      }
      if ( SecurityDescriptor[0] )
        LocalFree(SecurityDescriptor[0]);
      if ( v7 < 0 )
        goto LABEL_24;
      v12 = *(_QWORD *)&a2->Data2;
      LODWORD(v22[0]) = a2->Data1;
      HIDWORD(v22[1]) = *(_DWORD *)&a2->Data4[4];
      v22[2] = v21;
      *(_QWORD *)((char *)v22 + 4) = v12;
    }
    GetSystemTimeAsFileTime((LPFILETIME)&v22[3]);
    v14 = AddToInterfaceStateNameList(a1, (struct InterfaceStateEntry *)v22, v13, &v17);
    v7 = v14;
    if ( v14 >= 0 )
      break;
    if ( v14 != -805306367 )
      goto LABEL_24;
  }
  if ( a3 )
    *a3 = v21;
  v15 = NullWnfStateName;
  v21 = (struct _WNF_STATE_NAME)NullWnfStateName;
LABEL_28:
  if ( v21 != __PAIR64__(HIDWORD(NullWnfStateName), v15) )
    NtDeleteWnfStateName(&v21);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18008be10  mov     [rsp-8+arg_18], rbx
0x18008be15  push    rbp
0x18008be16  push    rsi
0x18008be17  push    rdi
0x18008be18  push    r14
0x18008be1a  push    r15
0x18008be1c  lea     rbp, [rsp-37h]
0x18008be21  sub     rsp, 0B0h
0x18008be28  mov     rax, cs:__security_cookie
0x18008be2f  xor     rax, rsp
0x18008be32  mov     [rbp+57h+var_28], rax
0x18008be36  xorps   xmm0, xmm0
0x18008be39  xor     eax, eax
0x18008be3b  movups  xmmword ptr [rbp+57h+var_6C], xmm0
0x18008be3f  mov     r14, r8
0x18008be42  mov     r15, rdx
0x18008be45  movups  xmmword ptr [rbp+57h+var_44], xmm0
0x18008be49  mov     rdi, rcx
0x18008be4c  mov     [rbp+57h+var_48], eax
0x18008be4f  movups  xmmword ptr [rbp+57h+var_6C+0Ch], xmm0
0x18008be53  mov     [rbp+57h+var_50], rax
0x18008be57  movups  xmmword ptr [rbp+57h+var_44+0Ch], xmm0
0x18008be5b  mov     [rbp+57h+var_90], eax
0x18008be5e  movaps  xmm0, xmmword ptr [r15]
0x18008be62  lea     r9, [rbp+57h+var_90]; unsigned int *
0x18008be66  lea     r8, [rbp+57h+var_70]; struct InterfaceStateEntry *
0x18008be6a  movdqa  xmmword ptr [rbp+57h+SecurityDescriptor], xmm0
0x18008be6f  lea     rdx, [rbp+57h+SecurityDescriptor]; struct _GUID
0x18008be73  mov     rcx, rdi; struct _WNF_STATE_NAME
0x18008be76  call    ?GetInterfaceStateEntryFromInterfaceGuid@@YAJU_WNF_STATE_NAME@@U_GUID@@PEAUInterfaceStateEntry@@PEAK@Z; GetInterfaceStateEntryFromInterfaceGuid(_WNF_STATE_NAME,_GUID,InterfaceStateEntry *,ulong *)
0x18008be7b  mov     esi, eax
0x18008be7d  cmp     eax, 80070490h
0x18008be82  jz      short loc_18008BECD
0x18008be84  test    eax, eax
0x18008be86  js      loc_18008BFD5
0x18008be8c  mov     rbx, qword ptr [rbp+57h+var_6C+0Ch]
0x18008be90  mov     rcx, rbx; struct _WNF_STATE_NAME
0x18008be93  call    ?CheckStateNameExists@@YAJU_WNF_STATE_NAME@@@Z; CheckStateNameExists(_WNF_STATE_NAME)
0x18008be98  mov     esi, eax
0x18008be9a  test    eax, eax
0x18008be9c  js      loc_18008BFD5
0x18008bea2  jz      loc_18008BFC8
0x18008bea8  cmp     eax, 1
0x18008beab  jnz     short loc_18008BECD
0x18008bead  movaps  xmm0, xmmword ptr [r15]
0x18008beb1  lea     rdx, [rbp+57h+SecurityDescriptor]; struct _GUID
0x18008beb5  mov     rcx, rdi; struct _WNF_STATE_NAME
0x18008beb8  movdqa  xmmword ptr [rbp+57h+SecurityDescriptor], xmm0
0x18008bebd  call    ?RemoveInterfaceFromInterfaceStateNameList@@YAJU_WNF_STATE_NAME@@U_GUID@@@Z; RemoveInterfaceFromInterfaceStateNameList(_WNF_STATE_NAME,_GUID)
0x18008bec2  mov     esi, eax
0x18008bec4  test    eax, eax
0x18008bec6  jns     short loc_18008BE5E
0x18008bec8  jmp     loc_18008BFD5
0x18008becd  mov     eax, dword ptr [rbp+57h+var_50]
0x18008bed0  cmp     eax, dword ptr cs:NullWnfStateName
0x18008bed6  jnz     loc_18008BF9B
0x18008bedc  mov     eax, dword ptr cs:NullWnfStateName+4
0x18008bee2  cmp     dword ptr [rbp+57h+var_50+4], eax
0x18008bee5  jnz     loc_18008BF9B
0x18008beeb  lea     r9, [rbp+57h+SecurityDescriptorSize]; SecurityDescriptorSize
0x18008beef  mov     [rbp+57h+SecurityDescriptor], 0
0x18008bef7  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18008befb  mov     [rbp+57h+SecurityDescriptorSize], 0
0x18008bf02  mov     edx, 1; StringSDRevision
0x18008bf07  lea     rcx, StringSecurityDescriptor; "D:(A;;0x10003;;;SY)(A;;0x10002;;;S-1-5-"...
0x18008bf0e  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18008bf14  test    eax, eax
0x18008bf16  jnz     short loc_18008BF2F
0x18008bf18  call    cs:__imp_GetLastError
0x18008bf1e  mov     esi, eax
0x18008bf20  test    eax, eax
0x18008bf22  jle     short loc_18008BF64
0x18008bf24  movzx   esi, ax
0x18008bf27  or      esi, 80070000h
0x18008bf2d  jmp     short loc_18008BF64
0x18008bf2f  mov     rax, [rbp+57h+SecurityDescriptor]
0x18008bf33  lea     rcx, [rbp+57h+var_50]
0x18008bf37  mov     [rsp+0D0h+var_A0], rax
0x18008bf3c  xor     esi, esi
0x18008bf3e  mov     [rsp+0D0h+var_A8], 1000h
0x18008bf46  xor     r9d, r9d
0x18008bf49  xor     r8d, r8d
0x18008bf4c  mov     [rsp+0D0h+var_B0], rsi
0x18008bf51  lea     edx, [rsi+3]
0x18008bf54  call    cs:__imp_NtCreateWnfStateName
0x18008bf5a  test    eax, eax
0x18008bf5c  jns     short loc_18008BF64
0x18008bf5e  mov     esi, eax
0x18008bf60  bts     esi, 1Ch
0x18008bf64  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x18008bf68  test    rcx, rcx
0x18008bf6b  jz      short loc_18008BF73
0x18008bf6d  call    cs:__imp_LocalFree
0x18008bf73  test    esi, esi
0x18008bf75  js      short loc_18008BFD5
0x18008bf77  mov     eax, [r15]
0x18008bf7a  movsd   xmm0, qword ptr [r15+4]
0x18008bf80  mov     [rbp+57h+var_48], eax
0x18008bf83  mov     eax, [r15+0Ch]
0x18008bf87  mov     dword ptr [rbp+57h+var_44+8], eax
0x18008bf8a  mov     eax, dword ptr [rbp+57h+var_50]
0x18008bf8d  mov     dword ptr [rbp+57h+var_44+0Ch], eax
0x18008bf90  mov     eax, dword ptr [rbp+57h+var_50+4]
0x18008bf93  mov     dword ptr [rbp+57h+var_44+10h], eax
0x18008bf96  movsd   qword ptr [rbp+57h+var_44], xmm0
0x18008bf9b  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18008bf9f  call    cs:__imp_GetSystemTimeAsFileTime
0x18008bfa5  lea     r9, [rbp+57h+var_90]; unsigned int *
0x18008bfa9  mov     rcx, rdi; struct _WNF_STATE_NAME
0x18008bfac  lea     rdx, [rbp+57h+var_48]; struct InterfaceStateEntry *
0x18008bfb0  call    ?AddToInterfaceStateNameList@@YAJU_WNF_STATE_NAME@@PEAUInterfaceStateEntry@@KPEAK@Z; AddToInterfaceStateNameList(_WNF_STATE_NAME,InterfaceStateEntry *,ulong,ulong *)
0x18008bfb5  mov     esi, eax
0x18008bfb7  test    eax, eax
0x18008bfb9  jns     short loc_18008BFDE
0x18008bfbb  cmp     eax, 0D0000001h
0x18008bfc0  jz      loc_18008BE5E
0x18008bfc6  jmp     short loc_18008BFD5
0x18008bfc8  mov     esi, 800700B7h
0x18008bfcd  test    r14, r14
0x18008bfd0  jz      short loc_18008BFD5
0x18008bfd2  mov     [r14], rbx
0x18008bfd5  mov     rax, cs:NullWnfStateName
0x18008bfdc  jmp     short loc_18008BFF5
0x18008bfde  test    r14, r14
0x18008bfe1  jz      short loc_18008BFEA
0x18008bfe3  mov     rax, [rbp+57h+var_50]
0x18008bfe7  mov     [r14], rax
0x18008bfea  mov     rax, cs:NullWnfStateName
0x18008bff1  mov     [rbp+57h+var_50], rax
0x18008bff5  cmp     dword ptr [rbp+57h+var_50], eax
0x18008bff8  jnz     short loc_18008C005
0x18008bffa  mov     eax, dword ptr cs:NullWnfStateName+4
0x18008c000  cmp     dword ptr [rbp+57h+var_50+4], eax
0x18008c003  jz      short loc_18008C00F
0x18008c005  lea     rcx, [rbp+57h+var_50]
0x18008c009  call    cs:__imp_NtDeleteWnfStateName
0x18008c00f  mov     eax, esi
0x18008c011  mov     rcx, [rbp+57h+var_28]
0x18008c015  xor     rcx, rsp; StackCookie
0x18008c018  call    __security_check_cookie
0x18008c01d  mov     rbx, [rsp+0D0h+arg_18]
0x18008c025  add     rsp, 0B0h
0x18008c02c  pop     r15
0x18008c02e  pop     r14
0x18008c030  pop     rdi
0x18008c031  pop     rsi
0x18008c032  pop     rbp
0x18008c033  retn
```
