# WwanSetDeviceObjectDacl

- ea: `0x14000e158`
- end: `0x14000e5fd`
- name: `WwanSetDeviceObjectDacl`
- size: `1189`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14000ca14`

## callees

- `0x140007d00`
- `0x14000cd98`
- `0x14000d91c`
- `0x14000e158`

## import_xrefs

- `ntoskrnl!ZwSetSecurityObject` at `0x14000e570`
- `ntoskrnl!ZwSetSecurityObject` at `0x14000e570`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14000e530`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14000e530`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14000e4e9`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14000e4e9`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14000e322`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14000e39b`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14000e414`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14000e483`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14000e322`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14000e39b`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14000e414`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14000e483`
- `ntoskrnl!RtlCreateAcl` at `0x14000e2ca`
- `ntoskrnl!RtlCreateAcl` at `0x14000e2ca`
- `ntoskrnl!SeExports` at `0x14000e1f6`
- `ntoskrnl!SeExports` at `0x14000e213`
- `ntoskrnl!SeExports` at `0x14000e234`
- `ntoskrnl!SeExports` at `0x14000e306`
- `ntoskrnl!SeExports` at `0x14000e37f`
- `ntoskrnl!SeExports` at `0x14000e3f8`
- `ntoskrnl!RtlLengthSid` at `0x14000e207`
- `ntoskrnl!RtlLengthSid` at `0x14000e226`
- `ntoskrnl!RtlLengthSid` at `0x14000e245`
- `ntoskrnl!RtlLengthSid` at `0x14000e25a`
- `ntoskrnl!RtlLengthSid` at `0x14000e207`
- `ntoskrnl!RtlLengthSid` at `0x14000e226`
- `ntoskrnl!RtlLengthSid` at `0x14000e245`
- `ntoskrnl!RtlLengthSid` at `0x14000e25a`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14000e1b9`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14000e1b9`
- `ntoskrnl!ZwClose` at `0x14000e5bd`
- `ntoskrnl!ZwClose` at `0x14000e5bd`
- `NDIS!NdisFreeMemory` at `0x14000e5de`
- `NDIS!NdisFreeMemory` at `0x14000e5de`

## pseudocode

```c
__int64 WwanSetDeviceObjectDacl()
{
  PVOID DeviceExtension; // rsi
  struct _ACL *v1; // rdi
  NTSTATUS v2; // ebx
  PDEVICE_OBJECT v3; // rcx
  __int64 v4; // rdx
  ULONG v5; // edi
  ULONG v6; // edi
  ULONG v7; // edi
  ULONG v8; // edi
  __int64 v9; // r8
  ULONG v10; // edx
  _OWORD SecurityDescriptor[2]; // [rsp+40h] [rbp-30h] BYREF
  __int64 v13; // [rsp+60h] [rbp-10h]
  HANDLE Handle; // [rsp+90h] [rbp+20h] BYREF
  PACL Acl; // [rsp+98h] [rbp+28h] BYREF

  DeviceExtension = WPP_MAIN_CB.DeviceExtension;
  v1 = 0;
  v13 = 0;
  Handle = 0;
  Acl = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v2 = ObOpenObjectByPointer(DeviceObject, 0x200u, 0, 0x40000u, 0, 0, &Handle);
  if ( v2 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v4 = 10;
LABEL_50:
      WPP_SF_d(v3->AttachedDevice, v4, WPP_d5e31b45fa4f31b576e451b1be9986c5_Traceguids);
      goto LABEL_51;
    }
    goto LABEL_51;
  }
  v5 = RtlLengthSid(SeExports->SeAliasAdminsSid);
  v6 = RtlLengthSid(SeExports->SeLocalSystemSid) + v5;
  v7 = RtlLengthSid(SeExports->SeLocalServiceSid) + v6;
  v8 = RtlLengthSid(qword_1400120A0) + v7;
  v2 = AllocMem(DeviceExtension, v8 + 40, v9, &Acl);
  if ( v2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_d5e31b45fa4f31b576e451b1be9986c5_Traceguids);
    v1 = Acl;
    goto LABEL_51;
  }
  v10 = v8 + 40;
  v1 = Acl;
  v2 = RtlCreateAcl(Acl, v10, 2u);
  if ( v2 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v4 = 12;
      goto LABEL_50;
    }
    goto LABEL_51;
  }
  v2 = RtlAddAccessAllowedAce(v1, 2u, 0x10000000u, SeExports->SeAliasAdminsSid);
  if ( v2 < 0 )
  {
    TraceAssert("NT_SUCCESS(Status)", "onecoreuap\\net\\vwifi\\filter\\device.c", 69);
LABEL_17:
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v4 = 13;
      goto LABEL_50;
    }
    goto LABEL_51;
  }
  if ( v2 )
    goto LABEL_17;
  v2 = RtlAddAccessAllowedAce(v1, 2u, 0x10000000u, SeExports->SeLocalSystemSid);
  if ( v2 < 0 )
  {
    TraceAssert("NT_SUCCESS(Status)", "onecoreuap\\net\\vwifi\\filter\\device.c", 79);
LABEL_23:
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v4 = 14;
      goto LABEL_50;
    }
    goto LABEL_51;
  }
  if ( v2 )
    goto LABEL_23;
  v2 = RtlAddAccessAllowedAce(v1, 2u, 0x80000000, SeExports->SeLocalServiceSid);
  if ( v2 < 0 )
  {
    TraceAssert("NT_SUCCESS(Status)", "onecoreuap\\net\\vwifi\\filter\\device.c", 89);
LABEL_29:
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v4 = 15;
      goto LABEL_50;
    }
    goto LABEL_51;
  }
  if ( v2 )
    goto LABEL_29;
  v2 = RtlAddAccessAllowedAce(v1, 2u, 0x10000000u, qword_1400120A0);
  if ( v2 >= 0 )
  {
    if ( !v2 )
    {
      v2 = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
      if ( v2 )
      {
        v3 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          v4 = 17;
          goto LABEL_50;
        }
      }
      else
      {
        v2 = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v1, 0);
        if ( v2 )
        {
          v3 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            v4 = 18;
            goto LABEL_50;
          }
        }
        else
        {
          v2 = ZwSetSecurityObject(Handle, 4u, SecurityDescriptor);
          if ( v2 )
          {
            v3 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
            {
              v4 = 19;
              goto LABEL_50;
            }
          }
        }
      }
      goto LABEL_51;
    }
  }
  else
  {
    TraceAssert("NT_SUCCESS(Status)", "onecoreuap\\net\\vwifi\\filter\\device.c", 99);
  }
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    v4 = 16;
    goto LABEL_50;
  }
LABEL_51:
  if ( Handle )
  {
    ZwClose(Handle);
    Handle = 0;
  }
  if ( v1 )
    NdisFreeMemory(v1, 0, 0);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14000e158  mov     r11, rsp
0x14000e15b  mov     [r11+18h], rbx
0x14000e15f  mov     [r11+10h], rdx
0x14000e163  mov     [r11+8], rcx
0x14000e167  push    rbp
0x14000e168  push    rsi
0x14000e169  push    rdi
0x14000e16a  mov     rbp, rsp
0x14000e16d  sub     rsp, 70h
0x14000e171  mov     rcx, cs:DeviceObject; Object
0x14000e178  xor     eax, eax
0x14000e17a  mov     rsi, cs:WPP_MAIN_CB.DeviceExtension
0x14000e181  xor     edi, edi
0x14000e183  xorps   xmm0, xmm0
0x14000e186  mov     [rbp+var_10], rax
0x14000e18a  mov     [rbp+Handle], rax
0x14000e18e  mov     r9d, 40000h; DesiredAccess
0x14000e194  lea     rax, [rbp+Handle]
0x14000e198  mov     [rbp+Acl], rdi
0x14000e19c  mov     [r11-58h], rax
0x14000e1a0  xor     r8d, r8d; PassedAccessState
0x14000e1a3  mov     [rsp+70h+AccessMode], dil; AccessMode
0x14000e1a8  mov     edx, 200h; HandleAttributes
0x14000e1ad  mov     [r11-68h], rdi
0x14000e1b1  movups  [rbp+SecurityDescriptor], xmm0
0x14000e1b5  movups  [rbp+var_20], xmm0
0x14000e1b9  call    cs:__imp_ObOpenObjectByPointer
0x14000e1c0  nop     dword ptr [rax+rax+00h]
0x14000e1c5  mov     ebx, eax
0x14000e1c7  test    eax, eax
0x14000e1c9  jz      short loc_14000E1F6
0x14000e1cb  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e1d2  lea     rax, WPP_GLOBAL_Control
0x14000e1d9  cmp     rcx, rax
0x14000e1dc  jz      loc_14000E5B4
0x14000e1e2  mov     edx, [rcx+2Ch]
0x14000e1e5  test    dl, 1
0x14000e1e8  jz      loc_14000E5B4
0x14000e1ee  lea     edx, [rdi+0Ah]
0x14000e1f1  jmp     loc_14000E5A1
0x14000e1f6  mov     rax, cs:__imp_SeExports
0x14000e1fd  mov     rcx, [rax]
0x14000e200  mov     rcx, [rcx+110h]; Sid
0x14000e207  call    cs:__imp_RtlLengthSid
0x14000e20e  nop     dword ptr [rax+rax+00h]
0x14000e213  mov     rcx, cs:__imp_SeExports
0x14000e21a  mov     edi, eax
0x14000e21c  mov     rcx, [rcx]
0x14000e21f  mov     rcx, [rcx+108h]; Sid
0x14000e226  call    cs:__imp_RtlLengthSid
0x14000e22d  nop     dword ptr [rax+rax+00h]
0x14000e232  add     edi, eax
0x14000e234  mov     rax, cs:__imp_SeExports
0x14000e23b  mov     rcx, [rax]
0x14000e23e  mov     rcx, [rcx+180h]; Sid
0x14000e245  call    cs:__imp_RtlLengthSid
0x14000e24c  nop     dword ptr [rax+rax+00h]
0x14000e251  lea     rcx, qword_1400120A0; Sid
0x14000e258  add     edi, eax
0x14000e25a  call    cs:__imp_RtlLengthSid
0x14000e261  nop     dword ptr [rax+rax+00h]
0x14000e266  lea     r9, [rbp+Acl]
0x14000e26a  mov     rcx, rsi
0x14000e26d  add     edi, eax
0x14000e26f  lea     edx, [rdi+28h]
0x14000e272  call    AllocMem
0x14000e277  mov     ebx, eax
0x14000e279  test    eax, eax
0x14000e27b  jz      short loc_14000E2B8
0x14000e27d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e284  lea     rax, WPP_GLOBAL_Control
0x14000e28b  cmp     rcx, rax
0x14000e28e  jz      short loc_14000E2AF
0x14000e290  mov     eax, [rcx+2Ch]
0x14000e293  test    al, 1
0x14000e295  jz      short loc_14000E2AF
0x14000e297  mov     rcx, [rcx+18h]
0x14000e29b  lea     r8, WPP_d5e31b45fa4f31b576e451b1be9986c5_Traceguids
0x14000e2a2  mov     edx, 0Bh
0x14000e2a7  mov     r9d, ebx
0x14000e2aa  call    WPP_SF_d
0x14000e2af  mov     rdi, [rbp+Acl]
0x14000e2b3  jmp     loc_14000E5B4
0x14000e2b8  lea     edx, [rdi+28h]; AclLength
0x14000e2bb  mov     esi, 2
0x14000e2c0  mov     rdi, [rbp+Acl]
0x14000e2c4  mov     r8d, esi; AclRevision
0x14000e2c7  mov     rcx, rdi; Acl
0x14000e2ca  call    cs:__imp_RtlCreateAcl
0x14000e2d1  nop     dword ptr [rax+rax+00h]
0x14000e2d6  mov     ebx, eax
0x14000e2d8  test    eax, eax
0x14000e2da  jz      short loc_14000E306
0x14000e2dc  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e2e3  lea     rax, WPP_GLOBAL_Control
0x14000e2ea  cmp     rcx, rax
0x14000e2ed  jz      loc_14000E5B4
0x14000e2f3  mov     eax, [rcx+2Ch]
0x14000e2f6  test    al, 1
0x14000e2f8  jz      loc_14000E5B4
0x14000e2fe  lea     edx, [rsi+0Ah]
0x14000e301  jmp     loc_14000E5A1
0x14000e306  mov     rax, cs:__imp_SeExports
0x14000e30d  mov     r8d, 10000000h; AccessMask
0x14000e313  mov     edx, esi; AceRevision
0x14000e315  mov     rcx, rdi; Acl
0x14000e318  mov     r9, [rax]
0x14000e31b  mov     r9, [r9+110h]; Sid
0x14000e322  call    cs:__imp_RtlAddAccessAllowedAce
0x14000e329  nop     dword ptr [rax+rax+00h]
0x14000e32e  mov     ebx, eax
0x14000e330  test    eax, eax
0x14000e332  jns     short loc_14000E34F
0x14000e334  mov     r8d, 45h ; 'E'
0x14000e33a  lea     rdx, aOnecoreuapNetV_0; "onecoreuap\\net\\vwifi\\filter\\device."...
0x14000e341  lea     rcx, aNtSuccessStatu; "NT_SUCCESS(Status)"
0x14000e348  call    TraceAssert
0x14000e34d  jmp     short loc_14000E353
0x14000e34f  test    ebx, ebx
0x14000e351  jz      short loc_14000E37F
0x14000e353  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e35a  lea     rax, WPP_GLOBAL_Control
0x14000e361  cmp     rcx, rax
0x14000e364  jz      loc_14000E5B4
0x14000e36a  mov     eax, [rcx+2Ch]
0x14000e36d  test    al, 1
0x14000e36f  jz      loc_14000E5B4
0x14000e375  mov     edx, 0Dh
0x14000e37a  jmp     loc_14000E5A1
0x14000e37f  mov     rax, cs:__imp_SeExports
0x14000e386  mov     r8d, 10000000h; AccessMask
0x14000e38c  mov     edx, esi; AceRevision
0x14000e38e  mov     rcx, rdi; Acl
0x14000e391  mov     r9, [rax]
0x14000e394  mov     r9, [r9+108h]; Sid
0x14000e39b  call    cs:__imp_RtlAddAccessAllowedAce
0x14000e3a2  nop     dword ptr [rax+rax+00h]
0x14000e3a7  mov     ebx, eax
0x14000e3a9  test    eax, eax
0x14000e3ab  jns     short loc_14000E3C8
0x14000e3ad  mov     r8d, 4Fh ; 'O'
0x14000e3b3  lea     rdx, aOnecoreuapNetV_0; "onecoreuap\\net\\vwifi\\filter\\device."...
0x14000e3ba  lea     rcx, aNtSuccessStatu; "NT_SUCCESS(Status)"
0x14000e3c1  call    TraceAssert
0x14000e3c6  jmp     short loc_14000E3CC
0x14000e3c8  test    ebx, ebx
0x14000e3ca  jz      short loc_14000E3F8
0x14000e3cc  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e3d3  lea     rax, WPP_GLOBAL_Control
0x14000e3da  cmp     rcx, rax
0x14000e3dd  jz      loc_14000E5B4
0x14000e3e3  mov     eax, [rcx+2Ch]
0x14000e3e6  test    al, 1
0x14000e3e8  jz      loc_14000E5B4
0x14000e3ee  mov     edx, 0Eh
0x14000e3f3  jmp     loc_14000E5A1
0x14000e3f8  mov     rax, cs:__imp_SeExports
0x14000e3ff  mov     r8d, 80000000h; AccessMask
0x14000e405  mov     edx, esi; AceRevision
0x14000e407  mov     rcx, rdi; Acl
0x14000e40a  mov     r9, [rax]
0x14000e40d  mov     r9, [r9+180h]; Sid
0x14000e414  call    cs:__imp_RtlAddAccessAllowedAce
0x14000e41b  nop     dword ptr [rax+rax+00h]
0x14000e420  mov     ebx, eax
0x14000e422  test    eax, eax
0x14000e424  jns     short loc_14000E441
0x14000e426  mov     r8d, 59h ; 'Y'
0x14000e42c  lea     rdx, aOnecoreuapNetV_0; "onecoreuap\\net\\vwifi\\filter\\device."...
0x14000e433  lea     rcx, aNtSuccessStatu; "NT_SUCCESS(Status)"
0x14000e43a  call    TraceAssert
0x14000e43f  jmp     short loc_14000E445
0x14000e441  test    ebx, ebx
0x14000e443  jz      short loc_14000E471
0x14000e445  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e44c  lea     rax, WPP_GLOBAL_Control
0x14000e453  cmp     rcx, rax
0x14000e456  jz      loc_14000E5B4
0x14000e45c  mov     eax, [rcx+2Ch]
0x14000e45f  test    al, 1
0x14000e461  jz      loc_14000E5B4
0x14000e467  mov     edx, 0Fh
0x14000e46c  jmp     loc_14000E5A1
0x14000e471  lea     r9, qword_1400120A0; Sid
0x14000e478  mov     r8d, 10000000h; AccessMask
0x14000e47e  mov     edx, esi; AceRevision
0x14000e480  mov     rcx, rdi; Acl
0x14000e483  call    cs:__imp_RtlAddAccessAllowedAce
0x14000e48a  nop     dword ptr [rax+rax+00h]
0x14000e48f  mov     ebx, eax
0x14000e491  test    eax, eax
0x14000e493  jns     short loc_14000E4B0
0x14000e495  mov     r8d, 63h ; 'c'
0x14000e49b  lea     rdx, aOnecoreuapNetV_0; "onecoreuap\\net\\vwifi\\filter\\device."...
0x14000e4a2  lea     rcx, aNtSuccessStatu; "NT_SUCCESS(Status)"
0x14000e4a9  call    TraceAssert
0x14000e4ae  jmp     short loc_14000E4B4
0x14000e4b0  test    ebx, ebx
0x14000e4b2  jz      short loc_14000E4E0
0x14000e4b4  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e4bb  lea     rax, WPP_GLOBAL_Control
0x14000e4c2  cmp     rcx, rax
0x14000e4c5  jz      loc_14000E5B4
0x14000e4cb  mov     eax, [rcx+2Ch]
0x14000e4ce  test    al, 1
0x14000e4d0  jz      loc_14000E5B4
0x14000e4d6  mov     edx, 10h
0x14000e4db  jmp     loc_14000E5A1
0x14000e4e0  mov     edx, 1; Revision
0x14000e4e5  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x14000e4e9  call    cs:__imp_RtlCreateSecurityDescriptor
0x14000e4f0  nop     dword ptr [rax+rax+00h]
0x14000e4f5  mov     ebx, eax
0x14000e4f7  test    eax, eax
0x14000e4f9  jz      short loc_14000E524
0x14000e4fb  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e502  lea     rax, WPP_GLOBAL_Control
0x14000e509  cmp     rcx, rax
0x14000e50c  jz      loc_14000E5B4
0x14000e512  mov     eax, [rcx+2Ch]
0x14000e515  test    al, 1
0x14000e517  jz      loc_14000E5B4
0x14000e51d  mov     edx, 11h
0x14000e522  jmp     short loc_14000E5A1
0x14000e524  xor     r9d, r9d; DaclDefaulted
0x14000e527  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x14000e52b  mov     r8, rdi; Dacl
0x14000e52e  mov     dl, 1; DaclPresent
0x14000e530  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14000e537  nop     dword ptr [rax+rax+00h]
0x14000e53c  mov     ebx, eax
0x14000e53e  test    eax, eax
0x14000e540  jz      short loc_14000E563
0x14000e542  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e549  lea     rax, WPP_GLOBAL_Control
0x14000e550  cmp     rcx, rax
0x14000e553  jz      short loc_14000E5B4
0x14000e555  mov     eax, [rcx+2Ch]
0x14000e558  test    al, 1
0x14000e55a  jz      short loc_14000E5B4
0x14000e55c  mov     edx, 12h
0x14000e561  jmp     short loc_14000E5A1
0x14000e563  mov     rcx, [rbp+Handle]; Handle
0x14000e567  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x14000e56b  mov     edx, 4; SecurityInformation
0x14000e570  call    cs:__imp_ZwSetSecurityObject
0x14000e577  nop     dword ptr [rax+rax+00h]
0x14000e57c  mov     ebx, eax
0x14000e57e  test    eax, eax
0x14000e580  jz      short loc_14000E5B4
0x14000e582  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e589  lea     rax, WPP_GLOBAL_Control
0x14000e590  cmp     rcx, rax
0x14000e593  jz      short loc_14000E5B4
0x14000e595  mov     eax, [rcx+2Ch]
0x14000e598  test    al, 1
0x14000e59a  jz      short loc_14000E5B4
0x14000e59c  mov     edx, 13h
0x14000e5a1  mov     rcx, [rcx+18h]
0x14000e5a5  lea     r8, WPP_d5e31b45fa4f31b576e451b1be9986c5_Traceguids
0x14000e5ac  mov     r9d, ebx
0x14000e5af  call    WPP_SF_d
0x14000e5b4  mov     rcx, [rbp+Handle]; Handle
0x14000e5b8  test    rcx, rcx
0x14000e5bb  jz      short loc_14000E5D1
0x14000e5bd  call    cs:__imp_ZwClose
0x14000e5c4  nop     dword ptr [rax+rax+00h]
0x14000e5c9  mov     [rbp+Handle], 0
0x14000e5d1  test    rdi, rdi
0x14000e5d4  jz      short loc_14000E5EA
0x14000e5d6  xor     r8d, r8d; MemoryFlags
0x14000e5d9  xor     edx, edx; Length
0x14000e5db  mov     rcx, rdi; VirtualAddress
0x14000e5de  call    cs:__imp_NdisFreeMemory
0x14000e5e5  nop     dword ptr [rax+rax+00h]
0x14000e5ea  mov     eax, ebx
0x14000e5ec  mov     rbx, [rsp+70h+arg_10]
0x14000e5f4  add     rsp, 70h
0x14000e5f8  pop     rdi
0x14000e5f9  pop     rsi
0x14000e5fa  pop     rbp
0x14000e5fb  retn
```
