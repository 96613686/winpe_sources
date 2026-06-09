# SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)

- ea: `0x14006b270`
- end: `0x14006b3e9`
- name: `?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z`
- size: `377`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, int, void **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14004dd50`

## callees

- `0x140053720`
- `0x14006b270`
- `0x14009cc54`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14006b317`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14006b37c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14006b317`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14006b37c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14006b2cc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14006b2cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14006b3a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14006b3a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14006b32e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14006b32e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14006b393`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14006b393`

## pseudocode

```c
__int64 __fastcall SHRegAllocData(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        void **a5)
{
  int v5; // esi
  LSTATUS v6; // eax
  int v7; // ebx
  LSTATUS ValueW; // eax
  void *pvData; // rax
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE Src[256]; // [rsp+50h] [rbp-B0h] BYREF

  hkey = a1;
  if ( aSoftwareMicros_42[0] )
  {
    v5 = 1;
    v6 = RegOpenKeyExW(a1, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\UserLogonTracing", 0, 1u, &hkey);
    a1 = hkey;
    v7 = v6;
  }
  else
  {
    v7 = 0;
    v5 = 0;
  }
  if ( v7 )
    goto LABEL_17;
  pcbData = 256;
  ValueW = RegGetValueW(a1, 0, L"UserLogonCorrelationId", 2u, 0, Src, &pcbData);
  v7 = ValueW;
  if ( !ValueW || ValueW == 234 )
  {
    pvData = CoTaskMemAlloc(pcbData);
    *a5 = pvData;
    if ( pvData )
    {
      if ( v7 )
      {
        if ( RegGetValueW(hkey, 0, L"UserLogonCorrelationId", 2u, 0, pvData, &pcbData) )
        {
          v7 = 1003;
          CoTaskMemFree(*a5);
        }
        else
        {
          v7 = 0;
        }
      }
      else
      {
        memcpy_0(pvData, Src, pcbData);
      }
    }
    else
    {
      v7 = 14;
    }
  }
  if ( v5 )
    RegCloseKey(hkey);
  if ( v7 )
  {
LABEL_17:
    *a5 = 0;
    if ( v7 > 0 )
      return (unsigned __int16)v7 | 0x80070000;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14006b270  mov     [rsp-8+arg_8], rbx
0x14006b275  mov     [rsp-8+arg_10], rsi
0x14006b27a  push    rbp
0x14006b27b  push    rdi
0x14006b27c  push    r14
0x14006b27e  lea     rbp, [rsp-60h]
0x14006b283  sub     rsp, 160h
0x14006b28a  mov     rax, cs:__security_cookie
0x14006b291  xor     rax, rsp
0x14006b294  mov     [rbp+70h+var_20], rax
0x14006b298  mov     rdi, [rbp+70h+arg_20]
0x14006b29f  xor     r14d, r14d
0x14006b2a2  cmp     word ptr cs:aSoftwareMicros_42, r14w; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x14006b2aa  mov     [rsp+170h+hkey], rcx
0x14006b2af  jz      short loc_14006B2DB
0x14006b2b1  lea     rax, [rsp+170h+hkey]
0x14006b2b6  xor     r8d, r8d; ulOptions
0x14006b2b9  lea     esi, [r14+1]
0x14006b2bd  mov     [rsp+170h+phkResult], rax; phkResult
0x14006b2c2  mov     r9d, esi; samDesired
0x14006b2c5  lea     rdx, aSoftwareMicros_42; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x14006b2cc  call    cs:__imp_RegOpenKeyExW
0x14006b2d2  mov     rcx, [rsp+170h+hkey]; hkey
0x14006b2d7  mov     ebx, eax
0x14006b2d9  jmp     short loc_14006B2E1
0x14006b2db  mov     ebx, r14d
0x14006b2de  mov     esi, r14d
0x14006b2e1  test    ebx, ebx
0x14006b2e3  jnz     loc_14006B3B3
0x14006b2e9  lea     rax, [rsp+170h+var_130]
0x14006b2ee  mov     [rsp+170h+var_130], 100h
0x14006b2f6  mov     [rsp+170h+pcbData], rax; pcbData
0x14006b2fb  lea     r9d, [rbx+2]; dwFlags
0x14006b2ff  lea     rax, [rsp+170h+Src]
0x14006b304  xor     edx, edx; lpSubKey
0x14006b306  mov     [rsp+170h+pvData], rax; pvData
0x14006b30b  lea     r8, aUserlogoncorre; "UserLogonCorrelationId"
0x14006b312  mov     [rsp+170h+phkResult], r14; pdwType
0x14006b317  call    cs:__imp_RegGetValueW
0x14006b31d  mov     ebx, eax
0x14006b31f  test    eax, eax
0x14006b321  jz      short loc_14006B32A
0x14006b323  cmp     eax, 0EAh
0x14006b328  jnz     short loc_14006B3A0
0x14006b32a  mov     ecx, [rsp+170h+var_130]; cb
0x14006b32e  call    cs:__imp_CoTaskMemAlloc
0x14006b334  mov     [rdi], rax
0x14006b337  test    rax, rax
0x14006b33a  jz      short loc_14006B39B
0x14006b33c  test    ebx, ebx
0x14006b33e  jnz     short loc_14006B354
0x14006b340  mov     r8d, [rsp+170h+var_130]; Size
0x14006b345  lea     rdx, [rsp+170h+Src]; Src
0x14006b34a  mov     rcx, rax; void *
0x14006b34d  call    memcpy_0
0x14006b352  jmp     short loc_14006B3A0
0x14006b354  lea     rcx, [rsp+170h+var_130]
0x14006b359  mov     r9d, 2; dwFlags
0x14006b35f  mov     [rsp+170h+pcbData], rcx; pcbData
0x14006b364  lea     r8, aUserlogoncorre; "UserLogonCorrelationId"
0x14006b36b  mov     rcx, [rsp+170h+hkey]; hkey
0x14006b370  xor     edx, edx; lpSubKey
0x14006b372  mov     [rsp+170h+pvData], rax; pvData
0x14006b377  mov     [rsp+170h+phkResult], r14; pdwType
0x14006b37c  call    cs:__imp_RegGetValueW
0x14006b382  test    eax, eax
0x14006b384  jnz     short loc_14006B38B
0x14006b386  mov     ebx, r14d
0x14006b389  jmp     short loc_14006B3A0
0x14006b38b  mov     rcx, [rdi]; pv
0x14006b38e  mov     ebx, 3EBh
0x14006b393  call    cs:__imp_CoTaskMemFree
0x14006b399  jmp     short loc_14006B3A0
0x14006b39b  mov     ebx, 0Eh
0x14006b3a0  test    esi, esi
0x14006b3a2  jz      short loc_14006B3AF
0x14006b3a4  mov     rcx, [rsp+170h+hkey]; hKey
0x14006b3a9  call    cs:__imp_RegCloseKey
0x14006b3af  test    ebx, ebx
0x14006b3b1  jz      short loc_14006B3C3
0x14006b3b3  mov     [rdi], r14
0x14006b3b6  test    ebx, ebx
0x14006b3b8  jle     short loc_14006B3C3
0x14006b3ba  movzx   ebx, bx
0x14006b3bd  or      ebx, 80070000h
0x14006b3c3  mov     eax, ebx
0x14006b3c5  mov     rcx, [rbp+70h+var_20]
0x14006b3c9  xor     rcx, rsp; StackCookie
0x14006b3cc  call    __security_check_cookie
0x14006b3d1  lea     r11, [rsp+170h+var_10]
0x14006b3d9  mov     rbx, [r11+28h]
0x14006b3dd  mov     rsi, [r11+30h]
0x14006b3e1  mov     rsp, r11
0x14006b3e4  pop     r14
0x14006b3e6  pop     rdi
0x14006b3e7  pop     rbp
0x14006b3e8  retn
```
