# CUwfStaticConfiguration::RestoreOrDeleteRegValueAndCommit(ushort const *,HKEY__ *,ushort const *,ushort const *,ulong)

- ea: `0x1800092a8`
- end: `0x180009682`
- name: `?RestoreOrDeleteRegValueAndCommit@CUwfStaticConfiguration@@AEAAJPEBGPEAUHKEY__@@00K@Z`
- size: `986`
- prototype: `__int64 __fastcall(CUwfStaticConfiguration *this, const unsigned __int16 *, HKEY, const unsigned __int16 *, unsigned __int16 *, char)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006144`

## callees

- `0x1800053ac`
- `0x1800092a8`
- `0x18000d5f0`
- `0x18000d9f0`
- `0x18000dd80`
- `0x18000e480`
- `0x180013100`
- `0x180013310`
- `0x180013460`
- `0x1800139f0`
- `0x18001afe2`
- `0x18001b020`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800094c4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009534`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800094c4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009534`

## pseudocode

```c
__int64 __fastcall CUwfStaticConfiguration::RestoreOrDeleteRegValueAndCommit(
        CUwfStaticConfiguration *this,
        const unsigned __int16 *a2,
        HKEY a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        char a6)
{
  __int64 v8; // r15
  __int64 v9; // rsi
  WCHAR *v10; // r8
  int v11; // edi
  unsigned __int64 v12; // rdx
  __int64 v13; // rax
  unsigned __int16 *v14; // rcx
  WCHAR *v15; // rcx
  signed int v16; // ebx
  unsigned __int16 *v17; // rax
  WCHAR *v18; // rdx
  WCHAR *v19; // rcx
  bool v20; // di
  LSTATUS v21; // eax
  bool v22; // sf
  signed int v23; // eax
  LSTATUS v24; // eax
  bool v25; // sf
  signed int v26; // eax
  DWORD Type; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  BYTE Data[4]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v32[2]; // [rsp+58h] [rbp-A8h] BYREF
  char v33; // [rsp+68h] [rbp-98h]
  int v34; // [rsp+70h] [rbp-90h]
  WCHAR v35[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR ValueName[264]; // [rsp+290h] [rbp+190h] BYREF

  v32[1] = -1;
  hKey = 0;
  v33 = 0;
  *(_DWORD *)Data = 0;
  v32[0] = &CUwfRegDevice::`vftable';
  v34 = -2147019873;
  memset_0(v35, 0, 0x208u);
  memset_0(ValueName, 0, 0x208u);
  v8 = 2147483646;
  v34 = CDevice::Initialize((CDevice *)v32, L"\\\\.\\UwfregControl");
  v9 = 260;
  v10 = v35;
  v11 = v34;
  v12 = 260;
  v13 = 2147483646;
  v14 = a5;
  do
  {
    if ( !v13 )
      break;
    if ( !*v14 )
      break;
    *v10++ = *v14++;
    --v13;
    --v12;
  }
  while ( v12 );
  v15 = v10 - 1;
  v16 = v12 == 0 ? 0x8007007A : 0;
  if ( v12 )
    v15 = v10;
  *v15 = 0;
  if ( !v12 )
    goto LABEL_53;
  v16 = StringCchCatW(v35, v12, L".uwf");
  if ( v16 < 0 )
    goto LABEL_53;
  v17 = a5;
  v18 = ValueName;
  do
  {
    if ( !v8 )
      break;
    if ( !*v17 )
      break;
    *v18++ = *v17++;
    --v8;
    --v9;
  }
  while ( v9 );
  v19 = v18 - 1;
  v16 = v9 == 0 ? 0x8007007A : 0;
  if ( v9 )
    v19 = v18;
  *v19 = 0;
  if ( !v9 )
    goto LABEL_53;
  v16 = StringCchCatW(ValueName, (unsigned __int64)v18, L".uwf_del");
  if ( v16 < 0 )
    goto LABEL_53;
  v16 = CUwfRegKey::Create(&hKey, HKEY_LOCAL_MACHINE, a4, 0, 0, 0xF003Fu, 0, 0);
  if ( v16 < 0 )
    goto LABEL_53;
  v20 = v11 >= 0;
  if ( (a6 & 2) == 0 )
    goto LABEL_23;
  Type = 0;
  cbData = 4;
  v21 = RegQueryValueExW(hKey, ValueName, 0, &Type, Data, &cbData);
  v22 = v21 < 0;
  if ( v21 )
  {
    if ( v21 > 0 )
      v22 = 1;
    if ( !v22 )
      goto LABEL_23;
  }
  else if ( Type == 4 && cbData == 4 )
  {
    goto LABEL_23;
  }
  cbData = 0;
  Type = 4;
  v24 = RegQueryValueExW(hKey, v35, 0, &cbData, Data, &Type);
  v25 = v24 < 0;
  if ( !v24 )
  {
    if ( cbData == 4 && Type == 4 )
      goto LABEL_34;
LABEL_23:
    if ( v20 )
      v23 = CUwfRegDevice::CommitRegistryValueDeletion((CUwfRegDevice *)v32, a2, a5);
    else
      v23 = CUwfRegKey::DeleteValue(&hKey, a5);
    v16 = v23;
    if ( ((v23 + 0x80000000) & 0x80000000) == 0 && v23 != -2147024894 )
      goto LABEL_53;
    v16 = 0;
    goto LABEL_42;
  }
  if ( v24 > 0 )
    v25 = 1;
  if ( v25 )
    goto LABEL_23;
LABEL_34:
  v16 = CUwfRegKey::SetDWORDValue((CUwfRegKey *)&hKey, a5, *(unsigned int *)Data);
  if ( v16 < 0 )
    goto LABEL_53;
  if ( v20 )
  {
    v16 = CUwfRegDevice::CommitRegistryValue((CUwfRegDevice *)v32, a2, a5);
    if ( v16 < 0 )
      goto LABEL_53;
  }
LABEL_42:
  if ( (a6 & 8) == 0 )
    goto LABEL_53;
  if ( v20 )
  {
    v16 = CUwfRegDevice::CommitRegistryValueDeletion((CUwfRegDevice *)v32, a2, v35);
    if ( ((v16 + 0x80000000) & 0x80000000) == 0 && v16 != -2147024894 )
      goto LABEL_53;
    v26 = CUwfRegDevice::CommitRegistryValueDeletion((CUwfRegDevice *)v32, a2, ValueName);
  }
  else
  {
    v16 = CUwfRegKey::DeleteValue(&hKey, v35);
    if ( ((v16 + 0x80000000) & 0x80000000) == 0 && v16 != -2147024894 )
      goto LABEL_53;
    v26 = CUwfRegKey::DeleteValue(&hKey, ValueName);
  }
  v16 = v26;
  if ( ((v26 + 0x80000000) & 0x80000000) != 0 || v26 == -2147024894 )
    v16 = 0;
LABEL_53:
  v32[0] = &CDevice::`vftable';
  CDevice::Close((CDevice *)v32);
  CUwfRegKey::Close(&hKey);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x1800092a8  mov     [rsp-8+arg_0], rbx
0x1800092ad  push    rbp
0x1800092ae  push    rsi
0x1800092af  push    rdi
0x1800092b0  push    r12
0x1800092b2  push    r13
0x1800092b4  push    r14
0x1800092b6  push    r15
0x1800092b8  lea     rbp, [rsp-3B0h]
0x1800092c0  sub     rsp, 4B0h
0x1800092c7  mov     rax, cs:__security_cookie
0x1800092ce  xor     rax, rsp
0x1800092d1  mov     [rbp+3E0h+var_40], rax
0x1800092d8  mov     r14, [rbp+3E0h+arg_20]
0x1800092df  lea     rax, ??_7CUwfRegDevice@@6B@; const CUwfRegDevice::`vftable'
0x1800092e6  xor     r8d, r8d
0x1800092e9  mov     [rsp+4E0h+var_480], 0FFFFFFFFFFFFFFFFh
0x1800092f2  mov     [rsp+4E0h+hKey], r8
0x1800092f7  lea     rcx, [rbp+3E0h+var_460]; void *
0x1800092fb  mov     [rsp+4E0h+var_478], r8b
0x180009300  mov     r12, rdx
0x180009303  mov     dword ptr [rsp+4E0h+Data], r8d
0x180009308  mov     ebx, 208h
0x18000930d  mov     r8d, ebx; Size
0x180009310  mov     [rsp+4E0h+var_488], rax
0x180009315  xor     edx, edx; Val
0x180009317  mov     [rsp+4E0h+var_470], 8007139Fh
0x18000931f  mov     r13, r9
0x180009322  call    memset_0
0x180009327  mov     r8d, ebx; Size
0x18000932a  lea     rcx, [rbp+3E0h+ValueName]; void *
0x180009331  xor     edx, edx; Val
0x180009333  call    memset_0
0x180009338  lea     rdx, FileName; "\\\\.\\UwfregControl"
0x18000933f  lea     rcx, [rsp+4E0h+var_488]; this
0x180009344  call    ?Initialize@CDevice@@QEAAJPEBG@Z; CDevice::Initialize(ushort const *)
0x180009349  mov     r15d, 7FFFFFFEh
0x18000934f  mov     [rsp+4E0h+var_470], eax
0x180009353  mov     esi, 104h
0x180009358  lea     r8, [rbp+3E0h+var_460]
0x18000935c  mov     edi, eax
0x18000935e  mov     edx, esi
0x180009360  mov     eax, r15d
0x180009363  mov     rcx, r14
0x180009366  xor     r10d, r10d
0x180009369  test    rax, rax
0x18000936c  jz      short loc_18000938D
0x18000936e  movzx   r9d, word ptr [rcx]
0x180009372  test    r9w, r9w
0x180009376  jz      short loc_18000938D
0x180009378  mov     [r8], r9w
0x18000937c  add     rcx, 2
0x180009380  add     r8, 2
0x180009384  dec     rax
0x180009387  sub     rdx, 1; unsigned __int64
0x18000938b  jnz     short loc_180009369
0x18000938d  mov     rax, rdx
0x180009390  lea     rcx, [r8-2]
0x180009394  neg     rax
0x180009397  sbb     ebx, ebx
0x180009399  not     ebx
0x18000939b  and     ebx, 8007007Ah
0x1800093a1  test    rdx, rdx
0x1800093a4  cmovnz  rcx, r8
0x1800093a8  mov     [rcx], r10w
0x1800093ac  jz      loc_180009636
0x1800093b2  lea     r8, aUwf; ".uwf"
0x1800093b9  lea     rcx, [rbp+3E0h+var_460]; unsigned __int16 *
0x1800093bd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800093c2  mov     ebx, eax
0x1800093c4  test    eax, eax
0x1800093c6  js      loc_180009636
0x1800093cc  mov     rax, r14
0x1800093cf  lea     rdx, [rbp+3E0h+ValueName]
0x1800093d6  test    r15, r15
0x1800093d9  jz      short loc_1800093F7
0x1800093db  movzx   ecx, word ptr [rax]
0x1800093de  test    cx, cx
0x1800093e1  jz      short loc_1800093F7
0x1800093e3  mov     [rdx], cx
0x1800093e6  add     rax, 2
0x1800093ea  add     rdx, 2; unsigned __int64
0x1800093ee  dec     r15
0x1800093f1  sub     rsi, 1
0x1800093f5  jnz     short loc_1800093D6
0x1800093f7  mov     rax, rsi
0x1800093fa  lea     rcx, [rdx-2]
0x1800093fe  neg     rax
0x180009401  sbb     ebx, ebx
0x180009403  xor     r15d, r15d
0x180009406  not     ebx
0x180009408  and     ebx, 8007007Ah
0x18000940e  test    rsi, rsi
0x180009411  cmovnz  rcx, rdx
0x180009415  mov     [rcx], r15w
0x180009419  jz      loc_180009636
0x18000941f  lea     r8, aUwfDel; ".uwf_del"
0x180009426  lea     rcx, [rbp+3E0h+ValueName]; unsigned __int16 *
0x18000942d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009432  mov     ebx, eax
0x180009434  test    eax, eax
0x180009436  js      loc_180009636
0x18000943c  mov     [rsp+4E0h+var_4A8], r15; LPDWORD
0x180009441  lea     rcx, [rsp+4E0h+hKey]; phkResult
0x180009446  mov     [rsp+4E0h+var_4B0], r15; LPSECURITY_ATTRIBUTES
0x18000944b  xor     r9d, r9d; lpClass
0x18000944e  mov     dword ptr [rsp+4E0h+lpcbData], 0F003Fh; REGSAM
0x180009456  mov     r8, r13; lpSubKey
0x180009459  mov     rdx, 0FFFFFFFF80000002h; hKey
0x180009460  mov     dword ptr [rsp+4E0h+lpData], r15d; DWORD
0x180009465  call    ?Create@CUwfRegKey@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; CUwfRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x18000946a  mov     ebx, eax
0x18000946c  test    eax, eax
0x18000946e  js      loc_180009636
0x180009474  shr     edi, 1Fh
0x180009477  mov     esi, 80000000h
0x18000947c  xor     dil, 1
0x180009480  mov     r13d, 80070002h
0x180009486  test    byte ptr [rbp+3E0h+arg_28], 2
0x18000948d  jz      short loc_1800094DC
0x18000948f  mov     rcx, [rsp+4E0h+hKey]; hKey
0x180009494  lea     rax, [rsp+4E0h+cbData]
0x180009499  mov     [rsp+4E0h+lpcbData], rax; lpcbData
0x18000949e  lea     ebx, [r15+4]
0x1800094a2  lea     rax, [rsp+4E0h+Data]
0x1800094a7  mov     [rsp+4E0h+Type], r15d
0x1800094ac  lea     r9, [rsp+4E0h+Type]; lpType
0x1800094b1  mov     [rsp+4E0h+lpData], rax; lpData
0x1800094b6  xor     r8d, r8d; lpReserved
0x1800094b9  mov     [rsp+4E0h+cbData], ebx
0x1800094bd  lea     rdx, [rbp+3E0h+ValueName]; lpValueName
0x1800094c4  call    cs:__imp_RegQueryValueExW
0x1800094ca  test    eax, eax
0x1800094cc  jz      short loc_1800094FA
0x1800094ce  jle     short loc_1800094DA
0x1800094d0  movzx   eax, ax
0x1800094d3  or      eax, 80070000h
0x1800094d8  test    eax, eax
0x1800094da  js      short loc_180009506
0x1800094dc  test    dil, dil
0x1800094df  jz      loc_180009597
0x1800094e5  mov     r8, r14; unsigned __int16 *
0x1800094e8  lea     rcx, [rsp+4E0h+var_488]; this
0x1800094ed  mov     rdx, r12; unsigned __int16 *
0x1800094f0  call    ?CommitRegistryValueDeletion@CUwfRegDevice@@QEAAJPEBG0@Z; CUwfRegDevice::CommitRegistryValueDeletion(ushort const *,ushort const *)
0x1800094f5  jmp     loc_1800095A4
0x1800094fa  cmp     [rsp+4E0h+Type], ebx
0x1800094fe  jnz     short loc_180009506
0x180009500  cmp     [rsp+4E0h+cbData], ebx
0x180009504  jz      short loc_1800094DC
0x180009506  mov     rcx, [rsp+4E0h+hKey]; hKey
0x18000950b  lea     rax, [rsp+4E0h+Type]
0x180009510  mov     [rsp+4E0h+lpcbData], rax; lpcbData
0x180009515  lea     r9, [rsp+4E0h+cbData]; lpType
0x18000951a  lea     rax, [rsp+4E0h+Data]
0x18000951f  mov     [rsp+4E0h+cbData], r15d
0x180009524  xor     r8d, r8d; lpReserved
0x180009527  mov     [rsp+4E0h+lpData], rax; lpData
0x18000952c  lea     rdx, [rbp+3E0h+var_460]; lpValueName
0x180009530  mov     [rsp+4E0h+Type], ebx
0x180009534  call    cs:__imp_RegQueryValueExW
0x18000953a  test    eax, eax
0x18000953c  jz      short loc_18000954E
0x18000953e  jle     short loc_18000954A
0x180009540  movzx   eax, ax
0x180009543  or      eax, 80070000h
0x180009548  test    eax, eax
0x18000954a  js      short loc_1800094DC
0x18000954c  jmp     short loc_18000955A
0x18000954e  cmp     [rsp+4E0h+cbData], ebx
0x180009552  jnz     short loc_1800094DC
0x180009554  cmp     [rsp+4E0h+Type], ebx
0x180009558  jnz     short loc_1800094DC
0x18000955a  mov     r8d, dword ptr [rsp+4E0h+Data]; unsigned int
0x18000955f  lea     rcx, [rsp+4E0h+hKey]; this
0x180009564  mov     rdx, r14; unsigned __int16 *
0x180009567  call    ?SetDWORDValue@CUwfRegKey@@QEAAJPEBGK@Z; CUwfRegKey::SetDWORDValue(ushort const *,ulong)
0x18000956c  mov     ebx, eax
0x18000956e  test    eax, eax
0x180009570  js      loc_180009636
0x180009576  test    dil, dil
0x180009579  jz      short loc_1800095B8
0x18000957b  mov     r8, r14; unsigned __int16 *
0x18000957e  lea     rcx, [rsp+4E0h+var_488]; this
0x180009583  mov     rdx, r12; unsigned __int16 *
0x180009586  call    ?CommitRegistryValue@CUwfRegDevice@@QEAAJPEBG0@Z; CUwfRegDevice::CommitRegistryValue(ushort const *,ushort const *)
0x18000958b  mov     ebx, eax
0x18000958d  test    eax, eax
0x18000958f  js      loc_180009636
0x180009595  jmp     short loc_1800095B8
0x180009597  mov     rdx, r14; unsigned __int16 *
0x18000959a  lea     rcx, [rsp+4E0h+hKey]; this
0x18000959f  call    ?DeleteValue@CUwfRegKey@@QEAAJPEBG@Z; CUwfRegKey::DeleteValue(ushort const *)
0x1800095a4  mov     ebx, eax
0x1800095a6  add     eax, esi
0x1800095a8  test    esi, eax
0x1800095aa  jnz     short loc_1800095B5
0x1800095ac  cmp     ebx, r13d
0x1800095af  jnz     loc_180009636
0x1800095b5  mov     ebx, r15d
0x1800095b8  test    byte ptr [rbp+3E0h+arg_28], 8
0x1800095bf  jz      short loc_180009636
0x1800095c1  test    dil, dil
0x1800095c4  jz      short loc_1800095FA
0x1800095c6  lea     r8, [rbp+3E0h+var_460]; unsigned __int16 *
0x1800095ca  mov     rdx, r12; unsigned __int16 *
0x1800095cd  lea     rcx, [rsp+4E0h+var_488]; this
0x1800095d2  call    ?CommitRegistryValueDeletion@CUwfRegDevice@@QEAAJPEBG0@Z; CUwfRegDevice::CommitRegistryValueDeletion(ushort const *,ushort const *)
0x1800095d7  mov     ebx, eax
0x1800095d9  add     eax, esi
0x1800095db  test    esi, eax
0x1800095dd  jnz     short loc_1800095E4
0x1800095df  cmp     ebx, r13d
0x1800095e2  jnz     short loc_180009636
0x1800095e4  lea     r8, [rbp+3E0h+ValueName]; unsigned __int16 *
0x1800095eb  mov     rdx, r12; unsigned __int16 *
0x1800095ee  lea     rcx, [rsp+4E0h+var_488]; this
0x1800095f3  call    ?CommitRegistryValueDeletion@CUwfRegDevice@@QEAAJPEBG0@Z; CUwfRegDevice::CommitRegistryValueDeletion(ushort const *,ushort const *)
0x1800095f8  jmp     short loc_180009626
0x1800095fa  lea     rdx, [rbp+3E0h+var_460]; unsigned __int16 *
0x1800095fe  lea     rcx, [rsp+4E0h+hKey]; this
0x180009603  call    ?DeleteValue@CUwfRegKey@@QEAAJPEBG@Z; CUwfRegKey::DeleteValue(ushort const *)
0x180009608  mov     ebx, eax
0x18000960a  add     eax, esi
0x18000960c  test    esi, eax
0x18000960e  jnz     short loc_180009615
0x180009610  cmp     ebx, r13d
0x180009613  jnz     short loc_180009636
0x180009615  lea     rdx, [rbp+3E0h+ValueName]; unsigned __int16 *
0x18000961c  lea     rcx, [rsp+4E0h+hKey]; this
0x180009621  call    ?DeleteValue@CUwfRegKey@@QEAAJPEBG@Z; CUwfRegKey::DeleteValue(ushort const *)
0x180009626  mov     ebx, eax
0x180009628  add     eax, esi
0x18000962a  test    esi, eax
0x18000962c  jnz     short loc_180009633
0x18000962e  cmp     ebx, r13d
0x180009631  jnz     short loc_180009636
0x180009633  mov     ebx, r15d
0x180009636  lea     rax, ??_7CDevice@@6B@; const CDevice::`vftable'
0x18000963d  lea     rcx, [rsp+4E0h+var_488]; this
0x180009642  mov     [rsp+4E0h+var_488], rax
0x180009647  call    ?Close@CDevice@@QEAAXXZ; CDevice::Close(void)
0x18000964c  lea     rcx, [rsp+4E0h+hKey]; this
0x180009651  call    ?Close@CUwfRegKey@@QEAAJXZ; CUwfRegKey::Close(void)
0x180009656  mov     eax, ebx
0x180009658  mov     rcx, [rbp+3E0h+var_40]
0x18000965f  xor     rcx, rsp; StackCookie
0x180009662  call    __security_check_cookie
0x180009667  mov     rbx, [rsp+4E0h+arg_0]
0x18000966f  add     rsp, 4B0h
0x180009676  pop     r15
0x180009678  pop     r14
0x18000967a  pop     r13
0x18000967c  pop     r12
0x18000967e  pop     rdi
0x18000967f  pop     rsi
0x180009680  pop     rbp
0x180009681  retn
```
