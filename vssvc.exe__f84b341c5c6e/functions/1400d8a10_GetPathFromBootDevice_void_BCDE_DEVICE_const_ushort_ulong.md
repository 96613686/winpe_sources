# _GetPathFromBootDevice(void *,_BCDE_DEVICE const *,ushort *,ulong)

- ea: `0x1400d8a10`
- end: `0x1400d8c9c`
- name: `?_GetPathFromBootDevice@@YAHPEAXPEBU_BCDE_DEVICE@@PEAGK@Z`
- size: `652`
- prototype: `__int64 __fastcall(void *, const struct _BCDE_DEVICE *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400d8774`

## callees

- `0x140021ca0`
- `0x140022ec8`
- `0x1400235a8`
- `0x1400d257c`
- `0x1400d7ebc`
- `0x1400d8774`
- `0x1400d8a10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400d8c87`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400d8c87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d8bc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d8be7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d8c23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d8c44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d8bc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d8be7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d8c23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d8c44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d8c73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d8c73`
- `bcd!BcdOpenObject` at `0x1400d8b32`
- `bcd!BcdOpenObject` at `0x1400d8b76`
- `bcd!BcdOpenObject` at `0x1400d8b32`
- `bcd!BcdOpenObject` at `0x1400d8b76`
- `bcd!BcdCloseObject` at `0x1400d8c61`
- `bcd!BcdCloseObject` at `0x1400d8c61`

## string_xrefs

- `0x1400d8b13`: `pwszDevicePath`
- `0x1400d8b7c`: `::BcdOpenObject(hStore, &GUID_WINDOWS_BOOTMGR, &hBootMgr)`
- `0x1400d8a2c`: `_GetPathFromBootDevice`
- `0x1400d8c79`: `_GetPathFromBootDevice`
- `0x1400d8c4d`: `_GetPathFromBcdePath( hStore, pDevice, pwszDevicePath, cchDevicePath )`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall _GetPathFromBootDevice(
        void *a1,
        const struct _BCDE_DEVICE *a2,
        unsigned __int16 *a3,
        unsigned int a4)
{
  unsigned int v8; // ebx
  DWORD LastError; // edi
  struct _DRIVE_LAYOUT_INFORMATION_EX *v10; // rcx
  int v11; // edx
  const char *v12; // rax
  int v13; // eax
  int v14; // eax
  DWORD v15; // eax
  int v16; // edx
  const char *v17; // rcx
  void *v19; // [rsp+30h] [rbp-18h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-10h] BYREF
  unsigned int v21; // [rsp+88h] [rbp+40h] BYREF

  TraceFunctionEnter(L"_GetPathFromBootDevice");
  pv = 0;
  v19 = 0;
  v21 = 0;
  if ( !a2 )
  {
    v8 = 0;
    LastError = 87;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) == 0 )
    {
      goto LABEL_31;
    }
    v11 = 67;
    v12 = "pBcdeDevice";
LABEL_5:
    WPP_SF_Ds(
      *(_QWORD *)v10->Gpt.DiskId.Data4,
      v11,
      (unsigned int)WPP_124d85f99f08373ac6969d47c4dffa15_Traceguids,
      87,
      (__int64)v12);
    goto LABEL_29;
  }
  v8 = 1;
  if ( *(_DWORD *)a2 != 1 )
  {
    v8 = 0;
    LastError = 87;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) == 0 )
    {
      goto LABEL_31;
    }
    v11 = 68;
    v12 = "pBcdeDevice->DeviceType == BCDE_DEVICE_TYPE_BOOT_DEVICE";
    goto LABEL_5;
  }
  if ( !a3 )
  {
    v8 = 0;
    LastError = 87;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) == 0 )
    {
      goto LABEL_31;
    }
    v11 = 69;
    v12 = "pwszDevicePath";
    goto LABEL_5;
  }
  *a3 = 0;
  v13 = BcdOpenObject(a1, &GUID_WINDOWS_BOOTMGR, &v19);
  if ( v13 < 0 )
  {
    v8 = 0;
    LastError = WIN32_FROM_NTSTATUS((unsigned int)v13);
    if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
    {
      v14 = BcdOpenObject(a1, &GUID_WINDOWS_BOOTMGR, &v19);
      WPP_SF_Ds(
        *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
        70,
        (unsigned int)WPP_124d85f99f08373ac6969d47c4dffa15_Traceguids,
        v14,
        (__int64)"::BcdOpenObject(hStore, &GUID_WINDOWS_BOOTMGR, &hBootMgr)");
    }
    goto LABEL_29;
  }
  if ( (unsigned int)_GetElementData(v19, 0x11000001u, &pv, &v21) )
  {
    if ( (unsigned int)_GetPathFromBcdePath(a1, (const struct _BCDE_DEVICE *)pv, a3, a4) )
    {
      LastError = 0;
      goto LABEL_29;
    }
    v8 = 0;
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
    {
      v15 = GetLastError();
      v16 = 72;
      v17 = "_GetPathFromBcdePath( hStore, pDevice, pwszDevicePath, cchDevicePath )";
      goto LABEL_23;
    }
  }
  else
  {
    v8 = 0;
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
    {
      v15 = GetLastError();
      v16 = 71;
      v17 = "_GetElementData( hBootMgr, BCDE_LIBRARY_TYPE_APPLICATION_DEVICE, (PVOID*) &pDevice, &cbData)";
LABEL_23:
      WPP_SF_Ds(
        *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
        v16,
        (unsigned int)WPP_124d85f99f08373ac6969d47c4dffa15_Traceguids,
        v15,
        (__int64)v17);
    }
  }
LABEL_29:
  if ( v19 )
  {
    BcdCloseObject();
    v19 = 0;
  }
LABEL_31:
  CoTaskMemFree(pv);
  TraceFunctionExit(L"_GetPathFromBootDevice");
  SetLastError(LastError);
  return v8;
}

```

## disassembly

```asm
0x1400d8a10  push    rbp
0x1400d8a12  push    rbx
0x1400d8a13  push    rsi
0x1400d8a14  push    rdi
0x1400d8a15  push    r14
0x1400d8a17  push    r15
0x1400d8a19  mov     rbp, rsp
0x1400d8a1c  sub     rsp, 48h
0x1400d8a20  mov     r15d, r9d
0x1400d8a23  mov     rdi, r8
0x1400d8a26  mov     rsi, rdx
0x1400d8a29  mov     r14, rcx
0x1400d8a2c  lea     rcx, aGetpathfromboo; "_GetPathFromBootDevice"
0x1400d8a33  call    ?TraceFunctionEnter@@YAXPEAG@Z; TraceFunctionEnter(ushort *)
0x1400d8a38  mov     [rbp+pv], 0
0x1400d8a40  mov     [rbp+var_18], 0
0x1400d8a48  mov     [rbp+arg_8], 0
0x1400d8a4f  test    rsi, rsi
0x1400d8a52  jnz     short loc_1400D8AA2
0x1400d8a54  lea     r9d, [rsi+57h]
0x1400d8a58  xor     ebx, ebx
0x1400d8a5a  mov     edi, r9d
0x1400d8a5d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d8a64  lea     rax, WPP_GLOBAL_Control
0x1400d8a6b  cmp     rcx, rax
0x1400d8a6e  jz      loc_1400D8C6F
0x1400d8a74  test    byte ptr [rcx+1Ch], 8
0x1400d8a78  jz      loc_1400D8C6F
0x1400d8a7e  lea     edx, [rsi+43h]
0x1400d8a81  lea     rax, aPbcdedevice; "pBcdeDevice"
0x1400d8a88  mov     [rsp+48h+var_28], rax
0x1400d8a8d  mov     rcx, [rcx+10h]
0x1400d8a91  lea     r8, WPP_124d85f99f08373ac6969d47c4dffa15_Traceguids
0x1400d8a98  call    WPP_SF_Ds
0x1400d8a9d  jmp     loc_1400D8C58
0x1400d8aa2  mov     ebx, 1
0x1400d8aa7  cmp     [rsi], ebx
0x1400d8aa9  jz      short loc_1400D8AE1
0x1400d8aab  xor     ebx, ebx
0x1400d8aad  lea     r9d, [rbx+57h]
0x1400d8ab1  mov     edi, r9d
0x1400d8ab4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d8abb  lea     rax, WPP_GLOBAL_Control
0x1400d8ac2  cmp     rcx, rax
0x1400d8ac5  jz      loc_1400D8C6F
0x1400d8acb  test    byte ptr [rcx+1Ch], 8
0x1400d8acf  jz      loc_1400D8C6F
0x1400d8ad5  lea     edx, [rbx+44h]
0x1400d8ad8  lea     rax, aPbcdedeviceDev_0; "pBcdeDevice->DeviceType == BCDE_DEVICE_"...
0x1400d8adf  jmp     short loc_1400D8A88
0x1400d8ae1  test    rdi, rdi
0x1400d8ae4  jnz     short loc_1400D8B1F
0x1400d8ae6  lea     r9d, [rdi+57h]
0x1400d8aea  xor     ebx, ebx
0x1400d8aec  mov     edi, r9d
0x1400d8aef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d8af6  lea     rax, WPP_GLOBAL_Control
0x1400d8afd  cmp     rcx, rax
0x1400d8b00  jz      loc_1400D8C6F
0x1400d8b06  test    byte ptr [rcx+1Ch], 8
0x1400d8b0a  jz      loc_1400D8C6F
0x1400d8b10  lea     edx, [rbx+45h]
0x1400d8b13  lea     rax, aPwszdevicepath; "pwszDevicePath"
0x1400d8b1a  jmp     loc_1400D8A88
0x1400d8b1f  xor     eax, eax
0x1400d8b21  lea     r8, [rbp+var_18]
0x1400d8b25  lea     rdx, GUID_WINDOWS_BOOTMGR
0x1400d8b2c  mov     [rdi], ax
0x1400d8b2f  mov     rcx, r14
0x1400d8b32  call    cs:__imp_BcdOpenObject
0x1400d8b38  test    eax, eax
0x1400d8b3a  jns     short loc_1400D8BAA
0x1400d8b3c  xor     ebx, ebx
0x1400d8b3e  mov     ecx, eax
0x1400d8b40  call    WIN32_FROM_NTSTATUS
0x1400d8b45  mov     edi, eax
0x1400d8b47  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d8b4e  lea     rax, WPP_GLOBAL_Control
0x1400d8b55  cmp     rcx, rax
0x1400d8b58  jz      loc_1400D8C58
0x1400d8b5e  test    byte ptr [rcx+1Ch], 8
0x1400d8b62  jz      loc_1400D8C58
0x1400d8b68  lea     r8, [rbp+var_18]
0x1400d8b6c  mov     rcx, r14
0x1400d8b6f  lea     rdx, GUID_WINDOWS_BOOTMGR
0x1400d8b76  call    cs:__imp_BcdOpenObject
0x1400d8b7c  lea     rcx, aBcdopenobjectH; "::BcdOpenObject(hStore, &GUID_WINDOWS_B"...
0x1400d8b83  mov     r9d, eax
0x1400d8b86  mov     [rsp+48h+var_28], rcx
0x1400d8b8b  lea     edx, [rbx+46h]
0x1400d8b8e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d8b95  lea     r8, WPP_124d85f99f08373ac6969d47c4dffa15_Traceguids
0x1400d8b9c  mov     rcx, [rcx+10h]
0x1400d8ba0  call    WPP_SF_Ds
0x1400d8ba5  jmp     loc_1400D8C58
0x1400d8baa  mov     rcx, [rbp+var_18]; void *
0x1400d8bae  lea     r9, [rbp+arg_8]; unsigned int *
0x1400d8bb2  lea     r8, [rbp+pv]; void **
0x1400d8bb6  mov     edx, 11000001h; unsigned int
0x1400d8bbb  call    ?_GetElementData@@YAHPEAXKPEAPEAXPEAK@Z; _GetElementData(void *,ulong,void * *,ulong *)
0x1400d8bc0  test    eax, eax
0x1400d8bc2  jnz     short loc_1400D8C0B
0x1400d8bc4  xor     ebx, ebx
0x1400d8bc6  call    cs:__imp_GetLastError
0x1400d8bcc  mov     edi, eax
0x1400d8bce  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d8bd5  lea     rax, WPP_GLOBAL_Control
0x1400d8bdc  cmp     rcx, rax
0x1400d8bdf  jz      short loc_1400D8C58
0x1400d8be1  test    byte ptr [rcx+1Ch], 8
0x1400d8be5  jz      short loc_1400D8C58
0x1400d8be7  call    cs:__imp_GetLastError
0x1400d8bed  lea     edx, [rbx+47h]
0x1400d8bf0  lea     rcx, aGetelementdata_0; "_GetElementData( hBootMgr, BCDE_LIBRARY"...
0x1400d8bf7  mov     [rsp+48h+var_28], rcx
0x1400d8bfc  mov     r9d, eax
0x1400d8bff  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d8c06  jmp     loc_1400D8A8D
0x1400d8c0b  mov     rdx, [rbp+pv]; struct _BCDE_DEVICE *
0x1400d8c0f  mov     r9d, r15d; unsigned int
0x1400d8c12  mov     r8, rdi; unsigned __int16 *
0x1400d8c15  mov     rcx, r14; void *
0x1400d8c18  call    ?_GetPathFromBcdePath@@YAHPEAXPEBU_BCDE_DEVICE@@PEAGK@Z; _GetPathFromBcdePath(void *,_BCDE_DEVICE const *,ushort *,ulong)
0x1400d8c1d  test    eax, eax
0x1400d8c1f  jnz     short loc_1400D8C56
0x1400d8c21  xor     ebx, ebx
0x1400d8c23  call    cs:__imp_GetLastError
0x1400d8c29  mov     edi, eax
0x1400d8c2b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d8c32  lea     rax, WPP_GLOBAL_Control
0x1400d8c39  cmp     rcx, rax
0x1400d8c3c  jz      short loc_1400D8C58
0x1400d8c3e  test    byte ptr [rcx+1Ch], 8
0x1400d8c42  jz      short loc_1400D8C58
0x1400d8c44  call    cs:__imp_GetLastError
0x1400d8c4a  lea     edx, [rbx+48h]
0x1400d8c4d  lea     rcx, aGetpathfrombcd; "_GetPathFromBcdePath( hStore, pDevice, "...
0x1400d8c54  jmp     short loc_1400D8BF7
0x1400d8c56  xor     edi, edi
0x1400d8c58  mov     rcx, [rbp+var_18]
0x1400d8c5c  test    rcx, rcx
0x1400d8c5f  jz      short loc_1400D8C6F
0x1400d8c61  call    cs:__imp_BcdCloseObject
0x1400d8c67  mov     [rbp+var_18], 0
0x1400d8c6f  mov     rcx, [rbp+pv]; pv
0x1400d8c73  call    cs:__imp_CoTaskMemFree
0x1400d8c79  lea     rcx, aGetpathfromboo; "_GetPathFromBootDevice"
0x1400d8c80  call    ?TraceFunctionExit@@YAXPEAG@Z; TraceFunctionExit(ushort *)
0x1400d8c85  mov     ecx, edi; dwErrCode
0x1400d8c87  call    cs:__imp_SetLastError
0x1400d8c8d  mov     eax, ebx
0x1400d8c8f  add     rsp, 48h
0x1400d8c93  pop     r15
0x1400d8c95  pop     r14
0x1400d8c97  pop     rdi
0x1400d8c98  pop     rsi
0x1400d8c99  pop     rbx
0x1400d8c9a  pop     rbp
0x1400d8c9b  retn
```
