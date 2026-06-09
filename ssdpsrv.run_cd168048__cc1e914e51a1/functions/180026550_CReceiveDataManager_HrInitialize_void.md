# CReceiveDataManager::HrInitialize(void)

- ea: `0x180026550`
- end: `0x18002662e`
- name: `?HrInitialize@CReceiveDataManager@@QEAAJXZ`
- size: `222`
- prototype: `__int64 __fastcall(CReceiveDataManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c078`

## callees

- `0x18000683c`
- `0x180026550`
- `0x1800271fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18002656a`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180026594`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18002656a`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180026594`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800265d3`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800265d3`

## pseudocode

```c
__int64 __fastcall CReceiveDataManager::HrInitialize(CReceiveDataManager *this)
{
  int Win32Error; // ebx
  HANDLE EventA; // rax
  HANDLE v4; // rax
  HANDLE Thread; // rax

  Win32Error = 0;
  EventA = CreateEventA(0, 1, 0, 0);
  *((_QWORD *)this + 7) = EventA;
  if ( EventA || (Win32Error = HrFromLastWin32Error(), Win32Error >= 0) )
  {
    v4 = CreateEventA(0, 0, 0, 0);
    *((_QWORD *)this + 8) = v4;
    if ( v4 || (Win32Error = HrFromLastWin32Error(), Win32Error >= 0) )
    {
      Thread = CreateThread(0, 0, CReceiveDataManager::ThreadFunc, 0, 0, 0);
      *((_QWORD *)this + 9) = Thread;
      if ( !Thread )
        Win32Error = HrFromLastWin32Error();
    }
  }
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      WPP_bc52afbc171436f214070148f5e15db4_Traceguids,
      (unsigned int)Win32Error);
  return (unsigned int)Win32Error;
}

```

## disassembly

```asm
0x180026550  mov     [rsp+arg_0], rbx
0x180026555  push    rdi
0x180026556  sub     rsp, 30h
0x18002655a  mov     rdi, rcx
0x18002655d  xor     ebx, ebx
0x18002655f  xor     r9d, r9d; lpName
0x180026562  xor     r8d, r8d; bInitialState
0x180026565  xor     ecx, ecx; lpEventAttributes
0x180026567  lea     edx, [rbx+1]; bManualReset
0x18002656a  call    cs:__imp_CreateEventA
0x180026571  nop     dword ptr [rax+rax+00h]
0x180026576  mov     [rdi+38h], rax
0x18002657a  test    rax, rax
0x18002657d  jnz     short loc_18002658A
0x18002657f  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180026584  mov     ebx, eax
0x180026586  test    eax, eax
0x180026588  js      short loc_1800265EF
0x18002658a  xor     r9d, r9d; lpName
0x18002658d  xor     r8d, r8d; bInitialState
0x180026590  xor     edx, edx; bManualReset
0x180026592  xor     ecx, ecx; lpEventAttributes
0x180026594  call    cs:__imp_CreateEventA
0x18002659b  nop     dword ptr [rax+rax+00h]
0x1800265a0  mov     [rdi+40h], rax
0x1800265a4  test    rax, rax
0x1800265a7  jnz     short loc_1800265B4
0x1800265a9  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x1800265ae  mov     ebx, eax
0x1800265b0  test    eax, eax
0x1800265b2  js      short loc_1800265EF
0x1800265b4  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x1800265bd  lea     r8, ?ThreadFunc@CReceiveDataManager@@CAKPEAX@Z; lpStartAddress
0x1800265c4  xor     r9d, r9d; lpParameter
0x1800265c7  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x1800265cf  xor     edx, edx; dwStackSize
0x1800265d1  xor     ecx, ecx; lpThreadAttributes
0x1800265d3  call    cs:__imp_CreateThread
0x1800265da  nop     dword ptr [rax+rax+00h]
0x1800265df  mov     [rdi+48h], rax
0x1800265e3  test    rax, rax
0x1800265e6  jnz     short loc_1800265EF
0x1800265e8  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x1800265ed  mov     ebx, eax
0x1800265ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800265f6  lea     rax, WPP_GLOBAL_Control
0x1800265fd  cmp     rcx, rax
0x180026600  jz      short loc_180026620
0x180026602  test    byte ptr [rcx+1Ch], 8
0x180026606  jz      short loc_180026620
0x180026608  mov     rcx, [rcx+10h]
0x18002660c  lea     r8, WPP_bc52afbc171436f214070148f5e15db4_Traceguids
0x180026613  mov     edx, 0Ch
0x180026618  mov     r9d, ebx
0x18002661b  call    WPP_SF_d
0x180026620  mov     eax, ebx
0x180026622  mov     rbx, [rsp+38h+arg_0]
0x180026627  add     rsp, 30h
0x18002662b  pop     rdi
0x18002662c  retn
```
