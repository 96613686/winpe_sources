# HrCreateOrOpenDeviceHostKey(HKEY__ * *)

- ea: `0x18001c058`
- end: `0x18001c1d0`
- name: `?HrCreateOrOpenDeviceHostKey@@YAJPEAPEAUHKEY__@@@Z`
- size: `376`
- prototype: `__int64 __fastcall(HKEY *)`
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011bfc`
- `0x18001bf14`
- `0x18001c9d4`
- `0x18001dcac`
- `0x18001df9c`

## callees

- `0x18000db4c`
- `0x18001c058`
- `0x18001d254`
- `0x1800311bc`
- `0x180038ce4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001c10d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001c10d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c16f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c16f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c0ae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c0ae`

## string_xrefs

- `0x18001c149`: `HrRegOpenKeyEx`

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
0x18001c058  mov     [rsp+arg_10], rbx
0x18001c05d  mov     [rsp+arg_18], rbp
0x18001c062  push    rdi
0x18001c063  sub     rsp, 40h
0x18001c067  mov     rdi, rcx
0x18001c06a  test    rcx, rcx
0x18001c06d  jnz     short loc_18001C084
0x18001c06f  mov     eax, 80004003h
0x18001c074  mov     rbx, [rsp+48h+arg_10]
0x18001c079  mov     rbp, [rsp+48h+arg_18]
0x18001c07e  add     rsp, 40h
0x18001c082  pop     rdi
0x18001c083  retn
0x18001c084  lea     rax, [rsp+48h+hKey]
0x18001c089  mov     [rsp+48h+hKey], 0
0x18001c092  mov     r9d, 2001Fh; samDesired
0x18001c098  mov     [rsp+48h+phkResult], rax; struct _SECURITY_ATTRIBUTES *
0x18001c09d  xor     r8d, r8d; ulOptions
0x18001c0a0  lea     rdx, ?c_szRegistryMicrosoft@@3QBGB; "SOFTWARE\\Microsoft\\UPnP Device Host"
0x18001c0a7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001c0ae  call    cs:__imp_RegOpenKeyExW
0x18001c0b4  mov     ebx, eax
0x18001c0b6  test    eax, eax
0x18001c0b8  jle     short loc_18001C0C3
0x18001c0ba  movzx   ebx, ax
0x18001c0bd  or      ebx, 80070000h
0x18001c0c3  lea     rbp, WPP_GLOBAL_Control
0x18001c0ca  test    ebx, ebx
0x18001c0cc  js      short loc_18001C12A
0x18001c0ce  jnz     short loc_18001C133
0x18001c0d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c0d7  test    ebx, ebx
0x18001c0d9  jns     short loc_18001C0E5
0x18001c0db  jnz     loc_18001C1A0
0x18001c0e1  mov     eax, ebx
0x18001c0e3  jmp     short loc_18001C074
0x18001c0e5  mov     rcx, [rsp+48h+hKey]; hKey
0x18001c0ea  lea     r8, [rsp+48h+Block]; this
0x18001c0ef  lea     rdx, ValueName; "RedirectionKey"
0x18001c0f6  mov     [rsp+48h+Block], 0
0x18001c0ff  call    ?HrRegQueryString@@YAJPEAUHKEY__@@PEBGAEAVCUString@@@Z; HrRegQueryString(HKEY__ *,ushort const *,CUString &)
0x18001c104  test    eax, eax
0x18001c106  jns     short loc_18001C16A
0x18001c108  mov     rcx, [rsp+48h+Block]; Block
0x18001c10d  call    cs:__imp_free
0x18001c113  test    ebx, ebx
0x18001c115  js      short loc_18001C11F
0x18001c117  mov     rcx, [rsp+48h+hKey]
0x18001c11c  mov     [rdi], rcx
0x18001c11f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c126  test    ebx, ebx
0x18001c128  jmp     short loc_18001C0DB
0x18001c12a  mov     [rsp+48h+hKey], 0
0x18001c133  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c13a  cmp     rcx, rbp
0x18001c13d  jz      short loc_18001C0D7
0x18001c13f  test    byte ptr [rcx+1Ch], 1
0x18001c143  jz      short loc_18001C0D7
0x18001c145  mov     rcx, [rcx+10h]
0x18001c149  lea     r9, aHrregopenkeyex; "HrRegOpenKeyEx"
0x18001c150  mov     edx, 0Fh
0x18001c155  mov     dword ptr [rsp+48h+phkResult], ebx
0x18001c159  lea     r8, WPP_c680b5d87c9d36903333b9725f9279d1_Traceguids
0x18001c160  call    WPP_SF_sd
0x18001c165  jmp     loc_18001C0D0
0x18001c16a  mov     rcx, [rsp+48h+hKey]; hKey
0x18001c16f  call    cs:__imp_RegCloseKey
0x18001c175  mov     rdx, [rsp+48h+Block]; unsigned __int16 *
0x18001c17a  lea     rax, [rsp+48h+hKey]
0x18001c17f  mov     [rsp+48h+var_18], 0; unsigned int *
0x18001c188  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x18001c18f  mov     [rsp+48h+var_20], rax; HKEY *
0x18001c194  call    ?HrRegCreateKeyEx@@YAJPEAUHKEY__@@PEBGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z; HrRegCreateKeyEx(HKEY__ *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x18001c199  mov     ebx, eax
0x18001c19b  jmp     loc_18001C108
0x18001c1a0  cmp     rcx, rbp
0x18001c1a3  jz      loc_18001C0E1
0x18001c1a9  test    byte ptr [rcx+1Ch], 1
0x18001c1ad  jz      loc_18001C0E1
0x18001c1b3  mov     rcx, [rcx+10h]
0x18001c1b7  lea     r8, WPP_cd0457ca62d634003859bdcf9006b616_Traceguids
0x18001c1be  mov     edx, 0Bh
0x18001c1c3  mov     r9d, ebx
0x18001c1c6  call    WPP_SF_d
0x18001c1cb  jmp     loc_18001C0E1
```
