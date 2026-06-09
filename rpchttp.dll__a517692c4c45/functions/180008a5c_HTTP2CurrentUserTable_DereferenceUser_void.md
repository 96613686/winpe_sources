# HTTP2CurrentUserTable::DereferenceUser(void *)

- ea: `0x180008a5c`
- end: `0x180008b2a`
- name: `?DereferenceUser@HTTP2CurrentUserTable@@QEAAHPEAX@Z`
- size: `206`
- prototype: `int(HTTP2CurrentUserTable *__hidden this, void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180002fa8`
- `0x18000311c`

## callees

- `0x1800033d8`
- `0x180008a5c`
- `0x18000ce68`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180008b0c`
- `ntdll!RtlLeaveCriticalSection` at `0x180008b0c`
- `ntdll!RtlEnterCriticalSection` at `0x180008a9e`
- `ntdll!RtlEnterCriticalSection` at `0x180008a9e`
- `ADVAPI32!EqualSid` at `0x180008ac8`
- `ADVAPI32!EqualSid` at `0x180008ac8`

## pseudocode

```c
__int64 __fastcall HTTP2CurrentUserTable::DereferenceUser(HTTP2CurrentUserTable *this, unsigned __int8 *a2)
{
  struct HTTP2CurrentUserTable *v2; // rsi
  __int64 v4; // rbx
  unsigned int v5; // eax
  unsigned int v6; // r12d
  __int64 v7; // rdi
  __int64 v8; // rbp
  volatile signed __int32 *v9; // r14
  __int64 v10; // r15
  unsigned int v11; // edx
  __int64 v12; // rax

  v2 = g_HTTP2CurrentUserTable;
  v4 = *(_QWORD *)g_HTTP2CurrentUserTable;
  v5 = HTTP2CurrentUserTable::HashSid(this, a2);
  if ( !*(_QWORD *)v2 )
    return 0;
  v6 = 0;
  v7 = 88LL * (v5 % *((_DWORD *)v2 + 2));
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(v7 + v4 + 48));
  v8 = 0;
  while ( (unsigned int)v8 < *(_DWORD *)(v7 + v4 + 8) )
  {
    v9 = *(volatile signed __int32 **)(*(_QWORD *)(v7 + v4) + 8 * v8);
    if ( v9 )
    {
      v10 = (unsigned int)v8;
      v8 = (unsigned int)(v8 + 1);
      if ( EqualSid(*(PSID *)v9, a2) )
      {
        if ( _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
        {
          if ( (unsigned int)v10 < *(_DWORD *)(v7 + v4 + 8) )
          {
            v12 = *(_QWORD *)(v7 + v4);
            --*(_DWORD *)(v7 + v4 + 12);
            *(_QWORD *)(v12 + 8 * v10) = 0;
          }
          HTTP2CurrentUserEntry::`scalar deleting destructor'((HTTP2CurrentUserEntry *)v9, v11);
          _InterlockedDecrement((volatile signed __int32 *)v2 + 3);
          v6 = 1;
        }
        break;
      }
    }
    else
    {
      v8 = (unsigned int)(v8 + 1);
    }
  }
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(v7 + v4 + 48));
  return v6;
}

```

## disassembly

```asm
0x180008a5c  push    rbx
0x180008a5e  push    rbp
0x180008a5f  push    rsi
0x180008a60  push    rdi
0x180008a61  push    r12
0x180008a63  push    r13
0x180008a65  push    r14
0x180008a67  push    r15
0x180008a69  sub     rsp, 28h
0x180008a6d  mov     rsi, cs:?g_HTTP2CurrentUserTable@@3PEAVHTTP2CurrentUserTable@@EA; HTTP2CurrentUserTable * g_HTTP2CurrentUserTable
0x180008a74  mov     r13, rdx
0x180008a77  mov     rbx, [rsi]
0x180008a7a  call    ?HashSid@HTTP2CurrentUserTable@@IEAAKPEAX@Z; HTTP2CurrentUserTable::HashSid(void *)
0x180008a7f  cmp     qword ptr [rsi], 0
0x180008a83  jz      loc_180008B17
0x180008a89  xor     edx, edx
0x180008a8b  xor     r12d, r12d
0x180008a8e  div     dword ptr [rsi+8]
0x180008a91  mov     ecx, edx
0x180008a93  imul    rdi, rcx, 58h ; 'X'
0x180008a97  lea     rcx, [rbx+30h]
0x180008a9b  add     rcx, rdi; CriticalSection
0x180008a9e  call    cs:__imp_RtlEnterCriticalSection
0x180008aa4  xor     ebp, ebp
0x180008aa6  cmp     ebp, [rdi+rbx+8]
0x180008aaa  jnb     short loc_180008B05
0x180008aac  mov     rax, [rdi+rbx]
0x180008ab0  mov     r14, [rax+rbp*8]
0x180008ab4  test    r14, r14
0x180008ab7  jnz     short loc_180008ABD
0x180008ab9  inc     ebp
0x180008abb  jmp     short loc_180008AA6
0x180008abd  mov     rcx, [r14]; pSid1
0x180008ac0  mov     rdx, r13; pSid2
0x180008ac3  mov     r15d, ebp
0x180008ac6  inc     ebp
0x180008ac8  call    cs:__imp_EqualSid
0x180008ace  test    eax, eax
0x180008ad0  jz      short loc_180008AA6
0x180008ad2  or      eax, 0FFFFFFFFh
0x180008ad5  lock xadd [r14+8], eax
0x180008adb  cmp     eax, 1
0x180008ade  jnz     short loc_180008B05
0x180008ae0  cmp     r15d, [rdi+rbx+8]
0x180008ae5  jnb     short loc_180008AF3
0x180008ae7  mov     rax, [rdi+rbx]
0x180008aeb  dec     dword ptr [rdi+rbx+0Ch]
0x180008aef  mov     [rax+r15*8], r12
0x180008af3  mov     rcx, r14; this
0x180008af6  call    ??_GHTTP2CurrentUserEntry@@QEAAPEAXI@Z; HTTP2CurrentUserEntry::`scalar deleting destructor'(uint)
0x180008afb  lock dec dword ptr [rsi+0Ch]
0x180008aff  mov     r12d, 1
0x180008b05  lea     rcx, [rbx+30h]
0x180008b09  add     rcx, rdi; CriticalSection
0x180008b0c  call    cs:__imp_RtlLeaveCriticalSection
0x180008b12  mov     eax, r12d
0x180008b15  jmp     short loc_180008B19
0x180008b17  xor     eax, eax
0x180008b19  add     rsp, 28h
0x180008b1d  pop     r15
0x180008b1f  pop     r14
0x180008b21  pop     r13
0x180008b23  pop     r12
0x180008b25  pop     rdi
0x180008b26  pop     rsi
0x180008b27  pop     rbp
0x180008b28  pop     rbx
0x180008b29  retn
```
