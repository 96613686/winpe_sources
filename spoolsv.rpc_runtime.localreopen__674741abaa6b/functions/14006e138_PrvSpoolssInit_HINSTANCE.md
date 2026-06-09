# PrvSpoolssInit(HINSTANCE__ *)

- ea: `0x14006e138`
- end: `0x14006e33f`
- name: `?PrvSpoolssInit@@YAHPEAUHINSTANCE__@@@Z`
- size: `519`
- prototype: `__int64 __fastcall(HINSTANCE hLibModule)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14004c580`

## callees

- `0x140008ca0`
- `0x140015574`
- `0x14002d0a0`
- `0x14006e00c`
- `0x14006e138`
- `0x14006e6c8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x14006e1a2`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x14006e1a2`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x14006e257`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x14006e27c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x14006e257`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x14006e27c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x14006e2dc`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x14006e2dc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14006e2bd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14006e2bd`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x14006e160`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x14006e160`
- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x14006e193`
- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x14006e193`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x14006e2ff`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x14006e2ff`
- `ADVAPI32!AllocateAndInitializeSid` at `0x14006e20a`
- `ADVAPI32!AllocateAndInitializeSid` at `0x14006e20a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x14006e22d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x14006e22d`

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
  dword_1400D2D4C = 1;
  v4 = InitializeCriticalSectionAndSpinCount(&DeviceArrivalCS, 0x80000000);
  if ( !v4 )
    goto LABEL_12;
  dword_1400D2D54 = 1;
  if ( (int)NCoreLibrary::CreateAutoEventHandle(1, (int)&pEventInit, v5) < 0 )
    goto LABEL_11;
  if ( (int)InitializeSessionInfo() < 0 )
    goto LABEL_11;
  hEventPoll = CreateEventW(0, 0, 0, 0);
  if ( !hEventPoll )
    goto LABEL_11;
  InitializeCriticalSection(&RouterNotifySection);
  dword_1400D2D50 = 1;
  v4 = ThreadInit();
  if ( !v4 )
  {
LABEL_12:
    PrvSpoolssCleanup();
    return v4;
  }
  dword_1400D2D48 = 1;
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
0x14006e138  mov     [rsp+arg_8], rbx
0x14006e13d  mov     [rsp+arg_10], rbp
0x14006e142  push    rdi
0x14006e143  sub     rsp, 70h
0x14006e147  mov     rax, cs:__security_cookie
0x14006e14e  xor     rax, rsp
0x14006e151  mov     [rsp+78h+var_10], rax
0x14006e156  mov     rbx, rcx
0x14006e159  xor     r8d, r8d; dwMaximumSize
0x14006e15c  xor     ecx, ecx; flOptions
0x14006e15e  xor     edx, edx; dwInitialSize
0x14006e160  call    cs:__imp_HeapCreate
0x14006e167  nop     dword ptr [rax+rax+00h]
0x14006e16c  mov     cs:?g_hSpoolssHeap@@3PEAXEA, rax; void * g_hSpoolssHeap
0x14006e173  test    rax, rax
0x14006e176  jz      loc_14006E316
0x14006e17c  mov     edi, 2
0x14006e181  lea     r8, [rsp+78h+HeapInformation]; HeapInformation
0x14006e186  xor     edx, edx; HeapInformationClass
0x14006e188  mov     [rsp+78h+HeapInformation], edi
0x14006e18c  mov     rcx, rax; HeapHandle
0x14006e18f  lea     r9d, [rdi+2]; HeapInformationLength
0x14006e193  call    cs:__imp_HeapSetInformation
0x14006e19a  nop     dword ptr [rax+rax+00h]
0x14006e19f  mov     rcx, rbx; hLibModule
0x14006e1a2  call    cs:__imp_DisableThreadLibraryCalls
0x14006e1a9  nop     dword ptr [rax+rax+00h]
0x14006e1ae  lea     rax, ?g_pAppContainerSid@@3PEAXEA; void * g_pAppContainerSid
0x14006e1b5  mov     [rsp+78h+HeapInformation], 0
0x14006e1bd  mov     [rsp+78h+pSid], rax; pSid
0x14006e1c2  lea     ebp, [rdi-1]
0x14006e1c5  mov     [rsp+78h+nSubAuthority7], 0; nSubAuthority7
0x14006e1cd  lea     rcx, [rsp+78h+HeapInformation]; pIdentifierAuthority
0x14006e1d2  mov     [rsp+78h+nSubAuthority6], 0; nSubAuthority6
0x14006e1da  mov     r9d, ebp; nSubAuthority1
0x14006e1dd  mov     [rsp+78h+nSubAuthority5], 0; nSubAuthority5
0x14006e1e5  mov     r8d, edi; nSubAuthority0
0x14006e1e8  mov     [rsp+78h+nSubAuthority4], 0; nSubAuthority4
0x14006e1f0  mov     dl, dil; nSubAuthorityCount
0x14006e1f3  mov     [rsp+78h+nSubAuthority3], 0; nSubAuthority3
0x14006e1fb  mov     [rsp+78h+nSubAuthority2], 0; nSubAuthority2
0x14006e203  mov     [rsp+78h+var_14], 0F00h
0x14006e20a  call    cs:__imp_AllocateAndInitializeSid
0x14006e211  nop     dword ptr [rax+rax+00h]
0x14006e216  xor     ebx, ebx
0x14006e218  lea     rdx, ?g_pLPACCapabilitySid@@3PEAXEA; Sid
0x14006e21f  test    eax, eax
0x14006e221  lea     rcx, aS1153102440448; "S-1-15-3-1024-4044835139-2658482041-312"...
0x14006e228  mov     edi, eax
0x14006e22a  setnz   bl
0x14006e22d  call    cs:__imp_ConvertStringSidToSidW
0x14006e234  nop     dword ptr [rax+rax+00h]
0x14006e239  test    eax, eax
0x14006e23b  jz      loc_14006E316
0x14006e241  test    edi, edi
0x14006e243  jz      loc_14006E318
0x14006e249  mov     edi, 80000000h
0x14006e24e  lea     rcx, ?RouterCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14006e255  mov     edx, edi; dwSpinCount
0x14006e257  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x14006e25e  nop     dword ptr [rax+rax+00h]
0x14006e263  mov     ebx, eax
0x14006e265  test    eax, eax
0x14006e267  jz      loc_14006E318
0x14006e26d  mov     edx, edi; dwSpinCount
0x14006e26f  mov     cs:dword_1400D2D4C, ebp
0x14006e275  lea     rcx, ?DeviceArrivalCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14006e27c  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x14006e283  nop     dword ptr [rax+rax+00h]
0x14006e288  mov     ebx, eax
0x14006e28a  test    eax, eax
0x14006e28c  jz      loc_14006E318
0x14006e292  lea     rdx, ?pEventInit@@3PEAVTAutoHandle@NCoreLibrary@@EA; int
0x14006e299  mov     cs:dword_1400D2D54, ebp
0x14006e29f  mov     ecx, ebp; bManualReset
0x14006e2a1  call    ?CreateAutoEventHandle@NCoreLibrary@@YAJHPEAPEAVTAutoHandle@1@@Z; NCoreLibrary::CreateAutoEventHandle(int,NCoreLibrary::TAutoHandle * *)
0x14006e2a6  test    eax, eax
0x14006e2a8  js      short loc_14006E316
0x14006e2aa  call    InitializeSessionInfo
0x14006e2af  test    eax, eax
0x14006e2b1  js      short loc_14006E316
0x14006e2b3  xor     r9d, r9d; lpName
0x14006e2b6  xor     r8d, r8d; bInitialState
0x14006e2b9  xor     edx, edx; bManualReset
0x14006e2bb  xor     ecx, ecx; lpEventAttributes
0x14006e2bd  call    cs:__imp_CreateEventW
0x14006e2c4  nop     dword ptr [rax+rax+00h]
0x14006e2c9  mov     cs:?hEventPoll@@3PEAXEA, rax; void * hEventPoll
0x14006e2d0  test    rax, rax
0x14006e2d3  jz      short loc_14006E316
0x14006e2d5  lea     rcx, ?RouterNotifySection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14006e2dc  call    cs:__imp_InitializeCriticalSection
0x14006e2e3  nop     dword ptr [rax+rax+00h]
0x14006e2e8  mov     cs:dword_1400D2D50, ebp
0x14006e2ee  call    ?ThreadInit@@YAHXZ; ThreadInit(void)
0x14006e2f3  mov     ebx, eax
0x14006e2f5  test    eax, eax
0x14006e2f7  jz      short loc_14006E318
0x14006e2f9  mov     cs:dword_1400D2D48, ebp
0x14006e2ff  call    cs:__imp_TlsAlloc
0x14006e306  nop     dword ptr [rax+rax+00h]
0x14006e30b  mov     cs:?gdwTlsGetPrinterIndex@@3KA, eax; ulong gdwTlsGetPrinterIndex
0x14006e311  cmp     eax, 0FFFFFFFFh
0x14006e314  jnz     short loc_14006E31D
0x14006e316  xor     ebx, ebx
0x14006e318  call    ?PrvSpoolssCleanup@@YAXXZ; PrvSpoolssCleanup(void)
0x14006e31d  mov     eax, ebx
0x14006e31f  mov     rcx, [rsp+78h+var_10]
0x14006e324  xor     rcx, rsp; StackCookie
0x14006e327  call    __security_check_cookie
0x14006e32c  lea     r11, [rsp+78h+var_8]
0x14006e331  mov     rbx, [r11+18h]
0x14006e335  mov     rbp, [r11+20h]
0x14006e339  mov     rsp, r11
0x14006e33c  pop     rdi
0x14006e33d  retn
```
