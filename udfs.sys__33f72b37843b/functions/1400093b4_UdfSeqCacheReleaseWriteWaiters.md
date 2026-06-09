# UdfSeqCacheReleaseWriteWaiters

- ea: `0x1400093b4`
- end: `0x140009447`
- name: `UdfSeqCacheReleaseWriteWaiters`
- size: `147`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140006680`
- `0x14000cce0`
- `0x14001ac8c`

## callees

- `0x1400093b4`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140009427`
- `ntoskrnl!KeSetEvent` at `0x140009427`

## pseudocode

```c
void __fastcall UdfSeqCacheReleaseWriteWaiters(__int64 a1, unsigned int a2, __int64 a3, int a4, char a5)
{
  __int64 *v5; // rdi
  __int64 *v7; // rbx
  __int64 *v10; // rax
  __int64 **v11; // rdx
  __int64 *v12; // rcx

  v5 = (__int64 *)(a1 + 624);
  v7 = *(__int64 **)(a1 + 624);
  while ( v7 != v5 )
  {
    if ( a2 != -1 && *((_DWORD *)v7 + 10) <= a2 && (a5 || !*((_BYTE *)v7 + 56)) || a3 == v7[6] )
    {
      v10 = (__int64 *)*v7;
      if ( *(__int64 **)(*v7 + 8) != v7 || (v11 = (__int64 **)v7[1], *v11 != v7) )
        __fastfail(3u);
      *v11 = v10;
      v12 = v7;
      v10[1] = (__int64)v11;
      v7 = (__int64 *)*v7;
      *((_DWORD *)v12 + 11) = a4;
      KeSetEvent((PRKEVENT)(v12 + 2), 1, 0);
    }
    else
    {
      v7 = (__int64 *)*v7;
    }
  }
}

```

## disassembly

```asm
0x1400093b4  push    rbx
0x1400093b6  push    rbp
0x1400093b7  push    rsi
0x1400093b8  push    rdi
0x1400093b9  push    r14
0x1400093bb  sub     rsp, 20h
0x1400093bf  lea     rdi, [rcx+270h]
0x1400093c6  mov     r14d, r9d
0x1400093c9  mov     rbx, [rdi]
0x1400093cc  mov     rbp, r8
0x1400093cf  mov     esi, edx
0x1400093d1  cmp     rbx, rdi
0x1400093d4  jnz     short loc_1400093E2
0x1400093d6  add     rsp, 20h
0x1400093da  pop     r14
0x1400093dc  pop     rdi
0x1400093dd  pop     rsi
0x1400093de  pop     rbp
0x1400093df  pop     rbx
0x1400093e0  retn
0x1400093e2  cmp     esi, 0FFFFFFFFh
0x1400093e5  jz      short loc_140009435
0x1400093e7  cmp     [rbx+28h], esi
0x1400093ea  ja      short loc_140009435
0x1400093ec  cmp     [rsp+48h+arg_20], 0
0x1400093f1  jnz     short loc_1400093F9
0x1400093f3  cmp     byte ptr [rbx+38h], 0
0x1400093f7  jnz     short loc_140009435
0x1400093f9  mov     rax, [rbx]
0x1400093fc  cmp     [rax+8], rbx
0x140009400  jnz     short loc_140009440
0x140009402  mov     rdx, [rbx+8]
0x140009406  cmp     [rdx], rbx
0x140009409  jnz     short loc_140009440
0x14000940b  mov     [rdx], rax
0x14000940e  mov     rcx, rbx
0x140009411  mov     [rax+8], rdx
0x140009415  xor     r8d, r8d; Wait
0x140009418  mov     rbx, [rbx]
0x14000941b  mov     [rcx+2Ch], r14d
0x14000941f  add     rcx, 10h; Event
0x140009423  lea     edx, [r8+1]; Increment
0x140009427  call    cs:__imp_KeSetEvent
0x14000942e  nop     dword ptr [rax+rax+00h]
0x140009433  jmp     short loc_1400093D1
0x140009435  cmp     rbp, [rbx+30h]
0x140009439  jz      short loc_1400093F9
0x14000943b  mov     rbx, [rbx]
0x14000943e  jmp     short loc_1400093D1
0x140009440  mov     ecx, 3
0x140009445  int     29h; Win8: RtlFailFast(ecx)
```
