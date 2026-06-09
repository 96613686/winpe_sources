# WinHvpOnCallCompletionNotification

- ea: `0x140007a40`
- end: `0x140007ad1`
- name: `WinHvpOnCallCompletionNotification`
- size: `145`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400011c0`

## callees

- `0x140002bf0`
- `0x140007a40`

## import_xrefs

- `ntoskrnl!KeInsertQueueDpc` at `0x140007ab9`
- `ntoskrnl!KeInsertQueueDpc` at `0x140007ab9`

## pseudocode

```c
BOOLEAN __fastcall WinHvpOnCallCompletionNotification(__int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // rdx
  int v4; // eax
  unsigned int v5; // ecx
  struct _KDPC *v6; // rcx
  int v7; // eax
  unsigned int v8; // eax

  v2 = *(_QWORD *)(a1 + 16);
  if ( v2 )
  {
    v3 = WinHvpReferencePartition(v2);
    v4 = *(unsigned __int16 *)(a1 + 24);
    if ( (_WORD)v4 )
      v5 = v4 | 0xC0350000;
    else
      v5 = 0;
    *(_DWORD *)(v3 + 240) = v5;
    v6 = (struct _KDPC *)(v3 + 96);
    *(_QWORD *)(v3 + 248) = *(_QWORD *)(a1 + 32);
    *(_DWORD *)(v3 + 256) = *(_DWORD *)(a1 + 28);
  }
  else
  {
    v7 = *(unsigned __int16 *)(a1 + 24);
    if ( (_WORD)v7 )
      v8 = v7 | 0xC0350000;
    else
      v8 = 0;
    WinHvpGlobalAsyncStatus = v8;
    v6 = &WinHvpGlobalAsyncDpc;
    v3 = 0;
  }
  return KeInsertQueueDpc(v6, (PVOID)v3, 0);
}

```

## disassembly

```asm
0x140007a40  mov     [rsp+arg_0], rbx
0x140007a45  push    rdi
0x140007a46  sub     rsp, 20h
0x140007a4a  mov     rbx, rcx
0x140007a4d  xor     edi, edi
0x140007a4f  mov     rcx, [rcx+10h]
0x140007a53  test    rcx, rcx
0x140007a56  jz      short loc_140007A95
0x140007a58  call    WinHvpReferencePartition
0x140007a5d  mov     rdx, rax
0x140007a60  movzx   eax, word ptr [rbx+18h]
0x140007a64  test    ax, ax
0x140007a67  jnz     short loc_140007A6D
0x140007a69  mov     ecx, edi
0x140007a6b  jmp     short loc_140007A75
0x140007a6d  mov     ecx, eax
0x140007a6f  or      ecx, 0C0350000h
0x140007a75  mov     [rdx+0F0h], ecx
0x140007a7b  lea     rcx, [rdx+60h]
0x140007a7f  mov     rax, [rbx+20h]
0x140007a83  mov     [rdx+0F8h], rax
0x140007a8a  mov     eax, [rbx+1Ch]
0x140007a8d  mov     [rdx+100h], eax
0x140007a93  jmp     short loc_140007AB6
0x140007a95  movzx   eax, word ptr [rbx+18h]
0x140007a99  test    ax, ax
0x140007a9c  jnz     short loc_140007AA2
0x140007a9e  mov     eax, edi
0x140007aa0  jmp     short loc_140007AA7
0x140007aa2  or      eax, 0C0350000h
0x140007aa7  mov     cs:WinHvpGlobalAsyncStatus, eax
0x140007aad  lea     rcx, WinHvpGlobalAsyncDpc; Dpc
0x140007ab4  xor     edx, edx; SystemArgument1
0x140007ab6  xor     r8d, r8d; SystemArgument2
0x140007ab9  call    cs:__imp_KeInsertQueueDpc
0x140007ac0  nop     dword ptr [rax+rax+00h]
0x140007ac5  mov     rbx, [rsp+28h+arg_0]
0x140007aca  add     rsp, 20h
0x140007ace  pop     rdi
0x140007acf  retn
```
