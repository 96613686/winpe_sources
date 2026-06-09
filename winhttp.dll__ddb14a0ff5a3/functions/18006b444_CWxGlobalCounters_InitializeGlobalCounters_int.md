# CWxGlobalCounters::InitializeGlobalCounters(int)

- ea: `0x18006b444`
- end: `0x18006b791`
- name: `?InitializeGlobalCounters@CWxGlobalCounters@@AEAAJH@Z`
- size: `845`
- prototype: `__int64 __fastcall(CWxGlobalCounters *__hidden this, int)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18005036c`
- `0x18006b0ac`
- `0x18006b158`

## callees

- `0x18006b444`
- `0x1800995e8`
- `0x1800a1d10`
- `0x1800a2660`
- `0x1800cf008`
- `0x1800cf58c`
- `0x1800db6b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b5cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b660`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b68c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b6ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b5cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b660`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b68c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b6ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006b59c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006b59c`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x18006b52f`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x18006b52f`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18006b560`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18006b560`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18006b64e`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18006b64e`

## pseudocode

```c
__int64 __fastcall CWxGlobalCounters::InitializeGlobalCounters(CWxGlobalCounters *this, int a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  HANDLE v8; // rbx
  BOOL v9; // esi
  _QWORD *v10; // r15
  int v11; // edi
  DWORD v13; // eax
  signed int v14; // eax
  signed int LastError; // eax
  DWORD v16; // eax
  SIZE_T dwNumberOfBytesToMap; // [rsp+20h] [rbp-E0h]
  unsigned int v18; // [rsp+40h] [rbp-C0h]
  unsigned int v19; // [rsp+50h] [rbp-B0h]
  unsigned int *v20; // [rsp+58h] [rbp-A8h]
  unsigned int v21; // [rsp+60h] [rbp-A0h] BYREF
  int v22; // [rsp+64h] [rbp-9Ch]
  int v23; // [rsp+68h] [rbp-98h]
  int v24; // [rsp+6Ch] [rbp-94h]
  unsigned int v25[4]; // [rsp+70h] [rbp-90h] BYREF
  struct _SID *v26[4]; // [rsp+80h] [rbp-80h] BYREF
  struct _SECURITY_ATTRIBUTES FileMappingAttributes; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int8 v28[560]; // [rsp+C0h] [rbp-40h] BYREF

  memset_0(v28, 0, 0x228u);
  v21 = -1609564160;
  v25[0] = 12;
  v26[0] = (struct _SID *)c_rgbWorldSid;
  v26[1] = (struct _SID *)c_rgbWcmsvcSid;
  v26[2] = (struct _SID *)c_rgbDnsCacheSid;
  v26[3] = (struct _SID *)&c_rgbWinHttpAutoProxySvcSid;
  v22 = 0x10000000;
  v23 = 0x10000000;
  v24 = 0x10000000;
  memset(&FileMappingAttributes, 0, sizeof(FileMappingAttributes));
  v25[1] = 32;
  v25[2] = 32;
  v25[3] = 32;
  if ( (xmmword_180107A60 & 0x20) != 0 )
  {
    LODWORD(dwNumberOfBytesToMap) = a2;
    WPP_SF_qD(1029, 26, WPP_d4cae040b0b73edceba5bfba558ab8fc_Traceguids, this);
  }
  if ( a2 )
  {
    v8 = OpenFileMappingW(4u, 0, L"Global\\F932B6C7-3A20-46A0-B8A0-8894AA421973");
    if ( v8 )
    {
      v9 = 1;
LABEL_6:
      v10 = MapViewOfFile(v8, a2 != 0 ? 4 : 2, 0, 0, 8u);
      if ( v10 )
      {
        v11 = 0;
        if ( !a2 && !v9 )
        {
          if ( (xmmword_180107A60 & 0x20) != 0 )
            WPP_SF_(1029, 29, WPP_d4cae040b0b73edceba5bfba558ab8fc_Traceguids);
          *v10 = 0;
        }
        *((_QWORD *)this + 2) = v8;
        v8 = 0;
        *((_QWORD *)this + 3) = v10;
      }
      else
      {
        LastError = GetLastError();
        v11 = LastError;
        if ( LastError > 0 )
          v11 = (unsigned __int16)LastError | 0x80070000;
        v22 = 337;
        if ( v11 >= 0 )
          v11 = -2147418113;
      }
      goto LABEL_9;
    }
    v13 = GetLastError();
    if ( (xmmword_180107A60 & 0x20) != 0 )
      WPP_SF_d(1029, 28, WPP_d4cae040b0b73edceba5bfba558ab8fc_Traceguids, v13, dwNumberOfBytesToMap);
    v11 = -2147023728;
    v22 = 328;
  }
  else
  {
    v11 = ConstructSecurityDescriptorInternal(v5, v4, v6, v7, dwNumberOfBytesToMap, v26, v25, &v21, v18, v28, v19, v20);
    if ( v11 < 0 )
    {
      v8 = 0;
      v22 = 297;
      goto LABEL_9;
    }
    FileMappingAttributes.lpSecurityDescriptor = v28;
    v8 = CreateFileMappingW(
           (HANDLE)0xFFFFFFFFFFFFFFFFLL,
           &FileMappingAttributes,
           4u,
           0,
           8u,
           L"Global\\F932B6C7-3A20-46A0-B8A0-8894AA421973");
    if ( v8 )
    {
      v16 = GetLastError();
      v9 = v16 == 183;
      if ( (xmmword_180107A60 & 0x20) != 0 )
        WPP_SF_d(1029, 27, WPP_d4cae040b0b73edceba5bfba558ab8fc_Traceguids, v16 == 183, dwNumberOfBytesToMap);
      goto LABEL_6;
    }
    v14 = GetLastError();
    v11 = v14;
    if ( v14 > 0 )
      v11 = (unsigned __int16)v14 | 0x80070000;
    v22 = 307;
    if ( v11 >= 0 )
      v11 = -2147418113;
  }
LABEL_9:
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_d(1029, 30, WPP_d4cae040b0b73edceba5bfba558ab8fc_Traceguids, (unsigned int)v11, dwNumberOfBytesToMap);
  if ( v8 )
    CloseHandle(v8);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18006b444  mov     [rsp-8+arg_8], rbx
0x18006b449  mov     [rsp-8+arg_10], rsi
0x18006b44e  push    rbp
0x18006b44f  push    rdi
0x18006b450  push    r13
0x18006b452  push    r14
0x18006b454  push    r15
0x18006b456  lea     rbp, [rsp-200h]
0x18006b45e  sub     rsp, 300h
0x18006b465  mov     rax, cs:__security_cookie
0x18006b46c  xor     rax, rsp
0x18006b46f  mov     [rbp+220h+var_30], rax
0x18006b476  mov     r14d, edx
0x18006b479  mov     [rsp+320h+var_2BC], 0
0x18006b481  mov     r13, rcx
0x18006b484  xor     edx, edx; Val
0x18006b486  lea     rcx, [rbp+220h+var_260]; void *
0x18006b48a  mov     r8d, 228h; Size
0x18006b490  call    memset_0
0x18006b495  xor     eax, eax
0x18006b497  mov     [rsp+320h+var_2C0], 0A0100000h
0x18006b49f  mov     qword ptr [rbp+220h+FileMappingAttributes.bInheritHandle], rax
0x18006b4a3  xorps   xmm0, xmm0
0x18006b4a6  lea     rax, c_rgbWorldSid
0x18006b4ad  mov     [rsp+320h+var_2B0], 0Ch
0x18006b4b5  mov     [rbp+220h+var_2A0], rax
0x18006b4b9  lea     rax, c_rgbWcmsvcSid
0x18006b4c0  mov     [rbp+220h+var_298], rax
0x18006b4c4  lea     rax, c_rgbDnsCacheSid
0x18006b4cb  mov     [rbp+220h+var_290], rax
0x18006b4cf  lea     rax, c_rgbWinHttpAutoProxySvcSid
0x18006b4d6  mov     [rbp+220h+var_288], rax
0x18006b4da  mov     eax, 10000000h
0x18006b4df  mov     [rsp+320h+var_2BC], eax
0x18006b4e3  mov     [rsp+320h+var_2B8], eax
0x18006b4e7  mov     [rsp+320h+var_2B4], eax
0x18006b4eb  movups  xmmword ptr [rbp+220h+FileMappingAttributes.nLength], xmm0
0x18006b4ef  mov     [rsp+320h+var_2AC], 20h ; ' '
0x18006b4f7  mov     [rsp+320h+var_2A8], 20h ; ' '
0x18006b4ff  mov     [rsp+320h+var_2A4], 20h ; ' '
0x18006b507  test    byte ptr cs:xmmword_180107A60, 20h
0x18006b50e  jnz     loc_18006B6B8
0x18006b514  mov     r15d, 8
0x18006b51a  test    r14d, r14d
0x18006b51d  jz      loc_18006B5F1
0x18006b523  xor     edx, edx; bInheritHandle
0x18006b525  lea     r8, Name; "Global\\F932B6C7-3A20-46A0-B8A0-8894AA4"...
0x18006b52c  lea     ecx, [rdx+4]; dwDesiredAccess
0x18006b52f  call    cs:__imp_OpenFileMappingW
0x18006b535  mov     rbx, rax
0x18006b538  test    rax, rax
0x18006b53b  jz      loc_18006B5CF
0x18006b541  lea     esi, [r15-7]
0x18006b545  mov     eax, r14d
0x18006b548  mov     [rsp+320h+dwNumberOfBytesToMap], r15; dwNumberOfBytesToMap
0x18006b54d  neg     eax
0x18006b54f  mov     rcx, rbx; hFileMappingObject
0x18006b552  sbb     edx, edx
0x18006b554  xor     r9d, r9d; dwFileOffsetLow
0x18006b557  and     edx, 2
0x18006b55a  xor     r8d, r8d; dwFileOffsetHigh
0x18006b55d  add     edx, 2; dwDesiredAccess
0x18006b560  call    cs:__imp_MapViewOfFile
0x18006b566  mov     r15, rax
0x18006b569  test    rax, rax
0x18006b56c  jz      loc_18006B68C
0x18006b572  xor     edi, edi
0x18006b574  test    r14d, r14d
0x18006b577  jz      loc_18006B726
0x18006b57d  mov     [r13+10h], rbx
0x18006b581  xor     ebx, ebx
0x18006b583  mov     [r13+18h], r15
0x18006b587  test    byte ptr cs:xmmword_180107A60, 20h
0x18006b58e  jnz     loc_18006B773
0x18006b594  test    rbx, rbx
0x18006b597  jz      short loc_18006B5A2
0x18006b599  mov     rcx, rbx; hObject
0x18006b59c  call    cs:__imp_CloseHandle
0x18006b5a2  mov     eax, edi
0x18006b5a4  mov     rcx, [rbp+220h+var_30]
0x18006b5ab  xor     rcx, rsp; StackCookie
0x18006b5ae  call    __security_check_cookie
0x18006b5b3  lea     r11, [rsp+320h+var_20]
0x18006b5bb  mov     rbx, [r11+38h]
0x18006b5bf  mov     rsi, [r11+40h]
0x18006b5c3  mov     rsp, r11
0x18006b5c6  pop     r15
0x18006b5c8  pop     r14
0x18006b5ca  pop     r13
0x18006b5cc  pop     rdi
0x18006b5cd  pop     rbp
0x18006b5ce  retn
0x18006b5cf  call    cs:__imp_GetLastError
0x18006b5d5  test    byte ptr cs:xmmword_180107A60, 20h
0x18006b5dc  jnz     loc_18006B755
0x18006b5e2  mov     edi, 80070490h
0x18006b5e7  mov     [rsp+320h+var_2BC], 148h
0x18006b5ef  jmp     short loc_18006B587
0x18006b5f1  lea     rax, [rbp+220h+var_260]
0x18006b5f5  mov     [rsp+320h+var_2D8], rax; unsigned __int8 *
0x18006b5fa  lea     rax, [rsp+320h+var_2C0]
0x18006b5ff  mov     [rsp+320h+var_2E8], rax; unsigned int *
0x18006b604  lea     rax, [rsp+320h+var_2B0]
0x18006b609  mov     [rsp+320h+var_2F0], rax; unsigned int *
0x18006b60e  lea     rax, [rbp+220h+var_2A0]
0x18006b612  mov     [rsp+320h+lpName], rax; struct _SID **
0x18006b617  call    ?ConstructSecurityDescriptorInternal@@YAJKKKKKPEAPEAU_SID@@PEAK1KPEAEK1@Z; ConstructSecurityDescriptorInternal(ulong,ulong,ulong,ulong,ulong,_SID * *,ulong *,ulong *,ulong,uchar *,ulong,ulong *)
0x18006b61c  mov     edi, eax
0x18006b61e  test    eax, eax
0x18006b620  js      loc_18006B6DB
0x18006b626  lea     r8, Name; "Global\\F932B6C7-3A20-46A0-B8A0-8894AA4"...
0x18006b62d  xor     r9d, r9d; dwMaximumSizeHigh
0x18006b630  mov     [rsp+320h+lpName], r8; lpName
0x18006b635  lea     rax, [rbp+220h+var_260]
0x18006b639  lea     rdx, [rbp+220h+FileMappingAttributes]; lpFileMappingAttributes
0x18006b63d  mov     [rbp+220h+FileMappingAttributes.lpSecurityDescriptor], rax
0x18006b641  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18006b645  mov     dword ptr [rsp+320h+dwNumberOfBytesToMap], r15d; dwMaximumSizeLow
0x18006b64a  lea     r8d, [r9+4]; flProtect
0x18006b64e  call    cs:__imp_CreateFileMappingW
0x18006b654  mov     rbx, rax
0x18006b657  test    rax, rax
0x18006b65a  jnz     loc_18006B6EA
0x18006b660  call    cs:__imp_GetLastError
0x18006b666  mov     edi, eax
0x18006b668  test    eax, eax
0x18006b66a  jle     short loc_18006B675
0x18006b66c  movzx   edi, ax
0x18006b66f  or      edi, 80070000h
0x18006b675  test    edi, edi
0x18006b677  mov     [rsp+320h+var_2BC], 133h
0x18006b67f  mov     eax, 8000FFFFh
0x18006b684  cmovns  edi, eax
0x18006b687  jmp     loc_18006B587
0x18006b68c  call    cs:__imp_GetLastError
0x18006b692  mov     edi, eax
0x18006b694  test    eax, eax
0x18006b696  jle     short loc_18006B6A1
0x18006b698  movzx   edi, ax
0x18006b69b  or      edi, 80070000h
0x18006b6a1  test    edi, edi
0x18006b6a3  mov     [rsp+320h+var_2BC], 151h
0x18006b6ab  mov     eax, 8000FFFFh
0x18006b6b0  cmovns  edi, eax
0x18006b6b3  jmp     loc_18006B587
0x18006b6b8  mov     edx, 1Ah
0x18006b6bd  mov     dword ptr [rsp+320h+dwNumberOfBytesToMap], r14d
0x18006b6c2  mov     ecx, 405h
0x18006b6c7  lea     r8, WPP_d4cae040b0b73edceba5bfba558ab8fc_Traceguids
0x18006b6ce  mov     r9, r13
0x18006b6d1  call    WPP_SF_qD
0x18006b6d6  jmp     loc_18006B514
0x18006b6db  xor     ebx, ebx
0x18006b6dd  mov     [rsp+320h+var_2BC], 129h
0x18006b6e5  jmp     loc_18006B587
0x18006b6ea  call    cs:__imp_GetLastError
0x18006b6f0  xor     esi, esi
0x18006b6f2  cmp     eax, 0B7h
0x18006b6f7  setz    sil
0x18006b6fb  test    byte ptr cs:xmmword_180107A60, 20h
0x18006b702  jz      loc_18006B545
0x18006b708  mov     edx, 1Bh
0x18006b70d  lea     r8, WPP_d4cae040b0b73edceba5bfba558ab8fc_Traceguids
0x18006b714  mov     ecx, 405h
0x18006b719  mov     r9d, esi
0x18006b71c  call    WPP_SF_d
0x18006b721  jmp     loc_18006B545
0x18006b726  test    esi, esi
0x18006b728  jnz     loc_18006B57D
0x18006b72e  test    byte ptr cs:xmmword_180107A60, 20h
0x18006b735  jz      short loc_18006B74B
0x18006b737  lea     edx, [rsi+1Dh]
0x18006b73a  mov     ecx, 405h
0x18006b73f  lea     r8, WPP_d4cae040b0b73edceba5bfba558ab8fc_Traceguids
0x18006b746  call    WPP_SF_
0x18006b74b  xor     eax, eax
0x18006b74d  mov     [r15], rax
0x18006b750  jmp     loc_18006B57D
0x18006b755  mov     edx, 1Ch
0x18006b75a  lea     r8, WPP_d4cae040b0b73edceba5bfba558ab8fc_Traceguids
0x18006b761  mov     ecx, 405h
0x18006b766  mov     r9d, eax
0x18006b769  call    WPP_SF_d
0x18006b76e  jmp     loc_18006B5E2
0x18006b773  mov     edx, 1Eh
0x18006b778  lea     r8, WPP_d4cae040b0b73edceba5bfba558ab8fc_Traceguids
0x18006b77f  mov     ecx, 405h
0x18006b784  mov     r9d, edi
0x18006b787  call    WPP_SF_d
0x18006b78c  jmp     loc_18006B594
```
