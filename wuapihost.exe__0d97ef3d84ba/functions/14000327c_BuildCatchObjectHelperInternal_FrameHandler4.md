# BuildCatchObjectHelperInternal___FrameHandler4_

- ea: `0x14000327c`
- end: `0x140003470`
- name: `BuildCatchObjectHelperInternal___FrameHandler4_`
- size: `500`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x140003478`

## callees

- `0x140002a80`
- `0x140002a98`
- `0x140002c80`
- `0x14000327c`
- `0x1400056be`
- `0x1400059e0`
- `0x140005e20`

## pseudocode

```c
__int64 __fastcall BuildCatchObjectHelperInternal___FrameHandler4_(__int64 a1, void **a2, __int64 a3, __int64 a4)
{
  unsigned int v8; // edi
  __int64 v9; // r15
  __int64 v10; // rdx
  __int64 v11; // r15
  __int64 v12; // rcx
  void *v13; // rax
  void *v14; // rcx
  const void *v15; // rdx
  __int64 v16; // rbx
  __int64 v17; // rcx
  size_t v18; // rbx
  const void *v19; // rax
  __int64 v20; // rbx
  __int64 v21; // rcx

  v8 = 0;
  v9 = *(int *)(a3 + 8);
  if ( (_DWORD)v9 )
    v10 = v9 + GetImageBase();
  else
    v10 = 0;
  if ( v10 )
  {
    v11 = *(int *)(a3 + 8);
    v12 = (_DWORD)v11 ? v11 + GetImageBase() : 0LL;
    if ( *(_BYTE *)(v12 + 16) && (*(_DWORD *)(a3 + 12) || *(int *)(a3 + 4) < 0) )
    {
      if ( *(int *)(a3 + 4) >= 0 )
        a2 = (void **)((char *)*a2 + *(unsigned int *)(a3 + 12));
      if ( *(char *)(a3 + 4) < 0 && (*(_BYTE *)a4 & 0x10) != 0 && __WinRTOutOfMemoryExceptionCallback )
      {
        v13 = __WinRTOutOfMemoryExceptionCallback();
        if ( !v13 || !a2 )
          abort();
        *a2 = v13;
        v14 = v13;
      }
      else if ( (*(_BYTE *)(a3 + 4) & 8) != 0 )
      {
        v14 = *(void **)(a1 + 40);
        if ( !v14 || !a2 )
          abort();
        *a2 = v14;
      }
      else
      {
        if ( (*(_BYTE *)a4 & 1) == 0 )
        {
          v16 = *(int *)(a4 + 24);
          if ( (_DWORD)v16 )
            v17 = v16 + GetThrowImageBase();
          else
            v17 = 0;
          if ( v17 )
          {
            if ( !*(_QWORD *)(a1 + 40)
              || !a2
              || ((v20 = *(int *)(a4 + 24), !(_DWORD)v20) ? (v21 = 0) : (v21 = v20 + GetThrowImageBase()), !v21) )
            {
              abort();
            }
            return (unsigned int)((*(_BYTE *)a4 & 4) != 0) + 1;
          }
          else
          {
            if ( !*(_QWORD *)(a1 + 40) || !a2 )
              abort();
            v18 = *(int *)(a4 + 20);
            v19 = (const void *)_AdjustPointer(*(_QWORD *)(a1 + 40), a4 + 8);
            memmove(a2, v19, v18);
          }
          return v8;
        }
        v15 = *(const void **)(a1 + 40);
        if ( !v15 || !a2 )
          abort();
        memmove(a2, v15, *(int *)(a4 + 20));
        if ( *(_DWORD *)(a4 + 20) != 8 || !*a2 )
          return v8;
        v14 = *a2;
      }
      *a2 = (void *)_AdjustPointer(v14, a4 + 8);
      return v8;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14000327c  mov     [rsp+arg_0], rbx
0x140003281  mov     [rsp+arg_8], rsi
0x140003286  mov     [rsp+arg_10], rdi
0x14000328b  push    r13
0x14000328d  push    r14
0x14000328f  push    r15
0x140003291  sub     rsp, 30h
0x140003295  mov     r14, r9
0x140003298  mov     rbx, r8
0x14000329b  mov     rsi, rdx
0x14000329e  mov     r13, rcx
0x1400032a1  xor     edi, edi
0x1400032a3  movsxd  r15, dword ptr [r8+8]
0x1400032a7  test    r15d, r15d
0x1400032aa  jz      short loc_1400032B7
0x1400032ac  call    _GetImageBase
0x1400032b1  lea     rdx, [r15+rax]
0x1400032b5  jmp     short loc_1400032BA
0x1400032b7  mov     rdx, rdi
0x1400032ba  test    rdx, rdx
0x1400032bd  jz      loc_140003434
0x1400032c3  movsxd  r15, dword ptr [rbx+8]
0x1400032c7  test    r15d, r15d
0x1400032ca  jz      short loc_1400032D7
0x1400032cc  call    _GetImageBase
0x1400032d1  lea     rcx, [r15+rax]
0x1400032d5  jmp     short loc_1400032DA
0x1400032d7  mov     rcx, rdi
0x1400032da  cmp     [rcx+10h], dil
0x1400032de  jz      loc_140003434
0x1400032e4  cmp     [rbx+0Ch], edi
0x1400032e7  jnz     short loc_1400032F2
0x1400032e9  cmp     [rbx+4], edi
0x1400032ec  jge     loc_140003434
0x1400032f2  cmp     [rbx+4], edi
0x1400032f5  jl      short loc_140003300
0x1400032f7  mov     eax, [rbx+0Ch]
0x1400032fa  add     rax, [rsi]
0x1400032fd  mov     rsi, rax
0x140003300  test    byte ptr [rbx+4], 80h
0x140003304  jz      short loc_140003337
0x140003306  test    byte ptr [r14], 10h
0x14000330a  jz      short loc_140003337
0x14000330c  mov     rax, cs:?__WinRTOutOfMemoryExceptionCallback@@3P6APEAXXZEA; void * (*__WinRTOutOfMemoryExceptionCallback)(void)
0x140003313  test    rax, rax
0x140003316  jz      short loc_140003337
0x140003318  call    _guard_dispatch_icall
0x14000331d  test    rax, rax
0x140003320  jz      loc_140003450
0x140003326  test    rsi, rsi
0x140003329  jz      loc_140003450
0x14000332f  mov     [rsi], rax
0x140003332  mov     rcx, rax
0x140003335  jmp     short loc_140003397
0x140003337  test    byte ptr [rbx+4], 8
0x14000333b  jz      short loc_140003358
0x14000333d  mov     rcx, [r13+28h]
0x140003341  test    rcx, rcx
0x140003344  jz      loc_140003455
0x14000334a  test    rsi, rsi
0x14000334d  jz      loc_140003455
0x140003353  mov     [rsi], rcx
0x140003356  jmp     short loc_140003397
0x140003358  test    byte ptr [r14], 1
0x14000335c  jz      short loc_1400033A8
0x14000335e  mov     rdx, [r13+28h]; Src
0x140003362  test    rdx, rdx
0x140003365  jz      loc_14000345A
0x14000336b  test    rsi, rsi
0x14000336e  jz      loc_14000345A
0x140003374  movsxd  r8, dword ptr [r14+14h]; Size
0x140003378  mov     rcx, rsi; void *
0x14000337b  call    memmove
0x140003380  cmp     dword ptr [r14+14h], 8
0x140003385  jnz     loc_140003430
0x14000338b  cmp     [rsi], rdi
0x14000338e  jz      loc_140003430
0x140003394  mov     rcx, [rsi]
0x140003397  lea     rdx, [r14+8]
0x14000339b  call    __AdjustPointer
0x1400033a0  mov     [rsi], rax
0x1400033a3  jmp     loc_140003430
0x1400033a8  movsxd  rbx, dword ptr [r14+18h]
0x1400033ac  test    ebx, ebx
0x1400033ae  jz      short loc_1400033BB
0x1400033b0  call    _GetThrowImageBase
0x1400033b5  lea     rcx, [rbx+rax]
0x1400033b9  jmp     short loc_1400033BE
0x1400033bb  mov     rcx, rdi
0x1400033be  test    rcx, rcx
0x1400033c1  jnz     short loc_1400033F7
0x1400033c3  cmp     [r13+28h], rdi
0x1400033c7  jz      loc_14000345F
0x1400033cd  test    rsi, rsi
0x1400033d0  jz      loc_14000345F
0x1400033d6  movsxd  rbx, dword ptr [r14+14h]
0x1400033da  lea     rdx, [r14+8]
0x1400033de  mov     rcx, [r13+28h]
0x1400033e2  call    __AdjustPointer
0x1400033e7  mov     rdx, rax; Src
0x1400033ea  mov     r8, rbx; Size
0x1400033ed  mov     rcx, rsi; void *
0x1400033f0  call    memmove
0x1400033f5  jmp     short loc_140003430
0x1400033f7  cmp     [r13+28h], rdi
0x1400033fb  jz      short loc_140003464
0x1400033fd  test    rsi, rsi
0x140003400  jz      short loc_140003464
0x140003402  movsxd  rbx, dword ptr [r14+18h]
0x140003406  test    ebx, ebx
0x140003408  jz      short loc_140003415
0x14000340a  call    _GetThrowImageBase
0x14000340f  lea     rcx, [rbx+rax]
0x140003413  jmp     short loc_140003418
0x140003415  mov     rcx, rdi
0x140003418  test    rcx, rcx
0x14000341b  jz      short loc_140003464
0x14000341d  mov     al, [r14]
0x140003420  and     al, 4
0x140003422  neg     al
0x140003424  sbb     ecx, ecx
0x140003426  neg     ecx
0x140003428  inc     ecx
0x14000342a  mov     edi, ecx
0x14000342c  mov     [rsp+48h+var_28], ecx
0x140003430  mov     eax, edi
0x140003432  jmp     short loc_140003436
0x140003434  xor     eax, eax
0x140003436  mov     rbx, [rsp+48h+arg_0]
0x14000343b  mov     rsi, [rsp+48h+arg_8]
0x140003440  mov     rdi, [rsp+48h+arg_10]
0x140003445  add     rsp, 30h
0x140003449  pop     r15
0x14000344b  pop     r14
0x14000344d  pop     r13
0x14000344f  retn
0x140003450  call    abort
0x140003455  call    abort
0x14000345a  call    abort
0x14000345f  call    abort
0x140003464  call    abort
0x14000346a  call    abort
```
