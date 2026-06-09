# HrCreateOrOpenDescriptionKey(HKEY__ * *)

- ea: `0x180010d88`
- end: `0x180010ed2`
- name: `?HrCreateOrOpenDescriptionKey@@YAJPEAPEAUHKEY__@@@Z`
- size: `330`
- prototype: `__int64 __fastcall(PHKEY phkResult)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000a5f0`
- `0x18000fdc0`
- `0x180010c98`
- `0x1800127ec`

## callees

- `0x180010d88`
- `0x180010ed8`
- `0x1800200f4`
- `0x18003b1cc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010e45`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010e45`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180010e1f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180010e1f`

## string_xrefs

- `0x180010e7d`: `HrRegCreateKeyEx`

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
0x180010d88  mov     rax, rsp
0x180010d8b  mov     [rax+18h], rbx
0x180010d8f  mov     [rax+20h], rbp
0x180010d93  push    rdi
0x180010d94  sub     rsp, 50h
0x180010d98  mov     rdi, rcx
0x180010d9b  test    rcx, rcx
0x180010d9e  jz      loc_180010E56
0x180010da4  lea     rcx, [rax+10h]; HKEY *
0x180010da8  mov     qword ptr [rax+10h], 0
0x180010db0  call    ?HrCreateOrOpenDeviceHostKey@@YAJPEAPEAUHKEY__@@@Z; HrCreateOrOpenDeviceHostKey(HKEY__ * *)
0x180010db5  lea     rbp, WPP_GLOBAL_Control
0x180010dbc  mov     ebx, eax
0x180010dbe  test    eax, eax
0x180010dc0  jns     short loc_180010DDD
0x180010dc2  test    ebx, ebx
0x180010dc4  jnz     loc_180010E9B
0x180010dca  mov     eax, ebx
0x180010dcc  mov     rbx, [rsp+58h+arg_10]
0x180010dd1  mov     rbp, [rsp+58h+arg_18]
0x180010dd6  add     rsp, 50h
0x180010dda  pop     rdi
0x180010ddb  retn
0x180010ddd  mov     rcx, [rsp+58h+hKey]; hKey
0x180010de2  lea     rax, [rsp+58h+dwDisposition]
0x180010de7  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x180010dec  lea     rdx, aDescription; "Description"
0x180010df3  mov     [rsp+58h+phkResult], rdi; phkResult
0x180010df8  xor     r9d, r9d; lpClass
0x180010dfb  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180010e04  xor     r8d, r8d; Reserved
0x180010e07  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x180010e0f  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180010e17  mov     [rsp+58h+dwDisposition], 0
0x180010e1f  call    cs:__imp_RegCreateKeyExW
0x180010e26  nop     dword ptr [rax+rax+00h]
0x180010e2b  mov     ebx, eax
0x180010e2d  test    eax, eax
0x180010e2f  jle     short loc_180010E3A
0x180010e31  movzx   ebx, ax
0x180010e34  or      ebx, 80070000h
0x180010e3a  test    ebx, ebx
0x180010e3c  js      short loc_180010E60
0x180010e3e  jnz     short loc_180010E67
0x180010e40  mov     rcx, [rsp+58h+hKey]; hKey
0x180010e45  call    cs:__imp_RegCloseKey
0x180010e4c  nop     dword ptr [rax+rax+00h]
0x180010e51  jmp     loc_180010DC2
0x180010e56  mov     eax, 80004003h
0x180010e5b  jmp     loc_180010DCC
0x180010e60  mov     qword ptr [rdi], 0
0x180010e67  mov     rcx, cs:WPP_GLOBAL_Control
0x180010e6e  cmp     rcx, rbp
0x180010e71  jz      short loc_180010E40
0x180010e73  test    byte ptr [rcx+1Ch], 1
0x180010e77  jz      short loc_180010E40
0x180010e79  mov     rcx, [rcx+10h]
0x180010e7d  lea     r9, aHrregcreatekey; "HrRegCreateKeyEx"
0x180010e84  mov     edx, 0Ah
0x180010e89  mov     [rsp+58h+dwOptions], ebx
0x180010e8d  lea     r8, WPP_c680b5d87c9d36903333b9725f9279d1_Traceguids
0x180010e94  call    WPP_SF_sd
0x180010e99  jmp     short loc_180010E40
0x180010e9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180010ea2  cmp     rcx, rbp
0x180010ea5  jz      loc_180010DCA
0x180010eab  test    byte ptr [rcx+1Ch], 1
0x180010eaf  jz      loc_180010DCA
0x180010eb5  mov     rcx, [rcx+10h]
0x180010eb9  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x180010ec0  mov     edx, 79h ; 'y'
0x180010ec5  mov     r9d, ebx
0x180010ec8  call    WPP_SF_d
0x180010ecd  jmp     loc_180010DCA
```
