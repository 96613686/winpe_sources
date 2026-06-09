# u8_ipps_createTabDftInvRec_32f

- ea: `0x18005bb38`
- end: `0x18005bb92`
- name: `u8_ipps_createTabDftInvRec_32f`
- size: `90`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001da40`
- `0x18001e7d0`

## callees

- `0x18001f910`
- `0x18005bb38`

## pseudocode

```c
__int64 __fastcall u8_ipps_createTabDftInvRec_32f(int a1, __int64 a2)
{
  __int64 v3; // rdi
  __int64 result; // rax
  __int64 v5; // rdx
  _QWORD *v6; // rcx
  __int64 v7; // rbx

  v3 = (a1 + 3) / 4;
  result = px_ippsMalloc_8u((unsigned int)(8 * ((a1 + 3) / 4)));
  if ( result )
  {
    v5 = v3;
    if ( (int)v3 > 0 )
    {
      v6 = (_QWORD *)result;
      v7 = a2 - result;
      do
      {
        *v6 = *(_QWORD *)((char *)v6 + v7 + 8);
        ++v6;
        --v5;
      }
      while ( v5 );
    }
  }
  return result;
}

```

## disassembly

```asm
0x18005bb38  mov     [rsp+arg_0], rbx
0x18005bb3d  push    rdi
0x18005bb3e  sub     rsp, 20h
0x18005bb42  lea     eax, [rcx+3]
0x18005bb45  mov     rbx, rdx
0x18005bb48  cdq
0x18005bb49  and     edx, 3
0x18005bb4c  add     eax, edx
0x18005bb4e  sar     eax, 2
0x18005bb51  movsxd  rdi, eax
0x18005bb54  mov     ecx, edi
0x18005bb56  shl     ecx, 3
0x18005bb59  call    px_ippsMalloc_8u
0x18005bb5e  mov     r8, rax
0x18005bb61  test    rax, rax
0x18005bb64  jz      short loc_18005BB87
0x18005bb66  mov     rdx, rdi
0x18005bb69  test    edi, edi
0x18005bb6b  jle     short loc_18005BB84
0x18005bb6d  mov     rcx, rax
0x18005bb70  sub     rbx, rax
0x18005bb73  mov     rax, [rbx+rcx+8]
0x18005bb78  mov     [rcx], rax
0x18005bb7b  lea     rcx, [rcx+8]
0x18005bb7f  dec     rdx
0x18005bb82  jnz     short loc_18005BB73
0x18005bb84  mov     rax, r8
0x18005bb87  mov     rbx, [rsp+28h+arg_0]
0x18005bb8c  add     rsp, 20h
0x18005bb90  pop     rdi
0x18005bb91  retn
```
