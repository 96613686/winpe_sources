# SkpInstallEncryptionKey

- ea: `0x1400bacac`
- end: `0x1400bae2f`
- name: `SkpInstallEncryptionKey`
- size: `387`
- prototype: `__int64 __fastcall(int, int, int, int, int, void *Src, size_t Size)`
- caller_count: `3`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x1400bacac`
- `0x1400baf28`
- `0x1400bf1ec`

## callees

- `0x14000f0f0`
- `0x140037e68`
- `0x1400bacac`
- `0x1400bf8e4`
- `0x1400bf9c0`
- `0x1400bfc44`
- `0x1400f9780`

## pseudocode

```c
__int64 __fastcall SkpInstallEncryptionKey(
        unsigned int a1,
        __int64 a2,
        UCHAR *a3,
        ULONG a4,
        int a5,
        void *Src,
        size_t Size)
{
  int v12; // esi
  __int64 Pool; // rax
  __int64 v14; // rdi
  unsigned int v15; // ebx
  unsigned int v16; // ebx

  if ( !SkpEncryptCrashData )
    return 3221225659LL;
  if ( Size <= 0x14 )
  {
    if ( a2 )
    {
      if ( *(_QWORD *)(a2 + 72) )
        SkFinalizePageEncryption(a2);
      v12 = SkPageEncryptionRegisterPublicKey(a1, a3, a4, 0);
      if ( v12 >= 0 )
      {
        v12 = SkPreparePageEncryption(a1, 0, a2, 0, 0, 0, 0);
        if ( v12 >= 0 )
        {
          *(_DWORD *)(a2 + 612) = a5;
          memmove((void *)(a2 + 592), Src, Size);
        }
      }
    }
    else
    {
      Pool = SkAllocatePool(512, 0x2E8u);
      v14 = Pool;
      if ( Pool )
      {
        v12 = SkpInstallEncryptionKey(a1, Pool, (int)a3, a4, a5, Src, Size);
        if ( v12 >= 0 )
        {
          v15 = a1 - 1;
          if ( v15 )
          {
            v16 = v15 - 1;
            if ( v16 )
            {
              if ( v16 == 4 )
                qword_14016B548 = v14;
              else
                qword_14016B550 = v14;
            }
            else
            {
              qword_14016B540 = v14;
            }
          }
          else
          {
            qword_14016B538 = v14;
          }
        }
        else
        {
          SkFreePool(512, v14);
        }
      }
      else
      {
        return (unsigned int)-1073741670;
      }
    }
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1400bacac  push    rbx
0x1400bacae  push    rbp
0x1400bacaf  push    rsi
0x1400bacb0  push    rdi
0x1400bacb1  push    r14
0x1400bacb3  sub     rsp, 40h
0x1400bacb7  mov     eax, cs:SkpEncryptCrashData
0x1400bacbd  mov     rsi, r9
0x1400bacc0  mov     r14, r8
0x1400bacc3  mov     rdi, rdx
0x1400bacc6  mov     ebx, ecx
0x1400bacc8  test    eax, eax
0x1400bacca  jnz     short loc_1400BACD6
0x1400baccc  mov     eax, 0C00000BBh
0x1400bacd1  jmp     loc_1400BAE23
0x1400bacd6  mov     rbp, [rsp+68h+Size]
0x1400bacde  cmp     rbp, 14h
0x1400bace2  jbe     short loc_1400BACEE
0x1400bace4  mov     esi, 0C000000Dh
0x1400bace9  jmp     loc_1400BAE21
0x1400bacee  test    rdi, rdi
0x1400bacf1  jnz     loc_1400BADA8
0x1400bacf7  mov     edx, 2E8h
0x1400bacfc  mov     ecx, 200h
0x1400bad01  mov     r8d, 45626948h
0x1400bad07  call    SkAllocatePool
0x1400bad0c  mov     rdi, rax
0x1400bad0f  test    rax, rax
0x1400bad12  jnz     short loc_1400BAD1E
0x1400bad14  mov     esi, 0C000009Ah
0x1400bad19  jmp     loc_1400BAE21
0x1400bad1e  mov     rax, [rsp+68h+Src]
0x1400bad26  mov     r9, rsi; int
0x1400bad29  mov     [rsp+68h+var_30], 0
0x1400bad32  mov     r8, r14; int
0x1400bad35  mov     [rsp+68h+var_38], rbp; Size
0x1400bad3a  mov     rdx, rdi; int
0x1400bad3d  mov     [rsp+68h+var_40], rax; Src
0x1400bad42  mov     ecx, ebx; int
0x1400bad44  mov     eax, [rsp+68h+arg_20]
0x1400bad4b  mov     [rsp+68h+var_48], eax; int
0x1400bad4f  call    SkpInstallEncryptionKey
0x1400bad54  mov     esi, eax
0x1400bad56  test    eax, eax
0x1400bad58  jns     short loc_1400BAD6C
0x1400bad5a  mov     rdx, rdi
0x1400bad5d  mov     ecx, 200h
0x1400bad62  call    SkFreePool
0x1400bad67  jmp     loc_1400BAE21
0x1400bad6c  sub     ebx, 1
0x1400bad6f  jz      short loc_1400BAD9F
0x1400bad71  sub     ebx, 1
0x1400bad74  jz      short loc_1400BAD93
0x1400bad76  cmp     ebx, 4
0x1400bad79  jz      short loc_1400BAD87
0x1400bad7b  mov     cs:qword_14016B550, rdi
0x1400bad82  jmp     loc_1400BAE21
0x1400bad87  mov     cs:qword_14016B548, rdi
0x1400bad8e  jmp     loc_1400BAE21
0x1400bad93  mov     cs:qword_14016B540, rdi
0x1400bad9a  jmp     loc_1400BAE21
0x1400bad9f  mov     cs:qword_14016B538, rdi
0x1400bada6  jmp     short loc_1400BAE21
0x1400bada8  cmp     qword ptr [rdx+48h], 0
0x1400badad  jz      short loc_1400BADB7
0x1400badaf  mov     rcx, rdi
0x1400badb2  call    SkFinalizePageEncryption
0x1400badb7  xor     r9d, r9d
0x1400badba  mov     r8, rsi
0x1400badbd  mov     rdx, r14
0x1400badc0  mov     ecx, ebx
0x1400badc2  call    SkPageEncryptionRegisterPublicKey
0x1400badc7  mov     esi, eax
0x1400badc9  test    eax, eax
0x1400badcb  js      short loc_1400BAE21
0x1400badcd  mov     [rsp+68h+var_38], 0
0x1400badd6  xor     r9d, r9d
0x1400badd9  mov     [rsp+68h+var_40], 0
0x1400bade2  mov     r8, rdi
0x1400bade5  xor     edx, edx
0x1400bade7  mov     qword ptr [rsp+68h+var_48], 0
0x1400badf0  mov     ecx, ebx
0x1400badf2  call    SkPreparePageEncryption
0x1400badf7  mov     esi, eax
0x1400badf9  test    eax, eax
0x1400badfb  js      short loc_1400BAE21
0x1400badfd  mov     eax, [rsp+68h+arg_20]
0x1400bae04  lea     rcx, [rdi+250h]; void *
0x1400bae0b  mov     rdx, [rsp+68h+Src]; Src
0x1400bae13  mov     r8, rbp; Size
0x1400bae16  mov     [rdi+264h], eax
0x1400bae1c  call    memmove
0x1400bae21  mov     eax, esi
0x1400bae23  add     rsp, 40h
0x1400bae27  pop     r14
0x1400bae29  pop     rdi
0x1400bae2a  pop     rsi
0x1400bae2b  pop     rbp
0x1400bae2c  pop     rbx
0x1400bae2d  retn
```
