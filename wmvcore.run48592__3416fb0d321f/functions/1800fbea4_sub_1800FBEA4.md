# sub_1800FBEA4

- ea: `0x1800fbea4`
- end: `0x1800fbf41`
- name: `sub_1800FBEA4`
- size: `157`
- prototype: ``
- caller_count: `16`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18002a5e4`
- `0x18002bf80`
- `0x180061dac`
- `0x1800c4b30`
- `0x1800fb548`
- `0x1800fb7dc`
- `0x1800fb8f0`
- `0x1800fb98c`
- `0x1800fba0c`
- `0x1800fbacc`
- `0x1800fbb8c`
- `0x1800fbc54`
- `0x1800fbd6c`
- `0x1800fbf48`
- `0x1800fbfdc`
- `0x1800fc08c`

## callees

- `0x1800fbea4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800fbf2b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800fbf2b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800fbed9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800fbed9`

## pseudocode

```c
LSTATUS __fastcall sub_1800FBEA4(
        __int64 a1,
        __int64 a2,
        int a3,
        int a4,
        HKEY *phkResult,
        __int64 a6,
        DWORD dwDisposition)
{
  _BOOL8 v7; // r10
  bool v8; // zf
  const WCHAR *v9; // rdx
  HKEY v10; // rcx
  LSTATUS result; // eax

  v7 = a3 >= 4;
  v8 = a4 == 0;
  v9 = off_18017BB50[a3];
  v10 = (HKEY)(v7 - 0x80000000LL);
  if ( v8 )
  {
    result = RegOpenKeyExW(v10, v9, 0, 0x20019u, phkResult);
  }
  else
  {
    dwDisposition = 0;
    result = RegCreateKeyExW(v10, v9, 0, 0, 0, 0x2001Fu, 0, phkResult, &dwDisposition);
  }
  if ( !result )
    return 0;
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800fbea4  sub     rsp, 58h
0x1800fbea8  xor     r10d, r10d
0x1800fbeab  movsxd  rax, edx
0x1800fbeae  cmp     edx, 4
0x1800fbeb1  lea     rdx, off_18017BB50; "Windows Media\\WMSDK\\AudioEncode"
0x1800fbeb8  setnl   r10b
0x1800fbebc  test    ecx, ecx
0x1800fbebe  mov     rdx, [rdx+rax*8]; lpSubKey
0x1800fbec2  lea     rcx, [r10-80000000h]; hKey
0x1800fbec9  jnz     short loc_1800FBEF5
0x1800fbecb  mov     [rsp+58h+phkResult], r8; phkResult
0x1800fbed0  mov     r9d, 20019h; samDesired
0x1800fbed6  xor     r8d, r8d; ulOptions
0x1800fbed9  call    cs:RegOpenKeyExW
0x1800fbee0  nop     dword ptr [rax+rax+00h]
0x1800fbee5  test    eax, eax
0x1800fbee7  jz      short loc_1800FBF39
0x1800fbee9  jle     short loc_1800FBF3B
0x1800fbeeb  movzx   eax, ax
0x1800fbeee  or      eax, 80070000h
0x1800fbef3  jmp     short loc_1800FBF3B
0x1800fbef5  lea     rax, [rsp+58h+dwDisposition]
0x1800fbefa  mov     [rsp+58h+dwDisposition], 0
0x1800fbf02  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x1800fbf07  xor     r9d, r9d; lpClass
0x1800fbf0a  mov     [rsp+58h+var_20], r8; phkResult
0x1800fbf0f  xor     r8d, r8d; Reserved
0x1800fbf12  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800fbf1b  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x1800fbf23  mov     dword ptr [rsp+58h+phkResult], 0; dwOptions
0x1800fbf2b  call    cs:RegCreateKeyExW
0x1800fbf32  nop     dword ptr [rax+rax+00h]
0x1800fbf37  jmp     short loc_1800FBEE5
0x1800fbf39  xor     eax, eax
0x1800fbf3b  add     rsp, 58h
0x1800fbf3f  retn
```
