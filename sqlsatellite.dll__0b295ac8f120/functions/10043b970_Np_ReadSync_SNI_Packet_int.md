# Np::ReadSync(SNI_Packet * *,int)

- ea: `0x10043b970`
- end: `0x10043bf1e`
- name: `?ReadSync@Np@@UEAAKPEAPEAVSNI_Packet@@H@Z`
- size: `1454`
- prototype: `unsigned int __fastcall(Np *__hidden this, struct SNI_Packet **, int)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callees

- `0x10041ec10`
- `0x10041f180`
- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042bb70`
- `0x10042c270`
- `0x10042c430`
- `0x10042c590`
- `0x1004349f0`
- `0x10043b970`
- `0x10045a400`

## import_xrefs

- `KERNEL32!GetOverlappedResult` at `0x10043bb3f`
- `KERNEL32!GetOverlappedResult` at `0x10043bc6a`
- `KERNEL32!GetOverlappedResult` at `0x10043bb3f`
- `KERNEL32!GetOverlappedResult` at `0x10043bc6a`
- `KERNEL32!WaitForSingleObject` at `0x10043bc3c`
- `KERNEL32!WaitForSingleObject` at `0x10043bc3c`
- `KERNEL32!GetTickCount` at `0x10043bc2c`
- `KERNEL32!GetTickCount` at `0x10043bca8`
- `KERNEL32!GetTickCount` at `0x10043bc2c`
- `KERNEL32!GetTickCount` at `0x10043bca8`
- `KERNEL32!ReadFile` at `0x10043ba68`
- `KERNEL32!ReadFile` at `0x10043ba68`
- `KERNEL32!GetLastError` at `0x10043ba78`
- `KERNEL32!GetLastError` at `0x10043bb49`
- `KERNEL32!GetLastError` at `0x10043bc78`
- `KERNEL32!GetLastError` at `0x10043ba78`
- `KERNEL32!GetLastError` at `0x10043bb49`
- `KERNEL32!GetLastError` at `0x10043bc78`

## string_xrefs

- `0x10043b99d`: `sql\common\dk\sni\src\np.cpp`
- `0x10043ba00`: `sql\common\dk\sni\src\np.cpp`
- `0x10043bba2`: `sql\common\dk\sni\src\np.cpp`
- `0x10043bbe0`: `sql\common\dk\sni\src\np.cpp`
- `0x10043bc13`: `sql\common\dk\sni\src\np.cpp`
- `0x10043bcf9`: `sql\common\dk\sni\src\np.cpp`
- `0x10043bdb7`: `sql\common\dk\sni\src\np.cpp`
- `0x10043be26`: `sql\common\dk\sni\src\np.cpp`
- `0x10043be7d`: `sql\common\dk\sni\src\np.cpp`
- `0x10043bece`: `sql\common\dk\sni\src\np.cpp`
- `0x10043bef2`: `sql\common\dk\sni\src\np.cpp`
- `0x10043b9a8`: `Np::ReadSync`
- `0x10043baa6`: `Np::ReadSync`
- `0x10043baf6`: `Np::ReadSync`
- `0x10043bb1b`: `Np::ReadSync`
- `0x10043bb9b`: `Np::ReadSync`
- `0x10043bbd9`: `Np::ReadSync`
- `0x10043bc0c`: `Np::ReadSync`
- `0x10043bcef`: `Np::ReadSync`
- `0x10043bd4d`: `Np::ReadSync`
- `0x10043bd61`: `Np::ReadSync`
- `0x10043bd7d`: `Np::ReadSync`
- `0x10043bdc3`: `Np::ReadSync`
- `0x10043be1c`: `Np::ReadSync`
- `0x10043be34`: `Np::ReadSync`
- `0x10043be76`: `Np::ReadSync`
- `0x10043beaa`: `Np::ReadSync`
- `0x10043beeb`: `Np::ReadSync`
- `0x10043ba99`: `ERR|SNIReadFile: %d{WINERR}\n`
- `0x10043bb8e`: `SNIReceive Packet, BytesRead:%d{DWORD}\n`
- `0x10043bb0e`: `ERR|SNIReadFile returned ERROR_MORE_DATA.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Np::ReadSync(Np *this, struct SNI_Packet **a2, signed int a3)
{
  signed int v3; // r12d
  DWORD v6; // ebp
  struct SNI_Packet *v7; // rsi
  struct SNI_Packet *Ex2; // rax
  void *v9; // rdx
  DWORD v10; // r8d
  struct _OVERLAPPED *v11; // r15
  DWORD LastError; // ebx
  char v13; // al
  int v14; // r8d
  const wchar_t *v15; // r9
  DWORD v16; // eax
  __int16 v17; // ax
  DWORD TickCount; // r14d
  DWORD v19; // eax
  DWORD v20; // eax
  LPOVERLAPPED lpOverlapped; // [rsp+20h] [rbp-68h]
  __int64 v23; // [rsp+28h] [rbp-60h]
  __int64 v24; // [rsp+30h] [rbp-58h]
  DWORD NumberOfBytesTransferred; // [rsp+90h] [rbp+8h] BYREF

  v3 = a3;
  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\np.cpp",
      "Np::ReadSync",
      1585,
      L"API|SNI%u#, ppNewPacket: %p{SNI_Packet**}, iTimeOut: %d\n",
      *((_DWORD *)this + 11),
      a2,
      a3);
  v6 = 0;
  NumberOfBytesTransferred = 0;
  *a2 = 0;
  while ( 1 )
  {
    v7 = (struct SNI_Packet *)*((_QWORD *)this + 10);
    if ( v7 )
    {
      v11 = (struct _OVERLAPPED *)((char *)v7 + 16);
      *((_QWORD *)this + 10) = 0;
    }
    else
    {
      Ex2 = (struct SNI_Packet *)SNIPacketAllocateEx2(*((_QWORD *)this + 4), 0);
      v7 = Ex2;
      if ( !Ex2 )
      {
        LastError = 14;
        if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
        {
          LODWORD(v24) = 14;
          LODWORD(v23) = 0;
          LODWORD(lpOverlapped) = *((_DWORD *)this + 18);
          SNIXE_SNI_ERROR_ON(
            "sql\\common\\dk\\sni\\src\\np.cpp",
            "Np::ReadSync",
            1606,
            L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
            lpOverlapped,
            v23,
            v24);
        }
        SNISetLastError(*((unsigned int *)this + 18), 14, 50100);
        goto LABEL_53;
      }
      SNI::detail::Transport::PrepareForSyncCall(this, Ex2);
      v9 = (void *)(*((_QWORD *)v7 + 21) + *((unsigned int *)v7 + 46));
      v10 = *((_DWORD *)v7 + 45);
      v11 = (struct _OVERLAPPED *)((char *)v7 + 16);
      NumberOfBytesTransferred = 0;
      *((_QWORD *)v7 + 4) = 0;
      LastError = 0;
      if ( !ReadFile(*((HANDLE *)this + 8), v9, v10, 0, (LPOVERLAPPED)((char *)v7 + 16)) )
      {
        LastError = GetLastError();
        if ( LastError == 997 )
          goto LABEL_26;
        v13 = g_XeSniPkg_enabledBitmap;
        if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
        {
          LODWORD(lpOverlapped) = LastError;
          SNIXE_SNI_ERROR_ON(
            "sql\\common\\dk\\sni\\src\\np.cpp",
            "Np::ReadSync",
            1637,
            L"ERR|SNIReadFile: %d{WINERR}\n",
            lpOverlapped);
          v13 = g_XeSniPkg_enabledBitmap;
        }
        if ( LastError != 234 )
        {
          if ( (v13 & 2) != 0 )
          {
            LODWORD(v24) = LastError;
            v14 = 1644;
            goto LABEL_13;
          }
          goto LABEL_43;
        }
        if ( (v13 & 2) != 0 )
          SNIXE_SNI_ERROR_ON(
            "sql\\common\\dk\\sni\\src\\np.cpp",
            "Np::ReadSync",
            1657,
            L"ERR|SNIReadFile returned ERROR_MORE_DATA.\n");
      }
      if ( !GetOverlappedResult(*((HANDLE *)this + 8), (LPOVERLAPPED)((char *)v7 + 16), &NumberOfBytesTransferred, 1) )
      {
        v16 = GetLastError();
        LastError = v16;
        if ( v16 != 234 )
        {
          if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
          {
            LODWORD(v24) = v16;
            v14 = 1666;
            goto LABEL_13;
          }
LABEL_43:
          SNISetLastError(*((unsigned int *)this + 18), LastError, 50100);
          if ( LastError == 258 )
          {
LABEL_53:
            if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
            {
              LODWORD(lpOverlapped) = LastError;
              SNIXE_SNI_TRACE_ON(
                "sql\\common\\dk\\sni\\src\\np.cpp",
                "Np::ReadSync",
                1769,
                L"RET|SNI%d{WINERR}\n",
                lpOverlapped);
            }
            v6 = LastError;
            goto LABEL_56;
          }
LABEL_51:
          if ( v7 )
          {
            SNIPacketRelease(v7);
            *((_QWORD *)this + 10) = 0;
          }
          goto LABEL_53;
        }
      }
      if ( LastError != 997 )
        goto LABEL_19;
    }
LABEL_26:
    TickCount = GetTickCount();
    v19 = WaitForSingleObject(v11->hEvent, v3);
    LastError = v19;
    if ( v19 == -1 )
    {
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        LODWORD(v24) = -1;
        LODWORD(v23) = 0;
        LODWORD(lpOverlapped) = *((_DWORD *)this + 18);
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\np.cpp",
          "Np::ReadSync",
          1692,
          L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
          lpOverlapped,
          v23,
          v24);
      }
      SNISetLastError(*((unsigned int *)this + 18), LastError, 50100);
      goto LABEL_51;
    }
    if ( v19 == 258 )
    {
      *((_QWORD *)this + 10) = v7;
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        LODWORD(v24) = 258;
        LODWORD(v23) = 11;
        LODWORD(lpOverlapped) = *((_DWORD *)this + 18);
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\np.cpp",
          "Np::ReadSync",
          1699,
          L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
          lpOverlapped,
          v23,
          v24);
      }
      SNISetLastError(*((unsigned int *)this + 18), LastError, 50111);
      goto LABEL_53;
    }
    if ( GetOverlappedResult(*((HANDLE *)this + 8), v11, &NumberOfBytesTransferred, 0) )
      goto LABEL_19;
    v20 = GetLastError();
    LastError = v20;
    if ( v20 != 995 )
      break;
    SNIPacketRelease(v7);
    *((_QWORD *)this + 10) = 0;
    NumberOfBytesTransferred = 0;
    if ( v3 != -1 )
    {
      v3 += TickCount - GetTickCount();
      if ( v3 <= 0 )
      {
        LastError = 258;
        if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
        {
          LODWORD(v24) = 258;
          LODWORD(v23) = 11;
          LODWORD(lpOverlapped) = *((_DWORD *)this + 18);
          SNIXE_SNI_ERROR_ON(
            "sql\\common\\dk\\sni\\src\\np.cpp",
            "Np::ReadSync",
            1725,
            L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
            lpOverlapped,
            v23,
            v24);
        }
        SNISetLastError(*((unsigned int *)this + 18), 258, 50111);
        goto LABEL_53;
      }
    }
  }
  if ( v20 != 234 )
  {
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      LODWORD(v24) = v20;
      v14 = 1735;
LABEL_13:
      LODWORD(v23) = 0;
      LODWORD(lpOverlapped) = *((_DWORD *)this + 18);
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\np.cpp",
        "Np::ReadSync",
        v14,
        L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
        lpOverlapped,
        v23,
        v24);
    }
    goto LABEL_43;
  }
LABEL_19:
  *((_DWORD *)v7 + 44) = NumberOfBytesTransferred;
  *a2 = v7;
  v17 = g_XeSniPkg_enabledBitmap;
  if ( (g_XeSniPkg_enabledBitmap & 4) != 0 )
  {
    LODWORD(lpOverlapped) = NumberOfBytesTransferred;
    SNIXE_SNI_SNIPKT_ON(
      "sql\\common\\dk\\sni\\src\\np.cpp",
      "Np::ReadSync",
      1751,
      L"SNIReceive Packet, BytesRead:%d{DWORD}\n",
      lpOverlapped);
    v17 = g_XeSniPkg_enabledBitmap;
  }
  if ( (v17 & 0x100) != 0 )
  {
    SNIXE_SNI_SNIPKT_DATA_ON(
      "sql\\common\\dk\\sni\\src\\np.cpp",
      "Np::ReadSync",
      1752,
      (const void *)(*((_QWORD *)v7 + 21) + *((unsigned int *)v7 + 46)),
      NumberOfBytesTransferred);
    LOBYTE(v17) = g_XeSniPkg_enabledBitmap;
  }
  if ( (v17 & 1) != 0 )
    SNIXE_SNI_TRACE_ON("sql\\common\\dk\\sni\\src\\np.cpp", "Np::ReadSync", 1754, L"RET|SNI%d{WINERR}\n", 0);
LABEL_56:
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\np.cpp", "Np::ReadSync", 1585, v15);
  return v6;
}

```

## disassembly

```asm
0x10043b970  mov     rax, rsp
0x10043b973  push    rdi
0x10043b974  push    r12
0x10043b976  push    r13
0x10043b978  push    r14
0x10043b97a  push    r15
0x10043b97c  sub     rsp, 60h
0x10043b980  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x10043b988  mov     [rax+10h], rbx
0x10043b98c  mov     [rax+18h], rbp
0x10043b990  mov     [rax+20h], rsi
0x10043b994  mov     r12d, r8d
0x10043b997  mov     r13, rdx
0x10043b99a  mov     rdi, rcx
0x10043b99d  lea     r14, aSqlCommonDkSni_22; "sql\\common\\dk\\sni\\src\\np.cpp"
0x10043b9a4  mov     [rax-40h], r14
0x10043b9a8  lea     r15, aNpReadsync; "Np::ReadSync"
0x10043b9af  mov     [rax-38h], r15
0x10043b9b3  mov     dword ptr [rax-30h], 631h
0x10043b9ba  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043b9c1  jz      short loc_10043B9EA
0x10043b9c3  mov     [rax-58h], r8d
0x10043b9c7  mov     [rax-60h], rdx
0x10043b9cb  mov     eax, [rcx+2Ch]
0x10043b9ce  mov     dword ptr [rsp+88h+lpOverlapped], eax
0x10043b9d2  lea     r9, aApiSniUPpnewpa_0; "API|SNI%u#, ppNewPacket: %p{SNI_Packet*"...
0x10043b9d9  mov     r8d, 631h; int
0x10043b9df  mov     rdx, r15; char *
0x10043b9e2  mov     rcx, r14; char *
0x10043b9e5  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x10043b9ea  xor     ebp, ebp
0x10043b9ec  mov     [rsp+88h+NumberOfBytesTransferred], ebp
0x10043b9f3  mov     [r13+0], rbp
0x10043b9f7  jmp     short loc_10043BA07
0x10043ba00  lea     r14, aSqlCommonDkSni_22; "sql\\common\\dk\\sni\\src\\np.cpp"
0x10043ba07  mov     rsi, [rdi+50h]
0x10043ba0b  test    rsi, rsi
0x10043ba0e  jnz     loc_10043BC24
0x10043ba14  xor     r8d, r8d
0x10043ba17  xor     edx, edx
0x10043ba19  mov     rcx, [rdi+20h]
0x10043ba1d  call    SNIPacketAllocateEx2
0x10043ba22  mov     rsi, rax
0x10043ba25  test    rax, rax
0x10043ba28  jz      loc_10043BD23
0x10043ba2e  mov     rdx, rax; struct SNI_Packet *
0x10043ba31  mov     rcx, rdi; this
0x10043ba34  call    ?PrepareForSyncCall@Transport@detail@SNI@@IEAAXPEAVSNI_Packet@@@Z; SNI::detail::Transport::PrepareForSyncCall(SNI_Packet *)
0x10043ba39  mov     edx, [rsi+0B8h]
0x10043ba3f  add     rdx, [rsi+0A8h]; lpBuffer
0x10043ba46  mov     r8d, [rsi+0B4h]; nNumberOfBytesToRead
0x10043ba4d  lea     r15, [rsi+10h]
0x10043ba51  mov     [rsp+88h+NumberOfBytesTransferred], ebp
0x10043ba58  mov     [r15+10h], rbp
0x10043ba5c  mov     [rsp+88h+lpOverlapped], r15; lpOverlapped
0x10043ba61  xor     r9d, r9d; lpNumberOfBytesRead
0x10043ba64  mov     rcx, [rdi+40h]; hFile
0x10043ba68  call    cs:__imp_ReadFile
0x10043ba6e  mov     ebx, ebp
0x10043ba70  test    eax, eax
0x10043ba72  jnz     loc_10043BB2A
0x10043ba78  call    cs:__imp_GetLastError
0x10043ba7e  mov     ebx, eax
0x10043ba80  cmp     eax, 3E5h
0x10043ba85  jz      loc_10043BC2C
0x10043ba8b  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043ba91  test    al, 2
0x10043ba93  jz      short loc_10043BABB
0x10043ba95  mov     dword ptr [rsp+88h+lpOverlapped], ebx
0x10043ba99  lea     r9, aErrSnireadfile; "ERR|SNIReadFile: %d{WINERR}\n"
0x10043baa0  mov     r8d, 665h; int
0x10043baa6  lea     rdx, aNpReadsync; "Np::ReadSync"
0x10043baad  mov     rcx, r14; char *
0x10043bab0  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10043bab5  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043babb  cmp     ebx, 0EAh
0x10043bac1  jz      short loc_10043BB0A
0x10043bac3  cmp     ebx, 3E5h
0x10043bac9  jz      loc_10043BC2C
0x10043bacf  test    al, 2
0x10043bad1  jz      loc_10043BDC3
0x10043bad7  mov     dword ptr [rsp+88h+var_58], ebx
0x10043badb  mov     r8d, 66Ch; int
0x10043bae1  mov     rcx, r14; char *
0x10043bae4  mov     dword ptr [rsp+88h+var_60], ebp
0x10043bae8  mov     eax, [rdi+48h]
0x10043baeb  mov     dword ptr [rsp+88h+lpOverlapped], eax
0x10043baef  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10043baf6  lea     r15, aNpReadsync; "Np::ReadSync"
0x10043bafd  mov     rdx, r15; char *
0x10043bb00  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10043bb05  jmp     loc_10043BDCA
0x10043bb0a  test    al, 2
0x10043bb0c  jz      short loc_10043BB2A
0x10043bb0e  lea     r9, aErrSnireadfile_1; "ERR|SNIReadFile returned ERROR_MORE_DAT"...
0x10043bb15  mov     r8d, 679h; int
0x10043bb1b  lea     rdx, aNpReadsync; "Np::ReadSync"
0x10043bb22  mov     rcx, r14; char *
0x10043bb25  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10043bb2a  mov     r9d, 1; bWait
0x10043bb30  lea     r8, [rsp+88h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x10043bb38  mov     rdx, r15; lpOverlapped
0x10043bb3b  mov     rcx, [rdi+40h]; hFile
0x10043bb3f  call    cs:__imp_GetOverlappedResult
0x10043bb45  test    eax, eax
0x10043bb47  jnz     short loc_10043BB5C
0x10043bb49  call    cs:__imp_GetLastError
0x10043bb4f  mov     ebx, eax
0x10043bb51  cmp     eax, 0EAh
0x10043bb56  jnz     loc_10043BD07
0x10043bb5c  cmp     ebx, 3E5h
0x10043bb62  jz      loc_10043BC2C
0x10043bb68  mov     eax, [rsp+88h+NumberOfBytesTransferred]
0x10043bb6f  mov     [rsi+0B0h], eax
0x10043bb75  mov     [r13+0], rsi
0x10043bb79  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043bb7f  test    al, 4
0x10043bb81  jz      short loc_10043BBB4
0x10043bb83  mov     eax, [rsp+88h+NumberOfBytesTransferred]
0x10043bb8a  mov     dword ptr [rsp+88h+lpOverlapped], eax
0x10043bb8e  lea     r9, aSnireceivePack; "SNIReceive Packet, BytesRead:%d{DWORD}"...
0x10043bb95  mov     r8d, 6D7h; int
0x10043bb9b  lea     rdx, aNpReadsync; "Np::ReadSync"
0x10043bba2  lea     rcx, aSqlCommonDkSni_22; "sql\\common\\dk\\sni\\src\\np.cpp"
0x10043bba9  call    ?SNIXE_SNI_SNIPKT_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_SNIPKT_ON(char const *,char const *,int,wchar_t const *,...)
0x10043bbae  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043bbb4  bt      eax, 8
0x10043bbb8  jnb     short loc_10043BBF2
0x10043bbba  mov     r9d, [rsi+0B8h]
0x10043bbc1  add     r9, [rsi+0A8h]; void *
0x10043bbc8  mov     eax, [rsp+88h+NumberOfBytesTransferred]
0x10043bbcf  mov     dword ptr [rsp+88h+lpOverlapped], eax; int
0x10043bbd3  mov     r8d, 6D8h; int
0x10043bbd9  lea     rdx, aNpReadsync; "Np::ReadSync"
0x10043bbe0  lea     rcx, aSqlCommonDkSni_22; "sql\\common\\dk\\sni\\src\\np.cpp"
0x10043bbe7  call    ?SNIXE_SNI_SNIPKT_DATA_ON@@YAXPEBD0HPEBXH@Z; SNIXE_SNI_SNIPKT_DATA_ON(char const *,char const *,int,void const *,int)
0x10043bbec  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043bbf2  test    al, 1
0x10043bbf4  jz      loc_10043BEDC
0x10043bbfa  mov     [rsp+88h+lpOverlapped], rbp
0x10043bbff  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x10043bc06  mov     r8d, 6DAh; int
0x10043bc0c  lea     rdx, aNpReadsync; "Np::ReadSync"
0x10043bc13  lea     rcx, aSqlCommonDkSni_22; "sql\\common\\dk\\sni\\src\\np.cpp"
0x10043bc1a  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10043bc1f  jmp     loc_10043BEDC
0x10043bc24  lea     r15, [rsi+10h]
0x10043bc28  mov     [rdi+50h], rbp
0x10043bc2c  call    cs:__imp_GetTickCount
0x10043bc32  mov     r14d, eax
0x10043bc35  mov     edx, r12d; dwMilliseconds
0x10043bc38  mov     rcx, [r15+18h]; hHandle
0x10043bc3c  call    cs:__imp_WaitForSingleObject
0x10043bc42  mov     ebx, eax
0x10043bc44  cmp     eax, 0FFFFFFFFh
0x10043bc47  jz      loc_10043BE4D
0x10043bc4d  cmp     eax, 102h
0x10043bc52  jz      loc_10043BDEB
0x10043bc58  xor     r9d, r9d; bWait
0x10043bc5b  lea     r8, [rsp+88h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x10043bc63  mov     rdx, r15; lpOverlapped
0x10043bc66  mov     rcx, [rdi+40h]; hFile
0x10043bc6a  call    cs:__imp_GetOverlappedResult
0x10043bc70  test    eax, eax
0x10043bc72  jnz     loc_10043BB68
0x10043bc78  call    cs:__imp_GetLastError
0x10043bc7e  mov     ebx, eax
0x10043bc80  cmp     eax, 3E3h
0x10043bc85  jnz     loc_10043BD99
0x10043bc8b  mov     rcx, rsi; struct SNI_Packet *
0x10043bc8e  call    SNIPacketRelease
0x10043bc93  mov     [rdi+50h], rbp
0x10043bc97  mov     [rsp+88h+NumberOfBytesTransferred], ebp
0x10043bc9e  cmp     r12d, 0FFFFFFFFh
0x10043bca2  jz      loc_10043BA00
0x10043bca8  call    cs:__imp_GetTickCount
0x10043bcae  sub     r14d, eax
0x10043bcb1  add     r12d, r14d
0x10043bcb4  test    r12d, r12d
0x10043bcb7  jg      loc_10043BA00
0x10043bcbd  mov     ebx, 102h
0x10043bcc2  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043bcc9  jz      loc_10043BD7D
0x10043bccf  mov     dword ptr [rsp+88h+var_58], ebx
0x10043bcd3  mov     dword ptr [rsp+88h+var_60], 0Bh
0x10043bcdb  mov     eax, [rdi+48h]
0x10043bcde  mov     dword ptr [rsp+88h+lpOverlapped], eax
0x10043bce2  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10043bce9  mov     r8d, 6BDh; int
0x10043bcef  lea     r15, aNpReadsync; "Np::ReadSync"
0x10043bcf6  mov     rdx, r15; char *
0x10043bcf9  lea     rcx, aSqlCommonDkSni_22; "sql\\common\\dk\\sni\\src\\np.cpp"
0x10043bd00  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10043bd05  jmp     short loc_10043BD84
0x10043bd07  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043bd0e  jz      loc_10043BDC3
0x10043bd14  mov     dword ptr [rsp+88h+var_58], eax
0x10043bd18  mov     r8d, 682h
0x10043bd1e  jmp     loc_10043BAE1
0x10043bd23  mov     ebx, 0Eh
0x10043bd28  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043bd2f  jz      short loc_10043BD61
0x10043bd31  mov     dword ptr [rsp+88h+var_58], ebx
0x10043bd35  mov     dword ptr [rsp+88h+var_60], ebp
0x10043bd39  mov     eax, [rdi+48h]
0x10043bd3c  mov     dword ptr [rsp+88h+lpOverlapped], eax
0x10043bd40  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10043bd47  mov     r8d, 646h; int
0x10043bd4d  lea     r15, aNpReadsync; "Np::ReadSync"
0x10043bd54  mov     rdx, r15; char *
0x10043bd57  mov     rcx, r14; char *
0x10043bd5a  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10043bd5f  jmp     short loc_10043BD68
0x10043bd61  lea     r15, aNpReadsync; "Np::ReadSync"
0x10043bd68  mov     r8d, 0C3B4h
0x10043bd6e  mov     edx, ebx
0x10043bd70  mov     ecx, [rdi+48h]
0x10043bd73  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10043bd78  jmp     loc_10043BEB1
0x10043bd7d  lea     r15, aNpReadsync; "Np::ReadSync"
0x10043bd84  mov     edx, ebx
0x10043bd86  mov     r8d, 0C3BFh
0x10043bd8c  mov     ecx, [rdi+48h]
0x10043bd8f  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10043bd94  jmp     loc_10043BEB1
0x10043bd99  cmp     eax, 0EAh
0x10043bd9e  jz      loc_10043BB68
0x10043bda4  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043bdab  jz      short loc_10043BDC3
0x10043bdad  mov     dword ptr [rsp+88h+var_58], eax
0x10043bdb1  mov     r8d, 6C7h
0x10043bdb7  lea     rcx, aSqlCommonDkSni_22; "sql\\common\\dk\\sni\\src\\np.cpp"
0x10043bdbe  jmp     loc_10043BAE4
0x10043bdc3  lea     r15, aNpReadsync; "Np::ReadSync"
0x10043bdca  mov     r8d, 0C3B4h
0x10043bdd0  mov     edx, ebx
0x10043bdd2  mov     ecx, [rdi+48h]
0x10043bdd5  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10043bdda  cmp     ebx, 102h
0x10043bde0  jz      loc_10043BEB1
0x10043bde6  jmp     loc_10043BE99
0x10043bdeb  mov     [rdi+50h], rsi
0x10043bdef  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043bdf6  jz      short loc_10043BE34
0x10043bdf8  mov     dword ptr [rsp+88h+var_58], 102h
0x10043be00  mov     dword ptr [rsp+88h+var_60], 0Bh
0x10043be08  mov     eax, [rdi+48h]
0x10043be0b  mov     dword ptr [rsp+88h+lpOverlapped], eax
0x10043be0f  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10043be16  mov     r8d, 6A3h; int
0x10043be1c  lea     r15, aNpReadsync; "Np::ReadSync"
0x10043be23  mov     rdx, r15; char *
0x10043be26  lea     rcx, aSqlCommonDkSni_22; "sql\\common\\dk\\sni\\src\\np.cpp"
0x10043be2d  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10043be32  jmp     short loc_10043BE3B
0x10043be34  lea     r15, aNpReadsync; "Np::ReadSync"
0x10043be3b  mov     r8d, 0C3BFh
0x10043be41  mov     edx, ebx
0x10043be43  mov     ecx, [rdi+48h]
0x10043be46  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10043be4b  jmp     short loc_10043BEB1
0x10043be4d  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043be54  jz      short loc_10043BE89
0x10043be56  mov     dword ptr [rsp+88h+var_58], 0FFFFFFFFh
0x10043be5e  mov     dword ptr [rsp+88h+var_60], ebp
0x10043be62  mov     eax, [rdi+48h]
0x10043be65  mov     dword ptr [rsp+88h+lpOverlapped], eax
0x10043be69  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10043be70  mov     r8d, 69Ch; int
0x10043be76  lea     rdx, aNpReadsync; "Np::ReadSync"
0x10043be7d  lea     rcx, aSqlCommonDkSni_22; "sql\\common\\dk\\sni\\src\\np.cpp"
0x10043be84  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10043be89  mov     r8d, 0C3B4h
0x10043be8f  mov     edx, ebx
0x10043be91  mov     ecx, [rdi+48h]
0x10043be94  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10043be99  test    rsi, rsi
0x10043be9c  jz      short loc_10043BEAA
0x10043be9e  mov     rcx, rsi; struct SNI_Packet *
0x10043bea1  call    SNIPacketRelease
0x10043bea6  mov     [rdi+50h], rbp
0x10043beaa  lea     r15, aNpReadsync; "Np::ReadSync"
0x10043beb1  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043beb8  jz      short loc_10043BEDA
0x10043beba  mov     dword ptr [rsp+88h+lpOverlapped], ebx
0x10043bebe  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x10043bec5  mov     r8d, 6E9h; int
0x10043becb  mov     rdx, r15; char *
0x10043bece  lea     rcx, aSqlCommonDkSni_22; "sql\\common\\dk\\sni\\src\\np.cpp"
0x10043bed5  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10043beda  mov     ebp, ebx
0x10043bedc  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043bee3  jz      short loc_10043BEFE
0x10043bee5  mov     r8d, 631h; int
0x10043beeb  lea     rdx, aNpReadsync; "Np::ReadSync"
0x10043bef2  lea     rcx, aSqlCommonDkSni_22; "sql\\common\\dk\\sni\\src\\np.cpp"
0x10043bef9  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x10043befe  mov     eax, ebp
0x10043bf00  lea     r11, [rsp+88h+var_28]
0x10043bf05  mov     rbx, [r11+38h]
  ... truncated ...
```
