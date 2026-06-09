# CLicensingStateTools::get_ServiceInformation(ushort *,long *)

- ea: `0x1800195d0`
- end: `0x1800196bf`
- name: `?get_ServiceInformation@CLicensingStateTools@@UEAAJPEAGPEAJ@Z`
- size: `239`
- prototype: `int(CLicensingStateTools *__hidden this, unsigned __int16 *, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x180003520`
- `0x180004288`
- `0x1800195d0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019686`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019686`
- `SLC!SLGetServiceInformation` at `0x18001964d`
- `SLC!SLGetServiceInformation` at `0x18001964d`
- `SLC!SLOpen` at `0x18001961f`
- `SLC!SLOpen` at `0x18001961f`
- `SLC!SLClose` at `0x1800196a3`
- `SLC!SLClose` at `0x1800196a3`

## pseudocode

```c
__int64 __fastcall CLicensingStateTools::get_ServiceInformation(
        CLicensingStateTools *this,
        unsigned __int16 *a2,
        int *a3)
{
  __int64 v5; // rcx
  unsigned int v6; // ebx
  HRESULT v7; // eax
  PBYTE ppbValue; // [rsp+30h] [rbp-10h] BYREF
  HSLC phSLC; // [rsp+38h] [rbp-8h] BYREF
  UINT pcbValue; // [rsp+68h] [rbp+28h] BYREF
  SLDATATYPE peDataType; // [rsp+78h] [rbp+38h] BYREF

  phSLC = 0;
  peDataType = SL_DATA_NONE;
  pcbValue = 0;
  ppbValue = 0;
  if ( !a2 || !a3 )
  {
    v5 = 2147942487LL;
    v6 = -2147024809;
LABEL_3:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
    goto LABEL_11;
  }
  v7 = SLOpen(&phSLC);
  v6 = v7;
  if ( v7 < 0 || (v7 = SLGetServiceInformation(phSLC, a2, &peDataType, &pcbValue, &ppbValue), v6 = v7, v7 < 0) )
  {
    v5 = (unsigned int)v7;
    goto LABEL_3;
  }
  if ( pcbValue != 4 )
  {
    v6 = -2147418113;
    v5 = 2147549183LL;
    goto LABEL_3;
  }
  *a3 = *(_DWORD *)ppbValue;
LABEL_11:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  if ( ppbValue )
  {
    LocalFree(ppbValue);
    ppbValue = 0;
  }
  if ( phSLC )
    SLClose(phSLC);
  return v6;
}

```

## disassembly

```asm
0x1800195d0  mov     [rsp-18h+arg_0], rbx
0x1800195d5  push    rbp
0x1800195d6  push    rsi
0x1800195d7  push    rdi
0x1800195d8  mov     rbp, rsp
0x1800195db  sub     rsp, 40h
0x1800195df  mov     [rbp+phSLC], 0
0x1800195e7  mov     rdi, r8
0x1800195ea  mov     [rbp+peDataType], 0
0x1800195f1  mov     rsi, rdx
0x1800195f4  mov     [rbp+pcbValue], 0
0x1800195fb  mov     [rbp+var_10], 0
0x180019603  test    rdx, rdx
0x180019606  jnz     short loc_180019616
0x180019608  mov     ecx, 80070057h
0x18001960d  mov     ebx, ecx
0x18001960f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180019614  jmp     short loc_180019676
0x180019616  test    rdi, rdi
0x180019619  jz      short loc_180019608
0x18001961b  lea     rcx, [rbp+phSLC]; phSLC
0x18001961f  call    cs:__imp_SLOpen
0x180019626  nop     dword ptr [rax+rax+00h]
0x18001962b  mov     ebx, eax
0x18001962d  test    eax, eax
0x18001962f  jns     short loc_180019635
0x180019631  mov     ecx, eax
0x180019633  jmp     short loc_18001960F
0x180019635  mov     rcx, [rbp+phSLC]; hSLC
0x180019639  lea     rax, [rbp+var_10]
0x18001963d  lea     r9, [rbp+pcbValue]; pcbValue
0x180019641  mov     [rsp+40h+ppbValue], rax; ppbValue
0x180019646  lea     r8, [rbp+peDataType]; peDataType
0x18001964a  mov     rdx, rsi; pwszValueName
0x18001964d  call    cs:__imp_SLGetServiceInformation
0x180019654  nop     dword ptr [rax+rax+00h]
0x180019659  mov     ebx, eax
0x18001965b  test    eax, eax
0x18001965d  js      short loc_180019631
0x18001965f  cmp     [rbp+pcbValue], 4
0x180019663  jz      short loc_18001966E
0x180019665  mov     ebx, 8000FFFFh
0x18001966a  mov     ecx, ebx
0x18001966c  jmp     short loc_18001960F
0x18001966e  mov     rax, [rbp+var_10]
0x180019672  mov     ecx, [rax]
0x180019674  mov     [rdi], ecx
0x180019676  mov     ecx, ebx
0x180019678  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001967d  mov     rcx, [rbp+var_10]; hMem
0x180019681  test    rcx, rcx
0x180019684  jz      short loc_18001969A
0x180019686  call    cs:__imp_LocalFree
0x18001968d  nop     dword ptr [rax+rax+00h]
0x180019692  mov     [rbp+var_10], 0
0x18001969a  mov     rcx, [rbp+phSLC]; hSLC
0x18001969e  test    rcx, rcx
0x1800196a1  jz      short loc_1800196AF
0x1800196a3  call    cs:__imp_SLClose
0x1800196aa  nop     dword ptr [rax+rax+00h]
0x1800196af  mov     eax, ebx
0x1800196b1  mov     rbx, [rsp+40h+arg_0]
0x1800196b6  add     rsp, 40h
0x1800196ba  pop     rdi
0x1800196bb  pop     rsi
0x1800196bc  pop     rbp
0x1800196bd  retn
```
