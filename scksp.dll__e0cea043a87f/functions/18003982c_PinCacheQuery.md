# PinCacheQuery

- ea: `0x18003982c`
- end: `0x18003998e`
- name: `PinCacheQuery`
- size: `354`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180039670`

## callees

- `0x180009e76`
- `0x180038e7c`
- `0x18003916c`
- `0x18003982c`

## import_xrefs

- `msvcrt!time` at `0x180039896`
- `msvcrt!time` at `0x180039896`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039960`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039960`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039950`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039950`

## pseudocode

```c
__int64 __fastcall PinCacheQuery(__int64 a1, int a2, __int64 a3, void *a4, _DWORD *a5, _DWORD *a6)
{
  _DWORD *v8; // rdi
  unsigned int v9; // ebx
  unsigned int v10; // eax
  unsigned int v11; // eax
  __int64 v12; // rbp
  _DWORD *v13; // r14
  _DWORD *v14; // rax
  int v15; // ecx
  _BYTE *v16; // rax
  __int64 v17; // rcx
  HANDLE ProcessHeap; // rax
  void *Src; // [rsp+20h] [rbp-28h] BYREF
  time_t Time; // [rsp+28h] [rbp-20h] BYREF
  size_t Size; // [rsp+50h] [rbp+8h] BYREF

  Src = 0;
  LODWORD(Size) = 0;
  Time = 0;
  if ( (unsigned int)(a2 - 1) > 7 )
    return 160;
  if ( a1 && (v8 = *(_DWORD **)(a1 + 8LL * (unsigned int)(a2 - 1))) != 0 )
  {
    if ( a3
      && *(_DWORD *)(a3 + 24) == 1
      && ((time(&Time), (unsigned int)Time < v8[10]) || (unsigned int)(Time - v8[10]) > v8[12]) )
    {
      return (unsigned int)-2146435022;
    }
    else
    {
      v10 = I_PinCacheLookup(v8);
      v9 = v10;
      if ( v10 )
      {
        if ( v10 == 4306 )
          *a5 = 0;
      }
      else
      {
        v11 = I_PinCacheDecryptPin(v8, &Src, &Size);
        v12 = (unsigned int)Size;
        v9 = v11;
        if ( !v11 )
        {
          v13 = a5;
          if ( a4 )
          {
            if ( *a5 < (unsigned int)Size )
              v9 = 234;
            else
              memcpy_0(a4, Src, (unsigned int)Size);
          }
          v14 = a6;
          v15 = v8[8];
          *v13 = v12;
          *v14 = v15;
        }
        if ( Src )
        {
          v16 = Src;
          v17 = v12;
          if ( (_DWORD)v12 )
          {
            do
            {
              *v16++ = 0;
              --v17;
            }
            while ( v17 );
          }
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, Src);
        }
      }
    }
    return v9;
  }
  else
  {
    *a5 = 0;
    return 4306;
  }
}

```

## disassembly

```asm
0x18003982c  mov     rax, rsp
0x18003982f  mov     [rax+10h], rbx
0x180039833  mov     [rax+18h], rbp
0x180039837  push    rdi
0x180039838  push    r14
0x18003983a  push    r15
0x18003983c  sub     rsp, 30h
0x180039840  mov     qword ptr [rax-28h], 0
0x180039848  mov     r15, r9
0x18003984b  mov     dword ptr [rax+8], 0
0x180039852  mov     qword ptr [rax-20h], 0
0x18003985a  lea     eax, [rdx-1]
0x18003985d  cmp     eax, 7
0x180039860  jbe     short loc_18003986C
0x180039862  mov     eax, 0A0h
0x180039867  jmp     loc_18003997A
0x18003986c  test    rcx, rcx
0x18003986f  jz      loc_18003996A
0x180039875  lea     eax, [rdx-1]
0x180039878  mov     rdi, [rcx+rax*8]
0x18003987c  test    rdi, rdi
0x18003987f  jz      loc_18003996A
0x180039885  test    r8, r8
0x180039888  jz      short loc_1800398B8
0x18003988a  cmp     dword ptr [r8+18h], 1
0x18003988f  jnz     short loc_1800398B8
0x180039891  lea     rcx, [rsp+48h+Time]; Time
0x180039896  call    cs:__imp_time
0x18003989c  mov     rax, [rsp+48h+Time]
0x1800398a1  cmp     eax, [rdi+28h]
0x1800398a4  jb      short loc_1800398AE
0x1800398a6  sub     eax, [rdi+28h]
0x1800398a9  cmp     eax, [rdi+30h]
0x1800398ac  jbe     short loc_1800398B8
0x1800398ae  mov     ebx, 80100032h
0x1800398b3  jmp     loc_180039966
0x1800398b8  mov     rcx, rdi
0x1800398bb  call    I_PinCacheLookup
0x1800398c0  mov     ebx, eax
0x1800398c2  test    eax, eax
0x1800398c4  jz      short loc_1800398E1
0x1800398c6  cmp     eax, 10D2h
0x1800398cb  jnz     loc_180039966
0x1800398d1  mov     rcx, [rsp+48h+arg_20]
0x1800398d6  mov     dword ptr [rcx], 0
0x1800398dc  jmp     loc_180039966
0x1800398e1  lea     r8, [rsp+48h+Size]
0x1800398e6  mov     rcx, rdi
0x1800398e9  lea     rdx, [rsp+48h+Src]
0x1800398ee  call    I_PinCacheDecryptPin
0x1800398f3  mov     ebp, dword ptr [rsp+48h+Size]
0x1800398f7  mov     ebx, eax
0x1800398f9  test    eax, eax
0x1800398fb  jnz     short loc_180039930
0x1800398fd  mov     r14, [rsp+48h+arg_20]
0x180039902  test    r15, r15
0x180039905  jz      short loc_180039923
0x180039907  cmp     [r14], ebp
0x18003990a  jb      short loc_18003991E
0x18003990c  mov     rdx, [rsp+48h+Src]; Src
0x180039911  mov     r8d, ebp; Size
0x180039914  mov     rcx, r15; void *
0x180039917  call    memcpy_0
0x18003991c  jmp     short loc_180039923
0x18003991e  mov     ebx, 0EAh
0x180039923  mov     rax, [rsp+48h+arg_28]
0x180039928  mov     ecx, [rdi+20h]
0x18003992b  mov     [r14], ebp
0x18003992e  mov     [rax], ecx
0x180039930  cmp     [rsp+48h+Src], 0
0x180039936  jz      short loc_180039966
0x180039938  mov     rax, [rsp+48h+Src]
0x18003993d  mov     rcx, rbp
0x180039940  test    ebp, ebp
0x180039942  jz      short loc_180039950
0x180039944  mov     byte ptr [rax], 0
0x180039947  inc     rax
0x18003994a  sub     rcx, 1
0x18003994e  jnz     short loc_180039944
0x180039950  call    cs:__imp_GetProcessHeap
0x180039956  mov     r8, [rsp+48h+Src]; lpMem
0x18003995b  xor     edx, edx; dwFlags
0x18003995d  mov     rcx, rax; hHeap
0x180039960  call    cs:__imp_HeapFree
0x180039966  mov     eax, ebx
0x180039968  jmp     short loc_18003997A
0x18003996a  mov     rax, [rsp+48h+arg_20]
0x18003996f  mov     dword ptr [rax], 0
0x180039975  mov     eax, 10D2h
0x18003997a  mov     rbx, [rsp+48h+arg_8]
0x18003997f  mov     rbp, [rsp+48h+arg_10]
0x180039984  add     rsp, 30h
0x180039988  pop     r15
0x18003998a  pop     r14
0x18003998c  pop     rdi
0x18003998d  retn
```
