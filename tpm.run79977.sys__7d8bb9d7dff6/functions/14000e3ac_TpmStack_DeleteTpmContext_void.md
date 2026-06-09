# TpmStack::DeleteTpmContext(void *)

- ea: `0x14000e3ac`
- end: `0x14000e4dd`
- name: `?DeleteTpmContext@TpmStack@@QEAAXPEAX@Z`
- size: `305`
- prototype: `void __fastcall(TpmStack *__hidden this, void *)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000e2b0`
- `0x14001d224`
- `0x14002ed30`

## callees

- `0x14000e3ac`
- `0x14000e4e4`
- `0x14000e98c`
- `0x14001ab78`
- `0x140039780`

## import_xrefs

- `ntoskrnl!ExInterlockedInsertTailList` at `0x14000e448`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x14000e448`
- `ntoskrnl!KeSetEvent` at `0x14000e464`
- `ntoskrnl!KeSetEvent` at `0x14000e464`

## pseudocode

```c
void __fastcall TpmStack::DeleteTpmContext(TpmDevice **this, char *a2)
{
  Tpm20Scheduler *v4; // rbx
  const void **v5; // rax
  __int64 v6; // rax
  TpmDevice *v7; // rbx
  const void ***v8; // rbp
  const void ***v9; // rdx

  if ( TpmTransportType::m_Version == 1 )
  {
    TpmDevice::DeleteContext(*this, a2);
  }
  else
  {
    v4 = this[2];
    (*((void (__fastcall **)(PKDPC, _QWORD, _QWORD))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 313))(
      WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
      *((_QWORD *)v4 + 7),
      0);
    if ( a2 )
      a2[44] = 1;
    v5 = (const void **)*((_QWORD *)v4 + 8);
    if ( v5 != (const void **)((char *)v4 + 64) )
    {
      do
      {
        v8 = (const void ***)*v5;
        if ( *(v5 - 30) == a2 )
        {
          if ( v8[1] != v5 || (v9 = (const void ***)v5[1], *v9 != v5) )
            __fastfail(3u);
          *v9 = (const void **)v8;
          v8[1] = (const void **)v9;
          Tpm20Context::CompleteTpm20Request(v5 - 32, 0xC0000120);
        }
        v5 = (const void **)v8;
      }
      while ( v8 != (const void ***)((char *)v4 + 64) );
    }
    if ( a2 )
      a2[44] = 0;
    v6 = *((_QWORD *)v4 + 10);
    if ( v6 && *(char **)(v6 + 16) == a2 )
      Tpm20Scheduler::CancelCurrentRequestLockedAndUnlock(v4);
    else
      (*((void (__fastcall **)(PKDPC, _QWORD))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 314))(
        WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
        *((_QWORD *)v4 + 7));
    v7 = this[2];
    ExInterlockedInsertTailList((PLIST_ENTRY)((char *)v7 + 120), (PLIST_ENTRY)(a2 + 24), (PKSPIN_LOCK)v7 + 14);
    _InterlockedOr((volatile signed __int32 *)v7 + 47, 0x10u);
    KeSetEvent((PRKEVENT)v7, 0, 0);
  }
}

```

## disassembly

```asm
0x14000e3ac  push    rbx
0x14000e3ae  push    rbp
0x14000e3af  push    rsi
0x14000e3b0  push    rdi
0x14000e3b1  push    r14
0x14000e3b3  sub     rsp, 20h
0x14000e3b7  cmp     cs:?m_Version@TpmTransportType@@0W4VERSION@1@A, 1; TpmTransportType::VERSION TpmTransportType::m_Version
0x14000e3be  mov     rdi, rdx
0x14000e3c1  mov     r14, rcx
0x14000e3c4  jz      loc_14000E4AA
0x14000e3ca  mov     rbx, [rcx+10h]
0x14000e3ce  xor     r8d, r8d
0x14000e3d1  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x14000e3d8  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x14000e3df  mov     rdx, [rbx+38h]
0x14000e3e3  mov     rax, [rax+9C8h]
0x14000e3ea  call    _guard_dispatch_icall
0x14000e3ef  test    rdi, rdi
0x14000e3f2  jz      short loc_14000E3F8
0x14000e3f4  mov     byte ptr [rdi+2Ch], 1
0x14000e3f8  lea     rsi, [rbx+40h]
0x14000e3fc  mov     rax, [rsi]
0x14000e3ff  cmp     rax, rsi
0x14000e402  jnz     loc_14000E48C
0x14000e408  test    rdi, rdi
0x14000e40b  jz      short loc_14000E411
0x14000e40d  mov     byte ptr [rdi+2Ch], 0
0x14000e411  mov     rax, [rbx+50h]
0x14000e415  test    rax, rax
0x14000e418  jnz     short loc_14000E47C
0x14000e41a  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x14000e421  mov     rdx, [rbx+38h]
0x14000e425  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x14000e42c  mov     rax, [rax+9D0h]
0x14000e433  call    _guard_dispatch_icall
0x14000e438  mov     rbx, [r14+10h]
0x14000e43c  lea     rdx, [rdi+18h]; ListEntry
0x14000e440  lea     r8, [rbx+70h]; Lock
0x14000e444  lea     rcx, [rbx+78h]; ListHead
0x14000e448  call    cs:__imp_ExInterlockedInsertTailList
0x14000e44f  nop     dword ptr [rax+rax+00h]
0x14000e454  lock or dword ptr [rbx+0BCh], 10h
0x14000e45c  xor     r8d, r8d; Wait
0x14000e45f  xor     edx, edx; Increment
0x14000e461  mov     rcx, rbx; Event
0x14000e464  call    cs:__imp_KeSetEvent
0x14000e46b  nop     dword ptr [rax+rax+00h]
0x14000e470  add     rsp, 20h
0x14000e474  pop     r14
0x14000e476  pop     rdi
0x14000e477  pop     rsi
0x14000e478  pop     rbp
0x14000e479  pop     rbx
0x14000e47a  retn
0x14000e47c  cmp     [rax+10h], rdi
0x14000e480  jnz     short loc_14000E41A
0x14000e482  mov     rcx, rbx; this
0x14000e485  call    ?CancelCurrentRequestLockedAndUnlock@Tpm20Scheduler@@AEAAXXZ; Tpm20Scheduler::CancelCurrentRequestLockedAndUnlock(void)
0x14000e48a  jmp     short loc_14000E438
0x14000e48c  mov     rbp, [rax]
0x14000e48f  lea     rcx, [rax-100h]; this
0x14000e496  cmp     [rcx+10h], rdi
0x14000e49a  jz      short loc_14000E4B4
0x14000e49c  mov     rax, rbp
0x14000e49f  cmp     rbp, rsi
0x14000e4a2  jz      loc_14000E408
0x14000e4a8  jmp     short loc_14000E48C
0x14000e4aa  mov     rcx, [rcx]; this
0x14000e4ad  call    ?DeleteContext@TpmDevice@@QEAAXPEAX@Z; TpmDevice::DeleteContext(void *)
0x14000e4b2  jmp     short loc_14000E470
0x14000e4b4  cmp     [rbp+8], rax
0x14000e4b8  jnz     short loc_14000E4D6
0x14000e4ba  mov     rdx, [rax+8]
0x14000e4be  cmp     [rdx], rax
0x14000e4c1  jnz     short loc_14000E4D6
0x14000e4c3  mov     [rdx], rbp
0x14000e4c6  mov     [rbp+8], rdx
0x14000e4ca  mov     edx, 0C0000120h; int
0x14000e4cf  call    ?CompleteTpm20Request@Tpm20Context@@SAXPEAVTpm20Request@@J@Z; Tpm20Context::CompleteTpm20Request(Tpm20Request *,long)
0x14000e4d4  jmp     short loc_14000E49C
0x14000e4d6  mov     ecx, 3
0x14000e4db  int     29h; Win8: RtlFailFast(ecx)
```
