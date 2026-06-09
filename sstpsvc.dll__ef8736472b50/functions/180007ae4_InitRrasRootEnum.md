# InitRrasRootEnum

- ea: `0x180007ae4`
- end: `0x180007dab`
- name: `InitRrasRootEnum`
- size: `711`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800067b4`

## callees

- `0x180007ae4`
- `0x18001d1da`
- `0x18001d210`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180007b83`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180007b83`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180007ced`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180007ced`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007b99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007b99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d04`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007c0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007c0d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007c37`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007c37`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007c21`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007d48`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007c21`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007d48`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007d60`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007d60`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x180007ccd`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x180007ccd`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceClose` at `0x180007bec`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceClose` at `0x180007bec`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x180007bc7`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x180007bc7`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_IDW` at `0x180007c7b`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_IDW` at `0x180007c7b`

## pseudocode

```c
__int64 __fastcall InitRrasRootEnum(_QWORD *a1)
{
  signed int LastError; // eax
  signed int v3; // ebx
  HANDLE v4; // rax
  DWORD v6; // eax
  signed int v7; // eax
  HANDLE ProcessHeap; // rax
  _QWORD *v9; // rax
  DEVNODE pdnDevInst; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE hObject[2]; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID lpMem[2]; // [rsp+58h] [rbp-A8h]
  int v13; // [rsp+70h] [rbp-90h] BYREF
  const wchar_t *v14; // [rsp+78h] [rbp-88h]
  int v15; // [rsp+98h] [rbp-68h]
  const wchar_t *v16; // [rsp+A0h] [rbp-60h]
  WCHAR Buffer[200]; // [rsp+C0h] [rbp-40h] BYREF

  memset_0(&v13, 0, 0x48u);
  *(_OWORD *)hObject = 0;
  *(_OWORD *)lpMem = 0;
  memset_0(Buffer, 0, sizeof(Buffer));
  pdnDevInst = 0;
  v14 = L"{5e259276-bc7e-40e3-b93b-8f89b5f3abc0}";
  g_RrasRootEnum = 0;
  v16 = L"Microsoft RRAS Root Enumerator";
  v13 = 72;
  v15 = 2;
  hObject[0] = CreateEventW(0, 0, 0, 0);
  if ( !hObject[0] )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
LABEL_22:
    if ( v3 >= 0 )
      goto LABEL_8;
    goto LABEL_6;
  }
  if ( CM_Locate_DevNodeW(&pdnDevInst, 0, 0) || CM_Get_Device_IDW(pdnDevInst, Buffer, 0xC8u, 0) )
  {
    v3 = -2147467259;
    goto LABEL_6;
  }
  v3 = SwDeviceCreate(L"MSRRAS", Buffer, &v13, 0, 0, &RrasSwDeviceCreateCallback, hObject, &g_RrasRootEnum);
  if ( v3 < 0 )
  {
LABEL_6:
    if ( g_RrasRootEnum )
    {
      SwDeviceClose();
      g_RrasRootEnum = 0;
    }
    goto LABEL_8;
  }
  v6 = WaitForSingleObject(hObject[0], 0x7530u);
  if ( v6 )
  {
    if ( v6 == 258 )
    {
      v3 = -2147023436;
      goto LABEL_6;
    }
    v7 = GetLastError();
    v3 = v7;
    if ( v7 > 0 )
      v3 = (unsigned __int16)v7 | 0x80070000;
    if ( v3 < 0 )
      goto LABEL_6;
  }
  if ( SLODWORD(lpMem[0]) < 0 )
  {
    v3 = (signed int)lpMem[0];
    goto LABEL_22;
  }
  ProcessHeap = GetProcessHeap();
  v9 = HeapAlloc(ProcessHeap, 8u, 0x10u);
  if ( !v9 )
  {
    v3 = -2147024882;
    goto LABEL_6;
  }
  v9[1] = g_RrasRootEnum;
  *v9 = lpMem[1];
  lpMem[1] = 0;
  if ( a1 )
    *a1 = v9;
LABEL_8:
  if ( hObject[0] )
    CloseHandle(hObject[0]);
  if ( lpMem[1] )
  {
    v4 = GetProcessHeap();
    HeapFree(v4, 0, lpMem[1]);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180007ae4  mov     [rsp-8+arg_8], rbx
0x180007ae9  mov     [rsp-8+arg_10], rdi
0x180007aee  push    rbp
0x180007aef  lea     rbp, [rsp-160h]
0x180007af7  sub     rsp, 260h
0x180007afe  mov     rax, cs:__security_cookie
0x180007b05  xor     rax, rsp
0x180007b08  mov     [rbp+160h+var_10], rax
0x180007b0f  mov     rdi, rcx
0x180007b12  mov     ebx, 48h ; 'H'
0x180007b17  mov     r8d, ebx; Size
0x180007b1a  lea     rcx, [rsp+260h+var_1F0]; void *
0x180007b1f  xor     edx, edx; Val
0x180007b21  call    memset_0
0x180007b26  xorps   xmm0, xmm0
0x180007b29  lea     rcx, [rbp+160h+Buffer]; void *
0x180007b2d  xor     edx, edx; Val
0x180007b2f  mov     r8d, 190h; Size
0x180007b35  movups  xmmword ptr [rsp+260h+hObject], xmm0
0x180007b3a  movups  xmmword ptr [rsp+260h+lpMem], xmm0
0x180007b3f  call    memset_0
0x180007b44  lea     rax, a5e259276Bc7e40; "{5e259276-bc7e-40e3-b93b-8f89b5f3abc0}"
0x180007b4b  mov     [rsp+260h+pdnDevInst], 0
0x180007b53  mov     [rsp+260h+var_1E8], rax
0x180007b58  xor     r9d, r9d; lpName
0x180007b5b  lea     rax, aMicrosoftRrasR; "Microsoft RRAS Root Enumerator"
0x180007b62  mov     cs:g_RrasRootEnum, 0
0x180007b6d  xor     r8d, r8d; bInitialState
0x180007b70  mov     [rbp+160h+var_1C0], rax
0x180007b74  xor     edx, edx; bManualReset
0x180007b76  mov     [rsp+260h+var_1F0], ebx
0x180007b7a  xor     ecx, ecx; lpEventAttributes
0x180007b7c  mov     [rbp+160h+var_1C8], 2
0x180007b83  call    cs:__imp_CreateEventW
0x180007b8a  nop     dword ptr [rax+rax+00h]
0x180007b8f  mov     [rsp+260h+hObject], rax
0x180007b94  test    rax, rax
0x180007b97  jnz     short loc_180007BBD
0x180007b99  call    cs:__imp_GetLastError
0x180007ba0  nop     dword ptr [rax+rax+00h]
0x180007ba5  mov     ebx, eax
0x180007ba7  test    eax, eax
0x180007ba9  jle     loc_180007D31
0x180007baf  movzx   ebx, ax
0x180007bb2  or      ebx, 80070000h
0x180007bb8  jmp     loc_180007D31
0x180007bbd  xor     r8d, r8d; ulFlags
0x180007bc0  lea     rcx, [rsp+260h+pdnDevInst]; pdnDevInst
0x180007bc5  xor     edx, edx; pDeviceID
0x180007bc7  call    cs:__imp_CM_Locate_DevNodeW
0x180007bce  nop     dword ptr [rax+rax+00h]
0x180007bd3  test    eax, eax
0x180007bd5  jz      loc_180007C6A
0x180007bdb  mov     ebx, 80004005h
0x180007be0  mov     rcx, cs:g_RrasRootEnum
0x180007be7  test    rcx, rcx
0x180007bea  jz      short loc_180007C03
0x180007bec  call    cs:__imp_SwDeviceClose
0x180007bf3  nop     dword ptr [rax+rax+00h]
0x180007bf8  mov     cs:g_RrasRootEnum, 0
0x180007c03  mov     rcx, [rsp+260h+hObject]; hObject
0x180007c08  test    rcx, rcx
0x180007c0b  jz      short loc_180007C19
0x180007c0d  call    cs:__imp_CloseHandle
0x180007c14  nop     dword ptr [rax+rax+00h]
0x180007c19  cmp     [rsp+260h+lpMem+8], 0
0x180007c1f  jz      short loc_180007C43
0x180007c21  call    cs:__imp_GetProcessHeap
0x180007c28  nop     dword ptr [rax+rax+00h]
0x180007c2d  mov     r8, [rsp+260h+lpMem+8]; lpMem
0x180007c32  xor     edx, edx; dwFlags
0x180007c34  mov     rcx, rax; hHeap
0x180007c37  call    cs:__imp_HeapFree
0x180007c3e  nop     dword ptr [rax+rax+00h]
0x180007c43  mov     eax, ebx
0x180007c45  mov     rcx, [rbp+160h+var_10]
0x180007c4c  xor     rcx, rsp; StackCookie
0x180007c4f  call    __security_check_cookie
0x180007c54  lea     r11, [rsp+260h+var_s0]
0x180007c5c  mov     rbx, [r11+18h]
0x180007c60  mov     rdi, [r11+20h]
0x180007c64  mov     rsp, r11
0x180007c67  pop     rbp
0x180007c68  retn
0x180007c6a  mov     ecx, [rsp+260h+pdnDevInst]; dnDevInst
0x180007c6e  lea     rdx, [rbp+160h+Buffer]; Buffer
0x180007c72  xor     r9d, r9d; ulFlags
0x180007c75  mov     r8d, 0C8h; BufferLen
0x180007c7b  call    cs:__imp_CM_Get_Device_IDW
0x180007c82  nop     dword ptr [rax+rax+00h]
0x180007c87  test    eax, eax
0x180007c89  jnz     loc_180007BDB
0x180007c8f  lea     rax, g_RrasRootEnum
0x180007c96  xor     r9d, r9d
0x180007c99  mov     [rsp+260h+var_228], rax
0x180007c9e  lea     r8, [rsp+260h+var_1F0]
0x180007ca3  lea     rax, [rsp+260h+hObject]
0x180007ca8  mov     [rsp+260h+var_230], rax
0x180007cad  lea     rdx, [rbp+160h+Buffer]
0x180007cb1  lea     rax, RrasSwDeviceCreateCallback
0x180007cb8  mov     [rsp+260h+var_238], rax
0x180007cbd  lea     rcx, aMsrras; "MSRRAS"
0x180007cc4  mov     [rsp+260h+var_240], 0
0x180007ccd  call    cs:__imp_SwDeviceCreate
0x180007cd4  nop     dword ptr [rax+rax+00h]
0x180007cd9  mov     ebx, eax
0x180007cdb  test    eax, eax
0x180007cdd  js      loc_180007BE0
0x180007ce3  mov     rcx, [rsp+260h+hObject]; hHandle
0x180007ce8  mov     edx, 7530h; dwMilliseconds
0x180007ced  call    cs:__imp_WaitForSingleObject
0x180007cf4  nop     dword ptr [rax+rax+00h]
0x180007cf9  test    eax, eax
0x180007cfb  jz      short loc_180007D27
0x180007cfd  cmp     eax, 102h
0x180007d02  jz      short loc_180007D3E
0x180007d04  call    cs:__imp_GetLastError
0x180007d0b  nop     dword ptr [rax+rax+00h]
0x180007d10  mov     ebx, eax
0x180007d12  test    eax, eax
0x180007d14  jle     short loc_180007D1F
0x180007d16  movzx   ebx, ax
0x180007d19  or      ebx, 80070000h
0x180007d1f  test    ebx, ebx
0x180007d21  js      loc_180007BE0
0x180007d27  mov     eax, dword ptr [rsp+260h+lpMem]
0x180007d2b  test    eax, eax
0x180007d2d  jns     short loc_180007D48
0x180007d2f  mov     ebx, eax
0x180007d31  test    ebx, ebx
0x180007d33  js      loc_180007BE0
0x180007d39  jmp     loc_180007C03
0x180007d3e  mov     ebx, 800705B4h
0x180007d43  jmp     loc_180007BE0
0x180007d48  call    cs:__imp_GetProcessHeap
0x180007d4f  nop     dword ptr [rax+rax+00h]
0x180007d54  mov     edx, 8; dwFlags
0x180007d59  mov     rcx, rax; hHeap
0x180007d5c  lea     r8d, [rdx+8]; dwBytes
0x180007d60  call    cs:__imp_HeapAlloc
0x180007d67  nop     dword ptr [rax+rax+00h]
0x180007d6c  mov     rcx, rax
0x180007d6f  test    rax, rax
0x180007d72  jnz     short loc_180007D7E
0x180007d74  mov     ebx, 8007000Eh
0x180007d79  jmp     loc_180007BE0
0x180007d7e  mov     rax, cs:g_RrasRootEnum
0x180007d85  mov     [rcx+8], rax
0x180007d89  mov     rax, [rsp+260h+lpMem+8]
0x180007d8e  mov     [rcx], rax
0x180007d91  mov     [rsp+260h+lpMem+8], 0
0x180007d9a  test    rdi, rdi
0x180007d9d  jz      loc_180007C03
0x180007da3  mov     [rdi], rcx
0x180007da6  jmp     loc_180007C03
```
