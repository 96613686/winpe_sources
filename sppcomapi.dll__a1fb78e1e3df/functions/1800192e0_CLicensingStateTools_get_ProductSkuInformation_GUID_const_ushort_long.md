# CLicensingStateTools::get_ProductSkuInformation(_GUID const *,ushort *,long *)

- ea: `0x1800192e0`
- end: `0x1800193ed`
- name: `?get_ProductSkuInformation@CLicensingStateTools@@UEAAJPEBU_GUID@@PEAGPEAJ@Z`
- size: `269`
- prototype: `int(CLicensingStateTools *__hidden this, const struct _GUID *, unsigned __int16 *, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180003520`
- `0x180004288`
- `0x1800192e0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800193ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800193ac`
- `SLC!SLGetProductSkuInformation` at `0x180019373`
- `SLC!SLGetProductSkuInformation` at `0x180019373`
- `SLC!SLOpen` at `0x18001933d`
- `SLC!SLOpen` at `0x18001933d`
- `SLC!SLClose` at `0x1800193c9`
- `SLC!SLClose` at `0x1800193c9`

## pseudocode

```c
__int64 __fastcall CLicensingStateTools::get_ProductSkuInformation(
        CLicensingStateTools *this,
        const struct _GUID *a2,
        unsigned __int16 *a3,
        int *a4)
{
  __int64 v7; // rcx
  unsigned int v8; // ebx
  HRESULT v9; // eax
  SLDATATYPE peDataType; // [rsp+30h] [rbp-20h] BYREF
  PBYTE ppbValue; // [rsp+38h] [rbp-18h] BYREF
  HSLC phSLC; // [rsp+40h] [rbp-10h] BYREF
  UINT pcbValue; // [rsp+78h] [rbp+28h] BYREF

  phSLC = 0;
  peDataType = SL_DATA_NONE;
  pcbValue = 0;
  ppbValue = 0;
  if ( !a2 || !a3 || !a4 )
  {
    v7 = 2147942487LL;
    v8 = -2147024809;
LABEL_3:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
    goto LABEL_12;
  }
  v9 = SLOpen(&phSLC);
  v8 = v9;
  if ( v9 < 0 || (v9 = SLGetProductSkuInformation(phSLC, a2, a3, &peDataType, &pcbValue, &ppbValue), v8 = v9, v9 < 0) )
  {
    v7 = (unsigned int)v9;
    goto LABEL_3;
  }
  if ( pcbValue != 4 )
  {
    v8 = -2147418113;
    v7 = 2147549183LL;
    goto LABEL_3;
  }
  *a4 = *(_DWORD *)ppbValue;
LABEL_12:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v8);
  if ( ppbValue )
  {
    LocalFree(ppbValue);
    ppbValue = 0;
  }
  if ( phSLC )
    SLClose(phSLC);
  return v8;
}

```

## disassembly

```asm
0x1800192e0  mov     [rsp-18h+arg_0], rbx
0x1800192e5  mov     [rsp-18h+arg_10], rsi
0x1800192ea  push    rbp
0x1800192eb  push    rdi
0x1800192ec  push    r14
0x1800192ee  mov     rbp, rsp
0x1800192f1  sub     rsp, 50h
0x1800192f5  mov     [rbp+phSLC], 0
0x1800192fd  mov     rdi, r9
0x180019300  mov     [rbp+peDataType], 0
0x180019307  mov     rsi, r8
0x18001930a  mov     [rbp+arg_8], 0
0x180019311  mov     r14, rdx
0x180019314  mov     [rbp+var_18], 0
0x18001931c  test    rdx, rdx
0x18001931f  jnz     short loc_18001932F
0x180019321  mov     ecx, 80070057h
0x180019326  mov     ebx, ecx
0x180019328  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001932d  jmp     short loc_18001939C
0x18001932f  test    rsi, rsi
0x180019332  jz      short loc_180019321
0x180019334  test    rdi, rdi
0x180019337  jz      short loc_180019321
0x180019339  lea     rcx, [rbp+phSLC]; phSLC
0x18001933d  call    cs:__imp_SLOpen
0x180019344  nop     dword ptr [rax+rax+00h]
0x180019349  mov     ebx, eax
0x18001934b  test    eax, eax
0x18001934d  jns     short loc_180019353
0x18001934f  mov     ecx, eax
0x180019351  jmp     short loc_180019328
0x180019353  mov     rcx, [rbp+phSLC]; hSLC
0x180019357  lea     rax, [rbp+var_18]
0x18001935b  mov     [rsp+50h+ppbValue], rax; ppbValue
0x180019360  lea     r9, [rbp+peDataType]; peDataType
0x180019364  lea     rax, [rbp+arg_8]
0x180019368  mov     r8, rsi; pwszValueName
0x18001936b  mov     rdx, r14; pProductSkuId
0x18001936e  mov     [rsp+50h+pcbValue], rax; pcbValue
0x180019373  call    cs:__imp_SLGetProductSkuInformation
0x18001937a  nop     dword ptr [rax+rax+00h]
0x18001937f  mov     ebx, eax
0x180019381  test    eax, eax
0x180019383  js      short loc_18001934F
0x180019385  cmp     [rbp+arg_8], 4
0x180019389  jz      short loc_180019394
0x18001938b  mov     ebx, 8000FFFFh
0x180019390  mov     ecx, ebx
0x180019392  jmp     short loc_180019328
0x180019394  mov     rax, [rbp+var_18]
0x180019398  mov     ecx, [rax]
0x18001939a  mov     [rdi], ecx
0x18001939c  mov     ecx, ebx
0x18001939e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800193a3  mov     rcx, [rbp+var_18]; hMem
0x1800193a7  test    rcx, rcx
0x1800193aa  jz      short loc_1800193C0
0x1800193ac  call    cs:__imp_LocalFree
0x1800193b3  nop     dword ptr [rax+rax+00h]
0x1800193b8  mov     [rbp+var_18], 0
0x1800193c0  mov     rcx, [rbp+phSLC]; hSLC
0x1800193c4  test    rcx, rcx
0x1800193c7  jz      short loc_1800193D5
0x1800193c9  call    cs:__imp_SLClose
0x1800193d0  nop     dword ptr [rax+rax+00h]
0x1800193d5  lea     r11, [rsp+50h+var_s0]
0x1800193da  mov     eax, ebx
0x1800193dc  mov     rbx, [r11+20h]
0x1800193e0  mov     rsi, [r11+30h]
0x1800193e4  mov     rsp, r11
0x1800193e7  pop     r14
0x1800193e9  pop     rdi
0x1800193ea  pop     rbp
0x1800193eb  retn
```
