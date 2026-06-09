# SlbNatWfpBlockExternalAddressPortRange

- ea: `0x140034078`
- end: `0x140034310`
- name: `SlbNatWfpBlockExternalAddressPortRange`
- size: `664`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140014dcc`

## callees

- `0x14000d7c8`
- `0x14001f320`
- `0x14001f980`
- `0x140034078`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140034290`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034290`
- `ntoskrnl!ExAllocatePool2` at `0x140034110`
- `ntoskrnl!ExAllocatePool2` at `0x140034110`
- `fwpkclnt!FwpmFilterAdd0` at `0x140034246`
- `fwpkclnt!FwpmFilterAdd0` at `0x14003426a`
- `fwpkclnt!FwpmFilterAdd0` at `0x140034246`
- `fwpkclnt!FwpmFilterAdd0` at `0x14003426a`
- `fwpkclnt!FwpmEngineClose0` at `0x1400342a5`
- `fwpkclnt!FwpmEngineClose0` at `0x1400342a5`
- `fwpkclnt!FwpmEngineOpen0` at `0x1400340ea`
- `fwpkclnt!FwpmEngineOpen0` at `0x1400340ea`

## pseudocode

```c
__int64 __fastcall SlbNatWfpBlockExternalAddressPortRange(_WORD *a1, HANDLE *a2)
{
  int v4; // edx
  NTSTATUS v5; // edi
  int v6; // r8d
  __int64 Pool2; // rax
  FWPM_FILTER0 *v8; // rsi
  __int64 v9; // rbx
  const GUID *v10; // rcx
  unsigned int *v11; // rax
  HANDLE engineHandle; // [rsp+40h] [rbp-69h] BYREF
  UINT64 id; // [rsp+48h] [rbp-61h] BYREF
  _OWORD v15[2]; // [rsp+50h] [rbp-59h] BYREF
  FWPM_SESSION0 session; // [rsp+70h] [rbp-39h] BYREF

  engineHandle = 0;
  memset(v15, 0, 28);
  memset(&session, 0, sizeof(session));
  id = 0;
  session.flags = 1;
  v5 = FwpmEngineOpen0(0, 0xAu, 0, &session, &engineHandle);
  if ( v5 >= 0 )
  {
    Pool2 = ExAllocatePool2(64, 360, 1719094871);
    v8 = (FWPM_FILTER0 *)Pool2;
    if ( Pool2 )
    {
      v9 = Pool2 + 200;
      *(_QWORD *)(Pool2 + 16) = L"Windows NAT TCP/UDP port range reservation filter";
      *(_QWORD *)(Pool2 + 24) = L"Blocks TCP/UDP port numbers reserved for Windows NAT external addresses";
      v10 = &FWPM_LAYER_ALE_RESOURCE_ASSIGNMENT_V4;
      v11 = (unsigned int *)(a1 + 2);
      if ( *a1 != 2 )
        v10 = &FWPM_LAYER_ALE_RESOURCE_ASSIGNMENT_V6;
      v8->layerKey = *v10;
      *(_DWORD *)(v9 + 16) = 0;
      *(GUID *)v9 = FWPM_CONDITION_IP_LOCAL_ADDRESS;
      if ( *a1 == 2 )
      {
        *(_DWORD *)(v9 + 24) = 3;
        *(_DWORD *)(v9 + 32) = _byteswap_ulong(*v11);
      }
      else
      {
        *(_DWORD *)(v9 + 24) = 11;
        *(_QWORD *)(v9 + 32) = v11;
      }
      *(_DWORD *)(v9 + 56) = 5;
      *(GUID *)(v9 + 40) = FWPM_CONDITION_IP_LOCAL_PORT;
      WORD4(v15[0]) = a1[10];
      WORD4(v15[1]) = a1[11];
      LODWORD(v15[0]) = 2;
      LODWORD(v15[1]) = 2;
      *(GUID *)(v9 + 80) = FWPM_CONDITION_IP_PROTOCOL;
      *(_QWORD *)(v9 + 72) = v15;
      *(_DWORD *)(v9 + 136) = 8;
      *(_DWORD *)(v9 + 152) = 8;
      *(GUID *)(v9 + 120) = FWPM_CONDITION_FLAGS;
      *(_DWORD *)(v9 + 64) = 258;
      *(_DWORD *)(v9 + 96) = 0;
      *(_DWORD *)(v9 + 104) = 1;
      *(_BYTE *)(v9 + 112) = 6;
      *(_DWORD *)(v9 + 144) = 3;
      v8->numFilterConditions = 4;
      v8->filterCondition = (FWPM_FILTER_CONDITION0 *)v9;
      v8->action.type = 4097;
      v5 = FwpmFilterAdd0(engineHandle, v8, 0, &id);
      if ( v5 >= 0 )
      {
        *(_BYTE *)(v9 + 112) = 17;
        v5 = FwpmFilterAdd0(engineHandle, v8, 0, &id);
        if ( v5 >= 0 )
        {
          *a2 = engineHandle;
          engineHandle = 0;
        }
      }
      ExFreePoolWithTag(v8, 0);
    }
    else
    {
      v5 = -1073741670;
    }
  }
  if ( engineHandle )
    FwpmEngineClose0(engineHandle);
  if ( v5 < 0 && dword_140027104 == 1 && (byte_140027BED & 0x10) != 0 )
    McTemplateK0qzqq_EtwWriteTransfer(
      (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
      v4,
      v6,
      3011,
      (__int64)L"Reserve external address and port range",
      0,
      v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140034078  push    rbp
0x14003407a  push    rbx
0x14003407b  push    rsi
0x14003407c  push    rdi
0x14003407d  push    r14
0x14003407f  push    r15
0x140034081  lea     rbp, [rsp-2Fh]
0x140034086  sub     rsp, 0D8h
0x14003408d  mov     rax, cs:__security_cookie
0x140034094  xor     rax, rsp
0x140034097  mov     [rbp+57h+var_40], rax
0x14003409b  xorps   xmm0, xmm0
0x14003409e  mov     [rbp+57h+var_C0], 0
0x1400340a6  xor     eax, eax
0x1400340a8  mov     r15, rdx
0x1400340ab  mov     r14, rcx
0x1400340ae  xor     edx, edx; Val
0x1400340b0  movups  [rbp+57h+var_B0], xmm0
0x1400340b4  lea     rcx, [rbp+57h+session]; void *
0x1400340b8  lea     r8d, [rax+48h]; Size
0x1400340bc  movups  [rbp+57h+var_B0+0Ch], xmm0
0x1400340c0  call    memset
0x1400340c5  xor     r8d, r8d; authIdentity
0x1400340c8  mov     [rbp+57h+id], 0
0x1400340d0  lea     rax, [rbp+57h+var_C0]
0x1400340d4  mov     [rbp+57h+session.flags], 1
0x1400340db  lea     r9, [rbp+57h+session]; session
0x1400340df  mov     [rsp+100h+engineHandle], rax; engineHandle
0x1400340e4  xor     ecx, ecx; serverName
0x1400340e6  lea     edx, [r8+0Ah]; authnService
0x1400340ea  call    cs:__imp_FwpmEngineOpen0
0x1400340f1  nop     dword ptr [rax+rax+00h]
0x1400340f6  mov     edi, eax
0x1400340f8  test    eax, eax
0x1400340fa  js      loc_14003429C
0x140034100  mov     edx, 168h
0x140034105  mov     ecx, 40h ; '@'
0x14003410a  mov     r8d, 66774E57h
0x140034110  call    cs:__imp_ExAllocatePool2
0x140034117  nop     dword ptr [rax+rax+00h]
0x14003411c  mov     rsi, rax
0x14003411f  test    rax, rax
0x140034122  jnz     short loc_14003412E
0x140034124  mov     edi, 0C000009Ah
0x140034129  jmp     loc_14003429C
0x14003412e  movups  xmm1, xmmword ptr cs:FWPM_CONDITION_IP_LOCAL_ADDRESS.Data1
0x140034135  lea     rbx, [rax+0C8h]
0x14003413c  mov     r8d, 2
0x140034142  lea     rax, aWindowsNatTcpU; "Windows NAT TCP/UDP port range reservat"...
0x140034149  mov     [rsi+10h], rax
0x14003414d  lea     rdx, FWPM_LAYER_ALE_RESOURCE_ASSIGNMENT_V6
0x140034154  lea     rax, aBlocksTcpUdpPo; "Blocks TCP/UDP port numbers reserved fo"...
0x14003415b  mov     [rsi+18h], rax
0x14003415f  lea     rcx, FWPM_LAYER_ALE_RESOURCE_ASSIGNMENT_V4
0x140034166  cmp     [r14], r8w
0x14003416a  lea     rax, [r14+4]
0x14003416e  cmovnz  rcx, rdx
0x140034172  movups  xmm0, xmmword ptr [rcx]
0x140034175  lea     ecx, [r8+1]
0x140034179  movdqu  xmmword ptr [rsi+40h], xmm0
0x14003417e  mov     dword ptr [rbx+10h], 0
0x140034185  movdqu  xmmword ptr [rbx], xmm1
0x140034189  cmp     [r14], r8w
0x14003418d  jnz     short loc_14003419B
0x14003418f  mov     [rbx+18h], ecx
0x140034192  mov     eax, [rax]
0x140034194  bswap   eax
0x140034196  mov     [rbx+20h], eax
0x140034199  jmp     short loc_1400341A6
0x14003419b  mov     dword ptr [rbx+18h], 0Bh
0x1400341a2  mov     [rbx+20h], rax
0x1400341a6  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_LOCAL_PORT.Data1
0x1400341ad  mov     dword ptr [rbx+38h], 5
0x1400341b4  lea     r9, [rbp+57h+id]; id
0x1400341b8  mov     rdx, rsi; filter
0x1400341bb  movdqu  xmmword ptr [rbx+28h], xmm0
0x1400341c0  movzx   eax, word ptr [r14+14h]
0x1400341c5  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_PROTOCOL.Data1
0x1400341cc  mov     word ptr [rbp+57h+var_B0+8], ax
0x1400341d0  movzx   eax, word ptr [r14+16h]
0x1400341d5  mov     [rbp+57h+var_98], ax
0x1400341d9  lea     rax, [rbp+57h+var_B0]
0x1400341dd  mov     dword ptr [rbp+57h+var_B0], r8d
0x1400341e1  mov     [rbp+57h+var_A0], r8d
0x1400341e5  xor     r8d, r8d; sd
0x1400341e8  movdqu  xmmword ptr [rbx+50h], xmm0
0x1400341ed  mov     [rbx+48h], rax
0x1400341f1  mov     eax, 8
0x1400341f6  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_FLAGS.Data1
0x1400341fd  mov     [rbx+88h], eax
0x140034203  mov     [rbx+98h], eax
0x140034209  movdqu  xmmword ptr [rbx+78h], xmm0
0x14003420e  mov     dword ptr [rbx+40h], 102h
0x140034215  mov     dword ptr [rbx+60h], 0
0x14003421c  mov     dword ptr [rbx+68h], 1
0x140034223  mov     byte ptr [rbx+70h], 6
0x140034227  mov     [rbx+90h], ecx
0x14003422d  mov     dword ptr [rsi+70h], 4
0x140034234  mov     [rsi+78h], rbx
0x140034238  mov     dword ptr [rsi+80h], 1001h
0x140034242  mov     rcx, [rbp+57h+var_C0]; engineHandle
0x140034246  call    cs:__imp_FwpmFilterAdd0
0x14003424d  nop     dword ptr [rax+rax+00h]
0x140034252  mov     edi, eax
0x140034254  test    eax, eax
0x140034256  js      short loc_14003428B
0x140034258  mov     byte ptr [rbx+70h], 11h
0x14003425c  lea     r9, [rbp+57h+id]; id
0x140034260  mov     rcx, [rbp+57h+var_C0]; engineHandle
0x140034264  xor     r8d, r8d; sd
0x140034267  mov     rdx, rsi; filter
0x14003426a  call    cs:__imp_FwpmFilterAdd0
0x140034271  nop     dword ptr [rax+rax+00h]
0x140034276  mov     edi, eax
0x140034278  test    eax, eax
0x14003427a  js      short loc_14003428B
0x14003427c  mov     rax, [rbp+57h+var_C0]
0x140034280  mov     [r15], rax
0x140034283  mov     [rbp+57h+var_C0], 0
0x14003428b  xor     edx, edx; Tag
0x14003428d  mov     rcx, rsi; P
0x140034290  call    cs:__imp_ExFreePoolWithTag
0x140034297  nop     dword ptr [rax+rax+00h]
0x14003429c  mov     rcx, [rbp+57h+var_C0]; engineHandle
0x1400342a0  test    rcx, rcx
0x1400342a3  jz      short loc_1400342B1
0x1400342a5  call    cs:__imp_FwpmEngineClose0
0x1400342ac  nop     dword ptr [rax+rax+00h]
0x1400342b1  test    edi, edi
0x1400342b3  jns     short loc_1400342F1
0x1400342b5  cmp     cs:dword_140027104, 1
0x1400342bc  jnz     short loc_1400342F1
0x1400342be  test    cs:byte_140027BED, 10h
0x1400342c5  jz      short loc_1400342F1
0x1400342c7  mov     [rsp+100h+var_D0], edi
0x1400342cb  lea     rax, aReserveExterna; "Reserve external address and port range"
0x1400342d2  mov     [rsp+100h+var_D8], 0
0x1400342da  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x1400342e1  mov     r9d, 0BC3h
0x1400342e7  mov     [rsp+100h+engineHandle], rax
0x1400342ec  call    McTemplateK0qzqq_EtwWriteTransfer
0x1400342f1  mov     eax, edi
0x1400342f3  mov     rcx, [rbp+57h+var_40]
0x1400342f7  xor     rcx, rsp; StackCookie
0x1400342fa  call    __security_check_cookie
0x1400342ff  add     rsp, 0D8h
0x140034306  pop     r15
0x140034308  pop     r14
0x14003430a  pop     rdi
0x14003430b  pop     rsi
0x14003430c  pop     rbx
0x14003430d  pop     rbp
0x14003430e  retn
```
