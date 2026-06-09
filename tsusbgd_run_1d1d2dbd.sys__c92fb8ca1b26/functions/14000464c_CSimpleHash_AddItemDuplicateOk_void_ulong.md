# CSimpleHash::AddItemDuplicateOk(void *,ulong *)

- ea: `0x14000464c`
- end: `0x1400046d3`
- name: `?AddItemDuplicateOk@CSimpleHash@@QEAAJPEAXPEAK@Z`
- size: `135`
- prototype: `__int64 __fastcall(CSimpleHash *__hidden this, void *, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140005f20`
- `0x140006160`

## callees

- `0x14000464c`
- `0x140004798`

## pseudocode

```c
__int64 __fastcall CSimpleHash::AddItemDuplicateOk(CSimpleHash *this, void *a2, unsigned int *a3)
{
  _QWORD *v4; // rdi
  __int64 v6; // r9
  bool v7; // zf
  __int64 result; // rax
  unsigned int v9; // edx
  unsigned int v10; // [rsp+30h] [rbp+8h] BYREF

  v4 = (_QWORD *)((char *)this + 8);
  if ( *(_DWORD *)this )
  {
    v6 = 0;
    while ( *(void **)(*v4 + 8 * v6) != a2 )
    {
      v6 = (unsigned int)(v6 + 1);
      if ( (unsigned int)v6 >= *(_DWORD *)this )
        goto LABEL_5;
    }
    if ( a3 )
      *a3 = v6;
    return 0;
  }
LABEL_5:
  v7 = *((_BYTE *)this + 24) == 0;
  v10 = 0;
  if ( !v7 )
    return 3221225473LL;
  result = CSimpleHash::FindEmptySlot(this, &v10);
  if ( (int)result >= 0 )
  {
    v9 = v10;
    *(_QWORD *)(*v4 + 8LL * v10) = a2;
    if ( a3 )
      *a3 = v9;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000464c  mov     [rsp+arg_8], rbx
0x140004651  mov     [rsp+arg_10], rsi
0x140004656  push    rdi
0x140004657  sub     rsp, 20h
0x14000465b  mov     rbx, r8
0x14000465e  lea     rdi, [rcx+8]
0x140004662  mov     r8d, [rcx]
0x140004665  mov     rsi, rdx
0x140004668  test    r8d, r8d
0x14000466b  jz      short loc_140004681
0x14000466d  mov     rdx, [rdi]
0x140004670  xor     r9d, r9d
0x140004673  cmp     [rdx+r9*8], rsi
0x140004677  jz      short loc_140004696
0x140004679  inc     r9d
0x14000467c  cmp     r9d, r8d
0x14000467f  jb      short loc_140004673
0x140004681  cmp     byte ptr [rcx+18h], 0
0x140004685  mov     [rsp+28h+arg_0], 0
0x14000468d  jz      short loc_1400046A0
0x14000468f  mov     eax, 0C0000001h
0x140004694  jmp     short loc_1400046C2
0x140004696  test    rbx, rbx
0x140004699  jz      short loc_1400046C0
0x14000469b  mov     [rbx], r9d
0x14000469e  jmp     short loc_1400046C0
0x1400046a0  lea     rdx, [rsp+28h+arg_0]; unsigned int *
0x1400046a5  call    ?FindEmptySlot@CSimpleHash@@AEAAJPEAK@Z; CSimpleHash::FindEmptySlot(ulong *)
0x1400046aa  test    eax, eax
0x1400046ac  js      short loc_1400046C2
0x1400046ae  mov     edx, [rsp+28h+arg_0]
0x1400046b2  mov     rax, [rdi]
0x1400046b5  mov     [rax+rdx*8], rsi
0x1400046b9  test    rbx, rbx
0x1400046bc  jz      short loc_1400046C0
0x1400046be  mov     [rbx], edx
0x1400046c0  xor     eax, eax
0x1400046c2  mov     rbx, [rsp+28h+arg_8]
0x1400046c7  mov     rsi, [rsp+28h+arg_10]
0x1400046cc  add     rsp, 20h
0x1400046d0  pop     rdi
0x1400046d1  retn
```
