# WdiCreateInstance

- ea: `0x18000b220`
- end: `0x18000b49a`
- name: `WdiCreateInstance`
- size: `634`
- prototype: `__int64 __fastcall(unsigned int, _QWORD *, HANDLE *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x180001340`
- `0x180002ba0`
- `0x180003160`
- `0x180009f18`
- `0x18000b220`
- `0x18000f1c2`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000b284`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000b372`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000b284`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000b372`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b292`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b384`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b292`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b384`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000b3cf`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000b3cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b41f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b439`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b455`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b474`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b41f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b439`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b455`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b474`

## string_xrefs

- `0x18000b25c`: `WdiCreateInstance`
- `0x18000b2cd`: `WdiCreateInstance`

## pseudocode

```c
__int64 __fastcall WdiCreateInstance(unsigned int a1, _QWORD *a2, HANDLE *a3)
{
  signed int v6; // ebx
  _QWORD *v7; // rdi
  char *v8; // r14
  HANDLE EventW; // rax
  signed int v10; // eax
  _QWORD *v11; // rax
  int v12; // eax
  HANDLE v13; // rax
  signed int LastError; // eax
  char *v15; // rax
  char *v16; // rcx
  char *v17; // rcx
  DWORD ThreadId; // [rsp+80h] [rbp+18h] BYREF

  ThreadId = 0;
  if ( !a3 )
  {
    v6 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
      (int)L"WdiCreateInstance",
      52,
      (int)L"Error = %d",
      87);
    return (unsigned int)v6;
  }
  v7 = 0;
  v8 = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  *a3 = EventW;
  if ( !EventW )
    goto LABEL_4;
  if ( a2 )
  {
    v11 = (_QWORD *)WdipAlloc(216);
    v7 = v11;
    if ( v11 )
    {
      memset_0(v11, 0, 0xD8u);
      v7[3] = v7 + 23;
      v7[4] = v7 + 25;
      *(_OWORD *)v7 = WDI_CLIENT_PARAMETER_ID;
      *((_DWORD *)v7 + 26) = 0;
      v12 = WdipConnectClientToDPS(a1, v7 + 5, v7 + 15);
      v6 = v12;
      if ( v12 >= 0 )
      {
        v13 = CreateEventW(0, 1, 0, 0);
        v7[18] = v13;
        if ( v13 )
          goto LABEL_18;
        LastError = GetLastError();
        v6 = LastError;
        if ( LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
        if ( v6 >= 0 )
        {
LABEL_18:
          v15 = (char *)CreateThread(0, 0, WdipClientListener, v7, 0, &ThreadId);
          v8 = v15;
          if ( v15 )
          {
            v7[16] = v15;
            *((_DWORD *)v7 + 4) = 1;
            v7[22] = 0;
            v7[17] = *a3;
            *((_DWORD *)v7 + 38) = a1;
            *a2 = v7;
            goto LABEL_20;
          }
LABEL_4:
          v10 = GetLastError();
          v6 = v10;
          if ( v10 > 0 )
            v6 = (unsigned __int16)v10 | 0x80070000;
LABEL_20:
          if ( v6 >= 0 )
            return (unsigned int)v6;
          goto LABEL_21;
        }
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
          (int)L"WdiCreateInstance",
          95,
          (int)L"Error = %d",
          v6);
      }
      else
      {
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
          (int)L"WdiCreateInstance",
          89,
          (int)L"Error = %d",
          v12);
      }
    }
    else
    {
      v6 = -2147024882;
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
        (int)L"WdiCreateInstance",
        69,
        (int)L"Error = %d",
        14);
    }
  }
  else
  {
    v6 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
      (int)L"WdiCreateInstance",
      61,
      (int)L"Error = %d",
      87);
  }
LABEL_21:
  if ( (char *)*a3 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(*a3);
    *a3 = 0;
  }
  if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v8);
  if ( v7 )
  {
    v16 = (char *)v7[18];
    if ( (unsigned __int64)(v16 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(v16);
      v7[18] = 0;
    }
    v17 = (char *)v7[15];
    if ( (unsigned __int64)(v17 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(v17);
      v7[15] = 0;
    }
    WdipFree(v7);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000b220  mov     rax, rsp
0x18000b223  push    rbx
0x18000b224  push    rsi
0x18000b225  push    rdi
0x18000b226  push    r12
0x18000b228  push    r14
0x18000b22a  push    r15
0x18000b22c  sub     rsp, 38h
0x18000b230  mov     dword ptr [rax+18h], 0
0x18000b237  mov     rsi, r8
0x18000b23a  mov     r15, rdx
0x18000b23d  mov     r12d, ecx
0x18000b240  test    r8, r8
0x18000b243  jnz     short loc_18000B274
0x18000b245  lea     r9, aErrorD_0; "Error = %d"
0x18000b24c  mov     dword ptr [rax-48h], 57h ; 'W'
0x18000b253  lea     r8d, [rsi+34h]; int
0x18000b257  mov     ebx, 80070057h
0x18000b25c  lea     rdx, aWdicreateinsta_0; "WdiCreateInstance"
0x18000b263  lea     rcx, aClientcoreBase_13; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000b26a  call    WdipTraceError
0x18000b26f  jmp     loc_18000B48A
0x18000b274  xor     edi, edi
0x18000b276  xor     r9d, r9d; lpName
0x18000b279  xor     r8d, r8d; bInitialState
0x18000b27c  xor     ecx, ecx; lpEventAttributes
0x18000b27e  xor     r14d, r14d
0x18000b281  lea     edx, [rdi+1]; bManualReset
0x18000b284  call    cs:__imp_CreateEventW
0x18000b28a  mov     [rsi], rax
0x18000b28d  test    rax, rax
0x18000b290  jnz     short loc_18000B2B0
0x18000b292  call    cs:__imp_GetLastError
0x18000b298  mov     ebx, eax
0x18000b29a  test    eax, eax
0x18000b29c  jle     loc_18000B40E
0x18000b2a2  movzx   ebx, ax
0x18000b2a5  or      ebx, 80070000h
0x18000b2ab  jmp     loc_18000B40E
0x18000b2b0  test    r15, r15
0x18000b2b3  jnz     short loc_18000B2E5
0x18000b2b5  mov     ebx, 80070057h
0x18000b2ba  mov     [rsp+68h+dwCreationFlags], 57h ; 'W'; Args
0x18000b2c2  lea     r8d, [r15+3Dh]; int
0x18000b2c6  lea     r9, aErrorD_0; "Error = %d"
0x18000b2cd  lea     rdx, aWdicreateinsta_0; "WdiCreateInstance"
0x18000b2d4  lea     rcx, aClientcoreBase_13; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000b2db  call    WdipTraceError
0x18000b2e0  jmp     loc_18000B412
0x18000b2e5  mov     ebx, 0D8h
0x18000b2ea  mov     ecx, ebx
0x18000b2ec  call    WdipAlloc
0x18000b2f1  mov     rdi, rax
0x18000b2f4  test    rax, rax
0x18000b2f7  jnz     short loc_18000B30C
0x18000b2f9  mov     ebx, 8007000Eh
0x18000b2fe  mov     [rsp+68h+dwCreationFlags], 0Eh
0x18000b306  lea     r8d, [rax+45h]
0x18000b30a  jmp     short loc_18000B2C6
0x18000b30c  mov     r8, rbx; Size
0x18000b30f  xor     edx, edx; Val
0x18000b311  mov     rcx, rdi; void *
0x18000b314  call    memset_0
0x18000b319  lea     rax, [rdi+0B8h]
0x18000b320  mov     ecx, r12d
0x18000b323  mov     [rdi+18h], rax
0x18000b327  lea     r8, [rdi+78h]
0x18000b32b  lea     rax, [rdi+0C8h]
0x18000b332  mov     [rdi+20h], rax
0x18000b336  lea     rdx, [rdi+28h]
0x18000b33a  movups  xmm0, cs:WDI_CLIENT_PARAMETER_ID
0x18000b341  movdqu  xmmword ptr [rdi], xmm0
0x18000b345  mov     [rdi+68h], r14d
0x18000b349  call    WdipConnectClientToDPS
0x18000b34e  mov     ebx, eax
0x18000b350  test    eax, eax
0x18000b352  jns     short loc_18000B366
0x18000b354  movzx   ecx, ax
0x18000b357  mov     r8d, 59h ; 'Y'
0x18000b35d  mov     [rsp+68h+dwCreationFlags], ecx
0x18000b361  jmp     loc_18000B2C6
0x18000b366  xor     r9d, r9d; lpName
0x18000b369  xor     r8d, r8d; bInitialState
0x18000b36c  xor     ecx, ecx; lpEventAttributes
0x18000b36e  lea     edx, [r9+1]; bManualReset
0x18000b372  call    cs:__imp_CreateEventW
0x18000b378  mov     [rdi+90h], rax
0x18000b37f  test    rax, rax
0x18000b382  jnz     short loc_18000B3AF
0x18000b384  call    cs:__imp_GetLastError
0x18000b38a  mov     ebx, eax
0x18000b38c  test    eax, eax
0x18000b38e  jle     short loc_18000B399
0x18000b390  movzx   ebx, ax
0x18000b393  or      ebx, 80070000h
0x18000b399  test    ebx, ebx
0x18000b39b  jns     short loc_18000B3AF
0x18000b39d  movzx   eax, bx
0x18000b3a0  mov     r8d, 5Fh ; '_'
0x18000b3a6  mov     [rsp+68h+dwCreationFlags], eax
0x18000b3aa  jmp     loc_18000B2C6
0x18000b3af  lea     rax, [rsp+68h+ThreadId]
0x18000b3b7  mov     r9, rdi; lpParameter
0x18000b3ba  mov     [rsp+68h+lpThreadId], rax; lpThreadId
0x18000b3bf  lea     r8, WdipClientListener; lpStartAddress
0x18000b3c6  xor     edx, edx; dwStackSize
0x18000b3c8  mov     [rsp+68h+dwCreationFlags], r14d; dwCreationFlags
0x18000b3cd  xor     ecx, ecx; lpThreadAttributes
0x18000b3cf  call    cs:__imp_CreateThread
0x18000b3d5  mov     r14, rax
0x18000b3d8  test    rax, rax
0x18000b3db  jz      loc_18000B292
0x18000b3e1  mov     [rdi+80h], rax
0x18000b3e8  mov     dword ptr [rdi+10h], 1
0x18000b3ef  mov     qword ptr [rdi+0B0h], 0
0x18000b3fa  mov     rax, [rsi]
0x18000b3fd  mov     [rdi+88h], rax
0x18000b404  mov     [rdi+98h], r12d
0x18000b40b  mov     [r15], rdi
0x18000b40e  test    ebx, ebx
0x18000b410  jns     short loc_18000B48A
0x18000b412  mov     rcx, [rsi]; hObject
0x18000b415  lea     rax, [rcx-1]
0x18000b419  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000b41d  ja      short loc_18000B42C
0x18000b41f  call    cs:__imp_CloseHandle
0x18000b425  mov     qword ptr [rsi], 0
0x18000b42c  lea     rax, [r14-1]
0x18000b430  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000b434  ja      short loc_18000B43F
0x18000b436  mov     rcx, r14; hObject
0x18000b439  call    cs:__imp_CloseHandle
0x18000b43f  test    rdi, rdi
0x18000b442  jz      short loc_18000B48A
0x18000b444  mov     rcx, [rdi+90h]; hObject
0x18000b44b  lea     rax, [rcx-1]
0x18000b44f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000b453  ja      short loc_18000B466
0x18000b455  call    cs:__imp_CloseHandle
0x18000b45b  mov     qword ptr [rdi+90h], 0
0x18000b466  mov     rcx, [rdi+78h]; hObject
0x18000b46a  lea     rax, [rcx-1]
0x18000b46e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000b472  ja      short loc_18000B482
0x18000b474  call    cs:__imp_CloseHandle
0x18000b47a  mov     qword ptr [rdi+78h], 0
0x18000b482  mov     rcx, rdi
0x18000b485  call    WdipFree
0x18000b48a  mov     eax, ebx
0x18000b48c  add     rsp, 38h
0x18000b490  pop     r15
0x18000b492  pop     r14
0x18000b494  pop     r12
0x18000b496  pop     rdi
0x18000b497  pop     rsi
0x18000b498  pop     rbx
0x18000b499  retn
```
