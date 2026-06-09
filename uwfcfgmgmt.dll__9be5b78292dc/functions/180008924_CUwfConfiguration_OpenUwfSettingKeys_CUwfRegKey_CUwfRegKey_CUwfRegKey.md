# CUwfConfiguration::OpenUwfSettingKeys(CUwfRegKey &,CUwfRegKey &,CUwfRegKey &)

- ea: `0x180008924`
- end: `0x180008b33`
- name: `?OpenUwfSettingKeys@CUwfConfiguration@@AEAAJAEAVCUwfRegKey@@00@Z`
- size: `527`
- prototype: `__int64 __fastcall(CUwfConfiguration *this, HKEY *, HKEY *, HKEY *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800091f0`

## callees

- `0x180008924`
- `0x18000d5f0`
- `0x18000de30`
- `0x18000df60`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800089fa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008ab2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800089fa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008ab2`

## string_xrefs

- `0x180008ae6`: `SYSTEM\CurrentControlSet\Services\UWFVOL\Parameters\Static\Copy0`
- `0x180008adf`: `SYSTEM\CurrentControlSet\Services\UWFVOL\Parameters\Static\Copy1`
- `0x1800089ec`: `UpdatedSettings`
- `0x180008aa4`: `UpdatedSettings`
- `0x18000895b`: `SYSTEM\CurrentControlSet\Services\UWFVOL\Parameters.Default\Dynamic`
- `0x180008993`: `SYSTEM\CurrentControlSet\Services\UWFVOL\Parameters.Default\Static`
- `0x180008a24`: `SYSTEM\CurrentControlSet\Services\UWFVOL\Parameters.Default\Static\Copy0`
- `0x180008a1d`: `SYSTEM\CurrentControlSet\Services\UWFVOL\Parameters.Default\Static\Copy1`

## pseudocode

```c
__int64 __fastcall CUwfConfiguration::OpenUwfSettingKeys(CUwfConfiguration *this, HKEY *a2, HKEY *a3, HKEY *a4)
{
  void *v4; // rax
  int v8; // eax
  signed int v9; // ebx
  void *v10; // rax
  int v11; // eax
  LSTATUS v12; // eax
  const WCHAR *v13; // r8
  int v14; // eax
  HKEY v15; // rcx
  LSTATUS v16; // eax
  const WCHAR *v17; // r8
  signed int v18; // eax
  DWORD Type; // [rsp+30h] [rbp-18h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-14h] BYREF
  HKEY hKey[2]; // [rsp+38h] [rbp-10h] BYREF
  int Data; // [rsp+80h] [rbp+38h] BYREF

  v4 = (void *)*((_QWORD *)this + 1);
  Data = 0;
  hKey[0] = 0;
  if ( v4 == (void *)-1LL )
    v8 = CUwfRegKey::Open(
           a2,
           HKEY_LOCAL_MACHINE,
           L"SYSTEM\\CurrentControlSet\\Services\\UWFVOL\\Parameters.Default\\Dynamic",
           0x20019u);
  else
    v8 = CUwfRegKey::OpenTransacted(
           a2,
           HKEY_LOCAL_MACHINE,
           L"SYSTEM\\CurrentControlSet\\Services\\UWFVOL\\Parameters.Default\\Dynamic",
           0x20019u,
           v4);
  v9 = v8;
  if ( v8 < 0 )
    goto LABEL_36;
  v10 = (void *)*((_QWORD *)this + 1);
  v11 = v10 == (void *)-1LL
      ? CUwfRegKey::Open(
          hKey,
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Services\\UWFVOL\\Parameters.Default\\Static",
          0x20019u)
      : CUwfRegKey::OpenTransacted(
          hKey,
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Services\\UWFVOL\\Parameters.Default\\Static",
          0x20019u,
          v10);
  v9 = v11;
  if ( v11 < 0 )
    goto LABEL_36;
  Type = 0;
  cbData = 4;
  v12 = RegQueryValueExW(hKey[0], L"UpdatedSettings", 0, &Type, (LPBYTE)&Data, &cbData);
  v9 = v12;
  if ( v12 )
  {
    if ( v12 > 0 )
      v9 = (unsigned __int16)v12 | 0x80070000;
    if ( v9 < 0 )
      goto LABEL_36;
  }
  else
  {
    if ( Type != 4 )
      goto LABEL_18;
    if ( cbData != 4 )
      goto LABEL_20;
  }
  v13 = L"SYSTEM\\CurrentControlSet\\Services\\UWFVOL\\Parameters.Default\\Static\\Copy0";
  if ( Data )
    v13 = L"SYSTEM\\CurrentControlSet\\Services\\UWFVOL\\Parameters.Default\\Static\\Copy1";
  if ( *((_QWORD *)this + 1) == -1 )
    v14 = CUwfRegKey::Open(a3, HKEY_LOCAL_MACHINE, v13, 0x20019u);
  else
    v14 = CUwfRegKey::OpenTransacted(a3, HKEY_LOCAL_MACHINE, v13, 0x20019u, *((HANDLE *)this + 1));
  v9 = v14;
  if ( v14 >= 0 )
  {
    v15 = (HKEY)*((_QWORD *)this + 4);
    cbData = 0;
    Type = 4;
    v16 = RegQueryValueExW(v15, L"UpdatedSettings", 0, &cbData, (LPBYTE)&Data, &Type);
    v9 = v16;
    if ( v16 )
    {
      if ( v16 > 0 )
        v9 = (unsigned __int16)v16 | 0x80070000;
      if ( v9 < 0 )
        goto LABEL_36;
LABEL_30:
      v17 = L"SYSTEM\\CurrentControlSet\\Services\\UWFVOL\\Parameters\\Static\\Copy0";
      if ( Data )
        v17 = L"SYSTEM\\CurrentControlSet\\Services\\UWFVOL\\Parameters\\Static\\Copy1";
      if ( *((_QWORD *)this + 1) == -1 )
        v18 = CUwfRegKey::Open(a4, HKEY_LOCAL_MACHINE, v17, 0xF003Fu);
      else
        v18 = CUwfRegKey::OpenTransacted(a4, HKEY_LOCAL_MACHINE, v17, 0xF003Fu, *((HANDLE *)this + 1));
      v9 = v18;
      goto LABEL_36;
    }
    if ( cbData == 4 )
    {
      if ( Type == 4 )
        goto LABEL_30;
LABEL_20:
      v9 = -2147024883;
      goto LABEL_36;
    }
LABEL_18:
    v9 = -2147023267;
  }
LABEL_36:
  CUwfRegKey::Close(hKey);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180008924  push    rbp
0x180008926  push    rbx
0x180008927  push    rdi
0x180008928  push    r12
0x18000892a  push    r14
0x18000892c  push    r15
0x18000892e  mov     rbp, rsp
0x180008931  sub     rsp, 48h
0x180008935  mov     rax, [rcx+8]
0x180008939  mov     r14, rcx
0x18000893c  mov     [rbp+Data], 0
0x180008943  mov     rdi, 0FFFFFFFF80000002h
0x18000894a  mov     [rbp+hKey], 0
0x180008952  mov     r15, r9
0x180008955  mov     r12, r8
0x180008958  mov     r10, rdx
0x18000895b  lea     r8, aSystemCurrentc_16; "SYSTEM\\CurrentControlSet\\Services\\UW"...
0x180008962  mov     rcx, rdx; phkResult
0x180008965  mov     r9d, 20019h; samDesired
0x18000896b  mov     rdx, rdi; hKey
0x18000896e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180008972  jz      short loc_180008980
0x180008974  mov     [rsp+48h+lpData], rax; HANDLE
0x180008979  call    ?OpenTransacted@CUwfRegKey@@QEAAJPEAUHKEY__@@PEBGKPEAX@Z; CUwfRegKey::OpenTransacted(HKEY__ *,ushort const *,ulong,void *)
0x18000897e  jmp     short loc_180008985
0x180008980  call    ?Open@CUwfRegKey@@QEAAJPEAUHKEY__@@PEBGK@Z; CUwfRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180008985  mov     ebx, eax
0x180008987  test    eax, eax
0x180008989  js      loc_180008B1A
0x18000898f  mov     rax, [r14+8]
0x180008993  lea     r8, aSystemCurrentc_14; "SYSTEM\\CurrentControlSet\\Services\\UW"...
0x18000899a  lea     rcx, [rbp+hKey]; phkResult
0x18000899e  mov     r9d, 20019h; samDesired
0x1800089a4  mov     rdx, rdi; hKey
0x1800089a7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800089ab  jz      short loc_1800089B9
0x1800089ad  mov     [rsp+48h+lpData], rax; HANDLE
0x1800089b2  call    ?OpenTransacted@CUwfRegKey@@QEAAJPEAUHKEY__@@PEBGKPEAX@Z; CUwfRegKey::OpenTransacted(HKEY__ *,ushort const *,ulong,void *)
0x1800089b7  jmp     short loc_1800089BE
0x1800089b9  call    ?Open@CUwfRegKey@@QEAAJPEAUHKEY__@@PEBGK@Z; CUwfRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800089be  mov     ebx, eax
0x1800089c0  test    eax, eax
0x1800089c2  js      loc_180008B1A
0x1800089c8  mov     rcx, [rbp+hKey]; hKey
0x1800089cc  lea     rax, [rbp+cbData]
0x1800089d0  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1800089d5  lea     r9, [rbp+Type]; lpType
0x1800089d9  lea     rax, [rbp+Data]
0x1800089dd  mov     [rbp+Type], 0
0x1800089e4  xor     r8d, r8d; lpReserved
0x1800089e7  mov     [rsp+48h+lpData], rax; lpData
0x1800089ec  lea     rdx, aUpdatedsetting; "UpdatedSettings"
0x1800089f3  mov     [rbp+cbData], 4
0x1800089fa  call    cs:__imp_RegQueryValueExW
0x180008a00  mov     ebx, eax
0x180008a02  test    eax, eax
0x180008a04  jz      short loc_180008A51
0x180008a06  jle     short loc_180008A11
0x180008a08  movzx   ebx, ax
0x180008a0b  or      ebx, 80070000h
0x180008a11  test    ebx, ebx
0x180008a13  js      loc_180008B1A
0x180008a19  cmp     [rbp+Data], 0
0x180008a1d  lea     rax, aSystemCurrentc_6; "SYSTEM\\CurrentControlSet\\Services\\UW"...
0x180008a24  lea     r8, aSystemCurrentc_5; "SYSTEM\\CurrentControlSet\\Services\\UW"...
0x180008a2b  mov     r9d, 20019h; samDesired
0x180008a31  cmovnz  r8, rax; lpSubKey
0x180008a35  mov     rdx, rdi; hKey
0x180008a38  mov     rax, [r14+8]
0x180008a3c  mov     rcx, r12; phkResult
0x180008a3f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180008a43  jz      short loc_180008A71
0x180008a45  mov     [rsp+48h+lpData], rax; HANDLE
0x180008a4a  call    ?OpenTransacted@CUwfRegKey@@QEAAJPEAUHKEY__@@PEBGKPEAX@Z; CUwfRegKey::OpenTransacted(HKEY__ *,ushort const *,ulong,void *)
0x180008a4f  jmp     short loc_180008A76
0x180008a51  cmp     [rbp+Type], 4
0x180008a55  jz      short loc_180008A61
0x180008a57  mov     ebx, 8007065Dh
0x180008a5c  jmp     loc_180008B1A
0x180008a61  cmp     [rbp+cbData], 4
0x180008a65  jz      short loc_180008A19
0x180008a67  mov     ebx, 8007000Dh
0x180008a6c  jmp     loc_180008B1A
0x180008a71  call    ?Open@CUwfRegKey@@QEAAJPEAUHKEY__@@PEBGK@Z; CUwfRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180008a76  mov     ebx, eax
0x180008a78  test    eax, eax
0x180008a7a  js      loc_180008B1A
0x180008a80  mov     rcx, [r14+20h]; hKey
0x180008a84  lea     rax, [rbp+Type]
0x180008a88  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180008a8d  lea     r9, [rbp+cbData]; lpType
0x180008a91  lea     rax, [rbp+Data]
0x180008a95  mov     [rbp+cbData], 0
0x180008a9c  xor     r8d, r8d; lpReserved
0x180008a9f  mov     [rsp+48h+lpData], rax; lpData
0x180008aa4  lea     rdx, aUpdatedsetting; "UpdatedSettings"
0x180008aab  mov     [rbp+Type], 4
0x180008ab2  call    cs:__imp_RegQueryValueExW
0x180008ab8  mov     ebx, eax
0x180008aba  test    eax, eax
0x180008abc  jz      short loc_180008ACF
0x180008abe  jle     short loc_180008AC9
0x180008ac0  movzx   ebx, ax
0x180008ac3  or      ebx, 80070000h
0x180008ac9  test    ebx, ebx
0x180008acb  jns     short loc_180008ADB
0x180008acd  jmp     short loc_180008B1A
0x180008acf  cmp     [rbp+cbData], 4
0x180008ad3  jnz     short loc_180008A57
0x180008ad5  cmp     [rbp+Type], 4
0x180008ad9  jnz     short loc_180008A67
0x180008adb  cmp     [rbp+Data], 0
0x180008adf  lea     rax, aSystemCurrentc_17; "SYSTEM\\CurrentControlSet\\Services\\UW"...
0x180008ae6  lea     r8, aSystemCurrentc_12; "SYSTEM\\CurrentControlSet\\Services\\UW"...
0x180008aed  mov     r9d, 0F003Fh; samDesired
0x180008af3  cmovnz  r8, rax; lpSubKey
0x180008af7  mov     rdx, rdi; hKey
0x180008afa  mov     rax, [r14+8]
0x180008afe  mov     rcx, r15; phkResult
0x180008b01  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180008b05  jz      short loc_180008B13
0x180008b07  mov     [rsp+48h+lpData], rax; HANDLE
0x180008b0c  call    ?OpenTransacted@CUwfRegKey@@QEAAJPEAUHKEY__@@PEBGKPEAX@Z; CUwfRegKey::OpenTransacted(HKEY__ *,ushort const *,ulong,void *)
0x180008b11  jmp     short loc_180008B18
0x180008b13  call    ?Open@CUwfRegKey@@QEAAJPEAUHKEY__@@PEBGK@Z; CUwfRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180008b18  mov     ebx, eax
0x180008b1a  lea     rcx, [rbp+hKey]; this
0x180008b1e  call    ?Close@CUwfRegKey@@QEAAJXZ; CUwfRegKey::Close(void)
0x180008b23  mov     eax, ebx
0x180008b25  add     rsp, 48h
0x180008b29  pop     r15
0x180008b2b  pop     r14
0x180008b2d  pop     r12
0x180008b2f  pop     rdi
0x180008b30  pop     rbx
0x180008b31  pop     rbp
0x180008b32  retn
```
