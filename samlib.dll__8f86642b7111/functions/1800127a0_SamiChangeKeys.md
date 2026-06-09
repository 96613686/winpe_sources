# SamiChangeKeys

- ea: `0x1800127a0`
- end: `0x180012c26`
- name: `SamiChangeKeys`
- size: `1158`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180001800`
- `0x180002a80`
- `0x180004dd0`
- `0x180006620`
- `0x1800078c0`
- `0x18000807c`
- `0x1800127a0`
- `0x180014030`
- `0x180016848`
- `0x180016900`
- `0x180016eb4`

## import_xrefs

- `CRYPTBASE!SystemFunction036` at `0x180012a7c`
- `CRYPTBASE!SystemFunction036` at `0x180012a7c`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180012ba0`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180012ba0`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180012bb9`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180012bb9`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x1800128d3`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x1800128d3`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180012885`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180012885`

## pseudocode

```c
__int64 SamiChangeKeys()
{
  NTSTATUS v0; // eax
  unsigned int v1; // ebx
  _QWORD *v2; // rcx
  __int64 v3; // rdx
  int v4; // eax
  __int64 v5; // rdx
  __int64 v6; // r9
  unsigned int v8; // [rsp+20h] [rbp-99h] BYREF
  void *v9; // [rsp+28h] [rbp-91h] BYREF
  void *v10; // [rsp+30h] [rbp-89h] BYREF
  PVOID PolicyHandle; // [rsp+38h] [rbp-81h] BYREF
  PVOID Buffer; // [rsp+40h] [rbp-79h] BYREF
  __int128 v13; // [rsp+48h] [rbp-71h]
  __int128 v14; // [rsp+58h] [rbp-61h]
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-51h] BYREF
  __int64 v16; // [rsp+98h] [rbp-21h] BYREF
  int v17; // [rsp+A0h] [rbp-19h]
  __int128 v18; // [rsp+B0h] [rbp-9h] BYREF
  __int128 v19; // [rsp+C0h] [rbp+7h] BYREF
  _BYTE RandomBuffer[16]; // [rsp+D0h] [rbp+17h] BYREF

  v10 = 0;
  v9 = 0;
  v16 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v17 = 0;
  Buffer = 0;
  v8 = 0;
  v13 = 0;
  PolicyHandle = 0;
  v14 = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 315, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids);
  ObjectAttributes.Length = 48;
  ObjectAttributes.SecurityQualityOfService = &v16;
  memset(&ObjectAttributes.RootDirectory, 0, 20);
  ObjectAttributes.SecurityDescriptor = 0;
  v16 = 0x20000000CLL;
  LOWORD(v17) = 1;
  v0 = LsaOpenPolicy(0, &ObjectAttributes, 1u, &PolicyHandle);
  v1 = v0;
  if ( v0 < 0 )
  {
    v2 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v3 = 316;
LABEL_8:
      WPP_SF_D(v2[2], v3, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, (unsigned int)v0);
LABEL_57:
      v2 = WPP_GLOBAL_Control;
      goto LABEL_58;
    }
    goto LABEL_58;
  }
  v0 = LsaQueryInformationPolicy(PolicyHandle, PolicyAccountDomainInformation, &Buffer);
  v1 = v0;
  if ( v0 >= 0 )
  {
    v0 = SamConnect(0, &v10, 32, &ObjectAttributes);
    v1 = v0;
    if ( v0 < 0 )
    {
      v2 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v3 = 318;
        goto LABEL_8;
      }
      goto LABEL_58;
    }
    v4 = SamOpenDomain(v10, 3, *((PSID *)Buffer + 2), (__int64 *)&v9);
    v1 = v4;
    if ( v4 < 0 )
    {
      v2 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_55;
      v5 = 319;
      goto LABEL_21;
    }
    v4 = WxReadBootOption(&v8);
    v1 = v4;
    if ( v4 < 0 )
    {
      v2 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_55;
      v5 = 320;
      goto LABEL_21;
    }
    if ( v8 != 1 )
    {
      v2 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 321, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, v8);
        v2 = WPP_GLOBAL_Control;
      }
      v1 = -1073741604;
      goto LABEL_55;
    }
    v18 = 0;
    if ( !WxpDeObfuscateKey(0, (__int64)&v18) )
    {
      v1 = -1073741823;
      v2 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_55;
      v5 = 322;
      v6 = 3221225473LL;
      goto LABEL_53;
    }
    v19 = v18;
    *((_QWORD *)&v13 + 1) = &v19;
    LODWORD(v13) = 1048592;
    v4 = SamiSetBootKeyInformation(v9);
    v1 = v4;
    if ( v4 < 0 )
    {
      v2 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_55;
      v5 = 323;
      goto LABEL_21;
    }
    if ( !SystemFunction036(RandomBuffer, 0x10u) )
    {
      v1 = -1073741823;
LABEL_54:
      v2 = WPP_GLOBAL_Control;
LABEL_55:
      if ( !v9 )
        goto LABEL_58;
      SamCloseHandle(v9);
      goto LABEL_57;
    }
    *((_QWORD *)&v14 + 1) = RandomBuffer;
    LODWORD(v14) = 1048592;
    v4 = SamiSetBootKeyInformation(v9);
    v1 = v4;
    if ( v4 < 0 )
    {
      v2 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_55;
      v5 = 324;
LABEL_21:
      v6 = (unsigned int)v4;
LABEL_53:
      WPP_SF_D(v2[2], v5, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, v6);
      goto LABEL_54;
    }
    if ( (_WORD)v14 == 16 )
    {
      v18 = **((_OWORD **)&v14 + 1);
      if ( WxpObfuscateKey((__int64)&v18) )
      {
        v1 = 0;
        goto LABEL_54;
      }
      v1 = -1073741823;
    }
    else
    {
      v1 = -1073741811;
    }
    v2 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_55;
    v5 = 325;
    v6 = v1;
    goto LABEL_53;
  }
  v2 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v3 = 317;
    goto LABEL_8;
  }
LABEL_58:
  if ( v10 )
  {
    SamCloseHandle(v10);
    v2 = WPP_GLOBAL_Control;
  }
  if ( PolicyHandle )
  {
    LsaClose(PolicyHandle);
    v2 = WPP_GLOBAL_Control;
  }
  if ( Buffer )
  {
    LsaFreeMemory(Buffer);
    v2 = WPP_GLOBAL_Control;
  }
  if ( (v1 & 0x80000000) != 0 )
  {
    if ( (*((_BYTE *)v2 + 28) & 2) != 0 && *((_BYTE *)v2 + 25) >= 2u )
      WPP_SF_D(v2[2], 327, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, v1);
  }
  else if ( (*((_BYTE *)v2 + 28) & 2) != 0 && *((_BYTE *)v2 + 25) >= 4u )
  {
    WPP_SF_(v2[2], 326, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids);
  }
  return v1;
}

```

## disassembly

```asm
0x1800127a0  push    rbp
0x1800127a2  push    rbx
0x1800127a3  push    rsi
0x1800127a4  push    r12
0x1800127a6  push    r15
0x1800127a8  lea     rbp, [rsp-37h]
0x1800127ad  sub     rsp, 0F0h
0x1800127b4  mov     rax, cs:__security_cookie
0x1800127bb  xor     rax, rsp
0x1800127be  mov     [rbp+57h+var_30], rax
0x1800127c2  xorps   xmm0, xmm0
0x1800127c5  mov     [rsp+110h+var_E0], 0
0x1800127ce  xor     eax, eax
0x1800127d0  mov     [rsp+110h+var_E8], 0
0x1800127d9  xorps   xmm1, xmm1
0x1800127dc  mov     [rbp+57h+var_78], rax
0x1800127e0  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800127e4  mov     [rbp+57h+var_70], eax
0x1800127e7  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800127eb  mov     [rbp+57h+Buffer], rax
0x1800127ef  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800127f3  mov     [rsp+110h+var_F0], eax
0x1800127f7  movups  [rbp+57h+var_C8], xmm0
0x1800127fb  mov     [rsp+110h+PolicyHandle], 0
0x180012804  movups  [rbp+57h+var_B8], xmm1
0x180012808  mov     rcx, cs:WPP_GLOBAL_Control
0x18001280f  lea     esi, [rax+2]
0x180012812  lea     r15, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x180012819  test    [rcx+1Ch], sil
0x18001281d  jz      short loc_180012836
0x18001281f  cmp     byte ptr [rcx+19h], 4
0x180012823  jb      short loc_180012836
0x180012825  mov     rcx, [rcx+10h]
0x180012829  mov     edx, 13Bh
0x18001282e  mov     r8, r15
0x180012831  call    WPP_SF_
0x180012836  lea     rax, [rbp+57h+var_78]
0x18001283a  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180012841  lea     r9, [rsp+110h+PolicyHandle]; PolicyHandle
0x180012846  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], rax
0x18001284a  mov     r8d, 1; DesiredAccess
0x180012850  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x180012858  lea     rdx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18001285c  mov     [rbp+57h+ObjectAttributes.Attributes], 0
0x180012863  xor     ecx, ecx; SystemName
0x180012865  mov     [rbp+57h+ObjectAttributes.ObjectName], 0
0x18001286d  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], 0
0x180012875  mov     dword ptr [rbp+57h+var_78], 0Ch
0x18001287c  mov     dword ptr [rbp+57h+var_78+4], esi
0x18001287f  mov     word ptr [rbp+57h+var_70], 1
0x180012885  call    cs:__imp_LsaOpenPolicy
0x18001288b  mov     ebx, eax
0x18001288d  test    eax, eax
0x18001288f  jns     short loc_1800128C5
0x180012891  mov     rcx, cs:WPP_GLOBAL_Control
0x180012898  test    [rcx+1Ch], sil
0x18001289c  jz      loc_180012B7A
0x1800128a2  cmp     [rcx+19h], sil
0x1800128a6  jb      loc_180012B7A
0x1800128ac  mov     edx, 13Ch
0x1800128b1  mov     rcx, [rcx+10h]
0x1800128b5  mov     r9d, eax
0x1800128b8  mov     r8, r15
0x1800128bb  call    WPP_SF_D
0x1800128c0  jmp     loc_180012B73
0x1800128c5  mov     rcx, [rsp+110h+PolicyHandle]; PolicyHandle
0x1800128ca  lea     r8, [rbp+57h+Buffer]; Buffer
0x1800128ce  mov     edx, 5; InformationClass
0x1800128d3  call    cs:__imp_LsaQueryInformationPolicy
0x1800128d9  mov     ebx, eax
0x1800128db  test    eax, eax
0x1800128dd  jns     short loc_180012901
0x1800128df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800128e6  test    [rcx+1Ch], sil
0x1800128ea  jz      loc_180012B7A
0x1800128f0  cmp     [rcx+19h], sil
0x1800128f4  jb      loc_180012B7A
0x1800128fa  mov     edx, 13Dh
0x1800128ff  jmp     short loc_1800128B1
0x180012901  lea     r9, [rbp+57h+ObjectAttributes]
0x180012905  mov     r8d, 20h ; ' '
0x18001290b  lea     rdx, [rsp+110h+var_E0]
0x180012910  xor     ecx, ecx
0x180012912  call    SamConnect
0x180012917  mov     ebx, eax
0x180012919  test    eax, eax
0x18001291b  jns     short loc_180012942
0x18001291d  mov     rcx, cs:WPP_GLOBAL_Control
0x180012924  test    [rcx+1Ch], sil
0x180012928  jz      loc_180012B7A
0x18001292e  cmp     [rcx+19h], sil
0x180012932  jb      loc_180012B7A
0x180012938  mov     edx, 13Eh
0x18001293d  jmp     loc_1800128B1
0x180012942  mov     r8, [rbp+57h+Buffer]
0x180012946  lea     r9, [rsp+110h+var_E8]
0x18001294b  mov     rcx, [rsp+110h+var_E0]; void *
0x180012950  mov     edx, 3; char
0x180012955  mov     r8, [r8+10h]; pSid
0x180012959  call    SamOpenDomain
0x18001295e  mov     ebx, eax
0x180012960  test    eax, eax
0x180012962  jns     short loc_18001298C
0x180012964  mov     rcx, cs:WPP_GLOBAL_Control
0x18001296b  test    [rcx+1Ch], sil
0x18001296f  jz      loc_180012B61
0x180012975  cmp     [rcx+19h], sil
0x180012979  jb      loc_180012B61
0x18001297f  mov     edx, 13Fh
0x180012984  mov     r9d, eax
0x180012987  jmp     loc_180012B4E
0x18001298c  lea     rcx, [rsp+110h+var_F0]
0x180012991  call    WxReadBootOption
0x180012996  mov     ebx, eax
0x180012998  test    eax, eax
0x18001299a  jns     short loc_1800129BE
0x18001299c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800129a3  test    [rcx+1Ch], sil
0x1800129a7  jz      loc_180012B61
0x1800129ad  cmp     [rcx+19h], sil
0x1800129b1  jb      loc_180012B61
0x1800129b7  mov     edx, 140h
0x1800129bc  jmp     short loc_180012984
0x1800129be  mov     r9d, [rsp+110h+var_F0]
0x1800129c3  cmp     r9d, 1
0x1800129c7  jz      short loc_1800129FE
0x1800129c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800129d0  test    [rcx+1Ch], sil
0x1800129d4  jz      short loc_1800129F4
0x1800129d6  cmp     [rcx+19h], sil
0x1800129da  jb      short loc_1800129F4
0x1800129dc  mov     rcx, [rcx+10h]
0x1800129e0  mov     edx, 141h
0x1800129e5  mov     r8, r15
0x1800129e8  call    WPP_SF_D
0x1800129ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800129f4  mov     ebx, 0C00000DCh
0x1800129f9  jmp     loc_180012B61
0x1800129fe  xorps   xmm0, xmm0
0x180012a01  lea     rdx, [rbp+57h+var_60]
0x180012a05  xor     ecx, ecx
0x180012a07  movups  [rbp+57h+var_60], xmm0
0x180012a0b  call    WxpDeObfuscateKey
0x180012a10  test    al, al
0x180012a12  jz      loc_180012B2B
0x180012a18  movaps  xmm0, [rbp+57h+var_60]
0x180012a1c  lea     rax, [rbp+57h+var_50]
0x180012a20  mov     rcx, [rsp+110h+var_E8]; void *
0x180012a25  lea     r9, [rbp+57h+var_C8]
0x180012a29  lea     r8, [rbp+57h+var_C8]
0x180012a2d  movdqa  [rbp+57h+var_50], xmm0
0x180012a32  mov     dl, 1
0x180012a34  mov     qword ptr [rbp+57h+var_C8+8], rax
0x180012a38  mov     r12d, 10h
0x180012a3e  mov     dword ptr [rbp+57h+var_C8], 100010h
0x180012a45  call    SamiSetBootKeyInformation
0x180012a4a  mov     ebx, eax
0x180012a4c  test    eax, eax
0x180012a4e  jns     short loc_180012A75
0x180012a50  mov     rcx, cs:WPP_GLOBAL_Control
0x180012a57  test    [rcx+1Ch], sil
0x180012a5b  jz      loc_180012B61
0x180012a61  cmp     [rcx+19h], sil
0x180012a65  jb      loc_180012B61
0x180012a6b  mov     edx, 143h
0x180012a70  jmp     loc_180012984
0x180012a75  mov     edx, r12d; RandomBufferLength
0x180012a78  lea     rcx, [rbp+57h+RandomBuffer]; RandomBuffer
0x180012a7c  call    cs:__imp_SystemFunction036
0x180012a82  test    al, al
0x180012a84  jnz     short loc_180012A90
0x180012a86  mov     ebx, 0C0000001h
0x180012a8b  jmp     loc_180012B5A
0x180012a90  mov     rcx, [rsp+110h+var_E8]; void *
0x180012a95  lea     rax, [rbp+57h+RandomBuffer]
0x180012a99  lea     r9, [rbp+57h+var_B8]
0x180012a9d  mov     qword ptr [rbp+57h+var_B8+8], rax
0x180012aa1  lea     r8, [rbp+57h+var_C8]
0x180012aa5  mov     dword ptr [rbp+57h+var_B8], 100010h
0x180012aac  xor     edx, edx
0x180012aae  call    SamiSetBootKeyInformation
0x180012ab3  mov     ebx, eax
0x180012ab5  test    eax, eax
0x180012ab7  jns     short loc_180012ADE
0x180012ab9  mov     rcx, cs:WPP_GLOBAL_Control
0x180012ac0  test    [rcx+1Ch], sil
0x180012ac4  jz      loc_180012B61
0x180012aca  cmp     [rcx+19h], sil
0x180012ace  jb      loc_180012B61
0x180012ad4  mov     edx, 144h
0x180012ad9  jmp     loc_180012984
0x180012ade  cmp     word ptr [rbp+57h+var_B8], r12w
0x180012ae3  jz      short loc_180012AEC
0x180012ae5  mov     ebx, 0C000000Dh
0x180012aea  jmp     short loc_180012B0E
0x180012aec  mov     rax, qword ptr [rbp+57h+var_B8+8]
0x180012af0  lea     rcx, [rbp+57h+var_60]
0x180012af4  movups  xmm0, xmmword ptr [rax]
0x180012af7  movdqu  [rbp+57h+var_60], xmm0
0x180012afc  call    WxpObfuscateKey
0x180012b01  test    al, al
0x180012b03  jz      short loc_180012B09
0x180012b05  xor     ebx, ebx
0x180012b07  jmp     short loc_180012B5A
0x180012b09  mov     ebx, 0C0000001h
0x180012b0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180012b15  test    [rcx+1Ch], sil
0x180012b19  jz      short loc_180012B61
0x180012b1b  cmp     [rcx+19h], sil
0x180012b1f  jb      short loc_180012B61
0x180012b21  mov     edx, 145h
0x180012b26  mov     r9d, ebx
0x180012b29  jmp     short loc_180012B4E
0x180012b2b  mov     ebx, 0C0000001h
0x180012b30  mov     rcx, cs:WPP_GLOBAL_Control
0x180012b37  test    [rcx+1Ch], sil
0x180012b3b  jz      short loc_180012B61
0x180012b3d  cmp     [rcx+19h], sil
0x180012b41  jb      short loc_180012B61
0x180012b43  mov     edx, 142h
0x180012b48  mov     r9d, 0C0000001h
0x180012b4e  mov     rcx, [rcx+10h]
0x180012b52  mov     r8, r15
0x180012b55  call    WPP_SF_D
0x180012b5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180012b61  cmp     [rsp+110h+var_E8], 0
0x180012b67  jz      short loc_180012B7A
0x180012b69  mov     rcx, [rsp+110h+var_E8]; void *
0x180012b6e  call    SamCloseHandle
0x180012b73  mov     rcx, cs:WPP_GLOBAL_Control
0x180012b7a  mov     rax, [rsp+110h+var_E0]
0x180012b7f  test    rax, rax
0x180012b82  jz      short loc_180012B93
0x180012b84  mov     rcx, rax; void *
0x180012b87  call    SamCloseHandle
0x180012b8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180012b93  mov     rax, [rsp+110h+PolicyHandle]
0x180012b98  test    rax, rax
0x180012b9b  jz      short loc_180012BAD
0x180012b9d  mov     rcx, rax; ObjectHandle
0x180012ba0  call    cs:__imp_LsaClose
0x180012ba6  mov     rcx, cs:WPP_GLOBAL_Control
0x180012bad  mov     rax, [rbp+57h+Buffer]
0x180012bb1  test    rax, rax
0x180012bb4  jz      short loc_180012BC6
0x180012bb6  mov     rcx, rax; Buffer
0x180012bb9  call    cs:__imp_LsaFreeMemory
0x180012bbf  mov     rcx, cs:WPP_GLOBAL_Control
0x180012bc6  test    ebx, ebx
0x180012bc8  js      short loc_180012BE9
0x180012bca  test    [rcx+1Ch], sil
0x180012bce  jz      short loc_180012C09
0x180012bd0  cmp     byte ptr [rcx+19h], 4
0x180012bd4  jb      short loc_180012C09
0x180012bd6  mov     rcx, [rcx+10h]
0x180012bda  mov     edx, 146h
0x180012bdf  mov     r8, r15
0x180012be2  call    WPP_SF_
0x180012be7  jmp     short loc_180012C09
0x180012be9  test    [rcx+1Ch], sil
0x180012bed  jz      short loc_180012C09
0x180012bef  cmp     [rcx+19h], sil
0x180012bf3  jb      short loc_180012C09
0x180012bf5  mov     rcx, [rcx+10h]
0x180012bf9  mov     edx, 147h
0x180012bfe  mov     r9d, ebx
0x180012c01  mov     r8, r15
0x180012c04  call    WPP_SF_D
0x180012c09  mov     eax, ebx
0x180012c0b  mov     rcx, [rbp+57h+var_30]
0x180012c0f  xor     rcx, rsp; StackCookie
0x180012c12  call    __security_check_cookie
0x180012c17  add     rsp, 0F0h
0x180012c1e  pop     r15
0x180012c20  pop     r12
0x180012c22  pop     rsi
0x180012c23  pop     rbx
0x180012c24  pop     rbp
0x180012c25  retn
```
