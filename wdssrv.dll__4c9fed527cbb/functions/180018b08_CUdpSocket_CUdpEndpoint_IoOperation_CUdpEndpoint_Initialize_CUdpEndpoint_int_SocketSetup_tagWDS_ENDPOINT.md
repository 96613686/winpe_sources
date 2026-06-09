# CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::Initialize(CUdpEndpoint *,int,SocketSetup *,tagWDS_ENDPOINT *)

- ea: `0x180018b08`
- end: `0x180018cd6`
- name: `?Initialize@?$CUdpSocket@VCUdpEndpoint@@U?$IoOperation@VCUdpEndpoint@@@@@@QEAAKPEAVCUdpEndpoint@@HPEAUSocketSetup@@PEAUtagWDS_ENDPOINT@@@Z`
- size: `462`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180018cdc`

## callees

- `0x180003944`
- `0x1800186f0`
- `0x180018b08`
- `0x18001a008`
- `0x18001a250`
- `0x18001c11e`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180018b4e`
- `KERNEL32!GetLastError` at `0x180018b4e`
- `KERNEL32!CreateEventW` at `0x180018b36`
- `KERNEL32!CreateEventW` at `0x180018b36`
- `WS2_32!WSASocketW` at `0x180018c42`
- `WS2_32!WSASocketW` at `0x180018c42`
- `WdsServerCommonLib!?Initialize@CMRSWLock@@QEAAKK@Z` at `0x180018b82`
- `WdsServerCommonLib!?Initialize@CMRSWLock@@QEAAKK@Z` at `0x180018b82`

## pseudocode

```c
__int64 __fastcall CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::Initialize(
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
  __int64 v13; // rbx
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
    LODWORD(v13) = ElValidateWin32(LastError, v11, "onecore\\internal\\base\\inc\\private\\eco\\wds\\ChildCount.h", 213);
    if ( !(_DWORD)v13 )
      LODWORD(v13) = 31;
  }
  if ( (unsigned int)ElValidateWin32((unsigned int)v13, v12, "base\\Eco\\WDS\\wdslib\\net\\UdpSocket.h", 386) )
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
  LODWORD(v13) = 0;
  if ( !(unsigned int)ElValidateWin32(0, v15, "base\\Eco\\WDS\\wdslib\\net\\UdpSocket.h", 422) )
  {
    v18 = WSASocketW(a3, 2, 17, 0, 0, 1u);
    *(_QWORD *)(a1 + 56) = v18;
    if ( v18 == -1 )
    {
      LODWORD(v13) = ElValidateWin32(0, v19, "base\\Eco\\WDS\\wdslib\\net\\UdpSocket.h", 437);
    }
    else
    {
      v13 = (unsigned int)CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::SetSocketOptions(a1);
      if ( !(unsigned int)ElValidateWin32(v13, v20, "base\\Eco\\WDS\\wdslib\\net\\UdpSocket.h", 445) && a5 )
      {
        v13 = (unsigned int)CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::Bind(a1, a5);
        ElValidateWin32(v13, v21, "base\\Eco\\WDS\\wdslib\\net\\UdpSocket.h", 454);
      }
    }
LABEL_18:
    if ( (_DWORD)v13 )
      CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::Shutdown(a1);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180018b08  mov     [rsp+arg_0], rbx
0x180018b0d  mov     [rsp+arg_8], rbp
0x180018b12  mov     [rsp+arg_10], rsi
0x180018b17  push    rdi
0x180018b18  push    r14
0x180018b1a  push    r15
0x180018b1c  sub     rsp, 30h
0x180018b20  mov     rbp, r9
0x180018b23  mov     esi, r8d
0x180018b26  mov     r14, rdx
0x180018b29  mov     rdi, rcx
0x180018b2c  xor     r9d, r9d; lpName
0x180018b2f  xor     r8d, r8d; bInitialState
0x180018b32  xor     edx, edx; bManualReset
0x180018b34  xor     ecx, ecx; lpEventAttributes
0x180018b36  call    cs:__imp_CreateEventW
0x180018b3d  nop     dword ptr [rax+rax+00h]
0x180018b42  mov     [rdi+1E8h], rax
0x180018b49  test    rax, rax
0x180018b4c  jnz     short loc_180018B79
0x180018b4e  call    cs:__imp_GetLastError
0x180018b55  nop     dword ptr [rax+rax+00h]
0x180018b5a  mov     r9d, 0D5h
0x180018b60  lea     r8, aOnecoreInterna_1; "onecore\\internal\\base\\inc\\private\\"...
0x180018b67  mov     ecx, eax
0x180018b69  call    ElValidateWin32
0x180018b6e  mov     ebx, eax
0x180018b70  test    eax, eax
0x180018b72  jnz     short loc_180018BA4
0x180018b74  lea     ebx, [rax+1Fh]
0x180018b77  jmp     short loc_180018BA4
0x180018b79  lea     rcx, [rdi+1F0h]
0x180018b80  xor     edx, edx
0x180018b82  call    cs:__imp_?Initialize@CMRSWLock@@QEAAKK@Z; CMRSWLock::Initialize(ulong)
0x180018b89  nop     dword ptr [rax+rax+00h]
0x180018b8e  mov     r9d, 0D9h
0x180018b94  lea     r8, aOnecoreInterna_1; "onecore\\internal\\base\\inc\\private\\"...
0x180018b9b  mov     ecx, eax
0x180018b9d  mov     ebx, eax
0x180018b9f  call    ElValidateWin32
0x180018ba4  lea     r15, aBaseEcoWdsWdsl; "base\\Eco\\WDS\\wdslib\\net\\UdpSocket."...
0x180018bab  mov     r9d, 182h
0x180018bb1  mov     r8, r15
0x180018bb4  mov     ecx, ebx
0x180018bb6  call    ElValidateWin32
0x180018bbb  test    eax, eax
0x180018bbd  jnz     loc_180018CAE
0x180018bc3  lea     rbx, [rdi+48h]
0x180018bc7  mov     r8d, 0D8h; Size
0x180018bcd  mov     rcx, rbx; void *
0x180018bd0  mov     rdx, rbp; Src
0x180018bd3  call    memmove_0
0x180018bd8  mov     ecx, [rbx]
0x180018bda  mov     [rdi+40h], esi
0x180018bdd  mov     [rdi+30h], r14
0x180018be1  test    ecx, ecx
0x180018be3  jnz     short loc_180018BEC
0x180018be5  mov     ecx, 10h
0x180018bea  mov     [rbx], ecx
0x180018bec  cmp     dword ptr [rdi+4Ch], 0
0x180018bf0  jnz     short loc_180018BF9
0x180018bf2  mov     dword ptr [rdi+4Ch], 400h
0x180018bf9  mov     eax, [rdi+50h]
0x180018bfc  test    eax, eax
0x180018bfe  jnz     short loc_180018C08
0x180018c00  mov     eax, 40h ; '@'
0x180018c05  mov     [rdi+50h], eax
0x180018c08  add     eax, ecx
0x180018c0a  mov     [rdi+1D4h], eax
0x180018c10  mov     r9d, 1A6h
0x180018c16  mov     r8, r15
0x180018c19  xor     ecx, ecx
0x180018c1b  xor     ebx, ebx
0x180018c1d  call    ElValidateWin32
0x180018c22  test    eax, eax
0x180018c24  jnz     loc_180018CBA
0x180018c2a  mov     [rsp+48h+dwFlags], 1; dwFlags
0x180018c32  lea     edx, [rbx+2]; type
0x180018c35  and     [rsp+48h+var_28], ebx
0x180018c39  lea     r8d, [rbx+11h]; protocol
0x180018c3d  xor     r9d, r9d; lpProtocolInfo
0x180018c40  mov     ecx, esi; af
0x180018c42  call    cs:__imp_WSASocketW
0x180018c49  nop     dword ptr [rax+rax+00h]
0x180018c4e  mov     [rdi+38h], rax
0x180018c52  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180018c56  jnz     short loc_180018C6C
0x180018c58  mov     r9d, 1B5h
0x180018c5e  mov     r8, r15
0x180018c61  xor     ecx, ecx
0x180018c63  call    ElValidateWin32
0x180018c68  mov     ebx, eax
0x180018c6a  jmp     short loc_180018CAE
0x180018c6c  mov     rcx, rdi
0x180018c6f  call    ?SetSocketOptions@?$CUdpSocket@VCUdpEndpoint@@U?$IoOperation@VCUdpEndpoint@@@@@@AEAAKXZ; CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::SetSocketOptions(void)
0x180018c74  mov     r9d, 1BDh
0x180018c7a  mov     r8, r15
0x180018c7d  mov     ecx, eax
0x180018c7f  mov     ebx, eax
0x180018c81  call    ElValidateWin32
0x180018c86  test    eax, eax
0x180018c88  jnz     short loc_180018CAE
0x180018c8a  mov     rdx, [rsp+48h+arg_20]
0x180018c8f  test    rdx, rdx
0x180018c92  jz      short loc_180018CAE
0x180018c94  mov     rcx, rdi
0x180018c97  call    ?Bind@?$CUdpSocket@VCUdpEndpoint@@U?$IoOperation@VCUdpEndpoint@@@@@@QEAAKPEAUtagWDS_ENDPOINT@@@Z; CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::Bind(tagWDS_ENDPOINT *)
0x180018c9c  mov     r9d, 1C6h
0x180018ca2  mov     r8, r15
0x180018ca5  mov     ecx, eax
0x180018ca7  mov     ebx, eax
0x180018ca9  call    ElValidateWin32
0x180018cae  test    ebx, ebx
0x180018cb0  jz      short loc_180018CBA
0x180018cb2  mov     rcx, rdi
0x180018cb5  call    ?Shutdown@?$CUdpSocket@VCUdpEndpoint@@U?$IoOperation@VCUdpEndpoint@@@@@@QEAAKXZ; CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::Shutdown(void)
0x180018cba  mov     rbp, [rsp+48h+arg_8]
0x180018cbf  mov     eax, ebx
0x180018cc1  mov     rbx, [rsp+48h+arg_0]
0x180018cc6  mov     rsi, [rsp+48h+arg_10]
0x180018ccb  add     rsp, 30h
0x180018ccf  pop     r15
0x180018cd1  pop     r14
0x180018cd3  pop     rdi
0x180018cd4  retn
```
