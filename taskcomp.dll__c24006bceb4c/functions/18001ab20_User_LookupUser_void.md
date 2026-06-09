# User::LookupUser(void *)

- ea: `0x18001ab20`
- end: `0x18001aba4`
- name: `?LookupUser@User@@CA?AV1@PEAX@Z`
- size: `132`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180018d00`
- `0x180019168`
- `0x180019a10`

## callees

- `0x180017210`
- `0x18001ab20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ab47`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ab47`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ab90`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ab90`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001ab72`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001ab72`

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
0x18001ab20  push    rbx
0x18001ab22  push    rbp
0x18001ab23  push    rsi
0x18001ab24  push    rdi
0x18001ab25  push    r14
0x18001ab27  sub     rsp, 20h
0x18001ab2b  mov     qword ptr [rcx], 0
0x18001ab32  mov     rbp, rdx
0x18001ab35  mov     rsi, rcx
0x18001ab38  test    rdx, rdx
0x18001ab3b  jz      short loc_18001AB96
0x18001ab3d  mov     rdi, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18001ab44  mov     rcx, rdi; lpCriticalSection
0x18001ab47  call    cs:__imp_EnterCriticalSection
0x18001ab4d  mov     r14, cs:?s_userTable@User@@0PEAV?$vector@PEAUUserEntry@User@@V?$allocator@PEAUUserEntry@User@@@std@@@std@@EA; std::vector<User::UserEntry *> * User::s_userTable
0x18001ab54  mov     rbx, [r14]
0x18001ab57  cmp     rbx, [r14+8]
0x18001ab5b  jz      short loc_18001AB8D
0x18001ab5d  cmp     rbx, [r14+8]
0x18001ab61  jz      short loc_18001AB8D
0x18001ab63  mov     rax, [rbx]
0x18001ab66  mov     rcx, [rax+20h]; pSid1
0x18001ab6a  test    rcx, rcx
0x18001ab6d  jz      short loc_18001AB7C
0x18001ab6f  mov     rdx, rbp; pSid2
0x18001ab72  call    cs:__imp_EqualSid
0x18001ab78  test    eax, eax
0x18001ab7a  jnz     short loc_18001AB82
0x18001ab7c  add     rbx, 8
0x18001ab80  jmp     short loc_18001AB5D
0x18001ab82  mov     rdx, [rbx]
0x18001ab85  mov     rcx, rsi
0x18001ab88  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x18001ab8d  mov     rcx, rdi; lpCriticalSection
0x18001ab90  call    cs:__imp_LeaveCriticalSection
0x18001ab96  mov     rax, rsi
0x18001ab99  add     rsp, 20h
0x18001ab9d  pop     r14
0x18001ab9f  pop     rdi
0x18001aba0  pop     rsi
0x18001aba1  pop     rbp
0x18001aba2  pop     rbx
0x18001aba3  retn
```
