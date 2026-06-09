# CRegZoneContainer::EnumerateAndLoadZones(REGZONEUSE,CRegZoneContainer::CRegListElem * *,ulong *)

- ea: `0x1800330bc`
- end: `0x180033738`
- name: `?EnumerateAndLoadZones@CRegZoneContainer@@QEAAJW4REGZONEUSE@@PEAPEAUCRegListElem@1@PEAK@Z`
- size: `1660`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180011830`
- `0x180032c64`

## callees

- `0x180030880`
- `0x1800330bc`
- `0x180033740`
- `0x1800342d0`
- `0x18003434c`
- `0x1800345fc`
- `0x18011baa0`
- `0x18011c010`

## import_xrefs

- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegEnumUSKeyW` at `0x180033399`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegEnumUSKeyW` at `0x18003367b`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegEnumUSKeyW` at `0x180033399`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegEnumUSKeyW` at `0x18003367b`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180033201`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180033329`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x1800334f4`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x18003352d`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180033580`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180033646`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180033201`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180033329`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x1800334f4`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x18003352d`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180033580`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180033646`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x1800335ef`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x1800335ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800333c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033443`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800333c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033443`

## string_xrefs

- `0x180033694`: `Software\Policies\Microsoft\Windows\CurrentVersion\Internet Settings\TemplatePolicies\`
- `0x1800336d9`: `Software\Microsoft\Windows\CurrentVersion\Internet Settings\TemplatePolicies\`

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
0x1800330bc  push    rbp
0x1800330be  push    rbx
0x1800330bf  push    rsi
0x1800330c0  push    rdi
0x1800330c1  push    r12
0x1800330c3  push    r13
0x1800330c5  push    r14
0x1800330c7  push    r15
0x1800330c9  lea     rbp, [rsp-3A8h]
0x1800330d1  sub     rsp, 4A8h
0x1800330d8  mov     rax, cs:__security_cookie
0x1800330df  xor     rax, rsp
0x1800330e2  mov     [rbp+3E0h+var_50], rax
0x1800330e9  mov     eax, 103h
0x1800330ee  mov     [rsp+4E0h+var_480], r8
0x1800330f3  xor     r13d, r13d
0x1800330f6  mov     [rsp+4E0h+var_488], rcx
0x1800330fb  mov     r15, r9
0x1800330fe  mov     r14, r8
0x180033101  mov     r12d, edx
0x180033104  mov     rsi, rcx
0x180033107  lea     ebx, [rax+1]
0x18003310a  mov     r9d, edx
0x18003310d  test    edx, edx
0x18003310f  jnz     short loc_180033147
0x180033111  mov     ecx, eax
0x180033113  lea     r8, aSoftwarePolici_4; "Software\\Policies\\Microsoft\\Windows"...
0x18003311a  lea     rax, [rsp+4E0h+pwzPath]
0x18003311f  mov     edx, ebx
0x180033121  test    rcx, rcx
0x180033124  jz      short loc_18003318D
0x180033126  movzx   r9d, word ptr [r8]
0x18003312a  test    r9w, r9w
0x18003312e  jz      short loc_18003318D
0x180033130  mov     [rax], r9w
0x180033134  add     r8, 2
0x180033138  add     rax, 2
0x18003313c  dec     rcx
0x18003313f  sub     rdx, 1
0x180033143  jnz     short loc_180033121
0x180033145  jmp     short loc_18003318D
0x180033147  sub     r9d, 1
0x18003314b  jz      loc_180033691
0x180033151  cmp     r9d, 1
0x180033155  jnz     short loc_1800331A4
0x180033157  mov     rcx, rax
0x18003315a  lea     r8, aSoftwarePolici_7; "Software\\Policies\\Microsoft\\Windows"...
0x180033161  lea     rax, [rsp+4E0h+pwzPath]
0x180033166  mov     rdx, rbx
0x180033169  test    rcx, rcx
0x18003316c  jz      short loc_18003318D
0x18003316e  movzx   r9d, word ptr [r8]
0x180033172  test    r9w, r9w
0x180033176  jz      short loc_18003318D
0x180033178  mov     [rax], r9w
0x18003317c  add     r8, 2
0x180033180  add     rax, 2
0x180033184  dec     rcx
0x180033187  sub     rdx, 1
0x18003318b  jnz     short loc_180033169
0x18003318d  test    rdx, rdx
0x180033190  lea     rcx, [rax-2]
0x180033194  cmovnz  rcx, rax
0x180033198  mov     [rcx], r13w
0x18003319c  mov     [rbp+3E0h+var_26A], r13w
0x1800331a4  lea     rax, ??_7CRegKey@@6B@; const CRegKey::`vftable'
0x1800331ab  mov     [rsp+4E0h+hUSKey], r13
0x1800331b0  mov     [rsp+4E0h+var_4A8], rax
0x1800331b5  lea     rcx, [rsp+4E0h+var_4A8]; this
0x1800331ba  mov     eax, [rsi+1Ch]
0x1800331bd  mov     [rsp+4E0h+var_498], eax
0x1800331c1  mov     [rsp+4E0h+var_494], 1
0x1800331ca  mov     [rsp+4E0h+phNewUSKey], r13
0x1800331cf  call    ?Close@CRegKey@@UEAAJXZ; CRegKey::Close(void)
0x1800331d4  mov     edi, 80004005h
0x1800331d9  cmp     dword ptr [rsp+4E0h+var_494], r13d
0x1800331de  jnz     loc_1800334CE
0x1800331e4  mov     eax, [rsp+4E0h+var_498]
0x1800331e8  lea     r9, [rsp+4E0h+phNewUSKey]; phNewUSKey
0x1800331ed  mov     [rsp+4E0h+fIgnoreHKCU], eax; fIgnoreHKCU
0x1800331f1  xor     r8d, r8d; hRelativeUSKey
0x1800331f4  lea     rcx, [rsp+4E0h+pwzPath]; pwzPath
0x1800331f9  mov     edx, 20019h; samDesired
0x1800331fe  mov     r13d, edi
0x180033201  call    cs:__imp_SHRegOpenUSKeyW
0x180033207  xor     r10d, r10d
0x18003320a  test    eax, eax
0x18003320c  jnz     short loc_180033236
0x18003320e  mov     rax, [rsp+4E0h+phNewUSKey]
0x180033213  lea     rdx, [rsp+4E0h+var_4A8]
0x180033218  mov     r9, r14
0x18003321b  mov     [rsp+4E0h+hUSKey], rax
0x180033220  mov     r8d, r12d
0x180033223  mov     qword ptr [rsp+4E0h+fIgnoreHKCU], r15
0x180033228  mov     rcx, rsi
0x18003322b  call    ?EnumerateAndLoadZones@CRegZoneContainer@@IEAAJAEAVCRegKey@@W4REGZONEUSE@@PEAPEAUCRegListElem@1@PEAK@Z; CRegZoneContainer::EnumerateAndLoadZones(CRegKey &,REGZONEUSE,CRegZoneContainer::CRegListElem * *,ulong *)
0x180033230  mov     r13d, eax
0x180033233  xor     r10d, r10d
0x180033236  mov     dword ptr [rsp+4E0h+var_494], r10d
0x18003323b  cmp     [rsi+1Ch], r10d
0x18003323f  jz      loc_180033543
0x180033245  mov     ecx, r12d
0x180033248  test    r12d, r12d
0x18003324b  jnz     short loc_180033287
0x18003324d  mov     ecx, 103h
0x180033252  lea     r8, aSoftwareMicros_69; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180033259  mov     rdx, rbx
0x18003325c  lea     rax, [rsp+4E0h+pwzPath]
0x180033261  test    rcx, rcx
0x180033264  jz      short loc_1800332CD
0x180033266  movzx   r9d, word ptr [r8]
0x18003326a  test    r9w, r9w
0x18003326e  jz      short loc_1800332CD
0x180033270  mov     [rax], r9w
0x180033274  add     r8, 2
0x180033278  add     rax, 2
0x18003327c  dec     rcx
0x18003327f  sub     rdx, 1
0x180033283  jnz     short loc_180033261
0x180033285  jmp     short loc_1800332CD
0x180033287  sub     ecx, 1
0x18003328a  jz      loc_1800336D4
0x180033290  cmp     ecx, 1
0x180033293  jnz     short loc_1800332E4
0x180033295  mov     ecx, 103h
0x18003329a  lea     r8, aSoftwareMicros_35; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800332a1  mov     rdx, rbx
0x1800332a4  lea     rax, [rsp+4E0h+pwzPath]
0x1800332a9  test    rcx, rcx
0x1800332ac  jz      short loc_1800332CD
0x1800332ae  movzx   r9d, word ptr [r8]
0x1800332b2  test    r9w, r9w
0x1800332b6  jz      short loc_1800332CD
0x1800332b8  mov     [rax], r9w
0x1800332bc  add     r8, 2
0x1800332c0  add     rax, 2
0x1800332c4  dec     rcx
0x1800332c7  sub     rdx, 1
0x1800332cb  jnz     short loc_1800332A9
0x1800332cd  test    rdx, rdx
0x1800332d0  lea     rcx, [rax-2]
0x1800332d4  cmovnz  rcx, rax
0x1800332d8  mov     [rcx], r10w
0x1800332dc  mov     [rbp+3E0h+var_26A], r10w
0x1800332e4  mov     rax, [rsp+4E0h+var_4A8]
0x1800332e9  lea     rcx, [rsp+4E0h+var_4A8]
0x1800332ee  mov     [rsp+4E0h+phNewUSKey], r10
0x1800332f3  mov     rax, [rax+10h]
0x1800332f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800332fc  xor     r10d, r10d
0x1800332ff  mov     esi, 8000FFFFh
0x180033304  cmp     dword ptr [rsp+4E0h+var_494], r10d
0x180033309  jnz     loc_180033507
0x18003330f  mov     eax, [rsp+4E0h+var_498]
0x180033313  lea     r9, [rsp+4E0h+phNewUSKey]; phNewUSKey
0x180033318  mov     [rsp+4E0h+fIgnoreHKCU], eax; fIgnoreHKCU
0x18003331c  xor     r8d, r8d; hRelativeUSKey
0x18003331f  lea     rcx, [rsp+4E0h+pwzPath]; pwzPath
0x180033324  mov     edx, 20019h; samDesired
0x180033329  call    cs:__imp_SHRegOpenUSKeyW
0x18003332f  xor     r10d, r10d
0x180033332  test    eax, eax
0x180033334  jnz     loc_1800335D1
0x18003333a  mov     rax, [rsp+4E0h+phNewUSKey]
0x18003333f  mov     edi, r10d
0x180033342  mov     [rsp+4E0h+hUSKey], rax
0x180033347  mov     r14d, r10d
0x18003334a  mov     dword ptr [rsp+4E0h+phNewUSKey], ebx
0x18003334e  mov     rcx, [rsp+4E0h+hUSKey]; hUSKey
0x180033353  test    rcx, rcx
0x180033356  jz      loc_180033731
0x18003335c  cmp     dword ptr [rsp+4E0h+var_494], r10d
0x180033361  jnz     loc_180033659
0x180033367  mov     dword ptr [rsp+4E0h+phNewUSKey], ebx
0x18003336b  cmp     [rsp+4E0h+var_498], r10d
0x180033370  jnz     loc_1800334BC
0x180033376  cmp     dword ptr [rsp+4E0h+var_494+4], r10d
0x18003337b  mov     eax, r10d
0x18003337e  setnz   al
0x180033381  mov     rcx, [rsp+4E0h+hUSKey]; hUSKey
0x180033386  lea     r9, [rsp+4E0h+phNewUSKey]; pcchName
0x18003338b  lea     r8, [rbp+3E0h+pwzName]; pwzName
0x180033392  mov     [rsp+4E0h+fIgnoreHKCU], eax; enumRegFlags
0x180033396  mov     edx, r14d; dwIndex
0x180033399  call    cs:__imp_SHRegEnumUSKeyW
0x18003339f  xor     r10d, r10d
0x1800333a2  cmp     eax, 103h
0x1800333a7  jz      loc_1800335D1
0x1800333ad  test    eax, eax
0x1800333af  jnz     loc_180033731
0x1800333b5  lea     ecx, [rax+50h]; cb
0x1800333b8  mov     dword ptr [rsp+4E0h+phNewUSKey], 0F0h
0x1800333c0  call    cs:__imp_CoTaskMemAlloc
0x1800333c6  xor     r10d, r10d
0x1800333c9  mov     rbx, rax
0x1800333cc  test    rax, rax
0x1800333cf  jz      loc_1800335C9
0x1800333d5  mov     [rax+20h], r10
0x1800333d9  mov     [rax+38h], r10
0x1800333dd  mov     [rax+40h], r10
0x1800333e1  mov     dword ptr [rax], 0FFFFFFFFh
0x1800333e7  mov     dword ptr [rax+4], 2
0x1800333ee  mov     [rax+8], r10
0x1800333f2  mov     [rax+10h], r10
0x1800333f6  mov     [rax+18h], r10
0x1800333fa  mov     qword ptr [rax+2Ch], 1
0x180033402  mov     dword ptr [rax+28h], 1
0x180033409  mov     [rax+34h], r10d
0x18003340d  mov     [rax+48h], r10
0x180033411  mov     rax, [rsp+4E0h+var_488]
0x180033416  test    r12d, r12d
0x180033419  jnz     short loc_18003341F
0x18003341b  mov     [rbx+48h], rax
0x18003341f  mov     r8d, [rax+1Ch]
0x180033423  lea     rdx, [rbp+3E0h+pwzName]
0x18003342a  mov     r9d, r12d
0x18003342d  mov     rcx, rbx
0x180033430  call    ?Init@CRegZone@@QEAAHPEBGHW4REGZONEUSE@@H@Z; CRegZone::Init(ushort const *,int,REGZONEUSE,int)
0x180033435  xor     r10d, r10d
0x180033438  test    eax, eax
0x18003343a  jz      short loc_1800334B0
0x18003343c  inc     dword ptr [r15]
0x18003343f  lea     ecx, [r10+18h]; cb
0x180033443  call    cs:__imp_CoTaskMemAlloc
0x180033449  xor     r10d, r10d
0x18003344c  mov     rcx, rax; void *
0x18003344f  test    rax, rax
0x180033452  jz      loc_1800335C9
0x180033458  mov     [rax], r10
0x18003345b  mov     [rax+10h], r10
0x18003345f  mov     [rax+8], rbx
0x180033463  mov     r9d, [rbx]
0x180033466  mov     [rax+10h], r9d
0x18003346a  mov     rax, [rsp+4E0h+var_480]
0x18003346f  mov     rdx, [rax]
0x180033472  test    rdx, rdx
0x180033475  jz      short loc_1800334C6
0x180033477  cmp     [rdx+10h], r9d
0x18003347b  ja      loc_1800335BE
0x180033481  mov     r8, [rdx]
0x180033484  test    r8, r8
0x180033487  jz      short loc_18003349D
0x180033489  cmp     [r8+10h], r9d
0x18003348d  ja      short loc_18003349D
0x18003348f  mov     rax, [r8]
0x180033492  mov     rdx, r8
0x180033495  mov     r8, rax
0x180033498  test    rax, rax
0x18003349b  jnz     short loc_180033489
0x18003349d  cmp     [rdx+10h], r9d
0x1800334a1  jz      loc_180033719
0x1800334a7  mov     rax, [rdx]
0x1800334aa  mov     [rcx], rax
0x1800334ad  mov     [rdx], rcx
0x1800334b0  mov     ebx, dword ptr [rsp+4E0h+phNewUSKey]
0x1800334b4  inc     r14d
0x1800334b7  jmp     loc_18003334E
0x1800334bc  mov     eax, 10h
0x1800334c1  jmp     loc_180033381
0x1800334c6  mov     [rax], rcx
0x1800334c9  mov     [rcx], r10
0x1800334cc  jmp     short loc_1800334B0
0x1800334ce  mov     eax, [rsp+4E0h+var_498]
0x1800334d2  test    eax, eax
0x1800334d4  jnz     loc_1800331E8
0x1800334da  lea     r9, [rsp+4E0h+phNewUSKey]; phNewUSKey
0x1800334df  mov     [rsp+4E0h+fIgnoreHKCU], 1; fIgnoreHKCU
0x1800334e7  xor     r8d, r8d; hRelativeUSKey
0x1800334ea  lea     rcx, [rsp+4E0h+pwzPath]; pwzPath
0x1800334ef  mov     edx, 20019h; samDesired
0x1800334f4  call    cs:__imp_SHRegOpenUSKeyW
0x1800334fa  test    eax, eax
0x1800334fc  jnz     loc_1800331E4
0x180033502  jmp     loc_18003320E
0x180033507  mov     eax, [rsp+4E0h+var_498]
0x18003350b  test    eax, eax
0x18003350d  jnz     loc_180033313
0x180033513  lea     r9, [rsp+4E0h+phNewUSKey]; phNewUSKey
0x180033518  mov     [rsp+4E0h+fIgnoreHKCU], 1; fIgnoreHKCU
0x180033520  xor     r8d, r8d; hRelativeUSKey
0x180033523  lea     rcx, [rsp+4E0h+pwzPath]; pwzPath
0x180033528  mov     edx, 20019h; samDesired
0x18003352d  call    cs:__imp_SHRegOpenUSKeyW
0x180033533  xor     r10d, r10d
0x180033536  test    eax, eax
0x180033538  jnz     loc_18003330F
0x18003353e  jmp     loc_18003333A
0x180033543  mov     rcx, [rsp+4E0h+var_4A8]
0x180033548  mov     [rsp+4E0h+phNewUSKey], r10
0x18003354d  mov     rax, [rcx+10h]
0x180033551  lea     rcx, [rsp+4E0h+var_4A8]
0x180033556  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003355b  cmp     dword ptr [rsp+4E0h+var_494], 0
0x180033560  jnz     loc_180033620
0x180033566  mov     eax, [rsp+4E0h+var_498]
0x18003356a  lea     r9, [rsp+4E0h+phNewUSKey]; phNewUSKey
0x18003356f  mov     [rsp+4E0h+fIgnoreHKCU], eax; fIgnoreHKCU
0x180033573  xor     r8d, r8d; hRelativeUSKey
0x180033576  lea     rcx, [rsp+4E0h+pwzPath]; pwzPath
0x18003357b  mov     edx, 20019h; samDesired
  ... truncated ...
```
