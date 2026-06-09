# wsm_wstring::deserialize(read_buffer_aligned &)

- ea: `0x14000cdc0`
- end: `0x14000ce80`
- name: `?deserialize@wsm_wstring@@UEAAJAEAVread_buffer_aligned@@@Z`
- size: `192`
- prototype: `__int64 __fastcall(wsm_wstring *__hidden this, struct read_buffer_aligned *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x14000cdc0`
- `0x14000ce88`
- `0x14000fa40`

## pseudocode

```c
__int64 __fastcall wsm_wstring::deserialize(wsm_wstring *this, struct read_buffer_aligned *a2)
{
  unsigned int v3; // edx
  int v4; // ebp
  unsigned int v6; // eax
  unsigned int v7; // ebx
  unsigned int v8; // ecx
  int v9; // esi
  unsigned int v10; // esi
  int v11; // ecx
  __int64 v12; // rdx
  __int64 result; // rax
  unsigned int v14; // ecx
  const unsigned __int16 *v15; // rdx
  unsigned __int16 v16; // [rsp+68h] [rbp+10h] BYREF

  v3 = *((_DWORD *)a2 + 3);
  v4 = -1;
  v16 = 0;
  if ( (v3 & 1) != 0 )
  {
    v6 = v3 + (v3 & 1);
    v7 = -1;
    if ( v6 >= v3 )
      v7 = v3 + (v3 & 1);
    v8 = v6 < v3 ? 0xC0000095 : 0;
    if ( v6 < v3 )
      return v8;
    *((_DWORD *)a2 + 3) = v7;
  }
  else
  {
    v7 = v3;
  }
  v9 = *((_DWORD *)a2 + 2);
  if ( v7 == v9 )
    return (unsigned int)-2147483614;
  v10 = v9 - v7;
  if ( v10 >= 2 )
    v10 = 2;
  memmove(&v16, (const void *)(*(_QWORD *)a2 + v7), v10);
  v11 = v16;
  v12 = v7 + v10;
  *((_DWORD *)a2 + 3) = v12;
  result = 0;
  if ( (_WORD)v11 )
  {
    if ( (((_BYTE)v7 + (_BYTE)v10) & 1) != 0 )
    {
      return 3221226612LL;
    }
    else
    {
      v14 = v12 + v11;
      if ( v14 >= (unsigned int)v12 )
        v4 = v14;
      result = v14 < (unsigned int)v12 ? 0xC0000095 : 0;
      if ( v14 >= (unsigned int)v12 )
      {
        v15 = (const unsigned __int16 *)(*(_QWORD *)a2 + v12);
        *((_DWORD *)a2 + 3) = v4;
        return wsm_wstring::init(this, v15);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000cdc0  push    rbx
0x14000cdc2  push    rbp
0x14000cdc3  push    rsi
0x14000cdc4  push    rdi
0x14000cdc5  push    r14
0x14000cdc7  push    r15
0x14000cdc9  sub     rsp, 28h
0x14000cdcd  xor     r15d, r15d
0x14000cdd0  mov     rdi, rdx
0x14000cdd3  mov     edx, [rdx+0Ch]
0x14000cdd6  or      ebp, 0FFFFFFFFh
0x14000cdd9  mov     eax, edx
0x14000cddb  mov     [rsp+58h+arg_8], r15w
0x14000cde1  mov     r14, rcx
0x14000cde4  and     eax, 1
0x14000cde7  jz      short loc_14000CE03
0x14000cde9  add     eax, edx
0x14000cdeb  mov     ebx, ebp
0x14000cded  cmp     eax, edx
0x14000cdef  cmovnb  ebx, eax
0x14000cdf2  sbb     ecx, ecx
0x14000cdf4  and     ecx, 0C0000095h
0x14000cdfa  cmp     eax, edx
0x14000cdfc  jb      short loc_14000CE70
0x14000cdfe  mov     [rdi+0Ch], ebx
0x14000ce01  jmp     short loc_14000CE05
0x14000ce03  mov     ebx, edx
0x14000ce05  mov     esi, [rdi+8]
0x14000ce08  cmp     ebx, esi
0x14000ce0a  jz      short loc_14000CE6B
0x14000ce0c  mov     eax, 2
0x14000ce11  mov     edx, ebx
0x14000ce13  sub     esi, ebx
0x14000ce15  lea     rcx, [rsp+58h+arg_8]; void *
0x14000ce1a  cmp     esi, eax
0x14000ce1c  cmovnb  esi, eax
0x14000ce1f  add     rdx, [rdi]; Src
0x14000ce22  mov     r8d, esi; Size
0x14000ce25  call    memmove
0x14000ce2a  movzx   ecx, [rsp+58h+arg_8]
0x14000ce2f  lea     edx, [rbx+rsi]
0x14000ce32  mov     [rdi+0Ch], edx
0x14000ce35  mov     eax, r15d
0x14000ce38  test    cx, cx
0x14000ce3b  jz      short loc_14000CE72
0x14000ce3d  test    dl, 1
0x14000ce40  jz      short loc_14000CE49
0x14000ce42  mov     eax, 0C0000474h
0x14000ce47  jmp     short loc_14000CE72
0x14000ce49  add     ecx, edx
0x14000ce4b  cmp     ecx, edx
0x14000ce4d  cmovnb  ebp, ecx
0x14000ce50  sbb     eax, eax
0x14000ce52  and     eax, 0C0000095h
0x14000ce57  cmp     ecx, edx
0x14000ce59  jb      short loc_14000CE72
0x14000ce5b  add     rdx, [rdi]; unsigned __int16 *
0x14000ce5e  mov     rcx, r14; this
0x14000ce61  mov     [rdi+0Ch], ebp
0x14000ce64  call    ?init@wsm_wstring@@IEAAJPEBG@Z; wsm_wstring::init(ushort const *)
0x14000ce69  jmp     short loc_14000CE72
0x14000ce6b  mov     ecx, 80000022h
0x14000ce70  mov     eax, ecx
0x14000ce72  add     rsp, 28h
0x14000ce76  pop     r15
0x14000ce78  pop     r14
0x14000ce7a  pop     rdi
0x14000ce7b  pop     rsi
0x14000ce7c  pop     rbp
0x14000ce7d  pop     rbx
0x14000ce7e  retn
```
