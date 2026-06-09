# CrashOpenChannel

- ea: `0x14000a9e0`
- end: `0x14000aad2`
- name: `CrashOpenChannel`
- size: `242`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x14000a9e0`
- `0x14000d410`
- `0x14000d620`
- `0x14000d704`
- `0x14000d910`

## pseudocode

```c
char __fastcall CrashOpenChannel(__int64 a1)
{
  __int64 v2; // r9
  __int64 v3; // rax
  unsigned int *v4; // rsi

  if ( !MvmInitialized )
  {
    if ( !MvmInitialize() )
      return 0;
    MvmInitialized = 1;
  }
  if ( !*(_BYTE *)(a1 + 576) )
    return 0;
  if ( *(_BYTE *)(a1 + 105) || (v2 = *(_QWORD *)(a1 + 152)) == 0 )
  {
    v2 = *(_QWORD *)(a1 + 128);
    v3 = 192;
  }
  else
  {
    v3 = 384;
  }
  *(_QWORD *)(a1 + 184) = a1 + v3;
  v4 = (unsigned int *)(a1 + 120);
  if ( !MvmCreateGpadl(a1 + 48, v2 + 48, 0, *(_DWORD *)(v2 + 40), (_DWORD *)(a1 + 120)) )
    return 0;
  if ( !MvmOpenChannel(a1 + 48, *v4, *(_DWORD *)(a1 + 180)) )
  {
    MvmDeleteGpadl(a1 + 48, *v4);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x14000a9e0  mov     [rsp+arg_0], rbx
0x14000a9e5  mov     [rsp+arg_8], rsi
0x14000a9ea  push    rdi
0x14000a9eb  sub     rsp, 30h
0x14000a9ef  mov     al, cs:MvmInitialized
0x14000a9f5  mov     rbx, rcx
0x14000a9f8  test    al, al
0x14000a9fa  jnz     short loc_14000AA10
0x14000a9fc  call    MvmInitialize
0x14000aa01  test    al, al
0x14000aa03  jz      loc_14000AABB
0x14000aa09  mov     cs:MvmInitialized, 1
0x14000aa10  cmp     byte ptr [rbx+240h], 0
0x14000aa17  jz      loc_14000AABB
0x14000aa1d  cmp     byte ptr [rbx+69h], 0
0x14000aa21  jnz     short loc_14000AA36
0x14000aa23  mov     r9, [rbx+98h]
0x14000aa2a  test    r9, r9
0x14000aa2d  jz      short loc_14000AA36
0x14000aa2f  mov     eax, 180h
0x14000aa34  jmp     short loc_14000AA42
0x14000aa36  mov     r9, [rbx+80h]
0x14000aa3d  mov     eax, 0C0h
0x14000aa42  add     rax, rbx
0x14000aa45  lea     rdx, [r9+30h]
0x14000aa49  mov     [rbx+0B8h], rax
0x14000aa50  lea     rdi, [rbx+30h]
0x14000aa54  mov     r9d, [r9+28h]
0x14000aa58  lea     rsi, [rbx+78h]
0x14000aa5c  xor     r8d, r8d
0x14000aa5f  mov     [rsp+38h+var_18], rsi
0x14000aa64  mov     rcx, rdi
0x14000aa67  call    MvmCreateGpadl
0x14000aa6c  test    al, al
0x14000aa6e  jz      short loc_14000AABB
0x14000aa70  mov     r8d, [rbx+0B4h]
0x14000aa77  mov     rcx, rdi
0x14000aa7a  mov     edx, [rsi]
0x14000aa7c  call    MvmOpenChannel
0x14000aa81  test    al, al
0x14000aa83  jnz     short loc_14000AACE
0x14000aa85  mov     r10, [rbx+80h]
0x14000aa8c  mov     rcx, rdi
0x14000aa8f  mov     edx, [rsi]
0x14000aa91  mov     r8d, [r10+2Ch]
0x14000aa95  add     r8d, [r10+20h]
0x14000aa99  mov     r9d, [r10+28h]
0x14000aa9d  and     r8d, 0FFFh
0x14000aaa4  add     r9, 0FFFh
0x14000aaab  add     r9, r8
0x14000aaae  lea     r8, [r10+30h]
0x14000aab2  shr     r9, 0Ch
0x14000aab6  call    MvmDeleteGpadl
0x14000aabb  xor     al, al
0x14000aabd  mov     rbx, [rsp+38h+arg_0]
0x14000aac2  mov     rsi, [rsp+38h+arg_8]
0x14000aac7  add     rsp, 30h
0x14000aacb  pop     rdi
0x14000aacc  retn
0x14000aace  mov     al, 1
0x14000aad0  jmp     short loc_14000AABD
```
