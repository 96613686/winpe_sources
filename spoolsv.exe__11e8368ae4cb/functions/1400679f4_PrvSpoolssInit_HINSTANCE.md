# PrvSpoolssInit(HINSTANCE__ *)

- ea: `0x1400679f4`
- end: `0x140067bba`
- name: `?PrvSpoolssInit@@YAHPEAUHINSTANCE__@@@Z`
- size: `454`
- prototype: `__int64 __fastcall(HINSTANCE hLibModule)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140048140`

## callees

- `0x140008094`
- `0x1400142c4`
- `0x14002abc0`
- `0x1400678ec`
- `0x1400679f4`
- `0x140067f10`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x140067a52`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x140067a52`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x140067af5`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x140067b14`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x140067af5`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x140067b14`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x140067b64`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x140067b64`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140067b4b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140067b4b`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x140067a1c`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x140067a1c`
- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x140067a49`
- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x140067a49`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x140067b81`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x140067b81`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140067ab4`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140067ab4`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x140067ad1`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x140067ad1`

## pseudocode

```c
__int64 __fastcall PrvSpoolssInit(HINSTANCE hLibModule)
{
  HANDLE v2; // rax
  BOOL v3; // edi
  unsigned int v4; // ebx
  struct NCoreLibrary::TAutoHandle **v5; // r8
  struct _SID_IDENTIFIER_AUTHORITY HeapInformation; // [rsp+60h] [rbp-18h] BYREF

  v2 = HeapCreate(0, 0, 0);
  g_hSpoolssHeap = v2;
  if ( !v2 )
    goto LABEL_11;
  *(_DWORD *)HeapInformation.Value = 2;
  HeapSetInformation(v2, HeapCompatibilityInformation, &HeapInformation, 4u);
  DisableThreadLibraryCalls(hLibModule);
  *(_DWORD *)HeapInformation.Value = 0;
  *(_WORD *)&HeapInformation.Value[4] = 3840;
  v3 = AllocateAndInitializeSid(&HeapInformation, 2u, 2u, 1u, 0, 0, 0, 0, 0, 0, &g_pAppContainerSid);
  v4 = v3;
  if ( !ConvertStringSidToSidW(
          L"S-1-15-3-1024-4044835139-2658482041-3127973164-329287231-3865880861-1938685643-461067658-1087000422",
          &g_pLPACCapabilitySid) )
    goto LABEL_11;
  if ( !v3 )
    goto LABEL_12;
  v4 = InitializeCriticalSectionAndSpinCount(&RouterCriticalSection, 0x80000000);
  if ( !v4 )
    goto LABEL_12;
  dword_1400CBBDC = 1;
  v4 = InitializeCriticalSectionAndSpinCount(&DeviceArrivalCS, 0x80000000);
  if ( !v4 )
    goto LABEL_12;
  dword_1400CBBD4 = 1;
  if ( (int)NCoreLibrary::CreateAutoEventHandle(1, (int)&pEventInit, v5) < 0 )
    goto LABEL_11;
  if ( (int)InitializeSessionInfo() < 0 )
    goto LABEL_11;
  hEventPoll = CreateEventW(0, 0, 0, 0);
  if ( !hEventPoll )
    goto LABEL_11;
  InitializeCriticalSection(&RouterNotifySection);
  dword_1400CBBD0 = 1;
  v4 = ThreadInit();
  if ( !v4 )
  {
LABEL_12:
    PrvSpoolssCleanup();
    return v4;
  }
  dword_1400CBBD8 = 1;
  gdwTlsGetPrinterIndex = TlsAlloc();
  if ( gdwTlsGetPrinterIndex == -1 )
  {
LABEL_11:
    v4 = 0;
    goto LABEL_12;
  }
  return v4;
}

```

## disassembly

```asm
0x1400679f4  mov     [rsp+arg_8], rbx
0x1400679f9  mov     [rsp+arg_10], rbp
0x1400679fe  push    rdi
0x1400679ff  sub     rsp, 70h
0x140067a03  mov     rax, cs:__security_cookie
0x140067a0a  xor     rax, rsp
0x140067a0d  mov     [rsp+78h+var_10], rax
0x140067a12  mov     rbx, rcx
0x140067a15  xor     r8d, r8d; dwMaximumSize
0x140067a18  xor     ecx, ecx; flOptions
0x140067a1a  xor     edx, edx; dwInitialSize
0x140067a1c  call    cs:__imp_HeapCreate
0x140067a22  mov     cs:?g_hSpoolssHeap@@3PEAXEA, rax; void * g_hSpoolssHeap
0x140067a29  test    rax, rax
0x140067a2c  jz      loc_140067B92
0x140067a32  mov     edi, 2
0x140067a37  lea     r8, [rsp+78h+HeapInformation]; HeapInformation
0x140067a3c  xor     edx, edx; HeapInformationClass
0x140067a3e  mov     [rsp+78h+HeapInformation], edi
0x140067a42  mov     rcx, rax; HeapHandle
0x140067a45  lea     r9d, [rdi+2]; HeapInformationLength
0x140067a49  call    cs:__imp_HeapSetInformation
0x140067a4f  mov     rcx, rbx; hLibModule
0x140067a52  call    cs:__imp_DisableThreadLibraryCalls
0x140067a58  lea     rax, ?g_pAppContainerSid@@3PEAXEA; void * g_pAppContainerSid
0x140067a5f  mov     [rsp+78h+HeapInformation], 0
0x140067a67  mov     [rsp+78h+pSid], rax; pSid
0x140067a6c  lea     ebp, [rdi-1]
0x140067a6f  mov     [rsp+78h+nSubAuthority7], 0; nSubAuthority7
0x140067a77  lea     rcx, [rsp+78h+HeapInformation]; pIdentifierAuthority
0x140067a7c  mov     [rsp+78h+nSubAuthority6], 0; nSubAuthority6
0x140067a84  mov     r9d, ebp; nSubAuthority1
0x140067a87  mov     [rsp+78h+nSubAuthority5], 0; nSubAuthority5
0x140067a8f  mov     r8d, edi; nSubAuthority0
0x140067a92  mov     [rsp+78h+nSubAuthority4], 0; nSubAuthority4
0x140067a9a  mov     dl, dil; nSubAuthorityCount
0x140067a9d  mov     [rsp+78h+nSubAuthority3], 0; nSubAuthority3
0x140067aa5  mov     [rsp+78h+nSubAuthority2], 0; nSubAuthority2
0x140067aad  mov     [rsp+78h+var_14], 0F00h
0x140067ab4  call    cs:__imp_AllocateAndInitializeSid
0x140067aba  xor     ebx, ebx
0x140067abc  lea     rdx, ?g_pLPACCapabilitySid@@3PEAXEA; Sid
0x140067ac3  test    eax, eax
0x140067ac5  lea     rcx, aS1153102440448; "S-1-15-3-1024-4044835139-2658482041-312"...
0x140067acc  mov     edi, eax
0x140067ace  setnz   bl
0x140067ad1  call    cs:__imp_ConvertStringSidToSidW
0x140067ad7  test    eax, eax
0x140067ad9  jz      loc_140067B92
0x140067adf  test    edi, edi
0x140067ae1  jz      loc_140067B94
0x140067ae7  mov     edi, 80000000h
0x140067aec  lea     rcx, ?RouterCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140067af3  mov     edx, edi; dwSpinCount
0x140067af5  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x140067afb  mov     ebx, eax
0x140067afd  test    eax, eax
0x140067aff  jz      loc_140067B94
0x140067b05  mov     edx, edi; dwSpinCount
0x140067b07  mov     cs:dword_1400CBBDC, ebp
0x140067b0d  lea     rcx, ?DeviceArrivalCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140067b14  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x140067b1a  mov     ebx, eax
0x140067b1c  test    eax, eax
0x140067b1e  jz      short loc_140067B94
0x140067b20  lea     rdx, ?pEventInit@@3PEAVTAutoHandle@NCoreLibrary@@EA; int
0x140067b27  mov     cs:dword_1400CBBD4, ebp
0x140067b2d  mov     ecx, ebp; bManualReset
0x140067b2f  call    ?CreateAutoEventHandle@NCoreLibrary@@YAJHPEAPEAVTAutoHandle@1@@Z; NCoreLibrary::CreateAutoEventHandle(int,NCoreLibrary::TAutoHandle * *)
0x140067b34  test    eax, eax
0x140067b36  js      short loc_140067B92
0x140067b38  call    InitializeSessionInfo
0x140067b3d  test    eax, eax
0x140067b3f  js      short loc_140067B92
0x140067b41  xor     r9d, r9d; lpName
0x140067b44  xor     r8d, r8d; bInitialState
0x140067b47  xor     edx, edx; bManualReset
0x140067b49  xor     ecx, ecx; lpEventAttributes
0x140067b4b  call    cs:__imp_CreateEventW
0x140067b51  mov     cs:?hEventPoll@@3PEAXEA, rax; void * hEventPoll
0x140067b58  test    rax, rax
0x140067b5b  jz      short loc_140067B92
0x140067b5d  lea     rcx, ?RouterNotifySection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140067b64  call    cs:__imp_InitializeCriticalSection
0x140067b6a  mov     cs:dword_1400CBBD0, ebp
0x140067b70  call    ?ThreadInit@@YAHXZ; ThreadInit(void)
0x140067b75  mov     ebx, eax
0x140067b77  test    eax, eax
0x140067b79  jz      short loc_140067B94
0x140067b7b  mov     cs:dword_1400CBBD8, ebp
0x140067b81  call    cs:__imp_TlsAlloc
0x140067b87  mov     cs:?gdwTlsGetPrinterIndex@@3KA, eax; ulong gdwTlsGetPrinterIndex
0x140067b8d  cmp     eax, 0FFFFFFFFh
0x140067b90  jnz     short loc_140067B99
0x140067b92  xor     ebx, ebx
0x140067b94  call    ?PrvSpoolssCleanup@@YAXXZ; PrvSpoolssCleanup(void)
0x140067b99  mov     eax, ebx
0x140067b9b  mov     rcx, [rsp+78h+var_10]
0x140067ba0  xor     rcx, rsp; StackCookie
0x140067ba3  call    __security_check_cookie
0x140067ba8  lea     r11, [rsp+78h+var_8]
0x140067bad  mov     rbx, [r11+18h]
0x140067bb1  mov     rbp, [r11+20h]
0x140067bb5  mov     rsp, r11
0x140067bb8  pop     rdi
0x140067bb9  retn
```
