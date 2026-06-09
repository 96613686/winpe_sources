# GetDeviceInfDetails(ushort const *,ushort * *,ushort * *,ushort * *)

- ea: `0x18002b6d0`
- end: `0x18002bbbe`
- name: `?GetDeviceInfDetails@@YAJPEBGPEAPEAG11@Z`
- size: `1262`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPVOID *, LPVOID *, LPVOID *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002c0bc`

## callees

- `0x18000b8f8`
- `0x18000b98c`
- `0x18001ba64`
- `0x18002b6d0`
- `0x180047ea6`
- `0x180047ef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b733`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b7ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b8b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b9c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002baab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b733`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b7ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b8b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b9c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002baab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002b90e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002ba17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002baf6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002b90e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002ba17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002baf6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bb6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bb7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bb89`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bb6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bb7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bb89`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18002b724`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18002b724`
- `DEVOBJ!DevObjOpenDeviceInfo` at `0x18002b7e0`
- `DEVOBJ!DevObjOpenDeviceInfo` at `0x18002b7e0`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x18002b8a6`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x18002b9b6`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x18002baa1`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x18002b8a6`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x18002b9b6`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x18002baa1`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18002bb5a`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18002bb5a`

## string_xrefs

- `0x18002b77c`: `DevObjCreateDeviceInfoList FAILED`
- `0x18002b838`: `DevObjOpenDeviceInfo FAILED`

## pseudocode

```c
__int64 __fastcall GetDeviceInfDetails(const unsigned __int16 *a1, LPVOID *a2, LPVOID *a3, LPVOID *a4)
{
  __int64 DeviceInfoList; // rsi
  signed int LastError; // eax
  signed int v10; // ebx
  unsigned int v11; // eax
  signed int v12; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v14; // edx
  const char *v15; // rcx
  signed int v16; // eax
  unsigned __int16 *v17; // rax
  unsigned int v18; // eax
  int v19; // edx
  signed int v20; // eax
  unsigned __int16 *v21; // rax
  signed int v22; // eax
  unsigned __int16 *v23; // rax
  SIZE_T cb; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD v26[3]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE Src[528]; // [rsp+80h] [rbp-80h] BYREF

  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  if ( DeviceInfoList != -1 )
    goto LABEL_9;
  LastError = GetLastError();
  v10 = LastError;
  if ( LastError > 0 )
    v10 = (unsigned __int16)LastError | 0x80070000;
  if ( v10 >= 0 )
  {
LABEL_9:
    memset(v26, 0, sizeof(v26));
    LODWORD(v26[0]) = 48;
    if ( !(unsigned int)DevObjOpenDeviceInfo(DeviceInfoList, a1, 0, 0, v26) )
    {
      v12 = GetLastError();
      v10 = v12;
      if ( v12 > 0 )
        v10 = (unsigned __int16)v12 | 0x80070000;
      if ( v10 < 0 )
      {
        if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
          && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v14 = 23;
          v15 = "DevObjOpenDeviceInfo FAILED";
LABEL_17:
          WPP_SF_DsD(
            *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
            v14,
            (unsigned int)WPP_9f8b2618b856326daa1832c892715ef0_Traceguids,
            CurrentThreadActivityIdPrefix,
            (__int64)v15,
            v10);
        }
LABEL_61:
        if ( !DeviceInfoList )
          goto LABEL_63;
        goto LABEL_62;
      }
    }
    cb = 0;
    if ( !(unsigned int)DevObjGetDeviceProperty(
                          DeviceInfoList,
                          v26,
                          &DEVPKEY_Device_MatchingDeviceId,
                          (char *)&cb + 4,
                          Src,
                          520,
                          &cb,
                          0) )
    {
      v16 = GetLastError();
      v10 = v16;
      if ( v16 > 0 )
        v10 = (unsigned __int16)v16 | 0x80070000;
      if ( v10 < 0 )
      {
        if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) == 0
          || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
        {
          goto LABEL_61;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v14 = 24;
        goto LABEL_26;
      }
    }
    v17 = (unsigned __int16 *)CoTaskMemAlloc((unsigned int)cb);
    *a2 = v17;
    if ( !v17 )
    {
      if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) == 0
        || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
      {
        goto LABEL_33;
      }
      v18 = RdpWppGetCurrentThreadActivityIdPrefix();
      v19 = 25;
      goto LABEL_32;
    }
    memcpy_0(v17, Src, (unsigned int)cb);
    if ( !(unsigned int)DevObjGetDeviceProperty(
                          DeviceInfoList,
                          v26,
                          &DEVPKEY_Device_DriverInfPath,
                          (char *)&cb + 4,
                          Src,
                          520,
                          &cb,
                          0) )
    {
      v20 = GetLastError();
      v10 = v20;
      if ( v20 > 0 )
        v10 = (unsigned __int16)v20 | 0x80070000;
      if ( v10 < 0 )
      {
        if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) == 0
          || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
        {
          goto LABEL_61;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v14 = 26;
        goto LABEL_26;
      }
    }
    v21 = (unsigned __int16 *)CoTaskMemAlloc((unsigned int)cb);
    *a3 = v21;
    if ( v21 )
    {
      memcpy_0(v21, Src, (unsigned int)cb);
      if ( !(unsigned int)DevObjGetDeviceProperty(
                            DeviceInfoList,
                            v26,
                            &DEVPKEY_Device_Driver,
                            (char *)&cb + 4,
                            Src,
                            520,
                            &cb,
                            0) )
      {
        v22 = GetLastError();
        v10 = v22;
        if ( v22 > 0 )
          v10 = (unsigned __int16)v22 | 0x80070000;
        if ( v10 < 0 )
        {
          if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) == 0
            || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
          {
            goto LABEL_61;
          }
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v14 = 28;
LABEL_26:
          v15 = "DevObjGetDeviceProperty FAILED";
          goto LABEL_17;
        }
      }
      v23 = (unsigned __int16 *)CoTaskMemAlloc((unsigned int)cb);
      *a4 = v23;
      if ( v23 )
      {
        memcpy_0(v23, Src, (unsigned int)cb);
        v10 = 0;
        goto LABEL_61;
      }
      if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) == 0
        || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
      {
LABEL_33:
        v10 = -2147024882;
        goto LABEL_61;
      }
      v18 = RdpWppGetCurrentThreadActivityIdPrefix();
      v19 = 29;
    }
    else
    {
      if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) == 0
        || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
      {
        goto LABEL_33;
      }
      v18 = RdpWppGetCurrentThreadActivityIdPrefix();
      v19 = 27;
    }
LABEL_32:
    WPP_SF_Ds(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      v19,
      (unsigned int)WPP_9f8b2618b856326daa1832c892715ef0_Traceguids,
      v18,
      (__int64)"PBYTE");
    goto LABEL_33;
  }
  if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
    && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    v11 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsD(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      22,
      (unsigned int)WPP_9f8b2618b856326daa1832c892715ef0_Traceguids,
      v11,
      (__int64)"DevObjCreateDeviceInfoList FAILED",
      v10);
  }
LABEL_62:
  DevObjDestroyDeviceInfoList(DeviceInfoList);
LABEL_63:
  if ( v10 )
  {
    if ( *a2 )
      CoTaskMemFree(*a2);
    if ( *a3 )
      CoTaskMemFree(*a3);
    if ( *a4 )
      CoTaskMemFree(*a4);
    *a2 = 0;
    *a3 = 0;
    *a4 = 0;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18002b6d0  push    rbp
0x18002b6d2  push    rbx
0x18002b6d3  push    rsi
0x18002b6d4  push    rdi
0x18002b6d5  push    r12
0x18002b6d7  push    r13
0x18002b6d9  push    r14
0x18002b6db  push    r15
0x18002b6dd  lea     rbp, [rsp-1A8h]
0x18002b6e5  sub     rsp, 2A8h
0x18002b6ec  mov     rax, cs:__security_cookie
0x18002b6f3  xor     rax, rsp
0x18002b6f6  mov     [rbp+1E0h+var_50], rax
0x18002b6fd  xor     r13d, r13d
0x18002b700  mov     r14, r9
0x18002b703  mov     [rdx], r13
0x18002b706  mov     r12, r8
0x18002b709  mov     [r8], r13
0x18002b70c  mov     r15, rdx
0x18002b70f  mov     [r9], r13
0x18002b712  mov     rdi, rcx
0x18002b715  xor     r9d, r9d
0x18002b718  mov     [rsp+2E0h+var_2C0], r13
0x18002b71d  xor     r8d, r8d
0x18002b720  xor     edx, edx
0x18002b722  xor     ecx, ecx
0x18002b724  call    cs:__imp_DevObjCreateDeviceInfoList
0x18002b72a  mov     rsi, rax
0x18002b72d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002b731  jnz     short loc_18002B7B0
0x18002b733  call    cs:__imp_GetLastError
0x18002b739  mov     ebx, eax
0x18002b73b  test    eax, eax
0x18002b73d  jle     short loc_18002B748
0x18002b73f  movzx   ebx, ax
0x18002b742  or      ebx, 80070000h
0x18002b748  test    ebx, ebx
0x18002b74a  jns     short loc_18002B7B0
0x18002b74c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b753  lea     rax, WPP_GLOBAL_Control
0x18002b75a  cmp     rcx, rax
0x18002b75d  jz      loc_18002BB57
0x18002b763  test    byte ptr [rcx+1Ch], 8
0x18002b767  jz      loc_18002BB57
0x18002b76d  cmp     byte ptr [rcx+19h], 2
0x18002b771  jb      loc_18002BB57
0x18002b777  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002b77c  lea     rcx, aDevobjcreatede_0; "DevObjCreateDeviceInfoList FAILED"
0x18002b783  mov     [rsp+2E0h+var_2B8], ebx
0x18002b787  mov     [rsp+2E0h+var_2C0], rcx
0x18002b78c  lea     r8, WPP_9f8b2618b856326daa1832c892715ef0_Traceguids
0x18002b793  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b79a  mov     edx, 16h
0x18002b79f  mov     r9d, eax
0x18002b7a2  mov     rcx, [rcx+10h]
0x18002b7a6  call    WPP_SF_DsD
0x18002b7ab  jmp     loc_18002BB57
0x18002b7b0  xorps   xmm0, xmm0
0x18002b7b3  lea     rax, [rsp+2E0h+var_298]
0x18002b7b8  movups  [rsp+2E0h+var_298], xmm0
0x18002b7bd  xor     r9d, r9d
0x18002b7c0  mov     dword ptr [rsp+2E0h+var_298], 30h ; '0'
0x18002b7c8  xor     r8d, r8d
0x18002b7cb  mov     [rsp+2E0h+var_2C0], rax
0x18002b7d0  mov     rdx, rdi
0x18002b7d3  mov     rcx, rsi
0x18002b7d6  movups  [rsp+2E0h+var_288], xmm0
0x18002b7db  movups  [rsp+2E0h+var_278], xmm0
0x18002b7e0  call    cs:__imp_DevObjOpenDeviceInfo
0x18002b7e6  test    eax, eax
0x18002b7e8  jnz     short loc_18002B867
0x18002b7ea  call    cs:__imp_GetLastError
0x18002b7f0  mov     ebx, eax
0x18002b7f2  test    eax, eax
0x18002b7f4  jle     short loc_18002B7FF
0x18002b7f6  movzx   ebx, ax
0x18002b7f9  or      ebx, 80070000h
0x18002b7ff  test    ebx, ebx
0x18002b801  jns     short loc_18002B867
0x18002b803  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b80a  lea     rax, WPP_GLOBAL_Control
0x18002b811  cmp     rcx, rax
0x18002b814  jz      loc_18002BB52
0x18002b81a  test    byte ptr [rcx+1Ch], 8
0x18002b81e  jz      loc_18002BB52
0x18002b824  cmp     byte ptr [rcx+19h], 2
0x18002b828  jb      loc_18002BB52
0x18002b82e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002b833  mov     edx, 17h
0x18002b838  lea     rcx, aDevobjopendevi_2; "DevObjOpenDeviceInfo FAILED"
0x18002b83f  mov     [rsp+2E0h+var_2B8], ebx
0x18002b843  lea     r8, WPP_9f8b2618b856326daa1832c892715ef0_Traceguids
0x18002b84a  mov     [rsp+2E0h+var_2C0], rcx
0x18002b84f  mov     r9d, eax
0x18002b852  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b859  mov     rcx, [rcx+10h]
0x18002b85d  call    WPP_SF_DsD
0x18002b862  jmp     loc_18002BB52
0x18002b867  mov     [rsp+2E0h+var_2A8], r13d
0x18002b86c  lea     rax, [rsp+2E0h+cb]
0x18002b871  mov     [rsp+2E0h+var_2B0], rax
0x18002b876  lea     r9, [rsp+2E0h+cb+4]
0x18002b87b  lea     rax, [rbp+1E0h+Src]
0x18002b87f  mov     dword ptr [rsp+2E0h+cb+4], r13d
0x18002b884  mov     edi, 208h
0x18002b889  mov     dword ptr [rsp+2E0h+cb], r13d
0x18002b88e  mov     [rsp+2E0h+var_2B8], edi
0x18002b892  lea     r8, DEVPKEY_Device_MatchingDeviceId
0x18002b899  lea     rdx, [rsp+2E0h+var_298]
0x18002b89e  mov     [rsp+2E0h+var_2C0], rax
0x18002b8a3  mov     rcx, rsi
0x18002b8a6  call    cs:__imp_DevObjGetDeviceProperty
0x18002b8ac  test    eax, eax
0x18002b8ae  jnz     short loc_18002B90A
0x18002b8b0  call    cs:__imp_GetLastError
0x18002b8b6  mov     ebx, eax
0x18002b8b8  test    eax, eax
0x18002b8ba  jle     short loc_18002B8C5
0x18002b8bc  movzx   ebx, ax
0x18002b8bf  or      ebx, 80070000h
0x18002b8c5  test    ebx, ebx
0x18002b8c7  jns     short loc_18002B90A
0x18002b8c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b8d0  lea     rax, WPP_GLOBAL_Control
0x18002b8d7  cmp     rcx, rax
0x18002b8da  jz      loc_18002BB52
0x18002b8e0  test    byte ptr [rcx+1Ch], 8
0x18002b8e4  jz      loc_18002BB52
0x18002b8ea  cmp     byte ptr [rcx+19h], 2
0x18002b8ee  jb      loc_18002BB52
0x18002b8f4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002b8f9  mov     edx, 18h
0x18002b8fe  lea     rcx, aDevobjgetdevic_4; "DevObjGetDeviceProperty FAILED"
0x18002b905  jmp     loc_18002B83F
0x18002b90a  mov     ecx, dword ptr [rsp+2E0h+cb]; cb
0x18002b90e  call    cs:__imp_CoTaskMemAlloc
0x18002b914  mov     [r15], rax
0x18002b917  test    rax, rax
0x18002b91a  jnz     short loc_18002B975
0x18002b91c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b923  lea     rax, WPP_GLOBAL_Control
0x18002b92a  cmp     rcx, rax
0x18002b92d  jz      short loc_18002B96B
0x18002b92f  test    byte ptr [rcx+1Ch], 8
0x18002b933  jz      short loc_18002B96B
0x18002b935  cmp     byte ptr [rcx+19h], 2
0x18002b939  jb      short loc_18002B96B
0x18002b93b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002b940  mov     edx, 19h
0x18002b945  lea     rcx, aPbyte; "PBYTE"
0x18002b94c  mov     r9d, eax
0x18002b94f  mov     [rsp+2E0h+var_2C0], rcx
0x18002b954  lea     r8, WPP_9f8b2618b856326daa1832c892715ef0_Traceguids
0x18002b95b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b962  mov     rcx, [rcx+10h]
0x18002b966  call    WPP_SF_Ds
0x18002b96b  mov     ebx, 8007000Eh
0x18002b970  jmp     loc_18002BB52
0x18002b975  mov     r8d, dword ptr [rsp+2E0h+cb]; Size
0x18002b97a  lea     rdx, [rbp+1E0h+Src]; Src
0x18002b97e  mov     rcx, rax; void *
0x18002b981  call    memcpy_0
0x18002b986  mov     [rsp+2E0h+var_2A8], r13d
0x18002b98b  lea     rax, [rsp+2E0h+cb]
0x18002b990  mov     [rsp+2E0h+var_2B0], rax
0x18002b995  lea     r9, [rsp+2E0h+cb+4]
0x18002b99a  lea     rax, [rbp+1E0h+Src]
0x18002b99e  mov     [rsp+2E0h+var_2B8], edi
0x18002b9a2  lea     r8, DEVPKEY_Device_DriverInfPath
0x18002b9a9  mov     [rsp+2E0h+var_2C0], rax
0x18002b9ae  lea     rdx, [rsp+2E0h+var_298]
0x18002b9b3  mov     rcx, rsi
0x18002b9b6  call    cs:__imp_DevObjGetDeviceProperty
0x18002b9bc  test    eax, eax
0x18002b9be  jnz     short loc_18002BA13
0x18002b9c0  call    cs:__imp_GetLastError
0x18002b9c6  mov     ebx, eax
0x18002b9c8  test    eax, eax
0x18002b9ca  jle     short loc_18002B9D5
0x18002b9cc  movzx   ebx, ax
0x18002b9cf  or      ebx, 80070000h
0x18002b9d5  test    ebx, ebx
0x18002b9d7  jns     short loc_18002BA13
0x18002b9d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b9e0  lea     rax, WPP_GLOBAL_Control
0x18002b9e7  cmp     rcx, rax
0x18002b9ea  jz      loc_18002BB52
0x18002b9f0  test    byte ptr [rcx+1Ch], 8
0x18002b9f4  jz      loc_18002BB52
0x18002b9fa  cmp     byte ptr [rcx+19h], 2
0x18002b9fe  jb      loc_18002BB52
0x18002ba04  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002ba09  mov     edx, 1Ah
0x18002ba0e  jmp     loc_18002B8FE
0x18002ba13  mov     ecx, dword ptr [rsp+2E0h+cb]; cb
0x18002ba17  call    cs:__imp_CoTaskMemAlloc
0x18002ba1d  mov     [r12], rax
0x18002ba21  test    rax, rax
0x18002ba24  jnz     short loc_18002BA60
0x18002ba26  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ba2d  lea     rax, WPP_GLOBAL_Control
0x18002ba34  cmp     rcx, rax
0x18002ba37  jz      loc_18002B96B
0x18002ba3d  test    byte ptr [rcx+1Ch], 8
0x18002ba41  jz      loc_18002B96B
0x18002ba47  cmp     byte ptr [rcx+19h], 2
0x18002ba4b  jb      loc_18002B96B
0x18002ba51  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002ba56  mov     edx, 1Bh
0x18002ba5b  jmp     loc_18002B945
0x18002ba60  mov     r8d, dword ptr [rsp+2E0h+cb]; Size
0x18002ba65  lea     rdx, [rbp+1E0h+Src]; Src
0x18002ba69  mov     rcx, rax; void *
0x18002ba6c  call    memcpy_0
0x18002ba71  mov     [rsp+2E0h+var_2A8], r13d
0x18002ba76  lea     rax, [rsp+2E0h+cb]
0x18002ba7b  mov     [rsp+2E0h+var_2B0], rax
0x18002ba80  lea     r9, [rsp+2E0h+cb+4]
0x18002ba85  lea     rax, [rbp+1E0h+Src]
0x18002ba89  mov     [rsp+2E0h+var_2B8], edi
0x18002ba8d  lea     r8, DEVPKEY_Device_Driver
0x18002ba94  mov     [rsp+2E0h+var_2C0], rax
0x18002ba99  lea     rdx, [rsp+2E0h+var_298]
0x18002ba9e  mov     rcx, rsi
0x18002baa1  call    cs:__imp_DevObjGetDeviceProperty
0x18002baa7  test    eax, eax
0x18002baa9  jnz     short loc_18002BAF2
0x18002baab  call    cs:__imp_GetLastError
0x18002bab1  mov     ebx, eax
0x18002bab3  test    eax, eax
0x18002bab5  jle     short loc_18002BAC0
0x18002bab7  movzx   ebx, ax
0x18002baba  or      ebx, 80070000h
0x18002bac0  test    ebx, ebx
0x18002bac2  jns     short loc_18002BAF2
0x18002bac4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bacb  lea     rax, WPP_GLOBAL_Control
0x18002bad2  cmp     rcx, rax
0x18002bad5  jz      short loc_18002BB52
0x18002bad7  test    byte ptr [rcx+1Ch], 8
0x18002badb  jz      short loc_18002BB52
0x18002badd  cmp     byte ptr [rcx+19h], 2
0x18002bae1  jb      short loc_18002BB52
0x18002bae3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002bae8  mov     edx, 1Ch
0x18002baed  jmp     loc_18002B8FE
0x18002baf2  mov     ecx, dword ptr [rsp+2E0h+cb]; cb
0x18002baf6  call    cs:__imp_CoTaskMemAlloc
0x18002bafc  mov     [r14], rax
0x18002baff  test    rax, rax
0x18002bb02  jnz     short loc_18002BB3E
0x18002bb04  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bb0b  lea     rax, WPP_GLOBAL_Control
0x18002bb12  cmp     rcx, rax
0x18002bb15  jz      loc_18002B96B
0x18002bb1b  test    byte ptr [rcx+1Ch], 8
0x18002bb1f  jz      loc_18002B96B
0x18002bb25  cmp     byte ptr [rcx+19h], 2
0x18002bb29  jb      loc_18002B96B
0x18002bb2f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002bb34  mov     edx, 1Dh
0x18002bb39  jmp     loc_18002B945
0x18002bb3e  mov     r8d, dword ptr [rsp+2E0h+cb]; Size
0x18002bb43  lea     rdx, [rbp+1E0h+Src]; Src
0x18002bb47  mov     rcx, rax; void *
0x18002bb4a  call    memcpy_0
0x18002bb4f  mov     ebx, r13d
0x18002bb52  test    rsi, rsi
0x18002bb55  jz      short loc_18002BB60
0x18002bb57  mov     rcx, rsi
0x18002bb5a  call    cs:__imp_DevObjDestroyDeviceInfoList
0x18002bb60  test    ebx, ebx
0x18002bb62  jz      short loc_18002BB99
0x18002bb64  mov     rcx, [r15]; pv
0x18002bb67  test    rcx, rcx
0x18002bb6a  jz      short loc_18002BB72
0x18002bb6c  call    cs:__imp_CoTaskMemFree
0x18002bb72  mov     rcx, [r12]; pv
0x18002bb76  test    rcx, rcx
0x18002bb79  jz      short loc_18002BB81
0x18002bb7b  call    cs:__imp_CoTaskMemFree
0x18002bb81  mov     rcx, [r14]; pv
0x18002bb84  test    rcx, rcx
0x18002bb87  jz      short loc_18002BB8F
0x18002bb89  call    cs:__imp_CoTaskMemFree
0x18002bb8f  mov     [r15], r13
0x18002bb92  mov     [r12], r13
0x18002bb96  mov     [r14], r13
0x18002bb99  mov     eax, ebx
0x18002bb9b  mov     rcx, [rbp+1E0h+var_50]
0x18002bba2  xor     rcx, rsp; StackCookie
0x18002bba5  call    __security_check_cookie
0x18002bbaa  add     rsp, 2A8h
0x18002bbb1  pop     r15
0x18002bbb3  pop     r14
0x18002bbb5  pop     r13
0x18002bbb7  pop     r12
0x18002bbb9  pop     rdi
0x18002bbba  pop     rsi
0x18002bbbb  pop     rbx
  ... truncated ...
```
