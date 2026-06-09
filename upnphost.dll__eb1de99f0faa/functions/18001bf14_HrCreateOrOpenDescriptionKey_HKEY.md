# HrCreateOrOpenDescriptionKey(HKEY__ * *)

- ea: `0x18001bf14`
- end: `0x18001c051`
- name: `?HrCreateOrOpenDescriptionKey@@YAJPEAPEAUHKEY__@@@Z`
- size: `317`
- prototype: `__int64 __fastcall(PHKEY phkResult)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800162e0`
- `0x18001b060`
- `0x18001be34`
- `0x18001cc38`

## callees

- `0x18000db4c`
- `0x18001bf14`
- `0x18001c058`
- `0x180038ce4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001bfca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001bfca`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001bfaa`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001bfaa`

## string_xrefs

- `0x18001bffc`: `HrRegCreateKeyEx`

## pseudocode

```c
__int64 __fastcall HrCreateOrOpenDescriptionKey(PHKEY phkResult)
{
  signed int v2; // ebx
  LSTATUS v4; // eax
  DWORD dwDisposition; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  if ( !phkResult )
    return 2147500035LL;
  hKey = 0;
  v2 = HrCreateOrOpenDeviceHostKey(&hKey);
  if ( v2 >= 0 )
  {
    dwDisposition = 0;
    v4 = RegCreateKeyExW(hKey, L"Description", 0, 0, 0, 0x2001Fu, 0, phkResult, &dwDisposition);
    v2 = v4;
    if ( v4 > 0 )
      v2 = (unsigned __int16)v4 | 0x80070000;
    if ( v2 < 0 )
    {
      *phkResult = 0;
    }
    else if ( !v2 )
    {
LABEL_9:
      RegCloseKey(hKey);
      goto LABEL_3;
    }
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        (unsigned int)WPP_c680b5d87c9d36903333b9725f9279d1_Traceguids,
        (unsigned int)"HrRegCreateKeyEx",
        v2);
    goto LABEL_9;
  }
LABEL_3:
  if ( v2 && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      121,
      WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids,
      (unsigned int)v2);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18001bf14  mov     rax, rsp
0x18001bf17  mov     [rax+18h], rbx
0x18001bf1b  mov     [rax+20h], rbp
0x18001bf1f  push    rdi
0x18001bf20  sub     rsp, 50h
0x18001bf24  mov     rdi, rcx
0x18001bf27  test    rcx, rcx
0x18001bf2a  jz      loc_18001BFD5
0x18001bf30  lea     rcx, [rax+10h]; HKEY *
0x18001bf34  mov     qword ptr [rax+10h], 0
0x18001bf3c  call    ?HrCreateOrOpenDeviceHostKey@@YAJPEAPEAUHKEY__@@@Z; HrCreateOrOpenDeviceHostKey(HKEY__ * *)
0x18001bf41  lea     rbp, WPP_GLOBAL_Control
0x18001bf48  mov     ebx, eax
0x18001bf4a  test    eax, eax
0x18001bf4c  jns     short loc_18001BF68
0x18001bf4e  test    ebx, ebx
0x18001bf50  jnz     loc_18001C01A
0x18001bf56  mov     eax, ebx
0x18001bf58  mov     rbx, [rsp+58h+arg_10]
0x18001bf5d  mov     rbp, [rsp+58h+arg_18]
0x18001bf62  add     rsp, 50h
0x18001bf66  pop     rdi
0x18001bf67  retn
0x18001bf68  mov     rcx, [rsp+58h+hKey]; hKey
0x18001bf6d  lea     rax, [rsp+58h+dwDisposition]
0x18001bf72  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x18001bf77  lea     rdx, aDescription; "Description"
0x18001bf7e  mov     [rsp+58h+phkResult], rdi; phkResult
0x18001bf83  xor     r9d, r9d; lpClass
0x18001bf86  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18001bf8f  xor     r8d, r8d; Reserved
0x18001bf92  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x18001bf9a  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18001bfa2  mov     [rsp+58h+dwDisposition], 0
0x18001bfaa  call    cs:__imp_RegCreateKeyExW
0x18001bfb0  mov     ebx, eax
0x18001bfb2  test    eax, eax
0x18001bfb4  jle     short loc_18001BFBF
0x18001bfb6  movzx   ebx, ax
0x18001bfb9  or      ebx, 80070000h
0x18001bfbf  test    ebx, ebx
0x18001bfc1  js      short loc_18001BFDF
0x18001bfc3  jnz     short loc_18001BFE6
0x18001bfc5  mov     rcx, [rsp+58h+hKey]; hKey
0x18001bfca  call    cs:__imp_RegCloseKey
0x18001bfd0  jmp     loc_18001BF4E
0x18001bfd5  mov     eax, 80004003h
0x18001bfda  jmp     loc_18001BF58
0x18001bfdf  mov     qword ptr [rdi], 0
0x18001bfe6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bfed  cmp     rcx, rbp
0x18001bff0  jz      short loc_18001BFC5
0x18001bff2  test    byte ptr [rcx+1Ch], 1
0x18001bff6  jz      short loc_18001BFC5
0x18001bff8  mov     rcx, [rcx+10h]
0x18001bffc  lea     r9, aHrregcreatekey; "HrRegCreateKeyEx"
0x18001c003  mov     edx, 0Ah
0x18001c008  mov     [rsp+58h+dwOptions], ebx
0x18001c00c  lea     r8, WPP_c680b5d87c9d36903333b9725f9279d1_Traceguids
0x18001c013  call    WPP_SF_sd
0x18001c018  jmp     short loc_18001BFC5
0x18001c01a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c021  cmp     rcx, rbp
0x18001c024  jz      loc_18001BF56
0x18001c02a  test    byte ptr [rcx+1Ch], 1
0x18001c02e  jz      loc_18001BF56
0x18001c034  mov     rcx, [rcx+10h]
0x18001c038  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x18001c03f  mov     edx, 79h ; 'y'
0x18001c044  mov     r9d, ebx
0x18001c047  call    WPP_SF_d
0x18001c04c  jmp     loc_18001BF56
```
