# DataStoreClient::Initialize(ushort const *)

- ea: `0x1800548c0`
- end: `0x180054b3e`
- name: `?Initialize@DataStoreClient@@UEAAJPEBG@Z`
- size: `638`
- prototype: `int(DataStoreClient *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18003d140`
- `0x180043eec`

## callees

- `0x18002cd00`
- `0x18002d08c`
- `0x18002d278`
- `0x18002efa0`
- `0x18002f08c`
- `0x180039830`
- `0x18004161c`
- `0x180042a80`
- `0x1800548c0`
- `0x180058010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18005496f`
- `KERNEL32!EnterCriticalSection` at `0x18005496f`
- `KERNEL32!LeaveCriticalSection` at `0x180054b26`
- `KERNEL32!LeaveCriticalSection` at `0x180054b26`
- `KERNEL32!SwitchToThread` at `0x180054964`
- `KERNEL32!SwitchToThread` at `0x180054964`
- `KERNEL32!TryEnterCriticalSection` at `0x180054951`
- `KERNEL32!TryEnterCriticalSection` at `0x180054951`
- `ole32!CoCreateInstanceEx` at `0x180054a0d`
- `ole32!CoCreateInstanceEx` at `0x180054a0d`

## string_xrefs

- `0x180054a8e`: `Failed to CoCreate DataStoreComServer on localbox, hr: 0x%x`
- `0x180054ae8`: `Failed to remotely CoCreate DataStoreComServer on:%S, hr: 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DataStoreClient::Initialize(DataStoreClient *this, wchar_t *a2)
{
  HRESULT v4; // esi
  int v5; // eax
  int v6; // r14d
  _bstr_t *v7; // rax
  char v8; // cl
  COSERVERINFO *v9; // r9
  IUnknown *pItf; // rdi
  __int64 v11; // rcx
  MULTI_QI *pResults; // [rsp+28h] [rbp-31h]
  __int64 v14; // [rsp+30h] [rbp-29h] BYREF
  wchar_t *v15; // [rsp+38h] [rbp-21h]
  __int64 v16; // [rsp+40h] [rbp-19h]
  __int64 v17; // [rsp+48h] [rbp-11h]
  MULTI_QI v18; // [rsp+50h] [rbp-9h] BYREF
  GUID *v19; // [rsp+68h] [rbp+Fh]
  struct IUnknown *v20; // [rsp+70h] [rbp+17h]
  int v21; // [rsp+78h] [rbp+1Fh]
  char v22; // [rsp+C0h] [rbp+67h] BYREF

  v4 = 0;
  if ( !a2
    || !*a2
    || (unsigned int)IsComputerLocalEx(a2, ComputerNameNetBIOS)
    || (unsigned int)IsComputerLocalEx(a2, ComputerNameDnsHostname)
    || (unsigned int)IsComputerLocalEx(a2, ComputerNameDnsFullyQualified)
    || (unsigned int)IsComputerLocalEx(a2, ComputerNamePhysicalNetBIOS)
    || (unsigned int)IsComputerLocalEx(a2, ComputerNamePhysicalDnsHostname)
    || (v5 = IsComputerLocalEx(a2, ComputerNamePhysicalDnsFullyQualified)) != 0 )
  {
    LOBYTE(v5) = 1;
  }
  *((_BYTE *)this + 80) = v5;
  v6 = 0;
  while ( !TryEnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8)) )
  {
    if ( ++v6 >= 100 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
      break;
    }
    SwitchToThread();
  }
  v7 = _bstr_t::_bstr_t((_bstr_t *)&v22, a2);
  _bstr_t::operator=((char *)this + 72, v7);
  _bstr_t::_Free((_bstr_t *)&v22);
  if ( ++*((_DWORD *)this + 12) == 1 )
  {
    v14 = 0;
    v15 = a2;
    v16 = 0;
    v17 = 0;
    v18.pIID = &GUID_83e05bd5_aec1_4e58_ae50_e819c7296f67;
    v18.pItf = 0;
    v18.hr = 0;
    v19 = &GUID_c323be28_e546_4c23_a81b_d6ad8d8fac7b;
    v20 = 0;
    v21 = 0;
    v8 = *((_BYTE *)this + 80);
    v9 = (COSERVERINFO *)&v14;
    if ( v8 )
      v9 = 0;
    v4 = CoCreateInstanceEx(&GUID_48da6741_1bf0_4a44_8325_293086c79077, 0, v8 != 0 ? 4 : 16, v9, 2u, &v18);
    if ( v4 < 0 )
    {
      if ( *((_BYTE *)this + 80) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          WppDbgPrint("Failed to CoCreate DataStoreComServer on localbox, hr: 0x%x");
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            10,
            (unsigned int)WPP_bc84e2600b1038389a22987ce46afadc_Traceguids,
            (unsigned int)"NPSDS",
            v4);
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WppDbgPrint("Failed to remotely CoCreate DataStoreComServer on:%S, hr: 0x%x");
        LODWORD(pResults) = v4;
        WPP_SF_sSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          (unsigned int)WPP_bc84e2600b1038389a22987ce46afadc_Traceguids,
          (unsigned int)"NPSDS",
          (__int64)a2,
          pResults,
          v14,
          v15,
          v16,
          v17,
          v18.pIID);
      }
      --*((_DWORD *)this + 12);
    }
    else
    {
      if ( v18.hr >= 0 )
      {
        pItf = v18.pItf;
        v11 = *((_QWORD *)this + 7);
        if ( v11 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
        *((_QWORD *)this + 7) = pItf;
      }
      if ( v21 >= 0 && *((struct IUnknown **)this + 8) != v20 )
        ATL::AtlComPtrAssign((struct IUnknown **)this + 8, v20);
      v4 = 0;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800548c0  push    rbp
0x1800548c2  push    rbx
0x1800548c3  push    rsi
0x1800548c4  push    rdi
0x1800548c5  push    r14
0x1800548c7  push    r15
0x1800548c9  lea     rbp, [rsp-2Fh]
0x1800548ce  sub     rsp, 88h
0x1800548d5  mov     rdi, rdx
0x1800548d8  mov     rbx, rcx
0x1800548db  xor     esi, esi
0x1800548dd  test    rdx, rdx
0x1800548e0  jz      short loc_180054942
0x1800548e2  xor     eax, eax
0x1800548e4  cmp     ax, [rdx]
0x1800548e7  jz      short loc_180054942
0x1800548e9  xor     edx, edx; NameType
0x1800548eb  mov     rcx, rdi; String2
0x1800548ee  call    ?IsComputerLocalEx@@YAHPEBGW4_COMPUTER_NAME_FORMAT@@@Z; IsComputerLocalEx(ushort const *,_COMPUTER_NAME_FORMAT)
0x1800548f3  test    eax, eax
0x1800548f5  jnz     short loc_180054942
0x1800548f7  lea     edx, [rsi+1]; NameType
0x1800548fa  mov     rcx, rdi; String2
0x1800548fd  call    ?IsComputerLocalEx@@YAHPEBGW4_COMPUTER_NAME_FORMAT@@@Z; IsComputerLocalEx(ushort const *,_COMPUTER_NAME_FORMAT)
0x180054902  test    eax, eax
0x180054904  jnz     short loc_180054942
0x180054906  lea     edx, [rsi+3]; NameType
0x180054909  mov     rcx, rdi; String2
0x18005490c  call    ?IsComputerLocalEx@@YAHPEBGW4_COMPUTER_NAME_FORMAT@@@Z; IsComputerLocalEx(ushort const *,_COMPUTER_NAME_FORMAT)
0x180054911  test    eax, eax
0x180054913  jnz     short loc_180054942
0x180054915  lea     edx, [rsi+4]; NameType
0x180054918  mov     rcx, rdi; String2
0x18005491b  call    ?IsComputerLocalEx@@YAHPEBGW4_COMPUTER_NAME_FORMAT@@@Z; IsComputerLocalEx(ushort const *,_COMPUTER_NAME_FORMAT)
0x180054920  test    eax, eax
0x180054922  jnz     short loc_180054942
0x180054924  lea     edx, [rsi+5]; NameType
0x180054927  mov     rcx, rdi; String2
0x18005492a  call    ?IsComputerLocalEx@@YAHPEBGW4_COMPUTER_NAME_FORMAT@@@Z; IsComputerLocalEx(ushort const *,_COMPUTER_NAME_FORMAT)
0x18005492f  test    eax, eax
0x180054931  jnz     short loc_180054942
0x180054933  lea     edx, [rsi+7]; NameType
0x180054936  mov     rcx, rdi; String2
0x180054939  call    ?IsComputerLocalEx@@YAHPEBGW4_COMPUTER_NAME_FORMAT@@@Z; IsComputerLocalEx(ushort const *,_COMPUTER_NAME_FORMAT)
0x18005493e  test    eax, eax
0x180054940  jz      short loc_180054944
0x180054942  mov     al, 1
0x180054944  mov     [rbx+50h], al
0x180054947  lea     r15, [rbx+8]
0x18005494b  xor     r14d, r14d
0x18005494e  mov     rcx, r15; lpCriticalSection
0x180054951  call    cs:__imp_TryEnterCriticalSection
0x180054957  test    eax, eax
0x180054959  jnz     short loc_180054975
0x18005495b  inc     r14d
0x18005495e  cmp     r14d, 64h ; 'd'
0x180054962  jge     short loc_18005496C
0x180054964  call    cs:__imp_SwitchToThread
0x18005496a  jmp     short loc_18005494E
0x18005496c  mov     rcx, r15; lpCriticalSection
0x18005496f  call    cs:__imp_EnterCriticalSection
0x180054975  mov     rdx, rdi; unsigned __int16 *
0x180054978  lea     rcx, [rbp+57h+arg_0]; this
0x18005497c  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180054981  lea     rcx, [rbx+48h]
0x180054985  mov     rdx, rax
0x180054988  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x18005498d  lea     rcx, [rbp+57h+arg_0]; this
0x180054991  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180054996  inc     dword ptr [rbx+30h]
0x180054999  cmp     dword ptr [rbx+30h], 1
0x18005499d  jnz     loc_180054B23
0x1800549a3  mov     [rbp+57h+var_80], rsi
0x1800549a7  mov     [rbp+57h+var_78], rdi
0x1800549ab  mov     [rbp+57h+var_70], rsi
0x1800549af  mov     [rbp+57h+var_68], rsi
0x1800549b3  lea     rax, _GUID_83e05bd5_aec1_4e58_ae50_e819c7296f67
0x1800549ba  mov     [rbp+57h+var_60.pIID], rax
0x1800549be  mov     [rbp+57h+var_60.pItf], rsi
0x1800549c2  mov     [rbp+57h+var_60.hr], esi
0x1800549c5  lea     rax, _GUID_c323be28_e546_4c23_a81b_d6ad8d8fac7b
0x1800549cc  mov     [rbp+57h+var_48], rax
0x1800549d0  mov     [rbp+57h+var_40], rsi
0x1800549d4  mov     [rbp+57h+var_38], esi
0x1800549d7  mov     cl, [rbx+50h]
0x1800549da  lea     r9, [rbp+57h+var_80]
0x1800549de  xor     eax, eax
0x1800549e0  test    cl, cl
0x1800549e2  cmovnz  r9, rax; pServerInfo
0x1800549e6  neg     cl
0x1800549e8  sbb     r8d, r8d
0x1800549eb  and     r8d, 0FFFFFFF4h
0x1800549ef  add     r8d, 10h; dwClsCtx
0x1800549f3  lea     rax, [rbp+57h+var_60]
0x1800549f7  mov     [rsp+0B0h+pResults], rax; pResults
0x1800549fc  mov     [rsp+0B0h+dwCount], 2; dwCount
0x180054a04  xor     edx, edx; punkOuter
0x180054a06  lea     rcx, _GUID_48da6741_1bf0_4a44_8325_293086c79077; Clsid
0x180054a0d  call    cs:__imp_CoCreateInstanceEx
0x180054a13  mov     esi, eax
0x180054a15  test    eax, eax
0x180054a17  js      short loc_180054A5B
0x180054a19  cmp     [rbp+57h+var_60.hr], 0
0x180054a1d  jl      short loc_180054A3C
0x180054a1f  mov     rdi, [rbp+57h+var_60.pItf]
0x180054a23  mov     rcx, [rbx+38h]
0x180054a27  test    rcx, rcx
0x180054a2a  jz      short loc_180054A38
0x180054a2c  mov     rax, [rcx]
0x180054a2f  mov     rax, [rax+10h]
0x180054a33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054a38  mov     [rbx+38h], rdi
0x180054a3c  cmp     [rbp+57h+var_38], 0
0x180054a40  jl      short loc_180054A54
0x180054a42  mov     rdx, [rbp+57h+var_40]; struct IUnknown *
0x180054a46  lea     rcx, [rbx+40h]; struct IUnknown **
0x180054a4a  cmp     [rcx], rdx
0x180054a4d  jz      short loc_180054A54
0x180054a4f  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180054a54  xor     esi, esi
0x180054a56  jmp     loc_180054B23
0x180054a5b  cmp     byte ptr [rbx+50h], 0
0x180054a5f  jz      short loc_180054AC3
0x180054a61  lea     rcx, WPP_GLOBAL_Control
0x180054a68  mov     rax, cs:WPP_GLOBAL_Control
0x180054a6f  cmp     rax, rcx
0x180054a72  jz      loc_180054B20
0x180054a78  cmp     byte ptr [rax+19h], 2
0x180054a7c  jb      loc_180054B20
0x180054a82  test    byte ptr [rax+1Ch], 10h
0x180054a86  jz      loc_180054B20
0x180054a8c  mov     edx, esi
0x180054a8e  lea     rcx, aFailedToCocrea; "Failed to CoCreate DataStoreComServer o"...
0x180054a95  call    WppDbgPrint
0x180054a9a  mov     edx, 0Ah
0x180054a9f  mov     [rsp+0B0h+dwCount], esi
0x180054aa3  lea     r9, aNpsds; "NPSDS"
0x180054aaa  lea     r8, WPP_bc84e2600b1038389a22987ce46afadc_Traceguids
0x180054ab1  mov     rcx, cs:WPP_GLOBAL_Control
0x180054ab8  mov     rcx, [rcx+10h]
0x180054abc  call    WPP_SF_sd
0x180054ac1  jmp     short loc_180054B20
0x180054ac3  lea     rcx, WPP_GLOBAL_Control
0x180054aca  mov     rax, cs:WPP_GLOBAL_Control
0x180054ad1  cmp     rax, rcx
0x180054ad4  jz      short loc_180054B20
0x180054ad6  cmp     byte ptr [rax+19h], 2
0x180054ada  jb      short loc_180054B20
0x180054adc  test    byte ptr [rax+1Ch], 10h
0x180054ae0  jz      short loc_180054B20
0x180054ae2  mov     r8d, esi
0x180054ae5  mov     rdx, rdi
0x180054ae8  lea     rcx, aFailedToRemote; "Failed to remotely CoCreate DataStoreCo"...
0x180054aef  call    WppDbgPrint
0x180054af4  mov     edx, 0Bh
0x180054af9  mov     dword ptr [rsp+0B0h+pResults], esi
0x180054afd  mov     qword ptr [rsp+0B0h+dwCount], rdi
0x180054b02  lea     r9, aNpsds; "NPSDS"
0x180054b09  lea     r8, WPP_bc84e2600b1038389a22987ce46afadc_Traceguids
0x180054b10  mov     rcx, cs:WPP_GLOBAL_Control
0x180054b17  mov     rcx, [rcx+10h]
0x180054b1b  call    WPP_SF_sSd
0x180054b20  dec     dword ptr [rbx+30h]
0x180054b23  mov     rcx, r15; lpCriticalSection
0x180054b26  call    cs:__imp_LeaveCriticalSection
0x180054b2c  mov     eax, esi
0x180054b2e  add     rsp, 88h
0x180054b35  pop     r15
0x180054b37  pop     r14
0x180054b39  pop     rdi
0x180054b3a  pop     rsi
0x180054b3b  pop     rbx
0x180054b3c  pop     rbp
0x180054b3d  retn
```
