# CDevicePersistenceManager::SavePhyisicalDevice(_GUID const &,ushort const *,ushort const *,ushort const *,ushort const *,long)

- ea: `0x18004bd40`
- end: `0x18004bf1a`
- name: `?SavePhyisicalDevice@CDevicePersistenceManager@@UEAAJAEBU_GUID@@PEBG111J@Z`
- size: `474`
- prototype: `__int64 __fastcall(CDevicePersistenceManager *this, const struct _GUID *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800071c0`
- `0x18000fb0c`
- `0x180012c40`
- `0x180012d00`
- `0x180012fa0`
- `0x180032ae0`
- `0x180032c6c`
- `0x18003b1cc`
- `0x18004bd40`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004bef6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004bef6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004be8e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004beac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004be8e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004beac`

## string_xrefs

- `0x18004be4d`: `Resource Path`

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
  unsigned int v12; // r8d
  unsigned int v13; // r9d
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
0x18004bd40  push    rbp
0x18004bd42  push    rbx
0x18004bd43  push    rdi
0x18004bd44  push    r12
0x18004bd46  push    r13
0x18004bd48  push    r14
0x18004bd4a  mov     rbp, rsp
0x18004bd4d  sub     rsp, 68h
0x18004bd51  mov     r12, r9
0x18004bd54  mov     r13, r8
0x18004bd57  mov     r14, rdx
0x18004bd5a  test    r8, r8
0x18004bd5d  jz      loc_18004BF06
0x18004bd63  test    r9, r9
0x18004bd66  jz      loc_18004BF06
0x18004bd6c  cmp     [rbp+arg_20], 0
0x18004bd71  jz      loc_18004BF06
0x18004bd77  cmp     [rbp+arg_28], 0
0x18004bd7c  jz      loc_18004BF06
0x18004bd82  xor     ebx, ebx
0x18004bd84  mov     [rbp+var_28], rbx
0x18004bd88  lea     ecx, [rbx+1]
0x18004bd8b  call    ?HrIsAllowedCOMCallLocality@@YAJW4CALL_LOCALITY@@@Z; HrIsAllowedCOMCallLocality(CALL_LOCALITY)
0x18004bd90  mov     edi, eax
0x18004bd92  test    eax, eax
0x18004bd94  js      loc_18004BEBE
0x18004bd9a  mov     rdx, r14; struct _GUID *
0x18004bd9d  lea     rcx, [rbp+var_28]; this
0x18004bda1  call    ?HrInitFromGUID@CUString@@QEAAJAEBU_GUID@@@Z; CUString::HrInitFromGUID(_GUID const &)
0x18004bda6  mov     edi, eax
0x18004bda8  test    eax, eax
0x18004bdaa  js      loc_18004BEBA
0x18004bdb0  lea     rcx, [rbp+var_18]; HKEY *
0x18004bdb4  mov     [rbp+var_18], rbx
0x18004bdb8  call    ?HrCreateOrOpenDevicesKey@@YAJPEAPEAUHKEY__@@@Z; HrCreateOrOpenDevicesKey(HKEY__ * *)
0x18004bdbd  mov     edi, eax
0x18004bdbf  test    eax, eax
0x18004bdc1  js      loc_18004BEBA
0x18004bdc7  mov     r14, [rbp+var_18]
0x18004bdcb  lea     rax, [rbp+arg_10]
0x18004bdcf  mov     [rsp+68h+var_38], rax; unsigned int *
0x18004bdd4  mov     rcx, r14; HKEY
0x18004bdd7  mov     [rbp+hKey], rbx
0x18004bddb  lea     rax, [rbp+hKey]
0x18004bddf  mov     [rbp+arg_10], ebx
0x18004bde2  mov     rbx, [rbp+var_28]
0x18004bde6  mov     rdx, rbx; unsigned __int16 *
0x18004bde9  mov     [rsp+68h+var_40], rax; HKEY *
0x18004bdee  call    ?HrRegCreateKeyEx@@YAJPEAUHKEY__@@PEBGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z; HrRegCreateKeyEx(HKEY__ *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x18004bdf3  mov     edi, eax
0x18004bdf5  test    eax, eax
0x18004bdf7  js      loc_18004BEA9
0x18004bdfd  mov     rcx, [rbp+hKey]; HKEY
0x18004be01  lea     rdx, aProgid; "ProgId"
0x18004be08  mov     r8, r13; unsigned __int16 *
0x18004be0b  call    ?HrRegSetSz@@YAJPEAUHKEY__@@PEBG1@Z; HrRegSetSz(HKEY__ *,ushort const *,ushort const *)
0x18004be10  mov     edi, eax
0x18004be12  test    eax, eax
0x18004be14  js      short loc_18004BE8A
0x18004be16  mov     rcx, [rbp+hKey]; HKEY
0x18004be1a  lea     rdx, aInitString; "Init String"
0x18004be21  mov     r8, r12; unsigned __int16 *
0x18004be24  call    ?HrRegSetSz@@YAJPEAUHKEY__@@PEBG1@Z; HrRegSetSz(HKEY__ *,ushort const *,ushort const *)
0x18004be29  mov     edi, eax
0x18004be2b  test    eax, eax
0x18004be2d  js      short loc_18004BE8A
0x18004be2f  mov     r8, [rbp+arg_20]; unsigned __int16 *
0x18004be33  lea     rdx, aContainerId; "Container Id"
0x18004be3a  mov     rcx, [rbp+hKey]; HKEY
0x18004be3e  call    ?HrRegSetSz@@YAJPEAUHKEY__@@PEBG1@Z; HrRegSetSz(HKEY__ *,ushort const *,ushort const *)
0x18004be43  mov     edi, eax
0x18004be45  test    eax, eax
0x18004be47  js      short loc_18004BE8A
0x18004be49  mov     r8, [rbp+arg_28]; unsigned __int16 *
0x18004be4d  lea     rdx, aResourcePath; "Resource Path"
0x18004be54  mov     rcx, [rbp+hKey]; HKEY
0x18004be58  call    ?HrRegSetSz@@YAJPEAUHKEY__@@PEBG1@Z; HrRegSetSz(HKEY__ *,ushort const *,ushort const *)
0x18004be5d  mov     edi, eax
0x18004be5f  test    eax, eax
0x18004be61  js      short loc_18004BE8A
0x18004be63  mov     eax, [rbp+arg_30]
0x18004be66  lea     r9, [rbp+var_28]; unsigned __int8 *
0x18004be6a  mov     rcx, [rbp+hKey]; HKEY
0x18004be6e  lea     rdx, aLifeTime; "Life Time"
0x18004be75  mov     r8d, 4; unsigned int
0x18004be7b  mov     dword ptr [rbp+var_28], eax
0x18004be7e  mov     dword ptr [rsp+68h+var_48], r8d; unsigned int
0x18004be83  call    ?HrRegSetValueEx@@YAJPEAUHKEY__@@PEBGKPEBEK@Z; HrRegSetValueEx(HKEY__ *,ushort const *,ulong,uchar const *,ulong)
0x18004be88  mov     edi, eax
0x18004be8a  mov     rcx, [rbp+hKey]; hKey
0x18004be8e  call    cs:__imp_RegCloseKey
0x18004be95  nop     dword ptr [rax+rax+00h]
0x18004be9a  test    edi, edi
0x18004be9c  jns     short loc_18004BEA9
0x18004be9e  mov     rdx, rbx; unsigned __int16 *
0x18004bea1  mov     rcx, r14; HKEY
0x18004bea4  call    ?HrRegDeleteKeyTree@@YAJPEAUHKEY__@@PEBG@Z; HrRegDeleteKeyTree(HKEY__ *,ushort const *)
0x18004bea9  mov     rcx, r14; hKey
0x18004beac  call    cs:__imp_RegCloseKey
0x18004beb3  nop     dword ptr [rax+rax+00h]
0x18004beb8  jmp     short loc_18004BEBE
0x18004beba  mov     rbx, [rbp+var_28]
0x18004bebe  test    edi, edi
0x18004bec0  jz      short loc_18004BEF3
0x18004bec2  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bec9  lea     rax, WPP_GLOBAL_Control
0x18004bed0  cmp     rcx, rax
0x18004bed3  jz      short loc_18004BEF3
0x18004bed5  test    byte ptr [rcx+1Ch], 1
0x18004bed9  jz      short loc_18004BEF3
0x18004bedb  mov     rcx, [rcx+10h]
0x18004bedf  lea     r8, WPP_7ca04b3421e13ea3d8a938e31850813e_Traceguids
0x18004bee6  mov     edx, 0Ch
0x18004beeb  mov     r9d, edi
0x18004beee  call    WPP_SF_d
0x18004bef3  mov     rcx, rbx; Block
0x18004bef6  call    cs:__imp_free
0x18004befd  nop     dword ptr [rax+rax+00h]
0x18004bf02  mov     eax, edi
0x18004bf04  jmp     short loc_18004BF0B
0x18004bf06  mov     eax, 80070057h
0x18004bf0b  add     rsp, 68h
0x18004bf0f  pop     r14
0x18004bf11  pop     r13
0x18004bf13  pop     r12
0x18004bf15  pop     rdi
0x18004bf16  pop     rbx
0x18004bf17  pop     rbp
0x18004bf18  retn
```
