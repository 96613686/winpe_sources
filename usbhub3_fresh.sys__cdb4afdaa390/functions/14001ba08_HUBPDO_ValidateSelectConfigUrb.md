# HUBPDO_ValidateSelectConfigUrb

- ea: `0x14001ba08`
- end: `0x14001bdbf`
- name: `HUBPDO_ValidateSelectConfigUrb`
- size: `951`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x140025710`

## callees

- `0x1400024b8`
- `0x1400025a4`
- `0x1400067ac`
- `0x140014580`
- `0x14001b804`
- `0x14001ba08`
- `0x140033530`
- `0x140045530`
- `0x140045570`
- `0x14008d9e0`
- `0x14008e0e0`

## string_xrefs

- `0x14001bc84`: `DeviceHwVerifierSetConfigTooMuchPowerRequired`

## pseudocode

```c
__int64 __fastcall HUBPDO_ValidateSelectConfigUrb(__int64 a1)
{
  __int64 v1; // r15
  __int64 v2; // rdx
  unsigned __int16 *v4; // r12
  __int64 v5; // r13
  int v6; // edx
  int v7; // ebx
  __int64 v8; // r8
  __int64 v9; // r9
  int v10; // edi
  __int64 v11; // rax
  unsigned int v12; // ecx
  unsigned int *v13; // rdx
  unsigned int v14; // ecx
  __int64 v15; // rdx
  unsigned __int16 *v16; // rcx
  unsigned __int64 v17; // r8
  unsigned int v18; // edx
  __int64 v19; // r9
  int v20; // eax
  __int64 result; // rax
  char v22; // [rsp+30h] [rbp-68h]
  _OWORD v23[2]; // [rsp+40h] [rbp-58h] BYREF
  __int64 v24; // [rsp+60h] [rbp-38h]

  v1 = *(_QWORD *)(a1 + 16);
  v2 = *(_QWORD *)(a1 + 464);
  memset(v23, 0, sizeof(v23));
  v24 = 0;
  LOWORD(v23[0]) = 40;
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _OWORD *))(WdfFunctions_01015 + 2128))(
    WdfDriverGlobals,
    v2,
    v23);
  v4 = (unsigned __int16 *)*((_QWORD *)&v23[0] + 1);
  v5 = *(_QWORD *)(*((_QWORD *)&v23[0] + 1) + 24LL);
  if ( !v5 )
  {
    *(_DWORD *)(v1 + 36) = 0;
    return 4077;
  }
  v7 = HUBPDO_ValidateConfigurationDescriptor(
         a1,
         *(char **)(*((_QWORD *)&v23[0] + 1) + 24LL),
         *(unsigned __int16 *)(v5 + 2));
  if ( !v7 )
  {
    v11 = *(_QWORD *)(v1 + 16);
    v12 = 2 * *(unsigned __int8 *)(v5 + 8);
    *(_DWORD *)(v1 + 36) = v12;
    v13 = (unsigned int *)(v11 + 92);
    if ( *(_BYTE *)(v11 + 240) && v12 > *v13 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v13) = 3;
        WPP_RECORDER_SF_(
          *(_QWORD *)(*(_QWORD *)(a1 + 8) + 1432LL),
          (_DWORD)v13,
          5,
          28,
          (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids);
      }
      v10 = -1073741670;
      v7 = -1073737728;
      *(_DWORD *)(*(_QWORD *)(a1 + 8) + 1424LL) = 5;
      if ( (unsigned int)Feature_UH3WET__private_IsEnabledDeviceUsageNoInline() )
        WMI_FireNotification(*(__int64 **)(a1 + 8), 2);
      else
        WMI_FireNotificationOld(*(_QWORD *)a1, *(_WORD *)(v1 + 48), 2u);
    }
    else
    {
      if ( (*(_DWORD *)(a1 + 1464) & 0x800) != 0 )
      {
        v14 = 150;
        if ( *v13 != 100 )
          v14 = 900;
        if ( 8 * (unsigned int)*(unsigned __int8 *)(v5 + 8) > v14 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v13) = 3;
            WPP_RECORDER_SF_(
              *(_QWORD *)(*(_QWORD *)(a1 + 8) + 1432LL),
              (_DWORD)v13,
              5,
              29,
              (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids);
          }
          v15 = *(_QWORD *)(v1 + 24);
          if ( (*(_DWORD *)(v15 + 2444) & 0x1000) != 0 )
            HUBMISC_VerifierDbgBreak("DeviceHwVerifierSetConfigTooMuchPowerRequired", v15 + 512, v8, v9);
        }
      }
      v16 = v4 + 20;
      v17 = (unsigned __int64)v4 + *v4;
      v18 = 0;
      if ( (unsigned __int64)(v4 + 21) < v17 )
      {
        while ( v18 < *(unsigned __int8 *)(v5 + 4) )
        {
          v19 = *v16;
          if ( (unsigned int)v19 < 0x18 || (v16 = (unsigned __int16 *)((char *)v16 + v19), (unsigned __int64)v16 > v17) )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v18) = 3;
              WPP_RECORDER_SF_d(
                *(_QWORD *)(*(_QWORD *)(a1 + 8) + 1432LL),
                v18,
                5,
                30,
                (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids,
                v19);
            }
            goto LABEL_55;
          }
          ++v18;
          if ( (unsigned __int64)(v16 + 1) >= v17 )
            break;
        }
      }
      v20 = *(unsigned __int8 *)(v5 + 4);
      if ( (_BYTE)v20 )
      {
        if ( v18 == v20 && v18 )
          return 4077;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v22 = v18;
          LOBYTE(v18) = 3;
          WPP_RECORDER_SF_dD(
            *(_QWORD *)(*(_QWORD *)(a1 + 8) + 1432LL),
            v18,
            5,
            32,
            (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids,
            v20,
            v22);
        }
      }
      else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v18) = 3;
        WPP_RECORDER_SF_(
          *(_QWORD *)(*(_QWORD *)(a1 + 8) + 1432LL),
          v18,
          5,
          31,
          (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids);
      }
LABEL_55:
      v7 = -1073737984;
      v10 = -1073741823;
    }
    goto LABEL_56;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v6) = 3;
    WPP_RECORDER_SF_(
      *(_QWORD *)(*(_QWORD *)(a1 + 8) + 1432LL),
      v6,
      5,
      27,
      (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids);
  }
  if ( v7 <= -1073737728 )
  {
    switch ( v7 )
    {
      case -1073737728:
        v10 = -1073741670;
        goto LABEL_23;
      case -2147483136:
      case -2147482880:
      case -2147482112:
      case -1073739264:
        v10 = -1073741811;
        goto LABEL_23;
      case -1073738240:
        v10 = -1073741637;
        goto LABEL_23;
    }
    goto LABEL_19;
  }
  switch ( v7 )
  {
    case -1073713152:
      v10 = -1073741810;
      break;
    case -1073676288:
      v10 = -1073741536;
      break;
    case 1:
      v10 = 0;
      break;
    default:
LABEL_19:
      v10 = -1073741823;
      break;
  }
LABEL_23:
  if ( v10 >= 0 )
    return 4077;
LABEL_56:
  result = 4065;
  *(_DWORD *)(a1 + 1568) = v10;
  *(_DWORD *)(a1 + 1572) = v7;
  return result;
}

```

## disassembly

```asm
0x14001ba08  mov     r11, rsp
0x14001ba0b  mov     [r11+10h], rbx
0x14001ba0f  mov     [r11+18h], rsi
0x14001ba13  push    rdi
0x14001ba14  push    r12
0x14001ba16  push    r13
0x14001ba18  push    r14
0x14001ba1a  push    r15
0x14001ba1c  sub     rsp, 70h
0x14001ba20  mov     rax, cs:__security_cookie
0x14001ba27  xor     rax, rsp
0x14001ba2a  mov     [rsp+98h+var_30], rax
0x14001ba2f  mov     r15, [rcx+10h]
0x14001ba33  lea     r8, [r11-58h]
0x14001ba37  mov     rdx, [rcx+1D0h]
0x14001ba3e  xor     eax, eax
0x14001ba40  xorps   xmm0, xmm0
0x14001ba43  mov     rsi, rcx
0x14001ba46  mov     rcx, cs:WdfDriverGlobals
0x14001ba4d  movups  [rsp+98h+var_58], xmm0
0x14001ba52  movups  [rsp+98h+var_48], xmm0
0x14001ba57  mov     [r11-38h], rax
0x14001ba5b  mov     eax, 28h ; '('
0x14001ba60  mov     word ptr [rsp+98h+var_58], ax
0x14001ba65  mov     rax, cs:WdfFunctions_01015
0x14001ba6c  mov     rax, [rax+850h]
0x14001ba73  call    _guard_dispatch_icall
0x14001ba78  mov     r12, qword ptr [rsp+98h+var_58+8]
0x14001ba7d  mov     r13, [r12+18h]
0x14001ba82  test    r13, r13
0x14001ba85  jnz     short loc_14001BA90
0x14001ba87  mov     [r15+24h], r13d
0x14001ba8b  jmp     loc_14001BD43
0x14001ba90  movzx   r8d, word ptr [r13+2]
0x14001ba95  mov     rdx, r13
0x14001ba98  mov     rcx, rsi
0x14001ba9b  call    HUBPDO_ValidateConfigurationDescriptor
0x14001baa0  mov     ebx, eax
0x14001baa2  test    eax, eax
0x14001baa4  jz      loc_14001BB63
0x14001baaa  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001bab1  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14001bab8  jz      short loc_14001BAE2
0x14001baba  mov     rcx, [rsi+8]
0x14001babe  lea     r14, WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids
0x14001bac5  mov     r9d, 1Bh
0x14001bacb  mov     [rsp+98h+var_78], r14
0x14001bad0  mov     dl, 3
0x14001bad2  mov     rcx, [rcx+598h]
0x14001bad9  lea     r8d, [r9-16h]
0x14001badd  call    WPP_RECORDER_SF_
0x14001bae2  mov     eax, 0C0001000h
0x14001bae7  cmp     ebx, eax
0x14001bae9  jg      short loc_14001BB2A
0x14001baeb  jz      short loc_14001BB23
0x14001baed  cmp     ebx, 80000200h
0x14001baf3  jz      short loc_14001BB1C
0x14001baf5  cmp     ebx, 80000300h
0x14001bafb  jz      short loc_14001BB1C
0x14001bafd  cmp     ebx, 80000600h
0x14001bb03  jz      short loc_14001BB1C
0x14001bb05  cmp     ebx, 0C0000A00h
0x14001bb0b  jz      short loc_14001BB1C
0x14001bb0d  cmp     ebx, 0C0000E00h
0x14001bb13  jnz     short loc_14001BB3F
0x14001bb15  mov     edi, 0C00000BBh
0x14001bb1a  jmp     short loc_14001BB56
0x14001bb1c  mov     edi, 0C000000Dh
0x14001bb21  jmp     short loc_14001BB56
0x14001bb23  mov     edi, 0C000009Ah
0x14001bb28  jmp     short loc_14001BB56
0x14001bb2a  cmp     ebx, 0C0007000h
0x14001bb30  jz      short loc_14001BB51
0x14001bb32  cmp     ebx, 0C0010000h
0x14001bb38  jz      short loc_14001BB4A
0x14001bb3a  cmp     ebx, 1
0x14001bb3d  jz      short loc_14001BB46
0x14001bb3f  mov     edi, 0C0000001h
0x14001bb44  jmp     short loc_14001BB56
0x14001bb46  xor     edi, edi
0x14001bb48  jmp     short loc_14001BB56
0x14001bb4a  mov     edi, 0C0000120h
0x14001bb4f  jmp     short loc_14001BB56
0x14001bb51  mov     edi, 0C000000Eh
0x14001bb56  test    edi, edi
0x14001bb58  jns     loc_14001BD43
0x14001bb5e  jmp     loc_14001BD86
0x14001bb63  movzx   ecx, byte ptr [r13+8]
0x14001bb68  mov     rax, [r15+10h]
0x14001bb6c  add     ecx, ecx
0x14001bb6e  mov     [r15+24h], ecx
0x14001bb72  cmp     byte ptr [rax+0F0h], 0
0x14001bb79  lea     rdx, [rax+5Ch]
0x14001bb7d  jz      loc_14001BC0D
0x14001bb83  cmp     ecx, [rdx]
0x14001bb85  jbe     loc_14001BC0D
0x14001bb8b  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001bb92  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14001bb99  jz      short loc_14001BBC3
0x14001bb9b  mov     rcx, [rsi+8]
0x14001bb9f  lea     r14, WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids
0x14001bba6  mov     r9d, 1Ch
0x14001bbac  mov     [rsp+98h+var_78], r14
0x14001bbb1  mov     dl, 3
0x14001bbb3  mov     rcx, [rcx+598h]
0x14001bbba  lea     r8d, [r9-17h]
0x14001bbbe  call    WPP_RECORDER_SF_
0x14001bbc3  mov     rax, [rsi+8]
0x14001bbc7  mov     edi, 0C000009Ah
0x14001bbcc  mov     ebx, 0C0001000h
0x14001bbd1  mov     dword ptr [rax+590h], 5
0x14001bbdb  call    Feature_UH3WET__private_IsEnabledDeviceUsageNoInline
0x14001bbe0  test    eax, eax
0x14001bbe2  jnz     short loc_14001BBFA
0x14001bbe4  movzx   edx, word ptr [r15+30h]
0x14001bbe9  lea     r8d, [rax+2]
0x14001bbed  mov     rcx, [rsi]
0x14001bbf0  call    WMI_FireNotificationOld
0x14001bbf5  jmp     loc_14001BD86
0x14001bbfa  mov     rcx, [rsi+8]
0x14001bbfe  mov     edx, 2
0x14001bc03  call    WMI_FireNotification
0x14001bc08  jmp     loc_14001BD86
0x14001bc0d  test    dword ptr [rsi+5B8h], 800h
0x14001bc17  lea     rdi, WPP_RECORDER_INITIALIZED
0x14001bc1e  lea     r14, WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids
0x14001bc25  jz      short loc_14001BC90
0x14001bc27  cmp     dword ptr [rdx], 64h ; 'd'
0x14001bc2a  mov     eax, 384h
0x14001bc2f  mov     ecx, 96h
0x14001bc34  cmovnz  ecx, eax
0x14001bc37  movzx   eax, byte ptr [r13+8]
0x14001bc3c  shl     eax, 3
0x14001bc3f  cmp     eax, ecx
0x14001bc41  jbe     short loc_14001BC90
0x14001bc43  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x14001bc4a  jz      short loc_14001BC6D
0x14001bc4c  mov     rcx, [rsi+8]
0x14001bc50  mov     r9d, 1Dh
0x14001bc56  mov     dl, 3
0x14001bc58  mov     [rsp+98h+var_78], r14
0x14001bc5d  mov     rcx, [rcx+598h]
0x14001bc64  lea     r8d, [r9-18h]
0x14001bc68  call    WPP_RECORDER_SF_
0x14001bc6d  mov     rdx, [r15+18h]
0x14001bc71  test    dword ptr [rdx+98Ch], 1000h
0x14001bc7b  jz      short loc_14001BC90
0x14001bc7d  add     rdx, 200h
0x14001bc84  lea     rcx, aDevicehwverifi_4; "DeviceHwVerifierSetConfigTooMuchPowerRe"...
0x14001bc8b  call    HUBMISC_VerifierDbgBreak
0x14001bc90  movzx   r8d, word ptr [r12]
0x14001bc95  lea     rcx, [r12+28h]
0x14001bc9a  add     r8, r12
0x14001bc9d  lea     rax, [rcx+2]
0x14001bca1  xor     edx, edx
0x14001bca3  cmp     rax, r8
0x14001bca6  jnb     short loc_14001BCCF
0x14001bca8  movzx   r10d, byte ptr [r13+4]
0x14001bcad  cmp     edx, r10d
0x14001bcb0  jnb     short loc_14001BCCF
0x14001bcb2  movzx   r9d, word ptr [rcx]
0x14001bcb6  cmp     r9d, 18h
0x14001bcba  jb      short loc_14001BD08
0x14001bcbc  add     rcx, r9
0x14001bcbf  cmp     rcx, r8
0x14001bcc2  ja      short loc_14001BD08
0x14001bcc4  inc     edx
0x14001bcc6  lea     rax, [rcx+2]
0x14001bcca  cmp     rax, r8
0x14001bccd  jb      short loc_14001BCAD
0x14001bccf  movzx   eax, byte ptr [r13+4]
0x14001bcd4  test    al, al
0x14001bcd6  jnz     short loc_14001BD3B
0x14001bcd8  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x14001bcdf  jz      loc_14001BD7C
0x14001bce5  mov     rcx, [rsi+8]
0x14001bce9  mov     r9d, 1Fh
0x14001bcef  mov     dl, 3
0x14001bcf1  mov     [rsp+98h+var_78], r14
0x14001bcf6  mov     rcx, [rcx+598h]
0x14001bcfd  lea     r8d, [r9-1Ah]
0x14001bd01  call    WPP_RECORDER_SF_
0x14001bd06  jmp     short loc_14001BD7C
0x14001bd08  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x14001bd0f  jz      short loc_14001BD7C
0x14001bd11  mov     rcx, [rsi+8]
0x14001bd15  mov     eax, r9d
0x14001bd18  mov     r9d, 1Eh
0x14001bd1e  mov     [rsp+98h+var_70], eax
0x14001bd22  mov     dl, 3
0x14001bd24  mov     [rsp+98h+var_78], r14
0x14001bd29  mov     rcx, [rcx+598h]
0x14001bd30  lea     r8d, [r9-19h]
0x14001bd34  call    WPP_RECORDER_SF_d
0x14001bd39  jmp     short loc_14001BD7C
0x14001bd3b  cmp     edx, eax
0x14001bd3d  jnz     short loc_14001BD4A
0x14001bd3f  test    edx, edx
0x14001bd41  jz      short loc_14001BD4A
0x14001bd43  mov     eax, 0FEDh
0x14001bd48  jmp     short loc_14001BD97
0x14001bd4a  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x14001bd51  jz      short loc_14001BD7C
0x14001bd53  mov     rcx, [rsi+8]
0x14001bd57  mov     r9d, 20h ; ' '
0x14001bd5d  mov     dword ptr [rsp+98h+var_68], edx
0x14001bd61  mov     dl, 3
0x14001bd63  mov     [rsp+98h+var_70], eax
0x14001bd67  mov     [rsp+98h+var_78], r14
0x14001bd6c  mov     rcx, [rcx+598h]
0x14001bd73  lea     r8d, [r9-1Bh]
0x14001bd77  call    WPP_RECORDER_SF_dD
0x14001bd7c  mov     ebx, 0C0000F00h
0x14001bd81  mov     edi, 0C0000001h
0x14001bd86  mov     eax, 0FE1h
0x14001bd8b  mov     [rsi+620h], edi
0x14001bd91  mov     [rsi+624h], ebx
0x14001bd97  mov     rcx, [rsp+98h+var_30]
0x14001bd9c  xor     rcx, rsp; StackCookie
0x14001bd9f  call    __security_check_cookie
0x14001bda4  lea     r11, [rsp+98h+var_28]
0x14001bda9  mov     rbx, [r11+38h]
0x14001bdad  mov     rsi, [r11+40h]
0x14001bdb1  mov     rsp, r11
0x14001bdb4  pop     r15
0x14001bdb6  pop     r14
0x14001bdb8  pop     r13
0x14001bdba  pop     r12
0x14001bdbc  pop     rdi
0x14001bdbd  retn
```
