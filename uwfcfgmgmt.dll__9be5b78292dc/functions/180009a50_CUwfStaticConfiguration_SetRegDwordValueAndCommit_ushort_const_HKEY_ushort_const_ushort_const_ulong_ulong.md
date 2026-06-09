# CUwfStaticConfiguration::SetRegDwordValueAndCommit(ushort const *,HKEY__ *,ushort const *,ushort const *,ulong,ulong)

- ea: `0x180009a50`
- end: `0x180009f32`
- name: `?SetRegDwordValueAndCommit@CUwfStaticConfiguration@@AEAAJPEBGPEAUHKEY__@@00KK@Z`
- size: `1250`
- prototype: `__int64 __fastcall(CUwfStaticConfiguration *this, const unsigned __int16 *, HKEY, const unsigned __int16 *, const unsigned __int16 *lpValueName, char, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009688`

## callees

- `0x1800053ac`
- `0x180009a50`
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

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009c5c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009cbd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009d16`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009c5c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009cbd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009d16`

## pseudocode

```c
__int64 __fastcall CUwfStaticConfiguration::SetRegDwordValueAndCommit(
        CUwfStaticConfiguration *this,
        const unsigned __int16 *a2,
        HKEY a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *lpValueName,
        char a6,
        unsigned int a7)
{
  int v9; // r14d
  signed int v10; // ebx
  __int64 v11; // r15
  WCHAR *v12; // r8
  __int64 v13; // rsi
  __int64 v14; // rax
  unsigned __int64 v15; // rdx
  const unsigned __int16 *v16; // rcx
  bool v17; // di
  WCHAR *v18; // rcx
  const unsigned __int16 *v19; // rax
  WCHAR *v20; // rdx
  WCHAR *v21; // rcx
  LSTATUS v22; // eax
  int v23; // ebx
  LSTATUS v24; // eax
  bool v25; // sf
  LSTATUS v26; // eax
  bool v27; // sf
  int v28; // eax
  DWORD Type; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  BYTE Data[4]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v34[2]; // [rsp+58h] [rbp-A8h] BYREF
  char v35; // [rsp+68h] [rbp-98h]
  int v36; // [rsp+70h] [rbp-90h]
  WCHAR ValueName[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR v38[264]; // [rsp+290h] [rbp+190h] BYREF

  v34[1] = -1;
  hKey = 0;
  v35 = 0;
  v34[0] = &CUwfRegDevice::`vftable';
  v36 = -2147019873;
  *(_DWORD *)Data = 0;
  memset_0(ValueName, 0, 0x208u);
  memset_0(v38, 0, 0x208u);
  v9 = CDevice::Initialize((CDevice *)v34, L"\\\\.\\UwfregControl");
  v36 = v9;
  v10 = CUwfRegKey::Create(&hKey, HKEY_LOCAL_MACHINE, a4, 0, 0, 0xF003Fu, 0, 0);
  if ( v10 < 0 )
    goto LABEL_65;
  v11 = 2147483646;
  v12 = ValueName;
  v13 = 260;
  v14 = 2147483646;
  v15 = 260;
  v16 = lpValueName;
  v17 = 1;
  do
  {
    if ( !v14 )
      break;
    if ( !*v16 )
      break;
    *v12++ = *v16++;
    --v14;
    --v15;
  }
  while ( v15 );
  v18 = v12 - 1;
  v10 = v15 == 0 ? 0x8007007A : 0;
  if ( v15 )
    v18 = v12;
  *v18 = 0;
  if ( !v15 )
    goto LABEL_65;
  v10 = StringCchCatW(ValueName, v15, L".uwf");
  if ( v10 < 0 )
    goto LABEL_65;
  v19 = lpValueName;
  v20 = v38;
  do
  {
    if ( !v11 )
      break;
    if ( !*v19 )
      break;
    *v20++ = *v19++;
    --v11;
    --v13;
  }
  while ( v13 );
  v21 = v20 - 1;
  v10 = v13 == 0 ? 0x8007007A : 0;
  if ( v13 )
    v21 = v20;
  *v21 = 0;
  if ( !v13 )
    goto LABEL_65;
  v10 = StringCchCatW(v38, (unsigned __int64)v20, L".uwf_del");
  if ( v10 < 0 )
    goto LABEL_65;
  if ( (a6 & 1) == 0 )
  {
LABEL_62:
    v10 = CUwfRegKey::SetDWORDValue(&hKey, lpValueName, a7);
    if ( v10 >= 0 && v9 >= 0 )
      v10 = CUwfRegDevice::CommitRegistryValue((CUwfRegDevice *)v34, a2, lpValueName);
    goto LABEL_65;
  }
  Type = 0;
  cbData = 4;
  v22 = RegQueryValueExW(hKey, ValueName, 0, &Type, Data, &cbData);
  if ( v22 )
  {
    v23 = -2147024896;
    if ( v22 <= 0 )
      v23 = v22;
  }
  else if ( Type == 4 )
  {
    v23 = 0;
    if ( cbData != 4 )
      v23 = -2147024883;
  }
  else
  {
    v23 = -2147023267;
  }
  cbData = 0;
  Type = 4;
  v24 = RegQueryValueExW(hKey, v38, 0, &cbData, Data, &Type);
  v25 = v24 < 0;
  if ( !v24 )
  {
    if ( cbData == 4 && Type == 4 )
      goto LABEL_35;
LABEL_34:
    v17 = v23 >= 0;
    goto LABEL_35;
  }
  if ( v24 > 0 )
    v25 = 1;
  if ( v25 )
    goto LABEL_34;
LABEL_35:
  cbData = 0;
  Type = 4;
  v26 = RegQueryValueExW(hKey, lpValueName, 0, &cbData, Data, &Type);
  v27 = v26 < 0;
  if ( !v26 )
  {
    if ( cbData != 4 || Type != 4 )
      goto LABEL_39;
LABEL_48:
    if ( v17 )
      goto LABEL_62;
    v28 = CUwfRegKey::SetDWORDValue(&hKey, ValueName, *(int *)Data);
    v10 = v28;
    if ( v9 < 0 )
    {
      if ( v28 < 0 )
        goto LABEL_65;
      v10 = CUwfRegKey::DeleteValue(&hKey, v38);
      if ( (int)(v10 + 0x80000000) >= 0 && v10 != -2147024894 )
        goto LABEL_65;
      goto LABEL_62;
    }
    if ( v28 < 0 )
      goto LABEL_65;
    v10 = CUwfRegDevice::CommitRegistryValue((CUwfRegDevice *)v34, a2, ValueName);
    if ( v10 < 0 )
      goto LABEL_65;
    v10 = CUwfRegDevice::CommitRegistryValueDeletion((CUwfRegDevice *)v34, a2, v38);
    if ( (int)(v10 + 0x80000000) >= 0 && v10 != -2147024894 )
      goto LABEL_65;
    goto LABEL_45;
  }
  if ( v26 > 0 )
    v27 = 1;
  if ( !v27 )
    goto LABEL_48;
LABEL_39:
  if ( v17 )
    goto LABEL_62;
  if ( v9 < 0 )
  {
    v10 = CUwfRegKey::DeleteValue(&hKey, ValueName);
    if ( (int)(v10 + 0x80000000) < 0 || v10 == -2147024894 )
    {
      v10 = CUwfRegKey::SetDWORDValue(&hKey, v38, 0);
      if ( v10 >= 0 )
        goto LABEL_62;
    }
  }
  else
  {
    v10 = CUwfRegDevice::CommitRegistryValueDeletion((CUwfRegDevice *)v34, a2, ValueName);
    if ( (int)(v10 + 0x80000000) < 0 || v10 == -2147024894 )
    {
      v10 = CUwfRegKey::SetDWORDValue(&hKey, v38, 0);
      if ( v10 >= 0 )
      {
        v10 = CUwfRegDevice::CommitRegistryValue((CUwfRegDevice *)v34, a2, v38);
        if ( v10 >= 0 )
        {
LABEL_45:
          v9 = v36;
          goto LABEL_62;
        }
      }
    }
  }
LABEL_65:
  v34[0] = &CDevice::`vftable';
  CDevice::Close((CDevice *)v34);
  CUwfRegKey::Close(&hKey);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180009a50  mov     [rsp-8+arg_0], rbx
0x180009a55  push    rbp
0x180009a56  push    rsi
0x180009a57  push    rdi
0x180009a58  push    r12
0x180009a5a  push    r13
0x180009a5c  push    r14
0x180009a5e  push    r15
0x180009a60  lea     rbp, [rsp-3B0h]
0x180009a68  sub     rsp, 4B0h
0x180009a6f  mov     rax, cs:__security_cookie
0x180009a76  xor     rax, rsp
0x180009a79  mov     [rbp+3E0h+var_40], rax
0x180009a80  mov     r13, [rbp+3E0h+lpValueName]
0x180009a87  lea     rax, ??_7CUwfRegDevice@@6B@; const CUwfRegDevice::`vftable'
0x180009a8e  xor     esi, esi
0x180009a90  mov     [rsp+4E0h+var_480], 0FFFFFFFFFFFFFFFFh
0x180009a99  mov     r12, rdx
0x180009a9c  mov     [rsp+4E0h+hKey], rsi
0x180009aa1  mov     edi, 208h
0x180009aa6  mov     [rsp+4E0h+var_478], sil
0x180009aab  mov     r8d, edi; Size
0x180009aae  mov     [rsp+4E0h+var_488], rax
0x180009ab3  xor     edx, edx; Val
0x180009ab5  mov     [rsp+4E0h+var_470], 8007139Fh
0x180009abd  lea     rcx, [rbp+3E0h+ValueName]; void *
0x180009ac1  mov     dword ptr [rsp+4E0h+Data], esi
0x180009ac5  mov     rbx, r9
0x180009ac8  call    memset_0
0x180009acd  mov     r8d, edi; Size
0x180009ad0  lea     rcx, [rbp+3E0h+var_250]; void *
0x180009ad7  xor     edx, edx; Val
0x180009ad9  call    memset_0
0x180009ade  lea     rdx, FileName; "\\\\.\\UwfregControl"
0x180009ae5  lea     rcx, [rsp+4E0h+var_488]; this
0x180009aea  call    ?Initialize@CDevice@@QEAAJPEBG@Z; CDevice::Initialize(ushort const *)
0x180009aef  mov     [rsp+4E0h+var_4A8], rsi; LPDWORD
0x180009af4  lea     rcx, [rsp+4E0h+hKey]; phkResult
0x180009af9  mov     [rsp+4E0h+var_4B0], rsi; LPSECURITY_ATTRIBUTES
0x180009afe  xor     r9d, r9d; lpClass
0x180009b01  mov     dword ptr [rsp+4E0h+lpcbData], 0F003Fh; REGSAM
0x180009b09  mov     r8, rbx; lpSubKey
0x180009b0c  mov     rdx, 0FFFFFFFF80000002h; hKey
0x180009b13  mov     dword ptr [rsp+4E0h+lpData], esi; DWORD
0x180009b17  mov     r14d, eax
0x180009b1a  mov     [rsp+4E0h+var_470], eax
0x180009b1e  call    ?Create@CUwfRegKey@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; CUwfRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x180009b23  mov     ebx, eax
0x180009b25  test    eax, eax
0x180009b27  js      loc_180009EE6
0x180009b2d  mov     r15d, 7FFFFFFEh
0x180009b33  lea     r8, [rbp+3E0h+ValueName]
0x180009b37  mov     esi, 104h
0x180009b3c  mov     eax, r15d
0x180009b3f  mov     edx, esi
0x180009b41  mov     rcx, r13
0x180009b44  mov     edi, 1
0x180009b49  xor     r10d, r10d
0x180009b4c  test    rax, rax
0x180009b4f  jz      short loc_180009B6F
0x180009b51  movzx   r9d, word ptr [rcx]
0x180009b55  test    r9w, r9w
0x180009b59  jz      short loc_180009B6F
0x180009b5b  mov     [r8], r9w
0x180009b5f  add     rcx, 2
0x180009b63  add     r8, 2
0x180009b67  sub     rax, rdi
0x180009b6a  sub     rdx, rdi; unsigned __int64
0x180009b6d  jnz     short loc_180009B4C
0x180009b6f  mov     rax, rdx
0x180009b72  lea     rcx, [r8-2]
0x180009b76  neg     rax
0x180009b79  sbb     ebx, ebx
0x180009b7b  not     ebx
0x180009b7d  and     ebx, 8007007Ah
0x180009b83  test    rdx, rdx
0x180009b86  cmovnz  rcx, r8
0x180009b8a  mov     [rcx], r10w
0x180009b8e  jz      loc_180009EE6
0x180009b94  lea     r8, aUwf; ".uwf"
0x180009b9b  lea     rcx, [rbp+3E0h+ValueName]; unsigned __int16 *
0x180009b9f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009ba4  mov     ebx, eax
0x180009ba6  test    eax, eax
0x180009ba8  js      loc_180009EE6
0x180009bae  mov     rax, r13
0x180009bb1  lea     rdx, [rbp+3E0h+var_250]
0x180009bb8  test    r15, r15
0x180009bbb  jz      short loc_180009BD8
0x180009bbd  movzx   ecx, word ptr [rax]
0x180009bc0  test    cx, cx
0x180009bc3  jz      short loc_180009BD8
0x180009bc5  mov     [rdx], cx
0x180009bc8  add     rax, 2
0x180009bcc  add     rdx, 2; unsigned __int64
0x180009bd0  sub     r15, rdi
0x180009bd3  sub     rsi, rdi
0x180009bd6  jnz     short loc_180009BB8
0x180009bd8  mov     rax, rsi
0x180009bdb  lea     rcx, [rdx-2]
0x180009bdf  neg     rax
0x180009be2  sbb     ebx, ebx
0x180009be4  xor     r15d, r15d
0x180009be7  not     ebx
0x180009be9  and     ebx, 8007007Ah
0x180009bef  test    rsi, rsi
0x180009bf2  cmovnz  rcx, rdx
0x180009bf6  mov     [rcx], r15w
0x180009bfa  jz      loc_180009EE6
0x180009c00  lea     r8, aUwfDel; ".uwf_del"
0x180009c07  lea     rcx, [rbp+3E0h+var_250]; unsigned __int16 *
0x180009c0e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009c13  mov     ebx, eax
0x180009c15  test    eax, eax
0x180009c17  js      loc_180009EE6
0x180009c1d  test    [rbp+3E0h+arg_28], dil
0x180009c24  jz      loc_180009EB5
0x180009c2a  mov     rcx, [rsp+4E0h+hKey]; hKey
0x180009c2f  lea     rax, [rsp+4E0h+cbData]
0x180009c34  mov     [rsp+4E0h+lpcbData], rax; lpcbData
0x180009c39  lea     esi, [r15+4]
0x180009c3d  lea     rax, [rsp+4E0h+Data]
0x180009c42  mov     [rsp+4E0h+Type], r15d
0x180009c47  lea     r9, [rsp+4E0h+Type]; lpType
0x180009c4c  mov     [rsp+4E0h+lpData], rax; lpData
0x180009c51  xor     r8d, r8d; lpReserved
0x180009c54  mov     [rsp+4E0h+cbData], esi
0x180009c58  lea     rdx, [rbp+3E0h+ValueName]; lpValueName
0x180009c5c  call    cs:__imp_RegQueryValueExW
0x180009c62  test    eax, eax
0x180009c64  jz      short loc_180009C70
0x180009c66  mov     ebx, 80070000h
0x180009c6b  cmovle  ebx, eax
0x180009c6e  jmp     short loc_180009C8C
0x180009c70  cmp     [rsp+4E0h+Type], esi
0x180009c74  jz      short loc_180009C7D
0x180009c76  mov     ebx, 8007065Dh
0x180009c7b  jmp     short loc_180009C8C
0x180009c7d  cmp     [rsp+4E0h+cbData], esi
0x180009c81  mov     ebx, r15d
0x180009c84  mov     eax, 8007000Dh
0x180009c89  cmovnz  ebx, eax
0x180009c8c  mov     rcx, [rsp+4E0h+hKey]; hKey
0x180009c91  lea     rax, [rsp+4E0h+Type]
0x180009c96  mov     [rsp+4E0h+lpcbData], rax; lpcbData
0x180009c9b  lea     r9, [rsp+4E0h+cbData]; lpType
0x180009ca0  lea     rax, [rsp+4E0h+Data]
0x180009ca5  mov     [rsp+4E0h+cbData], r15d
0x180009caa  xor     r8d, r8d; lpReserved
0x180009cad  mov     [rsp+4E0h+lpData], rax; lpData
0x180009cb2  lea     rdx, [rbp+3E0h+var_250]; lpValueName
0x180009cb9  mov     [rsp+4E0h+Type], esi
0x180009cbd  call    cs:__imp_RegQueryValueExW
0x180009cc3  test    eax, eax
0x180009cc5  jz      short loc_180009CD7
0x180009cc7  jle     short loc_180009CD3
0x180009cc9  movzx   eax, ax
0x180009ccc  or      eax, 80070000h
0x180009cd1  test    eax, eax
0x180009cd3  js      short loc_180009CE3
0x180009cd5  jmp     short loc_180009CE9
0x180009cd7  cmp     [rsp+4E0h+cbData], esi
0x180009cdb  jnz     short loc_180009CE3
0x180009cdd  cmp     [rsp+4E0h+Type], esi
0x180009ce1  jz      short loc_180009CE9
0x180009ce3  shr     ebx, 1Fh
0x180009ce6  xor     dil, bl
0x180009ce9  mov     rcx, [rsp+4E0h+hKey]; hKey
0x180009cee  lea     rax, [rsp+4E0h+Type]
0x180009cf3  mov     [rsp+4E0h+lpcbData], rax; lpcbData
0x180009cf8  lea     r9, [rsp+4E0h+cbData]; lpType
0x180009cfd  lea     rax, [rsp+4E0h+Data]
0x180009d02  mov     [rsp+4E0h+cbData], r15d
0x180009d07  xor     r8d, r8d; lpReserved
0x180009d0a  mov     [rsp+4E0h+lpData], rax; lpData
0x180009d0f  mov     rdx, r13; lpValueName
0x180009d12  mov     [rsp+4E0h+Type], esi
0x180009d16  call    cs:__imp_RegQueryValueExW
0x180009d1c  test    eax, eax
0x180009d1e  jz      loc_180009DB8
0x180009d24  jle     short loc_180009D30
0x180009d26  movzx   eax, ax
0x180009d29  or      eax, 80070000h
0x180009d2e  test    eax, eax
0x180009d30  jns     loc_180009DCC
0x180009d36  test    dil, dil
0x180009d39  jnz     loc_180009EB5
0x180009d3f  test    r14d, r14d
0x180009d42  js      loc_180009E78
0x180009d48  lea     r8, [rbp+3E0h+ValueName]; unsigned __int16 *
0x180009d4c  mov     rdx, r12; unsigned __int16 *
0x180009d4f  lea     rcx, [rsp+4E0h+var_488]; this
0x180009d54  call    ?CommitRegistryValueDeletion@CUwfRegDevice@@QEAAJPEBG0@Z; CUwfRegDevice::CommitRegistryValueDeletion(ushort const *,ushort const *)
0x180009d59  mov     ecx, 80000000h
0x180009d5e  mov     ebx, eax
0x180009d60  add     eax, ecx
0x180009d62  test    ecx, eax
0x180009d64  jnz     short loc_180009D72
0x180009d66  cmp     ebx, 80070002h
0x180009d6c  jnz     loc_180009EE6
0x180009d72  xor     r8d, r8d; unsigned int
0x180009d75  lea     rdx, [rbp+3E0h+var_250]; unsigned __int16 *
0x180009d7c  lea     rcx, [rsp+4E0h+hKey]; this
0x180009d81  call    ?SetDWORDValue@CUwfRegKey@@QEAAJPEBGK@Z; CUwfRegKey::SetDWORDValue(ushort const *,ulong)
0x180009d86  mov     ebx, eax
0x180009d88  test    eax, eax
0x180009d8a  js      loc_180009EE6
0x180009d90  lea     r8, [rbp+3E0h+var_250]; unsigned __int16 *
0x180009d97  mov     rdx, r12; unsigned __int16 *
0x180009d9a  lea     rcx, [rsp+4E0h+var_488]; this
0x180009d9f  call    ?CommitRegistryValue@CUwfRegDevice@@QEAAJPEBG0@Z; CUwfRegDevice::CommitRegistryValue(ushort const *,ushort const *)
0x180009da4  mov     ebx, eax
0x180009da6  test    eax, eax
0x180009da8  js      loc_180009EE6
0x180009dae  mov     r14d, [rsp+4E0h+var_470]
0x180009db3  jmp     loc_180009EB5
0x180009db8  cmp     [rsp+4E0h+cbData], esi
0x180009dbc  jnz     loc_180009D36
0x180009dc2  cmp     [rsp+4E0h+Type], esi
0x180009dc6  jnz     loc_180009D36
0x180009dcc  test    dil, dil
0x180009dcf  jnz     loc_180009EB5
0x180009dd5  mov     r8d, dword ptr [rsp+4E0h+Data]; unsigned int
0x180009dda  lea     rdx, [rbp+3E0h+ValueName]; unsigned __int16 *
0x180009dde  lea     rcx, [rsp+4E0h+hKey]; this
0x180009de3  call    ?SetDWORDValue@CUwfRegKey@@QEAAJPEBGK@Z; CUwfRegKey::SetDWORDValue(ushort const *,ulong)
0x180009de8  mov     ebx, eax
0x180009dea  test    r14d, r14d
0x180009ded  js      short loc_180009E48
0x180009def  test    eax, eax
0x180009df1  js      loc_180009EE6
0x180009df7  lea     r8, [rbp+3E0h+ValueName]; unsigned __int16 *
0x180009dfb  mov     rdx, r12; unsigned __int16 *
0x180009dfe  lea     rcx, [rsp+4E0h+var_488]; this
0x180009e03  call    ?CommitRegistryValue@CUwfRegDevice@@QEAAJPEBG0@Z; CUwfRegDevice::CommitRegistryValue(ushort const *,ushort const *)
0x180009e08  mov     ebx, eax
0x180009e0a  test    eax, eax
0x180009e0c  js      loc_180009EE6
0x180009e12  lea     r8, [rbp+3E0h+var_250]; unsigned __int16 *
0x180009e19  mov     rdx, r12; unsigned __int16 *
0x180009e1c  lea     rcx, [rsp+4E0h+var_488]; this
0x180009e21  call    ?CommitRegistryValueDeletion@CUwfRegDevice@@QEAAJPEBG0@Z; CUwfRegDevice::CommitRegistryValueDeletion(ushort const *,ushort const *)
0x180009e26  mov     ecx, 80000000h
0x180009e2b  mov     ebx, eax
0x180009e2d  add     eax, ecx
0x180009e2f  test    ecx, eax
0x180009e31  jnz     loc_180009DAE
0x180009e37  cmp     ebx, 80070002h
0x180009e3d  jnz     loc_180009EE6
0x180009e43  jmp     loc_180009DAE
0x180009e48  test    eax, eax
0x180009e4a  js      loc_180009EE6
0x180009e50  lea     rdx, [rbp+3E0h+var_250]; unsigned __int16 *
0x180009e57  lea     rcx, [rsp+4E0h+hKey]; this
0x180009e5c  call    ?DeleteValue@CUwfRegKey@@QEAAJPEBG@Z; CUwfRegKey::DeleteValue(ushort const *)
0x180009e61  mov     ecx, 80000000h
0x180009e66  mov     ebx, eax
0x180009e68  add     eax, ecx
0x180009e6a  test    ecx, eax
0x180009e6c  jnz     short loc_180009EB5
0x180009e6e  cmp     ebx, 80070002h
0x180009e74  jnz     short loc_180009EE6
0x180009e76  jmp     short loc_180009EB5
0x180009e78  lea     rdx, [rbp+3E0h+ValueName]; unsigned __int16 *
0x180009e7c  lea     rcx, [rsp+4E0h+hKey]; this
0x180009e81  call    ?DeleteValue@CUwfRegKey@@QEAAJPEBG@Z; CUwfRegKey::DeleteValue(ushort const *)
0x180009e86  mov     ecx, 80000000h
0x180009e8b  mov     ebx, eax
0x180009e8d  add     eax, ecx
0x180009e8f  test    ecx, eax
0x180009e91  jnz     short loc_180009E9B
0x180009e93  cmp     ebx, 80070002h
0x180009e99  jnz     short loc_180009EE6
0x180009e9b  xor     r8d, r8d; unsigned int
0x180009e9e  lea     rdx, [rbp+3E0h+var_250]; unsigned __int16 *
0x180009ea5  lea     rcx, [rsp+4E0h+hKey]; this
0x180009eaa  call    ?SetDWORDValue@CUwfRegKey@@QEAAJPEBGK@Z; CUwfRegKey::SetDWORDValue(ushort const *,ulong)
0x180009eaf  mov     ebx, eax
0x180009eb1  test    eax, eax
0x180009eb3  js      short loc_180009EE6
0x180009eb5  mov     r8d, [rbp+3E0h+arg_30]; unsigned int
0x180009ebc  lea     rcx, [rsp+4E0h+hKey]; this
0x180009ec1  mov     rdx, r13; unsigned __int16 *
0x180009ec4  call    ?SetDWORDValue@CUwfRegKey@@QEAAJPEBGK@Z; CUwfRegKey::SetDWORDValue(ushort const *,ulong)
0x180009ec9  mov     ebx, eax
0x180009ecb  test    eax, eax
0x180009ecd  js      short loc_180009EE6
0x180009ecf  test    r14d, r14d
0x180009ed2  js      short loc_180009EE6
0x180009ed4  mov     r8, r13; unsigned __int16 *
0x180009ed7  lea     rcx, [rsp+4E0h+var_488]; this
0x180009edc  mov     rdx, r12; unsigned __int16 *
0x180009edf  call    ?CommitRegistryValue@CUwfRegDevice@@QEAAJPEBG0@Z; CUwfRegDevice::CommitRegistryValue(ushort const *,ushort const *)
0x180009ee4  mov     ebx, eax
0x180009ee6  lea     rax, ??_7CDevice@@6B@; const CDevice::`vftable'
0x180009eed  lea     rcx, [rsp+4E0h+var_488]; this
0x180009ef2  mov     [rsp+4E0h+var_488], rax
0x180009ef7  call    ?Close@CDevice@@QEAAXXZ; CDevice::Close(void)
0x180009efc  lea     rcx, [rsp+4E0h+hKey]; this
0x180009f01  call    ?Close@CUwfRegKey@@QEAAJXZ; CUwfRegKey::Close(void)
  ... truncated ...
```
