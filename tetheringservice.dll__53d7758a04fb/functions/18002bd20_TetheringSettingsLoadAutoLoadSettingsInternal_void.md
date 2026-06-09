# TetheringSettingsLoadAutoLoadSettingsInternal(void)

- ea: `0x18002bd20`
- end: `0x18002c02e`
- name: `?TetheringSettingsLoadAutoLoadSettingsInternal@@YAJXZ`
- size: `782`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task`

## callers

- `0x18001935c`

## callees

- `0x180003034`
- `0x18000304c`
- `0x180003058`
- `0x18000bf4c`
- `0x18000bf74`
- `0x18000ea08`
- `0x180013fb4`
- `0x180029aec`
- `0x18002bd20`
- `0x1800315f8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002be2b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002be6c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002be2b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002be6c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002bf2c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002bf2c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002bd97`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002bd97`

## pseudocode

```c
__int64 TetheringSettingsLoadAutoLoadSettingsInternal(void)
{
  unsigned __int16 near **PersistedTetheringSettingsRegKeyPath; // rax
  LSTATUS v1; // eax
  unsigned int v2; // ebx
  TetheringServiceTelemetry *v3; // rcx
  __int64 v4; // rdx
  __int64 v5; // r14
  unsigned __int64 v6; // rdi
  const WCHAR *v7; // rdx
  LSTATUS v8; // eax
  BYTE *v9; // rsi
  LSTATUS v10; // eax
  int v11; // eax
  struct _TETHERING_SETTING *v12; // rax
  DWORD cbData; // [rsp+70h] [rbp+40h] BYREF
  DWORD Type; // [rsp+78h] [rbp+48h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+50h] BYREF

  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_526e2569a9333f836f2472508a4e2fa1_Traceguids);
  }
  hKey = 0;
  cbData = 0;
  Type = 0;
  PersistedTetheringSettingsRegKeyPath = GetPersistedTetheringSettingsRegKeyPath();
  v1 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)PersistedTetheringSettingsRegKeyPath, 0, 0x20019u, &hKey);
  v2 = v1;
  if ( v1 )
  {
    if ( v1 > 0 )
      v2 = (unsigned __int16)v1 | 0x80070000;
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v4 = 11;
LABEL_10:
      WPP_SF_d(*((_QWORD *)v3 + 2), v4, &WPP_526e2569a9333f836f2472508a4e2fa1_Traceguids, v2);
    }
    goto LABEL_30;
  }
  v5 = 0;
  while ( 1 )
  {
    v6 = 48 * v5;
    if ( !*((_DWORD *)&g_rgTetheringSettingsGlobal + 12 * v5 + 3) )
      goto LABEL_28;
    v7 = *(const WCHAR **)((char *)&g_rgTetheringSettingsGlobal + v6);
    cbData = 0;
    v8 = RegQueryValueExW(hKey, v7, 0, &Type, 0, &cbData);
    v2 = v8;
    if ( v8 )
    {
      if ( v8 != 2 )
      {
        if ( v8 > 0 )
          v2 = (unsigned __int16)v8 | 0x80070000;
        if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            (unsigned int)&WPP_526e2569a9333f836f2472508a4e2fa1_Traceguids,
            (unsigned int)*(struct _TETHERING_SETTING near **)((char *)&g_rgTetheringSettingsGlobal + v6),
            v2);
        }
        goto LABEL_30;
      }
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          &WPP_526e2569a9333f836f2472508a4e2fa1_Traceguids,
          *(struct _TETHERING_SETTING near **)((char *)&g_rgTetheringSettingsGlobal + v6));
      }
      goto LABEL_25;
    }
    v9 = (BYTE *)o_malloc_0(cbData);
    if ( !v9 )
      break;
    v10 = RegQueryValueExW(hKey, *(LPCWSTR *)((char *)&g_rgTetheringSettingsGlobal + v6), 0, &Type, v9, &cbData);
    v2 = v10;
    if ( v10 )
    {
      if ( v10 > 0 )
        v2 = (unsigned __int16)v10 | 0x80070000;
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          (unsigned int)&WPP_526e2569a9333f836f2472508a4e2fa1_Traceguids,
          (unsigned int)*(struct _TETHERING_SETTING near **)((char *)&g_rgTetheringSettingsGlobal + v6),
          v2);
      }
      free(v9);
      goto LABEL_30;
    }
    v11 = *(_DWORD *)((char *)&g_rgTetheringSettingsGlobal + v6 + 8);
    if ( Type != v11 )
    {
      free(v9);
LABEL_25:
      v12 = *(struct _TETHERING_SETTING near **)((char *)&g_rgTetheringSettingsGlobal + v6 + 24);
      if ( *(_DWORD *)((char *)&g_rgTetheringSettingsGlobal + v6 + 8) == 1 )
        v12 = (struct _TETHERING_SETTING *)wcsdup(*(const wchar_t **)((char *)&g_rgTetheringSettingsGlobal + v6 + 24));
      *(struct _TETHERING_SETTING near **)((char *)&g_rgTetheringSettingsGlobal + v6 + 16) = v12;
      goto LABEL_28;
    }
    if ( ((v11 - 1) & 0xFFFFFFFD) != 0 )
    {
      memcpy_0(&qword_180041328[v6 / 8 + 1], v9, cbData);
      free(v9);
    }
    else
    {
      *(struct _TETHERING_SETTING near **)((char *)&g_rgTetheringSettingsGlobal + v6 + 16) = (struct _TETHERING_SETTING near *)v9;
    }
LABEL_28:
    v5 = (unsigned int)(v5 + 1);
    if ( (int)v5 >= 17 )
    {
      v2 = 0;
      g_fTetheringSettingsLoaded = 1;
      goto LABEL_30;
    }
  }
  v2 = -2147024882;
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v4 = 12;
    goto LABEL_10;
  }
LABEL_30:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_526e2569a9333f836f2472508a4e2fa1_Traceguids, v2);
  }
  return v2;
}

```

## disassembly

```asm
0x18002bd20  push    rbp
0x18002bd22  push    rbx
0x18002bd23  push    rsi
0x18002bd24  push    rdi
0x18002bd25  push    r12
0x18002bd27  push    r13
0x18002bd29  push    r14
0x18002bd2b  mov     rbp, rsp
0x18002bd2e  sub     rsp, 30h
0x18002bd32  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bd39  lea     r13, WPP_GLOBAL_Control
0x18002bd40  cmp     rcx, r13
0x18002bd43  jz      short loc_18002BD60
0x18002bd45  test    byte ptr [rcx+1Ch], 8
0x18002bd49  jz      short loc_18002BD60
0x18002bd4b  mov     rcx, [rcx+10h]
0x18002bd4f  lea     r8, WPP_526e2569a9333f836f2472508a4e2fa1_Traceguids
0x18002bd56  mov     edx, 0Ah
0x18002bd5b  call    WPP_SF_
0x18002bd60  mov     [rbp+hKey], 0
0x18002bd68  mov     [rbp+cbData], 0
0x18002bd6f  mov     [rbp+Type], 0
0x18002bd76  call    ?GetPersistedTetheringSettingsRegKeyPath@@YAPEAGXZ; GetPersistedTetheringSettingsRegKeyPath(void)
0x18002bd7b  mov     rdx, rax; lpSubKey
0x18002bd7e  mov     r9d, 20019h; samDesired
0x18002bd84  lea     rax, [rbp+hKey]
0x18002bd88  xor     r8d, r8d; ulOptions
0x18002bd8b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002bd92  mov     [rsp+30h+phkResult], rax; phkResult
0x18002bd97  call    cs:__imp_RegOpenKeyExW
0x18002bd9d  mov     ebx, eax
0x18002bd9f  test    eax, eax
0x18002bda1  jz      short loc_18002BDE5
0x18002bda3  jle     short loc_18002BDAE
0x18002bda5  movzx   ebx, ax
0x18002bda8  or      ebx, 80070000h
0x18002bdae  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bdb5  cmp     rcx, r13
0x18002bdb8  jz      loc_18002BF23
0x18002bdbe  test    byte ptr [rcx+1Ch], 1
0x18002bdc2  jz      loc_18002BF23
0x18002bdc8  mov     edx, 0Bh
0x18002bdcd  mov     rcx, [rcx+10h]
0x18002bdd1  lea     r8, WPP_526e2569a9333f836f2472508a4e2fa1_Traceguids
0x18002bdd8  mov     r9d, ebx
0x18002bddb  call    WPP_SF_d
0x18002bde0  jmp     loc_18002BF23
0x18002bde5  xor     r14d, r14d
0x18002bde8  lea     r12, ?g_rgTetheringSettingsGlobal@@3PAU_TETHERING_SETTING@@A; _TETHERING_SETTING near * g_rgTetheringSettingsGlobal
0x18002bdef  lea     rdi, [r14+r14*2]
0x18002bdf3  shl     rdi, 4
0x18002bdf7  cmp     dword ptr [rdi+r12+0Ch], 0
0x18002bdfd  jz      loc_18002BF0A
0x18002be03  mov     rdx, [rdi+r12]; lpValueName
0x18002be07  lea     rax, [rbp+cbData]
0x18002be0b  mov     rcx, [rbp+hKey]; hKey
0x18002be0f  lea     r9, [rbp+Type]; lpType
0x18002be13  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18002be18  xor     r8d, r8d; lpReserved
0x18002be1b  mov     [rsp+30h+phkResult], 0; lpData
0x18002be24  mov     [rbp+cbData], 0
0x18002be2b  call    cs:__imp_RegQueryValueExW
0x18002be31  mov     ebx, eax
0x18002be33  test    eax, eax
0x18002be35  jnz     loc_18002BEBE
0x18002be3b  mov     ecx, [rbp+cbData]; Size
0x18002be3e  call    _o_malloc_0
0x18002be43  mov     rsi, rax
0x18002be46  test    rax, rax
0x18002be49  jz      loc_18002BFBC
0x18002be4f  mov     rdx, [rdi+r12]; lpValueName
0x18002be53  lea     rax, [rbp+cbData]
0x18002be57  mov     rcx, [rbp+hKey]; hKey
0x18002be5b  lea     r9, [rbp+Type]; lpType
0x18002be5f  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18002be64  xor     r8d, r8d; lpReserved
0x18002be67  mov     [rsp+30h+phkResult], rsi; lpData
0x18002be6c  call    cs:__imp_RegQueryValueExW
0x18002be72  mov     ebx, eax
0x18002be74  test    eax, eax
0x18002be76  jnz     loc_18002BF75
0x18002be7c  mov     eax, [rdi+r12+8]
0x18002be81  cmp     [rbp+Type], eax
0x18002be84  jnz     short loc_18002BEB4
0x18002be86  dec     eax
0x18002be88  test    eax, 0FFFFFFFDh
0x18002be8d  jz      short loc_18002BEAD
0x18002be8f  mov     r8d, [rbp+cbData]; Size
0x18002be93  lea     rcx, [r12+10h]
0x18002be98  add     rcx, rdi; void *
0x18002be9b  mov     rdx, rsi; Src
0x18002be9e  call    memcpy_0
0x18002bea3  mov     rcx, rsi; Block
0x18002bea6  call    free
0x18002beab  jmp     short loc_18002BF0A
0x18002bead  mov     [rdi+r12+10h], rsi
0x18002beb2  jmp     short loc_18002BF0A
0x18002beb4  mov     rcx, rsi; Block
0x18002beb7  call    free
0x18002bebc  jmp     short loc_18002BEF0
0x18002bebe  cmp     eax, 2
0x18002bec1  jnz     loc_18002BFE5
0x18002bec7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bece  cmp     rcx, r13
0x18002bed1  jz      short loc_18002BEF0
0x18002bed3  test    byte ptr [rcx+1Ch], 8
0x18002bed7  jz      short loc_18002BEF0
0x18002bed9  mov     r9, [rdi+r12]
0x18002bedd  lea     edx, [rax+0Ch]
0x18002bee0  mov     rcx, [rcx+10h]
0x18002bee4  lea     r8, WPP_526e2569a9333f836f2472508a4e2fa1_Traceguids
0x18002beeb  call    WPP_SF_S
0x18002bef0  cmp     dword ptr [rdi+r12+8], 1
0x18002bef6  mov     rax, [rdi+r12+18h]
0x18002befb  jnz     short loc_18002BF05
0x18002befd  mov     rcx, rax; String
0x18002bf00  call    _wcsdup
0x18002bf05  mov     [rdi+r12+10h], rax
0x18002bf0a  inc     r14d
0x18002bf0d  cmp     r14d, 11h
0x18002bf11  jl      loc_18002BDEF
0x18002bf17  xor     ebx, ebx
0x18002bf19  mov     cs:?g_fTetheringSettingsLoaded@@3HA, 1; int g_fTetheringSettingsLoaded
0x18002bf23  mov     rcx, [rbp+hKey]; hKey
0x18002bf27  test    rcx, rcx
0x18002bf2a  jz      short loc_18002BF3A
0x18002bf2c  call    cs:__imp_RegCloseKey
0x18002bf32  mov     [rbp+hKey], 0
0x18002bf3a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bf41  cmp     rcx, r13
0x18002bf44  jz      short loc_18002BF64
0x18002bf46  test    byte ptr [rcx+1Ch], 8
0x18002bf4a  jz      short loc_18002BF64
0x18002bf4c  mov     rcx, [rcx+10h]
0x18002bf50  lea     r8, WPP_526e2569a9333f836f2472508a4e2fa1_Traceguids
0x18002bf57  mov     edx, 10h
0x18002bf5c  mov     r9d, ebx
0x18002bf5f  call    WPP_SF_d
0x18002bf64  mov     eax, ebx
0x18002bf66  add     rsp, 30h
0x18002bf6a  pop     r14
0x18002bf6c  pop     r13
0x18002bf6e  pop     r12
0x18002bf70  pop     rdi
0x18002bf71  pop     rsi
0x18002bf72  pop     rbx
0x18002bf73  pop     rbp
0x18002bf74  retn
0x18002bf75  jle     short loc_18002BF80
0x18002bf77  movzx   ebx, ax
0x18002bf7a  or      ebx, 80070000h
0x18002bf80  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bf87  cmp     rcx, r13
0x18002bf8a  jz      short loc_18002BFAF
0x18002bf8c  test    byte ptr [rcx+1Ch], 1
0x18002bf90  jz      short loc_18002BFAF
0x18002bf92  mov     r9, [rdi+r12]
0x18002bf96  lea     r8, WPP_526e2569a9333f836f2472508a4e2fa1_Traceguids
0x18002bf9d  mov     rcx, [rcx+10h]
0x18002bfa1  mov     edx, 0Dh
0x18002bfa6  mov     dword ptr [rsp+30h+phkResult], ebx
0x18002bfaa  call    WPP_SF_Sd
0x18002bfaf  mov     rcx, rsi; Block
0x18002bfb2  call    free
0x18002bfb7  jmp     loc_18002BF23
0x18002bfbc  mov     ebx, 8007000Eh
0x18002bfc1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bfc8  cmp     rcx, r13
0x18002bfcb  jz      loc_18002BF23
0x18002bfd1  test    byte ptr [rcx+1Ch], 1
0x18002bfd5  jz      loc_18002BF23
0x18002bfdb  mov     edx, 0Ch
0x18002bfe0  jmp     loc_18002BDCD
0x18002bfe5  test    eax, eax
0x18002bfe7  jle     short loc_18002BFF2
0x18002bfe9  movzx   ebx, ax
0x18002bfec  or      ebx, 80070000h
0x18002bff2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bff9  cmp     rcx, r13
0x18002bffc  jz      loc_18002BF23
0x18002c002  test    byte ptr [rcx+1Ch], 1
0x18002c006  jz      loc_18002BF23
0x18002c00c  mov     r9, [rdi+r12]
0x18002c010  lea     r8, WPP_526e2569a9333f836f2472508a4e2fa1_Traceguids
0x18002c017  mov     rcx, [rcx+10h]
0x18002c01b  mov     edx, 0Fh
0x18002c020  mov     dword ptr [rsp+30h+phkResult], ebx
0x18002c024  call    WPP_SF_Sd
0x18002c029  jmp     loc_18002BF23
```
