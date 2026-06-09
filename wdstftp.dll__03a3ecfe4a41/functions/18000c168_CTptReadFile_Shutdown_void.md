# CTptReadFile::Shutdown(void)

- ea: `0x18000c168`
- end: `0x18000c493`
- name: `?Shutdown@CTptReadFile@@QEAAKXZ`
- size: `811`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `7`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000615c`
- `0x180008b1c`
- `0x180008d80`
- `0x180009008`
- `0x1800092e0`
- `0x180009d20`
- `0x18000c5fc`

## callees

- `0x18000a960`
- `0x18000be08`
- `0x18000c168`
- `0x18000d84c`
- `0x18003c514`
- `0x18003cf50`
- `0x18003d028`
- `0x180060e70`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000c216`
- `KERNEL32!EnterCriticalSection` at `0x18000c216`
- `KERNEL32!LeaveCriticalSection` at `0x18000c46a`
- `KERNEL32!LeaveCriticalSection` at `0x18000c46a`
- `KERNEL32!CloseHandle` at `0x18000c22f`
- `KERNEL32!CloseHandle` at `0x18000c22f`
- `KERNEL32!WaitForSingleObjectEx` at `0x18000c1d1`
- `KERNEL32!WaitForSingleObjectEx` at `0x18000c1d1`
- `WDSSRV!WdsPacketFree` at `0x18000c39d`
- `WDSSRV!WdsPacketFree` at `0x18000c414`
- `WDSSRV!WdsPacketFree` at `0x18000c39d`
- `WDSSRV!WdsPacketFree` at `0x18000c414`

## string_xrefs

- `0x18000c28f`: `base\eco\wds\transport\lib\tptreadfile.cpp`
- `0x18000c2bd`: `CTptReadFile::Shutdown: Deleting CTptReadFile Cache of size = %I64u.`
- `0x18000c367`: `m_bIOCompleted`
- `0x18000c3de`: `m_bIOCompleted`
- `0x18000c378`: `base\eco\wds\transport\lib\tptreadfile.h`
- `0x18000c3ef`: `base\eco\wds\transport\lib\tptreadfile.h`

## pseudocode

```c
__int64 __fastcall CTptReadFile::Shutdown(LPCRITICAL_SECTION lpCriticalSection)
{
  DWORD v2; // eax
  HANDLE OwningThread; // rcx
  void *v4; // rcx
  unsigned __int64 DebugInfo_high; // rax
  unsigned __int128 v6; // rax
  unsigned __int64 v7; // kr00_8
  __int64 v8; // rbx
  int v9; // esi
  const char *v10; // rdx
  const char *v11; // r8
  __int64 v12; // r9
  _QWORD *v13; // rbx
  _QWORD *v14; // rsi
  _QWORD *v15; // rax
  _QWORD *v16; // rcx
  __int64 v17; // rax
  _QWORD *v18; // rax
  _QWORD *v19; // rcx
  __int64 v20; // r8
  unsigned int i; // ebx
  __int64 v22; // rsi
  __int64 v23; // r8
  void *SpinCount; // rcx

  if ( HIDWORD(lpCriticalSection[3].DebugInfo) != 2
    && (Microsoft_Windows_Deployment_Services_DiagnosticsEnableBits & 1) != 0 )
  {
    McTemplateU0zxq(
      (_DWORD)lpCriticalSection,
      (unsigned int)TptReadFileBufferDeleted,
      *(_QWORD *)&lpCriticalSection[1].LockCount,
      lpCriticalSection[1].LockSemaphore,
      HIDWORD(lpCriticalSection[3].DebugInfo));
  }
  while ( _InterlockedExchangeAdd(&lpCriticalSection[4].LockCount, 0) )
  {
    v2 = WaitForSingleObjectEx(lpCriticalSection[4].OwningThread, 0x1F4u, 1);
    if ( v2 && v2 != 258 && v2 != 192 )
    {
      if ( g_ErrLibTraceFunctionEx )
        g_ErrLibTraceFunctionEx(0x80000u, L"CChildCount::WaitForChildren failed; %u", v2);
      break;
    }
  }
  EnterCriticalSection(lpCriticalSection);
  OwningThread = lpCriticalSection[1].OwningThread;
  if ( OwningThread != (HANDLE)-1LL )
  {
    CloseHandle(OwningThread);
    lpCriticalSection[1].OwningThread = (HANDLE)-1LL;
  }
  CWIMFile::Shutdown((CWIMFile *)&lpCriticalSection[1].SpinCount);
  v4 = *(void **)&lpCriticalSection[1].LockCount;
  if ( v4 )
  {
    operator delete(v4);
    *(_QWORD *)&lpCriticalSection[1].LockCount = 0;
  }
  if ( HIDWORD(lpCriticalSection[3].DebugInfo) == 1 )
    DebugInfo_high = HIDWORD(lpCriticalSection[4].DebugInfo);
  else
    DebugInfo_high = HIDWORD(lpCriticalSection[3].LockSemaphore);
  v7 = DebugInfo_high;
  v6 = LODWORD(lpCriticalSection[2].LockSemaphore) * (unsigned __int128)DebugInfo_high;
  v8 = v6;
  if ( is_mul_ok(LODWORD(lpCriticalSection[2].LockSemaphore), v7) )
  {
    v9 = 0;
  }
  else
  {
    v8 = -1;
    v9 = -2147024362;
  }
  ElValidateHrLite(v9, *((const char **)&v6 + 1), "base\\eco\\wds\\transport\\lib\\tptreadfile.cpp", 0xBCu);
  if ( (v9 >= 0 || (int)ElValidateHr(v9, v10, v11, v12) >= 0) && g_ErrLibTraceFunctionEx )
    g_ErrLibTraceFunctionEx(0x10000u, L"CTptReadFile::Shutdown: Deleting CTptReadFile Cache of size = %I64u.", v8);
  v13 = *(_QWORD **)&lpCriticalSection[3].LockCount;
  while ( v13 )
  {
    v14 = v13;
    v15 = *(_QWORD **)&lpCriticalSection[3].LockCount;
    v16 = lpCriticalSection[3].OwningThread;
    if ( v15 == v16 )
    {
      lpCriticalSection[3].OwningThread = 0;
      *(_QWORD *)&lpCriticalSection[3].LockCount = 0;
LABEL_31:
      v13 = 0;
      goto LABEL_33;
    }
    if ( v13 == v15 )
    {
      v17 = v15[12];
      *(_QWORD *)&lpCriticalSection[3].LockCount = v17;
      *(_QWORD *)(v17 + 104) = 0;
      v13 = *(_QWORD **)&lpCriticalSection[3].LockCount;
      goto LABEL_33;
    }
    if ( v13 == v16 )
    {
      v18 = (_QWORD *)v16[13];
      lpCriticalSection[3].OwningThread = v18;
      v18[12] = 0;
      goto LABEL_31;
    }
    v19 = v13 + 12;
    v13 = (_QWORD *)v13[12];
    *(_QWORD *)(v14[13] + 96LL) = v13;
    *(_QWORD *)(*v19 + 104LL) = v14[13];
LABEL_33:
    --HIDWORD(lpCriticalSection[3].LockSemaphore);
    if ( !*((_DWORD *)v14 + 18) )
      WdsAssert("base\\eco\\wds\\transport\\lib\\tptreadfile.h", 0xD1u, "m_bIOCompleted", v12, 0);
    v20 = v14[7];
    if ( v20 )
      WdsPacketFree(*(_QWORD *)&::lpCriticalSection[4].LockCount, 0, v20, v12);
    operator delete(v14);
  }
  for ( i = 0; i < LODWORD(lpCriticalSection[4].DebugInfo); ++i )
  {
    v22 = *(_QWORD *)(lpCriticalSection[3].SpinCount + 8LL * i);
    if ( v22 )
    {
      if ( !*(_DWORD *)(v22 + 72) )
        WdsAssert("base\\eco\\wds\\transport\\lib\\tptreadfile.h", 0xD1u, "m_bIOCompleted", v12, 0);
      v23 = *(_QWORD *)(v22 + 56);
      if ( v23 )
        WdsPacketFree(*(_QWORD *)&::lpCriticalSection[4].LockCount, 0, v23, v12);
      operator delete((void *)v22);
      *(_QWORD *)(lpCriticalSection[3].SpinCount + 8LL * i) = 0;
    }
  }
  SpinCount = (void *)lpCriticalSection[3].SpinCount;
  lpCriticalSection[4].DebugInfo = 0;
  if ( SpinCount )
  {
    operator delete(SpinCount);
    lpCriticalSection[3].SpinCount = 0;
  }
  HIDWORD(lpCriticalSection[3].DebugInfo) = 2;
  LODWORD(lpCriticalSection[3].DebugInfo) = 0;
  LeaveCriticalSection(lpCriticalSection);
  return 0;
}

```

## disassembly

```asm
0x18000c168  mov     rax, rsp
0x18000c16b  mov     [rax+8], rbx
0x18000c16f  mov     [rax+10h], rbp
0x18000c173  mov     [rax+18h], rsi
0x18000c177  mov     [rax+20h], rdi
0x18000c17b  push    r14
0x18000c17d  sub     rsp, 30h
0x18000c181  mov     eax, [rcx+7Ch]
0x18000c184  mov     rdi, rcx
0x18000c187  cmp     eax, 2
0x18000c18a  jz      short loc_18000C1AD
0x18000c18c  test    cs:Microsoft_Windows_Deployment_Services_DiagnosticsEnableBits, 1
0x18000c193  jz      short loc_18000C1AD
0x18000c195  mov     r9, [rcx+40h]
0x18000c199  lea     rdx, TptReadFileBufferDeleted
0x18000c1a0  mov     r8, [rcx+30h]
0x18000c1a4  mov     [rsp+38h+var_18], eax
0x18000c1a8  call    McTemplateU0zxq
0x18000c1ad  xor     r14d, r14d
0x18000c1b0  mov     eax, r14d
0x18000c1b3  lock xadd [rdi+0A8h], eax
0x18000c1bb  test    eax, eax
0x18000c1bd  jz      short loc_18000C213
0x18000c1bf  mov     rcx, [rdi+0B0h]; hHandle
0x18000c1c6  mov     edx, 1F4h; dwMilliseconds
0x18000c1cb  mov     r8d, 1; bAlertable
0x18000c1d1  call    cs:__imp_WaitForSingleObjectEx
0x18000c1d8  nop     dword ptr [rax+rax+00h]
0x18000c1dd  test    eax, eax
0x18000c1df  jz      short loc_18000C1B0
0x18000c1e1  cmp     eax, 102h
0x18000c1e6  jz      short loc_18000C1B0
0x18000c1e8  cmp     eax, 0C0h
0x18000c1ed  jz      short loc_18000C1B0
0x18000c1ef  mov     r9, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000c1f6  test    r9, r9
0x18000c1f9  jz      short loc_18000C213
0x18000c1fb  mov     r8d, eax
0x18000c1fe  lea     rdx, aCchildcountWai; "CChildCount::WaitForChildren failed; %u"
0x18000c205  mov     rax, r9
0x18000c208  mov     ecx, 80000h
0x18000c20d  call    cs:__guard_dispatch_icall_fptr
0x18000c213  mov     rcx, rdi; lpCriticalSection
0x18000c216  call    cs:__imp_EnterCriticalSection
0x18000c21d  nop     dword ptr [rax+rax+00h]
0x18000c222  mov     rcx, [rdi+38h]; hObject
0x18000c226  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000c22a  cmp     rcx, rsi
0x18000c22d  jz      short loc_18000C23F
0x18000c22f  call    cs:__imp_CloseHandle
0x18000c236  nop     dword ptr [rax+rax+00h]
0x18000c23b  mov     [rdi+38h], rsi
0x18000c23f  lea     rcx, [rdi+48h]; this
0x18000c243  call    ?Shutdown@CWIMFile@@QEAAKXZ; CWIMFile::Shutdown(void)
0x18000c248  mov     rcx, [rdi+30h]; void *
0x18000c24c  test    rcx, rcx
0x18000c24f  jz      short loc_18000C25A
0x18000c251  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c256  mov     [rdi+30h], r14
0x18000c25a  cmp     dword ptr [rdi+7Ch], 1
0x18000c25e  jnz     short loc_18000C268
0x18000c260  mov     eax, [rdi+0A4h]
0x18000c266  jmp     short loc_18000C26E
0x18000c268  mov     eax, [rdi+94h]
0x18000c26e  mov     ecx, [rdi+68h]
0x18000c271  mul     rcx
0x18000c274  mov     rbx, rax
0x18000c277  test    rdx, rdx
0x18000c27a  jnz     short loc_18000C281
0x18000c27c  mov     esi, r14d
0x18000c27f  jmp     short loc_18000C289
0x18000c281  mov     rbx, rsi
0x18000c284  mov     esi, 80070216h
0x18000c289  mov     r9d, 0BCh; unsigned int
0x18000c28f  lea     r8, aBaseEcoWdsTran_9; "base\\eco\\wds\\transport\\lib\\tptread"...
0x18000c296  mov     ecx, esi; int
0x18000c298  call    ?ElValidateHrLite@@YAJJPEBD0K@Z; ElValidateHrLite(long,char const *,char const *,ulong)
0x18000c29d  test    esi, esi
0x18000c29f  jns     short loc_18000C2AE
0x18000c2a1  mov     ecx, esi; int
0x18000c2a3  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000c2a8  mov     esi, eax
0x18000c2aa  test    eax, eax
0x18000c2ac  js      short loc_18000C2CF
0x18000c2ae  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000c2b5  test    rax, rax
0x18000c2b8  jz      short loc_18000C2CF
0x18000c2ba  mov     r8, rbx
0x18000c2bd  lea     rdx, aCtptreadfileSh; "CTptReadFile::Shutdown: Deleting CTptRe"...
0x18000c2c4  mov     ecx, 10000h
0x18000c2c9  call    cs:__guard_dispatch_icall_fptr
0x18000c2cf  mov     rbx, [rdi+80h]
0x18000c2d6  jmp     loc_18000C3B1
0x18000c2db  mov     rsi, rbx
0x18000c2de  test    rbx, rbx
0x18000c2e1  jz      short loc_18000C35C
0x18000c2e3  mov     rax, [rdi+80h]
0x18000c2ea  mov     rcx, [rdi+88h]
0x18000c2f1  cmp     rax, rcx
0x18000c2f4  jnz     short loc_18000C306
0x18000c2f6  mov     [rdi+88h], r14
0x18000c2fd  mov     [rdi+80h], r14
0x18000c304  jmp     short loc_18000C337
0x18000c306  cmp     rbx, rax
0x18000c309  jnz     short loc_18000C323
0x18000c30b  mov     rax, [rax+60h]
0x18000c30f  mov     [rdi+80h], rax
0x18000c316  mov     [rax+68h], r14
0x18000c31a  mov     rbx, [rdi+80h]
0x18000c321  jmp     short loc_18000C356
0x18000c323  cmp     rbx, rcx
0x18000c326  jnz     short loc_18000C33C
0x18000c328  mov     rax, [rcx+68h]
0x18000c32c  mov     [rdi+88h], rax
0x18000c333  mov     [rax+60h], r14
0x18000c337  mov     rbx, r14
0x18000c33a  jmp     short loc_18000C356
0x18000c33c  mov     rax, [rsi+68h]
0x18000c340  lea     rcx, [rbx+60h]
0x18000c344  mov     rbx, [rcx]
0x18000c347  mov     [rax+60h], rbx
0x18000c34b  mov     rcx, [rcx]
0x18000c34e  mov     rax, [rsi+68h]
0x18000c352  mov     [rcx+68h], rax
0x18000c356  dec     dword ptr [rdi+94h]
0x18000c35c  test    rsi, rsi
0x18000c35f  jz      short loc_18000C3B1
0x18000c361  cmp     [rsi+48h], r14d
0x18000c365  jnz     short loc_18000C384
0x18000c367  lea     r8, aMBiocompleted; "m_bIOCompleted"
0x18000c36e  mov     [rsp+38h+var_18], r14d; int
0x18000c373  mov     edx, 0D1h; unsigned int
0x18000c378  lea     rcx, aBaseEcoWdsTran; "base\\eco\\wds\\transport\\lib\\tptread"...
0x18000c37f  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18000c384  mov     r8, [rsi+38h]
0x18000c388  test    r8, r8
0x18000c38b  jz      short loc_18000C3A9
0x18000c38d  mov     rcx, cs:lpCriticalSection
0x18000c394  xor     edx, edx
0x18000c396  mov     rcx, [rcx+0A8h]
0x18000c39d  call    cs:__imp_WdsPacketFree
0x18000c3a4  nop     dword ptr [rax+rax+00h]
0x18000c3a9  mov     rcx, rsi; void *
0x18000c3ac  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c3b1  test    rbx, rbx
0x18000c3b4  jnz     loc_18000C2DB
0x18000c3ba  mov     ebx, r14d
0x18000c3bd  cmp     [rdi+0A0h], r14d
0x18000c3c4  jbe     short loc_18000C43D
0x18000c3c6  mov     rax, [rdi+98h]
0x18000c3cd  mov     ebp, ebx
0x18000c3cf  mov     rsi, [rax+rbp*8]
0x18000c3d3  test    rsi, rsi
0x18000c3d6  jz      short loc_18000C433
0x18000c3d8  cmp     [rsi+48h], r14d
0x18000c3dc  jnz     short loc_18000C3FB
0x18000c3de  lea     r8, aMBiocompleted; "m_bIOCompleted"
0x18000c3e5  mov     [rsp+38h+var_18], r14d; int
0x18000c3ea  mov     edx, 0D1h; unsigned int
0x18000c3ef  lea     rcx, aBaseEcoWdsTran; "base\\eco\\wds\\transport\\lib\\tptread"...
0x18000c3f6  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18000c3fb  mov     r8, [rsi+38h]
0x18000c3ff  test    r8, r8
0x18000c402  jz      short loc_18000C420
0x18000c404  mov     rcx, cs:lpCriticalSection
0x18000c40b  xor     edx, edx
0x18000c40d  mov     rcx, [rcx+0A8h]
0x18000c414  call    cs:__imp_WdsPacketFree
0x18000c41b  nop     dword ptr [rax+rax+00h]
0x18000c420  mov     rcx, rsi; void *
0x18000c423  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c428  mov     rax, [rdi+98h]
0x18000c42f  mov     [rax+rbp*8], r14
0x18000c433  inc     ebx
0x18000c435  cmp     ebx, [rdi+0A0h]
0x18000c43b  jb      short loc_18000C3C6
0x18000c43d  mov     rcx, [rdi+98h]; void *
0x18000c444  mov     [rdi+0A0h], r14
0x18000c44b  test    rcx, rcx
0x18000c44e  jz      short loc_18000C45C
0x18000c450  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c455  mov     [rdi+98h], r14
0x18000c45c  mov     rcx, rdi; lpCriticalSection
0x18000c45f  mov     dword ptr [rdi+7Ch], 2
0x18000c466  mov     [rdi+78h], r14d
0x18000c46a  call    cs:__imp_LeaveCriticalSection
0x18000c471  nop     dword ptr [rax+rax+00h]
0x18000c476  mov     rbx, [rsp+38h+arg_0]
0x18000c47b  xor     eax, eax
0x18000c47d  mov     rbp, [rsp+38h+arg_8]
0x18000c482  mov     rsi, [rsp+38h+arg_10]
0x18000c487  mov     rdi, [rsp+38h+arg_18]
0x18000c48c  add     rsp, 30h
0x18000c490  pop     r14
0x18000c492  retn
```
