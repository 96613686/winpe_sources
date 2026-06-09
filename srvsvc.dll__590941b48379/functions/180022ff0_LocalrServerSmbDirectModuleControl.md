# LocalrServerSmbDirectModuleControl

- ea: `0x180022ff0`
- end: `0x180023115`
- name: `LocalrServerSmbDirectModuleControl`
- size: `293`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation`

## callees

- `0x18000ae90`
- `0x18000b300`
- `0x18001deb0`
- `0x18001e80c`
- `0x180022ff0`
- `0x180028928`
- `0x180028b08`
- `0x180028bac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180023076`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180023076`

## pseudocode

```c
__int64 __fastcall LocalrServerSmbDirectModuleControl(__int64 a1, int a2)
{
  int v3; // ebx
  HANDLE CurrentThread; // rax
  int Status; // ebx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-88h] BYREF
  _BYTE InputBuffer[80]; // [rsp+50h] [rbp-78h] BYREF
  int v9; // [rsp+A0h] [rbp-28h]

  IoStatusBlock = 0;
  memset_0(InputBuffer, 0, 0x60u);
  if ( a2 )
  {
    v3 = a2 - 1;
    if ( v3 )
    {
      if ( v3 != 1 )
        return 87;
      v9 = 3;
    }
    else
    {
      v9 = 2;
    }
  }
  else
  {
    v9 = 1;
  }
  if ( (unsigned int)SsImpersonateClient("LocalrServerSmbDirectModuleControl", 59) )
    return 5;
  CurrentThread = GetCurrentThread();
  if ( !(unsigned int)SsIsPrivilegeHeld(CurrentThread) )
  {
    SsRevertToSelf("LocalrServerSmbDirectModuleControl", 59);
    return 5;
  }
  Status = SsServerFsControlFile(qword_18005CDB8, &IoStatusBlock, 0x1460A3u, InputBuffer, 0x60u, 0, 0);
  SsRevertToSelf("LocalrServerSmbDirectModuleControl", 68);
  if ( Status < 0 )
    return NetpNtStatusToApiStatus(Status);
  Status = IoStatusBlock.Status;
  if ( IoStatusBlock.Status < 0 )
    return NetpNtStatusToApiStatus(Status);
  else
    return 0;
}

```

## disassembly

```asm
0x180022ff0  push    rbx
0x180022ff2  sub     rsp, 0C0h
0x180022ff9  mov     rax, cs:__security_cookie
0x180023000  xor     rax, rsp
0x180023003  mov     [rsp+0C8h+var_18], rax
0x18002300b  mov     ebx, edx
0x18002300d  lea     rcx, [rsp+0C8h+InputBuffer]; void *
0x180023012  xor     edx, edx; Val
0x180023014  xorps   xmm0, xmm0
0x180023017  movups  xmmword ptr [rsp+0C8h+IoStatusBlock], xmm0
0x18002301c  lea     r8d, [rdx+60h]; Size
0x180023020  call    memset_0
0x180023025  test    ebx, ebx
0x180023027  jz      short loc_180023054
0x180023029  sub     ebx, 1
0x18002302c  jz      short loc_180023047
0x18002302e  cmp     ebx, 1
0x180023031  jz      short loc_18002303A
0x180023033  mov     eax, 57h ; 'W'
0x180023038  jmp     short loc_18002309B
0x18002303a  mov     [rsp+0C8h+var_28], 3
0x180023045  jmp     short loc_18002305F
0x180023047  mov     [rsp+0C8h+var_28], 2
0x180023052  jmp     short loc_18002305F
0x180023054  mov     [rsp+0C8h+var_28], 1
0x18002305f  mov     ebx, 3Bh ; ';'
0x180023064  lea     rcx, aLocalrserversm; "LocalrServerSmbDirectModuleControl"
0x18002306b  mov     edx, ebx
0x18002306d  call    SsImpersonateClient
0x180023072  test    eax, eax
0x180023074  jnz     short loc_180023096
0x180023076  call    cs:__imp_GetCurrentThread
0x18002307c  mov     rcx, rax
0x18002307f  call    SsIsPrivilegeHeld
0x180023084  test    eax, eax
0x180023086  jnz     short loc_1800230B4
0x180023088  mov     edx, ebx
0x18002308a  lea     rcx, aLocalrserversm; "LocalrServerSmbDirectModuleControl"
0x180023091  call    SsRevertToSelf
0x180023096  mov     eax, 5
0x18002309b  mov     rcx, [rsp+0C8h+var_18]
0x1800230a3  xor     rcx, rsp; StackCookie
0x1800230a6  call    __security_check_cookie
0x1800230ab  add     rsp, 0C0h
0x1800230b2  pop     rbx
0x1800230b3  retn
0x1800230b4  mov     rcx, cs:qword_18005CDB8; FileHandle
0x1800230bb  lea     r9, [rsp+0C8h+InputBuffer]; InputBuffer
0x1800230c0  mov     [rsp+0C8h+var_98], 0; ULONG
0x1800230c8  lea     rdx, [rsp+0C8h+IoStatusBlock]; IoStatusBlock
0x1800230cd  mov     [rsp+0C8h+var_A0], 0; PVOID
0x1800230d6  mov     r8d, 1460A3h; FsControlCode
0x1800230dc  mov     [rsp+0C8h+var_A8], 60h ; '`'; ULONG
0x1800230e4  call    SsServerFsControlFile
0x1800230e9  mov     edx, 44h ; 'D'
0x1800230ee  lea     rcx, aLocalrserversm; "LocalrServerSmbDirectModuleControl"
0x1800230f5  mov     ebx, eax
0x1800230f7  call    SsRevertToSelf
0x1800230fc  test    ebx, ebx
0x1800230fe  js      short loc_18002310C
0x180023100  mov     ebx, dword ptr [rsp+0C8h+IoStatusBlock]
0x180023104  test    ebx, ebx
0x180023106  js      short loc_18002310C
0x180023108  xor     eax, eax
0x18002310a  jmp     short loc_18002309B
0x18002310c  mov     ecx, ebx; Status
0x18002310e  call    NetpNtStatusToApiStatus
0x180023113  jmp     short loc_18002309B
```
