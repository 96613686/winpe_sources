# Triggers::Trigulator::WriteRegistrationData(HKEY__ *)

- ea: `0x180019150`
- end: `0x180019849`
- name: `?WriteRegistrationData@Trigulator@Triggers@@AEBAJPEAUHKEY__@@@Z`
- size: `1785`
- prototype: `int(Triggers::Trigulator *__hidden this, HKEY)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180018a20`

## callees

- `0x180019150`
- `0x180056794`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800191c3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180019269`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180019314`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800193bf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001946d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001951b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800195c9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180019677`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180019725`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800197d0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800191c3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180019269`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180019314`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800193bf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001946d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001951b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800195c9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180019677`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180019725`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800197d0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180019194`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800192b9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180019364`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001940f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800194bd`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001956b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180019619`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800196c7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180019775`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180019820`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180019194`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800192b9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180019364`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001940f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800194bd`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001956b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180019619`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800196c7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180019775`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180019820`

## string_xrefs

- `0x1800193b8`: `SecurityDescriptor`
- `0x1800193e7`: `SecurityDescriptor`
- `0x180019405`: `SecurityDescriptor`

## pseudocode

```c
__int64 __fastcall Triggers::Trigulator::WriteRegistrationData(Triggers::Trigulator *this, HKEY a2)
{
  LSTATUS v4; // eax
  LSTATUS v5; // ebx
  LSTATUS v6; // eax
  bool v7; // cc
  __int64 v9; // rbp
  const BYTE **v10; // rcx
  const BYTE *lpData; // rdx
  __int64 v12; // rax
  LSTATUS v13; // eax
  LSTATUS v14; // eax
  const BYTE **v15; // rcx
  const BYTE *v16; // rdx
  __int64 v17; // rax
  LSTATUS v18; // eax
  LSTATUS v19; // eax
  const BYTE **v20; // rcx
  const BYTE *v21; // rdx
  __int64 v22; // rax
  LSTATUS v23; // eax
  LSTATUS v24; // eax
  const BYTE **v25; // rcx
  const BYTE *v26; // rdx
  __int64 v27; // rax
  LSTATUS v28; // eax
  LSTATUS v29; // eax
  const BYTE **v30; // rcx
  const BYTE *v31; // rdx
  __int64 v32; // rax
  LSTATUS v33; // eax
  LSTATUS v34; // eax
  const BYTE **v35; // rcx
  const BYTE *v36; // rdx
  __int64 v37; // rax
  LSTATUS v38; // eax
  LSTATUS v39; // eax
  const BYTE **v40; // rcx
  const BYTE *v41; // rdx
  __int64 v42; // rax
  LSTATUS v43; // eax
  LSTATUS v44; // eax
  const BYTE **v45; // rcx
  const BYTE *v46; // rdx
  __int64 v47; // rax
  LSTATUS v48; // eax
  LSTATUS v49; // eax
  const BYTE **v50; // rcx
  const BYTE *v51; // rcx
  LSTATUS v52; // eax
  LSTATUS v53; // eax
  int Data; // [rsp+80h] [rbp+8h] BYREF

  Data = *(_DWORD *)(*((_QWORD *)this + 6) + 96LL);
  if ( Data )
  {
    v6 = RegSetValueExW(a2, L"Schema", 0, 4u, (const BYTE *)&Data, 4u);
    v5 = v6;
    if ( v6
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        (unsigned int)WPP_2e3cbcf08cb7377099a4c131f2f33a2b_Traceguids,
        (unsigned int)L"Schema",
        v6);
    }
  }
  else
  {
    v4 = RegDeleteValueW(a2, L"Schema");
    v5 = 0;
    if ( v4 != 2 )
      v5 = v4;
  }
  v7 = v5 <= 0;
  if ( !v5 )
  {
    v9 = -1;
    v10 = *(const BYTE ***)(*((_QWORD *)this + 6) + 112LL);
    if ( v10 && (lpData = *v10) != 0 )
    {
      v12 = -1;
      do
        ++v12;
      while ( *(_WORD *)&lpData[2 * v12] );
      v13 = RegSetValueExW(a2, L"Version", 0, 1u, lpData, 2 * v12 + 2);
      v5 = v13;
      if ( v13
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          (unsigned int)WPP_2e3cbcf08cb7377099a4c131f2f33a2b_Traceguids,
          (unsigned int)L"Version",
          v13);
      }
    }
    else
    {
      v14 = RegDeleteValueW(a2, L"Version");
      v5 = 0;
      if ( v14 != 2 )
        v5 = v14;
    }
    v7 = v5 <= 0;
    if ( !v5 )
    {
      v15 = *(const BYTE ***)(*((_QWORD *)this + 6) + 104LL);
      if ( v15 && (v16 = *v15) != 0 )
      {
        v17 = -1;
        do
          ++v17;
        while ( *(_WORD *)&v16[2 * v17] );
        v18 = RegSetValueExW(a2, L"Date", 0, 1u, v16, 2 * v17 + 2);
        v5 = v18;
        if ( v18
          && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            16,
            (unsigned int)WPP_2e3cbcf08cb7377099a4c131f2f33a2b_Traceguids,
            (unsigned int)L"Date",
            v18);
        }
      }
      else
      {
        v19 = RegDeleteValueW(a2, L"Date");
        v5 = 0;
        if ( v19 != 2 )
          v5 = v19;
      }
      v7 = v5 <= 0;
      if ( !v5 )
      {
        v20 = *(const BYTE ***)(*((_QWORD *)this + 6) + 120LL);
        if ( v20 && (v21 = *v20) != 0 )
        {
          v22 = -1;
          do
            ++v22;
          while ( *(_WORD *)&v21[2 * v22] );
          v23 = RegSetValueExW(a2, L"SecurityDescriptor", 0, 1u, v21, 2 * v22 + 2);
          v5 = v23;
          if ( v23
            && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              16,
              (unsigned int)WPP_2e3cbcf08cb7377099a4c131f2f33a2b_Traceguids,
              (unsigned int)L"SecurityDescriptor",
              v23);
          }
        }
        else
        {
          v24 = RegDeleteValueW(a2, L"SecurityDescriptor");
          v5 = 0;
          if ( v24 != 2 )
            v5 = v24;
        }
        v7 = v5 <= 0;
        if ( !v5 )
        {
          v25 = *(const BYTE ***)(*((_QWORD *)this + 6) + 128LL);
          if ( v25 && (v26 = *v25) != 0 )
          {
            v27 = -1;
            do
              ++v27;
            while ( *(_WORD *)&v26[2 * v27] );
            v28 = RegSetValueExW(a2, L"Source", 0, 1u, v26, 2 * v27 + 2);
            v5 = v28;
            if ( v28
              && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                16,
                (unsigned int)WPP_2e3cbcf08cb7377099a4c131f2f33a2b_Traceguids,
                (unsigned int)L"Source",
                v28);
            }
          }
          else
          {
            v29 = RegDeleteValueW(a2, L"Source");
            v5 = 0;
            if ( v29 != 2 )
              v5 = v29;
          }
          v7 = v5 <= 0;
          if ( !v5 )
          {
            v30 = *(const BYTE ***)(*((_QWORD *)this + 6) + 136LL);
            if ( v30 && (v31 = *v30) != 0 )
            {
              v32 = -1;
              do
                ++v32;
              while ( *(_WORD *)&v31[2 * v32] );
              v33 = RegSetValueExW(a2, L"Author", 0, 1u, v31, 2 * v32 + 2);
              v5 = v33;
              if ( v33
                && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_Sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  16,
                  (unsigned int)WPP_2e3cbcf08cb7377099a4c131f2f33a2b_Traceguids,
                  (unsigned int)L"Author",
                  v33);
              }
            }
            else
            {
              v34 = RegDeleteValueW(a2, L"Author");
              v5 = 0;
              if ( v34 != 2 )
                v5 = v34;
            }
            v7 = v5 <= 0;
            if ( !v5 )
            {
              v35 = *(const BYTE ***)(*((_QWORD *)this + 6) + 144LL);
              if ( v35 && (v36 = *v35) != 0 )
              {
                v37 = -1;
                do
                  ++v37;
                while ( *(_WORD *)&v36[2 * v37] );
                v38 = RegSetValueExW(a2, L"Description", 0, 1u, v36, 2 * v37 + 2);
                v5 = v38;
                if ( v38
                  && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_Sd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    16,
                    (unsigned int)WPP_2e3cbcf08cb7377099a4c131f2f33a2b_Traceguids,
                    (unsigned int)L"Description",
                    v38);
                }
              }
              else
              {
                v39 = RegDeleteValueW(a2, L"Description");
                v5 = 0;
                if ( v39 != 2 )
                  v5 = v39;
              }
              v7 = v5 <= 0;
              if ( !v5 )
              {
                v40 = *(const BYTE ***)(*((_QWORD *)this + 6) + 152LL);
                if ( v40 && (v41 = *v40) != 0 )
                {
                  v42 = -1;
                  do
                    ++v42;
                  while ( *(_WORD *)&v41[2 * v42] );
                  v43 = RegSetValueExW(a2, L"Documentation", 0, 1u, v41, 2 * v42 + 2);
                  v5 = v43;
                  if ( v43
                    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    WPP_SF_Sd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      16,
                      (unsigned int)WPP_2e3cbcf08cb7377099a4c131f2f33a2b_Traceguids,
                      (unsigned int)L"Documentation",
                      v43);
                  }
                }
                else
                {
                  v44 = RegDeleteValueW(a2, L"Documentation");
                  v5 = 0;
                  if ( v44 != 2 )
                    v5 = v44;
                }
                v7 = v5 <= 0;
                if ( !v5 )
                {
                  v45 = *(const BYTE ***)(*((_QWORD *)this + 6) + 160LL);
                  if ( v45 && (v46 = *v45) != 0 )
                  {
                    v47 = -1;
                    do
                      ++v47;
                    while ( *(_WORD *)&v46[2 * v47] );
                    v48 = RegSetValueExW(a2, L"URI", 0, 1u, v46, 2 * v47 + 2);
                    v5 = v48;
                    if ( v48
                      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      WPP_SF_Sd(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        16,
                        (unsigned int)WPP_2e3cbcf08cb7377099a4c131f2f33a2b_Traceguids,
                        (unsigned int)L"URI",
                        v48);
                    }
                  }
                  else
                  {
                    v49 = RegDeleteValueW(a2, L"URI");
                    v5 = 0;
                    if ( v49 != 2 )
                      v5 = v49;
                  }
                  v7 = v5 <= 0;
                  if ( !v5 )
                  {
                    v50 = *(const BYTE ***)(*((_QWORD *)this + 6) + 168LL);
                    if ( v50 && (v51 = *v50) != 0 )
                    {
                      do
                        ++v9;
                      while ( *(_WORD *)&v51[2 * v9] );
                      v52 = RegSetValueExW(a2, L"Data", 0, 1u, v51, 2 * v9 + 2);
                      v5 = v52;
                      if ( v52
                        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                      {
                        WPP_SF_Sd(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          16,
                          (unsigned int)WPP_2e3cbcf08cb7377099a4c131f2f33a2b_Traceguids,
                          (unsigned int)L"Data",
                          v52);
                      }
                    }
                    else
                    {
                      v53 = RegDeleteValueW(a2, L"Data");
                      v5 = 0;
                      if ( v53 != 2 )
                        v5 = v53;
                    }
                    v7 = v5 <= 0;
                    if ( !v5 )
                      return 0;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  if ( !v7 )
    return (unsigned __int16)v5 | 0x80070000;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180019150  mov     r11, rsp
0x180019153  push    rbx
0x180019154  push    rbp
0x180019155  push    rsi
0x180019156  push    rdi
0x180019157  push    r12
0x180019159  push    r13
0x18001915b  push    r14
0x18001915d  push    r15
0x18001915f  sub     rsp, 38h
0x180019163  mov     rax, [rcx+30h]
0x180019167  lea     r12, WPP_GLOBAL_Control
0x18001916e  mov     rsi, rdx
0x180019171  xor     r15d, r15d
0x180019174  mov     r14, rcx
0x180019177  lea     rdx, aSchema; "Schema"
0x18001917e  mov     r13d, 40000h
0x180019184  mov     rcx, rsi; hKey
0x180019187  mov     r8d, [rax+60h]
0x18001918b  mov     [r11+8], r8d
0x18001918f  test    r8d, r8d
0x180019192  jnz     short loc_1800191A8
0x180019194  call    cs:__imp_RegDeleteValueW
0x18001919a  lea     edi, [r15+2]
0x18001919e  mov     ebx, r15d
0x1800191a1  cmp     eax, edi
0x1800191a3  cmovnz  ebx, eax
0x1800191a6  jmp     short loc_18001920A
0x1800191a8  mov     r9d, 4; dwType
0x1800191ae  lea     rax, [rsp+78h+Data]
0x1800191b6  mov     [rsp+78h+cbData], r9d; cbData
0x1800191bb  xor     r8d, r8d; Reserved
0x1800191be  mov     [rsp+78h+lpData], rax; lpData
0x1800191c3  call    cs:__imp_RegSetValueExW
0x1800191c9  mov     ebx, eax
0x1800191cb  mov     edi, 2
0x1800191d0  test    eax, eax
0x1800191d2  jz      short loc_18001920A
0x1800191d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800191db  cmp     rcx, r12
0x1800191de  jz      short loc_18001920A
0x1800191e0  test    [rcx+1Ch], r13d
0x1800191e4  jz      short loc_18001920A
0x1800191e6  cmp     [rcx+19h], dil
0x1800191ea  jb      short loc_18001920A
0x1800191ec  mov     rcx, [rcx+10h]
0x1800191f0  lea     edx, [rdi+0Dh]
0x1800191f3  lea     r9, aSchema; "Schema"
0x1800191fa  mov     dword ptr [rsp+78h+lpData], eax
0x1800191fe  lea     r8, WPP_2e3cbcf08cb7377099a4c131f2f33a2b_Traceguids
0x180019205  call    WPP_SF_Sd
0x18001920a  test    ebx, ebx
0x18001920c  jz      short loc_180019220
0x18001920e  jle     short loc_180019219
0x180019210  movzx   ebx, bx
0x180019213  or      ebx, 80070000h
0x180019219  mov     eax, ebx
0x18001921b  jmp     loc_180019838
0x180019220  mov     rax, [r14+30h]
0x180019224  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180019228  mov     rcx, [rax+70h]
0x18001922c  test    rcx, rcx
0x18001922f  jz      short loc_1800192AF
0x180019231  mov     rdx, [rcx]
0x180019234  test    rdx, rdx
0x180019237  jz      short loc_1800192AF
0x180019239  mov     rax, rbp
0x18001923c  inc     rax
0x18001923f  cmp     [rdx+rax*2], r15w
0x180019244  jnz     short loc_18001923C
0x180019246  lea     eax, ds:2[rax*2]
0x18001924d  mov     r9d, 1; dwType
0x180019253  mov     [rsp+78h+cbData], eax; cbData
0x180019257  xor     r8d, r8d; Reserved
0x18001925a  mov     [rsp+78h+lpData], rdx; lpData
0x18001925f  mov     rcx, rsi; hKey
0x180019262  lea     rdx, aVersion_0; "Version"
0x180019269  call    cs:__imp_RegSetValueExW
0x18001926f  mov     ebx, eax
0x180019271  test    eax, eax
0x180019273  jz      short loc_1800192C7
0x180019275  mov     rcx, cs:WPP_GLOBAL_Control
0x18001927c  cmp     rcx, r12
0x18001927f  jz      short loc_1800192C7
0x180019281  test    [rcx+1Ch], r13d
0x180019285  jz      short loc_1800192C7
0x180019287  cmp     [rcx+19h], dil
0x18001928b  jb      short loc_1800192C7
0x18001928d  mov     rcx, [rcx+10h]
0x180019291  lea     r9, aVersion_0; "Version"
0x180019298  mov     edx, 10h
0x18001929d  mov     dword ptr [rsp+78h+lpData], eax
0x1800192a1  lea     r8, WPP_2e3cbcf08cb7377099a4c131f2f33a2b_Traceguids
0x1800192a8  call    WPP_SF_Sd
0x1800192ad  jmp     short loc_1800192C7
0x1800192af  lea     rdx, aVersion_0; "Version"
0x1800192b6  mov     rcx, rsi; hKey
0x1800192b9  call    cs:__imp_RegDeleteValueW
0x1800192bf  cmp     eax, edi
0x1800192c1  mov     ebx, r15d
0x1800192c4  cmovnz  ebx, eax
0x1800192c7  test    ebx, ebx
0x1800192c9  jnz     loc_18001920E
0x1800192cf  mov     rax, [r14+30h]
0x1800192d3  mov     rcx, [rax+68h]
0x1800192d7  test    rcx, rcx
0x1800192da  jz      short loc_18001935A
0x1800192dc  mov     rdx, [rcx]
0x1800192df  test    rdx, rdx
0x1800192e2  jz      short loc_18001935A
0x1800192e4  mov     rax, rbp
0x1800192e7  inc     rax
0x1800192ea  cmp     [rdx+rax*2], r15w
0x1800192ef  jnz     short loc_1800192E7
0x1800192f1  lea     eax, ds:2[rax*2]
0x1800192f8  mov     r9d, 1; dwType
0x1800192fe  mov     [rsp+78h+cbData], eax; cbData
0x180019302  xor     r8d, r8d; Reserved
0x180019305  mov     [rsp+78h+lpData], rdx; lpData
0x18001930a  mov     rcx, rsi; hKey
0x18001930d  lea     rdx, aDate; "Date"
0x180019314  call    cs:__imp_RegSetValueExW
0x18001931a  mov     ebx, eax
0x18001931c  test    eax, eax
0x18001931e  jz      short loc_180019372
0x180019320  mov     rcx, cs:WPP_GLOBAL_Control
0x180019327  cmp     rcx, r12
0x18001932a  jz      short loc_180019372
0x18001932c  test    [rcx+1Ch], r13d
0x180019330  jz      short loc_180019372
0x180019332  cmp     [rcx+19h], dil
0x180019336  jb      short loc_180019372
0x180019338  mov     rcx, [rcx+10h]
0x18001933c  lea     r9, aDate; "Date"
0x180019343  mov     edx, 10h
0x180019348  mov     dword ptr [rsp+78h+lpData], eax
0x18001934c  lea     r8, WPP_2e3cbcf08cb7377099a4c131f2f33a2b_Traceguids
0x180019353  call    WPP_SF_Sd
0x180019358  jmp     short loc_180019372
0x18001935a  lea     rdx, aDate; "Date"
0x180019361  mov     rcx, rsi; hKey
0x180019364  call    cs:__imp_RegDeleteValueW
0x18001936a  cmp     eax, edi
0x18001936c  mov     ebx, r15d
0x18001936f  cmovnz  ebx, eax
0x180019372  test    ebx, ebx
0x180019374  jnz     loc_18001920E
0x18001937a  mov     rax, [r14+30h]
0x18001937e  mov     rcx, [rax+78h]
0x180019382  test    rcx, rcx
0x180019385  jz      short loc_180019405
0x180019387  mov     rdx, [rcx]
0x18001938a  test    rdx, rdx
0x18001938d  jz      short loc_180019405
0x18001938f  mov     rax, rbp
0x180019392  inc     rax
0x180019395  cmp     [rdx+rax*2], r15w
0x18001939a  jnz     short loc_180019392
0x18001939c  lea     eax, ds:2[rax*2]
0x1800193a3  mov     r9d, 1; dwType
0x1800193a9  mov     [rsp+78h+cbData], eax; cbData
0x1800193ad  xor     r8d, r8d; Reserved
0x1800193b0  mov     [rsp+78h+lpData], rdx; lpData
0x1800193b5  mov     rcx, rsi; hKey
0x1800193b8  lea     rdx, aSecuritydescri; "SecurityDescriptor"
0x1800193bf  call    cs:__imp_RegSetValueExW
0x1800193c5  mov     ebx, eax
0x1800193c7  test    eax, eax
0x1800193c9  jz      short loc_18001941D
0x1800193cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800193d2  cmp     rcx, r12
0x1800193d5  jz      short loc_18001941D
0x1800193d7  test    [rcx+1Ch], r13d
0x1800193db  jz      short loc_18001941D
0x1800193dd  cmp     [rcx+19h], dil
0x1800193e1  jb      short loc_18001941D
0x1800193e3  mov     rcx, [rcx+10h]
0x1800193e7  lea     r9, aSecuritydescri; "SecurityDescriptor"
0x1800193ee  mov     edx, 10h
0x1800193f3  mov     dword ptr [rsp+78h+lpData], eax
0x1800193f7  lea     r8, WPP_2e3cbcf08cb7377099a4c131f2f33a2b_Traceguids
0x1800193fe  call    WPP_SF_Sd
0x180019403  jmp     short loc_18001941D
0x180019405  lea     rdx, aSecuritydescri; "SecurityDescriptor"
0x18001940c  mov     rcx, rsi; hKey
0x18001940f  call    cs:__imp_RegDeleteValueW
0x180019415  cmp     eax, edi
0x180019417  mov     ebx, r15d
0x18001941a  cmovnz  ebx, eax
0x18001941d  test    ebx, ebx
0x18001941f  jnz     loc_18001920E
0x180019425  mov     rax, [r14+30h]
0x180019429  mov     rcx, [rax+80h]
0x180019430  test    rcx, rcx
0x180019433  jz      short loc_1800194B3
0x180019435  mov     rdx, [rcx]
0x180019438  test    rdx, rdx
0x18001943b  jz      short loc_1800194B3
0x18001943d  mov     rax, rbp
0x180019440  inc     rax
0x180019443  cmp     [rdx+rax*2], r15w
0x180019448  jnz     short loc_180019440
0x18001944a  lea     eax, ds:2[rax*2]
0x180019451  mov     r9d, 1; dwType
0x180019457  mov     [rsp+78h+cbData], eax; cbData
0x18001945b  xor     r8d, r8d; Reserved
0x18001945e  mov     [rsp+78h+lpData], rdx; lpData
0x180019463  mov     rcx, rsi; hKey
0x180019466  lea     rdx, aSource; "Source"
0x18001946d  call    cs:__imp_RegSetValueExW
0x180019473  mov     ebx, eax
0x180019475  test    eax, eax
0x180019477  jz      short loc_1800194CB
0x180019479  mov     rcx, cs:WPP_GLOBAL_Control
0x180019480  cmp     rcx, r12
0x180019483  jz      short loc_1800194CB
0x180019485  test    [rcx+1Ch], r13d
0x180019489  jz      short loc_1800194CB
0x18001948b  cmp     [rcx+19h], dil
0x18001948f  jb      short loc_1800194CB
0x180019491  mov     rcx, [rcx+10h]
0x180019495  lea     r9, aSource; "Source"
0x18001949c  mov     edx, 10h
0x1800194a1  mov     dword ptr [rsp+78h+lpData], eax
0x1800194a5  lea     r8, WPP_2e3cbcf08cb7377099a4c131f2f33a2b_Traceguids
0x1800194ac  call    WPP_SF_Sd
0x1800194b1  jmp     short loc_1800194CB
0x1800194b3  lea     rdx, aSource; "Source"
0x1800194ba  mov     rcx, rsi; hKey
0x1800194bd  call    cs:__imp_RegDeleteValueW
0x1800194c3  cmp     eax, edi
0x1800194c5  mov     ebx, r15d
0x1800194c8  cmovnz  ebx, eax
0x1800194cb  test    ebx, ebx
0x1800194cd  jnz     loc_18001920E
0x1800194d3  mov     rax, [r14+30h]
0x1800194d7  mov     rcx, [rax+88h]
0x1800194de  test    rcx, rcx
0x1800194e1  jz      short loc_180019561
0x1800194e3  mov     rdx, [rcx]
0x1800194e6  test    rdx, rdx
0x1800194e9  jz      short loc_180019561
0x1800194eb  mov     rax, rbp
0x1800194ee  inc     rax
0x1800194f1  cmp     [rdx+rax*2], r15w
0x1800194f6  jnz     short loc_1800194EE
0x1800194f8  lea     eax, ds:2[rax*2]
0x1800194ff  mov     r9d, 1; dwType
0x180019505  mov     [rsp+78h+cbData], eax; cbData
0x180019509  xor     r8d, r8d; Reserved
0x18001950c  mov     [rsp+78h+lpData], rdx; lpData
0x180019511  mov     rcx, rsi; hKey
0x180019514  lea     rdx, psz; "Author"
0x18001951b  call    cs:__imp_RegSetValueExW
0x180019521  mov     ebx, eax
0x180019523  test    eax, eax
0x180019525  jz      short loc_180019579
0x180019527  mov     rcx, cs:WPP_GLOBAL_Control
0x18001952e  cmp     rcx, r12
0x180019531  jz      short loc_180019579
0x180019533  test    [rcx+1Ch], r13d
0x180019537  jz      short loc_180019579
0x180019539  cmp     [rcx+19h], dil
0x18001953d  jb      short loc_180019579
0x18001953f  mov     rcx, [rcx+10h]
0x180019543  lea     r9, psz; "Author"
0x18001954a  mov     edx, 10h
0x18001954f  mov     dword ptr [rsp+78h+lpData], eax
0x180019553  lea     r8, WPP_2e3cbcf08cb7377099a4c131f2f33a2b_Traceguids
0x18001955a  call    WPP_SF_Sd
0x18001955f  jmp     short loc_180019579
0x180019561  lea     rdx, psz; "Author"
0x180019568  mov     rcx, rsi; hKey
0x18001956b  call    cs:__imp_RegDeleteValueW
0x180019571  cmp     eax, edi
0x180019573  mov     ebx, r15d
0x180019576  cmovnz  ebx, eax
0x180019579  test    ebx, ebx
0x18001957b  jnz     loc_18001920E
0x180019581  mov     rax, [r14+30h]
0x180019585  mov     rcx, [rax+90h]
0x18001958c  test    rcx, rcx
0x18001958f  jz      short loc_18001960F
0x180019591  mov     rdx, [rcx]
0x180019594  test    rdx, rdx
0x180019597  jz      short loc_18001960F
0x180019599  mov     rax, rbp
0x18001959c  inc     rax
0x18001959f  cmp     [rdx+rax*2], r15w
0x1800195a4  jnz     short loc_18001959C
0x1800195a6  lea     eax, ds:2[rax*2]
0x1800195ad  mov     r9d, 1; dwType
0x1800195b3  mov     [rsp+78h+cbData], eax; cbData
0x1800195b7  xor     r8d, r8d; Reserved
0x1800195ba  mov     [rsp+78h+lpData], rdx; lpData
0x1800195bf  mov     rcx, rsi; hKey
0x1800195c2  lea     rdx, aDescription; "Description"
0x1800195c9  call    cs:__imp_RegSetValueExW
0x1800195cf  mov     ebx, eax
0x1800195d1  test    eax, eax
  ... truncated ...
```
