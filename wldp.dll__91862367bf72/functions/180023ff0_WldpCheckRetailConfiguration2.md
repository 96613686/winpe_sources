# WldpCheckRetailConfiguration2

- ea: `0x180023ff0`
- end: `0x180024367`
- name: `WldpCheckRetailConfiguration2`
- size: `887`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002ade4`
- `0x18002af60`

## callees

- `0x180021ec0`
- `0x180022a10`
- `0x1800239ac`
- `0x180023a04`
- `0x180023a5c`
- `0x180023cd0`
- `0x180023ff0`
- `0x18002b670`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024054`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002412b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024054`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002412b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002407d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024088`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002415b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002407d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024088`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002415b`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18002409c`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18002409c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024349`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024349`
- `ntdll!NtQuerySystemInformation` at `0x1800240d2`
- `ntdll!NtQuerySystemInformation` at `0x1800242d0`
- `ntdll!NtQuerySystemInformation` at `0x1800240d2`
- `ntdll!NtQuerySystemInformation` at `0x1800242d0`

## pseudocode

```c
__int64 __fastcall WldpCheckRetailConfiguration2(char a1, _DWORD *a2, int *a3, int *a4)
{
  int *v7; // rsi
  int v8; // r14d
  int v9; // edi
  int v10; // ebx
  NTSTATUS v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rcx
  int v14; // esi
  int v15; // eax
  __int64 *v16; // rdx
  __int64 v17; // r8
  __int64 v19; // r8
  __int64 i; // rsi
  int v21; // eax
  NTSTATUS v22; // ebx
  __int64 v23; // rcx
  __int64 v24; // r8
  signed int LastError; // eax
  int SystemInformation; // [rsp+30h] [rbp-D0h] BYREF
  int *v27; // [rsp+38h] [rbp-C8h]
  ULONG ReturnLength; // [rsp+40h] [rbp-C0h] BYREF
  ULONG v29; // [rsp+44h] [rbp-BCh] BYREF
  __int128 v30; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v31; // [rsp+58h] [rbp-A8h]
  _OSVERSIONINFOW VersionInformation; // [rsp+60h] [rbp-A0h] BYREF
  char v33; // [rsp+17Ah] [rbp+7Ah]
  struct _EVENT_DATA_DESCRIPTOR v34; // [rsp+180h] [rbp+80h] BYREF

  v27 = a4;
  v29 = 0;
  v7 = a4;
  memset_0(&VersionInformation, 0, 0x11Cu);
  EnterCriticalSection(&CheckedCriticalSection);
  if ( byte_18005AB78 == 1 )
  {
    v8 = dword_18005AB74;
    v9 = dword_18005AB70;
    v10 = dword_18005AB40;
    LeaveCriticalSection(&CheckedCriticalSection);
    goto LABEL_17;
  }
  LeaveCriticalSection(&CheckedCriticalSection);
  VersionInformation.dwOSVersionInfoSize = 284;
  v9 = 0;
  v8 = 0;
  if ( GetVersionExW(&VersionInformation) )
  {
    if ( v33 != 1 )
    {
      v10 = 0;
      goto LABEL_17;
    }
    LOWORD(SystemInformation) = 0;
    ReturnLength = 0;
    v11 = NtQuerySystemInformation(SystemObjectInformation|0x80, &SystemInformation, 2u, &ReturnLength);
    v12 = (unsigned int)v11;
    if ( v11 < 0 )
    {
      v13 = 0;
      v14 = 0;
    }
    else
    {
      v13 = BYTE1(SystemInformation);
      v14 = (unsigned __int8)SystemInformation;
    }
    v15 = v11 | 0x10000000;
    v10 = 0;
    if ( (int)v12 < 0 )
      v10 = v15;
    if ( v10 < 0 )
    {
      v8 = 1;
      if ( (Microsoft_Windows_VerifyHardwareSecurityEnableBits & 4) != 0 )
      {
        v16 = securebootEnabledFailedToCheck;
        goto LABEL_14;
      }
      goto LABEL_16;
    }
    if ( (_DWORD)v13 )
    {
      if ( (a1 & 1) != 0 )
      {
        if ( (Microsoft_Windows_VerifyHardwareSecurityEnableBits & 1) != 0 )
          McTemplateU0q_EventWriteTransfer(v13, v12, 1);
        if ( !v14 )
        {
          v9 = 1;
          LogFormatOut("TEST FAIL: SecureBoot: Secure Boot is not enabled\n");
          if ( (Microsoft_Windows_VerifyHardwareSecurityEnableBits & 2) != 0 )
            McGenEventWrite_EventWriteTransfer(
              v13,
              (const EVENT_DESCRIPTOR *)securebootEnabledFailedCheck,
              v19,
              1u,
              &v34);
        }
      }
      if ( (a1 & 2) != 0 )
      {
        SystemInformation = 0;
        if ( (Microsoft_Windows_VerifyHardwareSecurityEnableBits & 1) != 0 )
          McTemplateU0q_EventWriteTransfer(v13, v12, 2);
        for ( i = 0; (unsigned int)i < 3; i = (unsigned int)(i + 1) )
        {
          v21 = SearchThumbprintInEFI(&off_180043830[5 * i], v12, &SystemInformation);
          v10 = v21;
          if ( v21 < 0 )
          {
            v8 = 2;
            if ( (Microsoft_Windows_VerifyHardwareSecurityEnableBits & 4) == 0 )
              goto LABEL_16;
            v17 = (unsigned int)v21;
            v16 = certsFailedToCheck;
            goto LABEL_15;
          }
          if ( SystemInformation )
          {
            v9 |= 2u;
            LogFormatOut("TEST FAIL: SecureBoot: Found prohibited certs in list: %d\n", i);
          }
        }
      }
      if ( (a1 & 4) != 0 && (v9 & 1) == 0 )
      {
        if ( (Microsoft_Windows_VerifyHardwareSecurityEnableBits & 1) != 0 )
          McTemplateU0q_EventWriteTransfer(v13, v12, 4);
        v31 = 0;
        v30 = 0;
        v22 = NtQuerySystemInformation(SystemNonPagedPoolInformation|0x80, &v30, 0x18u, &v29);
        if ( v22 < 0 )
        {
          v10 = v22 | 0x10000000;
          v8 = 4;
          if ( (Microsoft_Windows_VerifyHardwareSecurityEnableBits & 4) != 0 )
          {
            v16 = securebootPolicyFailedToCheck;
LABEL_14:
            v17 = (unsigned int)v10;
LABEL_15:
            McTemplateU0d_EventWriteTransfer(v13, v16, v17);
          }
LABEL_16:
          v7 = v27;
          goto LABEL_17;
        }
        if ( (v31 & 0x1000000000LL) != 0 )
        {
          v9 |= 4u;
          LogFormatOut("TEST FAIL: SecureBoot: Invalid Secure Boot Policy option\n");
          if ( (Microsoft_Windows_VerifyHardwareSecurityEnableBits & 2) != 0 )
            McGenEventWrite_EventWriteTransfer(
              v23,
              (const EVENT_DESCRIPTOR *)securebootPolicyFailedCheck,
              v24,
              1u,
              &v34);
        }
      }
    }
    v10 = 0;
    goto LABEL_16;
  }
  LastError = GetLastError();
  v10 = LastError;
  if ( LastError > 0 )
    v10 = (unsigned __int16)LastError | 0x80070000;
LABEL_17:
  EnterCriticalSection(&CheckedCriticalSection);
  if ( !byte_18005AB78 )
  {
    dword_18005AB74 = v8;
    dword_18005AB70 = v9;
    dword_18005AB40 = v10;
    byte_18005AB78 = 1;
  }
  LeaveCriticalSection(&CheckedCriticalSection);
  if ( !v8 )
  {
    *a2 = v9 == 0;
    *v7 = v9;
  }
  *a3 = v8;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180023ff0  mov     [rsp-8+arg_0], rbx
0x180023ff5  push    rbp
0x180023ff6  push    rsi
0x180023ff7  push    rdi
0x180023ff8  push    r12
0x180023ffa  push    r13
0x180023ffc  push    r14
0x180023ffe  push    r15
0x180024000  lea     rbp, [rsp-0A0h]
0x180024008  sub     rsp, 1A0h
0x18002400f  mov     rax, cs:__security_cookie
0x180024016  xor     rax, rsp
0x180024019  mov     [rbp+0D0h+var_40], rax
0x180024020  mov     r12, r8
0x180024023  mov     [rsp+1D0h+var_198], r9
0x180024028  mov     r13, rdx
0x18002402b  mov     [rsp+1D0h+var_18C], 0
0x180024033  mov     r15d, ecx
0x180024036  mov     ebx, 11Ch
0x18002403b  mov     r8d, ebx; Size
0x18002403e  lea     rcx, [rsp+1D0h+VersionInformation]; void *
0x180024043  xor     edx, edx; Val
0x180024045  mov     rsi, r9
0x180024048  call    memset_0
0x18002404d  lea     rcx, CheckedCriticalSection; lpCriticalSection
0x180024054  call    cs:__imp_EnterCriticalSection
0x18002405a  cmp     cs:byte_18005AB78, 1
0x180024061  lea     rcx, CheckedCriticalSection; lpCriticalSection
0x180024068  jnz     short loc_180024088
0x18002406a  mov     r14d, cs:dword_18005AB74
0x180024071  mov     edi, cs:dword_18005AB70
0x180024077  mov     ebx, cs:dword_18005AB40
0x18002407d  call    cs:__imp_LeaveCriticalSection
0x180024083  jmp     loc_180024124
0x180024088  call    cs:__imp_LeaveCriticalSection
0x18002408e  lea     rcx, [rsp+1D0h+VersionInformation]; lpVersionInformation
0x180024093  mov     [rsp+1D0h+VersionInformation.dwOSVersionInfoSize], ebx
0x180024097  xor     edi, edi
0x180024099  xor     r14d, r14d
0x18002409c  call    cs:__imp_GetVersionExW
0x1800240a2  test    eax, eax
0x1800240a4  jz      loc_180024349
0x1800240aa  cmp     [rbp+0D0h+var_56], 1
0x1800240ae  jz      short loc_1800240B4
0x1800240b0  xor     ebx, ebx
0x1800240b2  jmp     short loc_180024124
0x1800240b4  xor     eax, eax
0x1800240b6  lea     r9, [rsp+1D0h+ReturnLength]; ReturnLength
0x1800240bb  lea     rdx, [rsp+1D0h+SystemInformation]; SystemInformation
0x1800240c0  mov     word ptr [rsp+1D0h+SystemInformation], ax
0x1800240c5  mov     ecx, 91h; SystemInformationClass
0x1800240ca  mov     [rsp+1D0h+ReturnLength], eax
0x1800240ce  lea     r8d, [rax+2]; SystemInformationLength
0x1800240d2  call    cs:__imp_NtQuerySystemInformation
0x1800240d8  mov     edx, eax
0x1800240da  test    eax, eax
0x1800240dc  js      short loc_1800240EA
0x1800240de  movzx   ecx, byte ptr [rsp+1D0h+SystemInformation+1]
0x1800240e3  movzx   esi, byte ptr [rsp+1D0h+SystemInformation]
0x1800240e8  jmp     short loc_1800240EE
0x1800240ea  xor     ecx, ecx
0x1800240ec  xor     esi, esi
0x1800240ee  bts     eax, 1Ch
0x1800240f2  xor     ebx, ebx
0x1800240f4  test    edx, edx
0x1800240f6  cmovs   ebx, eax
0x1800240f9  test    ebx, ebx
0x1800240fb  jns     loc_1800241A3
0x180024101  test    cs:Microsoft_Windows_VerifyHardwareSecurityEnableBits, 4
0x180024108  mov     r14d, 1
0x18002410e  jz      short loc_18002411F
0x180024110  lea     rdx, securebootEnabledFailedToCheck
0x180024117  mov     r8d, ebx
0x18002411a  call    McTemplateU0d_EventWriteTransfer
0x18002411f  mov     rsi, [rsp+1D0h+var_198]
0x180024124  lea     rcx, CheckedCriticalSection; lpCriticalSection
0x18002412b  call    cs:__imp_EnterCriticalSection
0x180024131  cmp     cs:byte_18005AB78, 0
0x180024138  jnz     short loc_180024154
0x18002413a  mov     cs:dword_18005AB74, r14d
0x180024141  mov     cs:dword_18005AB70, edi
0x180024147  mov     cs:dword_18005AB40, ebx
0x18002414d  mov     cs:byte_18005AB78, 1
0x180024154  lea     rcx, CheckedCriticalSection; lpCriticalSection
0x18002415b  call    cs:__imp_LeaveCriticalSection
0x180024161  test    r14d, r14d
0x180024164  jnz     short loc_180024173
0x180024166  xor     eax, eax
0x180024168  test    edi, edi
0x18002416a  setz    al
0x18002416d  mov     [r13+0], eax
0x180024171  mov     [rsi], edi
0x180024173  mov     [r12], r14d
0x180024177  mov     eax, ebx
0x180024179  mov     rcx, [rbp+0D0h+var_40]
0x180024180  xor     rcx, rsp; StackCookie
0x180024183  call    __security_check_cookie
0x180024188  mov     rbx, [rsp+1D0h+arg_0]
0x180024190  add     rsp, 1A0h
0x180024197  pop     r15
0x180024199  pop     r14
0x18002419b  pop     r13
0x18002419d  pop     r12
0x18002419f  pop     rdi
0x1800241a0  pop     rsi
0x1800241a1  pop     rbp
0x1800241a2  retn
0x1800241a3  test    ecx, ecx
0x1800241a5  jnz     short loc_1800241AE
0x1800241a7  xor     ebx, ebx
0x1800241a9  jmp     loc_18002411F
0x1800241ae  mov     ebx, 1
0x1800241b3  test    bl, r15b
0x1800241b6  jz      short loc_1800241FE
0x1800241b8  test    cs:Microsoft_Windows_VerifyHardwareSecurityEnableBits, bl
0x1800241be  jz      short loc_1800241C8
0x1800241c0  mov     r8d, ebx
0x1800241c3  call    McTemplateU0q_EventWriteTransfer
0x1800241c8  test    esi, esi
0x1800241ca  jnz     short loc_1800241FE
0x1800241cc  lea     rcx, aTestFailSecure; "TEST FAIL: SecureBoot: Secure Boot is n"...
0x1800241d3  mov     edi, ebx
0x1800241d5  call    LogFormatOut
0x1800241da  test    cs:Microsoft_Windows_VerifyHardwareSecurityEnableBits, 2
0x1800241e1  jz      short loc_1800241FE
0x1800241e3  lea     rax, [rbp+0D0h+var_50]
0x1800241ea  mov     r9d, ebx
0x1800241ed  lea     rdx, securebootEnabledFailedCheck
0x1800241f4  mov     [rsp+1D0h+var_1B0], rax
0x1800241f9  call    McGenEventWrite_EventWriteTransfer
0x1800241fe  test    r15b, 2
0x180024202  jz      loc_180024289
0x180024208  test    cs:Microsoft_Windows_VerifyHardwareSecurityEnableBits, bl
0x18002420e  mov     [rsp+1D0h+SystemInformation], r14d
0x180024213  jz      short loc_180024220
0x180024215  mov     r8d, 2
0x18002421b  call    McTemplateU0q_EventWriteTransfer
0x180024220  xor     esi, esi
0x180024222  cmp     esi, 3
0x180024225  jnb     short loc_180024289
0x180024227  lea     rax, off_180043830
0x18002422e  lea     rcx, [rsi+rsi*4]
0x180024232  lea     rcx, [rax+rcx*8]
0x180024236  lea     r8, [rsp+1D0h+SystemInformation]
0x18002423b  call    SearchThumbprintInEFI
0x180024240  mov     ebx, eax
0x180024242  test    eax, eax
0x180024244  js      short loc_180024267
0x180024246  cmp     [rsp+1D0h+SystemInformation], r14d
0x18002424b  jz      short loc_18002425E
0x18002424d  or      edi, 2
0x180024250  lea     rcx, aTestFailSecure_1; "TEST FAIL: SecureBoot: Found prohibited"...
0x180024257  mov     edx, esi
0x180024259  call    LogFormatOut
0x18002425e  mov     ebx, 1
0x180024263  add     esi, ebx
0x180024265  jmp     short loc_180024222
0x180024267  test    cs:Microsoft_Windows_VerifyHardwareSecurityEnableBits, 4
0x18002426e  mov     r14d, 2
0x180024274  jz      loc_18002411F
0x18002427a  mov     r8d, eax
0x18002427d  lea     rdx, certsFailedToCheck
0x180024284  jmp     loc_18002411A
0x180024289  test    r15b, 4
0x18002428d  jz      loc_1800241A7
0x180024293  test    bl, dil
0x180024296  jnz     loc_1800241A7
0x18002429c  test    cs:Microsoft_Windows_VerifyHardwareSecurityEnableBits, bl
0x1800242a2  jz      short loc_1800242AF
0x1800242a4  mov     r8d, 4
0x1800242aa  call    McTemplateU0q_EventWriteTransfer
0x1800242af  xor     eax, eax
0x1800242b1  lea     r9, [rsp+1D0h+var_18C]; ReturnLength
0x1800242b6  xorps   xmm0, xmm0
0x1800242b9  mov     [rsp+1D0h+var_178], rax
0x1800242be  lea     rdx, [rsp+1D0h+var_188]; SystemInformation
0x1800242c3  movups  [rsp+1D0h+var_188], xmm0
0x1800242c8  lea     r8d, [rax+18h]; SystemInformationLength
0x1800242cc  lea     ecx, [r8+77h]; SystemInformationClass
0x1800242d0  call    cs:__imp_NtQuerySystemInformation
0x1800242d6  mov     ebx, eax
0x1800242d8  test    eax, eax
0x1800242da  js      short loc_180024326
0x1800242dc  test    byte ptr [rsp+1D0h+var_178+4], 10h
0x1800242e1  jz      loc_1800241A7
0x1800242e7  lea     rcx, aTestFailSecure_0; "TEST FAIL: SecureBoot: Invalid Secure B"...
0x1800242ee  or      edi, 4
0x1800242f1  call    LogFormatOut
0x1800242f6  test    cs:Microsoft_Windows_VerifyHardwareSecurityEnableBits, 2
0x1800242fd  jz      loc_1800241A7
0x180024303  lea     rax, [rbp+0D0h+var_50]
0x18002430a  mov     r9d, 1
0x180024310  lea     rdx, securebootPolicyFailedCheck
0x180024317  mov     [rsp+1D0h+var_1B0], rax
0x18002431c  call    McGenEventWrite_EventWriteTransfer
0x180024321  jmp     loc_1800241A7
0x180024326  bts     ebx, 1Ch
0x18002432a  mov     r14d, 4
0x180024330  test    cs:Microsoft_Windows_VerifyHardwareSecurityEnableBits, r14b
0x180024337  jz      loc_18002411F
0x18002433d  lea     rdx, securebootPolicyFailedToCheck
0x180024344  jmp     loc_180024117
0x180024349  call    cs:__imp_GetLastError
0x18002434f  mov     ebx, eax
0x180024351  test    eax, eax
0x180024353  jle     loc_180024124
0x180024359  movzx   ebx, ax
0x18002435c  or      ebx, 80070000h
0x180024362  jmp     loc_180024124
```
