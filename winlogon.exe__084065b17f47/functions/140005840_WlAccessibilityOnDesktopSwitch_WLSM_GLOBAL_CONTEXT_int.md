# WlAccessibilityOnDesktopSwitch(_WLSM_GLOBAL_CONTEXT *,int)

- ea: `0x140005840`
- end: `0x1400060c5`
- name: `?WlAccessibilityOnDesktopSwitch@@YAKPEAU_WLSM_GLOBAL_CONTEXT@@H@Z`
- size: `2181`
- prototype: `unsigned int __fastcall(struct _WLSM_GLOBAL_CONTEXT *, int)`
- caller_count: `5`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140003b60`
- `0x140004470`
- `0x1400045d0`
- `0x140004e80`
- `0x14008d360`

## callees

- `0x1400057f4`
- `0x140005840`
- `0x140019df8`
- `0x140041c34`
- `0x140053720`
- `0x14007c608`
- `0x14007cf90`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ultow` at `0x14000598f`
- `api-ms-win-crt-private-l1-1-0!_o__ultow` at `0x14000598f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400059c4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400059c4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005d6b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005d6b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400059b3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005d5d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400059b3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005d5d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140005dff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140005dff`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140005e5c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140005e5c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140005d52`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140005d52`

## string_xrefs

- `0x140005a0b`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility`
- `0x140006015`: `atbroker.exe`
- `0x140005e50`: `Configuration`

## pseudocode

```c
__int64 __fastcall WlAccessibilityOnDesktopSwitch(struct _WLSM_GLOBAL_CONTEXT *a1, int a2)
{
  WCHAR *v3; // r15
  int v4; // r12d
  unsigned int v5; // edi
  __int64 v6; // r14
  __int64 v7; // rcx
  const wchar_t *v8; // rdx
  __int64 v9; // rax
  wchar_t *v10; // r8
  int v11; // r11d
  __int64 v12; // r10
  wchar_t v13; // r9
  __int64 v14; // rbx
  __int64 v15; // rax
  unsigned __int64 v16; // rdi
  HANDLE ProcessHeap; // rax
  _WORD *v18; // rax
  _WORD *v19; // r11
  LSTATUS v20; // esi
  __int64 v21; // rdx
  const WCHAR *v22; // r8
  __int64 v23; // rcx
  WCHAR *v24; // r9
  __int64 v25; // r10
  WCHAR v26; // ax
  __int64 v27; // rcx
  _WORD *v28; // rax
  unsigned __int64 v29; // rax
  __int64 v30; // rdx
  const wchar_t *v31; // r8
  unsigned __int64 v32; // rcx
  wchar_t *v33; // r9
  __int64 v34; // r10
  wchar_t v35; // ax
  __int64 v36; // rcx
  _WORD *v37; // rax
  unsigned __int64 v38; // rcx
  __int16 *v39; // rax
  unsigned __int64 v40; // rdi
  _WORD *v41; // rcx
  __int64 v42; // r8
  __int16 v43; // dx
  HANDLE v44; // rax
  __int64 v45; // r9
  unsigned int v46; // edi
  CUser *v47; // rcx
  __int64 v48; // r9
  unsigned int v49; // eax
  __int64 v50; // r8
  unsigned int started; // eax
  DWORD cbData; // [rsp+3Ch] [rbp-19Ch] BYREF
  int v54; // [rsp+40h] [rbp-198h]
  int v55; // [rsp+44h] [rbp-194h]
  unsigned __int64 v56; // [rsp+48h] [rbp-190h]
  unsigned __int64 v57; // [rsp+50h] [rbp-188h]
  HKEY hKey; // [rsp+58h] [rbp-180h] BYREF
  wchar_t *v59; // [rsp+60h] [rbp-178h]
  __int64 v60; // [rsp+68h] [rbp-170h]
  WCHAR *v61; // [rsp+70h] [rbp-168h]
  __int64 v62; // [rsp+78h] [rbp-160h]
  wchar_t *v63; // [rsp+80h] [rbp-158h]
  __int64 v64; // [rsp+88h] [rbp-150h]
  _WORD *v65; // [rsp+90h] [rbp-148h]
  __int64 v66; // [rsp+98h] [rbp-140h]
  _WORD *v67; // [rsp+A0h] [rbp-138h]
  const wchar_t *v68; // [rsp+A8h] [rbp-130h]
  __int64 v69; // [rsp+B0h] [rbp-128h]
  __int64 v70; // [rsp+B8h] [rbp-120h]
  const WCHAR *v71; // [rsp+C0h] [rbp-118h]
  __int64 v72; // [rsp+C8h] [rbp-110h]
  __int64 v73; // [rsp+D0h] [rbp-108h]
  _WORD *v74; // [rsp+D8h] [rbp-100h]
  __int64 v75; // [rsp+E0h] [rbp-F8h]
  const wchar_t *v76; // [rsp+E8h] [rbp-F0h]
  unsigned __int64 v77; // [rsp+F0h] [rbp-E8h]
  __int64 v78; // [rsp+F8h] [rbp-E0h]
  _WORD *v79; // [rsp+100h] [rbp-D8h]
  __int64 v80; // [rsp+108h] [rbp-D0h]
  __int16 *v81; // [rsp+110h] [rbp-C8h]
  __int64 v82; // [rsp+118h] [rbp-C0h]
  __int64 v83; // [rsp+120h] [rbp-B8h]
  wchar_t v84[56]; // [rsp+130h] [rbp-A8h] BYREF

  v55 = a2;
  v3 = 0;
  v67 = 0;
  hKey = 0;
  v4 = 1;
  v54 = 1;
  v5 = *(_DWORD *)(*((_QWORD *)a1 + 2) + 88LL);
  v6 = 2147483646;
  v7 = 2147483646;
  v70 = 2147483646;
  v8 = L"Session";
  v68 = L"Session";
  v9 = 50;
  v69 = 50;
  v10 = v84;
  v59 = v84;
  v11 = 0;
  v12 = 0;
  v60 = 0;
  while ( v9 )
  {
    if ( !v7 )
      goto LABEL_6;
    v13 = *v8;
    if ( !*v8 )
      goto LABEL_6;
    v68 = ++v8;
    *v10++ = v13;
    v59 = v10;
    v69 = --v9;
    v70 = --v7;
    v60 = ++v12;
  }
  v59 = --v10;
  v60 = v12 - 1;
  v11 = -2147024774;
LABEL_6:
  *v10 = 0;
  if ( v11 < 0 )
  {
    v20 = (unsigned __int16)v11;
  }
  else
  {
    v14 = -1;
    v15 = -1;
    do
      ++v15;
    while ( v84[v15] );
    _ultow(v5, &v84[v15], 10);
    do
      ++v14;
    while ( v84[v14] );
    v16 = v14 + 60;
    ProcessHeap = GetProcessHeap();
    v18 = HeapAlloc(ProcessHeap, 8u, 2 * (v14 + 60));
    v19 = v18;
    if ( v18 )
    {
      if ( v14 == -60 || (v20 = 0, v16 > 0x7FFFFFFF) )
        v20 = -2147024809;
      if ( v20 < 0 )
      {
        if ( v14 != -60 )
          *v18 = 0;
      }
      else
      {
        v21 = 2147483646;
        v73 = 2147483646;
        v22 = L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Accessibility";
        v71 = L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Accessibility";
        v23 = v14 + 60;
        v72 = v14 + 60;
        v24 = v18;
        v61 = v18;
        v20 = 0;
        v25 = 0;
        v62 = 0;
        while ( v23 )
        {
          if ( !v21 )
            goto LABEL_20;
          v26 = *v22;
          if ( !*v22 )
            goto LABEL_20;
          v71 = ++v22;
          *v24++ = v26;
          v61 = v24;
          v72 = --v23;
          v73 = --v21;
          v62 = ++v25;
        }
        v61 = --v24;
        v62 = v25 - 1;
        v20 = -2147024774;
LABEL_20:
        *v24 = 0;
      }
      if ( v20 < 0 )
        goto LABEL_86;
      v56 = 0;
      if ( (unsigned __int64)(v14 + 59) > 0x7FFFFFFE )
      {
        v20 = -2147024809;
        v29 = 0;
        v56 = 0;
      }
      else
      {
        v27 = v14 + 60;
        v75 = v14 + 60;
        v28 = v19;
        v74 = v19;
        v20 = 0;
        while ( v27 )
        {
          if ( !*v28 )
            goto LABEL_29;
          v74 = ++v28;
          v75 = --v27;
        }
        v20 = -2147024809;
LABEL_29:
        v56 = v20 < 0 ? 0LL : v16 - v27;
        v29 = v56;
      }
      if ( v20 < 0 )
        goto LABEL_86;
      v30 = 2147483646;
      v78 = 2147483646;
      v31 = L"\\";
      v76 = L"\\";
      v32 = v16 - v29;
      v77 = v16 - v29;
      v33 = &v19[v29];
      v63 = v33;
      v20 = 0;
      v34 = 0;
      v64 = 0;
      while ( v32 )
      {
        if ( !v30 )
          goto LABEL_38;
        v35 = *v31;
        if ( !*v31 )
          goto LABEL_38;
        v76 = ++v31;
        *v33++ = v35;
        v63 = v33;
        v77 = --v32;
        v78 = --v30;
        v64 = ++v34;
      }
      v63 = --v33;
      v64 = v34 - 1;
      v20 = -2147024774;
LABEL_38:
      *v33 = 0;
      if ( v20 < 0 )
        goto LABEL_86;
      v57 = 0;
      if ( (unsigned __int64)(v14 + 59) > 0x7FFFFFFE )
      {
        v20 = -2147024809;
        v38 = 0;
        v57 = 0;
      }
      else
      {
        v36 = v14 + 60;
        v80 = v14 + 60;
        v37 = v19;
        v79 = v19;
        v20 = 0;
        while ( v36 )
        {
          if ( !*v37 )
            goto LABEL_44;
          v79 = ++v37;
          v80 = --v36;
        }
        v20 = -2147024809;
LABEL_44:
        v57 = v20 < 0 ? 0LL : v16 - v36;
        v38 = v57;
      }
      if ( v20 < 0 )
        goto LABEL_86;
      v83 = 2147483646;
      v39 = (__int16 *)v84;
      v81 = (__int16 *)v84;
      v40 = v16 - v38;
      v82 = v40;
      v41 = &v19[v38];
      v65 = v41;
      v20 = 0;
      v42 = 0;
      v66 = 0;
      while ( v40 )
      {
        if ( !v6 )
          goto LABEL_53;
        v43 = *v39;
        if ( !*v39 )
          goto LABEL_53;
        v81 = ++v39;
        *v41++ = v43;
        v65 = v41;
        v82 = --v40;
        v83 = --v6;
        v66 = ++v42;
      }
      v65 = --v41;
      v66 = v42 - 1;
      v20 = -2147024774;
LABEL_53:
      *v41 = 0;
      if ( v20 < 0 )
      {
LABEL_86:
        v20 = (unsigned __int16)v20;
      }
      else
      {
        v3 = v19;
        v67 = v19;
        v20 = 0;
      }
    }
    else
    {
      v20 = 14;
    }
  }
  if ( !v20 )
  {
    v20 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0xF003Fu, &hKey);
    if ( !v20 )
    {
      cbData = 0;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 139, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids, v48);
      }
      v20 = RegQueryValueExW(hKey, L"Configuration", 0, 0, 0, &cbData);
      if ( cbData )
      {
        if ( !v20 )
          v4 = 0;
        v54 = v4;
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v3 )
  {
    v44 = GetProcessHeap();
    HeapFree(v44, 0, v3);
    v67 = 0;
  }
  if ( v20
    && WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      98,
      WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids,
      (unsigned int)v20);
  }
  if ( v4 && (unsigned int)CSession::IsAccessibilityJobObjectEmpty(*((CSession **)a1 + 2)) )
  {
    v46 = 0;
    v47 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 99, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids, v45);
LABEL_105:
      v47 = WPP_GLOBAL_Control;
    }
  }
  else
  {
    v49 = CSession::TerminateAtJob(*((CSession **)a1 + 2));
    if ( v49
      && WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 100, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids, v49);
    }
    started = WlAccessibilitypStartProcessInAtJob((CSession **)a1, L"atbroker.exe", v50, v55);
    v46 = started;
    if ( !started )
    {
      v46 = 0;
      goto LABEL_105;
    }
    v47 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids, started);
      goto LABEL_105;
    }
  }
  if ( v47 != (CUser *)&WPP_GLOBAL_Control && (*((_DWORD *)v47 + 7) & 0x40000) != 0 && *((_BYTE *)v47 + 25) >= 4u )
    WPP_SF_d(*((_QWORD *)v47 + 2), 102, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids, v46);
  return v46;
}

```

## disassembly

```asm
0x140005840  mov     [rsp+arg_10], rbx
0x140005845  mov     [rsp+arg_18], rsi
0x14000584a  push    rdi
0x14000584b  push    r12
0x14000584d  push    r13
0x14000584f  push    r14
0x140005851  push    r15
0x140005853  sub     rsp, 1B0h
0x14000585a  mov     rax, cs:__security_cookie
0x140005861  xor     rax, rsp
0x140005864  mov     [rsp+1D8h+var_38], rax
0x14000586c  mov     [rsp+1D8h+var_194], edx
0x140005870  mov     r13, rcx
0x140005873  mov     [rsp+1D8h+var_1A8], 57h ; 'W'
0x14000587b  xor     ebx, ebx
0x14000587d  mov     r15d, ebx
0x140005880  mov     [rsp+1D8h+var_138], rbx
0x140005888  mov     [rsp+1D8h+hKey], rbx
0x14000588d  mov     r12d, 1
0x140005893  mov     [rsp+1D8h+var_198], r12d
0x140005898  mov     rax, [rcx+10h]
0x14000589c  mov     edi, [rax+58h]
0x14000589f  mov     [rsp+1D8h+var_1A4], ebx
0x1400058a3  mov     [rsp+1D8h+var_1A4], ebx
0x1400058a7  mov     r14d, 7FFFFFFEh
0x1400058ad  mov     ecx, r14d
0x1400058b0  mov     [rsp+1D8h+var_120], rcx
0x1400058b8  lea     rdx, aSession; "Session"
0x1400058bf  mov     [rsp+1D8h+var_130], rdx
0x1400058c7  mov     eax, 32h ; '2'
0x1400058cc  mov     [rsp+1D8h+var_128], rax
0x1400058d4  lea     r8, [rsp+1D8h+var_A8]
0x1400058dc  mov     [rsp+1D8h+var_178], r8
0x1400058e1  mov     r11d, ebx
0x1400058e4  mov     r10d, ebx
0x1400058e7  mov     [rsp+1D8h+var_170], rbx
0x1400058ec  nop     dword ptr [rax+00h]
0x1400058f0  test    rax, rax
0x1400058f3  jz      loc_140005B12
0x1400058f9  test    rcx, rcx
0x1400058fc  jz      short loc_140005941
0x1400058fe  movzx   r9d, word ptr [rdx]
0x140005902  test    r9w, r9w
0x140005906  jz      short loc_140005941
0x140005908  add     rdx, 2
0x14000590c  mov     [rsp+1D8h+var_130], rdx
0x140005914  mov     [r8], r9w
0x140005918  add     r8, 2
0x14000591c  mov     [rsp+1D8h+var_178], r8
0x140005921  dec     rax
0x140005924  mov     [rsp+1D8h+var_128], rax
0x14000592c  dec     rcx
0x14000592f  mov     [rsp+1D8h+var_120], rcx
0x140005937  inc     r10
0x14000593a  mov     [rsp+1D8h+var_170], r10
0x14000593f  jmp     short loc_1400058F0
0x140005941  test    rax, rax
0x140005944  jz      loc_140005B12
0x14000594a  mov     [r8], bx
0x14000594e  mov     [rsp+1D8h+var_1A4], r11d
0x140005953  test    r11d, r11d
0x140005956  js      loc_140005F6D
0x14000595c  lea     rcx, [rsp+1D8h+var_A8]
0x140005964  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x14000596b  mov     rax, rbx
0x14000596e  xchg    ax, ax
0x140005970  lea     rax, [rax+1]
0x140005974  cmp     [rcx+rax*2], r15w
0x140005979  jnz     short loc_140005970
0x14000597b  lea     rdx, [rsp+1D8h+var_A8]
0x140005983  lea     rdx, [rdx+rax*2]; Buffer
0x140005987  mov     r8d, 0Ah; Radix
0x14000598d  mov     ecx, edi; Value
0x14000598f  call    cs:__imp__ultow
0x140005995  lea     rax, [rsp+1D8h+var_A8]
0x14000599d  nop     dword ptr [rax]
0x1400059a0  lea     rbx, [rbx+1]
0x1400059a4  cmp     [rax+rbx*2], r15w
0x1400059a9  jnz     short loc_1400059A0
0x1400059ab  lea     rdi, [rbx+3Ch]
0x1400059af  lea     rbx, [rdi+rdi]
0x1400059b3  call    cs:__imp_GetProcessHeap
0x1400059b9  mov     rcx, rax; hHeap
0x1400059bc  mov     r8, rbx; dwBytes
0x1400059bf  mov     edx, 8; dwFlags
0x1400059c4  call    cs:__imp_HeapAlloc
0x1400059ca  mov     r11, rax
0x1400059cd  xor     ebx, ebx
0x1400059cf  test    rax, rax
0x1400059d2  jz      loc_140005F87
0x1400059d8  mov     [rsp+1D8h+var_1A0], ebx
0x1400059dc  test    rdi, rdi
0x1400059df  jz      loc_140005F91
0x1400059e5  mov     esi, ebx
0x1400059e7  cmp     rdi, 7FFFFFFFh
0x1400059ee  ja      loc_140005F91
0x1400059f4  mov     [rsp+1D8h+var_1A0], esi
0x1400059f8  test    esi, esi
0x1400059fa  js      loc_140005F9B
0x140005a00  mov     rdx, r14
0x140005a03  mov     [rsp+1D8h+var_108], rdx
0x140005a0b  lea     r8, aSoftwareMicros_13; "Software\\Microsoft\\Windows NT\\Curren"...
0x140005a12  mov     [rsp+1D8h+var_118], r8
0x140005a1a  mov     rcx, rdi
0x140005a1d  mov     [rsp+1D8h+var_110], rcx
0x140005a25  mov     r9, r11
0x140005a28  mov     [rsp+1D8h+var_168], r11
0x140005a2d  mov     esi, ebx
0x140005a2f  mov     r10, rbx
0x140005a32  mov     [rsp+1D8h+var_160], rbx
0x140005a37  test    rcx, rcx
0x140005a3a  jz      loc_140005AF7
0x140005a40  test    rdx, rdx
0x140005a43  jz      short loc_140005A87
0x140005a45  movzx   eax, word ptr [r8]
0x140005a49  test    ax, ax
0x140005a4c  jz      short loc_140005A87
0x140005a4e  add     r8, 2
0x140005a52  mov     [rsp+1D8h+var_118], r8
0x140005a5a  mov     [r9], ax
0x140005a5e  add     r9, 2
0x140005a62  mov     [rsp+1D8h+var_168], r9
0x140005a67  dec     rcx
0x140005a6a  mov     [rsp+1D8h+var_110], rcx
0x140005a72  dec     rdx
0x140005a75  mov     [rsp+1D8h+var_108], rdx
0x140005a7d  inc     r10
0x140005a80  mov     [rsp+1D8h+var_160], r10
0x140005a85  jmp     short loc_140005A37
0x140005a87  test    rcx, rcx
0x140005a8a  jz      short loc_140005AF7
0x140005a8c  mov     [r9], bx
0x140005a90  mov     [rsp+1D8h+var_1A0], esi
0x140005a94  test    esi, esi
0x140005a96  js      loc_140005F53
0x140005a9c  mov     [rsp+1D8h+var_190], rbx
0x140005aa1  lea     rax, [rdi-1]
0x140005aa5  cmp     rax, r14
0x140005aa8  ja      loc_140005FAC
0x140005aae  lea     rdx, [rsp+1D8h+var_190]
0x140005ab3  mov     rcx, rdi
0x140005ab6  mov     [rsp+1D8h+var_F8], rcx
0x140005abe  mov     rax, r11
0x140005ac1  mov     [rsp+1D8h+var_100], rax
0x140005ac9  mov     esi, ebx
0x140005acb  nop     dword ptr [rax+rax+00h]
0x140005ad0  test    rcx, rcx
0x140005ad3  jz      loc_140005F2F
0x140005ad9  cmp     [rax], bx
0x140005adc  jz      short loc_140005B2E
0x140005ade  add     rax, 2
0x140005ae2  mov     [rsp+1D8h+var_100], rax
0x140005aea  dec     rcx
0x140005aed  mov     [rsp+1D8h+var_F8], rcx
0x140005af5  jmp     short loc_140005AD0
0x140005af7  sub     r9, 2
0x140005afb  mov     [rsp+1D8h+var_168], r9
0x140005b00  dec     r10
0x140005b03  mov     [rsp+1D8h+var_160], r10
0x140005b08  mov     esi, 8007007Ah
0x140005b0d  jmp     loc_140005A8C
0x140005b12  sub     r8, 2
0x140005b16  mov     [rsp+1D8h+var_178], r8
0x140005b1b  dec     r10
0x140005b1e  mov     [rsp+1D8h+var_170], r10
0x140005b23  mov     r11d, 8007007Ah
0x140005b29  jmp     loc_14000594A
0x140005b2e  test    rcx, rcx
0x140005b31  jz      loc_140005F2F
0x140005b37  test    esi, esi
0x140005b39  js      loc_140005F43
0x140005b3f  mov     rax, rdi
0x140005b42  sub     rax, rcx
0x140005b45  mov     [rdx], rax
0x140005b48  mov     rax, [rsp+1D8h+var_190]
0x140005b4d  test    esi, esi
0x140005b4f  js      loc_140005F53
0x140005b55  mov     rdx, r14
0x140005b58  mov     [rsp+1D8h+var_E0], rdx
0x140005b60  lea     r8, SubStr; "\\"
0x140005b67  mov     [rsp+1D8h+var_F0], r8
0x140005b6f  mov     rcx, rdi
0x140005b72  sub     rcx, rax
0x140005b75  mov     [rsp+1D8h+var_E8], rcx
0x140005b7d  lea     r9, [r11+rax*2]
0x140005b81  mov     [rsp+1D8h+var_158], r9
0x140005b89  mov     esi, ebx
0x140005b8b  mov     r10, rbx
0x140005b8e  mov     [rsp+1D8h+var_150], rbx
0x140005b96  test    rcx, rcx
0x140005b99  jz      loc_140005EC9
0x140005b9f  test    rdx, rdx
0x140005ba2  jz      short loc_140005BEC
0x140005ba4  movzx   eax, word ptr [r8]
0x140005ba8  test    ax, ax
0x140005bab  jz      short loc_140005BEC
0x140005bad  add     r8, 2
0x140005bb1  mov     [rsp+1D8h+var_F0], r8
0x140005bb9  mov     [r9], ax
0x140005bbd  add     r9, 2
0x140005bc1  mov     [rsp+1D8h+var_158], r9
0x140005bc9  dec     rcx
0x140005bcc  mov     [rsp+1D8h+var_E8], rcx
0x140005bd4  dec     rdx
0x140005bd7  mov     [rsp+1D8h+var_E0], rdx
0x140005bdf  inc     r10
0x140005be2  mov     [rsp+1D8h+var_150], r10
0x140005bea  jmp     short loc_140005B96
0x140005bec  test    rcx, rcx
0x140005bef  jz      loc_140005EC9
0x140005bf5  mov     [r9], bx
0x140005bf9  test    esi, esi
0x140005bfb  js      loc_140005F53
0x140005c01  mov     [rsp+1D8h+var_188], rbx
0x140005c06  lea     rax, [rdi-1]
0x140005c0a  cmp     rax, r14
0x140005c0d  ja      loc_140005FBE
0x140005c13  lea     rdx, [rsp+1D8h+var_188]
0x140005c18  mov     rcx, rdi
0x140005c1b  mov     [rsp+1D8h+var_D0], rcx
0x140005c23  mov     rax, r11
0x140005c26  mov     [rsp+1D8h+var_D8], rax
0x140005c2e  mov     esi, ebx
0x140005c30  test    rcx, rcx
0x140005c33  jz      loc_140005F39
0x140005c39  cmp     [rax], bx
0x140005c3c  jz      short loc_140005C57
0x140005c3e  add     rax, 2
0x140005c42  mov     [rsp+1D8h+var_D8], rax
0x140005c4a  dec     rcx
0x140005c4d  mov     [rsp+1D8h+var_D0], rcx
0x140005c55  jmp     short loc_140005C30
0x140005c57  test    rcx, rcx
0x140005c5a  jz      loc_140005F39
0x140005c60  test    esi, esi
0x140005c62  js      loc_140005F4B
0x140005c68  mov     rax, rdi
0x140005c6b  sub     rax, rcx
0x140005c6e  mov     [rdx], rax
0x140005c71  mov     rcx, [rsp+1D8h+var_188]
0x140005c76  test    esi, esi
0x140005c78  js      loc_140005F53
0x140005c7e  mov     [rsp+1D8h+var_B8], r14
0x140005c86  lea     rax, [rsp+1D8h+var_A8]
0x140005c8e  mov     [rsp+1D8h+var_C8], rax
0x140005c96  sub     rdi, rcx
0x140005c99  mov     [rsp+1D8h+var_C0], rdi
0x140005ca1  lea     rcx, [r11+rcx*2]
0x140005ca5  mov     [rsp+1D8h+var_148], rcx
0x140005cad  mov     esi, ebx
0x140005caf  mov     r8, rbx
0x140005cb2  mov     [rsp+1D8h+var_140], rbx
0x140005cba  nop     word ptr [rax+rax+00h]
0x140005cc0  test    rdi, rdi
0x140005cc3  jz      loc_140005EEA
0x140005cc9  test    r14, r14
0x140005ccc  jz      short loc_140005D14
0x140005cce  movzx   edx, word ptr [rax]
0x140005cd1  test    dx, dx
0x140005cd4  jz      short loc_140005D14
0x140005cd6  add     rax, 2
0x140005cda  mov     [rsp+1D8h+var_C8], rax
0x140005ce2  mov     [rcx], dx
0x140005ce5  add     rcx, 2
0x140005ce9  mov     [rsp+1D8h+var_148], rcx
0x140005cf1  dec     rdi
0x140005cf4  mov     [rsp+1D8h+var_C0], rdi
0x140005cfc  dec     r14
0x140005cff  mov     [rsp+1D8h+var_B8], r14
0x140005d07  inc     r8
0x140005d0a  mov     [rsp+1D8h+var_140], r8
0x140005d12  jmp     short loc_140005CC0
0x140005d14  test    rdi, rdi
0x140005d17  jz      loc_140005EEA
0x140005d1d  mov     [rcx], bx
0x140005d20  test    esi, esi
0x140005d22  js      loc_140005F53
0x140005d28  mov     r15, r11
0x140005d2b  mov     [rsp+1D8h+var_138], r11
0x140005d33  mov     esi, ebx
0x140005d35  mov     [rsp+1D8h+var_1A8], esi
0x140005d39  test    esi, esi
0x140005d3b  jz      loc_140005DE2
0x140005d41  lea     rbx, WPP_GLOBAL_Control
0x140005d48  mov     rcx, [rsp+1D8h+hKey]; hKey
0x140005d4d  test    rcx, rcx
0x140005d50  jz      short loc_140005D58
0x140005d52  call    cs:__imp_RegCloseKey
0x140005d58  test    r15, r15
0x140005d5b  jz      short loc_140005D7D
0x140005d5d  call    cs:__imp_GetProcessHeap
0x140005d63  mov     r8, r15; lpMem
0x140005d66  xor     edx, edx; dwFlags
0x140005d68  mov     rcx, rax; hHeap
0x140005d6b  call    cs:__imp_HeapFree
0x140005d71  mov     [rsp+1D8h+var_138], 0
0x140005d7d  test    esi, esi
0x140005d7f  jnz     loc_140005E85
0x140005d85  test    r12d, r12d
0x140005d88  jz      loc_140005FD0
  ... truncated ...
```
