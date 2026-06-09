# SqospRemoveClient

- ea: `0x140015810`
- end: `0x140015892`
- name: `SqospRemoveClient`
- size: `130`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140001ab0`
- `0x140003650`
- `0x140003940`
- `0x140011120`

## callees

- `0x140004b3c`
- `0x140015810`
- `0x1400158a0`

## import_xrefs

- `ntoskrnl!RtlRbRemoveNode` at `0x140015843`
- `ntoskrnl!RtlRbRemoveNode` at `0x140015843`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140015822`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140015822`
- `FLTMGR!FltReleasePushLockEx` at `0x140015860`
- `FLTMGR!FltReleasePushLockEx` at `0x14001587f`
- `FLTMGR!FltReleasePushLockEx` at `0x140015860`
- `FLTMGR!FltReleasePushLockEx` at `0x14001587f`

## pseudocode

```c
__int64 __fastcall SqospRemoveClient(_DWORD *Entry)
{
  FltAcquirePushLockExclusiveEx(&SqosGlobals, 0);
  if ( Entry[3] )
    return FltReleasePushLockEx(&SqosGlobals, 0);
  *((_BYTE *)Entry + 125) = 0;
  RtlRbRemoveNode(&qword_14000D158, Entry + 16);
  SqospRemoveClientFlows(Entry);
  FltReleasePushLockEx(&SqosGlobals, 0);
  return SqospCleanupClient(Entry);
}

```

## disassembly

```asm
0x140015810  push    rbx
0x140015812  sub     rsp, 20h
0x140015816  mov     rbx, rcx
0x140015819  xor     edx, edx
0x14001581b  lea     rcx, SqosGlobals
0x140015822  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140015829  nop     dword ptr [rax+rax+00h]
0x14001582e  mov     eax, [rbx+0Ch]
0x140015831  test    eax, eax
0x140015833  jnz     short loc_140015876
0x140015835  lea     rdx, [rbx+40h]
0x140015839  mov     [rbx+7Dh], al
0x14001583c  lea     rcx, qword_14000D158
0x140015843  call    cs:__imp_RtlRbRemoveNode
0x14001584a  nop     dword ptr [rax+rax+00h]
0x14001584f  mov     rcx, rbx
0x140015852  call    SqospRemoveClientFlows
0x140015857  xor     edx, edx
0x140015859  lea     rcx, SqosGlobals
0x140015860  call    cs:__imp_FltReleasePushLockEx
0x140015867  nop     dword ptr [rax+rax+00h]
0x14001586c  mov     rcx, rbx; Entry
0x14001586f  call    SqospCleanupClient
0x140015874  jmp     short loc_14001588B
0x140015876  xor     edx, edx
0x140015878  lea     rcx, SqosGlobals
0x14001587f  call    cs:__imp_FltReleasePushLockEx
0x140015886  nop     dword ptr [rax+rax+00h]
0x14001588b  add     rsp, 20h
0x14001588f  pop     rbx
0x140015890  retn
```
