# EqualString(_UNICODE_STRING,ushort *,uchar)

- ea: `0x140016808`
- end: `0x1400168f6`
- name: `?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z`
- size: `238`
- prototype: `unsigned __int8 __fastcall(struct _UNICODE_STRING *__struct_ptr, unsigned __int16 *, unsigned __int8)`
- caller_count: `42`
- callee_count: `1`
- tags: ``

## callers

- `0x14001a760`
- `0x1400281f0`
- `0x14002ac00`
- `0x14002b2d4`
- `0x14002c100`
- `0x14002d240`
- `0x14002d7e0`
- `0x1400309c0`
- `0x140030ac0`
- `0x140030bf8`
- `0x140030cf8`
- `0x14003123c`
- `0x1400313c4`
- `0x1400314c8`
- `0x1400315c8`
- `0x1400318f0`
- `0x140031fb8`
- `0x140032230`
- `0x14003290c`
- `0x140032dcc`
- `0x140033414`
- `0x14003364c`
- `0x1400339c8`
- `0x140033ec4`
- `0x14003413c`
- `0x14003451c`
- `0x140034cc8`
- `0x140034dc4`
- `0x14003506c`
- `0x140035300`
- `0x14003552c`
- `0x14003579c`
- `0x140035880`
- `0x140035f48`
- `0x140036258`
- `0x140036ce0`
- `0x140037214`
- `0x140037364`
- `0x140037698`
- `0x140037b90`
- `0x140037d2c`
- `0x14003809c`

## callees

- `0x140016808`

## pseudocode

```c
char __fastcall EqualString(struct _UNICODE_STRING *a1, unsigned __int16 *a2, char a3)
{
  __int64 v4; // r10
  char v5; // r9
  unsigned __int16 *v6; // rax
  __int16 v7; // r8
  PWSTR Buffer; // rcx
  unsigned __int16 v9; // r10
  WCHAR v10; // bx

  if ( a2 )
  {
    v4 = 0x7FFFFFFF;
    v5 = 1;
    v6 = a2;
    do
    {
      if ( !*v6 )
        break;
      ++v6;
      --v4;
    }
    while ( v4 );
    if ( v4 )
    {
      v7 = a1->Length >> 1;
      if ( v7 == (unsigned __int16)(v4 != 0 ? -2 - 2 * v4 : 0) >> 1 )
      {
        if ( !v7 )
          return v5;
        Buffer = a1->Buffer;
        if ( a3 )
        {
          while ( 1 )
          {
            v9 = *a2;
            if ( *Buffer != *a2 )
            {
              v10 = *Buffer - 32;
              if ( (unsigned __int16)(*Buffer - 97) > 0x19u )
                v10 = *Buffer;
              if ( (unsigned __int16)(v9 - 97) <= 0x19u )
                v9 -= 32;
              if ( v10 != v9 )
                break;
            }
            ++a2;
            ++Buffer;
            if ( !--v7 )
              return v5;
          }
        }
        else
        {
          while ( *Buffer == *a2 )
          {
            ++a2;
            ++Buffer;
            if ( !--v7 )
              return v5;
          }
        }
      }
      return 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140016808  mov     [rsp+arg_0], rbx
0x14001680d  mov     [rsp+arg_8], rdi
0x140016812  xor     edi, edi
0x140016814  mov     bl, r8b
0x140016817  mov     r11, rcx
0x14001681a  test    rdx, rdx
0x14001681d  jz      loc_1400168E9
0x140016823  mov     r10d, 7FFFFFFFh
0x140016829  lea     r9d, [rdi+1]
0x14001682d  mov     rax, rdx
0x140016830  cmp     [rax], di
0x140016833  jz      short loc_14001683E
0x140016835  add     rax, 2
0x140016839  sub     r10, r9
0x14001683c  jnz     short loc_140016830
0x14001683e  test    r10, r10
0x140016841  jz      loc_1400168E9
0x140016847  movzx   r8d, word ptr [rcx]
0x14001684b  movzx   eax, r10w
0x14001684f  add     ax, ax
0x140016852  shr     r8w, 1
0x140016856  mov     ecx, 0FFFEh
0x14001685b  sub     cx, ax
0x14001685e  neg     r10
0x140016861  sbb     ax, ax
0x140016864  and     ax, cx
0x140016867  shr     ax, 1
0x14001686a  cmp     r8w, ax
0x14001686e  jnz     short loc_1400168E1
0x140016870  test    r8w, r8w
0x140016874  jz      short loc_1400168E4
0x140016876  mov     rcx, [r11+8]
0x14001687a  mov     r11d, 0FFFFh
0x140016880  test    bl, bl
0x140016882  jz      short loc_1400168C9
0x140016884  movzx   r10d, word ptr [rdx]
0x140016888  cmp     [rcx], r10w
0x14001688c  jz      short loc_1400168B9
0x14001688e  movzx   eax, word ptr [rcx]
0x140016891  movzx   ebx, word ptr [rcx]
0x140016894  sub     ax, 61h ; 'a'
0x140016898  sub     bx, 20h ; ' '
0x14001689c  cmp     ax, 19h
0x1400168a0  lea     eax, [r10-61h]
0x1400168a4  cmova   bx, [rcx]
0x1400168a8  cmp     ax, 19h
0x1400168ac  ja      short loc_1400168B3
0x1400168ae  sub     r10w, 20h ; ' '
0x1400168b3  cmp     bx, r10w
0x1400168b7  jnz     short loc_1400168E1
0x1400168b9  add     rdx, 2
0x1400168bd  add     rcx, 2
0x1400168c1  add     r8w, r11w
0x1400168c5  jnz     short loc_140016884
0x1400168c7  jmp     short loc_1400168E4
0x1400168c9  movzx   eax, word ptr [rdx]
0x1400168cc  cmp     [rcx], ax
0x1400168cf  jnz     short loc_1400168E1
0x1400168d1  add     rdx, 2
0x1400168d5  add     rcx, 2
0x1400168d9  add     r8w, r11w
0x1400168dd  jnz     short loc_1400168C9
0x1400168df  jmp     short loc_1400168E4
0x1400168e1  mov     r9b, dil
0x1400168e4  mov     al, r9b
0x1400168e7  jmp     short loc_1400168EB
0x1400168e9  xor     al, al
0x1400168eb  mov     rbx, [rsp+arg_0]
0x1400168f0  mov     rdi, [rsp+arg_8]
0x1400168f5  retn
```
