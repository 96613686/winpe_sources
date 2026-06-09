# CLogManager::RemoveFields(void)

- ea: `0x18001fc08`
- end: `0x18001fd09`
- name: `?RemoveFields@CLogManager@@IEAAHXZ`
- size: `257`
- prototype: `__int64 __fastcall(CLogManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001e8c0`
- `0x18001f020`

## callees

- `0x18001fc08`
- `0x1800274c6`

## pseudocode

```c
__int64 __fastcall CLogManager::RemoveFields(CLogManager *this)
{
  unsigned int *v1; // rax
  char *v3; // r14
  int v4; // edi
  unsigned int v5; // ebp
  int v6; // r8d
  __int64 v7; // r11
  unsigned int v8; // edx
  unsigned __int16 *v9; // rcx
  unsigned __int16 *v10; // rax
  int v11; // r9d
  int v12; // r10d
  __int64 v14; // rdx
  unsigned int v15; // ecx

  v1 = (unsigned int *)*((_QWORD *)this + 2);
  if ( !v1 || !*((_QWORD *)this + 7) )
    return 0;
  v3 = (char *)v1 + *v1;
  v4 = *((_DWORD *)this + 16) - 1;
  if ( v4 >= 0 )
  {
    v5 = v1[1] / 0x20C - 1;
    do
    {
      v6 = v5;
      v7 = *((_QWORD *)this + 7) + 544LL * (unsigned int)v4;
      v8 = 0;
      while ( v6 >= 0 )
      {
        v9 = (unsigned __int16 *)&v3[524 * v6];
        v10 = v9 + 6;
        do
        {
          v11 = *(unsigned __int16 *)((char *)v10 + v7 - (_QWORD)(v9 + 6));
          v12 = *v10 - v11;
          if ( v12 )
            break;
          ++v10;
        }
        while ( v11 );
        if ( !v12 && (*(_DWORD *)v9)-- == 1 )
        {
          if ( v8 )
            memcpy_0(v9, v9 + 262, v8);
          v14 = *((_QWORD *)this + 2);
          v15 = *(_DWORD *)(v14 + 4);
          if ( v15 >= 0x20C )
            *(_DWORD *)(v14 + 4) = v15 - 524;
          break;
        }
        v8 += 524;
        --v6;
      }
      --v4;
    }
    while ( v4 >= 0 );
  }
  return 1;
}

```

## disassembly

```asm
0x18001fc08  mov     [rsp+arg_8], rbx
0x18001fc0d  mov     [rsp+arg_10], rbp
0x18001fc12  push    rsi
0x18001fc13  push    rdi
0x18001fc14  push    r14
0x18001fc16  sub     rsp, 20h
0x18001fc1a  mov     rax, [rcx+10h]
0x18001fc1e  mov     rbx, rcx
0x18001fc21  test    rax, rax
0x18001fc24  jz      loc_18001FCF3
0x18001fc2a  cmp     qword ptr [rcx+38h], 0
0x18001fc2f  jz      loc_18001FCF3
0x18001fc35  mov     r14d, [rax]
0x18001fc38  mov     ecx, [rax+4]
0x18001fc3b  add     r14, rax
0x18001fc3e  mov     edi, [rbx+40h]
0x18001fc41  mov     rax, 3E88CB3C9484E2Bh
0x18001fc4b  mul     rcx
0x18001fc4e  shr     rdx, 3
0x18001fc52  sub     edi, 1
0x18001fc55  js      loc_18001FCEC
0x18001fc5b  lea     ebp, [rdx-1]
0x18001fc5e  mov     eax, edi
0x18001fc60  mov     r8d, ebp
0x18001fc63  imul    r11, rax, 220h
0x18001fc6a  add     r11, [rbx+38h]
0x18001fc6e  xor     edx, edx
0x18001fc70  test    r8d, r8d
0x18001fc73  js      short loc_18001FCE3
0x18001fc75  movsxd  rax, r8d
0x18001fc78  mov     rsi, r11
0x18001fc7b  imul    rcx, rax, 20Ch
0x18001fc82  add     rcx, r14; void *
0x18001fc85  lea     rax, [rcx+0Ch]
0x18001fc89  sub     rsi, rax
0x18001fc8c  movzx   r10d, word ptr [rax]
0x18001fc90  movzx   r9d, word ptr [rax+rsi]
0x18001fc95  sub     r10d, r9d
0x18001fc98  jnz     short loc_18001FCA3
0x18001fc9a  add     rax, 2
0x18001fc9e  test    r9d, r9d
0x18001fca1  jnz     short loc_18001FC8C
0x18001fca3  test    r10d, r10d
0x18001fca6  jnz     short loc_18001FCAD
0x18001fca8  add     dword ptr [rcx], 0FFFFFFFFh
0x18001fcab  jz      short loc_18001FCB8
0x18001fcad  add     edx, 20Ch
0x18001fcb3  dec     r8d
0x18001fcb6  jmp     short loc_18001FC70
0x18001fcb8  test    edx, edx
0x18001fcba  jz      short loc_18001FCCB
0x18001fcbc  mov     r8d, edx; Size
0x18001fcbf  lea     rdx, [rcx+20Ch]; Src
0x18001fcc6  call    memcpy_0
0x18001fccb  mov     rdx, [rbx+10h]
0x18001fccf  mov     ecx, [rdx+4]
0x18001fcd2  cmp     ecx, 20Ch
0x18001fcd8  jb      short loc_18001FCE3
0x18001fcda  add     ecx, 0FFFFFDF4h
0x18001fce0  mov     [rdx+4], ecx
0x18001fce3  sub     edi, 1
0x18001fce6  jns     loc_18001FC5E
0x18001fcec  mov     eax, 1
0x18001fcf1  jmp     short loc_18001FCF5
0x18001fcf3  xor     eax, eax
0x18001fcf5  mov     rbx, [rsp+38h+arg_8]
0x18001fcfa  mov     rbp, [rsp+38h+arg_10]
0x18001fcff  add     rsp, 20h
0x18001fd03  pop     r14
0x18001fd05  pop     rdi
0x18001fd06  pop     rsi
0x18001fd07  retn
```
