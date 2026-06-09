# CWMResizeDMO::RegisterThreads(ulong,ushort const *)

- ea: `0x180008440`
- end: `0x180008549`
- name: `?RegisterThreads@CWMResizeDMO@@UEAAJKPEBG@Z`
- size: `265`
- prototype: `__int64 __fastcall(CWMResizeDMO *__hidden this, unsigned int, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180008440`
- `0x180014140`

## pseudocode

```c
__int64 __fastcall CWMResizeDMO::RegisterThreads(CWMResizeDMO *this, unsigned int a2, const unsigned __int16 *a3)
{
  _WORD *v4; // r10
  __int64 v6; // rax
  __int64 v7; // r9
  _WORD *v8; // rdx
  __int64 result; // rax
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rax

  v4 = (_WORD *)((char *)this + 264);
  v6 = 2147483646;
  v7 = 256;
  do
  {
    if ( !v6 )
      break;
    if ( !*a3 )
      break;
    *v4++ = *a3++;
    --v6;
    --v7;
  }
  while ( v7 );
  v8 = v4 - 1;
  result = 2147942522LL;
  if ( v7 )
  {
    v8 = v4;
    result = 0;
  }
  *v8 = 0;
  if ( v7 )
  {
    if ( a2 )
    {
      v10 = *((_QWORD *)this + 11);
      *((_DWORD *)this + 195) = a2;
      *((_DWORD *)this + 194) = 1;
      if ( !v10 )
      {
LABEL_13:
        v12 = *((_QWORD *)this + 9);
        if ( !v12 )
          return 0;
        if ( !(unsigned int)setResizerThreadClass(v12, v8, (char *)this + 264, *((unsigned int *)this + 195)) )
        {
          v13 = *((_QWORD *)this + 9);
          if ( v13 )
          {
            *(_DWORD *)(v13 + 204) = 1;
            return 0;
          }
        }
        return 2147500037LL;
      }
      if ( !(unsigned int)setResizerThreadClass(v10, v8, (char *)this + 264, a2) )
      {
        v11 = *((_QWORD *)this + 11);
        if ( v11 )
        {
          *(_DWORD *)(v11 + 204) = 1;
          goto LABEL_13;
        }
      }
    }
    return 2147500037LL;
  }
  return result;
}

```

## disassembly

```asm
0x180008440  mov     [rsp+arg_0], rbx
0x180008445  mov     [rsp+arg_8], rsi
0x18000844a  push    rdi
0x18000844b  sub     rsp, 20h
0x18000844f  mov     edi, edx
0x180008451  lea     r10, [rcx+108h]
0x180008458  mov     rbx, rcx
0x18000845b  mov     eax, 7FFFFFFEh
0x180008460  mov     r9d, 100h
0x180008466  test    rax, rax
0x180008469  jz      short loc_18000848A
0x18000846b  movzx   r11d, word ptr [r8]
0x18000846f  test    r11w, r11w
0x180008473  jz      short loc_18000848A
0x180008475  mov     [r10], r11w
0x180008479  add     r8, 2
0x18000847d  add     r10, 2
0x180008481  dec     rax
0x180008484  sub     r9, 1
0x180008488  jnz     short loc_180008466
0x18000848a  xor     ecx, ecx
0x18000848c  lea     rdx, [r10-2]
0x180008490  test    r9, r9
0x180008493  mov     eax, 8007007Ah
0x180008498  cmovnz  rdx, r10
0x18000849c  cmovnz  eax, ecx
0x18000849f  mov     [rdx], cx
0x1800084a2  jz      loc_180008539
0x1800084a8  test    edi, edi
0x1800084aa  jz      loc_180008534
0x1800084b0  mov     rcx, [rbx+58h]
0x1800084b4  mov     [rbx+30Ch], edi
0x1800084ba  mov     dword ptr [rbx+308h], 1
0x1800084c4  test    rcx, rcx
0x1800084c7  jz      short loc_1800084EF
0x1800084c9  mov     r9d, edi
0x1800084cc  lea     r8, [rbx+108h]
0x1800084d3  call    setResizerThreadClass
0x1800084d8  test    eax, eax
0x1800084da  jnz     short loc_180008534
0x1800084dc  mov     rax, [rbx+58h]
0x1800084e0  test    rax, rax
0x1800084e3  jz      short loc_180008534
0x1800084e5  mov     dword ptr [rax+0CCh], 1
0x1800084ef  mov     rcx, [rbx+48h]
0x1800084f3  test    rcx, rcx
0x1800084f6  jz      short loc_180008522
0x1800084f8  mov     r9d, [rbx+30Ch]
0x1800084ff  lea     r8, [rbx+108h]
0x180008506  call    setResizerThreadClass
0x18000850b  test    eax, eax
0x18000850d  jnz     short loc_180008534
0x18000850f  mov     rax, [rbx+48h]
0x180008513  test    rax, rax
0x180008516  jz      short loc_180008534
0x180008518  mov     dword ptr [rax+0CCh], 1
0x180008522  xor     eax, eax
0x180008524  mov     rbx, [rsp+28h+arg_0]
0x180008529  mov     rsi, [rsp+28h+arg_8]
0x18000852e  add     rsp, 20h
0x180008532  pop     rdi
0x180008533  retn
0x180008534  mov     eax, 80004005h
0x180008539  mov     rbx, [rsp+28h+arg_0]
0x18000853e  mov     rsi, [rsp+28h+arg_8]
0x180008543  add     rsp, 20h
0x180008547  pop     rdi
0x180008548  retn
```
