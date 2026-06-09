# User::UninitializeUserTable(void)

- ea: `0x18002cc50`
- end: `0x18002cd0b`
- name: `?UninitializeUserTable@User@@SAXXZ`
- size: `187`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180026730`

## callees

- `0x18002cc50`
- `0x18003af48`

## import_xrefs

- `msvcrt!free` at `0x18002cc88`
- `msvcrt!free` at `0x18002cca8`
- `msvcrt!free` at `0x18002ccc7`
- `msvcrt!free` at `0x18002ccf5`
- `msvcrt!free` at `0x18002cc88`
- `msvcrt!free` at `0x18002cca8`
- `msvcrt!free` at `0x18002ccc7`
- `msvcrt!free` at `0x18002ccf5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002ccbe`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002ccbe`

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
0x18002cc50  push    rbx
0x18002cc52  sub     rsp, 20h
0x18002cc56  mov     rbx, cs:?s_userCache@User@@0PEAVUserCache@1@EA; User::UserCache * User::s_userCache
0x18002cc5d  test    rbx, rbx
0x18002cc60  jnz     short loc_18002CCDA
0x18002cc62  mov     rbx, cs:?s_userTable@User@@0PEAV?$vector@PEAUUserEntry@User@@V?$allocator@PEAUUserEntry@User@@@std@@@std@@EA; std::vector<User::UserEntry *> * User::s_userTable
0x18002cc69  test    rbx, rbx
0x18002cc6c  jnz     short loc_18002CC80
0x18002cc6e  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18002cc75  test    rbx, rbx
0x18002cc78  jnz     short loc_18002CCBB
0x18002cc7a  add     rsp, 20h
0x18002cc7e  pop     rbx
0x18002cc7f  retn
0x18002cc80  mov     rcx, [rbx]; Block
0x18002cc83  test    rcx, rcx
0x18002cc86  jz      short loc_18002CCA5
0x18002cc88  call    cs:__imp_free
0x18002cc8e  mov     qword ptr [rbx], 0
0x18002cc95  mov     qword ptr [rbx+8], 0
0x18002cc9d  mov     qword ptr [rbx+10h], 0
0x18002cca5  mov     rcx, rbx; Block
0x18002cca8  call    cs:__imp_free
0x18002ccae  mov     cs:?s_userTable@User@@0PEAV?$vector@PEAUUserEntry@User@@V?$allocator@PEAUUserEntry@User@@@std@@@std@@EA, 0; std::vector<User::UserEntry *> * User::s_userTable
0x18002ccb9  jmp     short loc_18002CC6E
0x18002ccbb  mov     rcx, rbx; lpCriticalSection
0x18002ccbe  call    cs:__imp_DeleteCriticalSection
0x18002ccc4  mov     rcx, rbx; Block
0x18002ccc7  call    cs:__imp_free
0x18002cccd  mov     cs:?s_cs@User@@0PEAVCritSec@wmi@@EA, 0; wmi::CritSec * User::s_cs
0x18002ccd8  jmp     short loc_18002CC7A
0x18002ccda  lea     r9, ??1?$unique_ptr@VUser@@U?$default_delete@VUser@@@std@@@std@@QEAA@XZ; void (*)(void *)
0x18002cce1  mov     edx, 8; unsigned __int64
0x18002cce6  mov     r8d, edx; unsigned __int64
0x18002cce9  mov     rcx, rbx; void *
0x18002ccec  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18002ccf1  nop
0x18002ccf2  mov     rcx, rbx; Block
0x18002ccf5  call    cs:__imp_free
0x18002ccfb  mov     cs:?s_userCache@User@@0PEAVUserCache@1@EA, 0; User::UserCache * User::s_userCache
0x18002cd06  jmp     loc_18002CC62
```
