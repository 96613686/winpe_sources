# CMFBaseStringT<ushort>::_EnsureSpace(long)

- ea: `0x140013120`
- end: `0x140013280`
- name: `?_EnsureSpace@?$CMFBaseStringT@G@@IEAAJJ@Z`
- size: `352`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `6`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x140011780`
- `0x140011874`
- `0x140012b30`
- `0x140013a20`
- `0x140098e50`
- `0x14009a474`

## callees

- `0x140013120`
- `0x14009ad10`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x14001316d`
- `KERNEL32!GetProcessHeap` at `0x1400131cb`
- `KERNEL32!GetProcessHeap` at `0x14001316d`
- `KERNEL32!GetProcessHeap` at `0x1400131cb`
- `KERNEL32!HeapFree` at `0x1400131d9`
- `KERNEL32!HeapFree` at `0x1400131d9`
- `KERNEL32!HeapAlloc` at `0x14001317b`
- `KERNEL32!HeapAlloc` at `0x14001317b`
- `ole32!CoTaskMemFree` at `0x140013275`
- `ole32!CoTaskMemFree` at `0x140013275`

## pseudocode

```c
__int64 __fastcall CMFBaseStringT<unsigned short>::_EnsureSpace(__int64 a1, unsigned int a2)
{
  __int64 result; // rax
  unsigned int v4; // esi
  SIZE_T v5; // rdi
  HANDLE ProcessHeap; // rax
  _WORD *v7; // rax
  _WORD *v8; // rdi
  const void *v9; // rdx
  unsigned int v10; // eax
  int v11; // r14d
  void *v12; // rbp
  int v13; // eax
  HANDLE v14; // rax
  __int64 v15; // rax

  result = *(unsigned int *)(a1 + 4);
  if ( (int)result >= 0 )
  {
    if ( a2 > 0x3FFFFFF )
    {
      *(_DWORD *)(a1 + 4) = -2147024785;
      return 2147942511LL;
    }
    else
    {
      v4 = a2 + 1;
      if ( (signed int)(a2 + 1) > *(_DWORD *)(a1 + 12) )
      {
        if ( (*(_DWORD *)a1 & 6) == 4 )
        {
          result = 2147942522LL;
          *(_DWORD *)(a1 + 4) = -2147024774;
          return result;
        }
        v5 = 2LL * (int)a2 + 2;
        ProcessHeap = GetProcessHeap();
        v7 = HeapAlloc(ProcessHeap, 0, v5);
        v8 = v7;
        if ( !v7 )
        {
          result = 2147942414LL;
          *(_DWORD *)(a1 + 8) = 0;
          *(_DWORD *)(a1 + 4) = -2147024882;
          return result;
        }
        v9 = *(const void **)(a1 + 16);
        if ( v9 )
        {
          memcpy_0(v7, v9, 2LL * *(int *)(a1 + 8));
          v10 = *(_DWORD *)a1;
          v11 = *(_DWORD *)(a1 + 8);
          if ( (*(_DWORD *)a1 & 1) == 0 )
          {
            v12 = *(void **)(a1 + 16);
            if ( v12 )
            {
              v13 = *(_DWORD *)a1 & 6;
              if ( v13 )
              {
                if ( v13 == 2 )
                  CoTaskMemFree(*(LPVOID *)(a1 + 16));
              }
              else
              {
                v14 = GetProcessHeap();
                HeapFree(v14, 0, v12);
              }
            }
            v10 = *(_DWORD *)a1 & 0xFFFFFFF9;
          }
          *(_DWORD *)(a1 + 8) = v11;
          *(_DWORD *)a1 = v10 & 0xFFFFFFFE;
        }
        v15 = *(int *)(a1 + 8);
        *(_QWORD *)(a1 + 16) = v8;
        *(_DWORD *)(a1 + 12) = v4;
        v8[v15] = 0;
      }
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140013120  push    rbx
0x140013122  sub     rsp, 20h
0x140013126  mov     eax, [rcx+4]
0x140013129  mov     rbx, rcx
0x14001312c  test    eax, eax
0x14001312e  js      loc_140013214
0x140013134  cmp     edx, 3FFFFFFh
0x14001313a  ja      loc_140013257
0x140013140  mov     [rsp+28h+arg_8], rsi
0x140013145  lea     esi, [rdx+1]
0x140013148  mov     [rsp+28h+arg_10], rdi
0x14001314d  cmp     esi, [rcx+0Ch]
0x140013150  jle     loc_140013208
0x140013156  mov     eax, [rcx]
0x140013158  and     al, 6
0x14001315a  cmp     al, 4
0x14001315c  jz      loc_14001321A
0x140013162  movsxd  rax, edx
0x140013165  lea     rdi, ds:2[rax*2]
0x14001316d  call    cs:__imp_GetProcessHeap
0x140013173  mov     r8, rdi; dwBytes
0x140013176  xor     edx, edx; dwFlags
0x140013178  mov     rcx, rax; hHeap
0x14001317b  call    cs:__imp_HeapAlloc
0x140013181  mov     rdi, rax
0x140013184  test    rax, rax
0x140013187  jz      loc_140013236
0x14001318d  mov     rdx, [rbx+10h]; Src
0x140013191  test    rdx, rdx
0x140013194  jz      short loc_1400131F7
0x140013196  movsxd  r8, dword ptr [rbx+8]
0x14001319a  mov     rcx, rax; void *
0x14001319d  add     r8, r8; Size
0x1400131a0  mov     [rsp+28h+arg_18], r14
0x1400131a5  call    memcpy_0
0x1400131aa  mov     eax, [rbx]
0x1400131ac  mov     r14d, [rbx+8]
0x1400131b0  test    al, 1
0x1400131b2  jnz     short loc_1400131E9
0x1400131b4  mov     [rsp+28h+arg_0], rbp
0x1400131b9  mov     rbp, [rbx+10h]
0x1400131bd  test    rbp, rbp
0x1400131c0  jz      short loc_1400131DF
0x1400131c2  and     eax, 6
0x1400131c5  jnz     loc_140013269
0x1400131cb  call    cs:__imp_GetProcessHeap
0x1400131d1  mov     r8, rbp; lpMem
0x1400131d4  xor     edx, edx; dwFlags
0x1400131d6  mov     rcx, rax; hHeap
0x1400131d9  call    cs:__imp_HeapFree
0x1400131df  mov     eax, [rbx]
0x1400131e1  mov     rbp, [rsp+28h+arg_0]
0x1400131e6  and     eax, 0FFFFFFF9h
0x1400131e9  and     eax, 0FFFFFFFEh
0x1400131ec  mov     [rbx+8], r14d
0x1400131f0  mov     r14, [rsp+28h+arg_18]
0x1400131f5  mov     [rbx], eax
0x1400131f7  movsxd  rax, dword ptr [rbx+8]
0x1400131fb  xor     ecx, ecx
0x1400131fd  mov     [rbx+10h], rdi
0x140013201  mov     [rbx+0Ch], esi
0x140013204  mov     [rdi+rax*2], cx
0x140013208  mov     rdi, [rsp+28h+arg_10]
0x14001320d  xor     eax, eax
0x14001320f  mov     rsi, [rsp+28h+arg_8]
0x140013214  add     rsp, 20h
0x140013218  pop     rbx
0x140013219  retn
0x14001321a  mov     rdi, [rsp+28h+arg_10]
0x14001321f  mov     eax, 8007007Ah
0x140013224  mov     rsi, [rsp+28h+arg_8]
0x140013229  mov     dword ptr [rcx+4], 8007007Ah
0x140013230  add     rsp, 20h
0x140013234  pop     rbx
0x140013235  retn
0x140013236  mov     rdi, [rsp+28h+arg_10]
0x14001323b  xor     ecx, ecx
0x14001323d  mov     rsi, [rsp+28h+arg_8]
0x140013242  mov     eax, 8007000Eh
0x140013247  mov     [rbx+8], ecx
0x14001324a  mov     dword ptr [rbx+4], 8007000Eh
0x140013251  add     rsp, 20h
0x140013255  pop     rbx
0x140013256  retn
0x140013257  mov     dword ptr [rcx+4], 8007006Fh
0x14001325e  mov     eax, 8007006Fh
0x140013263  add     rsp, 20h
0x140013267  pop     rbx
0x140013268  retn
0x140013269  cmp     eax, 2
0x14001326c  jnz     loc_1400131DF
0x140013272  mov     rcx, rbp; pv
0x140013275  call    cs:__imp_CoTaskMemFree
0x14001327b  jmp     loc_1400131DF
```
