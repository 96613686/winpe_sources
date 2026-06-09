# CTftpServer::Initialize(void *)

- ea: `0x1800012e0`
- end: `0x18000174d`
- name: `?Initialize@CTftpServer@@QEAAKPEAX@Z`
- size: `1133`
- prototype: `__int64 __fastcall(CTftpServer *this, void *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180005b00`

## callees

- `0x1800012e0`
- `0x180001950`
- `0x180002544`
- `0x180002d84`
- `0x18000339c`
- `0x180008638`
- `0x1800093e0`
- `0x18003ce78`
- `0x1800607b0`
- `0x180060e5a`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000143c`
- `KERNEL32!GetLastError` at `0x18000143c`
- `ADVAPI32!RegisterEventSourceW` at `0x180001424`
- `ADVAPI32!RegisterEventSourceW` at `0x180001424`
- `WDSSRV!WdsRegisterCallback` at `0x18000151c`
- `WDSSRV!WdsRegisterCallback` at `0x180001552`
- `WDSSRV!WdsRegisterCallback` at `0x180001588`
- `WDSSRV!WdsRegisterCallback` at `0x18000151c`
- `WDSSRV!WdsRegisterCallback` at `0x180001552`
- `WDSSRV!WdsRegisterCallback` at `0x180001588`
- `WDSSRV!WdsEndpointOpen` at `0x180001622`
- `WDSSRV!WdsEndpointOpen` at `0x1800016e2`
- `WDSSRV!WdsEndpointOpen` at `0x180001622`
- `WDSSRV!WdsEndpointOpen` at `0x1800016e2`
- `WDSCSL!WdsClientInitializeLibrary` at `0x1800013e6`
- `WDSCSL!WdsClientInitializeLibrary` at `0x1800013e6`
- `WS2_32!__imp_WSAStartup` at `0x18000138e`
- `WS2_32!__imp_WSAStartup` at `0x18000138e`

## string_xrefs

- `0x180001372`: `onecore\base\eco\wds\wdslib\common\src\winsockinitializer.cpp`
- `0x1800013ad`: `onecore\base\eco\wds\wdslib\common\src\winsockinitializer.cpp`

## pseudocode

```c
__int64 __fastcall CTftpServer::Initialize(CTftpServer *this, void *a2)
{
  DWORD LastError; // ebx
  const char *v5; // rdx
  const char *v6; // rdx
  unsigned int v7; // eax
  const char *v8; // rdx
  const char *v9; // rdx
  const char *v10; // rdx
  const char *v11; // rdx
  const char *v12; // rdx
  const char *v13; // rdx
  const char *v14; // rdx
  const char *v15; // rdx
  const char *v16; // rdx
  const char *v17; // rdx
  const char *v18; // rdx
  const char *v19; // rdx
  const char *v20; // rdx
  int v22; // [rsp+40h] [rbp-C0h] BYREF
  int v23; // [rsp+44h] [rbp-BCh]
  int v24; // [rsp+48h] [rbp-B8h]
  GUID v25; // [rsp+4Ch] [rbp-B4h]
  WSAData WSAData; // [rsp+460h] [rbp+360h] BYREF
  int v27; // [rsp+600h] [rbp+500h] BYREF
  unsigned int (__fastcall *v28)(void *, void *, struct tagWDS_ENDPOINT *, struct tagWDS_ENDPOINT *, void *, unsigned int); // [rsp+608h] [rbp+508h] BYREF
  CTftpServer *v29; // [rsp+610h] [rbp+510h]
  int v30; // [rsp+638h] [rbp+538h]
  int v31; // [rsp+640h] [rbp+540h]

  memset_0(&v22, 0, 0x41Cu);
  memset_0(&v28, 0, 0xA0u);
  McGenEventRegister();
  *((_QWORD *)this + 21) = a2;
  LastError = 0;
  memset_0(&WSAData, 0, sizeof(WSAData));
  if ( !*((_DWORD *)this + 856)
    || (LastError = 1247,
        !ElValidateWin32(0x4DFu, v5, "onecore\\base\\eco\\wds\\wdslib\\common\\src\\winsockinitializer.cpp", 0x6Fu)) )
  {
    v7 = WSAStartup(2u, &WSAData);
    if ( v7 )
    {
      LastError = v7;
      ElValidateWin32(v7, v6, "onecore\\base\\eco\\wds\\wdslib\\common\\src\\winsockinitializer.cpp", 0x7Bu);
    }
    else
    {
      *((_DWORD *)this + 856) = 1;
    }
  }
  if ( !ElValidateWin32(LastError, v6, "base\\eco\\wds\\transport\\server\\tftp\\tftpserver.cpp", 0x8Du) )
  {
    LastError = 0;
    if ( !*((_DWORD *)this + 857) )
    {
      LastError = WdsClientInitializeLibrary();
      *((_DWORD *)this + 857) = LastError == 0;
    }
    if ( !ElValidateWin32(LastError, v8, "base\\eco\\wds\\transport\\server\\tftp\\tftpserver.cpp", 0x94u) )
    {
      LastError = 0;
      hEventLog = RegisterEventSourceW(0, L"WDSTFTP");
      if ( hEventLog )
        word_1800779E8 = 263;
      else
        LastError = GetLastError();
      if ( !ElValidateWin32(LastError, v9, "base\\eco\\wds\\transport\\server\\tftp\\tftpserver.cpp", 0x9Bu) )
      {
        LastError = CTftpPerfCounters::InitializeServer((CTftpPerfCounters *)&qword_1800779F0);
        if ( !ElValidateWin32(LastError, v10, "base\\eco\\wds\\transport\\server\\tftp\\tftpserver.cpp", 0xA2u) )
        {
          LastError = CTftpServer::ReadParameters(this);
          if ( !ElValidateWin32(LastError, v11, "base\\eco\\wds\\transport\\server\\tftp\\tftpserver.cpp", 0xA9u) )
          {
            LastError = 0;
            if ( !ElValidateWin32(0, v12, "base\\eco\\wds\\transport\\server\\tftp\\tftpserver.cpp", 0xB0u) )
            {
              if ( !*((_DWORD *)this + 142)
                || (LastError = CTftpReadFileManager::Initialize(
                                  (LPCRITICAL_SECTION)((char *)this + 576),
                                  *((_DWORD *)this + 139),
                                  *((_DWORD *)this + 138)),
                    !ElValidateWin32(LastError, v13, "base\\eco\\wds\\transport\\server\\tftp\\tftpserver.cpp", 0xBAu)) )
              {
                LastError = WdsRegisterCallback(a2, 0, WdsProviderShutdown, 0);
                if ( !ElValidateWin32(LastError, v14, "base\\eco\\wds\\transport\\server\\tftp\\tftpserver.cpp", 0xC6u) )
                {
                  LastError = WdsRegisterCallback(a2, 1, CTftpServer::_RecvRequest, 0);
                  if ( !ElValidateWin32(
                          LastError,
                          v15,
                          "base\\eco\\wds\\transport\\server\\tftp\\tftpserver.cpp",
                          0xD1u) )
                  {
                    LastError = WdsRegisterCallback(a2, 7, CTftpServer::_ServiceControl, 0);
                    if ( !ElValidateWin32(
                            LastError,
                            v16,
                            "base\\eco\\wds\\transport\\server\\tftp\\tftpserver.cpp",
                            0xDCu) )
                    {
                      if ( *((_DWORD *)this + 44) )
                      {
                        v23 = 0;
                        v29 = 0;
                        v22 = 1052;
                        LOWORD(v25.Data1) = 69;
                        v27 = 66567;
                        v28 = CTftpServer::_ServerRequest;
                        v30 = 524548;
                        v31 = 1;
                        LastError = WdsEndpointOpen(a2, &v22, 2, &v27, (char *)this + 184);
                        if ( !ElValidateWin32(
                                LastError,
                                v17,
                                "base\\eco\\wds\\transport\\server\\tftp\\tftpserver.cpp",
                                0xF5u) )
                        {
                          if ( !*((_DWORD *)this + 141)
                            || (LastError = CTftpServer::CreateDataPortPool(this),
                                !ElValidateWin32(
                                   LastError,
                                   v18,
                                   "base\\eco\\wds\\transport\\server\\tftp\\tftpserver.cpp",
                                   0xFFu)) )
                          {
                            v22 = 1052;
                            v28 = CTftpServer::_ManagementRequest;
                            v23 = 1;
                            v24 = 1;
                            v27 = 66567;
                            v25 = WDSTFTP_MGMT_ENDPOINT;
                            v29 = this;
                            v30 = 197124;
                            v31 = 1;
                            LastError = WdsEndpointOpen(a2, &v22, 2, &v27, (char *)this + 192);
                            if ( !ElValidateWin32(
                                    LastError,
                                    v19,
                                    "base\\eco\\wds\\transport\\server\\tftp\\tftpserver.cpp",
                                    0x119u) )
                            {
                              LastError = CTimer<CTftpServer>::Initialize((char *)this + 200);
                              ElValidateWin32(
                                LastError,
                                v20,
                                "base\\eco\\wds\\transport\\server\\tftp\\tftpserver.cpp",
                                0x120u);
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x1800012e0  mov     [rsp-8+arg_10], rbx
0x1800012e5  push    rbp
0x1800012e6  push    rsi
0x1800012e7  push    rdi
0x1800012e8  push    r12
0x1800012ea  push    r15
0x1800012ec  lea     rbp, [rsp-5C0h]
0x1800012f4  sub     rsp, 6C0h
0x1800012fb  mov     rax, cs:__security_cookie
0x180001302  xor     rax, rsp
0x180001305  mov     [rbp+5E0h+var_30], rax
0x18000130c  mov     rsi, rdx
0x18000130f  mov     rdi, rcx
0x180001312  xor     edx, edx; Val
0x180001314  lea     rcx, [rsp+6E0h+var_6A0]; void *
0x180001319  mov     r8d, 41Ch; Size
0x18000131f  call    memset_0
0x180001324  xor     edx, edx; Val
0x180001326  lea     rcx, [rbp+5E0h+var_D8]; void *
0x18000132d  mov     r8d, 0A0h; Size
0x180001333  call    memset_0
0x180001338  call    McGenEventRegister
0x18000133d  xor     edx, edx; Val
0x18000133f  mov     [rdi+0A8h], rsi
0x180001346  mov     r8d, 198h; Size
0x18000134c  lea     rcx, [rbp+5E0h+WSAData]; void *
0x180001353  xor     ebx, ebx
0x180001355  call    memset_0
0x18000135a  lea     r12d, [rbx+1]
0x18000135e  cmp     [rdi+0D60h], ebx
0x180001364  jz      short loc_180001382
0x180001366  mov     ebx, 4DFh
0x18000136b  lea     r9d, [r12+6Eh]; unsigned int
0x180001370  mov     ecx, ebx; unsigned int
0x180001372  lea     r8, aOnecoreBaseEco_2; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180001379  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000137e  test    eax, eax
0x180001380  jnz     short loc_1800013BD
0x180001382  mov     ecx, 2; wVersionRequested
0x180001387  lea     rdx, [rbp+5E0h+WSAData]; lpWSAData
0x18000138e  call    cs:__imp_WSAStartup
0x180001395  nop     dword ptr [rax+rax+00h]
0x18000139a  test    eax, eax
0x18000139c  jnz     short loc_1800013A7
0x18000139e  mov     [rdi+0D60h], r12d
0x1800013a5  jmp     short loc_1800013BD
0x1800013a7  mov     r9d, 7Bh ; '{'; unsigned int
0x1800013ad  lea     r8, aOnecoreBaseEco_2; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x1800013b4  mov     ecx, eax; unsigned int
0x1800013b6  mov     ebx, eax
0x1800013b8  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800013bd  lea     r15, aBaseEcoWdsTran_8; "base\\eco\\wds\\transport\\server\\tftp"...
0x1800013c4  mov     r9d, 8Dh; unsigned int
0x1800013ca  mov     r8, r15; char *
0x1800013cd  mov     ecx, ebx; unsigned int
0x1800013cf  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800013d4  test    eax, eax
0x1800013d6  jnz     loc_180001725
0x1800013dc  xor     ebx, ebx
0x1800013de  cmp     [rdi+0D64h], ebx
0x1800013e4  jnz     short loc_180001401
0x1800013e6  call    cs:__imp_WdsClientInitializeLibrary
0x1800013ed  nop     dword ptr [rax+rax+00h]
0x1800013f2  mov     ebx, eax
0x1800013f4  xor     eax, eax
0x1800013f6  test    ebx, ebx
0x1800013f8  setz    al
0x1800013fb  mov     [rdi+0D64h], eax
0x180001401  mov     r9d, 94h; unsigned int
0x180001407  mov     r8, r15; char *
0x18000140a  mov     ecx, ebx; unsigned int
0x18000140c  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180001411  test    eax, eax
0x180001413  jnz     loc_180001725
0x180001419  lea     rdx, SourceName; "WDSTFTP"
0x180001420  xor     ecx, ecx; lpUNCServerName
0x180001422  xor     ebx, ebx
0x180001424  call    cs:__imp_RegisterEventSourceW
0x18000142b  nop     dword ptr [rax+rax+00h]
0x180001430  mov     cs:hEventLog, rax
0x180001437  test    rax, rax
0x18000143a  jnz     short loc_18000144C
0x18000143c  call    cs:__imp_GetLastError
0x180001443  nop     dword ptr [rax+rax+00h]
0x180001448  mov     ebx, eax
0x18000144a  jmp     short loc_180001458
0x18000144c  mov     eax, 107h
0x180001451  mov     cs:word_1800779E8, ax
0x180001458  mov     r9d, 9Bh; unsigned int
0x18000145e  mov     r8, r15; char *
0x180001461  mov     ecx, ebx; unsigned int
0x180001463  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180001468  test    eax, eax
0x18000146a  jnz     loc_180001725
0x180001470  lea     rcx, qword_1800779F0; this
0x180001477  call    ?InitializeServer@CTftpPerfCounters@@QEAAKXZ; CTftpPerfCounters::InitializeServer(void)
0x18000147c  mov     r9d, 0A2h; unsigned int
0x180001482  mov     r8, r15; char *
0x180001485  mov     ecx, eax; unsigned int
0x180001487  mov     ebx, eax
0x180001489  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000148e  test    eax, eax
0x180001490  jnz     loc_180001725
0x180001496  mov     rcx, rdi; this
0x180001499  call    ?ReadParameters@CTftpServer@@AEAAKXZ; CTftpServer::ReadParameters(void)
0x18000149e  mov     r9d, 0A9h; unsigned int
0x1800014a4  mov     r8, r15; char *
0x1800014a7  mov     ecx, eax; unsigned int
0x1800014a9  mov     ebx, eax
0x1800014ab  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800014b0  test    eax, eax
0x1800014b2  jnz     loc_180001725
0x1800014b8  mov     r9d, 0B0h; unsigned int
0x1800014be  mov     r8, r15; char *
0x1800014c1  xor     ecx, ecx; unsigned int
0x1800014c3  xor     ebx, ebx
0x1800014c5  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800014ca  test    eax, eax
0x1800014cc  jnz     loc_180001725
0x1800014d2  cmp     [rdi+238h], ebx
0x1800014d8  jz      short loc_18000150D
0x1800014da  mov     r8d, [rdi+228h]; unsigned int
0x1800014e1  lea     rcx, [rdi+240h]; lpCriticalSection
0x1800014e8  mov     edx, [rdi+22Ch]; unsigned int
0x1800014ee  call    ?Initialize@CTftpReadFileManager@@QEAAKKK@Z; CTftpReadFileManager::Initialize(ulong,ulong)
0x1800014f3  mov     r9d, 0BAh; unsigned int
0x1800014f9  mov     r8, r15; char *
0x1800014fc  mov     ecx, eax; unsigned int
0x1800014fe  mov     ebx, eax
0x180001500  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180001505  test    eax, eax
0x180001507  jnz     loc_180001725
0x18000150d  xor     r9d, r9d
0x180001510  lea     r8, ?WdsProviderShutdown@@YAKPEAX@Z; WdsProviderShutdown(void *)
0x180001517  xor     edx, edx
0x180001519  mov     rcx, rsi
0x18000151c  call    cs:__imp_WdsRegisterCallback
0x180001523  nop     dword ptr [rax+rax+00h]
0x180001528  mov     r9d, 0C6h; unsigned int
0x18000152e  mov     r8, r15; char *
0x180001531  mov     ecx, eax; unsigned int
0x180001533  mov     ebx, eax
0x180001535  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000153a  test    eax, eax
0x18000153c  jnz     loc_180001725
0x180001542  xor     r9d, r9d
0x180001545  lea     r8, ?_RecvRequest@CTftpServer@@SAKPEAX0PEAUtagWDS_ENDPOINT@@10K@Z; CTftpServer::_RecvRequest(void *,void *,tagWDS_ENDPOINT *,tagWDS_ENDPOINT *,void *,ulong)
0x18000154c  mov     edx, r12d
0x18000154f  mov     rcx, rsi
0x180001552  call    cs:__imp_WdsRegisterCallback
0x180001559  nop     dword ptr [rax+rax+00h]
0x18000155e  mov     r9d, 0D1h; unsigned int
0x180001564  mov     r8, r15; char *
0x180001567  mov     ecx, eax; unsigned int
0x180001569  mov     ebx, eax
0x18000156b  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180001570  test    eax, eax
0x180001572  jnz     loc_180001725
0x180001578  xor     r9d, r9d
0x18000157b  lea     r8, ?_ServiceControl@CTftpServer@@SAXPEAXK@Z; CTftpServer::_ServiceControl(void *,ulong)
0x180001582  lea     edx, [rax+7]
0x180001585  mov     rcx, rsi
0x180001588  call    cs:__imp_WdsRegisterCallback
0x18000158f  nop     dword ptr [rax+rax+00h]
0x180001594  mov     r9d, 0DCh; unsigned int
0x18000159a  mov     r8, r15; char *
0x18000159d  mov     ecx, eax; unsigned int
0x18000159f  mov     ebx, eax
0x1800015a1  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800015a6  test    eax, eax
0x1800015a8  jnz     loc_180001725
0x1800015ae  cmp     [rdi+0B0h], eax
0x1800015b4  jz      loc_180001725
0x1800015ba  and     [rsp+6E0h+var_69C], eax
0x1800015be  lea     r9, [rbp+5E0h+var_E0]
0x1800015c5  and     [rbp+5E0h+var_D0], 0
0x1800015cd  lea     rdx, [rsp+6E0h+var_6A0]
0x1800015d2  mov     eax, 45h ; 'E'
0x1800015d7  mov     [rsp+6E0h+var_6A0], 41Ch
0x1800015df  mov     word ptr [rsp+6E0h+var_694], ax
0x1800015e4  mov     r8d, 2
0x1800015ea  lea     rax, ?_ServerRequest@CTftpServer@@SAKPEAX0PEAUtagWDS_ENDPOINT@@10K@Z; CTftpServer::_ServerRequest(void *,void *,tagWDS_ENDPOINT *,tagWDS_ENDPOINT *,void *,ulong)
0x1800015f1  mov     [rbp+5E0h+var_E0], 10407h
0x1800015fb  mov     [rbp+5E0h+var_D8], rax
0x180001602  mov     rcx, rsi
0x180001605  lea     rax, [rdi+0B8h]
0x18000160c  mov     [rbp+5E0h+var_A8], 80104h
0x180001616  mov     [rsp+6E0h+var_6C0], rax
0x18000161b  mov     [rbp+5E0h+var_A0], r12d
0x180001622  call    cs:__imp_WdsEndpointOpen
0x180001629  nop     dword ptr [rax+rax+00h]
0x18000162e  mov     r9d, 0F5h; unsigned int
0x180001634  mov     r8, r15; char *
0x180001637  mov     ecx, eax; unsigned int
0x180001639  mov     ebx, eax
0x18000163b  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180001640  test    eax, eax
0x180001642  jnz     loc_180001725
0x180001648  cmp     [rdi+234h], eax
0x18000164e  jz      short loc_180001672
0x180001650  mov     rcx, rdi; this
0x180001653  call    ?CreateDataPortPool@CTftpServer@@AEAAKXZ; CTftpServer::CreateDataPortPool(void)
0x180001658  mov     r9d, 0FFh; unsigned int
0x18000165e  mov     r8, r15; char *
0x180001661  mov     ecx, eax; unsigned int
0x180001663  mov     ebx, eax
0x180001665  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000166a  test    eax, eax
0x18000166c  jnz     loc_180001725
0x180001672  movups  xmm0, xmmword ptr cs:?WDSTFTP_MGMT_ENDPOINT@@3U_GUID@@B.Data1; _GUID const WDSTFTP_MGMT_ENDPOINT ...
0x180001679  lea     rax, ?_ManagementRequest@CTftpServer@@SAKPEAX0PEAUtagWDS_ENDPOINT@@10K@Z; CTftpServer::_ManagementRequest(void *,void *,tagWDS_ENDPOINT *,tagWDS_ENDPOINT *,void *,ulong)
0x180001680  mov     [rsp+6E0h+var_6A0], 41Ch
0x180001688  mov     [rbp+5E0h+var_D8], rax
0x18000168f  lea     r9, [rbp+5E0h+var_E0]
0x180001696  lea     rax, [rdi+0C0h]
0x18000169d  mov     [rsp+6E0h+var_69C], r12d
0x1800016a2  mov     r8d, 2
0x1800016a8  mov     [rsp+6E0h+var_6C0], rax
0x1800016ad  lea     rdx, [rsp+6E0h+var_6A0]
0x1800016b2  mov     [rsp+6E0h+var_698], r12d
0x1800016b7  mov     rcx, rsi
0x1800016ba  mov     [rbp+5E0h+var_E0], 10407h
0x1800016c4  movdqu  [rsp+6E0h+var_694], xmm0
0x1800016ca  mov     [rbp+5E0h+var_D0], rdi
0x1800016d1  mov     [rbp+5E0h+var_A8], 30204h
0x1800016db  mov     [rbp+5E0h+var_A0], r12d
0x1800016e2  call    cs:__imp_WdsEndpointOpen
0x1800016e9  nop     dword ptr [rax+rax+00h]
0x1800016ee  mov     r9d, 119h; unsigned int
0x1800016f4  mov     r8, r15; char *
0x1800016f7  mov     ecx, eax; unsigned int
0x1800016f9  mov     ebx, eax
0x1800016fb  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180001700  test    eax, eax
0x180001702  jnz     short loc_180001725
0x180001704  lea     rcx, [rdi+0C8h]; Parameter
0x18000170b  mov     rdx, rdi
0x18000170e  call    ?Initialize@?$CTimer@VCTftpServer@@@@QEAAKPEAVCTftpServer@@PEAXKK1K@Z; CTimer<CTftpServer>::Initialize(CTftpServer *,void *,ulong,ulong,void *,ulong)
0x180001713  mov     r9d, 120h; unsigned int
0x180001719  mov     r8, r15; char *
0x18000171c  mov     ecx, eax; unsigned int
0x18000171e  mov     ebx, eax
0x180001720  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180001725  mov     eax, ebx
0x180001727  mov     rcx, [rbp+5E0h+var_30]
0x18000172e  xor     rcx, rsp; StackCookie
0x180001731  call    __security_check_cookie
0x180001736  mov     rbx, [rsp+6E0h+arg_10]
0x18000173e  add     rsp, 6C0h
0x180001745  pop     r15
0x180001747  pop     r12
0x180001749  pop     rdi
0x18000174a  pop     rsi
0x18000174b  pop     rbp
0x18000174c  retn
```
