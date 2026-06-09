# SlbNatWfpBlockExternalAddressPortRange

- ea: `0x140032f48`
- end: `0x1400331e0`
- name: `SlbNatWfpBlockExternalAddressPortRange`
- size: `664`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14001448c`

## callees

- `0x14000d7f8`
- `0x14001ede0`
- `0x14001f440`
- `0x140032f48`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140033160`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033160`
- `ntoskrnl!ExAllocatePool2` at `0x140032fe0`
- `ntoskrnl!ExAllocatePool2` at `0x140032fe0`
- `fwpkclnt!FwpmFilterAdd0` at `0x140033116`
- `fwpkclnt!FwpmFilterAdd0` at `0x14003313a`
- `fwpkclnt!FwpmFilterAdd0` at `0x140033116`
- `fwpkclnt!FwpmFilterAdd0` at `0x14003313a`
- `fwpkclnt!FwpmEngineClose0` at `0x140033175`
- `fwpkclnt!FwpmEngineClose0` at `0x140033175`
- `fwpkclnt!FwpmEngineOpen0` at `0x140032fba`
- `fwpkclnt!FwpmEngineOpen0` at `0x140032fba`

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
  if ( v5 < 0 && dword_140026104 == 1 && (byte_140026BED & 0x10) != 0 )
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
0x140032f48  push    rbp
0x140032f4a  push    rbx
0x140032f4b  push    rsi
0x140032f4c  push    rdi
0x140032f4d  push    r14
0x140032f4f  push    r15
0x140032f51  lea     rbp, [rsp-2Fh]
0x140032f56  sub     rsp, 0D8h
0x140032f5d  mov     rax, cs:__security_cookie
0x140032f64  xor     rax, rsp
0x140032f67  mov     [rbp+57h+var_40], rax
0x140032f6b  xorps   xmm0, xmm0
0x140032f6e  mov     [rbp+57h+var_C0], 0
0x140032f76  xor     eax, eax
0x140032f78  mov     r15, rdx
0x140032f7b  mov     r14, rcx
0x140032f7e  xor     edx, edx; Val
0x140032f80  movups  [rbp+57h+var_B0], xmm0
0x140032f84  lea     rcx, [rbp+57h+session]; void *
0x140032f88  lea     r8d, [rax+48h]; Size
0x140032f8c  movups  [rbp+57h+var_B0+0Ch], xmm0
0x140032f90  call    memset
0x140032f95  xor     r8d, r8d; authIdentity
0x140032f98  mov     [rbp+57h+id], 0
0x140032fa0  lea     rax, [rbp+57h+var_C0]
0x140032fa4  mov     [rbp+57h+session.flags], 1
0x140032fab  lea     r9, [rbp+57h+session]; session
0x140032faf  mov     [rsp+100h+engineHandle], rax; engineHandle
0x140032fb4  xor     ecx, ecx; serverName
0x140032fb6  lea     edx, [r8+0Ah]; authnService
0x140032fba  call    cs:__imp_FwpmEngineOpen0
0x140032fc1  nop     dword ptr [rax+rax+00h]
0x140032fc6  mov     edi, eax
0x140032fc8  test    eax, eax
0x140032fca  js      loc_14003316C
0x140032fd0  mov     edx, 168h
0x140032fd5  mov     ecx, 40h ; '@'
0x140032fda  mov     r8d, 66774E57h
0x140032fe0  call    cs:__imp_ExAllocatePool2
0x140032fe7  nop     dword ptr [rax+rax+00h]
0x140032fec  mov     rsi, rax
0x140032fef  test    rax, rax
0x140032ff2  jnz     short loc_140032FFE
0x140032ff4  mov     edi, 0C000009Ah
0x140032ff9  jmp     loc_14003316C
0x140032ffe  movups  xmm1, xmmword ptr cs:FWPM_CONDITION_IP_LOCAL_ADDRESS.Data1
0x140033005  lea     rbx, [rax+0C8h]
0x14003300c  mov     r8d, 2
0x140033012  lea     rax, aWindowsNatTcpU; "Windows NAT TCP/UDP port range reservat"...
0x140033019  mov     [rsi+10h], rax
0x14003301d  lea     rdx, FWPM_LAYER_ALE_RESOURCE_ASSIGNMENT_V6
0x140033024  lea     rax, aBlocksTcpUdpPo; "Blocks TCP/UDP port numbers reserved fo"...
0x14003302b  mov     [rsi+18h], rax
0x14003302f  lea     rcx, FWPM_LAYER_ALE_RESOURCE_ASSIGNMENT_V4
0x140033036  cmp     [r14], r8w
0x14003303a  lea     rax, [r14+4]
0x14003303e  cmovnz  rcx, rdx
0x140033042  movups  xmm0, xmmword ptr [rcx]
0x140033045  lea     ecx, [r8+1]
0x140033049  movdqu  xmmword ptr [rsi+40h], xmm0
0x14003304e  mov     dword ptr [rbx+10h], 0
0x140033055  movdqu  xmmword ptr [rbx], xmm1
0x140033059  cmp     [r14], r8w
0x14003305d  jnz     short loc_14003306B
0x14003305f  mov     [rbx+18h], ecx
0x140033062  mov     eax, [rax]
0x140033064  bswap   eax
0x140033066  mov     [rbx+20h], eax
0x140033069  jmp     short loc_140033076
0x14003306b  mov     dword ptr [rbx+18h], 0Bh
0x140033072  mov     [rbx+20h], rax
0x140033076  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_LOCAL_PORT.Data1
0x14003307d  mov     dword ptr [rbx+38h], 5
0x140033084  lea     r9, [rbp+57h+id]; id
0x140033088  mov     rdx, rsi; filter
0x14003308b  movdqu  xmmword ptr [rbx+28h], xmm0
0x140033090  movzx   eax, word ptr [r14+14h]
0x140033095  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_PROTOCOL.Data1
0x14003309c  mov     word ptr [rbp+57h+var_B0+8], ax
0x1400330a0  movzx   eax, word ptr [r14+16h]
0x1400330a5  mov     [rbp+57h+var_98], ax
0x1400330a9  lea     rax, [rbp+57h+var_B0]
0x1400330ad  mov     dword ptr [rbp+57h+var_B0], r8d
0x1400330b1  mov     [rbp+57h+var_A0], r8d
0x1400330b5  xor     r8d, r8d; sd
0x1400330b8  movdqu  xmmword ptr [rbx+50h], xmm0
0x1400330bd  mov     [rbx+48h], rax
0x1400330c1  mov     eax, 8
0x1400330c6  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_FLAGS.Data1
0x1400330cd  mov     [rbx+88h], eax
0x1400330d3  mov     [rbx+98h], eax
0x1400330d9  movdqu  xmmword ptr [rbx+78h], xmm0
0x1400330de  mov     dword ptr [rbx+40h], 102h
0x1400330e5  mov     dword ptr [rbx+60h], 0
0x1400330ec  mov     dword ptr [rbx+68h], 1
0x1400330f3  mov     byte ptr [rbx+70h], 6
0x1400330f7  mov     [rbx+90h], ecx
0x1400330fd  mov     dword ptr [rsi+70h], 4
0x140033104  mov     [rsi+78h], rbx
0x140033108  mov     dword ptr [rsi+80h], 1001h
0x140033112  mov     rcx, [rbp+57h+var_C0]; engineHandle
0x140033116  call    cs:__imp_FwpmFilterAdd0
0x14003311d  nop     dword ptr [rax+rax+00h]
0x140033122  mov     edi, eax
0x140033124  test    eax, eax
0x140033126  js      short loc_14003315B
0x140033128  mov     byte ptr [rbx+70h], 11h
0x14003312c  lea     r9, [rbp+57h+id]; id
0x140033130  mov     rcx, [rbp+57h+var_C0]; engineHandle
0x140033134  xor     r8d, r8d; sd
0x140033137  mov     rdx, rsi; filter
0x14003313a  call    cs:__imp_FwpmFilterAdd0
0x140033141  nop     dword ptr [rax+rax+00h]
0x140033146  mov     edi, eax
0x140033148  test    eax, eax
0x14003314a  js      short loc_14003315B
0x14003314c  mov     rax, [rbp+57h+var_C0]
0x140033150  mov     [r15], rax
0x140033153  mov     [rbp+57h+var_C0], 0
0x14003315b  xor     edx, edx; Tag
0x14003315d  mov     rcx, rsi; P
0x140033160  call    cs:__imp_ExFreePoolWithTag
0x140033167  nop     dword ptr [rax+rax+00h]
0x14003316c  mov     rcx, [rbp+57h+var_C0]; engineHandle
0x140033170  test    rcx, rcx
0x140033173  jz      short loc_140033181
0x140033175  call    cs:__imp_FwpmEngineClose0
0x14003317c  nop     dword ptr [rax+rax+00h]
0x140033181  test    edi, edi
0x140033183  jns     short loc_1400331C1
0x140033185  cmp     cs:dword_140026104, 1
0x14003318c  jnz     short loc_1400331C1
0x14003318e  test    cs:byte_140026BED, 10h
0x140033195  jz      short loc_1400331C1
0x140033197  mov     [rsp+100h+var_D0], edi
0x14003319b  lea     rax, aReserveExterna; "Reserve external address and port range"
0x1400331a2  mov     [rsp+100h+var_D8], 0
0x1400331aa  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x1400331b1  mov     r9d, 0BC3h
0x1400331b7  mov     [rsp+100h+engineHandle], rax
0x1400331bc  call    McTemplateK0qzqq_EtwWriteTransfer
0x1400331c1  mov     eax, edi
0x1400331c3  mov     rcx, [rbp+57h+var_40]
0x1400331c7  xor     rcx, rsp; StackCookie
0x1400331ca  call    __security_check_cookie
0x1400331cf  add     rsp, 0D8h
0x1400331d6  pop     r15
0x1400331d8  pop     r14
0x1400331da  pop     rdi
0x1400331db  pop     rsi
0x1400331dc  pop     rbx
0x1400331dd  pop     rbp
0x1400331de  retn
```
