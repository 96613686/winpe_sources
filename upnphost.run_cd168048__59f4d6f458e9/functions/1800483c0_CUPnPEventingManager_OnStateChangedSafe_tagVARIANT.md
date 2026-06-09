# CUPnPEventingManager::OnStateChangedSafe(tagVARIANT)

- ea: `0x1800483c0`
- end: `0x18004854e`
- name: `?OnStateChangedSafe@CUPnPEventingManager@@UEAAJUtagVARIANT@@@Z`
- size: `398`
- prototype: `__int64 __fastcall(CUPnPEventingManager *__hidden this, struct tagVARIANT *__struct_ptr)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800071c0`
- `0x1800200f4`
- `0x1800483c0`
- `0x180059010`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetDim` at `0x180048464`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x180048464`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18004849c`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18004849c`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18004847f`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18004847f`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800484b4`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800484b4`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800484e2`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800484e2`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18004842e`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18004842e`

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
0x1800483c0  mov     rax, rsp
0x1800483c3  mov     [rax+8], rbx
0x1800483c7  mov     [rax+10h], rsi
0x1800483cb  push    rdi
0x1800483cc  sub     rsp, 40h
0x1800483d0  mov     rdi, rdx
0x1800483d3  mov     rsi, rcx
0x1800483d6  mov     qword ptr [rax-10h], 0
0x1800483de  mov     dword ptr [rax+20h], 0
0x1800483e5  mov     dword ptr [rax-18h], 0
0x1800483ec  xor     eax, eax
0x1800483ee  mov     [rsp+48h+pvt], ax
0x1800483f3  lea     ecx, [rax+1]
0x1800483f6  call    ?HrIsAllowedCOMCallLocality@@YAJW4CALL_LOCALITY@@@Z; HrIsAllowedCOMCallLocality(CALL_LOCALITY)
0x1800483fb  mov     ebx, eax
0x1800483fd  test    eax, eax
0x1800483ff  js      loc_1800484FE
0x180048405  mov     eax, 2000h
0x18004840a  test    [rdi], ax
0x18004840d  jnz     short loc_180048419
0x18004840f  mov     eax, 80070057h
0x180048414  jmp     loc_18004853D
0x180048419  mov     rdi, [rdi+8]
0x18004841d  test    rdi, rdi
0x180048420  jz      loc_1800484F0
0x180048426  lea     rdx, [rsp+48h+pvt]; pvt
0x18004842b  mov     rcx, rdi; psa
0x18004842e  call    cs:__imp_SafeArrayGetVartype
0x180048435  nop     dword ptr [rax+rax+00h]
0x18004843a  test    eax, eax
0x18004843c  js      loc_1800484F0
0x180048442  cmp     [rsp+48h+pvt], 17h
0x180048448  ja      loc_1800484F0
0x18004844e  movzx   eax, [rsp+48h+pvt]
0x180048453  mov     ecx, 0C80008h
0x180048458  bt      ecx, eax
0x18004845b  jnb     loc_1800484F0
0x180048461  mov     rcx, rdi; psa
0x180048464  call    cs:__imp_SafeArrayGetDim
0x18004846b  nop     dword ptr [rax+rax+00h]
0x180048470  cmp     eax, 1
0x180048473  jnz     short loc_1800484F0
0x180048475  lea     r8, [rsp+48h+plLbound]; plLbound
0x18004847a  mov     edx, eax; nDim
0x18004847c  mov     rcx, rdi; psa
0x18004847f  call    cs:__imp_SafeArrayGetLBound
0x180048486  nop     dword ptr [rax+rax+00h]
0x18004848b  test    eax, eax
0x18004848d  js      short loc_1800484F0
0x18004848f  lea     r8, [rsp+48h+plUbound]; plUbound
0x180048494  mov     edx, 1; nDim
0x180048499  mov     rcx, rdi; psa
0x18004849c  call    cs:__imp_SafeArrayGetUBound
0x1800484a3  nop     dword ptr [rax+rax+00h]
0x1800484a8  test    eax, eax
0x1800484aa  js      short loc_1800484F0
0x1800484ac  lea     rdx, [rsp+48h+ppvData]; ppvData
0x1800484b1  mov     rcx, rdi; psa
0x1800484b4  call    cs:__imp_SafeArrayAccessData
0x1800484bb  nop     dword ptr [rax+rax+00h]
0x1800484c0  mov     ebx, eax
0x1800484c2  test    eax, eax
0x1800484c4  js      short loc_1800484FE
0x1800484c6  mov     rax, [rsi]
0x1800484c9  mov     r8, [rsp+48h+ppvData]
0x1800484ce  mov     edx, [rdi+18h]
0x1800484d1  mov     rcx, rsi
0x1800484d4  mov     rax, [rax+18h]
0x1800484d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800484dd  mov     ebx, eax
0x1800484df  mov     rcx, rdi; psa
0x1800484e2  call    cs:__imp_SafeArrayUnaccessData
0x1800484e9  nop     dword ptr [rax+rax+00h]
0x1800484ee  jmp     short loc_1800484FE
0x1800484f0  mov     eax, 80070057h
0x1800484f5  jmp     short loc_18004853D
0x1800484f7  mov     eax, 80070057h
0x1800484fc  jmp     short loc_18004853D
0x1800484fe  test    ebx, ebx
0x180048500  jz      short loc_18004853B
0x180048502  lea     rax, WPP_GLOBAL_Control
0x180048509  mov     rcx, cs:WPP_GLOBAL_Control
0x180048510  cmp     rcx, rax
0x180048513  jz      short loc_18004853B
0x180048515  test    byte ptr [rcx+1Ch], 1
0x180048519  jz      short loc_18004853B
0x18004851b  mov     edx, 16h
0x180048520  mov     [rsp+48h+var_28], ebx
0x180048524  lea     r9, aCupnpeventingm_5; "CUPnPEventingManager::OnStateChangedSaf"...
0x18004852b  lea     r8, WPP_26899187c1a539900c7f96418485818e_Traceguids
0x180048532  mov     rcx, [rcx+10h]
0x180048536  call    WPP_SF_sd
0x18004853b  mov     eax, ebx
0x18004853d  mov     rbx, [rsp+48h+arg_0]
0x180048542  mov     rsi, [rsp+48h+arg_8]
0x180048547  add     rsp, 40h
0x18004854b  pop     rdi
0x18004854c  retn
```
