# W32TimeGetErrorInfoWrap(uint *,ulong *,unsigned __int64 *,unsigned __int64 *,long *,uint *,int *,ushort *,ulong,ushort *)

- ea: `0x180015784`
- end: `0x180015b5a`
- name: `?W32TimeGetErrorInfoWrap@@YAJPEAIPEAKPEA_K2PEAJ0PEAHPEAGK5@Z`
- size: `982`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int *, unsigned __int64 *, unsigned __int64 *, int *, unsigned int *, int *, PCWSTR pszFirst, unsigned int, PCWSTR psz1)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180015b60`

## callees

- `0x1800089c8`
- `0x180015784`
- `0x1800166b0`
- `0x180016818`
- `0x18002a010`

## import_xrefs

- `SHLWAPI!StrStrW` at `0x180015a78`
- `SHLWAPI!StrStrW` at `0x180015a92`
- `SHLWAPI!StrStrW` at `0x180015a78`
- `SHLWAPI!StrStrW` at `0x180015a92`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180015b41`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180015b41`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800158c7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800158dc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800158ed`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800158c7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800158dc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800158ed`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015805`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015876`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015805`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015876`

## string_xrefs

- `0x1800158a7`: `w32time.DLL`
- `0x1800157f3`: `SYSTEM\ControlSet001\Services\W32Time\Config`
- `0x180015864`: `SYSTEM\ControlSet001\Services\W32Time\Config`

## pseudocode

```c
__int64 __fastcall W32TimeGetErrorInfoWrap(
        unsigned int *a1,
        unsigned int *a2,
        unsigned __int64 *a3,
        unsigned __int64 *a4,
        int *a5,
        unsigned int *a6,
        int *a7,
        unsigned __int16 *pszFirst,
        unsigned int pvData,
        PCWSTR psz1)
{
  unsigned int v12; // ebx
  HMODULE LibraryW; // rax
  HMODULE v14; // r12
  FARPROC ProcAddress; // rsi
  FARPROC v16; // rdi
  FARPROC v17; // rax
  void (*v18)(void); // r14
  int v19; // eax
  __int64 v20; // rcx
  unsigned __int64 v21; // rdx
  unsigned int *v22; // r9
  unsigned int v23; // r8d
  unsigned int v24; // edi
  const WCHAR *v25; // rsi
  __int64 v26; // r14
  int v27; // eax
  __int64 v28; // rax
  __int64 v29; // rdx
  __int64 v30; // rcx
  const unsigned __int16 *v31; // r8
  PWSTR v32; // rax
  PWSTR v33; // rax
  int v34; // eax
  __int64 v35; // rcx
  __int64 v36; // rax
  DWORD pcbData[2]; // [rsp+40h] [rbp-28h] BYREF
  __int64 v39; // [rsp+48h] [rbp-20h] BYREF
  void (*v40)(void); // [rsp+50h] [rbp-18h]
  __int64 (__fastcall *v41)(_QWORD, _QWORD); // [rsp+58h] [rbp-10h]

  v12 = -2147467259;
  if ( !qword_18003AD08 )
  {
    pvData = 0;
    pcbData[0] = 4;
    if ( RegGetValueW(
           HKEY_LOCAL_MACHINE,
           L"SYSTEM\\ControlSet001\\Services\\W32Time\\Config",
           L"MaxPosPhaseCorrection",
           0x10u,
           0,
           &pvData,
           pcbData) )
    {
      qword_18003AD08 = 0x7FFFFFFFFFFFFFFFLL;
    }
    else
    {
      qword_18003AD08 = 10000000LL * pvData;
    }
  }
  if ( !qword_18003AD00 )
  {
    pvData = 0;
    pcbData[0] = 4;
    if ( RegGetValueW(
           HKEY_LOCAL_MACHINE,
           L"SYSTEM\\ControlSet001\\Services\\W32Time\\Config",
           L"MaxNegPhaseCorrection",
           0x10u,
           0,
           &pvData,
           pcbData) )
    {
      qword_18003AD00 = 0x8000000000000001uLL;
    }
    else
    {
      qword_18003AD00 = -10000000LL * pvData;
    }
  }
  LibraryW = IsolationAwareLoadLibraryW(L"w32time.DLL");
  v14 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, (LPCSTR)0x17);
    v41 = (__int64 (__fastcall *)(_QWORD, _QWORD))ProcAddress;
    v16 = GetProcAddress(v14, (LPCSTR)0x14);
    v17 = GetProcAddress(v14, (LPCSTR)0xC);
    v40 = (void (*)(void))v17;
    v18 = (void (*)(void))v17;
    if ( !v16 || !ProcAddress || !v17 )
      goto LABEL_44;
    *a3 = 0;
    *a4 = 0;
    *a1 = 0;
    *a5 = -2147467259;
    *pszFirst = 0;
    *(_QWORD *)pcbData = 0;
    *a2 = 0;
    *a6 = 0;
    *a7 = 0;
    v19 = ((__int64 (__fastcall *)(_QWORD, _QWORD, const wchar_t *, DWORD *))v16)(0, 0, L"NtpClient", pcbData);
    v12 = v19;
    if ( v19 )
    {
      if ( v19 > 0 )
        v12 = (unsigned __int16)v19 | 0x80070000;
      goto LABEL_44;
    }
    v20 = *(_QWORD *)pcbData;
    if ( !*(_QWORD *)pcbData )
    {
LABEL_44:
      FreeLibrary(v14);
      return v12;
    }
    v21 = 0;
    v22 = a6;
    v23 = -1;
    v12 = 0;
    *a5 = *(_DWORD *)(*(_QWORD *)pcbData + 4LL);
    v24 = 0;
    v25 = psz1;
    *a6 = *(_DWORD *)(v20 + 8);
    pvData = -1;
    v39 = 0;
    if ( *(_DWORD *)(v20 + 12) )
    {
      do
      {
        v26 = 56LL * v24;
        if ( !v25
          || (v27 = ComparePeers(v25, *(PCWSTR *)(*(_QWORD *)(v20 + 16) + v26 + 40)),
              v20 = *(_QWORD *)pcbData,
              v23 = pvData,
              v21 = v39,
              v27) )
        {
          v28 = *(_QWORD *)(v20 + 16);
          if ( v21 <= *(_QWORD *)(v28 + v26 + 16) )
          {
            v21 = *(_QWORD *)(v28 + v26 + 16);
            v23 = v24;
            v39 = v21;
            pvData = v24;
          }
        }
        ++v24;
      }
      while ( v24 < *(_DWORD *)(v20 + 12) );
      v18 = v40;
      v22 = a6;
    }
    if ( v23 < *(_DWORD *)(v20 + 12) && (v29 = *(_QWORD *)(v20 + 16)) != 0 )
    {
      v30 = 56LL * v23;
      *a1 = *(_DWORD *)(v30 + v29 + 4);
      *a2 = *(_DWORD *)(v30 + v29 + 32);
      *a3 = *(_QWORD *)(v30 + v29 + 8);
      v31 = *(const unsigned __int16 **)(v30 + v29 + 40);
      *a5 = *(_DWORD *)(v30 + v29 + 24);
      *v22 = *(_DWORD *)(v30 + v29 + 28);
      if ( v31 )
      {
        StringCchCopyW(pszFirst, 0x104u, v31);
        v32 = StrStrW(pszFirst, L" (");
        if ( v32 )
          *v32 = 0;
        v33 = StrStrW(pszFirst, L",");
        if ( v33 )
          *v33 = 0;
      }
      v39 = 0;
      v34 = v41(0, &v39);
      if ( v34 )
      {
        if ( v34 > 0 )
        {
          v12 = (unsigned __int16)v34 | 0x80070000;
          goto LABEL_40;
        }
      }
      else
      {
        v35 = v39;
        if ( v39 )
        {
          *a4 = *(_QWORD *)(v39 + 96);
          v36 = *(_QWORD *)(v35 + 64);
          if ( v36 < qword_18003AD00 || v36 > qword_18003AD08 )
            *a7 = 1;
          v18();
          goto LABEL_40;
        }
      }
      v12 = v34;
    }
    else
    {
      *a5 = -2147023436;
      if ( !v25 )
      {
LABEL_41:
        ((void (__fastcall *)(__int64))v18)(v20);
        goto LABEL_44;
      }
      StringCchCopyW(pszFirst, 0x104u, v25);
    }
LABEL_40:
    v20 = *(_QWORD *)pcbData;
    goto LABEL_41;
  }
  return v12;
}

```

## disassembly

```asm
0x180015784  mov     r11, rsp
0x180015787  mov     [r11+20h], r9
0x18001578b  mov     [r11+18h], r8
0x18001578f  mov     [r11+10h], rdx
0x180015793  mov     [r11+8], rcx
0x180015797  push    rbp
0x180015798  push    rbx
0x180015799  push    rsi
0x18001579a  push    rdi
0x18001579b  push    r12
0x18001579d  push    r13
0x18001579f  push    r14
0x1800157a1  push    r15
0x1800157a3  mov     rbp, rsp
0x1800157a6  sub     rsp, 68h
0x1800157aa  mov     esi, 4
0x1800157af  xor     edi, edi
0x1800157b1  cmp     cs:qword_18003AD08, rdi
0x1800157b8  mov     r15, r9
0x1800157bb  mov     r13, r8
0x1800157be  mov     ebx, 80004005h
0x1800157c3  mov     r12, 0FFFFFFFF80000002h
0x1800157ca  lea     r14d, [rsi+0Ch]
0x1800157ce  jnz     short loc_180015836
0x1800157d0  lea     rax, [rbp+var_28]
0x1800157d4  mov     [rbp+arg_40], edi
0x1800157da  mov     [r11-78h], rax
0x1800157de  lea     r8, aMaxposphasecor; "MaxPosPhaseCorrection"
0x1800157e5  lea     rax, [rbp+arg_40]
0x1800157ec  mov     [rbp+var_28], esi
0x1800157ef  mov     [r11-80h], rax
0x1800157f3  lea     rdx, aSystemControls; "SYSTEM\\ControlSet001\\Services\\W32Tim"...
0x1800157fa  mov     r9d, r14d; dwFlags
0x1800157fd  mov     [rsp+68h+pdwType], rdi; pdwType
0x180015802  mov     rcx, r12; hkey
0x180015805  call    cs:__imp_RegGetValueW
0x18001580b  test    eax, eax
0x18001580d  jnz     short loc_180015825
0x18001580f  mov     eax, [rbp+arg_40]
0x180015815  imul    rcx, rax, 989680h
0x18001581c  mov     cs:qword_18003AD08, rcx
0x180015823  jmp     short loc_180015836
0x180015825  mov     rax, 7FFFFFFFFFFFFFFFh
0x18001582f  mov     cs:qword_18003AD08, rax
0x180015836  cmp     cs:qword_18003AD00, rdi
0x18001583d  jnz     short loc_1800158A7
0x18001583f  lea     rax, [rbp+var_28]
0x180015843  mov     [rbp+arg_40], edi
0x180015849  mov     [rsp+68h+pcbData], rax; pcbData
0x18001584e  lea     r8, aMaxnegphasecor; "MaxNegPhaseCorrection"
0x180015855  lea     rax, [rbp+arg_40]
0x18001585c  mov     [rbp+var_28], esi
0x18001585f  mov     [rsp+68h+pvData], rax; pvData
0x180015864  lea     rdx, aSystemControls; "SYSTEM\\ControlSet001\\Services\\W32Tim"...
0x18001586b  mov     r9d, r14d; dwFlags
0x18001586e  mov     [rsp+68h+pdwType], rdi; pdwType
0x180015873  mov     rcx, r12; hkey
0x180015876  call    cs:__imp_RegGetValueW
0x18001587c  test    eax, eax
0x18001587e  jnz     short loc_180015896
0x180015880  mov     eax, [rbp+arg_40]
0x180015886  imul    rcx, rax, 0FFFFFFFFFF676980h
0x18001588d  mov     cs:qword_18003AD00, rcx
0x180015894  jmp     short loc_1800158A7
0x180015896  mov     rax, 8000000000000001h
0x1800158a0  mov     cs:qword_18003AD00, rax
0x1800158a7  lea     rcx, aW32timeDll; "w32time.DLL"
0x1800158ae  call    IsolationAwareLoadLibraryW
0x1800158b3  mov     r12, rax
0x1800158b6  test    rax, rax
0x1800158b9  jz      loc_180015B47
0x1800158bf  mov     edx, 17h; lpProcName
0x1800158c4  mov     rcx, rax; hModule
0x1800158c7  call    cs:__imp_GetProcAddress
0x1800158cd  mov     edx, 14h; lpProcName
0x1800158d2  mov     rcx, r12; hModule
0x1800158d5  mov     rsi, rax
0x1800158d8  mov     [rbp+var_10], rax
0x1800158dc  call    cs:__imp_GetProcAddress
0x1800158e2  mov     edx, 0Ch; lpProcName
0x1800158e7  mov     rcx, r12; hModule
0x1800158ea  mov     rdi, rax
0x1800158ed  call    cs:__imp_GetProcAddress
0x1800158f3  mov     [rbp+var_18], rax
0x1800158f7  mov     r14, rax
0x1800158fa  test    rdi, rdi
0x1800158fd  jz      loc_180015B3E
0x180015903  test    rsi, rsi
0x180015906  jz      loc_180015B3E
0x18001590c  xor     esi, esi
0x18001590e  test    rax, rax
0x180015911  jz      loc_180015B3E
0x180015917  mov     rax, [rbp+arg_0]
0x18001591b  lea     r9, [rbp+var_28]
0x18001591f  mov     [r13+0], rsi
0x180015923  lea     r8, aNtpclient; "NtpClient"
0x18001592a  mov     r13, [rbp+arg_20]
0x18001592e  xor     edx, edx
0x180015930  mov     [r15], rsi
0x180015933  xor     ecx, ecx
0x180015935  mov     r15, [rbp+pszFirst]
0x18001593c  mov     [rax], esi
0x18001593e  mov     rax, [rbp+arg_8]
0x180015942  mov     [r13+0], ebx
0x180015946  mov     [r15], si
0x18001594a  mov     qword ptr [rbp+var_28], rsi
0x18001594e  mov     [rax], esi
0x180015950  mov     rax, [rbp+arg_28]
0x180015954  mov     [rax], esi
0x180015956  mov     rax, [rbp+arg_30]
0x18001595a  mov     [rax], esi
0x18001595c  mov     rax, rdi
0x18001595f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015964  mov     ebx, eax
0x180015966  test    eax, eax
0x180015968  jnz     loc_180015B33
0x18001596e  mov     rcx, qword ptr [rbp+var_28]
0x180015972  test    rcx, rcx
0x180015975  jz      loc_180015B3E
0x18001597b  mov     eax, [rcx+4]
0x18001597e  mov     edx, esi
0x180015980  mov     r9, [rbp+arg_28]
0x180015984  or      r8d, 0FFFFFFFFh
0x180015988  mov     ebx, esi
0x18001598a  mov     [r13+0], eax
0x18001598e  mov     edi, esi
0x180015990  mov     eax, [rcx+8]
0x180015993  mov     rsi, [rbp+psz1]
0x18001599a  mov     [r9], eax
0x18001599d  mov     [rbp+arg_40], r8d
0x1800159a4  mov     [rbp+var_20], rdx
0x1800159a8  cmp     [rcx+0Ch], edx
0x1800159ab  jbe     short loc_180015A08
0x1800159ad  mov     eax, edi
0x1800159af  imul    r14, rax, 38h ; '8'
0x1800159b3  test    rsi, rsi
0x1800159b6  jz      short loc_1800159DC
0x1800159b8  mov     rdx, [rcx+10h]
0x1800159bc  mov     rcx, rsi; psz1
0x1800159bf  mov     rdx, [rdx+r14+28h]; psz2
0x1800159c4  call    ?ComparePeers@@YAHPEAG0@Z; ComparePeers(ushort *,ushort *)
0x1800159c9  mov     rcx, qword ptr [rbp+var_28]
0x1800159cd  mov     r8d, [rbp+arg_40]
0x1800159d4  mov     rdx, [rbp+var_20]
0x1800159d8  test    eax, eax
0x1800159da  jz      short loc_1800159F9
0x1800159dc  mov     rax, [rcx+10h]
0x1800159e0  cmp     rdx, [rax+r14+10h]
0x1800159e5  ja      short loc_1800159F9
0x1800159e7  mov     rdx, [rax+r14+10h]
0x1800159ec  mov     r8d, edi
0x1800159ef  mov     [rbp+var_20], rdx
0x1800159f3  mov     [rbp+arg_40], edi
0x1800159f9  inc     edi
0x1800159fb  cmp     edi, [rcx+0Ch]
0x1800159fe  jb      short loc_1800159AD
0x180015a00  mov     r14, [rbp+var_18]
0x180015a04  mov     r9, [rbp+arg_28]
0x180015a08  cmp     r8d, [rcx+0Ch]
0x180015a0c  jnb     loc_180015B08
0x180015a12  mov     rdx, [rcx+10h]
0x180015a16  test    rdx, rdx
0x180015a19  jz      loc_180015B08
0x180015a1f  mov     eax, r8d
0x180015a22  mov     r8, [rbp+arg_0]
0x180015a26  imul    rcx, rax, 38h ; '8'
0x180015a2a  mov     eax, [rcx+rdx+4]
0x180015a2e  mov     [r8], eax
0x180015a31  mov     r8, [rbp+arg_8]
0x180015a35  mov     eax, [rcx+rdx+20h]
0x180015a39  mov     [r8], eax
0x180015a3c  mov     r8, [rbp+arg_10]
0x180015a40  mov     rax, [rcx+rdx+8]
0x180015a45  mov     [r8], rax
0x180015a48  mov     eax, [rcx+rdx+18h]
0x180015a4c  mov     r8, [rcx+rdx+28h]; unsigned __int16 *
0x180015a51  mov     [r13+0], eax
0x180015a55  mov     eax, [rcx+rdx+1Ch]
0x180015a59  mov     [r9], eax
0x180015a5c  test    r8, r8
0x180015a5f  jz      short loc_180015AA2
0x180015a61  mov     edx, 104h; unsigned __int64
0x180015a66  mov     rcx, r15; unsigned __int16 *
0x180015a69  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180015a6e  lea     rdx, asc_18002F614; " ("
0x180015a75  mov     rcx, r15; pszFirst
0x180015a78  call    cs:__imp_StrStrW
0x180015a7e  test    rax, rax
0x180015a81  jz      short loc_180015A88
0x180015a83  xor     edx, edx
0x180015a85  mov     [rax], dx
0x180015a88  lea     rdx, asc_18002F324; ","
0x180015a8f  mov     rcx, r15; pszFirst
0x180015a92  call    cs:__imp_StrStrW
0x180015a98  test    rax, rax
0x180015a9b  jz      short loc_180015AA2
0x180015a9d  xor     ecx, ecx
0x180015a9f  mov     [rax], cx
0x180015aa2  mov     rax, [rbp+var_10]
0x180015aa6  lea     rdx, [rbp+var_20]
0x180015aaa  xor     ecx, ecx
0x180015aac  mov     [rbp+var_20], rbx
0x180015ab0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ab5  test    eax, eax
0x180015ab7  jnz     short loc_180015AF7
0x180015ab9  mov     rcx, [rbp+var_20]
0x180015abd  test    rcx, rcx
0x180015ac0  jz      short loc_180015AF9
0x180015ac2  mov     rax, [rcx+60h]
0x180015ac6  mov     rdx, [rbp+arg_18]
0x180015aca  mov     [rdx], rax
0x180015acd  mov     rax, [rcx+40h]
0x180015ad1  cmp     rax, cs:qword_18003AD00
0x180015ad8  jl      short loc_180015AE3
0x180015ada  cmp     rax, cs:qword_18003AD08
0x180015ae1  jle     short loc_180015AED
0x180015ae3  mov     rax, [rbp+arg_30]
0x180015ae7  mov     dword ptr [rax], 1
0x180015aed  mov     rax, r14
0x180015af0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015af5  jmp     short loc_180015B25
0x180015af7  jg      short loc_180015AFD
0x180015af9  mov     ebx, eax
0x180015afb  jmp     short loc_180015B25
0x180015afd  movzx   ebx, ax
0x180015b00  or      ebx, 80070000h
0x180015b06  jmp     short loc_180015B25
0x180015b08  mov     dword ptr [r13+0], 800705B4h
0x180015b10  test    rsi, rsi
0x180015b13  jz      short loc_180015B29
0x180015b15  mov     r8, rsi; unsigned __int16 *
0x180015b18  mov     edx, 104h; unsigned __int64
0x180015b1d  mov     rcx, r15; unsigned __int16 *
0x180015b20  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180015b25  mov     rcx, qword ptr [rbp+var_28]
0x180015b29  mov     rax, r14
0x180015b2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b31  jmp     short loc_180015B3E
0x180015b33  jle     short loc_180015B3E
0x180015b35  movzx   ebx, ax
0x180015b38  or      ebx, 80070000h
0x180015b3e  mov     rcx, r12; hLibModule
0x180015b41  call    cs:__imp_FreeLibrary
0x180015b47  mov     eax, ebx
0x180015b49  add     rsp, 68h
0x180015b4d  pop     r15
0x180015b4f  pop     r14
0x180015b51  pop     r13
0x180015b53  pop     r12
0x180015b55  pop     rdi
0x180015b56  pop     rsi
0x180015b57  pop     rbx
0x180015b58  pop     rbp
0x180015b59  retn
```
