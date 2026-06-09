# CReceiveDataManager::HrInitialize(void)

- ea: `0x180024a20`
- end: `0x180024aeb`
- name: `?HrInitialize@CReceiveDataManager@@QEAAJXZ`
- size: `203`
- prototype: `__int64 __fastcall(CReceiveDataManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a768`

## callees

- `0x18000554c`
- `0x180024a20`
- `0x1800255a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180024a3a`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180024a5e`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180024a3a`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180024a5e`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180024a97`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180024a97`

## pseudocode

```c
__int64 __fastcall CReceiveDataManager::HrInitialize(CReceiveDataManager *this)
{
  signed int Win32Error; // ebx
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
0x180024a20  mov     [rsp+arg_0], rbx
0x180024a25  push    rdi
0x180024a26  sub     rsp, 30h
0x180024a2a  mov     rdi, rcx
0x180024a2d  xor     ebx, ebx
0x180024a2f  xor     r9d, r9d; lpName
0x180024a32  xor     r8d, r8d; bInitialState
0x180024a35  xor     ecx, ecx; lpEventAttributes
0x180024a37  lea     edx, [rbx+1]; bManualReset
0x180024a3a  call    cs:__imp_CreateEventA
0x180024a40  mov     [rdi+38h], rax
0x180024a44  test    rax, rax
0x180024a47  jnz     short loc_180024A54
0x180024a49  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180024a4e  mov     ebx, eax
0x180024a50  test    eax, eax
0x180024a52  js      short loc_180024AAD
0x180024a54  xor     r9d, r9d; lpName
0x180024a57  xor     r8d, r8d; bInitialState
0x180024a5a  xor     edx, edx; bManualReset
0x180024a5c  xor     ecx, ecx; lpEventAttributes
0x180024a5e  call    cs:__imp_CreateEventA
0x180024a64  mov     [rdi+40h], rax
0x180024a68  test    rax, rax
0x180024a6b  jnz     short loc_180024A78
0x180024a6d  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180024a72  mov     ebx, eax
0x180024a74  test    eax, eax
0x180024a76  js      short loc_180024AAD
0x180024a78  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x180024a81  lea     r8, ?ThreadFunc@CReceiveDataManager@@CAKPEAX@Z; lpStartAddress
0x180024a88  xor     r9d, r9d; lpParameter
0x180024a8b  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x180024a93  xor     edx, edx; dwStackSize
0x180024a95  xor     ecx, ecx; lpThreadAttributes
0x180024a97  call    cs:__imp_CreateThread
0x180024a9d  mov     [rdi+48h], rax
0x180024aa1  test    rax, rax
0x180024aa4  jnz     short loc_180024AAD
0x180024aa6  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180024aab  mov     ebx, eax
0x180024aad  mov     rcx, cs:WPP_GLOBAL_Control
0x180024ab4  lea     rax, WPP_GLOBAL_Control
0x180024abb  cmp     rcx, rax
0x180024abe  jz      short loc_180024ADE
0x180024ac0  test    byte ptr [rcx+1Ch], 8
0x180024ac4  jz      short loc_180024ADE
0x180024ac6  mov     rcx, [rcx+10h]
0x180024aca  lea     r8, WPP_bc52afbc171436f214070148f5e15db4_Traceguids
0x180024ad1  mov     edx, 0Ch
0x180024ad6  mov     r9d, ebx
0x180024ad9  call    WPP_SF_d
0x180024ade  mov     eax, ebx
0x180024ae0  mov     rbx, [rsp+38h+arg_0]
0x180024ae5  add     rsp, 30h
0x180024ae9  pop     rdi
0x180024aea  retn
```
