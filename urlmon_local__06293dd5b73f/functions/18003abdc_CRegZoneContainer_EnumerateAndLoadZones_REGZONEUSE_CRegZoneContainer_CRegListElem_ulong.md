# CRegZoneContainer::EnumerateAndLoadZones(REGZONEUSE,CRegZoneContainer::CRegListElem * *,ulong *)

- ea: `0x18003abdc`
- end: `0x18003b29b`
- name: `?EnumerateAndLoadZones@CRegZoneContainer@@QEAAJW4REGZONEUSE@@PEAPEAUCRegListElem@1@PEAK@Z`
- size: `1727`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180019e70`
- `0x18003a744`

## callees

- `0x18002fee0`
- `0x18003abdc`
- `0x18003b2b0`
- `0x18003bef0`
- `0x18003bf74`
- `0x18003c248`
- `0x180128660`
- `0x180129010`

## import_xrefs

- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegEnumUSKeyW` at `0x18003aec5`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegEnumUSKeyW` at `0x18003b1d8`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegEnumUSKeyW` at `0x18003aec5`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegEnumUSKeyW` at `0x18003b1d8`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x18003ad21`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x18003ae4f`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x18003b032`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x18003b071`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x18003b0ca`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x18003b19d`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x18003ad21`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x18003ae4f`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x18003b032`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x18003b071`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x18003b0ca`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x18003b19d`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x18003b13f`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x18003b13f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003aef2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003af7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003aef2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003af7b`

## string_xrefs

- `0x18003b1f7`: `Software\Policies\Microsoft\Windows\CurrentVersion\Internet Settings\TemplatePolicies\`
- `0x18003b23c`: `Software\Microsoft\Windows\CurrentVersion\Internet Settings\TemplatePolicies\`

## pseudocode

```c
__int64 __fastcall CRegZoneContainer::EnumerateAndLoadZones(__int64 a1, unsigned int a2, _QWORD *a3, _DWORD *a4)
{
  int v8; // ebx
  __int64 v9; // rcx
  const wchar_t *v10; // r8
  WCHAR *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rcx
  const wchar_t *v14; // r8
  WCHAR *v15; // rcx
  int v16; // edi
  BOOL fIgnoreHKCU; // eax
  int v18; // r13d
  __int64 v19; // rcx
  const WCHAR *v20; // r8
  __int64 v21; // rdx
  WCHAR *v22; // rax
  __int64 v23; // rcx
  const wchar_t *v24; // r8
  WCHAR *v25; // rcx
  unsigned int v26; // esi
  BOOL v27; // eax
  DWORD v28; // r14d
  SHREGENUM_FLAGS v29; // eax
  LSTATUS v30; // eax
  _QWORD *v31; // rax
  CRegZone *v32; // rbx
  __int64 v33; // rax
  _QWORD *v34; // rax
  _QWORD *v35; // rcx
  unsigned int v36; // r9d
  _QWORD *v37; // rax
  __int64 **v38; // rdx
  __int64 *i; // r8
  BOOL v40; // eax
  __int64 v42; // rcx
  const wchar_t *v43; // r8
  __int64 v44; // rcx
  const wchar_t *v45; // r8
  unsigned int v46; // edx
  HUSKEY phNewUSKey; // [rsp+30h] [rbp-D0h] BYREF
  const unsigned int *v48; // [rsp+38h] [rbp-C8h] BYREF
  HUSKEY hUSKey; // [rsp+40h] [rbp-C0h]
  BOOL v50; // [rsp+48h] [rbp-B8h]
  __int64 v51; // [rsp+4Ch] [rbp-B4h]
  __int64 v52; // [rsp+58h] [rbp-A8h]
  _QWORD *v53; // [rsp+60h] [rbp-A0h]
  WCHAR pwzPath[259]; // [rsp+70h] [rbp-90h] BYREF
  __int16 v55; // [rsp+276h] [rbp+176h]
  WCHAR pwzName[264]; // [rsp+280h] [rbp+180h] BYREF

  v53 = a3;
  v52 = a1;
  v8 = 260;
  if ( a2 )
  {
    if ( a2 == 1 )
    {
      v42 = 259;
      v43 = L"Software\\Policies\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\TemplatePolicies\\";
      v11 = pwzPath;
      v12 = 260;
      do
      {
        if ( !v42 )
          break;
        if ( !*v43 )
          break;
        *v11++ = *v43++;
        --v42;
        --v12;
      }
      while ( v12 );
    }
    else
    {
      if ( a2 != 2 )
        goto LABEL_16;
      v13 = 259;
      v14 = L"Software\\Policies\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\Lockdown_Zones\\";
      v11 = pwzPath;
      v12 = 260;
      do
      {
        if ( !v13 )
          break;
        if ( !*v14 )
          break;
        *v11++ = *v14++;
        --v13;
        --v12;
      }
      while ( v12 );
    }
  }
  else
  {
    v9 = 259;
    v10 = L"Software\\Policies\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\Zones\\";
    v11 = pwzPath;
    v12 = 260;
    do
    {
      if ( !v9 )
        break;
      if ( !*v10 )
        break;
      *v11++ = *v10++;
      --v9;
      --v12;
    }
    while ( v12 );
  }
  v15 = v11 - 1;
  if ( v12 )
    v15 = v11;
  *v15 = 0;
  v55 = 0;
LABEL_16:
  hUSKey = 0;
  v48 = &CRegKey::`vftable';
  v50 = *(_DWORD *)(a1 + 28);
  v51 = 1;
  phNewUSKey = 0;
  CRegKey::Close((CRegKey *)&v48);
  v16 = -2147467259;
  if ( !(_DWORD)v51 )
  {
LABEL_17:
    fIgnoreHKCU = v50;
    goto LABEL_18;
  }
  fIgnoreHKCU = v50;
  if ( !v50 )
  {
    if ( !SHRegOpenUSKeyW(pwzPath, 0x20019u, 0, &phNewUSKey, 1) )
      goto LABEL_19;
    goto LABEL_17;
  }
LABEL_18:
  v18 = -2147467259;
  if ( !SHRegOpenUSKeyW(pwzPath, 0x20019u, 0, &phNewUSKey, fIgnoreHKCU) )
  {
LABEL_19:
    hUSKey = phNewUSKey;
    v18 = CRegZoneContainer::EnumerateAndLoadZones(a1, &v48, a2, a3, a4);
  }
  LODWORD(v51) = 0;
  if ( *(_DWORD *)(a1 + 28) )
    goto LABEL_21;
  phNewUSKey = 0;
  (*((void (__fastcall **)(const unsigned int **))v48 + 2))(&v48);
  if ( !(_DWORD)v51 )
    goto LABEL_69;
  v40 = v50;
  if ( v50 )
  {
LABEL_70:
    if ( SHRegOpenUSKeyW(pwzPath, 0x20019u, 0, &phNewUSKey, v40) )
      goto LABEL_21;
    goto LABEL_71;
  }
  if ( SHRegOpenUSKeyW(pwzPath, 0x20019u, 0, &phNewUSKey, 1) )
  {
LABEL_69:
    v40 = v50;
    goto LABEL_70;
  }
LABEL_71:
  hUSKey = phNewUSKey;
  v18 = CRegZoneContainer::EnumerateAndLoadZones(a1, &v48, a2, a3, a4);
LABEL_21:
  switch ( a2 )
  {
    case 0u:
      v19 = 259;
      v20 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\Zones\\";
      v21 = 260;
      v22 = pwzPath;
      do
      {
        if ( !v19 )
          break;
        if ( !*v20 )
          break;
        *v22++ = *v20++;
        --v19;
        --v21;
      }
      while ( v21 );
LABEL_33:
      v25 = v22 - 1;
      if ( v21 )
        v25 = v22;
      *v25 = 0;
      v55 = 0;
      break;
    case 1u:
      v44 = 259;
      v45 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\TemplatePolicies\\";
      v21 = 260;
      v22 = pwzPath;
      do
      {
        if ( !v44 )
          break;
        if ( !*v45 )
          break;
        *v22++ = *v45++;
        --v44;
        --v21;
      }
      while ( v21 );
      goto LABEL_33;
    case 2u:
      v23 = 259;
      v24 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\Lockdown_Zones\\";
      v21 = 260;
      v22 = pwzPath;
      do
      {
        if ( !v23 )
          break;
        if ( !*v24 )
          break;
        *v22++ = *v24++;
        --v23;
        --v21;
      }
      while ( v21 );
      goto LABEL_33;
  }
  phNewUSKey = 0;
  (*((void (__fastcall **)(const unsigned int **))v48 + 2))(&v48);
  v26 = -2147418113;
  if ( !(_DWORD)v51 )
    goto LABEL_37;
  v27 = v50;
  if ( v50 )
  {
LABEL_38:
    if ( SHRegOpenUSKeyW(pwzPath, 0x20019u, 0, &phNewUSKey, v27) )
      goto LABEL_74;
    goto LABEL_39;
  }
  if ( SHRegOpenUSKeyW(pwzPath, 0x20019u, 0, &phNewUSKey, 1) )
  {
LABEL_37:
    v27 = v50;
    goto LABEL_38;
  }
LABEL_39:
  v16 = 0;
  hUSKey = phNewUSKey;
  v28 = 0;
  LODWORD(phNewUSKey) = 260;
  while ( hUSKey )
  {
    if ( !(_DWORD)v51 || v50 || (v30 = SHRegEnumUSKeyW(hUSKey, v28, pwzName, (LPDWORD)&phNewUSKey, SHREGENUM_HKLM)) != 0 )
    {
      LODWORD(phNewUSKey) = v8;
      if ( v50 )
        v29 = SHREGENUM_HKLM;
      else
        v29 = HIDWORD(v51) != 0;
      v30 = SHRegEnumUSKeyW(hUSKey, v28, pwzName, (LPDWORD)&phNewUSKey, v29);
    }
    if ( v30 == 259 )
      goto LABEL_74;
    if ( v30 )
      break;
    LODWORD(phNewUSKey) = 240;
    v31 = CoTaskMemAlloc(0x50u);
    v32 = (CRegZone *)v31;
    if ( !v31 )
      goto LABEL_73;
    v31[4] = 0;
    v31[7] = 0;
    v31[8] = 0;
    *(_DWORD *)v31 = -1;
    *((_DWORD *)v31 + 1) = 2;
    v31[1] = 0;
    v31[2] = 0;
    v31[3] = 0;
    *(_QWORD *)((char *)v31 + 44) = 1;
    *((_DWORD *)v31 + 10) = 1;
    *((_DWORD *)v31 + 13) = 0;
    v31[9] = 0;
    v33 = v52;
    if ( !a2 )
      *((_QWORD *)v32 + 9) = v52;
    if ( (unsigned int)CRegZone::Init((__int64)v32, pwzName, *(_DWORD *)(v33 + 28), a2) )
    {
      ++*a4;
      v34 = CoTaskMemAlloc(0x18u);
      v35 = v34;
      if ( !v34 )
      {
LABEL_73:
        *a4 = 0;
        v16 = -2147024882;
        goto LABEL_74;
      }
      *v34 = 0;
      v34[2] = 0;
      v34[1] = v32;
      v36 = *(_DWORD *)v32;
      *((_DWORD *)v34 + 4) = *(_DWORD *)v32;
      v37 = v53;
      v38 = (__int64 **)*v53;
      if ( *v53 )
      {
        if ( *((_DWORD *)v38 + 4) > v36 )
        {
          *v35 = v38;
          *v37 = v35;
        }
        else
        {
          for ( i = *v38; i; i = (__int64 *)*i )
          {
            if ( *((_DWORD *)i + 4) > v36 )
              break;
            v38 = (__int64 **)i;
          }
          if ( *((_DWORD *)v38 + 4) == v36 )
          {
            operator delete(v35);
            CRegZone::`scalar deleting destructor'(v32, v46);
            --*a4;
          }
          else
          {
            *v35 = *v38;
            *v38 = v35;
          }
        }
      }
      else
      {
        *v53 = v35;
        *v35 = 0;
      }
    }
    v8 = (int)phNewUSKey;
    ++v28;
  }
  v16 = -2147418113;
LABEL_74:
  if ( !v18 || !v16 )
    v26 = 0;
  v48 = &CRegKey::`vftable';
  if ( hUSKey )
    SHRegCloseUSKey(hUSKey);
  return v26;
}

```

## disassembly

```asm
0x18003abdc  push    rbp
0x18003abde  push    rbx
0x18003abdf  push    rsi
0x18003abe0  push    rdi
0x18003abe1  push    r12
0x18003abe3  push    r13
0x18003abe5  push    r14
0x18003abe7  push    r15
0x18003abe9  lea     rbp, [rsp-3A8h]
0x18003abf1  sub     rsp, 4A8h
0x18003abf8  mov     rax, cs:__security_cookie
0x18003abff  xor     rax, rsp
0x18003ac02  mov     [rbp+3E0h+var_50], rax
0x18003ac09  mov     eax, 103h
0x18003ac0e  mov     [rsp+4E0h+var_480], r8
0x18003ac13  xor     r13d, r13d
0x18003ac16  mov     [rsp+4E0h+var_488], rcx
0x18003ac1b  mov     r15, r9
0x18003ac1e  mov     r14, r8
0x18003ac21  mov     r12d, edx
0x18003ac24  mov     rsi, rcx
0x18003ac27  lea     ebx, [rax+1]
0x18003ac2a  mov     r9d, edx
0x18003ac2d  test    edx, edx
0x18003ac2f  jnz     short loc_18003AC67
0x18003ac31  mov     ecx, eax
0x18003ac33  lea     r8, aSoftwarePolici_4; "Software\\Policies\\Microsoft\\Windows"...
0x18003ac3a  lea     rax, [rsp+4E0h+pwzPath]
0x18003ac3f  mov     edx, ebx
0x18003ac41  test    rcx, rcx
0x18003ac44  jz      short loc_18003ACAD
0x18003ac46  movzx   r9d, word ptr [r8]
0x18003ac4a  test    r9w, r9w
0x18003ac4e  jz      short loc_18003ACAD
0x18003ac50  mov     [rax], r9w
0x18003ac54  add     r8, 2
0x18003ac58  add     rax, 2
0x18003ac5c  dec     rcx
0x18003ac5f  sub     rdx, 1
0x18003ac63  jnz     short loc_18003AC41
0x18003ac65  jmp     short loc_18003ACAD
0x18003ac67  sub     r9d, 1
0x18003ac6b  jz      loc_18003B1F4
0x18003ac71  cmp     r9d, 1
0x18003ac75  jnz     short loc_18003ACC4
0x18003ac77  mov     rcx, rax
0x18003ac7a  lea     r8, aSoftwarePolici_7; "Software\\Policies\\Microsoft\\Windows"...
0x18003ac81  lea     rax, [rsp+4E0h+pwzPath]
0x18003ac86  mov     rdx, rbx
0x18003ac89  test    rcx, rcx
0x18003ac8c  jz      short loc_18003ACAD
0x18003ac8e  movzx   r9d, word ptr [r8]
0x18003ac92  test    r9w, r9w
0x18003ac96  jz      short loc_18003ACAD
0x18003ac98  mov     [rax], r9w
0x18003ac9c  add     r8, 2
0x18003aca0  add     rax, 2
0x18003aca4  dec     rcx
0x18003aca7  sub     rdx, 1
0x18003acab  jnz     short loc_18003AC89
0x18003acad  test    rdx, rdx
0x18003acb0  lea     rcx, [rax-2]
0x18003acb4  cmovnz  rcx, rax
0x18003acb8  mov     [rcx], r13w
0x18003acbc  mov     [rbp+3E0h+var_26A], r13w
0x18003acc4  lea     rax, ??_7CRegKey@@6B@; const CRegKey::`vftable'
0x18003accb  mov     [rsp+4E0h+hUSKey], r13
0x18003acd0  mov     [rsp+4E0h+var_4A8], rax
0x18003acd5  lea     rcx, [rsp+4E0h+var_4A8]; this
0x18003acda  mov     eax, [rsi+1Ch]
0x18003acdd  mov     [rsp+4E0h+var_498], eax
0x18003ace1  mov     [rsp+4E0h+var_494], 1
0x18003acea  mov     [rsp+4E0h+phNewUSKey], r13
0x18003acef  call    ?Close@CRegKey@@UEAAJXZ; CRegKey::Close(void)
0x18003acf4  mov     edi, 80004005h
0x18003acf9  cmp     dword ptr [rsp+4E0h+var_494], r13d
0x18003acfe  jnz     loc_18003B00C
0x18003ad04  mov     eax, [rsp+4E0h+var_498]
0x18003ad08  lea     r9, [rsp+4E0h+phNewUSKey]; phNewUSKey
0x18003ad0d  mov     [rsp+4E0h+fIgnoreHKCU], eax; fIgnoreHKCU
0x18003ad11  xor     r8d, r8d; hRelativeUSKey
0x18003ad14  lea     rcx, [rsp+4E0h+pwzPath]; pwzPath
0x18003ad19  mov     edx, 20019h; samDesired
0x18003ad1e  mov     r13d, edi
0x18003ad21  call    cs:__imp_SHRegOpenUSKeyW
0x18003ad28  nop     dword ptr [rax+rax+00h]
0x18003ad2d  xor     r10d, r10d
0x18003ad30  test    eax, eax
0x18003ad32  jnz     short loc_18003AD5C
0x18003ad34  mov     rax, [rsp+4E0h+phNewUSKey]
0x18003ad39  lea     rdx, [rsp+4E0h+var_4A8]
0x18003ad3e  mov     r9, r14
0x18003ad41  mov     [rsp+4E0h+hUSKey], rax
0x18003ad46  mov     r8d, r12d
0x18003ad49  mov     qword ptr [rsp+4E0h+fIgnoreHKCU], r15
0x18003ad4e  mov     rcx, rsi
0x18003ad51  call    ?EnumerateAndLoadZones@CRegZoneContainer@@IEAAJAEAVCRegKey@@W4REGZONEUSE@@PEAPEAUCRegListElem@1@PEAK@Z; CRegZoneContainer::EnumerateAndLoadZones(CRegKey &,REGZONEUSE,CRegZoneContainer::CRegListElem * *,ulong *)
0x18003ad56  mov     r13d, eax
0x18003ad59  xor     r10d, r10d
0x18003ad5c  mov     dword ptr [rsp+4E0h+var_494], r10d
0x18003ad61  cmp     [rsi+1Ch], r10d
0x18003ad65  jz      loc_18003B08D
0x18003ad6b  mov     ecx, r12d
0x18003ad6e  test    r12d, r12d
0x18003ad71  jnz     short loc_18003ADAD
0x18003ad73  mov     ecx, 103h
0x18003ad78  lea     r8, aSoftwareMicros_69; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003ad7f  mov     rdx, rbx
0x18003ad82  lea     rax, [rsp+4E0h+pwzPath]
0x18003ad87  test    rcx, rcx
0x18003ad8a  jz      short loc_18003ADF3
0x18003ad8c  movzx   r9d, word ptr [r8]
0x18003ad90  test    r9w, r9w
0x18003ad94  jz      short loc_18003ADF3
0x18003ad96  mov     [rax], r9w
0x18003ad9a  add     r8, 2
0x18003ad9e  add     rax, 2
0x18003ada2  dec     rcx
0x18003ada5  sub     rdx, 1
0x18003ada9  jnz     short loc_18003AD87
0x18003adab  jmp     short loc_18003ADF3
0x18003adad  sub     ecx, 1
0x18003adb0  jz      loc_18003B237
0x18003adb6  cmp     ecx, 1
0x18003adb9  jnz     short loc_18003AE0A
0x18003adbb  mov     ecx, 103h
0x18003adc0  lea     r8, aSoftwareMicros_35; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003adc7  mov     rdx, rbx
0x18003adca  lea     rax, [rsp+4E0h+pwzPath]
0x18003adcf  test    rcx, rcx
0x18003add2  jz      short loc_18003ADF3
0x18003add4  movzx   r9d, word ptr [r8]
0x18003add8  test    r9w, r9w
0x18003addc  jz      short loc_18003ADF3
0x18003adde  mov     [rax], r9w
0x18003ade2  add     r8, 2
0x18003ade6  add     rax, 2
0x18003adea  dec     rcx
0x18003aded  sub     rdx, 1
0x18003adf1  jnz     short loc_18003ADCF
0x18003adf3  test    rdx, rdx
0x18003adf6  lea     rcx, [rax-2]
0x18003adfa  cmovnz  rcx, rax
0x18003adfe  mov     [rcx], r10w
0x18003ae02  mov     [rbp+3E0h+var_26A], r10w
0x18003ae0a  mov     rax, [rsp+4E0h+var_4A8]
0x18003ae0f  lea     rcx, [rsp+4E0h+var_4A8]
0x18003ae14  mov     [rsp+4E0h+phNewUSKey], r10
0x18003ae19  mov     rax, [rax+10h]
0x18003ae1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ae22  xor     r10d, r10d
0x18003ae25  mov     esi, 8000FFFFh
0x18003ae2a  cmp     dword ptr [rsp+4E0h+var_494], r10d
0x18003ae2f  jnz     loc_18003B04B
0x18003ae35  mov     eax, [rsp+4E0h+var_498]
0x18003ae39  lea     r9, [rsp+4E0h+phNewUSKey]; phNewUSKey
0x18003ae3e  mov     [rsp+4E0h+fIgnoreHKCU], eax; fIgnoreHKCU
0x18003ae42  xor     r8d, r8d; hRelativeUSKey
0x18003ae45  lea     rcx, [rsp+4E0h+pwzPath]; pwzPath
0x18003ae4a  mov     edx, 20019h; samDesired
0x18003ae4f  call    cs:__imp_SHRegOpenUSKeyW
0x18003ae56  nop     dword ptr [rax+rax+00h]
0x18003ae5b  xor     r10d, r10d
0x18003ae5e  test    eax, eax
0x18003ae60  jnz     loc_18003B121
0x18003ae66  mov     rax, [rsp+4E0h+phNewUSKey]
0x18003ae6b  mov     edi, r10d
0x18003ae6e  mov     [rsp+4E0h+hUSKey], rax
0x18003ae73  mov     r14d, r10d
0x18003ae76  mov     dword ptr [rsp+4E0h+phNewUSKey], ebx
0x18003ae7a  mov     rcx, [rsp+4E0h+hUSKey]; hUSKey
0x18003ae7f  test    rcx, rcx
0x18003ae82  jz      loc_18003B294
0x18003ae88  cmp     dword ptr [rsp+4E0h+var_494], r10d
0x18003ae8d  jnz     loc_18003B1B6
0x18003ae93  mov     dword ptr [rsp+4E0h+phNewUSKey], ebx
0x18003ae97  cmp     [rsp+4E0h+var_498], r10d
0x18003ae9c  jnz     loc_18003AFFA
0x18003aea2  cmp     dword ptr [rsp+4E0h+var_494+4], r10d
0x18003aea7  mov     eax, r10d
0x18003aeaa  setnz   al
0x18003aead  mov     rcx, [rsp+4E0h+hUSKey]; hUSKey
0x18003aeb2  lea     r9, [rsp+4E0h+phNewUSKey]; pcchName
0x18003aeb7  lea     r8, [rbp+3E0h+pwzName]; pwzName
0x18003aebe  mov     [rsp+4E0h+fIgnoreHKCU], eax; enumRegFlags
0x18003aec2  mov     edx, r14d; dwIndex
0x18003aec5  call    cs:__imp_SHRegEnumUSKeyW
0x18003aecc  nop     dword ptr [rax+rax+00h]
0x18003aed1  xor     r10d, r10d
0x18003aed4  cmp     eax, 103h
0x18003aed9  jz      loc_18003B121
0x18003aedf  test    eax, eax
0x18003aee1  jnz     loc_18003B294
0x18003aee7  lea     ecx, [rax+50h]; cb
0x18003aeea  mov     dword ptr [rsp+4E0h+phNewUSKey], 0F0h
0x18003aef2  call    cs:__imp_CoTaskMemAlloc
0x18003aef9  nop     dword ptr [rax+rax+00h]
0x18003aefe  xor     r10d, r10d
0x18003af01  mov     rbx, rax
0x18003af04  test    rax, rax
0x18003af07  jz      loc_18003B119
0x18003af0d  mov     [rax+20h], r10
0x18003af11  mov     [rax+38h], r10
0x18003af15  mov     [rax+40h], r10
0x18003af19  mov     dword ptr [rax], 0FFFFFFFFh
0x18003af1f  mov     dword ptr [rax+4], 2
0x18003af26  mov     [rax+8], r10
0x18003af2a  mov     [rax+10h], r10
0x18003af2e  mov     [rax+18h], r10
0x18003af32  mov     qword ptr [rax+2Ch], 1
0x18003af3a  mov     dword ptr [rax+28h], 1
0x18003af41  mov     [rax+34h], r10d
0x18003af45  mov     [rax+48h], r10
0x18003af49  mov     rax, [rsp+4E0h+var_488]
0x18003af4e  test    r12d, r12d
0x18003af51  jnz     short loc_18003AF57
0x18003af53  mov     [rbx+48h], rax
0x18003af57  mov     r8d, [rax+1Ch]
0x18003af5b  lea     rdx, [rbp+3E0h+pwzName]
0x18003af62  mov     r9d, r12d
0x18003af65  mov     rcx, rbx
0x18003af68  call    ?Init@CRegZone@@QEAAHPEBGHW4REGZONEUSE@@H@Z; CRegZone::Init(ushort const *,int,REGZONEUSE,int)
0x18003af6d  xor     r10d, r10d
0x18003af70  test    eax, eax
0x18003af72  jz      short loc_18003AFEE
0x18003af74  inc     dword ptr [r15]
0x18003af77  lea     ecx, [r10+18h]; cb
0x18003af7b  call    cs:__imp_CoTaskMemAlloc
0x18003af82  nop     dword ptr [rax+rax+00h]
0x18003af87  xor     r10d, r10d
0x18003af8a  mov     rcx, rax; void *
0x18003af8d  test    rax, rax
0x18003af90  jz      loc_18003B119
0x18003af96  mov     [rax], r10
0x18003af99  mov     [rax+10h], r10
0x18003af9d  mov     [rax+8], rbx
0x18003afa1  mov     r9d, [rbx]
0x18003afa4  mov     [rax+10h], r9d
0x18003afa8  mov     rax, [rsp+4E0h+var_480]
0x18003afad  mov     rdx, [rax]
0x18003afb0  test    rdx, rdx
0x18003afb3  jz      short loc_18003B004
0x18003afb5  cmp     [rdx+10h], r9d
0x18003afb9  ja      loc_18003B10E
0x18003afbf  mov     r8, [rdx]
0x18003afc2  test    r8, r8
0x18003afc5  jz      short loc_18003AFDB
0x18003afc7  cmp     [r8+10h], r9d
0x18003afcb  ja      short loc_18003AFDB
0x18003afcd  mov     rax, [r8]
0x18003afd0  mov     rdx, r8
0x18003afd3  mov     r8, rax
0x18003afd6  test    rax, rax
0x18003afd9  jnz     short loc_18003AFC7
0x18003afdb  cmp     [rdx+10h], r9d
0x18003afdf  jz      loc_18003B27C
0x18003afe5  mov     rax, [rdx]
0x18003afe8  mov     [rcx], rax
0x18003afeb  mov     [rdx], rcx
0x18003afee  mov     ebx, dword ptr [rsp+4E0h+phNewUSKey]
0x18003aff2  inc     r14d
0x18003aff5  jmp     loc_18003AE7A
0x18003affa  mov     eax, 10h
0x18003afff  jmp     loc_18003AEAD
0x18003b004  mov     [rax], rcx
0x18003b007  mov     [rcx], r10
0x18003b00a  jmp     short loc_18003AFEE
0x18003b00c  mov     eax, [rsp+4E0h+var_498]
0x18003b010  test    eax, eax
0x18003b012  jnz     loc_18003AD08
0x18003b018  lea     r9, [rsp+4E0h+phNewUSKey]; phNewUSKey
0x18003b01d  mov     [rsp+4E0h+fIgnoreHKCU], 1; fIgnoreHKCU
0x18003b025  xor     r8d, r8d; hRelativeUSKey
0x18003b028  lea     rcx, [rsp+4E0h+pwzPath]; pwzPath
0x18003b02d  mov     edx, 20019h; samDesired
0x18003b032  call    cs:__imp_SHRegOpenUSKeyW
0x18003b039  nop     dword ptr [rax+rax+00h]
0x18003b03e  test    eax, eax
0x18003b040  jnz     loc_18003AD04
0x18003b046  jmp     loc_18003AD34
0x18003b04b  mov     eax, [rsp+4E0h+var_498]
0x18003b04f  test    eax, eax
0x18003b051  jnz     loc_18003AE39
0x18003b057  lea     r9, [rsp+4E0h+phNewUSKey]; phNewUSKey
0x18003b05c  mov     [rsp+4E0h+fIgnoreHKCU], 1; fIgnoreHKCU
0x18003b064  xor     r8d, r8d; hRelativeUSKey
0x18003b067  lea     rcx, [rsp+4E0h+pwzPath]; pwzPath
0x18003b06c  mov     edx, 20019h; samDesired
0x18003b071  call    cs:__imp_SHRegOpenUSKeyW
0x18003b078  nop     dword ptr [rax+rax+00h]
0x18003b07d  xor     r10d, r10d
0x18003b080  test    eax, eax
0x18003b082  jnz     loc_18003AE35
0x18003b088  jmp     loc_18003AE66
0x18003b08d  mov     rcx, [rsp+4E0h+var_4A8]
0x18003b092  mov     [rsp+4E0h+phNewUSKey], r10
0x18003b097  mov     rax, [rcx+10h]
0x18003b09b  lea     rcx, [rsp+4E0h+var_4A8]
0x18003b0a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b0a5  cmp     dword ptr [rsp+4E0h+var_494], 0
  ... truncated ...
```
