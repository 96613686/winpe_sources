# CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::Initialize(CClientLibrary *,int,SocketSetup *,tagWDS_ENDPOINT *)

- ea: `0x180006dac`
- end: `0x180006f7a`
- name: `?Initialize@?$CUdpSocket@VCClientLibrary@@U?$IoOperation@VCClientLibrary@@@@@@QEAAKPEAVCClientLibrary@@HPEAUSocketSetup@@PEAUtagWDS_ENDPOINT@@@Z`
- size: `462`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800077f4`

## callees

- `0x1800026c4`
- `0x18000474c`
- `0x180006dac`
- `0x18000a610`
- `0x18000a858`
- `0x18000bd5c`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x180006dda`
- `KERNEL32!CreateEventW` at `0x180006dda`
- `KERNEL32!GetLastError` at `0x180006df2`
- `KERNEL32!GetLastError` at `0x180006df2`
- `WS2_32!WSASocketW` at `0x180006ee6`
- `WS2_32!WSASocketW` at `0x180006ee6`
- `WdsCommonLib!?Initialize@CMRSWLock@@QEAAKK@Z` at `0x180006e26`
- `WdsCommonLib!?Initialize@CMRSWLock@@QEAAKK@Z` at `0x180006e26`

## pseudocode

```c
__int64 __fastcall CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::Initialize(
        __int64 a1,
        __int64 a2,
        int a3,
        const void *a4,
        __int64 a5)
{
  HANDLE EventW; // rax
  DWORD LastError; // eax
  __int64 v11; // rdx
  __int64 v12; // rdx
  unsigned int v13; // ebx
  __int64 v14; // rdx
  __int64 v15; // rdx
  int v16; // ecx
  int v17; // eax
  SOCKET v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rdx
  __int64 v21; // rdx

  EventW = CreateEventW(0, 0, 0, 0);
  *(_QWORD *)(a1 + 488) = EventW;
  if ( EventW )
  {
    v13 = CMRSWLock::Initialize((CMRSWLock *)(a1 + 496), 0);
    ElValidateWin32(v13, v14, "onecore\\internal\\base\\inc\\private\\eco\\wds\\ChildCount.h", 217);
  }
  else
  {
    LastError = GetLastError();
    v13 = ElValidateWin32(LastError, v11, "onecore\\internal\\base\\inc\\private\\eco\\wds\\ChildCount.h", 213);
    if ( !v13 )
      v13 = 31;
  }
  if ( (unsigned int)ElValidateWin32(v13, v12, "base\\Eco\\WDS\\wdslib\\net\\UdpSocket.h", 386) )
    goto LABEL_18;
  memmove_0((void *)(a1 + 72), a4, 0xD8u);
  v16 = *(_DWORD *)(a1 + 72);
  *(_DWORD *)(a1 + 64) = a3;
  *(_QWORD *)(a1 + 48) = a2;
  if ( !v16 )
  {
    v16 = 16;
    *(_DWORD *)(a1 + 72) = 16;
  }
  if ( !*(_DWORD *)(a1 + 76) )
    *(_DWORD *)(a1 + 76) = 1024;
  v17 = *(_DWORD *)(a1 + 80);
  if ( !v17 )
  {
    v17 = 64;
    *(_DWORD *)(a1 + 80) = 64;
  }
  *(_DWORD *)(a1 + 468) = v16 + v17;
  v13 = 0;
  if ( !(unsigned int)ElValidateWin32(0, v15, "base\\Eco\\WDS\\wdslib\\net\\UdpSocket.h", 422) )
  {
    v18 = WSASocketW(a3, 2, 17, 0, 0, 1u);
    *(_QWORD *)(a1 + 56) = v18;
    if ( v18 == -1 )
    {
      v13 = ElValidateWin32(0, v19, "base\\Eco\\WDS\\wdslib\\net\\UdpSocket.h", 437);
    }
    else
    {
      v13 = CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::SetSocketOptions(a1);
      if ( !(unsigned int)ElValidateWin32(v13, v20, "base\\Eco\\WDS\\wdslib\\net\\UdpSocket.h", 445) && a5 )
      {
        v13 = CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::Bind(a1, a5);
        ElValidateWin32(v13, v21, "base\\Eco\\WDS\\wdslib\\net\\UdpSocket.h", 454);
      }
    }
LABEL_18:
    if ( v13 )
      CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::Shutdown(a1);
  }
  return v13;
}

```

## disassembly

```asm
0x180006dac  mov     [rsp+arg_0], rbx
0x180006db1  mov     [rsp+arg_8], rbp
0x180006db6  mov     [rsp+arg_10], rsi
0x180006dbb  push    rdi
0x180006dbc  push    r14
0x180006dbe  push    r15
0x180006dc0  sub     rsp, 30h
0x180006dc4  mov     rbp, r9
0x180006dc7  mov     esi, r8d
0x180006dca  mov     r14, rdx
0x180006dcd  mov     rdi, rcx
0x180006dd0  xor     r9d, r9d; lpName
0x180006dd3  xor     r8d, r8d; bInitialState
0x180006dd6  xor     edx, edx; bManualReset
0x180006dd8  xor     ecx, ecx; lpEventAttributes
0x180006dda  call    cs:__imp_CreateEventW
0x180006de1  nop     dword ptr [rax+rax+00h]
0x180006de6  mov     [rdi+1E8h], rax
0x180006ded  test    rax, rax
0x180006df0  jnz     short loc_180006E1D
0x180006df2  call    cs:__imp_GetLastError
0x180006df9  nop     dword ptr [rax+rax+00h]
0x180006dfe  mov     r9d, 0D5h
0x180006e04  lea     r8, aOnecoreInterna_0; "onecore\\internal\\base\\inc\\private\\"...
0x180006e0b  mov     ecx, eax
0x180006e0d  call    ElValidateWin32
0x180006e12  mov     ebx, eax
0x180006e14  test    eax, eax
0x180006e16  jnz     short loc_180006E48
0x180006e18  lea     ebx, [rax+1Fh]
0x180006e1b  jmp     short loc_180006E48
0x180006e1d  lea     rcx, [rdi+1F0h]
0x180006e24  xor     edx, edx
0x180006e26  call    cs:__imp_?Initialize@CMRSWLock@@QEAAKK@Z; CMRSWLock::Initialize(ulong)
0x180006e2d  nop     dword ptr [rax+rax+00h]
0x180006e32  mov     r9d, 0D9h
0x180006e38  lea     r8, aOnecoreInterna_0; "onecore\\internal\\base\\inc\\private\\"...
0x180006e3f  mov     ecx, eax
0x180006e41  mov     ebx, eax
0x180006e43  call    ElValidateWin32
0x180006e48  lea     r15, aBaseEcoWdsWdsl; "base\\Eco\\WDS\\wdslib\\net\\UdpSocket."...
0x180006e4f  mov     r9d, 182h
0x180006e55  mov     r8, r15
0x180006e58  mov     ecx, ebx
0x180006e5a  call    ElValidateWin32
0x180006e5f  test    eax, eax
0x180006e61  jnz     loc_180006F52
0x180006e67  lea     rbx, [rdi+48h]
0x180006e6b  mov     r8d, 0D8h; Size
0x180006e71  mov     rcx, rbx; void *
0x180006e74  mov     rdx, rbp; Src
0x180006e77  call    memmove_0
0x180006e7c  mov     ecx, [rbx]
0x180006e7e  mov     [rdi+40h], esi
0x180006e81  mov     [rdi+30h], r14
0x180006e85  test    ecx, ecx
0x180006e87  jnz     short loc_180006E90
0x180006e89  mov     ecx, 10h
0x180006e8e  mov     [rbx], ecx
0x180006e90  cmp     dword ptr [rdi+4Ch], 0
0x180006e94  jnz     short loc_180006E9D
0x180006e96  mov     dword ptr [rdi+4Ch], 400h
0x180006e9d  mov     eax, [rdi+50h]
0x180006ea0  test    eax, eax
0x180006ea2  jnz     short loc_180006EAC
0x180006ea4  mov     eax, 40h ; '@'
0x180006ea9  mov     [rdi+50h], eax
0x180006eac  add     eax, ecx
0x180006eae  mov     [rdi+1D4h], eax
0x180006eb4  mov     r9d, 1A6h
0x180006eba  mov     r8, r15
0x180006ebd  xor     ecx, ecx
0x180006ebf  xor     ebx, ebx
0x180006ec1  call    ElValidateWin32
0x180006ec6  test    eax, eax
0x180006ec8  jnz     loc_180006F5E
0x180006ece  mov     [rsp+48h+dwFlags], 1; dwFlags
0x180006ed6  lea     edx, [rbx+2]; type
0x180006ed9  and     [rsp+48h+var_28], ebx
0x180006edd  lea     r8d, [rbx+11h]; protocol
0x180006ee1  xor     r9d, r9d; lpProtocolInfo
0x180006ee4  mov     ecx, esi; af
0x180006ee6  call    cs:__imp_WSASocketW
0x180006eed  nop     dword ptr [rax+rax+00h]
0x180006ef2  mov     [rdi+38h], rax
0x180006ef6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180006efa  jnz     short loc_180006F10
0x180006efc  mov     r9d, 1B5h
0x180006f02  mov     r8, r15
0x180006f05  xor     ecx, ecx
0x180006f07  call    ElValidateWin32
0x180006f0c  mov     ebx, eax
0x180006f0e  jmp     short loc_180006F52
0x180006f10  mov     rcx, rdi
0x180006f13  call    ?SetSocketOptions@?$CUdpSocket@VCClientLibrary@@U?$IoOperation@VCClientLibrary@@@@@@AEAAKXZ; CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::SetSocketOptions(void)
0x180006f18  mov     r9d, 1BDh
0x180006f1e  mov     r8, r15
0x180006f21  mov     ecx, eax
0x180006f23  mov     ebx, eax
0x180006f25  call    ElValidateWin32
0x180006f2a  test    eax, eax
0x180006f2c  jnz     short loc_180006F52
0x180006f2e  mov     rdx, [rsp+48h+arg_20]
0x180006f33  test    rdx, rdx
0x180006f36  jz      short loc_180006F52
0x180006f38  mov     rcx, rdi
0x180006f3b  call    ?Bind@?$CUdpSocket@VCClientLibrary@@U?$IoOperation@VCClientLibrary@@@@@@QEAAKPEAUtagWDS_ENDPOINT@@@Z; CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::Bind(tagWDS_ENDPOINT *)
0x180006f40  mov     r9d, 1C6h
0x180006f46  mov     r8, r15
0x180006f49  mov     ecx, eax
0x180006f4b  mov     ebx, eax
0x180006f4d  call    ElValidateWin32
0x180006f52  test    ebx, ebx
0x180006f54  jz      short loc_180006F5E
0x180006f56  mov     rcx, rdi
0x180006f59  call    ?Shutdown@?$CUdpSocket@VCClientLibrary@@U?$IoOperation@VCClientLibrary@@@@@@QEAAKXZ; CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::Shutdown(void)
0x180006f5e  mov     rbp, [rsp+48h+arg_8]
0x180006f63  mov     eax, ebx
0x180006f65  mov     rbx, [rsp+48h+arg_0]
0x180006f6a  mov     rsi, [rsp+48h+arg_10]
0x180006f6f  add     rsp, 30h
0x180006f73  pop     r15
0x180006f75  pop     r14
0x180006f77  pop     rdi
0x180006f78  retn
```
