# ComputeGssBindHash

- ea: `0x1800339e8`
- end: `0x180033ba8`
- name: `ComputeGssBindHash`
- size: `448`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180034398`
- `0x180034434`

## callees

- `0x1800339e8`
- `0x180038010`

## import_xrefs

- `cryptdll!CDLocateCheckSum` at `0x180033a1a`
- `cryptdll!CDLocateCheckSum` at `0x180033a1a`

## pseudocode

```c
__int64 __fastcall ComputeGssBindHash(unsigned int *a1, __int64 a2)
{
  int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // rdx
  __int64 v7; // rdx
  __int64 v9; // [rsp+60h] [rbp+40h] BYREF
  __int64 v10; // [rsp+68h] [rbp+48h] BYREF

  v9 = 0;
  v10 = 0;
  v4 = CDLocateCheckSum(7, &v9);
  if ( v4 >= 0 )
  {
    v4 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(v9 + 16))(0, &v10);
    if ( v4 >= 0 )
    {
      v4 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(v9 + 24))(v10, 4, a1 + 4);
      if ( v4 >= 0 )
      {
        v4 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(v9 + 24))(v10, 4, a1 + 5);
        if ( v4 >= 0 )
        {
          v5 = a1[5];
          if ( !(_DWORD)v5
            || (v4 = (*(__int64 (__fastcall **)(__int64, __int64, char *))(v9 + 24))(v10, v5, (char *)a1 + a1[6]),
                v4 >= 0) )
          {
            v4 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(v9 + 24))(v10, 4, a1 + 7);
            if ( v4 >= 0 )
            {
              v4 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(v9 + 24))(v10, 4, a1 + 8);
              if ( v4 >= 0 )
              {
                v6 = a1[8];
                if ( !(_DWORD)v6
                  || (v4 = (*(__int64 (__fastcall **)(__int64, __int64, char *))(v9 + 24))(v10, v6, (char *)a1 + a1[9]),
                      v4 >= 0) )
                {
                  v4 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(v9 + 24))(v10, 4, a1 + 10);
                  if ( v4 >= 0 )
                  {
                    v7 = a1[10];
                    if ( !(_DWORD)v7
                      || (v4 = (*(__int64 (__fastcall **)(__int64, __int64, char *))(v9 + 24))(
                                 v10,
                                 v7,
                                 (char *)a1 + a1[11]),
                          v4 >= 0) )
                    {
                      v4 = (*(__int64 (__fastcall **)(__int64, __int64))(v9 + 32))(v10, a2);
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  if ( v9 && v10 )
    (*(void (__fastcall **)(__int64 *))(v9 + 40))(&v10);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800339e8  mov     [rsp-28h+arg_0], rbx
0x1800339ed  push    rbp
0x1800339ee  push    rsi
0x1800339ef  push    rdi
0x1800339f0  push    r12
0x1800339f2  push    r14
0x1800339f4  mov     rbp, rsp
0x1800339f7  sub     rsp, 20h
0x1800339fb  mov     r14, rdx
0x1800339fe  mov     [rbp+arg_10], 0
0x180033a06  mov     rdi, rcx
0x180033a09  mov     [rbp+arg_18], 0
0x180033a11  lea     rdx, [rbp+arg_10]
0x180033a15  mov     ecx, 7
0x180033a1a  call    cs:__imp_CDLocateCheckSum
0x180033a20  mov     ebx, eax
0x180033a22  test    eax, eax
0x180033a24  js      loc_180033B78
0x180033a2a  mov     rax, [rbp+arg_10]
0x180033a2e  lea     rdx, [rbp+arg_18]
0x180033a32  xor     ecx, ecx
0x180033a34  mov     rax, [rax+10h]
0x180033a38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033a3d  mov     ebx, eax
0x180033a3f  test    eax, eax
0x180033a41  js      loc_180033B78
0x180033a47  mov     rax, [rbp+arg_10]
0x180033a4b  lea     r8, [rdi+10h]
0x180033a4f  mov     rcx, [rbp+arg_18]
0x180033a53  mov     r12d, 4
0x180033a59  mov     edx, r12d
0x180033a5c  mov     rax, [rax+18h]
0x180033a60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033a65  mov     ebx, eax
0x180033a67  test    eax, eax
0x180033a69  js      loc_180033B78
0x180033a6f  mov     rax, [rbp+arg_10]
0x180033a73  lea     r8, [rdi+14h]
0x180033a77  mov     rcx, [rbp+arg_18]
0x180033a7b  mov     edx, r12d
0x180033a7e  mov     rax, [rax+18h]
0x180033a82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033a87  mov     ebx, eax
0x180033a89  test    eax, eax
0x180033a8b  js      loc_180033B78
0x180033a91  mov     edx, [rdi+14h]
0x180033a94  test    edx, edx
0x180033a96  jz      short loc_180033ABA
0x180033a98  mov     rax, [rbp+arg_10]
0x180033a9c  mov     r8d, [rdi+18h]
0x180033aa0  mov     rcx, [rbp+arg_18]
0x180033aa4  add     r8, rdi
0x180033aa7  mov     rax, [rax+18h]
0x180033aab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033ab0  mov     ebx, eax
0x180033ab2  test    eax, eax
0x180033ab4  js      loc_180033B78
0x180033aba  mov     rax, [rbp+arg_10]
0x180033abe  lea     r8, [rdi+1Ch]
0x180033ac2  mov     rcx, [rbp+arg_18]
0x180033ac6  mov     edx, r12d
0x180033ac9  mov     rax, [rax+18h]
0x180033acd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033ad2  mov     ebx, eax
0x180033ad4  test    eax, eax
0x180033ad6  js      loc_180033B78
0x180033adc  mov     rax, [rbp+arg_10]
0x180033ae0  lea     r8, [rdi+20h]
0x180033ae4  mov     rcx, [rbp+arg_18]
0x180033ae8  mov     edx, r12d
0x180033aeb  mov     rax, [rax+18h]
0x180033aef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033af4  mov     ebx, eax
0x180033af6  test    eax, eax
0x180033af8  js      short loc_180033B78
0x180033afa  mov     edx, [rdi+20h]
0x180033afd  test    edx, edx
0x180033aff  jz      short loc_180033B1F
0x180033b01  mov     rax, [rbp+arg_10]
0x180033b05  mov     r8d, [rdi+24h]
0x180033b09  mov     rcx, [rbp+arg_18]
0x180033b0d  add     r8, rdi
0x180033b10  mov     rax, [rax+18h]
0x180033b14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033b19  mov     ebx, eax
0x180033b1b  test    eax, eax
0x180033b1d  js      short loc_180033B78
0x180033b1f  mov     rax, [rbp+arg_10]
0x180033b23  lea     r8, [rdi+28h]
0x180033b27  mov     rcx, [rbp+arg_18]
0x180033b2b  mov     edx, r12d
0x180033b2e  mov     rax, [rax+18h]
0x180033b32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033b37  mov     ebx, eax
0x180033b39  test    eax, eax
0x180033b3b  js      short loc_180033B78
0x180033b3d  mov     edx, [rdi+28h]
0x180033b40  test    edx, edx
0x180033b42  jz      short loc_180033B62
0x180033b44  mov     rax, [rbp+arg_10]
0x180033b48  mov     r8d, [rdi+2Ch]
0x180033b4c  mov     rcx, [rbp+arg_18]
0x180033b50  add     r8, rdi
0x180033b53  mov     rax, [rax+18h]
0x180033b57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033b5c  mov     ebx, eax
0x180033b5e  test    eax, eax
0x180033b60  js      short loc_180033B78
0x180033b62  mov     rax, [rbp+arg_10]
0x180033b66  mov     rdx, r14
0x180033b69  mov     rcx, [rbp+arg_18]
0x180033b6d  mov     rax, [rax+20h]
0x180033b71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033b76  mov     ebx, eax
0x180033b78  mov     rax, [rbp+arg_10]
0x180033b7c  test    rax, rax
0x180033b7f  jz      short loc_180033B95
0x180033b81  cmp     [rbp+arg_18], 0
0x180033b86  jz      short loc_180033B95
0x180033b88  mov     rax, [rax+28h]
0x180033b8c  lea     rcx, [rbp+arg_18]
0x180033b90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033b95  mov     eax, ebx
0x180033b97  mov     rbx, [rsp+20h+arg_0]
0x180033b9c  add     rsp, 20h
0x180033ba0  pop     r14
0x180033ba2  pop     r12
0x180033ba4  pop     rdi
0x180033ba5  pop     rsi
0x180033ba6  pop     rbp
0x180033ba7  retn
```
