# DetermineIfControllerIsUSB(void *,_DO_DEVINFO_DATA,_USB_BOOT_INFORMATION_CONTROLLER_TYPE *)

- ea: `0x18000e360`
- end: `0x18000e639`
- name: `?DetermineIfControllerIsUSB@@YAKPEAXU_DO_DEVINFO_DATA@@PEAW4_USB_BOOT_INFORMATION_CONTROLLER_TYPE@@@Z`
- size: `729`
- prototype: `__int64 __fastcall(__int64, _OWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x18000f180`

## callees

- `0x180002410`
- `0x180002e3e`
- `0x180002e4a`
- `0x180002e56`
- `0x18000e360`
- `0x18000f32c`
- `0x18000fe84`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e410`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e4c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e4cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e57d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e5e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e410`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e4c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e4cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e57d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e5e3`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x18000e406`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x18000e4b8`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x18000e406`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x18000e4b8`
- `DEVOBJ!DevObjOpenDeviceInfo` at `0x18000e450`
- `DEVOBJ!DevObjOpenDeviceInfo` at `0x18000e450`

## pseudocode

```c
__int64 __fastcall DetermineIfControllerIsUSB(__int64 a1, _OWORD *a2, _DWORD *a3)
{
  size_t v3; // rdi
  _WORD *v4; // rbx
  __int128 v5; // xmm1
  unsigned int v6; // eax
  __int128 v9; // xmm0
  __int64 v10; // r8
  DWORD LastError; // edi
  __int64 v12; // r8
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  size_t Size[2]; // [rsp+40h] [rbp-19h] BYREF
  _OWORD v19[3]; // [rsp+50h] [rbp-9h] BYREF

  LODWORD(v3) = 0;
  v4 = 0;
  v5 = a2[1];
  v6 = 0;
  v19[0] = *a2;
  v9 = a2[2];
  v19[1] = v5;
  v19[2] = v9;
  for ( Size[0] = 0; ; v6 = Size[0] )
  {
    if ( v6 == (_DWORD)v3 )
      goto LABEL_7;
    v3 = v6;
    if ( v4 )
      free(v4);
    v4 = o_malloc_0(v3);
    if ( !v4 )
      break;
    *v4 = 0;
LABEL_7:
    if ( (unsigned int)DevObjGetDeviceProperty(a1, v19, &DEVPKEY_Device_Parent, (char *)Size + 4, v4, v3, Size, 0) )
    {
      if ( !wcscmp_0(v4, L"HTREE\\ROOT\\0") )
      {
        LastError = 15;
      }
      else
      {
        if ( (unsigned int)DevObjOpenDeviceInfo(a1, v4, 0, 0, v19) )
        {
          while ( 1 )
          {
            if ( LODWORD(Size[0]) != (_DWORD)v3 )
            {
              v3 = LODWORD(Size[0]);
              if ( v4 )
                free(v4);
              v4 = o_malloc_0(v3);
              if ( !v4 )
              {
                LastError = 14;
                v15 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  v16 = 21;
                  goto LABEL_28;
                }
                return LastError;
              }
              *v4 = 0;
            }
            if ( (unsigned int)DevObjGetDeviceProperty(
                                 a1,
                                 v19,
                                 &DEVPKEY_Device_Service,
                                 (char *)Size + 4,
                                 v4,
                                 v3,
                                 Size,
                                 0) )
            {
              if ( wcsnicmp(v4, L"usbxhci", 7u) )
              {
                if ( wcsnicmp(v4, L"usbehci", 7u) )
                  goto LABEL_9;
                *a3 = 0;
              }
              else
              {
                *a3 = 1;
              }
              LastError = 0;
              goto LABEL_42;
            }
            if ( GetLastError() != 122 )
            {
              LastError = GetLastError();
              v13 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v14 = 22;
                goto LABEL_32;
              }
              goto LABEL_42;
            }
          }
        }
        LastError = GetLastError();
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v14 = 20;
          goto LABEL_32;
        }
      }
LABEL_42:
      if ( v4 )
        free(v4);
      return LastError;
    }
    if ( GetLastError() != 122 )
    {
      LastError = GetLastError();
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v14 = 19;
LABEL_32:
        WPP_SF_D(v13[2], v14, v12, LastError);
        goto LABEL_42;
      }
      goto LABEL_42;
    }
LABEL_9:
    ;
  }
  LastError = 14;
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v16 = 18;
LABEL_28:
    WPP_SF_D(v15[2], v16, v10, 14);
  }
  return LastError;
}

```

## disassembly

```asm
0x18000e360  push    rbp
0x18000e362  push    rbx
0x18000e363  push    rsi
0x18000e364  push    rdi
0x18000e365  push    r14
0x18000e367  lea     rbp, [rsp-37h]
0x18000e36c  sub     rsp, 90h
0x18000e373  mov     rax, cs:__security_cookie
0x18000e37a  xor     rax, rsp
0x18000e37d  mov     [rbp+57h+var_30], rax
0x18000e381  movups  xmm0, xmmword ptr [rdx]
0x18000e384  xor     edi, edi
0x18000e386  xor     ebx, ebx
0x18000e388  movups  xmm1, xmmword ptr [rdx+10h]
0x18000e38c  xor     eax, eax
0x18000e38e  mov     rsi, r8
0x18000e391  movaps  [rbp+57h+var_60], xmm0
0x18000e395  mov     r14, rcx
0x18000e398  movups  xmm0, xmmword ptr [rdx+20h]
0x18000e39c  mov     dword ptr [rbp+57h+Size+4], 0
0x18000e3a3  movaps  [rbp+57h+var_50], xmm1
0x18000e3a7  movaps  [rbp+57h+var_40], xmm0
0x18000e3ab  mov     dword ptr [rbp+57h+Size], eax
0x18000e3ae  cmp     eax, edi
0x18000e3b0  jz      short loc_18000E3DA
0x18000e3b2  mov     edi, eax
0x18000e3b4  test    rbx, rbx
0x18000e3b7  jz      short loc_18000E3C1
0x18000e3b9  mov     rcx, rbx; Block
0x18000e3bc  call    free
0x18000e3c1  mov     rcx, rdi; Size
0x18000e3c4  call    _o_malloc_0
0x18000e3c9  mov     rbx, rax
0x18000e3cc  test    rax, rax
0x18000e3cf  jz      loc_18000E541
0x18000e3d5  xor     eax, eax
0x18000e3d7  mov     [rbx], ax
0x18000e3da  mov     [rsp+0B0h+var_78], 0
0x18000e3e2  lea     rax, [rbp+57h+Size]
0x18000e3e6  mov     [rsp+0B0h+var_80], rax
0x18000e3eb  lea     r9, [rbp+57h+Size+4]
0x18000e3ef  mov     [rsp+0B0h+var_88], edi
0x18000e3f3  lea     r8, DEVPKEY_Device_Parent
0x18000e3fa  lea     rdx, [rbp+57h+var_60]
0x18000e3fe  mov     [rsp+0B0h+var_90], rbx
0x18000e403  mov     rcx, r14
0x18000e406  call    cs:__imp_DevObjGetDeviceProperty
0x18000e40c  test    eax, eax
0x18000e40e  jnz     short loc_18000E424
0x18000e410  call    cs:__imp_GetLastError
0x18000e416  cmp     eax, 7Ah ; 'z'
0x18000e419  jnz     loc_18000E57D
0x18000e41f  mov     eax, dword ptr [rbp+57h+Size]
0x18000e422  jmp     short loc_18000E3AE
0x18000e424  lea     rdx, aHtreeRoot0; "HTREE\\ROOT\\0"
0x18000e42b  mov     rcx, rbx; String1
0x18000e42e  call    wcscmp_0
0x18000e433  test    eax, eax
0x18000e435  jz      loc_18000E60B
0x18000e43b  lea     rax, [rbp+57h+var_60]
0x18000e43f  xor     r9d, r9d
0x18000e442  xor     r8d, r8d
0x18000e445  mov     [rsp+0B0h+var_90], rax
0x18000e44a  mov     rdx, rbx
0x18000e44d  mov     rcx, r14
0x18000e450  call    cs:__imp_DevObjOpenDeviceInfo
0x18000e456  test    eax, eax
0x18000e458  jz      loc_18000E5E3
0x18000e45e  cmp     dword ptr [rbp+57h+Size], edi
0x18000e461  jz      short loc_18000E48C
0x18000e463  mov     edi, dword ptr [rbp+57h+Size]
0x18000e466  test    rbx, rbx
0x18000e469  jz      short loc_18000E473
0x18000e46b  mov     rcx, rbx; Block
0x18000e46e  call    free
0x18000e473  mov     rcx, rdi; Size
0x18000e476  call    _o_malloc_0
0x18000e47b  mov     rbx, rax
0x18000e47e  test    rax, rax
0x18000e481  jz      loc_18000E5B1
0x18000e487  xor     eax, eax
0x18000e489  mov     [rbx], ax
0x18000e48c  mov     [rsp+0B0h+var_78], 0
0x18000e494  lea     rax, [rbp+57h+Size]
0x18000e498  mov     [rsp+0B0h+var_80], rax
0x18000e49d  lea     r9, [rbp+57h+Size+4]
0x18000e4a1  mov     [rsp+0B0h+var_88], edi
0x18000e4a5  lea     r8, DEVPKEY_Device_Service
0x18000e4ac  lea     rdx, [rbp+57h+var_60]
0x18000e4b0  mov     [rsp+0B0h+var_90], rbx
0x18000e4b5  mov     rcx, r14
0x18000e4b8  call    cs:__imp_DevObjGetDeviceProperty
0x18000e4be  test    eax, eax
0x18000e4c0  jnz     short loc_18000E500
0x18000e4c2  call    cs:__imp_GetLastError
0x18000e4c8  cmp     eax, 7Ah ; 'z'
0x18000e4cb  jz      short loc_18000E45E
0x18000e4cd  call    cs:__imp_GetLastError
0x18000e4d3  mov     edi, eax
0x18000e4d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e4dc  lea     rax, WPP_GLOBAL_Control
0x18000e4e3  cmp     rcx, rax
0x18000e4e6  jz      loc_18000E610
0x18000e4ec  test    byte ptr [rcx+1Ch], 1
0x18000e4f0  jz      loc_18000E610
0x18000e4f6  mov     edx, 16h
0x18000e4fb  jmp     loc_18000E5A3
0x18000e500  mov     r8d, 7; MaxCount
0x18000e506  lea     rdx, aUsbxhci; "usbxhci"
0x18000e50d  mov     rcx, rbx; String1
0x18000e510  call    _wcsnicmp
0x18000e515  test    eax, eax
0x18000e517  jz      loc_18000E5D9
0x18000e51d  mov     r8d, 7; MaxCount
0x18000e523  lea     rdx, aUsbehci; "usbehci"
0x18000e52a  mov     rcx, rbx; String1
0x18000e52d  call    _wcsnicmp
0x18000e532  test    eax, eax
0x18000e534  jnz     loc_18000E41F
0x18000e53a  mov     [rsi], eax
0x18000e53c  jmp     loc_18000E5DF
0x18000e541  mov     r9d, 0Eh
0x18000e547  mov     edi, r9d
0x18000e54a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e551  lea     rax, WPP_GLOBAL_Control
0x18000e558  cmp     rcx, rax
0x18000e55b  jz      loc_18000E61D
0x18000e561  test    byte ptr [rcx+1Ch], 1
0x18000e565  jz      loc_18000E61D
0x18000e56b  lea     edx, [r9+4]
0x18000e56f  mov     rcx, [rcx+10h]
0x18000e573  call    WPP_SF_D
0x18000e578  jmp     loc_18000E61D
0x18000e57d  call    cs:__imp_GetLastError
0x18000e583  mov     edi, eax
0x18000e585  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e58c  lea     rax, WPP_GLOBAL_Control
0x18000e593  cmp     rcx, rax
0x18000e596  jz      short loc_18000E610
0x18000e598  test    byte ptr [rcx+1Ch], 1
0x18000e59c  jz      short loc_18000E610
0x18000e59e  mov     edx, 13h
0x18000e5a3  mov     rcx, [rcx+10h]
0x18000e5a7  mov     r9d, edi
0x18000e5aa  call    WPP_SF_D
0x18000e5af  jmp     short loc_18000E610
0x18000e5b1  mov     r9d, 0Eh
0x18000e5b7  mov     edi, r9d
0x18000e5ba  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e5c1  lea     rax, WPP_GLOBAL_Control
0x18000e5c8  cmp     rcx, rax
0x18000e5cb  jz      short loc_18000E61D
0x18000e5cd  test    byte ptr [rcx+1Ch], 1
0x18000e5d1  jz      short loc_18000E61D
0x18000e5d3  lea     edx, [r9+7]
0x18000e5d7  jmp     short loc_18000E56F
0x18000e5d9  mov     dword ptr [rsi], 1
0x18000e5df  xor     edi, edi
0x18000e5e1  jmp     short loc_18000E610
0x18000e5e3  call    cs:__imp_GetLastError
0x18000e5e9  mov     edi, eax
0x18000e5eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e5f2  lea     rax, WPP_GLOBAL_Control
0x18000e5f9  cmp     rcx, rax
0x18000e5fc  jz      short loc_18000E610
0x18000e5fe  test    byte ptr [rcx+1Ch], 1
0x18000e602  jz      short loc_18000E610
0x18000e604  mov     edx, 14h
0x18000e609  jmp     short loc_18000E5A3
0x18000e60b  mov     edi, 0Fh
0x18000e610  test    rbx, rbx
0x18000e613  jz      short loc_18000E61D
0x18000e615  mov     rcx, rbx; Block
0x18000e618  call    free
0x18000e61d  mov     eax, edi
0x18000e61f  mov     rcx, [rbp+57h+var_30]
0x18000e623  xor     rcx, rsp; StackCookie
0x18000e626  call    __security_check_cookie
0x18000e62b  add     rsp, 90h
0x18000e632  pop     r14
0x18000e634  pop     rdi
0x18000e635  pop     rsi
0x18000e636  pop     rbx
0x18000e637  pop     rbp
0x18000e638  retn
```
