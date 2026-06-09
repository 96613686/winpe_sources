# HrCreateOrOpenDeviceHostKey(HKEY__ * *)

- ea: `0x180010ed8`
- end: `0x180011063`
- name: `?HrCreateOrOpenDeviceHostKey@@YAJPEAPEAUHKEY__@@@Z`
- size: `395`
- prototype: `__int64 __fastcall(HKEY *)`
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005b24`
- `0x180010d88`
- `0x1800118b0`
- `0x180012d70`
- `0x180012fa0`

## callees

- `0x180010ed8`
- `0x180011cfc`
- `0x1800200f4`
- `0x180032c6c`
- `0x18003b1cc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180010f94`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180010f94`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010ffc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010ffc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010f2f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010f2f`

## string_xrefs

- `0x180010fd6`: `HrRegOpenKeyEx`

## pseudocode

```c
__int64 __fastcall HrCreateOrOpenDeviceHostKey(HKEY *a1)
{
  LSTATUS v3; // eax
  signed int v4; // ebx
  STRSAFE_PCNZWCH v5; // rcx
  bool v6; // zf
  unsigned int v7; // r8d
  unsigned int v8; // r9d
  struct _SECURITY_ATTRIBUTES *phkResult; // [rsp+20h] [rbp-28h]
  HKEY hKey; // [rsp+50h] [rbp+8h] BYREF
  void *Block; // [rsp+58h] [rbp+10h] BYREF

  if ( !a1 )
    return 2147500035LL;
  hKey = 0;
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\UPnP Device Host", 0, 0x2001Fu, &hKey);
  v4 = v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
  if ( v4 < 0 )
  {
    hKey = 0;
  }
  else if ( !v4 )
  {
    goto LABEL_7;
  }
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
    goto LABEL_8;
  WPP_SF_sd(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    15,
    (unsigned int)WPP_c680b5d87c9d36903333b9725f9279d1_Traceguids,
    (unsigned int)"HrRegOpenKeyEx",
    v4);
LABEL_7:
  v5 = WPP_GLOBAL_Control;
LABEL_8:
  v6 = v4 == 0;
  if ( v4 >= 0 )
  {
    Block = 0;
    if ( (int)HrRegQueryString(hKey, L"RedirectionKey", (struct CUString *)&Block) >= 0 )
    {
      RegCloseKey(hKey);
      v4 = HrRegCreateKeyEx(HKEY_LOCAL_MACHINE, (const unsigned __int16 *)Block, v7, v8, phkResult, &hKey, 0);
    }
    free(Block);
    if ( v4 >= 0 )
      *a1 = hKey;
    v5 = WPP_GLOBAL_Control;
    v6 = v4 == 0;
  }
  if ( !v6 && v5 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v5[14] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)v5 + 2), 11, WPP_cd0457ca62d634003859bdcf9006b616_Traceguids, (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180010ed8  mov     [rsp+arg_10], rbx
0x180010edd  mov     [rsp+arg_18], rbp
0x180010ee2  push    rdi
0x180010ee3  sub     rsp, 40h
0x180010ee7  mov     rdi, rcx
0x180010eea  test    rcx, rcx
0x180010eed  jnz     short loc_180010F05
0x180010eef  mov     eax, 80004003h
0x180010ef4  mov     rbx, [rsp+48h+arg_10]
0x180010ef9  mov     rbp, [rsp+48h+arg_18]
0x180010efe  add     rsp, 40h
0x180010f02  pop     rdi
0x180010f03  retn
0x180010f05  lea     rax, [rsp+48h+hKey]
0x180010f0a  mov     [rsp+48h+hKey], 0
0x180010f13  mov     r9d, 2001Fh; samDesired
0x180010f19  mov     [rsp+48h+phkResult], rax; struct _SECURITY_ATTRIBUTES *
0x180010f1e  xor     r8d, r8d; ulOptions
0x180010f21  lea     rdx, ?c_szRegistryMicrosoft@@3QBGB; "SOFTWARE\\Microsoft\\UPnP Device Host"
0x180010f28  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180010f2f  call    cs:__imp_RegOpenKeyExW
0x180010f36  nop     dword ptr [rax+rax+00h]
0x180010f3b  mov     ebx, eax
0x180010f3d  test    eax, eax
0x180010f3f  jle     short loc_180010F4A
0x180010f41  movzx   ebx, ax
0x180010f44  or      ebx, 80070000h
0x180010f4a  lea     rbp, WPP_GLOBAL_Control
0x180010f51  test    ebx, ebx
0x180010f53  js      short loc_180010FB7
0x180010f55  jnz     short loc_180010FC0
0x180010f57  mov     rcx, cs:WPP_GLOBAL_Control
0x180010f5e  test    ebx, ebx
0x180010f60  jns     short loc_180010F6C
0x180010f62  jnz     loc_180011033
0x180010f68  mov     eax, ebx
0x180010f6a  jmp     short loc_180010EF4
0x180010f6c  mov     rcx, [rsp+48h+hKey]; hKey
0x180010f71  lea     r8, [rsp+48h+Block]; this
0x180010f76  lea     rdx, ValueName; "RedirectionKey"
0x180010f7d  mov     [rsp+48h+Block], 0
0x180010f86  call    ?HrRegQueryString@@YAJPEAUHKEY__@@PEBGAEAVCUString@@@Z; HrRegQueryString(HKEY__ *,ushort const *,CUString &)
0x180010f8b  test    eax, eax
0x180010f8d  jns     short loc_180010FF7
0x180010f8f  mov     rcx, [rsp+48h+Block]; Block
0x180010f94  call    cs:__imp_free
0x180010f9b  nop     dword ptr [rax+rax+00h]
0x180010fa0  test    ebx, ebx
0x180010fa2  js      short loc_180010FAC
0x180010fa4  mov     rcx, [rsp+48h+hKey]
0x180010fa9  mov     [rdi], rcx
0x180010fac  mov     rcx, cs:WPP_GLOBAL_Control
0x180010fb3  test    ebx, ebx
0x180010fb5  jmp     short loc_180010F62
0x180010fb7  mov     [rsp+48h+hKey], 0
0x180010fc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180010fc7  cmp     rcx, rbp
0x180010fca  jz      short loc_180010F5E
0x180010fcc  test    byte ptr [rcx+1Ch], 1
0x180010fd0  jz      short loc_180010F5E
0x180010fd2  mov     rcx, [rcx+10h]
0x180010fd6  lea     r9, aHrregopenkeyex; "HrRegOpenKeyEx"
0x180010fdd  mov     edx, 0Fh
0x180010fe2  mov     dword ptr [rsp+48h+phkResult], ebx
0x180010fe6  lea     r8, WPP_c680b5d87c9d36903333b9725f9279d1_Traceguids
0x180010fed  call    WPP_SF_sd
0x180010ff2  jmp     loc_180010F57
0x180010ff7  mov     rcx, [rsp+48h+hKey]; hKey
0x180010ffc  call    cs:__imp_RegCloseKey
0x180011003  nop     dword ptr [rax+rax+00h]
0x180011008  mov     rdx, [rsp+48h+Block]; unsigned __int16 *
0x18001100d  lea     rax, [rsp+48h+hKey]
0x180011012  mov     [rsp+48h+var_18], 0; unsigned int *
0x18001101b  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180011022  mov     [rsp+48h+var_20], rax; HKEY *
0x180011027  call    ?HrRegCreateKeyEx@@YAJPEAUHKEY__@@PEBGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z; HrRegCreateKeyEx(HKEY__ *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x18001102c  mov     ebx, eax
0x18001102e  jmp     loc_180010F8F
0x180011033  cmp     rcx, rbp
0x180011036  jz      loc_180010F68
0x18001103c  test    byte ptr [rcx+1Ch], 1
0x180011040  jz      loc_180010F68
0x180011046  mov     rcx, [rcx+10h]
0x18001104a  lea     r8, WPP_cd0457ca62d634003859bdcf9006b616_Traceguids
0x180011051  mov     edx, 0Bh
0x180011056  mov     r9d, ebx
0x180011059  call    WPP_SF_d
0x18001105e  jmp     loc_180010F68
```
