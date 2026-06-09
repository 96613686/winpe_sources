# GetServiceDllFunction

- ea: `0x140002e00`
- end: `0x140003172`
- name: `GetServiceDllFunction`
- size: `882`
- prototype: `FARPROC __fastcall(__int64, const CHAR *, DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140003180`

## callees

- `0x140002b90`
- `0x140002e00`
- `0x140004bd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002e64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002f6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002fa0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002fd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002e64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002f6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002fa0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002fd9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140002f5c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140002f5c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140002fcb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140002fcb`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140002f4a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x14000313b`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140002f4a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x14000313b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x140002f96`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x140002f96`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x140002ff5`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x140002ff5`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x140002e4c`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x140002e4c`

## pseudocode

```c
FARPROC __fastcall GetServiceDllFunction(__int64 a1, const CHAR *a2, DWORD *a3)
{
  void *v5; // rcx
  FARPROC ProcAddress; // r12
  __int64 v8; // rbx
  DWORD LastError; // edi
  __int64 v10; // r15
  char *v11; // rcx
  __int64 v12; // rax
  bool v13; // zf
  int v14; // eax
  HMODULE Library; // rax
  char *v16; // rcx
  __int64 v17; // rax
  int v18; // eax
  int v19; // ebx
  ULONG_PTR Cookie; // [rsp+38h] [rbp-C8h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v23; // [rsp+50h] [rbp-B0h] BYREF
  EVENT_DESCRIPTOR v24; // [rsp+58h] [rbp-A8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+70h] [rbp-90h] BYREF
  void *v26; // [rsp+80h] [rbp-80h]
  int v27; // [rsp+88h] [rbp-78h]
  int v28; // [rsp+8Ch] [rbp-74h]
  char *v29; // [rsp+90h] [rbp-70h]
  int v30; // [rsp+98h] [rbp-68h]
  int v31; // [rsp+9Ch] [rbp-64h]
  const CHAR *v32; // [rsp+A0h] [rbp-60h]
  int v33; // [rsp+A8h] [rbp-58h]
  int v34; // [rsp+ACh] [rbp-54h]
  __int64 *v35; // [rsp+B0h] [rbp-50h]
  __int64 v36; // [rsp+B8h] [rbp-48h]
  EVENT_DESCRIPTOR *p_EventDescriptor; // [rsp+C0h] [rbp-40h]
  __int64 v38; // [rsp+C8h] [rbp-38h]
  WCHAR WideCharStr[264]; // [rsp+D0h] [rbp-30h] BYREF

  v5 = *(void **)(a1 + 40);
  ProcAddress = 0;
  Cookie = 0;
  v8 = -1;
  if ( ActivateActCtx(v5, &Cookie) )
  {
    v10 = 3;
    if ( *(_QWORD *)(a1 + 16) )
      goto LABEL_38;
    if ( (unsigned int)dword_14000F000 > 5 )
    {
      v11 = *(char **)(a1 + 24);
      if ( v11 )
      {
        v12 = -1;
        do
          v13 = *(_WORD *)&v11[2 * v12++ + 2] == 0;
        while ( !v13 );
        v14 = 2 * v12 + 2;
      }
      else
      {
        v11 = "";
        v14 = 2;
      }
      v30 = v14;
      *(_DWORD *)&EventDescriptor.Level = 5;
      UserData.Ptr = (ULONGLONG)off_14000F008;
      v29 = v11;
      v31 = 0;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0;
      UserData.Size = *(unsigned __int16 *)off_14000F008;
      v26 = &unk_14000BAD7;
      UserData.Reserved = 2;
      v27 = 31;
      v28 = 1;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
    }
    Library = LoadLibraryExW(*(LPCWSTR *)(a1 + 24), 0, 8u);
    *(_QWORD *)(a1 + 16) = Library;
    if ( Library )
    {
LABEL_38:
      if ( MultiByteToWideChar(0, 0, a2, -1, WideCharStr, 260) )
      {
        LastError = ConfigCiSecurityPolicyCheck(a1, WideCharStr);
        if ( LastError )
        {
          v10 = 4;
        }
        else
        {
          ProcAddress = GetProcAddress(*(HMODULE *)(a1 + 16), a2);
          if ( ProcAddress )
          {
            LastError = 0;
            v10 = 0;
          }
          else
          {
            LastError = GetLastError();
            v10 = 5;
          }
        }
      }
      else
      {
        LastError = GetLastError();
      }
    }
    else
    {
      LastError = GetLastError();
      v10 = 2;
    }
    DeactivateActCtx(0, Cookie);
  }
  else
  {
    LastError = GetLastError();
    v10 = 1;
  }
  if ( a3 )
  {
    if ( LastError && (unsigned int)dword_14000F000 > 5 )
    {
      v16 = *(char **)(a1 + 24);
      if ( v16 )
      {
        v17 = -1;
        do
          v13 = *(_WORD *)&v16[2 * v17++ + 2] == 0;
        while ( !v13 );
        v18 = 2 * v17 + 2;
      }
      else
      {
        v16 = "";
        v18 = 2;
      }
      v29 = v16;
      v30 = v18;
      v31 = 0;
      if ( a2 )
      {
        do
          ++v8;
        while ( a2[v8] );
        v19 = v8 + 1;
      }
      else
      {
        a2 = (const CHAR *)&unk_14000ADED;
        v19 = 1;
      }
      v34 = 0;
      v35 = &v23;
      v24.Keyword = 0;
      v32 = a2;
      v33 = v19;
      v23 = v10;
      v36 = 8;
      v38 = 8;
      *(_DWORD *)&v24.Id = 184549376;
      *(_QWORD *)&EventDescriptor.Id = LastError;
      p_EventDescriptor = &EventDescriptor;
      *(_DWORD *)&v24.Level = 5;
      UserData.Ptr = (ULONGLONG)off_14000F008;
      UserData.Size = *(unsigned __int16 *)off_14000F008;
      v26 = &unk_14000BA7E;
      UserData.Reserved = 2;
      v27 = 77;
      v28 = 1;
      EventWriteTransfer(RegHandle, &v24, 0, 0, 6u, &UserData);
    }
    *a3 = LastError;
  }
  return ProcAddress;
}

```

## disassembly

```asm
0x140002e00  mov     [rsp-8+arg_18], rbx
0x140002e05  push    rbp
0x140002e06  push    rsi
0x140002e07  push    rdi
0x140002e08  push    r12
0x140002e0a  push    r13
0x140002e0c  push    r14
0x140002e0e  push    r15
0x140002e10  lea     rbp, [rsp-1F0h]
0x140002e18  sub     rsp, 2F0h
0x140002e1f  mov     rax, cs:__security_cookie
0x140002e26  xor     rax, rsp
0x140002e29  mov     [rbp+220h+var_40], rax
0x140002e30  mov     r14, rdx
0x140002e33  mov     rsi, rcx
0x140002e36  mov     rcx, [rcx+28h]; hActCtx
0x140002e3a  lea     rdx, [rsp+320h+Cookie]; lpCookie
0x140002e3f  xor     edi, edi
0x140002e41  mov     r13, r8
0x140002e44  mov     r12d, edi
0x140002e47  mov     [rsp+320h+Cookie], rdi
0x140002e4c  call    cs:__imp_ActivateActCtx
0x140002e52  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x140002e59  lea     rdx, _TraceLoggingMetadata
0x140002e60  test    eax, eax
0x140002e62  jnz     short loc_140002E77
0x140002e64  call    cs:__imp_GetLastError
0x140002e6a  mov     edi, eax
0x140002e6c  mov     r15d, 1
0x140002e72  jmp     loc_140002FFB
0x140002e77  mov     r15d, 3
0x140002e7d  cmp     [rsi+10h], rdi
0x140002e81  jnz     loc_140002F7B
0x140002e87  mov     eax, cs:dword_14000F000
0x140002e8d  cmp     eax, 5
0x140002e90  jbe     loc_140002F50
0x140002e96  mov     rcx, [rsi+18h]
0x140002e9a  test    rcx, rcx
0x140002e9d  jz      short loc_140002EB6
0x140002e9f  mov     rax, rbx
0x140002ea2  cmp     [rcx+rax*2+2], di
0x140002ea7  lea     rax, [rax+1]
0x140002eab  jnz     short loc_140002EA2
0x140002ead  lea     eax, ds:2[rax*2]
0x140002eb4  jmp     short loc_140002EC2
0x140002eb6  lea     rcx, aNourlmimefilte+10h; ""
0x140002ebd  mov     eax, 2
0x140002ec2  mov     [rbp+220h+var_288], eax
0x140002ec5  xor     r9d, r9d; RelatedActivityId
0x140002ec8  movzx   eax, cs:word_14000BACD
0x140002ecf  xor     r8d, r8d; ActivityId
0x140002ed2  mov     dword ptr [rsp+320h+EventDescriptor.Level], eax
0x140002ed6  mov     rax, cs:off_14000F008
0x140002edd  mov     [rsp+320h+var_2B0.Ptr], rax
0x140002ee2  mov     [rbp+220h+var_290], rcx
0x140002ee6  mov     [rbp+220h+var_284], edi
0x140002ee9  mov     dword ptr [rsp+320h+EventDescriptor.Id], 0B000000h
0x140002ef1  mov     [rsp+320h+EventDescriptor.Keyword], rdi
0x140002ef6  movzx   eax, word ptr [rax]
0x140002ef9  mov     [rsp+320h+var_2B0.Size], eax
0x140002efd  lea     rax, unk_14000BAD7
0x140002f04  mov     [rbp+220h+var_2A0], rax
0x140002f08  lea     rax, _TraceLoggingMetadataEnd
0x140002f0f  sub     eax, edx
0x140002f11  mov     dword ptr [rsp+320h+var_2B0.0Ch], 2
0x140002f19  mov     [rbp+220h+var_298], 1Fh
0x140002f20  lea     rdx, [rsp+320h+EventDescriptor]; EventDescriptor
0x140002f25  mov     [rbp+220h+var_294], 1
0x140002f2c  mov     [rsp+320h+var_2F0], eax
0x140002f30  mov     eax, [rsp+320h+var_2F0]
0x140002f34  mov     rcx, cs:RegHandle; RegHandle
0x140002f3b  lea     rax, [rsp+320h+var_2B0]
0x140002f40  mov     [rsp+320h+UserData], rax; UserData
0x140002f45  mov     [rsp+320h+UserDataCount], r15d; UserDataCount
0x140002f4a  call    cs:__imp_EventWriteTransfer
0x140002f50  mov     rcx, [rsi+18h]; lpLibFileName
0x140002f54  xor     edx, edx; hFile
0x140002f56  mov     r8d, 8; dwFlags
0x140002f5c  call    cs:__imp_LoadLibraryExW
0x140002f62  mov     [rsi+10h], rax
0x140002f66  test    rax, rax
0x140002f69  jnz     short loc_140002F7B
0x140002f6b  call    cs:__imp_GetLastError
0x140002f71  mov     edi, eax
0x140002f73  mov     r15d, 2
0x140002f79  jmp     short loc_140002FEE
0x140002f7b  lea     rax, [rbp+220h+WideCharStr]
0x140002f7f  mov     dword ptr [rsp+320h+UserData], 104h; cchWideChar
0x140002f87  mov     r9d, ebx; cbMultiByte
0x140002f8a  mov     qword ptr [rsp+320h+UserDataCount], rax; lpWideCharStr
0x140002f8f  mov     r8, r14; lpMultiByteStr
0x140002f92  xor     edx, edx; dwFlags
0x140002f94  xor     ecx, ecx; CodePage
0x140002f96  call    cs:__imp_MultiByteToWideChar
0x140002f9c  test    eax, eax
0x140002f9e  jnz     short loc_140002FAA
0x140002fa0  call    cs:__imp_GetLastError
0x140002fa6  mov     edi, eax
0x140002fa8  jmp     short loc_140002FEE
0x140002faa  lea     rdx, [rbp+220h+WideCharStr]
0x140002fae  mov     rcx, rsi
0x140002fb1  call    ConfigCiSecurityPolicyCheck
0x140002fb6  mov     edi, eax
0x140002fb8  test    eax, eax
0x140002fba  jz      short loc_140002FC4
0x140002fbc  mov     r15d, 4
0x140002fc2  jmp     short loc_140002FEE
0x140002fc4  mov     rcx, [rsi+10h]; hModule
0x140002fc8  mov     rdx, r14; lpProcName
0x140002fcb  call    cs:__imp_GetProcAddress
0x140002fd1  mov     r12, rax
0x140002fd4  test    rax, rax
0x140002fd7  jnz     short loc_140002FE9
0x140002fd9  call    cs:__imp_GetLastError
0x140002fdf  mov     edi, eax
0x140002fe1  mov     r15d, 5
0x140002fe7  jmp     short loc_140002FEE
0x140002fe9  xor     edi, edi
0x140002feb  xor     r15d, r15d
0x140002fee  mov     rdx, [rsp+320h+Cookie]; ulCookie
0x140002ff3  xor     ecx, ecx; dwFlags
0x140002ff5  call    cs:__imp_DeactivateActCtx
0x140002ffb  test    r13, r13
0x140002ffe  jz      loc_140003145
0x140003004  test    edi, edi
0x140003006  jz      loc_140003141
0x14000300c  mov     eax, cs:dword_14000F000
0x140003012  cmp     eax, 5
0x140003015  jbe     loc_140003141
0x14000301b  mov     rcx, [rsi+18h]
0x14000301f  test    rcx, rcx
0x140003022  jz      short loc_140003045
0x140003024  mov     rax, rbx
0x140003027  nop     word ptr [rax+rax+00000000h]
0x140003030  cmp     word ptr [rcx+rax*2+2], 0
0x140003036  lea     rax, [rax+1]
0x14000303a  jnz     short loc_140003030
0x14000303c  lea     eax, ds:2[rax*2]
0x140003043  jmp     short loc_140003051
0x140003045  lea     rcx, aNourlmimefilte+10h; ""
0x14000304c  mov     eax, 2
0x140003051  mov     [rbp+220h+var_290], rcx
0x140003055  xor     ecx, ecx
0x140003057  mov     [rbp+220h+var_288], eax
0x14000305a  mov     [rbp+220h+var_284], ecx
0x14000305d  test    r14, r14
0x140003060  jz      short loc_14000306F
0x140003062  inc     rbx
0x140003065  cmp     [r14+rbx], cl
0x140003069  jnz     short loc_140003062
0x14000306b  inc     ebx
0x14000306d  jmp     short loc_14000307B
0x14000306f  lea     r14, unk_14000ADED
0x140003076  mov     ebx, 1
0x14000307b  mov     [rbp+220h+var_274], ecx
0x14000307e  lea     rax, [rsp+320h+var_2D0]
0x140003083  mov     [rbp+220h+var_270], rax
0x140003087  lea     rdx, [rsp+320h+var_2C8]; EventDescriptor
0x14000308c  mov     [rsp+320h+var_2C8.Keyword], rcx
0x140003091  xor     r9d, r9d; RelatedActivityId
0x140003094  mov     [rbp+220h+var_280], r14
0x140003098  lea     rcx, _TraceLoggingMetadata
0x14000309f  mov     [rbp+220h+var_278], ebx
0x1400030a2  xor     r8d, r8d; ActivityId
0x1400030a5  mov     [rsp+320h+var_2D0], r15
0x1400030aa  mov     [rbp+220h+var_268], 8
0x1400030b2  mov     [rbp+220h+var_258], 8
0x1400030ba  mov     dword ptr [rsp+320h+var_2C8.Id], 0B000000h
0x1400030c2  mov     eax, edi
0x1400030c4  mov     qword ptr [rsp+320h+EventDescriptor.Id], rax
0x1400030c9  lea     rax, [rsp+320h+EventDescriptor]
0x1400030ce  mov     [rbp+220h+var_260], rax
0x1400030d2  movzx   eax, cs:word_14000BA74
0x1400030d9  mov     dword ptr [rsp+320h+var_2C8.Level], eax
0x1400030dd  mov     rax, cs:off_14000F008
0x1400030e4  mov     [rsp+320h+var_2B0.Ptr], rax
0x1400030e9  movzx   eax, word ptr [rax]
0x1400030ec  mov     [rsp+320h+var_2B0.Size], eax
0x1400030f0  lea     rax, unk_14000BA7E
0x1400030f7  mov     [rbp+220h+var_2A0], rax
0x1400030fb  lea     rax, _TraceLoggingMetadataEnd
0x140003102  sub     eax, ecx
0x140003104  mov     dword ptr [rsp+320h+var_2B0.0Ch], 2
0x14000310c  mov     [rbp+220h+var_298], 4Dh ; 'M'
0x140003113  mov     [rbp+220h+var_294], 1
0x14000311a  mov     [rsp+320h+var_2F0], eax
0x14000311e  mov     eax, [rsp+320h+var_2F0]
0x140003122  mov     rcx, cs:RegHandle; RegHandle
0x140003129  lea     rax, [rsp+320h+var_2B0]
0x14000312e  mov     [rsp+320h+UserData], rax; UserData
0x140003133  mov     [rsp+320h+UserDataCount], 6; UserDataCount
0x14000313b  call    cs:__imp_EventWriteTransfer
0x140003141  mov     [r13+0], edi
0x140003145  mov     rax, r12
0x140003148  mov     rcx, [rbp+220h+var_40]
0x14000314f  xor     rcx, rsp; StackCookie
0x140003152  call    __security_check_cookie
0x140003157  mov     rbx, [rsp+320h+arg_18]
0x14000315f  add     rsp, 2F0h
0x140003166  pop     r15
0x140003168  pop     r14
0x14000316a  pop     r13
0x14000316c  pop     r12
0x14000316e  pop     rdi
0x14000316f  pop     rsi
0x140003170  pop     rbp
0x140003171  retn
```
