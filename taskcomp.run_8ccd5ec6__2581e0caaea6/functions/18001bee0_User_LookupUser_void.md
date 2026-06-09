# User::LookupUser(void *)

- ea: `0x18001bee0`
- end: `0x18001bf77`
- name: `?LookupUser@User@@CA?AV1@PEAX@Z`
- size: `151`
- prototype: `static struct User __high(void *)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180019f10`
- `0x18001a394`
- `0x18001acc4`

## callees

- `0x1800181ec`
- `0x18001bee0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bf07`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bf07`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bf5c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bf5c`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001bf38`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001bf38`

## pseudocode

```c
_QWORD *__fastcall User::LookupUser(_QWORD *a1, void *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  _QWORD **v5; // r14
  _QWORD *v6; // rbx
  void *v7; // rcx

  *a1 = 0;
  if ( a2 )
  {
    v4 = User::s_cs;
    EnterCriticalSection(User::s_cs);
    v5 = (_QWORD **)User::s_userTable;
    v6 = *(_QWORD **)User::s_userTable;
    if ( *(_QWORD *)User::s_userTable != *((_QWORD *)User::s_userTable + 1) )
    {
      while ( v6 != v5[1] )
      {
        v7 = *(void **)(*v6 + 32LL);
        if ( v7 && EqualSid(v7, a2) )
        {
          wmi::AutoRef<User::UserEntry>::operator=(a1, *v6);
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
0x18001bee0  push    rbx
0x18001bee2  push    rbp
0x18001bee3  push    rsi
0x18001bee4  push    rdi
0x18001bee5  push    r14
0x18001bee7  sub     rsp, 20h
0x18001beeb  mov     qword ptr [rcx], 0
0x18001bef2  mov     rbp, rdx
0x18001bef5  mov     rsi, rcx
0x18001bef8  test    rdx, rdx
0x18001befb  jz      short loc_18001BF68
0x18001befd  mov     rdi, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18001bf04  mov     rcx, rdi; lpCriticalSection
0x18001bf07  call    cs:__imp_EnterCriticalSection
0x18001bf0e  nop     dword ptr [rax+rax+00h]
0x18001bf13  mov     r14, cs:?s_userTable@User@@0PEAV?$vector@PEAUUserEntry@User@@V?$allocator@PEAUUserEntry@User@@@std@@@std@@EA; std::vector<User::UserEntry *> * User::s_userTable
0x18001bf1a  mov     rbx, [r14]
0x18001bf1d  cmp     rbx, [r14+8]
0x18001bf21  jz      short loc_18001BF59
0x18001bf23  cmp     rbx, [r14+8]
0x18001bf27  jz      short loc_18001BF59
0x18001bf29  mov     rax, [rbx]
0x18001bf2c  mov     rcx, [rax+20h]; pSid1
0x18001bf30  test    rcx, rcx
0x18001bf33  jz      short loc_18001BF48
0x18001bf35  mov     rdx, rbp; pSid2
0x18001bf38  call    cs:__imp_EqualSid
0x18001bf3f  nop     dword ptr [rax+rax+00h]
0x18001bf44  test    eax, eax
0x18001bf46  jnz     short loc_18001BF4E
0x18001bf48  add     rbx, 8
0x18001bf4c  jmp     short loc_18001BF23
0x18001bf4e  mov     rdx, [rbx]
0x18001bf51  mov     rcx, rsi
0x18001bf54  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x18001bf59  mov     rcx, rdi; lpCriticalSection
0x18001bf5c  call    cs:__imp_LeaveCriticalSection
0x18001bf63  nop     dword ptr [rax+rax+00h]
0x18001bf68  mov     rax, rsi
0x18001bf6b  add     rsp, 20h
0x18001bf6f  pop     r14
0x18001bf71  pop     rdi
0x18001bf72  pop     rsi
0x18001bf73  pop     rbp
0x18001bf74  pop     rbx
0x18001bf75  retn
```
