# CUwfManagement::set_HORMEnabled(bool)

- ea: `0x180017230`
- end: `0x1800174ed`
- name: `?set_HORMEnabled@CUwfManagement@@QEAAJ_N@Z`
- size: `701`
- prototype: `__int64 __fastcall(CUwfManagement *this, char)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180019d70`

## callees

- `0x180006200`
- `0x180008170`
- `0x18000aed0`
- `0x18000afb0`
- `0x18000c030`
- `0x180012430`
- `0x1800149d0`
- `0x180014a90`
- `0x180014d30`
- `0x180015af0`
- `0x180016a74`
- `0x180017230`

## import_xrefs

- `ntdll!NtCommitTransaction` at `0x180017292`
- `ntdll!NtCommitTransaction` at `0x180017292`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800172eb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800173a1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800172eb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800173a1`

## pseudocode

```c
__int64 __fastcall CUwfManagement::set_HORMEnabled(CUwfManagement *this, char a2)
{
  char v4; // r12
  int OverlayFlags; // ebx
  __int64 v6; // rdx
  __int64 v7; // rcx
  HKEY v9; // rcx
  LSTATUS v10; // eax
  HKEY v11; // rcx
  LSTATUS v12; // eax
  CUwfManagement *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rdx
  DWORD Type; // [rsp+70h] [rbp+40h] BYREF
  DWORD cbData; // [rsp+80h] [rbp+50h] BYREF
  int Data; // [rsp+88h] [rbp+58h] BYREF

  v4 = 0;
  if ( !*((_BYTE *)this + 9) )
  {
LABEL_2:
    OverlayFlags = -2147023091;
LABEL_3:
    *((_DWORD *)this + 3) = OverlayFlags;
    if ( v4 )
      CUwfConfiguration::Initialize((CUwfManagement *)((char *)this + 80), (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    CUwfConfiguration::set_HORMEnabled((CUwfManagement *)((char *)this + 80), a2 ^ 1, 1);
    v7 = *((_QWORD *)this + 2);
    if ( v7 != -1 )
    {
      LOBYTE(v6) = 1;
      NtCommitTransaction(v7, v6);
    }
    goto LABEL_7;
  }
  v9 = (HKEY)*((_QWORD *)this + 13);
  Data = 0;
  Type = 0;
  cbData = 4;
  v10 = RegQueryValueExW(v9, L"HormEnabled", 0, &Type, (LPBYTE)&Data, &cbData);
  OverlayFlags = v10;
  if ( v10 )
  {
    if ( v10 > 0 )
      OverlayFlags = (unsigned __int16)v10 | 0x80070000;
    if ( OverlayFlags < 0 )
      goto LABEL_3;
  }
  else
  {
    if ( Type != 4 )
      goto LABEL_15;
    OverlayFlags = 0;
    if ( cbData != 4 )
      goto LABEL_29;
  }
  if ( !a2 )
  {
    if ( !Data )
      return (unsigned int)OverlayFlags;
    OverlayFlags = CUwfVolumeDevice::set_HORMEnabled((CUwfManagement *)((char *)this + 24), 0);
    if ( OverlayFlags < 0 )
      goto LABEL_3;
    OverlayFlags = CUwfConfiguration::set_HORMEnabled((CUwfManagement *)((char *)this + 80), 0, 1);
    if ( OverlayFlags < 0 )
      goto LABEL_3;
    OverlayFlags = CUwfManagement::Finalize(this, v15);
    if ( OverlayFlags < 0 )
      goto LABEL_3;
    CUwfConfiguration::Close((CUwfManagement *)((char *)this + 80));
    goto LABEL_7;
  }
  if ( Data )
    return (unsigned int)OverlayFlags;
  if ( !HiberFileExists() )
    goto LABEL_2;
  Type = 0;
  OverlayFlags = CUwfStaticConfiguration::get_OverlayFlags((CUwfManagement *)((char *)this + 120), &Type);
  if ( OverlayFlags < 0 )
    goto LABEL_3;
  if ( Type != 4 )
    goto LABEL_2;
  v11 = (HKEY)*((_QWORD *)this + 17);
  Data = 0;
  Type = 0;
  cbData = 4;
  v12 = RegQueryValueExW(v11, L"UWFEnabled", 0, &Type, (LPBYTE)&Data, &cbData);
  OverlayFlags = v12;
  if ( !v12 )
  {
    if ( Type == 4 )
    {
      if ( cbData == 4 )
        goto LABEL_30;
LABEL_29:
      OverlayFlags = -2147024883;
      goto LABEL_3;
    }
LABEL_15:
    OverlayFlags = -2147023267;
    goto LABEL_3;
  }
  if ( v12 > 0 )
    OverlayFlags = (unsigned __int16)v12 | 0x80070000;
  if ( OverlayFlags < 0 )
    goto LABEL_3;
LABEL_30:
  if ( !Data )
    goto LABEL_2;
  Type = 0;
  OverlayFlags = CUwfStaticConfiguration::get_OverlayType(
                   (CUwfManagement *)((char *)this + 120),
                   (enum _UWF_CONFIG_OVERLAY_TYPE *)&Type);
  if ( OverlayFlags < 0 )
    goto LABEL_3;
  if ( Type )
    goto LABEL_2;
  LOBYTE(Type) = 0;
  OverlayFlags = CUwfManagement::get_AllFixedMountedVolumesProtected(v13, (bool *)&Type);
  if ( OverlayFlags < 0 )
    goto LABEL_3;
  if ( !(_BYTE)Type )
    goto LABEL_2;
  OverlayFlags = CUwfVolumeDevice::set_RomModeDisposition((char *)this + 24, 2);
  if ( OverlayFlags < 0 )
    goto LABEL_3;
  OverlayFlags = CUwfConfiguration::set_HORMEnabled((CUwfManagement *)((char *)this + 80), 1u, 1);
  if ( OverlayFlags < 0 )
    goto LABEL_3;
  OverlayFlags = CUwfManagement::Finalize(this, v14);
  if ( OverlayFlags < 0 )
    goto LABEL_3;
  v4 = 1;
  CUwfConfiguration::Close((CUwfManagement *)((char *)this + 80));
  OverlayFlags = CUwfVolumeDevice::set_HORMEnabled((CUwfManagement *)((char *)this + 24), 1);
  if ( OverlayFlags < 0 )
    goto LABEL_3;
LABEL_7:
  CUwfManagement::Close(this);
  return (unsigned int)OverlayFlags;
}

```

## disassembly

```asm
0x180017230  mov     [rsp-38h+arg_8], rbx
0x180017235  push    rbp
0x180017236  push    rsi
0x180017237  push    rdi
0x180017238  push    r12
0x18001723a  push    r13
0x18001723c  push    r14
0x18001723e  push    r15
0x180017240  mov     rbp, rsp
0x180017243  sub     rsp, 30h
0x180017247  xor     r13d, r13d
0x18001724a  mov     r15b, dl
0x18001724d  mov     rdi, rcx
0x180017250  mov     r12b, r13b
0x180017253  cmp     [rcx+9], r13b
0x180017257  jnz     short loc_1800172B7
0x180017259  mov     ebx, 8007070Dh
0x18001725e  mov     [rdi+0Ch], ebx
0x180017261  test    r12b, r12b
0x180017264  jz      short loc_180017273
0x180017266  or      rdx, 0FFFFFFFFFFFFFFFFh; HANDLE
0x18001726a  lea     rcx, [rdi+50h]; this
0x18001726e  call    ?Initialize@CUwfConfiguration@@QEAAJPEAX@Z; CUwfConfiguration::Initialize(void *)
0x180017273  xor     r15b, 1
0x180017277  lea     rcx, [rdi+50h]; this
0x18001727b  mov     dl, r15b; bool
0x18001727e  mov     r8b, 1; bool
0x180017281  call    ?set_HORMEnabled@CUwfConfiguration@@QEAAJ_N0@Z; CUwfConfiguration::set_HORMEnabled(bool,bool)
0x180017286  mov     rcx, [rdi+10h]
0x18001728a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001728e  jz      short loc_180017298
0x180017290  mov     dl, 1
0x180017292  call    cs:__imp_NtCommitTransaction
0x180017298  mov     rcx, rdi; this
0x18001729b  call    ?Close@CUwfManagement@@QEAAXXZ; CUwfManagement::Close(void)
0x1800172a0  mov     eax, ebx
0x1800172a2  mov     rbx, [rsp+30h+arg_8]
0x1800172a7  add     rsp, 30h
0x1800172ab  pop     r15
0x1800172ad  pop     r14
0x1800172af  pop     r13
0x1800172b1  pop     r12
0x1800172b3  pop     rdi
0x1800172b4  pop     rsi
0x1800172b5  pop     rbp
0x1800172b6  retn
0x1800172b7  mov     rcx, [rcx+68h]; hKey
0x1800172bb  lea     rax, [rbp+cbData]
0x1800172bf  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800172c4  lea     r9, [rbp+Type]; lpType
0x1800172c8  lea     rax, [rbp+Data]
0x1800172cc  mov     [rbp+Data], r13d
0x1800172d0  mov     esi, 4
0x1800172d5  mov     [rsp+30h+lpData], rax; lpData
0x1800172da  xor     r8d, r8d; lpReserved
0x1800172dd  mov     [rbp+Type], r13d
0x1800172e1  lea     rdx, aHormenabled; "HormEnabled"
0x1800172e8  mov     [rbp+cbData], esi
0x1800172eb  call    cs:__imp_RegQueryValueExW
0x1800172f1  mov     ebx, eax
0x1800172f3  test    eax, eax
0x1800172f5  jz      short loc_18001730B
0x1800172f7  jle     short loc_180017302
0x1800172f9  movzx   ebx, ax
0x1800172fc  or      ebx, 80070000h
0x180017302  test    ebx, ebx
0x180017304  jns     short loc_180017326
0x180017306  jmp     loc_18001725E
0x18001730b  cmp     [rbp+Type], esi
0x18001730e  jz      short loc_18001731A
0x180017310  mov     ebx, 8007065Dh
0x180017315  jmp     loc_18001725E
0x18001731a  mov     ebx, r13d
0x18001731d  cmp     [rbp+cbData], esi
0x180017320  jnz     loc_1800173CF
0x180017326  cmp     [rbp+Data], r13d
0x18001732a  setnz   al
0x18001732d  test    r15b, r15b
0x180017330  jz      loc_180017498
0x180017336  test    al, al
0x180017338  jnz     loc_1800172A0
0x18001733e  call    ?HiberFileExists@@YA_NXZ; HiberFileExists(void)
0x180017343  test    al, al
0x180017345  jz      loc_180017259
0x18001734b  lea     rcx, [rdi+78h]; this
0x18001734f  mov     [rbp+Type], r13d
0x180017353  lea     rdx, [rbp+Type]; unsigned int *
0x180017357  call    ?get_OverlayFlags@CUwfStaticConfiguration@@QEAAJPEAK@Z; CUwfStaticConfiguration::get_OverlayFlags(ulong *)
0x18001735c  mov     ebx, eax
0x18001735e  test    eax, eax
0x180017360  js      loc_18001725E
0x180017366  cmp     [rbp+Type], esi
0x180017369  jnz     loc_180017259
0x18001736f  mov     rcx, [rdi+88h]; hKey
0x180017376  lea     rax, [rbp+cbData]
0x18001737a  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18001737f  lea     r9, [rbp+Type]; lpType
0x180017383  lea     rax, [rbp+Data]
0x180017387  mov     [rbp+Data], r13d
0x18001738b  xor     r8d, r8d; lpReserved
0x18001738e  mov     [rsp+30h+lpData], rax; lpData
0x180017393  lea     rdx, aUwfenabled; "UWFEnabled"
0x18001739a  mov     [rbp+Type], r13d
0x18001739e  mov     [rbp+cbData], esi
0x1800173a1  call    cs:__imp_RegQueryValueExW
0x1800173a7  mov     ebx, eax
0x1800173a9  test    eax, eax
0x1800173ab  jz      short loc_1800173C1
0x1800173ad  jle     short loc_1800173B8
0x1800173af  movzx   ebx, ax
0x1800173b2  or      ebx, 80070000h
0x1800173b8  test    ebx, ebx
0x1800173ba  jns     short loc_1800173D9
0x1800173bc  jmp     loc_18001725E
0x1800173c1  cmp     [rbp+Type], esi
0x1800173c4  jnz     loc_180017310
0x1800173ca  cmp     [rbp+cbData], esi
0x1800173cd  jz      short loc_1800173D9
0x1800173cf  mov     ebx, 8007000Dh
0x1800173d4  jmp     loc_18001725E
0x1800173d9  cmp     [rbp+Data], r13d
0x1800173dd  setnz   al
0x1800173e0  test    al, al
0x1800173e2  jz      loc_180017259
0x1800173e8  lea     rcx, [rdi+78h]; this
0x1800173ec  mov     [rbp+Type], r13d
0x1800173f0  lea     rdx, [rbp+Type]; enum _UWF_CONFIG_OVERLAY_TYPE *
0x1800173f4  call    ?get_OverlayType@CUwfStaticConfiguration@@QEAAJPEAW4_UWF_CONFIG_OVERLAY_TYPE@@@Z; CUwfStaticConfiguration::get_OverlayType(_UWF_CONFIG_OVERLAY_TYPE *)
0x1800173f9  mov     ebx, eax
0x1800173fb  test    eax, eax
0x1800173fd  js      loc_18001725E
0x180017403  cmp     [rbp+Type], r13d
0x180017407  jnz     loc_180017259
0x18001740d  lea     rdx, [rbp+Type]; bool *
0x180017411  mov     byte ptr [rbp+Type], r13b
0x180017415  call    ?get_AllFixedMountedVolumesProtected@CUwfManagement@@AEAAJPEA_N@Z; CUwfManagement::get_AllFixedMountedVolumesProtected(bool *)
0x18001741a  mov     ebx, eax
0x18001741c  test    eax, eax
0x18001741e  js      loc_18001725E
0x180017424  cmp     byte ptr [rbp+Type], r13b
0x180017428  jz      loc_180017259
0x18001742e  mov     edx, 2
0x180017433  lea     rcx, [rdi+18h]
0x180017437  call    ?set_RomModeDisposition@CUwfVolumeDevice@@QEAAJW4_UWFVOL_ROM_MODE_DISPOSITION@@@Z; CUwfVolumeDevice::set_RomModeDisposition(_UWFVOL_ROM_MODE_DISPOSITION)
0x18001743c  mov     ebx, eax
0x18001743e  test    eax, eax
0x180017440  js      loc_18001725E
0x180017446  mov     r8b, 1; bool
0x180017449  lea     rcx, [rdi+50h]; this
0x18001744d  mov     dl, r8b; bool
0x180017450  call    ?set_HORMEnabled@CUwfConfiguration@@QEAAJ_N0@Z; CUwfConfiguration::set_HORMEnabled(bool,bool)
0x180017455  mov     ebx, eax
0x180017457  test    eax, eax
0x180017459  js      loc_18001725E
0x18001745f  mov     rcx, rdi; this
0x180017462  call    ?Finalize@CUwfManagement@@QEAAJXZ; CUwfManagement::Finalize(void)
0x180017467  mov     ebx, eax
0x180017469  test    eax, eax
0x18001746b  js      loc_18001725E
0x180017471  lea     rcx, [rdi+50h]; this
0x180017475  mov     r12b, 1
0x180017478  call    ?Close@CUwfConfiguration@@QEAAXXZ; CUwfConfiguration::Close(void)
0x18001747d  mov     dl, r12b; bool
0x180017480  lea     rcx, [rdi+18h]; this
0x180017484  call    ?set_HORMEnabled@CUwfVolumeDevice@@QEAAJ_N@Z; CUwfVolumeDevice::set_HORMEnabled(bool)
0x180017489  mov     ebx, eax
0x18001748b  test    eax, eax
0x18001748d  js      loc_18001725E
0x180017493  jmp     loc_180017298
0x180017498  test    al, al
0x18001749a  jz      loc_1800172A0
0x1800174a0  lea     rcx, [rdi+18h]; this
0x1800174a4  xor     edx, edx; bool
0x1800174a6  call    ?set_HORMEnabled@CUwfVolumeDevice@@QEAAJ_N@Z; CUwfVolumeDevice::set_HORMEnabled(bool)
0x1800174ab  mov     ebx, eax
0x1800174ad  test    eax, eax
0x1800174af  js      loc_18001725E
0x1800174b5  mov     r8b, 1; bool
0x1800174b8  lea     rcx, [rdi+50h]; this
0x1800174bc  xor     edx, edx; bool
0x1800174be  call    ?set_HORMEnabled@CUwfConfiguration@@QEAAJ_N0@Z; CUwfConfiguration::set_HORMEnabled(bool,bool)
0x1800174c3  mov     ebx, eax
0x1800174c5  test    eax, eax
0x1800174c7  js      loc_18001725E
0x1800174cd  mov     rcx, rdi; this
0x1800174d0  call    ?Finalize@CUwfManagement@@QEAAJXZ; CUwfManagement::Finalize(void)
0x1800174d5  mov     ebx, eax
0x1800174d7  test    eax, eax
0x1800174d9  js      loc_18001725E
0x1800174df  lea     rcx, [rdi+50h]; this
0x1800174e3  call    ?Close@CUwfConfiguration@@QEAAXXZ; CUwfConfiguration::Close(void)
0x1800174e8  jmp     loc_180017298
```
