# Smb2DereferenceHandleEx

- ea: `0x14001b3fc`
- end: `0x14001b4e0`
- name: `Smb2DereferenceHandleEx`
- size: `228`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `18`
- callee_count: `4`
- tags: ``

## callers

- `0x140007400`
- `0x14000989c`
- `0x14000a5a0`
- `0x14000c070`
- `0x14000c680`
- `0x14000e5f0`
- `0x140019450`
- `0x14001c2d0`
- `0x14001c8ec`
- `0x140020f78`
- `0x14002143c`
- `0x1400219d4`
- `0x140029228`
- `0x140029810`
- `0x14002a7e8`
- `0x14002eb84`
- `0x14002edbc`
- `0x1400874c0`

## callees

- `0x140004960`
- `0x140005070`
- `0x14001b3fc`
- `0x140091cc0`

## import_xrefs

- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14001b482`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14001b482`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001b433`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001b433`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14001b49d`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14001b49d`

## string_xrefs

- `0x14001b463`: `Srv2PostToThreadPool`

## pseudocode

```c
__int64 __fastcall Smb2DereferenceHandleEx(char *P, __int64 a2)
{
  signed __int64 v4; // rsi
  __int64 v5; // rdx
  bool v6; // zf
  __int64 v7; // rbx
  struct _KEVENT *v8; // rbx

  v4 = _InterlockedDecrement64((volatile signed __int64 *)P);
  if ( v4 == -1 )
  {
    __int2c();
  }
  else if ( !v4 )
  {
    if ( KeGetCurrentIrql() )
    {
      v6 = *((_DWORD *)P + 2) == 5;
      *((_QWORD *)P + 6) = Smb2DereferenceHandleCallback;
      *((_DWORD *)P + 18) = 0;
      if ( v6 )
      {
        LOBYTE(v5) = 1;
        SRV2_PERF_ENTER_EX(P + 584, v5, 391, "Srv2PostToThreadPool", 1);
      }
      v7 = *(_QWORD *)(*((_QWORD *)P + 8) + 136LL);
      v8 = *(struct _KEVENT **)(v7 + 8LL * KeGetCurrentNodeNumber() + 8);
      if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)v8, (PSLIST_ENTRY)P + 2)
        && WORD1(v8[2].Header.WaitListHead.Blink) )
      {
        RfspThreadPoolNodeWakeIdleWorker(v8);
      }
    }
    else
    {
      Smb2DereferenceHandleCleanup(P, a2);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x14001b3fc  mov     [rsp+arg_0], rbx
0x14001b401  mov     [rsp+arg_8], rsi
0x14001b406  push    rdi
0x14001b407  sub     rsp, 30h
0x14001b40b  mov     rbx, rdx
0x14001b40e  mov     rdi, rcx
0x14001b411  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14001b415  lock xadd [rcx], rsi
0x14001b41a  dec     rsi
0x14001b41d  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x14001b421  jb      short loc_14001B42A
0x14001b423  int     2Ch; Windows NT - assertion failure
0x14001b425  jmp     loc_14001B4CC
0x14001b42a  test    rsi, rsi
0x14001b42d  jnz     loc_14001B4CC
0x14001b433  call    cs:__imp_KeGetCurrentIrql
0x14001b43a  nop     dword ptr [rax+rax+00h]
0x14001b43f  test    al, al
0x14001b441  jz      short loc_14001B4C1
0x14001b443  cmp     dword ptr [rdi+8], 5
0x14001b447  lea     rax, Smb2DereferenceHandleCallback
0x14001b44e  mov     [rdi+30h], rax
0x14001b452  mov     [rdi+48h], esi
0x14001b455  jnz     short loc_14001B477
0x14001b457  lea     rcx, [rdi+248h]
0x14001b45e  mov     [rsp+38h+var_18], 1
0x14001b463  lea     r9, SourceString; "Srv2PostToThreadPool"
0x14001b46a  mov     r8d, 187h
0x14001b470  mov     dl, 1
0x14001b472  call    SRV2_PERF_ENTER_EX
0x14001b477  mov     rax, [rdi+40h]
0x14001b47b  mov     rbx, [rax+88h]
0x14001b482  call    cs:__imp_KeGetCurrentNodeNumber
0x14001b489  nop     dword ptr [rax+rax+00h]
0x14001b48e  movzx   eax, ax
0x14001b491  lea     rdx, [rdi+20h]; ListEntry
0x14001b495  mov     rbx, [rbx+rax*8+8]
0x14001b49a  mov     rcx, rbx; ListHead
0x14001b49d  call    cs:__imp_ExpInterlockedPushEntrySList
0x14001b4a4  nop     dword ptr [rax+rax+00h]
0x14001b4a9  test    rax, rax
0x14001b4ac  jnz     short loc_14001B4CC
0x14001b4ae  movzx   edx, word ptr [rbx+42h]
0x14001b4b2  cmp     ax, dx
0x14001b4b5  jz      short loc_14001B4CC
0x14001b4b7  mov     rcx, rbx
0x14001b4ba  call    RfspThreadPoolNodeWakeIdleWorker
0x14001b4bf  jmp     short loc_14001B4CC
0x14001b4c1  mov     rdx, rbx
0x14001b4c4  mov     rcx, rdi; P
0x14001b4c7  call    Smb2DereferenceHandleCleanup
0x14001b4cc  mov     rbx, [rsp+38h+arg_0]
0x14001b4d1  mov     rax, rsi
0x14001b4d4  mov     rsi, [rsp+38h+arg_8]
0x14001b4d9  add     rsp, 30h
0x14001b4dd  pop     rdi
0x14001b4de  retn
```
