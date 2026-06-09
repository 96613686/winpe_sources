# CWdsTransportServer::Initialize(ushort const *)

- ea: `0x180008ee4`
- end: `0x180008ff8`
- name: `?Initialize@CWdsTransportServer@@AEAAJPEBG@Z`
- size: `276`
- prototype: `__int64 __fastcall(CWdsTransportServer *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180008afc`

## callees

- `0x180008ee4`
- `0x180009000`
- `0x180009af8`
- `0x180009c1c`

## import_xrefs

- `WdsCommonLib!?ReverseQueryHostName@CNetworkAddress@@SAKPEBGPEAPEAG@Z` at `0x180008f67`
- `WdsCommonLib!?ReverseQueryHostName@CNetworkAddress@@SAKPEBGPEAPEAG@Z` at `0x180008f67`
- `WdsCommonLib!?GetHostName@@YAKW4_COMPUTER_NAME_FORMAT@@PEAPEAG@Z` at `0x180008f84`
- `WdsCommonLib!?GetHostName@@YAKW4_COMPUTER_NAME_FORMAT@@PEAPEAG@Z` at `0x180008f84`
- `WdsCommonLib!?Initialize@CWinsockInitializer@@QEAAKH@Z` at `0x180008f26`
- `WdsCommonLib!?Initialize@CWinsockInitializer@@QEAAKH@Z` at `0x180008f26`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180008f14`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180008fd4`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180008f14`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180008fd4`

## pseudocode

```c
__int64 __fastcall CWdsTransportServer::Initialize(unsigned __int16 **this, const unsigned __int16 *a2)
{
  __int64 v4; // rbx
  __int64 v5; // rdx
  __int64 v6; // r8
  unsigned int HostName; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // rdx
  __int64 v12; // r8
  int v14; // [rsp+20h] [rbp-18h]

  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"-> CWdsTransportServer::Initialize(0x%p)", this);
  v4 = CWinsockInitializer::Initialize((CWinsockInitializer *)(this + 8), 0);
  if ( (unsigned int)ElValidateWin32_1(v4, v5, v6, 134)
    || (!a2 || !*a2
      ? (HostName = GetHostName(ComputerNameDnsFullyQualified, this + 14), v10 = 145)
      : (HostName = CNetworkAddress::ReverseQueryHostName(a2, this + 14), v10 = 156),
        LODWORD(v4) = HostName,
        (unsigned int)ElValidateWin32_1(HostName, v8, v9, v10)) )
  {
    if ( (int)v4 > 0 )
      LODWORD(v4) = (unsigned __int16)v4 | 0x80070000;
  }
  else
  {
    v4 = (unsigned int)CWdsTransportServer::InitializeManagers((CWdsTransportServer *)this);
    ElValidateHr_1(v4, v11, v12, 163);
  }
  v14 = v4;
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"<- CWdsTransportServer::Initialize(0x%p) =%x", this, v14);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180008ee4  mov     [rsp+arg_0], rbx
0x180008ee9  mov     [rsp+arg_8], rbp
0x180008eee  mov     [rsp+arg_10], rsi
0x180008ef3  push    rdi
0x180008ef4  sub     rsp, 30h
0x180008ef8  mov     rsi, rdx
0x180008efb  lea     r8, aCwdstransports_2; "-> CWdsTransportServer::Initialize(0x%p"...
0x180008f02  mov     rdi, rcx
0x180008f05  mov     r9, rcx
0x180008f08  mov     edx, 10000h
0x180008f0d  lea     rcx, qword_18003B770
0x180008f14  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180008f1b  nop     dword ptr [rax+rax+00h]
0x180008f20  lea     rcx, [rdi+40h]
0x180008f24  xor     edx, edx
0x180008f26  call    cs:__imp_?Initialize@CWinsockInitializer@@QEAAKH@Z; CWinsockInitializer::Initialize(int)
0x180008f2d  nop     dword ptr [rax+rax+00h]
0x180008f32  mov     ecx, eax
0x180008f34  mov     r9d, 86h
0x180008f3a  mov     ebx, eax
0x180008f3c  call    ElValidateWin32_1
0x180008f41  xor     ebp, ebp
0x180008f43  test    eax, eax
0x180008f45  jz      short loc_180008F56
0x180008f47  test    ebx, ebx
0x180008f49  jle     short loc_180008FBA
0x180008f4b  movzx   ebx, bx
0x180008f4e  or      ebx, 80070000h
0x180008f54  jmp     short loc_180008FBA
0x180008f56  test    rsi, rsi
0x180008f59  jz      short loc_180008F7B
0x180008f5b  cmp     [rsi], bp
0x180008f5e  jz      short loc_180008F7B
0x180008f60  lea     rdx, [rdi+70h]
0x180008f64  mov     rcx, rsi
0x180008f67  call    cs:__imp_?ReverseQueryHostName@CNetworkAddress@@SAKPEBGPEAPEAG@Z; CNetworkAddress::ReverseQueryHostName(ushort const *,ushort * *)
0x180008f6e  nop     dword ptr [rax+rax+00h]
0x180008f73  mov     r9d, 9Ch
0x180008f79  jmp     short loc_180008F96
0x180008f7b  lea     rdx, [rdi+70h]
0x180008f7f  mov     ecx, 3
0x180008f84  call    cs:__imp_?GetHostName@@YAKW4_COMPUTER_NAME_FORMAT@@PEAPEAG@Z; GetHostName(_COMPUTER_NAME_FORMAT,ushort * *)
0x180008f8b  nop     dword ptr [rax+rax+00h]
0x180008f90  mov     r9d, 91h
0x180008f96  mov     ecx, eax
0x180008f98  mov     ebx, eax
0x180008f9a  call    ElValidateWin32_1
0x180008f9f  test    eax, eax
0x180008fa1  jnz     short loc_180008F47
0x180008fa3  mov     rcx, rdi; this
0x180008fa6  call    ?InitializeManagers@CWdsTransportServer@@AEAAJXZ; CWdsTransportServer::InitializeManagers(void)
0x180008fab  mov     r9d, 0A3h
0x180008fb1  mov     ecx, eax
0x180008fb3  mov     ebx, eax
0x180008fb5  call    ElValidateHr_1
0x180008fba  mov     r9, rdi
0x180008fbd  mov     [rsp+38h+var_18], ebx
0x180008fc1  lea     r8, aCwdstransports_7; "<- CWdsTransportServer::Initialize(0x%p"...
0x180008fc8  mov     edx, 10000h
0x180008fcd  lea     rcx, qword_18003B770
0x180008fd4  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180008fdb  nop     dword ptr [rax+rax+00h]
0x180008fe0  mov     rbp, [rsp+38h+arg_8]
0x180008fe5  mov     eax, ebx
0x180008fe7  mov     rbx, [rsp+38h+arg_0]
0x180008fec  mov     rsi, [rsp+38h+arg_10]
0x180008ff1  add     rsp, 30h
0x180008ff5  pop     rdi
0x180008ff6  retn
```
