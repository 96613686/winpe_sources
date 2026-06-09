# ReserveHTTPPrefix(ushort *,ushort *)

- ea: `0x140051bc0`
- end: `0x140051da7`
- name: `?ReserveHTTPPrefix@@YAKPEAG0@Z`
- size: `487`
- prototype: `unsigned int(unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140051db0`

## callees

- `0x14003f17c`
- `0x140047798`
- `0x140051bc0`
- `0x140054534`

## import_xrefs

- `HTTPAPI!HttpDeleteServiceConfiguration` at `0x140051c87`
- `HTTPAPI!HttpDeleteServiceConfiguration` at `0x140051c87`
- `HTTPAPI!HttpSetServiceConfiguration` at `0x140051c35`
- `HTTPAPI!HttpSetServiceConfiguration` at `0x140051ced`
- `HTTPAPI!HttpSetServiceConfiguration` at `0x140051c35`
- `HTTPAPI!HttpSetServiceConfiguration` at `0x140051ced`

## pseudocode

```c
__int64 __fastcall ReserveHTTPPrefix(unsigned __int16 *a1, unsigned __int16 *a2)
{
  ULONG v3; // ebx
  PVOID *v4; // r10
  unsigned int v5; // eax
  unsigned int v6; // eax
  __int64 v7; // rdx
  unsigned int v8; // eax
  _QWORD pConfigInformation[7]; // [rsp+30h] [rbp-38h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a2);
  }
  pConfigInformation[0] = L"http://+:10243/WMPNSSv4/";
  pConfigInformation[1] = a2;
  v3 = HttpSetServiceConfiguration(0, HttpServiceConfigUrlAclInfo, pConfigInformation, 0x10u, 0);
  if ( v3 != 183 )
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v3;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_30;
    v8 = 5;
    if ( v3 )
      v8 = 2;
    if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) < v8 )
      goto LABEL_30;
    v7 = 148;
    goto LABEL_29;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 145, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids);
  }
  v3 = HttpDeleteServiceConfiguration(0, HttpServiceConfigUrlAclInfo, pConfigInformation, 0x10u, 0);
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v5 = 5;
    if ( v3 )
      v5 = 2;
    if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= v5 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 146, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids, v3);
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( !v3 )
  {
    v3 = HttpSetServiceConfiguration(0, HttpServiceConfigUrlAclInfo, pConfigInformation, 0x10u, 0);
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v3;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v6 = 5;
      if ( v3 )
        v6 = 2;
      if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= v6 )
      {
        v7 = 147;
LABEL_29:
        WPP_SF_d(v4[2], v7, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids, v3);
        v4 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
  }
LABEL_30:
  if ( v4 != &WPP_GLOBAL_Control
    && (*((_BYTE *)v4 + 28) & 1) != 0
    && *((unsigned __int8 *)v4 + 25) >= (unsigned int)(v3 != 0 ? 2 : 5) )
  {
    WPP_SF_d(v4[2], 149, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids, v3);
  }
  return v3;
}

```

## disassembly

```asm
0x140051bc0  push    rbx
0x140051bc2  push    rdi
0x140051bc3  push    r14
0x140051bc5  push    r15
0x140051bc7  sub     rsp, 48h
0x140051bcb  mov     rbx, rdx
0x140051bce  mov     rcx, cs:WPP_GLOBAL_Control
0x140051bd5  lea     r14, WPP_GLOBAL_Control
0x140051bdc  lea     rdi, aHttp10243Wmpns; "http://+:10243/WMPNSSv4/"
0x140051be3  lea     r15, WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids
0x140051bea  cmp     rcx, r14
0x140051bed  jz      short loc_140051C14
0x140051bef  test    byte ptr [rcx+1Ch], 1
0x140051bf3  jz      short loc_140051C14
0x140051bf5  cmp     byte ptr [rcx+19h], 5
0x140051bf9  jb      short loc_140051C14
0x140051bfb  mov     rcx, [rcx+10h]; LoggerHandle
0x140051bff  mov     edx, 90h
0x140051c04  mov     r9, rdi
0x140051c07  mov     [rsp+68h+pOverlapped], rbx; __int64
0x140051c0c  mov     r8, r15
0x140051c0f  call    WPP_SF_SS
0x140051c14  xor     eax, eax
0x140051c16  mov     [rsp+68h+pConfigInformation], rdi
0x140051c1b  lea     r8, [rsp+68h+pConfigInformation]; pConfigInformation
0x140051c20  mov     [rsp+68h+var_30], rbx
0x140051c25  xor     ecx, ecx; ServiceHandle
0x140051c27  mov     [rsp+68h+pOverlapped], rax; pOverlapped
0x140051c2c  lea     edi, [rax+2]
0x140051c2f  mov     edx, edi; ConfigId
0x140051c31  lea     r9d, [rax+10h]; ConfigInformationLength
0x140051c35  call    cs:__imp_HttpSetServiceConfiguration
0x140051c3b  mov     ebx, eax
0x140051c3d  cmp     eax, 0B7h
0x140051c42  jnz     loc_140051D25
0x140051c48  mov     rcx, cs:WPP_GLOBAL_Control
0x140051c4f  cmp     rcx, r14
0x140051c52  jz      short loc_140051C6F
0x140051c54  test    [rcx+1Ch], dil
0x140051c58  jz      short loc_140051C6F
0x140051c5a  cmp     byte ptr [rcx+19h], 5
0x140051c5e  jb      short loc_140051C6F
0x140051c60  mov     rcx, [rcx+10h]
0x140051c64  lea     edx, [rax-26h]
0x140051c67  mov     r8, r15
0x140051c6a  call    WPP_SF_
0x140051c6f  mov     r9d, 10h; ConfigInformationLength
0x140051c75  mov     [rsp+68h+pOverlapped], 0; pOverlapped
0x140051c7e  lea     r8, [rsp+68h+pConfigInformation]; pConfigInformation
0x140051c83  mov     edx, edi; ConfigId
0x140051c85  xor     ecx, ecx; ServiceHandle
0x140051c87  call    cs:__imp_HttpDeleteServiceConfiguration
0x140051c8d  mov     ebx, eax
0x140051c8f  mov     r10, cs:WPP_GLOBAL_Control
0x140051c96  cmp     r10, r14
0x140051c99  jz      short loc_140051CCF
0x140051c9b  test    [r10+1Ch], dil
0x140051c9f  jz      short loc_140051CCF
0x140051ca1  movzx   edx, byte ptr [r10+19h]
0x140051ca6  test    ebx, ebx
0x140051ca8  mov     eax, 5
0x140051cad  cmovnz  eax, edi
0x140051cb0  cmp     edx, eax
0x140051cb2  jb      short loc_140051CCF
0x140051cb4  mov     rcx, [r10+10h]
0x140051cb8  mov     edx, 92h
0x140051cbd  mov     r9d, ebx
0x140051cc0  mov     r8, r15
0x140051cc3  call    WPP_SF_d
0x140051cc8  mov     r10, cs:WPP_GLOBAL_Control
0x140051ccf  test    ebx, ebx
0x140051cd1  jnz     loc_140051D65
0x140051cd7  lea     r9d, [rbx+10h]; ConfigInformationLength
0x140051cdb  mov     [rsp+68h+pOverlapped], 0; pOverlapped
0x140051ce4  lea     r8, [rsp+68h+pConfigInformation]; pConfigInformation
0x140051ce9  mov     edx, edi; ConfigId
0x140051ceb  xor     ecx, ecx; ServiceHandle
0x140051ced  call    cs:__imp_HttpSetServiceConfiguration
0x140051cf3  mov     ebx, eax
0x140051cf5  mov     r10, cs:WPP_GLOBAL_Control
0x140051cfc  cmp     r10, r14
0x140051cff  jz      loc_140051D9A
0x140051d05  test    [r10+1Ch], dil
0x140051d09  jz      short loc_140051D65
0x140051d0b  movzx   ecx, byte ptr [r10+19h]
0x140051d10  test    ebx, ebx
0x140051d12  mov     eax, 5
0x140051d17  cmovnz  eax, edi
0x140051d1a  cmp     ecx, eax
0x140051d1c  jb      short loc_140051D65
0x140051d1e  mov     edx, 93h
0x140051d23  jmp     short loc_140051D4F
0x140051d25  mov     r10, cs:WPP_GLOBAL_Control
0x140051d2c  cmp     r10, r14
0x140051d2f  jz      short loc_140051D9A
0x140051d31  test    [r10+1Ch], dil
0x140051d35  jz      short loc_140051D65
0x140051d37  movzx   ecx, byte ptr [r10+19h]
0x140051d3c  test    ebx, ebx
0x140051d3e  mov     eax, 5
0x140051d43  cmovnz  eax, edi
0x140051d46  cmp     ecx, eax
0x140051d48  jb      short loc_140051D65
0x140051d4a  mov     edx, 94h
0x140051d4f  mov     rcx, [r10+10h]
0x140051d53  mov     r9d, ebx
0x140051d56  mov     r8, r15
0x140051d59  call    WPP_SF_d
0x140051d5e  mov     r10, cs:WPP_GLOBAL_Control
0x140051d65  cmp     r10, r14
0x140051d68  jz      short loc_140051D9A
0x140051d6a  test    byte ptr [r10+1Ch], 1
0x140051d6f  jz      short loc_140051D9A
0x140051d71  movzx   edx, byte ptr [r10+19h]
0x140051d76  mov     eax, ebx
0x140051d78  neg     eax
0x140051d7a  sbb     ecx, ecx
0x140051d7c  and     ecx, 0FFFFFFFDh
0x140051d7f  add     ecx, 5
0x140051d82  cmp     edx, ecx
0x140051d84  jb      short loc_140051D9A
0x140051d86  mov     rcx, [r10+10h]
0x140051d8a  mov     edx, 95h
0x140051d8f  mov     r9d, ebx
0x140051d92  mov     r8, r15
0x140051d95  call    WPP_SF_d
0x140051d9a  mov     eax, ebx
0x140051d9c  add     rsp, 48h
0x140051da0  pop     r15
0x140051da2  pop     r14
0x140051da4  pop     rdi
0x140051da5  pop     rbx
0x140051da6  retn
```
