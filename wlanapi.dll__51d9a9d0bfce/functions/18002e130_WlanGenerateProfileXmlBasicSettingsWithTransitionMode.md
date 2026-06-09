# WlanGenerateProfileXmlBasicSettingsWithTransitionMode

- ea: `0x18002e130`
- end: `0x18002e506`
- name: `WlanGenerateProfileXmlBasicSettingsWithTransitionMode`
- size: `982`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, int, int, unsigned __int16 *, int, int, int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18002e0c0`

## callees

- `0x180005330`
- `0x1800063a0`
- `0x180006934`
- `0x18001a5bc`
- `0x18002de94`
- `0x18002e130`
- `0x180043fc0`
- `0x180044000`
- `0x18006013c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e1da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e231`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e46a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e1da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e231`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e46a`
- `OneX!OneXCreateDefaultProfileWithEapMethodId` at `0x18002e437`
- `OneX!OneXCreateDefaultProfileWithEapMethodId` at `0x18002e437`
- `OneX!OneXCreateDefaultProfile` at `0x18002e44e`
- `OneX!OneXCreateDefaultProfile` at `0x18002e44e`
- `OneX!OneXFreeMemory` at `0x18002e490`
- `OneX!OneXFreeMemory` at `0x18002e490`

## pseudocode

```c
__int64 __fastcall WlanGenerateProfileXmlBasicSettingsWithTransitionMode(
        _WORD *Src,
        __int64 a2,
        int a3,
        int a4,
        int a5,
        int a6,
        unsigned __int16 *a7,
        int a8,
        int a9,
        int a10,
        unsigned __int16 **a11)
{
  union DOT11_OUI_HEADER *v15; // rcx
  __int64 v16; // rbx
  __int64 v17; // rax
  _DWORD *Memory; // rax
  _QWORD *v19; // rsi
  DWORD v20; // eax
  unsigned int v21; // ebx
  _DWORD *v22; // rax
  _DWORD *v23; // rbx
  DWORD LastError; // eax
  int v25; // eax
  unsigned int v26; // eax
  int v27; // ecx
  int v28; // eax
  int v29; // ecx
  unsigned int v30; // eax
  _BYTE *v31; // rax
  __int64 v32; // rcx
  _QWORD *v33; // rax
  _QWORD *v34; // r14
  _QWORD *v35; // rax
  _QWORD *v36; // rdi
  _DWORD *v37; // rax
  int v38; // ebx
  __int64 v39; // rax
  unsigned __int16 *v40; // rdx
  unsigned int KeyFromKeyMaterial; // eax
  int v42; // eax
  unsigned int v43; // eax
  PVOID v44; // rax
  PVOID v45; // rbx
  void *Srca[3]; // [rsp+30h] [rbp-18h] BYREF
  DWORD dwMemorySize; // [rsp+90h] [rbp+48h] BYREF

  dwMemorySize = 0;
  Srca[0] = 0;
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 14, WPP_98e362750f263b2963d6cf53eb247a44_Traceguids);
    v15 = WPP_GLOBAL_Control;
  }
  if ( !Src )
    goto LABEL_52;
  v16 = -1;
  v17 = -1;
  do
    ++v17;
  while ( Src[v17] );
  if ( (unsigned __int64)(v17 - 1) > 0xFE || !a2 )
  {
LABEL_52:
    v21 = 87;
    goto LABEL_53;
  }
  Memory = WlanAllocateMemory(0x230u);
  v19 = Memory;
  if ( Memory )
  {
    Memory[5] = 1;
    Memory[134] = 5304833;
    do
      ++v16;
    while ( Src[v16] );
    memcpy_0(Memory + 6, Src, 2 * v16 + 2);
    v22 = WlanAllocateMemory(0x48u);
    v23 = v22;
    if ( v22 )
    {
      memset_0(v22, 0, 0x48u);
      v19[69] = v23;
      *v23 = 1;
      v23[4] = a3;
      if ( a3 == 1 )
      {
        v23[1] |= 1u;
        v25 = v23[6];
        if ( a8 )
          v26 = v25 | 1;
        else
          v26 = v25 & 0xFFFFFFFE;
        v23[6] = v26;
      }
      v27 = v23[6];
      v23[1] |= 4u;
      v28 = v27;
      v29 = v27 | 2;
      v30 = v28 & 0xFFFFFFFD;
      if ( !a9 )
        v29 = v30;
      v23[6] = v29;
      v31 = WlanAllocateMemory(0x30u);
      *((_QWORD *)v23 + 1) = v31;
      if ( v31 )
      {
        *v31 = 0x80;
        *(_BYTE *)(*((_QWORD *)v23 + 1) + 1LL) = 1;
        *(_WORD *)(*((_QWORD *)v23 + 1) + 2LL) = 48;
        *(_DWORD *)(*((_QWORD *)v23 + 1) + 4LL) = 1;
        *(_DWORD *)(*((_QWORD *)v23 + 1) + 8LL) = 1;
        v32 = *((_QWORD *)v23 + 1);
        *(_OWORD *)(v32 + 12) = *(_OWORD *)a2;
        *(_OWORD *)(v32 + 28) = *(_OWORD *)(a2 + 16);
        *(_DWORD *)(v32 + 44) = *(_DWORD *)(a2 + 32);
        v33 = WlanAllocateMemory(0x1C8u);
        *((_QWORD *)v23 + 4) = v33;
        v34 = v33;
        if ( v33 )
        {
          v35 = WlanAllocateMemory(0x98u);
          v34[53] = v35;
          v36 = v35;
          if ( v35 )
          {
            v37 = WlanAllocateMemory(8u);
            v36[3] = v37;
            if ( v37 )
            {
              v38 = a5;
              *((_DWORD *)v36 + 4) = 1;
              *v37 = a4;
              *(_DWORD *)(v36[3] + 4LL) = v38;
              if ( a10 && a4 == 9 )
              {
                if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
                  && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u
                  && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 15, WPP_98e362750f263b2963d6cf53eb247a44_Traceguids);
                }
                v39 = v36[3];
                *((_DWORD *)v36 + 4) = 2;
                *(_DWORD *)(v39 + 8) = 7;
                *(_DWORD *)(v36[3] + 12LL) = v38;
              }
              v40 = a7;
              if ( a7 )
              {
                KeyFromKeyMaterial = PrflExtractKeyFromKeyMaterial((struct DOT11_MSMSEC_CONNECTION_PROFILE *)v36, a7);
                if ( KeyFromKeyMaterial )
                {
                  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
                    && *((_BYTE *)WPP_GLOBAL_Control + 105)
                    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 12),
                      16,
                      WPP_98e362750f263b2963d6cf53eb247a44_Traceguids,
                      KeyFromKeyMaterial);
                  }
                  v21 = 87;
                  goto LABEL_51;
                }
              }
              v42 = a6;
              *((_DWORD *)v36 + 8) = a6;
              if ( v42 )
              {
                if ( a4 == 8 )
                {
                  LOBYTE(v40) = 13;
                  v43 = OneXCreateDefaultProfileWithEapMethodId(1, v40, 0, &dwMemorySize, Srca);
                }
                else
                {
                  v43 = OneXCreateDefaultProfile(1, 0, &dwMemorySize, Srca, 0);
                }
                v21 = v43;
                if ( v43 )
                  goto LABEL_51;
                v44 = WlanAllocateMemory(dwMemorySize);
                v45 = v44;
                if ( !v44 )
                {
                  LastError = GetLastError();
                  goto LABEL_50;
                }
                memcpy_0(v44, Srca[0], dwMemorySize);
                *((_DWORD *)v36 + 10) = dwMemorySize;
                v36[6] = v45;
                v21 = OneXFreeMemory(Srca[0]);
                if ( v21 )
                {
LABEL_51:
                  WpFreeProfile(v19);
                  v15 = WPP_GLOBAL_Control;
                  goto LABEL_53;
                }
              }
              LastError = WpGenerateProfileXml((struct _PM_PROFILE *)v19, a11);
              goto LABEL_50;
            }
          }
        }
      }
    }
    LastError = GetLastError();
LABEL_50:
    v21 = LastError;
    goto LABEL_51;
  }
  v20 = GetLastError();
  v15 = WPP_GLOBAL_Control;
  v21 = v20;
LABEL_53:
  if ( v15 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)v15 + 105) >= 4u
    && (*((_BYTE *)v15 + 108) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)v15 + 12), 17, WPP_98e362750f263b2963d6cf53eb247a44_Traceguids, v21);
  }
  return v21;
}

```

## disassembly

```asm
0x18002e130  push    rbp
0x18002e132  push    rbx
0x18002e133  push    rsi
0x18002e134  push    rdi
0x18002e135  push    r12
0x18002e137  push    r13
0x18002e139  push    r14
0x18002e13b  push    r15
0x18002e13d  mov     rbp, rsp
0x18002e140  sub     rsp, 48h
0x18002e144  xor     r12d, r12d
0x18002e147  mov     r15d, r9d
0x18002e14a  mov     [rbp+dwMemorySize], r12d
0x18002e14e  mov     r14d, r8d
0x18002e151  mov     [rbp+Src], r12
0x18002e155  mov     r13, rdx
0x18002e158  mov     rdi, rcx
0x18002e15b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e162  lea     rax, WPP_GLOBAL_Control
0x18002e169  cmp     rcx, rax
0x18002e16c  jz      short loc_18002E196
0x18002e16e  cmp     byte ptr [rcx+69h], 4
0x18002e172  jb      short loc_18002E196
0x18002e174  test    byte ptr [rcx+6Ch], 2
0x18002e178  jz      short loc_18002E196
0x18002e17a  mov     rcx, [rcx+60h]
0x18002e17e  lea     edx, [r12+0Eh]
0x18002e183  lea     r8, WPP_98e362750f263b2963d6cf53eb247a44_Traceguids
0x18002e18a  call    WPP_SF_
0x18002e18f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e196  test    rdi, rdi
0x18002e199  jz      loc_18002E4BE
0x18002e19f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002e1a3  mov     rax, rbx
0x18002e1a6  inc     rax
0x18002e1a9  cmp     [rdi+rax*2], r12w
0x18002e1ae  jnz     short loc_18002E1A6
0x18002e1b0  dec     rax
0x18002e1b3  cmp     rax, 0FEh
0x18002e1b9  ja      loc_18002E4BE
0x18002e1bf  test    r13, r13
0x18002e1c2  jz      loc_18002E4BE
0x18002e1c8  mov     ecx, 230h; dwMemorySize
0x18002e1cd  call    WlanAllocateMemory
0x18002e1d2  mov     rsi, rax
0x18002e1d5  test    rax, rax
0x18002e1d8  jnz     short loc_18002E1EE
0x18002e1da  call    cs:__imp_GetLastError
0x18002e1e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e1e7  mov     ebx, eax
0x18002e1e9  jmp     loc_18002E4C3
0x18002e1ee  mov     dword ptr [rax+14h], 1
0x18002e1f5  mov     dword ptr [rax+218h], 50F201h
0x18002e1ff  inc     rbx
0x18002e202  cmp     [rdi+rbx*2], r12w
0x18002e207  jnz     short loc_18002E1FF
0x18002e209  lea     r8, ds:2[rbx*2]; Size
0x18002e211  mov     rdx, rdi; Src
0x18002e214  lea     rcx, [rax+18h]; void *
0x18002e218  call    memcpy_0
0x18002e21d  mov     edi, 48h ; 'H'
0x18002e222  mov     ecx, edi; dwMemorySize
0x18002e224  call    WlanAllocateMemory
0x18002e229  mov     rbx, rax
0x18002e22c  test    rax, rax
0x18002e22f  jnz     short loc_18002E243
0x18002e231  call    cs:__imp_GetLastError
0x18002e237  lea     r13, WPP_GLOBAL_Control
0x18002e23e  jmp     loc_18002E4AB
0x18002e243  mov     r8, rdi; Size
0x18002e246  xor     edx, edx; Val
0x18002e248  mov     rcx, rbx; void *
0x18002e24b  call    memset_0
0x18002e250  mov     edi, 1
0x18002e255  mov     [rsi+228h], rbx
0x18002e25c  mov     [rbx], edi
0x18002e25e  mov     [rbx+10h], r14d
0x18002e262  cmp     r14d, edi
0x18002e265  jnz     short loc_18002E280
0x18002e267  or      [rbx+4], edi
0x18002e26a  mov     eax, [rbx+18h]
0x18002e26d  cmp     [rbp+arg_38], r12d
0x18002e274  jz      short loc_18002E27A
0x18002e276  or      eax, edi
0x18002e278  jmp     short loc_18002E27D
0x18002e27a  and     eax, 0FFFFFFFEh
0x18002e27d  mov     [rbx+18h], eax
0x18002e280  mov     ecx, [rbx+18h]
0x18002e283  mov     r14d, 30h ; '0'
0x18002e289  or      dword ptr [rbx+4], 4
0x18002e28d  mov     eax, ecx
0x18002e28f  or      ecx, 2
0x18002e292  and     eax, 0FFFFFFFDh
0x18002e295  cmp     [rbp+arg_40], r12d
0x18002e29c  cmovz   ecx, eax
0x18002e29f  mov     [rbx+18h], ecx
0x18002e2a2  mov     ecx, r14d; dwMemorySize
0x18002e2a5  call    WlanAllocateMemory
0x18002e2aa  mov     [rbx+8], rax
0x18002e2ae  test    rax, rax
0x18002e2b1  jz      loc_18002E231
0x18002e2b7  mov     byte ptr [rax], 80h
0x18002e2ba  mov     rax, [rbx+8]
0x18002e2be  mov     [rax+1], dil
0x18002e2c2  mov     rax, [rbx+8]
0x18002e2c6  mov     [rax+2], r14w
0x18002e2cb  mov     rax, [rbx+8]
0x18002e2cf  mov     [rax+4], edi
0x18002e2d2  mov     rax, [rbx+8]
0x18002e2d6  mov     [rax+8], edi
0x18002e2d9  mov     rcx, [rbx+8]
0x18002e2dd  movups  xmm0, xmmword ptr [r13+0]
0x18002e2e2  movups  xmmword ptr [rcx+0Ch], xmm0
0x18002e2e6  movups  xmm1, xmmword ptr [r13+10h]
0x18002e2eb  movups  xmmword ptr [rcx+1Ch], xmm1
0x18002e2ef  mov     eax, [r13+20h]
0x18002e2f3  mov     [rcx+2Ch], eax
0x18002e2f6  mov     ecx, 1C8h; dwMemorySize
0x18002e2fb  call    WlanAllocateMemory
0x18002e300  mov     [rbx+20h], rax
0x18002e304  mov     r14, rax
0x18002e307  test    rax, rax
0x18002e30a  jz      loc_18002E231
0x18002e310  mov     ecx, 98h; dwMemorySize
0x18002e315  call    WlanAllocateMemory
0x18002e31a  mov     [r14+1A8h], rax
0x18002e321  mov     rdi, rax
0x18002e324  test    rax, rax
0x18002e327  jz      loc_18002E231
0x18002e32d  mov     ecx, 8; dwMemorySize
0x18002e332  call    WlanAllocateMemory
0x18002e337  mov     [rdi+18h], rax
0x18002e33b  test    rax, rax
0x18002e33e  jz      loc_18002E231
0x18002e344  mov     r14d, 1
0x18002e34a  mov     ebx, [rbp+arg_20]
0x18002e34d  mov     [rdi+10h], r14d
0x18002e351  mov     [rax], r15d
0x18002e354  mov     rax, [rdi+18h]
0x18002e358  mov     [rax+4], ebx
0x18002e35b  cmp     [rbp+arg_48], r12d
0x18002e362  jz      short loc_18002E3B8
0x18002e364  cmp     r15d, 9
0x18002e368  jnz     short loc_18002E3B8
0x18002e36a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e371  lea     r13, WPP_GLOBAL_Control
0x18002e378  cmp     rcx, r13
0x18002e37b  jz      short loc_18002E39D
0x18002e37d  cmp     byte ptr [rcx+69h], 3
0x18002e381  jb      short loc_18002E39D
0x18002e383  test    byte ptr [rcx+6Ch], 2
0x18002e387  jz      short loc_18002E39D
0x18002e389  mov     rcx, [rcx+60h]
0x18002e38d  lea     edx, [r14+0Eh]
0x18002e391  lea     r8, WPP_98e362750f263b2963d6cf53eb247a44_Traceguids
0x18002e398  call    WPP_SF_
0x18002e39d  mov     rax, [rdi+18h]
0x18002e3a1  mov     dword ptr [rdi+10h], 2
0x18002e3a8  mov     dword ptr [rax+8], 7
0x18002e3af  mov     rax, [rdi+18h]
0x18002e3b3  mov     [rax+0Ch], ebx
0x18002e3b6  jmp     short loc_18002E3BF
0x18002e3b8  lea     r13, WPP_GLOBAL_Control
0x18002e3bf  mov     rdx, [rbp+arg_30]; unsigned __int16 *
0x18002e3c3  test    rdx, rdx
0x18002e3c6  jz      short loc_18002E40E
0x18002e3c8  mov     rcx, rdi; struct DOT11_MSMSEC_CONNECTION_PROFILE *
0x18002e3cb  call    ?PrflExtractKeyFromKeyMaterial@@YAKPEAUDOT11_MSMSEC_CONNECTION_PROFILE@@PEBG@Z; PrflExtractKeyFromKeyMaterial(DOT11_MSMSEC_CONNECTION_PROFILE *,ushort const *)
0x18002e3d0  test    eax, eax
0x18002e3d2  jz      short loc_18002E40E
0x18002e3d4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e3db  cmp     rcx, r13
0x18002e3de  jz      short loc_18002E404
0x18002e3e0  cmp     [rcx+69h], r14b
0x18002e3e4  jb      short loc_18002E404
0x18002e3e6  test    byte ptr [rcx+6Ch], 2
0x18002e3ea  jz      short loc_18002E404
0x18002e3ec  mov     rcx, [rcx+60h]
0x18002e3f0  lea     r8, WPP_98e362750f263b2963d6cf53eb247a44_Traceguids
0x18002e3f7  mov     edx, 10h
0x18002e3fc  mov     r9d, eax
0x18002e3ff  call    WPP_SF_d
0x18002e404  mov     ebx, 57h ; 'W'
0x18002e409  jmp     loc_18002E4AD
0x18002e40e  mov     eax, [rbp+arg_28]
0x18002e411  mov     [rdi+20h], eax
0x18002e414  test    eax, eax
0x18002e416  jz      loc_18002E49C
0x18002e41c  mov     ecx, r14d
0x18002e41f  cmp     r15d, 8
0x18002e423  jnz     short loc_18002E43F
0x18002e425  lea     rax, [rbp+Src]
0x18002e429  xor     r8d, r8d
0x18002e42c  lea     r9, [rbp+dwMemorySize]
0x18002e430  mov     [rsp+48h+var_28], rax
0x18002e435  mov     dl, 0Dh
0x18002e437  call    cs:__imp_OneXCreateDefaultProfileWithEapMethodId
0x18002e43d  jmp     short loc_18002E454
0x18002e43f  lea     r9, [rbp+Src]
0x18002e443  mov     [rsp+48h+var_28], r12
0x18002e448  lea     r8, [rbp+dwMemorySize]
0x18002e44c  xor     edx, edx
0x18002e44e  call    cs:__imp_OneXCreateDefaultProfile
0x18002e454  mov     ebx, eax
0x18002e456  test    eax, eax
0x18002e458  jnz     short loc_18002E4AD
0x18002e45a  mov     ecx, [rbp+dwMemorySize]; dwMemorySize
0x18002e45d  call    WlanAllocateMemory
0x18002e462  mov     rbx, rax
0x18002e465  test    rax, rax
0x18002e468  jnz     short loc_18002E472
0x18002e46a  call    cs:__imp_GetLastError
0x18002e470  jmp     short loc_18002E4AB
0x18002e472  mov     r8d, [rbp+dwMemorySize]; Size
0x18002e476  mov     rcx, rbx; void *
0x18002e479  mov     rdx, [rbp+Src]; Src
0x18002e47d  call    memcpy_0
0x18002e482  mov     eax, [rbp+dwMemorySize]
0x18002e485  mov     [rdi+28h], eax
0x18002e488  mov     [rdi+30h], rbx
0x18002e48c  mov     rcx, [rbp+Src]
0x18002e490  call    cs:__imp_OneXFreeMemory
0x18002e496  mov     ebx, eax
0x18002e498  test    eax, eax
0x18002e49a  jnz     short loc_18002E4AD
0x18002e49c  mov     rdx, [rbp+arg_50]; unsigned __int16 **
0x18002e4a3  mov     rcx, rsi; struct _PM_PROFILE *
0x18002e4a6  call    WpGenerateProfileXml
0x18002e4ab  mov     ebx, eax
0x18002e4ad  mov     rcx, rsi; lpMem
0x18002e4b0  call    WpFreeProfile
0x18002e4b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e4bc  jmp     short loc_18002E4CA
0x18002e4be  mov     ebx, 57h ; 'W'
0x18002e4c3  lea     r13, WPP_GLOBAL_Control
0x18002e4ca  cmp     rcx, r13
0x18002e4cd  jz      short loc_18002E4F3
0x18002e4cf  cmp     byte ptr [rcx+69h], 4
0x18002e4d3  jb      short loc_18002E4F3
0x18002e4d5  test    byte ptr [rcx+6Ch], 2
0x18002e4d9  jz      short loc_18002E4F3
0x18002e4db  mov     rcx, [rcx+60h]
0x18002e4df  lea     r8, WPP_98e362750f263b2963d6cf53eb247a44_Traceguids
0x18002e4e6  mov     edx, 11h
0x18002e4eb  mov     r9d, ebx
0x18002e4ee  call    WPP_SF_d
0x18002e4f3  mov     eax, ebx
0x18002e4f5  add     rsp, 48h
0x18002e4f9  pop     r15
0x18002e4fb  pop     r14
0x18002e4fd  pop     r13
0x18002e4ff  pop     r12
0x18002e501  pop     rdi
0x18002e502  pop     rsi
0x18002e503  pop     rbx
0x18002e504  pop     rbp
0x18002e505  retn
```
