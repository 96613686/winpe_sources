# GetWpdDevicePathFromAnyPath(_GUID,ushort const *,ushort *,uint)

- ea: `0x18000e4d4`
- end: `0x18000e74e`
- name: `?GetWpdDevicePathFromAnyPath@@YAJU_GUID@@PEBGPEAGI@Z`
- size: `634`
- prototype: `__int64 __fastcall(GUID *AliasInterfaceClassGuid, PCWSTR DevicePath, unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callers

- `0x18000d63c`
- `0x18000d9b0`

## callees

- `0x18000e4d4`
- `0x180015700`
- `0x18002ff5c`
- `0x180035590`
- `0x1800361ba`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000e55b`
- `KERNEL32!GetLastError` at `0x18000e593`
- `KERNEL32!GetLastError` at `0x18000e5f3`
- `KERNEL32!GetLastError` at `0x18000e55b`
- `KERNEL32!GetLastError` at `0x18000e593`
- `KERNEL32!GetLastError` at `0x18000e5f3`
- `KERNEL32!HeapAlloc` at `0x18000e616`
- `KERNEL32!HeapAlloc` at `0x18000e616`
- `KERNEL32!GetProcessHeap` at `0x18000e603`
- `KERNEL32!GetProcessHeap` at `0x18000e603`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x18000e5e8`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x18000e656`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x18000e5e8`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x18000e656`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x18000e6e4`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x18000e6e4`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x18000e54c`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x18000e54c`
- `SETUPAPI!SetupDiGetDeviceInterfaceAlias` at `0x18000e5bf`
- `SETUPAPI!SetupDiGetDeviceInterfaceAlias` at `0x18000e5bf`
- `SETUPAPI!SetupDiOpenDeviceInterfaceW` at `0x18000e589`
- `SETUPAPI!SetupDiOpenDeviceInterfaceW` at `0x18000e589`

## pseudocode

```c
__int64 __fastcall GetWpdDevicePathFromAnyPath(GUID *AliasInterfaceClassGuid, PCWSTR DevicePath, unsigned __int16 *a3)
{
  unsigned __int16 *v3; // rdi
  unsigned int v6; // ebx
  HDEVINFO DeviceInfoList; // rax
  void *v8; // r14
  signed int LastError; // eax
  struct _SP_DEVICE_INTERFACE_DETAIL_DATA_W *v10; // rsi
  signed int v11; // eax
  DWORD v12; // ebx
  HANDLE ProcessHeap; // rax
  struct _SP_DEVICE_INTERFACE_DETAIL_DATA_W *v14; // rax
  __int64 v15; // rax
  WCHAR *v16; // rcx
  __int64 v17; // rdx
  unsigned __int16 *v18; // rcx
  DWORD DeviceInterfaceDetailDataSize; // [rsp+30h] [rbp-50h] BYREF
  struct _SP_DEVICE_INTERFACE_DATA AliasDeviceInterfaceData; // [rsp+38h] [rbp-48h] BYREF
  _SP_DEVICE_INTERFACE_DATA DeviceInterfaceData; // [rsp+58h] [rbp-28h] BYREF

  v3 = a3;
  memset(&DeviceInterfaceData, 0, sizeof(DeviceInterfaceData));
  memset(&AliasDeviceInterfaceData, 0, sizeof(AliasDeviceInterfaceData));
  if ( DevicePath && a3 )
  {
    *a3 = 0;
    DeviceInterfaceData.cbSize = 32;
    AliasDeviceInterfaceData.cbSize = 32;
    DeviceInfoList = SetupDiCreateDeviceInfoList(0, 0);
    v8 = DeviceInfoList;
    if ( DeviceInfoList == (HDEVINFO)-1LL )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_29;
    }
    v10 = 0;
    if ( SetupDiOpenDeviceInterfaceW(DeviceInfoList, DevicePath, 0, &DeviceInterfaceData) )
    {
      if ( SetupDiGetDeviceInterfaceAlias(v8, &DeviceInterfaceData, AliasInterfaceClassGuid, &AliasDeviceInterfaceData) )
      {
        DeviceInterfaceDetailDataSize = 0;
        if ( !SetupDiGetDeviceInterfaceDetailW(v8, &AliasDeviceInterfaceData, 0, 0, &DeviceInterfaceDetailDataSize, 0) )
        {
          v11 = GetLastError();
          v6 = v11;
          if ( v11 != 122 )
          {
LABEL_9:
            if ( v11 > 0 )
              v6 = (unsigned __int16)v11 | 0x80070000;
            goto LABEL_27;
          }
          v12 = DeviceInterfaceDetailDataSize;
          ProcessHeap = GetProcessHeap();
          v14 = (struct _SP_DEVICE_INTERFACE_DETAIL_DATA_W *)HeapAlloc(ProcessHeap, 8u, v12);
          v10 = v14;
          if ( !v14 )
          {
            v6 = -2147024882;
LABEL_27:
            SetupDiDestroyDeviceInfoList(v8);
            if ( v10 )
              operator delete(v10);
LABEL_29:
            if ( (v6 & 0x80000000) == 0 )
              return v6;
            goto LABEL_30;
          }
          memset_0(v14, 0, DeviceInterfaceDetailDataSize);
          v10->cbSize = 8;
          if ( SetupDiGetDeviceInterfaceDetailW(v8, &AliasDeviceInterfaceData, v10, DeviceInterfaceDetailDataSize, 0, 0) )
          {
            v15 = 2147483646;
            v16 = v10->DevicePath;
            v17 = 260;
            do
            {
              if ( !v15 )
                break;
              if ( !*v16 )
                break;
              *v3++ = *v16++;
              --v15;
              --v17;
            }
            while ( v17 );
            v18 = v3 - 1;
            v6 = v17 == 0 ? 0x8007007A : 0;
            if ( v17 )
              v18 = v3;
            *v18 = 0;
            if ( !v17 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_ca15e54dda593755eec8c8e0194d7ab1_Traceguids, v6);
            goto LABEL_27;
          }
        }
      }
    }
    v11 = GetLastError();
    v6 = v11;
    goto LABEL_9;
  }
  v6 = -2147467261;
LABEL_30:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_ca15e54dda593755eec8c8e0194d7ab1_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x18000e4d4  mov     [rsp-38h+arg_18], rbx
0x18000e4d9  push    rbp
0x18000e4da  push    rsi
0x18000e4db  push    rdi
0x18000e4dc  push    r12
0x18000e4de  push    r13
0x18000e4e0  push    r14
0x18000e4e2  push    r15
0x18000e4e4  mov     rbp, rsp
0x18000e4e7  sub     rsp, 80h
0x18000e4ee  mov     rax, cs:__security_cookie
0x18000e4f5  xor     rax, rsp
0x18000e4f8  mov     [rbp+var_8], rax
0x18000e4fc  xorps   xmm0, xmm0
0x18000e4ff  lea     r13, WPP_GLOBAL_Control
0x18000e506  xorps   xmm1, xmm1
0x18000e509  xor     r12d, r12d
0x18000e50c  mov     rdi, r8
0x18000e50f  mov     rbx, rdx
0x18000e512  mov     r15, rcx
0x18000e515  movups  xmmword ptr [rbp+DeviceInterfaceData.cbSize], xmm0
0x18000e519  movups  xmmword ptr [rbp+DeviceInterfaceData.InterfaceClassGuid.Data4+4], xmm0
0x18000e51d  movups  xmmword ptr [rbp+AliasDeviceInterfaceData.cbSize], xmm1
0x18000e521  movups  xmmword ptr [rbp+AliasDeviceInterfaceData.InterfaceClassGuid.Data4+4], xmm1
0x18000e525  test    rdx, rdx
0x18000e528  jnz     short loc_18000E534
0x18000e52a  mov     ebx, 80004003h
0x18000e52f  jmp     loc_18000E6FB
0x18000e534  test    r8, r8
0x18000e537  jz      short loc_18000E52A
0x18000e539  mov     eax, 20h ; ' '
0x18000e53e  mov     [r8], r12w
0x18000e542  xor     edx, edx; hwndParent
0x18000e544  mov     [rbp+DeviceInterfaceData.cbSize], eax
0x18000e547  xor     ecx, ecx; ClassGuid
0x18000e549  mov     [rbp+AliasDeviceInterfaceData.cbSize], eax
0x18000e54c  call    cs:__imp_SetupDiCreateDeviceInfoList
0x18000e552  mov     r14, rax
0x18000e555  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000e559  jnz     short loc_18000E579
0x18000e55b  call    cs:__imp_GetLastError
0x18000e561  mov     ebx, eax
0x18000e563  test    eax, eax
0x18000e565  jle     loc_18000E6F7
0x18000e56b  movzx   ebx, ax
0x18000e56e  or      ebx, 80070000h
0x18000e574  jmp     loc_18000E6F7
0x18000e579  lea     r9, [rbp+DeviceInterfaceData]; DeviceInterfaceData
0x18000e57d  xor     r8d, r8d; OpenFlags
0x18000e580  mov     rdx, rbx; DevicePath
0x18000e583  mov     rcx, r14; DeviceInfoSet
0x18000e586  mov     rsi, r12
0x18000e589  call    cs:__imp_SetupDiOpenDeviceInterfaceW
0x18000e58f  test    eax, eax
0x18000e591  jnz     short loc_18000E5B1
0x18000e593  call    cs:__imp_GetLastError
0x18000e599  mov     ebx, eax
0x18000e59b  test    eax, eax
0x18000e59d  jle     loc_18000E6E1
0x18000e5a3  movzx   ebx, ax
0x18000e5a6  or      ebx, 80070000h
0x18000e5ac  jmp     loc_18000E6E1
0x18000e5b1  lea     r9, [rbp+AliasDeviceInterfaceData]; AliasDeviceInterfaceData
0x18000e5b5  mov     r8, r15; AliasInterfaceClassGuid
0x18000e5b8  lea     rdx, [rbp+DeviceInterfaceData]; DeviceInterfaceData
0x18000e5bc  mov     rcx, r14; DeviceInfoSet
0x18000e5bf  call    cs:__imp_SetupDiGetDeviceInterfaceAlias
0x18000e5c5  test    eax, eax
0x18000e5c7  jz      short loc_18000E593
0x18000e5c9  lea     rax, [rbp+DeviceInterfaceDetailDataSize]
0x18000e5cd  mov     [rsp+80h+DeviceInfoData], r12; DeviceInfoData
0x18000e5d2  xor     r9d, r9d; DeviceInterfaceDetailDataSize
0x18000e5d5  mov     [rsp+80h+RequiredSize], rax; RequiredSize
0x18000e5da  xor     r8d, r8d; DeviceInterfaceDetailData
0x18000e5dd  mov     [rbp+DeviceInterfaceDetailDataSize], r12d
0x18000e5e1  lea     rdx, [rbp+AliasDeviceInterfaceData]; DeviceInterfaceData
0x18000e5e5  mov     rcx, r14; DeviceInfoSet
0x18000e5e8  call    cs:__imp_SetupDiGetDeviceInterfaceDetailW
0x18000e5ee  cmp     eax, 1
0x18000e5f1  jz      short loc_18000E593
0x18000e5f3  call    cs:__imp_GetLastError
0x18000e5f9  mov     ebx, eax
0x18000e5fb  cmp     eax, 7Ah ; 'z'
0x18000e5fe  jnz     short loc_18000E59B
0x18000e600  mov     ebx, [rbp+DeviceInterfaceDetailDataSize]
0x18000e603  call    cs:__imp_GetProcessHeap
0x18000e609  mov     r8d, ebx; dwBytes
0x18000e60c  mov     ebx, 8
0x18000e611  mov     edx, ebx; dwFlags
0x18000e613  mov     rcx, rax; hHeap
0x18000e616  call    cs:__imp_HeapAlloc
0x18000e61c  mov     rsi, rax
0x18000e61f  test    rax, rax
0x18000e622  jnz     short loc_18000E62E
0x18000e624  mov     ebx, 8007000Eh
0x18000e629  jmp     loc_18000E6E1
0x18000e62e  mov     r8d, [rbp+DeviceInterfaceDetailDataSize]; Size
0x18000e632  xor     edx, edx; Val
0x18000e634  mov     rcx, rsi; void *
0x18000e637  call    memset_0
0x18000e63c  mov     [rsi], ebx
0x18000e63e  lea     rdx, [rbp+AliasDeviceInterfaceData]; DeviceInterfaceData
0x18000e642  mov     r9d, [rbp+DeviceInterfaceDetailDataSize]; DeviceInterfaceDetailDataSize
0x18000e646  mov     r8, rsi; DeviceInterfaceDetailData
0x18000e649  mov     rcx, r14; DeviceInfoSet
0x18000e64c  mov     [rsp+80h+DeviceInfoData], r12; DeviceInfoData
0x18000e651  mov     [rsp+80h+RequiredSize], r12; RequiredSize
0x18000e656  call    cs:__imp_SetupDiGetDeviceInterfaceDetailW
0x18000e65c  test    eax, eax
0x18000e65e  jz      loc_18000E593
0x18000e664  mov     eax, 7FFFFFFEh
0x18000e669  lea     rcx, [rsi+4]
0x18000e66d  mov     edx, 104h
0x18000e672  test    rax, rax
0x18000e675  jz      short loc_18000E696
0x18000e677  movzx   r8d, word ptr [rcx]
0x18000e67b  test    r8w, r8w
0x18000e67f  jz      short loc_18000E696
0x18000e681  mov     [rdi], r8w
0x18000e685  add     rcx, 2
0x18000e689  add     rdi, 2
0x18000e68d  dec     rax
0x18000e690  sub     rdx, 1
0x18000e694  jnz     short loc_18000E672
0x18000e696  mov     rax, rdx
0x18000e699  lea     rcx, [rdi-2]
0x18000e69d  neg     rax
0x18000e6a0  sbb     ebx, ebx
0x18000e6a2  not     ebx
0x18000e6a4  and     ebx, 8007007Ah
0x18000e6aa  test    rdx, rdx
0x18000e6ad  cmovnz  rcx, rdi
0x18000e6b1  mov     [rcx], r12w
0x18000e6b5  jnz     short loc_18000E6E1
0x18000e6b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e6be  cmp     rcx, r13
0x18000e6c1  jz      short loc_18000E6E1
0x18000e6c3  test    byte ptr [rcx+1Ch], 2
0x18000e6c7  jz      short loc_18000E6E1
0x18000e6c9  mov     rcx, [rcx+10h]
0x18000e6cd  lea     r8, WPP_ca15e54dda593755eec8c8e0194d7ab1_Traceguids
0x18000e6d4  mov     edx, 17h
0x18000e6d9  mov     r9d, ebx
0x18000e6dc  call    WPP_SF_d
0x18000e6e1  mov     rcx, r14; DeviceInfoSet
0x18000e6e4  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x18000e6ea  test    rsi, rsi
0x18000e6ed  jz      short loc_18000E6F7
0x18000e6ef  mov     rcx, rsi; lpMem
0x18000e6f2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e6f7  test    ebx, ebx
0x18000e6f9  jns     short loc_18000E725
0x18000e6fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e702  cmp     rcx, r13
0x18000e705  jz      short loc_18000E725
0x18000e707  test    byte ptr [rcx+1Ch], 2
0x18000e70b  jz      short loc_18000E725
0x18000e70d  mov     rcx, [rcx+10h]
0x18000e711  lea     r8, WPP_ca15e54dda593755eec8c8e0194d7ab1_Traceguids
0x18000e718  mov     edx, 18h
0x18000e71d  mov     r9d, ebx
0x18000e720  call    WPP_SF_d
0x18000e725  mov     eax, ebx
0x18000e727  mov     rcx, [rbp+var_8]
0x18000e72b  xor     rcx, rsp; StackCookie
0x18000e72e  call    __security_check_cookie
0x18000e733  mov     rbx, [rsp+80h+arg_18]
0x18000e73b  add     rsp, 80h
0x18000e742  pop     r15
0x18000e744  pop     r14
0x18000e746  pop     r13
0x18000e748  pop     r12
0x18000e74a  pop     rdi
0x18000e74b  pop     rsi
0x18000e74c  pop     rbp
0x18000e74d  retn
```
