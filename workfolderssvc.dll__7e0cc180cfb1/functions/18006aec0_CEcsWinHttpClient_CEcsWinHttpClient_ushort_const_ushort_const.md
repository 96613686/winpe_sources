# CEcsWinHttpClient::CEcsWinHttpClient(ushort const *,ushort const *)

- ea: `0x18006aec0`
- end: `0x18006b218`
- name: `??0CEcsWinHttpClient@@QEAA@PEBG0@Z`
- size: `856`
- prototype: `CEcsWinHttpClient *__fastcall(CEcsWinHttpClient *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800735c8`

## callees

- `0x180002ab0`
- `0x1800035f8`
- `0x180003604`
- `0x180006fa0`
- `0x180007b9c`
- `0x180007e10`
- `0x180008bdc`
- `0x180011314`
- `0x180015150`
- `0x180015904`
- `0x18001db58`
- `0x180035564`
- `0x180063c08`
- `0x18006aec0`
- `0x18006e090`

## import_xrefs

- `KERNEL32!GetComputerNameW` at `0x18006b12d`
- `KERNEL32!GetComputerNameW` at `0x18006b12d`
- `KERNEL32!GetVersionExW` at `0x18006b0fa`
- `KERNEL32!GetVersionExW` at `0x18006b0fa`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18006af16`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18006af16`
- `WINHTTP!WinHttpOpen` at `0x18006b070`
- `WINHTTP!WinHttpOpen` at `0x18006b070`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
CEcsWinHttpClient *__fastcall CEcsWinHttpClient::CEcsWinHttpClient(
        CEcsWinHttpClient *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  char v6; // r14
  _BYTE *v7; // rax
  HINTERNET v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  int pExceptionObject; // [rsp+40h] [rbp-C0h] BYREF
  DWORD nSize; // [rsp+44h] [rbp-BCh] BYREF
  int LastFailureAsHRESULT; // [rsp+48h] [rbp-B8h] BYREF
  int v16; // [rsp+4Ch] [rbp-B4h]
  char v17; // [rsp+50h] [rbp-B0h]
  const char *v18; // [rsp+58h] [rbp-A8h]
  __int64 v19; // [rsp+60h] [rbp-A0h]
  CEcsWinHttpClient *v20; // [rsp+68h] [rbp-98h]
  _OSVERSIONINFOW VersionInformation; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Buffer[16]; // [rsp+190h] [rbp+90h] BYREF
  unsigned __int16 v23; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v24[510]; // [rsp+1B2h] [rbp+B2h] BYREF

  v20 = this;
  *(_QWORD *)this = &IEcsCommunicationClient::`vftable';
  *(_QWORD *)this = &CEcsWinHttpClient::`vftable';
  InitializeSRWLock((PSRWLOCK)this + 1);
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  std::wstring::wstring((char *)this + 40);
  *((_BYTE *)this + 74) = 0;
  std::wstring::wstring((char *)this + 80);
  ATL::CComPtrBase<IFileInfoFromDisk>::CComPtrBase<IFileInfoFromDisk>((char *)this + 112);
  v6 = 1;
  *((_QWORD *)this + 15) = 1;
  std::wstring::wstring((char *)this + 128);
  std::wstring::wstring((char *)this + 160);
  std::wstring::wstring((char *)this + 192);
  std::wstring::wstring((char *)this + 224);
  std::wstring::wstring((char *)this + 256);
  std::wstring::wstring((char *)this + 288);
  *((_QWORD *)this + 40) = 0;
  if ( !a3 )
    a3 = &Format;
  std::wstring::wstring((char *)this + 328, a3);
  if ( !a2 )
    a2 = &Format;
  std::wstring::wstring((char *)this + 360, a2);
  *((_DWORD *)this + 98) = 1;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) == 0 )
    {
LABEL_11:
      v6 = 0;
      goto LABEL_12;
    }
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 10, &WPP_13baba31ff4d3f580777c125170b76f8_Traceguids);
      v7 = WPP_GLOBAL_Control;
    }
  }
  if ( (v7[68] & 8) == 0 || v7[65] < 6u )
    goto LABEL_11;
LABEL_12:
  LastFailureAsHRESULT = 0;
  v16 = 54;
  v17 = v6;
  v18 = "CEcsWinHttpClient::CEcsWinHttpClient";
  v19 = 0;
  v8 = WinHttpOpen(L"MS_WorkFoldersClient", 4u, 0, 0, 0);
  *((_QWORD *)this + 2) = v8;
  if ( !v8 )
  {
    LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
    HIWORD(v16) = 57;
    pExceptionObject = LastFailureAsHRESULT;
    throw (long *)&pExceptionObject;
  }
  LastFailureAsHRESULT = 0;
  LOWORD(v16) = 57;
  *((_DWORD *)this + 99) = 600000;
  *((_DWORD *)this + 100) = 10;
  CEcsWinHttpClient::GetRegistryOverrides(this);
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x110u);
  VersionInformation.dwOSVersionInfoSize = 276;
  GetVersionExW(&VersionInformation);
  memset(Buffer, 0, sizeof(Buffer));
  nSize = 16;
  GetComputerNameW(Buffer, &nSize);
  v23 = 0;
  memset_0(v24, 0, sizeof(v24));
  StringCchPrintfW(
    &v23,
    0x100u,
    L"%s:%s,Windows,%d,%d,%s\r\n",
    L"x-ecs-devicename",
    Buffer,
    VersionInformation.dwMajorVersion,
    VersionInformation.dwMinorVersion,
    L"MS_WorkFoldersClient");
  std::wstring::operator=((char *)this + 288, &v23);
  if ( *((_QWORD *)this + 47) )
  {
    v9 = std::wstring::append((char *)this + 288, L"x-ecs-replica-id");
    v10 = std::wstring::append(v9, L": ");
    v11 = std::wstring::append(v10, (char *)this + 360);
    std::wstring::append(v11, L"\r\n");
  }
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&LastFailureAsHRESULT);
  return this;
}

```

## disassembly

```asm
0x18006aec0  mov     [rsp-8+arg_18], rbx
0x18006aec5  push    rbp
0x18006aec6  push    rsi
0x18006aec7  push    rdi
0x18006aec8  push    r12
0x18006aeca  push    r13
0x18006aecc  push    r14
0x18006aece  push    r15
0x18006aed0  lea     rbp, [rsp-2C0h]
0x18006aed8  sub     rsp, 3C0h
0x18006aedf  mov     rax, cs:__security_cookie
0x18006aee6  xor     rax, rsp
0x18006aee9  mov     [rbp+2F0h+var_40], rax
0x18006aef0  mov     rbx, r8
0x18006aef3  mov     rdi, rdx
0x18006aef6  mov     rsi, rcx
0x18006aef9  mov     [rsp+3F0h+var_388], rcx
0x18006aefe  lea     rax, ??_7IEcsCommunicationClient@@6B@; const IEcsCommunicationClient::`vftable'
0x18006af05  mov     [rcx], rax
0x18006af08  lea     rax, ??_7CEcsWinHttpClient@@6B@; const CEcsWinHttpClient::`vftable'
0x18006af0f  mov     [rcx], rax
0x18006af12  add     rcx, 8; SRWLock
0x18006af16  call    cs:__imp_InitializeSRWLock
0x18006af1c  xor     r13d, r13d
0x18006af1f  mov     [rsi+18h], r13
0x18006af23  mov     [rsi+20h], r13
0x18006af27  lea     rcx, [rsi+28h]
0x18006af2b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18006af30  nop
0x18006af31  mov     [rsi+4Ah], r13b
0x18006af35  lea     rcx, [rsi+50h]
0x18006af39  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18006af3e  nop
0x18006af3f  lea     rcx, [rsi+70h]
0x18006af43  call    ??0?$CComPtrBase@UIFileInfoFromDisk@@@ATL@@IEAA@PEAUIFileInfoFromDisk@@@Z; ATL::CComPtrBase<IFileInfoFromDisk>::CComPtrBase<IFileInfoFromDisk>(IFileInfoFromDisk *)
0x18006af48  nop
0x18006af49  lea     r14d, [r13+1]
0x18006af4d  mov     [rsi+78h], r14
0x18006af51  lea     rcx, [rsi+80h]
0x18006af58  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18006af5d  nop
0x18006af5e  lea     rcx, [rsi+0A0h]
0x18006af65  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18006af6a  nop
0x18006af6b  lea     rcx, [rsi+0C0h]
0x18006af72  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18006af77  nop
0x18006af78  lea     rcx, [rsi+0E0h]
0x18006af7f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18006af84  nop
0x18006af85  lea     rcx, [rsi+100h]
0x18006af8c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18006af91  nop
0x18006af92  lea     r15, [rsi+120h]
0x18006af99  mov     rcx, r15
0x18006af9c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18006afa1  nop
0x18006afa2  mov     [rsi+140h], r13
0x18006afa9  lea     r12, Format
0x18006afb0  test    rbx, rbx
0x18006afb3  cmovz   rbx, r12
0x18006afb7  lea     rcx, [rsi+148h]
0x18006afbe  mov     rdx, rbx
0x18006afc1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006afc6  nop
0x18006afc7  lea     rbx, [rsi+168h]
0x18006afce  test    rdi, rdi
0x18006afd1  cmovz   rdi, r12
0x18006afd5  mov     rdx, rdi
0x18006afd8  mov     rcx, rbx
0x18006afdb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006afe0  nop
0x18006afe1  mov     [rsi+188h], r14d
0x18006afe8  lea     rcx, WPP_GLOBAL_Control
0x18006afef  lea     r12d, [r13+0Ah]
0x18006aff3  mov     rax, cs:WPP_GLOBAL_Control
0x18006affa  cmp     rax, rcx
0x18006affd  jz      short loc_18006B025
0x18006afff  test    byte ptr [rax+44h], 8
0x18006b003  jz      short loc_18006B031
0x18006b005  cmp     byte ptr [rax+41h], 6
0x18006b009  jb      short loc_18006B025
0x18006b00b  mov     edx, r12d
0x18006b00e  lea     r8, WPP_13baba31ff4d3f580777c125170b76f8_Traceguids
0x18006b015  mov     rcx, [rax+38h]
0x18006b019  call    WPP_SF_
0x18006b01e  mov     rax, cs:WPP_GLOBAL_Control
0x18006b025  test    byte ptr [rax+44h], 8
0x18006b029  jz      short loc_18006B031
0x18006b02b  cmp     byte ptr [rax+41h], 6
0x18006b02f  jnb     short loc_18006B034
0x18006b031  mov     r14b, r13b
0x18006b034  mov     [rsp+3F0h+var_3A8], r13d
0x18006b039  mov     [rsp+3F0h+var_3A4], 36h ; '6'
0x18006b041  mov     [rsp+3F0h+var_3A0], r14b
0x18006b046  lea     rax, aCecswinhttpcli; "CEcsWinHttpClient::CEcsWinHttpClient"
0x18006b04d  mov     [rsp+3F0h+var_398], rax
0x18006b052  mov     [rsp+3F0h+var_390], r13
0x18006b057  mov     [rsp+3F0h+dwFlags], r13d; dwFlags
0x18006b05c  xor     r9d, r9d; pszProxyBypassW
0x18006b05f  xor     r8d, r8d; pszProxyW
0x18006b062  lea     edx, [r9+4]; dwAccessType
0x18006b066  lea     rdi, pszAgentW; "MS_WorkFoldersClient"
0x18006b06d  mov     rcx, rdi; pszAgentW
0x18006b070  call    cs:__imp_WinHttpOpen
0x18006b076  mov     rcx, rax
0x18006b079  mov     [rsi+10h], rax
0x18006b07d  mov     eax, [rsp+3F0h+var_3A8]
0x18006b081  mov     [rsp+3F0h+var_3A8], eax
0x18006b085  test    rcx, rcx
0x18006b088  jnz     short loc_18006B0B3
0x18006b08a  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x18006b08f  mov     [rsp+3F0h+var_3A8], eax
0x18006b093  mov     ecx, 39h ; '9'
0x18006b098  mov     word ptr [rsp+3F0h+var_3A4+2], cx
0x18006b09d  mov     [rsp+3F0h+pExceptionObject], eax
0x18006b0a1  lea     rdx, _TI1J; pThrowInfo
0x18006b0a8  lea     rcx, [rsp+3F0h+pExceptionObject]; pExceptionObject
0x18006b0ad  call    _CxxThrowException_0
0x18006b0b3  mov     [rsp+3F0h+var_3A8], r13d
0x18006b0b8  mov     ecx, 39h ; '9'
0x18006b0bd  mov     word ptr [rsp+3F0h+var_3A4], cx
0x18006b0c2  mov     dword ptr [rsi+18Ch], 927C0h
0x18006b0cc  mov     [rsi+190h], r12d
0x18006b0d3  mov     rcx, rsi; this
0x18006b0d6  call    ?GetRegistryOverrides@CEcsWinHttpClient@@AEAAXXZ; CEcsWinHttpClient::GetRegistryOverrides(void)
0x18006b0db  xor     edx, edx; Val
0x18006b0dd  mov     r8d, 110h; Size
0x18006b0e3  lea     rcx, [rsp+3F0h+VersionInformation.dwMajorVersion]; void *
0x18006b0e8  call    memset_0
0x18006b0ed  mov     [rsp+3F0h+VersionInformation.dwOSVersionInfoSize], 114h
0x18006b0f5  lea     rcx, [rsp+3F0h+VersionInformation]; lpVersionInformation
0x18006b0fa  call    cs:__imp_GetVersionExW
0x18006b100  mov     [rbp+2F0h+Buffer], r13w
0x18006b108  xorps   xmm0, xmm0
0x18006b10b  movups  xmmword ptr [rbp+2F0h+var_25E], xmm0
0x18006b112  movups  xmmword ptr [rbp+2F0h+var_25E+0Eh], xmm0
0x18006b119  mov     [rsp+3F0h+nSize], 10h
0x18006b121  lea     rdx, [rsp+3F0h+nSize]; nSize
0x18006b126  lea     rcx, [rbp+2F0h+Buffer]; lpBuffer
0x18006b12d  call    cs:__imp_GetComputerNameW
0x18006b133  mov     [rbp+2F0h+var_240], r13w
0x18006b13b  xor     edx, edx; Val
0x18006b13d  mov     r8d, 1FEh; Size
0x18006b143  lea     rcx, [rbp+2F0h+var_23E]; void *
0x18006b14a  call    memset_0
0x18006b14f  mov     [rsp+3F0h+var_3B8], rdi
0x18006b154  mov     eax, [rsp+3F0h+VersionInformation.dwMinorVersion]
0x18006b158  mov     [rsp+3F0h+var_3C0], eax
0x18006b15c  mov     eax, [rsp+3F0h+VersionInformation.dwMajorVersion]
0x18006b160  mov     [rsp+3F0h+var_3C8], eax
0x18006b164  lea     rax, [rbp+2F0h+Buffer]
0x18006b16b  mov     qword ptr [rsp+3F0h+dwFlags], rax
0x18006b170  lea     r9, aXEcsDevicename; "x-ecs-devicename"
0x18006b177  lea     r8, aSSWindowsDDS; "%s:%s,Windows,%d,%d,%s\r\n"
0x18006b17e  mov     edx, 100h; unsigned __int64
0x18006b183  lea     rcx, [rbp+2F0h+var_240]; unsigned __int16 *
0x18006b18a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006b18f  lea     rdx, [rbp+2F0h+var_240]
0x18006b196  mov     rcx, r15
0x18006b199  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator=(ushort const * const)
0x18006b19e  cmp     [rsi+178h], r13
0x18006b1a5  jz      short loc_18006B1E0
0x18006b1a7  lea     rdx, aXEcsReplicaId; "x-ecs-replica-id"
0x18006b1ae  mov     rcx, r15
0x18006b1b1  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18006b1b6  lea     rdx, asc_180156290; ": "
0x18006b1bd  mov     rcx, rax
0x18006b1c0  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18006b1c5  mov     rdx, rbx
0x18006b1c8  mov     rcx, rax
0x18006b1cb  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18006b1d0  lea     rdx, asc_180156288; "\r\n"
0x18006b1d7  mov     rcx, rax
0x18006b1da  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18006b1df  nop
0x18006b1e0  lea     rcx, [rsp+3F0h+var_3A8]; this
0x18006b1e5  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x18006b1ea  nop
0x18006b1eb  mov     rax, rsi
0x18006b1ee  mov     rcx, [rbp+2F0h+var_40]
0x18006b1f5  xor     rcx, rsp; StackCookie
0x18006b1f8  call    __security_check_cookie
0x18006b1fd  mov     rbx, [rsp+3F0h+arg_18]
0x18006b205  add     rsp, 3C0h
0x18006b20c  pop     r15
0x18006b20e  pop     r14
0x18006b210  pop     r13
0x18006b212  pop     r12
0x18006b214  pop     rdi
0x18006b215  pop     rsi
0x18006b216  pop     rbp
0x18006b217  retn
```
