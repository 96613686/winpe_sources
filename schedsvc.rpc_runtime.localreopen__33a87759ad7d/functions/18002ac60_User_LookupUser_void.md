# User::LookupUser(void *)

- ea: `0x18002ac60`
- end: `0x18002ad32`
- name: `?LookupUser@User@@CA?AV1@PEAX@Z`
- size: `210`
- prototype: `static struct User __high(void *)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180029508`
- `0x180031ef0`
- `0x18004cfb0`
- `0x1800515c0`

## callees

- `0x18002ac60`
- `0x18002ad40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002acf3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ad07`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002acf3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ad07`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ac9a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ace7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ac9a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ace7`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002accb`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002accb`

## pseudocode

```c
User::UserEntry **__fastcall User::LookupUser(User::UserEntry **a1, void *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  _QWORD *v5; // rsi
  User::UserEntry **v6; // rbx
  void *v7; // rcx
  User::UserEntry *v8; // rsi
  struct _RTL_CRITICAL_SECTION *v9; // rbx

  *a1 = 0;
  if ( a2 )
  {
    v4 = User::s_cs;
    EnterCriticalSection(User::s_cs);
    v5 = User::s_userTable;
    v6 = *(User::UserEntry ***)User::s_userTable;
    if ( *(_QWORD *)User::s_userTable != *((_QWORD *)User::s_userTable + 1) )
    {
      while ( v6 != (User::UserEntry **)v5[1] )
      {
        v7 = (void *)*((_QWORD *)*v6 + 4);
        if ( v7 && EqualSid(v7, a2) )
        {
          v8 = *v6;
          if ( *v6 )
          {
            v9 = User::s_cs;
            EnterCriticalSection(User::s_cs);
            ++*((_DWORD *)v8 + 11);
            LeaveCriticalSection(v9);
          }
          if ( *a1 )
            User::UserEntry::Release(*a1);
          *a1 = v8;
          break;
        }
        ++v6;
      }
    }
    LeaveCriticalSection(v4);
  }
  return a1;
}

```

## disassembly

```asm
0x18002ac60  mov     [rsp+arg_18], rbp
0x18002ac65  push    r14
0x18002ac67  sub     rsp, 20h
0x18002ac6b  mov     qword ptr [rcx], 0
0x18002ac72  mov     rbp, rdx
0x18002ac75  mov     r14, rcx
0x18002ac78  test    rdx, rdx
0x18002ac7b  jz      loc_18002AD1C
0x18002ac81  mov     [rsp+28h+arg_0], rbx
0x18002ac86  mov     [rsp+28h+arg_8], rsi
0x18002ac8b  mov     [rsp+28h+arg_10], rdi
0x18002ac90  mov     rdi, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18002ac97  mov     rcx, rdi; lpCriticalSection
0x18002ac9a  call    cs:__imp_EnterCriticalSection
0x18002aca0  mov     rsi, cs:?s_userTable@User@@0PEAV?$vector@PEAUUserEntry@User@@V?$allocator@PEAUUserEntry@User@@@std@@@std@@EA; std::vector<User::UserEntry *> * User::s_userTable
0x18002aca7  mov     rbx, [rsi]
0x18002acaa  cmp     rbx, [rsi+8]
0x18002acae  jz      short loc_18002AD04
0x18002acb0  cmp     rbx, [rsi+8]
0x18002acb4  jz      short loc_18002AD04
0x18002acb6  mov     rcx, [rbx]
0x18002acb9  mov     rcx, [rcx+20h]; pSid1
0x18002acbd  test    rcx, rcx
0x18002acc0  jnz     short loc_18002ACC8
0x18002acc2  add     rbx, 8
0x18002acc6  jmp     short loc_18002ACB0
0x18002acc8  mov     rdx, rbp; pSid2
0x18002accb  call    cs:__imp_EqualSid
0x18002acd1  test    eax, eax
0x18002acd3  jz      short loc_18002ACC2
0x18002acd5  mov     rsi, [rbx]
0x18002acd8  test    rsi, rsi
0x18002acdb  jz      short loc_18002ACF9
0x18002acdd  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18002ace4  mov     rcx, rbx; lpCriticalSection
0x18002ace7  call    cs:__imp_EnterCriticalSection
0x18002aced  inc     dword ptr [rsi+2Ch]
0x18002acf0  mov     rcx, rbx; lpCriticalSection
0x18002acf3  call    cs:__imp_LeaveCriticalSection
0x18002acf9  mov     rcx, [r14]; this
0x18002acfc  test    rcx, rcx
0x18002acff  jnz     short loc_18002AD2B
0x18002ad01  mov     [r14], rsi
0x18002ad04  mov     rcx, rdi; lpCriticalSection
0x18002ad07  call    cs:__imp_LeaveCriticalSection
0x18002ad0d  mov     rdi, [rsp+28h+arg_10]
0x18002ad12  mov     rsi, [rsp+28h+arg_8]
0x18002ad17  mov     rbx, [rsp+28h+arg_0]
0x18002ad1c  mov     rbp, [rsp+28h+arg_18]
0x18002ad21  mov     rax, r14
0x18002ad24  add     rsp, 20h
0x18002ad28  pop     r14
0x18002ad2a  retn
0x18002ad2b  call    ?Release@UserEntry@User@@QEAAKXZ; User::UserEntry::Release(void)
0x18002ad30  jmp     short loc_18002AD01
```
