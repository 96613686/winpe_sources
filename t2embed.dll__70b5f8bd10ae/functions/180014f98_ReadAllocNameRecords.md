# ReadAllocNameRecords

- ea: `0x180014f98`
- end: `0x18001517f`
- name: `ReadAllocNameRecords`
- size: `487`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18002049c`
- `0x180028f78`

## callees

- `0x1800134b4`
- `0x180014f98`
- `0x180015190`
- `0x18001569c`
- `0x180016438`
- `0x180016dd0`
- `0x18002b010`

## pseudocode

```c
__int64 __fastcall ReadAllocNameRecords(
        __int64 *a1,
        __int64 *a2,
        unsigned __int16 *a3,
        __int64 (__fastcall *a4)(_QWORD),
        __int64 a5)
{
  unsigned __int16 v5; // r15
  unsigned int v10; // r13d
  __int64 result; // rax
  unsigned __int16 Bytes; // bx
  unsigned __int16 v13; // si
  __int64 v14; // rax
  __int64 v15; // rcx
  unsigned int v16; // ebp
  __int64 v17; // rax
  __int64 v18; // rcx
  unsigned __int16 v19; // [rsp+78h] [rbp+10h] BYREF
  int v20; // [rsp+80h] [rbp+18h] BYREF
  unsigned __int16 v21; // [rsp+84h] [rbp+1Ch]
  __int64 (__fastcall *v22)(_QWORD); // [rsp+88h] [rbp+20h]

  v22 = a4;
  v5 = 0;
  *a2 = 0;
  v20 = 0;
  v21 = 0;
  v19 = 0;
  *a3 = 0;
  v10 = TTTableOffset(a1, "name");
  if ( !v10 )
    return 1037;
  if ( !(unsigned int)TTTableLength(a1, "name") )
    return 1067;
  result = ReadGeneric(a1, (__int64)&v20, 6u, (unsigned __int8 *)&NAME_HEADER_CONTROL, v10, &v19);
  Bytes = result;
  if ( !(_WORD)result )
  {
    v13 = HIWORD(v20);
    v14 = a4(40LL * HIWORD(v20));
    *a2 = v14;
    v15 = v14;
    if ( v14 )
    {
      v16 = v10 + v19;
      *a3 = v13;
      while ( v5 < *a3 )
      {
        Bytes = ReadGeneric(a1, v15 + 40LL * v5, 0xCu, (unsigned __int8 *)&NAME_RECORD_CONTROL, v16, &v19);
        if ( Bytes )
          goto LABEL_15;
        v15 = *a2;
        if ( *(_WORD *)(*a2 + 40LL * v5 + 8) )
        {
          v17 = v22(*(unsigned __int16 *)(*a2 + 40LL * v5 + 8));
          v18 = *a2;
          *(_QWORD *)(*a2 + 40LL * v5 + 16) = v17;
          if ( !v17 )
          {
            Bytes = 1005;
LABEL_15:
            FreeNameRecords(*a2, *a3, a5);
            *a2 = 0;
            *a3 = 0;
            return Bytes;
          }
          Bytes = ReadBytes(
                    a1,
                    v17,
                    v10 + *(unsigned __int16 *)(v18 + 40LL * v5 + 10) + v21,
                    *(unsigned __int16 *)(v18 + 40LL * v5 + 8));
          if ( Bytes )
            goto LABEL_15;
          v15 = *a2;
          *(_QWORD *)(v15 + 40LL * v5 + 24) = 0;
          *(_WORD *)(v15 + 40LL * v5 + 12) = 0;
          *(_DWORD *)(v15 + 40LL * v5 + 32) = 0;
        }
        v16 += v19;
        ++v5;
      }
      return Bytes;
    }
    else
    {
      return 1005;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180014f98  mov     r11, rsp
0x180014f9b  mov     [r11+8], rbx
0x180014f9f  mov     [r11+20h], r9
0x180014fa3  push    rbp
0x180014fa4  push    rsi
0x180014fa5  push    rdi
0x180014fa6  push    r12
0x180014fa8  push    r13
0x180014faa  push    r14
0x180014fac  push    r15
0x180014fae  sub     rsp, 30h
0x180014fb2  xor     r15d, r15d
0x180014fb5  xor     eax, eax
0x180014fb7  mov     [rdx], r15
0x180014fba  mov     rdi, rdx
0x180014fbd  lea     rdx, aName; "name"
0x180014fc4  mov     [r11+18h], eax
0x180014fc8  mov     rbp, r9
0x180014fcb  mov     [r11+1Ch], ax
0x180014fd0  mov     r14, r8
0x180014fd3  mov     [r11+10h], r15w
0x180014fd8  mov     r12, rcx
0x180014fdb  mov     [r8], r15w
0x180014fdf  call    TTTableOffset
0x180014fe4  mov     r13d, eax
0x180014fe7  test    eax, eax
0x180014fe9  jz      loc_180015164
0x180014fef  lea     rdx, aName; "name"
0x180014ff6  mov     rcx, r12
0x180014ff9  call    TTTableLength
0x180014ffe  test    eax, eax
0x180015000  jz      loc_18001516E
0x180015006  lea     rax, [rsp+68h+arg_8]
0x18001500b  mov     rcx, r12
0x18001500e  mov     [rsp+68h+var_40], rax
0x180015013  lea     r8d, [r15+6]
0x180015017  lea     r9, NAME_HEADER_CONTROL
0x18001501e  mov     [rsp+68h+var_48], r13d
0x180015023  lea     rdx, [rsp+68h+arg_10]
0x18001502b  call    ReadGeneric
0x180015030  movzx   ebx, ax
0x180015033  test    ax, ax
0x180015036  jnz     short loc_180015060
0x180015038  movzx   esi, [rsp+68h+arg_12]
0x180015040  mov     rax, rbp
0x180015043  lea     rcx, [rsi+rsi*4]
0x180015047  shl     rcx, 3
0x18001504b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015050  mov     [rdi], rax
0x180015053  mov     rcx, rax
0x180015056  test    rax, rax
0x180015059  jnz     short loc_180015075
0x18001505b  mov     eax, 3EDh
0x180015060  mov     rbx, [rsp+68h+arg_0]
0x180015065  add     rsp, 30h
0x180015069  pop     r15
0x18001506b  pop     r14
0x18001506d  pop     r13
0x18001506f  pop     r12
0x180015071  pop     rdi
0x180015072  pop     rsi
0x180015073  pop     rbp
0x180015074  retn
0x180015075  movzx   ebp, [rsp+68h+arg_8]
0x18001507a  add     ebp, r13d
0x18001507d  mov     [r14], si
0x180015081  cmp     r15w, [r14]
0x180015085  jnb     loc_18001515C
0x18001508b  movzx   eax, r15w
0x18001508f  lea     r9, NAME_RECORD_CONTROL
0x180015096  mov     r8d, 0Ch
0x18001509c  lea     rsi, [rax+rax*4]
0x1800150a0  lea     rax, [rsp+68h+arg_8]
0x1800150a5  lea     rdx, [rcx+rsi*8]
0x1800150a9  mov     [rsp+68h+var_40], rax
0x1800150ae  mov     rcx, r12
0x1800150b1  mov     [rsp+68h+var_48], ebp
0x1800150b5  call    ReadGeneric
0x1800150ba  movzx   ebx, ax
0x1800150bd  test    ax, ax
0x1800150c0  jnz     short loc_18001513F
0x1800150c2  mov     rcx, [rdi]
0x1800150c5  movzx   eax, word ptr [rcx+rsi*8+8]
0x1800150ca  test    ax, ax
0x1800150cd  jz      short loc_18001512F
0x1800150cf  mov     ecx, eax
0x1800150d1  mov     rax, [rsp+68h+arg_18]
0x1800150d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800150de  mov     rcx, [rdi]
0x1800150e1  mov     [rcx+rsi*8+10h], rax
0x1800150e6  test    rax, rax
0x1800150e9  jz      loc_180015178
0x1800150ef  movzx   r9d, word ptr [rcx+rsi*8+8]
0x1800150f5  mov     rdx, rax
0x1800150f8  movzx   ecx, word ptr [rcx+rsi*8+0Ah]
0x1800150fd  movzx   r8d, [rsp+68h+arg_14]
0x180015106  add     ecx, r13d
0x180015109  add     r8d, ecx
0x18001510c  mov     rcx, r12
0x18001510f  call    ReadBytes
0x180015114  xor     edx, edx
0x180015116  movzx   ebx, ax
0x180015119  test    ax, ax
0x18001511c  jnz     short loc_18001513F
0x18001511e  mov     rcx, [rdi]
0x180015121  mov     [rcx+rsi*8+18h], rdx
0x180015126  mov     [rcx+rsi*8+0Ch], dx
0x18001512b  mov     [rcx+rsi*8+20h], edx
0x18001512f  movzx   eax, [rsp+68h+arg_8]
0x180015134  add     ebp, eax
0x180015136  inc     r15w
0x18001513a  jmp     loc_180015081
0x18001513f  mov     r8, [rsp+68h+arg_20]
0x180015147  movzx   edx, word ptr [r14]
0x18001514b  mov     rcx, [rdi]
0x18001514e  call    FreeNameRecords
0x180015153  xor     eax, eax
0x180015155  mov     [rdi], rax
0x180015158  mov     [r14], ax
0x18001515c  movzx   eax, bx
0x18001515f  jmp     loc_180015060
0x180015164  mov     eax, 40Dh
0x180015169  jmp     loc_180015060
0x18001516e  mov     eax, 42Bh
0x180015173  jmp     loc_180015060
0x180015178  mov     ebx, 3EDh
0x18001517d  jmp     short loc_18001513F
```
