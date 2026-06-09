# Np::PostReadAsync(SNI_Packet *)

- ea: `0x10043c3c0`
- end: `0x10043c75e`
- name: `?PostReadAsync@Np@@AEAAKPEAVSNI_Packet@@@Z`
- size: `926`
- prototype: `unsigned int __fastcall(Np *__hidden this, struct SNI_Packet *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x10043c250`

## callees

- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042bb70`
- `0x10042c270`
- `0x10042c430`
- `0x10042c590`
- `0x1004349f0`
- `0x10043c3c0`
- `0x10045a4d0`

## import_xrefs

- `KERNEL32!GetOverlappedResult` at `0x10043c52c`
- `KERNEL32!GetOverlappedResult` at `0x10043c52c`
- `KERNEL32!ReadFile` at `0x10043c4c7`
- `KERNEL32!ReadFile` at `0x10043c4c7`
- `KERNEL32!GetLastError` at `0x10043c4d1`
- `KERNEL32!GetLastError` at `0x10043c53a`
- `KERNEL32!GetLastError` at `0x10043c4d1`
- `KERNEL32!GetLastError` at `0x10043c53a`

## string_xrefs

- `0x10043c3ea`: `sql\common\dk\sni\src\np.cpp`
- `0x10043c4f8`: `ERR|SNIReadFile returned ERROR_MORE_DATA.\n`
- `0x10043c5c3`: `ERR|SNIReadFile: %d{WINERR}.\n`
- `0x10043c3f5`: `Np::PostReadAsync`
- `0x10043c655`: `SNI0-byte successful Named Pipe read.\n`
- `0x10043c594`: `ERR|SNIGetOverlappedResult failed to obtain size of successful async read: %d{WINERR}\n`
- `0x10043c6e1`: `SNISuppressing successful read completion and returning ERROR_IO_PENDING.\n`
- `0x10043c688`: `SNIReceive Packet, dwBytesRead:%u{DWORD}\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Np::PostReadAsync(Np *this, struct SNI_Packet *a2)
{
  void *v4; // rbx
  DWORD v5; // r14d
  unsigned int v6; // ebx
  int v7; // r8d
  const wchar_t *v8; // r9
  DWORD LastError; // eax
  DWORD v10; // eax
  DWORD v11; // eax
  LPOVERLAPPED lpOverlapped; // [rsp+20h] [rbp-68h]
  __int64 v14; // [rsp+28h] [rbp-60h]
  DWORD NumberOfBytesTransferred; // [rsp+90h] [rbp+8h] BYREF

  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\np.cpp",
      "Np::PostReadAsync",
      1929,
      L"API|SNI%u#, pPacket: %p{SNI_Packet*}\n",
      *((_DWORD *)this + 11),
      a2);
  v4 = (void *)(*((_QWORD *)a2 + 21) + *((unsigned int *)a2 + 46));
  v5 = *((_DWORD *)a2 + 45) - *((_DWORD *)a2 + 44);
  *((_QWORD *)a2 + 4) = 0;
  if ( *((_QWORD *)this + 10) )
  {
    v6 = 5023;
    if ( (g_XeSniPkg_enabledBitmap & 2) == 0 )
    {
LABEL_7:
      SNISetLastError(*((_DWORD *)this + 18), v6, 0xC3B4u);
      goto LABEL_34;
    }
    v7 = 1946;
LABEL_6:
    LODWORD(v14) = 0;
    LODWORD(lpOverlapped) = *((_DWORD *)this + 18);
    SNIXE_SNI_ERROR_ON(
      "sql\\common\\dk\\sni\\src\\np.cpp",
      "Np::PostReadAsync",
      v7,
      L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
      lpOverlapped,
      v14,
      v6);
    goto LABEL_7;
  }
  SNI::detail::Transport::PrepareForAsyncCall(this, a2);
  if ( !ReadFile(*((HANDLE *)this + 8), v4, v5, 0, (LPOVERLAPPED)((char *)a2 + 16)) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError == 997 )
      goto LABEL_34;
    if ( LastError != 234 )
    {
      if ( (g_XeSniPkg_enabledBitmap & 2) == 0 )
        goto LABEL_7;
      LODWORD(lpOverlapped) = LastError;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\np.cpp",
        "Np::PostReadAsync",
        1975,
        L"ERR|SNIReadFile: %d{WINERR}.\n",
        lpOverlapped);
      if ( (g_XeSniPkg_enabledBitmap & 2) == 0 )
        goto LABEL_7;
      v7 = 1976;
      goto LABEL_6;
    }
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\np.cpp",
        "Np::PostReadAsync",
        1970,
        L"ERR|SNIReadFile returned ERROR_MORE_DATA.\n");
  }
  if ( !*((_BYTE *)this + 61) )
  {
    if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
      SNIXE_SNI_TRACE_ON(
        "sql\\common\\dk\\sni\\src\\np.cpp",
        "Np::PostReadAsync",
        2017,
        L"SNISuppressing successful read completion and returning ERROR_IO_PENDING.\n");
    v6 = 997;
    goto LABEL_34;
  }
  if ( !GetOverlappedResult(*((HANDLE *)this + 8), (LPOVERLAPPED)((char *)a2 + 16), &NumberOfBytesTransferred, 0) )
  {
    v10 = GetLastError();
    v6 = v10;
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      LODWORD(v14) = 0;
      LODWORD(lpOverlapped) = *((_DWORD *)this + 18);
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\np.cpp",
        "Np::PostReadAsync",
        1990,
        L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
        lpOverlapped,
        v14,
        v10);
    }
    SNISetLastError(*((_DWORD *)this + 18), v6, 0xC3B4u);
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      LODWORD(lpOverlapped) = v6;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\np.cpp",
        "Np::PostReadAsync",
        1993,
        L"ERR|SNIGetOverlappedResult failed to obtain size of successful async read: %d{WINERR}\n",
        lpOverlapped);
    }
    goto LABEL_34;
  }
  v11 = NumberOfBytesTransferred;
  if ( NumberOfBytesTransferred )
  {
    v6 = 0;
    *((_DWORD *)a2 + 44) += NumberOfBytesTransferred;
    if ( (g_XeSniPkg_enabledBitmap & 4) != 0 )
    {
      LODWORD(lpOverlapped) = v11;
      SNIXE_SNI_SNIPKT_ON(
        "sql\\common\\dk\\sni\\src\\np.cpp",
        "Np::PostReadAsync",
        2010,
        L"SNIReceive Packet, dwBytesRead:%u{DWORD}\n",
        lpOverlapped);
      v11 = NumberOfBytesTransferred;
    }
    if ( (g_XeSniPkg_enabledBitmap & 0x100) != 0 )
      SNIXE_SNI_SNIPKT_DATA_ON(
        "sql\\common\\dk\\sni\\src\\np.cpp",
        "Np::PostReadAsync",
        2011,
        (const void *)(*((_QWORD *)a2 + 21) + *((unsigned int *)a2 + 46)),
        v11);
    goto LABEL_34;
  }
  v6 = 233;
  if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
  {
    LODWORD(v14) = 2;
    LODWORD(lpOverlapped) = *((_DWORD *)this + 18);
    SNIXE_SNI_ERROR_ON(
      "sql\\common\\dk\\sni\\src\\np.cpp",
      "Np::PostReadAsync",
      1999,
      L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
      lpOverlapped,
      v14,
      233);
  }
  SNISetLastError(*((_DWORD *)this + 18), 0xE9u, 0xC3B6u);
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\np.cpp",
      "Np::PostReadAsync",
      2000,
      L"SNI0-byte successful Named Pipe read.\n");
LABEL_34:
    if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
    {
      LODWORD(lpOverlapped) = v6;
      SNIXE_SNI_TRACE_ON(
        "sql\\common\\dk\\sni\\src\\np.cpp",
        "Np::PostReadAsync",
        2022,
        L"RET|SNI%d{WINERR}\n",
        lpOverlapped);
    }
  }
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\np.cpp", "Np::PostReadAsync", 1929, v8);
  return v6;
}

```

## disassembly

```asm
0x10043c3c0  mov     rax, rsp
0x10043c3c3  push    rdi
0x10043c3c4  push    r12
0x10043c3c6  push    r13
0x10043c3c8  push    r14
0x10043c3ca  push    r15
0x10043c3cc  sub     rsp, 60h
0x10043c3d0  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x10043c3d8  mov     [rax+10h], rbx
0x10043c3dc  mov     [rax+18h], rbp
0x10043c3e0  mov     [rax+20h], rsi
0x10043c3e4  mov     rsi, rdx
0x10043c3e7  mov     rdi, rcx
0x10043c3ea  lea     r15, aSqlCommonDkSni_22; "sql\\common\\dk\\sni\\src\\np.cpp"
0x10043c3f1  mov     [rax-40h], r15
0x10043c3f5  lea     r12, aNpPostreadasyn; "Np::PostReadAsync"
0x10043c3fc  mov     [rax-38h], r12
0x10043c400  mov     dword ptr [rax-30h], 789h
0x10043c407  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043c40e  jz      short loc_10043C433
0x10043c410  mov     [rax-60h], rdx
0x10043c414  mov     eax, [rcx+2Ch]
0x10043c417  mov     dword ptr [rsp+88h+lpOverlapped], eax
0x10043c41b  lea     r9, aApiSniUPpacket_5; "API|SNI%u#, pPacket: %p{SNI_Packet*}\n"
0x10043c422  mov     r8d, 789h; int
0x10043c428  mov     rdx, r12; char *
0x10043c42b  mov     rcx, r15; char *
0x10043c42e  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x10043c433  mov     ebx, [rsi+0B8h]
0x10043c439  add     rbx, [rsi+0A8h]
0x10043c440  mov     r14d, [rsi+0B4h]
0x10043c447  sub     r14d, [rsi+0B0h]
0x10043c44e  lea     rbp, [rsi+10h]
0x10043c452  xor     r13d, r13d
0x10043c455  mov     [rbp+10h], r13
0x10043c459  cmp     [rdi+50h], r13
0x10043c45d  jz      short loc_10043C4AA
0x10043c45f  mov     ebx, 139Fh
0x10043c464  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043c46b  jz      short loc_10043C495
0x10043c46d  mov     r8d, 79Ah; int
0x10043c473  mov     [rsp+88h+var_58], ebx
0x10043c477  mov     dword ptr [rsp+88h+var_60], r13d
0x10043c47c  mov     eax, [rdi+48h]
0x10043c47f  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10043c486  mov     dword ptr [rsp+88h+lpOverlapped], eax
0x10043c48a  mov     rdx, r12; char *
0x10043c48d  mov     rcx, r15; char *
0x10043c490  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10043c495  mov     r8d, 0C3B4h
0x10043c49b  mov     edx, ebx
0x10043c49d  mov     ecx, [rdi+48h]
0x10043c4a0  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10043c4a5  jmp     loc_10043C6FE
0x10043c4aa  mov     rdx, rsi; struct SNI_Packet *
0x10043c4ad  mov     rcx, rdi; this
0x10043c4b0  call    ?PrepareForAsyncCall@Transport@detail@SNI@@IEAAXPEAVSNI_Packet@@@Z; SNI::detail::Transport::PrepareForAsyncCall(SNI_Packet *)
0x10043c4b5  mov     [rsp+88h+lpOverlapped], rbp; lpOverlapped
0x10043c4ba  xor     r9d, r9d; lpNumberOfBytesRead
0x10043c4bd  mov     r8d, r14d; nNumberOfBytesToRead
0x10043c4c0  mov     rdx, rbx; lpBuffer
0x10043c4c3  mov     rcx, [rdi+40h]; hFile
0x10043c4c7  call    cs:__imp_ReadFile
0x10043c4cd  test    eax, eax
0x10043c4cf  jnz     short loc_10043C510
0x10043c4d1  call    cs:__imp_GetLastError
0x10043c4d7  mov     ebx, eax
0x10043c4d9  cmp     eax, 3E5h
0x10043c4de  jz      loc_10043C6FE
0x10043c4e4  cmp     eax, 0EAh
0x10043c4e9  jnz     loc_10043C5B1
0x10043c4ef  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043c4f6  jz      short loc_10043C510
0x10043c4f8  lea     r9, aErrSnireadfile_1; "ERR|SNIReadFile returned ERROR_MORE_DAT"...
0x10043c4ff  mov     r8d, 7B2h; int
0x10043c505  mov     rdx, r12; char *
0x10043c508  mov     rcx, r15; char *
0x10043c50b  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10043c510  cmp     [rdi+3Dh], r13b
0x10043c514  jz      loc_10043C6D8
0x10043c51a  xor     r9d, r9d; bWait
0x10043c51d  lea     r8, [rsp+88h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x10043c525  mov     rdx, rbp; lpOverlapped
0x10043c528  mov     rcx, [rdi+40h]; hFile
0x10043c52c  call    cs:__imp_GetOverlappedResult
0x10043c532  test    eax, eax
0x10043c534  jnz     loc_10043C5F4
0x10043c53a  call    cs:__imp_GetLastError
0x10043c540  mov     ebx, eax
0x10043c542  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043c549  jz      short loc_10043C573
0x10043c54b  mov     [rsp+88h+var_58], eax
0x10043c54f  mov     dword ptr [rsp+88h+var_60], r13d
0x10043c554  mov     eax, [rdi+48h]
0x10043c557  mov     dword ptr [rsp+88h+lpOverlapped], eax
0x10043c55b  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10043c562  mov     r8d, 7C6h; int
0x10043c568  mov     rdx, r12; char *
0x10043c56b  mov     rcx, r15; char *
0x10043c56e  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10043c573  mov     r8d, 0C3B4h
0x10043c579  mov     edx, ebx
0x10043c57b  mov     ecx, [rdi+48h]
0x10043c57e  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10043c583  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043c58a  jz      loc_10043C6FE
0x10043c590  mov     dword ptr [rsp+88h+lpOverlapped], ebx
0x10043c594  lea     r9, aErrSnigetoverl; "ERR|SNIGetOverlappedResult failed to ob"...
0x10043c59b  mov     r8d, 7C9h; int
0x10043c5a1  mov     rdx, r12; char *
0x10043c5a4  mov     rcx, r15; char *
0x10043c5a7  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10043c5ac  jmp     loc_10043C6FE
0x10043c5b1  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043c5b7  test    al, 2
0x10043c5b9  jz      loc_10043C495
0x10043c5bf  mov     dword ptr [rsp+88h+lpOverlapped], ebx
0x10043c5c3  lea     r9, aErrSnireadfile_0; "ERR|SNIReadFile: %d{WINERR}.\n"
0x10043c5ca  mov     r8d, 7B7h; int
0x10043c5d0  mov     rdx, r12; char *
0x10043c5d3  mov     rcx, r15; char *
0x10043c5d6  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10043c5db  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043c5e1  test    al, 2
0x10043c5e3  jz      loc_10043C495
0x10043c5e9  mov     r8d, 7B8h
0x10043c5ef  jmp     loc_10043C473
0x10043c5f4  mov     eax, [rsp+88h+NumberOfBytesTransferred]
0x10043c5fb  test    eax, eax
0x10043c5fd  jnz     short loc_10043C672
0x10043c5ff  mov     ebx, 0E9h
0x10043c604  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043c60b  jz      short loc_10043C638
0x10043c60d  mov     [rsp+88h+var_58], ebx
0x10043c611  mov     dword ptr [rsp+88h+var_60], 2
0x10043c619  mov     eax, [rdi+48h]
0x10043c61c  mov     dword ptr [rsp+88h+lpOverlapped], eax
0x10043c620  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10043c627  mov     r8d, 7CFh; int
0x10043c62d  mov     rdx, r12; char *
0x10043c630  mov     rcx, r15; char *
0x10043c633  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10043c638  mov     r8d, 0C3B6h
0x10043c63e  mov     edx, ebx
0x10043c640  mov     ecx, [rdi+48h]
0x10043c643  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10043c648  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043c64f  jz      loc_10043C724
0x10043c655  lea     r9, aSni0ByteSucces; "SNI0-byte successful Named Pipe read.\n"
0x10043c65c  mov     r8d, 7D0h; int
0x10043c662  mov     rdx, r12; char *
0x10043c665  mov     rcx, r15; char *
0x10043c668  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10043c66d  jmp     loc_10043C6FE
0x10043c672  mov     ebx, r13d
0x10043c675  add     [rsi+0B0h], eax
0x10043c67b  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 4; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043c682  jz      short loc_10043C6A7
0x10043c684  mov     dword ptr [rsp+88h+lpOverlapped], eax
0x10043c688  lea     r9, aSnireceivePack_0; "SNIReceive Packet, dwBytesRead:%u{DWORD"...
0x10043c68f  mov     r8d, 7DAh; int
0x10043c695  mov     rdx, r12; char *
0x10043c698  mov     rcx, r15; char *
0x10043c69b  call    ?SNIXE_SNI_SNIPKT_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_SNIPKT_ON(char const *,char const *,int,wchar_t const *,...)
0x10043c6a0  mov     eax, [rsp+88h+NumberOfBytesTransferred]
0x10043c6a7  test    cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 100h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043c6b1  jz      short loc_10043C6FE
0x10043c6b3  mov     r9d, [rsi+0B8h]
0x10043c6ba  add     r9, [rsi+0A8h]; void *
0x10043c6c1  mov     dword ptr [rsp+88h+lpOverlapped], eax; int
0x10043c6c5  mov     r8d, 7DBh; int
0x10043c6cb  mov     rdx, r12; char *
0x10043c6ce  mov     rcx, r15; char *
0x10043c6d1  call    ?SNIXE_SNI_SNIPKT_DATA_ON@@YAXPEBD0HPEBXH@Z; SNIXE_SNI_SNIPKT_DATA_ON(char const *,char const *,int,void const *,int)
0x10043c6d6  jmp     short loc_10043C6FE
0x10043c6d8  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043c6df  jz      short loc_10043C6F9
0x10043c6e1  lea     r9, aSnisuppressing_0; "SNISuppressing successful read completi"...
0x10043c6e8  mov     r8d, 7E1h; int
0x10043c6ee  mov     rdx, r12; char *
0x10043c6f1  mov     rcx, r15; char *
0x10043c6f4  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10043c6f9  mov     ebx, 3E5h
0x10043c6fe  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043c705  jz      short loc_10043C724
0x10043c707  mov     dword ptr [rsp+88h+lpOverlapped], ebx
0x10043c70b  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x10043c712  mov     r8d, 7E6h; int
0x10043c718  mov     rdx, r12; char *
0x10043c71b  mov     rcx, r15; char *
0x10043c71e  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10043c723  nop
0x10043c724  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043c72b  jz      short loc_10043C73E
0x10043c72d  mov     r8d, 789h; int
0x10043c733  mov     rdx, r12; char *
0x10043c736  mov     rcx, r15; char *
0x10043c739  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x10043c73e  mov     eax, ebx
0x10043c740  lea     r11, [rsp+88h+var_28]
0x10043c745  mov     rbx, [r11+38h]
0x10043c749  mov     rbp, [r11+40h]
0x10043c74d  mov     rsi, [r11+48h]
0x10043c751  mov     rsp, r11
0x10043c754  pop     r15
0x10043c756  pop     r14
0x10043c758  pop     r13
0x10043c75a  pop     r12
0x10043c75c  pop     rdi
0x10043c75d  retn
```
