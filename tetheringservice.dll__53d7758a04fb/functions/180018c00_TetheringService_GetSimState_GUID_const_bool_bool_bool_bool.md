# TetheringService::GetSimState(_GUID const *,bool *,bool *,bool *,bool *)

- ea: `0x180018c00`
- end: `0x180018f5e`
- name: `?GetSimState@TetheringService@@AEAAJPEBU_GUID@@PEA_N111@Z`
- size: `862`
- prototype: `__int64 __fastcall(TetheringService *__hidden this, const struct _GUID *, bool *, bool *, bool *, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18001dc08`

## callees

- `0x1800035a8`
- `0x18000bf74`
- `0x18000f9a4`
- `0x180018c00`
- `0x180021aa8`

## import_xrefs

- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x180018cd6`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x180018d94`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x180018cd6`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x180018d94`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180018efc`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180018efc`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180018d60`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180018e4c`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180018d60`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180018e4c`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x180018c9c`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x180018c9c`

## pseudocode

```c
__int64 __fastcall TetheringService::GetSimState(
        TetheringService *this,
        const struct _GUID *a2,
        bool *a3,
        bool *a4,
        bool *a5,
        bool *a6)
{
  bool *v9; // r14
  bool *v10; // r15
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9
  unsigned int Interface; // ebx
  TetheringServiceTelemetry *v15; // rax
  __int64 v16; // rdx
  _DWORD *v17; // rcx
  char v18; // al
  unsigned int *v19; // rcx
  unsigned int v20; // edx
  __int64 v21; // rdi
  __int64 v22; // r11
  TetheringService **v24; // [rsp+20h] [rbp-30h]
  unsigned int **v25; // [rsp+28h] [rbp-28h]
  __int64 v26; // [rsp+30h] [rbp-20h]
  __int64 v27; // [rsp+38h] [rbp-18h]
  _DWORD *v28; // [rsp+40h] [rbp-10h] BYREF
  unsigned int *v29; // [rsp+48h] [rbp-8h] BYREF
  TetheringService *v30; // [rsp+90h] [rbp+40h] BYREF
  int v31; // [rsp+A0h] [rbp+50h] BYREF
  __int64 v32; // [rsp+A8h] [rbp+58h] BYREF

  v30 = this;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 402, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, a2);
  }
  v9 = a5;
  v10 = a6;
  *a3 = 0;
  *a4 = 0;
  *v9 = 0;
  *v10 = 0;
  v32 = 0;
  v31 = 0;
  v28 = 0;
  LODWORD(v30) = 0;
  v29 = 0;
  if ( !(unsigned __int8)IsWwanOpenHandlePresent() )
  {
    Interface = 50;
    goto LABEL_39;
  }
  Interface = WwanOpenHandle(1, 0, &v31, &v32);
  if ( Interface )
  {
LABEL_39:
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v16 = 403;
      goto LABEL_42;
    }
    goto LABEL_45;
  }
  v27 = 0;
  HIDWORD(v26) = 0;
  v25 = &v28;
  v24 = &v30;
  Interface = WwanQueryInterface(v32, a2, 7);
  if ( Interface )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v16 = 404;
LABEL_42:
      v13 = Interface;
      goto LABEL_43;
    }
    goto LABEL_45;
  }
  v17 = v28;
  if ( !v28 )
  {
    v13 = 2147549183LL;
    Interface = -2147418113;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_45;
    }
    v16 = 405;
    goto LABEL_43;
  }
  if ( !v28[256] )
  {
    *a3 = v28[228] == 2;
    *a4 = v17[228] == 1;
  }
  if ( !v17[261] )
  {
    if ( v17[260] != 1 || (v18 = 1, v17[259] != 1) )
      v18 = 0;
    *v9 = v18;
  }
  WwanFreeMemory(v17);
  v27 = 0;
  HIDWORD(v26) = 0;
  v25 = &v29;
  v28 = 0;
  v24 = &v30;
  Interface = WwanQueryInterface(v32, a2, 15);
  if ( !Interface )
  {
    v19 = v29;
    if ( v29 )
    {
      v20 = 0;
      if ( *v29 )
      {
        v21 = WWAN_PROFILE_SET_GUID_INTERNET_AO;
        v22 = WWAN_PROFILE_SET_GUID_ALL_HOST_PROFILES;
        do
        {
          if ( *(_QWORD *)&v19[5 * v20 + 1] == v21 && *(_QWORD *)&v19[5 * v20 + 3] == 0x5F5157C6F13398A1LL
            || *(_QWORD *)&v19[5 * v20 + 1] == v22 && *(_QWORD *)&v19[5 * v20 + 3] == 0x5770A73BA7DDA38FLL )
          {
            *v10 = v19[5 * v20 + 5] == 1;
            v21 = WWAN_PROFILE_SET_GUID_INTERNET_AO;
            v22 = WWAN_PROFILE_SET_GUID_ALL_HOST_PROFILES;
          }
          ++v20;
        }
        while ( v20 < *v19 );
      }
      WwanFreeMemory(v19);
      v29 = 0;
      goto LABEL_44;
    }
    v13 = 2147549183LL;
    Interface = -2147418113;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_45;
    }
    v16 = 407;
LABEL_43:
    WPP_SF_d(*((_QWORD *)v15 + 2), v16, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, v13);
LABEL_44:
    v15 = WPP_GLOBAL_Control;
    goto LABEL_45;
  }
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v16 = 406;
    goto LABEL_42;
  }
LABEL_45:
  if ( v32 )
  {
    WwanCloseHandle(v32, 0);
    v15 = WPP_GLOBAL_Control;
    v32 = 0;
  }
  if ( (int)Interface > 0 )
    Interface = (unsigned __int16)Interface | 0x80070000;
  if ( v15 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 8) != 0 )
  {
    LOBYTE(v13) = *a4;
    LODWORD(v26) = Interface;
    LOBYTE(v25) = *v10;
    LOBYTE(v24) = *v9;
    WPP_SF_cccd(*((_QWORD *)v15 + 2), v11, v12, v13, v24, v25, v26, v27);
  }
  return Interface;
}

```

## disassembly

```asm
0x180018c00  mov     [rsp-38h+arg_8], rbx
0x180018c05  mov     [rsp-38h+arg_0], rcx
0x180018c0a  push    rbp
0x180018c0b  push    rsi
0x180018c0c  push    rdi
0x180018c0d  push    r12
0x180018c0f  push    r13
0x180018c11  push    r14
0x180018c13  push    r15
0x180018c15  mov     rbp, rsp
0x180018c18  sub     rsp, 50h
0x180018c1c  mov     r12, r9
0x180018c1f  mov     rdi, r8
0x180018c22  mov     rsi, rdx
0x180018c25  mov     rcx, cs:WPP_GLOBAL_Control
0x180018c2c  lea     rax, WPP_GLOBAL_Control
0x180018c33  cmp     rcx, rax
0x180018c36  jz      short loc_180018C56
0x180018c38  test    byte ptr [rcx+1Ch], 8
0x180018c3c  jz      short loc_180018C56
0x180018c3e  mov     rcx, [rcx+10h]
0x180018c42  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x180018c49  mov     edx, 192h
0x180018c4e  mov     r9, rsi
0x180018c51  call    WPP_SF__guid_
0x180018c56  mov     r14, [rbp+arg_20]
0x180018c5a  xor     r13d, r13d
0x180018c5d  mov     r15, [rbp+arg_28]
0x180018c61  mov     [rdi], r13b
0x180018c64  mov     [r12], r13b
0x180018c68  mov     [r14], r13b
0x180018c6b  mov     [r15], r13b
0x180018c6e  mov     [rbp+arg_18], r13
0x180018c72  mov     [rbp+arg_10], r13d
0x180018c76  mov     [rbp+var_10], r13
0x180018c7a  mov     dword ptr [rbp+arg_0], r13d
0x180018c7e  mov     [rbp+var_8], r13
0x180018c82  call    IsWwanOpenHandlePresent
0x180018c87  test    al, al
0x180018c89  jz      loc_180018EB4
0x180018c8f  xor     edx, edx
0x180018c91  lea     r9, [rbp+arg_18]
0x180018c95  lea     r8, [rbp+arg_10]
0x180018c99  lea     ecx, [rdx+1]
0x180018c9c  call    cs:__imp_WwanOpenHandle
0x180018ca2  mov     ebx, eax
0x180018ca4  test    eax, eax
0x180018ca6  jnz     loc_180018EB9
0x180018cac  mov     rcx, [rbp+arg_18]
0x180018cb0  lea     rax, [rbp+var_10]
0x180018cb4  mov     [rsp+50h+var_18], r13
0x180018cb9  lea     r8d, [r13+7]
0x180018cbd  mov     [rsp+50h+var_20], r13
0x180018cc2  xor     r9d, r9d
0x180018cc5  mov     [rsp+50h+var_28], rax
0x180018cca  mov     rdx, rsi
0x180018ccd  lea     rax, [rbp+arg_0]
0x180018cd1  mov     [rsp+50h+var_30], rax
0x180018cd6  call    cs:__imp_WwanQueryInterface
0x180018cdc  mov     ebx, eax
0x180018cde  test    eax, eax
0x180018ce0  jz      short loc_180018D0D
0x180018ce2  mov     rax, cs:WPP_GLOBAL_Control
0x180018ce9  lea     rdi, WPP_GLOBAL_Control
0x180018cf0  cmp     rax, rdi
0x180018cf3  jz      loc_180018EF1
0x180018cf9  test    byte ptr [rax+1Ch], 1
0x180018cfd  jz      loc_180018EF1
0x180018d03  mov     edx, 194h
0x180018d08  jmp     loc_180018ED7
0x180018d0d  mov     rcx, [rbp+var_10]
0x180018d11  test    rcx, rcx
0x180018d14  jz      loc_180018E8B
0x180018d1a  cmp     [rcx+400h], r13d
0x180018d21  jnz     short loc_180018D3D
0x180018d23  cmp     dword ptr [rcx+390h], 2
0x180018d2a  setz    al
0x180018d2d  mov     [rdi], al
0x180018d2f  cmp     dword ptr [rcx+390h], 1
0x180018d36  setz    al
0x180018d39  mov     [r12], al
0x180018d3d  cmp     [rcx+414h], r13d
0x180018d44  jnz     short loc_180018D60
0x180018d46  cmp     dword ptr [rcx+410h], 1
0x180018d4d  jnz     short loc_180018D5A
0x180018d4f  cmp     dword ptr [rcx+40Ch], 1
0x180018d56  mov     al, 1
0x180018d58  jz      short loc_180018D5D
0x180018d5a  mov     al, r13b
0x180018d5d  mov     [r14], al
0x180018d60  call    cs:__imp_WwanFreeMemory
0x180018d66  mov     rcx, [rbp+arg_18]
0x180018d6a  lea     rax, [rbp+var_8]
0x180018d6e  mov     [rsp+50h+var_18], r13
0x180018d73  xor     r9d, r9d
0x180018d76  mov     [rsp+50h+var_20], r13
0x180018d7b  mov     rdx, rsi
0x180018d7e  mov     [rsp+50h+var_28], rax
0x180018d83  lea     rax, [rbp+arg_0]
0x180018d87  mov     [rbp+var_10], r13
0x180018d8b  lea     r8d, [r9+0Fh]
0x180018d8f  mov     [rsp+50h+var_30], rax
0x180018d94  call    cs:__imp_WwanQueryInterface
0x180018d9a  mov     ebx, eax
0x180018d9c  test    eax, eax
0x180018d9e  jz      short loc_180018DCB
0x180018da0  mov     rax, cs:WPP_GLOBAL_Control
0x180018da7  lea     rdi, WPP_GLOBAL_Control
0x180018dae  cmp     rax, rdi
0x180018db1  jz      loc_180018EF1
0x180018db7  test    byte ptr [rax+1Ch], 1
0x180018dbb  jz      loc_180018EF1
0x180018dc1  mov     edx, 196h
0x180018dc6  jmp     loc_180018ED7
0x180018dcb  mov     rcx, [rbp+var_8]
0x180018dcf  test    rcx, rcx
0x180018dd2  jz      loc_180018E62
0x180018dd8  mov     edx, r13d
0x180018ddb  cmp     [rcx], r13d
0x180018dde  jbe     short loc_180018E4C
0x180018de0  mov     r10, cs:qword_1800365B0
0x180018de7  mov     rdi, cs:WWAN_PROFILE_SET_GUID_INTERNET_AO
0x180018dee  mov     r9, cs:qword_1800365D0
0x180018df5  mov     r11, cs:WWAN_PROFILE_SET_GUID_ALL_HOST_PROFILES
0x180018dfc  mov     eax, edx
0x180018dfe  lea     r8, [rax+rax*4]
0x180018e02  cmp     [rcx+r8*4+4], rdi
0x180018e07  jnz     short loc_180018E10
0x180018e09  cmp     [rcx+r8*4+0Ch], r10
0x180018e0e  jz      short loc_180018E1E
0x180018e10  cmp     [rcx+r8*4+4], r11
0x180018e15  jnz     short loc_180018E46
0x180018e17  cmp     [rcx+r8*4+0Ch], r9
0x180018e1c  jnz     short loc_180018E46
0x180018e1e  cmp     dword ptr [rcx+r8*4+14h], 1
0x180018e24  setz    al
0x180018e27  mov     [r15], al
0x180018e2a  mov     r10, cs:qword_1800365B0
0x180018e31  mov     rdi, cs:WWAN_PROFILE_SET_GUID_INTERNET_AO
0x180018e38  mov     r9, cs:qword_1800365D0
0x180018e3f  mov     r11, cs:WWAN_PROFILE_SET_GUID_ALL_HOST_PROFILES
0x180018e46  inc     edx
0x180018e48  cmp     edx, [rcx]
0x180018e4a  jb      short loc_180018DFC
0x180018e4c  call    cs:__imp_WwanFreeMemory
0x180018e52  mov     [rbp+var_8], r13
0x180018e56  lea     rdi, WPP_GLOBAL_Control
0x180018e5d  jmp     loc_180018EEA
0x180018e62  mov     r9d, 8000FFFFh
0x180018e68  mov     ebx, r9d
0x180018e6b  mov     rax, cs:WPP_GLOBAL_Control
0x180018e72  lea     rdi, WPP_GLOBAL_Control
0x180018e79  cmp     rax, rdi
0x180018e7c  jz      short loc_180018EF1
0x180018e7e  test    byte ptr [rax+1Ch], 1
0x180018e82  jz      short loc_180018EF1
0x180018e84  mov     edx, 197h
0x180018e89  jmp     short loc_180018EDA
0x180018e8b  mov     r9d, 8000FFFFh
0x180018e91  mov     ebx, r9d
0x180018e94  mov     rax, cs:WPP_GLOBAL_Control
0x180018e9b  lea     rdi, WPP_GLOBAL_Control
0x180018ea2  cmp     rax, rdi
0x180018ea5  jz      short loc_180018EF1
0x180018ea7  test    byte ptr [rax+1Ch], 1
0x180018eab  jz      short loc_180018EF1
0x180018ead  mov     edx, 195h
0x180018eb2  jmp     short loc_180018EDA
0x180018eb4  mov     ebx, 32h ; '2'
0x180018eb9  mov     rax, cs:WPP_GLOBAL_Control
0x180018ec0  lea     rdi, WPP_GLOBAL_Control
0x180018ec7  cmp     rax, rdi
0x180018eca  jz      short loc_180018EF1
0x180018ecc  test    byte ptr [rax+1Ch], 1
0x180018ed0  jz      short loc_180018EF1
0x180018ed2  mov     edx, 193h
0x180018ed7  mov     r9d, ebx
0x180018eda  mov     rcx, [rax+10h]
0x180018ede  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x180018ee5  call    WPP_SF_d
0x180018eea  mov     rax, cs:WPP_GLOBAL_Control
0x180018ef1  mov     rcx, [rbp+arg_18]
0x180018ef5  test    rcx, rcx
0x180018ef8  jz      short loc_180018F0D
0x180018efa  xor     edx, edx
0x180018efc  call    cs:__imp_WwanCloseHandle
0x180018f02  mov     rax, cs:WPP_GLOBAL_Control
0x180018f09  mov     [rbp+arg_18], r13
0x180018f0d  test    ebx, ebx
0x180018f0f  jle     short loc_180018F1A
0x180018f11  movzx   ebx, bx
0x180018f14  or      ebx, 80070000h
0x180018f1a  cmp     rax, rdi
0x180018f1d  jz      short loc_180018F44
0x180018f1f  test    byte ptr [rax+1Ch], 8
0x180018f23  jz      short loc_180018F44
0x180018f25  mov     cl, [r15]
0x180018f28  mov     r9b, [r12]
0x180018f2c  mov     dword ptr [rsp+50h+var_20], ebx
0x180018f30  mov     byte ptr [rsp+50h+var_28], cl
0x180018f34  mov     cl, [r14]
0x180018f37  mov     byte ptr [rsp+50h+var_30], cl
0x180018f3b  mov     rcx, [rax+10h]
0x180018f3f  call    WPP_SF_cccd
0x180018f44  mov     eax, ebx
0x180018f46  mov     rbx, [rsp+50h+arg_8]
0x180018f4e  add     rsp, 50h
0x180018f52  pop     r15
0x180018f54  pop     r14
0x180018f56  pop     r13
0x180018f58  pop     r12
0x180018f5a  pop     rdi
0x180018f5b  pop     rsi
0x180018f5c  pop     rbp
0x180018f5d  retn
```
