# RegisterDLL(HINSTANCE__ *,_GUID,ushort *,ushort *,ushort *)

- ea: `0x1800349a0`
- end: `0x180034deb`
- name: `?RegisterDLL@@YAXPEAUHINSTANCE__@@U_GUID@@PEAG22@Z`
- size: `1099`
- prototype: `void __usercall(HINSTANCE hModule@<rcx>, GUID *rguid@<rdx>, LPCWSTR lpString@<r8>, unsigned __int16 *@<r9>, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000f5b4`
- `0x18001016c`
- `0x180011db4`
- `0x180011e40`
- `0x180013564`
- `0x180014120`
- `0x1800154d0`
- `0x180028de4`
- `0x1800349a0`
- `0x180044310`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180034bf4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180034bf4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180034b70`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180034c0c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180034c40`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180034d78`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180034b70`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180034c0c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180034c40`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180034d78`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180034a01`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180034a01`

## string_xrefs

- `0x180034a6e`: `SOFTWARE\CLASSES\CLSID\`
- `0x180034c5a`: `ThreadingModel`
- `0x180034d53`: `CLSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall RegisterDLL(
        HINSTANCE hModule,
        GUID *rguid,
        LPCWSTR lpString,
        unsigned __int16 *a4,
        unsigned __int16 *a5)
{
  signed int v7; // eax
  unsigned int v8; // ebx
  signed int v9; // eax
  unsigned int v10; // ebx
  signed int v11; // eax
  __int64 v12; // r8
  __int64 v13; // r9
  unsigned int v14; // ebx
  __int64 v15; // rdi
  int v16; // r15d
  int v17; // r8d
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 v20; // rsi
  int v21; // eax
  int v22; // r8d
  int v23; // eax
  int v24; // r8d
  signed int v25; // eax
  __int64 v26; // r8
  __int64 v27; // r9
  unsigned int v28; // ebx
  int v29; // r8d
  __int64 v30; // r14
  __int64 v31; // r8
  __int64 v32; // r9
  LPCWSTR v33; // rbx
  int v34; // eax
  int v35; // r8d
  __int64 v36; // [rsp+30h] [rbp-D0h]
  __int64 v37; // [rsp+30h] [rbp-D0h]
  __int64 v38; // [rsp+30h] [rbp-D0h]
  __int64 v39; // [rsp+30h] [rbp-D0h]
  LPCWSTR lpStringa; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v41; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v42; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v43[5]; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 v44[128]; // [rsp+90h] [rbp-70h] BYREF
  OLECHAR sz[128]; // [rsp+190h] [rbp+90h] BYREF
  unsigned __int16 v46[128]; // [rsp+290h] [rbp+190h] BYREF
  WCHAR Filename[264]; // [rsp+390h] [rbp+290h] BYREF

  lpStringa = a4;
  v41 = 0;
  v42 = 0;
  if ( StringFromGUID2(rguid, sz, 128) )
  {
    v7 = StringCchCopyW(v44, 0x80u, sz);
    v8 = v7;
    if ( v7 < 0 )
    {
      CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v7);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_a60f760638933c70bc5f9e1dc5005fb6_Traceguids, v8);
      }
    }
    v9 = StringCchCopyW(v46, 0x80u, L"SOFTWARE\\CLASSES\\CLSID\\");
    v10 = v9;
    if ( v9 < 0 )
    {
      CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v9);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_a60f760638933c70bc5f9e1dc5005fb6_Traceguids, v10);
      }
    }
    v11 = StringCchCatW(v46, 0x80u, v44);
    v14 = v11;
    if ( v11 < 0 )
    {
      CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v11);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_a60f760638933c70bc5f9e1dc5005fb6_Traceguids, v14);
      }
    }
    if ( !DLRegCreateKeyExW(-2147483646, (__int64)v46, v12, v13, 0, 0x2000000, v36, (__int64)&v41, 0) )
    {
      v15 = v41;
      v43[1] = v41;
      v16 = 2 * lstrlenW(lpString) + 2;
      DLRegSetValueExW(v41, 0, v17, 1, (__int64)lpString, v16);
      if ( !DLRegCreateKeyExW(v41, (__int64)L"InprocServer32", v18, v19, 0, 0x2000000, v37, (__int64)&v42, 0) )
      {
        v20 = v42;
        v43[2] = v42;
        Filename[260] = 48;
        if ( GetModuleFileNameW(hModule, Filename, 0x104u) )
        {
          v21 = lstrlenW(Filename);
          DLRegSetValueExW(v42, 0, v22, 1, (__int64)Filename, 2 * v21 + 2);
          v23 = lstrlenW(lpStringa);
          DLRegSetValueExW(v42, (unsigned int)L"ThreadingModel", v24, 1, (__int64)lpStringa, 2 * v23 + 2);
          if ( a5 )
          {
            v25 = StringCchPrintfW(v44, 0x80u, L"SOFTWARE\\CLASSES\\%s", a5);
            v28 = v25;
            if ( v25 < 0 )
            {
              CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v25);
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_a60f760638933c70bc5f9e1dc5005fb6_Traceguids, v28);
              }
            }
            v43[0] = 0;
            if ( !DLRegCreateKeyExW(-2147483646, (__int64)v44, v26, v27, 0, 0x2000000, v38, (__int64)v43, 0) )
            {
              v30 = v43[0];
              v43[3] = v43[0];
              DLRegSetValueExW(v43[0], 0, v29, 1, (__int64)lpString, v16);
              lpStringa = 0;
              if ( !DLRegCreateKeyExW(v43[0], (__int64)L"CLSID", v31, v32, 0, 0x2000000, v39, (__int64)&lpStringa, 0) )
              {
                v33 = lpStringa;
                v43[4] = (__int64)lpStringa;
                v34 = lstrlenW(sz);
                DLRegSetValueExW((_DWORD)lpStringa, 0, v35, 1, (__int64)sz, 2 * v34 + 2);
                DLRegCloseKey(v33);
              }
              DLRegCloseKey(v30);
            }
          }
        }
        DLRegCloseKey(v20);
      }
      DLRegCloseKey(v15);
    }
  }
}

```

## disassembly

```asm
0x1800349a0  push    rbp
0x1800349a2  push    rbx
0x1800349a3  push    rsi
0x1800349a4  push    rdi
0x1800349a5  push    r12
0x1800349a7  push    r13
0x1800349a9  push    r14
0x1800349ab  push    r15
0x1800349ad  lea     rbp, [rsp-4B8h]
0x1800349b5  sub     rsp, 5B8h
0x1800349bc  mov     rax, cs:__security_cookie
0x1800349c3  xor     rax, rsp
0x1800349c6  mov     [rbp+4F0h+var_50], rax
0x1800349cd  mov     [rsp+5F0h+lpString], r9
0x1800349d2  mov     r12, r8
0x1800349d5  mov     rax, rdx
0x1800349d8  mov     r13, rcx
0x1800349db  mov     r14, [rbp+4F0h+arg_20]
0x1800349e2  xor     esi, esi
0x1800349e4  mov     [rsp+5F0h+var_598], rsi
0x1800349e9  mov     [rsp+5F0h+var_590], rsi
0x1800349ee  mov     r15d, 80h
0x1800349f4  mov     r8d, r15d; cchMax
0x1800349f7  lea     rdx, [rbp+4F0h+sz]; lpsz
0x1800349fe  mov     rcx, rax; rguid
0x180034a01  call    cs:__imp_StringFromGUID2
0x180034a07  test    eax, eax
0x180034a09  jz      loc_180034DC8
0x180034a0f  lea     r8, [rbp+4F0h+sz]; unsigned __int16 *
0x180034a16  mov     edx, r15d; unsigned __int64
0x180034a19  lea     rcx, [rbp+4F0h+var_560]; unsigned __int16 *
0x180034a1d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z
0x180034a22  mov     ebx, eax
0x180034a24  mov     dil, 2
0x180034a27  test    eax, eax
0x180034a29  jns     short loc_180034A6E
0x180034a2b  mov     edx, eax; int
0x180034a2d  lea     rcx, qword_18006A9C0; this
0x180034a34  call    ?Write@CMemoryLog@@QEAAXJ@Z
0x180034a39  mov     rcx, cs:WPP_GLOBAL_Control
0x180034a40  lea     rax, WPP_GLOBAL_Control
0x180034a47  cmp     rcx, rax
0x180034a4a  jz      short loc_180034A6E
0x180034a4c  test    byte ptr [rcx+1Ch], 1
0x180034a50  jz      short loc_180034A6E
0x180034a52  cmp     [rcx+19h], dil
0x180034a56  jb      short loc_180034A6E
0x180034a58  lea     edx, [rsi+0Ah]
0x180034a5b  mov     r9d, ebx
0x180034a5e  lea     r8, WPP_a60f760638933c70bc5f9e1dc5005fb6_Traceguids
0x180034a65  mov     rcx, [rcx+10h]
0x180034a69  call    WPP_SF_D
0x180034a6e  lea     r8, aSoftwareClasse_0
0x180034a75  mov     rdx, r15; unsigned __int64
0x180034a78  lea     rcx, [rbp+4F0h+var_360]; unsigned __int16 *
0x180034a7f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z
0x180034a84  mov     ebx, eax
0x180034a86  test    eax, eax
0x180034a88  jns     short loc_180034ACF
0x180034a8a  mov     edx, eax; int
0x180034a8c  lea     rcx, qword_18006A9C0; this
0x180034a93  call    ?Write@CMemoryLog@@QEAAXJ@Z
0x180034a98  mov     rcx, cs:WPP_GLOBAL_Control
0x180034a9f  lea     rax, WPP_GLOBAL_Control
0x180034aa6  cmp     rcx, rax
0x180034aa9  jz      short loc_180034ACF
0x180034aab  test    byte ptr [rcx+1Ch], 1
0x180034aaf  jz      short loc_180034ACF
0x180034ab1  cmp     [rcx+19h], dil
0x180034ab5  jb      short loc_180034ACF
0x180034ab7  mov     edx, 0Bh
0x180034abc  mov     r9d, ebx
0x180034abf  lea     r8, WPP_a60f760638933c70bc5f9e1dc5005fb6_Traceguids
0x180034ac6  mov     rcx, [rcx+10h]
0x180034aca  call    WPP_SF_D
0x180034acf  lea     r8, [rbp+4F0h+var_560]; unsigned __int16 *
0x180034ad3  mov     rdx, r15; unsigned __int64
0x180034ad6  lea     rcx, [rbp+4F0h+var_360]; unsigned __int16 *
0x180034add  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z
0x180034ae2  mov     ebx, eax
0x180034ae4  test    eax, eax
0x180034ae6  jns     short loc_180034B2D
0x180034ae8  mov     edx, eax; int
0x180034aea  lea     rcx, qword_18006A9C0; this
0x180034af1  call    ?Write@CMemoryLog@@QEAAXJ@Z
0x180034af6  mov     rcx, cs:WPP_GLOBAL_Control
0x180034afd  lea     rax, WPP_GLOBAL_Control
0x180034b04  cmp     rcx, rax
0x180034b07  jz      short loc_180034B2D
0x180034b09  test    byte ptr [rcx+1Ch], 1
0x180034b0d  jz      short loc_180034B2D
0x180034b0f  cmp     [rcx+19h], dil
0x180034b13  jb      short loc_180034B2D
0x180034b15  mov     edx, 0Ch
0x180034b1a  mov     r9d, ebx
0x180034b1d  lea     r8, WPP_a60f760638933c70bc5f9e1dc5005fb6_Traceguids
0x180034b24  mov     rcx, [rcx+10h]
0x180034b28  call    WPP_SF_D
0x180034b2d  mov     [rsp+5F0h+var_5B0], rsi
0x180034b32  lea     rax, [rsp+5F0h+var_598]
0x180034b37  mov     [rsp+5F0h+var_5B8], rax
0x180034b3c  mov     [rsp+5F0h+var_5C8], 2000000h
0x180034b44  mov     dword ptr [rsp+5F0h+var_5D0], esi
0x180034b48  lea     rdx, [rbp+4F0h+var_360]
0x180034b4f  mov     rcx, 0FFFFFFFF80000002h
0x180034b56  call    DLRegCreateKeyExW
0x180034b5b  test    eax, eax
0x180034b5d  jnz     loc_180034DC8
0x180034b63  mov     rdi, [rsp+5F0h+var_598]
0x180034b68  mov     [rsp+5F0h+var_580], rdi
0x180034b6d  mov     rcx, r12; lpString
0x180034b70  call    cs:__imp_lstrlenW
0x180034b76  lea     r15d, ds:2[rax*2]
0x180034b7e  mov     [rsp+5F0h+var_5C8], r15d
0x180034b83  mov     [rsp+5F0h+var_5D0], r12
0x180034b88  mov     ebx, 1
0x180034b8d  mov     r9d, ebx
0x180034b90  xor     edx, edx
0x180034b92  mov     rcx, [rsp+5F0h+var_598]
0x180034b97  call    DLRegSetValueExW
0x180034b9c  mov     [rsp+5F0h+var_5B0], rsi
0x180034ba1  lea     rax, [rsp+5F0h+var_590]
0x180034ba6  mov     [rsp+5F0h+var_5B8], rax
0x180034bab  mov     [rsp+5F0h+var_5C8], 2000000h
0x180034bb3  mov     dword ptr [rsp+5F0h+var_5D0], esi
0x180034bb7  lea     rdx, aInprocserver32
0x180034bbe  mov     rcx, [rsp+5F0h+var_598]
0x180034bc3  call    DLRegCreateKeyExW
0x180034bc8  test    eax, eax
0x180034bca  jnz     loc_180034DC0
0x180034bd0  mov     rsi, [rsp+5F0h+var_590]
0x180034bd5  mov     [rsp+5F0h+var_578], rsi
0x180034bda  lea     eax, [rbx+2Fh]
0x180034bdd  mov     [rbp+4F0h+var_58], ax
0x180034be4  mov     r8d, 104h; nSize
0x180034bea  lea     rdx, [rbp+4F0h+Filename]; lpFilename
0x180034bf1  mov     rcx, r13; hModule
0x180034bf4  call    cs:__imp_GetModuleFileNameW
0x180034bfa  xor     r13d, r13d
0x180034bfd  test    eax, eax
0x180034bff  jz      loc_180034DB7
0x180034c05  lea     rcx, [rbp+4F0h+Filename]; lpString
0x180034c0c  call    cs:__imp_lstrlenW
0x180034c12  lea     eax, ds:2[rax*2]
0x180034c19  mov     [rsp+5F0h+var_5C8], eax
0x180034c1d  lea     rax, [rbp+4F0h+Filename]
0x180034c24  mov     [rsp+5F0h+var_5D0], rax
0x180034c29  mov     r9d, ebx
0x180034c2c  xor     edx, edx
0x180034c2e  mov     rcx, [rsp+5F0h+var_590]
0x180034c33  call    DLRegSetValueExW
0x180034c38  mov     rbx, [rsp+5F0h+lpString]
0x180034c3d  mov     rcx, rbx; lpString
0x180034c40  call    cs:__imp_lstrlenW
0x180034c46  lea     eax, ds:2[rax*2]
0x180034c4d  mov     [rsp+5F0h+var_5C8], eax
0x180034c51  mov     [rsp+5F0h+var_5D0], rbx
0x180034c56  lea     r9d, [r13+1]
0x180034c5a  lea     rdx, aThreadingmodel
0x180034c61  mov     rcx, [rsp+5F0h+var_590]
0x180034c66  call    DLRegSetValueExW
0x180034c6b  test    r14, r14
0x180034c6e  jz      loc_180034DB7
0x180034c74  mov     r9, r14
0x180034c77  lea     r8, aSoftwareClasse
0x180034c7e  mov     edx, 80h; unsigned __int64
0x180034c83  lea     rcx, [rbp+4F0h+var_560]; unsigned __int16 *
0x180034c87  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ
0x180034c8c  mov     ebx, eax
0x180034c8e  test    eax, eax
0x180034c90  jns     short loc_180034CD6
0x180034c92  mov     edx, eax; int
0x180034c94  lea     rcx, qword_18006A9C0; this
0x180034c9b  call    ?Write@CMemoryLog@@QEAAXJ@Z
0x180034ca0  mov     rcx, cs:WPP_GLOBAL_Control
0x180034ca7  lea     rax, WPP_GLOBAL_Control
0x180034cae  cmp     rcx, rax
0x180034cb1  jz      short loc_180034CD6
0x180034cb3  test    byte ptr [rcx+1Ch], 1
0x180034cb7  jz      short loc_180034CD6
0x180034cb9  cmp     byte ptr [rcx+19h], 2
0x180034cbd  jb      short loc_180034CD6
0x180034cbf  lea     edx, [r13+0Dh]
0x180034cc3  mov     r9d, ebx
0x180034cc6  lea     r8, WPP_a60f760638933c70bc5f9e1dc5005fb6_Traceguids
0x180034ccd  mov     rcx, [rcx+10h]
0x180034cd1  call    WPP_SF_D
0x180034cd6  mov     [rsp+5F0h+var_588], r13
0x180034cdb  mov     [rsp+5F0h+var_5B0], r13
0x180034ce0  lea     rax, [rsp+5F0h+var_588]
0x180034ce5  mov     [rsp+5F0h+var_5B8], rax
0x180034cea  mov     ebx, 2000000h
0x180034cef  mov     [rsp+5F0h+var_5C8], ebx
0x180034cf3  mov     dword ptr [rsp+5F0h+var_5D0], r13d
0x180034cf8  lea     rdx, [rbp+4F0h+var_560]
0x180034cfc  mov     rcx, 0FFFFFFFF80000002h
0x180034d03  call    DLRegCreateKeyExW
0x180034d08  test    eax, eax
0x180034d0a  jnz     loc_180034DB7
0x180034d10  mov     r14, [rsp+5F0h+var_588]
0x180034d15  mov     [rbp+4F0h+var_570], r14
0x180034d19  mov     [rsp+5F0h+var_5C8], r15d
0x180034d1e  mov     [rsp+5F0h+var_5D0], r12
0x180034d23  lea     r15d, [rax+1]
0x180034d27  mov     r9d, r15d
0x180034d2a  xor     edx, edx
0x180034d2c  mov     rcx, [rsp+5F0h+var_588]
0x180034d31  call    DLRegSetValueExW
0x180034d36  mov     [rsp+5F0h+lpString], r13
0x180034d3b  mov     [rsp+5F0h+var_5B0], r13
0x180034d40  lea     rax, [rsp+5F0h+lpString]
0x180034d45  mov     [rsp+5F0h+var_5B8], rax
0x180034d4a  mov     [rsp+5F0h+var_5C8], ebx
0x180034d4e  mov     dword ptr [rsp+5F0h+var_5D0], r13d
0x180034d53  lea     rdx, aClsid
0x180034d5a  mov     rcx, [rsp+5F0h+var_588]
0x180034d5f  call    DLRegCreateKeyExW
0x180034d64  test    eax, eax
0x180034d66  jnz     short loc_180034DAE
0x180034d68  mov     rbx, [rsp+5F0h+lpString]
0x180034d6d  mov     [rbp+4F0h+var_568], rbx
0x180034d71  lea     rcx, [rbp+4F0h+sz]; lpString
0x180034d78  call    cs:__imp_lstrlenW
0x180034d7e  lea     eax, ds:2[rax*2]
0x180034d85  mov     [rsp+5F0h+var_5C8], eax
0x180034d89  lea     rax, [rbp+4F0h+sz]
0x180034d90  mov     [rsp+5F0h+var_5D0], rax
0x180034d95  mov     r9d, r15d
0x180034d98  xor     edx, edx
0x180034d9a  mov     rcx, [rsp+5F0h+lpString]
0x180034d9f  call    DLRegSetValueExW
0x180034da4  nop
0x180034da5  mov     rcx, rbx
0x180034da8  call    DLRegCloseKey
0x180034dad  nop
0x180034dae  mov     rcx, r14
0x180034db1  call    DLRegCloseKey
0x180034db6  nop
0x180034db7  mov     rcx, rsi
0x180034dba  call    DLRegCloseKey
0x180034dbf  nop
0x180034dc0  mov     rcx, rdi
0x180034dc3  call    DLRegCloseKey
0x180034dc8  mov     rcx, [rbp+4F0h+var_50]
0x180034dcf  xor     rcx, rsp; StackCookie
0x180034dd2  call    __security_check_cookie
0x180034dd7  add     rsp, 5B8h
0x180034dde  pop     r15
0x180034de0  pop     r14
0x180034de2  pop     r13
0x180034de4  pop     r12
0x180034de6  pop     rdi
0x180034de7  pop     rsi
0x180034de8  pop     rbx
0x180034de9  pop     rbp
0x180034dea  retn
```
