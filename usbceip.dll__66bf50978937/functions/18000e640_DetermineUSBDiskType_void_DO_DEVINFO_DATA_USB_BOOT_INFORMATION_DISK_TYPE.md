# DetermineUSBDiskType(void *,_DO_DEVINFO_DATA,_USB_BOOT_INFORMATION_DISK_TYPE *)

- ea: `0x18000e640`
- end: `0x18000e921`
- name: `?DetermineUSBDiskType@@YAKPEAXU_DO_DEVINFO_DATA@@PEAW4_USB_BOOT_INFORMATION_DISK_TYPE@@@Z`
- size: `737`
- prototype: `__int64 __fastcall(__int64, _OWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x18000efd4`

## callees

- `0x180002410`
- `0x180002e3e`
- `0x180002e4a`
- `0x180002e56`
- `0x18000e640`
- `0x18000f32c`
- `0x18000fe84`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e6f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e6fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e7d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e7e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e8c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e6f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e6fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e7d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e7e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e8c8`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x18000e6e6`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x18000e7ce`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x18000e6e6`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x18000e7ce`
- `DEVOBJ!DevObjOpenDeviceInfo` at `0x18000e766`
- `DEVOBJ!DevObjOpenDeviceInfo` at `0x18000e766`

## pseudocode

```c
__int64 __fastcall DetermineUSBDiskType(__int64 a1, _OWORD *a2, _DWORD *a3)
{
  size_t v3; // rdi
  __int128 v5; // xmm1
  _WORD *v6; // rbx
  __int128 v8; // xmm0
  __int64 v9; // r8
  DWORD LastError; // edi
  __int64 v11; // r8
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  size_t Size[2]; // [rsp+40h] [rbp-19h] BYREF
  _OWORD v18[3]; // [rsp+50h] [rbp-9h] BYREF

  LODWORD(v3) = 0;
  v5 = a2[1];
  v6 = 0;
  v18[0] = *a2;
  v8 = a2[2];
  v18[1] = v5;
  v18[2] = v8;
  Size[0] = 0;
  while ( 1 )
  {
LABEL_2:
    if ( LODWORD(Size[0]) != (_DWORD)v3 )
    {
      v3 = LODWORD(Size[0]);
      if ( v6 )
        free(v6);
      v6 = o_malloc_0(v3);
      if ( !v6 )
      {
        LastError = 14;
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v15 = 28;
LABEL_32:
          WPP_SF_D(v14[2], v15, v9, 14);
        }
        return LastError;
      }
      *v6 = 0;
    }
    if ( (unsigned int)DevObjGetDeviceProperty(a1, v18, &DEVPKEY_Device_Parent, (char *)Size + 4, v6, v3, Size, 0) )
      break;
    if ( GetLastError() != 122 )
    {
      LastError = GetLastError();
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v13 = 29;
LABEL_12:
        WPP_SF_D(v12[2], v13, v11, LastError);
        goto LABEL_42;
      }
      goto LABEL_42;
    }
  }
  if ( !wcscmp_0(v6, L"HTREE\\ROOT\\0") )
  {
    LastError = 15;
  }
  else
  {
    if ( (unsigned int)DevObjOpenDeviceInfo(a1, v6, 0, 0, v18) )
    {
      while ( 1 )
      {
        if ( LODWORD(Size[0]) != (_DWORD)v3 )
        {
          v3 = LODWORD(Size[0]);
          if ( v6 )
            free(v6);
          v6 = o_malloc_0(v3);
          if ( !v6 )
          {
            LastError = 14;
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v15 = 31;
              goto LABEL_32;
            }
            return LastError;
          }
          *v6 = 0;
        }
        if ( (unsigned int)DevObjGetDeviceProperty(a1, v18, &DEVPKEY_Device_Service, (char *)Size + 4, v6, v3, Size, 0) )
        {
          if ( !v6 )
            goto LABEL_2;
          if ( wcsnicmp(v6, L"usbstor", 7u) )
          {
            if ( wcsnicmp(v6, L"uaspstor", 8u) )
              goto LABEL_2;
            *a3 = 1;
          }
          else
          {
            *a3 = 0;
          }
          LastError = 0;
          goto LABEL_43;
        }
        if ( GetLastError() != 122 )
        {
          LastError = GetLastError();
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v13 = 32;
            goto LABEL_12;
          }
          goto LABEL_42;
        }
      }
    }
    LastError = GetLastError();
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = 30;
      goto LABEL_12;
    }
  }
LABEL_42:
  if ( v6 )
LABEL_43:
    free(v6);
  return LastError;
}

```

## disassembly

```asm
0x18000e640  push    rbp
0x18000e642  push    rbx
0x18000e643  push    rsi
0x18000e644  push    rdi
0x18000e645  push    r14
0x18000e647  lea     rbp, [rsp-37h]
0x18000e64c  sub     rsp, 90h
0x18000e653  mov     rax, cs:__security_cookie
0x18000e65a  xor     rax, rsp
0x18000e65d  mov     [rbp+57h+var_30], rax
0x18000e661  movups  xmm0, xmmword ptr [rdx]
0x18000e664  xor     edi, edi
0x18000e666  mov     rsi, r8
0x18000e669  movups  xmm1, xmmword ptr [rdx+10h]
0x18000e66d  xor     ebx, ebx
0x18000e66f  mov     r14, rcx
0x18000e672  movaps  [rbp+57h+var_60], xmm0
0x18000e676  movups  xmm0, xmmword ptr [rdx+20h]
0x18000e67a  mov     dword ptr [rbp+57h+Size+4], 0
0x18000e681  movaps  [rbp+57h+var_50], xmm1
0x18000e685  movaps  [rbp+57h+var_40], xmm0
0x18000e689  mov     dword ptr [rbp+57h+Size], ebx
0x18000e68c  cmp     dword ptr [rbp+57h+Size], edi
0x18000e68f  jz      short loc_18000E6BA
0x18000e691  mov     edi, dword ptr [rbp+57h+Size]
0x18000e694  test    rbx, rbx
0x18000e697  jz      short loc_18000E6A1
0x18000e699  mov     rcx, rbx; Block
0x18000e69c  call    free
0x18000e6a1  mov     rcx, rdi; Size
0x18000e6a4  call    _o_malloc_0
0x18000e6a9  mov     rbx, rax
0x18000e6ac  test    rax, rax
0x18000e6af  jz      loc_18000E861
0x18000e6b5  xor     eax, eax
0x18000e6b7  mov     [rbx], ax
0x18000e6ba  mov     [rsp+0B0h+var_78], 0
0x18000e6c2  lea     rax, [rbp+57h+Size]
0x18000e6c6  mov     [rsp+0B0h+var_80], rax
0x18000e6cb  lea     r9, [rbp+57h+Size+4]
0x18000e6cf  mov     [rsp+0B0h+var_88], edi
0x18000e6d3  lea     r8, DEVPKEY_Device_Parent
0x18000e6da  lea     rdx, [rbp+57h+var_60]
0x18000e6de  mov     [rsp+0B0h+var_90], rbx
0x18000e6e3  mov     rcx, r14
0x18000e6e6  call    cs:__imp_DevObjGetDeviceProperty
0x18000e6ec  test    eax, eax
0x18000e6ee  jnz     short loc_18000E73A
0x18000e6f0  call    cs:__imp_GetLastError
0x18000e6f6  cmp     eax, 7Ah ; 'z'
0x18000e6f9  jz      short loc_18000E68C
0x18000e6fb  call    cs:__imp_GetLastError
0x18000e701  mov     edi, eax
0x18000e703  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e70a  lea     rax, WPP_GLOBAL_Control
0x18000e711  cmp     rcx, rax
0x18000e714  jz      loc_18000E8F8
0x18000e71a  test    byte ptr [rcx+1Ch], 1
0x18000e71e  jz      loc_18000E8F8
0x18000e724  mov     edx, 1Dh
0x18000e729  mov     rcx, [rcx+10h]
0x18000e72d  mov     r9d, edi
0x18000e730  call    WPP_SF_D
0x18000e735  jmp     loc_18000E8F8
0x18000e73a  lea     rdx, aHtreeRoot0; "HTREE\\ROOT\\0"
0x18000e741  mov     rcx, rbx; String1
0x18000e744  call    wcscmp_0
0x18000e749  test    eax, eax
0x18000e74b  jz      loc_18000E8F3
0x18000e751  lea     rax, [rbp+57h+var_60]
0x18000e755  xor     r9d, r9d
0x18000e758  xor     r8d, r8d
0x18000e75b  mov     [rsp+0B0h+var_90], rax
0x18000e760  mov     rdx, rbx
0x18000e763  mov     rcx, r14
0x18000e766  call    cs:__imp_DevObjOpenDeviceInfo
0x18000e76c  test    eax, eax
0x18000e76e  jz      loc_18000E8C8
0x18000e774  cmp     dword ptr [rbp+57h+Size], edi
0x18000e777  jz      short loc_18000E7A2
0x18000e779  mov     edi, dword ptr [rbp+57h+Size]
0x18000e77c  test    rbx, rbx
0x18000e77f  jz      short loc_18000E789
0x18000e781  mov     rcx, rbx; Block
0x18000e784  call    free
0x18000e789  mov     rcx, rdi; Size
0x18000e78c  call    _o_malloc_0
0x18000e791  mov     rbx, rax
0x18000e794  test    rax, rax
0x18000e797  jz      loc_18000E896
0x18000e79d  xor     eax, eax
0x18000e79f  mov     [rbx], ax
0x18000e7a2  mov     [rsp+0B0h+var_78], 0
0x18000e7aa  lea     rax, [rbp+57h+Size]
0x18000e7ae  mov     [rsp+0B0h+var_80], rax
0x18000e7b3  lea     r9, [rbp+57h+Size+4]
0x18000e7b7  mov     [rsp+0B0h+var_88], edi
0x18000e7bb  lea     r8, DEVPKEY_Device_Service
0x18000e7c2  lea     rdx, [rbp+57h+var_60]
0x18000e7c6  mov     [rsp+0B0h+var_90], rbx
0x18000e7cb  mov     rcx, r14
0x18000e7ce  call    cs:__imp_DevObjGetDeviceProperty
0x18000e7d4  test    eax, eax
0x18000e7d6  jnz     short loc_18000E816
0x18000e7d8  call    cs:__imp_GetLastError
0x18000e7de  cmp     eax, 7Ah ; 'z'
0x18000e7e1  jz      short loc_18000E774
0x18000e7e3  call    cs:__imp_GetLastError
0x18000e7e9  mov     edi, eax
0x18000e7eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e7f2  lea     rax, WPP_GLOBAL_Control
0x18000e7f9  cmp     rcx, rax
0x18000e7fc  jz      loc_18000E8F8
0x18000e802  test    byte ptr [rcx+1Ch], 1
0x18000e806  jz      loc_18000E8F8
0x18000e80c  mov     edx, 20h ; ' '
0x18000e811  jmp     loc_18000E729
0x18000e816  test    rbx, rbx
0x18000e819  jz      loc_18000E68C
0x18000e81f  mov     r8d, 7; MaxCount
0x18000e825  lea     rdx, aUsbstor; "usbstor"
0x18000e82c  mov     rcx, rbx; String1
0x18000e82f  call    _wcsnicmp
0x18000e834  test    eax, eax
0x18000e836  jz      loc_18000E8BE
0x18000e83c  mov     r8d, 8; MaxCount
0x18000e842  lea     rdx, aUaspstor; "uaspstor"
0x18000e849  mov     rcx, rbx; String1
0x18000e84c  call    _wcsnicmp
0x18000e851  test    eax, eax
0x18000e853  jnz     loc_18000E68C
0x18000e859  mov     dword ptr [rsi], 1
0x18000e85f  jmp     short loc_18000E8C4
0x18000e861  mov     r9d, 0Eh
0x18000e867  mov     edi, r9d
0x18000e86a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e871  lea     rax, WPP_GLOBAL_Control
0x18000e878  cmp     rcx, rax
0x18000e87b  jz      loc_18000E905
0x18000e881  test    byte ptr [rcx+1Ch], 1
0x18000e885  jz      short loc_18000E905
0x18000e887  lea     edx, [r9+0Eh]
0x18000e88b  mov     rcx, [rcx+10h]
0x18000e88f  call    WPP_SF_D
0x18000e894  jmp     short loc_18000E905
0x18000e896  mov     r9d, 0Eh
0x18000e89c  mov     edi, r9d
0x18000e89f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e8a6  lea     rax, WPP_GLOBAL_Control
0x18000e8ad  cmp     rcx, rax
0x18000e8b0  jz      short loc_18000E905
0x18000e8b2  test    byte ptr [rcx+1Ch], 1
0x18000e8b6  jz      short loc_18000E905
0x18000e8b8  lea     edx, [r9+11h]
0x18000e8bc  jmp     short loc_18000E88B
0x18000e8be  mov     dword ptr [rsi], 0
0x18000e8c4  xor     edi, edi
0x18000e8c6  jmp     short loc_18000E8FD
0x18000e8c8  call    cs:__imp_GetLastError
0x18000e8ce  mov     edi, eax
0x18000e8d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e8d7  lea     rax, WPP_GLOBAL_Control
0x18000e8de  cmp     rcx, rax
0x18000e8e1  jz      short loc_18000E8F8
0x18000e8e3  test    byte ptr [rcx+1Ch], 1
0x18000e8e7  jz      short loc_18000E8F8
0x18000e8e9  mov     edx, 1Eh
0x18000e8ee  jmp     loc_18000E729
0x18000e8f3  mov     edi, 0Fh
0x18000e8f8  test    rbx, rbx
0x18000e8fb  jz      short loc_18000E905
0x18000e8fd  mov     rcx, rbx; Block
0x18000e900  call    free
0x18000e905  mov     eax, edi
0x18000e907  mov     rcx, [rbp+57h+var_30]
0x18000e90b  xor     rcx, rsp; StackCookie
0x18000e90e  call    __security_check_cookie
0x18000e913  add     rsp, 90h
0x18000e91a  pop     r14
0x18000e91c  pop     rdi
0x18000e91d  pop     rsi
0x18000e91e  pop     rbx
0x18000e91f  pop     rbp
0x18000e920  retn
```
