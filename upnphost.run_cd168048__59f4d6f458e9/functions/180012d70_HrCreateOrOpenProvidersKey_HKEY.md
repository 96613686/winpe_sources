# HrCreateOrOpenProvidersKey(HKEY__ * *)

- ea: `0x180012d70`
- end: `0x180012ebe`
- name: `?HrCreateOrOpenProvidersKey@@YAJPEAPEAUHKEY__@@@Z`
- size: `334`
- prototype: `__int64 __fastcall(HKEY *)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180024230`
- `0x180034254`
- `0x18004b600`
- `0x18004bb10`
- `0x18004bbc0`

## callees

- `0x180010ed8`
- `0x180012d70`
- `0x1800200f4`
- `0x18003b1cc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012e79`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012e79`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180012e07`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180012e07`

## string_xrefs

- `0x180012e49`: `HrRegCreateKeyEx`

## pseudocode

```c
__int64 __fastcall HrCreateOrOpenProvidersKey(HKEY *a1)
{
  signed int v3; // ebx
  LSTATUS v4; // eax
  DWORD dwDisposition; // [rsp+70h] [rbp+8h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+18h] BYREF

  if ( !a1 )
    return 2147500035LL;
  hKey = 0;
  v3 = HrCreateOrOpenDeviceHostKey(&hKey);
  if ( v3 >= 0 )
  {
    phkResult = 0;
    dwDisposition = 0;
    v4 = RegCreateKeyExW(hKey, L"Providers", 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
    v3 = v4;
    if ( v4 > 0 )
      v3 = (unsigned __int16)v4 | 0x80070000;
    if ( v3 >= 0 )
    {
      if ( !v3 )
      {
LABEL_12:
        if ( v3 >= 0 )
          *a1 = phkResult;
        RegCloseKey(hKey);
        goto LABEL_15;
      }
    }
    else
    {
      phkResult = 0;
    }
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        (unsigned int)WPP_c680b5d87c9d36903333b9725f9279d1_Traceguids,
        (unsigned int)"HrRegCreateKeyEx",
        v3);
    goto LABEL_12;
  }
LABEL_15:
  if ( v3 && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_7ca04b3421e13ea3d8a938e31850813e_Traceguids, (unsigned int)v3);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180012d70  push    rbx
0x180012d72  push    rbp
0x180012d73  push    rdi
0x180012d74  sub     rsp, 50h
0x180012d78  mov     rdi, rcx
0x180012d7b  test    rcx, rcx
0x180012d7e  jnz     short loc_180012D8A
0x180012d80  mov     eax, 80004003h
0x180012d85  jmp     loc_180012EB5
0x180012d8a  lea     rcx, [rsp+68h+hKey]; HKEY *
0x180012d92  mov     [rsp+68h+hKey], 0
0x180012d9e  call    ?HrCreateOrOpenDeviceHostKey@@YAJPEAPEAUHKEY__@@@Z; HrCreateOrOpenDeviceHostKey(HKEY__ * *)
0x180012da3  lea     rbp, WPP_GLOBAL_Control
0x180012daa  mov     ebx, eax
0x180012dac  test    eax, eax
0x180012dae  js      loc_180012E85
0x180012db4  mov     rcx, [rsp+68h+hKey]; hKey
0x180012dbc  lea     rax, [rsp+68h+dwDisposition]
0x180012dc1  mov     [rsp+68h+lpdwDisposition], rax; lpdwDisposition
0x180012dc6  lea     rdx, aProviders; "Providers"
0x180012dcd  lea     rax, [rsp+68h+arg_8]
0x180012dd2  mov     [rsp+68h+arg_8], 0
0x180012ddb  mov     [rsp+68h+phkResult], rax; phkResult
0x180012de0  xor     r9d, r9d; lpClass
0x180012de3  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180012dec  xor     r8d, r8d; Reserved
0x180012def  mov     [rsp+68h+samDesired], 2001Fh; samDesired
0x180012df7  mov     [rsp+68h+dwOptions], 0; dwOptions
0x180012dff  mov     [rsp+68h+dwDisposition], 0
0x180012e07  call    cs:__imp_RegCreateKeyExW
0x180012e0e  nop     dword ptr [rax+rax+00h]
0x180012e13  mov     ebx, eax
0x180012e15  test    eax, eax
0x180012e17  jle     short loc_180012E22
0x180012e19  movzx   ebx, ax
0x180012e1c  or      ebx, 80070000h
0x180012e22  test    ebx, ebx
0x180012e24  jns     short loc_180012E31
0x180012e26  mov     [rsp+68h+arg_8], 0
0x180012e2f  jmp     short loc_180012E33
0x180012e31  jz      short loc_180012E65
0x180012e33  mov     rcx, cs:WPP_GLOBAL_Control
0x180012e3a  cmp     rcx, rbp
0x180012e3d  jz      short loc_180012E65
0x180012e3f  test    byte ptr [rcx+1Ch], 1
0x180012e43  jz      short loc_180012E65
0x180012e45  mov     rcx, [rcx+10h]
0x180012e49  lea     r9, aHrregcreatekey; "HrRegCreateKeyEx"
0x180012e50  mov     edx, 0Ah
0x180012e55  mov     [rsp+68h+dwOptions], ebx
0x180012e59  lea     r8, WPP_c680b5d87c9d36903333b9725f9279d1_Traceguids
0x180012e60  call    WPP_SF_sd
0x180012e65  test    ebx, ebx
0x180012e67  js      short loc_180012E71
0x180012e69  mov     rax, [rsp+68h+arg_8]
0x180012e6e  mov     [rdi], rax
0x180012e71  mov     rcx, [rsp+68h+hKey]; hKey
0x180012e79  call    cs:__imp_RegCloseKey
0x180012e80  nop     dword ptr [rax+rax+00h]
0x180012e85  test    ebx, ebx
0x180012e87  jz      short loc_180012EB3
0x180012e89  mov     rcx, cs:WPP_GLOBAL_Control
0x180012e90  cmp     rcx, rbp
0x180012e93  jz      short loc_180012EB3
0x180012e95  test    byte ptr [rcx+1Ch], 1
0x180012e99  jz      short loc_180012EB3
0x180012e9b  mov     rcx, [rcx+10h]
0x180012e9f  lea     r8, WPP_7ca04b3421e13ea3d8a938e31850813e_Traceguids
0x180012ea6  mov     edx, 0Bh
0x180012eab  mov     r9d, ebx
0x180012eae  call    WPP_SF_d
0x180012eb3  mov     eax, ebx
0x180012eb5  add     rsp, 50h
0x180012eb9  pop     rdi
0x180012eba  pop     rbp
0x180012ebb  pop     rbx
0x180012ebc  retn
```
