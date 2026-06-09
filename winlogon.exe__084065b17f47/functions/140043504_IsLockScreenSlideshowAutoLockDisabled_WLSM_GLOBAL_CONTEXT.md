# IsLockScreenSlideshowAutoLockDisabled(_WLSM_GLOBAL_CONTEXT *)

- ea: `0x140043504`
- end: `0x1400436ef`
- name: `?IsLockScreenSlideshowAutoLockDisabled@@YAHPEAU_WLSM_GLOBAL_CONTEXT@@@Z`
- size: `491`
- prototype: `__int64 __fastcall(struct _WLSM_GLOBAL_CONTEXT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14008d360`

## callees

- `0x1400155f0`
- `0x140043504`
- `0x140053720`
- `0x140065244`
- `0x1400827e4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140043599`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400435f8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140043599`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400435f8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400435be`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14004361d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400435be`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14004361d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400435ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004362d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400435ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004362d`

## pseudocode

```c
__int64 __fastcall IsLockScreenSlideshowAutoLockDisabled(
        struct _WLSM_GLOBAL_CONTEXT *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  int v4; // esi
  HKEY *v6; // rcx
  int v7; // edi
  int v8; // r14d
  int v9; // edx
  int v10; // eax
  unsigned int v11; // ebx
  DWORD lpcbData; // [rsp+28h] [rbp-48h]
  unsigned int v14; // [rsp+40h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-28h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-20h] BYREF
  BYTE Data[8]; // [rsp+58h] [rbp-18h] BYREF

  v4 = 0;
  v6 = (HKEY *)*((_QWORD *)a1 + 4);
  v7 = 0;
  v8 = 0;
  *(_QWORD *)Data = 0;
  hKey = 0;
  phkResult = 0;
  if ( v6 )
  {
    if ( !(unsigned int)CUser::RegQuerySZ(v6, a2, a3, a4, Data, lpcbData) )
    {
      v9 = *(unsigned __int16 *)Data - 48;
      if ( *(unsigned __int16 *)Data == 48 )
        v9 = *(unsigned __int16 *)&Data[2];
      if ( !v9 )
        v7 = 1;
    }
    if ( !RegOpenKeyExW(
            *(HKEY *)(*((_QWORD *)a1 + 4) + 232LL),
            L"Software\\Policies\\Microsoft\\Windows\\Control Panel\\Desktop",
            0,
            0x20019u,
            &hKey) )
    {
      LOBYTE(v8) = RegQueryValueExW(hKey, L"SCRNSAVE.EXE", 0, 0, 0, 0) == 0;
      RegCloseKey(hKey);
    }
    if ( !RegOpenKeyExW(*(HKEY *)(*((_QWORD *)a1 + 4) + 232LL), L"Control Panel\\Desktop", 0, 0x20019u, &phkResult) )
    {
      LOBYTE(v4) = RegQueryValueExW(phkResult, L"SCRNSAVE.EXE", 0, 0, 0, 0) == 0;
      RegCloseKey(phkResult);
    }
  }
  v14 = 0;
  if ( CMachine::RegQueryDWORD(
         (CMachine *)v6,
         L"Software\\Policies\\Microsoft\\Windows\\Personalization",
         L"NoLockScreenSlideshow",
         0,
         &v14)
    || v14 != 1 )
  {
    if ( v7 || (v10 = 0, !v8) && !v4 )
    {
      v11 = 0;
      v10 = 0;
      goto LABEL_19;
    }
  }
  else
  {
    v10 = 1;
  }
  v11 = 1;
LABEL_19:
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_lllll(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      103,
      WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids,
      v11,
      v10,
      v7,
      v8,
      v4);
  }
  return v11;
}

```

## disassembly

```asm
0x140043504  mov     [rsp-18h+arg_8], rbx
0x140043509  mov     [rsp-18h+arg_10], rsi
0x14004350e  push    rbp
0x14004350f  push    rdi
0x140043510  push    r14
0x140043512  mov     rbp, rsp
0x140043515  sub     rsp, 70h
0x140043519  mov     rax, cs:__security_cookie
0x140043520  xor     rax, rsp
0x140043523  mov     [rbp+var_10], rax
0x140043527  xor     esi, esi
0x140043529  mov     rbx, rcx
0x14004352c  mov     rcx, [rcx+20h]; this
0x140043530  xor     edi, edi
0x140043532  xor     r14d, r14d
0x140043535  mov     qword ptr [rbp+Data], rsi
0x140043539  mov     [rbp+hKey], rsi
0x14004353d  mov     [rbp+var_20], rsi
0x140043541  test    rcx, rcx
0x140043544  jz      loc_140043633
0x14004354a  lea     rax, [rbp+Data]
0x14004354e  mov     [rsp+70h+phkResult], rax; lpData
0x140043553  call    ?RegQuerySZ@CUser@@QEAAKPEBG00PEAGK@Z; CUser::RegQuerySZ(ushort const *,ushort const *,ushort const *,ushort *,ulong)
0x140043558  test    eax, eax
0x14004355a  jnz     short loc_140043575
0x14004355c  movzx   edx, word ptr [rbp+Data]
0x140043560  sub     edx, 30h ; '0'
0x140043563  jnz     short loc_14004356E
0x140043565  movzx   edx, word ptr [rbp+Data+2]
0x140043569  movzx   ecx, ax
0x14004356c  sub     edx, ecx
0x14004356e  test    edx, edx
0x140043570  jnz     short loc_140043575
0x140043572  lea     edi, [rdx+1]
0x140043575  mov     rcx, [rbx+20h]
0x140043579  lea     rax, [rbp+hKey]
0x14004357d  mov     r9d, 20019h; samDesired
0x140043583  mov     [rsp+70h+phkResult], rax; phkResult
0x140043588  xor     r8d, r8d; ulOptions
0x14004358b  lea     rdx, aSoftwarePolici_0; "Software\\Policies\\Microsoft\\Windows"...
0x140043592  mov     rcx, [rcx+0E8h]; hKey
0x140043599  call    cs:__imp_RegOpenKeyExW
0x14004359f  test    eax, eax
0x1400435a1  jnz     short loc_1400435D4
0x1400435a3  mov     rcx, [rbp+hKey]; hKey
0x1400435a7  lea     rdx, aScrnsaveExe; "SCRNSAVE.EXE"
0x1400435ae  mov     [rsp+70h+lpcbData], rsi; lpcbData
0x1400435b3  xor     r9d, r9d; lpType
0x1400435b6  xor     r8d, r8d; lpReserved
0x1400435b9  mov     [rsp+70h+phkResult], rsi; lpData
0x1400435be  call    cs:__imp_RegQueryValueExW
0x1400435c4  mov     rcx, [rbp+hKey]; hKey
0x1400435c8  test    eax, eax
0x1400435ca  setz    r14b
0x1400435ce  call    cs:__imp_RegCloseKey
0x1400435d4  mov     rcx, [rbx+20h]
0x1400435d8  lea     rax, [rbp+var_20]
0x1400435dc  mov     r9d, 20019h; samDesired
0x1400435e2  mov     [rsp+70h+phkResult], rax; phkResult
0x1400435e7  xor     r8d, r8d; ulOptions
0x1400435ea  lea     rdx, aControlPanelDe; "Control Panel\\Desktop"
0x1400435f1  mov     rcx, [rcx+0E8h]; hKey
0x1400435f8  call    cs:__imp_RegOpenKeyExW
0x1400435fe  test    eax, eax
0x140043600  jnz     short loc_140043633
0x140043602  mov     rcx, [rbp+var_20]; hKey
0x140043606  lea     rdx, aScrnsaveExe; "SCRNSAVE.EXE"
0x14004360d  mov     [rsp+70h+lpcbData], rsi; lpcbData
0x140043612  xor     r9d, r9d; lpType
0x140043615  xor     r8d, r8d; lpReserved
0x140043618  mov     [rsp+70h+phkResult], rsi; lpData
0x14004361d  call    cs:__imp_RegQueryValueExW
0x140043623  mov     rcx, [rbp+var_20]; hKey
0x140043627  test    eax, eax
0x140043629  setz    sil
0x14004362d  call    cs:__imp_RegCloseKey
0x140043633  lea     rax, [rbp+var_30]
0x140043637  mov     [rbp+var_30], 0
0x14004363e  xor     r9d, r9d; unsigned int
0x140043641  mov     [rsp+70h+phkResult], rax; unsigned int *
0x140043646  lea     r8, aNolockscreensl; "NoLockScreenSlideshow"
0x14004364d  lea     rdx, aSoftwarePolici_3; "Software\\Policies\\Microsoft\\Windows"...
0x140043654  call    ?RegQueryDWORD@CMachine@@QEAAKPEBG0KPEAK@Z; CMachine::RegQueryDWORD(ushort const *,ushort const *,ulong,ulong *)
0x140043659  test    eax, eax
0x14004365b  jnz     short loc_14004366A
0x14004365d  cmp     [rbp+var_30], 1
0x140043661  jnz     short loc_14004366A
0x140043663  mov     eax, 1
0x140043668  jmp     short loc_140043679
0x14004366a  test    edi, edi
0x14004366c  jnz     short loc_140043680
0x14004366e  xor     eax, eax
0x140043670  test    r14d, r14d
0x140043673  jnz     short loc_140043679
0x140043675  test    esi, esi
0x140043677  jz      short loc_140043680
0x140043679  mov     ebx, 1
0x14004367e  jmp     short loc_140043684
0x140043680  xor     ebx, ebx
0x140043682  xor     eax, eax
0x140043684  mov     rcx, cs:WPP_GLOBAL_Control
0x14004368b  lea     rdx, WPP_GLOBAL_Control
0x140043692  cmp     rcx, rdx
0x140043695  jz      short loc_1400436CC
0x140043697  test    byte ptr [rcx+1Ch], 1
0x14004369b  jz      short loc_1400436CC
0x14004369d  cmp     byte ptr [rcx+19h], 4
0x1400436a1  jb      short loc_1400436CC
0x1400436a3  mov     rcx, [rcx+10h]
0x1400436a7  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x1400436ae  mov     [rsp+70h+var_38], esi
0x1400436b2  mov     edx, 67h ; 'g'
0x1400436b7  mov     [rsp+70h+var_40], r14d
0x1400436bc  mov     r9d, ebx
0x1400436bf  mov     dword ptr [rsp+70h+lpcbData], edi
0x1400436c3  mov     dword ptr [rsp+70h+phkResult], eax
0x1400436c7  call    WPP_SF_lllll
0x1400436cc  mov     eax, ebx
0x1400436ce  mov     rcx, [rbp+var_10]
0x1400436d2  xor     rcx, rsp; StackCookie
0x1400436d5  call    __security_check_cookie
0x1400436da  lea     r11, [rsp+70h+var_s0]
0x1400436df  mov     rbx, [r11+28h]
0x1400436e3  mov     rsi, [r11+30h]
0x1400436e7  mov     rsp, r11
0x1400436ea  pop     r14
0x1400436ec  pop     rdi
0x1400436ed  pop     rbp
0x1400436ee  retn
```
