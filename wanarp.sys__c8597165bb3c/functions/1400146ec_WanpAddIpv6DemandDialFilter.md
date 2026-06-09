# WanpAddIpv6DemandDialFilter

- ea: `0x1400146ec`
- end: `0x14001495e`
- name: `WanpAddIpv6DemandDialFilter`
- size: `626`
- prototype: `__int64 __fastcall(__int128 *, char, UINT64, __int64, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14001324c`

## callees

- `0x140004d48`
- `0x1400050b0`
- `0x1400054c0`
- `0x1400146ec`

## import_xrefs

- `fwpkclnt!FwpmFilterDeleteById0` at `0x14001491b`
- `fwpkclnt!FwpmFilterDeleteById0` at `0x14001491b`
- `fwpkclnt!FwpmFilterAdd0` at `0x140014833`
- `fwpkclnt!FwpmFilterAdd0` at `0x1400148fe`
- `fwpkclnt!FwpmFilterAdd0` at `0x140014833`
- `fwpkclnt!FwpmFilterAdd0` at `0x1400148fe`

## pseudocode

```c
__int64 __fastcall WanpAddIpv6DemandDialFilter(__int128 *a1, char a2, UINT64 a3, __int64 a4, char a5)
{
  NTSTATUS CompartmentInformation; // edi
  __int128 v10; // xmm0
  int v11; // r12d
  _DWORD v13[4]; // [rsp+20h] [rbp-E0h] BYREF
  FWPM_FILTER0 filter; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v15; // [rsp+100h] [rbp+0h] BYREF
  _OWORD v16[2]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v17; // [rsp+130h] [rbp+30h]

  memset(&filter, 0, sizeof(filter));
  v17 = 0;
  v13[0] = *(_DWORD *)(a3 + 164);
  memset(v16, 0, sizeof(v16));
  v15 = 0;
  CompartmentInformation = FllwanpGetCompartmentInformation(0, v13, v16, &v15);
  if ( CompartmentInformation < 0 )
    goto LABEL_7;
  v10 = *a1;
  v11 = DWORD2(v16[0]);
  *(_BYTE *)(a4 + 192) = a2;
  *(_OWORD *)(a4 + 176) = v10;
  *(_DWORD *)(a4 + 16) = 0;
  *(_DWORD *)(a4 + 24) = 257;
  *(_QWORD *)(a4 + 32) = a4 + 176;
  *(_DWORD *)(a4 + 56) = 0;
  *(_DWORD *)(a4 + 64) = 3;
  *(_DWORD *)(a4 + 72) = v11;
  *(GUID *)a4 = FWPM_CONDITION_IP_REMOTE_ADDRESS;
  *(GUID *)(a4 + 40) = FWPM_CONDITION_INTERFACE_INDEX;
  if ( a5 )
  {
    filter.displayData.name = L"RRAS WANARP";
    filter.flags = 0;
    filter.layerKey = FWPM_LAYER_OUTBOUND_IPPACKET_V6;
    filter.weight.uint64 = (UINT64 *)&qword_140009568;
    filter.weight.type = FWP_UINT64;
    filter.numFilterConditions = 2;
    filter.action.4 = (union FWPM_ACTION0_::$6EA882394A24E7F0D0D0A8FACB4240B6)xmmword_140007658;
    filter.filterCondition = (FWPM_FILTER_CONDITION0 *)a4;
    filter.action.type = 20483;
    filter.rawContext = a3;
    CompartmentInformation = FwpmFilterAdd0(engineHandle, &filter, 0, (UINT64 *)(a4 + 80));
    if ( CompartmentInformation < 0 )
      goto LABEL_7;
  }
  *(_DWORD *)(a4 + 104) = 0;
  *(_DWORD *)(a4 + 112) = 257;
  *(_QWORD *)(a4 + 120) = a4 + 176;
  *(_DWORD *)(a4 + 144) = 0;
  *(_DWORD *)(a4 + 152) = 3;
  *(_DWORD *)(a4 + 160) = v11;
  *(GUID *)(a4 + 88) = FWPM_CONDITION_IP_DESTINATION_ADDRESS;
  *(GUID *)(a4 + 128) = FWPM_CONDITION_DESTINATION_INTERFACE_INDEX;
  if ( a5 )
  {
    filter.displayData.name = L"RRAS WANARP";
    filter.flags = 0;
    filter.layerKey = FWPM_LAYER_IPFORWARD_V6;
    filter.weight.uint64 = (UINT64 *)&qword_140009568;
    filter.weight.type = FWP_UINT64;
    filter.numFilterConditions = 2;
    filter.action.4 = (union FWPM_ACTION0_::$6EA882394A24E7F0D0D0A8FACB4240B6)xmmword_140007678;
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
0x1400146ec  mov     [rsp-8+arg_0], rbx
0x1400146f1  push    rbp
0x1400146f2  push    rsi
0x1400146f3  push    rdi
0x1400146f4  push    r12
0x1400146f6  push    r13
0x1400146f8  push    r14
0x1400146fa  push    r15
0x1400146fc  lea     rbp, [rsp-40h]
0x140014701  sub     rsp, 140h
0x140014708  mov     rax, cs:__security_cookie
0x14001470f  xor     rax, rsp
0x140014712  mov     [rbp+70h+var_38], rax
0x140014716  mov     r15, r8
0x140014719  mov     sil, dl
0x14001471c  mov     r13, rcx
0x14001471f  xor     edx, edx; Val
0x140014721  mov     r8d, 0C8h; Size
0x140014727  lea     rcx, [rsp+170h+filter]; void *
0x14001472c  mov     rbx, r9
0x14001472f  call    memset
0x140014734  xorps   xmm0, xmm0
0x140014737  lea     r9, [rbp+70h+var_70]
0x14001473b  xor     eax, eax
0x14001473d  lea     r8, [rbp+70h+var_60]
0x140014741  mov     [rbp+70h+var_40], rax
0x140014745  lea     rdx, [rsp+170h+var_150]
0x14001474a  mov     eax, [r15+0A4h]
0x140014751  xor     ecx, ecx
0x140014753  mov     [rsp+170h+var_150], eax
0x140014757  movups  [rbp+70h+var_60], xmm0
0x14001475b  movups  [rbp+70h+var_50], xmm0
0x14001475f  movups  [rbp+70h+var_70], xmm0
0x140014763  call    FllwanpGetCompartmentInformation
0x140014768  xor     ecx, ecx
0x14001476a  mov     edi, eax
0x14001476c  test    eax, eax
0x14001476e  js      loc_140014929
0x140014774  movups  xmm0, xmmword ptr [r13+0]
0x140014779  mov     r13b, [rbp+70h+arg_20]
0x140014780  lea     r14, [rbx+0B0h]
0x140014787  mov     r12d, dword ptr [rbp+70h+var_60+8]
0x14001478b  lea     rdx, aRrasWanarp; "RRAS WANARP"
0x140014792  mov     [rbx+0C0h], sil
0x140014799  lea     r8, qword_140009568
0x1400147a0  movups  xmm1, xmmword ptr cs:FWPM_CONDITION_IP_REMOTE_ADDRESS.Data1
0x1400147a7  movdqu  xmmword ptr [r14], xmm0
0x1400147ac  mov     [rbx+10h], ecx
0x1400147af  mov     dword ptr [rbx+18h], 101h
0x1400147b6  mov     [rbx+20h], r14
0x1400147ba  mov     [rbx+38h], ecx
0x1400147bd  mov     dword ptr [rbx+40h], 3
0x1400147c4  mov     [rbx+48h], r12d
0x1400147c8  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_INTERFACE_INDEX.Data1
0x1400147cf  movdqu  xmmword ptr [rbx], xmm1
0x1400147d3  movdqu  xmmword ptr [rbx+28h], xmm0
0x1400147d8  test    r13b, r13b
0x1400147db  jz      short loc_140014859
0x1400147dd  movups  xmm0, xmmword ptr cs:FWPM_LAYER_OUTBOUND_IPPACKET_V6.Data1
0x1400147e4  mov     [rsp+170h+filter.displayData.name], rdx
0x1400147e9  lea     r9, [rbx+50h]; id
0x1400147ed  mov     [rsp+170h+filter.flags], ecx
0x1400147f1  lea     rdx, [rsp+170h+filter]; filter
0x1400147f6  mov     rcx, cs:engineHandle; engineHandle
0x1400147fd  movdqu  xmmword ptr [rsp+170h+filter.layerKey.Data1], xmm0
0x140014803  mov     qword ptr [rbp+70h+filter.weight.8], r8
0x140014807  xor     r8d, r8d; sd
0x14001480a  movups  xmm0, cs:xmmword_140007658
0x140014811  mov     [rbp+70h+filter.weight.type], 4
0x140014818  mov     [rbp+70h+filter.numFilterConditions], 2
0x14001481f  movdqu  xmmword ptr [rbp+70h+filter.action.4], xmm0
0x140014824  mov     [rbp+70h+filter.filterCondition], rbx
0x140014828  mov     [rbp+70h+filter.action.type], 5003h
0x14001482f  mov     qword ptr [rbp+70h+filter.98h], r15
0x140014833  call    cs:__imp_FwpmFilterAdd0
0x14001483a  nop     dword ptr [rax+rax+00h]
0x14001483f  xor     ecx, ecx
0x140014841  mov     edi, eax
0x140014843  test    eax, eax
0x140014845  js      loc_140014929
0x14001484b  lea     rdx, aRrasWanarp; "RRAS WANARP"
0x140014852  lea     r8, qword_140009568
0x140014859  mov     [rbx+68h], ecx
0x14001485c  lea     rax, [rbx+58h]
0x140014860  mov     dword ptr [rbx+70h], 101h
0x140014867  mov     [rbx+78h], r14
0x14001486b  mov     [rbx+90h], ecx
0x140014871  mov     dword ptr [rbx+98h], 3
0x14001487b  mov     [rbx+0A0h], r12d
0x140014882  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_DESTINATION_ADDRESS.Data1
0x140014889  movdqu  xmmword ptr [rax], xmm0
0x14001488d  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_DESTINATION_INTERFACE_INDEX.Data1
0x140014894  movdqu  xmmword ptr [rbx+80h], xmm0
0x14001489c  test    r13b, r13b
0x14001489f  jz      loc_140014934
0x1400148a5  movups  xmm0, xmmword ptr cs:FWPM_LAYER_IPFORWARD_V6.Data1
0x1400148ac  mov     [rsp+170h+filter.displayData.name], rdx
0x1400148b1  lea     r9, [rbx+0A8h]; id
0x1400148b8  mov     [rsp+170h+filter.flags], ecx
0x1400148bc  lea     rdx, [rsp+170h+filter]; filter
0x1400148c1  mov     rcx, cs:engineHandle; engineHandle
0x1400148c8  movdqu  xmmword ptr [rsp+170h+filter.layerKey.Data1], xmm0
0x1400148ce  mov     qword ptr [rbp+70h+filter.weight.8], r8
0x1400148d2  xor     r8d, r8d; sd
0x1400148d5  movups  xmm0, cs:xmmword_140007678
0x1400148dc  mov     [rbp+70h+filter.weight.type], 4
0x1400148e3  mov     [rbp+70h+filter.numFilterConditions], 2
0x1400148ea  movdqu  xmmword ptr [rbp+70h+filter.action.4], xmm0
0x1400148ef  mov     [rbp+70h+filter.filterCondition], rax
0x1400148f3  mov     [rbp+70h+filter.action.type], 5003h
0x1400148fa  mov     qword ptr [rbp+70h+filter.98h], r15
0x1400148fe  call    cs:__imp_FwpmFilterAdd0
0x140014905  nop     dword ptr [rax+rax+00h]
0x14001490a  mov     edi, eax
0x14001490c  test    eax, eax
0x14001490e  jns     short loc_140014934
0x140014910  mov     rdx, [rbx+50h]; id
0x140014914  mov     rcx, cs:engineHandle; engineHandle
0x14001491b  call    cs:__imp_FwpmFilterDeleteById0
0x140014922  nop     dword ptr [rax+rax+00h]
0x140014927  xor     ecx, ecx
0x140014929  mov     [rbx+0A8h], rcx
0x140014930  mov     [rbx+50h], rcx
0x140014934  mov     eax, edi
0x140014936  mov     rcx, [rbp+70h+var_38]
0x14001493a  xor     rcx, rsp; StackCookie
0x14001493d  call    __security_check_cookie
0x140014942  mov     rbx, [rsp+170h+arg_0]
0x14001494a  add     rsp, 140h
0x140014951  pop     r15
0x140014953  pop     r14
0x140014955  pop     r13
0x140014957  pop     r12
0x140014959  pop     rdi
0x14001495a  pop     rsi
0x14001495b  pop     rbp
0x14001495c  retn
```
