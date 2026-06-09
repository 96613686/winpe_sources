# CHttpPolicyExtensionLoader::ReadExtensionConfig(_HTTP_POLICY_EXTENSION_LOADER_TYPE,int,HKEY__ *,ushort const *)

- ea: `0x18001944c`
- end: `0x180019ab6`
- name: `?ReadExtensionConfig@CHttpPolicyExtensionLoader@@AEAAJW4_HTTP_POLICY_EXTENSION_LOADER_TYPE@@HPEAUHKEY__@@PEBG@Z`
- size: `1642`
- prototype: `int __high(enum _HTTP_POLICY_EXTENSION_LOADER_TYPE, int, HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180017cc4`

## callees

- `0x1800081a0`
- `0x180008554`
- `0x1800169a0`
- `0x180016c84`
- `0x1800193a0`
- `0x18001944c`
- `0x180019ac0`
- `0x18001b480`
- `0x1800a1d10`
- `0x1800a2660`
- `0x1800cdd7c`
- `0x1800cdd88`
- `0x1800d06fc`
- `0x1800dab00`
- `0x1800db6b0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180019709`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180019709`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001996f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001996f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180019576`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180019576`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800194fd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800194fd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019847`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019847`

## string_xrefs

- `0x180019527`: `PolicySubPath`
- `0x180019550`: `DllPath`

## pseudocode

```c
__int64 __fastcall CHttpPolicyExtensionLoader::ReadExtensionConfig(
        unsigned __int16 *a1,
        __int64 a2,
        int a3,
        HKEY a4,
        const WCHAR *lpSubKey)
{
  int v5; // r13d
  __int64 *v6; // rsi
  int v8; // edx
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  LSTATUS v12; // eax
  __int64 v13; // r9
  int RegistryString; // eax
  int v15; // eax
  __int64 v16; // r14
  int v17; // eax
  unsigned int v18; // edi
  __int64 v19; // r15
  unsigned int v20; // r12d
  __int64 v21; // r14
  __int64 v22; // rcx
  int v23; // eax
  int v24; // edx
  void *v25; // rcx
  __int64 *v26; // r13
  char *v27; // rax
  char *v28; // rbx
  __int64 *v29; // r14
  void **v30; // rdi
  unsigned __int16 *v31; // r13
  unsigned __int16 **v32; // rcx
  int v34; // eax
  unsigned __int16 *v35; // rdi
  signed int LastError; // eax
  unsigned int v37; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int v39; // [rsp+60h] [rbp-A0h]
  unsigned __int16 *v41; // [rsp+70h] [rbp-90h] BYREF
  void *Src; // [rsp+78h] [rbp-88h] BYREF
  __int64 v43; // [rsp+80h] [rbp-80h]
  __int64 Heap; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v45; // [rsp+90h] [rbp-70h] BYREF
  __int64 v46; // [rsp+98h] [rbp-68h]
  __int64 *v47; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v48; // [rsp+A8h] [rbp-58h]
  HKEY hKey; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR Buffer; // [rsp+C0h] [rbp-40h] BYREF
  char v51[526]; // [rsp+C2h] [rbp-3Eh] BYREF

  v5 = a3;
  v41 = a1;
  hKey = 0;
  v47 = qword_1800E7D10;
  v48 = 0;
  v6 = qword_1800E7D10;
  v45 = (unsigned __int16 *)qword_1800E7D10;
  v46 = 0;
  Src = qword_1800E7D10;
  v43 = 0;
  Buffer = 0;
  memset_0(v51, 0, 0x206u);
  if ( (BYTE1(xmmword_180107A60) & 0x40) != 0 )
    WPP_SF_dlqS(v9, v8, v10, v11, v5, (__int64)a4, (__int64)lpSubKey);
  v12 = RegOpenKeyExW(a4, lpSubKey, 0, 0x20019u, &hKey);
  v13 = (unsigned int)v12;
  if ( v12 > 0 )
    v13 = (unsigned __int16)v12 | 0x80070000;
  if ( (int)v13 < 0 )
    goto LABEL_63;
  RegistryString = WxGetRegistryString(hKey, L"PolicySubPath", (struct CWxString *)&v47);
  v13 = (unsigned int)RegistryString;
  if ( RegistryString < 0 )
    goto LABEL_43;
  if ( !(_DWORD)v48 )
  {
    v13 = 2147942487LL;
    goto LABEL_63;
  }
  RegistryString = WxGetRegistryString(hKey, L"DllPath", (struct CWxString *)&v45);
  v13 = (unsigned int)RegistryString;
  if ( RegistryString < 0 )
  {
LABEL_43:
    v18 = RegistryString;
    goto LABEL_44;
  }
  if ( (_DWORD)v46 )
    goto LABEL_17;
  if ( GetSystemDirectoryW(&Buffer, 0x104u) - 1 <= 0x102 )
  {
    v15 = v46;
    if ( (_DWORD)v46 )
    {
      LODWORD(v46) = 0;
      *v45 = 0;
      v15 = v46;
    }
    v16 = -1;
    do
      ++v16;
    while ( *(_WORD *)&v51[2 * v16 - 2] );
    v13 = 0;
    if ( (_DWORD)v16 )
    {
      v34 = CWxString::ExtendBuffer((CWxString *)&v45, (int)v16 + v15 + 1);
      v13 = (unsigned int)v34;
      if ( v34 >= 0 )
      {
        v35 = &v45[(unsigned int)v46];
        memcpy_0(v35, &Buffer, 2LL * (unsigned int)v16);
        v35[(unsigned int)v16] = 0;
        LODWORD(v46) = v16 + v46;
        goto LABEL_17;
      }
    }
    if ( (int)v13 >= 0 )
    {
LABEL_17:
      if ( !v45 || !*v45 )
      {
        v13 = 2147942487LL;
        v18 = -2147024809;
        goto LABEL_44;
      }
      v17 = CWxString::_CombinePathImpl((CWxString *)&Src, v45, lpSubKey, (const unsigned __int16 *)v13);
      v6 = (__int64 *)Src;
      v13 = (unsigned int)v17;
      v18 = v17;
      if ( v17 < 0 )
        goto LABEL_44;
      v18 = -2147024882;
      if ( *(_WORD *)Src == 92 && *((_WORD *)Src + 1) == 92 )
      {
        if ( (*((_WORD *)Src + 2) == 63 || *((_WORD *)Src + 2) == 46) && (v13 = 0, *((_WORD *)Src + 3) == 92) )
        {
          v20 = HIDWORD(v43);
          LODWORD(v19) = v43;
        }
        else
        {
          v37 = CWxString::Insert((CWxString *)&Src, 2u, L"?\\UNC\\");
          v20 = HIDWORD(v43);
          v13 = v37;
          LODWORD(v19) = v43;
          v6 = (__int64 *)Src;
        }
LABEL_32:
        if ( (int)v13 < 0 )
        {
          v18 = v13;
        }
        else
        {
          if ( (BYTE1(xmmword_180107A60) & 0x40) != 0 )
            WPP_SF_SS(1038, 29, (unsigned int)WPP_70a6ea6fbc8b32957ec072c0c9e35dfc_Traceguids, (_DWORD)v6, (__int64)v47);
          v27 = (char *)HeapAlloc(g_hWxProcessHeap, 0, 0x60u);
          v28 = v27;
          if ( v27 )
          {
            v29 = (__int64 *)(v27 + 48);
            v30 = (void **)(v27 + 32);
            *(_OWORD *)(v27 + 72) = 0;
            *((_QWORD *)v27 + 11) = 0;
            *((_QWORD *)v27 + 4) = qword_1800E7D10;
            *((_QWORD *)v27 + 5) = 0;
            *((_QWORD *)v27 + 6) = qword_1800E7D10;
            *((_QWORD *)v27 + 7) = 0;
            *((_QWORD *)v27 + 8) = 0;
            *((_QWORD *)v27 + 1) = v27;
            *(_QWORD *)v27 = v27;
            *((_DWORD *)v27 + 4) = v5;
            v31 = v41;
            *((_QWORD *)v27 + 3) = v41;
            *((_DWORD *)v27 + 5) = 1;
            if ( v27 != (char *)-48LL && v29 != (__int64 *)&v47 )
            {
              CWxString::_Release((CWxString *)(v27 + 48));
              *v29 = (__int64)v47;
              *((_QWORD *)v28 + 7) = v48;
              v47 = qword_1800E7D10;
              v48 = 0;
            }
            if ( v30 != &Src )
            {
              CWxString::_Release((CWxString *)(v28 + 32));
              *v30 = v6;
              v6 = qword_1800E7D10;
              *((_DWORD *)v28 + 10) = v19;
              *((_DWORD *)v28 + 11) = v20;
            }
            v32 = (unsigned __int16 **)*((_QWORD *)v31 + 2);
            v13 = 0;
            if ( *v32 != v31 + 4 )
              __fastfail(3u);
            *(_QWORD *)v28 = v31 + 4;
            v18 = 0;
            *((_QWORD *)v28 + 1) = v32;
            *v32 = (unsigned __int16 *)v28;
            *((_QWORD *)v31 + 2) = v28;
          }
          else
          {
            v13 = 2147942414LL;
          }
        }
        goto LABEL_44;
      }
      v19 = (unsigned int)v43;
      v20 = HIDWORD(v43);
      v21 = (unsigned int)(v43 + 4);
      if ( HIDWORD(v43) < (unsigned int)v21 )
      {
        v22 = (unsigned int)(v43 + 6);
        v23 = 256;
        if ( (unsigned int)v22 > 0x100 )
        {
          if ( (unsigned int)v22 > 0x400 )
          {
            v23 = 4096;
            if ( (unsigned int)v22 <= 0x1000 )
              v23 = 1024;
          }
        }
        else
        {
          v23 = 64;
        }
        v24 = -v23 & (v23 + v43 + 5);
        v39 = v24 - 1;
        if ( (unsigned int)(v24 - 1) > 0xFFFFFFE )
        {
LABEL_60:
          v13 = 2147942487LL;
          goto LABEL_32;
        }
        HIDWORD(Heap) = 0;
        Heap = WxAllocateHeapEx(v22, (unsigned int)(2 * v24));
        v25 = (void *)Heap;
        if ( !Heap )
        {
          Heap = 0x3400000000LL;
          v13 = 2147942414LL;
          goto LABEL_32;
        }
        *(_WORD *)Heap = 0;
        v26 = v6;
        memcpy_0(v25, v6, 2 * v19);
        v6 = (__int64 *)Heap;
        v20 = v39;
        *(_WORD *)(2 * v19 + Heap) = 0;
        if ( v26 )
        {
          Heap = (__int64)v26;
          if ( v26 != qword_1800E7D10 )
            WxFreeHeapEx(&Heap);
        }
        v5 = a3;
      }
      memmove_0(v6 + 1, v6, 2LL * (unsigned int)(v19 + 1));
      *v6 = *(_QWORD *)L"\\\\?\\";
      if ( (unsigned int)v21 <= v20 )
      {
        v13 = 0;
        LODWORD(v19) = v21;
        *((_WORD *)v6 + v21) = 0;
        goto LABEL_32;
      }
      goto LABEL_60;
    }
LABEL_63:
    v18 = v13;
    goto LABEL_44;
  }
  LastError = GetLastError();
  v13 = (unsigned int)LastError;
  if ( LastError > 0 )
    v13 = (unsigned __int16)LastError | 0x80070000;
  if ( (int)v13 >= 0 )
    v13 = 2147549183LL;
  v18 = v13;
LABEL_44:
  if ( (BYTE1(xmmword_180107A60) & 0x40) != 0 )
    WPP_SF_d(1038, 30, WPP_70a6ea6fbc8b32957ec072c0c9e35dfc_Traceguids, v13, phkResult);
  v41 = (unsigned __int16 *)v6;
  if ( v6 != qword_1800E7D10 && v6 )
    WxFreeHeapEx(&v41);
  v41 = v45;
  if ( v45 != (unsigned __int16 *)qword_1800E7D10 && v45 )
    WxFreeHeapEx(&v41);
  v45 = (unsigned __int16 *)qword_1800E7D10;
  v46 = 0;
  v41 = (unsigned __int16 *)v47;
  if ( v47 != qword_1800E7D10 && v47 )
    WxFreeHeapEx(&v41);
  v47 = qword_1800E7D10;
  v48 = 0;
  if ( hKey )
    RegCloseKey(hKey);
  return v18;
}

```

## disassembly

```asm
0x18001944c  mov     [rsp-8+arg_8], rbx
0x180019451  push    rbp
0x180019452  push    rsi
0x180019453  push    rdi
0x180019454  push    r12
0x180019456  push    r13
0x180019458  push    r14
0x18001945a  push    r15
0x18001945c  lea     rbp, [rsp-1E0h]
0x180019464  sub     rsp, 2E0h
0x18001946b  mov     rax, cs:__security_cookie
0x180019472  xor     rax, rsp
0x180019475  mov     [rbp+210h+var_40], rax
0x18001947c  mov     r15, [rbp+210h+lpSubKey]
0x180019483  lea     rax, qword_1800E7D10
0x18001948a  xor     r12d, r12d
0x18001948d  mov     [rsp+310h+var_2A8], r8d
0x180019492  mov     r13d, r8d
0x180019495  mov     [rsp+310h+var_2A0], rcx
0x18001949a  mov     r8d, 206h; Size
0x1800194a0  mov     [rsp+310h+var_2AC], r12d
0x1800194a5  lea     rcx, [rbp+210h+var_24E]; void *
0x1800194a9  mov     [rbp+210h+hKey], r12
0x1800194ad  xor     edx, edx; Val
0x1800194af  mov     [rbp+210h+var_270], rax
0x1800194b3  mov     [rbp+210h+var_268], r12
0x1800194b7  mov     rsi, rax
0x1800194ba  mov     [rbp+210h+var_280], rax
0x1800194be  mov     rbx, r9
0x1800194c1  mov     [rbp+210h+var_278], r12
0x1800194c5  mov     [rsp+310h+Src], rax
0x1800194ca  mov     [rbp+210h+var_290], r12
0x1800194ce  mov     [rbp+210h+Buffer], r12w
0x1800194d3  call    memset_0
0x1800194d8  test    byte ptr cs:xmmword_180107A60+1, 40h
0x1800194df  jnz     loc_18001999E
0x1800194e5  lea     rax, [rbp+210h+hKey]
0x1800194e9  mov     r9d, 20019h; samDesired
0x1800194ef  xor     r8d, r8d; ulOptions
0x1800194f2  mov     [rsp+310h+phkResult], rax; unsigned __int16 *
0x1800194f7  mov     rdx, r15; lpSubKey
0x1800194fa  mov     rcx, rbx; hKey
0x1800194fd  call    cs:__imp_RegOpenKeyExW
0x180019503  mov     r9d, eax
0x180019506  mov     ebx, 80070000h
0x18001950b  test    eax, eax
0x18001950d  jle     short loc_180019516
0x18001950f  movzx   r9d, ax
0x180019513  or      r9d, ebx
0x180019516  test    r9d, r9d
0x180019519  js      loc_180019937
0x18001951f  mov     rcx, [rbp+210h+hKey]; hkey
0x180019523  lea     r8, [rbp+210h+var_270]; struct CWxString *
0x180019527  lea     rdx, aPolicysubpath; "PolicySubPath"
0x18001952e  call    ?WxGetRegistryString@@YAJPEAUHKEY__@@PEBGPEAVCWxString@@@Z; WxGetRegistryString(HKEY__ *,ushort const *,CWxString *)
0x180019533  mov     r9d, eax
0x180019536  test    eax, eax
0x180019538  js      loc_1800199B7
0x18001953e  cmp     dword ptr [rbp+210h+var_268], r12d
0x180019542  jz      loc_1800199C4
0x180019548  mov     rcx, [rbp+210h+hKey]; hkey
0x18001954c  lea     r8, [rbp+210h+var_280]; struct CWxString *
0x180019550  lea     rdx, aDllpath; "DllPath"
0x180019557  call    ?WxGetRegistryString@@YAJPEAUHKEY__@@PEBGPEAVCWxString@@@Z; WxGetRegistryString(HKEY__ *,ushort const *,CWxString *)
0x18001955c  mov     r9d, eax
0x18001955f  test    eax, eax
0x180019561  js      loc_1800197EA
0x180019567  cmp     dword ptr [rbp+210h+var_278], r12d
0x18001956b  jnz     short loc_1800195C6
0x18001956d  mov     edx, 104h; uSize
0x180019572  lea     rcx, [rbp+210h+Buffer]; lpBuffer
0x180019576  call    cs:__imp_GetSystemDirectoryW
0x18001957c  dec     eax
0x18001957e  cmp     eax, 102h
0x180019583  ja      loc_18001996F
0x180019589  mov     eax, dword ptr [rbp+210h+var_278]
0x18001958c  test    eax, eax
0x18001958e  jz      short loc_18001959F
0x180019590  mov     rax, [rbp+210h+var_280]
0x180019594  mov     dword ptr [rbp+210h+var_278], r12d
0x180019598  mov     [rax], r12w
0x18001959c  mov     eax, dword ptr [rbp+210h+var_278]
0x18001959f  lea     rcx, [rbp+210h+Buffer]
0x1800195a3  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800195a7  inc     r14
0x1800195aa  cmp     [rcx+r14*2], r12w
0x1800195af  jnz     short loc_1800195A7
0x1800195b1  mov     r9d, r12d; unsigned __int16 *
0x1800195b4  test    r14d, r14d
0x1800195b7  jnz     loc_1800198BA
0x1800195bd  test    r9d, r9d
0x1800195c0  js      loc_1800199D7
0x1800195c6  mov     rdx, [rbp+210h+var_280]; unsigned __int16 *
0x1800195ca  test    rdx, rdx
0x1800195cd  jz      loc_180019A85
0x1800195d3  cmp     [rdx], r12w
0x1800195d7  jz      loc_180019A85
0x1800195dd  mov     r8, r15; unsigned __int16 *
0x1800195e0  lea     rcx, [rsp+310h+Src]; this
0x1800195e5  call    ?_CombinePathImpl@CWxString@@AEAAJPEBG000000000@Z; CWxString::_CombinePathImpl(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x1800195ea  mov     rsi, [rsp+310h+Src]
0x1800195ef  mov     r9d, eax
0x1800195f2  mov     edi, eax
0x1800195f4  test    eax, eax
0x1800195f6  js      loc_180019A8E
0x1800195fc  cmp     word ptr [rsi], 5Ch ; '\'
0x180019600  mov     edi, 8007000Eh
0x180019605  jz      loc_1800199E4
0x18001960b  mov     r15d, dword ptr [rbp+210h+var_290]
0x18001960f  mov     r12d, dword ptr [rbp+210h+var_290+4]
0x180019613  lea     r14d, [r15+4]
0x180019617  cmp     r12d, r14d
0x18001961a  jnb     loc_1800196B3
0x180019620  lea     ecx, [r14+2]
0x180019624  mov     eax, 100h
0x180019629  cmp     ecx, eax
0x18001962b  ja      loc_180019953
0x180019631  mov     eax, 40h ; '@'
0x180019636  lea     edx, [rcx-1]
0x180019639  add     edx, eax
0x18001963b  neg     eax
0x18001963d  and     edx, eax
0x18001963f  lea     eax, [rdx-1]
0x180019642  mov     [rsp+310h+var_2B0], eax
0x180019646  cmp     eax, 0FFFFFFEh
0x18001964b  ja      loc_180019903
0x180019651  add     edx, edx
0x180019653  mov     [rbp+210h+var_284], 0
0x18001965a  call    WxAllocateHeapEx
0x18001965f  mov     [rbp-78h], rax
0x180019663  mov     rcx, rax; void *
0x180019666  test    rax, rax
0x180019669  jz      loc_180019A3F
0x18001966f  xor     eax, eax
0x180019671  lea     rbx, [r15+r15]
0x180019675  mov     r8, rbx; Size
0x180019678  mov     [rcx], ax
0x18001967b  mov     rdx, rsi; Src
0x18001967e  mov     r13, rsi
0x180019681  call    memcpy_0
0x180019686  mov     rsi, [rbp-78h]
0x18001968a  xor     eax, eax
0x18001968c  mov     r12d, [rsp+310h+var_2B0]
0x180019691  mov     [rbx+rsi], ax
0x180019695  test    r13, r13
0x180019698  jz      short loc_1800196AE
0x18001969a  lea     rax, qword_1800E7D10
0x1800196a1  mov     [rbp-78h], r13
0x1800196a5  cmp     r13, rax
0x1800196a8  jnz     loc_1800198AC
0x1800196ae  mov     r13d, [rsp+310h+var_2A8]
0x1800196b3  lea     r8d, [r15+1]
0x1800196b7  mov     rdx, rsi; Src
0x1800196ba  add     r8, r8; Size
0x1800196bd  lea     rcx, [rsi+8]; void *
0x1800196c1  call    memmove_0
0x1800196c6  mov     rax, qword ptr cs:asc_1800E6768; "\\\\?\\"
0x1800196cd  mov     [rsi], rax
0x1800196d0  cmp     r14d, r12d
0x1800196d3  ja      loc_180019903
0x1800196d9  xor     r9d, r9d
0x1800196dc  mov     r15d, r14d
0x1800196df  xor     eax, eax
0x1800196e1  mov     [rsi+r14*2], ax
0x1800196e6  test    r9d, r9d
0x1800196e9  js      loc_180019A4E
0x1800196ef  test    byte ptr cs:xmmword_180107A60+1, 40h
0x1800196f6  jnz     loc_180019A5E
0x1800196fc  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x180019703  xor     edx, edx; dwFlags
0x180019705  lea     r8d, [rdx+60h]; dwBytes
0x180019709  call    cs:__imp_HeapAlloc
0x18001970f  xor     ecx, ecx
0x180019711  mov     rbx, rax
0x180019714  test    rax, rax
0x180019717  jz      loc_180019924
0x18001971d  xor     eax, eax
0x18001971f  lea     r14, [rbx+30h]
0x180019723  lea     rdi, [rbx+20h]
0x180019727  xorps   xmm0, xmm0
0x18001972a  movups  xmmword ptr [rbx+48h], xmm0
0x18001972e  mov     [rbx+58h], rax
0x180019732  lea     rax, qword_1800E7D10
0x180019739  mov     [rdi], rax
0x18001973c  mov     [rdi+8], rcx
0x180019740  mov     [r14], rax
0x180019743  mov     [r14+8], rcx
0x180019747  mov     [rbx+40h], rcx
0x18001974b  mov     [rbx+8], rbx
0x18001974f  mov     [rbx], rbx
0x180019752  mov     [rbx+10h], r13d
0x180019756  mov     r13, [rsp+310h+var_2A0]
0x18001975b  mov     [rbx+18h], r13
0x18001975f  mov     dword ptr [rbx+14h], 1
0x180019766  test    r14, r14
0x180019769  jz      loc_180019947
0x18001976f  lea     rax, [rbp+210h+var_270]
0x180019773  cmp     r14, rax
0x180019776  jz      loc_180019947
0x18001977c  mov     rcx, r14; this
0x18001977f  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x180019784  mov     rax, [rbp+210h+var_270]
0x180019788  mov     [r14], rax
0x18001978b  mov     eax, dword ptr [rbp+210h+var_268]
0x18001978e  mov     [r14+8], eax
0x180019792  mov     eax, dword ptr [rbp+210h+var_268+4]
0x180019795  mov     [r14+0Ch], eax
0x180019799  lea     r14, qword_1800E7D10
0x1800197a0  mov     [rbp+210h+var_270], r14
0x1800197a4  mov     [rbp+210h+var_268], 0
0x1800197ac  lea     rax, [rsp+310h+Src]
0x1800197b1  cmp     rdi, rax
0x1800197b4  jz      short loc_1800197CC
0x1800197b6  mov     rcx, rdi; this
0x1800197b9  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x1800197be  mov     [rdi], rsi
0x1800197c1  mov     rsi, r14
0x1800197c4  mov     [rdi+8], r15d
0x1800197c8  mov     [rdi+0Ch], r12d
0x1800197cc  lea     rax, [r13+8]
0x1800197d0  xor     r12d, r12d
0x1800197d3  mov     rcx, [rax+8]
0x1800197d7  mov     r9d, r12d
0x1800197da  cmp     [rcx], rax
0x1800197dd  jz      loc_18001990E
0x1800197e3  lea     ecx, [r12+3]
0x1800197e8  int     29h; Win8: RtlFailFast(ecx)
0x1800197ea  mov     [rsp+310h+var_2AC], 17Dh
0x1800197f2  mov     edi, eax
0x1800197f4  test    byte ptr cs:xmmword_180107A60+1, 40h
0x1800197fb  jnz     loc_180019A9B
0x180019801  lea     rbx, qword_1800E7D10
0x180019808  mov     [rsp+310h+var_2A0], rsi
0x18001980d  cmp     rsi, rbx
0x180019810  jnz     short loc_180019879
0x180019812  mov     rax, [rbp+210h+var_280]
0x180019816  mov     [rsp+310h+var_2A0], rax
0x18001981b  cmp     rax, rbx
0x18001981e  jnz     short loc_18001988A
0x180019820  mov     rax, [rbp+210h+var_270]
0x180019824  mov     [rbp+210h+var_280], rbx
0x180019828  mov     [rbp+210h+var_278], r12
0x18001982c  mov     [rsp+310h+var_2A0], rax
0x180019831  cmp     rax, rbx
0x180019834  jnz     short loc_18001989B
0x180019836  mov     rcx, [rbp+210h+hKey]; hKey
0x18001983a  mov     [rbp+210h+var_270], rbx
0x18001983e  mov     [rbp+210h+var_268], r12
0x180019842  test    rcx, rcx
0x180019845  jz      short loc_18001984D
0x180019847  call    cs:__imp_RegCloseKey
0x18001984d  mov     eax, edi
0x18001984f  mov     rcx, [rbp+210h+var_40]
0x180019856  xor     rcx, rsp; StackCookie
0x180019859  call    __security_check_cookie
0x18001985e  mov     rbx, [rsp+310h+arg_8]
0x180019866  add     rsp, 2E0h
0x18001986d  pop     r15
0x18001986f  pop     r14
0x180019871  pop     r13
0x180019873  pop     r12
0x180019875  pop     rdi
0x180019876  pop     rsi
0x180019877  pop     rbp
0x180019878  retn
0x180019879  test    rsi, rsi
0x18001987c  jz      short loc_180019812
0x18001987e  lea     rcx, [rsp+310h+var_2A0]
0x180019883  call    WxFreeHeapEx
0x180019888  jmp     short loc_180019812
0x18001988a  test    rax, rax
0x18001988d  jz      short loc_180019820
0x18001988f  lea     rcx, [rsp+310h+var_2A0]
0x180019894  call    WxFreeHeapEx
0x180019899  jmp     short loc_180019820
0x18001989b  test    rax, rax
0x18001989e  jz      short loc_180019836
0x1800198a0  lea     rcx, [rsp+310h+var_2A0]
0x1800198a5  call    WxFreeHeapEx
0x1800198aa  jmp     short loc_180019836
0x1800198ac  lea     rcx, [rbp+210h+var_288]
0x1800198b0  call    WxFreeHeapEx
0x1800198b5  jmp     loc_1800196AE
0x1800198ba  lea     edx, [rax+1]
0x1800198bd  add     edx, r14d; unsigned int
0x1800198c0  lea     rcx, [rbp+210h+var_280]; this
0x1800198c4  call    ?ExtendBuffer@CWxString@@QEAAJK@Z; CWxString::ExtendBuffer(ulong)
0x1800198c9  mov     r9d, eax
0x1800198cc  test    eax, eax
0x1800198ce  js      loc_1800195BD
0x1800198d4  mov     ecx, dword ptr [rbp+210h+var_278]
0x1800198d7  lea     rdx, [rbp+210h+Buffer]; Src
0x1800198db  mov     rax, [rbp+210h+var_280]
0x1800198df  lea     rdi, [rax+rcx*2]
0x1800198e3  mov     eax, r14d
0x1800198e6  mov     rcx, rdi; void *
0x1800198e9  lea     rbx, [rax+rax]
0x1800198ed  mov     r8, rbx; Size
0x1800198f0  call    memcpy_0
0x1800198f5  mov     [rbx+rdi], r12w
  ... truncated ...
```
