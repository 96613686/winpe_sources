# GetServiceDllFunction

- ea: `0x1400030b0`
- end: `0x140003469`
- name: `GetServiceDllFunction`
- size: `953`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140003470`

## callees

- `0x140002e20`
- `0x1400030b0`
- `0x140004f90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000311a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003235`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003279`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400032be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000311a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003235`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003279`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400032be`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140003220`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140003220`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400032aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400032aa`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140003208`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x14000342b`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140003208`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x14000342b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x140003269`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x140003269`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x1400032e0`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x1400032e0`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x1400030fc`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x1400030fc`

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
0x1400030b0  mov     [rsp-8+arg_18], rbx
0x1400030b5  push    rbp
0x1400030b6  push    rsi
0x1400030b7  push    rdi
0x1400030b8  push    r12
0x1400030ba  push    r13
0x1400030bc  push    r14
0x1400030be  push    r15
0x1400030c0  lea     rbp, [rsp-1F0h]
0x1400030c8  sub     rsp, 2F0h
0x1400030cf  mov     rax, cs:__security_cookie
0x1400030d6  xor     rax, rsp
0x1400030d9  mov     [rbp+220h+var_40], rax
0x1400030e0  mov     r14, rdx
0x1400030e3  mov     rsi, rcx
0x1400030e6  mov     rcx, [rcx+28h]; hActCtx
0x1400030ea  lea     rdx, [rsp+320h+Cookie]; lpCookie
0x1400030ef  xor     edi, edi
0x1400030f1  mov     r13, r8
0x1400030f4  mov     r12d, edi
0x1400030f7  mov     [rsp+320h+Cookie], rdi
0x1400030fc  call    cs:__imp_ActivateActCtx
0x140003103  nop     dword ptr [rax+rax+00h]
0x140003108  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x14000310f  lea     rdx, _TraceLoggingMetadata
0x140003116  test    eax, eax
0x140003118  jnz     short loc_140003133
0x14000311a  call    cs:__imp_GetLastError
0x140003121  nop     dword ptr [rax+rax+00h]
0x140003126  mov     edi, eax
0x140003128  mov     r15d, 1
0x14000312e  jmp     loc_1400032EC
0x140003133  mov     r15d, 3
0x140003139  cmp     [rsi+10h], rdi
0x14000313d  jnz     loc_14000324E
0x140003143  mov     eax, cs:dword_14000F000
0x140003149  cmp     eax, 5
0x14000314c  jbe     loc_140003214
0x140003152  mov     rcx, [rsi+18h]
0x140003156  test    rcx, rcx
0x140003159  jz      short loc_140003174
0x14000315b  mov     rax, rbx
0x14000315e  xchg    ax, ax
0x140003160  cmp     [rcx+rax*2+2], di
0x140003165  lea     rax, [rax+1]
0x140003169  jnz     short loc_140003160
0x14000316b  lea     eax, ds:2[rax*2]
0x140003172  jmp     short loc_140003180
0x140003174  lea     rcx, aNourlmimefilte+10h; ""
0x14000317b  mov     eax, 2
0x140003180  mov     [rbp+220h+var_288], eax
0x140003183  xor     r9d, r9d; RelatedActivityId
0x140003186  movzx   eax, cs:word_14000BACD
0x14000318d  xor     r8d, r8d; ActivityId
0x140003190  mov     dword ptr [rsp+320h+EventDescriptor.Level], eax
0x140003194  mov     rax, cs:off_14000F008
0x14000319b  mov     [rsp+320h+var_2B0.Ptr], rax
0x1400031a0  mov     [rbp+220h+var_290], rcx
0x1400031a4  mov     [rbp+220h+var_284], edi
0x1400031a7  mov     dword ptr [rsp+320h+EventDescriptor.Id], 0B000000h
0x1400031af  mov     [rsp+320h+EventDescriptor.Keyword], rdi
0x1400031b4  movzx   eax, word ptr [rax]
0x1400031b7  mov     [rsp+320h+var_2B0.Size], eax
0x1400031bb  lea     rax, unk_14000BAD7
0x1400031c2  mov     [rbp+220h+var_2A0], rax
0x1400031c6  lea     rax, _TraceLoggingMetadataEnd
0x1400031cd  sub     eax, edx
0x1400031cf  mov     dword ptr [rsp+320h+var_2B0.0Ch], 2
0x1400031d7  mov     [rbp+220h+var_298], 1Fh
0x1400031de  lea     rdx, [rsp+320h+EventDescriptor]; EventDescriptor
0x1400031e3  mov     [rbp+220h+var_294], 1
0x1400031ea  mov     [rsp+320h+var_2F0], eax
0x1400031ee  mov     eax, [rsp+320h+var_2F0]
0x1400031f2  mov     rcx, cs:RegHandle; RegHandle
0x1400031f9  lea     rax, [rsp+320h+var_2B0]
0x1400031fe  mov     [rsp+320h+UserData], rax; UserData
0x140003203  mov     [rsp+320h+UserDataCount], r15d; UserDataCount
0x140003208  call    cs:__imp_EventWriteTransfer
0x14000320f  nop     dword ptr [rax+rax+00h]
0x140003214  mov     rcx, [rsi+18h]; lpLibFileName
0x140003218  xor     edx, edx; hFile
0x14000321a  mov     r8d, 8; dwFlags
0x140003220  call    cs:__imp_LoadLibraryExW
0x140003227  nop     dword ptr [rax+rax+00h]
0x14000322c  mov     [rsi+10h], rax
0x140003230  test    rax, rax
0x140003233  jnz     short loc_14000324E
0x140003235  call    cs:__imp_GetLastError
0x14000323c  nop     dword ptr [rax+rax+00h]
0x140003241  mov     edi, eax
0x140003243  mov     r15d, 2
0x140003249  jmp     loc_1400032D9
0x14000324e  lea     rax, [rbp+220h+WideCharStr]
0x140003252  mov     dword ptr [rsp+320h+UserData], 104h; cchWideChar
0x14000325a  mov     r9d, ebx; cbMultiByte
0x14000325d  mov     qword ptr [rsp+320h+UserDataCount], rax; lpWideCharStr
0x140003262  mov     r8, r14; lpMultiByteStr
0x140003265  xor     edx, edx; dwFlags
0x140003267  xor     ecx, ecx; CodePage
0x140003269  call    cs:__imp_MultiByteToWideChar
0x140003270  nop     dword ptr [rax+rax+00h]
0x140003275  test    eax, eax
0x140003277  jnz     short loc_140003289
0x140003279  call    cs:__imp_GetLastError
0x140003280  nop     dword ptr [rax+rax+00h]
0x140003285  mov     edi, eax
0x140003287  jmp     short loc_1400032D9
0x140003289  lea     rdx, [rbp+220h+WideCharStr]
0x14000328d  mov     rcx, rsi
0x140003290  call    ConfigCiSecurityPolicyCheck
0x140003295  mov     edi, eax
0x140003297  test    eax, eax
0x140003299  jz      short loc_1400032A3
0x14000329b  mov     r15d, 4
0x1400032a1  jmp     short loc_1400032D9
0x1400032a3  mov     rcx, [rsi+10h]; hModule
0x1400032a7  mov     rdx, r14; lpProcName
0x1400032aa  call    cs:__imp_GetProcAddress
0x1400032b1  nop     dword ptr [rax+rax+00h]
0x1400032b6  mov     r12, rax
0x1400032b9  test    rax, rax
0x1400032bc  jnz     short loc_1400032D4
0x1400032be  call    cs:__imp_GetLastError
0x1400032c5  nop     dword ptr [rax+rax+00h]
0x1400032ca  mov     edi, eax
0x1400032cc  mov     r15d, 5
0x1400032d2  jmp     short loc_1400032D9
0x1400032d4  xor     edi, edi
0x1400032d6  xor     r15d, r15d
0x1400032d9  mov     rdx, [rsp+320h+Cookie]; ulCookie
0x1400032de  xor     ecx, ecx; dwFlags
0x1400032e0  call    cs:__imp_DeactivateActCtx
0x1400032e7  nop     dword ptr [rax+rax+00h]
0x1400032ec  test    r13, r13
0x1400032ef  jz      loc_14000343B
0x1400032f5  test    edi, edi
0x1400032f7  jz      loc_140003437
0x1400032fd  mov     eax, cs:dword_14000F000
0x140003303  cmp     eax, 5
0x140003306  jbe     loc_140003437
0x14000330c  mov     rcx, [rsi+18h]
0x140003310  test    rcx, rcx
0x140003313  jz      short loc_140003335
0x140003315  mov     rax, rbx
0x140003318  nop     dword ptr [rax+rax+00000000h]
0x140003320  cmp     word ptr [rcx+rax*2+2], 0
0x140003326  lea     rax, [rax+1]
0x14000332a  jnz     short loc_140003320
0x14000332c  lea     eax, ds:2[rax*2]
0x140003333  jmp     short loc_140003341
0x140003335  lea     rcx, aNourlmimefilte+10h; ""
0x14000333c  mov     eax, 2
0x140003341  mov     [rbp+220h+var_290], rcx
0x140003345  xor     ecx, ecx
0x140003347  mov     [rbp+220h+var_288], eax
0x14000334a  mov     [rbp+220h+var_284], ecx
0x14000334d  test    r14, r14
0x140003350  jz      short loc_14000335F
0x140003352  inc     rbx
0x140003355  cmp     [r14+rbx], cl
0x140003359  jnz     short loc_140003352
0x14000335b  inc     ebx
0x14000335d  jmp     short loc_14000336B
0x14000335f  lea     r14, unk_14000ADED
0x140003366  mov     ebx, 1
0x14000336b  mov     [rbp+220h+var_274], ecx
0x14000336e  lea     rax, [rsp+320h+var_2D0]
0x140003373  mov     [rbp+220h+var_270], rax
0x140003377  lea     rdx, [rsp+320h+var_2C8]; EventDescriptor
0x14000337c  mov     [rsp+320h+var_2C8.Keyword], rcx
0x140003381  xor     r9d, r9d; RelatedActivityId
0x140003384  mov     [rbp+220h+var_280], r14
0x140003388  lea     rcx, _TraceLoggingMetadata
0x14000338f  mov     [rbp+220h+var_278], ebx
0x140003392  xor     r8d, r8d; ActivityId
0x140003395  mov     [rsp+320h+var_2D0], r15
0x14000339a  mov     [rbp+220h+var_268], 8
0x1400033a2  mov     [rbp+220h+var_258], 8
0x1400033aa  mov     dword ptr [rsp+320h+var_2C8.Id], 0B000000h
0x1400033b2  mov     eax, edi
0x1400033b4  mov     qword ptr [rsp+320h+EventDescriptor.Id], rax
0x1400033b9  lea     rax, [rsp+320h+EventDescriptor]
0x1400033be  mov     [rbp+220h+var_260], rax
0x1400033c2  movzx   eax, cs:word_14000BA74
0x1400033c9  mov     dword ptr [rsp+320h+var_2C8.Level], eax
0x1400033cd  mov     rax, cs:off_14000F008
0x1400033d4  mov     [rsp+320h+var_2B0.Ptr], rax
0x1400033d9  movzx   eax, word ptr [rax]
0x1400033dc  mov     [rsp+320h+var_2B0.Size], eax
0x1400033e0  lea     rax, unk_14000BA7E
0x1400033e7  mov     [rbp+220h+var_2A0], rax
0x1400033eb  lea     rax, _TraceLoggingMetadataEnd
0x1400033f2  sub     eax, ecx
0x1400033f4  mov     dword ptr [rsp+320h+var_2B0.0Ch], 2
0x1400033fc  mov     [rbp+220h+var_298], 4Dh ; 'M'
0x140003403  mov     [rbp+220h+var_294], 1
0x14000340a  mov     [rsp+320h+var_2F0], eax
0x14000340e  mov     eax, [rsp+320h+var_2F0]
0x140003412  mov     rcx, cs:RegHandle; RegHandle
0x140003419  lea     rax, [rsp+320h+var_2B0]
0x14000341e  mov     [rsp+320h+UserData], rax; UserData
0x140003423  mov     [rsp+320h+UserDataCount], 6; UserDataCount
0x14000342b  call    cs:__imp_EventWriteTransfer
0x140003432  nop     dword ptr [rax+rax+00h]
0x140003437  mov     [r13+0], edi
0x14000343b  mov     rax, r12
0x14000343e  mov     rcx, [rbp+220h+var_40]
0x140003445  xor     rcx, rsp; StackCookie
0x140003448  call    __security_check_cookie
0x14000344d  mov     rbx, [rsp+320h+arg_18]
0x140003455  add     rsp, 2F0h
0x14000345c  pop     r15
0x14000345e  pop     r14
0x140003460  pop     r13
0x140003462  pop     r12
0x140003464  pop     rdi
0x140003465  pop     rsi
0x140003466  pop     rbp
0x140003467  retn
```
