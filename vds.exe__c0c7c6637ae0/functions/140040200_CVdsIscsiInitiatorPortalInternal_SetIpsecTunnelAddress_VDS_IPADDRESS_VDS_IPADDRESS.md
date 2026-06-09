# CVdsIscsiInitiatorPortalInternal::SetIpsecTunnelAddress(_VDS_IPADDRESS *,_VDS_IPADDRESS *)

- ea: `0x140040200`
- end: `0x140040405`
- name: `?SetIpsecTunnelAddress@CVdsIscsiInitiatorPortalInternal@@UEAAJPEAU_VDS_IPADDRESS@@0@Z`
- size: `517`
- prototype: `__int64 __fastcall(CVdsIscsiInitiatorPortalInternal *__hidden this, struct _VDS_IPADDRESS *, struct _VDS_IPADDRESS *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x14002e123`
- `0x140040200`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400403c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400403c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400402be`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400402be`
- `vdsutil!VdsIscsiIpAddressToString` at `0x140040312`
- `vdsutil!VdsIscsiIpAddressToString` at `0x140040336`
- `vdsutil!VdsIscsiIpAddressToString` at `0x140040312`
- `vdsutil!VdsIscsiIpAddressToString` at `0x140040336`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140040253`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140040253`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400403d7`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400403d7`
- `vdsutil!VdsTraceW` at `0x1400402a1`
- `vdsutil!VdsTraceW` at `0x1400402fa`
- `vdsutil!VdsTraceW` at `0x140040394`
- `vdsutil!VdsTraceW` at `0x1400403ae`
- `vdsutil!VdsTraceW` at `0x1400402a1`
- `vdsutil!VdsTraceW` at `0x1400402fa`
- `vdsutil!VdsTraceW` at `0x140040394`
- `vdsutil!VdsTraceW` at `0x1400403ae`

## string_xrefs

- `0x1400403a5`: `CVdsIscsiInitiatorPortalInternal::SetIpsecTunnelAddress: Could not access necessary function in iSCSI library.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVdsIscsiInitiatorPortalInternal::SetIpsecTunnelAddress(
        CVdsIscsiInitiatorPortalInternal *this,
        struct _VDS_IPADDRESS *a2,
        struct _VDS_IPADDRESS *a3)
{
  FARPROC ProcAddress; // rdi
  int v7; // eax
  unsigned int v8; // ebx
  int v9; // eax
  int v10; // eax
  unsigned int v11; // eax
  char v13; // [rsp+20h] [rbp-E0h]
  _BYTE v14[16]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v15; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-B0h]
  _BYTE v17[512]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v18[512]; // [rsp+260h] [rbp+160h] BYREF

  v15 = 0;
  pv = 0;
  CVdsCallTracer::CVdsCallTracer(
    (CVdsCallTracer *)v14,
    0x5Eu,
    "CVdsIscsiInitiatorPortalInternal::SetIpsecTunnelAddress()");
  v15 = 0;
  pv = 0;
  memset_0(v17, 0, sizeof(v17));
  memset_0(v18, 0, sizeof(v18));
  if ( !a2 || !a3 )
    VdsTraceW(0, L"CVdsIscsiInitiatorPortalInternal::SetIpsecTunnelAddress: NULL input arguments");
  if ( CVdsService::m_hIscsidscModule
    && (ProcAddress = GetProcAddress(CVdsService::m_hIscsidscModule, "SetIScsiTunnelModeOuterAddressW")) != 0 )
  {
    v7 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(**((_QWORD **)this + 8) + 24LL))(*((_QWORD *)this + 8), &v15);
    v8 = v7;
    if ( v7 >= 0 )
    {
      v9 = VdsIscsiIpAddressToString(a2, 256, v17);
      v8 = v9;
      if ( v9 >= 0 )
      {
        v10 = VdsIscsiIpAddressToString(a3, 256, v18);
        v8 = v10;
        if ( v10 >= 0 )
        {
          v13 = 1;
          v11 = ((__int64 (__fastcall *)(LPVOID, _QWORD, _BYTE *, _BYTE *, char))ProcAddress)(
                  pv,
                  *((unsigned int *)this + 160),
                  v18,
                  v17,
                  v13);
          if ( v11 && ((v11 & 0xFFF0000) == 0 || (v11 & 0xC0000000) == 0xC0000000) )
          {
            VdsTraceW(
              0,
              L"CVdsIscsiInitiatorPortalInternal::SetIpsecTunnelAddress: SetIScsiTunnelModeOuterAddressW failed: %X",
              v11);
            v8 = -2147211004;
          }
          else
          {
            v8 = 0;
          }
        }
        else
        {
          VdsTraceW(
            0,
            L"CVdsIscsiInitiatorPortalInternal::SetIpsecTunnelAddress: VdsIscsiIpAddressToString pDestinationAddress: %X",
            (unsigned int)v10);
        }
      }
      else
      {
        VdsTraceW(
          0,
          L"CVdsIscsiInitiatorPortalInternal::SetIpsecTunnelAddress: VdsIscsiIpAddressToString pTunnelAddress: %X",
          (unsigned int)v9);
      }
    }
    else
    {
      VdsTraceW(
        0,
        L"CVdsIscsiInitiatorPortalInternal::SetIpsecTunnelAddress: m_pParentAdapter->GetProperties: %X",
        (unsigned int)v7);
    }
  }
  else
  {
    VdsTraceW(
      0,
      L"CVdsIscsiInitiatorPortalInternal::SetIpsecTunnelAddress: Could not access necessary function in iSCSI library.");
    v8 = -2147212288;
  }
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v14);
  return v8;
}

```

## disassembly

```asm
0x140040200  mov     [rsp-8+arg_18], rbx
0x140040205  push    rbp
0x140040206  push    rsi
0x140040207  push    rdi
0x140040208  push    r14
0x14004020a  push    r15
0x14004020c  lea     rbp, [rsp-370h]
0x140040214  sub     rsp, 470h
0x14004021b  mov     rax, cs:__security_cookie
0x140040222  xor     rax, rsp
0x140040225  mov     [rbp+390h+var_30], rax
0x14004022c  mov     rsi, r8
0x14004022f  mov     r15, rdx
0x140040232  mov     r14, rcx
0x140040235  xorps   xmm0, xmm0
0x140040238  xor     eax, eax
0x14004023a  movups  [rsp+490h+var_450], xmm0
0x14004023f  mov     [rsp+490h+pv], rax
0x140040244  lea     r8, aCvdsiscsiiniti_35; "CVdsIscsiInitiatorPortalInternal::SetIp"...
0x14004024b  lea     edx, [rax+5Eh]
0x14004024e  lea     rcx, [rsp+490h+var_460]
0x140040253  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140040259  nop
0x14004025a  xorps   xmm0, xmm0
0x14004025d  xor     eax, eax
0x14004025f  movups  [rsp+490h+var_450], xmm0
0x140040264  mov     [rsp+490h+pv], rax
0x140040269  mov     ebx, 200h
0x14004026e  mov     r8d, ebx; Size
0x140040271  xor     edx, edx; Val
0x140040273  lea     rcx, [rsp+490h+var_430]; void *
0x140040278  call    memset_0
0x14004027d  mov     r8d, ebx; Size
0x140040280  xor     edx, edx; Val
0x140040282  lea     rcx, [rbp+390h+var_230]; void *
0x140040289  call    memset_0
0x14004028e  test    r15, r15
0x140040291  jz      short loc_140040298
0x140040293  test    rsi, rsi
0x140040296  jnz     short loc_1400402A7
0x140040298  lea     rdx, aCvdsiscsiiniti_93; "CVdsIscsiInitiatorPortalInternal::SetIp"...
0x14004029f  xor     ecx, ecx
0x1400402a1  call    cs:__imp_VdsTraceW
0x1400402a7  mov     rcx, cs:?m_hIscsidscModule@CVdsService@@2PEAUHINSTANCE__@@EA; hModule
0x1400402ae  test    rcx, rcx
0x1400402b1  jz      loc_1400403A5
0x1400402b7  lea     rdx, aSetiscsitunnel; "SetIScsiTunnelModeOuterAddressW"
0x1400402be  call    cs:__imp_GetProcAddress
0x1400402c4  mov     rdi, rax
0x1400402c7  test    rax, rax
0x1400402ca  jz      loc_1400403A5
0x1400402d0  mov     r8, [r14+40h]
0x1400402d4  mov     rcx, [r8]
0x1400402d7  mov     rax, [rcx+18h]
0x1400402db  lea     rdx, [rsp+490h+var_450]
0x1400402e0  mov     rcx, r8
0x1400402e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400402e8  mov     ebx, eax
0x1400402ea  test    eax, eax
0x1400402ec  jns     short loc_140040305
0x1400402ee  lea     rdx, aCvdsiscsiiniti_85; "CVdsIscsiInitiatorPortalInternal::SetIp"...
0x1400402f5  mov     r8d, eax
0x1400402f8  xor     ecx, ecx
0x1400402fa  call    cs:__imp_VdsTraceW
0x140040300  jmp     loc_1400403B9
0x140040305  lea     r8, [rsp+490h+var_430]
0x14004030a  mov     edx, 100h
0x14004030f  mov     rcx, r15
0x140040312  call    cs:__imp_VdsIscsiIpAddressToString
0x140040318  mov     ebx, eax
0x14004031a  test    eax, eax
0x14004031c  jns     short loc_140040327
0x14004031e  lea     rdx, aCvdsiscsiiniti_73; "CVdsIscsiInitiatorPortalInternal::SetIp"...
0x140040325  jmp     short loc_1400402F5
0x140040327  lea     r8, [rbp+390h+var_230]
0x14004032e  mov     edx, 100h
0x140040333  mov     rcx, rsi
0x140040336  call    cs:__imp_VdsIscsiIpAddressToString
0x14004033c  mov     ebx, eax
0x14004033e  test    eax, eax
0x140040340  jns     short loc_14004034B
0x140040342  lea     rdx, aCvdsiscsiiniti_43; "CVdsIscsiInitiatorPortalInternal::SetIp"...
0x140040349  jmp     short loc_1400402F5
0x14004034b  mov     [rsp+490h+var_470], 1
0x140040350  lea     r9, [rsp+490h+var_430]
0x140040355  lea     r8, [rbp+390h+var_230]
0x14004035c  mov     edx, [r14+280h]
0x140040363  mov     rcx, [rsp+490h+pv]
0x140040368  mov     rax, rdi
0x14004036b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140040370  test    eax, eax
0x140040372  jz      short loc_1400403A1
0x140040374  test    eax, 0FFF0000h
0x140040379  jz      short loc_140040388
0x14004037b  mov     ecx, eax
0x14004037d  mov     edx, 0C0000000h
0x140040382  and     ecx, edx
0x140040384  cmp     ecx, edx
0x140040386  jnz     short loc_1400403A1
0x140040388  mov     r8d, eax
0x14004038b  lea     rdx, aCvdsiscsiiniti_23; "CVdsIscsiInitiatorPortalInternal::SetIp"...
0x140040392  xor     ecx, ecx
0x140040394  call    cs:__imp_VdsTraceW
0x14004039a  mov     ebx, 80042904h
0x14004039f  jmp     short loc_1400403B9
0x1400403a1  xor     ebx, ebx
0x1400403a3  jmp     short loc_1400403B9
0x1400403a5  lea     rdx, aCvdsiscsiiniti_18; "CVdsIscsiInitiatorPortalInternal::SetIp"...
0x1400403ac  xor     ecx, ecx
0x1400403ae  call    cs:__imp_VdsTraceW
0x1400403b4  mov     ebx, 80042400h
0x1400403b9  mov     rcx, [rsp+490h+pv]; pv
0x1400403be  test    rcx, rcx
0x1400403c1  jz      short loc_1400403D2
0x1400403c3  call    cs:__imp_CoTaskMemFree
0x1400403c9  mov     [rsp+490h+pv], 0
0x1400403d2  lea     rcx, [rsp+490h+var_460]
0x1400403d7  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x1400403dd  mov     eax, ebx
0x1400403df  mov     rcx, [rbp+390h+var_30]
0x1400403e6  xor     rcx, rsp; StackCookie
0x1400403e9  call    __security_check_cookie
0x1400403ee  mov     rbx, [rsp+490h+arg_18]
0x1400403f6  add     rsp, 470h
0x1400403fd  pop     r15
0x1400403ff  pop     r14
0x140040401  pop     rdi
0x140040402  pop     rsi
0x140040403  pop     rbp
0x140040404  retn
```
