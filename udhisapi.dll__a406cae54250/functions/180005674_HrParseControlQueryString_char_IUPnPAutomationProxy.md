# HrParseControlQueryString(char *,IUPnPAutomationProxy * *)

- ea: `0x180005674`
- end: `0x180005b62`
- name: `?HrParseControlQueryString@@YAJPEADPEAPEAUIUPnPAutomationProxy@@@Z`
- size: `1262`
- prototype: `__int64 __fastcall(char *, struct IUPnPAutomationProxy **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000512c`

## callees

- `0x18000249c`
- `0x1800038ec`
- `0x180005674`
- `0x180006cd0`
- `0x180009a74`
- `0x18000c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005872`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005ac1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005ad6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005872`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005ac1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005ad6`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180005843`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180005843`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800057c4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800057c4`

## string_xrefs

- `0x18000596d`: `HrParseControlQueryString(): Failed to convert Service ID to unicode string`
- `0x1800059f2`: `HrParseControlQueryString(): No service ID found`
- `0x180005a96`: `HrParseControlQueryString(): Failed to create registrar object`

## pseudocode

```c
__int64 __fastcall HrParseControlQueryString(char *a1, struct IUPnPAutomationProxy **a2)
{
  const char *v2; // rax
  __int64 v3; // r8
  unsigned __int64 v6; // r9
  unsigned int v7; // ebx
  unsigned __int64 v8; // rdx
  __int64 v9; // rcx
  char *v10; // rax
  unsigned __int16 *v11; // rdi
  unsigned __int16 *v12; // rsi
  int v13; // ecx
  char *v14; // r13
  _QWORD *v15; // rcx
  HRESULT v16; // eax
  int v17; // eax
  char *v18; // r15
  unsigned int v19; // ebx
  size_t v20; // rbp
  CHAR *v21; // r14
  __int64 v22; // rax
  CHAR *v23; // rcx
  CHAR *v24; // rax
  unsigned __int16 *v25; // rax
  int v26; // r8d
  _QWORD *v27; // rcx
  int v28; // edx
  const char *v29; // r9
  LPVOID ppv; // [rsp+90h] [rbp+18h] BYREF

  v2 = "control=";
  v3 = 0x7FFFFFFF;
  v6 = 0;
  do
  {
    if ( !*v2 )
      break;
    ++v2;
    --v3;
  }
  while ( v3 );
  v7 = v3 == 0 ? 0x80070057 : 0;
  v8 = (0x7FFFFFFF - v3) & ((unsigned __int128)-(__int128)(unsigned __int64)v3 >> 64);
  if ( !v3 )
  {
    v8 = 0;
    goto LABEL_14;
  }
  if ( !a1 )
  {
    v7 = -2147024809;
LABEL_13:
    v6 = 0;
    goto LABEL_14;
  }
  v9 = 0x7FFFFFFF;
  v10 = a1;
  do
  {
    if ( !*v10 )
      break;
    ++v10;
    --v9;
  }
  while ( v9 );
  v6 = (0x7FFFFFFF - v9) & -(__int64)(v9 != 0);
  v7 = v9 == 0 ? 0x80070057 : 0;
  if ( !v9 )
    goto LABEL_13;
LABEL_14:
  if ( (v7 & 0x80000000) != 0 )
    goto LABEL_74;
  if ( v6 <= v8 )
  {
    v7 = -2147024809;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v7;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        96,
        (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids,
        (unsigned int)"HrParseControlQueryString(): Length of query string was <= length of the prefix",
        87);
      v15 = WPP_GLOBAL_Control;
    }
  }
  else
  {
    v11 = 0;
    v12 = 0;
    v13 = v8;
    if ( (unsigned int)v8 < (unsigned int)v6 )
    {
      while ( 1 )
      {
        v14 = &a1[v13];
        if ( *v14 == 43 )
          break;
        if ( ++v13 >= (unsigned int)v6 )
          goto LABEL_19;
      }
      v18 = &a1[v8];
      v19 = v13 - v8;
      v20 = (unsigned int)(v13 - v8 + 1);
      v21 = (CHAR *)malloc(v20);
      if ( !v21 )
      {
        v7 = -2147024882;
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return v7;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_76;
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          94,
          (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids,
          (unsigned int)"HrParseControlQueryString(): Failed to allocate memory for UDN ANSI string",
          14);
LABEL_22:
        if ( (v7 & 0x80000000) == 0 )
        {
          ppv = 0;
          v16 = CoCreateInstance(&CLSID_UPnPRegistrar, 0, 1u, &IID_IUPnPRegistrarLookup, &ppv);
          v7 = v16;
          if ( v16 < 0 )
          {
            v15 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_70;
            WPP_SF_sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              99,
              (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids,
              (unsigned int)"HrParseControlQueryString(): Failed to create registrar object",
              v16);
          }
          else
          {
            v17 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 *, unsigned __int16 *, struct IUPnPAutomationProxy **))(*(_QWORD *)ppv + 32LL))(
                    ppv,
                    v11,
                    v12,
                    a2);
            v7 = v17;
            if ( v17 < 0 )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  98,
                  (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids,
                  (unsigned int)"HrParseControlQueryString(): Failed to get automation proxy",
                  v17);
              }
            }
            else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                   && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids);
            }
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
          }
        }
        v15 = WPP_GLOBAL_Control;
LABEL_70:
        if ( v11 )
        {
          free(v11);
          v15 = WPP_GLOBAL_Control;
        }
        if ( !v12 )
        {
LABEL_75:
          if ( !v7 )
            return v7;
          goto LABEL_76;
        }
        free(v12);
LABEL_74:
        v15 = WPP_GLOBAL_Control;
        goto LABEL_75;
      }
      if ( v20 - 1 <= 0x7FFFFFFE )
      {
        if ( v19 <= 0x7FFFFFFE )
        {
          v22 = v19;
          v23 = v21;
          do
          {
            if ( !v22 )
              break;
            if ( !*v18 )
              break;
            *v23++ = *v18++;
            --v22;
            --v20;
          }
          while ( v20 );
          v24 = v23 - 1;
          if ( v20 )
            v24 = v23;
          *v24 = 0;
          v7 = v20 == 0 ? 0x8007007A : 0;
          if ( !v20 )
            goto LABEL_33;
          if ( !v14[1] || !*v21 )
          {
            v7 = -2147024809;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                93,
                (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids,
                (unsigned int)"HrParseControlQueryString(): No service ID found",
                87);
            goto LABEL_33;
          }
          v11 = WszFromSz(v21);
          if ( v11 )
          {
            v25 = WszFromSz(v14 + 1);
            v12 = v25;
            if ( v25 )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
              {
                WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, v26, (_DWORD)v11, (__int64)v25);
              }
              goto LABEL_33;
            }
            v7 = -2147024882;
            v27 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            {
LABEL_33:
              free(v21);
              goto LABEL_22;
            }
            v28 = 91;
            v29 = "HrParseControlQueryString(): Failed to convert Service ID to unicode string";
          }
          else
          {
            v7 = -2147024882;
            v27 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_33;
            v28 = 92;
            v29 = "HrParseControlQueryString(): Failed to convert UDN to unicode string";
          }
          WPP_SF_sd(v27[2], v28, (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids, (_DWORD)v29, 14);
          goto LABEL_33;
        }
        *v21 = 0;
      }
      v7 = -2147024809;
      goto LABEL_33;
    }
LABEL_19:
    v7 = -2147024809;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v7;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        95,
        (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids,
        (unsigned int)"HrParseControlQueryString(): Could not find delimiter character",
        87);
      goto LABEL_22;
    }
  }
LABEL_76:
  if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 1) != 0 )
    WPP_SF_sd(
      v15[2],
      100,
      (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids,
      (unsigned int)"HrParseControlQueryString(): Exiting",
      v7);
  return v7;
}

```

## disassembly

```asm
0x180005674  push    rbx
0x180005676  push    rbp
0x180005677  push    rsi
0x180005678  push    rdi
0x180005679  push    r12
0x18000567b  push    r13
0x18000567d  push    r14
0x18000567f  push    r15
0x180005681  sub     rsp, 38h
0x180005685  mov     r10d, 7FFFFFFFh
0x18000568b  lea     rax, aControl; "control="
0x180005692  mov     r8d, r10d
0x180005695  mov     r12, rdx
0x180005698  mov     r11, rcx
0x18000569b  xor     r9d, r9d
0x18000569e  cmp     [rax], r9b
0x1800056a1  jz      short loc_1800056AC
0x1800056a3  inc     rax
0x1800056a6  sub     r8, 1
0x1800056aa  jnz     short loc_18000569E
0x1800056ac  mov     rax, r8
0x1800056af  mov     ebp, 80070057h
0x1800056b4  neg     rax
0x1800056b7  mov     rcx, r10
0x1800056ba  mov     rax, r8
0x1800056bd  sbb     ebx, ebx
0x1800056bf  sub     rcx, r8
0x1800056c2  not     ebx
0x1800056c4  and     ebx, ebp
0x1800056c6  neg     rax
0x1800056c9  sbb     rdx, rdx
0x1800056cc  and     rdx, rcx
0x1800056cf  test    r8, r8
0x1800056d2  jnz     short loc_1800056D8
0x1800056d4  xor     edx, edx
0x1800056d6  jmp     short loc_180005718
0x1800056d8  test    r11, r11
0x1800056db  jz      short loc_180005713
0x1800056dd  mov     rcx, r10
0x1800056e0  mov     rax, r11
0x1800056e3  cmp     [rax], r9b
0x1800056e6  jz      short loc_1800056F1
0x1800056e8  inc     rax
0x1800056eb  sub     rcx, 1
0x1800056ef  jnz     short loc_1800056E3
0x1800056f1  sub     r10, rcx
0x1800056f4  mov     rax, rcx
0x1800056f7  neg     rax
0x1800056fa  mov     rax, rcx
0x1800056fd  sbb     r9, r9
0x180005700  and     r9, r10
0x180005703  neg     rax
0x180005706  sbb     ebx, ebx
0x180005708  not     ebx
0x18000570a  and     ebx, ebp
0x18000570c  test    rcx, rcx
0x18000570f  jz      short loc_180005715
0x180005711  jmp     short loc_180005718
0x180005713  mov     ebx, ebp
0x180005715  xor     r9d, r9d
0x180005718  lea     r14, WPP_GLOBAL_Control
0x18000571f  test    ebx, ebx
0x180005721  js      loc_180005ADC
0x180005727  cmp     r9, rdx
0x18000572a  jbe     loc_180005B25
0x180005730  xor     edi, edi
0x180005732  xor     esi, esi
0x180005734  mov     ecx, edx
0x180005736  cmp     edx, r9d
0x180005739  jnb     short loc_180005753
0x18000573b  mov     r13d, ecx
0x18000573e  add     r13, r11
0x180005741  cmp     byte ptr [r13+0], 2Bh ; '+'
0x180005746  jz      loc_180005832
0x18000574c  inc     ecx
0x18000574e  cmp     ecx, r9d
0x180005751  jb      short loc_18000573B
0x180005753  mov     ebx, ebp
0x180005755  mov     rcx, cs:WPP_GLOBAL_Control
0x18000575c  cmp     rcx, r14
0x18000575f  jz      loc_180005B12
0x180005765  test    byte ptr [rcx+1Ch], 1
0x180005769  jz      loc_180005AE7
0x18000576f  mov     edx, 5Fh ; '_'
0x180005774  mov     dword ptr [rsp+78h+ppv], ebp
0x180005778  lea     r9, aHrparsecontrol_4; "HrParseControlQueryString(): Could not "...
0x18000577f  mov     rcx, [rcx+10h]
0x180005783  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x18000578a  call    WPP_SF_sd
0x18000578f  test    ebx, ebx
0x180005791  js      loc_180005AB2
0x180005797  xor     edx, edx; pUnkOuter
0x180005799  mov     [rsp+78h+arg_10], 0
0x1800057a5  lea     rax, [rsp+78h+arg_10]
0x1800057ad  lea     r9, IID_IUPnPRegistrarLookup; riid
0x1800057b4  mov     [rsp+78h+ppv], rax; ppv
0x1800057b9  lea     rcx, CLSID_UPnPRegistrar; rclsid
0x1800057c0  lea     r8d, [rdx+1]; dwClsContext
0x1800057c4  call    cs:__imp_CoCreateInstance
0x1800057ca  mov     ebx, eax
0x1800057cc  test    eax, eax
0x1800057ce  js      loc_180005A80
0x1800057d4  mov     rcx, [rsp+78h+arg_10]
0x1800057dc  mov     r9, r12
0x1800057df  mov     r8, rsi
0x1800057e2  mov     rdx, rdi
0x1800057e5  mov     rax, [rcx]
0x1800057e8  mov     rax, [rax+20h]
0x1800057ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057f1  mov     ebx, eax
0x1800057f3  test    eax, eax
0x1800057f5  js      loc_180005A38
0x1800057fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180005802  cmp     rcx, r14
0x180005805  jz      loc_180005A6A
0x18000580b  test    dword ptr [rcx+1Ch], 400h
0x180005812  jz      loc_180005A6A
0x180005818  mov     rcx, [rcx+10h]
0x18000581c  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x180005823  mov     edx, 61h ; 'a'
0x180005828  call    WPP_SF_
0x18000582d  jmp     loc_180005A6A
0x180005832  lea     r15, [rdx+r11]
0x180005836  mov     ebx, r13d
0x180005839  sub     ebx, r15d
0x18000583c  lea     eax, [rbx+1]
0x18000583f  mov     ecx, eax; Size
0x180005841  mov     ebp, eax
0x180005843  call    cs:__imp_malloc
0x180005849  mov     r14, rax
0x18000584c  test    rax, rax
0x18000584f  jz      loc_1800059FB
0x180005855  lea     rax, [rbp-1]
0x180005859  mov     ecx, 7FFFFFFEh
0x18000585e  cmp     rax, rcx
0x180005861  ja      short loc_18000586A
0x180005863  cmp     ebx, ecx
0x180005865  jbe     short loc_180005884
0x180005867  mov     [r14], sil
0x18000586a  mov     ebx, 80070057h
0x18000586f  mov     rcx, r14; Block
0x180005872  call    cs:__imp_free
0x180005878  lea     r14, WPP_GLOBAL_Control
0x18000587f  jmp     loc_18000578F
0x180005884  mov     eax, ebx
0x180005886  mov     rcx, r14
0x180005889  test    rax, rax
0x18000588c  jz      short loc_1800058A6
0x18000588e  mov     dl, [r15]
0x180005891  test    dl, dl
0x180005893  jz      short loc_1800058A6
0x180005895  mov     [rcx], dl
0x180005897  inc     r15
0x18000589a  inc     rcx
0x18000589d  dec     rax
0x1800058a0  sub     rbp, 1
0x1800058a4  jnz     short loc_180005889
0x1800058a6  test    rbp, rbp
0x1800058a9  lea     rax, [rcx-1]
0x1800058ad  cmovnz  rax, rcx
0x1800058b1  mov     [rax], sil
0x1800058b4  mov     rax, rbp
0x1800058b7  neg     rax
0x1800058ba  sbb     ebx, ebx
0x1800058bc  not     ebx
0x1800058be  and     ebx, 8007007Ah
0x1800058c4  test    rbp, rbp
0x1800058c7  jz      short loc_18000586F
0x1800058c9  cmp     [r13+1], sil
0x1800058cd  jz      loc_1800059C3
0x1800058d3  cmp     [r14], sil
0x1800058d6  jz      loc_1800059C3
0x1800058dc  mov     rcx, r14; lpMultiByteStr
0x1800058df  call    ?WszFromSz@@YAPEAGPEBD@Z; WszFromSz(char const *)
0x1800058e4  mov     rdi, rax
0x1800058e7  test    rax, rax
0x1800058ea  jz      loc_180005976
0x1800058f0  lea     rcx, [r13+1]; lpMultiByteStr
0x1800058f4  call    ?WszFromSz@@YAPEAGPEBD@Z; WszFromSz(char const *)
0x1800058f9  mov     rsi, rax
0x1800058fc  test    rax, rax
0x1800058ff  jz      short loc_180005940
0x180005901  mov     rcx, cs:WPP_GLOBAL_Control
0x180005908  lea     rdx, WPP_GLOBAL_Control
0x18000590f  cmp     rcx, rdx
0x180005912  jz      loc_18000586F
0x180005918  test    dword ptr [rcx+1Ch], 400h
0x18000591f  jz      loc_18000586F
0x180005925  mov     rcx, [rcx+10h]
0x180005929  mov     edx, 5Ah ; 'Z'
0x18000592e  mov     r9, rdi
0x180005931  mov     [rsp+78h+ppv], rax
0x180005936  call    WPP_SF_SS
0x18000593b  jmp     loc_18000586F
0x180005940  mov     eax, 8007000Eh
0x180005945  mov     ebx, eax
0x180005947  mov     rcx, cs:WPP_GLOBAL_Control
0x18000594e  lea     rdx, WPP_GLOBAL_Control
0x180005955  cmp     rcx, rdx
0x180005958  jz      loc_18000586F
0x18000595e  test    byte ptr [rcx+1Ch], 1
0x180005962  jz      loc_18000586F
0x180005968  mov     edx, 5Bh ; '['
0x18000596d  lea     r9, aHrparsecontrol_6; "HrParseControlQueryString(): Failed to "...
0x180005974  jmp     short loc_1800059AA
0x180005976  mov     eax, 8007000Eh
0x18000597b  mov     ebx, eax
0x18000597d  mov     rcx, cs:WPP_GLOBAL_Control
0x180005984  lea     rdx, WPP_GLOBAL_Control
0x18000598b  cmp     rcx, rdx
0x18000598e  jz      loc_18000586F
0x180005994  test    byte ptr [rcx+1Ch], 1
0x180005998  jz      loc_18000586F
0x18000599e  mov     edx, 5Ch ; '\'
0x1800059a3  lea     r9, aHrparsecontrol_3; "HrParseControlQueryString(): Failed to "...
0x1800059aa  mov     dword ptr [rsp+78h+ppv], eax
0x1800059ae  mov     rcx, [rcx+10h]
0x1800059b2  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x1800059b9  call    WPP_SF_sd
0x1800059be  jmp     loc_18000586F
0x1800059c3  mov     ebx, 80070057h
0x1800059c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800059cf  lea     rdx, WPP_GLOBAL_Control
0x1800059d6  cmp     rcx, rdx
0x1800059d9  jz      loc_18000586F
0x1800059df  test    byte ptr [rcx+1Ch], 1
0x1800059e3  jz      loc_18000586F
0x1800059e9  mov     edx, 5Dh ; ']'
0x1800059ee  mov     dword ptr [rsp+78h+ppv], ebx
0x1800059f2  lea     r9, aHrparsecontrol_7; "HrParseControlQueryString(): No service"...
0x1800059f9  jmp     short loc_1800059AE
0x1800059fb  mov     eax, 8007000Eh
0x180005a00  mov     ebx, eax
0x180005a02  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a09  lea     r14, WPP_GLOBAL_Control
0x180005a10  cmp     rcx, r14
0x180005a13  jz      loc_180005B12
0x180005a19  test    byte ptr [rcx+1Ch], 1
0x180005a1d  jz      loc_180005AE7
0x180005a23  mov     edx, 5Eh ; '^'
0x180005a28  mov     dword ptr [rsp+78h+ppv], eax
0x180005a2c  lea     r9, aHrparsecontrol_0; "HrParseControlQueryString(): Failed to "...
0x180005a33  jmp     loc_18000577F
0x180005a38  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a3f  cmp     rcx, r14
0x180005a42  jz      short loc_180005A6A
0x180005a44  test    byte ptr [rcx+1Ch], 1
0x180005a48  jz      short loc_180005A6A
0x180005a4a  mov     rcx, [rcx+10h]
0x180005a4e  lea     r9, aHrparsecontrol; "HrParseControlQueryString(): Failed to "...
0x180005a55  mov     edx, 62h ; 'b'
0x180005a5a  mov     dword ptr [rsp+78h+ppv], eax
0x180005a5e  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x180005a65  call    WPP_SF_sd
0x180005a6a  mov     rcx, [rsp+78h+arg_10]
0x180005a72  mov     rax, [rcx]
0x180005a75  mov     rax, [rax+10h]
0x180005a79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a7e  jmp     short loc_180005AB2
0x180005a80  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a87  cmp     rcx, r14
0x180005a8a  jz      short loc_180005AB9
0x180005a8c  test    byte ptr [rcx+1Ch], 1
0x180005a90  jz      short loc_180005AB9
0x180005a92  mov     rcx, [rcx+10h]
0x180005a96  lea     r9, aHrparsecontrol_2; "HrParseControlQueryString(): Failed to "...
0x180005a9d  mov     edx, 63h ; 'c'
0x180005aa2  mov     dword ptr [rsp+78h+ppv], eax
0x180005aa6  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x180005aad  call    WPP_SF_sd
0x180005ab2  mov     rcx, cs:WPP_GLOBAL_Control
0x180005ab9  test    rdi, rdi
0x180005abc  jz      short loc_180005ACE
0x180005abe  mov     rcx, rdi; Block
0x180005ac1  call    cs:__imp_free
0x180005ac7  mov     rcx, cs:WPP_GLOBAL_Control
0x180005ace  test    rsi, rsi
0x180005ad1  jz      short loc_180005AE3
0x180005ad3  mov     rcx, rsi; Block
0x180005ad6  call    cs:__imp_free
0x180005adc  mov     rcx, cs:WPP_GLOBAL_Control
0x180005ae3  test    ebx, ebx
0x180005ae5  jz      short loc_180005B12
0x180005ae7  cmp     rcx, r14
0x180005aea  jz      short loc_180005B12
0x180005aec  test    byte ptr [rcx+1Ch], 1
0x180005af0  jz      short loc_180005B12
0x180005af2  mov     rcx, [rcx+10h]
0x180005af6  lea     r9, aHrparsecontrol_5; "HrParseControlQueryString(): Exiting"
0x180005afd  mov     edx, 64h ; 'd'
0x180005b02  mov     dword ptr [rsp+78h+ppv], ebx
0x180005b06  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x180005b0d  call    WPP_SF_sd
0x180005b12  mov     eax, ebx
0x180005b14  add     rsp, 38h
0x180005b18  pop     r15
0x180005b1a  pop     r14
0x180005b1c  pop     r13
0x180005b1e  pop     r12
0x180005b20  pop     rdi
  ... truncated ...
```
