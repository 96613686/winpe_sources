# CallerIdentity::GetStateRegKey(void *,ushort const *,ulong,HKEY__ * *)

- ea: `0x18036fe28`
- end: `0x18036ffbd`
- name: `?GetStateRegKey@CallerIdentity@@YAJPEAXPEBGKPEAPEAUHKEY__@@@Z`
- size: `405`
- prototype: `int(CallerIdentity *__hidden this, void *, const unsigned __int16 *, unsigned int, HKEY *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180110788`
- `0x18013ad78`
- `0x1802bb370`

## callees

- `0x180047224`
- `0x18005f2d0`
- `0x180067bec`
- `0x18036fe28`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18036ff80`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18036ff80`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18036ff03`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18036ff35`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18036ff03`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18036ff35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18036fe96`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18036ffa7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18036fe96`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18036ffa7`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x18036fe5c`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x18036fed2`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x18036fe5c`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x18036fed2`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetStateRegKey(
        CallerIdentity *this,
        const WCHAR *a2,
        const unsigned __int16 *a3,
        HKEY *a4)
{
  REGSAM samDesired; // r12d
  int Error; // edi
  int v9; // edx
  int v10; // ecx
  LSTATUS v11; // eax
  LSTATUS v12; // eax
  LSTATUS Key; // eax
  HKEY hKey; // [rsp+58h] [rbp-20h] BYREF
  HKEY v16[3]; // [rsp+60h] [rbp-18h] BYREF
  int v17; // [rsp+C8h] [rbp+50h] BYREF

  *a4 = 0;
  samDesired = (unsigned int)a3;
  v17 = 0;
  if ( (unsigned int)GetSystemAppDataKey(this, 0, 0, &v17) )
  {
    return (unsigned int)-2147418113;
  }
  else
  {
    Error = ResultFromKnownLastError();
    if ( Error == -2147024774 && v17 )
    {
      CoTaskMemFree(0);
      Error = _AllocStringWorker<CTCoAllocPolicy>(v10, v9, 0, v17);
      if ( Error >= 0 )
      {
        hKey = 0;
        if ( (unsigned int)GetSystemAppDataKey(this, &hKey, 0, &v17) || (Error = ResultFromKnownLastError(), Error >= 0) )
        {
          if ( a2 )
          {
            v16[0] = 0;
            v12 = RegOpenKeyExW(hKey, 0, 0, 0x2001Fu, v16);
            Error = v12;
            if ( v12 > 0 )
              Error = (unsigned __int16)v12 | 0x80070000;
            if ( Error >= 0 )
            {
              Key = RegCreateKeyExW(v16[0], a2, 0, 0, 0, samDesired, 0, a4, 0);
              Error = Key;
              if ( Key > 0 )
                Error = (unsigned __int16)Key | 0x80070000;
            }
            CAutoHandle<HKEY__ *>::~CAutoHandle<HKEY__ *>(v16);
          }
          else
          {
            v11 = RegOpenKeyExW(hKey, 0, 0, samDesired, a4);
            Error = v11;
            if ( v11 > 0 )
              Error = (unsigned __int16)v11 | 0x80070000;
          }
        }
        CAutoHandle<HKEY__ *>::~CAutoHandle<HKEY__ *>(&hKey);
      }
      CoTaskMemFree(0);
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18036fe28  push    rbp
0x18036fe2a  push    rsi
0x18036fe2b  push    rdi
0x18036fe2c  push    r12
0x18036fe2e  push    r14
0x18036fe30  push    r15
0x18036fe32  mov     rbp, rsp
0x18036fe35  sub     rsp, 78h
0x18036fe39  mov     r15, r9
0x18036fe3c  mov     qword ptr [r9], 0
0x18036fe43  mov     r12d, r8d
0x18036fe46  mov     [rbp+arg_18], 0
0x18036fe4d  mov     r14, rdx
0x18036fe50  lea     r9, [rbp+arg_18]
0x18036fe54  xor     r8d, r8d
0x18036fe57  xor     edx, edx
0x18036fe59  mov     rsi, rcx
0x18036fe5c  call    cs:__imp_GetSystemAppDataKey
0x18036fe62  test    eax, eax
0x18036fe64  jz      short loc_18036FE70
0x18036fe66  mov     edi, 8000FFFFh
0x18036fe6b  jmp     loc_18036FFAD
0x18036fe70  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18036fe75  mov     edi, eax
0x18036fe77  cmp     eax, 8007007Ah
0x18036fe7c  jnz     loc_18036FFAD
0x18036fe82  cmp     [rbp+arg_18], 0
0x18036fe86  jbe     loc_18036FFAD
0x18036fe8c  xor     ecx, ecx; pv
0x18036fe8e  mov     [rbp+lpSubKey], 0
0x18036fe96  call    cs:__imp_CoTaskMemFree
0x18036fe9c  mov     r9d, [rbp+arg_18]
0x18036fea0  lea     rax, [rbp+lpSubKey]
0x18036fea4  xor     r8d, r8d
0x18036fea7  mov     qword ptr [rsp+78h+samDesired], rax
0x18036feac  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x18036feb1  mov     edi, eax
0x18036feb3  test    eax, eax
0x18036feb5  js      loc_18036FFA3
0x18036febb  mov     r8, [rbp+lpSubKey]
0x18036febf  lea     r9, [rbp+arg_18]
0x18036fec3  lea     rdx, [rbp+hKey]
0x18036fec7  mov     [rbp+hKey], 0
0x18036fecf  mov     rcx, rsi
0x18036fed2  call    cs:__imp_GetSystemAppDataKey
0x18036fed8  test    eax, eax
0x18036feda  jnz     short loc_18036FEEB
0x18036fedc  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18036fee1  mov     edi, eax
0x18036fee3  test    eax, eax
0x18036fee5  js      loc_18036FF9A
0x18036feeb  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x18036feef  xor     r8d, r8d; ulOptions
0x18036fef2  mov     rcx, [rbp+hKey]; hKey
0x18036fef6  test    r14, r14
0x18036fef9  jnz     short loc_18036FF1E
0x18036fefb  mov     r9d, r12d; samDesired
0x18036fefe  mov     [rsp+78h+phkResult], r15; phkResult
0x18036ff03  call    cs:__imp_RegOpenKeyExW
0x18036ff09  mov     edi, eax
0x18036ff0b  test    eax, eax
0x18036ff0d  jle     loc_18036FF9A
0x18036ff13  movzx   edi, ax
0x18036ff16  or      edi, 80070000h
0x18036ff1c  jmp     short loc_18036FF9A
0x18036ff1e  lea     rax, [rbp+var_18]
0x18036ff22  mov     [rbp+var_18], 0
0x18036ff2a  mov     r9d, 2001Fh; samDesired
0x18036ff30  mov     [rsp+78h+phkResult], rax; phkResult
0x18036ff35  call    cs:__imp_RegOpenKeyExW
0x18036ff3b  mov     edi, eax
0x18036ff3d  mov     esi, 80070000h
0x18036ff42  test    eax, eax
0x18036ff44  jle     short loc_18036FF4B
0x18036ff46  movzx   edi, ax
0x18036ff49  or      edi, esi
0x18036ff4b  test    edi, edi
0x18036ff4d  js      short loc_18036FF91
0x18036ff4f  mov     rcx, [rbp+var_18]; hKey
0x18036ff53  xor     r9d, r9d; lpClass
0x18036ff56  mov     [rsp+78h+lpdwDisposition], 0; lpdwDisposition
0x18036ff5f  xor     r8d, r8d; Reserved
0x18036ff62  mov     [rsp+78h+var_40], r15; phkResult
0x18036ff67  mov     rdx, r14; lpSubKey
0x18036ff6a  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18036ff73  mov     [rsp+78h+samDesired], r12d; samDesired
0x18036ff78  mov     dword ptr [rsp+78h+phkResult], 0; dwOptions
0x18036ff80  call    cs:__imp_RegCreateKeyExW
0x18036ff86  mov     edi, eax
0x18036ff88  test    eax, eax
0x18036ff8a  jle     short loc_18036FF91
0x18036ff8c  movzx   edi, ax
0x18036ff8f  or      edi, esi
0x18036ff91  lea     rcx, [rbp+var_18]
0x18036ff95  call    ??1?$CAutoHandle@PEAUHKEY__@@@@QEAA@XZ; CAutoHandle<HKEY__ *>::~CAutoHandle<HKEY__ *>(void)
0x18036ff9a  lea     rcx, [rbp+hKey]
0x18036ff9e  call    ??1?$CAutoHandle@PEAUHKEY__@@@@QEAA@XZ; CAutoHandle<HKEY__ *>::~CAutoHandle<HKEY__ *>(void)
0x18036ffa3  mov     rcx, [rbp+lpSubKey]; pv
0x18036ffa7  call    cs:__imp_CoTaskMemFree
0x18036ffad  mov     eax, edi
0x18036ffaf  add     rsp, 78h
0x18036ffb3  pop     r15
0x18036ffb5  pop     r14
0x18036ffb7  pop     r12
0x18036ffb9  pop     rdi
0x18036ffba  pop     rsi
0x18036ffbb  pop     rbp
0x18036ffbc  retn
```
