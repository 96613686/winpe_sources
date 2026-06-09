# UdfUpdateLvidCounts

- ea: `0x140017ecc`
- end: `0x140017fa2`
- name: `UdfUpdateLvidCounts`
- size: `214`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14001662c`
- `0x140031144`
- `0x140033548`

## callees

- `0x14001093c`
- `0x140017ecc`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140017eee`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140017eee`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140017f85`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140017f85`

## pseudocode

```c
void __fastcall UdfUpdateLvidCounts(__int64 a1, char a2, int a3)
{
  __int64 v6; // rax

  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(a1 + 16) + 1584LL));
  *(_QWORD *)(*(_QWORD *)(a1 + 16) + 1640LL) = KeGetCurrentThread();
  v6 = *(_QWORD *)(a1 + 16);
  if ( a2 )
    *(_DWORD *)(v6 + 1468) += a3;
  else
    *(_DWORD *)(v6 + 1464) += a3;
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x10000000) != 0 )
  {
    WPP_SF_dd(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
      10,
      WPP_3e271ebed6f63f8fe36d0f7ec1e80eae_Traceguids,
      *(unsigned int *)(*(_QWORD *)(a1 + 16) + 1464LL),
      *(_DWORD *)(*(_QWORD *)(a1 + 16) + 1468LL));
  }
  *(_QWORD *)(*(_QWORD *)(a1 + 16) + 1640LL) = 0;
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(a1 + 16) + 1584LL));
}

```

## disassembly

```asm
0x140017ecc  mov     [rsp+arg_0], rbx
0x140017ed1  mov     [rsp+arg_8], rsi
0x140017ed6  push    rdi
0x140017ed7  sub     rsp, 30h
0x140017edb  mov     rdi, rcx
0x140017ede  mov     esi, r8d
0x140017ee1  mov     rcx, [rcx+10h]
0x140017ee5  mov     bl, dl
0x140017ee7  add     rcx, 630h; FastMutex
0x140017eee  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140017ef5  nop     dword ptr [rax+rax+00h]
0x140017efa  mov     r9, gs:188h
0x140017f03  mov     rax, [rdi+10h]
0x140017f07  mov     [rax+668h], r9
0x140017f0e  mov     rax, [rdi+10h]
0x140017f12  test    bl, bl
0x140017f14  jz      short loc_140017F1E
0x140017f16  add     [rax+5BCh], esi
0x140017f1c  jmp     short loc_140017F24
0x140017f1e  add     [rax+5B8h], esi
0x140017f24  mov     rcx, cs:WPP_GLOBAL_Control
0x140017f2b  lea     rax, WPP_GLOBAL_Control
0x140017f32  cmp     rcx, rax
0x140017f35  jz      short loc_140017F6B
0x140017f37  test    dword ptr [rcx+2Ch], 10000000h
0x140017f3e  jz      short loc_140017F6B
0x140017f40  mov     r9, [rdi+10h]
0x140017f44  lea     r8, WPP_3e271ebed6f63f8fe36d0f7ec1e80eae_Traceguids
0x140017f4b  mov     rcx, [rcx+18h]
0x140017f4f  mov     edx, 0Ah
0x140017f54  mov     eax, [r9+5BCh]
0x140017f5b  mov     r9d, [r9+5B8h]
0x140017f62  mov     [rsp+38h+var_18], eax
0x140017f66  call    WPP_SF_dd
0x140017f6b  mov     rax, [rdi+10h]
0x140017f6f  mov     qword ptr [rax+668h], 0
0x140017f7a  mov     rcx, [rdi+10h]
0x140017f7e  add     rcx, 630h; FastMutex
0x140017f85  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140017f8c  nop     dword ptr [rax+rax+00h]
0x140017f91  mov     rbx, [rsp+38h+arg_0]
0x140017f96  mov     rsi, [rsp+38h+arg_8]
0x140017f9b  add     rsp, 30h
0x140017f9f  pop     rdi
0x140017fa0  retn
```
