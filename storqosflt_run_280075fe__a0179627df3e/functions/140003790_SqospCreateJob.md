# SqospCreateJob

- ea: `0x140003790`
- end: `0x14000385e`
- name: `SqospCreateJob`
- size: `206`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1400142c0`
- `0x140014950`

## callees

- `0x140003790`
- `0x140004910`
- `0x140009240`

## import_xrefs

- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400037cf`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400037cf`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x140003811`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x140003811`
- `FLTMGR!FltReleasePushLockEx` at `0x140003837`
- `FLTMGR!FltReleasePushLockEx` at `0x140003837`

## pseudocode

```c
_QWORD *__fastcall SqospCreateJob(__int64 a1, _QWORD *a2)
{
  int LockArray_high; // esi
  __int64 v5; // rcx
  __int64 v6; // rbx
  _QWORD *result; // rax
  _QWORD *v8; // rbx
  __int64 v9; // rcx

  LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
  v5 = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 144LL);
  v6 = v5 + ((unsigned __int64)(unsigned int)(LockArray_high + 1) << 7);
  if ( !*(_BYTE *)(v6 + 176) )
    PplpLazyInitializeLookasideList(v5, v6 + 64);
  result = ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v6 + 64));
  v8 = result;
  if ( result )
  {
    memset(result, 0, 0xC0u);
    v8[4] = a1;
    *v8 = a2;
    *((_DWORD *)v8 + 30) = LockArray_high;
    a2[7] = 0;
    a2[6] = 0;
    a2[8] = v8;
    FltAcquirePushLockSharedEx(v8[4], 0);
    _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(v8[4] + 16LL) + 12LL));
    v9 = v8[4];
    v8[5] = *(_QWORD *)(v9 + 24);
    FltReleasePushLockEx(v9, 0);
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x140003790  push    rbx
0x140003792  push    rbp
0x140003793  push    rsi
0x140003794  push    rdi
0x140003795  sub     rsp, 28h
0x140003799  mov     esi, gs:1A4h
0x1400037a1  mov     rdi, rcx
0x1400037a4  mov     rax, [rcx+8]
0x1400037a8  mov     rbp, rdx
0x1400037ab  lea     ebx, [rsi+1]
0x1400037ae  mov     rcx, [rax+90h]
0x1400037b5  shl     rbx, 7
0x1400037b9  add     rbx, rcx
0x1400037bc  movzx   eax, byte ptr [rbx+0B0h]
0x1400037c3  test    al, al
0x1400037c5  jz      loc_140003850
0x1400037cb  lea     rcx, [rbx+40h]; Lookaside
0x1400037cf  call    cs:__imp_ExAllocateFromLookasideListEx
0x1400037d6  nop     dword ptr [rax+rax+00h]
0x1400037db  mov     rbx, rax
0x1400037de  test    rax, rax
0x1400037e1  jz      short loc_140003846
0x1400037e3  xor     edx, edx; Val
0x1400037e5  mov     r8d, 0C0h; Size
0x1400037eb  mov     rcx, rax; void *
0x1400037ee  call    memset
0x1400037f3  mov     [rbx+20h], rdi
0x1400037f7  xor     eax, eax
0x1400037f9  mov     [rbx], rbp
0x1400037fc  xor     edx, edx
0x1400037fe  mov     [rbx+78h], esi
0x140003801  mov     [rbp+38h], rax
0x140003805  mov     [rbp+30h], rax
0x140003809  mov     [rbp+40h], rbx
0x14000380d  mov     rcx, [rbx+20h]
0x140003811  call    cs:__imp_FltAcquirePushLockSharedEx
0x140003818  nop     dword ptr [rax+rax+00h]
0x14000381d  mov     rax, [rbx+20h]
0x140003821  mov     rcx, [rax+10h]
0x140003825  lock inc dword ptr [rcx+0Ch]
0x140003829  mov     rcx, [rbx+20h]
0x14000382d  xor     edx, edx
0x14000382f  mov     rax, [rcx+18h]
0x140003833  mov     [rbx+28h], rax
0x140003837  call    cs:__imp_FltReleasePushLockEx
0x14000383e  nop     dword ptr [rax+rax+00h]
0x140003843  mov     rax, rbx
0x140003846  add     rsp, 28h
0x14000384a  pop     rdi
0x14000384b  pop     rsi
0x14000384c  pop     rbp
0x14000384d  pop     rbx
0x14000384e  retn
0x140003850  lea     rdx, [rbx+40h]
0x140003854  call    PplpLazyInitializeLookasideList
0x140003859  jmp     loc_1400037CB
```
