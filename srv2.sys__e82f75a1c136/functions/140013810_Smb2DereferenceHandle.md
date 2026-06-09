# Smb2DereferenceHandle

- ea: `0x140013810`
- end: `0x140013913`
- name: `Smb2DereferenceHandle`
- size: `259`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `30`
- callee_count: `4`
- tags: ``

## callers

- `0x14005a50c`
- `0x140063bf4`
- `0x140063dd4`
- `0x14006479c`
- `0x140064ac4`
- `0x14006507c`
- `0x14006574c`
- `0x140066300`
- `0x1400664c4`
- `0x140066dc4`
- `0x140068c10`
- `0x140068f48`
- `0x140069758`
- `0x14006e180`
- `0x140075bb8`
- `0x1400760e0`
- `0x140076de8`
- `0x14007a84c`
- `0x14007ca40`
- `0x14007cbf0`
- `0x14007e340`
- `0x14007f4c0`
- `0x1400809c0`
- `0x1400813b4`
- `0x140081d90`
- `0x140082290`
- `0x140085260`
- `0x140085670`
- `0x140088cf0`
- `0x140095f88`

## callees

- `0x140004960`
- `0x140005070`
- `0x140013810`
- `0x140091cc0`

## import_xrefs

- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1400138a0`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1400138a0`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400138ed`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400138ed`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400138bb`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400138bb`

## string_xrefs

- `0x140013881`: `Srv2PostToThreadPool`

## pseudocode

```c
__int64 __fastcall Smb2DereferenceHandle(char *P)
{
  signed __int64 v2; // rbx
  bool v4; // zf
  __int64 v5; // rdi
  __int64 v6; // rdi
  __int64 v7; // rdx

  v2 = _InterlockedDecrement64((volatile signed __int64 *)P);
  if ( v2 == -1 )
  {
    __int2c();
    return v2;
  }
  if ( v2 )
    return v2;
  if ( KeGetCurrentIrql() )
  {
    v4 = *((_DWORD *)P + 2) == 5;
    *((_QWORD *)P + 6) = Smb2DereferenceHandleCallback;
    *((_DWORD *)P + 18) = 0;
    if ( v4 )
    {
      LOBYTE(v7) = 1;
      SRV2_PERF_ENTER_EX(P + 584, v7, 391, "Srv2PostToThreadPool", 1);
    }
    v5 = *(_QWORD *)(*((_QWORD *)P + 8) + 136LL);
    v6 = *(_QWORD *)(v5 + 8LL * KeGetCurrentNodeNumber() + 8);
    if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)v6, (PSLIST_ENTRY)P + 2) )
    {
      if ( *(_WORD *)(v6 + 66) )
        RfspThreadPoolNodeWakeIdleWorker((struct _KEVENT *)v6);
    }
    return 0;
  }
  else
  {
    Smb2DereferenceHandleCleanup(P, 0);
    return 0;
  }
}

```

## disassembly

```asm
0x140013810  mov     [rsp+arg_8], rbx
0x140013815  push    rsi
0x140013816  sub     rsp, 30h
0x14001381a  mov     rsi, rcx
0x14001381d  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x140013824  lock xadd [rcx], rbx
0x140013829  dec     rbx
0x14001382c  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140013830  jnb     loc_1400138E6
0x140013836  test    rbx, rbx
0x140013839  jz      loc_1400138ED
0x14001383f  mov     rax, rbx
0x140013842  mov     rbx, [rsp+38h+arg_8]
0x140013847  add     rsp, 30h
0x14001384b  pop     rsi
0x14001384c  retn
0x14001384e  mov     rdi, [rsp+38h+arg_0]
0x140013853  mov     rax, rbx
0x140013856  jmp     short loc_140013842
0x140013858  cmp     dword ptr [rsi+8], 5
0x14001385c  lea     rax, Smb2DereferenceHandleCallback
0x140013863  mov     [rsi+30h], rax
0x140013867  mov     [rsp+38h+arg_0], rdi
0x14001386c  mov     dword ptr [rsi+48h], 0
0x140013873  jnz     short loc_140013895
0x140013875  lea     rcx, [rsi+248h]
0x14001387c  mov     [rsp+38h+var_18], 1
0x140013881  lea     r9, SourceString; "Srv2PostToThreadPool"
0x140013888  mov     r8d, 187h
0x14001388e  mov     dl, 1
0x140013890  call    SRV2_PERF_ENTER_EX
0x140013895  mov     rax, [rsi+40h]
0x140013899  mov     rdi, [rax+88h]
0x1400138a0  call    cs:__imp_KeGetCurrentNodeNumber
0x1400138a7  nop     dword ptr [rax+rax+00h]
0x1400138ac  movzx   eax, ax
0x1400138af  lea     rdx, [rsi+20h]; ListEntry
0x1400138b3  mov     rdi, [rdi+rax*8+8]
0x1400138b8  mov     rcx, rdi; ListHead
0x1400138bb  call    cs:__imp_ExpInterlockedPushEntrySList
0x1400138c2  nop     dword ptr [rax+rax+00h]
0x1400138c7  test    rax, rax
0x1400138ca  jnz     short loc_14001384E
0x1400138cc  movzx   edx, word ptr [rdi+42h]
0x1400138d0  cmp     ax, dx
0x1400138d3  jz      loc_14001384E
0x1400138d9  mov     rcx, rdi
0x1400138dc  call    RfspThreadPoolNodeWakeIdleWorker
0x1400138e1  jmp     loc_14001384E
0x1400138e6  int     2Ch; Windows NT - assertion failure
0x1400138e8  jmp     loc_14001383F
0x1400138ed  call    cs:__imp_KeGetCurrentIrql
0x1400138f4  nop     dword ptr [rax+rax+00h]
0x1400138f9  test    al, al
0x1400138fb  jnz     loc_140013858
0x140013901  xor     edx, edx
0x140013903  mov     rcx, rsi; P
0x140013906  call    Smb2DereferenceHandleCleanup
0x14001390b  mov     rax, rbx
0x14001390e  jmp     loc_140013842
```
