# SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)

- ea: `0x18003e978`
- end: `0x18003eaf8`
- name: `?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z`
- size: `384`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *, int, void **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180041f98`

## callees

- `0x180002280`
- `0x18003e978`
- `0x180055758`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003eab9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003eab9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003e9c7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003e9c7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003ea10`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003ea85`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003ea10`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003ea85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003eaa1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003eaa1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003ea31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003ea31`

## pseudocode

```c
__int64 __fastcall SHRegAllocData(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        void **a5)
{
  LSTATUS v6; // ebx
  LSTATUS ValueW; // eax
  void *pvData; // rax
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE Src[256]; // [rsp+50h] [rbp-B0h] BYREF

  hkey = HKEY_CURRENT_USER;
  v6 = RegOpenKeyExW(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Wallpapers\\Images",
         0,
         1u,
         &hkey);
  if ( v6 )
    goto LABEL_12;
  pcbData = 256;
  ValueW = RegGetValueW(hkey, 0, a3, 2u, 0, Src, &pcbData);
  v6 = ValueW;
  if ( !ValueW || ValueW == 234 )
  {
    pvData = CoTaskMemAlloc(pcbData);
    *a5 = pvData;
    if ( pvData )
    {
      if ( v6 )
      {
        if ( RegGetValueW(hkey, 0, a3, 2u, 0, pvData, &pcbData) )
        {
          v6 = 1003;
          CoTaskMemFree(*a5);
        }
        else
        {
          v6 = 0;
        }
      }
      else
      {
        memcpy_0(pvData, Src, pcbData);
      }
    }
    else
    {
      v6 = 14;
    }
  }
  RegCloseKey(hkey);
  if ( v6 )
  {
LABEL_12:
    *a5 = 0;
    if ( v6 > 0 )
      return (unsigned __int16)v6 | 0x80070000;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003e978  push    rbp
0x18003e97a  push    rbx
0x18003e97b  push    rsi
0x18003e97c  push    rdi
0x18003e97d  lea     rbp, [rsp-68h]
0x18003e982  sub     rsp, 168h
0x18003e989  mov     rax, cs:__security_cookie
0x18003e990  xor     rax, rsp
0x18003e993  mov     [rbp+80h+var_30], rax
0x18003e997  mov     rdi, [rbp+80h+arg_20]
0x18003e99e  lea     rax, [rsp+180h+hkey]
0x18003e9a3  mov     rsi, r8
0x18003e9a6  mov     [rsp+180h+phkResult], rax; phkResult
0x18003e9ab  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18003e9b2  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003e9b9  xor     r8d, r8d; ulOptions
0x18003e9bc  mov     [rsp+180h+hkey], rcx
0x18003e9c1  mov     r9d, 1; samDesired
0x18003e9c7  call    cs:__imp_RegOpenKeyExW
0x18003e9ce  nop     dword ptr [rax+rax+00h]
0x18003e9d3  mov     ebx, eax
0x18003e9d5  test    eax, eax
0x18003e9d7  jnz     loc_18003EAC9
0x18003e9dd  mov     rcx, [rsp+180h+hkey]; hkey
0x18003e9e2  lea     rax, [rsp+180h+var_140]
0x18003e9e7  mov     [rsp+180h+pcbData], rax; pcbData
0x18003e9ec  lea     r9d, [rbx+2]; dwFlags
0x18003e9f0  lea     rax, [rsp+180h+Src]
0x18003e9f5  mov     [rsp+180h+var_140], 100h
0x18003e9fd  mov     [rsp+180h+pvData], rax; pvData
0x18003ea02  mov     r8, rsi; lpValue
0x18003ea05  xor     edx, edx; lpSubKey
0x18003ea07  mov     [rsp+180h+phkResult], 0; pdwType
0x18003ea10  call    cs:__imp_RegGetValueW
0x18003ea17  nop     dword ptr [rax+rax+00h]
0x18003ea1c  mov     ebx, eax
0x18003ea1e  test    eax, eax
0x18003ea20  jz      short loc_18003EA2D
0x18003ea22  cmp     eax, 0EAh
0x18003ea27  jnz     loc_18003EAB4
0x18003ea2d  mov     ecx, [rsp+180h+var_140]; cb
0x18003ea31  call    cs:__imp_CoTaskMemAlloc
0x18003ea38  nop     dword ptr [rax+rax+00h]
0x18003ea3d  mov     [rdi], rax
0x18003ea40  test    rax, rax
0x18003ea43  jz      short loc_18003EAAF
0x18003ea45  test    ebx, ebx
0x18003ea47  jnz     short loc_18003EA5D
0x18003ea49  mov     r8d, [rsp+180h+var_140]; Size
0x18003ea4e  lea     rdx, [rsp+180h+Src]; Src
0x18003ea53  mov     rcx, rax; void *
0x18003ea56  call    memcpy_0
0x18003ea5b  jmp     short loc_18003EAB4
0x18003ea5d  lea     rcx, [rsp+180h+var_140]
0x18003ea62  mov     r9d, 2; dwFlags
0x18003ea68  mov     [rsp+180h+pcbData], rcx; pcbData
0x18003ea6d  mov     r8, rsi; lpValue
0x18003ea70  mov     rcx, [rsp+180h+hkey]; hkey
0x18003ea75  xor     edx, edx; lpSubKey
0x18003ea77  mov     [rsp+180h+pvData], rax; pvData
0x18003ea7c  mov     [rsp+180h+phkResult], 0; pdwType
0x18003ea85  call    cs:__imp_RegGetValueW
0x18003ea8c  nop     dword ptr [rax+rax+00h]
0x18003ea91  test    eax, eax
0x18003ea93  jnz     short loc_18003EA99
0x18003ea95  xor     ebx, ebx
0x18003ea97  jmp     short loc_18003EAB4
0x18003ea99  mov     rcx, [rdi]; pv
0x18003ea9c  mov     ebx, 3EBh
0x18003eaa1  call    cs:__imp_CoTaskMemFree
0x18003eaa8  nop     dword ptr [rax+rax+00h]
0x18003eaad  jmp     short loc_18003EAB4
0x18003eaaf  mov     ebx, 0Eh
0x18003eab4  mov     rcx, [rsp+180h+hkey]; hKey
0x18003eab9  call    cs:__imp_RegCloseKey
0x18003eac0  nop     dword ptr [rax+rax+00h]
0x18003eac5  test    ebx, ebx
0x18003eac7  jz      short loc_18003EADD
0x18003eac9  mov     qword ptr [rdi], 0
0x18003ead0  test    ebx, ebx
0x18003ead2  jle     short loc_18003EADD
0x18003ead4  movzx   ebx, bx
0x18003ead7  or      ebx, 80070000h
0x18003eadd  mov     eax, ebx
0x18003eadf  mov     rcx, [rbp+80h+var_30]
0x18003eae3  xor     rcx, rsp; StackCookie
0x18003eae6  call    __security_check_cookie
0x18003eaeb  add     rsp, 168h
0x18003eaf2  pop     rdi
0x18003eaf3  pop     rsi
0x18003eaf4  pop     rbx
0x18003eaf5  pop     rbp
0x18003eaf6  retn
```
