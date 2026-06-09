# SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)

- ea: `0x18005f67c`
- end: `0x18005f7f6`
- name: `?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z`
- size: `378`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, int, void **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18005f5d4`

## callees

- `0x18005f67c`
- `0x18008a030`
- `0x18008e5a2`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005f724`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005f789`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005f724`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005f789`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005f6d9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005f6d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005f7b6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005f7b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005f73b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005f73b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005f7a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005f7a0`

## string_xrefs

- `0x18005f718`: `Extension`
- `0x18005f771`: `Extension`

## pseudocode

```c
__int64 __fastcall SHRegAllocData(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        void **a5)
{
  HKEY v5; // rcx
  int v6; // esi
  LSTATUS v7; // eax
  int v8; // ebx
  LSTATUS ValueW; // eax
  void *pvData; // rax
  DWORD pcbData[4]; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE Src[256]; // [rsp+60h] [rbp-A0h] BYREF

  v5 = HKEY_CLASSES_ROOT;
  hkey = HKEY_CLASSES_ROOT;
  if ( a2 && *a2 )
  {
    v6 = 1;
    v7 = RegOpenKeyExW(HKEY_CLASSES_ROOT, a2, 0, 1u, &hkey);
    v5 = hkey;
    v8 = v7;
  }
  else
  {
    v8 = 0;
    v6 = 0;
  }
  if ( v8 )
    goto LABEL_18;
  pcbData[0] = 256;
  ValueW = RegGetValueW(v5, 0, L"Extension", 2u, 0, Src, pcbData);
  v8 = ValueW;
  if ( !ValueW || ValueW == 234 )
  {
    pvData = CoTaskMemAlloc(pcbData[0]);
    *a5 = pvData;
    if ( pvData )
    {
      if ( v8 )
      {
        if ( RegGetValueW(hkey, 0, L"Extension", 2u, 0, pvData, pcbData) )
        {
          v8 = 1003;
          CoTaskMemFree(*a5);
        }
        else
        {
          v8 = 0;
        }
      }
      else
      {
        memcpy_0(pvData, Src, pcbData[0]);
      }
    }
    else
    {
      v8 = 14;
    }
  }
  if ( v6 )
    RegCloseKey(hkey);
  if ( v8 )
  {
LABEL_18:
    *a5 = 0;
    if ( v8 > 0 )
      return (unsigned __int16)v8 | 0x80070000;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18005f67c  mov     [rsp-8+arg_0], rbx
0x18005f681  mov     [rsp-8+arg_10], rsi
0x18005f686  push    rbp
0x18005f687  push    rdi
0x18005f688  push    r14
0x18005f68a  lea     rbp, [rsp-70h]
0x18005f68f  sub     rsp, 170h
0x18005f696  mov     rax, cs:__security_cookie
0x18005f69d  xor     rax, rsp
0x18005f6a0  mov     [rbp+80h+var_20], rax
0x18005f6a4  mov     rdi, [rbp+80h+arg_20]
0x18005f6ab  xor     r14d, r14d
0x18005f6ae  mov     rcx, 0FFFFFFFF80000000h; hkey
0x18005f6b5  mov     [rsp+180h+hkey], rcx
0x18005f6ba  test    rdx, rdx
0x18005f6bd  jz      short loc_18005F6E8
0x18005f6bf  cmp     [rdx], r14w
0x18005f6c3  jz      short loc_18005F6E8
0x18005f6c5  lea     rax, [rsp+180h+hkey]
0x18005f6ca  xor     r8d, r8d; ulOptions
0x18005f6cd  lea     esi, [r14+1]
0x18005f6d1  mov     [rsp+180h+phkResult], rax; phkResult
0x18005f6d6  mov     r9d, esi; samDesired
0x18005f6d9  call    cs:__imp_RegOpenKeyExW
0x18005f6df  mov     rcx, [rsp+180h+hkey]
0x18005f6e4  mov     ebx, eax
0x18005f6e6  jmp     short loc_18005F6EE
0x18005f6e8  mov     ebx, r14d
0x18005f6eb  mov     esi, r14d
0x18005f6ee  test    ebx, ebx
0x18005f6f0  jnz     loc_18005F7C0
0x18005f6f6  lea     rax, [rsp+180h+var_140]
0x18005f6fb  mov     [rsp+180h+var_140], 100h
0x18005f703  mov     [rsp+180h+pcbData], rax; pcbData
0x18005f708  lea     r9d, [rbx+2]; dwFlags
0x18005f70c  lea     rax, [rsp+180h+Src]
0x18005f711  xor     edx, edx; lpSubKey
0x18005f713  mov     [rsp+180h+pvData], rax; pvData
0x18005f718  lea     r8, aExtension; "Extension"
0x18005f71f  mov     [rsp+180h+phkResult], r14; pdwType
0x18005f724  call    cs:__imp_RegGetValueW
0x18005f72a  mov     ebx, eax
0x18005f72c  test    eax, eax
0x18005f72e  jz      short loc_18005F737
0x18005f730  cmp     eax, 0EAh
0x18005f735  jnz     short loc_18005F7AD
0x18005f737  mov     ecx, [rsp+180h+var_140]; cb
0x18005f73b  call    cs:__imp_CoTaskMemAlloc
0x18005f741  mov     [rdi], rax
0x18005f744  test    rax, rax
0x18005f747  jz      short loc_18005F7A8
0x18005f749  test    ebx, ebx
0x18005f74b  jnz     short loc_18005F761
0x18005f74d  mov     r8d, [rsp+180h+var_140]; Size
0x18005f752  lea     rdx, [rsp+180h+Src]; Src
0x18005f757  mov     rcx, rax; void *
0x18005f75a  call    memcpy_0
0x18005f75f  jmp     short loc_18005F7AD
0x18005f761  lea     rcx, [rsp+180h+var_140]
0x18005f766  mov     r9d, 2; dwFlags
0x18005f76c  mov     [rsp+180h+pcbData], rcx; pcbData
0x18005f771  lea     r8, aExtension; "Extension"
0x18005f778  mov     rcx, [rsp+180h+hkey]; hkey
0x18005f77d  xor     edx, edx; lpSubKey
0x18005f77f  mov     [rsp+180h+pvData], rax; pvData
0x18005f784  mov     [rsp+180h+phkResult], r14; pdwType
0x18005f789  call    cs:__imp_RegGetValueW
0x18005f78f  test    eax, eax
0x18005f791  jnz     short loc_18005F798
0x18005f793  mov     ebx, r14d
0x18005f796  jmp     short loc_18005F7AD
0x18005f798  mov     rcx, [rdi]; pv
0x18005f79b  mov     ebx, 3EBh
0x18005f7a0  call    cs:__imp_CoTaskMemFree
0x18005f7a6  jmp     short loc_18005F7AD
0x18005f7a8  mov     ebx, 0Eh
0x18005f7ad  test    esi, esi
0x18005f7af  jz      short loc_18005F7BC
0x18005f7b1  mov     rcx, [rsp+180h+hkey]; hKey
0x18005f7b6  call    cs:__imp_RegCloseKey
0x18005f7bc  test    ebx, ebx
0x18005f7be  jz      short loc_18005F7D0
0x18005f7c0  mov     [rdi], r14
0x18005f7c3  test    ebx, ebx
0x18005f7c5  jle     short loc_18005F7D0
0x18005f7c7  movzx   ebx, bx
0x18005f7ca  or      ebx, 80070000h
0x18005f7d0  mov     eax, ebx
0x18005f7d2  mov     rcx, [rbp+80h+var_20]
0x18005f7d6  xor     rcx, rsp; StackCookie
0x18005f7d9  call    __security_check_cookie
0x18005f7de  lea     r11, [rsp+180h+var_10]
0x18005f7e6  mov     rbx, [r11+20h]
0x18005f7ea  mov     rsi, [r11+30h]
0x18005f7ee  mov     rsp, r11
0x18005f7f1  pop     r14
0x18005f7f3  pop     rdi
0x18005f7f4  pop     rbp
0x18005f7f5  retn
```
