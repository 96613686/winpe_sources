# VhdmpiSrbPartContinueComplete

- ea: `0x140010c70`
- end: `0x140010e58`
- name: `VhdmpiSrbPartContinueComplete`
- size: `488`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400078f0`
- `0x140011e90`
- `0x140015db8`

## callees

- `0x140010c70`
- `0x140010f40`
- `0x140011e90`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140010e47`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140010e47`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010c9c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010c9c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010ce1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010ce1`

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
0x140010c70  mov     [rsp+arg_0], rbx
0x140010c75  mov     [rsp+arg_8], rsi
0x140010c7a  push    rdi
0x140010c7b  sub     rsp, 30h
0x140010c7f  xorps   xmm0, xmm0
0x140010c82  mov     rbx, rcx
0x140010c85  movups  [rsp+38h+var_18], xmm0
0x140010c8a  test    edx, edx
0x140010c8c  jns     loc_140010D2E
0x140010c92  mov     rdi, [rbx]
0x140010c95  lea     rcx, [rdi+0A8h]; SpinLock
0x140010c9c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140010ca3  nop     dword ptr [rax+rax+00h]
0x140010ca8  mov     r9, [rbx+8]
0x140010cac  lea     rdx, [rbx+8]
0x140010cb0  cmp     [r9+8], rdx
0x140010cb4  jnz     loc_140010D98
0x140010cba  mov     r8, [rdx+8]
0x140010cbe  cmp     [r8], rdx
0x140010cc1  jnz     loc_140010D98
0x140010cc7  mov     [r8], r9
0x140010cca  xor     ecx, ecx
0x140010ccc  mov     [r9+8], r8
0x140010cd0  mov     [rdx], rcx
0x140010cd3  mov     [rdx+8], rcx
0x140010cd7  movzx   edx, al; NewIrql
0x140010cda  lea     rcx, [rdi+0A8h]; SpinLock
0x140010ce1  call    cs:__imp_KeReleaseSpinLock
0x140010ce8  nop     dword ptr [rax+rax+00h]
0x140010ced  mov     rcx, [rbx+18h]
0x140010cf1  lea     rax, [rbx+18h]
0x140010cf5  test    rcx, rcx
0x140010cf8  jnz     loc_140010D9F
0x140010cfe  cmp     [rax+8], rcx
0x140010d02  jnz     loc_140010D9F
0x140010d08  mov     rcx, [rbx+30h]
0x140010d0c  test    rcx, rcx
0x140010d0f  jnz     loc_140010E3D
0x140010d15  mov     rcx, rdi
0x140010d18  call    VhdmpiDecrementIoRefCountSrbExtension
0x140010d1d  mov     rbx, [rsp+38h+arg_0]
0x140010d22  mov     rsi, [rsp+38h+arg_8]
0x140010d27  add     rsp, 30h
0x140010d2b  pop     rdi
0x140010d2c  retn
0x140010d2e  cmp     byte ptr [rcx+6Eh], 0
0x140010d32  jz      loc_140010DEF
0x140010d38  mov     rax, [rcx+28h]
0x140010d3c  mov     rcx, [rax+478h]
0x140010d43  lea     rax, [rbx+18h]
0x140010d47  mov     [rbx+28h], rcx
0x140010d4b  mov     word ptr [rbx+6Eh], 0
0x140010d51  mov     rcx, [rax]
0x140010d54  test    r8, r8
0x140010d57  jz      short loc_140010DA9
0x140010d59  test    rcx, rcx
0x140010d5c  jnz     short loc_140010D8F
0x140010d5e  cmp     [rax+8], rcx
0x140010d62  lea     rbx, [rax+8]
0x140010d66  jnz     short loc_140010D93
0x140010d68  mov     rcx, [r8+8]
0x140010d6c  cmp     [rcx], r8
0x140010d6f  jnz     short loc_140010D98
0x140010d71  mov     [rax], r8
0x140010d74  mov     [rbx], rcx
0x140010d77  mov     [rcx], rax
0x140010d7a  mov     [r8+8], rax
0x140010d7e  mov     rbx, [rsp+38h+arg_0]
0x140010d83  mov     rsi, [rsp+38h+arg_8]
0x140010d88  add     rsp, 30h
0x140010d8c  pop     rdi
0x140010d8d  retn
0x140010d8f  add     rbx, 20h ; ' '
0x140010d93  cmp     rcx, rax
0x140010d96  jz      short loc_140010D68
0x140010d98  mov     ecx, 3
0x140010d9d  int     29h; Win8: RtlFailFast(ecx)
0x140010d9f  cmp     rcx, rax
0x140010da2  jnz     short loc_140010D98
0x140010da4  jmp     loc_140010D08
0x140010da9  test    rcx, rcx
0x140010dac  jnz     short loc_140010E20
0x140010dae  cmp     [rax+8], rcx
0x140010db2  lea     rbx, [rax+8]
0x140010db6  jnz     short loc_140010E24
0x140010db8  lea     rcx, [rsp+38h+var_18]
0x140010dbd  mov     qword ptr [rsp+38h+var_18], rax
0x140010dc2  mov     [rax], rcx
0x140010dc5  xor     edx, edx
0x140010dc7  lea     rcx, [rsp+38h+var_18]
0x140010dcc  mov     qword ptr [rsp+38h+var_18+8], rax
0x140010dd1  mov     [rbx], rcx
0x140010dd4  lea     rcx, [rsp+38h+var_18]
0x140010dd9  call    VhdmpiProcessParseThreadContext
0x140010dde  mov     rbx, [rsp+38h+arg_0]
0x140010de3  mov     rsi, [rsp+38h+arg_8]
0x140010de8  add     rsp, 30h
0x140010dec  pop     rdi
0x140010ded  retn
0x140010def  mov     rdx, [rcx]
0x140010df2  test    dword ptr [rdx+40h], 100h
0x140010df9  jz      loc_140010C92
0x140010dff  cmp     byte ptr [rcx+6Ch], 0
0x140010e03  jnz     short loc_140010E2F
0x140010e05  cmp     byte ptr [rcx+6Dh], 0
0x140010e09  jnz     loc_140010C92
0x140010e0f  mov     ecx, [rcx+60h]
0x140010e12  sub     ecx, [rdx+20h]
0x140010e15  add     ecx, [rbx+58h]
0x140010e18  mov     [rdx+38h], ecx
0x140010e1b  jmp     loc_140010C92
0x140010e20  add     rbx, 20h ; ' '
0x140010e24  cmp     rcx, rax
0x140010e27  jnz     loc_140010D98
0x140010e2d  jmp     short loc_140010DB8
0x140010e2f  mov     eax, [rcx+68h]
0x140010e32  add     eax, [rcx+64h]
0x140010e35  mov     [rdx+38h], eax
0x140010e38  jmp     loc_140010C92
0x140010e3d  add     rcx, 600h; Lookaside
0x140010e44  mov     rdx, rbx; Entry
0x140010e47  call    cs:__imp_ExFreeToNPagedLookasideList
0x140010e4e  nop     dword ptr [rax+rax+00h]
0x140010e53  jmp     loc_140010D15
```
