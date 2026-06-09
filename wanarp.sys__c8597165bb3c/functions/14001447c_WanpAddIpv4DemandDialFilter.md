# WanpAddIpv4DemandDialFilter

- ea: `0x14001447c`
- end: `0x1400146e5`
- name: `WanpAddIpv4DemandDialFilter`
- size: `617`
- prototype: `__int64 __fastcall(int, int, UINT64, __int64, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14001324c`

## callees

- `0x140004d48`
- `0x1400050b0`
- `0x1400054c0`
- `0x14001447c`

## import_xrefs

- `fwpkclnt!FwpmFilterDeleteById0` at `0x1400146a2`
- `fwpkclnt!FwpmFilterDeleteById0` at `0x1400146a2`
- `fwpkclnt!FwpmFilterAdd0` at `0x1400145ba`
- `fwpkclnt!FwpmFilterAdd0` at `0x140014685`
- `fwpkclnt!FwpmFilterAdd0` at `0x1400145ba`
- `fwpkclnt!FwpmFilterAdd0` at `0x140014685`

## pseudocode

```c
__int64 __fastcall WanpAddIpv4DemandDialFilter(int a1, int a2, UINT64 a3, __int64 a4, char a5)
{
  NTSTATUS CompartmentInformation; // edi
  int v10; // r15d
  _DWORD v12[4]; // [rsp+20h] [rbp-E0h] BYREF
  FWPM_FILTER0 filter; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v14; // [rsp+100h] [rbp+0h] BYREF
  _OWORD v15[2]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v16; // [rsp+130h] [rbp+30h]

  memset(&filter, 0, sizeof(filter));
  v16 = 0;
  v12[0] = *(_DWORD *)(a3 + 164);
  memset(v15, 0, sizeof(v15));
  v14 = 0;
  CompartmentInformation = FllwanpGetCompartmentInformation(0, v12, v15, &v14);
  if ( CompartmentInformation < 0 )
    goto LABEL_7;
  v10 = DWORD2(v15[0]);
  *(_DWORD *)(a4 + 176) = a1;
  *(_DWORD *)(a4 + 180) = a2;
  *(_DWORD *)(a4 + 16) = 0;
  *(_DWORD *)(a4 + 24) = 256;
  *(_QWORD *)(a4 + 32) = a4 + 176;
  *(_DWORD *)(a4 + 56) = 0;
  *(_DWORD *)(a4 + 64) = 3;
  *(_DWORD *)(a4 + 72) = v10;
  *(GUID *)a4 = FWPM_CONDITION_IP_REMOTE_ADDRESS;
  *(GUID *)(a4 + 40) = FWPM_CONDITION_INTERFACE_INDEX;
  if ( a5 )
  {
    filter.displayData.name = L"RRAS WANARP";
    filter.flags = 0;
    filter.layerKey = FWPM_LAYER_OUTBOUND_IPPACKET_V4;
    filter.weight.uint64 = (UINT64 *)&qword_140009568;
    filter.weight.type = FWP_UINT64;
    filter.numFilterConditions = 2;
    filter.action.4 = (union FWPM_ACTION0_::$6EA882394A24E7F0D0D0A8FACB4240B6)xmmword_140007668;
    filter.filterCondition = (FWPM_FILTER_CONDITION0 *)a4;
    filter.action.type = 20483;
    filter.rawContext = a3;
    CompartmentInformation = FwpmFilterAdd0(engineHandle, &filter, 0, (UINT64 *)(a4 + 80));
    if ( CompartmentInformation < 0 )
      goto LABEL_7;
  }
  *(_DWORD *)(a4 + 104) = 0;
  *(_DWORD *)(a4 + 112) = 256;
  *(_QWORD *)(a4 + 120) = a4 + 176;
  *(_DWORD *)(a4 + 144) = 0;
  *(_DWORD *)(a4 + 152) = 3;
  *(_DWORD *)(a4 + 160) = v10;
  *(GUID *)(a4 + 88) = FWPM_CONDITION_IP_DESTINATION_ADDRESS;
  *(GUID *)(a4 + 128) = FWPM_CONDITION_DESTINATION_INTERFACE_INDEX;
  if ( a5 )
  {
    filter.displayData.name = L"RRAS WANARP";
    filter.flags = 0;
    filter.layerKey = FWPM_LAYER_IPFORWARD_V4;
    filter.weight.uint64 = (UINT64 *)&qword_140009568;
    filter.weight.type = FWP_UINT64;
    filter.numFilterConditions = 2;
    filter.action.4 = (union FWPM_ACTION0_::$6EA882394A24E7F0D0D0A8FACB4240B6)xmmword_140007688;
    filter.filterCondition = (FWPM_FILTER_CONDITION0 *)(a4 + 88);
    filter.action.type = 20483;
    filter.rawContext = a3;
    CompartmentInformation = FwpmFilterAdd0(engineHandle, &filter, 0, (UINT64 *)(a4 + 168));
    if ( CompartmentInformation < 0 )
    {
      FwpmFilterDeleteById0(engineHandle, *(_QWORD *)(a4 + 80));
LABEL_7:
      *(_QWORD *)(a4 + 168) = 0;
      *(_QWORD *)(a4 + 80) = 0;
    }
  }
  return (unsigned int)CompartmentInformation;
}

```

## disassembly

```asm
0x14001447c  mov     [rsp-8+arg_0], rbx
0x140014481  push    rbp
0x140014482  push    rsi
0x140014483  push    rdi
0x140014484  push    r12
0x140014486  push    r13
0x140014488  push    r14
0x14001448a  push    r15
0x14001448c  lea     rbp, [rsp-40h]
0x140014491  sub     rsp, 140h
0x140014498  mov     rax, cs:__security_cookie
0x14001449f  xor     rax, rsp
0x1400144a2  mov     [rbp+70h+var_38], rax
0x1400144a6  mov     r13, r8
0x1400144a9  mov     esi, edx
0x1400144ab  mov     r12d, ecx
0x1400144ae  xor     edx, edx; Val
0x1400144b0  mov     r8d, 0C8h; Size
0x1400144b6  lea     rcx, [rsp+170h+filter]; void *
0x1400144bb  mov     rbx, r9
0x1400144be  call    memset
0x1400144c3  xorps   xmm0, xmm0
0x1400144c6  lea     r9, [rbp+70h+var_70]
0x1400144ca  xor     eax, eax
0x1400144cc  lea     r8, [rbp+70h+var_60]
0x1400144d0  mov     [rbp+70h+var_40], rax
0x1400144d4  lea     rdx, [rsp+170h+var_150]
0x1400144d9  mov     eax, [r13+0A4h]
0x1400144e0  xor     ecx, ecx
0x1400144e2  mov     [rsp+170h+var_150], eax
0x1400144e6  movups  [rbp+70h+var_60], xmm0
0x1400144ea  movups  [rbp+70h+var_50], xmm0
0x1400144ee  movups  [rbp+70h+var_70], xmm0
0x1400144f2  call    FllwanpGetCompartmentInformation
0x1400144f7  xor     ecx, ecx
0x1400144f9  mov     edi, eax
0x1400144fb  test    eax, eax
0x1400144fd  js      loc_1400146B0
0x140014503  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_REMOTE_ADDRESS.Data1
0x14001450a  mov     r15d, dword ptr [rbp+70h+var_60+8]
0x14001450e  lea     r14, [rbx+0B0h]
0x140014515  mov     [r14], r12d
0x140014518  lea     rdx, aRrasWanarp; "RRAS WANARP"
0x14001451f  mov     r12b, [rbp+70h+arg_20]
0x140014526  lea     r8, qword_140009568
0x14001452d  mov     [rbx+0B4h], esi
0x140014533  mov     [rbx+10h], ecx
0x140014536  mov     dword ptr [rbx+18h], 100h
0x14001453d  mov     [rbx+20h], r14
0x140014541  mov     [rbx+38h], ecx
0x140014544  mov     dword ptr [rbx+40h], 3
0x14001454b  mov     [rbx+48h], r15d
0x14001454f  movdqu  xmmword ptr [rbx], xmm0
0x140014553  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_INTERFACE_INDEX.Data1
0x14001455a  movdqu  xmmword ptr [rbx+28h], xmm0
0x14001455f  test    r12b, r12b
0x140014562  jz      short loc_1400145E0
0x140014564  movups  xmm0, xmmword ptr cs:FWPM_LAYER_OUTBOUND_IPPACKET_V4.Data1
0x14001456b  mov     [rsp+170h+filter.displayData.name], rdx
0x140014570  lea     r9, [rbx+50h]; id
0x140014574  mov     [rsp+170h+filter.flags], ecx
0x140014578  lea     rdx, [rsp+170h+filter]; filter
0x14001457d  mov     rcx, cs:engineHandle; engineHandle
0x140014584  movdqu  xmmword ptr [rsp+170h+filter.layerKey.Data1], xmm0
0x14001458a  mov     qword ptr [rbp+70h+filter.weight.8], r8
0x14001458e  xor     r8d, r8d; sd
0x140014591  movups  xmm0, cs:xmmword_140007668
0x140014598  mov     [rbp+70h+filter.weight.type], 4
0x14001459f  mov     [rbp+70h+filter.numFilterConditions], 2
0x1400145a6  movdqu  xmmword ptr [rbp+70h+filter.action.4], xmm0
0x1400145ab  mov     [rbp+70h+filter.filterCondition], rbx
0x1400145af  mov     [rbp+70h+filter.action.type], 5003h
0x1400145b6  mov     qword ptr [rbp+70h+filter.98h], r13
0x1400145ba  call    cs:__imp_FwpmFilterAdd0
0x1400145c1  nop     dword ptr [rax+rax+00h]
0x1400145c6  xor     ecx, ecx
0x1400145c8  mov     edi, eax
0x1400145ca  test    eax, eax
0x1400145cc  js      loc_1400146B0
0x1400145d2  lea     rdx, aRrasWanarp; "RRAS WANARP"
0x1400145d9  lea     r8, qword_140009568
0x1400145e0  mov     [rbx+68h], ecx
0x1400145e3  lea     rax, [rbx+58h]
0x1400145e7  mov     dword ptr [rbx+70h], 100h
0x1400145ee  mov     [rbx+78h], r14
0x1400145f2  mov     [rbx+90h], ecx
0x1400145f8  mov     dword ptr [rbx+98h], 3
0x140014602  mov     [rbx+0A0h], r15d
0x140014609  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_DESTINATION_ADDRESS.Data1
0x140014610  movdqu  xmmword ptr [rax], xmm0
0x140014614  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_DESTINATION_INTERFACE_INDEX.Data1
0x14001461b  movdqu  xmmword ptr [rbx+80h], xmm0
0x140014623  test    r12b, r12b
0x140014626  jz      loc_1400146BB
0x14001462c  movups  xmm0, xmmword ptr cs:FWPM_LAYER_IPFORWARD_V4.Data1
0x140014633  mov     [rsp+170h+filter.displayData.name], rdx
0x140014638  lea     r9, [rbx+0A8h]; id
0x14001463f  mov     [rsp+170h+filter.flags], ecx
0x140014643  lea     rdx, [rsp+170h+filter]; filter
0x140014648  mov     rcx, cs:engineHandle; engineHandle
0x14001464f  movdqu  xmmword ptr [rsp+170h+filter.layerKey.Data1], xmm0
0x140014655  mov     qword ptr [rbp+70h+filter.weight.8], r8
0x140014659  xor     r8d, r8d; sd
0x14001465c  movups  xmm0, cs:xmmword_140007688
0x140014663  mov     [rbp+70h+filter.weight.type], 4
0x14001466a  mov     [rbp+70h+filter.numFilterConditions], 2
0x140014671  movdqu  xmmword ptr [rbp+70h+filter.action.4], xmm0
0x140014676  mov     [rbp+70h+filter.filterCondition], rax
0x14001467a  mov     [rbp+70h+filter.action.type], 5003h
0x140014681  mov     qword ptr [rbp+70h+filter.98h], r13
0x140014685  call    cs:__imp_FwpmFilterAdd0
0x14001468c  nop     dword ptr [rax+rax+00h]
0x140014691  mov     edi, eax
0x140014693  test    eax, eax
0x140014695  jns     short loc_1400146BB
0x140014697  mov     rdx, [rbx+50h]; id
0x14001469b  mov     rcx, cs:engineHandle; engineHandle
0x1400146a2  call    cs:__imp_FwpmFilterDeleteById0
0x1400146a9  nop     dword ptr [rax+rax+00h]
0x1400146ae  xor     ecx, ecx
0x1400146b0  mov     [rbx+0A8h], rcx
0x1400146b7  mov     [rbx+50h], rcx
0x1400146bb  mov     eax, edi
0x1400146bd  mov     rcx, [rbp+70h+var_38]
0x1400146c1  xor     rcx, rsp; StackCookie
0x1400146c4  call    __security_check_cookie
0x1400146c9  mov     rbx, [rsp+170h+arg_0]
0x1400146d1  add     rsp, 140h
0x1400146d8  pop     r15
0x1400146da  pop     r14
0x1400146dc  pop     r13
0x1400146de  pop     r12
0x1400146e0  pop     rdi
0x1400146e1  pop     rsi
0x1400146e2  pop     rbp
0x1400146e3  retn
```
