# VhdmpiSrbPartContinueComplete

- ea: `0x14000f8c0`
- end: `0x14000faa8`
- name: `VhdmpiSrbPartContinueComplete`
- size: `488`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400078f0`
- `0x140010b60`
- `0x140015918`

## callees

- `0x14000f8c0`
- `0x14000fb90`
- `0x140010b60`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000fa97`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000fa97`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f8ec`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f8ec`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f931`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f931`

## pseudocode

```c
_QWORD *__fastcall VhdmpiSrbPartContinueComplete(_QWORD *Entry, int a2, __int64 a3)
{
  __int64 v4; // rdi
  KIRQL v5; // al
  __int64 v6; // r9
  _QWORD *v7; // rdx
  _QWORD *v8; // r8
  _QWORD *v9; // rcx
  struct _NPAGED_LOOKASIDE_LIST *v10; // rcx
  _QWORD *result; // rax
  _QWORD *v12; // rcx
  _QWORD *v13; // rbx
  _QWORD *v14; // rcx
  _QWORD *v15; // rbx
  __int64 v16; // rdx
  __int128 v17; // [rsp+20h] [rbp-18h] BYREF

  v17 = 0;
  if ( a2 < 0 )
    goto LABEL_2;
  if ( *((_BYTE *)Entry + 110) )
  {
    result = Entry + 3;
    Entry[5] = *(_QWORD *)(Entry[5] + 1144LL);
    *((_WORD *)Entry + 55) = 0;
    v12 = (_QWORD *)Entry[3];
    if ( a3 )
    {
      if ( v12 )
      {
        v13 = Entry + 4;
      }
      else
      {
        v13 = Entry + 4;
        if ( !result[1] )
        {
LABEL_13:
          v14 = *(_QWORD **)(a3 + 8);
          if ( *v14 == a3 )
          {
            *result = a3;
            *v13 = v14;
            *v14 = result;
            *(_QWORD *)(a3 + 8) = result;
            return result;
          }
LABEL_17:
          __fastfail(3u);
        }
      }
      if ( v12 != result )
        goto LABEL_17;
      goto LABEL_13;
    }
    if ( v12 )
    {
      v15 = Entry + 4;
    }
    else
    {
      v15 = Entry + 4;
      if ( !result[1] )
        goto LABEL_22;
    }
    if ( v12 != result )
      goto LABEL_17;
LABEL_22:
    *(_QWORD *)&v17 = result;
    *result = &v17;
    *((_QWORD *)&v17 + 1) = result;
    *v15 = &v17;
    return (_QWORD *)VhdmpiProcessParseThreadContext(&v17, 0);
  }
  v16 = *Entry;
  if ( (*(_DWORD *)(*Entry + 64LL) & 0x100) != 0 )
  {
    if ( *((_BYTE *)Entry + 108) )
    {
      *(_DWORD *)(v16 + 56) = *((_DWORD *)Entry + 25) + *((_DWORD *)Entry + 26);
    }
    else if ( !*((_BYTE *)Entry + 109) )
    {
      *(_DWORD *)(v16 + 56) = *((_DWORD *)Entry + 22) + *((_DWORD *)Entry + 24) - *(_DWORD *)(v16 + 32);
    }
  }
LABEL_2:
  v4 = *Entry;
  v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(*Entry + 168LL));
  v6 = Entry[1];
  v7 = Entry + 1;
  if ( *(_QWORD **)(v6 + 8) != Entry + 1 )
    goto LABEL_17;
  v8 = (_QWORD *)Entry[2];
  if ( (_QWORD *)*v8 != v7 )
    goto LABEL_17;
  *v8 = v6;
  *(_QWORD *)(v6 + 8) = v8;
  *v7 = 0;
  Entry[2] = 0;
  KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 168), v5);
  v9 = (_QWORD *)Entry[3];
  if ( (v9 || Entry[4]) && v9 != Entry + 3 )
    goto LABEL_17;
  v10 = (struct _NPAGED_LOOKASIDE_LIST *)Entry[6];
  if ( v10 )
    ExFreeToNPagedLookasideList(v10 + 12, Entry);
  return (_QWORD *)VhdmpiDecrementIoRefCountSrbExtension(v4);
}

```

## disassembly

```asm
0x14000f8c0  mov     [rsp+arg_0], rbx
0x14000f8c5  mov     [rsp+arg_8], rsi
0x14000f8ca  push    rdi
0x14000f8cb  sub     rsp, 30h
0x14000f8cf  xorps   xmm0, xmm0
0x14000f8d2  mov     rbx, rcx
0x14000f8d5  movups  [rsp+38h+var_18], xmm0
0x14000f8da  test    edx, edx
0x14000f8dc  jns     loc_14000F97E
0x14000f8e2  mov     rdi, [rbx]
0x14000f8e5  lea     rcx, [rdi+0A8h]; SpinLock
0x14000f8ec  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000f8f3  nop     dword ptr [rax+rax+00h]
0x14000f8f8  mov     r9, [rbx+8]
0x14000f8fc  lea     rdx, [rbx+8]
0x14000f900  cmp     [r9+8], rdx
0x14000f904  jnz     loc_14000F9E8
0x14000f90a  mov     r8, [rdx+8]
0x14000f90e  cmp     [r8], rdx
0x14000f911  jnz     loc_14000F9E8
0x14000f917  mov     [r8], r9
0x14000f91a  xor     ecx, ecx
0x14000f91c  mov     [r9+8], r8
0x14000f920  mov     [rdx], rcx
0x14000f923  mov     [rdx+8], rcx
0x14000f927  movzx   edx, al; NewIrql
0x14000f92a  lea     rcx, [rdi+0A8h]; SpinLock
0x14000f931  call    cs:__imp_KeReleaseSpinLock
0x14000f938  nop     dword ptr [rax+rax+00h]
0x14000f93d  mov     rcx, [rbx+18h]
0x14000f941  lea     rax, [rbx+18h]
0x14000f945  test    rcx, rcx
0x14000f948  jnz     loc_14000F9EF
0x14000f94e  cmp     [rax+8], rcx
0x14000f952  jnz     loc_14000F9EF
0x14000f958  mov     rcx, [rbx+30h]
0x14000f95c  test    rcx, rcx
0x14000f95f  jnz     loc_14000FA8D
0x14000f965  mov     rcx, rdi
0x14000f968  call    VhdmpiDecrementIoRefCountSrbExtension
0x14000f96d  mov     rbx, [rsp+38h+arg_0]
0x14000f972  mov     rsi, [rsp+38h+arg_8]
0x14000f977  add     rsp, 30h
0x14000f97b  pop     rdi
0x14000f97c  retn
0x14000f97e  cmp     byte ptr [rcx+6Eh], 0
0x14000f982  jz      loc_14000FA3F
0x14000f988  mov     rax, [rcx+28h]
0x14000f98c  mov     rcx, [rax+478h]
0x14000f993  lea     rax, [rbx+18h]
0x14000f997  mov     [rbx+28h], rcx
0x14000f99b  mov     word ptr [rbx+6Eh], 0
0x14000f9a1  mov     rcx, [rax]
0x14000f9a4  test    r8, r8
0x14000f9a7  jz      short loc_14000F9F9
0x14000f9a9  test    rcx, rcx
0x14000f9ac  jnz     short loc_14000F9DF
0x14000f9ae  cmp     [rax+8], rcx
0x14000f9b2  lea     rbx, [rax+8]
0x14000f9b6  jnz     short loc_14000F9E3
0x14000f9b8  mov     rcx, [r8+8]
0x14000f9bc  cmp     [rcx], r8
0x14000f9bf  jnz     short loc_14000F9E8
0x14000f9c1  mov     [rax], r8
0x14000f9c4  mov     [rbx], rcx
0x14000f9c7  mov     [rcx], rax
0x14000f9ca  mov     [r8+8], rax
0x14000f9ce  mov     rbx, [rsp+38h+arg_0]
0x14000f9d3  mov     rsi, [rsp+38h+arg_8]
0x14000f9d8  add     rsp, 30h
0x14000f9dc  pop     rdi
0x14000f9dd  retn
0x14000f9df  add     rbx, 20h ; ' '
0x14000f9e3  cmp     rcx, rax
0x14000f9e6  jz      short loc_14000F9B8
0x14000f9e8  mov     ecx, 3
0x14000f9ed  int     29h; Win8: RtlFailFast(ecx)
0x14000f9ef  cmp     rcx, rax
0x14000f9f2  jnz     short loc_14000F9E8
0x14000f9f4  jmp     loc_14000F958
0x14000f9f9  test    rcx, rcx
0x14000f9fc  jnz     short loc_14000FA70
0x14000f9fe  cmp     [rax+8], rcx
0x14000fa02  lea     rbx, [rax+8]
0x14000fa06  jnz     short loc_14000FA74
0x14000fa08  lea     rcx, [rsp+38h+var_18]
0x14000fa0d  mov     qword ptr [rsp+38h+var_18], rax
0x14000fa12  mov     [rax], rcx
0x14000fa15  xor     edx, edx
0x14000fa17  lea     rcx, [rsp+38h+var_18]
0x14000fa1c  mov     qword ptr [rsp+38h+var_18+8], rax
0x14000fa21  mov     [rbx], rcx
0x14000fa24  lea     rcx, [rsp+38h+var_18]
0x14000fa29  call    VhdmpiProcessParseThreadContext
0x14000fa2e  mov     rbx, [rsp+38h+arg_0]
0x14000fa33  mov     rsi, [rsp+38h+arg_8]
0x14000fa38  add     rsp, 30h
0x14000fa3c  pop     rdi
0x14000fa3d  retn
0x14000fa3f  mov     rdx, [rcx]
0x14000fa42  test    dword ptr [rdx+40h], 100h
0x14000fa49  jz      loc_14000F8E2
0x14000fa4f  cmp     byte ptr [rcx+6Ch], 0
0x14000fa53  jnz     short loc_14000FA7F
0x14000fa55  cmp     byte ptr [rcx+6Dh], 0
0x14000fa59  jnz     loc_14000F8E2
0x14000fa5f  mov     ecx, [rcx+60h]
0x14000fa62  sub     ecx, [rdx+20h]
0x14000fa65  add     ecx, [rbx+58h]
0x14000fa68  mov     [rdx+38h], ecx
0x14000fa6b  jmp     loc_14000F8E2
0x14000fa70  add     rbx, 20h ; ' '
0x14000fa74  cmp     rcx, rax
0x14000fa77  jnz     loc_14000F9E8
0x14000fa7d  jmp     short loc_14000FA08
0x14000fa7f  mov     eax, [rcx+68h]
0x14000fa82  add     eax, [rcx+64h]
0x14000fa85  mov     [rdx+38h], eax
0x14000fa88  jmp     loc_14000F8E2
0x14000fa8d  add     rcx, 600h; Lookaside
0x14000fa94  mov     rdx, rbx; Entry
0x14000fa97  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000fa9e  nop     dword ptr [rax+rax+00h]
0x14000faa3  jmp     loc_14000F965
```
