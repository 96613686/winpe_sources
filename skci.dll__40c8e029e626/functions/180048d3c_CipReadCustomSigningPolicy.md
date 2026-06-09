# CipReadCustomSigningPolicy

- ea: `0x180048d3c`
- end: `0x1800492f2`
- name: `CipReadCustomSigningPolicy`
- size: `1462`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180010bd4`

## callees

- `0x180006f10`
- `0x1800162b4`
- `0x180033980`
- `0x1800479a8`
- `0x180048d3c`

## import_xrefs

- `securekernel!SkFreePool` at `0x180049019`
- `securekernel!SkFreePool` at `0x1800492c3`
- `securekernel!SkFreePool` at `0x180049019`
- `securekernel!SkFreePool` at `0x1800492c3`
- `securekernel!SeQuerySecureBootPolicyValue` at `0x180048dde`
- `securekernel!SeQuerySecureBootPolicyValue` at `0x180048e94`
- `securekernel!SeQuerySecureBootPolicyValue` at `0x180048f22`
- `securekernel!SeQuerySecureBootPolicyValue` at `0x1800491b0`
- `securekernel!SeQuerySecureBootPolicyValue` at `0x180049210`
- `securekernel!SeQuerySecureBootPolicyValue` at `0x18004926c`
- `securekernel!SeQuerySecureBootPolicyValue` at `0x180048dde`
- `securekernel!SeQuerySecureBootPolicyValue` at `0x180048e94`
- `securekernel!SeQuerySecureBootPolicyValue` at `0x180048f22`
- `securekernel!SeQuerySecureBootPolicyValue` at `0x1800491b0`
- `securekernel!SeQuerySecureBootPolicyValue` at `0x180049210`
- `securekernel!SeQuerySecureBootPolicyValue` at `0x18004926c`
- `securekernel!_ultow_s` at `0x180048e49`
- `securekernel!_ultow_s` at `0x180048e49`
- `securekernel!RtlInitUnicodeString` at `0x180048e65`
- `securekernel!RtlInitUnicodeString` at `0x180048e65`

## pseudocode

```c
__int64 CipReadCustomSigningPolicy()
{
  int v0; // r12d
  unsigned int v1; // ebx
  void *v2; // r15
  unsigned int i; // esi
  __int64 v4; // r14
  __int64 v5; // rdi
  int v6; // eax
  int v7; // eax
  int v8; // eax
  int v9; // edx
  _BYTE *v10; // r10
  int v11; // ecx
  unsigned __int8 *v12; // r8
  __int64 v13; // r9
  unsigned int v14; // ecx
  int v15; // esi
  unsigned int v16; // r13d
  __int64 v17; // rdi
  __int64 v18; // r14
  __int64 v19; // r15
  int SecureBootPolicyValue; // eax
  int v21; // edx
  __int64 v22; // r14
  int v23; // eax
  int v24; // ecx
  int v25; // eax
  unsigned int v27; // [rsp+30h] [rbp-59h] BYREF
  int v28; // [rsp+34h] [rbp-55h] BYREF
  int v29; // [rsp+38h] [rbp-51h] BYREF
  unsigned int v30; // [rsp+3Ch] [rbp-4Dh] BYREF
  unsigned int v31; // [rsp+40h] [rbp-49h] BYREF
  int v32; // [rsp+44h] [rbp-45h] BYREF
  int v33; // [rsp+48h] [rbp-41h] BYREF
  int v34; // [rsp+4Ch] [rbp-3Dh] BYREF
  void *PoolHelper; // [rsp+50h] [rbp-39h]
  _BYTE *v36; // [rsp+58h] [rbp-31h] BYREF
  __int64 v37; // [rsp+60h] [rbp-29h] BYREF
  UNICODE_STRING DestinationString; // [rsp+68h] [rbp-21h] BYREF
  WCHAR SourceString[12]; // [rsp+78h] [rbp-11h] BYREF
  __int64 v40; // [rsp+90h] [rbp+7h]

  v0 = 0;
  v36 = 0;
  v40 = 0;
  DestinationString = 0;
  v34 = 0;
  v27 = 0;
  v33 = 0;
  v32 = 0;
  v29 = 0;
  wcscpy(SourceString, L"CI\\Signers\\");
  v30 = 0;
  v37 = 0;
  v31 = 0;
  v28 = 0;
  if ( (int)SeQuerySecureBootPolicyValue(&qword_180035CA0, &qword_180035CB0, 2, &v30, 4, &v28) < 0 )
    return 0;
  PoolHelper = SkAllocatePoolHelper(258, 40LL * v30, 1668499779);
  v2 = PoolHelper;
  if ( !PoolHelper )
    return (unsigned int)-1073741801;
  for ( i = 0; ; ++i )
  {
    if ( i >= v30 )
    {
      if ( (g_CiOptions & 8) != 0 )
      {
        g_CiSignerTypeMax = 2;
        v15 = 2;
      }
      else
      {
        v15 = ((unsigned __int8)g_CiDeveloperMode >> 2) & 1;
        g_CiSignerTypeMax = 0;
      }
      v16 = 0;
      g_CipCustomLevelComparisons = xmmword_180037E40;
      xmmword_18003F670 = xmmword_180037E50;
      xmmword_18003F680 = xmmword_180037E60;
      xmmword_18003F690 = xmmword_180037E70;
      while ( v16 < 0x13 )
      {
        v17 = v16;
        v18 = 12LL * v16;
        v19 = 2LL * v16;
        while ( v0 <= v15 )
        {
          v19 = 2LL * v16;
          SecureBootPolicyValue = CipAllocateAndQuerySecureBootPolicyValue(
                                    0x180000000LL + v19 * 8 + 219920,
                                    (unsigned int)&asc_180035CC0[8 * v0],
                                    4,
                                    (unsigned int)&v37,
                                    (__int64)&v31);
          v1 = SecureBootPolicyValue;
          if ( SecureBootPolicyValue < 0 )
          {
            if ( SecureBootPolicyValue != -1073741772 )
              goto LABEL_59;
            dword_18003F1D0[v18 + v0] = 0;
          }
          else
          {
            v31 >>= 2;
            v21 = v31;
            v18 = 12LL * v16;
            qword_18003F1B8[6 * v16 + v0] = v37;
            dword_18003F1D0[v0 + v18] = v21;
          }
          ++v0;
        }
        v22 = *((unsigned __int8 *)&qword_180037DC0[8] + v16);
        v0 = 0;
        if ( (_BYTE)v22 )
        {
          v23 = SeQuerySecureBootPolicyValue(&qword_180035B10[v19], &qword_180035C80, 2, &v29, 4, &v28);
          v1 = v23;
          if ( v23 < 0 )
          {
            if ( v23 != -1073741772 )
              goto LABEL_59;
          }
          else
          {
            *((_DWORD *)&g_CipCustomLevelComparisons + v22) = v29;
          }
        }
        if ( (int)SeQuerySecureBootPolicyValue(&qword_180035B10[v19], L"\b\n", 2, &v27, 4, &v28) >= 0 )
        {
          v24 = v27;
        }
        else
        {
          v24 = 32780;
          v27 = 32780;
        }
        ++v16;
        g_CiScenarios[12 * v17] = v24;
      }
      v25 = SeQuerySecureBootPolicyValue(&qword_180035C40, L"&(", 2, &v29, 4, &v28);
      v1 = v25;
      if ( v25 < 0 )
      {
        if ( v25 != -1073741772 )
        {
LABEL_59:
          v2 = PoolHelper;
          goto LABEL_60;
        }
      }
      else
      {
        g_CipCustomRuntimeCustomizableLevels = v29;
      }
      v1 = 0;
      g_CipWhichLevelComparisons = &g_CipCustomLevelComparisons;
      g_CiSignersCount = v30;
      g_CiSigners = (__int64)PoolHelper;
      return v1;
    }
    if ( _ultow_s(i, &SourceString[11], 5u, 10) )
      goto LABEL_34;
    RtlInitUnicodeString(&DestinationString, SourceString);
    if ( (int)SeQuerySecureBootPolicyValue(&DestinationString, &qword_180035C60, 2, &v32, 4, &v28) >= 0 && v32 )
    {
      v4 = i;
      v5 = (__int64)v2 + 40 * i;
      *(_DWORD *)v5 = v32;
      *(_DWORD *)(v5 + 8) = 0;
      goto LABEL_18;
    }
    v4 = i;
    v5 = (__int64)v2 + 40 * i;
    *(_DWORD *)v5 = 0;
    v6 = CipAllocateAndQuerySecureBootPolicyValue(
           (unsigned int)&DestinationString,
           (unsigned int)&qword_180035D20,
           10,
           (int)v5 + 16,
           v5 + 8);
    v1 = v6;
    if ( v6 < 0 )
      break;
    if ( (int)SeQuerySecureBootPolicyValue(&DestinationString, L"\b\n", 2, &v27, 4, &v28) >= 0 )
    {
      v7 = v27;
    }
    else
    {
      v7 = 32780;
      v27 = 32780;
    }
    *(_DWORD *)(v5 + 4) = v7;
    if ( (int)MinCrypK_GetHashLength(v27, &v33) < 0 || v33 != *(_DWORD *)(v5 + 8) )
      goto LABEL_34;
    v0 = 0;
LABEL_18:
    v8 = CipAllocateAndQuerySecureBootPolicyValue(
           (unsigned int)&DestinationString,
           (unsigned int)L"\b\n",
           10,
           (unsigned int)&v36,
           (__int64)&v34);
    v1 = v8;
    if ( v8 >= 0 )
    {
      v10 = v36;
      if ( !v34 || !*v36 )
        goto LABEL_32;
      v11 = v34 - 1;
      v9 = 0;
      v12 = v36 + 1;
      while ( v11 )
      {
        v13 = *v12;
        if ( (unsigned int)(v13 - 1) > 0x7E )
          goto LABEL_32;
        v14 = v11 - 1;
        if ( (unsigned int)v13 > v14 )
          goto LABEL_32;
        ++v9;
        v11 = v14 - v13;
        v12 += v13 + 1;
      }
      if ( v9 != (unsigned __int8)*v36 || !v9 )
      {
LABEL_32:
        SkFreePool(1, v36);
        goto LABEL_34;
      }
      v5 = (__int64)v2 + 40 * v4;
      *(_DWORD *)(v5 + 28) = v34 - 1;
      *(_QWORD *)(v5 + 32) = v10 + 1;
    }
    else
    {
      if ( v8 != -1073741772 )
        goto LABEL_60;
      v9 = 0;
    }
    *(_DWORD *)(v5 + 24) = v9;
  }
  if ( v6 == -1073741772 )
LABEL_34:
    v1 = -1069350909;
LABEL_60:
  SkFreePool(1, v2);
  return v1;
}

```

## disassembly

```asm
0x180048d3c  push    rbp
0x180048d3e  push    rbx
0x180048d3f  push    rsi
0x180048d40  push    rdi
0x180048d41  push    r12
0x180048d43  push    r13
0x180048d45  push    r14
0x180048d47  push    r15
0x180048d49  lea     rbp, [rsp-1Fh]
0x180048d4e  sub     rsp, 0A8h
0x180048d55  mov     rax, cs:__security_cookie
0x180048d5c  xor     rax, rsp
0x180048d5f  mov     [rbp+57h+var_48], rax
0x180048d63  movups  xmm1, xmmword ptr cs:aCiSigners; "CI\\Signers\\"
0x180048d6a  xor     r12d, r12d
0x180048d6d  lea     r9, [rbp+57h+var_A4]
0x180048d71  xor     eax, eax
0x180048d73  mov     [rbp+57h+var_88], r12
0x180048d77  xorps   xmm0, xmm0
0x180048d7a  mov     [rbp+57h+var_50], rax
0x180048d7e  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180048d82  lea     rax, [rbp+57h+var_AC]
0x180048d86  mov     [rbp+57h+var_94], r12d
0x180048d8a  movsd   xmm0, qword ptr cs:aCiSigners+10h; "rs\\"
0x180048d92  lea     edi, [r12+2]
0x180048d97  mov     [rsp+0E0h+var_B8], rax
0x180048d9c  lea     rdx, qword_180035CB0
0x180048da3  mov     r8d, edi
0x180048da6  mov     [rbp+57h+var_B0], r12d
0x180048daa  lea     rcx, qword_180035CA0
0x180048db1  mov     [rbp+57h+var_98], r12d
0x180048db5  mov     [rbp+57h+var_9C], r12d
0x180048db9  mov     [rbp+57h+var_A8], r12d
0x180048dbd  movups  xmmword ptr [rbp+57h+SourceString], xmm1
0x180048dc1  mov     [rbp+57h+var_A4], r12d
0x180048dc5  movsd   qword ptr [rbp+57h+DstBuf], xmm0
0x180048dca  mov     [rbp+57h+var_80], r12
0x180048dce  mov     [rbp+57h+var_A0], r12d
0x180048dd2  mov     [rbp+57h+var_AC], r12d
0x180048dd6  mov     dword ptr [rsp+0E0h+var_C0], 4
0x180048dde  call    cs:__imp_SeQuerySecureBootPolicyValue
0x180048de5  nop     dword ptr [rax+rax+00h]
0x180048dea  test    eax, eax
0x180048dec  jns     short loc_180048DF6
0x180048dee  mov     ebx, r12d
0x180048df1  jmp     loc_1800492CF
0x180048df6  mov     eax, [rbp+57h+var_A4]
0x180048df9  mov     ecx, 102h
0x180048dfe  mov     r8d, 63734943h
0x180048e04  lea     rdx, [rax+rax*4]
0x180048e08  shl     rdx, 3
0x180048e0c  call    SkAllocatePoolHelper
0x180048e11  mov     [rbp+57h+var_90], rax
0x180048e15  mov     r15, rax
0x180048e18  test    rax, rax
0x180048e1b  jnz     short loc_180048E27
0x180048e1d  mov     ebx, 0C0000017h
0x180048e22  jmp     loc_1800492CF
0x180048e27  mov     esi, r12d
0x180048e2a  mov     r13d, 0C0000034h
0x180048e30  cmp     esi, [rbp+57h+var_A4]
0x180048e33  jnb     loc_18004903A
0x180048e39  mov     r9d, 0Ah; Radix
0x180048e3f  lea     rdx, [rbp+57h+DstBuf+6]; DstBuf
0x180048e43  mov     ecx, esi; Val
0x180048e45  lea     r8d, [r9-5]; SizeInWords
0x180048e49  call    cs:__imp__ultow_s
0x180048e50  nop     dword ptr [rax+rax+00h]
0x180048e55  test    eax, eax
0x180048e57  jnz     loc_180049030
0x180048e5d  lea     rdx, [rbp+57h+SourceString]; SourceString
0x180048e61  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180048e65  call    cs:__imp_RtlInitUnicodeString
0x180048e6c  nop     dword ptr [rax+rax+00h]
0x180048e71  lea     rax, [rbp+57h+var_AC]
0x180048e75  mov     r8d, edi
0x180048e78  mov     [rsp+0E0h+var_B8], rax
0x180048e7d  lea     r9, [rbp+57h+var_9C]
0x180048e81  lea     rdx, qword_180035C60
0x180048e88  mov     dword ptr [rsp+0E0h+var_C0], 4
0x180048e90  lea     rcx, [rbp+57h+DestinationString]
0x180048e94  call    cs:__imp_SeQuerySecureBootPolicyValue
0x180048e9b  nop     dword ptr [rax+rax+00h]
0x180048ea0  test    eax, eax
0x180048ea2  js      short loc_180048EC1
0x180048ea4  mov     ecx, [rbp+57h+var_9C]
0x180048ea7  test    ecx, ecx
0x180048ea9  jz      short loc_180048EC1
0x180048eab  mov     r14d, esi
0x180048eae  lea     rax, [r14+r14*4]
0x180048eb2  lea     rdi, [r15+rax*8]
0x180048eb6  mov     [rdi], ecx
0x180048eb8  mov     [rdi+8], r12d
0x180048ebc  jmp     loc_180048F66
0x180048ec1  mov     r14d, esi
0x180048ec4  lea     rdx, qword_180035D20
0x180048ecb  mov     r8d, 0Ah
0x180048ed1  lea     rcx, [rbp+57h+DestinationString]
0x180048ed5  lea     rax, [r14+r14*4]
0x180048ed9  lea     rdi, [r15+rax*8]
0x180048edd  mov     [rdi], r12d
0x180048ee0  lea     r9, [rdi+10h]
0x180048ee4  lea     r12, [rdi+8]
0x180048ee8  mov     [rsp+0E0h+var_C0], r12
0x180048eed  call    CipAllocateAndQuerySecureBootPolicyValue
0x180048ef2  mov     ebx, eax
0x180048ef4  test    eax, eax
0x180048ef6  js      loc_180049027
0x180048efc  lea     rax, [rbp+57h+var_AC]
0x180048f00  mov     r8d, 2
0x180048f06  mov     [rsp+0E0h+var_B8], rax
0x180048f0b  lea     r9, [rbp+57h+var_B0]
0x180048f0f  lea     rdx, asc_180035C50; "\b\n"
0x180048f16  mov     dword ptr [rsp+0E0h+var_C0], 4
0x180048f1e  lea     rcx, [rbp+57h+DestinationString]
0x180048f22  call    cs:__imp_SeQuerySecureBootPolicyValue
0x180048f29  nop     dword ptr [rax+rax+00h]
0x180048f2e  test    eax, eax
0x180048f30  jns     short loc_180048F3C
0x180048f32  mov     eax, 800Ch
0x180048f37  mov     [rbp+57h+var_B0], eax
0x180048f3a  jmp     short loc_180048F3F
0x180048f3c  mov     eax, [rbp+57h+var_B0]
0x180048f3f  mov     [rdi+4], eax
0x180048f42  lea     rdx, [rbp+57h+var_98]
0x180048f46  mov     ecx, [rbp+57h+var_B0]
0x180048f49  call    MinCrypK_GetHashLength
0x180048f4e  test    eax, eax
0x180048f50  js      loc_180049030
0x180048f56  mov     eax, [r12]
0x180048f5a  cmp     [rbp+57h+var_98], eax
0x180048f5d  jnz     loc_180049030
0x180048f63  xor     r12d, r12d
0x180048f66  lea     rax, [rbp+57h+var_94]
0x180048f6a  mov     r8d, 0Ah
0x180048f70  lea     r9, [rbp+57h+var_88]
0x180048f74  mov     [rsp+0E0h+var_C0], rax
0x180048f79  lea     rdx, asc_180035D30; "\b\n"
0x180048f80  lea     rcx, [rbp+57h+DestinationString]
0x180048f84  call    CipAllocateAndQuerySecureBootPolicyValue
0x180048f89  mov     ebx, eax
0x180048f8b  test    eax, eax
0x180048f8d  jns     short loc_180048F9D
0x180048f8f  cmp     eax, r13d
0x180048f92  jnz     loc_1800492BB
0x180048f98  mov     edx, r12d
0x180048f9b  jmp     short loc_180049002
0x180048f9d  mov     ebx, [rbp+57h+var_94]
0x180048fa0  mov     ecx, ebx
0x180048fa2  mov     r10, [rbp+57h+var_88]
0x180048fa6  test    ebx, ebx
0x180048fa8  jz      short loc_180049011
0x180048faa  movzx   r11d, byte ptr [r10]
0x180048fae  mov     r8, r10
0x180048fb1  test    r11d, r11d
0x180048fb4  jz      short loc_180049011
0x180048fb6  dec     ecx
0x180048fb8  mov     edx, r12d
0x180048fbb  inc     r8
0x180048fbe  test    ecx, ecx
0x180048fc0  jz      short loc_180048FE3
0x180048fc2  movzx   r9d, byte ptr [r8]
0x180048fc6  lea     eax, [r9-1]
0x180048fca  cmp     eax, 7Eh ; '~'
0x180048fcd  ja      short loc_180049011
0x180048fcf  dec     ecx
0x180048fd1  cmp     r9d, ecx
0x180048fd4  ja      short loc_180049011
0x180048fd6  inc     edx
0x180048fd8  sub     ecx, r9d
0x180048fdb  inc     r8
0x180048fde  add     r8, r9
0x180048fe1  jmp     short loc_180048FBE
0x180048fe3  cmp     edx, r11d
0x180048fe6  jnz     short loc_180049011
0x180048fe8  test    edx, edx
0x180048fea  jz      short loc_180049011
0x180048fec  lea     rax, [r14+r14*4]
0x180048ff0  lea     rdi, [r15+rax*8]
0x180048ff4  lea     eax, [rbx-1]
0x180048ff7  mov     [rdi+1Ch], eax
0x180048ffa  lea     rax, [r10+1]
0x180048ffe  mov     [rdi+20h], rax
0x180049002  mov     [rdi+18h], edx
0x180049005  inc     esi
0x180049007  mov     edi, 2
0x18004900c  jmp     loc_180048E30
0x180049011  mov     rdx, r10
0x180049014  mov     ecx, 1
0x180049019  call    cs:__imp_SkFreePool
0x180049020  nop     dword ptr [rax+rax+00h]
0x180049025  jmp     short loc_180049030
0x180049027  cmp     eax, r13d
0x18004902a  jnz     loc_1800492BB
0x180049030  mov     ebx, 0C0430003h
0x180049035  jmp     loc_1800492BB
0x18004903a  mov     eax, cs:g_CiOptions
0x180049040  test    al, 8
0x180049042  jz      short loc_18004904E
0x180049044  mov     cs:g_CiSignerTypeMax, edi
0x18004904a  mov     esi, edi
0x18004904c  jmp     short loc_180049062
0x18004904e  movzx   esi, byte ptr cs:g_CiDeveloperMode
0x180049055  shr     esi, 2
0x180049058  and     esi, 1
0x18004905b  mov     cs:g_CiSignerTypeMax, r12d
0x180049062  movaps  xmm0, cs:xmmword_180037E40
0x180049069  lea     rbx, cs:180000000h
0x180049070  movaps  xmm1, cs:xmmword_180037E50
0x180049077  mov     r13d, r12d
0x18004907a  movups  cs:g_CipCustomLevelComparisons, xmm0
0x180049081  movaps  xmm0, cs:xmmword_180037E60
0x180049088  movups  cs:xmmword_18003F670, xmm1
0x18004908f  movaps  xmm1, cs:xmmword_180037E70
0x180049096  movups  cs:xmmword_18003F680, xmm0
0x18004909d  movups  cs:xmmword_18003F690, xmm1
0x1800490a4  cmp     r13d, 13h
0x1800490a8  jnb     loc_180049243
0x1800490ae  mov     edi, r13d
0x1800490b1  mov     r15d, r13d
0x1800490b4  lea     r14, [rdi+rdi*2]
0x1800490b8  shl     r14, 2
0x1800490bc  shl     r15, 4
0x1800490c0  cmp     r12d, esi
0x1800490c3  jg      loc_180049174
0x1800490c9  lea     rax, asc_180035CC0; "\"$"
0x1800490d0  movsxd  rdx, r12d
0x1800490d3  shl     rdx, 4
0x1800490d7  lea     r9, [rbp+57h+var_80]
0x1800490db  add     rdx, rax
0x1800490de  mov     r15, rdi
0x1800490e1  lea     rax, [rbp+57h+var_A0]
0x1800490e5  shl     r15, 4
0x1800490e9  mov     r8d, 4
0x1800490ef  mov     [rsp+0E0h+var_C0], rax
0x1800490f4  lea     rcx, [r15+35B10h]
0x1800490fb  add     rcx, rbx
0x1800490fe  call    CipAllocateAndQuerySecureBootPolicyValue
0x180049103  mov     ebx, eax
0x180049105  test    eax, eax
0x180049107  js      short loc_180049149
0x180049109  mov     edx, [rbp+57h+var_A0]
0x18004910c  lea     rax, [rdi+rdi*2]
0x180049110  shr     edx, 2
0x180049113  lea     rbx, cs:180000000h
0x18004911a  movsxd  r8, r12d
0x18004911d  lea     r14, [rdi+rdi*2]
0x180049121  mov     [rbp+57h+var_A0], edx
0x180049124  shl     r14, 2
0x180049128  lea     rcx, [r8+rax*2]
0x18004912c  mov     rax, [rbp+57h+var_80]
0x180049130  mov     rva qword_18003F1B8[rbx+rcx*8], rax
0x180049138  lea     rax, [rdi+rdi*2]
0x18004913c  lea     rcx, [r8+rax*4]
0x180049140  mov     rva dword_18003F1D0[rbx+rcx*4], edx
0x180049147  jmp     short loc_18004916C
0x180049149  cmp     eax, 0C0000034h
0x18004914e  jnz     loc_1800492B7
0x180049154  movsxd  rax, r12d
0x180049157  lea     rbx, cs:180000000h
0x18004915e  add     rax, r14
0x180049161  mov     rva dword_18003F1D0[rbx+rax*4], 0
0x18004916c  inc     r12d
0x18004916f  jmp     loc_1800490C0
0x180049174  movzx   r14d, byte ptr [rdi+rbx+37E00h]
0x18004917d  xor     r12d, r12d
0x180049180  test    r14b, r14b
0x180049183  jz      short loc_1800491E4
0x180049185  lea     rax, [rbp+57h+var_AC]
0x180049189  mov     [rsp+0E0h+var_B8], rax
0x18004918e  lea     rcx, rva qword_180035B10[rbx]
0x180049195  add     rcx, r15
0x180049198  mov     dword ptr [rsp+0E0h+var_C0], 4
0x1800491a0  lea     r9, [rbp+57h+var_A8]
0x1800491a4  lea     r8d, [r12+2]
0x1800491a9  lea     rdx, qword_180035C80
0x1800491b0  call    cs:__imp_SeQuerySecureBootPolicyValue
0x1800491b7  nop     dword ptr [rax+rax+00h]
0x1800491bc  mov     ebx, eax
0x1800491be  test    eax, eax
0x1800491c0  js      short loc_1800491D2
0x1800491c2  mov     eax, [rbp+57h+var_A8]
0x1800491c5  lea     rdx, g_CipCustomLevelComparisons
0x1800491cc  mov     [rdx+r14*4], eax
0x1800491d0  jmp     short loc_1800491DD
0x1800491d2  cmp     eax, 0C0000034h
0x1800491d7  jnz     loc_1800492B7
0x1800491dd  lea     rbx, cs:180000000h
0x1800491e4  lea     rax, [rbp+57h+var_AC]
0x1800491e8  mov     r8d, 2
0x1800491ee  mov     [rsp+0E0h+var_B8], rax
0x1800491f3  lea     rcx, rva qword_180035B10[rbx]
0x1800491fa  add     rcx, r15
0x1800491fd  mov     dword ptr [rsp+0E0h+var_C0], 4
0x180049205  lea     r9, [rbp+57h+var_B0]
0x180049209  lea     rdx, asc_180035C50; "\b\n"
0x180049210  call    cs:__imp_SeQuerySecureBootPolicyValue
0x180049217  nop     dword ptr [rax+rax+00h]
0x18004921c  test    eax, eax
0x18004921e  jns     short loc_18004922A
  ... truncated ...
```
