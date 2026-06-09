# InterfaceMgr::GetPreferredWWanPhysicalInterface(_GUID *)

- ea: `0x180012bfc`
- end: `0x1800130bf`
- name: `?GetPreferredWWanPhysicalInterface@InterfaceMgr@@CAJPEAU_GUID@@@Z`
- size: `1219`
- prototype: `__int64 __fastcall(struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180012a90`

## callees

- `0x1800035a8`
- `0x18000bf4c`
- `0x18000bf74`
- `0x180012bfc`
- `0x1800140f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012c91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012c91`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012ca6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012ca6`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x180012e2a`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x180012f2e`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x180012e2a`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x180012f2e`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180012c9e`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180013089`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180012c9e`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180013089`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180012d53`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180012e57`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180012f47`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180013064`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180013077`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180012d53`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180012e57`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180012f47`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180013064`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180013077`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x180012cbf`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x180012cbf`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanEnumerateInterfaces` at `0x180012d29`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanEnumerateInterfaces` at `0x180012d29`

## pseudocode

```c
__int64 __fastcall InterfaceMgr::GetPreferredWWanPhysicalInterface(struct _GUID *a1)
{
  struct _GUID v2; // xmm7
  struct _GUID v3; // xmm6
  int v4; // r8d
  signed int v5; // edi
  TetheringServiceTelemetry *v6; // rcx
  __int64 v7; // rdx
  int v8; // eax
  __int64 v9; // rcx
  _DWORD *v10; // rax
  char v11; // r15
  unsigned int v12; // r12d
  __int64 v13; // r13
  int Interface; // eax
  __int64 v15; // rcx
  char v16; // si
  __int64 v17; // rax
  int v18; // ebx
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v23; // [rsp+48h] [rbp-49h] BYREF
  __int64 v24; // [rsp+50h] [rbp-41h] BYREF
  __int64 v25; // [rsp+58h] [rbp-39h] BYREF
  __int64 v26; // [rsp+60h] [rbp-31h]
  __int64 *v27; // [rsp+68h] [rbp-29h]
  __int64 v28; // [rsp+70h] [rbp-21h] BYREF
  char v29; // [rsp+78h] [rbp-19h]
  char v30; // [rsp+F8h] [rbp+67h]
  int v31; // [rsp+108h] [rbp+77h] BYREF
  int v32; // [rsp+110h] [rbp+7Fh]

  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 122, &WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids);
  }
  v31 = 0;
  v2 = 0;
  *a1 = GUID_NULL;
  v24 = -1;
  v3 = 0;
  v23 = 0;
  v25 = 0;
  if ( (unsigned __int8)IsWwanOpenHandlePresent() )
  {
    v24 = -1;
    v5 = WwanOpenHandle(1, 0, &v31, &v24);
    if ( v5 <= 0 )
      goto LABEL_9;
  }
  else
  {
    LOWORD(v5) = 50;
  }
  v5 = (unsigned __int16)v5 | 0x80070000;
LABEL_9:
  if ( v5 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_68;
      v7 = 123;
      goto LABEL_13;
    }
    goto LABEL_71;
  }
  v27 = &v23;
  v28 = 0;
  v29 = 1;
  v8 = WwanEnumerateInterfaces(v24, 0, &v28);
  v5 = v8;
  if ( v8 > 0 )
    v5 = (unsigned __int16)v8 | 0x80070000;
  if ( v29 )
  {
    v9 = *v27;
    *v27 = v28;
    if ( v9 )
      WwanFreeMemory(v9);
  }
  if ( v5 >= 0 )
  {
    if ( !*(_DWORD *)v23 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 125, &WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids);
        v6 = WPP_GLOBAL_Control;
      }
      v5 = -2147024875;
      goto LABEL_68;
    }
    v10 = (_DWORD *)v23;
    v11 = 0;
    v30 = 0;
    v12 = 0;
    *a1 = *(struct _GUID *)(v23 + 4);
    if ( !*v10 )
    {
      v6 = WPP_GLOBAL_Control;
LABEL_63:
      if ( v6 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v6 + 28) & 4) != 0 )
        {
          v19 = 130;
LABEL_66:
          WPP_SF_(*((_QWORD *)v6 + 2), v19, &WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids);
          goto LABEL_67;
        }
LABEL_68:
        if ( v6 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
          WPP_SF_d_guid_(*((_QWORD *)v6 + 2), 131, v4, v5, (__int64)a1);
      }
      goto LABEL_71;
    }
    while ( 1 )
    {
      v27 = &v25;
      v13 = 588LL * v12;
      v28 = 0;
      v29 = 1;
      Interface = WwanQueryInterface(v24, v13 + v23 + 4, 28);
      v5 = Interface;
      if ( Interface > 0 )
        v5 = (unsigned __int16)Interface | 0x80070000;
      if ( v29 )
      {
        v15 = *v27;
        *v27 = v28;
        if ( v15 )
          WwanFreeMemory(v15);
      }
      if ( v5 < 0 )
        break;
      if ( v25 )
      {
        v5 = -2147467259;
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
          goto LABEL_71;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v19 = 127;
          goto LABEL_66;
        }
        goto LABEL_68;
      }
      v16 = 0;
      if ( MEMORY[0] == 1 )
      {
        if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 128, &WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids);
        }
        v17 = v23;
        v16 = 1;
        v30 = 1;
        v2 = *(struct _GUID *)(v23 + v13 + 4);
      }
      else
      {
        v17 = v23;
      }
      v26 = 0;
      v32 = 0;
      if ( (unsigned int)WwanQueryInterface(v24, v13 + v17 + 4, 7) )
        goto LABEL_53;
      if ( !v26 )
        goto LABEL_53;
      v18 = *(_DWORD *)(v26 + 2276);
      WwanFreeMemory(v26);
      if ( v18 )
        goto LABEL_53;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 129, &WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids);
        v6 = WPP_GLOBAL_Control;
      }
      v11 = 1;
      v3 = *(struct _GUID *)(v23 + v13 + 4);
      if ( v16 )
      {
LABEL_55:
        if ( !v30 )
        {
          if ( v11 )
            goto LABEL_57;
          goto LABEL_63;
        }
        if ( v11 )
        {
LABEL_57:
          *a1 = v3;
          goto LABEL_67;
        }
        *a1 = v2;
LABEL_67:
        v6 = WPP_GLOBAL_Control;
        goto LABEL_68;
      }
LABEL_54:
      if ( ++v12 >= *(_DWORD *)v23 )
        goto LABEL_55;
    }
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_54;
    }
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      126,
      &WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids,
      (unsigned int)v5);
LABEL_53:
    v6 = WPP_GLOBAL_Control;
    goto LABEL_54;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_68;
    v7 = 124;
LABEL_13:
    WPP_SF_d(*((_QWORD *)v6 + 2), v7, &WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids, (unsigned int)v5);
    goto LABEL_67;
  }
LABEL_71:
  v20 = v25;
  v25 = 0;
  if ( v20 )
    WwanFreeMemory(v20);
  v21 = v23;
  v23 = 0;
  if ( v21 )
    WwanFreeMemory(v21);
  if ( v24 != -1 )
    WwanCloseHandle(v24, 0);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180012bfc  mov     rax, rsp
0x180012bff  push    rbp
0x180012c00  push    rbx
0x180012c01  push    rsi
0x180012c02  push    rdi
0x180012c03  push    r12
0x180012c05  push    r13
0x180012c07  push    r14
0x180012c09  push    r15
0x180012c0b  lea     rbp, [rax-5Fh]
0x180012c0f  sub     rsp, 0A8h
0x180012c16  movaps  xmmword ptr [rax-58h], xmm6
0x180012c1a  mov     r14, rcx
0x180012c1d  movaps  xmmword ptr [rax-68h], xmm7
0x180012c21  mov     rcx, cs:WPP_GLOBAL_Control
0x180012c28  lea     rsi, WPP_GLOBAL_Control
0x180012c2f  lea     r13, WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids
0x180012c36  cmp     rcx, rsi
0x180012c39  jz      short loc_180012C52
0x180012c3b  test    byte ptr [rcx+1Ch], 8
0x180012c3f  jz      short loc_180012C52
0x180012c41  mov     rcx, [rcx+10h]
0x180012c45  mov     edx, 7Ah ; 'z'
0x180012c4a  mov     r8, r13
0x180012c4d  call    WPP_SF_
0x180012c52  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180012c59  xor     ebx, ebx
0x180012c5b  or      r12, 0FFFFFFFFFFFFFFFFh
0x180012c5f  mov     [rbp+57h+arg_10], ebx
0x180012c62  xorps   xmm7, xmm7
0x180012c65  movdqu  xmmword ptr [r14], xmm0
0x180012c6a  mov     [rbp+57h+var_98], r12
0x180012c6e  xorps   xmm6, xmm6
0x180012c71  mov     [rbp+57h+var_A0], rbx
0x180012c75  mov     [rbp+57h+var_90], rbx
0x180012c79  call    IsWwanOpenHandlePresent
0x180012c7e  mov     r15d, 80070000h
0x180012c84  test    al, al
0x180012c86  jz      short loc_180012CCD
0x180012c88  mov     rdi, [rbp+57h+var_98]
0x180012c8c  cmp     rdi, r12
0x180012c8f  jz      short loc_180012CAE
0x180012c91  call    cs:__imp_GetLastError
0x180012c97  xor     edx, edx
0x180012c99  mov     rcx, rdi
0x180012c9c  mov     ebx, eax
0x180012c9e  call    cs:__imp_WwanCloseHandle
0x180012ca4  mov     ecx, ebx; dwErrCode
0x180012ca6  call    cs:__imp_SetLastError
0x180012cac  xor     ebx, ebx
0x180012cae  xor     edx, edx
0x180012cb0  mov     [rbp+57h+var_98], r12
0x180012cb4  lea     r9, [rbp+57h+var_98]
0x180012cb8  lea     r8, [rbp+57h+arg_10]
0x180012cbc  lea     ecx, [rdx+1]
0x180012cbf  call    cs:__imp_WwanOpenHandle
0x180012cc5  mov     edi, eax
0x180012cc7  test    eax, eax
0x180012cc9  jle     short loc_180012CD8
0x180012ccb  jmp     short loc_180012CD2
0x180012ccd  mov     edi, 32h ; '2'
0x180012cd2  movzx   edi, di
0x180012cd5  or      edi, r15d
0x180012cd8  test    edi, edi
0x180012cda  jns     short loc_180012D0F
0x180012cdc  mov     rcx, cs:WPP_GLOBAL_Control
0x180012ce3  cmp     rcx, rsi
0x180012ce6  jz      loc_180013057
0x180012cec  test    byte ptr [rcx+1Ch], 1
0x180012cf0  jz      loc_180013036
0x180012cf6  mov     edx, 7Bh ; '{'
0x180012cfb  mov     rcx, [rcx+10h]
0x180012cff  mov     r9d, edi
0x180012d02  mov     r8, r13
0x180012d05  call    WPP_SF_d
0x180012d0a  jmp     loc_18001302F
0x180012d0f  mov     rcx, [rbp+57h+var_98]
0x180012d13  lea     rax, [rbp+57h+var_A0]
0x180012d17  lea     r8, [rbp+57h+var_78]
0x180012d1b  mov     [rbp+57h+var_80], rax
0x180012d1f  xor     edx, edx
0x180012d21  mov     [rbp+57h+var_78], rbx
0x180012d25  mov     [rbp+57h+var_70], 1
0x180012d29  call    cs:__imp_WwanEnumerateInterfaces
0x180012d2f  mov     edi, eax
0x180012d31  test    eax, eax
0x180012d33  jle     short loc_180012D3B
0x180012d35  movzx   edi, ax
0x180012d38  or      edi, r15d
0x180012d3b  cmp     [rbp+57h+var_70], bl
0x180012d3e  jz      short loc_180012D59
0x180012d40  mov     rdx, [rbp+57h+var_80]
0x180012d44  mov     rax, [rbp+57h+var_78]
0x180012d48  mov     rcx, [rdx]
0x180012d4b  mov     [rdx], rax
0x180012d4e  test    rcx, rcx
0x180012d51  jz      short loc_180012D59
0x180012d53  call    cs:__imp_WwanFreeMemory
0x180012d59  test    edi, edi
0x180012d5b  jns     short loc_180012D81
0x180012d5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180012d64  cmp     rcx, rsi
0x180012d67  jz      loc_180013057
0x180012d6d  test    byte ptr [rcx+1Ch], 1
0x180012d71  jz      loc_180013036
0x180012d77  mov     edx, 7Ch ; '|'
0x180012d7c  jmp     loc_180012CFB
0x180012d81  mov     rax, [rbp+57h+var_A0]
0x180012d85  mov     [rbp+57h+arg_8], ebx
0x180012d88  cmp     [rax], ebx
0x180012d8a  jnz     short loc_180012DC0
0x180012d8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180012d93  cmp     rcx, rsi
0x180012d96  jz      short loc_180012DB6
0x180012d98  test    byte ptr [rcx+1Ch], 1
0x180012d9c  jz      short loc_180012DB6
0x180012d9e  mov     rcx, [rcx+10h]
0x180012da2  mov     edx, 7Dh ; '}'
0x180012da7  mov     r8, r13
0x180012daa  call    WPP_SF_
0x180012daf  mov     rcx, cs:WPP_GLOBAL_Control
0x180012db6  mov     edi, 80070015h
0x180012dbb  jmp     loc_180013036
0x180012dc0  mov     rax, [rbp+57h+var_A0]
0x180012dc4  mov     r15b, bl
0x180012dc7  mov     [rbp+57h+arg_0], bl
0x180012dca  mov     r12d, ebx
0x180012dcd  movups  xmm0, xmmword ptr [rax+4]
0x180012dd1  movdqu  xmmword ptr [r14], xmm0
0x180012dd6  cmp     [rax], ebx
0x180012dd8  jbe     loc_1800130B3
0x180012dde  mov     rdx, [rbp+57h+var_A0]
0x180012de2  lea     rax, [rbp+57h+var_90]
0x180012de6  mov     rcx, [rbp+57h+var_98]
0x180012dea  xor     r9d, r9d
0x180012ded  mov     [rbp+57h+var_80], rax
0x180012df1  add     rdx, 4
0x180012df5  mov     [rsp+0E0h+var_A8], rbx
0x180012dfa  mov     eax, r12d
0x180012dfd  imul    r13, rax, 24Ch
0x180012e04  lea     rax, [rbp+57h+var_78]
0x180012e08  mov     [rsp+0E0h+var_B0], rbx
0x180012e0d  mov     [rsp+0E0h+var_B8], rax
0x180012e12  lea     r8d, [r9+1Ch]
0x180012e16  lea     rax, [rbp+57h+arg_8]
0x180012e1a  mov     [rbp+57h+var_78], rbx
0x180012e1e  add     rdx, r13
0x180012e21  mov     [rbp+57h+var_70], 1
0x180012e25  mov     [rsp+0E0h+var_C0], rax
0x180012e2a  call    cs:__imp_WwanQueryInterface
0x180012e30  mov     edi, eax
0x180012e32  test    eax, eax
0x180012e34  jle     short loc_180012E3F
0x180012e36  movzx   edi, ax
0x180012e39  or      edi, 80070000h
0x180012e3f  cmp     [rbp+57h+var_70], bl
0x180012e42  jz      short loc_180012E5D
0x180012e44  mov     rdx, [rbp+57h+var_80]
0x180012e48  mov     rax, [rbp+57h+var_78]
0x180012e4c  mov     rcx, [rdx]
0x180012e4f  mov     [rdx], rax
0x180012e52  test    rcx, rcx
0x180012e55  jz      short loc_180012E5D
0x180012e57  call    cs:__imp_WwanFreeMemory
0x180012e5d  test    edi, edi
0x180012e5f  jns     short loc_180012E98
0x180012e61  mov     rcx, cs:WPP_GLOBAL_Control
0x180012e68  cmp     rcx, rsi
0x180012e6b  jz      loc_180012FB3
0x180012e71  test    byte ptr [rcx+1Ch], 1
0x180012e75  jz      loc_180012FB3
0x180012e7b  mov     rcx, [rcx+10h]
0x180012e7f  lea     r8, WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids
0x180012e86  mov     edx, 7Eh ; '~'
0x180012e8b  mov     r9d, edi
0x180012e8e  call    WPP_SF_d
0x180012e93  jmp     loc_180012FAC
0x180012e98  cmp     [rbp+57h+var_90], rbx
0x180012e9c  jz      short loc_180012EA8
0x180012e9e  cmp     [rbp+57h+arg_8], 4
0x180012ea2  jnz     loc_180012FDB
0x180012ea8  mov     rax, [rbp+57h+var_90]
0x180012eac  mov     sil, bl
0x180012eaf  cmp     dword ptr [rax], 1
0x180012eb2  jnz     short loc_180012EF5
0x180012eb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180012ebb  lea     rax, WPP_GLOBAL_Control
0x180012ec2  cmp     rcx, rax
0x180012ec5  jz      short loc_180012EE2
0x180012ec7  test    byte ptr [rcx+1Ch], 4
0x180012ecb  jz      short loc_180012EE2
0x180012ecd  mov     rcx, [rcx+10h]
0x180012ed1  lea     r8, WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids
0x180012ed8  mov     edx, 80h
0x180012edd  call    WPP_SF_
0x180012ee2  mov     rax, [rbp+57h+var_A0]
0x180012ee6  mov     sil, 1
0x180012ee9  mov     [rbp+57h+arg_0], 1
0x180012eed  movups  xmm7, xmmword ptr [rax+r13+4]
0x180012ef3  jmp     short loc_180012EF9
0x180012ef5  mov     rax, [rbp+57h+var_A0]
0x180012ef9  mov     rcx, [rbp+57h+var_98]
0x180012efd  lea     rdx, [rax+4]
0x180012f01  mov     [rsp+0E0h+var_A8], rbx
0x180012f06  lea     rax, [rbp+57h+var_88]
0x180012f0a  xor     r9d, r9d
0x180012f0d  mov     [rsp+0E0h+var_B0], rbx
0x180012f12  mov     [rsp+0E0h+var_B8], rax
0x180012f17  add     rdx, r13
0x180012f1a  lea     rax, [rbp+57h+arg_18]
0x180012f1e  mov     [rbp+57h+var_88], rbx
0x180012f22  mov     [rsp+0E0h+var_C0], rax
0x180012f27  lea     r8d, [r9+7]
0x180012f2b  mov     [rbp+57h+arg_18], ebx
0x180012f2e  call    cs:__imp_WwanQueryInterface
0x180012f34  test    eax, eax
0x180012f36  jnz     short loc_180012FA5
0x180012f38  mov     rcx, [rbp+57h+var_88]
0x180012f3c  test    rcx, rcx
0x180012f3f  jz      short loc_180012FA5
0x180012f41  mov     ebx, [rcx+8E4h]
0x180012f47  call    cs:__imp_WwanFreeMemory
0x180012f4d  test    ebx, ebx
0x180012f4f  jnz     short loc_180012FA3
0x180012f51  mov     rcx, cs:WPP_GLOBAL_Control
0x180012f58  lea     rax, WPP_GLOBAL_Control
0x180012f5f  cmp     rcx, rax
0x180012f62  jz      short loc_180012F86
0x180012f64  test    byte ptr [rcx+1Ch], 4
0x180012f68  jz      short loc_180012F86
0x180012f6a  mov     rcx, [rcx+10h]
0x180012f6e  lea     r8, WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids
0x180012f75  mov     edx, 81h
0x180012f7a  call    WPP_SF_
0x180012f7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180012f86  mov     rax, [rbp+57h+var_A0]
0x180012f8a  xor     ebx, ebx
0x180012f8c  mov     r15b, 1
0x180012f8f  movups  xmm6, xmmword ptr [rax+r13+4]
0x180012f95  test    sil, sil
0x180012f98  jnz     short loc_180012FC3
0x180012f9a  lea     rsi, WPP_GLOBAL_Control
0x180012fa1  jmp     short loc_180012FB3
0x180012fa3  xor     ebx, ebx
0x180012fa5  lea     rsi, WPP_GLOBAL_Control
0x180012fac  mov     rcx, cs:WPP_GLOBAL_Control
0x180012fb3  mov     rax, [rbp+57h+var_A0]
0x180012fb7  inc     r12d
0x180012fba  cmp     r12d, [rax]
0x180012fbd  jb      loc_180012DDE
0x180012fc3  lea     rsi, WPP_GLOBAL_Control
0x180012fca  cmp     [rbp+57h+arg_0], bl
0x180012fcd  jz      short loc_180013007
0x180012fcf  test    r15b, r15b
0x180012fd2  jz      short loc_180013000
0x180012fd4  movdqu  xmmword ptr [r14], xmm6
0x180012fd9  jmp     short loc_18001302F
0x180012fdb  mov     edi, 80004005h
0x180012fe0  mov     rcx, cs:WPP_GLOBAL_Control
0x180012fe7  cmp     rcx, rsi
0x180012fea  jz      short loc_180013057
0x180012fec  test    byte ptr [rcx+1Ch], 1
0x180012ff0  jz      short loc_180013036
0x180012ff2  mov     edx, 7Fh
0x180012ff7  lea     r8, WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids
0x180012ffe  jmp     short loc_180013026
0x180013000  movdqu  xmmword ptr [r14], xmm7
0x180013005  jmp     short loc_18001302F
0x180013007  test    r15b, r15b
0x18001300a  jnz     short loc_180012FD4
0x18001300c  lea     r13, WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids
0x180013013  cmp     rcx, rsi
0x180013016  jz      short loc_180013057
0x180013018  test    byte ptr [rcx+1Ch], 4
0x18001301c  jz      short loc_180013036
0x18001301e  mov     edx, 82h
0x180013023  mov     r8, r13
0x180013026  mov     rcx, [rcx+10h]
0x18001302a  call    WPP_SF_
0x18001302f  mov     rcx, cs:WPP_GLOBAL_Control
0x180013036  cmp     rcx, rsi
0x180013039  jz      short loc_180013057
0x18001303b  test    byte ptr [rcx+1Ch], 8
0x18001303f  jz      short loc_180013057
0x180013041  mov     rcx, [rcx+10h]
0x180013045  mov     edx, 83h
0x18001304a  mov     r9d, edi
0x18001304d  mov     [rsp+0E0h+var_C0], r14
0x180013052  call    WPP_SF_d_guid_
0x180013057  mov     rcx, [rbp+57h+var_90]
0x18001305b  mov     [rbp+57h+var_90], rbx
0x18001305f  test    rcx, rcx
0x180013062  jz      short loc_18001306A
0x180013064  call    cs:__imp_WwanFreeMemory
0x18001306a  mov     rcx, [rbp+57h+var_A0]
0x18001306e  mov     [rbp+57h+var_A0], rbx
0x180013072  test    rcx, rcx
0x180013075  jz      short loc_18001307D
0x180013077  call    cs:__imp_WwanFreeMemory
0x18001307d  mov     rcx, [rbp+57h+var_98]
  ... truncated ...
```
