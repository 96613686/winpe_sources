# Triggers::Trigulator::WriteRegistrationData(HKEY__ *)

- ea: `0x180032c58`
- end: `0x1800333ee`
- name: `?WriteRegistrationData@Trigulator@Triggers@@AEBAJPEAUHKEY__@@@Z`
- size: `1942`
- prototype: `int(Triggers::Trigulator *__hidden this, HKEY)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800324f0`

## callees

- `0x180032c58`
- `0x180059140`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180032cd1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180032d81`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180032e3c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180032ef7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180032fb5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180033073`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180033131`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800331ef`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800332ad`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180033368`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180032cd1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180032d81`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180032e3c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180032ef7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180032fb5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180033073`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180033131`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800331ef`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800332ad`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180033368`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180032c9c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180032dd7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180032e92`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180032f4d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003300b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800330c9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180033187`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180033245`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180033303`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800333be`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180032c9c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180032dd7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180032e92`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180032f4d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003300b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800330c9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180033187`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180033245`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180033303`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800333be`

## string_xrefs

- `0x180032ef0`: `SecurityDescriptor`
- `0x180032f25`: `SecurityDescriptor`
- `0x180032f43`: `SecurityDescriptor`

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
0x180032c58  mov     r11, rsp
0x180032c5b  push    rbx
0x180032c5c  push    rbp
0x180032c5d  push    rsi
0x180032c5e  push    rdi
0x180032c5f  push    r12
0x180032c61  push    r13
0x180032c63  push    r14
0x180032c65  push    r15
0x180032c67  sub     rsp, 38h
0x180032c6b  mov     rax, [rcx+30h]
0x180032c6f  lea     r12, WPP_GLOBAL_Control
0x180032c76  mov     rsi, rdx
0x180032c79  xor     r15d, r15d
0x180032c7c  mov     r14, rcx
0x180032c7f  lea     rdx, aSchema; "Schema"
0x180032c86  mov     r13d, 40000h
0x180032c8c  mov     rcx, rsi; hKey
0x180032c8f  mov     r8d, [rax+60h]
0x180032c93  mov     [r11+8], r8d
0x180032c97  test    r8d, r8d
0x180032c9a  jnz     short loc_180032CB6
0x180032c9c  call    cs:__imp_RegDeleteValueW
0x180032ca3  nop     dword ptr [rax+rax+00h]
0x180032ca8  lea     edi, [r15+2]
0x180032cac  mov     ebx, r15d
0x180032caf  cmp     eax, edi
0x180032cb1  cmovnz  ebx, eax
0x180032cb4  jmp     short loc_180032D1E
0x180032cb6  mov     r9d, 4; dwType
0x180032cbc  lea     rax, [rsp+78h+Data]
0x180032cc4  mov     [rsp+78h+cbData], r9d; cbData
0x180032cc9  xor     r8d, r8d; Reserved
0x180032ccc  mov     [rsp+78h+lpData], rax; lpData
0x180032cd1  call    cs:__imp_RegSetValueExW
0x180032cd8  nop     dword ptr [rax+rax+00h]
0x180032cdd  mov     ebx, eax
0x180032cdf  mov     edi, 2
0x180032ce4  test    eax, eax
0x180032ce6  jz      short loc_180032D1E
0x180032ce8  mov     rcx, cs:WPP_GLOBAL_Control
0x180032cef  cmp     rcx, r12
0x180032cf2  jz      short loc_180032D1E
0x180032cf4  test    [rcx+1Ch], r13d
0x180032cf8  jz      short loc_180032D1E
0x180032cfa  cmp     [rcx+19h], dil
0x180032cfe  jb      short loc_180032D1E
0x180032d00  mov     rcx, [rcx+10h]
0x180032d04  lea     edx, [rdi+0Dh]
0x180032d07  lea     r9, aSchema; "Schema"
0x180032d0e  mov     dword ptr [rsp+78h+lpData], eax
0x180032d12  lea     r8, WPP_2e3cbcf08cb7377099a4c131f2f33a2b_Traceguids
0x180032d19  call    WPP_SF_Sd
0x180032d1e  test    ebx, ebx
0x180032d20  jz      short loc_180032D34
0x180032d22  jle     short loc_180032D2D
0x180032d24  movzx   ebx, bx
0x180032d27  or      ebx, 80070000h
0x180032d2d  mov     eax, ebx
0x180032d2f  jmp     loc_1800333DC
0x180032d34  mov     rax, [r14+30h]
0x180032d38  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180032d3c  mov     rcx, [rax+70h]
0x180032d40  test    rcx, rcx
0x180032d43  jz      loc_180032DCD
0x180032d49  mov     rdx, [rcx]
0x180032d4c  test    rdx, rdx
0x180032d4f  jz      short loc_180032DCD
0x180032d51  mov     rax, rbp
0x180032d54  inc     rax
0x180032d57  cmp     [rdx+rax*2], r15w
0x180032d5c  jnz     short loc_180032D54
0x180032d5e  lea     eax, ds:2[rax*2]
0x180032d65  mov     r9d, 1; dwType
0x180032d6b  mov     [rsp+78h+cbData], eax; cbData
0x180032d6f  xor     r8d, r8d; Reserved
0x180032d72  mov     [rsp+78h+lpData], rdx; lpData
0x180032d77  mov     rcx, rsi; hKey
0x180032d7a  lea     rdx, aVersion_0; "Version"
0x180032d81  call    cs:__imp_RegSetValueExW
0x180032d88  nop     dword ptr [rax+rax+00h]
0x180032d8d  mov     ebx, eax
0x180032d8f  test    eax, eax
0x180032d91  jz      short loc_180032DEB
0x180032d93  mov     rcx, cs:WPP_GLOBAL_Control
0x180032d9a  cmp     rcx, r12
0x180032d9d  jz      short loc_180032DEB
0x180032d9f  test    [rcx+1Ch], r13d
0x180032da3  jz      short loc_180032DEB
0x180032da5  cmp     [rcx+19h], dil
0x180032da9  jb      short loc_180032DEB
0x180032dab  mov     rcx, [rcx+10h]
0x180032daf  lea     r9, aVersion_0; "Version"
0x180032db6  mov     edx, 10h
0x180032dbb  mov     dword ptr [rsp+78h+lpData], eax
0x180032dbf  lea     r8, WPP_2e3cbcf08cb7377099a4c131f2f33a2b_Traceguids
0x180032dc6  call    WPP_SF_Sd
0x180032dcb  jmp     short loc_180032DEB
0x180032dcd  lea     rdx, aVersion_0; "Version"
0x180032dd4  mov     rcx, rsi; hKey
0x180032dd7  call    cs:__imp_RegDeleteValueW
0x180032dde  nop     dword ptr [rax+rax+00h]
0x180032de3  cmp     eax, edi
0x180032de5  mov     ebx, r15d
0x180032de8  cmovnz  ebx, eax
0x180032deb  test    ebx, ebx
0x180032ded  jnz     loc_180032D22
0x180032df3  mov     rax, [r14+30h]
0x180032df7  mov     rcx, [rax+68h]
0x180032dfb  test    rcx, rcx
0x180032dfe  jz      loc_180032E88
0x180032e04  mov     rdx, [rcx]
0x180032e07  test    rdx, rdx
0x180032e0a  jz      short loc_180032E88
0x180032e0c  mov     rax, rbp
0x180032e0f  inc     rax
0x180032e12  cmp     [rdx+rax*2], r15w
0x180032e17  jnz     short loc_180032E0F
0x180032e19  lea     eax, ds:2[rax*2]
0x180032e20  mov     r9d, 1; dwType
0x180032e26  mov     [rsp+78h+cbData], eax; cbData
0x180032e2a  xor     r8d, r8d; Reserved
0x180032e2d  mov     [rsp+78h+lpData], rdx; lpData
0x180032e32  mov     rcx, rsi; hKey
0x180032e35  lea     rdx, aDate; "Date"
0x180032e3c  call    cs:__imp_RegSetValueExW
0x180032e43  nop     dword ptr [rax+rax+00h]
0x180032e48  mov     ebx, eax
0x180032e4a  test    eax, eax
0x180032e4c  jz      short loc_180032EA6
0x180032e4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180032e55  cmp     rcx, r12
0x180032e58  jz      short loc_180032EA6
0x180032e5a  test    [rcx+1Ch], r13d
0x180032e5e  jz      short loc_180032EA6
0x180032e60  cmp     [rcx+19h], dil
0x180032e64  jb      short loc_180032EA6
0x180032e66  mov     rcx, [rcx+10h]
0x180032e6a  lea     r9, aDate; "Date"
0x180032e71  mov     edx, 10h
0x180032e76  mov     dword ptr [rsp+78h+lpData], eax
0x180032e7a  lea     r8, WPP_2e3cbcf08cb7377099a4c131f2f33a2b_Traceguids
0x180032e81  call    WPP_SF_Sd
0x180032e86  jmp     short loc_180032EA6
0x180032e88  lea     rdx, aDate; "Date"
0x180032e8f  mov     rcx, rsi; hKey
0x180032e92  call    cs:__imp_RegDeleteValueW
0x180032e99  nop     dword ptr [rax+rax+00h]
0x180032e9e  cmp     eax, edi
0x180032ea0  mov     ebx, r15d
0x180032ea3  cmovnz  ebx, eax
0x180032ea6  test    ebx, ebx
0x180032ea8  jnz     loc_180032D22
0x180032eae  mov     rax, [r14+30h]
0x180032eb2  mov     rcx, [rax+78h]
0x180032eb6  test    rcx, rcx
0x180032eb9  jz      loc_180032F43
0x180032ebf  mov     rdx, [rcx]
0x180032ec2  test    rdx, rdx
0x180032ec5  jz      short loc_180032F43
0x180032ec7  mov     rax, rbp
0x180032eca  inc     rax
0x180032ecd  cmp     [rdx+rax*2], r15w
0x180032ed2  jnz     short loc_180032ECA
0x180032ed4  lea     eax, ds:2[rax*2]
0x180032edb  mov     r9d, 1; dwType
0x180032ee1  mov     [rsp+78h+cbData], eax; cbData
0x180032ee5  xor     r8d, r8d; Reserved
0x180032ee8  mov     [rsp+78h+lpData], rdx; lpData
0x180032eed  mov     rcx, rsi; hKey
0x180032ef0  lea     rdx, aSecuritydescri; "SecurityDescriptor"
0x180032ef7  call    cs:__imp_RegSetValueExW
0x180032efe  nop     dword ptr [rax+rax+00h]
0x180032f03  mov     ebx, eax
0x180032f05  test    eax, eax
0x180032f07  jz      short loc_180032F61
0x180032f09  mov     rcx, cs:WPP_GLOBAL_Control
0x180032f10  cmp     rcx, r12
0x180032f13  jz      short loc_180032F61
0x180032f15  test    [rcx+1Ch], r13d
0x180032f19  jz      short loc_180032F61
0x180032f1b  cmp     [rcx+19h], dil
0x180032f1f  jb      short loc_180032F61
0x180032f21  mov     rcx, [rcx+10h]
0x180032f25  lea     r9, aSecuritydescri; "SecurityDescriptor"
0x180032f2c  mov     edx, 10h
0x180032f31  mov     dword ptr [rsp+78h+lpData], eax
0x180032f35  lea     r8, WPP_2e3cbcf08cb7377099a4c131f2f33a2b_Traceguids
0x180032f3c  call    WPP_SF_Sd
0x180032f41  jmp     short loc_180032F61
0x180032f43  lea     rdx, aSecuritydescri; "SecurityDescriptor"
0x180032f4a  mov     rcx, rsi; hKey
0x180032f4d  call    cs:__imp_RegDeleteValueW
0x180032f54  nop     dword ptr [rax+rax+00h]
0x180032f59  cmp     eax, edi
0x180032f5b  mov     ebx, r15d
0x180032f5e  cmovnz  ebx, eax
0x180032f61  test    ebx, ebx
0x180032f63  jnz     loc_180032D22
0x180032f69  mov     rax, [r14+30h]
0x180032f6d  mov     rcx, [rax+80h]
0x180032f74  test    rcx, rcx
0x180032f77  jz      loc_180033001
0x180032f7d  mov     rdx, [rcx]
0x180032f80  test    rdx, rdx
0x180032f83  jz      short loc_180033001
0x180032f85  mov     rax, rbp
0x180032f88  inc     rax
0x180032f8b  cmp     [rdx+rax*2], r15w
0x180032f90  jnz     short loc_180032F88
0x180032f92  lea     eax, ds:2[rax*2]
0x180032f99  mov     r9d, 1; dwType
0x180032f9f  mov     [rsp+78h+cbData], eax; cbData
0x180032fa3  xor     r8d, r8d; Reserved
0x180032fa6  mov     [rsp+78h+lpData], rdx; lpData
0x180032fab  mov     rcx, rsi; hKey
0x180032fae  lea     rdx, aSource; "Source"
0x180032fb5  call    cs:__imp_RegSetValueExW
0x180032fbc  nop     dword ptr [rax+rax+00h]
0x180032fc1  mov     ebx, eax
0x180032fc3  test    eax, eax
0x180032fc5  jz      short loc_18003301F
0x180032fc7  mov     rcx, cs:WPP_GLOBAL_Control
0x180032fce  cmp     rcx, r12
0x180032fd1  jz      short loc_18003301F
0x180032fd3  test    [rcx+1Ch], r13d
0x180032fd7  jz      short loc_18003301F
0x180032fd9  cmp     [rcx+19h], dil
0x180032fdd  jb      short loc_18003301F
0x180032fdf  mov     rcx, [rcx+10h]
0x180032fe3  lea     r9, aSource; "Source"
0x180032fea  mov     edx, 10h
0x180032fef  mov     dword ptr [rsp+78h+lpData], eax
0x180032ff3  lea     r8, WPP_2e3cbcf08cb7377099a4c131f2f33a2b_Traceguids
0x180032ffa  call    WPP_SF_Sd
0x180032fff  jmp     short loc_18003301F
0x180033001  lea     rdx, aSource; "Source"
0x180033008  mov     rcx, rsi; hKey
0x18003300b  call    cs:__imp_RegDeleteValueW
0x180033012  nop     dword ptr [rax+rax+00h]
0x180033017  cmp     eax, edi
0x180033019  mov     ebx, r15d
0x18003301c  cmovnz  ebx, eax
0x18003301f  test    ebx, ebx
0x180033021  jnz     loc_180032D22
0x180033027  mov     rax, [r14+30h]
0x18003302b  mov     rcx, [rax+88h]
0x180033032  test    rcx, rcx
0x180033035  jz      loc_1800330BF
0x18003303b  mov     rdx, [rcx]
0x18003303e  test    rdx, rdx
0x180033041  jz      short loc_1800330BF
0x180033043  mov     rax, rbp
0x180033046  inc     rax
0x180033049  cmp     [rdx+rax*2], r15w
0x18003304e  jnz     short loc_180033046
0x180033050  lea     eax, ds:2[rax*2]
0x180033057  mov     r9d, 1; dwType
0x18003305d  mov     [rsp+78h+cbData], eax; cbData
0x180033061  xor     r8d, r8d; Reserved
0x180033064  mov     [rsp+78h+lpData], rdx; lpData
0x180033069  mov     rcx, rsi; hKey
0x18003306c  lea     rdx, aAuthor; "Author"
0x180033073  call    cs:__imp_RegSetValueExW
0x18003307a  nop     dword ptr [rax+rax+00h]
0x18003307f  mov     ebx, eax
0x180033081  test    eax, eax
0x180033083  jz      short loc_1800330DD
0x180033085  mov     rcx, cs:WPP_GLOBAL_Control
0x18003308c  cmp     rcx, r12
0x18003308f  jz      short loc_1800330DD
0x180033091  test    [rcx+1Ch], r13d
0x180033095  jz      short loc_1800330DD
0x180033097  cmp     [rcx+19h], dil
0x18003309b  jb      short loc_1800330DD
0x18003309d  mov     rcx, [rcx+10h]
0x1800330a1  lea     r9, aAuthor; "Author"
0x1800330a8  mov     edx, 10h
0x1800330ad  mov     dword ptr [rsp+78h+lpData], eax
0x1800330b1  lea     r8, WPP_2e3cbcf08cb7377099a4c131f2f33a2b_Traceguids
0x1800330b8  call    WPP_SF_Sd
0x1800330bd  jmp     short loc_1800330DD
0x1800330bf  lea     rdx, aAuthor; "Author"
0x1800330c6  mov     rcx, rsi; hKey
0x1800330c9  call    cs:__imp_RegDeleteValueW
0x1800330d0  nop     dword ptr [rax+rax+00h]
0x1800330d5  cmp     eax, edi
0x1800330d7  mov     ebx, r15d
0x1800330da  cmovnz  ebx, eax
0x1800330dd  test    ebx, ebx
0x1800330df  jnz     loc_180032D22
0x1800330e5  mov     rax, [r14+30h]
0x1800330e9  mov     rcx, [rax+90h]
0x1800330f0  test    rcx, rcx
0x1800330f3  jz      loc_18003317D
0x1800330f9  mov     rdx, [rcx]
0x1800330fc  test    rdx, rdx
0x1800330ff  jz      short loc_18003317D
0x180033101  mov     rax, rbp
0x180033104  inc     rax
  ... truncated ...
```
