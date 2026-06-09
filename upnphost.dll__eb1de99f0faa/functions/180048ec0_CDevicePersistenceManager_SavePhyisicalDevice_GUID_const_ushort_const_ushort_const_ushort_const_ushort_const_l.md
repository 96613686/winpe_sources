# CDevicePersistenceManager::SavePhyisicalDevice(_GUID const &,ushort const *,ushort const *,ushort const *,ushort const *,long)

- ea: `0x180048ec0`
- end: `0x180049087`
- name: `?SavePhyisicalDevice@CDevicePersistenceManager@@UEAAJAEBU_GUID@@PEBG111J@Z`
- size: `455`
- prototype: `int(CDevicePersistenceManager *__hidden this, const struct _GUID *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180013180`
- `0x18001add0`
- `0x18001d048`
- `0x18001d100`
- `0x18001df9c`
- `0x180030f18`
- `0x1800311bc`
- `0x180038ce4`
- `0x180048ec0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004906a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004906a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004900e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180049026`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004900e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180049026`

## string_xrefs

- `0x180048fcd`: `Resource Path`

## pseudocode

```c
__int64 __fastcall CDevicePersistenceManager::SavePhyisicalDevice(
        CDevicePersistenceManager *this,
        const struct _GUID *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        int a7)
{
  unsigned __int16 *v10; // rbx
  int IsAllowedCOMCallLocality; // edi
  __int64 v12; // r8
  __int64 v13; // r9
  HKEY v14; // r14
  struct _SECURITY_ATTRIBUTES *v16; // [rsp+20h] [rbp-48h]
  unsigned __int16 *v17; // [rsp+40h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-20h] BYREF
  HKEY v19; // [rsp+50h] [rbp-18h] BYREF
  unsigned int v20; // [rsp+B0h] [rbp+48h] BYREF

  if ( !a3 || !a4 || !a5 || !a6 )
    return 2147942487LL;
  v10 = 0;
  v17 = 0;
  IsAllowedCOMCallLocality = HrIsAllowedCOMCallLocality(1);
  if ( IsAllowedCOMCallLocality >= 0 )
  {
    IsAllowedCOMCallLocality = CUString::HrInitFromGUID((CUString *)&v17, a2);
    if ( IsAllowedCOMCallLocality < 0
      || (v19 = 0, IsAllowedCOMCallLocality = HrCreateOrOpenDevicesKey(&v19), IsAllowedCOMCallLocality < 0) )
    {
      v10 = v17;
    }
    else
    {
      v14 = v19;
      hKey = 0;
      v20 = 0;
      v10 = v17;
      IsAllowedCOMCallLocality = HrRegCreateKeyEx(v19, v17, v12, v13, v16, &hKey, &v20);
      if ( IsAllowedCOMCallLocality >= 0 )
      {
        IsAllowedCOMCallLocality = HrRegSetSz(hKey, L"ProgId", a3);
        if ( IsAllowedCOMCallLocality >= 0 )
        {
          IsAllowedCOMCallLocality = HrRegSetSz(hKey, L"Init String", a4);
          if ( IsAllowedCOMCallLocality >= 0 )
          {
            IsAllowedCOMCallLocality = HrRegSetSz(hKey, L"Container Id", a5);
            if ( IsAllowedCOMCallLocality >= 0 )
            {
              IsAllowedCOMCallLocality = HrRegSetSz(hKey, L"Resource Path", a6);
              if ( IsAllowedCOMCallLocality >= 0 )
              {
                LODWORD(v17) = a7;
                IsAllowedCOMCallLocality = HrRegSetValueEx(hKey, L"Life Time", 4u, (const unsigned __int8 *)&v17, 4u);
              }
            }
          }
        }
        RegCloseKey(hKey);
        if ( IsAllowedCOMCallLocality < 0 )
          HrRegDeleteKeyTree(v14, v10);
      }
      RegCloseKey(v14);
    }
  }
  if ( IsAllowedCOMCallLocality
    && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      WPP_7ca04b3421e13ea3d8a938e31850813e_Traceguids,
      (unsigned int)IsAllowedCOMCallLocality);
  }
  free(v10);
  return (unsigned int)IsAllowedCOMCallLocality;
}

```

## disassembly

```asm
0x180048ec0  push    rbp
0x180048ec2  push    rbx
0x180048ec3  push    rdi
0x180048ec4  push    r12
0x180048ec6  push    r13
0x180048ec8  push    r14
0x180048eca  mov     rbp, rsp
0x180048ecd  sub     rsp, 68h
0x180048ed1  mov     r12, r9
0x180048ed4  mov     r13, r8
0x180048ed7  mov     r14, rdx
0x180048eda  test    r8, r8
0x180048edd  jz      loc_180049074
0x180048ee3  test    r9, r9
0x180048ee6  jz      loc_180049074
0x180048eec  cmp     [rbp+arg_20], 0
0x180048ef1  jz      loc_180049074
0x180048ef7  cmp     [rbp+arg_28], 0
0x180048efc  jz      loc_180049074
0x180048f02  xor     ebx, ebx
0x180048f04  mov     [rbp+var_28], rbx
0x180048f08  lea     ecx, [rbx+1]
0x180048f0b  call    ?HrIsAllowedCOMCallLocality@@YAJW4CALL_LOCALITY@@@Z; HrIsAllowedCOMCallLocality(CALL_LOCALITY)
0x180048f10  mov     edi, eax
0x180048f12  test    eax, eax
0x180048f14  js      loc_180049032
0x180048f1a  mov     rdx, r14; struct _GUID *
0x180048f1d  lea     rcx, [rbp+var_28]; this
0x180048f21  call    ?HrInitFromGUID@CUString@@QEAAJAEBU_GUID@@@Z; CUString::HrInitFromGUID(_GUID const &)
0x180048f26  mov     edi, eax
0x180048f28  test    eax, eax
0x180048f2a  js      loc_18004902E
0x180048f30  lea     rcx, [rbp+var_18]; HKEY *
0x180048f34  mov     [rbp+var_18], rbx
0x180048f38  call    ?HrCreateOrOpenDevicesKey@@YAJPEAPEAUHKEY__@@@Z; HrCreateOrOpenDevicesKey(HKEY__ * *)
0x180048f3d  mov     edi, eax
0x180048f3f  test    eax, eax
0x180048f41  js      loc_18004902E
0x180048f47  mov     r14, [rbp+var_18]
0x180048f4b  lea     rax, [rbp+arg_10]
0x180048f4f  mov     [rsp+68h+var_38], rax; unsigned int *
0x180048f54  mov     rcx, r14; HKEY
0x180048f57  mov     [rbp+hKey], rbx
0x180048f5b  lea     rax, [rbp+hKey]
0x180048f5f  mov     [rbp+arg_10], ebx
0x180048f62  mov     rbx, [rbp+var_28]
0x180048f66  mov     rdx, rbx; unsigned __int16 *
0x180048f69  mov     [rsp+68h+var_40], rax; HKEY *
0x180048f6e  call    ?HrRegCreateKeyEx@@YAJPEAUHKEY__@@PEBGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z; HrRegCreateKeyEx(HKEY__ *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x180048f73  mov     edi, eax
0x180048f75  test    eax, eax
0x180048f77  js      loc_180049023
0x180048f7d  mov     rcx, [rbp+hKey]; HKEY
0x180048f81  lea     rdx, aProgid; "ProgId"
0x180048f88  mov     r8, r13; unsigned __int16 *
0x180048f8b  call    ?HrRegSetSz@@YAJPEAUHKEY__@@PEBG1@Z; HrRegSetSz(HKEY__ *,ushort const *,ushort const *)
0x180048f90  mov     edi, eax
0x180048f92  test    eax, eax
0x180048f94  js      short loc_18004900A
0x180048f96  mov     rcx, [rbp+hKey]; HKEY
0x180048f9a  lea     rdx, aInitString; "Init String"
0x180048fa1  mov     r8, r12; unsigned __int16 *
0x180048fa4  call    ?HrRegSetSz@@YAJPEAUHKEY__@@PEBG1@Z; HrRegSetSz(HKEY__ *,ushort const *,ushort const *)
0x180048fa9  mov     edi, eax
0x180048fab  test    eax, eax
0x180048fad  js      short loc_18004900A
0x180048faf  mov     r8, [rbp+arg_20]; unsigned __int16 *
0x180048fb3  lea     rdx, aContainerId; "Container Id"
0x180048fba  mov     rcx, [rbp+hKey]; HKEY
0x180048fbe  call    ?HrRegSetSz@@YAJPEAUHKEY__@@PEBG1@Z; HrRegSetSz(HKEY__ *,ushort const *,ushort const *)
0x180048fc3  mov     edi, eax
0x180048fc5  test    eax, eax
0x180048fc7  js      short loc_18004900A
0x180048fc9  mov     r8, [rbp+arg_28]; unsigned __int16 *
0x180048fcd  lea     rdx, aResourcePath; "Resource Path"
0x180048fd4  mov     rcx, [rbp+hKey]; HKEY
0x180048fd8  call    ?HrRegSetSz@@YAJPEAUHKEY__@@PEBG1@Z; HrRegSetSz(HKEY__ *,ushort const *,ushort const *)
0x180048fdd  mov     edi, eax
0x180048fdf  test    eax, eax
0x180048fe1  js      short loc_18004900A
0x180048fe3  mov     eax, [rbp+arg_30]
0x180048fe6  lea     r9, [rbp+var_28]; unsigned __int8 *
0x180048fea  mov     rcx, [rbp+hKey]; HKEY
0x180048fee  lea     rdx, aLifeTime; "Life Time"
0x180048ff5  mov     r8d, 4; unsigned int
0x180048ffb  mov     dword ptr [rbp+var_28], eax
0x180048ffe  mov     dword ptr [rsp+68h+var_48], r8d; unsigned int
0x180049003  call    ?HrRegSetValueEx@@YAJPEAUHKEY__@@PEBGKPEBEK@Z; HrRegSetValueEx(HKEY__ *,ushort const *,ulong,uchar const *,ulong)
0x180049008  mov     edi, eax
0x18004900a  mov     rcx, [rbp+hKey]; hKey
0x18004900e  call    cs:__imp_RegCloseKey
0x180049014  test    edi, edi
0x180049016  jns     short loc_180049023
0x180049018  mov     rdx, rbx; unsigned __int16 *
0x18004901b  mov     rcx, r14; HKEY
0x18004901e  call    ?HrRegDeleteKeyTree@@YAJPEAUHKEY__@@PEBG@Z; HrRegDeleteKeyTree(HKEY__ *,ushort const *)
0x180049023  mov     rcx, r14; hKey
0x180049026  call    cs:__imp_RegCloseKey
0x18004902c  jmp     short loc_180049032
0x18004902e  mov     rbx, [rbp+var_28]
0x180049032  test    edi, edi
0x180049034  jz      short loc_180049067
0x180049036  mov     rcx, cs:WPP_GLOBAL_Control
0x18004903d  lea     rax, WPP_GLOBAL_Control
0x180049044  cmp     rcx, rax
0x180049047  jz      short loc_180049067
0x180049049  test    byte ptr [rcx+1Ch], 1
0x18004904d  jz      short loc_180049067
0x18004904f  mov     rcx, [rcx+10h]
0x180049053  lea     r8, WPP_7ca04b3421e13ea3d8a938e31850813e_Traceguids
0x18004905a  mov     edx, 0Ch
0x18004905f  mov     r9d, edi
0x180049062  call    WPP_SF_d
0x180049067  mov     rcx, rbx; Block
0x18004906a  call    cs:__imp_free
0x180049070  mov     eax, edi
0x180049072  jmp     short loc_180049079
0x180049074  mov     eax, 80070057h
0x180049079  add     rsp, 68h
0x18004907d  pop     r14
0x18004907f  pop     r13
0x180049081  pop     r12
0x180049083  pop     rdi
0x180049084  pop     rbx
0x180049085  pop     rbp
0x180049086  retn
```
