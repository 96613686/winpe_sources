# Smb2OplockLevelIIBreakSendComplete

- ea: `0x14002c360`
- end: `0x14002c492`
- name: `Smb2OplockLevelIIBreakSendComplete`
- size: `306`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140004960`
- `0x140005070`
- `0x14002bfc0`
- `0x14002c360`
- `0x14002d4dc`

## import_xrefs

- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14002c43a`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14002c43a`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002c3e5`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002c3e5`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14002c455`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14002c455`

## string_xrefs

- `0x14002c41b`: `Srv2PostToThreadPool`

## pseudocode

```c
int __fastcall Smb2OplockLevelIIBreakSendComplete(int a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rdi
  __int64 (__fastcall *v5)(PVOID); // rax
  bool v6; // zf
  __int64 v7; // rbx
  __int64 v8; // rbx
  PSLIST_ENTRY v9; // rax
  __int64 v11; // [rsp+20h] [rbp-18h]

  v3 = *(_QWORD *)(a3 + 24);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v11 = *(_QWORD *)(a3 + 24);
    WPP_SF_qqD(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_cd88c939257b3d437242ae5a960c8d69_Traceguids);
  }
  if ( (int)(a1 + 0x80000000) < 0 || a1 == -1073741108 || *(_QWORD *)(v3 + 304) == v3 + 304 )
  {
    if ( KeGetCurrentIrql() < 2u )
    {
      LODWORD(v9) = Smb2OplockCompleteLevelIIBreak((PVOID)v3);
      return (int)v9;
    }
    v5 = Smb2OplockCompleteLevelIIBreak;
  }
  else
  {
    v5 = Smb2OplockRetryBreakSend;
  }
  *(_QWORD *)(v3 + 48) = v5;
  v6 = *(_DWORD *)(v3 + 8) == 5;
  *(_DWORD *)(v3 + 72) = 0;
  if ( v6 )
  {
    LOBYTE(v11) = 1;
    LOBYTE(a2) = 1;
    SRV2_PERF_ENTER_EX(v3 + 584, a2, 391, "Srv2PostToThreadPool", v11);
  }
  v7 = *(_QWORD *)(*(_QWORD *)(v3 + 64) + 136LL);
  v8 = *(_QWORD *)(v7 + 8LL * KeGetCurrentNodeNumber() + 8);
  v9 = ExpInterlockedPushEntrySList((PSLIST_HEADER)v8, (PSLIST_ENTRY)(v3 + 32));
  if ( !v9 )
  {
    LODWORD(v9) = *(unsigned __int16 *)(v8 + 66);
    if ( (_WORD)v9 )
      LODWORD(v9) = RfspThreadPoolNodeWakeIdleWorker((struct _KEVENT *)v8);
  }
  return (int)v9;
}

```

## disassembly

```asm
0x14002c360  mov     [rsp+arg_0], rbx
0x14002c365  mov     [rsp+arg_8], rsi
0x14002c36a  push    rdi
0x14002c36b  sub     rsp, 30h
0x14002c36f  mov     rdi, [r8+18h]
0x14002c373  mov     ebx, ecx
0x14002c375  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002c37c  lea     rax, WPP_GLOBAL_Control
0x14002c383  cmp     rcx, rax
0x14002c386  jz      short loc_14002C3BC
0x14002c388  test    dword ptr [rcx+2Ch], 400000h
0x14002c38f  jz      short loc_14002C3BC
0x14002c391  cmp     byte ptr [rcx+29h], 2
0x14002c395  jb      short loc_14002C3BC
0x14002c397  mov     r9, [rdi+90h]
0x14002c39e  lea     r8, WPP_cd88c939257b3d437242ae5a960c8d69_Traceguids
0x14002c3a5  mov     rcx, [rcx+18h]
0x14002c3a9  mov     edx, 1Dh
0x14002c3ae  mov     [rsp+38h+var_10], ebx
0x14002c3b2  mov     [rsp+38h+var_18], rdi
0x14002c3b7  call    WPP_SF_qqD
0x14002c3bc  mov     ecx, 80000000h
0x14002c3c1  lea     eax, [rbx+rcx]
0x14002c3c4  test    ecx, eax
0x14002c3c6  jnz     short loc_14002C3E5
0x14002c3c8  cmp     ebx, 0C00002CCh
0x14002c3ce  jz      short loc_14002C3E5
0x14002c3d0  lea     rax, [rdi+130h]
0x14002c3d7  cmp     [rax], rax
0x14002c3da  jz      short loc_14002C3E5
0x14002c3dc  lea     rax, Smb2OplockRetryBreakSend
0x14002c3e3  jmp     short loc_14002C400
0x14002c3e5  call    cs:__imp_KeGetCurrentIrql
0x14002c3ec  nop     dword ptr [rax+rax+00h]
0x14002c3f1  cmp     al, 2
0x14002c3f3  jb      loc_14002C479
0x14002c3f9  lea     rax, Smb2OplockCompleteLevelIIBreak
0x14002c400  xor     esi, esi
0x14002c402  mov     [rdi+30h], rax
0x14002c406  cmp     dword ptr [rdi+8], 5
0x14002c40a  mov     [rdi+48h], esi
0x14002c40d  jnz     short loc_14002C42F
0x14002c40f  lea     rcx, [rdi+248h]
0x14002c416  mov     byte ptr [rsp+38h+var_18], 1
0x14002c41b  lea     r9, SourceString; "Srv2PostToThreadPool"
0x14002c422  mov     r8d, 187h
0x14002c428  mov     dl, 1
0x14002c42a  call    SRV2_PERF_ENTER_EX
0x14002c42f  mov     rax, [rdi+40h]
0x14002c433  mov     rbx, [rax+88h]
0x14002c43a  call    cs:__imp_KeGetCurrentNodeNumber
0x14002c441  nop     dword ptr [rax+rax+00h]
0x14002c446  movzx   eax, ax
0x14002c449  lea     rdx, [rdi+20h]; ListEntry
0x14002c44d  mov     rbx, [rbx+rax*8+8]
0x14002c452  mov     rcx, rbx; ListHead
0x14002c455  call    cs:__imp_ExpInterlockedPushEntrySList
0x14002c45c  nop     dword ptr [rax+rax+00h]
0x14002c461  test    rax, rax
0x14002c464  jnz     short loc_14002C481
0x14002c466  movzx   eax, word ptr [rbx+42h]
0x14002c46a  cmp     si, ax
0x14002c46d  jz      short loc_14002C481
0x14002c46f  mov     rcx, rbx
0x14002c472  call    RfspThreadPoolNodeWakeIdleWorker
0x14002c477  jmp     short loc_14002C481
0x14002c479  mov     rcx, rdi; P
0x14002c47c  call    Smb2OplockCompleteLevelIIBreak
0x14002c481  mov     rbx, [rsp+38h+arg_0]
0x14002c486  mov     rsi, [rsp+38h+arg_8]
0x14002c48b  add     rsp, 30h
0x14002c48f  pop     rdi
0x14002c490  retn
```
