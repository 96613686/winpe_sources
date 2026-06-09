# CDevicePersistenceManager::GetPhysicalDevices(long *,_GUID * *)

- ea: `0x1800485c0`
- end: `0x1800487e6`
- name: `?GetPhysicalDevices@CDevicePersistenceManager@@UEAAJPEAJPEAPEAU_GUID@@@Z`
- size: `550`
- prototype: `__int64 __fastcall(CDevicePersistenceManager *this, int *, struct _GUID **)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18000f348`
- `0x180013180`
- `0x180018738`
- `0x18001df9c`
- `0x18002aa74`
- `0x1800309a4`
- `0x180038ce4`
- `0x18003a560`
- `0x1800485c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180048701`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180048701`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800486ae`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800486ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048766`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048766`

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
        IsAllowedCOMCallLocality = CUArray<_GUID>::HrPushBack(&v17, &pclsid);
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
0x1800485c0  mov     [rsp-8+arg_0], rbx
0x1800485c5  push    rbp
0x1800485c6  push    rsi
0x1800485c7  push    rdi
0x1800485c8  push    r13
0x1800485ca  push    r14
0x1800485cc  lea     rbp, [rsp-1A0h]
0x1800485d4  sub     rsp, 2A0h
0x1800485db  mov     rax, cs:__security_cookie
0x1800485e2  xor     rax, rsp
0x1800485e5  mov     [rbp+1C0h+var_30], rax
0x1800485ec  mov     rsi, r8
0x1800485ef  mov     r14, rdx
0x1800485f2  test    rdx, rdx
0x1800485f5  jz      loc_1800487BB
0x1800485fb  test    r8, r8
0x1800485fe  jz      loc_1800487BB
0x180048604  mov     ecx, 1
0x180048609  mov     qword ptr [r8], 0
0x180048610  mov     [rsp+2C0h+var_270], 0
0x180048619  mov     qword ptr [rsp+2C0h+var_268], 0
0x180048622  mov     [rsp+2C0h+hKey], 0
0x18004862b  call    ?HrIsAllowedCOMCallLocality@@YAJW4CALL_LOCALITY@@@Z; HrIsAllowedCOMCallLocality(CALL_LOCALITY)
0x180048630  lea     r13, WPP_GLOBAL_Control
0x180048637  mov     ebx, eax
0x180048639  test    eax, eax
0x18004863b  js      loc_180048757
0x180048641  lea     rcx, [rsp+2C0h+hKey]; HKEY *
0x180048646  call    ?HrCreateOrOpenDevicesKey@@YAJPEAPEAUHKEY__@@@Z; HrCreateOrOpenDevicesKey(HKEY__ * *)
0x18004864b  mov     ebx, eax
0x18004864d  test    eax, eax
0x18004864f  js      loc_180048757
0x180048655  xorps   xmm0, xmm0
0x180048658  mov     [rsp+2C0h+var_280], 0
0x180048660  movups  xmmword ptr [rsp+2C0h+pclsid.Data1], xmm0
0x180048665  mov     qword ptr [rsp+2C0h+var_260.dwLowDateTime], 0
0x18004866e  xor     edi, edi
0x180048670  test    ebx, ebx
0x180048672  js      loc_1800486FC
0x180048678  mov     rcx, [rsp+2C0h+hKey]; HKEY
0x18004867d  lea     rax, [rsp+2C0h+var_260]
0x180048682  lea     r9, [rsp+2C0h+var_280]; unsigned int *
0x180048687  mov     [rsp+2C0h+var_290], rax; struct _FILETIME *
0x18004868c  lea     r8, [rbp+1C0h+sz]; unsigned __int16 *
0x180048690  mov     [rsp+2C0h+var_280], 104h
0x180048698  mov     edx, edi; unsigned int
0x18004869a  call    ?HrRegEnumKeyEx@@YAJPEAUHKEY__@@KPEAGPEAK12PEAU_FILETIME@@@Z; HrRegEnumKeyEx(HKEY__ *,ulong,ushort *,ulong *,ushort *,ulong *,_FILETIME *)
0x18004869f  test    eax, eax
0x1800486a1  jnz     short loc_1800486FA
0x1800486a3  lea     rdx, [rsp+2C0h+pclsid]; pclsid
0x1800486a8  inc     edi
0x1800486aa  lea     rcx, [rbp+1C0h+sz]; lpsz
0x1800486ae  call    cs:__imp_CLSIDFromString
0x1800486b4  test    eax, eax
0x1800486b6  jns     short loc_1800486E4
0x1800486b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800486bf  cmp     rcx, r13
0x1800486c2  jz      short loc_180048678
0x1800486c4  test    byte ptr [rcx+1Ch], 1
0x1800486c8  jz      short loc_180048678
0x1800486ca  mov     rcx, [rcx+10h]
0x1800486ce  lea     r8, WPP_7ca04b3421e13ea3d8a938e31850813e_Traceguids
0x1800486d5  mov     edx, 0Fh
0x1800486da  mov     r9d, eax
0x1800486dd  call    WPP_SF_d
0x1800486e2  jmp     short loc_180048678
0x1800486e4  lea     rdx, [rsp+2C0h+pclsid]
0x1800486e9  lea     rcx, [rsp+2C0h+var_270]
0x1800486ee  call    ?HrPushBack@?$CUArray@U_GUID@@@@QEAAJAEBU_GUID@@@Z; CUArray<_GUID>::HrPushBack(_GUID const &)
0x1800486f3  mov     ebx, eax
0x1800486f5  jmp     loc_180048670
0x1800486fa  xor     ebx, ebx
0x1800486fc  mov     rcx, [rsp+2C0h+hKey]; hKey
0x180048701  call    cs:__imp_RegCloseKey
0x180048707  test    ebx, ebx
0x180048709  js      short loc_180048757
0x18004870b  mov     edi, [rsp+2C0h+var_268]
0x18004870f  test    edi, edi
0x180048711  jz      loc_1800487AF
0x180048717  mov     r8, rsi; void **
0x18004871a  mov     edx, 10h; int
0x18004871f  mov     ecx, edi; int
0x180048721  call    ?HrCoTaskMemAllocArray@@YAJJJPEAPEAX@Z; HrCoTaskMemAllocArray(long,long,void * *)
0x180048726  mov     ebx, eax
0x180048728  test    eax, eax
0x18004872a  js      short loc_180048750
0x18004872c  xor     edx, edx
0x18004872e  test    edi, edi
0x180048730  jle     short loc_180048750
0x180048732  mov     rax, [rsp+2C0h+var_270]
0x180048737  mov     ecx, edx
0x180048739  inc     edx
0x18004873b  add     rcx, rcx
0x18004873e  movups  xmm0, xmmword ptr [rax+rcx*8]
0x180048742  mov     rax, [rsi]
0x180048745  movdqu  xmmword ptr [rax+rcx*8], xmm0
0x18004874a  cmp     edx, edi
0x18004874c  jl      short loc_180048732
0x18004874e  jmp     short loc_1800487B6
0x180048750  mov     [r14], edi
0x180048753  test    eax, eax
0x180048755  jns     short loc_180048773
0x180048757  mov     dword ptr [r14], 0
0x18004875e  mov     rcx, [rsi]; pv
0x180048761  test    rcx, rcx
0x180048764  jz      short loc_18004876C
0x180048766  call    cs:__imp_CoTaskMemFree
0x18004876c  mov     qword ptr [rsi], 0
0x180048773  test    ebx, ebx
0x180048775  jz      short loc_1800487A1
0x180048777  mov     rcx, cs:WPP_GLOBAL_Control
0x18004877e  cmp     rcx, r13
0x180048781  jz      short loc_1800487A1
0x180048783  test    byte ptr [rcx+1Ch], 1
0x180048787  jz      short loc_1800487A1
0x180048789  mov     rcx, [rcx+10h]
0x18004878d  lea     r8, WPP_7ca04b3421e13ea3d8a938e31850813e_Traceguids
0x180048794  mov     edx, 10h
0x180048799  mov     r9d, ebx
0x18004879c  call    WPP_SF_d
0x1800487a1  mov     rcx, [rsp+2C0h+var_270]; void *
0x1800487a6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800487ab  mov     eax, ebx
0x1800487ad  jmp     short loc_1800487C0
0x1800487af  mov     qword ptr [rsi], 0
0x1800487b6  mov     [r14], edi
0x1800487b9  jmp     short loc_180048773
0x1800487bb  mov     eax, 80004003h
0x1800487c0  mov     rcx, [rbp+1C0h+var_30]
0x1800487c7  xor     rcx, rsp; StackCookie
0x1800487ca  call    __security_check_cookie
0x1800487cf  mov     rbx, [rsp+2C0h+arg_0]
0x1800487d7  add     rsp, 2A0h
0x1800487de  pop     r14
0x1800487e0  pop     r13
0x1800487e2  pop     rdi
0x1800487e3  pop     rsi
0x1800487e4  pop     rbp
0x1800487e5  retn
```
