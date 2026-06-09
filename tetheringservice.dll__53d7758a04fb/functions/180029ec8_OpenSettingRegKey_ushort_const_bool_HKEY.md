# OpenSettingRegKey(ushort const *,bool,HKEY__ * *)

- ea: `0x180029ec8`
- end: `0x18002a29a`
- name: `?OpenSettingRegKey@@YAJPEBG_NPEAPEAUHKEY__@@@Z`
- size: `978`
- prototype: `__int64 __fastcall(const unsigned __int16 *, char, HKEY *)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, service_task`

## callers

- `0x18002ade8`
- `0x18002b2dc`
- `0x18002c0fc`

## callees

- `0x180002590`
- `0x180003088`
- `0x180009384`
- `0x1800094bc`
- `0x18000bf4c`
- `0x18000bf74`
- `0x18000ea08`
- `0x180013fb4`
- `0x180029aec`
- `0x180029ec8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a0af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a17c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a0af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a17c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a0c2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a18f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a0c2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a18f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a0ba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a140`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a187`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a0ba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a140`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a187`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002a1d4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002a1d4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a0ee`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a259`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a0ee`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a259`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall OpenSettingRegKey(const unsigned __int16 *a1, char a2, HKEY *a3)
{
  TetheringServiceTelemetry *v6; // rcx
  __int64 v7; // rbx
  unsigned __int16 near **PersistedTetheringSettingsRegKeyPath; // rax
  __int64 v9; // rdx
  unsigned __int16 *v10; // r8
  unsigned __int16 v11; // cx
  signed int v12; // ebx
  unsigned __int16 *v13; // rcx
  TetheringServiceTelemetry *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r9
  __int64 v17; // rax
  int v18; // eax
  DWORD LastError; // ebx
  LSTATUS v20; // eax
  HKEY v21; // rax
  DWORD v23; // ebx
  LSTATUS v24; // eax
  unsigned __int16 near **v25; // rax
  LSTATUS v26; // eax
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v29[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[264]; // [rsp+270h] [rbp+170h] BYREF

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_526e2569a9333f836f2472508a4e2fa1_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  hKey = 0;
  if ( a1 )
  {
    if ( v6 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
      WPP_SF_S(*((_QWORD *)v6 + 2), 20, &WPP_526e2569a9333f836f2472508a4e2fa1_Traceguids, a1);
    memset_0(v29, 0, 0x208u);
    v7 = 2147483646;
    PersistedTetheringSettingsRegKeyPath = GetPersistedTetheringSettingsRegKeyPath();
    v9 = 260;
    v10 = v29;
    do
    {
      if ( !v7 )
        break;
      v11 = *(_WORD *)PersistedTetheringSettingsRegKeyPath;
      if ( !*(_WORD *)PersistedTetheringSettingsRegKeyPath )
        break;
      PersistedTetheringSettingsRegKeyPath = (unsigned __int16 near **)((char *)PersistedTetheringSettingsRegKeyPath + 2);
      *v10++ = v11;
      --v7;
      --v9;
    }
    while ( v9 );
    v12 = v9 == 0 ? 0x8007007A : 0;
    v13 = v10 - 1;
    if ( v9 )
      v13 = v10;
    *v13 = 0;
    if ( !v9 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
        goto LABEL_41;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_38;
      v15 = 21;
      goto LABEL_18;
    }
    v17 = -1;
    do
      ++v17;
    while ( v29[v17] );
    v18 = StringCchCatW(v29, 260 - v17, L"\\%s");
    v12 = v18;
    if ( v18 < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
        goto LABEL_41;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_38;
      v15 = 22;
      goto LABEL_26;
    }
    v18 = StringCchPrintfW(SubKey, 0x104u, v29, a1);
    v12 = v18;
    if ( v18 < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
        goto LABEL_41;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_38;
      v15 = 23;
LABEL_26:
      v16 = (unsigned int)v18;
      goto LABEL_19;
    }
    if ( a2 )
    {
      if ( hKey )
      {
        LastError = GetLastError();
        RegCloseKey(hKey);
        SetLastError(LastError);
      }
      hKey = 0;
      v20 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey);
      v12 = v20;
      if ( v20 > 0 )
        v12 = (unsigned __int16)v20 | 0x80070000;
    }
    else
    {
      dwDisposition = 0;
      if ( hKey )
      {
        v23 = GetLastError();
        RegCloseKey(hKey);
        SetLastError(v23);
      }
      hKey = 0;
      v24 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x20006u, 0, &hKey, &dwDisposition);
      v12 = v24;
      if ( v24 > 0 )
        v12 = (unsigned __int16)v24 | 0x80070000;
      if ( v12 < 0 )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
          goto LABEL_41;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_38;
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          24,
          (unsigned int)&WPP_526e2569a9333f836f2472508a4e2fa1_Traceguids,
          (unsigned int)SubKey,
          v12);
        goto LABEL_37;
      }
    }
LABEL_36:
    v21 = hKey;
    hKey = 0;
    *a3 = v21;
    goto LABEL_37;
  }
  v25 = GetPersistedTetheringSettingsRegKeyPath();
  v26 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)v25, 0, a2 != 0 ? 131097 : 131078, &hKey);
  v12 = v26;
  if ( v26 > 0 )
    v12 = (unsigned __int16)v26 | 0x80070000;
  if ( v12 >= 0 )
    goto LABEL_36;
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
    goto LABEL_41;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v15 = 25;
LABEL_18:
    v16 = (unsigned int)v12;
LABEL_19:
    WPP_SF_d(*((_QWORD *)v14 + 2), v15, &WPP_526e2569a9333f836f2472508a4e2fa1_Traceguids, v16);
LABEL_37:
    v14 = WPP_GLOBAL_Control;
  }
LABEL_38:
  if ( v14 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)v14 + 2), 26, &WPP_526e2569a9333f836f2472508a4e2fa1_Traceguids, (unsigned int)v12);
LABEL_41:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180029ec8  mov     [rsp-8+arg_8], rbx
0x180029ecd  push    rbp
0x180029ece  push    rsi
0x180029ecf  push    rdi
0x180029ed0  push    r12
0x180029ed2  push    r13
0x180029ed4  push    r14
0x180029ed6  push    r15
0x180029ed8  lea     rbp, [rsp-390h]
0x180029ee0  sub     rsp, 490h
0x180029ee7  mov     rax, cs:__security_cookie
0x180029eee  xor     rax, rsp
0x180029ef1  mov     [rbp+3C0h+var_40], rax
0x180029ef8  mov     r14, r8
0x180029efb  mov     sil, dl
0x180029efe  mov     rdi, rcx
0x180029f01  lea     r12, WPP_GLOBAL_Control
0x180029f08  lea     r13, WPP_526e2569a9333f836f2472508a4e2fa1_Traceguids
0x180029f0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180029f16  cmp     rcx, r12
0x180029f19  jz      short loc_180029F39
0x180029f1b  test    byte ptr [rcx+1Ch], 8
0x180029f1f  jz      short loc_180029F39
0x180029f21  mov     edx, 13h
0x180029f26  mov     r8, r13
0x180029f29  mov     rcx, [rcx+10h]
0x180029f2d  call    WPP_SF_
0x180029f32  mov     rcx, cs:WPP_GLOBAL_Control
0x180029f39  xor     r15d, r15d
0x180029f3c  mov     [rsp+4C0h+hKey], r15
0x180029f41  test    rdi, rdi
0x180029f44  jz      loc_18002A22C
0x180029f4a  cmp     rcx, r12
0x180029f4d  jz      short loc_180029F68
0x180029f4f  test    byte ptr [rcx+1Ch], 8
0x180029f53  jz      short loc_180029F68
0x180029f55  lea     edx, [r15+14h]
0x180029f59  mov     r9, rdi
0x180029f5c  mov     r8, r13
0x180029f5f  mov     rcx, [rcx+10h]
0x180029f63  call    WPP_SF_S
0x180029f68  xor     edx, edx; Val
0x180029f6a  mov     r8d, 208h; Size
0x180029f70  lea     rcx, [rsp+4C0h+var_460]; void *
0x180029f75  call    memset_0
0x180029f7a  mov     ebx, 7FFFFFFEh
0x180029f7f  call    ?GetPersistedTetheringSettingsRegKeyPath@@YAPEAGXZ; GetPersistedTetheringSettingsRegKeyPath(void)
0x180029f84  mov     r9d, 104h
0x180029f8a  mov     edx, r9d
0x180029f8d  lea     r8, [rsp+4C0h+var_460]
0x180029f92  test    rbx, rbx
0x180029f95  jz      short loc_180029FB4
0x180029f97  movzx   ecx, word ptr [rax]
0x180029f9a  test    cx, cx
0x180029f9d  jz      short loc_180029FB4
0x180029f9f  add     rax, 2
0x180029fa3  mov     [r8], cx
0x180029fa7  add     r8, 2
0x180029fab  dec     rbx
0x180029fae  sub     rdx, 1
0x180029fb2  jnz     short loc_180029F92
0x180029fb4  mov     rax, rdx
0x180029fb7  neg     rax
0x180029fba  sbb     ebx, ebx
0x180029fbc  not     ebx
0x180029fbe  and     ebx, 8007007Ah
0x180029fc4  lea     rcx, [r8-2]
0x180029fc8  test    rdx, rdx
0x180029fcb  cmovnz  rcx, r8
0x180029fcf  mov     [rcx], r15w
0x180029fd3  jnz     short loc_18002A008
0x180029fd5  mov     rcx, cs:WPP_GLOBAL_Control
0x180029fdc  cmp     rcx, r12
0x180029fdf  jz      loc_18002A136
0x180029fe5  test    byte ptr [rcx+1Ch], 1
0x180029fe9  jz      loc_18002A117
0x180029fef  mov     edx, 15h
0x180029ff4  mov     r9d, ebx
0x180029ff7  mov     r8, r13
0x180029ffa  mov     rcx, [rcx+10h]
0x180029ffe  call    WPP_SF_d
0x18002a003  jmp     loc_18002A110
0x18002a008  lea     rcx, [rsp+4C0h+var_460]
0x18002a00d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002a011  inc     rax
0x18002a014  cmp     [rcx+rax*2], r15w
0x18002a019  jnz     short loc_18002A011
0x18002a01b  mov     rdx, r9
0x18002a01e  sub     rdx, rax; unsigned __int64
0x18002a021  lea     r8, aS; "\\%s"
0x18002a028  lea     rcx, [rsp+4C0h+var_460]; unsigned __int16 *
0x18002a02d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002a032  mov     ebx, eax
0x18002a034  test    eax, eax
0x18002a036  jns     short loc_18002A05C
0x18002a038  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a03f  cmp     rcx, r12
0x18002a042  jz      loc_18002A136
0x18002a048  test    byte ptr [rcx+1Ch], 1
0x18002a04c  jz      loc_18002A117
0x18002a052  mov     edx, 16h
0x18002a057  mov     r9d, eax
0x18002a05a  jmp     short loc_180029FF7
0x18002a05c  mov     r9, rdi
0x18002a05f  lea     r8, [rsp+4C0h+var_460]; unsigned __int16 *
0x18002a064  mov     edx, 104h; unsigned __int64
0x18002a069  lea     rcx, [rbp+3C0h+SubKey]; unsigned __int16 *
0x18002a070  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002a075  mov     ebx, eax
0x18002a077  test    eax, eax
0x18002a079  jns     short loc_18002A09C
0x18002a07b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a082  cmp     rcx, r12
0x18002a085  jz      loc_18002A136
0x18002a08b  test    byte ptr [rcx+1Ch], 1
0x18002a08f  jz      loc_18002A117
0x18002a095  mov     edx, 17h
0x18002a09a  jmp     short loc_18002A057
0x18002a09c  mov     rdi, [rsp+4C0h+hKey]
0x18002a0a1  test    sil, sil
0x18002a0a4  jz      loc_18002A172
0x18002a0aa  test    rdi, rdi
0x18002a0ad  jz      short loc_18002A0C8
0x18002a0af  call    cs:__imp_GetLastError
0x18002a0b5  mov     ebx, eax
0x18002a0b7  mov     rcx, rdi; hKey
0x18002a0ba  call    cs:__imp_RegCloseKey
0x18002a0c0  mov     ecx, ebx; dwErrCode
0x18002a0c2  call    cs:__imp_SetLastError
0x18002a0c8  mov     [rsp+4C0h+hKey], r15
0x18002a0cd  lea     rax, [rsp+4C0h+hKey]
0x18002a0d2  mov     [rsp+4C0h+phkResult], rax; phkResult
0x18002a0d7  mov     r9d, 20019h; samDesired
0x18002a0dd  xor     r8d, r8d; ulOptions
0x18002a0e0  lea     rdx, [rbp+3C0h+SubKey]; lpSubKey
0x18002a0e7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002a0ee  call    cs:__imp_RegOpenKeyExW
0x18002a0f4  mov     ebx, eax
0x18002a0f6  test    eax, eax
0x18002a0f8  jle     short loc_18002A103
0x18002a0fa  movzx   ebx, ax
0x18002a0fd  or      ebx, 80070000h
0x18002a103  mov     rax, [rsp+4C0h+hKey]
0x18002a108  mov     [rsp+4C0h+hKey], r15
0x18002a10d  mov     [r14], rax
0x18002a110  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a117  cmp     rcx, r12
0x18002a11a  jz      short loc_18002A136
0x18002a11c  test    byte ptr [rcx+1Ch], 8
0x18002a120  jz      short loc_18002A136
0x18002a122  mov     edx, 1Ah
0x18002a127  mov     r9d, ebx
0x18002a12a  mov     r8, r13
0x18002a12d  mov     rcx, [rcx+10h]
0x18002a131  call    WPP_SF_d
0x18002a136  mov     rcx, [rsp+4C0h+hKey]; hKey
0x18002a13b  test    rcx, rcx
0x18002a13e  jz      short loc_18002A146
0x18002a140  call    cs:__imp_RegCloseKey
0x18002a146  mov     eax, ebx
0x18002a148  mov     rcx, [rbp+3C0h+var_40]
0x18002a14f  xor     rcx, rsp; StackCookie
0x18002a152  call    __security_check_cookie
0x18002a157  mov     rbx, [rsp+4C0h+arg_8]
0x18002a15f  add     rsp, 490h
0x18002a166  pop     r15
0x18002a168  pop     r14
0x18002a16a  pop     r13
0x18002a16c  pop     r12
0x18002a16e  pop     rdi
0x18002a16f  pop     rsi
0x18002a170  pop     rbp
0x18002a171  retn
0x18002a172  mov     [rsp+4C0h+dwDisposition], r15d
0x18002a177  test    rdi, rdi
0x18002a17a  jz      short loc_18002A195
0x18002a17c  call    cs:__imp_GetLastError
0x18002a182  mov     ebx, eax
0x18002a184  mov     rcx, rdi; hKey
0x18002a187  call    cs:__imp_RegCloseKey
0x18002a18d  mov     ecx, ebx; dwErrCode
0x18002a18f  call    cs:__imp_SetLastError
0x18002a195  mov     [rsp+4C0h+hKey], r15
0x18002a19a  lea     rax, [rsp+4C0h+dwDisposition]
0x18002a19f  mov     [rsp+4C0h+lpdwDisposition], rax; lpdwDisposition
0x18002a1a4  lea     rax, [rsp+4C0h+hKey]
0x18002a1a9  mov     [rsp+4C0h+var_488], rax; phkResult
0x18002a1ae  mov     [rsp+4C0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18002a1b3  mov     [rsp+4C0h+samDesired], 20006h; samDesired
0x18002a1bb  mov     dword ptr [rsp+4C0h+phkResult], r15d; dwOptions
0x18002a1c0  xor     r9d, r9d; lpClass
0x18002a1c3  xor     r8d, r8d; Reserved
0x18002a1c6  lea     rdx, [rbp+3C0h+SubKey]; lpSubKey
0x18002a1cd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002a1d4  call    cs:__imp_RegCreateKeyExW
0x18002a1da  mov     ebx, eax
0x18002a1dc  test    eax, eax
0x18002a1de  jle     short loc_18002A1E9
0x18002a1e0  movzx   ebx, ax
0x18002a1e3  or      ebx, 80070000h
0x18002a1e9  test    ebx, ebx
0x18002a1eb  jns     loc_18002A103
0x18002a1f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a1f8  cmp     rcx, r12
0x18002a1fb  jz      loc_18002A136
0x18002a201  test    byte ptr [rcx+1Ch], 1
0x18002a205  jz      loc_18002A117
0x18002a20b  mov     edx, 18h
0x18002a210  mov     dword ptr [rsp+4C0h+phkResult], ebx
0x18002a214  lea     r9, [rbp+3C0h+SubKey]
0x18002a21b  mov     r8, r13
0x18002a21e  mov     rcx, [rcx+10h]
0x18002a222  call    WPP_SF_Sd
0x18002a227  jmp     loc_18002A110
0x18002a22c  call    ?GetPersistedTetheringSettingsRegKeyPath@@YAPEAGXZ; GetPersistedTetheringSettingsRegKeyPath(void)
0x18002a231  neg     sil
0x18002a234  sbb     r9d, r9d
0x18002a237  and     r9d, 13h
0x18002a23b  add     r9d, 20006h; samDesired
0x18002a242  lea     rcx, [rsp+4C0h+hKey]
0x18002a247  mov     [rsp+4C0h+phkResult], rcx; phkResult
0x18002a24c  xor     r8d, r8d; ulOptions
0x18002a24f  mov     rdx, rax; lpSubKey
0x18002a252  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002a259  call    cs:__imp_RegOpenKeyExW
0x18002a25f  mov     ebx, eax
0x18002a261  test    eax, eax
0x18002a263  jle     short loc_18002A26E
0x18002a265  movzx   ebx, ax
0x18002a268  or      ebx, 80070000h
0x18002a26e  test    ebx, ebx
0x18002a270  jns     loc_18002A103
0x18002a276  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a27d  cmp     rcx, r12
0x18002a280  jz      loc_18002A136
0x18002a286  test    byte ptr [rcx+1Ch], 1
0x18002a28a  jz      loc_18002A117
0x18002a290  mov     edx, 19h
0x18002a295  jmp     loc_180029FF4
```
