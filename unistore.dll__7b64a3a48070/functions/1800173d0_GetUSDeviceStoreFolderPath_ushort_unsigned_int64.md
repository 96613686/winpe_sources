# GetUSDeviceStoreFolderPath(ushort *,unsigned __int64)

- ea: `0x1800173d0`
- end: `0x1800175ac`
- name: `?GetUSDeviceStoreFolderPath@@YAJPEAG_K@Z`
- size: `476`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x1800132ac`
- `0x180017240`
- `0x180018804`
- `0x18007bb60`

## callees

- `0x1800173d0`
- `0x18001784c`
- `0x1800178c0`
- `0x180071e60`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18001752d`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18001752d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001754b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017553`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001754b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017553`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180017423`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180017423`

## string_xrefs

- `0x180017437`: `Comms`

## pseudocode

```c
__int64 __fastcall GetUSDeviceStoreFolderPath(unsigned __int16 *a1, unsigned __int64 a2, __int64 a3)
{
  unsigned int v5; // edi
  __int64 v6; // r8
  HRESULT v7; // eax
  __int64 v8; // r9
  __int64 v9; // r9
  int v11; // ebx
  int v12; // eax
  unsigned __int16 *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  __int64 v16; // rdx
  unsigned __int64 i; // rsi
  PCWSTR pszMore[11]; // [rsp+30h] [rbp-58h]
  LPVOID pv; // [rsp+90h] [rbp+8h] BYREF

  if ( !a1 )
  {
    v15 = 119;
    goto LABEL_28;
  }
  if ( !a2 )
  {
    v15 = 120;
LABEL_28:
    v16 = 0;
LABEL_29:
    v11 = -2147024809;
    goto LABEL_30;
  }
  if ( g_unistorePathReplace )
  {
    v12 = StringCchCopyW(a1, a2, &g_unistorePathReplace);
    v5 = v12;
    if ( v12 < 0 )
    {
      Log_UnistoreHREvent_16((unsigned int)v12, 1, a3, 124);
      return v5;
    }
  }
  else
  {
    pv = 0;
    v5 = SHGetKnownFolderPath(&rfid, 0x4000u, 0, (PWSTR *)&pv);
    if ( (v5 & 0x80000000) != 0 )
    {
      v9 = 137;
LABEL_9:
      Log_UnistoreHREvent_16(v5, 1, v6, v9);
      if ( pv )
        CoTaskMemFree(pv);
      return v5;
    }
    pszMore[1] = L"Comms";
    pszMore[0] = (PCWSTR)pv;
    pszMore[2] = L"UnistoreDB";
    v7 = StringCchCopyW(a1, a2, (const unsigned __int16 *)pv);
    v5 = v7;
    if ( v7 < 0 )
    {
      v8 = 33;
LABEL_7:
      Log_UnistoreHREvent_16((unsigned int)v7, 1, a3, v8);
      v9 = 146;
      goto LABEL_9;
    }
    for ( i = 1; i < 3; ++i )
    {
      v7 = PathCchCombine(a1, a2, a1, pszMore[i]);
      v5 = v7;
      if ( v7 < 0 )
      {
        v8 = 37;
        goto LABEL_7;
      }
    }
    if ( pv )
      CoTaskMemFree(pv);
  }
  v13 = a1;
  v14 = 0x7FFFFFFF;
  while ( *v13 )
  {
    ++v13;
    if ( !--v14 )
    {
      v15 = 150;
      v16 = 1;
      goto LABEL_29;
    }
  }
  if ( 0x7FFFFFFF != v14 && a1[0x7FFFFFFF - v14 - 1] == 92 )
    return 0;
  v11 = StringCchCatW(a1, a2, L"\\");
  if ( v11 >= 0 )
    return 0;
  v15 = 153;
  v16 = 1;
LABEL_30:
  Log_UnistoreHREvent_16((unsigned int)v11, v16, a3, v15);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800173d0  mov     rax, rsp
0x1800173d3  push    rbx
0x1800173d4  push    rbp
0x1800173d5  push    rsi
0x1800173d6  push    rdi
0x1800173d7  push    r14
0x1800173d9  push    r15
0x1800173db  sub     rsp, 58h
0x1800173df  xor     r14d, r14d
0x1800173e2  mov     rbp, rdx
0x1800173e5  mov     rbx, rcx
0x1800173e8  test    rcx, rcx
0x1800173eb  jz      loc_18001755E
0x1800173f1  test    rdx, rdx
0x1800173f4  jz      loc_180017584
0x1800173fa  cmp     cs:?g_unistorePathReplace@@3PAGA, r14w; ushort near * g_unistorePathReplace
0x180017402  lea     r15d, [r14+1]
0x180017406  jnz     loc_1800174DC
0x18001740c  lea     r9, [rax+8]; ppszPath
0x180017410  mov     [rax+8], r14
0x180017414  xor     r8d, r8d; hToken
0x180017417  lea     rcx, rfid; rfid
0x18001741e  mov     edx, 4000h; dwFlags
0x180017423  call    cs:__imp_SHGetKnownFolderPath
0x180017429  mov     edi, eax
0x18001742b  test    eax, eax
0x18001742d  js      short loc_18001747F
0x18001742f  mov     r8, [rsp+88h+pv]; unsigned __int16 *
0x180017437  lea     rax, ?gc_szCommsFolderName@@3QBGB; "Comms"
0x18001743e  mov     [rsp+88h+var_50], rax
0x180017443  mov     rdx, rbp; unsigned __int64
0x180017446  lea     rax, ?gc_szUSStoreVolumeFolderName@@3QBGB; "UnistoreDB"
0x18001744d  mov     [rsp+88h+pszMore], r8
0x180017452  mov     rcx, rbx; unsigned __int16 *
0x180017455  mov     [rsp+88h+var_48], rax
0x18001745a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001745f  mov     edi, eax
0x180017461  test    eax, eax
0x180017463  jns     loc_180017516
0x180017469  lea     r9d, [r14+21h]
0x18001746d  mov     edx, r15d
0x180017470  mov     ecx, eax
0x180017472  call    Log_UnistoreHREvent_16
0x180017477  mov     r9d, 92h
0x18001747d  jmp     short loc_180017485
0x18001747f  mov     r9d, 89h
0x180017485  mov     edx, r15d
0x180017488  mov     ecx, edi
0x18001748a  call    Log_UnistoreHREvent_16
0x18001748f  mov     rcx, [rsp+88h+pv]; pv
0x180017497  test    rcx, rcx
0x18001749a  jnz     loc_180017553
0x1800174a0  mov     eax, edi
0x1800174a2  jmp     short loc_1800174CF
0x1800174a4  sub     rax, rdx
0x1800174a7  jz      short loc_1800174B1
0x1800174a9  cmp     word ptr [rbx+rax*2-2], 5Ch ; '\'
0x1800174af  jz      short loc_1800174CD
0x1800174b1  lea     r8, asc_1800DB900; "\\"
0x1800174b8  mov     rdx, rbp; unsigned __int64
0x1800174bb  mov     rcx, rbx; unsigned __int16 *
0x1800174be  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800174c3  mov     ebx, eax
0x1800174c5  test    eax, eax
0x1800174c7  js      loc_180017579
0x1800174cd  xor     eax, eax
0x1800174cf  add     rsp, 58h
0x1800174d3  pop     r15
0x1800174d5  pop     r14
0x1800174d7  pop     rdi
0x1800174d8  pop     rsi
0x1800174d9  pop     rbp
0x1800174da  pop     rbx
0x1800174db  retn
0x1800174dc  lea     r8, ?g_unistorePathReplace@@3PAGA; unsigned __int16 *
0x1800174e3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800174e8  mov     edi, eax
0x1800174ea  test    eax, eax
0x1800174ec  js      loc_18001758C
0x1800174f2  mov     eax, 7FFFFFFFh
0x1800174f7  mov     rcx, rbx
0x1800174fa  mov     edx, eax
0x1800174fc  cmp     [rcx], r14w
0x180017500  jz      short loc_1800174A4
0x180017502  add     rcx, 2
0x180017506  sub     rdx, r15
0x180017509  jnz     short loc_1800174FC
0x18001750b  mov     r9d, 96h
0x180017511  mov     edx, r15d
0x180017514  jmp     short loc_180017566
0x180017516  mov     rsi, r15
0x180017519  cmp     rsi, 3
0x18001751d  jnb     short loc_18001753E
0x18001751f  mov     r9, [rsp+rsi*8+88h+pszMore]; pszMore
0x180017524  mov     r8, rbx; pszPathIn
0x180017527  mov     rdx, rbp; cchPathOut
0x18001752a  mov     rcx, rbx; pszPathOut
0x18001752d  call    cs:__imp_PathCchCombine
0x180017533  mov     edi, eax
0x180017535  test    eax, eax
0x180017537  js      short loc_1800175A1
0x180017539  add     rsi, r15
0x18001753c  jmp     short loc_180017519
0x18001753e  mov     rcx, [rsp+88h+pv]; pv
0x180017546  test    rcx, rcx
0x180017549  jz      short loc_1800174F2
0x18001754b  call    cs:__imp_CoTaskMemFree
0x180017551  jmp     short loc_1800174F2
0x180017553  call    cs:__imp_CoTaskMemFree
0x180017559  jmp     loc_1800174A0
0x18001755e  mov     r9d, 77h ; 'w'
0x180017564  xor     edx, edx
0x180017566  mov     ebx, 80070057h
0x18001756b  mov     ecx, ebx
0x18001756d  call    Log_UnistoreHREvent_16
0x180017572  mov     eax, ebx
0x180017574  jmp     loc_1800174CF
0x180017579  mov     r9d, 99h
0x18001757f  mov     edx, r15d
0x180017582  jmp     short loc_18001756B
0x180017584  mov     r9d, 78h ; 'x'
0x18001758a  jmp     short loc_180017564
0x18001758c  mov     r9d, 7Ch ; '|'
0x180017592  mov     edx, r15d
0x180017595  mov     ecx, edi
0x180017597  call    Log_UnistoreHREvent_16
0x18001759c  jmp     loc_1800174A0
0x1800175a1  mov     r9d, 25h ; '%'
0x1800175a7  jmp     loc_18001746D
```
