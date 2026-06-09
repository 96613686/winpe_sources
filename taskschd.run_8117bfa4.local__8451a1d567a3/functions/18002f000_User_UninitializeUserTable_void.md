# User::UninitializeUserTable(void)

- ea: `0x18002f000`
- end: `0x18002f0de`
- name: `?UninitializeUserTable@User@@SAXXZ`
- size: `222`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180026a10`

## callees

- `0x18002f000`
- `0x18003e2b8`

## import_xrefs

- `msvcrt!free` at `0x18002f03d`
- `msvcrt!free` at `0x18002f063`
- `msvcrt!free` at `0x18002f08e`
- `msvcrt!free` at `0x18002f0c2`
- `msvcrt!free` at `0x18002f03d`
- `msvcrt!free` at `0x18002f063`
- `msvcrt!free` at `0x18002f08e`
- `msvcrt!free` at `0x18002f0c2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002f07f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002f07f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void User::UninitializeUserTable(void)
{
  void *v0; // rbx
  _QWORD *v1; // rbx
  LPCRITICAL_SECTION v2; // rbx

  v0 = User::s_userCache;
  if ( User::s_userCache )
  {
    `eh vector destructor iterator'(User::s_userCache, 8u, 8u, std::unique_ptr<User>::~unique_ptr<User>);
    free(v0);
    User::s_userCache = 0;
  }
  v1 = User::s_userTable;
  if ( User::s_userTable )
  {
    if ( *(_QWORD *)User::s_userTable )
    {
      free(*(void **)User::s_userTable);
      *v1 = 0;
      v1[1] = 0;
      v1[2] = 0;
    }
    free(v1);
    User::s_userTable = 0;
  }
  v2 = User::s_cs;
  if ( User::s_cs )
  {
    DeleteCriticalSection(User::s_cs);
    free(v2);
    User::s_cs = 0;
  }
}

```

## disassembly

```asm
0x18002f000  push    rbx
0x18002f002  sub     rsp, 20h
0x18002f006  mov     rbx, cs:?s_userCache@User@@0PEAVUserCache@1@EA; User::UserCache * User::s_userCache
0x18002f00d  test    rbx, rbx
0x18002f010  jnz     loc_18002F0A7
0x18002f016  mov     rbx, cs:?s_userTable@User@@0PEAV?$vector@PEAUUserEntry@User@@V?$allocator@PEAUUserEntry@User@@@std@@@std@@EA; std::vector<User::UserEntry *> * User::s_userTable
0x18002f01d  test    rbx, rbx
0x18002f020  jnz     short loc_18002F035
0x18002f022  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18002f029  test    rbx, rbx
0x18002f02c  jnz     short loc_18002F07C
0x18002f02e  add     rsp, 20h
0x18002f032  pop     rbx
0x18002f033  retn
0x18002f035  mov     rcx, [rbx]; Block
0x18002f038  test    rcx, rcx
0x18002f03b  jz      short loc_18002F060
0x18002f03d  call    cs:__imp_free
0x18002f044  nop     dword ptr [rax+rax+00h]
0x18002f049  mov     qword ptr [rbx], 0
0x18002f050  mov     qword ptr [rbx+8], 0
0x18002f058  mov     qword ptr [rbx+10h], 0
0x18002f060  mov     rcx, rbx; Block
0x18002f063  call    cs:__imp_free
0x18002f06a  nop     dword ptr [rax+rax+00h]
0x18002f06f  mov     cs:?s_userTable@User@@0PEAV?$vector@PEAUUserEntry@User@@V?$allocator@PEAUUserEntry@User@@@std@@@std@@EA, 0; std::vector<User::UserEntry *> * User::s_userTable
0x18002f07a  jmp     short loc_18002F022
0x18002f07c  mov     rcx, rbx; lpCriticalSection
0x18002f07f  call    cs:__imp_DeleteCriticalSection
0x18002f086  nop     dword ptr [rax+rax+00h]
0x18002f08b  mov     rcx, rbx; Block
0x18002f08e  call    cs:__imp_free
0x18002f095  nop     dword ptr [rax+rax+00h]
0x18002f09a  mov     cs:?s_cs@User@@0PEAVCritSec@wmi@@EA, 0; wmi::CritSec * User::s_cs
0x18002f0a5  jmp     short loc_18002F02E
0x18002f0a7  lea     r9, ??1?$unique_ptr@VUser@@U?$default_delete@VUser@@@std@@@std@@QEAA@XZ; void (*)(void *)
0x18002f0ae  mov     edx, 8; unsigned __int64
0x18002f0b3  mov     r8d, edx; unsigned __int64
0x18002f0b6  mov     rcx, rbx; void *
0x18002f0b9  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18002f0be  nop
0x18002f0bf  mov     rcx, rbx; Block
0x18002f0c2  call    cs:__imp_free
0x18002f0c9  nop     dword ptr [rax+rax+00h]
0x18002f0ce  mov     cs:?s_userCache@User@@0PEAVUserCache@1@EA, 0; User::UserCache * User::s_userCache
0x18002f0d9  jmp     loc_18002F016
```
