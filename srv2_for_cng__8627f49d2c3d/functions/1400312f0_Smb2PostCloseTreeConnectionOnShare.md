# Smb2PostCloseTreeConnectionOnShare

- ea: `0x1400312f0`
- end: `0x1400313fc`
- name: `Smb2PostCloseTreeConnectionOnShare`
- size: `268`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140069984`

## callees

- `0x140004960`
- `0x140005070`
- `0x1400312f0`
- `0x140085d00`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x14003134c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003134c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140031321`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140031321`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1400313b3`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1400313b3`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400313ce`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400313ce`

## string_xrefs

- `0x140031394`: `Srv2PostToThreadPool`

## pseudocode

```c
int __fastcall Smb2PostCloseTreeConnectionOnShare(__int64 a1)
{
  char v2; // di
  __int64 v3; // rdx
  PSLIST_ENTRY v4; // rax
  volatile signed __int64 *v5; // rdi
  bool v6; // zf
  __int64 v7; // rbx
  __int64 v8; // rbx

  if ( ((_InterlockedExchangeAdd64(*(volatile signed __int64 **)a1, 1u) + 2) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    __int2c();
  ExAcquireResourceExclusiveLite((PERESOURCE)(*(_QWORD *)a1 + 96LL), 1u);
  if ( *(_BYTE *)(a1 + 281) )
  {
    v2 = 1;
  }
  else
  {
    v2 = 0;
    *(_BYTE *)(a1 + 281) = 1;
  }
  ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)a1 + 96LL));
  if ( v2 )
  {
    LODWORD(v4) = Smb2DereferenceShare(a1);
  }
  else
  {
    *(_QWORD *)(*(_QWORD *)a1 + 48LL) = Smb2PostCloseTreeConnectionOnShareCallback;
    v5 = *(volatile signed __int64 **)a1;
    v6 = *(_DWORD *)(*(_QWORD *)a1 + 8LL) == 5;
    *(_DWORD *)(*(_QWORD *)a1 + 72LL) = 0;
    if ( v6 )
    {
      LOBYTE(v3) = 1;
      SRV2_PERF_ENTER_EX(v5 + 73, v3, 391, "Srv2PostToThreadPool", 1);
    }
    v7 = *(_QWORD *)(*((_QWORD *)v5 + 8) + 136LL);
    v8 = *(_QWORD *)(v7 + 8LL * KeGetCurrentNodeNumber() + 8);
    v4 = ExpInterlockedPushEntrySList((PSLIST_HEADER)v8, (PSLIST_ENTRY)v5 + 2);
    if ( !v4 && *(_WORD *)(v8 + 66) )
      LODWORD(v4) = RfspThreadPoolNodeWakeIdleWorker((struct _KEVENT *)v8);
  }
  return (int)v4;
}

```

## disassembly

```asm
0x1400312f0  mov     [rsp+arg_0], rbx
0x1400312f5  push    rdi
0x1400312f6  sub     rsp, 30h
0x1400312fa  mov     rax, [rcx]
0x1400312fd  mov     rbx, rcx
0x140031300  mov     edx, 1
0x140031305  lock xadd [rax], rdx
0x14003130a  lea     rax, [rdx+2]
0x14003130e  test    rax, 0FFFFFFFFFFFFFFFEh
0x140031314  jnz     short loc_140031318
0x140031316  int     2Ch; Windows NT - assertion failure
0x140031318  mov     rcx, [rcx]
0x14003131b  mov     dl, 1; Wait
0x14003131d  add     rcx, 60h ; '`'; Resource
0x140031321  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140031328  nop     dword ptr [rax+rax+00h]
0x14003132d  cmp     byte ptr [rbx+119h], 0
0x140031334  jz      short loc_14003133B
0x140031336  mov     dil, 1
0x140031339  jmp     short loc_140031345
0x14003133b  xor     dil, dil
0x14003133e  mov     byte ptr [rbx+119h], 1
0x140031345  mov     rcx, [rbx]
0x140031348  add     rcx, 60h ; '`'; Resource
0x14003134c  call    cs:__imp_ExReleaseResourceLite
0x140031353  nop     dword ptr [rax+rax+00h]
0x140031358  test    dil, dil
0x14003135b  jz      short loc_14003136A
0x14003135d  mov     rcx, rbx
0x140031360  call    Smb2DereferenceShare
0x140031365  jmp     loc_1400313F0
0x14003136a  mov     rax, [rbx]
0x14003136d  lea     rcx, Smb2PostCloseTreeConnectionOnShareCallback
0x140031374  mov     [rax+30h], rcx
0x140031378  mov     rdi, [rbx]
0x14003137b  cmp     dword ptr [rdi+8], 5
0x14003137f  mov     dword ptr [rdi+48h], 0
0x140031386  jnz     short loc_1400313A8
0x140031388  lea     rcx, [rdi+248h]
0x14003138f  mov     [rsp+38h+var_18], 1
0x140031394  lea     r9, SourceString; "Srv2PostToThreadPool"
0x14003139b  mov     r8d, 187h
0x1400313a1  mov     dl, 1
0x1400313a3  call    SRV2_PERF_ENTER_EX
0x1400313a8  mov     rax, [rdi+40h]
0x1400313ac  mov     rbx, [rax+88h]
0x1400313b3  call    cs:__imp_KeGetCurrentNodeNumber
0x1400313ba  nop     dword ptr [rax+rax+00h]
0x1400313bf  movzx   eax, ax
0x1400313c2  lea     rdx, [rdi+20h]; ListEntry
0x1400313c6  mov     rbx, [rbx+rax*8+8]
0x1400313cb  mov     rcx, rbx; ListHead
0x1400313ce  call    cs:__imp_ExpInterlockedPushEntrySList
0x1400313d5  nop     dword ptr [rax+rax+00h]
0x1400313da  test    rax, rax
0x1400313dd  jnz     short loc_1400313F0
0x1400313df  movzx   edx, word ptr [rbx+42h]
0x1400313e3  cmp     ax, dx
0x1400313e6  jz      short loc_1400313F0
0x1400313e8  mov     rcx, rbx
0x1400313eb  call    RfspThreadPoolNodeWakeIdleWorker
0x1400313f0  mov     rbx, [rsp+38h+arg_0]
0x1400313f5  add     rsp, 30h
0x1400313f9  pop     rdi
0x1400313fa  retn
```
