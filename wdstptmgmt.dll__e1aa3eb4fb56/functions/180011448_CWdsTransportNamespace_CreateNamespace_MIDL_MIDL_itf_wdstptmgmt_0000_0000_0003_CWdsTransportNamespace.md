# CWdsTransportNamespace::CreateNamespace(__MIDL___MIDL_itf_wdstptmgmt_0000_0000_0003,CWdsTransportNamespace * *)

- ea: `0x180011448`
- end: `0x180011573`
- name: `?CreateNamespace@CWdsTransportNamespace@@CAJW4__MIDL___MIDL_itf_wdstptmgmt_0000_0000_0003@@PEAPEAV1@@Z`
- size: `299`
- prototype: `__int64 __fastcall(enum __MIDL___MIDL_itf_wdstptmgmt_0000_0000_0003, struct CWdsTransportNamespace **)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001157c`
- `0x18001170c`

## callees

- `0x180011128`
- `0x180011220`
- `0x180011344`
- `0x180011448`
- `0x1800137c4`

## import_xrefs

- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18001147f`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180011532`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180011554`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18001147f`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180011532`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180011554`

## string_xrefs

- `0x18001145d`: `-> CWdsTransportNamespace::CreateNamespace`
- `0x180011541`: `<- CWdsTransportNamespace::CreateNamespace=%x`

## pseudocode

```c
__int64 __fastcall CWdsTransportNamespace::CreateNamespace(unsigned int a1, struct CWdsTransportNamespace **a2)
{
  __int64 v4; // rbx
  __int64 v5; // rdx
  __int64 v6; // r8
  struct CWdsTransportNamespace *v7; // rax
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // r8
  struct CWdsTransportNamespace *v13; // [rsp+20h] [rbp-18h] BYREF
  struct CWdsTransportNamespace *v14; // [rsp+50h] [rbp+18h] BYREF
  struct CWdsTransportNamespace *v15; // [rsp+58h] [rbp+20h] BYREF

  v13 = 0;
  v15 = 0;
  v14 = 0;
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"-> CWdsTransportNamespace::CreateNamespace");
  if ( !a1 )
    goto LABEL_12;
  if ( a1 == 1 )
  {
    v4 = (unsigned int)ATL::CComObject<CWdsTransportNamespaceAutoCast>::CreateInstance(&v13);
    if ( (int)ElValidateHr_7(v4, v10, v11, 86) >= 0 )
    {
      v7 = v13;
      goto LABEL_11;
    }
    goto LABEL_13;
  }
  if ( a1 != 2 )
  {
    if ( a1 == 3 )
    {
      v4 = (unsigned int)ATL::CComObject<CWdsTransportNamespaceScheduledCastAutoStart>::CreateInstance(&v14);
      if ( (int)ElValidateHr_7(v4, v5, v6, 102) >= 0 )
      {
        v7 = v14;
LABEL_11:
        *a2 = v7;
        goto LABEL_13;
      }
      goto LABEL_13;
    }
LABEL_12:
    LODWORD(v4) = -2147024809;
    CTrace::Trace((CTrace *)qword_18003B770, 0x80000u, L"Encountered an invalid namespace type: %u.\n", a1);
    goto LABEL_13;
  }
  v4 = (unsigned int)ATL::CComObject<CWdsTransportNamespaceScheduledCastManualStart>::CreateInstance(&v15);
  if ( (int)ElValidateHr_7(v4, v8, v9, 94) >= 0 )
  {
    v7 = v15;
    goto LABEL_11;
  }
LABEL_13:
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"<- CWdsTransportNamespace::CreateNamespace=%x", (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180011448  mov     rax, rsp
0x18001144b  mov     [rax+8], rbx
0x18001144f  mov     [rax+10h], rsi
0x180011453  push    rdi
0x180011454  sub     rsp, 30h
0x180011458  and     qword ptr [rax-18h], 0
0x18001145d  lea     r8, aCwdstransportn_74; "-> CWdsTransportNamespace::CreateNamesp"...
0x180011464  and     qword ptr [rax+20h], 0
0x180011469  mov     rsi, rdx
0x18001146c  and     qword ptr [rax+18h], 0
0x180011471  mov     edi, ecx
0x180011473  mov     edx, 10000h
0x180011478  lea     rcx, qword_18003B770
0x18001147f  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180011486  nop     dword ptr [rax+rax+00h]
0x18001148b  mov     r8d, edi
0x18001148e  test    edi, edi
0x180011490  jz      loc_180011517
0x180011496  sub     r8d, 1
0x18001149a  jz      short loc_1800114F0
0x18001149c  sub     r8d, 1
0x1800114a0  jz      short loc_1800114CC
0x1800114a2  cmp     r8d, 1
0x1800114a6  jnz     short loc_180011517
0x1800114a8  lea     rcx, [rsp+38h+arg_10]
0x1800114ad  call    ?CreateInstance@?$CComObject@VCWdsTransportNamespaceScheduledCastAutoStart@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CWdsTransportNamespaceScheduledCastAutoStart>::CreateInstance(ATL::CComObject<CWdsTransportNamespaceScheduledCastAutoStart> * *)
0x1800114b2  mov     r9d, 66h ; 'f'
0x1800114b8  mov     ecx, eax
0x1800114ba  mov     ebx, eax
0x1800114bc  call    ElValidateHr_7
0x1800114c1  test    eax, eax
0x1800114c3  js      short loc_18001153E
0x1800114c5  mov     rax, [rsp+38h+arg_10]
0x1800114ca  jmp     short loc_180011512
0x1800114cc  lea     rcx, [rsp+38h+arg_18]
0x1800114d1  call    ?CreateInstance@?$CComObject@VCWdsTransportNamespaceScheduledCastManualStart@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CWdsTransportNamespaceScheduledCastManualStart>::CreateInstance(ATL::CComObject<CWdsTransportNamespaceScheduledCastManualStart> * *)
0x1800114d6  mov     r9d, 5Eh ; '^'
0x1800114dc  mov     ecx, eax
0x1800114de  mov     ebx, eax
0x1800114e0  call    ElValidateHr_7
0x1800114e5  test    eax, eax
0x1800114e7  js      short loc_18001153E
0x1800114e9  mov     rax, [rsp+38h+arg_18]
0x1800114ee  jmp     short loc_180011512
0x1800114f0  lea     rcx, [rsp+38h+var_18]
0x1800114f5  call    ?CreateInstance@?$CComObject@VCWdsTransportNamespaceAutoCast@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CWdsTransportNamespaceAutoCast>::CreateInstance(ATL::CComObject<CWdsTransportNamespaceAutoCast> * *)
0x1800114fa  mov     r9d, 56h ; 'V'
0x180011500  mov     ecx, eax
0x180011502  mov     ebx, eax
0x180011504  call    ElValidateHr_7
0x180011509  test    eax, eax
0x18001150b  js      short loc_18001153E
0x18001150d  mov     rax, [rsp+38h+var_18]
0x180011512  mov     [rsi], rax
0x180011515  jmp     short loc_18001153E
0x180011517  mov     r9d, edi
0x18001151a  lea     r8, aEncounteredAnI_2; "Encountered an invalid namespace type: "...
0x180011521  mov     edx, 80000h
0x180011526  lea     rcx, qword_18003B770
0x18001152d  mov     ebx, 80070057h
0x180011532  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180011539  nop     dword ptr [rax+rax+00h]
0x18001153e  mov     r9d, ebx
0x180011541  lea     r8, aCwdstransportn_53; "<- CWdsTransportNamespace::CreateNamesp"...
0x180011548  mov     edx, 10000h
0x18001154d  lea     rcx, qword_18003B770
0x180011554  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18001155b  nop     dword ptr [rax+rax+00h]
0x180011560  mov     rsi, [rsp+38h+arg_8]
0x180011565  mov     eax, ebx
0x180011567  mov     rbx, [rsp+38h+arg_0]
0x18001156c  add     rsp, 30h
0x180011570  pop     rdi
0x180011571  retn
```
