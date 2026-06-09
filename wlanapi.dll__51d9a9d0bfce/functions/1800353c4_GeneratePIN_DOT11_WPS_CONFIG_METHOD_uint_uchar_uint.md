# GeneratePIN(_DOT11_WPS_CONFIG_METHOD,uint,uchar *,uint *)

- ea: `0x1800353c4`
- end: `0x1800356e3`
- name: `?GeneratePIN@@YAKW4_DOT11_WPS_CONFIG_METHOD@@IPEAEPEAI@Z`
- size: `799`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x1800357dc`

## callees

- `0x180005330`
- `0x180005610`
- `0x1800063a0`
- `0x180006934`
- `0x180019a20`
- `0x1800334a8`
- `0x180033e6c`
- `0x1800353c4`
- `0x1800600d0`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18003542e`
- `ntdll!RtlNtStatusToDosError` at `0x18003542e`
- `bcrypt!BCryptGenRandom` at `0x180035426`
- `bcrypt!BCryptGenRandom` at `0x180035426`

## pseudocode

```c
__int64 __fastcall GeneratePIN(int a1, __int64 a2, unsigned __int8 *a3, unsigned int *a4)
{
  NTSTATUS v6; // eax
  ULONG v7; // ebx
  union DOT11_OUI_HEADER *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // r9
  unsigned int v11; // ecx
  unsigned __int64 v12; // rdx
  _DWORD *Memory; // rdi
  const WCHAR *v14; // rsi
  __int64 v15; // r9
  union DOT11_OUI_HEADER *v16; // rax
  __int64 v17; // rdx
  int v18; // r14d
  __int64 v19; // rbx
  __int64 v20; // rdx
  unsigned int v21; // edx
  __int64 i; // rcx
  UCHAR pbBuffer[16]; // [rsp+20h] [rbp-13D8h] BYREF
  int v25; // [rsp+30h] [rbp-13C8h] BYREF
  _DWORD v26[1251]; // [rsp+34h] [rbp-13C4h]

  *(_DWORD *)pbBuffer = 0;
  if ( !a3 )
  {
    v7 = 87;
    if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105)
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 22, WPP_165493f09ce23a9f247d79d24a2a269f_Traceguids);
    }
    return v7;
  }
  *(_QWORD *)a3 = 0;
  if ( (a1 & 0xFFFFFF7F) == 0 )
  {
    Memory = 0;
    *a4 = 0;
    v14 = 0;
    v7 = 0;
    goto LABEL_36;
  }
  v6 = BCryptGenRandom(0, pbBuffer, 4u, 2u);
  v7 = RtlNtStatusToDosError(v6);
  if ( v7 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105)
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
    {
      v9 = 23;
      v10 = v7;
LABEL_8:
      WPP_SF_d(*((_QWORD *)v8 + 12), v9, WPP_165493f09ce23a9f247d79d24a2a269f_Traceguids, v10);
      return v7;
    }
    return v7;
  }
  v11 = *(_DWORD *)pbBuffer;
  v12 = 1;
  v26[0] = *(_DWORD *)pbBuffer;
  v26[1248] = -1;
  do
  {
    v11 = v12 + 1812433253 * (v11 ^ (v11 >> 30));
    v26[v12++] = v11;
  }
  while ( v12 < 0x270 );
  v25 = 624;
  Memory = WlanAllocateMemory(0x20u);
  if ( Memory )
  {
    v14 = (const WCHAR *)WlanAllocateMemory(0x12u);
    if ( !v14 )
    {
      v15 = 14;
      v7 = 14;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
        || !*((_BYTE *)WPP_GLOBAL_Control + 105)
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) == 0 )
      {
        goto LABEL_37;
      }
      v17 = 25;
LABEL_21:
      WPP_SF_d(*((_QWORD *)v16 + 12), v17, WPP_165493f09ce23a9f247d79d24a2a269f_Traceguids, v15);
LABEL_37:
      FreeWLMem(Memory);
LABEL_38:
      if ( v14 )
        FreeWLMem(v14);
      return v7;
    }
    v18 = 0;
    v19 = 0;
    do
    {
      v20 = 10LL
          * (unsigned int)std::mersenne_twister<unsigned int,32,624,397,31,2567483615,11,7,2636928640,15,4022730752,18>::operator()(&v25);
      if ( (unsigned int)v20 <= 5 )
      {
        do
          v20 = 10LL
              * (unsigned int)std::mersenne_twister<unsigned int,32,624,397,31,2567483615,11,7,2636928640,15,4022730752,18>::operator()(&v25);
        while ( (unsigned int)v20 < 6 );
      }
      v21 = (HIDWORD(v20) + 0x80000000) ^ 0x80000000;
      v18 += v21;
      Memory[v19] = v21;
      if ( (v19 & 1) == 0 )
        v18 += 2 * v21;
      v19 = (unsigned int)(v19 + 1);
    }
    while ( (unsigned int)v19 < 7 );
    Memory[7] = (int)(10
                    * (((int)((unsigned __int64)(1717986919LL * v18) >> 32) >> 2)
                     + 1
                     + ((unsigned int)((unsigned __int64)(1717986919LL * v18) >> 32) >> 31))
                    - v18)
              % 10;
    for ( i = 0; i != 8; ++i )
      v14[i] = LOWORD(Memory[i]) + 48;
    *((_WORD *)v14 + 8) = 0;
    v7 = GenerateFromString(v14, 8u, a3, a4);
    if ( v7 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
        || !*((_BYTE *)WPP_GLOBAL_Control + 105)
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) == 0 )
      {
        goto LABEL_37;
      }
      v17 = 26;
      v15 = v7;
      goto LABEL_21;
    }
LABEL_36:
    if ( !Memory )
      goto LABEL_38;
    goto LABEL_37;
  }
  v10 = 14;
  v7 = 14;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105)
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
  {
    v9 = 24;
    goto LABEL_8;
  }
  return v7;
}

```

## disassembly

```asm
0x1800353c4  mov     [rsp+arg_0], rbx
0x1800353c9  push    rbp
0x1800353ca  push    rsi
0x1800353cb  push    rdi
0x1800353cc  push    r14
0x1800353ce  push    r15
0x1800353d0  mov     eax, 13D0h
0x1800353d5  call    _alloca_probe
0x1800353da  sub     rsp, rax
0x1800353dd  mov     rax, cs:__security_cookie
0x1800353e4  xor     rax, rsp
0x1800353e7  mov     [rsp+13F8h+var_38], rax
0x1800353ef  mov     dword ptr [rsp+13F8h+pbBuffer], 0
0x1800353f7  mov     rbp, r9
0x1800353fa  mov     r15, r8
0x1800353fd  test    r8, r8
0x180035400  jz      loc_180035683
0x180035406  xor     eax, eax
0x180035408  mov     [r8], rax
0x18003540b  test    ecx, 0FFFFFF7Fh
0x180035411  jz      loc_18003565E
0x180035417  lea     r9d, [rax+2]; dwFlags
0x18003541b  xor     ecx, ecx; hAlgorithm
0x18003541d  lea     r8d, [rax+4]; cbBuffer
0x180035421  lea     rdx, [rsp+13F8h+pbBuffer]; pbBuffer
0x180035426  call    cs:__imp_BCryptGenRandom
0x18003542c  mov     ecx, eax; Status
0x18003542e  call    cs:__imp_RtlNtStatusToDosError
0x180035434  mov     ebx, eax
0x180035436  test    eax, eax
0x180035438  jz      short loc_180035482
0x18003543a  mov     rax, cs:WPP_GLOBAL_Control
0x180035441  lea     rcx, WPP_GLOBAL_Control
0x180035448  cmp     rax, rcx
0x18003544b  jz      loc_1800356BA
0x180035451  cmp     byte ptr [rax+69h], 1
0x180035455  jb      loc_1800356BA
0x18003545b  test    byte ptr [rax+6Ch], 2
0x18003545f  jz      loc_1800356BA
0x180035465  mov     edx, 17h
0x18003546a  mov     r9d, ebx
0x18003546d  mov     rcx, [rax+60h]
0x180035471  lea     r8, WPP_165493f09ce23a9f247d79d24a2a269f_Traceguids
0x180035478  call    WPP_SF_d
0x18003547d  jmp     loc_1800356BA
0x180035482  mov     ecx, dword ptr [rsp+13F8h+pbBuffer]
0x180035486  mov     edx, 1
0x18003548b  mov     [rsp+13F8h+var_13C4], ecx
0x18003548f  mov     r8d, 270h
0x180035495  mov     [rsp+13F8h+var_44], 0FFFFFFFFh
0x1800354a0  mov     eax, ecx
0x1800354a2  shr     eax, 1Eh
0x1800354a5  xor     eax, ecx
0x1800354a7  imul    ecx, eax, 6C078965h
0x1800354ad  add     ecx, edx
0x1800354af  mov     [rsp+rdx*4+13F8h+var_13C4], ecx
0x1800354b3  inc     rdx
0x1800354b6  cmp     rdx, r8
0x1800354b9  jb      short loc_1800354A0
0x1800354bb  mov     ecx, 20h ; ' '; dwMemorySize
0x1800354c0  mov     [rsp+13F8h+var_13C8], r8d
0x1800354c5  call    WlanAllocateMemory
0x1800354ca  mov     rdi, rax
0x1800354cd  test    rax, rax
0x1800354d0  jnz     short loc_18003550C
0x1800354d2  lea     r9d, [rax+0Eh]
0x1800354d6  mov     ebx, r9d
0x1800354d9  mov     rax, cs:WPP_GLOBAL_Control
0x1800354e0  lea     rcx, WPP_GLOBAL_Control
0x1800354e7  cmp     rax, rcx
0x1800354ea  jz      loc_1800356BA
0x1800354f0  cmp     byte ptr [rax+69h], 1
0x1800354f4  jb      loc_1800356BA
0x1800354fa  test    byte ptr [rax+6Ch], 2
0x1800354fe  jz      loc_1800356BA
0x180035504  lea     edx, [rdi+18h]
0x180035507  jmp     loc_18003546D
0x18003550c  mov     ecx, 12h; dwMemorySize
0x180035511  call    WlanAllocateMemory
0x180035516  mov     rsi, rax
0x180035519  test    rax, rax
0x18003551c  jnz     short loc_180035568
0x18003551e  lea     r9d, [rax+0Eh]
0x180035522  mov     ebx, r9d
0x180035525  mov     rax, cs:WPP_GLOBAL_Control
0x18003552c  lea     rcx, WPP_GLOBAL_Control
0x180035533  cmp     rax, rcx
0x180035536  jz      loc_18003566C
0x18003553c  cmp     byte ptr [rax+69h], 1
0x180035540  jb      loc_18003566C
0x180035546  test    byte ptr [rax+6Ch], 2
0x18003554a  jz      loc_18003566C
0x180035550  lea     edx, [rsi+19h]
0x180035553  mov     rcx, [rax+60h]
0x180035557  lea     r8, WPP_165493f09ce23a9f247d79d24a2a269f_Traceguids
0x18003555e  call    WPP_SF_d
0x180035563  jmp     loc_18003566C
0x180035568  xor     r14d, r14d
0x18003556b  xor     ebx, ebx
0x18003556d  lea     rcx, [rsp+13F8h+var_13C8]
0x180035572  call    ??R?$mersenne_twister@I$0CA@$0CHA@$0BIN@$0BP@$0JJAILANP@$0L@$06$0JNCMFGIA@$0P@$0OPMGAAAA@$0BC@@std@@QEAAIXZ; std::mersenne_twister<uint,32,624,397,31,2567483615,11,7,2636928640,15,4022730752,18>::operator()(void)
0x180035577  mov     ecx, eax
0x180035579  lea     rdx, [rcx+rcx*4]
0x18003557d  add     rdx, rdx
0x180035580  cmp     edx, 5
0x180035583  ja      short loc_18003559D
0x180035585  lea     rcx, [rsp+13F8h+var_13C8]
0x18003558a  call    ??R?$mersenne_twister@I$0CA@$0CHA@$0BIN@$0BP@$0JJAILANP@$0L@$06$0JNCMFGIA@$0P@$0OPMGAAAA@$0BC@@std@@QEAAIXZ; std::mersenne_twister<uint,32,624,397,31,2567483615,11,7,2636928640,15,4022730752,18>::operator()(void)
0x18003558f  mov     ecx, eax
0x180035591  lea     rdx, [rcx+rcx*4]
0x180035595  add     rdx, rdx
0x180035598  cmp     edx, 6
0x18003559b  jb      short loc_180035585
0x18003559d  shr     rdx, 20h
0x1800355a1  add     edx, 80000000h
0x1800355a7  btc     edx, 1Fh
0x1800355ab  add     r14d, edx
0x1800355ae  mov     [rdi+rbx*4], edx
0x1800355b1  test    bl, 1
0x1800355b4  jnz     short loc_1800355BA
0x1800355b6  lea     r14d, [r14+rdx*2]
0x1800355ba  inc     ebx
0x1800355bc  cmp     ebx, 7
0x1800355bf  jb      short loc_18003556D
0x1800355c1  mov     r9d, 66666667h
0x1800355c7  mov     eax, r9d
0x1800355ca  imul    r14d
0x1800355cd  mov     eax, r9d
0x1800355d0  sar     edx, 2
0x1800355d3  mov     ecx, edx
0x1800355d5  inc     edx
0x1800355d7  shr     ecx, 1Fh
0x1800355da  add     ecx, edx
0x1800355dc  lea     r8d, [rcx+rcx*4]
0x1800355e0  add     r8d, r8d
0x1800355e3  sub     r8d, r14d
0x1800355e6  imul    r8d
0x1800355e9  sar     edx, 2
0x1800355ec  mov     eax, edx
0x1800355ee  shr     eax, 1Fh
0x1800355f1  add     edx, eax
0x1800355f3  lea     eax, [rdx+rdx*4]
0x1800355f6  add     eax, eax
0x1800355f8  sub     r8d, eax
0x1800355fb  mov     [rdi+1Ch], r8d
0x1800355ff  xor     ecx, ecx
0x180035601  movzx   eax, word ptr [rdi+rcx*4]
0x180035605  add     ax, 30h ; '0'
0x180035609  mov     [rsi+rcx*2], ax
0x18003560d  inc     rcx
0x180035610  cmp     rcx, 8
0x180035614  jnz     short loc_180035601
0x180035616  xor     eax, eax
0x180035618  mov     edx, ecx; unsigned int
0x18003561a  mov     rcx, rsi; lpWideCharStr
0x18003561d  mov     [rsi+10h], ax
0x180035621  mov     r9, rbp; unsigned int *
0x180035624  mov     r8, r15; unsigned __int8 *
0x180035627  call    ?GenerateFromString@@YAKPEAEI0PEAI@Z; GenerateFromString(uchar *,uint,uchar *,uint *)
0x18003562c  mov     ebx, eax
0x18003562e  test    eax, eax
0x180035630  jz      short loc_180035667
0x180035632  mov     rax, cs:WPP_GLOBAL_Control
0x180035639  lea     rcx, WPP_GLOBAL_Control
0x180035640  cmp     rax, rcx
0x180035643  jz      short loc_18003566C
0x180035645  cmp     byte ptr [rax+69h], 1
0x180035649  jb      short loc_18003566C
0x18003564b  test    byte ptr [rax+6Ch], 2
0x18003564f  jz      short loc_18003566C
0x180035651  mov     edx, 1Ah
0x180035656  mov     r9d, ebx
0x180035659  jmp     loc_180035553
0x18003565e  xor     edi, edi
0x180035660  mov     [r9], eax
0x180035663  xor     esi, esi
0x180035665  xor     ebx, ebx
0x180035667  test    rdi, rdi
0x18003566a  jz      short loc_180035674
0x18003566c  mov     rcx, rdi
0x18003566f  call    FreeWLMem
0x180035674  test    rsi, rsi
0x180035677  jz      short loc_1800356BA
0x180035679  mov     rcx, rsi
0x18003567c  call    FreeWLMem
0x180035681  jmp     short loc_1800356BA
0x180035683  mov     ebx, 57h ; 'W'
0x180035688  mov     rax, cs:WPP_GLOBAL_Control
0x18003568f  lea     rcx, WPP_GLOBAL_Control
0x180035696  cmp     rax, rcx
0x180035699  jz      short loc_1800356BA
0x18003569b  cmp     byte ptr [rax+69h], 1
0x18003569f  jb      short loc_1800356BA
0x1800356a1  test    byte ptr [rax+6Ch], 2
0x1800356a5  jz      short loc_1800356BA
0x1800356a7  mov     rcx, [rax+60h]
0x1800356ab  lea     edx, [rbx-41h]
0x1800356ae  lea     r8, WPP_165493f09ce23a9f247d79d24a2a269f_Traceguids
0x1800356b5  call    WPP_SF_
0x1800356ba  mov     eax, ebx
0x1800356bc  mov     rcx, [rsp+13F8h+var_38]
0x1800356c4  xor     rcx, rsp; StackCookie
0x1800356c7  call    __security_check_cookie
0x1800356cc  mov     rbx, [rsp+13F8h+arg_0]
0x1800356d4  add     rsp, 13D0h
0x1800356db  pop     r15
0x1800356dd  pop     r14
0x1800356df  pop     rdi
0x1800356e0  pop     rsi
0x1800356e1  pop     rbp
0x1800356e2  retn
```
