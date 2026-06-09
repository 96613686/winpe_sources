# FileProvInitializeCompressWorkItem

- ea: `0x14003b2e0`
- end: `0x14003b3ad`
- name: `FileProvInitializeCompressWorkItem`
- size: `205`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14003b078`

## callees

- `0x140011270`
- `0x14003b2e0`

## import_xrefs

- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14003b31d`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14003b31d`
- `ntoskrnl!KeInitializeEvent` at `0x14003b350`
- `ntoskrnl!KeInitializeEvent` at `0x14003b350`

## pseudocode

```c
__int64 __fastcall FileProvInitializeCompressWorkItem(_DWORD *a1, int a2, __int64 a3, __int64 a4)
{
  _BYTE *v7; // rax
  int v8; // r9d
  unsigned int v9; // edi

  *(_QWORD *)(a4 + 40) = a1;
  *(_DWORD *)(a4 + 32) = a2;
  *(_QWORD *)(a4 + 48) = a3;
  *(_QWORD *)(a4 + 16) = FileProvCompressWorkItem;
  *(_QWORD *)(a4 + 24) = a4;
  *(_QWORD *)a4 = 0;
  v7 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)(a1 + 16));
  *(_QWORD *)(a4 + 80) = v7;
  if ( v7 )
  {
    *(_QWORD *)(a4 + 72) = &v7[a1[2]];
    if ( a2 == 1 )
    {
      *(_QWORD *)(a4 + 120) = v7;
      v7[17348] = 0;
      if ( !(unsigned int)LZX_EncodeInit(*(_QWORD *)(a4 + 120), *a1, *a1, v8) )
        return (unsigned int)-1073741823;
      *(_BYTE *)(*(_QWORD *)(a4 + 120) + 17348LL) = 1;
    }
    v9 = 0;
    KeInitializeEvent((PRKEVENT)(a4 + 96), SynchronizationEvent, 0);
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return v9;
}

```

## disassembly

```asm
0x14003b2e0  mov     [rsp+arg_0], rbx
0x14003b2e5  mov     [rsp+arg_8], rsi
0x14003b2ea  push    rdi
0x14003b2eb  sub     rsp, 40h
0x14003b2ef  mov     [r9+28h], rcx
0x14003b2f3  lea     rax, FileProvCompressWorkItem
0x14003b2fa  mov     [r9+20h], edx
0x14003b2fe  mov     rbx, r9
0x14003b301  mov     [r9+30h], r8
0x14003b305  mov     rdi, rcx
0x14003b308  add     rcx, 40h ; '@'; Lookaside
0x14003b30c  mov     [r9+10h], rax
0x14003b310  mov     [r9+18h], rbx
0x14003b314  mov     esi, edx
0x14003b316  mov     qword ptr [r9], 0
0x14003b31d  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14003b324  nop     dword ptr [rax+rax+00h]
0x14003b329  mov     [rbx+50h], rax
0x14003b32d  mov     r8, rax
0x14003b330  test    rax, rax
0x14003b333  jz      short loc_14003B36F
0x14003b335  mov     eax, [rdi+8]
0x14003b338  add     rax, r8
0x14003b33b  mov     [rbx+48h], rax
0x14003b33f  cmp     esi, 1
0x14003b342  jz      short loc_14003B376
0x14003b344  xor     edi, edi
0x14003b346  lea     rcx, [rbx+60h]; Event
0x14003b34a  xor     r8d, r8d; State
0x14003b34d  lea     edx, [rdi+1]; Type
0x14003b350  call    cs:__imp_KeInitializeEvent
0x14003b357  nop     dword ptr [rax+rax+00h]
0x14003b35c  mov     rbx, [rsp+48h+arg_0]
0x14003b361  mov     eax, edi
0x14003b363  mov     rsi, [rsp+48h+arg_8]
0x14003b368  add     rsp, 40h
0x14003b36c  pop     rdi
0x14003b36d  retn
0x14003b36f  mov     edi, 0C000009Ah
0x14003b374  jmp     short loc_14003B35C
0x14003b376  mov     [rbx+78h], r8
0x14003b37a  mov     byte ptr [r8+43C4h], 0
0x14003b382  mov     rcx, [rbx+78h]
0x14003b386  mov     edx, [rdi]
0x14003b388  mov     r8d, edx
0x14003b38b  mov     [rsp+48h+var_18], rcx
0x14003b390  call    LZX_EncodeInit
0x14003b395  test    eax, eax
0x14003b397  jnz     short loc_14003B3A0
0x14003b399  mov     edi, 0C0000001h
0x14003b39e  jmp     short loc_14003B35C
0x14003b3a0  mov     rax, [rbx+78h]
0x14003b3a4  mov     byte ptr [rax+43C4h], 1
0x14003b3ab  jmp     short loc_14003B344
```
