# WctCalibrateWFSOSyscallNumber

- ea: `0x180007680`
- end: `0x18000783f`
- name: `WctCalibrateWFSOSyscallNumber`
- size: `447`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180061330`

## callees

- `0x180004c64`
- `0x180007680`
- `0x180008004`
- `0x180009464`
- `0x180020680`
- `0x180053300`
- `0x18006180c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180007752`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180007752`
- `ntdll!NtQueryInformationThread` at `0x1800077a3`
- `ntdll!NtQueryInformationThread` at `0x1800077a3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800077da`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800077da`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000770d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000770d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800077c8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800077c8`

## pseudocode

```c
__int64 WctCalibrateWFSOSyscallNumber()
{
  HANDLE v0; // rbx
  unsigned int v1; // edi
  HANDLE EventW; // rsi
  __int64 v3; // rcx
  HANDLE v4; // rax
  wchar_t *v5; // rcx
  __int64 v6; // rcx
  DWORD ThreadId; // [rsp+30h] [rbp-49h] BYREF
  ULONG ReturnLength; // [rsp+34h] [rbp-45h] BYREF
  HANDLE ThreadHandle; // [rsp+38h] [rbp-41h] BYREF
  _OWORD Parameter[3]; // [rsp+40h] [rbp-39h] BYREF
  __int64 v12; // [rsp+70h] [rbp-9h]
  __int128 ThreadInformation; // [rsp+78h] [rbp-1h] BYREF
  __int64 v14; // [rsp+88h] [rbp+Fh]

  ReturnLength = 0;
  v0 = 0;
  v14 = 0;
  ThreadHandle = 0;
  v1 = -1;
  ThreadInformation = 0;
  ThreadId = 0;
  memset(Parameter, 0, sizeof(Parameter));
  v12 = 0;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids);
  EventW = CreateEventW(0, 1, 0, 0);
  tlx::file_handle_traits::operator()(v3, 0);
  if ( (unsigned __int64)EventW + 1 > 1 )
  {
    *(_QWORD *)&Parameter[0] = EventW;
    v4 = CreateThread(0, 0, WctSyscallCalibratorThreadProc, Parameter, 0, &ThreadId);
    tlx::unique_any<tlx::file_handle_traits>::reset(&ThreadHandle, v4);
    v0 = ThreadHandle;
    if ( (unsigned __int64)ThreadHandle + 1 > 1 )
    {
      if ( (unsigned int)WctWaitUntilThreadIsBlocked(ThreadId)
        && NtQueryInformationThread(v0, ThreadLastSystemCall, &ThreadInformation, 0x18u, &ReturnLength) >= 0
        && ReturnLength == 24
        && WORD4(ThreadInformation) )
      {
        v1 = WORD4(ThreadInformation);
      }
      SetEvent(*(HANDLE *)&Parameter[0]);
      WaitForSingleObject(v0, 0xFFFFFFFF);
    }
  }
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids, v1);
  tlx::file_handle_traits::operator()(v5, EventW);
  tlx::file_handle_traits::operator()(v6, v0);
  return v1;
}

```

## disassembly

```asm
0x180007680  push    rbp
0x180007682  push    rbx
0x180007683  push    rsi
0x180007684  push    rdi
0x180007685  push    r14
0x180007687  push    r15
0x180007689  lea     rbp, [rsp-2Fh]
0x18000768e  sub     rsp, 0A8h
0x180007695  mov     rax, cs:__security_cookie
0x18000769c  xor     rax, rsp
0x18000769f  mov     [rbp+57h+var_40], rax
0x1800076a3  xor     r14d, r14d
0x1800076a6  xorps   xmm0, xmm0
0x1800076a9  xor     eax, eax
0x1800076ab  mov     [rbp+57h+ReturnLength], r14d
0x1800076af  mov     ebx, r14d
0x1800076b2  mov     [rbp+57h+var_48], rax
0x1800076b6  mov     [rbp+57h+ThreadHandle], rbx
0x1800076ba  or      edi, 0FFFFFFFFh
0x1800076bd  movups  [rbp+57h+ThreadInformation], xmm0
0x1800076c1  mov     [rbp+57h+ThreadId], r14d
0x1800076c5  movups  [rbp+57h+Parameter], xmm0
0x1800076c9  mov     [rbp+57h+var_60], rax
0x1800076cd  movups  [rbp+57h+var_80], xmm0
0x1800076d1  movups  [rbp+57h+var_70], xmm0
0x1800076d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800076dc  lea     r15, WPP_GLOBAL_Control
0x1800076e3  cmp     rcx, r15
0x1800076e6  jz      short loc_180007701
0x1800076e8  test    byte ptr [rcx+1Ch], 4
0x1800076ec  jz      short loc_180007701
0x1800076ee  mov     rcx, [rcx+10h]
0x1800076f2  lea     edx, [rax+10h]
0x1800076f5  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x1800076fc  call    WPP_SF_
0x180007701  xor     r9d, r9d; lpName
0x180007704  xor     r8d, r8d; bInitialState
0x180007707  xor     ecx, ecx; lpEventAttributes
0x180007709  lea     edx, [r9+1]; bManualReset
0x18000770d  call    cs:__imp_CreateEventW
0x180007714  nop     dword ptr [rax+rax+00h]
0x180007719  xor     edx, edx
0x18000771b  mov     rsi, rax
0x18000771e  call    ??Rfile_handle_traits@tlx@@QEBAXPEAX@Z; tlx::file_handle_traits::operator()(void *)
0x180007723  lea     rax, [rsi+1]
0x180007727  cmp     rax, 1
0x18000772b  jbe     loc_1800077E6
0x180007731  lea     rax, [rbp+57h+ThreadId]
0x180007735  mov     qword ptr [rbp+57h+Parameter], rsi
0x180007739  mov     [rsp+0D0h+lpThreadId], rax; lpThreadId
0x18000773e  lea     r9, [rbp+57h+Parameter]; lpParameter
0x180007742  lea     r8, WctSyscallCalibratorThreadProc; lpStartAddress
0x180007749  mov     [rsp+0D0h+dwCreationFlags], r14d; dwCreationFlags
0x18000774e  xor     edx, edx; dwStackSize
0x180007750  xor     ecx, ecx; lpThreadAttributes
0x180007752  call    cs:__imp_CreateThread
0x180007759  nop     dword ptr [rax+rax+00h]
0x18000775e  mov     rdx, rax
0x180007761  lea     rcx, [rbp+57h+ThreadHandle]
0x180007765  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18000776a  mov     rbx, [rbp+57h+ThreadHandle]
0x18000776e  lea     rax, [rbx+1]
0x180007772  cmp     rax, 1
0x180007776  jbe     short loc_1800077E6
0x180007778  mov     ecx, [rbp+57h+ThreadId]; unsigned int
0x18000777b  mov     edx, 6
0x180007780  call    WctWaitUntilThreadIsBlocked
0x180007785  test    eax, eax
0x180007787  jz      short loc_1800077C4
0x180007789  mov     r9d, 18h; ThreadInformationLength
0x18000778f  lea     rax, [rbp+57h+ReturnLength]
0x180007793  lea     r8, [rbp+57h+ThreadInformation]; ThreadInformation
0x180007797  mov     qword ptr [rsp+0D0h+dwCreationFlags], rax; ReturnLength
0x18000779c  mov     rcx, rbx; ThreadHandle
0x18000779f  lea     edx, [r9-3]; ThreadInformationClass
0x1800077a3  call    cs:__imp_NtQueryInformationThread
0x1800077aa  nop     dword ptr [rax+rax+00h]
0x1800077af  test    eax, eax
0x1800077b1  js      short loc_1800077C4
0x1800077b3  cmp     [rbp+57h+ReturnLength], 18h
0x1800077b7  jnz     short loc_1800077C4
0x1800077b9  movzx   eax, word ptr [rbp+57h+ThreadInformation+8]
0x1800077bd  test    ax, ax
0x1800077c0  jz      short loc_1800077C4
0x1800077c2  mov     edi, eax
0x1800077c4  mov     rcx, qword ptr [rbp+57h+Parameter]; hEvent
0x1800077c8  call    cs:__imp_SetEvent
0x1800077cf  nop     dword ptr [rax+rax+00h]
0x1800077d4  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800077d7  mov     rcx, rbx; hHandle
0x1800077da  call    cs:__imp_WaitForSingleObject
0x1800077e1  nop     dword ptr [rax+rax+00h]
0x1800077e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800077ed  cmp     rcx, r15
0x1800077f0  jz      short loc_180007810
0x1800077f2  test    byte ptr [rcx+1Ch], 4
0x1800077f6  jz      short loc_180007810
0x1800077f8  mov     rcx, [rcx+10h]
0x1800077fc  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x180007803  mov     edx, 11h
0x180007808  mov     r9d, edi
0x18000780b  call    WPP_SF_d
0x180007810  mov     rdx, rsi
0x180007813  call    ??Rfile_handle_traits@tlx@@QEBAXPEAX@Z; tlx::file_handle_traits::operator()(void *)
0x180007818  mov     rdx, rbx
0x18000781b  call    ??Rfile_handle_traits@tlx@@QEBAXPEAX@Z; tlx::file_handle_traits::operator()(void *)
0x180007820  mov     eax, edi
0x180007822  mov     rcx, [rbp+57h+var_40]
0x180007826  xor     rcx, rsp; StackCookie
0x180007829  call    __security_check_cookie
0x18000782e  add     rsp, 0A8h
0x180007835  pop     r15
0x180007837  pop     r14
0x180007839  pop     rdi
0x18000783a  pop     rsi
0x18000783b  pop     rbx
0x18000783c  pop     rbp
0x18000783d  retn
```
