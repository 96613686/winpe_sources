# VMX_PACK::PostCommitLog(void)

- ea: `0x14002a920`
- end: `0x14002ab3e`
- name: `?PostCommitLog@VMX_PACK@@AEAAXXZ`
- size: `542`
- prototype: `void __fastcall(VMX_PACK *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x14002a3f4`
- `0x14004e3ac`

## callees

- `0x140007600`
- `0x140007b08`
- `0x140008b38`
- `0x140019dc4`
- `0x140019ed8`
- `0x14001b9a0`
- `0x14002a920`
- `0x140049308`
- `0x140049b84`
- `0x1400549f8`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14002aabb`
- `ntoskrnl!KeInitializeEvent` at `0x14002aabb`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002aafc`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002aafc`

## pseudocode

```c
void __fastcall VMX_PACK::PostCommitLog(VMX_PACK *this)
{
  VMX_LOG *v2; // rcx
  VMX_LOG *v3; // rcx
  char v4; // bp
  _QWORD *v5; // rax
  _QWORD *v6; // rbx
  bool v7; // si
  __int16 v8; // ax
  __int64 v9; // r14
  _QWORD *v10; // rcx
  _QWORD *v11; // rcx
  bool v12; // zf
  __int16 v13; // ax
  unsigned int BlocksCount; // eax
  unsigned int v15; // edx
  VMX_LOG *v16; // rcx
  struct _KEVENT Event; // [rsp+30h] [rbp-58h] BYREF

  v2 = (VMX_LOG *)*((_QWORD *)this + 3);
  memset(&Event, 0, sizeof(Event));
  if ( !v2 )
    return;
  VMX_LOG::Acquire(v2);
  v3 = (VMX_LOG *)*((_QWORD *)this + 3);
  if ( !*((_BYTE *)v3 + 96) )
    goto LABEL_31;
  v4 = 0;
  v5 = (_QWORD *)(*((_QWORD *)this + 2) + 16LL);
  v6 = (_QWORD *)*v5;
  if ( (_QWORD *)*v5 == v5 )
    goto LABEL_28;
  do
  {
    v7 = 0;
    switch ( *((_WORD *)v6 + 16) )
    {
      case 1:
        v13 = *((_WORD *)v6 + 32);
        if ( (v13 & 8) == 0 )
        {
          if ( (v13 & 0x14) != 0x10 || !*(_QWORD *)(v6[5] + 248LL) )
            goto LABEL_25;
          v12 = *(_QWORD *)(v6[6] + 248LL) == 0;
LABEL_19:
          if ( !v12 )
            goto LABEL_25;
        }
        break;
      case 2:
        v8 = *((_WORD *)v6 + 32);
        if ( (v8 & 8) == 0 )
        {
          v9 = *(_QWORD *)(v6[(v8 & 1) + 5] + 136LL);
          if ( (*(_BYTE *)(v9 + 64) & 0x14) != 0x10 )
            goto LABEL_25;
          v10 = *(_QWORD **)(*(_QWORD *)(v9 + 40) + 248LL);
          if ( !v10 || !(*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)*v10 + 208LL))(*v10, v6[3], 0) )
            goto LABEL_25;
          v11 = *(_QWORD **)(*(_QWORD *)(v9 + 48) + 248LL);
          if ( !v11 )
            break;
          v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)*v11 + 208LL))(*v11, v6[3], 0) == 0;
          goto LABEL_19;
        }
        v7 = 1;
        break;
      case 3:
        v7 = (v6[8] & 8) != 0;
        goto LABEL_22;
      default:
        goto LABEL_25;
    }
    if ( VMX_LOG::RemoveEntryDirty(*((VMX_LOG **)this + 3), v6[3]) )
      v4 = 1;
LABEL_22:
    if ( v7 && VMX_LOG::RemoveEntryDetach(*((VMX_LOG **)this + 3), v6[3]) )
      v4 = 1;
LABEL_25:
    v6 = (_QWORD *)*v6;
  }
  while ( v6 != (_QWORD *)(*((_QWORD *)this + 2) + 16LL) );
  if ( v4 )
  {
    KeInitializeEvent(&Event, NotificationEvent, 0);
    VMX_LOG::Flush(*((VMX_LOG **)this + 3), 0, 0, (void (*)(void *, int))VmxpSynchLogFlushCompletion, &Event);
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
  }
LABEL_28:
  VMX_PACK::QueryRequiredLogBlocksCount(this, 1u);
  BlocksCount = VMX_LOG::QueryBlocksCount(*((VMX_LOG **)this + 3));
  if ( v15 < BlocksCount )
    VMX_LOG::SetBlocksCount(v16, v15);
  v3 = (VMX_LOG *)*((_QWORD *)this + 3);
LABEL_31:
  VMX_LOG::Release(v3);
}

```

## disassembly

```asm
0x14002a920  push    rbx
0x14002a922  push    rbp
0x14002a923  push    rsi
0x14002a924  push    rdi
0x14002a925  push    r12
0x14002a927  push    r14
0x14002a929  sub     rsp, 58h
0x14002a92d  xor     eax, eax
0x14002a92f  mov     rdi, rcx
0x14002a932  mov     rcx, [rcx+18h]; this
0x14002a936  xorps   xmm0, xmm0
0x14002a939  mov     [rsp+88h+Event.Header.WaitListHead.Blink], rax
0x14002a93e  movups  xmmword ptr [rsp+88h+Event.Header], xmm0
0x14002a943  test    rcx, rcx
0x14002a946  jz      loc_14002AB30
0x14002a94c  call    ?Acquire@VMX_LOG@@QEAAXXZ; VMX_LOG::Acquire(void)
0x14002a951  mov     rcx, [rdi+18h]
0x14002a955  cmp     byte ptr [rcx+60h], 0
0x14002a959  jz      loc_14002AB2B
0x14002a95f  mov     rax, [rdi+10h]
0x14002a963  xor     bpl, bpl
0x14002a966  add     rax, 10h
0x14002a96a  mov     r12d, 1
0x14002a970  mov     rbx, [rax]
0x14002a973  cmp     rbx, rax
0x14002a976  jz      loc_14002AB08
0x14002a97c  movzx   ecx, word ptr [rbx+20h]
0x14002a980  xor     sil, sil
0x14002a983  sub     ecx, r12d
0x14002a986  jz      loc_14002AA3B
0x14002a98c  sub     ecx, r12d
0x14002a98f  jz      short loc_14002A9AA
0x14002a991  cmp     ecx, r12d
0x14002a994  jnz     loc_14002AA98
0x14002a99a  mov     sil, [rbx+40h]
0x14002a99e  shr     sil, 3
0x14002a9a2  and     sil, r12b
0x14002a9a5  jmp     loc_14002AA7C
0x14002a9aa  movzx   eax, word ptr [rbx+40h]
0x14002a9ae  test    al, 8
0x14002a9b0  jz      short loc_14002A9BA
0x14002a9b2  mov     sil, r12b
0x14002a9b5  jmp     loc_14002AA65
0x14002a9ba  and     rax, r12
0x14002a9bd  mov     rax, [rbx+rax*8+28h]
0x14002a9c2  mov     r14, [rax+88h]
0x14002a9c9  mov     al, [r14+40h]
0x14002a9cd  and     al, 14h
0x14002a9cf  cmp     al, 10h
0x14002a9d1  jnz     loc_14002AA98
0x14002a9d7  mov     rax, [r14+28h]
0x14002a9db  mov     rcx, [rax+0F8h]
0x14002a9e2  test    rcx, rcx
0x14002a9e5  jz      loc_14002AA98
0x14002a9eb  mov     rcx, [rcx]
0x14002a9ee  xor     r8d, r8d
0x14002a9f1  mov     rdx, [rbx+18h]
0x14002a9f5  mov     rax, [rcx]
0x14002a9f8  mov     rax, [rax+0D0h]
0x14002a9ff  call    _guard_dispatch_icall
0x14002aa04  test    rax, rax
0x14002aa07  jz      loc_14002AA98
0x14002aa0d  mov     rax, [r14+30h]
0x14002aa11  mov     rcx, [rax+0F8h]
0x14002aa18  test    rcx, rcx
0x14002aa1b  jz      short loc_14002AA65
0x14002aa1d  mov     rcx, [rcx]
0x14002aa20  xor     r8d, r8d
0x14002aa23  mov     rdx, [rbx+18h]
0x14002aa27  mov     rax, [rcx]
0x14002aa2a  mov     rax, [rax+0D0h]
0x14002aa31  call    _guard_dispatch_icall
0x14002aa36  test    rax, rax
0x14002aa39  jmp     short loc_14002AA63
0x14002aa3b  movzx   eax, word ptr [rbx+40h]
0x14002aa3f  test    al, 8
0x14002aa41  jnz     short loc_14002AA65
0x14002aa43  and     al, 14h
0x14002aa45  cmp     al, 10h
0x14002aa47  jnz     short loc_14002AA98
0x14002aa49  mov     rax, [rbx+28h]
0x14002aa4d  cmp     qword ptr [rax+0F8h], 0
0x14002aa55  jz      short loc_14002AA98
0x14002aa57  mov     rax, [rbx+30h]
0x14002aa5b  cmp     qword ptr [rax+0F8h], 0
0x14002aa63  jnz     short loc_14002AA98
0x14002aa65  mov     rdx, [rbx+18h]; unsigned __int64
0x14002aa69  mov     rcx, [rdi+18h]; this
0x14002aa6d  call    ?RemoveEntryDirty@VMX_LOG@@QEAAE_K@Z; VMX_LOG::RemoveEntryDirty(unsigned __int64)
0x14002aa72  test    al, al
0x14002aa74  movzx   ebp, bpl
0x14002aa78  cmovnz  ebp, r12d
0x14002aa7c  test    sil, sil
0x14002aa7f  jz      short loc_14002AA98
0x14002aa81  mov     rdx, [rbx+18h]; unsigned __int64
0x14002aa85  mov     rcx, [rdi+18h]; this
0x14002aa89  call    ?RemoveEntryDetach@VMX_LOG@@QEAAE_K@Z; VMX_LOG::RemoveEntryDetach(unsigned __int64)
0x14002aa8e  test    al, al
0x14002aa90  movzx   ebp, bpl
0x14002aa94  cmovnz  ebp, r12d
0x14002aa98  mov     rax, [rdi+10h]
0x14002aa9c  mov     rbx, [rbx]
0x14002aa9f  add     rax, 10h
0x14002aaa3  cmp     rbx, rax
0x14002aaa6  jnz     loc_14002A97C
0x14002aaac  test    bpl, bpl
0x14002aaaf  jz      short loc_14002AB08
0x14002aab1  xor     r8d, r8d; State
0x14002aab4  lea     rcx, [rsp+88h+Event]; Event
0x14002aab9  xor     edx, edx; Type
0x14002aabb  call    cs:__imp_KeInitializeEvent
0x14002aac2  nop     dword ptr [rax+rax+00h]
0x14002aac7  mov     rcx, [rdi+18h]; this
0x14002aacb  lea     rax, [rsp+88h+Event]
0x14002aad0  lea     r9, ?VmxpSynchLogFlushCompletion@@YAXPEAXJ@Z; void (*)(void *, int)
0x14002aad7  mov     [rsp+88h+Timeout], rax; void *
0x14002aadc  xor     r8d, r8d; unsigned __int8
0x14002aadf  xor     edx, edx; struct VMX_LOG_COPY *
0x14002aae1  call    ?Flush@VMX_LOG@@QEAAXPEAVVMX_LOG_COPY@@EP6AXPEAXJ@Z1@Z; VMX_LOG::Flush(VMX_LOG_COPY *,uchar,void (*)(void *,long),void *)
0x14002aae6  xor     r9d, r9d; Alertable
0x14002aae9  mov     [rsp+88h+Timeout], 0; Timeout
0x14002aaf2  xor     r8d, r8d; WaitMode
0x14002aaf5  lea     rcx, [rsp+88h+Event]; Object
0x14002aafa  xor     edx, edx; WaitReason
0x14002aafc  call    cs:__imp_KeWaitForSingleObject
0x14002ab03  nop     dword ptr [rax+rax+00h]
0x14002ab08  mov     dl, r12b; unsigned __int8
0x14002ab0b  mov     rcx, rdi; this
0x14002ab0e  call    ?QueryRequiredLogBlocksCount@VMX_PACK@@AEAAKE@Z; VMX_PACK::QueryRequiredLogBlocksCount(uchar)
0x14002ab13  mov     rcx, [rdi+18h]; this
0x14002ab17  mov     edx, eax
0x14002ab19  call    ?QueryBlocksCount@VMX_LOG@@QEAAKXZ; VMX_LOG::QueryBlocksCount(void)
0x14002ab1e  cmp     edx, eax
0x14002ab20  jnb     short loc_14002AB27
0x14002ab22  call    ?SetBlocksCount@VMX_LOG@@QEAAJK@Z; VMX_LOG::SetBlocksCount(ulong)
0x14002ab27  mov     rcx, [rdi+18h]; this
0x14002ab2b  call    ?Release@VMX_LOG@@QEAAXXZ; VMX_LOG::Release(void)
0x14002ab30  add     rsp, 58h
0x14002ab34  pop     r14
0x14002ab36  pop     r12
0x14002ab38  pop     rdi
0x14002ab39  pop     rsi
0x14002ab3a  pop     rbp
0x14002ab3b  pop     rbx
0x14002ab3c  retn
```
