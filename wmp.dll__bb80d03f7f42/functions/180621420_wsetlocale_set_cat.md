# _wsetlocale_set_cat

- ea: `0x180621420`
- end: `0x180621bfc`
- name: `_wsetlocale_set_cat`
- size: `2012`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x180621338`

## callees

- `0x180007b30`
- `0x18000ef70`
- `0x180054c60`
- `0x1800b42dc`
- `0x18010b5d4`
- `0x180159890`
- `0x18015a7a0`
- `0x180184410`
- `0x1801b79bc`
- `0x1801ccb4c`
- `0x180287848`
- `0x1806177a0`
- `0x180621420`
- `0x18062346c`
- `0x18074be40`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x18062158c`
- `KERNEL32!LoadLibraryW` at `0x180621687`
- `KERNEL32!LoadLibraryW` at `0x18062158c`
- `KERNEL32!LoadLibraryW` at `0x180621687`
- `KERNEL32!GetProcAddress` at `0x1806215b2`
- `KERNEL32!GetProcAddress` at `0x1806215cf`
- `KERNEL32!GetProcAddress` at `0x1806215e8`
- `KERNEL32!GetProcAddress` at `0x180621605`
- `KERNEL32!GetProcAddress` at `0x18062161e`
- `KERNEL32!GetProcAddress` at `0x18062163e`
- `KERNEL32!GetProcAddress` at `0x1806216ad`
- `KERNEL32!GetProcAddress` at `0x1806216c6`
- `KERNEL32!GetProcAddress` at `0x1806216e0`
- `KERNEL32!GetProcAddress` at `0x1806216fa`
- `KERNEL32!GetProcAddress` at `0x1806215b2`
- `KERNEL32!GetProcAddress` at `0x1806215cf`
- `KERNEL32!GetProcAddress` at `0x1806215e8`
- `KERNEL32!GetProcAddress` at `0x180621605`
- `KERNEL32!GetProcAddress` at `0x18062161e`
- `KERNEL32!GetProcAddress` at `0x18062163e`
- `KERNEL32!GetProcAddress` at `0x1806216ad`
- `KERNEL32!GetProcAddress` at `0x1806216c6`
- `KERNEL32!GetProcAddress` at `0x1806216e0`
- `KERNEL32!GetProcAddress` at `0x1806216fa`
- `KERNEL32!GetLastError` at `0x18062181f`
- `KERNEL32!GetLastError` at `0x180621897`
- `KERNEL32!GetLastError` at `0x1806219f1`
- `KERNEL32!GetLastError` at `0x180621a4b`
- `KERNEL32!GetLastError` at `0x180621b1c`
- `KERNEL32!GetLastError` at `0x180621b49`
- `KERNEL32!GetLastError` at `0x180621b7d`
- `KERNEL32!GetLastError` at `0x18062181f`
- `KERNEL32!GetLastError` at `0x180621897`
- `KERNEL32!GetLastError` at `0x1806219f1`
- `KERNEL32!GetLastError` at `0x180621a4b`
- `KERNEL32!GetLastError` at `0x180621b1c`
- `KERNEL32!GetLastError` at `0x180621b49`
- `KERNEL32!GetLastError` at `0x180621b7d`
- `KERNEL32!FreeLibrary` at `0x180621b3b`
- `KERNEL32!FreeLibrary` at `0x180621b68`
- `KERNEL32!FreeLibrary` at `0x180621b3b`
- `KERNEL32!FreeLibrary` at `0x180621b68`

## string_xrefs

- `0x180621585`: `iphlpapi.dll`
- `0x1806215a8`: `IcmpCreateFile`
- `0x1806215be`: `Icmp6CreateFile`
- `0x180621680`: `ws2_32.dll`
- `0x1806216b9`: `WSACleanup`

## pseudocode

```c
__int64 __fastcall wsetlocale_set_cat(__int64 a1, int a2, _DWORD *a3)
{
  signed int v5; // ebx
  int i; // edi
  __int64 v7; // r9
  signed int v8; // eax
  PVOID *v9; // rcx
  HMODULE LibraryW; // rax
  HMODULE v11; // r13
  HANDLE (__stdcall *IcmpCreateFile)(); // rbx
  HANDLE (__stdcall *Icmp6CreateFile)(); // r15
  BOOL (__stdcall *IcmpCloseHandle)(HANDLE); // rdi
  DWORD (__stdcall *IcmpSendEcho)(HANDLE, IPAddr, LPVOID, WORD, PIP_OPTION_INFORMATION, LPVOID, DWORD, DWORD); // r12
  DWORD (__stdcall *Icmp6SendEcho2)(HANDLE, HANDLE, FARPROC, PVOID, struct sockaddr_in6 *, struct sockaddr_in6 *, LPVOID, WORD, PIP_OPTION_INFORMATION, LPVOID, DWORD, DWORD); // r14
  DWORD (__stdcall *GetBestInterfaceEx)(struct sockaddr *, PDWORD); // rax
  DWORD (__stdcall *v18)(struct sockaddr *, PDWORD); // r13
  int v19; // edi
  HMODULE v20; // rax
  HMODULE v21; // r14
  int (__stdcall *WSAStartup)(WORD, LPWSADATA); // rbx
  INT (__stdcall *GetAddrInfoW)(PCWSTR, PCWSTR, const ADDRINFOW *, PADDRINFOW *); // r14
  void (__stdcall *FreeAddrInfoW)(PADDRINFOW); // rax
  signed int v25; // eax
  bool v26; // cc
  int v27; // ecx
  int v28; // eax
  int v29; // ecx
  __int64 v30; // rax
  HANDLE v31; // rdi
  char v32; // r14
  signed int v33; // eax
  int v34; // r8d
  _QWORD *v35; // rcx
  int v36; // edx
  signed int v37; // eax
  _QWORD *v38; // rcx
  int v39; // edx
  int v40; // eax
  signed int v41; // eax
  signed int LastError; // eax
  const WCHAR *v44; // [rsp+70h] [rbp-90h] BYREF
  int v45; // [rsp+78h] [rbp-88h]
  __int16 v46; // [rsp+7Ch] [rbp-84h]
  __int64 v47; // [rsp+80h] [rbp-80h] BYREF
  __int64 (*v48)(void); // [rsp+88h] [rbp-78h] BYREF
  int v49; // [rsp+90h] [rbp-70h]
  BOOL (__stdcall *v50)(HANDLE); // [rsp+98h] [rbp-68h]
  int (__stdcall *WSACleanup)(); // [rsp+A0h] [rbp-60h]
  HMODULE hModule; // [rsp+A8h] [rbp-58h]
  void (__stdcall *v53)(PADDRINFOW); // [rsp+B0h] [rbp-50h]
  HMODULE hLibModule; // [rsp+B8h] [rbp-48h]
  _OWORD v55[3]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v56[416]; // [rsp+F0h] [rbp-10h] BYREF
  DWORD (__stdcall *v57)(HANDLE, HANDLE, FARPROC, PVOID, struct sockaddr_in6 *, struct sockaddr_in6 *, LPVOID, WORD, PIP_OPTION_INFORMATION, LPVOID, DWORD, DWORD); // [rsp+290h] [rbp+190h] BYREF
  _OWORD v58[3]; // [rsp+298h] [rbp+198h] BYREF
  _BYTE v59[8]; // [rsp+2C8h] [rbp+1C8h] BYREF
  _BYTE v60[80]; // [rsp+2D0h] [rbp+1D0h] BYREF

  v49 = a2;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  if ( RequestContext != &RequestContext
    && (*((_BYTE *)RequestContext + 28) & 1) != 0
    && *((_BYTE *)RequestContext + 25) >= 7u )
  {
    sub_180184410(*((_QWORD *)RequestContext + 2), 17, &stru_180863630);
  }
  *a3 = 0;
  if ( (unsigned __int8)sub_1801CCB4C(a1) )
  {
    v5 = sub_180054C60(a1, 0, &v44);
    if ( v5 >= 0 )
    {
      if ( sub_18010B5D4(&v44) >= 3 && *v44 == 92 && v44[1] == 92 )
      {
        for ( i = 2; i <= sub_18010B5D4(&v44); ++i )
        {
          if ( v44[i] == 92 )
          {
            v44[i] = 0;
            v8 = sub_180007B30((BSTR *)&v44, v44 + 2, 0xFFFFFFFFLL, v7);
            goto LABEL_17;
          }
        }
      }
      else
      {
        v5 = -2147024809;
      }
    }
  }
  else
  {
    v8 = sub_1806177A0(a1, &v44);
LABEL_17:
    v5 = v8;
  }
  v9 = (PVOID *)RequestContext;
  if ( RequestContext != &RequestContext
    && (*((_BYTE *)RequestContext + 28) & 1) != 0
    && *((_BYTE *)RequestContext + 25) >= 7u )
  {
    sub_1800B42DC(*((_QWORD *)RequestContext + 2), 18, &stru_180863630, v44);
    v9 = (PVOID *)RequestContext;
  }
  if ( v5 >= 0 )
  {
    LibraryW = LoadLibraryW(L"iphlpapi.dll");
    hLibModule = LibraryW;
    v11 = LibraryW;
    if ( !LibraryW )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_105;
    }
    IcmpCreateFile = (HANDLE (__stdcall *)())GetProcAddress(LibraryW, "IcmpCreateFile");
    v48 = (__int64 (*)(void))IcmpCreateFile;
    Icmp6CreateFile = (HANDLE (__stdcall *)())GetProcAddress(v11, "Icmp6CreateFile");
    IcmpCloseHandle = (BOOL (__stdcall *)(HANDLE))GetProcAddress(v11, "IcmpCloseHandle");
    v50 = IcmpCloseHandle;
    IcmpSendEcho = (DWORD (__stdcall *)(HANDLE, IPAddr, LPVOID, WORD, PIP_OPTION_INFORMATION, LPVOID, DWORD, DWORD))GetProcAddress(v11, "IcmpSendEcho");
    Icmp6SendEcho2 = (DWORD (__stdcall *)(HANDLE, HANDLE, FARPROC, PVOID, struct sockaddr_in6 *, struct sockaddr_in6 *, LPVOID, WORD, PIP_OPTION_INFORMATION, LPVOID, DWORD, DWORD))GetProcAddress(v11, "Icmp6SendEcho2");
    v57 = Icmp6SendEcho2;
    GetBestInterfaceEx = (DWORD (__stdcall *)(struct sockaddr *, PDWORD))GetProcAddress(v11, "GetBestInterfaceEx");
    v18 = GetBestInterfaceEx;
    if ( !IcmpCreateFile
      || !IcmpCloseHandle
      || !IcmpSendEcho
      || (!Icmp6CreateFile || !Icmp6SendEcho2 || !GetBestInterfaceEx ? (v19 = 0) : (v19 = 1),
          v20 = LoadLibraryW(L"ws2_32.dll"),
          hModule = v20,
          (v21 = v20) == 0) )
    {
      v41 = GetLastError();
      v5 = v41;
      if ( v41 > 0 )
        v5 = (unsigned __int16)v41 | 0x80070000;
      goto LABEL_102;
    }
    WSAStartup = (int (__stdcall *)(WORD, LPWSADATA))GetProcAddress(v20, "WSAStartup");
    WSACleanup = (int (__stdcall *)())GetProcAddress(v21, "WSACleanup");
    GetAddrInfoW = (INT (__stdcall *)(PCWSTR, PCWSTR, const ADDRINFOW *, PADDRINFOW *))GetProcAddress(
                                                                                         v21,
                                                                                         "GetAddrInfoW");
    FreeAddrInfoW = (void (__stdcall *)(PADDRINFOW))GetProcAddress(hModule, "FreeAddrInfoW");
    v53 = FreeAddrInfoW;
    if ( WSAStartup && WSACleanup && GetAddrInfoW && FreeAddrInfoW )
    {
      memset(v56, 0, 0x198u);
      v25 = ((__int64 (__fastcall *)(__int64, _BYTE *))WSAStartup)(514, v56);
      v5 = v25;
      v26 = v25 <= 0;
      if ( !v25 )
      {
        memset(v55, 0, sizeof(v55));
        v5 = 0;
        v47 = 0;
        v27 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 4));
        if ( !v19 )
          v27 = 2;
        DWORD1(v55[0]) = v27;
        v28 = ((__int64 (__fastcall *)(const WCHAR *, _QWORD, _OWORD *, __int64 *))GetAddrInfoW)(v44, 0, v55, &v47);
        if ( v28 )
        {
          if ( v28 > 0 )
            v5 = (unsigned __int16)v28 | 0x80070000;
          else
            v5 = v28;
          if ( RequestContext != &RequestContext
            && (*((_BYTE *)RequestContext + 28) & 1) != 0
            && *((_BYTE *)RequestContext + 25) >= 2u )
          {
            sub_1801B79BC(*((_QWORD *)RequestContext + 2), 24, &stru_180863630, (unsigned int)v28, v5);
          }
          goto LABEL_95;
        }
        v29 = *(_DWORD *)(v47 + 4);
        if ( v29 == 2 )
        {
          v30 = v48();
          v31 = (HANDLE)v30;
          if ( v30 != -1 )
          {
            v32 = v49;
            if ( ((unsigned int (__fastcall *)(__int64, _QWORD, DWORD (__stdcall **)(HANDLE, HANDLE, FARPROC, PVOID, struct sockaddr_in6 *, struct sockaddr_in6 *, LPVOID, WORD, PIP_OPTION_INFORMATION, LPVOID, DWORD, DWORD), __int64, _QWORD, _OWORD *, int, int))IcmpSendEcho)(
                   v30,
                   *(unsigned int *)(*(_QWORD *)(v47 + 32) + 4LL),
                   &v57,
                   8,
                   0,
                   v58,
                   48,
                   v49) )
            {
              goto LABEL_53;
            }
            *a3 = 1;
            v33 = GetLastError();
            v5 = v33 > 0 ? (unsigned __int16)v33 | 0x80070000 : v33;
            if ( v5 >= 0 )
              goto LABEL_53;
            v35 = RequestContext;
            if ( RequestContext == &RequestContext
              || (*((_BYTE *)RequestContext + 28) & 1) == 0
              || *((_BYTE *)RequestContext + 25) < 2u )
            {
              goto LABEL_53;
            }
            v36 = 19;
LABEL_52:
            sub_18062346C(v35[2], v36, v34, (_DWORD)v44, v32, v33, v5);
LABEL_53:
            ((void (__fastcall *)(HANDLE))v50)(v31);
LABEL_87:
            ((void (__fastcall *)(__int64))v53)(v47);
LABEL_95:
            WSACleanup();
LABEL_99:
            FreeLibrary(hModule);
LABEL_102:
            FreeLibrary(hLibModule);
LABEL_105:
            v9 = (PVOID *)RequestContext;
            goto LABEL_106;
          }
          *a3 = 1;
          v37 = GetLastError();
          if ( v37 > 0 )
            v5 = (unsigned __int16)v37 | 0x80070000;
          else
            v5 = v37;
          if ( v5 >= 0 )
            goto LABEL_87;
          v38 = RequestContext;
          if ( RequestContext == &RequestContext
            || (*((_BYTE *)RequestContext + 28) & 1) == 0
            || *((_BYTE *)RequestContext + 25) < 2u )
          {
            goto LABEL_87;
          }
          v39 = 20;
        }
        else
        {
          if ( v29 != 23 || !v19 )
          {
            v5 = -2147467259;
            goto LABEL_87;
          }
          v31 = Icmp6CreateFile();
          if ( v31 != (HANDLE)-1LL )
          {
            LODWORD(v48) = 0;
            memset(v58, 0, 28);
            if ( ((unsigned int (__fastcall *)(_QWORD, __int64 (**)(void)))v18)(*(_QWORD *)(v47 + 32), &v48) )
            {
              v40 = 0;
              LODWORD(v48) = 0;
            }
            else
            {
              v40 = (int)v48;
            }
            v32 = v49;
            memset(v58, 0, 28);
            LOWORD(v58[0]) = 23;
            DWORD2(v58[1]) = v40 & 0xFFFFFFF | 0x10000000;
            if ( ((unsigned int (__fastcall *)(HANDLE, _QWORD, _QWORD, _QWORD, _OWORD *, _QWORD, _BYTE *, __int16, _QWORD, _BYTE *, int, int))v57)(
                   v31,
                   0,
                   0,
                   0,
                   v58,
                   *(_QWORD *)(v47 + 32),
                   v59,
                   8,
                   0,
                   v60,
                   76,
                   v49) )
            {
              goto LABEL_53;
            }
            *a3 = 1;
            v33 = GetLastError();
            v5 = v33 > 0 ? (unsigned __int16)v33 | 0x80070000 : v33;
            if ( v5 >= 0 )
              goto LABEL_53;
            v35 = RequestContext;
            if ( RequestContext == &RequestContext
              || (*((_BYTE *)RequestContext + 28) & 1) == 0
              || *((_BYTE *)RequestContext + 25) < 2u )
            {
              goto LABEL_53;
            }
            v36 = 21;
            goto LABEL_52;
          }
          v37 = GetLastError();
          if ( v37 > 0 )
            v5 = (unsigned __int16)v37 | 0x80070000;
          else
            v5 = v37;
          if ( v5 >= 0 )
            goto LABEL_87;
          v38 = RequestContext;
          if ( RequestContext == &RequestContext
            || (*((_BYTE *)RequestContext + 28) & 1) == 0
            || *((_BYTE *)RequestContext + 25) < 2u )
          {
            goto LABEL_87;
          }
          v39 = 23;
        }
        sub_180287848(v38[2], v39, (unsigned int)&stru_180863630, (_DWORD)v44, v37, v5);
        goto LABEL_87;
      }
    }
    else
    {
      v25 = GetLastError();
      v5 = v25;
      v26 = v25 <= 0;
    }
    if ( !v26 )
      v5 = (unsigned __int16)v25 | 0x80070000;
    goto LABEL_99;
  }
LABEL_106:
  if ( v9 != &RequestContext && (*((_BYTE *)v9 + 28) & 1) != 0 && *((_BYTE *)v9 + 25) >= 7u )
    sub_180184410(v9[2], 25, &stru_180863630);
  sub_18000EF70(&v44);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180621420  mov     [rsp-8+arg_18], rbx
0x180621425  push    rbp
0x180621426  push    rsi
0x180621427  push    rdi
0x180621428  push    r12
0x18062142a  push    r13
0x18062142c  push    r14
0x18062142e  push    r15
0x180621430  lea     rbp, [rsp-230h]
0x180621438  sub     rsp, 330h
0x18062143f  mov     rax, cs:__security_cookie
0x180621446  xor     rax, rsp
0x180621449  mov     [rbp+260h+var_40], rax
0x180621450  xor     r14d, r14d
0x180621453  mov     [rbp+260h+var_2D0], edx
0x180621456  mov     [rsp+360h+var_2F0], r14
0x18062145b  mov     rsi, r8
0x18062145e  mov     [rsp+360h+var_2E8], r14d
0x180621463  mov     rbx, rcx
0x180621466  mov     [rsp+360h+var_2E4], r14w
0x18062146c  mov     rcx, cs:RequestContext
0x180621473  lea     r12, RequestContext
0x18062147a  cmp     rcx, r12
0x18062147d  jz      short loc_18062149F
0x18062147f  test    byte ptr [rcx+1Ch], 1
0x180621483  jz      short loc_18062149F
0x180621485  cmp     byte ptr [rcx+19h], 7
0x180621489  jb      short loc_18062149F
0x18062148b  mov     rcx, [rcx+10h]
0x18062148f  lea     edx, [r14+11h]
0x180621493  lea     r8, stru_180863630
0x18062149a  call    sub_180184410
0x18062149f  mov     rcx, rbx
0x1806214a2  mov     [rsi], r14d
0x1806214a5  call    sub_1801CCB4C
0x1806214aa  mov     rcx, rbx
0x1806214ad  test    al, al
0x1806214af  jz      loc_180621538
0x1806214b5  lea     r8, [rsp+360h+var_2F0]
0x1806214ba  xor     edx, edx
0x1806214bc  call    sub_180054C60
0x1806214c1  mov     ebx, eax
0x1806214c3  test    eax, eax
0x1806214c5  js      short loc_180621544
0x1806214c7  lea     rcx, [rsp+360h+var_2F0]
0x1806214cc  call    sub_18010B5D4
0x1806214d1  cmp     eax, 3
0x1806214d4  jl      short loc_180621531
0x1806214d6  mov     rax, [rsp+360h+var_2F0]
0x1806214db  mov     r15d, 5Ch ; '\'
0x1806214e1  cmp     [rax], r15w
0x1806214e5  jnz     short loc_180621531
0x1806214e7  cmp     [rax+2], r15w
0x1806214ec  jnz     short loc_180621531
0x1806214ee  lea     edi, [r15-5Ah]
0x1806214f2  lea     rcx, [rsp+360h+var_2F0]
0x1806214f7  call    sub_18010B5D4
0x1806214fc  cmp     edi, eax
0x1806214fe  jg      short loc_180621544
0x180621500  mov     rdx, [rsp+360h+var_2F0]
0x180621505  movsxd  rcx, edi
0x180621508  cmp     r15w, [rdx+rcx*2]
0x18062150d  jz      short loc_180621513
0x18062150f  inc     edi
0x180621511  jmp     short loc_1806214F2
0x180621513  mov     [rdx+rcx*2], r14w
0x180621518  or      r8d, 0FFFFFFFFh
0x18062151c  mov     rdx, [rsp+360h+var_2F0]
0x180621521  lea     rcx, [rsp+360h+var_2F0]
0x180621526  add     rdx, 4
0x18062152a  call    sub_180007B30
0x18062152f  jmp     short loc_180621542
0x180621531  mov     ebx, 80070057h
0x180621536  jmp     short loc_180621544
0x180621538  lea     rdx, [rsp+360h+var_2F0]
0x18062153d  call    sub_1806177A0
0x180621542  mov     ebx, eax
0x180621544  mov     rcx, cs:RequestContext
0x18062154b  cmp     rcx, r12
0x18062154e  jz      short loc_18062157D
0x180621550  test    byte ptr [rcx+1Ch], 1
0x180621554  jz      short loc_18062157D
0x180621556  cmp     byte ptr [rcx+19h], 7
0x18062155a  jb      short loc_18062157D
0x18062155c  mov     r9, [rsp+360h+var_2F0]
0x180621561  lea     r8, stru_180863630
0x180621568  mov     rcx, [rcx+10h]
0x18062156c  mov     edx, 12h
0x180621571  call    sub_1800B42DC
0x180621576  mov     rcx, cs:RequestContext
0x18062157d  test    ebx, ebx
0x18062157f  js      loc_180621B9F
0x180621585  lea     rcx, aIphlpapiDll_0
0x18062158c  call    cs:LoadLibraryW
0x180621593  nop     dword ptr [rax+rax+00h]
0x180621598  mov     [rbp+260h+hLibModule], rax
0x18062159c  mov     r13, rax
0x18062159f  test    rax, rax
0x1806215a2  jz      loc_180621B7D
0x1806215a8  lea     rdx, aIcmpcreatefile
0x1806215af  mov     rcx, rax; hModule
0x1806215b2  call    cs:GetProcAddress
0x1806215b9  nop     dword ptr [rax+rax+00h]
0x1806215be  lea     rdx, aIcmp6createfil
0x1806215c5  mov     rcx, r13; hModule
0x1806215c8  mov     rbx, rax
0x1806215cb  mov     [rbp+260h+var_2D8], rax
0x1806215cf  call    cs:GetProcAddress
0x1806215d6  nop     dword ptr [rax+rax+00h]
0x1806215db  lea     rdx, aIcmpclosehandl
0x1806215e2  mov     rcx, r13; hModule
0x1806215e5  mov     r15, rax
0x1806215e8  call    cs:GetProcAddress
0x1806215ef  nop     dword ptr [rax+rax+00h]
0x1806215f4  lea     rdx, aIcmpsendecho
0x1806215fb  mov     rcx, r13; hModule
0x1806215fe  mov     rdi, rax
0x180621601  mov     [rbp+260h+var_2C8], rax
0x180621605  call    cs:GetProcAddress
0x18062160c  nop     dword ptr [rax+rax+00h]
0x180621611  lea     rdx, aIcmp6sendecho2
0x180621618  mov     rcx, r13; hModule
0x18062161b  mov     r12, rax
0x18062161e  call    cs:GetProcAddress
0x180621625  nop     dword ptr [rax+rax+00h]
0x18062162a  lea     rdx, aGetbestinterfa
0x180621631  mov     rcx, r13; hModule
0x180621634  mov     r14, rax
0x180621637  mov     [rbp+260h+var_D0], rax
0x18062163e  call    cs:GetProcAddress
0x180621645  nop     dword ptr [rax+rax+00h]
0x18062164a  mov     r13, rax
0x18062164d  test    rbx, rbx
0x180621650  jz      loc_180621B49
0x180621656  test    rdi, rdi
0x180621659  jz      loc_180621B49
0x18062165f  test    r12, r12
0x180621662  jz      loc_180621B49
0x180621668  test    r15, r15
0x18062166b  jz      short loc_18062167E
0x18062166d  test    r14, r14
0x180621670  jz      short loc_18062167E
0x180621672  test    rax, rax
0x180621675  jz      short loc_18062167E
0x180621677  mov     edi, 1
0x18062167c  jmp     short loc_180621680
0x18062167e  xor     edi, edi
0x180621680  lea     rcx, aWs232Dll_0
0x180621687  call    cs:LoadLibraryW
0x18062168e  nop     dword ptr [rax+rax+00h]
0x180621693  mov     [rbp+260h+hModule], rax
0x180621697  mov     r14, rax
0x18062169a  test    rax, rax
0x18062169d  jz      loc_180621B49
0x1806216a3  lea     rdx, aWsastartup
0x1806216aa  mov     rcx, rax; hModule
0x1806216ad  call    cs:GetProcAddress
0x1806216b4  nop     dword ptr [rax+rax+00h]
0x1806216b9  lea     rdx, aWsacleanup
0x1806216c0  mov     rcx, r14; hModule
0x1806216c3  mov     rbx, rax
0x1806216c6  call    cs:GetProcAddress
0x1806216cd  nop     dword ptr [rax+rax+00h]
0x1806216d2  lea     rdx, aGetaddrinfow_0
0x1806216d9  mov     rcx, r14; hModule
0x1806216dc  mov     [rbp+260h+var_2C0], rax
0x1806216e0  call    cs:GetProcAddress
0x1806216e7  nop     dword ptr [rax+rax+00h]
0x1806216ec  mov     rcx, [rbp+260h+hModule]; hModule
0x1806216f0  lea     rdx, aFreeaddrinfow_0
0x1806216f7  mov     r14, rax
0x1806216fa  call    cs:GetProcAddress
0x180621701  nop     dword ptr [rax+rax+00h]
0x180621706  mov     [rbp+260h+var_2B0], rax
0x18062170a  test    rbx, rbx
0x18062170d  jz      loc_180621B1C
0x180621713  cmp     [rbp+260h+var_2C0], 0
0x180621718  jz      loc_180621B1C
0x18062171e  test    r14, r14
0x180621721  jz      loc_180621B1C
0x180621727  test    rax, rax
0x18062172a  jz      loc_180621B1C
0x180621730  xor     edx, edx; Val
0x180621732  lea     rcx, [rbp+260h+var_270]; void *
0x180621736  mov     r8d, 198h; Size
0x18062173c  call    memset
0x180621741  mov     ecx, 202h
0x180621746  lea     rdx, [rbp+260h+var_270]
0x18062174a  mov     rax, rbx
0x18062174d  call    cs:__guard_dispatch_icall_fptr
0x180621753  mov     ebx, eax
0x180621755  test    eax, eax
0x180621757  jnz     loc_180621B2C
0x18062175d  xorps   xmm0, xmm0
0x180621760  lea     r9, [rbp+260h+var_2E0]
0x180621764  movups  [rbp+260h+var_2A0], xmm0
0x180621768  xor     ebx, ebx
0x18062176a  lea     r8, [rbp+260h+var_2A0]
0x18062176e  movups  [rbp+260h+var_290], xmm0
0x180621772  test    edi, edi
0x180621774  mov     [rbp+260h+var_2E0], rbx
0x180621778  movups  [rbp+260h+var_280], xmm0
0x18062177c  lea     eax, [rbx+2]
0x18062177f  psrldq  xmm0, 4
0x180621784  movd    ecx, xmm0
0x180621788  cmovz   ecx, eax
0x18062178b  xor     edx, edx
0x18062178d  mov     dword ptr [rbp+260h+var_2A0+4], ecx
0x180621790  mov     rax, r14
0x180621793  mov     rcx, [rsp+360h+var_2F0]
0x180621798  call    cs:__guard_dispatch_icall_fptr
0x18062179e  test    eax, eax
0x1806217a0  jnz     loc_180621AC2
0x1806217a6  mov     rax, [rbp+260h+var_2E0]
0x1806217aa  lea     r14d, [rbx+2]
0x1806217ae  mov     ecx, [rax+4]
0x1806217b1  cmp     ecx, r14d
0x1806217b4  jnz     loc_1806218F1
0x1806217ba  mov     rax, [rbp+260h+var_2D8]
0x1806217be  call    cs:__guard_dispatch_icall_fptr
0x1806217c4  mov     rdi, rax
0x1806217c7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1806217cb  jz      loc_180621891
0x1806217d1  mov     rcx, [rbp+260h+var_2E0]
0x1806217d5  lea     rax, [rbp+260h+var_C8]
0x1806217dc  mov     r14d, [rbp+260h+var_2D0]
0x1806217e0  lea     r9d, [rbx+8]
0x1806217e4  mov     [rsp+360h+var_328], r14d
0x1806217e9  lea     r8, [rbp+260h+var_D0]
0x1806217f0  mov     dword ptr [rsp+360h+var_330], 30h ; '0'
0x1806217f8  mov     rdx, [rcx+20h]
0x1806217fc  mov     rcx, rdi
0x1806217ff  mov     [rsp+360h+var_338], rax
0x180621804  mov     rax, r12
0x180621807  mov     [rsp+360h+var_340], rbx
0x18062180c  mov     edx, [rdx+4]
0x18062180f  call    cs:__guard_dispatch_icall_fptr
0x180621815  test    eax, eax
0x180621817  jnz     short loc_18062187F
0x180621819  mov     dword ptr [rsi], 1
0x18062181f  call    cs:GetLastError
0x180621826  nop     dword ptr [rax+rax+00h]
0x18062182b  test    eax, eax
0x18062182d  jg      short loc_180621833
0x18062182f  mov     ebx, eax
0x180621831  jmp     short loc_18062183C
0x180621833  movzx   ebx, ax
0x180621836  or      ebx, 80070000h
0x18062183c  test    ebx, ebx
0x18062183e  jns     short loc_18062187F
0x180621840  mov     rcx, cs:RequestContext
0x180621847  lea     rdx, RequestContext
0x18062184e  cmp     rcx, rdx
0x180621851  jz      short loc_18062187F
0x180621853  test    byte ptr [rcx+1Ch], 1
0x180621857  jz      short loc_18062187F
0x180621859  cmp     byte ptr [rcx+19h], 2
0x18062185d  jb      short loc_18062187F
0x18062185f  mov     edx, 13h
0x180621864  mov     r9, [rsp+360h+var_2F0]
0x180621869  mov     rcx, [rcx+10h]
0x18062186d  mov     dword ptr [rsp+360h+var_330], ebx
0x180621871  mov     dword ptr [rsp+360h+var_338], eax
0x180621875  mov     dword ptr [rsp+360h+var_340], r14d
0x18062187a  call    sub_18062346C
0x18062187f  mov     rax, [rbp+260h+var_2C8]
0x180621883  mov     rcx, rdi
0x180621886  call    cs:__guard_dispatch_icall_fptr
0x18062188c  jmp     loc_180621AB2
0x180621891  mov     dword ptr [rsi], 1
0x180621897  call    cs:GetLastError
0x18062189e  nop     dword ptr [rax+rax+00h]
0x1806218a3  test    eax, eax
0x1806218a5  jg      short loc_1806218AB
0x1806218a7  mov     ebx, eax
0x1806218a9  jmp     short loc_1806218B4
0x1806218ab  movzx   ebx, ax
0x1806218ae  or      ebx, 80070000h
0x1806218b4  test    ebx, ebx
0x1806218b6  jns     loc_180621AB2
0x1806218bc  mov     rcx, cs:RequestContext
0x1806218c3  lea     rdx, RequestContext
0x1806218ca  cmp     rcx, rdx
0x1806218cd  jz      loc_180621AB2
0x1806218d3  test    byte ptr [rcx+1Ch], 1
0x1806218d7  jz      loc_180621AB2
0x1806218dd  cmp     [rcx+19h], r14b
0x1806218e1  jb      loc_180621AB2
0x1806218e7  mov     edx, 14h
0x1806218ec  jmp     loc_180621A8E
0x1806218f1  mov     r12d, 17h
0x1806218f7  cmp     ecx, r12d
0x1806218fa  jnz     loc_180621AAD
0x180621900  test    edi, edi
0x180621902  jz      loc_180621AAD
0x180621908  mov     rax, r15
0x18062190b  call    cs:__guard_dispatch_icall_fptr
0x180621911  mov     rdi, rax
0x180621914  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180621918  jz      loc_180621A4B
  ... truncated ...
```
