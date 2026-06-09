# HilbertFinder::FindPossibleTimezones(Cache::Proxy &)

- ea: `0x18000f530`
- end: `0x18000f747`
- name: `?FindPossibleTimezones@HilbertFinder@@UEAA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAVProxy@Cache@@@Z`
- size: `535`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x18000166c`
- `0x1800018fc`
- `0x180002960`
- `0x18000dae0`
- `0x18000e968`
- `0x18000f500`
- `0x18000f530`
- `0x18000f7d4`
- `0x18000fa60`
- `0x1800101c0`
- `0x18001b0f6`
- `0x18001b150`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000f5dd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000f5dd`

## string_xrefs

- `0x18000f5cf`: `SYSTEM\CurrentControlSet\Services\tzautoupdate\Config`
- `0x18000f5c8`: `HilbertIndexPath`

## pseudocode

```c
_QWORD *__fastcall HilbertFinder::FindPossibleTimezones(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  __int64 v5; // rax
  unsigned int ValueW; // eax
  __int64 v7; // rcx
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  __int128 *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rax
  double v15; // xmm0_8
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  int v17; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v18[3]; // [rsp+48h] [rbp-B8h] BYREF
  __int128 pExceptionObject; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v20; // [rsp+70h] [rbp-90h]
  _BYTE v21[80]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v22[16]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v23; // [rsp+E0h] [rbp-20h]
  double v24; // [rsp+F0h] [rbp-10h]
  unsigned __int16 pvData[264]; // [rsp+100h] [rbp+0h] BYREF

  v18[0] = (__int64)a2;
  v5 = a3[16];
  if ( *(_BYTE *)(v5 + 8) )
  {
    *(_BYTE *)(v5 + 8) = 0;
    *(_BYTE *)(a3[17] + 120LL) = 1;
  }
  if ( !*(_BYTE *)(a3[2] + 24LL) )
    goto LABEL_8;
  memset_0(pvData, 0, 0x208u);
  pcbData = 520;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SYSTEM\\CurrentControlSet\\Services\\tzautoupdate\\Config",
             L"HilbertIndexPath",
             2u,
             0,
             pvData,
             &pcbData);
  if ( ValueW )
  {
    if ( (unsigned int)dword_180030000 > 5 && (unsigned __int8)tlgKeywordOn(v7, 0x400000000000LL, ValueW) )
    {
      v17 = v9;
      v18[0] = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        v8,
        (unsigned int)byte_180028B39,
        v9,
        v10,
        (__int64)v18,
        (__int64)&v17);
    }
LABEL_8:
    *a2 = 0;
    a2[1] = 0;
    a2[2] = 0;
    return a2;
  }
  HilbertLocationToTimeZone::HilbertLocationToTimeZone(
    (HilbertLocationToTimeZone *)v21,
    (HilbertLocationToTimeZone *)pvData);
  v12 = (__int128 *)a3[2];
  if ( !*((_BYTE *)v12 + 24) )
  {
    std::logic_error::logic_error(
      (std::logic_error *)&pExceptionObject,
      "value must be set before it can be retrieved (check IsSet)");
    throw (std::logic_error *)&pExceptionObject;
  }
  pExceptionObject = *v12;
  v20 = *((_QWORD *)v12 + 2);
  HilbertLocationToTimeZone::LocationToTimeZone(v21, v22, &pExceptionObject);
  if ( v23 )
  {
    v14 = a3[16];
    v15 = v24;
    if ( !*(_BYTE *)(v14 + 8) || v24 != *(double *)v14 )
    {
      *(_BYTE *)(v14 + 8) = 1;
      *(double *)a3[16] = v15;
      *(_BYTE *)(a3[17] + 120LL) = 1;
    }
    *a2 = 0;
    a2[1] = 0;
    a2[2] = 0;
    std::vector<std::wstring>::_Construct_n(a2, v13, v22);
  }
  else
  {
    *a2 = 0;
    a2[1] = 0;
    a2[2] = 0;
  }
  LOBYTE(v13) = 1;
  std::wstring::_Tidy(v22, v13, 0);
  HilbertLocationToTimeZone::~HilbertLocationToTimeZone((HilbertLocationToTimeZone *)v21);
  return a2;
}

```

## disassembly

```asm
0x18000f530  mov     [rsp-8+arg_0], rbx
0x18000f535  push    rbp
0x18000f536  push    rdi
0x18000f537  push    r14
0x18000f539  lea     rbp, [rsp-220h]
0x18000f541  sub     rsp, 320h
0x18000f548  mov     rax, cs:__security_cookie
0x18000f54f  xor     rax, rsp
0x18000f552  mov     [rbp+230h+var_20], rax
0x18000f559  mov     rdi, r8
0x18000f55c  mov     rbx, rdx
0x18000f55f  mov     [rsp+330h+var_2E8], rdx
0x18000f564  xor     r14d, r14d
0x18000f567  mov     rax, [r8+80h]
0x18000f56e  cmp     [rax+8], r14b
0x18000f572  jz      short loc_18000F583
0x18000f574  mov     [rax+8], r14b
0x18000f578  mov     rax, [r8+88h]
0x18000f57f  mov     byte ptr [rax+78h], 1
0x18000f583  mov     rax, [r8+10h]
0x18000f587  cmp     [rax+18h], r14b
0x18000f58b  jz      loc_18000F636
0x18000f591  xor     edx, edx; Val
0x18000f593  mov     r8d, 208h; Size
0x18000f599  lea     rcx, [rbp+230h+var_230]; void *
0x18000f59d  call    memset_0
0x18000f5a2  mov     [rsp+330h+var_2F0], 208h
0x18000f5aa  lea     rax, [rsp+330h+var_2F0]
0x18000f5af  mov     [rsp+330h+pcbData], rax; pcbData
0x18000f5b4  lea     rax, [rbp+230h+var_230]
0x18000f5b8  mov     [rsp+330h+pvData], rax; pvData
0x18000f5bd  mov     [rsp+330h+pdwType], r14; pdwType
0x18000f5c2  mov     r9d, 2; dwFlags
0x18000f5c8  lea     r8, Value; "HilbertIndexPath"
0x18000f5cf  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\tz"...
0x18000f5d6  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000f5dd  call    cs:__imp_RegGetValueW
0x18000f5e3  mov     r8d, eax
0x18000f5e6  test    eax, eax
0x18000f5e8  jz      short loc_18000F667
0x18000f5ea  mov     eax, cs:dword_180030000
0x18000f5f0  cmp     eax, 5
0x18000f5f3  jbe     short loc_18000F636
0x18000f5f5  mov     rdx, 400000000000h
0x18000f5ff  call    _tlgKeywordOn
0x18000f604  test    al, al
0x18000f606  jz      short loc_18000F636
0x18000f608  mov     [rsp+330h+var_2EC], r8d
0x18000f60d  mov     [rsp+330h+var_2E8], 1000000h
0x18000f616  lea     rax, [rsp+330h+var_2EC]
0x18000f61b  mov     [rsp+330h+pvData], rax
0x18000f620  lea     rax, [rsp+330h+var_2E8]
0x18000f625  mov     [rsp+330h+pdwType], rax
0x18000f62a  lea     rdx, byte_180028B39
0x18000f631  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18000f636  mov     [rbx], r14
0x18000f639  mov     [rbx+8], r14
0x18000f63d  mov     [rbx+10h], r14
0x18000f641  mov     rax, rbx
0x18000f644  mov     rcx, [rbp+230h+var_20]
0x18000f64b  xor     rcx, rsp; StackCookie
0x18000f64e  call    __security_check_cookie
0x18000f653  mov     rbx, [rsp+330h+arg_0]
0x18000f65b  add     rsp, 320h
0x18000f662  pop     r14
0x18000f664  pop     rdi
0x18000f665  pop     rbp
0x18000f666  retn
0x18000f667  lea     rdx, [rbp+230h+var_230]; unsigned __int16 *
0x18000f66b  lea     rcx, [rbp+230h+var_2B0]; this
0x18000f66f  call    ??0HilbertLocationToTimeZone@@QEAA@PEBG@Z; HilbertLocationToTimeZone::HilbertLocationToTimeZone(ushort const *)
0x18000f674  nop
0x18000f675  mov     rax, [rdi+10h]
0x18000f679  cmp     [rax+18h], r14b
0x18000f67d  jz      loc_18000F724
0x18000f683  movups  xmm0, xmmword ptr [rax]
0x18000f686  movaps  [rsp+330h+pExceptionObject], xmm0
0x18000f68b  movsd   xmm1, qword ptr [rax+10h]
0x18000f690  movsd   [rsp+330h+var_2C0], xmm1
0x18000f696  lea     r8, [rsp+330h+pExceptionObject]
0x18000f69b  lea     rdx, [rbp+230h+var_260]
0x18000f69f  lea     rcx, [rbp+230h+var_2B0]
0x18000f6a3  call    ?LocationToTimeZone@HilbertLocationToTimeZone@@QEAA?AUTimeZoneAndRadius@@UBasicGeoposition@Geolocation@Devices@Windows@@@Z; HilbertLocationToTimeZone::LocationToTimeZone(Windows::Devices::Geolocation::BasicGeoposition)
0x18000f6a8  nop
0x18000f6a9  cmp     [rbp+230h+var_250], r14
0x18000f6ad  jnz     short loc_18000F6D7
0x18000f6af  mov     [rbx], r14
0x18000f6b2  mov     [rbx+8], r14
0x18000f6b6  mov     [rbx+10h], r14
0x18000f6ba  xor     r8d, r8d
0x18000f6bd  mov     dl, 1
0x18000f6bf  lea     rcx, [rbp+230h+var_260]
0x18000f6c3  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000f6c8  nop
0x18000f6c9  lea     rcx, [rbp+230h+var_2B0]; this
0x18000f6cd  call    ??1HilbertLocationToTimeZone@@QEAA@XZ; HilbertLocationToTimeZone::~HilbertLocationToTimeZone(void)
0x18000f6d2  jmp     loc_18000F641
0x18000f6d7  mov     rax, [rdi+80h]
0x18000f6de  movsd   xmm0, [rbp+230h+var_240]
0x18000f6e3  cmp     [rax+8], r14b
0x18000f6e7  jz      short loc_18000F6F1
0x18000f6e9  ucomisd xmm0, qword ptr [rax]
0x18000f6ed  jp      short loc_18000F6F1
0x18000f6ef  jz      short loc_18000F70B
0x18000f6f1  mov     byte ptr [rax+8], 1
0x18000f6f5  mov     rax, [rdi+80h]
0x18000f6fc  movsd   qword ptr [rax], xmm0
0x18000f700  mov     rax, [rdi+88h]
0x18000f707  mov     byte ptr [rax+78h], 1
0x18000f70b  mov     [rbx], r14
0x18000f70e  mov     [rbx+8], r14
0x18000f712  mov     [rbx+10h], r14
0x18000f716  lea     r8, [rbp+230h+var_260]
0x18000f71a  mov     rcx, rbx
0x18000f71d  call    ?_Construct_n@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX_KPEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::_Construct_n(unsigned __int64,std::wstring const *)
0x18000f722  jmp     short loc_18000F6BA
0x18000f724  lea     rdx, aValueMustBeSet; "value must be set before it can be retr"...
0x18000f72b  lea     rcx, [rsp+330h+pExceptionObject]; this
0x18000f730  call    ??0logic_error@std@@QEAA@PEBD@Z; std::logic_error::logic_error(char const *)
0x18000f735  lea     rdx, _TI2?AVlogic_error@std@@; pThrowInfo
0x18000f73c  lea     rcx, [rsp+330h+pExceptionObject]; pExceptionObject
0x18000f741  call    _CxxThrowException_0
```
