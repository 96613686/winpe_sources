# DllRegisterServer

- ea: `0x180002360`
- end: `0x1800025a1`
- name: `DllRegisterServer`
- size: `577`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002360`
- `0x1800039b0`
- `0x180003a9c`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180002547`
- `KERNEL32!SetLastError` at `0x180002547`
- `KERNEL32!GetLastError` at `0x1800024e2`
- `KERNEL32!GetLastError` at `0x1800024e2`

## string_xrefs

- `0x180002395`: `CLSID\{606B3777-3051-401F-974A-E66ACA82A3A3}`
- `0x1800023cc`: `Update Cleanup`
- `0x180002389`: `CLSID\{606B3777-3051-401F-974A-E66ACA82A3A3}\InProcServer32`
- `0x1800023df`: `%systemroot%\system32\scavengeui.dll`
- `0x1800023f2`: `ThreadingModel`
- `0x1800023c0`: `Software\Microsoft\Windows\CurrentVersion\Explorer\VolumeCaches\Update Cleanup`
- `0x18000241b`: `IconPath`
- `0x180002426`: `%systemroot%\system32\scavengeui.dll,0`
- `0x18000243c`: `@%systemroot%\system32\scavengeui.dll,-1002`
- `0x180002452`: `@%systemroot%\system32\scavengeui.dll,-1003`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  HRESULT result; // eax
  unsigned __int64 v1; // rbx
  int v2; // eax
  __int64 v3; // r10
  const wchar_t *v4; // rdx
  __int64 v5; // rax
  __int64 v6; // r9
  unsigned __int64 v7; // [rsp+30h] [rbp-D0h]
  const wchar_t *v8; // [rsp+38h] [rbp-C8h]
  __int64 *v9; // [rsp+40h] [rbp-C0h]
  __int64 v10; // [rsp+48h] [rbp-B8h]
  const wchar_t *v11; // [rsp+50h] [rbp-B0h]
  unsigned __int64 v12; // [rsp+58h] [rbp-A8h]
  const wchar_t *v13; // [rsp+60h] [rbp-A0h]
  __int64 *v14; // [rsp+68h] [rbp-98h]
  __int64 v15; // [rsp+70h] [rbp-90h]
  const wchar_t *v16; // [rsp+78h] [rbp-88h]
  unsigned __int64 v17; // [rsp+80h] [rbp-80h]
  const wchar_t *v18; // [rsp+88h] [rbp-78h]
  const wchar_t *v19; // [rsp+90h] [rbp-70h]
  __int64 v20; // [rsp+98h] [rbp-68h]
  const wchar_t *v21; // [rsp+A0h] [rbp-60h]
  __int64 v22; // [rsp+A8h] [rbp-58h]
  const wchar_t *v23; // [rsp+B0h] [rbp-50h]
  __int64 *v24; // [rsp+B8h] [rbp-48h]
  __int64 v25; // [rsp+C0h] [rbp-40h]
  const wchar_t *v26; // [rsp+C8h] [rbp-38h]
  __int64 v27; // [rsp+D0h] [rbp-30h]
  const wchar_t *v28; // [rsp+D8h] [rbp-28h]
  const wchar_t *v29; // [rsp+E0h] [rbp-20h]
  __int64 v30; // [rsp+E8h] [rbp-18h]
  const wchar_t *v31; // [rsp+F0h] [rbp-10h]
  __int64 v32; // [rsp+F8h] [rbp-8h]
  const wchar_t *v33; // [rsp+100h] [rbp+0h]
  const wchar_t *v34; // [rsp+108h] [rbp+8h]
  __int64 v35; // [rsp+110h] [rbp+10h]
  const wchar_t *v36; // [rsp+118h] [rbp+18h]
  __int64 v37; // [rsp+120h] [rbp+20h]
  const wchar_t *v38; // [rsp+128h] [rbp+28h]
  const wchar_t *v39; // [rsp+130h] [rbp+30h]
  __int64 v40; // [rsp+138h] [rbp+38h]
  const wchar_t *v41; // [rsp+140h] [rbp+40h]

  v10 = 1;
  v7 = 0xFFFFFFFF80000000uLL;
  v12 = 0xFFFFFFFF80000000uLL;
  v13 = L"CLSID\\{606B3777-3051-401F-974A-E66ACA82A3A3}\\InProcServer32";
  v8 = L"CLSID\\{606B3777-3051-401F-974A-E66ACA82A3A3}";
  v17 = 0xFFFFFFFF80000000uLL;
  v18 = L"CLSID\\{606B3777-3051-401F-974A-E66ACA82A3A3}\\InProcServer32";
  v9 = &qword_180007F48;
  v14 = &qword_180007F48;
  v11 = L"Update Cleanup";
  result = 0;
  v15 = 2;
  v16 = L"%systemroot%\\system32\\scavengeui.dll";
  v1 = 0;
  v20 = 1;
  v19 = L"ThreadingModel";
  v21 = L"Apartment";
  v26 = L"{606B3777-3051-401F-974A-E66ACA82A3A3}";
  v29 = L"IconPath";
  v31 = L"%systemroot%\\system32\\scavengeui.dll,0";
  v34 = L"Display";
  v36 = L"@%systemroot%\\system32\\scavengeui.dll,-1002";
  v39 = L"Description";
  v41 = L"@%systemroot%\\system32\\scavengeui.dll,-1003";
  v22 = -2147483646;
  v23 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\VolumeCaches\\Update Cleanup";
  v24 = &qword_180007F48;
  v25 = 1;
  v27 = -2147483646;
  v28 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\VolumeCaches\\Update Cleanup";
  v30 = 2;
  v32 = -2147483646;
  v33 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\VolumeCaches\\Update Cleanup";
  v35 = 2;
  v37 = -2147483646;
  v38 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\VolumeCaches\\Update Cleanup";
  v40 = 2;
  while ( v1 < 7 )
  {
    if ( *((_DWORD *)&v10 + 10 * v1) == 1 )
    {
      v3 = *(&v7 + 5 * v1);
      if ( !v3 || (v4 = (&v11)[5 * v1]) == 0 )
      {
LABEL_17:
        SetLastError(0x57u);
LABEL_9:
        result = GetLastError();
        if ( result )
        {
          if ( result > 0 )
            result = (unsigned __int16)result | 0x80070000;
        }
        else
        {
          result = -2147467259;
        }
        goto LABEL_25;
      }
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v6 = 1;
      goto LABEL_16;
    }
    if ( *((_DWORD *)&v10 + 10 * v1) == 2 )
    {
      v3 = *(&v7 + 5 * v1);
      if ( !v3 )
        goto LABEL_17;
      v4 = (&v11)[5 * v1];
      if ( !v4 )
        goto LABEL_17;
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v6 = 2;
LABEL_16:
      v2 = RegSetBinEx(
             v3,
             (&v8)[5 * v1],
             (&v9)[5 * v1],
             v6,
             v4,
             2 * (int)v5 + 2,
             v7,
             v8,
             v9,
             v10,
             v11,
             v12,
             v13,
             v14,
             v15,
             v16,
             v17,
             v18,
             v19,
             v20,
             v21,
             v22,
             v23,
             v24,
             v25,
             v26,
             v27,
             v28,
             v29,
             v30,
             v31,
             v32,
             v33,
             v34,
             v35,
             v36,
             v37,
             v38,
             v39,
             v40,
             v41);
      goto LABEL_7;
    }
    if ( *((_DWORD *)&v10 + 10 * v1) != 4 )
      return -2147024809;
    v2 = RegSetDword(*(&v7 + 5 * v1), (&v8)[5 * v1], (&v9)[5 * v1], *((unsigned int *)&v10 + 10 * v1 + 1));
LABEL_7:
    if ( !v2 )
      goto LABEL_9;
    result = 0;
LABEL_25:
    ++v1;
    if ( result < 0 )
      return result;
  }
  return result;
}

```

## disassembly

```asm
0x180002360  push    rbp
0x180002362  push    rbx
0x180002363  push    rdi
0x180002364  push    r15
0x180002366  lea     rbp, [rsp-58h]
0x18000236b  sub     rsp, 158h
0x180002372  mov     r8, 0FFFFFFFF80000000h
0x180002379  mov     [rsp+170h+var_128], 1
0x180002382  xor     edi, edi
0x180002384  mov     [rsp+170h+var_140], r8
0x180002389  lea     rdx, aClsid606b37773; "CLSID\\{606B3777-3051-401F-974A-E66ACA8"...
0x180002390  mov     [rsp+170h+var_118], r8
0x180002395  lea     rcx, aClsid606b37773_0; "CLSID\\{606B3777-3051-401F-974A-E66ACA8"...
0x18000239c  mov     [rsp+170h+var_110], rdx
0x1800023a1  mov     [rsp+170h+var_138], rcx
0x1800023a6  lea     r9, qword_180007F48
0x1800023ad  lea     r15d, [rdi+2]
0x1800023b1  mov     [rbp+70h+var_F0], r8
0x1800023b5  mov     r8, 0FFFFFFFF80000002h
0x1800023bc  mov     [rbp+70h+var_E8], rdx
0x1800023c0  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800023c7  mov     [rsp+170h+var_130], r9
0x1800023cc  lea     rcx, aUpdateCleanup; "Update Cleanup"
0x1800023d3  mov     [rsp+170h+var_108], r9
0x1800023d8  mov     [rsp+170h+var_120], rcx
0x1800023dd  mov     eax, edi
0x1800023df  lea     rcx, aSystemrootSyst_1; "%systemroot%\\system32\\scavengeui.dll"
0x1800023e6  mov     [rsp+170h+var_100], r15
0x1800023eb  mov     [rsp+170h+var_F8], rcx
0x1800023f0  mov     ebx, edi
0x1800023f2  lea     rcx, aThreadingmodel; "ThreadingModel"
0x1800023f9  mov     [rbp+70h+var_D8], 1
0x180002401  mov     [rbp+70h+var_E0], rcx
0x180002405  lea     rcx, aApartment; "Apartment"
0x18000240c  mov     [rbp+70h+var_D0], rcx
0x180002410  lea     rcx, a606b3777305140; "{606B3777-3051-401F-974A-E66ACA82A3A3}"
0x180002417  mov     [rbp+70h+var_A8], rcx
0x18000241b  lea     rcx, aIconpath; "IconPath"
0x180002422  mov     [rbp+70h+var_90], rcx
0x180002426  lea     rcx, aSystemrootSyst_0; "%systemroot%\\system32\\scavengeui.dll,"...
0x18000242d  mov     [rbp+70h+var_80], rcx
0x180002431  lea     rcx, aDisplay; "Display"
0x180002438  mov     [rbp+70h+var_68], rcx
0x18000243c  lea     rcx, aSystemrootSyst; "@%systemroot%\\system32\\scavengeui.dll"...
0x180002443  mov     [rbp+70h+var_58], rcx
0x180002447  lea     rcx, aDescription; "Description"
0x18000244e  mov     [rbp+70h+var_40], rcx
0x180002452  lea     rcx, aSystemrootSyst_2; "@%systemroot%\\system32\\scavengeui.dll"...
0x180002459  mov     [rbp+70h+var_30], rcx
0x18000245d  mov     [rbp+70h+var_C8], r8
0x180002461  mov     [rbp+70h+var_C0], rdx
0x180002465  mov     [rbp+70h+var_B8], r9
0x180002469  mov     [rbp+70h+var_B0], 1
0x180002471  mov     [rbp+70h+var_A0], r8
0x180002475  mov     [rbp+70h+var_98], rdx
0x180002479  mov     [rbp+70h+var_88], r15
0x18000247d  mov     [rbp+70h+var_78], r8
0x180002481  mov     [rbp+70h+var_70], rdx
0x180002485  mov     [rbp+70h+var_60], r15
0x180002489  mov     [rbp+70h+var_50], r8
0x18000248d  mov     [rbp+70h+var_48], rdx
0x180002491  mov     [rbp+70h+var_38], r15
0x180002495  cmp     rbx, 7
0x180002499  jnb     loc_180002594
0x18000249f  lea     rcx, [rbx+rbx*4]
0x1800024a3  mov     edx, dword ptr [rsp+rcx*8+170h+var_128]
0x1800024a7  sub     edx, 1
0x1800024aa  jz      loc_18000254F
0x1800024b0  sub     edx, 1
0x1800024b3  jz      short loc_1800024FA
0x1800024b5  cmp     edx, r15d
0x1800024b8  jnz     loc_18000258F
0x1800024be  mov     r9d, dword ptr [rsp+rcx*8+170h+var_128+4]
0x1800024c3  mov     r8, [rsp+rcx*8+170h+var_130]
0x1800024c8  mov     rdx, [rsp+rcx*8+170h+var_138]
0x1800024cd  mov     rcx, [rsp+rcx*8+170h+var_140]
0x1800024d2  call    RegSetDword
0x1800024d7  test    eax, eax
0x1800024d9  jz      short loc_1800024E2
0x1800024db  mov     eax, edi
0x1800024dd  jmp     loc_180002582
0x1800024e2  call    cs:__imp_GetLastError
0x1800024e8  test    eax, eax
0x1800024ea  jnz     loc_180002578
0x1800024f0  mov     eax, 80004005h
0x1800024f5  jmp     loc_180002582
0x1800024fa  mov     r10, [rsp+rcx*8+170h+var_140]
0x1800024ff  test    r10, r10
0x180002502  jz      short loc_180002542
0x180002504  mov     rdx, [rsp+rcx*8+170h+var_120]
0x180002509  test    rdx, rdx
0x18000250c  jz      short loc_180002542
0x18000250e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002512  inc     rax
0x180002515  cmp     [rdx+rax*2], di
0x180002519  jnz     short loc_180002512
0x18000251b  mov     r9d, r15d
0x18000251e  mov     r8, [rsp+rcx*8+170h+var_130]
0x180002523  lea     eax, ds:2[rax*2]
0x18000252a  mov     [rsp+170h+var_148], eax
0x18000252e  mov     [rsp+170h+var_150], rdx
0x180002533  mov     rdx, [rsp+rcx*8+170h+var_138]
0x180002538  mov     rcx, r10
0x18000253b  call    RegSetBinEx
0x180002540  jmp     short loc_1800024D7
0x180002542  mov     ecx, 57h ; 'W'; dwErrCode
0x180002547  call    cs:__imp_SetLastError
0x18000254d  jmp     short loc_1800024E2
0x18000254f  mov     r10, [rsp+rcx*8+170h+var_140]
0x180002554  test    r10, r10
0x180002557  jz      short loc_180002542
0x180002559  mov     rdx, [rsp+rcx*8+170h+var_120]
0x18000255e  test    rdx, rdx
0x180002561  jz      short loc_180002542
0x180002563  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002567  inc     rax
0x18000256a  cmp     [rdx+rax*2], di
0x18000256e  jnz     short loc_180002567
0x180002570  mov     r9d, 1
0x180002576  jmp     short loc_18000251E
0x180002578  jle     short loc_180002582
0x18000257a  movzx   eax, ax
0x18000257d  or      eax, 80070000h
0x180002582  inc     rbx
0x180002585  test    eax, eax
0x180002587  jns     loc_180002495
0x18000258d  jmp     short loc_180002594
0x18000258f  mov     eax, 80070057h
0x180002594  add     rsp, 158h
0x18000259b  pop     r15
0x18000259d  pop     rdi
0x18000259e  pop     rbx
0x18000259f  pop     rbp
0x1800025a0  retn
```
