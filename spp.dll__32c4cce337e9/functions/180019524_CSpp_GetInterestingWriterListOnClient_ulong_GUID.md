# CSpp::_GetInterestingWriterListOnClient(ulong *,_GUID * *)

- ea: `0x180019524`
- end: `0x180019777`
- name: `?_GetInterestingWriterListOnClient@CSpp@@AEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `595`
- prototype: `__int64 __fastcall(CSpp *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x180016e24`

## callees

- `0x1800041d4`
- `0x18000702c`
- `0x18000e040`
- `0x180018cb0`
- `0x180019524`
- `0x18001b70c`
- `0x180020710`
- `0x180020738`
- `0x1800211a4`
- `0x1800268b4`
- `0x1800269ac`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019747`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019747`

## string_xrefs

- `0x180019577`: `CSpp::_GetInterestingWriterListOnClient`

## pseudocode

```c
__int64 __fastcall CSpp::_GetInterestingWriterListOnClient(CSpp *this, unsigned int *a2, struct _GUID **a3)
{
  CSpp *v5; // rcx
  __int64 v6; // rbx
  __int16 v7; // ax
  CSpp *v8; // rcx
  int DisabledEnabledWritersList; // eax
  __int16 v10; // ax
  int v11; // eax
  __int64 v12; // r8
  bool v13; // sf
  __int16 v14; // r12
  unsigned int i; // edi
  unsigned int v16; // edi
  struct _GUID *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // r8
  unsigned int v20; // edi
  __int128 v22; // [rsp+20h] [rbp-50h] BYREF
  int IsServerSku; // [rsp+30h] [rbp-40h] BYREF
  __int16 v24; // [rsp+34h] [rbp-3Ch]
  __int16 v25; // [rsp+36h] [rbp-3Ah]
  CSpp *v26; // [rsp+B0h] [rbp+40h] BYREF
  LPVOID pv; // [rsp+B8h] [rbp+48h] BYREF
  __int64 v28; // [rsp+C8h] [rbp+58h] BYREF

  v26 = this;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&IsServerSku,
    "CSpp::_GetInterestingWriterListOnClient",
    4299,
    1);
  v6 = 0;
  pv = 0;
  LODWORD(v26) = 0;
  v7 = 4306;
  v28 = 0;
  if ( a2 && (v24 = 4306, v7 = 4307, a3) )
  {
    IsServerSku = 0;
    v24 = 4307;
    *a2 = 0;
    *a3 = 0;
    IsServerSku = CSpp::_IsServerSku(v5);
    v7 = 4312;
    if ( IsServerSku >= 0 )
    {
      v24 = 4312;
      DisabledEnabledWritersList = CSpp::_GetDisabledEnabledWritersList(
                                     v8,
                                     0,
                                     (unsigned int *)&v26,
                                     (struct _GUID **)&pv);
      IsServerSku = DisabledEnabledWritersList;
      if ( DisabledEnabledWritersList < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0 )
          WPP_SF_D(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            56,
            &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids,
            (unsigned int)DisabledEnabledWritersList);
        IsServerSku = 0;
        v10 = 4321;
LABEL_12:
        v24 = v10;
        goto LABEL_29;
      }
      v11 = CSxArrayBuilder<unsigned short *,&void Free_String(unsigned short * *),&void SxDefaultInit<unsigned short *>(unsigned short * *),&void SxDefaultTransfer<unsigned short *>(unsigned short * *,unsigned short * *)>::CreateInstance(&v28);
      v6 = v28;
      v13 = v11 < 0;
      IsServerSku = v11;
      v7 = 4324;
      if ( !v13 )
      {
        v24 = 4324;
        v14 = 4328;
        for ( i = 0; i < 7; ++i )
        {
          v22 = xmmword_18003BAD0[i];
          IsServerSku = CSxSimpleArray<_GUID>::Append(v6, &v22);
          if ( IsServerSku < 0 )
          {
LABEL_18:
            v25 = v14;
            goto LABEL_29;
          }
          v24 = 4328;
        }
        v16 = 0;
        v14 = 4335;
        while ( v16 < (unsigned int)v26 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
            WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, v12, (char *)pv + 16 * v16);
          v22 = *((_OWORD *)pv + v16);
          IsServerSku = CSxSimpleArray<_GUID>::Append(v6, &v22);
          if ( IsServerSku < 0 )
            goto LABEL_18;
          v24 = 4335;
          ++v16;
        }
        *a2 = *(_DWORD *)(v6 + 16);
        v17 = *(struct _GUID **)(v6 + 8);
        *(_QWORD *)(v6 + 8) = 0;
        *(_QWORD *)(v6 + 16) = 0;
        *a3 = v17;
        v10 = 4341;
        IsServerSku = 0;
        goto LABEL_12;
      }
    }
  }
  else
  {
    IsServerSku = -2147024809;
  }
  v25 = v7;
LABEL_29:
  CoTaskMemFree(pv);
  v20 = IsServerSku;
  if ( v6 )
    CSxSimpleArray<_GUID>::Release((void *)v6);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&IsServerSku, v18, v19);
  return v20;
}

```

## disassembly

```asm
0x180019524  mov     [rsp-38h+arg_0], rcx
0x180019529  push    rbp
0x18001952a  push    rbx
0x18001952b  push    rsi
0x18001952c  push    rdi
0x18001952d  push    r12
0x18001952f  push    r13
0x180019531  push    r14
0x180019533  mov     rbp, rsp
0x180019536  sub     rsp, 70h
0x18001953a  mov     rsi, r8
0x18001953d  mov     r14, rdx
0x180019540  mov     rcx, cs:WPP_GLOBAL_Control
0x180019547  lea     r13, WPP_GLOBAL_Control
0x18001954e  cmp     rcx, r13
0x180019551  jz      short loc_180019571
0x180019553  test    dword ptr [rcx+1Ch], 20000000h
0x18001955a  jz      short loc_180019571
0x18001955c  mov     rcx, [rcx+10h]
0x180019560  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x180019567  mov     edx, 37h ; '7'
0x18001956c  call    WPP_SF_
0x180019571  mov     r9d, 1; unsigned __int16
0x180019577  lea     rdx, aCsppGetinteres; "CSpp::_GetInterestingWriterListOnClient"
0x18001957e  mov     r8d, 10CBh; unsigned __int16
0x180019584  lea     rcx, [rbp+var_40]; this
0x180019588  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001958d  xor     ebx, ebx
0x18001958f  mov     [rbp+pv], 0
0x180019597  mov     dword ptr [rbp+arg_0], 0
0x18001959e  mov     eax, 10D2h
0x1800195a3  mov     [rbp+arg_18], rbx
0x1800195a7  test    r14, r14
0x1800195aa  jz      loc_180019738
0x1800195b0  mov     [rbp+var_3C], ax
0x1800195b4  mov     eax, 10D3h
0x1800195b9  test    rsi, rsi
0x1800195bc  jz      loc_180019738
0x1800195c2  mov     [rbp+var_40], ebx
0x1800195c5  mov     [rbp+var_3C], ax
0x1800195c9  mov     [r14], ebx
0x1800195cc  mov     [rsi], rbx
0x1800195cf  call    ?_IsServerSku@CSpp@@AEAAJXZ; CSpp::_IsServerSku(void)
0x1800195d4  mov     [rbp+var_40], eax
0x1800195d7  test    eax, eax
0x1800195d9  mov     eax, 10D8h
0x1800195de  js      loc_18001973F
0x1800195e4  lea     r9, [rbp+pv]; struct _GUID **
0x1800195e8  mov     [rbp+var_3C], ax
0x1800195ec  lea     r8, [rbp+arg_0]; unsigned int *
0x1800195f0  xor     edx, edx; int
0x1800195f2  call    ?_GetDisabledEnabledWritersList@CSpp@@AEAAJHPEAKPEAPEAU_GUID@@@Z; CSpp::_GetDisabledEnabledWritersList(int,ulong *,_GUID * *)
0x1800195f7  mov     [rbp+var_40], eax
0x1800195fa  test    eax, eax
0x1800195fc  jns     short loc_18001963A
0x1800195fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180019605  cmp     rcx, r13
0x180019608  jz      short loc_180019629
0x18001960a  test    dword ptr [rcx+1Ch], 4000000h
0x180019611  jz      short loc_180019629
0x180019613  mov     rcx, [rcx+10h]
0x180019617  lea     edx, [rbx+38h]
0x18001961a  mov     r9d, eax
0x18001961d  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x180019624  call    WPP_SF_D
0x180019629  mov     [rbp+var_40], ebx
0x18001962c  mov     eax, 10E1h
0x180019631  mov     [rbp+var_3C], ax
0x180019635  jmp     loc_180019743
0x18001963a  lea     rcx, [rbp+arg_18]
0x18001963e  call    ?CreateInstance@?$CSxArrayBuilder@PEAG$1?Free_String@@YAXPEAPEAG@Z$1??$SxDefaultInit@PEAG@@YAX0@Z$1??$SxDefaultTransfer@PEAG@@YAX00@Z@@SAJPEAPEAV1@@Z; CSxArrayBuilder<ushort *,&Free_String(ushort * *),&SxDefaultInit<ushort *>(ushort * *),&SxDefaultTransfer<ushort *>(ushort * *,ushort * *)>::CreateInstance(CSxArrayBuilder<ushort *,&Free_String(ushort * *),&SxDefaultInit<ushort *>(ushort * *),&SxDefaultTransfer<ushort *>(ushort * *,ushort * *)> * *)
0x180019643  mov     rbx, [rbp+arg_18]
0x180019647  test    eax, eax
0x180019649  mov     [rbp+var_40], eax
0x18001964c  mov     eax, 10E4h
0x180019651  js      loc_18001973F
0x180019657  mov     [rbp+var_3C], ax
0x18001965b  lea     r12d, [rax+4]
0x18001965f  xor     edi, edi
0x180019661  cmp     edi, 7
0x180019664  jnb     short loc_1800196A1
0x180019666  lea     rcx, xmmword_18003BAD0
0x18001966d  mov     eax, edi
0x18001966f  add     rax, rax
0x180019672  lea     rdx, [rbp+var_50]
0x180019676  movups  xmm0, xmmword ptr [rcx+rax*8]
0x18001967a  mov     rcx, rbx
0x18001967d  movdqu  [rbp+var_50], xmm0
0x180019682  call    ?Append@?$CSxSimpleArray@U_GUID@@@@QEAAJU_GUID@@@Z; CSxSimpleArray<_GUID>::Append(_GUID)
0x180019687  mov     [rbp+var_40], eax
0x18001968a  test    eax, eax
0x18001968c  js      short loc_180019697
0x18001968e  mov     [rbp+var_3C], r12w
0x180019693  inc     edi
0x180019695  jmp     short loc_180019661
0x180019697  mov     [rbp+var_3A], r12w
0x18001969c  jmp     loc_180019743
0x1800196a1  xor     edi, edi
0x1800196a3  mov     r12d, 10EFh
0x1800196a9  cmp     edi, dword ptr [rbp+arg_0]
0x1800196ac  jnb     short loc_18001970A
0x1800196ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800196b5  cmp     rcx, r13
0x1800196b8  jz      short loc_1800196DC
0x1800196ba  test    dword ptr [rcx+1Ch], 8000000h
0x1800196c1  jz      short loc_1800196DC
0x1800196c3  mov     rcx, [rcx+10h]
0x1800196c7  mov     edx, 39h ; '9'
0x1800196cc  mov     r9d, edi
0x1800196cf  shl     r9, 4
0x1800196d3  add     r9, [rbp+pv]
0x1800196d7  call    WPP_SF__guid_
0x1800196dc  mov     rax, [rbp+pv]
0x1800196e0  lea     rdx, [rbp+var_50]
0x1800196e4  mov     ecx, edi
0x1800196e6  add     rcx, rcx
0x1800196e9  movups  xmm0, xmmword ptr [rax+rcx*8]
0x1800196ed  mov     rcx, rbx
0x1800196f0  movdqu  [rbp+var_50], xmm0
0x1800196f5  call    ?Append@?$CSxSimpleArray@U_GUID@@@@QEAAJU_GUID@@@Z; CSxSimpleArray<_GUID>::Append(_GUID)
0x1800196fa  mov     [rbp+var_40], eax
0x1800196fd  test    eax, eax
0x1800196ff  js      short loc_180019697
0x180019701  mov     [rbp+var_3C], r12w
0x180019706  inc     edi
0x180019708  jmp     short loc_1800196A9
0x18001970a  mov     eax, [rbx+10h]
0x18001970d  mov     [r14], eax
0x180019710  mov     rax, [rbx+8]
0x180019714  mov     qword ptr [rbx+8], 0
0x18001971c  mov     qword ptr [rbx+10h], 0
0x180019724  mov     [rsi], rax
0x180019727  mov     eax, 10F5h
0x18001972c  mov     [rbp+var_40], 0
0x180019733  jmp     loc_180019631
0x180019738  mov     [rbp+var_40], 80070057h
0x18001973f  mov     [rbp+var_3A], ax
0x180019743  mov     rcx, [rbp+pv]; pv
0x180019747  call    cs:__imp_CoTaskMemFree
0x18001974d  mov     edi, [rbp+var_40]
0x180019750  test    rbx, rbx
0x180019753  jz      short loc_18001975D
0x180019755  mov     rcx, rbx; Block
0x180019758  call    ?Release@?$CSxSimpleArray@U_GUID@@@@QEAAKXZ; CSxSimpleArray<_GUID>::Release(void)
0x18001975d  lea     rcx, [rbp+var_40]; this
0x180019761  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180019766  mov     eax, edi
0x180019768  add     rsp, 70h
0x18001976c  pop     r14
0x18001976e  pop     r13
0x180019770  pop     r12
0x180019772  pop     rdi
0x180019773  pop     rsi
0x180019774  pop     rbx
0x180019775  pop     rbp
0x180019776  retn
```
