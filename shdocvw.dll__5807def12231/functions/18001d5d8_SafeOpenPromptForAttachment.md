# SafeOpenPromptForAttachment

- ea: `0x18001d5d8`
- end: `0x18001d8f6`
- name: `SafeOpenPromptForAttachment`
- size: `798`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned __int16 *, LPCWSTR, __int64, bool)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010f64`

## callees

- `0x1800056b4`
- `0x1800058c0`
- `0x180008320`
- `0x180009018`
- `0x18000bf34`
- `0x180015cbc`
- `0x18001d5d8`
- `0x18002760c`
- `0x180027c30`

## import_xrefs

- `SHLWAPI!PathIsNetworkPathW` at `0x18001d7c5`
- `SHLWAPI!PathIsNetworkPathW` at `0x18001d7c5`
- `SHLWAPI!PathFindExtensionW` at `0x18001d850`
- `SHLWAPI!PathFindExtensionW` at `0x18001d850`
- `SHLWAPI!PathUndecorateW` at `0x18001d686`
- `SHLWAPI!PathUndecorateW` at `0x18001d686`
- `SHLWAPI!__imp_ZoneCheckUrlExW` at `0x18001d804`
- `SHLWAPI!__imp_ZoneCheckUrlExW` at `0x18001d804`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001d789`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001d789`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d6c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d6c7`

## pseudocode

```c
__int64 __fastcall SafeOpenPromptForAttachment(
        HWND a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4,
        unsigned __int16 *a5,
        LPCWSTR a6,
        _DWORD *a7,
        bool a8)
{
  int v8; // r14d
  bool v11; // zf
  BOOL v12; // r13d
  unsigned int v13; // edx
  unsigned int v14; // r8d
  __int64 v15; // rdx
  __int64 result; // rax
  bool v17; // bl
  LPWSTR ExtensionW; // rax
  unsigned int v19; // edx
  unsigned int v20; // ecx
  int v21; // [rsp+40h] [rbp-C0h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-B8h] BYREF
  int v23; // [rsp+50h] [rbp-B0h]
  HWND hWndParent; // [rsp+58h] [rbp-A8h]
  _DWORD v25[3]; // [rsp+60h] [rbp-A0h] BYREF
  int v26; // [rsp+6Ch] [rbp-94h]
  WCHAR *v27; // [rsp+70h] [rbp-90h]
  WCHAR *v28; // [rsp+78h] [rbp-88h]
  LPWSTR v29; // [rsp+80h] [rbp-80h]
  unsigned __int16 *v30; // [rsp+88h] [rbp-78h]
  LPCWSTR v31; // [rsp+90h] [rbp-70h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  __int64 v33; // [rsp+A0h] [rbp-60h]
  int v34; // [rsp+A8h] [rbp-58h]
  int v35; // [rsp+ACh] [rbp-54h]
  bool v36; // [rsp+B0h] [rbp-50h]
  int v37; // [rsp+B1h] [rbp-4Fh]
  __int16 v38; // [rsp+B5h] [rbp-4Bh]
  char v39; // [rsp+B7h] [rbp-49h]
  _DWORD *v40; // [rsp+B8h] [rbp-48h]
  __int128 v41; // [rsp+C0h] [rbp-40h]
  __int128 v42; // [rsp+D0h] [rbp-30h]
  __int128 v43; // [rsp+E0h] [rbp-20h]
  __int64 v44; // [rsp+F0h] [rbp-10h]
  _DWORD v45[4]; // [rsp+100h] [rbp+0h] BYREF
  char v46; // [rsp+110h] [rbp+10h]
  __int16 *v47; // [rsp+128h] [rbp+28h]
  int v48; // [rsp+130h] [rbp+30h]
  __int16 *v49; // [rsp+138h] [rbp+38h]
  int v50; // [rsp+140h] [rbp+40h]
  WCHAR Buffer[96]; // [rsp+160h] [rbp+60h] BYREF
  __int16 v52; // [rsp+220h] [rbp+120h] BYREF
  _BYTE v53[254]; // [rsp+222h] [rbp+122h] BYREF
  WCHAR pszPath[264]; // [rsp+320h] [rbp+220h] BYREF
  unsigned __int16 v55; // [rsp+530h] [rbp+430h] BYREF
  _BYTE v56[4174]; // [rsp+532h] [rbp+432h] BYREF
  __int16 v57; // [rsp+1580h] [rbp+1480h] BYREF
  _BYTE v58[4174]; // [rsp+1582h] [rbp+1482h] BYREF

  v8 = 0;
  hWndParent = a1;
  v11 = *a7 == 1;
  v23 = a4;
  v12 = !v11;
  v55 = 0;
  memset_0(v56, 0, 0x1046u);
  v21 = 0;
  StringCchCopyW(pszPath, 0x104u, a3);
  DecodeCacheFilenameForDisplay(pszPath, v13, v14);
  PathUndecorateW(pszPath);
  if ( a5 )
  {
    hMem = 0;
    if ( (int)GetHostDisplayNameFromUrlInternal(a5, v15, &hMem, &v21) < 0 )
    {
      StringCchCopyW(&v55, 0x824u, a5);
      v8 = 1;
    }
    else
    {
      StringCchCopyW(&v55, 0x824u, (const unsigned __int16 *)hMem);
      LocalFree(hMem);
      v8 = v21;
    }
  }
  v52 = 0;
  memset_0(v53, 0, sizeof(v53));
  v57 = 0;
  memset_0(v58, 0, 0x1046u);
  memset_0(v45, 0, 0x58u);
  v45[0] = 88;
  v47 = &v52;
  v49 = &v57;
  v48 = 128;
  v50 = 2084;
  if ( a2 && *a2 )
    StringCchCopyW(Buffer, 0x60u, a2);
  else
    LoadStringW(g_hinst, 0x8534u, Buffer, 96);
  if ( a6 && GetPublisherAndUrl(a6, a8, (struct SIGNATURE_INFO *)v45) < 0 )
    return 0;
  v17 = 0;
  if ( (v46 & 2) != 0 )
  {
    if ( PathIsNetworkPathW(a6) )
    {
      v21 = 0;
      LODWORD(hMem) = 0;
      if ( (int)((__int64 (__fastcall *)(LPCWSTR, int *, __int64, HLOCAL *, int, int, int, _QWORD))ZoneCheckUrlExW)(
                  a6,
                  &v21,
                  4,
                  &hMem,
                  4,
                  6162,
                  4611,
                  0) >= 0 )
        v17 = (v21 & 0xF) != 0;
    }
  }
  v25[1] = v23;
  v25[0] = 0;
  v25[2] = a8;
  v26 = v12;
  v27 = Buffer;
  v28 = pszPath;
  ExtensionW = PathFindExtensionW(a3);
  v31 = a6;
  v29 = ExtensionW;
  v35 = v8;
  v44 = 0;
  v30 = &v55;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  v40 = v45;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v36 = v17;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v20 = _ShowSafeOpenDialog(hWndParent, v19, (struct SAFEOPENDLGPARAM *)v25);
  result = 2;
  if ( v26 == 2 )
    *a7 = 2;
  if ( v20 != 1 )
    return v20 == 4358;
  return result;
}

```

## disassembly

```asm
0x18001d5d8  push    rbp
0x18001d5da  push    rbx
0x18001d5db  push    rsi
0x18001d5dc  push    rdi
0x18001d5dd  push    r12
0x18001d5df  push    r13
0x18001d5e1  push    r14
0x18001d5e3  push    r15
0x18001d5e5  lea     rbp, [rsp-24E8h]
0x18001d5ed  mov     eax, 25E8h
0x18001d5f2  call    _alloca_probe
0x18001d5f7  sub     rsp, rax
0x18001d5fa  mov     rax, cs:__security_cookie
0x18001d601  xor     rax, rsp
0x18001d604  mov     [rbp+2520h+var_50], rax
0x18001d60b  mov     r15, [rbp+2520h+arg_30]
0x18001d612  xor     r14d, r14d
0x18001d615  mov     rsi, [rbp+2520h+arg_20]
0x18001d61c  mov     r12, r8
0x18001d61f  mov     rdi, [rbp+2520h+arg_28]
0x18001d626  mov     rbx, rdx
0x18001d629  mov     [rsp+2620h+hWndParent], rcx
0x18001d62e  mov     r13d, r14d
0x18001d631  cmp     dword ptr [r15], 1
0x18001d635  lea     rcx, [rbp+2520h+var_20EE]; void *
0x18001d63c  mov     r8d, 1046h; Size
0x18001d642  mov     [rsp+2620h+var_25D0], r9d
0x18001d647  setnz   r13b
0x18001d64b  mov     [rbp+2520h+var_20F0], r14w
0x18001d653  xor     edx, edx; Val
0x18001d655  call    memset_0
0x18001d65a  mov     r8, r12; unsigned __int16 *
0x18001d65d  mov     [rsp+2620h+var_25E0], r14d
0x18001d662  mov     edx, 104h; unsigned __int64
0x18001d667  lea     rcx, [rbp+2520h+pszPath]; unsigned __int16 *
0x18001d66e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001d673  lea     rcx, [rbp+2520h+pszPath]; unsigned __int16 *
0x18001d67a  call    ?DecodeCacheFilenameForDisplay@@YAXPEAGKK@Z; DecodeCacheFilenameForDisplay(ushort *,ulong,ulong)
0x18001d67f  lea     rcx, [rbp+2520h+pszPath]; pszPath
0x18001d686  call    cs:__imp_PathUndecorateW
0x18001d68c  test    rsi, rsi
0x18001d68f  jz      short loc_18001D6E2
0x18001d691  lea     r9, [rsp+2620h+var_25E0]; int *
0x18001d696  mov     [rsp+2620h+hMem], r14
0x18001d69b  lea     r8, [rsp+2620h+hMem]; unsigned __int16 **
0x18001d6a0  mov     rcx, rsi; unsigned __int16 *
0x18001d6a3  call    ?GetHostDisplayNameFromUrlInternal@@YAJPEBGIPEAPEAGPEAHHH@Z; GetHostDisplayNameFromUrlInternal(ushort const *,uint,ushort * *,int *,int,int)
0x18001d6a8  lea     rcx, [rbp+2520h+var_20F0]; unsigned __int16 *
0x18001d6af  mov     edx, 824h; unsigned __int64
0x18001d6b4  test    eax, eax
0x18001d6b6  js      short loc_18001D6D4
0x18001d6b8  mov     r8, [rsp+2620h+hMem]; unsigned __int16 *
0x18001d6bd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001d6c2  mov     rcx, [rsp+2620h+hMem]; hMem
0x18001d6c7  call    cs:__imp_LocalFree
0x18001d6cd  mov     r14d, [rsp+2620h+var_25E0]
0x18001d6d2  jmp     short loc_18001D6E2
0x18001d6d4  mov     r8, rsi; unsigned __int16 *
0x18001d6d7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001d6dc  mov     r14d, 1
0x18001d6e2  xor     eax, eax
0x18001d6e4  lea     rcx, [rbp+2520h+var_23FE]; void *
0x18001d6eb  xor     edx, edx; Val
0x18001d6ed  mov     [rbp+2520h+var_2400], ax
0x18001d6f4  mov     r8d, 0FEh; Size
0x18001d6fa  call    memset_0
0x18001d6ff  xor     eax, eax
0x18001d701  lea     rcx, [rbp+2520h+var_109E]; void *
0x18001d708  xor     edx, edx; Val
0x18001d70a  mov     [rbp+2520h+var_10A0], ax
0x18001d711  mov     r8d, 1046h; Size
0x18001d717  call    memset_0
0x18001d71c  mov     esi, 58h ; 'X'
0x18001d721  lea     rcx, [rbp+2520h+var_2520]; void *
0x18001d725  mov     r8d, esi; Size
0x18001d728  xor     edx, edx; Val
0x18001d72a  call    memset_0
0x18001d72f  lea     rax, [rbp+2520h+var_2400]
0x18001d736  mov     [rbp+2520h+var_2520], esi
0x18001d739  mov     [rbp+2520h+var_24F8], rax
0x18001d73d  lea     rax, [rbp+2520h+var_10A0]
0x18001d744  mov     [rbp+2520h+var_24E8], rax
0x18001d748  xor     eax, eax
0x18001d74a  mov     [rbp+2520h+var_24F0], 80h
0x18001d751  mov     [rbp+2520h+var_24E0], 824h
0x18001d758  test    rbx, rbx
0x18001d75b  jz      short loc_18001D773
0x18001d75d  cmp     [rbx], ax
0x18001d760  jz      short loc_18001D773
0x18001d762  mov     r8, rbx; unsigned __int16 *
0x18001d765  lea     edx, [rsi+8]; unsigned __int64
0x18001d768  lea     rcx, [rbp+2520h+Buffer]; unsigned __int16 *
0x18001d76c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001d771  jmp     short loc_18001D78F
0x18001d773  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hInstance
0x18001d77a  lea     r8, [rbp+2520h+Buffer]; lpBuffer
0x18001d77e  mov     r9d, 60h ; '`'; cchBufferMax
0x18001d784  mov     edx, 8534h; uID
0x18001d789  call    cs:__imp_LoadStringW
0x18001d78f  mov     sil, [rbp+2520h+arg_38]
0x18001d796  xor     ecx, ecx
0x18001d798  test    rdi, rdi
0x18001d79b  jz      short loc_18001D7B9
0x18001d79d  lea     r8, [rbp+2520h+var_2520]; struct SIGNATURE_INFO *
0x18001d7a1  mov     dl, sil; bool
0x18001d7a4  mov     rcx, rdi; unsigned __int16 *
0x18001d7a7  call    ?GetPublisherAndUrl@@YAJPEBG_NPEAUSIGNATURE_INFO@@@Z; GetPublisherAndUrl(ushort const *,bool,SIGNATURE_INFO *)
0x18001d7ac  xor     ecx, ecx
0x18001d7ae  test    eax, eax
0x18001d7b0  jns     short loc_18001D7B9
0x18001d7b2  xor     eax, eax
0x18001d7b4  jmp     loc_18001D8D3
0x18001d7b9  test    [rbp+2520h+var_2510], 2
0x18001d7bd  movzx   ebx, cl
0x18001d7c0  jz      short loc_18001D81B
0x18001d7c2  mov     rcx, rdi; pszPath
0x18001d7c5  call    cs:__imp_PathIsNetworkPathW
0x18001d7cb  xor     ecx, ecx
0x18001d7cd  test    eax, eax
0x18001d7cf  jz      short loc_18001D81B
0x18001d7d1  mov     [rsp+2620h+var_25E8], rcx
0x18001d7d6  lea     r8d, [rcx+4]
0x18001d7da  mov     [rsp+2620h+var_25F0], 1203h
0x18001d7e2  lea     r9, [rsp+2620h+hMem]
0x18001d7e7  mov     [rsp+2620h+var_25E0], ecx
0x18001d7eb  lea     rdx, [rsp+2620h+var_25E0]
0x18001d7f0  mov     dword ptr [rsp+2620h+hMem], ecx
0x18001d7f4  mov     rcx, rdi
0x18001d7f7  mov     [rsp+2620h+var_25F8], 1812h
0x18001d7ff  mov     [rsp+2620h+var_2600], r8d
0x18001d804  call    cs:__imp_ZoneCheckUrlExW
0x18001d80a  xor     ecx, ecx
0x18001d80c  test    eax, eax
0x18001d80e  js      short loc_18001D81B
0x18001d810  test    byte ptr [rsp+2620h+var_25E0], 0Fh
0x18001d815  lea     eax, [rcx+1]
0x18001d818  cmovnz  ebx, eax
0x18001d81b  mov     eax, [rsp+2620h+var_25D0]
0x18001d81f  test    sil, sil
0x18001d822  mov     [rsp+2620h+var_25BC], eax
0x18001d826  mov     eax, ecx
0x18001d828  setnz   al
0x18001d82b  mov     [rsp+2620h+var_25C0], ecx
0x18001d82f  mov     [rsp+2620h+var_25B8], eax
0x18001d833  mov     rcx, r12; pszPath
0x18001d836  lea     rax, [rbp+2520h+Buffer]
0x18001d83a  mov     [rsp+2620h+var_25B4], r13d
0x18001d83f  mov     [rsp+2620h+var_25B0], rax
0x18001d844  lea     rax, [rbp+2520h+pszPath]
0x18001d84b  mov     [rsp+2620h+var_25A8], rax
0x18001d850  call    cs:__imp_PathFindExtensionW
0x18001d856  xorps   xmm0, xmm0
0x18001d859  mov     [rbp+2520h+var_2590], rdi
0x18001d85d  mov     [rbp+2520h+var_25A0], rax
0x18001d861  lea     r8, [rsp+2620h+var_25C0]; struct SAFEOPENDLGPARAM *
0x18001d866  xor     ecx, ecx
0x18001d868  mov     [rbp+2520h+var_2574], r14d
0x18001d86c  xor     edi, edi
0x18001d86e  mov     [rbp+2520h+var_2530], rcx
0x18001d872  mov     rcx, [rsp+2620h+hWndParent]; hWndParent
0x18001d877  lea     rax, [rbp+2520h+var_20F0]
0x18001d87e  mov     [rbp+2520h+var_2598], rax
0x18001d882  xor     eax, eax
0x18001d884  mov     [rbp+2520h+var_256F], eax
0x18001d887  mov     [rbp+2520h+var_256B], ax
0x18001d88b  mov     [rbp+2520h+var_2569], al
0x18001d88e  lea     rax, [rbp+2520h+var_2520]
0x18001d892  mov     [rbp+2520h+var_2568], rax
0x18001d896  mov     [rbp+2520h+var_2588], rdi
0x18001d89a  mov     [rbp+2520h+var_2580], rdi
0x18001d89e  mov     [rbp+2520h+var_2578], edi
0x18001d8a1  mov     [rbp+2520h+var_2570], bl
0x18001d8a4  movups  [rbp+2520h+var_2560], xmm0
0x18001d8a8  movups  [rbp+2520h+var_2550], xmm0
0x18001d8ac  movups  [rbp+2520h+var_2540], xmm0
0x18001d8b0  call    ?_ShowSafeOpenDialog@@YAIPEAUHWND__@@IPEAUSAFEOPENDLGPARAM@@@Z; _ShowSafeOpenDialog(HWND__ *,uint,SAFEOPENDLGPARAM *)
0x18001d8b5  mov     ecx, eax
0x18001d8b7  lea     eax, [rdi+2]
0x18001d8ba  cmp     [rsp+2620h+var_25B4], eax
0x18001d8be  jnz     short loc_18001D8C3
0x18001d8c0  mov     [r15], eax
0x18001d8c3  cmp     ecx, 1
0x18001d8c6  jz      short loc_18001D8D3
0x18001d8c8  cmp     ecx, 1106h
0x18001d8ce  mov     eax, edi
0x18001d8d0  setz    al
0x18001d8d3  mov     rcx, [rbp+2520h+var_50]
0x18001d8da  xor     rcx, rsp; StackCookie
0x18001d8dd  call    __security_check_cookie
0x18001d8e2  add     rsp, 25E8h
0x18001d8e9  pop     r15
0x18001d8eb  pop     r14
0x18001d8ed  pop     r13
0x18001d8ef  pop     r12
0x18001d8f1  pop     rdi
0x18001d8f2  pop     rsi
0x18001d8f3  pop     rbx
0x18001d8f4  pop     rbp
0x18001d8f5  retn
```
