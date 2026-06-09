# CMFBaseStringT<ushort>::AppendByte(uchar)

- ea: `0x140029a90`
- end: `0x140029c79`
- name: `?AppendByte@?$CMFBaseStringT@G@@QEAAJE@Z`
- size: `489`
- prototype: `__int64 __fastcall(__int64, unsigned __int8)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x14006982c`

## callees

- `0x140029a90`
- `0x14002eda0`
- `0x14009ad10`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x140029ae9`
- `KERNEL32!GetProcessHeap` at `0x140029b3c`
- `KERNEL32!GetProcessHeap` at `0x140029ae9`
- `KERNEL32!GetProcessHeap` at `0x140029b3c`
- `KERNEL32!HeapFree` at `0x140029b4a`
- `KERNEL32!HeapFree` at `0x140029b4a`
- `KERNEL32!HeapAlloc` at `0x140029af7`
- `KERNEL32!HeapAlloc` at `0x140029af7`
- `ole32!CoTaskMemFree` at `0x140029c22`
- `ole32!CoTaskMemFree` at `0x140029c22`

## pseudocode

```c
__int64 __fastcall CMFBaseStringT<unsigned short>::AppendByte(__int64 a1, unsigned __int8 a2)
{
  unsigned __int64 v2; // r15
  int v4; // esi
  HANDLE ProcessHeap; // rax
  _WORD *v6; // rax
  _WORD *v7; // r14
  const void *v8; // rdx
  unsigned int v9; // eax
  int v10; // ebp
  void *v11; // rbx
  int v12; // eax
  HANDLE v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rcx
  int v16; // r8d
  __int64 v17; // rax
  unsigned __int64 v19; // rcx
  int v20; // [rsp+50h] [rbp+8h] BYREF

  v2 = a2;
  if ( *(int *)(a1 + 4) >= 0 )
  {
    v4 = *(_DWORD *)(a1 + 8) + 3;
    if ( (unsigned int)(*(_DWORD *)(a1 + 8) + 2) > 0x3FFFFFF )
    {
      *(_DWORD *)(a1 + 4) = -2147024785;
    }
    else
    {
      if ( v4 <= *(_DWORD *)(a1 + 12) )
        goto LABEL_14;
      if ( (*(_DWORD *)a1 & 6) == 4 )
      {
        *(_DWORD *)(a1 + 4) = -2147024774;
      }
      else
      {
        ProcessHeap = GetProcessHeap();
        v6 = HeapAlloc(ProcessHeap, 0, 2LL * v4);
        v7 = v6;
        if ( v6 )
        {
          v8 = *(const void **)(a1 + 16);
          if ( v8 )
          {
            memcpy_0(v6, v8, 2LL * *(int *)(a1 + 8));
            v9 = *(_DWORD *)a1;
            v10 = *(_DWORD *)(a1 + 8);
            if ( (*(_DWORD *)a1 & 1) == 0 )
            {
              v11 = *(void **)(a1 + 16);
              if ( v11 )
              {
                v12 = *(_DWORD *)a1 & 6;
                if ( v12 )
                {
                  if ( v12 == 2 )
                    CoTaskMemFree(*(LPVOID *)(a1 + 16));
                }
                else
                {
                  v13 = GetProcessHeap();
                  HeapFree(v13, 0, v11);
                }
              }
              v9 = *(_DWORD *)a1 & 0xFFFFFFF9;
            }
            *(_DWORD *)(a1 + 8) = v10;
            *(_DWORD *)a1 = v9 & 0xFFFFFFFE;
          }
          v14 = *(int *)(a1 + 8);
          *(_QWORD *)(a1 + 16) = v7;
          *(_DWORD *)(a1 + 12) = v4;
          v7[v14] = 0;
LABEL_14:
          *(_WORD *)(*(_QWORD *)(a1 + 16) + 2LL * *(int *)(a1 + 8)) = `CMFBaseStringT<unsigned short>::AppendByte'::`2'::b2c[v2 >> 4];
          *(_WORD *)(*(_QWORD *)(a1 + 16) + 2LL * *(int *)(a1 + 8) + 2) = `CMFBaseStringT<unsigned short>::AppendByte'::`2'::b2c[v2 & 0xF];
          v15 = *(int *)(a1 + 8);
          v16 = v15 + 2;
          v20 = v15 + 2;
          if ( *(int *)(a1 + 4) < 0 )
            return 0;
          v17 = *(int *)(a1 + 12);
          if ( v16 < 0 )
          {
            if ( (int)v17 <= 0 )
            {
              v16 = 0;
              goto LABEL_18;
            }
            *(_WORD *)(*(_QWORD *)(a1 + 16) + 2 * v17 - 2) = 0;
            v19 = -1;
            do
              ++v19;
            while ( *(_WORD *)(*(_QWORD *)(a1 + 16) + 2 * v19) );
            if ( (int)UIntPtrToLong(v19, &v20) >= 0 )
            {
              v16 = v20;
              goto LABEL_18;
            }
          }
          else if ( v16 < (int)v17 )
          {
            *(_WORD *)(*(_QWORD *)(a1 + 16) + 2 * v15 + 4) = 0;
LABEL_18:
            *(_DWORD *)(a1 + 8) = v16;
            return 0;
          }
          *(_DWORD *)(a1 + 4) = -2147024785;
          return 0;
        }
        *(_DWORD *)(a1 + 8) = 0;
        *(_DWORD *)(a1 + 4) = -2147024882;
      }
    }
  }
  return *(unsigned int *)(a1 + 4);
}

```

## disassembly

```asm
0x140029a90  mov     [rsp+arg_8], rbx
0x140029a95  mov     [rsp+arg_10], rbp
0x140029a9a  push    rsi
0x140029a9b  push    rdi
0x140029a9c  push    r12
0x140029a9e  push    r14
0x140029aa0  push    r15
0x140029aa2  sub     rsp, 20h
0x140029aa6  xor     r12d, r12d
0x140029aa9  movzx   r15d, dl
0x140029aad  mov     rdi, rcx
0x140029ab0  cmp     [rcx+4], r12d
0x140029ab4  jl      loc_140029BFB
0x140029aba  mov     esi, [rcx+8]
0x140029abd  add     esi, 3
0x140029ac0  lea     eax, [rsi-1]
0x140029ac3  cmp     eax, 3FFFFFFh
0x140029ac8  ja      loc_140029C0D
0x140029ace  cmp     esi, [rcx+0Ch]
0x140029ad1  jle     loc_140029B6D
0x140029ad7  mov     eax, [rcx]
0x140029ad9  and     al, 6
0x140029adb  cmp     al, 4
0x140029add  jz      loc_140029BF4
0x140029ae3  movsxd  rbx, esi
0x140029ae6  add     rbx, rbx
0x140029ae9  call    cs:__imp_GetProcessHeap
0x140029aef  mov     r8, rbx; dwBytes
0x140029af2  xor     edx, edx; dwFlags
0x140029af4  mov     rcx, rax; hHeap
0x140029af7  call    cs:__imp_HeapAlloc
0x140029afd  mov     r14, rax
0x140029b00  test    rax, rax
0x140029b03  jz      loc_140029C00
0x140029b09  mov     rdx, [rdi+10h]; Src
0x140029b0d  test    rdx, rdx
0x140029b10  jz      short loc_140029B5D
0x140029b12  movsxd  r8, dword ptr [rdi+8]
0x140029b16  mov     rcx, rax; void *
0x140029b19  add     r8, r8; Size
0x140029b1c  call    memcpy_0
0x140029b21  mov     eax, [rdi]
0x140029b23  mov     ebp, [rdi+8]
0x140029b26  test    al, 1
0x140029b28  jnz     short loc_140029B55
0x140029b2a  mov     rbx, [rdi+10h]
0x140029b2e  test    rbx, rbx
0x140029b31  jz      short loc_140029B50
0x140029b33  and     eax, 6
0x140029b36  jnz     loc_140029C16
0x140029b3c  call    cs:__imp_GetProcessHeap
0x140029b42  mov     r8, rbx; lpMem
0x140029b45  xor     edx, edx; dwFlags
0x140029b47  mov     rcx, rax; hHeap
0x140029b4a  call    cs:__imp_HeapFree
0x140029b50  mov     eax, [rdi]
0x140029b52  and     eax, 0FFFFFFF9h
0x140029b55  and     eax, 0FFFFFFFEh
0x140029b58  mov     [rdi+8], ebp
0x140029b5b  mov     [rdi], eax
0x140029b5d  movsxd  rcx, dword ptr [rdi+8]
0x140029b61  mov     [rdi+10h], r14
0x140029b65  mov     [rdi+0Ch], esi
0x140029b68  mov     [r14+rcx*2], r12w
0x140029b6d  movsxd  rcx, dword ptr [rdi+8]
0x140029b71  lea     r9, ?b2c@?1??AppendByte@?$CMFBaseStringT@G@@QEAAJE@Z@4QBDB; "0123456789abcdef&"
0x140029b78  mov     r8, r15
0x140029b7b  mov     rax, r15
0x140029b7e  shr     rax, 4
0x140029b82  and     r8d, 0Fh
0x140029b86  movsx   edx, byte ptr [rax+r9]
0x140029b8b  mov     rax, [rdi+10h]
0x140029b8f  mov     [rax+rcx*2], dx
0x140029b93  movsxd  rcx, dword ptr [rdi+8]
0x140029b97  movsx   edx, byte ptr [r8+r9]
0x140029b9c  mov     rax, [rdi+10h]
0x140029ba0  mov     [rax+rcx*2+2], dx
0x140029ba5  movsxd  rcx, dword ptr [rdi+8]
0x140029ba9  lea     r8d, [rcx+2]
0x140029bad  mov     [rsp+48h+arg_0], r8d
0x140029bb2  cmp     [rdi+4], r12d
0x140029bb6  jl      short loc_140029BDB
0x140029bb8  movsxd  rax, dword ptr [rdi+0Ch]
0x140029bbc  test    r8d, r8d
0x140029bbf  js      short loc_140029C2D
0x140029bc1  cmp     r8d, eax
0x140029bc4  jge     loc_140029C65
0x140029bca  mov     rdx, rcx
0x140029bcd  mov     rcx, [rdi+10h]
0x140029bd1  mov     [rcx+rdx*2+4], r12w
0x140029bd7  mov     [rdi+8], r8d
0x140029bdb  xor     eax, eax
0x140029bdd  mov     rbx, [rsp+48h+arg_8]
0x140029be2  mov     rbp, [rsp+48h+arg_10]
0x140029be7  add     rsp, 20h
0x140029beb  pop     r15
0x140029bed  pop     r14
0x140029bef  pop     r12
0x140029bf1  pop     rdi
0x140029bf2  pop     rsi
0x140029bf3  retn
0x140029bf4  mov     dword ptr [rcx+4], 8007007Ah
0x140029bfb  mov     eax, [rdi+4]
0x140029bfe  jmp     short loc_140029BDD
0x140029c00  mov     [rdi+8], r12d
0x140029c04  mov     dword ptr [rdi+4], 8007000Eh
0x140029c0b  jmp     short loc_140029BFB
0x140029c0d  mov     dword ptr [rcx+4], 8007006Fh
0x140029c14  jmp     short loc_140029BFB
0x140029c16  cmp     eax, 2
0x140029c19  jnz     loc_140029B50
0x140029c1f  mov     rcx, rbx; pv
0x140029c22  call    cs:__imp_CoTaskMemFree
0x140029c28  jmp     loc_140029B50
0x140029c2d  test    eax, eax
0x140029c2f  jle     short loc_140029C71
0x140029c31  mov     rcx, [rdi+10h]
0x140029c35  mov     [rcx+rax*2-2], r12w
0x140029c3b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140029c3f  mov     rax, [rdi+10h]
0x140029c43  inc     rcx; unsigned __int64
0x140029c46  cmp     [rax+rcx*2], r12w
0x140029c4b  jnz     short loc_140029C43
0x140029c4d  lea     rdx, [rsp+48h+arg_0]; int *
0x140029c52  call    ?UIntPtrToLong@@YAJ_KPEAJ@Z; UIntPtrToLong(unsigned __int64,long *)
0x140029c57  test    eax, eax
0x140029c59  js      short loc_140029C65
0x140029c5b  mov     r8d, [rsp+48h+arg_0]
0x140029c60  jmp     loc_140029BD7
0x140029c65  mov     dword ptr [rdi+4], 8007006Fh
0x140029c6c  jmp     loc_140029BDB
0x140029c71  mov     r8d, r12d
0x140029c74  jmp     loc_140029BD7
```
