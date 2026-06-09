# Np::SendPacketAsync(SNI_Packet *,ulong *,bool)

- ea: `0x10043cb90`
- end: `0x10043ceef`
- name: `?SendPacketAsync@Np@@AEAAKPEAVSNI_Packet@@PEAK_N@Z`
- size: `863`
- prototype: `unsigned int __fastcall(Np *__hidden this, struct SNI_Packet *, LPDWORD lpNumberOfBytesTransferred, bool)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x10043cf00`
- `0x10043cff0`

## callees

- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042bb70`
- `0x10042c270`
- `0x10042c430`
- `0x10042c590`
- `0x1004349f0`
- `0x10043cb90`
- `0x10045a4d0`

## import_xrefs

- `KERNEL32!GetOverlappedResult` at `0x10043cd35`
- `KERNEL32!GetOverlappedResult` at `0x10043cd35`
- `KERNEL32!WriteFile` at `0x10043cc4e`
- `KERNEL32!WriteFile` at `0x10043cc4e`
- `KERNEL32!GetLastError` at `0x10043cc5c`
- `KERNEL32!GetLastError` at `0x10043cd3f`
- `KERNEL32!GetLastError` at `0x10043cc5c`
- `KERNEL32!GetLastError` at `0x10043cd3f`

## string_xrefs

- `0x10043ce68`: `sql\common\dk\sni\include\sni_io.hpp`
- `0x10043cbc1`: `sql\common\dk\sni\src\np.cpp`
- `0x10043cc9f`: `sql\common\dk\sni\src\np.cpp`
- `0x10043ccdd`: `sql\common\dk\sni\src\np.cpp`
- `0x10043cd0e`: `sql\common\dk\sni\src\np.cpp`
- `0x10043cd77`: `sql\common\dk\sni\src\np.cpp`
- `0x10043cdc8`: `sql\common\dk\sni\src\np.cpp`
- `0x10043cdfb`: `sql\common\dk\sni\src\np.cpp`
- `0x10043ce26`: `sql\common\dk\sni\src\np.cpp`
- `0x10043cea0`: `sql\common\dk\sni\src\np.cpp`
- `0x10043cec3`: `sql\common\dk\sni\src\np.cpp`
- `0x10043ccc9`: `ERR|SNISend Packet Error, Bytes Try To Write:%d{DWORD}\n`
- `0x10043ce12`: `SNISuppressing successful write completion and returning ERROR_IO_PENDING.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Np::SendPacketAsync(Np *this, struct SNI_Packet *a2, LPDWORD lpNumberOfBytesTransferred, char a4)
{
  unsigned int v8; // ebx
  const void *v9; // rbp
  DWORD v10; // r12d
  struct _OVERLAPPED *v11; // r15
  const wchar_t *v12; // r9
  DWORD LastError; // eax
  DWORD v14; // eax
  LPOVERLAPPED lpOverlapped; // [rsp+20h] [rbp-68h]
  __int64 v17; // [rsp+28h] [rbp-60h]
  __int64 v18; // [rsp+30h] [rbp-58h]

  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
  {
    HIDWORD(v18) = HIDWORD(lpNumberOfBytesTransferred);
    HIDWORD(v17) = HIDWORD(a2);
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\np.cpp",
      "Np::SendPacketAsync",
      2160,
      L"API|SNI%u#, pPacket: %p{SNI_Packet*}, pdwBytesWritten: %p{DWORD*}\n",
      *((_DWORD *)this + 11));
  }
  v8 = 0;
  v9 = (const void *)(*((_QWORD *)a2 + 21) + *((unsigned int *)a2 + 46));
  v10 = *((_DWORD *)a2 + 44);
  if ( a4 )
  {
    v11 = (struct _OVERLAPPED *)((char *)a2 + 16);
    SNI::detail::Transport::PrepareForAsyncCall(this, a2);
  }
  else
  {
    v11 = (struct _OVERLAPPED *)((char *)this + 88);
  }
  v11->Pointer = 0;
  if ( !WriteFile(*((HANDLE *)this + 8), v9, v10, 0, v11) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError != 997 )
    {
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        LODWORD(v18) = LastError;
        LODWORD(v17) = 0;
        LODWORD(lpOverlapped) = *((_DWORD *)this + 18);
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\np.cpp",
          "Np::SendPacketAsync",
          2216,
          L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
          lpOverlapped,
          v17,
          v18);
      }
      SNISetLastError(*((unsigned int *)this + 18), v8, 50100);
      if ( (g_XeSniPkg_enabledBitmap & 4) != 0 )
      {
        LODWORD(lpOverlapped) = v10;
        SNIXE_SNI_SNIPKT_ON(
          "sql\\common\\dk\\sni\\src\\np.cpp",
          "Np::SendPacketAsync",
          2219,
          L"ERR|SNISend Packet Error, Bytes Try To Write:%d{DWORD}\n",
          lpOverlapped);
      }
      if ( (g_XeSniPkg_enabledBitmap & 0x100) != 0 )
        SNIXE_SNI_SNIPKT_DATA_ON("sql\\common\\dk\\sni\\src\\np.cpp", "Np::SendPacketAsync", 2220, v9, v10);
      goto LABEL_31;
    }
    goto LABEL_27;
  }
  if ( !*((_BYTE *)this + 61) )
  {
    if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
      SNIXE_SNI_TRACE_ON(
        "sql\\common\\dk\\sni\\src\\np.cpp",
        "Np::SendPacketAsync",
        2241,
        L"SNISuppressing successful write completion and returning ERROR_IO_PENDING.\n");
    v8 = 997;
    goto LABEL_27;
  }
  if ( !GetOverlappedResult(*((HANDLE *)this + 8), v11, lpNumberOfBytesTransferred, 0) )
  {
    v14 = GetLastError();
    v8 = v14;
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      LODWORD(v18) = v14;
      LODWORD(v17) = 0;
      LODWORD(lpOverlapped) = *((_DWORD *)this + 18);
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\np.cpp",
        "Np::SendPacketAsync",
        2231,
        L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
        lpOverlapped,
        v17,
        v18);
    }
    SNISetLastError(*((unsigned int *)this + 18), v8, 50100);
    if ( v8 != 997 )
      goto LABEL_31;
LABEL_27:
    if ( !a4 )
    {
      if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
      {
        LODWORD(lpOverlapped) = *((_DWORD *)a2 + 63);
        SNIXE_SNI_TRACE_ON(
          "sql\\common\\dk\\sni\\include\\sni_io.hpp",
          "SNIPacketAddRef",
          802,
          L"API|SNI%u#{SNI_Packet}, pPacket: %p{SNI_Packet*}\n",
          lpOverlapped,
          a2);
      }
      _InterlockedIncrement((volatile signed __int32 *)a2 + 47);
      *((_QWORD *)this + 15) = a2;
    }
    goto LABEL_31;
  }
  if ( (g_XeSniPkg_enabledBitmap & 4) != 0 )
  {
    LODWORD(lpOverlapped) = *lpNumberOfBytesTransferred;
    SNIXE_SNI_SNIPKT_ON(
      "sql\\common\\dk\\sni\\src\\np.cpp",
      "Np::SendPacketAsync",
      2235,
      L"SNISend Packet, BytesWritten:%d{DWORD}\n",
      lpOverlapped);
  }
  if ( (g_XeSniPkg_enabledBitmap & 0x100) != 0 )
    SNIXE_SNI_SNIPKT_DATA_ON(
      "sql\\common\\dk\\sni\\src\\np.cpp",
      "Np::SendPacketAsync",
      2236,
      v9,
      *lpNumberOfBytesTransferred);
LABEL_31:
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(lpOverlapped) = v8;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\np.cpp",
      "Np::SendPacketAsync",
      2263,
      L"RET|SNI%d{WINERR}\n",
      lpOverlapped);
  }
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\np.cpp", "Np::SendPacketAsync", 2160, v12);
  return v8;
}

```

## disassembly

```asm
0x10043cb90  mov     rax, rsp
0x10043cb93  push    rdi
0x10043cb94  push    r12
0x10043cb96  push    r13
0x10043cb98  push    r14
0x10043cb9a  push    r15
0x10043cb9c  sub     rsp, 60h
0x10043cba0  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x10043cba8  mov     [rax+8], rbx
0x10043cbac  mov     [rax+10h], rbp
0x10043cbb0  mov     [rax+18h], rsi
0x10043cbb4  movzx   r13d, r9b
0x10043cbb8  mov     r14, r8
0x10043cbbb  mov     rdi, rdx
0x10043cbbe  mov     rsi, rcx
0x10043cbc1  lea     rcx, aSqlCommonDkSni_22; "sql\\common\\dk\\sni\\src\\np.cpp"
0x10043cbc8  mov     [rax-40h], rcx
0x10043cbcc  lea     rdx, aNpSendpacketas; "Np::SendPacketAsync"
0x10043cbd3  mov     [rax-38h], rdx
0x10043cbd7  mov     dword ptr [rax-30h], 870h
0x10043cbde  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043cbe5  jz      short loc_10043CC08
0x10043cbe7  mov     [rax-58h], r8
0x10043cbeb  mov     [rax-60h], rdi
0x10043cbef  mov     eax, [rsi+2Ch]
0x10043cbf2  mov     dword ptr [rsp+88h+lpOverlapped], eax
0x10043cbf6  lea     r9, aApiSniUPpacket_3; "API|SNI%u#, pPacket: %p{SNI_Packet*}, p"...
0x10043cbfd  mov     r8d, 870h; int
0x10043cc03  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x10043cc08  xor     ebx, ebx
0x10043cc0a  mov     ebp, [rdi+0B8h]
0x10043cc10  add     rbp, [rdi+0A8h]
0x10043cc17  mov     r12d, [rdi+0B0h]
0x10043cc1e  test    r13b, r13b
0x10043cc21  jz      short loc_10043CC34
0x10043cc23  lea     r15, [rdi+10h]
0x10043cc27  mov     rdx, rdi; struct SNI_Packet *
0x10043cc2a  mov     rcx, rsi; this
0x10043cc2d  call    ?PrepareForAsyncCall@Transport@detail@SNI@@IEAAXPEAVSNI_Packet@@@Z; SNI::detail::Transport::PrepareForAsyncCall(SNI_Packet *)
0x10043cc32  jmp     short loc_10043CC38
0x10043cc34  lea     r15, [rsi+58h]
0x10043cc38  mov     [r15+10h], rbx
0x10043cc3c  mov     [rsp+88h+lpOverlapped], r15; lpOverlapped
0x10043cc41  xor     r9d, r9d; lpNumberOfBytesWritten
0x10043cc44  mov     r8d, r12d; nNumberOfBytesToWrite
0x10043cc47  mov     rdx, rbp; lpBuffer
0x10043cc4a  mov     rcx, [rsi+40h]; hFile
0x10043cc4e  call    cs:__imp_WriteFile
0x10043cc54  test    eax, eax
0x10043cc56  jnz     loc_10043CD1F
0x10043cc5c  call    cs:__imp_GetLastError
0x10043cc62  mov     ebx, eax
0x10043cc64  cmp     eax, 3E5h
0x10043cc69  jz      loc_10043CE37
0x10043cc6f  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043cc76  jz      short loc_10043CCAB
0x10043cc78  mov     [rsp+88h+var_58], eax
0x10043cc7c  mov     dword ptr [rsp+88h+var_60], 0
0x10043cc84  mov     ecx, [rsi+48h]
0x10043cc87  mov     dword ptr [rsp+88h+lpOverlapped], ecx
0x10043cc8b  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10043cc92  mov     r8d, 8A8h; int
0x10043cc98  lea     rdx, aNpSendpacketas; "Np::SendPacketAsync"
0x10043cc9f  lea     rcx, aSqlCommonDkSni_22; "sql\\common\\dk\\sni\\src\\np.cpp"
0x10043cca6  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10043ccab  mov     r8d, 0C3B4h
0x10043ccb1  mov     edx, ebx
0x10043ccb3  mov     ecx, [rsi+48h]
0x10043ccb6  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10043ccbb  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 4; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043ccc2  jz      short loc_10043CCE9
0x10043ccc4  mov     dword ptr [rsp+88h+lpOverlapped], r12d
0x10043ccc9  lea     r9, aErrSnisendPack_1; "ERR|SNISend Packet Error, Bytes Try To "...
0x10043ccd0  mov     r8d, 8ABh; int
0x10043ccd6  lea     rdx, aNpSendpacketas; "Np::SendPacketAsync"
0x10043ccdd  lea     rcx, aSqlCommonDkSni_22; "sql\\common\\dk\\sni\\src\\np.cpp"
0x10043cce4  call    ?SNIXE_SNI_SNIPKT_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_SNIPKT_ON(char const *,char const *,int,wchar_t const *,...)
0x10043cce9  test    cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 100h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043ccf3  jz      loc_10043CE7F
0x10043ccf9  mov     dword ptr [rsp+88h+lpOverlapped], r12d; int
0x10043ccfe  mov     r9, rbp; void *
0x10043cd01  mov     r8d, 8ACh; int
0x10043cd07  lea     rdx, aNpSendpacketas; "Np::SendPacketAsync"
0x10043cd0e  lea     rcx, aSqlCommonDkSni_22; "sql\\common\\dk\\sni\\src\\np.cpp"
0x10043cd15  call    ?SNIXE_SNI_SNIPKT_DATA_ON@@YAXPEBD0HPEBXH@Z; SNIXE_SNI_SNIPKT_DATA_ON(char const *,char const *,int,void const *,int)
0x10043cd1a  jmp     loc_10043CE7F
0x10043cd1f  cmp     [rsi+3Dh], bl
0x10043cd22  jz      loc_10043CE09
0x10043cd28  xor     r9d, r9d; bWait
0x10043cd2b  mov     r8, r14; lpNumberOfBytesTransferred
0x10043cd2e  mov     rdx, r15; lpOverlapped
0x10043cd31  mov     rcx, [rsi+40h]; hFile
0x10043cd35  call    cs:__imp_GetOverlappedResult
0x10043cd3b  test    eax, eax
0x10043cd3d  jnz     short loc_10043CDA4
0x10043cd3f  call    cs:__imp_GetLastError
0x10043cd45  mov     ebx, eax
0x10043cd47  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043cd4e  jz      short loc_10043CD83
0x10043cd50  mov     [rsp+88h+var_58], eax
0x10043cd54  mov     dword ptr [rsp+88h+var_60], 0
0x10043cd5c  mov     eax, [rsi+48h]
0x10043cd5f  mov     dword ptr [rsp+88h+lpOverlapped], eax
0x10043cd63  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10043cd6a  mov     r8d, 8B7h; int
0x10043cd70  lea     rdx, aNpSendpacketas; "Np::SendPacketAsync"
0x10043cd77  lea     rcx, aSqlCommonDkSni_22; "sql\\common\\dk\\sni\\src\\np.cpp"
0x10043cd7e  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10043cd83  mov     r8d, 0C3B4h
0x10043cd89  mov     edx, ebx
0x10043cd8b  mov     ecx, [rsi+48h]
0x10043cd8e  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10043cd93  cmp     ebx, 3E5h
0x10043cd99  jz      loc_10043CE37
0x10043cd9f  jmp     loc_10043CE7F
0x10043cda4  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 4; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043cdab  jz      short loc_10043CDD4
0x10043cdad  mov     eax, [r14]
0x10043cdb0  mov     dword ptr [rsp+88h+lpOverlapped], eax
0x10043cdb4  lea     r9, aSnisendPacketB; "SNISend Packet, BytesWritten:%d{DWORD}"...
0x10043cdbb  mov     r8d, 8BBh; int
0x10043cdc1  lea     rdx, aNpSendpacketas; "Np::SendPacketAsync"
0x10043cdc8  lea     rcx, aSqlCommonDkSni_22; "sql\\common\\dk\\sni\\src\\np.cpp"
0x10043cdcf  call    ?SNIXE_SNI_SNIPKT_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_SNIPKT_ON(char const *,char const *,int,wchar_t const *,...)
0x10043cdd4  test    cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 100h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043cdde  jz      loc_10043CE7F
0x10043cde4  mov     eax, [r14]
0x10043cde7  mov     dword ptr [rsp+88h+lpOverlapped], eax; int
0x10043cdeb  mov     r9, rbp; void *
0x10043cdee  mov     r8d, 8BCh; int
0x10043cdf4  lea     rdx, aNpSendpacketas; "Np::SendPacketAsync"
0x10043cdfb  lea     rcx, aSqlCommonDkSni_22; "sql\\common\\dk\\sni\\src\\np.cpp"
0x10043ce02  call    ?SNIXE_SNI_SNIPKT_DATA_ON@@YAXPEBD0HPEBXH@Z; SNIXE_SNI_SNIPKT_DATA_ON(char const *,char const *,int,void const *,int)
0x10043ce07  jmp     short loc_10043CE7F
0x10043ce09  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043ce10  jz      short loc_10043CE32
0x10043ce12  lea     r9, aSnisuppressing; "SNISuppressing successful write complet"...
0x10043ce19  mov     r8d, 8C1h; int
0x10043ce1f  lea     rdx, aNpSendpacketas; "Np::SendPacketAsync"
0x10043ce26  lea     rcx, aSqlCommonDkSni_22; "sql\\common\\dk\\sni\\src\\np.cpp"
0x10043ce2d  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10043ce32  mov     ebx, 3E5h
0x10043ce37  test    r13b, r13b
0x10043ce3a  jnz     short loc_10043CE7F
0x10043ce3c  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043ce43  jz      short loc_10043CE74
0x10043ce45  mov     [rsp+88h+var_60], rdi
0x10043ce4a  mov     eax, [rdi+0FCh]
0x10043ce50  mov     dword ptr [rsp+88h+lpOverlapped], eax
0x10043ce54  lea     r9, aApiSniUSniPack; "API|SNI%u#{SNI_Packet}, pPacket: %p{SNI"...
0x10043ce5b  mov     r8d, 322h; int
0x10043ce61  lea     rdx, aSnipacketaddre; "SNIPacketAddRef"
0x10043ce68  lea     rcx, aSqlCommonDkSni_15; "sql\\common\\dk\\sni\\include\\sni_io.h"...
0x10043ce6f  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10043ce74  lock inc dword ptr [rdi+0BCh]
0x10043ce7b  mov     [rsi+78h], rdi
0x10043ce7f  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043ce86  jz      short loc_10043CEAD
0x10043ce88  mov     dword ptr [rsp+88h+lpOverlapped], ebx
0x10043ce8c  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x10043ce93  mov     r8d, 8D7h; int
0x10043ce99  lea     rdx, aNpSendpacketas; "Np::SendPacketAsync"
0x10043cea0  lea     rcx, aSqlCommonDkSni_22; "sql\\common\\dk\\sni\\src\\np.cpp"
0x10043cea7  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10043ceac  nop
0x10043cead  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043ceb4  jz      short loc_10043CECF
0x10043ceb6  mov     r8d, 870h; int
0x10043cebc  lea     rdx, aNpSendpacketas; "Np::SendPacketAsync"
0x10043cec3  lea     rcx, aSqlCommonDkSni_22; "sql\\common\\dk\\sni\\src\\np.cpp"
0x10043ceca  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x10043cecf  mov     eax, ebx
0x10043ced1  lea     r11, [rsp+88h+var_28]
0x10043ced6  mov     rbx, [r11+30h]
0x10043ceda  mov     rbp, [r11+38h]
0x10043cede  mov     rsi, [r11+40h]
0x10043cee2  mov     rsp, r11
0x10043cee5  pop     r15
0x10043cee7  pop     r14
0x10043cee9  pop     r13
0x10043ceeb  pop     r12
0x10043ceed  pop     rdi
0x10043ceee  retn
```
