# UpdateSecureFrameMetadataInfo

- ea: `0x14000566c`
- end: `0x14000571b`
- name: `UpdateSecureFrameMetadataInfo`
- size: `175`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140001bcc`
- `0x140019fc8`

## callees

- `0x140005570`
- `0x14000566c`
- `0x140040b40`

## pseudocode

```c
__int64 __fastcall UpdateSecureFrameMetadataInfo(__int64 a1, __int64 a2)
{
  __int64 result; // rax
  _DWORD *v4; // r8
  const void *v5; // r9
  __int64 v6; // rbx
  _DWORD *v7; // rsi
  unsigned int v8; // edx
  __int64 v9; // rcx
  unsigned int v10; // edi

  result = GetMetadataInfoPtr();
  v6 = result;
  if ( result )
  {
    v7 = *(_DWORD **)(result + 16);
    if ( v7 )
    {
      v8 = v4[3];
      if ( v8 )
      {
        v9 = *(unsigned int *)(result + 4);
        result = (unsigned int)(*(_DWORD *)result - v9);
        if ( (unsigned int)result >= 0x28 && !(_DWORD)v9 )
        {
          v7[1] = 40;
          *v7 = 2;
          v7[2] = v4[4];
          v7[3] = v4[6];
          v7[6] = v4[10];
          result = (unsigned int)v4[12];
          v7[7] = result;
          *(_DWORD *)(v6 + 4) += 40;
          v9 = *(unsigned int *)(v6 + 4);
        }
        v10 = *(_DWORD *)v6 - v9;
        if ( v10 >= v8 )
          v10 = v8;
        if ( v10 )
        {
          memmove((void *)(*(_QWORD *)(v6 + 16) + v9), v5, v10);
          *(_DWORD *)(v6 + 4) += v10;
          result = *(_QWORD *)(a2 + 424);
          if ( !*(_QWORD *)(*(_QWORD *)(result + 16) + 1024LL) )
            v7[1] += v10;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000566c  push    rbx
0x14000566e  push    rbp
0x14000566f  push    rsi
0x140005670  push    rdi
0x140005671  sub     rsp, 28h
0x140005675  mov     rbp, rdx
0x140005678  call    GetMetadataInfoPtr
0x14000567d  mov     rbx, rax
0x140005680  test    rax, rax
0x140005683  jz      loc_140005711
0x140005689  mov     rsi, [rax+10h]
0x14000568d  test    rsi, rsi
0x140005690  jz      short loc_140005711
0x140005692  mov     edx, [r8+0Ch]
0x140005696  test    edx, edx
0x140005698  jz      short loc_140005711
0x14000569a  mov     ecx, [rax+4]
0x14000569d  mov     eax, [rax]
0x14000569f  sub     eax, ecx
0x1400056a1  cmp     eax, 28h ; '('
0x1400056a4  jb      short loc_1400056DA
0x1400056a6  test    ecx, ecx
0x1400056a8  jnz     short loc_1400056DA
0x1400056aa  mov     dword ptr [rsi+4], 28h ; '('
0x1400056b1  mov     dword ptr [rsi], 2
0x1400056b7  mov     eax, [r8+10h]
0x1400056bb  mov     [rsi+8], eax
0x1400056be  mov     eax, [r8+18h]
0x1400056c2  mov     [rsi+0Ch], eax
0x1400056c5  mov     eax, [r8+28h]
0x1400056c9  mov     [rsi+18h], eax
0x1400056cc  mov     eax, [r8+30h]
0x1400056d0  mov     [rsi+1Ch], eax
0x1400056d3  add     dword ptr [rbx+4], 28h ; '('
0x1400056d7  mov     ecx, [rbx+4]
0x1400056da  mov     edi, [rbx]
0x1400056dc  sub     edi, ecx
0x1400056de  cmp     edi, edx
0x1400056e0  cmovnb  edi, edx
0x1400056e3  test    edi, edi
0x1400056e5  jz      short loc_140005711
0x1400056e7  add     rcx, [rbx+10h]; void *
0x1400056eb  mov     rdx, r9; Src
0x1400056ee  mov     r8d, edi; Size
0x1400056f1  call    memmove
0x1400056f6  add     [rbx+4], edi
0x1400056f9  mov     rax, [rbp+1A8h]
0x140005700  mov     rcx, [rax+10h]
0x140005704  cmp     qword ptr [rcx+400h], 0
0x14000570c  jnz     short loc_140005711
0x14000570e  add     [rsi+4], edi
0x140005711  add     rsp, 28h
0x140005715  pop     rdi
0x140005716  pop     rsi
0x140005717  pop     rbp
0x140005718  pop     rbx
0x140005719  retn
```
