# CUPnPEventingManager::OnStateChangedSafe(tagVARIANT)

- ea: `0x180045790`
- end: `0x1800458f5`
- name: `?OnStateChangedSafe@CUPnPEventingManager@@UEAAJUtagVARIANT@@@Z`
- size: `357`
- prototype: `__int64 __fastcall(CUPnPEventingManager *__hidden this, struct tagVARIANT *__struct_ptr)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000db4c`
- `0x180013180`
- `0x180045790`
- `0x180055010`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18004582a`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18004582a`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180045856`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180045856`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18004583f`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18004583f`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180045868`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180045868`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180045890`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180045890`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1800457fe`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1800457fe`

## pseudocode

```c
__int64 __fastcall CUPnPEventingManager::OnStateChangedSafe(CUPnPEventingManager *this, struct tagVARIANT *a2)
{
  HRESULT IsAllowedCOMCallLocality; // ebx
  SAFEARRAY *parray; // rdi
  int v7; // ecx
  LONG plUbound; // [rsp+30h] [rbp-18h] BYREF
  void *ppvData; // [rsp+38h] [rbp-10h] BYREF
  VARTYPE pvt; // [rsp+60h] [rbp+18h] BYREF
  LONG plLbound; // [rsp+68h] [rbp+20h] BYREF

  ppvData = 0;
  plLbound = 0;
  plUbound = 0;
  pvt = 0;
  IsAllowedCOMCallLocality = HrIsAllowedCOMCallLocality(1);
  if ( IsAllowedCOMCallLocality >= 0 )
  {
    if ( (a2->vt & 0x2000) == 0 )
      return 2147942487LL;
    parray = a2->parray;
    if ( !parray )
      return 2147942487LL;
    if ( SafeArrayGetVartype(parray, &pvt) < 0 )
      return 2147942487LL;
    if ( pvt > 0x17u )
      return 2147942487LL;
    v7 = 13107208;
    if ( !_bittest(&v7, pvt)
      || SafeArrayGetDim(parray) != 1
      || SafeArrayGetLBound(parray, 1u, &plLbound) < 0
      || SafeArrayGetUBound(parray, 1u, &plUbound) < 0 )
    {
      return 2147942487LL;
    }
    IsAllowedCOMCallLocality = SafeArrayAccessData(parray, &ppvData);
    if ( IsAllowedCOMCallLocality >= 0 )
    {
      IsAllowedCOMCallLocality = (*(__int64 (__fastcall **)(CUPnPEventingManager *, _QWORD, void *))(*(_QWORD *)this + 24LL))(
                                   this,
                                   parray->rgsabound[0].cElements,
                                   ppvData);
      SafeArrayUnaccessData(parray);
    }
  }
  if ( IsAllowedCOMCallLocality
    && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      (unsigned int)WPP_26899187c1a539900c7f96418485818e_Traceguids,
      (unsigned int)"CUPnPEventingManager::OnStateChangedSafe",
      IsAllowedCOMCallLocality);
  }
  return (unsigned int)IsAllowedCOMCallLocality;
}

```

## disassembly

```asm
0x180045790  mov     rax, rsp
0x180045793  mov     [rax+8], rbx
0x180045797  mov     [rax+10h], rsi
0x18004579b  push    rdi
0x18004579c  sub     rsp, 40h
0x1800457a0  mov     rdi, rdx
0x1800457a3  mov     rsi, rcx
0x1800457a6  mov     qword ptr [rax-10h], 0
0x1800457ae  mov     dword ptr [rax+20h], 0
0x1800457b5  mov     dword ptr [rax-18h], 0
0x1800457bc  xor     eax, eax
0x1800457be  mov     [rsp+48h+pvt], ax
0x1800457c3  lea     ecx, [rax+1]
0x1800457c6  call    ?HrIsAllowedCOMCallLocality@@YAJW4CALL_LOCALITY@@@Z; HrIsAllowedCOMCallLocality(CALL_LOCALITY)
0x1800457cb  mov     ebx, eax
0x1800457cd  test    eax, eax
0x1800457cf  js      loc_1800458A6
0x1800457d5  mov     eax, 2000h
0x1800457da  test    [rdi], ax
0x1800457dd  jnz     short loc_1800457E9
0x1800457df  mov     eax, 80070057h
0x1800457e4  jmp     loc_1800458E5
0x1800457e9  mov     rdi, [rdi+8]
0x1800457ed  test    rdi, rdi
0x1800457f0  jz      loc_180045898
0x1800457f6  lea     rdx, [rsp+48h+pvt]; pvt
0x1800457fb  mov     rcx, rdi; psa
0x1800457fe  call    cs:__imp_SafeArrayGetVartype
0x180045804  test    eax, eax
0x180045806  js      loc_180045898
0x18004580c  cmp     [rsp+48h+pvt], 17h
0x180045812  ja      loc_180045898
0x180045818  movzx   eax, [rsp+48h+pvt]
0x18004581d  mov     ecx, 0C80008h
0x180045822  bt      ecx, eax
0x180045825  jnb     short loc_180045898
0x180045827  mov     rcx, rdi; psa
0x18004582a  call    cs:__imp_SafeArrayGetDim
0x180045830  cmp     eax, 1
0x180045833  jnz     short loc_180045898
0x180045835  lea     r8, [rsp+48h+plLbound]; plLbound
0x18004583a  mov     edx, eax; nDim
0x18004583c  mov     rcx, rdi; psa
0x18004583f  call    cs:__imp_SafeArrayGetLBound
0x180045845  test    eax, eax
0x180045847  js      short loc_180045898
0x180045849  lea     r8, [rsp+48h+plUbound]; plUbound
0x18004584e  mov     edx, 1; nDim
0x180045853  mov     rcx, rdi; psa
0x180045856  call    cs:__imp_SafeArrayGetUBound
0x18004585c  test    eax, eax
0x18004585e  js      short loc_180045898
0x180045860  lea     rdx, [rsp+48h+ppvData]; ppvData
0x180045865  mov     rcx, rdi; psa
0x180045868  call    cs:__imp_SafeArrayAccessData
0x18004586e  mov     ebx, eax
0x180045870  test    eax, eax
0x180045872  js      short loc_1800458A6
0x180045874  mov     rax, [rsi]
0x180045877  mov     r8, [rsp+48h+ppvData]
0x18004587c  mov     edx, [rdi+18h]
0x18004587f  mov     rcx, rsi
0x180045882  mov     rax, [rax+18h]
0x180045886  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004588b  mov     ebx, eax
0x18004588d  mov     rcx, rdi; psa
0x180045890  call    cs:__imp_SafeArrayUnaccessData
0x180045896  jmp     short loc_1800458A6
0x180045898  mov     eax, 80070057h
0x18004589d  jmp     short loc_1800458E5
0x18004589f  mov     eax, 80070057h
0x1800458a4  jmp     short loc_1800458E5
0x1800458a6  test    ebx, ebx
0x1800458a8  jz      short loc_1800458E3
0x1800458aa  lea     rax, WPP_GLOBAL_Control
0x1800458b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800458b8  cmp     rcx, rax
0x1800458bb  jz      short loc_1800458E3
0x1800458bd  test    byte ptr [rcx+1Ch], 1
0x1800458c1  jz      short loc_1800458E3
0x1800458c3  mov     edx, 16h
0x1800458c8  mov     [rsp+48h+var_28], ebx
0x1800458cc  lea     r9, aCupnpeventingm_5; "CUPnPEventingManager::OnStateChangedSaf"...
0x1800458d3  lea     r8, WPP_26899187c1a539900c7f96418485818e_Traceguids
0x1800458da  mov     rcx, [rcx+10h]
0x1800458de  call    WPP_SF_sd
0x1800458e3  mov     eax, ebx
0x1800458e5  mov     rbx, [rsp+48h+arg_0]
0x1800458ea  mov     rsi, [rsp+48h+arg_8]
0x1800458ef  add     rsp, 40h
0x1800458f3  pop     rdi
0x1800458f4  retn
```
