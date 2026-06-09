# WapTcpExtractSocket

- ea: `0x18008dd88`
- end: `0x18008dfed`
- name: `WapTcpExtractSocket`
- size: `613`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18006e4a0`

## callees

- `0x1800464f4`
- `0x18005dadc`
- `0x1800722f0`
- `0x18008dd88`
- `0x1800923bc`
- `0x1800971ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008de0e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008de0e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008de2b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008de58`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008de2b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008de58`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008de6e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008de6e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008dea9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008ded6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008dea9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008ded6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18008df96`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18008df96`
- `ntdll!NtSetInformationFile` at `0x18008df3a`
- `ntdll!NtSetInformationFile` at `0x18008df3a`
- `WS2_32!__imp_closesocket` at `0x18008df82`
- `WS2_32!__imp_closesocket` at `0x18008df82`
- `WS2_32!__imp_setsockopt` at `0x18008df03`
- `WS2_32!__imp_setsockopt` at `0x18008df03`

## pseudocode

```c
__int64 __fastcall WapTcpExtractSocket(__int64 a1, SOCKET *a2)
{
  unsigned int Error; // ebx
  SOCKET v5; // rsi
  struct _TP_IO *v6; // rbp
  char optval[8]; // [rsp+30h] [rbp-58h] BYREF
  __int128 FileInformation; // [rsp+38h] [rbp-50h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+48h] [rbp-40h] BYREF

  *(_DWORD *)optval = 0;
  IoStatusBlock = 0;
  FileInformation = 0;
  if ( (xmmword_1800AD720 & 8) != 0 )
    WPP_SF_qq(1027, 69, (unsigned int)WPP_14086b36644f38024399eb8d606249d9_Traceguids, a1, (__int64)a2);
  if ( !a2 )
  {
    Error = 87;
    goto LABEL_25;
  }
  *a2 = -1;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
  Error = 5023;
  if ( *(_DWORD *)(a1 + 224) != 4 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
    goto LABEL_25;
  }
  if ( !*(_DWORD *)(a1 + 232) )
    *(_DWORD *)(a1 + 232) = 5023;
  *(_DWORD *)(a1 + 224) = 6;
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 696));
  v5 = *(_QWORD *)(a1 + 704);
  if ( v5 == -1 )
  {
    Error = *(_DWORD *)(a1 + 232);
    if ( !Error )
      Error = 1359;
  }
  else if ( !*(_BYTE *)(a1 + 980) )
  {
    v6 = *(struct _TP_IO **)(a1 + 712);
    *(_QWORD *)(a1 + 712) = 0;
    *(_QWORD *)(a1 + 704) = -1;
    ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 696));
    *(_DWORD *)optval = 0;
    if ( setsockopt(v5, 6, 1, optval, 4) == -1 )
    {
      Error = WaWSAGetLastError(0);
    }
    else if ( !NtSetInformationFile(
                 (HANDLE)v5,
                 &IoStatusBlock,
                 &FileInformation,
                 0x10u,
                 FileMaximumInformation|FileStandardInformation) )
    {
      Error = 0;
      if ( (xmmword_1800AD720 & 8) != 0 )
        WPP_SF_d(1027, 70, WPP_14086b36644f38024399eb8d606249d9_Traceguids, (unsigned int)v5);
      *a2 = v5;
      v5 = -1;
    }
    goto LABEL_21;
  }
  v6 = 0;
  v5 = -1;
  ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 696));
LABEL_21:
  WapTcpIndicateCleanupEvent(a1);
  if ( v5 != -1 )
    closesocket(v5);
  if ( v6 )
    CloseThreadpoolIo(v6);
LABEL_25:
  if ( (xmmword_1800AD720 & 8) != 0 )
    WPP_SF_d(1027, 71, WPP_14086b36644f38024399eb8d606249d9_Traceguids, Error);
  return Error;
}

```

## disassembly

```asm
0x18008dd88  mov     [rsp+arg_10], rbx
0x18008dd8d  mov     [rsp+arg_18], rbp
0x18008dd92  push    rsi
0x18008dd93  push    rdi
0x18008dd94  push    r13
0x18008dd96  push    r14
0x18008dd98  push    r15
0x18008dd9a  sub     rsp, 60h
0x18008dd9e  mov     rax, cs:__security_cookie
0x18008dda5  xor     rax, rsp
0x18008dda8  mov     [rsp+88h+var_30], rax
0x18008ddad  xorps   xmm0, xmm0
0x18008ddb0  mov     dword ptr [rsp+88h+optval], 0
0x18008ddb8  xorps   xmm1, xmm1
0x18008ddbb  mov     r14, rdx
0x18008ddbe  movups  xmmword ptr [rsp+88h+IoStatusBlock], xmm0
0x18008ddc3  mov     rdi, rcx
0x18008ddc6  movups  [rsp+88h+FileInformation], xmm1
0x18008ddcb  test    byte ptr cs:xmmword_1800AD720, 8
0x18008ddd2  jz      short loc_18008DDF2
0x18008ddd4  mov     edx, 45h ; 'E'
0x18008ddd9  mov     qword ptr [rsp+88h+optlen], r14
0x18008ddde  mov     ecx, 403h
0x18008dde3  lea     r8, WPP_14086b36644f38024399eb8d606249d9_Traceguids
0x18008ddea  mov     r9, rdi
0x18008dded  call    WPP_SF_qq
0x18008ddf2  test    r14, r14
0x18008ddf5  jnz     short loc_18008DE00
0x18008ddf7  lea     ebx, [r14+57h]
0x18008ddfb  jmp     loc_18008DFA2
0x18008de00  lea     rsi, [rdi+18h]
0x18008de04  or      r13, 0FFFFFFFFFFFFFFFFh
0x18008de08  mov     rcx, rsi; lpCriticalSection
0x18008de0b  mov     [r14], r13
0x18008de0e  call    cs:__imp_EnterCriticalSection
0x18008de15  nop     dword ptr [rax+rax+00h]
0x18008de1a  cmp     dword ptr [rdi+0E0h], 4
0x18008de21  mov     ebx, 139Fh
0x18008de26  jz      short loc_18008DE3C
0x18008de28  mov     rcx, rsi; lpCriticalSection
0x18008de2b  call    cs:__imp_LeaveCriticalSection
0x18008de32  nop     dword ptr [rax+rax+00h]
0x18008de37  jmp     loc_18008DFA2
0x18008de3c  cmp     dword ptr [rdi+0E8h], 0
0x18008de43  jnz     short loc_18008DE4B
0x18008de45  mov     [rdi+0E8h], ebx
0x18008de4b  mov     rcx, rsi; lpCriticalSection
0x18008de4e  mov     dword ptr [rdi+0E0h], 6
0x18008de58  call    cs:__imp_LeaveCriticalSection
0x18008de5f  nop     dword ptr [rax+rax+00h]
0x18008de64  lea     r15, [rdi+2B8h]
0x18008de6b  mov     rcx, r15; SRWLock
0x18008de6e  call    cs:__imp_AcquireSRWLockExclusive
0x18008de75  nop     dword ptr [rax+rax+00h]
0x18008de7a  mov     rsi, [rdi+2C0h]
0x18008de81  cmp     rsi, r13
0x18008de84  jnz     short loc_18008DE98
0x18008de86  mov     ebx, [rdi+0E8h]
0x18008de8c  mov     eax, 54Fh
0x18008de91  test    ebx, ebx
0x18008de93  cmovz   ebx, eax
0x18008de96  jmp     short loc_18008DEA1
0x18008de98  cmp     byte ptr [rdi+3D4h], 0
0x18008de9f  jz      short loc_18008DEBA
0x18008dea1  xor     ebp, ebp
0x18008dea3  mov     rcx, r15; SRWLock
0x18008dea6  mov     rsi, r13
0x18008dea9  call    cs:__imp_ReleaseSRWLockExclusive
0x18008deb0  nop     dword ptr [rax+rax+00h]
0x18008deb5  jmp     loc_18008DF72
0x18008deba  mov     rbp, [rdi+2C8h]
0x18008dec1  mov     rcx, r15; SRWLock
0x18008dec4  mov     qword ptr [rdi+2C8h], 0
0x18008decf  mov     [rdi+2C0h], r13
0x18008ded6  call    cs:__imp_ReleaseSRWLockExclusive
0x18008dedd  nop     dword ptr [rax+rax+00h]
0x18008dee2  mov     edx, 6; level
0x18008dee7  mov     dword ptr [rsp+88h+optval], 0
0x18008deef  lea     r9, [rsp+88h+optval]; optval
0x18008def4  mov     [rsp+88h+optlen], 4; optlen
0x18008defc  mov     rcx, rsi; s
0x18008deff  lea     r8d, [rdx-5]; optname
0x18008df03  call    cs:__imp_setsockopt
0x18008df0a  nop     dword ptr [rax+rax+00h]
0x18008df0f  cmp     eax, r13d
0x18008df12  jnz     short loc_18008DF1F
0x18008df14  xor     ecx, ecx
0x18008df16  call    WaWSAGetLastError
0x18008df1b  mov     ebx, eax
0x18008df1d  jmp     short loc_18008DF72
0x18008df1f  mov     r9d, 10h; Length
0x18008df25  mov     [rsp+88h+optlen], 3Dh ; '='; FileInformationClass
0x18008df2d  lea     r8, [rsp+88h+FileInformation]; FileInformation
0x18008df32  mov     rcx, rsi; FileHandle
0x18008df35  lea     rdx, [rsp+88h+IoStatusBlock]; IoStatusBlock
0x18008df3a  call    cs:__imp_NtSetInformationFile
0x18008df41  nop     dword ptr [rax+rax+00h]
0x18008df46  test    eax, eax
0x18008df48  jnz     short loc_18008DF72
0x18008df4a  xor     ebx, ebx
0x18008df4c  test    byte ptr cs:xmmword_1800AD720, 8
0x18008df53  jz      short loc_18008DF6C
0x18008df55  mov     r9d, esi
0x18008df58  lea     edx, [rax+46h]
0x18008df5b  mov     ecx, 403h
0x18008df60  lea     r8, WPP_14086b36644f38024399eb8d606249d9_Traceguids
0x18008df67  call    WPP_SF_d
0x18008df6c  mov     [r14], rsi
0x18008df6f  mov     rsi, r13
0x18008df72  mov     rcx, rdi
0x18008df75  call    WapTcpIndicateCleanupEvent
0x18008df7a  cmp     rsi, r13
0x18008df7d  jz      short loc_18008DF8E
0x18008df7f  mov     rcx, rsi; s
0x18008df82  call    cs:__imp_closesocket
0x18008df89  nop     dword ptr [rax+rax+00h]
0x18008df8e  test    rbp, rbp
0x18008df91  jz      short loc_18008DFA2
0x18008df93  mov     rcx, rbp; pio
0x18008df96  call    cs:__imp_CloseThreadpoolIo
0x18008df9d  nop     dword ptr [rax+rax+00h]
0x18008dfa2  test    byte ptr cs:xmmword_1800AD720, 8
0x18008dfa9  jz      short loc_18008DFC4
0x18008dfab  mov     edx, 47h ; 'G'
0x18008dfb0  lea     r8, WPP_14086b36644f38024399eb8d606249d9_Traceguids
0x18008dfb7  mov     ecx, 403h
0x18008dfbc  mov     r9d, ebx
0x18008dfbf  call    WPP_SF_d
0x18008dfc4  mov     eax, ebx
0x18008dfc6  mov     rcx, [rsp+88h+var_30]
0x18008dfcb  xor     rcx, rsp; StackCookie
0x18008dfce  call    __security_check_cookie
0x18008dfd3  lea     r11, [rsp+88h+var_28]
0x18008dfd8  mov     rbx, [r11+40h]
0x18008dfdc  mov     rbp, [r11+48h]
0x18008dfe0  mov     rsp, r11
0x18008dfe3  pop     r15
0x18008dfe5  pop     r14
0x18008dfe7  pop     r13
0x18008dfe9  pop     rdi
0x18008dfea  pop     rsi
0x18008dfeb  retn
```
