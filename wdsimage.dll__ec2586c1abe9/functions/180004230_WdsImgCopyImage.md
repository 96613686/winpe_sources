# WdsImgCopyImage

- ea: `0x180004230`
- end: `0x1800042c9`
- name: `WdsImgCopyImage`
- size: `153`
- prototype: `__int64 __fastcall(CImage *this)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x180003c68`
- `0x180004230`
- `0x1800094b8`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall WdsImgCopyImage(CImage *this, const unsigned __int16 *a2, struct CImage **a3)
{
  struct CImage *v4; // rcx
  __int64 v6; // rbx
  __int64 v7; // rdx
  __int64 v8; // r8
  int v9; // eax
  struct CImage *v11; // [rsp+38h] [rbp+10h] BYREF

  v4 = 0;
  v11 = 0;
  if ( a2 && *a2 && a3 )
  {
    if ( !this )
    {
      LODWORD(v6) = -2147024809;
      return (unsigned int)v6;
    }
    if ( *((_DWORD *)this + 4) != 4 )
    {
      LODWORD(v6) = -1056833019;
      return (unsigned int)v6;
    }
    v6 = (unsigned int)CImage::Copy(this, a2, &v11);
    v9 = ElValidateHr_0(v6, v7, v8, 1792);
    v4 = v11;
    if ( v9 >= 0 )
    {
      *a3 = v11;
      return (unsigned int)v6;
    }
  }
  else
  {
    LODWORD(v6) = -2147024809;
  }
  if ( v4 )
    (*(void (__fastcall **)(struct CImage *))(*(_QWORD *)v4 + 8LL))(v4);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180004230  mov     [rsp+arg_0], rbx
0x180004235  mov     [rsp+arg_10], rsi
0x18000423a  push    rdi
0x18000423b  sub     rsp, 20h
0x18000423f  xor     esi, esi
0x180004241  mov     rax, rcx
0x180004244  mov     ecx, esi
0x180004246  mov     rdi, r8
0x180004249  mov     [rsp+28h+arg_8], rcx
0x18000424e  test    rdx, rdx
0x180004251  jz      short loc_1800042A0
0x180004253  cmp     [rdx], si
0x180004256  jz      short loc_1800042A0
0x180004258  test    r8, r8
0x18000425b  jz      short loc_1800042A0
0x18000425d  test    rax, rax
0x180004260  jnz     short loc_180004269
0x180004262  mov     ebx, 80070057h
0x180004267  jmp     short loc_1800042B6
0x180004269  cmp     dword ptr [rax+10h], 4
0x18000426d  jz      short loc_180004276
0x18000426f  mov     ebx, 0C1020205h
0x180004274  jmp     short loc_1800042B6
0x180004276  lea     r8, [rsp+28h+arg_8]; struct CImage **
0x18000427b  mov     rcx, rax; this
0x18000427e  call    ?Copy@CImage@@QEAAJPEBGPEAPEAV1@@Z; CImage::Copy(ushort const *,CImage * *)
0x180004283  mov     r9d, 700h
0x180004289  mov     ecx, eax
0x18000428b  mov     ebx, eax
0x18000428d  call    ElValidateHr_0
0x180004292  mov     rcx, [rsp+28h+arg_8]
0x180004297  test    eax, eax
0x180004299  js      short loc_1800042A5
0x18000429b  mov     [rdi], rcx
0x18000429e  jmp     short loc_1800042B6
0x1800042a0  mov     ebx, 80070057h
0x1800042a5  test    rcx, rcx
0x1800042a8  jz      short loc_1800042B6
0x1800042aa  mov     rax, [rcx]
0x1800042ad  mov     rax, [rax+8]
0x1800042b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042b6  mov     rsi, [rsp+28h+arg_10]
0x1800042bb  mov     eax, ebx
0x1800042bd  mov     rbx, [rsp+28h+arg_0]
0x1800042c2  add     rsp, 20h
0x1800042c6  pop     rdi
0x1800042c7  retn
```
