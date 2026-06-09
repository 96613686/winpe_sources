# WimpFSFSetBackgroundPriorities

- ea: `0x14002aa38`
- end: `0x14002ab39`
- name: `WimpFSFSetBackgroundPriorities`
- size: `257`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140028ef4`

## callees

- `0x140011560`
- `0x14002aa38`
- `0x14002ab40`

## import_xrefs

- `ntoskrnl!KeQueryPriorityThread` at `0x14002aad3`
- `ntoskrnl!KeQueryPriorityThread` at `0x14002aad3`
- `ntoskrnl!ZwQueryInformationThread` at `0x14002aa7f`
- `ntoskrnl!ZwQueryInformationThread` at `0x14002aab5`
- `ntoskrnl!ZwQueryInformationThread` at `0x14002aa7f`
- `ntoskrnl!ZwQueryInformationThread` at `0x14002aab5`

## pseudocode

```c
__int64 __fastcall WimpFSFSetBackgroundPriorities(__int64 a1)
{
  NTSTATUS InformationThread; // edi
  KPRIORITY PriorityThread; // eax
  __int64 v4; // rdx
  __int128 v6; // [rsp+30h] [rbp-28h] BYREF

  *(_OWORD *)a1 = 0;
  v6 = 0;
  InformationThread = ZwQueryInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadIoPriority, (PVOID)(a1 + 4), 4u, 0);
  if ( InformationThread >= 0 )
  {
    *(_DWORD *)a1 |= 1u;
    InformationThread = ZwQueryInformationThread(
                          (HANDLE)0xFFFFFFFFFFFFFFFELL,
                          ThreadPagePriority,
                          (PVOID)(a1 + 8),
                          4u,
                          0);
    if ( InformationThread >= 0 )
    {
      *(_DWORD *)a1 |= 2u;
      PriorityThread = KeQueryPriorityThread(KeGetCurrentThread());
      *(_DWORD *)a1 |= 4u;
      LODWORD(v6) = v6 | 7;
      *(_DWORD *)(a1 + 12) = PriorityThread;
      *((_QWORD *)&v6 + 1) = 0x400000001LL;
      DWORD1(v6) = 0;
      InformationThread = WimpFSFSetPriorities(&v6, 0);
      if ( InformationThread < 0 )
      {
        LOBYTE(v4) = 1;
        WimpFSFSetPriorities(a1, v4);
      }
    }
  }
  return (unsigned int)InformationThread;
}

```

## disassembly

```asm
0x14002aa38  mov     [rsp+arg_8], rbx
0x14002aa3d  push    rdi
0x14002aa3e  sub     rsp, 50h
0x14002aa42  mov     rax, cs:__security_cookie
0x14002aa49  xor     rax, rsp
0x14002aa4c  mov     [rsp+58h+var_18], rax
0x14002aa51  mov     edx, 16h; ThreadInformationClass
0x14002aa56  mov     [rsp+58h+ReturnLength], 0; ReturnLength
0x14002aa5f  xorps   xmm1, xmm1
0x14002aa62  lea     r8, [rcx+4]; ThreadInformation
0x14002aa66  mov     rbx, rcx
0x14002aa69  xorps   xmm0, xmm0
0x14002aa6c  movups  xmmword ptr [rcx], xmm1
0x14002aa6f  lea     r9d, [rdx-12h]; ThreadInformationLength
0x14002aa73  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x14002aa7a  movups  [rsp+58h+var_28], xmm0
0x14002aa7f  call    cs:__imp_ZwQueryInformationThread
0x14002aa86  nop     dword ptr [rax+rax+00h]
0x14002aa8b  mov     edi, eax
0x14002aa8d  test    eax, eax
0x14002aa8f  js      loc_14002AB1E
0x14002aa95  or      dword ptr [rbx], 1
0x14002aa98  lea     r8, [rbx+8]; ThreadInformation
0x14002aa9c  mov     edx, 18h; ThreadInformationClass
0x14002aaa1  mov     [rsp+58h+ReturnLength], 0; ReturnLength
0x14002aaaa  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x14002aab1  lea     r9d, [rdx-14h]; ThreadInformationLength
0x14002aab5  call    cs:__imp_ZwQueryInformationThread
0x14002aabc  nop     dword ptr [rax+rax+00h]
0x14002aac1  mov     edi, eax
0x14002aac3  test    eax, eax
0x14002aac5  js      short loc_14002AB1E
0x14002aac7  or      dword ptr [rbx], 2
0x14002aaca  mov     rcx, gs:188h; Thread
0x14002aad3  call    cs:__imp_KeQueryPriorityThread
0x14002aada  nop     dword ptr [rax+rax+00h]
0x14002aadf  or      dword ptr [rbx], 4
0x14002aae2  lea     rcx, [rsp+58h+var_28]
0x14002aae7  or      dword ptr [rsp+58h+var_28], 7
0x14002aaec  xor     edx, edx
0x14002aaee  mov     [rbx+0Ch], eax
0x14002aaf1  mov     dword ptr [rsp+58h+var_28+0Ch], 4
0x14002aaf9  mov     dword ptr [rsp+58h+var_28+8], 1
0x14002ab01  mov     dword ptr [rsp+58h+var_28+4], 0
0x14002ab09  call    WimpFSFSetPriorities
0x14002ab0e  mov     edi, eax
0x14002ab10  test    eax, eax
0x14002ab12  jns     short loc_14002AB1E
0x14002ab14  mov     dl, 1
0x14002ab16  mov     rcx, rbx
0x14002ab19  call    WimpFSFSetPriorities
0x14002ab1e  mov     eax, edi
0x14002ab20  mov     rcx, [rsp+58h+var_18]
0x14002ab25  xor     rcx, rsp; StackCookie
0x14002ab28  call    __security_check_cookie
0x14002ab2d  mov     rbx, [rsp+58h+arg_8]
0x14002ab32  add     rsp, 50h
0x14002ab36  pop     rdi
0x14002ab37  retn
```
