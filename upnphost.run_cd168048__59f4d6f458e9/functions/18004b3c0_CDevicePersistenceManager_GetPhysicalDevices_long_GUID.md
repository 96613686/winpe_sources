# CDevicePersistenceManager::GetPhysicalDevices(long *,_GUID * *)

- ea: `0x18004b3c0`
- end: `0x18004b5f9`
- name: `?GetPhysicalDevices@CDevicePersistenceManager@@UEAAJPEAJPEAPEAU_GUID@@@Z`
- size: `569`
- prototype: `int(CDevicePersistenceManager *__hidden this, int *, struct _GUID **)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x1800071c0`
- `0x18000c8e0`
- `0x180012fa0`
- `0x18002bed8`
- `0x18002c534`
- `0x180032540`
- `0x18003b1cc`
- `0x18003cb60`
- `0x18004b3c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b507`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b507`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18004b4ae`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18004b4ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b572`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b572`

## pseudocode

```c
__int64 __fastcall CDevicePersistenceManager::GetPhysicalDevices(
        CDevicePersistenceManager *this,
        int *a2,
        struct _GUID **a3)
{
  int IsAllowedCOMCallLocality; // ebx
  unsigned int v6; // edi
  HRESULT v7; // eax
  int v8; // edi
  int v9; // eax
  int v10; // edx
  __int64 v11; // rcx
  unsigned __int16 *v13; // [rsp+20h] [rbp-E0h]
  unsigned int *v14; // [rsp+28h] [rbp-D8h]
  unsigned int v15; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  void *v17; // [rsp+50h] [rbp-B0h] BYREF
  int v18[2]; // [rsp+58h] [rbp-A8h]
  struct _FILETIME v19; // [rsp+60h] [rbp-A0h] BYREF
  GUID pclsid; // [rsp+68h] [rbp-98h] BYREF
  OLECHAR sz[264]; // [rsp+80h] [rbp-80h] BYREF

  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  v17 = 0;
  *(_QWORD *)v18 = 0;
  hKey = 0;
  IsAllowedCOMCallLocality = HrIsAllowedCOMCallLocality(1);
  if ( IsAllowedCOMCallLocality < 0 )
    goto LABEL_21;
  IsAllowedCOMCallLocality = HrCreateOrOpenDevicesKey(&hKey);
  if ( IsAllowedCOMCallLocality < 0 )
    goto LABEL_21;
  v15 = 0;
  pclsid = 0;
  v19 = 0;
  v6 = 0;
LABEL_6:
  if ( IsAllowedCOMCallLocality >= 0 )
  {
    while ( 1 )
    {
      v15 = 260;
      if ( (unsigned int)HrRegEnumKeyEx(hKey, v6, sz, &v15, v13, v14, &v19) )
        break;
      ++v6;
      v7 = CLSIDFromString(sz, &pclsid);
      if ( v7 >= 0 )
      {
        IsAllowedCOMCallLocality = CUArray<_GUID>::HrPushBack(&v17);
        goto LABEL_6;
      }
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          WPP_7ca04b3421e13ea3d8a938e31850813e_Traceguids,
          (unsigned int)v7);
    }
    IsAllowedCOMCallLocality = 0;
  }
  RegCloseKey(hKey);
  if ( IsAllowedCOMCallLocality < 0 )
    goto LABEL_21;
  v8 = v18[0];
  if ( v18[0] )
  {
    v9 = HrCoTaskMemAllocArray(v18[0], 16, (void **)a3);
    IsAllowedCOMCallLocality = v9;
    if ( v9 >= 0 )
    {
      v10 = 0;
      if ( v8 > 0 )
      {
        do
        {
          v11 = (unsigned int)v10++;
          (*a3)[v11] = *((struct _GUID *)v17 + v11);
        }
        while ( v10 < v8 );
        goto LABEL_30;
      }
    }
    *a2 = v8;
    if ( v9 >= 0 )
      goto LABEL_24;
LABEL_21:
    *a2 = 0;
    if ( *a3 )
      CoTaskMemFree(*a3);
    *a3 = 0;
    goto LABEL_24;
  }
  *a3 = 0;
LABEL_30:
  *a2 = v8;
LABEL_24:
  if ( IsAllowedCOMCallLocality
    && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      WPP_7ca04b3421e13ea3d8a938e31850813e_Traceguids,
      (unsigned int)IsAllowedCOMCallLocality);
  }
  operator delete(v17);
  return (unsigned int)IsAllowedCOMCallLocality;
}

```

## disassembly

```asm
0x18004b3c0  mov     [rsp-8+arg_0], rbx
0x18004b3c5  push    rbp
0x18004b3c6  push    rsi
0x18004b3c7  push    rdi
0x18004b3c8  push    r13
0x18004b3ca  push    r14
0x18004b3cc  lea     rbp, [rsp-1A0h]
0x18004b3d4  sub     rsp, 2A0h
0x18004b3db  mov     rax, cs:__security_cookie
0x18004b3e2  xor     rax, rsp
0x18004b3e5  mov     [rbp+1C0h+var_30], rax
0x18004b3ec  mov     rsi, r8
0x18004b3ef  mov     r14, rdx
0x18004b3f2  test    rdx, rdx
0x18004b3f5  jz      loc_18004B5CD
0x18004b3fb  test    r8, r8
0x18004b3fe  jz      loc_18004B5CD
0x18004b404  mov     ecx, 1
0x18004b409  mov     qword ptr [r8], 0
0x18004b410  mov     [rsp+2C0h+var_270], 0
0x18004b419  mov     qword ptr [rsp+2C0h+var_268], 0
0x18004b422  mov     [rsp+2C0h+hKey], 0
0x18004b42b  call    ?HrIsAllowedCOMCallLocality@@YAJW4CALL_LOCALITY@@@Z; HrIsAllowedCOMCallLocality(CALL_LOCALITY)
0x18004b430  lea     r13, WPP_GLOBAL_Control
0x18004b437  mov     ebx, eax
0x18004b439  test    eax, eax
0x18004b43b  js      loc_18004B563
0x18004b441  lea     rcx, [rsp+2C0h+hKey]; HKEY *
0x18004b446  call    ?HrCreateOrOpenDevicesKey@@YAJPEAPEAUHKEY__@@@Z; HrCreateOrOpenDevicesKey(HKEY__ * *)
0x18004b44b  mov     ebx, eax
0x18004b44d  test    eax, eax
0x18004b44f  js      loc_18004B563
0x18004b455  xorps   xmm0, xmm0
0x18004b458  mov     [rsp+2C0h+var_280], 0
0x18004b460  movups  xmmword ptr [rsp+2C0h+pclsid.Data1], xmm0
0x18004b465  mov     qword ptr [rsp+2C0h+var_260.dwLowDateTime], 0
0x18004b46e  xor     edi, edi
0x18004b470  test    ebx, ebx
0x18004b472  js      loc_18004B502
0x18004b478  mov     rcx, [rsp+2C0h+hKey]; HKEY
0x18004b47d  lea     rax, [rsp+2C0h+var_260]
0x18004b482  lea     r9, [rsp+2C0h+var_280]; unsigned int *
0x18004b487  mov     [rsp+2C0h+var_290], rax; struct _FILETIME *
0x18004b48c  lea     r8, [rbp+1C0h+sz]; unsigned __int16 *
0x18004b490  mov     [rsp+2C0h+var_280], 104h
0x18004b498  mov     edx, edi; unsigned int
0x18004b49a  call    ?HrRegEnumKeyEx@@YAJPEAUHKEY__@@KPEAGPEAK12PEAU_FILETIME@@@Z; HrRegEnumKeyEx(HKEY__ *,ulong,ushort *,ulong *,ushort *,ulong *,_FILETIME *)
0x18004b49f  test    eax, eax
0x18004b4a1  jnz     short loc_18004B500
0x18004b4a3  lea     rdx, [rsp+2C0h+pclsid]; pclsid
0x18004b4a8  inc     edi
0x18004b4aa  lea     rcx, [rbp+1C0h+sz]; lpsz
0x18004b4ae  call    cs:__imp_CLSIDFromString
0x18004b4b5  nop     dword ptr [rax+rax+00h]
0x18004b4ba  test    eax, eax
0x18004b4bc  jns     short loc_18004B4EA
0x18004b4be  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b4c5  cmp     rcx, r13
0x18004b4c8  jz      short loc_18004B478
0x18004b4ca  test    byte ptr [rcx+1Ch], 1
0x18004b4ce  jz      short loc_18004B478
0x18004b4d0  mov     rcx, [rcx+10h]
0x18004b4d4  lea     r8, WPP_7ca04b3421e13ea3d8a938e31850813e_Traceguids
0x18004b4db  mov     edx, 0Fh
0x18004b4e0  mov     r9d, eax
0x18004b4e3  call    WPP_SF_d
0x18004b4e8  jmp     short loc_18004B478
0x18004b4ea  lea     rdx, [rsp+2C0h+pclsid]
0x18004b4ef  lea     rcx, [rsp+2C0h+var_270]
0x18004b4f4  call    ?HrPushBack@?$CUArray@U_GUID@@@@QEAAJAEBU_GUID@@@Z; CUArray<_GUID>::HrPushBack(_GUID const &)
0x18004b4f9  mov     ebx, eax
0x18004b4fb  jmp     loc_18004B470
0x18004b500  xor     ebx, ebx
0x18004b502  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18004b507  call    cs:__imp_RegCloseKey
0x18004b50e  nop     dword ptr [rax+rax+00h]
0x18004b513  test    ebx, ebx
0x18004b515  js      short loc_18004B563
0x18004b517  mov     edi, [rsp+2C0h+var_268]
0x18004b51b  test    edi, edi
0x18004b51d  jz      loc_18004B5C1
0x18004b523  mov     r8, rsi; void **
0x18004b526  mov     edx, 10h; int
0x18004b52b  mov     ecx, edi; int
0x18004b52d  call    ?HrCoTaskMemAllocArray@@YAJJJPEAPEAX@Z; HrCoTaskMemAllocArray(long,long,void * *)
0x18004b532  mov     ebx, eax
0x18004b534  test    eax, eax
0x18004b536  js      short loc_18004B55C
0x18004b538  xor     edx, edx
0x18004b53a  test    edi, edi
0x18004b53c  jle     short loc_18004B55C
0x18004b53e  mov     rax, [rsp+2C0h+var_270]
0x18004b543  mov     ecx, edx
0x18004b545  inc     edx
0x18004b547  add     rcx, rcx
0x18004b54a  movups  xmm0, xmmword ptr [rax+rcx*8]
0x18004b54e  mov     rax, [rsi]
0x18004b551  movdqu  xmmword ptr [rax+rcx*8], xmm0
0x18004b556  cmp     edx, edi
0x18004b558  jl      short loc_18004B53E
0x18004b55a  jmp     short loc_18004B5C8
0x18004b55c  mov     [r14], edi
0x18004b55f  test    eax, eax
0x18004b561  jns     short loc_18004B585
0x18004b563  mov     dword ptr [r14], 0
0x18004b56a  mov     rcx, [rsi]; pv
0x18004b56d  test    rcx, rcx
0x18004b570  jz      short loc_18004B57E
0x18004b572  call    cs:__imp_CoTaskMemFree
0x18004b579  nop     dword ptr [rax+rax+00h]
0x18004b57e  mov     qword ptr [rsi], 0
0x18004b585  test    ebx, ebx
0x18004b587  jz      short loc_18004B5B3
0x18004b589  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b590  cmp     rcx, r13
0x18004b593  jz      short loc_18004B5B3
0x18004b595  test    byte ptr [rcx+1Ch], 1
0x18004b599  jz      short loc_18004B5B3
0x18004b59b  mov     rcx, [rcx+10h]
0x18004b59f  lea     r8, WPP_7ca04b3421e13ea3d8a938e31850813e_Traceguids
0x18004b5a6  mov     edx, 10h
0x18004b5ab  mov     r9d, ebx
0x18004b5ae  call    WPP_SF_d
0x18004b5b3  mov     rcx, [rsp+2C0h+var_270]; void *
0x18004b5b8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004b5bd  mov     eax, ebx
0x18004b5bf  jmp     short loc_18004B5D2
0x18004b5c1  mov     qword ptr [rsi], 0
0x18004b5c8  mov     [r14], edi
0x18004b5cb  jmp     short loc_18004B585
0x18004b5cd  mov     eax, 80004003h
0x18004b5d2  mov     rcx, [rbp+1C0h+var_30]
0x18004b5d9  xor     rcx, rsp; StackCookie
0x18004b5dc  call    __security_check_cookie
0x18004b5e1  mov     rbx, [rsp+2C0h+arg_0]
0x18004b5e9  add     rsp, 2A0h
0x18004b5f0  pop     r14
0x18004b5f2  pop     r13
0x18004b5f4  pop     rdi
0x18004b5f5  pop     rsi
0x18004b5f6  pop     rbp
0x18004b5f7  retn
```
