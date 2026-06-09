# InitGlobalState(void)

- ea: `0x18002c1c4`
- end: `0x18002c7c6`
- name: `?InitGlobalState@@YAJXZ`
- size: `1538`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180039100`

## callees

- `0x18000a7e0`
- `0x180019714`
- `0x18002c1c4`
- `0x18003dd2c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c4cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c7b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c4cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c7b5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002c6d7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002c6ff`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002c72b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002c74f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002c6d7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002c6ff`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002c72b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002c74f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002c494`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002c494`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c4b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c530`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c554`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c4b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c530`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c554`
- `ntdll!RtlInitUnicodeString` at `0x18002c57f`
- `ntdll!RtlInitUnicodeString` at `0x18002c57f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002c4fb`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002c4fb`

## pseudocode

```c
__int64 InitGlobalState(void)
{
  signed int v0; // ebx
  unsigned int v2; // edi
  struct _SECURITY_ATTRIBUTES *v3; // rax
  const WCHAR *v4; // rcx
  const WCHAR *v5; // rsi
  HANDLE EventW; // rax
  signed int v7; // eax
  signed int LastError; // eax
  __int128 v9; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v10; // [rsp+30h] [rbp-D0h]
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE *v12; // [rsp+50h] [rbp-B0h]
  LPCWSTR StringSecurityDescriptor; // [rsp+58h] [rbp-A8h]
  BOOL bManualReset[2]; // [rsp+60h] [rbp-A0h]
  LPCWSTR lpName[61]; // [rsp+68h] [rbp-98h] BYREF
  ULONG SecurityDescriptorSize; // [rsp+260h] [rbp+160h] BYREF
  HLOCAL hMem; // [rsp+268h] [rbp+168h] BYREF
  __int64 v18; // [rsp+270h] [rbp+170h]

  SecurityDescriptorSize = 0;
  hMem = 0;
  v10 = 0;
  v9 = 0;
  memset_0(&g_state, 0, 0x10E0u);
  v0 = myInitializeCriticalSection(&CriticalSection);
  if ( v0 < 0 )
    goto LABEL_2;
  g_state = 1;
  v0 = myInitializeCriticalSection(&stru_1800A45E0);
  if ( v0 < 0 )
    goto LABEL_2;
  byte_1800A4608 = 1;
  dword_1800A460C = 0;
  v0 = myInitializeCriticalSection(&stru_1800A4610);
  if ( v0 < 0 )
    goto LABEL_2;
  byte_1800A4638 = 1;
  v0 = myInitializeCriticalSection(&stru_1800A4660);
  if ( v0 < 0 )
    goto LABEL_2;
  byte_1800A4688 = 1;
  v12 = &hEvent;
  v2 = 0;
  StringSecurityDescriptor = 0;
  lpName[1] = (LPCWSTR)&qword_1800A36D0;
  lpName[5] = (LPCWSTR)&qword_1800A36D8;
  lpName[9] = (LPCWSTR)&qword_1800A36F0;
  lpName[13] = (LPCWSTR)&qword_1800A36E8;
  lpName[17] = (LPCWSTR)&qword_1800A36F8;
  lpName[18] = L"D:(A;;GA;;;LS)(A;;GA;;;SY)(A;;GA;;;BA)";
  lpName[20] = L"W32TIME_NAMED_EVENT_SYSTIME_NOT_CORRECT";
  lpName[21] = (LPCWSTR)&qword_1800A3710;
  lpName[25] = (LPCWSTR)&qword_1800A3718;
  lpName[29] = (LPCWSTR)&qword_1800A3700;
  lpName[33] = (LPCWSTR)&qword_1800A3708;
  lpName[37] = (LPCWSTR)&NotificationEventHandle;
  lpName[41] = (LPCWSTR)&qword_1800A3730;
  lpName[45] = (LPCWSTR)&qword_1800A3738;
  lpName[49] = (LPCWSTR)&qword_1800A3740;
  lpName[53] = (LPCWSTR)&qword_1800A3748;
  *(_QWORD *)bManualReset = 1;
  lpName[0] = 0;
  memset(&lpName[2], 0, 24);
  memset(&lpName[6], 0, 24);
  memset(&lpName[10], 0, 24);
  lpName[14] = 0;
  lpName[15] = (LPCWSTR)1;
  lpName[16] = 0;
  lpName[19] = 0;
  lpName[22] = 0;
  lpName[23] = (LPCWSTR)1;
  lpName[24] = 0;
  lpName[26] = 0;
  lpName[27] = (LPCWSTR)1;
  lpName[28] = 0;
  lpName[30] = 0;
  lpName[31] = (LPCWSTR)1;
  lpName[32] = 0;
  lpName[34] = 0;
  lpName[35] = (LPCWSTR)1;
  lpName[36] = 0;
  memset(&lpName[38], 0, 24);
  memset(&lpName[42], 0, 24);
  memset(&lpName[46], 0, 24);
  memset(&lpName[50], 0, 24);
  memset(&lpName[54], 0, 24);
  while ( 1 )
  {
    if ( v2 >= 0xF )
    {
      dword_1800A3810 = 3;
      dword_1800A3814 = 0;
      dword_1800A3818 = 0;
      dword_1800A3838 = 0;
      qword_1800A383C = 0;
      dword_1800A3844 = 0;
      qword_1800A3848 = 0;
      dword_1800A3820 = 0;
      qword_1800A3824 = 0;
      dword_1800A382C = 0;
      qword_1800A3830 = 0;
      *(_QWORD *)&qword_1800A4340 = 0;
      dword_1800A45C8 = 0;
      dword_1800A45CC = 0;
      dword_1800A45D0 = 0;
      dword_1800A45D4 = 0;
      dword_1800A45D8 = 0;
      dword_1800A45A4 = 10;
      dword_1800A45DC = 0;
      qword_1800A42F0 = 0;
      *(_OWORD *)&Src = 0;
      *(_OWORD *)&Base = 0;
      word_1800A45A8 = 0;
      byte_1800A45AA = 0;
      dword_1800A45AC = 1;
      byte_1800A45B4 = 0;
      qword_1800A37B8 = 0;
      s = 0;
      qword_1800A4658 = 0;
      byte_1800A4689 = 0;
      dword_1800A468C = 0;
      dword_1800A4690 = 1;
      hHandle = qword_1800A3700;
      Src = LocalAlloc(0x40u, 0x1630u);
      if ( Src
        && (*(&Src + 1) = LocalAlloc(0x40u, 16LL * (unsigned int)dword_1800A45A4)) != 0
        && (Base = LocalAlloc(0x40u, 48LL * (unsigned int)dword_1800A45A4)) != 0
        && (*(&Base + 1) = LocalAlloc(0x40u, 16LL * (unsigned int)dword_1800A45A4)) != 0 )
      {
        v18 = 12;
        RequiredPrivileges = (PPRIVILEGE_SET)&dword_1800A46A4;
        v0 = 0;
        qword_1800A46AC = 12;
        dword_1800A46A4 = 1;
        dword_1800A46A8 = 1;
        dword_1800A46B4 = 0;
      }
      else
      {
        v0 = -2147024882;
      }
      goto LABEL_2;
    }
    v3 = 0;
    v4 = *(const WCHAR **)&bManualReset[8 * v2 - 2];
    if ( v4 )
      break;
LABEL_11:
    v5 = lpName[4 * v2];
    EventW = CreateEventW(v3, bManualReset[8 * v2], bManualReset[8 * v2 + 1], v5);
    *(&v12)[4 * v2] = EventW;
    if ( !EventW || GetLastError() == 183 )
    {
      LastError = GetLastError();
      v0 = LastError;
      if ( LastError > 0 )
        v0 = (unsigned __int16)LastError | 0x80070000;
      DestinationString = 0;
      RtlInitUnicodeString(&DestinationString, v5);
      LogEvent(&_W32TimeRegistrationHandle, "*", L"u", &DestinationString);
      goto LABEL_2;
    }
    LocalFree(hMem);
    ++v2;
    hMem = 0;
  }
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(v4, 1u, &hMem, &SecurityDescriptorSize) )
  {
    LODWORD(v9) = SecurityDescriptorSize;
    *((_QWORD *)&v9 + 1) = hMem;
    v3 = (struct _SECURITY_ATTRIBUTES *)&v9;
    LODWORD(v10) = 0;
    goto LABEL_11;
  }
  v7 = GetLastError();
  v0 = v7;
  if ( v7 > 0 )
    v0 = (unsigned __int16)v7 | 0x80070000;
LABEL_2:
  if ( hMem )
    LocalFree(hMem);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x18002c1c4  mov     [rsp-8+arg_18], rbx
0x18002c1c9  push    rbp
0x18002c1ca  push    rsi
0x18002c1cb  push    rdi
0x18002c1cc  push    r14
0x18002c1ce  push    r15
0x18002c1d0  lea     rbp, [rsp-130h]
0x18002c1d8  sub     rsp, 230h
0x18002c1df  xor     r14d, r14d
0x18002c1e2  lea     rcx, ?g_state@@3UStateInfo@@A; void *
0x18002c1e9  xorps   xmm0, xmm0
0x18002c1ec  mov     [rbp+150h+SecurityDescriptorSize], r14d
0x18002c1f3  xor     eax, eax
0x18002c1f5  mov     [rbp+150h+hMem], r14
0x18002c1fc  xor     edx, edx; Val
0x18002c1fe  mov     [rsp+250h+var_220], rax
0x18002c203  mov     r8d, 10E0h; Size
0x18002c209  movups  [rsp+250h+var_230], xmm0
0x18002c20e  call    memset_0
0x18002c213  lea     rcx, CriticalSection; lpCriticalSection
0x18002c21a  call    ?myInitializeCriticalSection@@YAJPEAU_RTL_CRITICAL_SECTION@@@Z; myInitializeCriticalSection(_RTL_CRITICAL_SECTION *)
0x18002c21f  mov     ebx, eax
0x18002c221  test    eax, eax
0x18002c223  jns     short loc_18002C24F
0x18002c225  mov     rcx, [rbp+150h+hMem]; hMem
0x18002c22c  test    rcx, rcx
0x18002c22f  jnz     loc_18002C7B5
0x18002c235  mov     eax, ebx
0x18002c237  mov     rbx, [rsp+250h+arg_18]
0x18002c23f  add     rsp, 230h
0x18002c246  pop     r15
0x18002c248  pop     r14
0x18002c24a  pop     rdi
0x18002c24b  pop     rsi
0x18002c24c  pop     rbp
0x18002c24d  retn
0x18002c24f  mov     r15d, 1
0x18002c255  lea     rcx, stru_1800A45E0; lpCriticalSection
0x18002c25c  mov     cs:?g_state@@3UStateInfo@@A, r15d; StateInfo g_state
0x18002c263  call    ?myInitializeCriticalSection@@YAJPEAU_RTL_CRITICAL_SECTION@@@Z; myInitializeCriticalSection(_RTL_CRITICAL_SECTION *)
0x18002c268  mov     ebx, eax
0x18002c26a  test    eax, eax
0x18002c26c  js      short loc_18002C225
0x18002c26e  mov     cs:byte_1800A4608, r15b
0x18002c275  lea     rcx, stru_1800A4610; lpCriticalSection
0x18002c27c  mov     cs:dword_1800A460C, r14d
0x18002c283  call    ?myInitializeCriticalSection@@YAJPEAU_RTL_CRITICAL_SECTION@@@Z; myInitializeCriticalSection(_RTL_CRITICAL_SECTION *)
0x18002c288  mov     ebx, eax
0x18002c28a  test    eax, eax
0x18002c28c  js      short loc_18002C225
0x18002c28e  lea     rcx, stru_1800A4660; lpCriticalSection
0x18002c295  mov     cs:byte_1800A4638, r15b
0x18002c29c  call    ?myInitializeCriticalSection@@YAJPEAU_RTL_CRITICAL_SECTION@@@Z; myInitializeCriticalSection(_RTL_CRITICAL_SECTION *)
0x18002c2a1  mov     ebx, eax
0x18002c2a3  test    eax, eax
0x18002c2a5  js      loc_18002C225
0x18002c2ab  lea     rax, hEvent
0x18002c2b2  mov     cs:byte_1800A4688, r15b
0x18002c2b9  mov     [rsp+250h+var_200], rax
0x18002c2be  mov     edi, r14d
0x18002c2c1  lea     rax, qword_1800A36D0
0x18002c2c8  mov     [rsp+250h+StringSecurityDescriptor], r14
0x18002c2cd  mov     [rsp+250h+var_1E0], rax
0x18002c2d2  lea     rax, qword_1800A36D8
0x18002c2d9  mov     [rbp+150h+var_1C0], rax
0x18002c2dd  lea     rax, qword_1800A36F0
0x18002c2e4  mov     [rbp+150h+var_1A0], rax
0x18002c2e8  lea     rax, qword_1800A36E8
0x18002c2ef  mov     [rbp+150h+var_180], rax
0x18002c2f3  lea     rax, qword_1800A36F8
0x18002c2fa  mov     [rbp+150h+var_160], rax
0x18002c2fe  lea     rax, aDAGaLsAGaSyAGa; "D:(A;;GA;;;LS)(A;;GA;;;SY)(A;;GA;;;BA)"
0x18002c305  mov     [rbp+150h+var_158], rax
0x18002c309  lea     rax, aW32timeNamedEv; "W32TIME_NAMED_EVENT_SYSTIME_NOT_CORRECT"
0x18002c310  mov     [rbp+150h+var_148], rax
0x18002c314  lea     rax, qword_1800A3710
0x18002c31b  mov     [rbp+150h+var_140], rax
0x18002c31f  lea     rax, qword_1800A3718
0x18002c326  mov     [rbp+150h+var_120], rax
0x18002c32a  lea     rax, qword_1800A3700
0x18002c331  mov     [rbp+150h+var_100], rax
0x18002c335  lea     rax, qword_1800A3708
0x18002c33c  mov     [rbp+150h+var_E0], rax
0x18002c340  lea     rax, NotificationEventHandle
0x18002c347  mov     [rbp+150h+var_C0], rax
0x18002c34e  lea     rax, qword_1800A3730
0x18002c355  mov     [rbp+150h+var_A0], rax
0x18002c35c  lea     rax, qword_1800A3738
0x18002c363  mov     [rbp+150h+var_80], rax
0x18002c36a  lea     rax, qword_1800A3740
0x18002c371  mov     [rbp+150h+var_60], rax
0x18002c378  lea     rax, qword_1800A3748
0x18002c37f  mov     [rbp+150h+var_40], rax
0x18002c386  mov     qword ptr [rsp+250h+bManualReset], r15
0x18002c38b  mov     [rsp+250h+lpName], r14
0x18002c390  mov     [rsp+250h+var_1D8], r14
0x18002c395  mov     [rbp+150h+var_1D0], r14
0x18002c399  mov     [rbp+150h+var_1C8], r14
0x18002c39d  mov     [rbp+150h+var_1B8], r14
0x18002c3a1  mov     [rbp+150h+var_1B0], r14
0x18002c3a5  mov     [rbp+150h+var_1A8], r14
0x18002c3a9  mov     [rbp+150h+var_198], r14
0x18002c3ad  mov     [rbp+150h+var_190], r14
0x18002c3b1  mov     [rbp+150h+var_188], r14
0x18002c3b5  mov     [rbp+150h+var_178], r14
0x18002c3b9  mov     [rbp+150h+var_170], r15
0x18002c3bd  mov     [rbp+150h+var_168], r14
0x18002c3c1  mov     [rbp+150h+var_150], r14
0x18002c3c5  mov     [rbp+150h+var_138], r14
0x18002c3c9  mov     [rbp+150h+var_130], r15
0x18002c3cd  mov     [rbp+150h+var_128], r14
0x18002c3d1  mov     [rbp+150h+var_118], r14
0x18002c3d5  mov     [rbp+150h+var_110], r15
0x18002c3d9  mov     [rbp+150h+var_108], r14
0x18002c3dd  mov     [rbp+150h+var_F8], r14
0x18002c3e1  mov     [rbp+150h+var_F0], r15
0x18002c3e5  mov     [rbp+150h+var_E8], r14
0x18002c3e9  mov     [rbp+150h+var_D8], r14
0x18002c3ed  mov     [rbp+150h+var_D0], r15
0x18002c3f4  mov     [rbp+150h+var_C8], r14
0x18002c3fb  mov     [rbp+150h+var_B8], r14
0x18002c402  mov     [rbp+150h+var_B0], r14
0x18002c409  mov     [rbp+150h+var_A8], r14
0x18002c410  mov     [rbp+150h+var_98], r14
0x18002c417  mov     [rbp+150h+var_90], r14
0x18002c41e  mov     [rbp+150h+var_88], r14
0x18002c425  mov     [rbp+150h+var_78], r14
0x18002c42c  mov     [rbp+150h+var_70], r14
0x18002c433  mov     [rbp+150h+var_68], r14
0x18002c43a  mov     [rbp+150h+var_58], r14
0x18002c441  mov     [rbp+150h+var_50], r14
0x18002c448  mov     [rbp+150h+var_48], r14
0x18002c44f  mov     [rbp+150h+var_38], r14
0x18002c456  mov     [rbp+150h+var_30], r14
0x18002c45d  mov     [rbp+150h+var_28], r14
0x18002c464  cmp     edi, 0Fh
0x18002c467  jnb     loc_18002C5AF
0x18002c46d  mov     ebx, edi
0x18002c46f  mov     rax, r14
0x18002c472  shl     rbx, 5
0x18002c476  mov     rcx, [rsp+rbx+250h+StringSecurityDescriptor]; StringSecurityDescriptor
0x18002c47b  test    rcx, rcx
0x18002c47e  jnz     short loc_18002C4EA
0x18002c480  mov     rsi, [rsp+rbx+250h+lpName]
0x18002c485  mov     rcx, rax; lpEventAttributes
0x18002c488  mov     r8d, [rsp+rbx+250h+bManualReset+4]; bInitialState
0x18002c48d  mov     r9, rsi; lpName
0x18002c490  mov     edx, [rsp+rbx+250h+bManualReset]; bManualReset
0x18002c494  call    cs:__imp_CreateEventW
0x18002c49b  nop     dword ptr [rax+rax+00h]
0x18002c4a0  mov     rcx, [rsp+rbx+250h+var_200]
0x18002c4a5  mov     [rcx], rax
0x18002c4a8  test    rax, rax
0x18002c4ab  jz      loc_18002C554
0x18002c4b1  call    cs:__imp_GetLastError
0x18002c4b8  nop     dword ptr [rax+rax+00h]
0x18002c4bd  cmp     eax, 0B7h
0x18002c4c2  jz      loc_18002C554
0x18002c4c8  mov     rcx, [rbp+150h+hMem]; hMem
0x18002c4cf  call    cs:__imp_LocalFree
0x18002c4d6  nop     dword ptr [rax+rax+00h]
0x18002c4db  add     edi, r15d
0x18002c4de  mov     [rbp+150h+hMem], r14
0x18002c4e5  jmp     loc_18002C464
0x18002c4ea  lea     r9, [rbp+150h+SecurityDescriptorSize]; SecurityDescriptorSize
0x18002c4f1  mov     edx, r15d; StringSDRevision
0x18002c4f4  lea     r8, [rbp+150h+hMem]; SecurityDescriptor
0x18002c4fb  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18002c502  nop     dword ptr [rax+rax+00h]
0x18002c507  test    eax, eax
0x18002c509  jz      short loc_18002C530
0x18002c50b  mov     eax, [rbp+150h+SecurityDescriptorSize]
0x18002c511  mov     dword ptr [rsp+250h+var_230], eax
0x18002c515  mov     rax, [rbp+150h+hMem]
0x18002c51c  mov     qword ptr [rsp+250h+var_230+8], rax
0x18002c521  lea     rax, [rsp+250h+var_230]
0x18002c526  mov     dword ptr [rsp+250h+var_220], r14d
0x18002c52b  jmp     loc_18002C480
0x18002c530  call    cs:__imp_GetLastError
0x18002c537  nop     dword ptr [rax+rax+00h]
0x18002c53c  mov     ebx, eax
0x18002c53e  test    eax, eax
0x18002c540  jle     loc_18002C225
0x18002c546  movzx   ebx, ax
0x18002c549  or      ebx, 80070000h
0x18002c54f  jmp     loc_18002C225
0x18002c554  call    cs:__imp_GetLastError
0x18002c55b  nop     dword ptr [rax+rax+00h]
0x18002c560  mov     ebx, eax
0x18002c562  test    eax, eax
0x18002c564  jle     short loc_18002C56F
0x18002c566  movzx   ebx, ax
0x18002c569  or      ebx, 80070000h
0x18002c56f  xorps   xmm0, xmm0
0x18002c572  lea     rcx, [rsp+250h+DestinationString]; DestinationString
0x18002c577  mov     rdx, rsi; SourceString
0x18002c57a  movups  xmmword ptr [rsp+250h+DestinationString.Length], xmm0
0x18002c57f  call    cs:__imp_RtlInitUnicodeString
0x18002c586  nop     dword ptr [rax+rax+00h]
0x18002c58b  lea     r9, [rsp+250h+DestinationString]
0x18002c590  lea     r8, aU; "u"
0x18002c597  lea     rdx, W32TIME_EVENT_NAMED_EVENT_ALREADY_OPEN; "*"
0x18002c59e  lea     rcx, ?_W32TimeRegistrationHandle@@3_KA; unsigned __int64 _W32TimeRegistrationHandle
0x18002c5a5  call    LogEvent
0x18002c5aa  jmp     loc_18002C225
0x18002c5af  mov     rax, cs:qword_1800A3700
0x18002c5b6  mov     ecx, 0Ah
0x18002c5bb  mov     cs:dword_1800A3810, 3
0x18002c5c5  xorps   xmm0, xmm0
0x18002c5c8  mov     cs:dword_1800A3814, r14d
0x18002c5cf  xorps   xmm1, xmm1
0x18002c5d2  mov     cs:dword_1800A3818, r14d
0x18002c5d9  mov     cs:dword_1800A3838, r14d
0x18002c5e0  lea     ebx, [rcx+36h]
0x18002c5e3  mov     dword ptr cs:qword_1800A383C, r14d
0x18002c5ea  mov     dword ptr cs:qword_1800A383C+4, r14d
0x18002c5f1  mov     cs:dword_1800A3844, r14d
0x18002c5f8  mov     dword ptr cs:qword_1800A3848, r14d
0x18002c5ff  mov     dword ptr cs:qword_1800A3848+4, r14d
0x18002c606  mov     cs:dword_1800A3820, r14d
0x18002c60d  mov     dword ptr cs:qword_1800A3824, r14d
0x18002c614  mov     dword ptr cs:qword_1800A3824+4, r14d
0x18002c61b  mov     cs:dword_1800A382C, r14d
0x18002c622  mov     dword ptr cs:qword_1800A3830, r14d
0x18002c629  mov     dword ptr cs:qword_1800A3830+4, r14d
0x18002c630  mov     cs:qword_1800A4340, r14
0x18002c637  mov     cs:dword_1800A45C8, r14d
0x18002c63e  mov     cs:dword_1800A45CC, r14d
0x18002c645  mov     cs:dword_1800A45D0, r14d
0x18002c64c  mov     cs:dword_1800A45D4, r14d
0x18002c653  mov     cs:dword_1800A45D8, r14d
0x18002c65a  mov     cs:dword_1800A45A4, ecx
0x18002c660  mov     cs:dword_1800A45DC, r14d
0x18002c667  mov     cs:qword_1800A42F0, r14
0x18002c66e  movdqa  cs:Src, xmm0
0x18002c676  movdqa  cs:Base, xmm1
0x18002c67e  mov     cs:word_1800A45A8, r14w
0x18002c686  mov     cs:byte_1800A45AA, r14b
0x18002c68d  mov     cs:dword_1800A45AC, r15d
0x18002c694  mov     cs:byte_1800A45B4, r14b
0x18002c69b  mov     cs:qword_1800A37B8, r14
0x18002c6a2  mov     cs:s, r14
0x18002c6a9  mov     cs:qword_1800A4658, r14
0x18002c6b0  mov     cs:byte_1800A4689, r14b
0x18002c6b7  mov     cs:dword_1800A468C, r14d
0x18002c6be  mov     cs:dword_1800A4690, r15d
0x18002c6c5  mov     cs:hHandle, rax
0x18002c6cc  mov     eax, ecx
0x18002c6ce  mov     ecx, ebx; uFlags
0x18002c6d0  imul    rdx, rax, 238h; uBytes
0x18002c6d7  call    cs:__imp_LocalAlloc
0x18002c6de  nop     dword ptr [rax+rax+00h]
0x18002c6e3  mov     qword ptr cs:Src, rax
0x18002c6ea  test    rax, rax
0x18002c6ed  jz      loc_18002C7AB
0x18002c6f3  mov     edx, cs:dword_1800A45A4
0x18002c6f9  mov     ecx, ebx; uFlags
0x18002c6fb  shl     rdx, 4; uBytes
0x18002c6ff  call    cs:__imp_LocalAlloc
0x18002c706  nop     dword ptr [rax+rax+00h]
0x18002c70b  mov     qword ptr cs:Src+8, rax
0x18002c712  test    rax, rax
0x18002c715  jz      loc_18002C7AB
0x18002c71b  mov     eax, cs:dword_1800A45A4
0x18002c721  mov     ecx, ebx; uFlags
0x18002c723  lea     rdx, [rax+rax*2]
0x18002c727  shl     rdx, 4; uBytes
0x18002c72b  call    cs:__imp_LocalAlloc
0x18002c732  nop     dword ptr [rax+rax+00h]
0x18002c737  mov     qword ptr cs:Base, rax
0x18002c73e  test    rax, rax
0x18002c741  jz      short loc_18002C7AB
0x18002c743  mov     edx, cs:dword_1800A45A4
0x18002c749  mov     ecx, ebx; uFlags
0x18002c74b  shl     rdx, 4; uBytes
0x18002c74f  call    cs:__imp_LocalAlloc
0x18002c756  nop     dword ptr [rax+rax+00h]
0x18002c75b  mov     qword ptr cs:Base+8, rax
0x18002c762  test    rax, rax
0x18002c765  jz      short loc_18002C7AB
0x18002c767  lea     rax, dword_1800A46A4
0x18002c76e  mov     [rbp+150h+arg_10], 0Ch
0x18002c779  mov     cs:RequiredPrivileges, rax
0x18002c780  mov     ebx, r14d
0x18002c783  mov     rax, [rbp+150h+arg_10]
0x18002c78a  mov     cs:qword_1800A46AC, rax
0x18002c791  mov     cs:dword_1800A46A4, r15d
0x18002c798  mov     cs:dword_1800A46A8, r15d
0x18002c79f  mov     cs:dword_1800A46B4, r14d
0x18002c7a6  jmp     loc_18002C225
0x18002c7ab  mov     ebx, 8007000Eh
0x18002c7b0  jmp     loc_18002C225
0x18002c7b5  call    cs:__imp_LocalFree
0x18002c7bc  nop     dword ptr [rax+rax+00h]
0x18002c7c1  jmp     loc_18002C235
```
