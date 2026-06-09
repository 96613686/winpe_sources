# HrCreateOrOpenProvidersKey(HKEY__ * *)

- ea: `0x18001dcac`
- end: `0x18001dded`
- name: `?HrCreateOrOpenProvidersKey@@YAJPEAPEAUHKEY__@@@Z`
- size: `321`
- prototype: `__int64 __fastcall(HKEY *)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180023530`
- `0x180032458`
- `0x1800487f0`
- `0x180048c90`
- `0x180048d40`

## callees

- `0x18000db4c`
- `0x18001c058`
- `0x18001dcac`
- `0x180038ce4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ddaf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ddaf`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001dd43`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001dd43`

## string_xrefs

- `0x18001dd7f`: `HrRegCreateKeyEx`

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
0x18001dcac  push    rbx
0x18001dcae  push    rbp
0x18001dcaf  push    rdi
0x18001dcb0  sub     rsp, 50h
0x18001dcb4  mov     rdi, rcx
0x18001dcb7  test    rcx, rcx
0x18001dcba  jnz     short loc_18001DCC6
0x18001dcbc  mov     eax, 80004003h
0x18001dcc1  jmp     loc_18001DDE5
0x18001dcc6  lea     rcx, [rsp+68h+hKey]; HKEY *
0x18001dcce  mov     [rsp+68h+hKey], 0
0x18001dcda  call    ?HrCreateOrOpenDeviceHostKey@@YAJPEAPEAUHKEY__@@@Z; HrCreateOrOpenDeviceHostKey(HKEY__ * *)
0x18001dcdf  lea     rbp, WPP_GLOBAL_Control
0x18001dce6  mov     ebx, eax
0x18001dce8  test    eax, eax
0x18001dcea  js      loc_18001DDB5
0x18001dcf0  mov     rcx, [rsp+68h+hKey]; hKey
0x18001dcf8  lea     rax, [rsp+68h+dwDisposition]
0x18001dcfd  mov     [rsp+68h+lpdwDisposition], rax; lpdwDisposition
0x18001dd02  lea     rdx, aProviders; "Providers"
0x18001dd09  lea     rax, [rsp+68h+arg_8]
0x18001dd0e  mov     [rsp+68h+arg_8], 0
0x18001dd17  mov     [rsp+68h+phkResult], rax; phkResult
0x18001dd1c  xor     r9d, r9d; lpClass
0x18001dd1f  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18001dd28  xor     r8d, r8d; Reserved
0x18001dd2b  mov     [rsp+68h+samDesired], 2001Fh; samDesired
0x18001dd33  mov     [rsp+68h+dwOptions], 0; dwOptions
0x18001dd3b  mov     [rsp+68h+dwDisposition], 0
0x18001dd43  call    cs:__imp_RegCreateKeyExW
0x18001dd49  mov     ebx, eax
0x18001dd4b  test    eax, eax
0x18001dd4d  jle     short loc_18001DD58
0x18001dd4f  movzx   ebx, ax
0x18001dd52  or      ebx, 80070000h
0x18001dd58  test    ebx, ebx
0x18001dd5a  jns     short loc_18001DD67
0x18001dd5c  mov     [rsp+68h+arg_8], 0
0x18001dd65  jmp     short loc_18001DD69
0x18001dd67  jz      short loc_18001DD9B
0x18001dd69  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dd70  cmp     rcx, rbp
0x18001dd73  jz      short loc_18001DD9B
0x18001dd75  test    byte ptr [rcx+1Ch], 1
0x18001dd79  jz      short loc_18001DD9B
0x18001dd7b  mov     rcx, [rcx+10h]
0x18001dd7f  lea     r9, aHrregcreatekey; "HrRegCreateKeyEx"
0x18001dd86  mov     edx, 0Ah
0x18001dd8b  mov     [rsp+68h+dwOptions], ebx
0x18001dd8f  lea     r8, WPP_c680b5d87c9d36903333b9725f9279d1_Traceguids
0x18001dd96  call    WPP_SF_sd
0x18001dd9b  test    ebx, ebx
0x18001dd9d  js      short loc_18001DDA7
0x18001dd9f  mov     rax, [rsp+68h+arg_8]
0x18001dda4  mov     [rdi], rax
0x18001dda7  mov     rcx, [rsp+68h+hKey]; hKey
0x18001ddaf  call    cs:__imp_RegCloseKey
0x18001ddb5  test    ebx, ebx
0x18001ddb7  jz      short loc_18001DDE3
0x18001ddb9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ddc0  cmp     rcx, rbp
0x18001ddc3  jz      short loc_18001DDE3
0x18001ddc5  test    byte ptr [rcx+1Ch], 1
0x18001ddc9  jz      short loc_18001DDE3
0x18001ddcb  mov     rcx, [rcx+10h]
0x18001ddcf  lea     r8, WPP_7ca04b3421e13ea3d8a938e31850813e_Traceguids
0x18001ddd6  mov     edx, 0Bh
0x18001dddb  mov     r9d, ebx
0x18001ddde  call    WPP_SF_d
0x18001dde3  mov     eax, ebx
0x18001dde5  add     rsp, 50h
0x18001dde9  pop     rdi
0x18001ddea  pop     rbp
0x18001ddeb  pop     rbx
0x18001ddec  retn
```
