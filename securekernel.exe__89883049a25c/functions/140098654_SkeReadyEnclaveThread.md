# SkeReadyEnclaveThread

- ea: `0x140098654`
- end: `0x140098783`
- name: `SkeReadyEnclaveThread`
- size: `303`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `9`
- tags: ``

## callers

- `0x14006b7a8`
- `0x1400b04d8`
- `0x1400b0ee8`

## callees

- `0x1400010f0`
- `0x140002410`
- `0x140002e40`
- `0x1400202b0`
- `0x140029308`
- `0x14003acd8`
- `0x140098654`
- `0x1400bb844`
- `0x1400f2f80`

## pseudocode

```c
__int64 __fastcall SkeReadyEnclaveThread(__int64 a1, char a2)
{
  __int64 result; // rax
  __int64 v4; // rsi
  __int64 v5; // rbx
  unsigned __int8 CurrentIrql; // di
  __int64 v7; // rdx
  __int64 v8; // rcx
  _QWORD *v9; // r8
  __int64 v10; // rdx
  _QWORD *v11; // rcx
  __int64 *v12; // rdx

  result = *(unsigned int *)(a1 + 172);
  v4 = *(_QWORD *)(a1 + 72);
  v5 = a1;
  if ( (result & 2) != 0 )
  {
    CurrentIrql = KeGetCurrentIrql();
  }
  else
  {
    CurrentIrql = SkAcquireSpinLockExclusive(v4 + 4);
    SkeDisableInterrupts();
    SkAcquireSpinLockExclusiveAtDpcLevel(v4 + 216);
    v8 = *(unsigned int *)(v5 + 172);
    if ( (v8 & 2) == 0 )
    {
      _InterlockedOr((volatile signed __int32 *)(v5 + 172), 0x400u);
      _InterlockedAnd((volatile signed __int32 *)(v5 + 172), 0xFFFFDFFF);
      if ( a2 )
      {
        v7 = v4 + 32;
        v9 = *(_QWORD **)(v4 + 40);
        if ( *v9 != v4 + 32 )
          goto LABEL_12;
        *(_QWORD *)(v5 + 48) = v7;
        *(_QWORD *)(v5 + 56) = v9;
        *v9 = v5 + 48;
        *(_QWORD *)(v4 + 40) = v5 + 48;
      }
      v5 = 0;
    }
    *(_DWORD *)(v4 + 216) = 0;
    SkTrackSpinLockRelease(v8, v7);
    _enable();
    LOBYTE(v10) = CurrentIrql;
    result = SkReleaseSpinLockExclusive(v4 + 4, v10);
  }
  if ( v5 )
  {
    if ( CurrentIrql == 2 )
    {
      SkAcquireSpinLockExclusiveAtDpcLevel(&SkiThreadReaperLock);
      v11 = (_QWORD *)qword_14014EDE8;
      v12 = &SkiDeferredEnclaveThreadList;
      if ( *(__int64 **)qword_14014EDE8 != &SkiDeferredEnclaveThreadList )
LABEL_12:
        __fastfail(3u);
      *(_QWORD *)(v5 + 48) = &SkiDeferredEnclaveThreadList;
      *(_QWORD *)(v5 + 56) = v11;
      *v11 = v5 + 48;
      qword_14014EDE8 = v5 + 48;
      if ( !SkiThreadReaperWorkItem )
        SkQueueWorkItem(&SkiThreadReaperWorkItem);
      SkiThreadReaperLock = 0;
      SkTrackSpinLockRelease(v11, v12);
      return SkRequestWorkCallback();
    }
    else
    {
      return SkpsDeleteEnclaveThread(v5);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140098654  push    rbx
0x140098656  push    rbp
0x140098657  push    rsi
0x140098658  push    rdi
0x140098659  push    r14
0x14009865b  sub     rsp, 20h
0x14009865f  mov     eax, [rcx+0ACh]
0x140098665  mov     bpl, dl
0x140098668  mov     rsi, [rcx+48h]
0x14009866c  mov     rbx, rcx
0x14009866f  test    al, 2
0x140098671  jnz     loc_1400986F9
0x140098677  lea     rcx, [rsi+4]
0x14009867b  call    SkAcquireSpinLockExclusive
0x140098680  mov     dil, al
0x140098683  call    SkeDisableInterrupts
0x140098688  lea     rcx, [rsi+0D8h]
0x14009868f  call    SkAcquireSpinLockExclusiveAtDpcLevel
0x140098694  mov     ecx, [rbx+0ACh]
0x14009869a  test    cl, 2
0x14009869d  jnz     short loc_1400986DB
0x14009869f  lock or dword ptr [rbx+0ACh], 400h
0x1400986aa  lock and dword ptr [rbx+0ACh], 0FFFFDFFFh
0x1400986b5  test    bpl, bpl
0x1400986b8  jz      short loc_1400986D9
0x1400986ba  lea     rdx, [rsi+20h]
0x1400986be  mov     r8, [rdx+8]
0x1400986c2  cmp     [r8], rdx
0x1400986c5  jnz     short loc_140098727
0x1400986c7  lea     rax, [rbx+30h]
0x1400986cb  mov     [rax], rdx
0x1400986ce  mov     [rax+8], r8
0x1400986d2  mov     [r8], rax
0x1400986d5  mov     [rdx+8], rax
0x1400986d9  xor     ebx, ebx
0x1400986db  mov     dword ptr [rsi+0D8h], 0
0x1400986e5  call    SkTrackSpinLockRelease
0x1400986ea  sti
0x1400986eb  mov     dl, dil
0x1400986ee  lea     rcx, [rsi+4]
0x1400986f2  call    SkReleaseSpinLockExclusive
0x1400986f7  jmp     short loc_1400986FD
0x1400986f9  mov     rdi, cr8
0x1400986fd  test    rbx, rbx
0x140098700  jz      short loc_140098777
0x140098702  cmp     dil, 2
0x140098706  jnz     short loc_14009876F
0x140098708  lea     rcx, SkiThreadReaperLock
0x14009870f  call    SkAcquireSpinLockExclusiveAtDpcLevel
0x140098714  mov     rcx, cs:qword_14014EDE8
0x14009871b  lea     rdx, SkiDeferredEnclaveThreadList
0x140098722  cmp     [rcx], rdx
0x140098725  jz      short loc_14009872E
0x140098727  mov     ecx, 3
0x14009872c  int     29h; Win8: RtlFailFast(ecx)
0x14009872e  lea     rax, [rbx+30h]
0x140098732  mov     [rax], rdx
0x140098735  mov     [rax+8], rcx
0x140098739  mov     [rcx], rax
0x14009873c  cmp     cs:SkiThreadReaperWorkItem, 0
0x140098744  mov     cs:qword_14014EDE8, rax
0x14009874b  jnz     short loc_140098759
0x14009874d  lea     rcx, SkiThreadReaperWorkItem
0x140098754  call    SkQueueWorkItem
0x140098759  mov     cs:SkiThreadReaperLock, 0
0x140098763  call    SkTrackSpinLockRelease
0x140098768  call    SkRequestWorkCallback
0x14009876d  jmp     short loc_140098777
0x14009876f  mov     rcx, rbx
0x140098772  call    SkpsDeleteEnclaveThread
0x140098777  add     rsp, 20h
0x14009877b  pop     r14
0x14009877d  pop     rdi
0x14009877e  pop     rsi
0x14009877f  pop     rbp
0x140098780  pop     rbx
0x140098781  retn
```
