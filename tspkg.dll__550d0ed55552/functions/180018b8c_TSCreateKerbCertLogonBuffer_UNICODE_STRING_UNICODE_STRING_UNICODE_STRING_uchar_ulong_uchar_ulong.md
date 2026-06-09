# TSCreateKerbCertLogonBuffer(_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,uchar *,ulong,uchar * *,ulong *)

- ea: `0x180018b8c`
- end: `0x180018cf2`
- name: `?TSCreateKerbCertLogonBuffer@@YAJPEAU_UNICODE_STRING@@00PEAEKPEAPEAEPEAK@Z`
- size: `358`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, unsigned __int8 *, size_t Size, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001449c`

## callees

- `0x1800032c0`
- `0x180018b8c`
- `0x18001c63c`

## pseudocode

```c
__int64 __fastcall TSCreateKerbCertLogonBuffer(
        struct _UNICODE_STRING *a1,
        struct _UNICODE_STRING *a2,
        struct _UNICODE_STRING *a3,
        unsigned __int8 *a4,
        size_t Size,
        unsigned __int8 **a6,
        unsigned int *a7)
{
  unsigned int v10; // r11d
  unsigned int v11; // ebp
  unsigned int v12; // esi
  _WORD *v13; // rax
  _WORD *v14; // rdi
  char *v15; // rbx
  void *v16; // rcx
  USHORT Length; // ax
  char *v18; // rbx
  char *v19; // rbx
  __int64 v20; // rcx
  char *v21; // rcx

  v10 = (a2->Length + a1->Length + a3->Length + 93) & 0xFFFFFFF8;
  v11 = v10 + Size;
  if ( v10 + (unsigned int)Size >= v10 )
  {
    v13 = TSAllocate(v11);
    v14 = v13;
    if ( v13 )
    {
      *(_DWORD *)v13 = 13;
      v15 = (char *)(v13 + 40);
      v16 = v13 + 40;
      v13[20] = a1->Length;
      v12 = 0;
      Length = a1->Length;
      *((_QWORD *)v14 + 6) = 80;
      v14[21] = Length + 2;
      memcpy_0(v16, a1->Buffer, a1->Length);
      v18 = &v15[(unsigned __int16)v14[21]];
      v14[4] = a2->Length;
      v14[5] = a2->Length + 2;
      *((_QWORD *)v14 + 2) = v18 - (char *)v14;
      memcpy_0(v18, a2->Buffer, a2->Length);
      v19 = &v18[(unsigned __int16)v14[5]];
      v14[12] = a3->Length;
      v14[13] = a3->Length + 2;
      *((_QWORD *)v14 + 4) = v19 - (char *)v14;
      memcpy_0(v19, a3->Buffer, a3->Length);
      v20 = (unsigned __int16)v14[13] + 7LL;
      *((_DWORD *)v14 + 15) = Size;
      v21 = (char *)((unsigned __int64)&v19[v20] & 0xFFFFFFFFFFFFFFF8uLL);
      *((_QWORD *)v14 + 8) = v21 - (char *)v14;
      memcpy_0(v21, a4, (unsigned int)Size);
      *a6 = (unsigned __int8 *)v14;
      *a7 = v11;
    }
    else
    {
      return (unsigned int)-1073741670;
    }
  }
  else
  {
    return (unsigned int)-1073741675;
  }
  return v12;
}

```

## disassembly

```asm
0x180018b8c  mov     [rsp+Src], r9
0x180018b91  push    rbx
0x180018b92  push    rbp
0x180018b93  push    rsi
0x180018b94  push    rdi
0x180018b95  push    r12
0x180018b97  push    r13
0x180018b99  push    r14
0x180018b9b  push    r15
0x180018b9d  sub     rsp, 28h
0x180018ba1  movzx   r10d, word ptr [rcx]
0x180018ba5  mov     r14, r8
0x180018ba8  movzx   eax, word ptr [rdx]
0x180018bab  mov     r15, rdx
0x180018bae  movzx   r11d, word ptr [r8]
0x180018bb2  add     r10d, eax
0x180018bb5  mov     r13d, dword ptr [rsp+68h+Size]
0x180018bbd  add     r11d, 5Dh ; ']'
0x180018bc1  add     r11d, r10d
0x180018bc4  mov     r12, rcx
0x180018bc7  and     r11d, 0FFFFFFF8h
0x180018bcb  lea     ebp, [r11+r13]
0x180018bcf  cmp     ebp, r11d
0x180018bd2  jnb     short loc_180018BDE
0x180018bd4  mov     esi, 0C0000095h
0x180018bd9  jmp     loc_180018CDF
0x180018bde  mov     ecx, ebp; Size
0x180018be0  call    ?TSAllocate@@YAPEAX_K@Z; TSAllocate(unsigned __int64)
0x180018be5  mov     rdi, rax
0x180018be8  test    rax, rax
0x180018beb  jnz     short loc_180018BF7
0x180018bed  mov     esi, 0C000009Ah
0x180018bf2  jmp     loc_180018CDF
0x180018bf7  mov     dword ptr [rax], 0Dh
0x180018bfd  lea     rbx, [rax+50h]
0x180018c01  movzx   eax, word ptr [r12]
0x180018c06  mov     rcx, rbx; void *
0x180018c09  mov     [rdi+28h], ax
0x180018c0d  xor     esi, esi
0x180018c0f  movzx   eax, word ptr [r12]
0x180018c14  mov     qword ptr [rdi+30h], 50h ; 'P'
0x180018c1c  add     ax, 2
0x180018c20  mov     [rdi+2Ah], ax
0x180018c24  movzx   r8d, word ptr [r12]; Size
0x180018c29  mov     rdx, [r12+8]; Src
0x180018c2e  call    memcpy_0
0x180018c33  movzx   eax, word ptr [rdi+2Ah]
0x180018c37  add     rbx, rax
0x180018c3a  movzx   eax, word ptr [r15]
0x180018c3e  mov     [rdi+8], ax
0x180018c42  mov     rcx, rbx; void *
0x180018c45  movzx   eax, word ptr [r15]
0x180018c49  add     ax, 2
0x180018c4d  mov     [rdi+0Ah], ax
0x180018c51  mov     rax, rbx
0x180018c54  sub     rax, rdi
0x180018c57  mov     [rdi+10h], rax
0x180018c5b  movzx   r8d, word ptr [r15]; Size
0x180018c5f  mov     rdx, [r15+8]; Src
0x180018c63  call    memcpy_0
0x180018c68  movzx   eax, word ptr [rdi+0Ah]
0x180018c6c  add     rbx, rax
0x180018c6f  movzx   eax, word ptr [r14]
0x180018c73  mov     [rdi+18h], ax
0x180018c77  mov     rcx, rbx; void *
0x180018c7a  movzx   eax, word ptr [r14]
0x180018c7e  add     ax, 2
0x180018c82  mov     [rdi+1Ah], ax
0x180018c86  mov     rax, rbx
0x180018c89  sub     rax, rdi
0x180018c8c  mov     [rdi+20h], rax
0x180018c90  movzx   r8d, word ptr [r14]; Size
0x180018c94  mov     rdx, [r14+8]; Src
0x180018c98  call    memcpy_0
0x180018c9d  movzx   ecx, word ptr [rdi+1Ah]
0x180018ca1  mov     r8, r13; Size
0x180018ca4  add     rcx, 7
0x180018ca8  mov     [rdi+3Ch], r13d
0x180018cac  add     rcx, rbx
0x180018caf  and     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x180018cb3  mov     rdx, rcx
0x180018cb6  sub     rdx, rdi
0x180018cb9  mov     [rdi+40h], rdx
0x180018cbd  mov     rdx, [rsp+68h+Src]; Src
0x180018cc5  call    memcpy_0
0x180018cca  mov     rcx, [rsp+68h+arg_28]
0x180018cd2  mov     [rcx], rdi
0x180018cd5  mov     rcx, [rsp+68h+arg_30]
0x180018cdd  mov     [rcx], ebp
0x180018cdf  mov     eax, esi
0x180018ce1  add     rsp, 28h
0x180018ce5  pop     r15
0x180018ce7  pop     r14
0x180018ce9  pop     r13
0x180018ceb  pop     r12
0x180018ced  pop     rdi
0x180018cee  pop     rsi
0x180018cef  pop     rbp
0x180018cf0  pop     rbx
0x180018cf1  retn
```
