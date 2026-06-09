# putend

- ea: `0x180025fd4`
- end: `0x1800261c4`
- name: `putend`
- size: `496`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000496c`
- `0x18001a6cc`

## callees

- `0x180005464`
- `0x180025fd4`
- `0x180036f50`
- `0x18003791c`
- `0x180037928`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180026085`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002614c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180026085`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002614c`

## pseudocode

```c
__int64 __fastcall putend(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, HANDLE *a6)
{
  int v9; // r14d
  _DWORD *v10; // rax
  void *v11; // rbx
  __int64 v13; // r12
  char *v14; // rax
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-48h] BYREF

  NumberOfBytesWritten = 0;
  if ( a1 <= 65534 && a2 <= 4294967294LL )
  {
    v9 = 0;
    if ( a3 <= 4294967294LL )
    {
LABEL_4:
      v10 = o_malloc_0(0x17u);
      v11 = v10;
      if ( v10 )
      {
        *v10 = 101010256;
        v10[1] = 0;
        if ( v9 )
        {
          if ( a1 <= 65534 )
            *((_WORD *)v10 + 4) = a1;
          else
            *((_WORD *)v10 + 4) = -1;
          if ( a1 <= 65534 )
            *((_WORD *)v10 + 5) = a1;
          else
            *((_WORD *)v10 + 5) = -1;
          if ( a2 <= 4294967294LL )
            v10[3] = a2;
          else
            v10[3] = -1;
          if ( a3 > 4294967294LL )
          {
            v10[4] = -1;
            goto LABEL_8;
          }
        }
        else
        {
          *((_WORD *)v10 + 4) = a1;
          *((_WORD *)v10 + 5) = a1;
          v10[3] = a2;
        }
        v10[4] = a3;
LABEL_8:
        *((_WORD *)v10 + 10) = 0;
        if ( WriteFile(*a6, v10, 0x16u, &NumberOfBytesWritten, 0) && NumberOfBytesWritten == 22 )
        {
          free(v11);
          return 0;
        }
        goto LABEL_27;
      }
      return 4;
    }
  }
  v9 = 1;
  v13 = DZSetFilePointer(*a6, 0, 1);
  v14 = (char *)o_malloc_0(0x4Du);
  v11 = v14;
  if ( !v14 )
    return 4;
  *(_DWORD *)v14 = 101075792;
  *(_QWORD *)(v14 + 4) = 44;
  *(_QWORD *)(v14 + 12) = 2949165;
  *((_DWORD *)v14 + 5) = 0;
  *((_QWORD *)v14 + 3) = a1;
  *((_QWORD *)v14 + 4) = a1;
  *((_QWORD *)v14 + 5) = a2;
  *((_QWORD *)v14 + 6) = a3;
  *((_QWORD *)v14 + 7) = 117853008;
  *((_QWORD *)v14 + 8) = v13;
  *((_DWORD *)v14 + 18) = 0;
  if ( WriteFile(*a6, v14, 0x4Cu, &NumberOfBytesWritten, 0) && NumberOfBytesWritten == 76 )
  {
    free(v11);
    goto LABEL_4;
  }
LABEL_27:
  free(v11);
  return 10;
}

```

## disassembly

```asm
0x180025fd4  push    rbx
0x180025fd6  push    rbp
0x180025fd7  push    rsi
0x180025fd8  push    rdi
0x180025fd9  push    r12
0x180025fdb  push    r14
0x180025fdd  push    r15
0x180025fdf  sub     rsp, 40h
0x180025fe3  mov     rax, cs:__security_cookie
0x180025fea  xor     rax, rsp
0x180025fed  mov     [rsp+78h+var_40], rax
0x180025ff2  mov     r15, [rsp+78h+arg_28]
0x180025ffa  mov     rbp, r8
0x180025ffd  mov     [rsp+78h+NumberOfBytesWritten], 0
0x180026005  mov     rsi, rdx
0x180026008  mov     rdi, rcx
0x18002600b  mov     r12d, 0FFFFFFFEh
0x180026011  cmp     rcx, 0FFFEh
0x180026018  jg      loc_1800260C4
0x18002601e  cmp     rdx, r12
0x180026021  jg      loc_1800260C4
0x180026027  xor     r14d, r14d
0x18002602a  cmp     r8, r12
0x18002602d  jg      loc_1800260C4
0x180026033  mov     ecx, 17h; Size
0x180026038  call    _o_malloc_0
0x18002603d  mov     rbx, rax
0x180026040  test    rax, rax
0x180026043  jz      loc_1800260EB
0x180026049  mov     dword ptr [rax], 6054B50h
0x18002604f  xor     eax, eax
0x180026051  mov     [rbx+4], eax
0x180026054  test    r14d, r14d
0x180026057  jnz     loc_180026170
0x18002605d  mov     [rbx+8], di
0x180026061  mov     [rbx+0Ah], di
0x180026065  mov     [rbx+0Ch], esi
0x180026068  mov     [rbx+10h], ebp
0x18002606b  xor     eax, eax
0x18002606d  lea     r9, [rsp+78h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180026072  mov     [rbx+14h], ax
0x180026076  mov     rdx, rbx; lpBuffer
0x180026079  mov     rcx, [r15]; hFile
0x18002607c  mov     [rsp+78h+lpOverlapped], rax; lpOverlapped
0x180026081  lea     r8d, [rax+16h]; nNumberOfBytesToWrite
0x180026085  call    cs:__imp_WriteFile
0x18002608b  test    eax, eax
0x18002608d  jz      loc_1800261B2
0x180026093  cmp     [rsp+78h+NumberOfBytesWritten], 16h
0x180026098  jnz     loc_1800261B2
0x18002609e  mov     rcx, rbx; Block
0x1800260a1  call    free
0x1800260a6  xor     eax, eax
0x1800260a8  mov     rcx, [rsp+78h+var_40]
0x1800260ad  xor     rcx, rsp; StackCookie
0x1800260b0  call    __security_check_cookie
0x1800260b5  add     rsp, 40h
0x1800260b9  pop     r15
0x1800260bb  pop     r14
0x1800260bd  pop     r12
0x1800260bf  pop     rdi
0x1800260c0  pop     rsi
0x1800260c1  pop     rbp
0x1800260c2  pop     rbx
0x1800260c3  retn
0x1800260c4  mov     rcx, [r15]
0x1800260c7  mov     r14d, 1
0x1800260cd  mov     r8d, r14d
0x1800260d0  xor     edx, edx
0x1800260d2  call    DZSetFilePointer
0x1800260d7  lea     ecx, [r14+4Ch]; Size
0x1800260db  mov     r12, rax
0x1800260de  call    _o_malloc_0
0x1800260e3  mov     rbx, rax
0x1800260e6  test    rax, rax
0x1800260e9  jnz     short loc_1800260F2
0x1800260eb  mov     eax, 4
0x1800260f0  jmp     short loc_1800260A8
0x1800260f2  mov     dword ptr [rax], 6064B50h
0x1800260f8  lea     r9, [rsp+78h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800260fd  mov     qword ptr [rax+4], 2Ch ; ','
0x180026105  mov     r8d, 4Ch ; 'L'; nNumberOfBytesToWrite
0x18002610b  mov     qword ptr [rax+0Ch], 2D002Dh
0x180026113  mov     rdx, rbx; lpBuffer
0x180026116  mov     dword ptr [rax+14h], 0
0x18002611d  mov     [rax+18h], rdi
0x180026121  mov     [rax+20h], rdi
0x180026125  mov     [rax+28h], rsi
0x180026129  mov     [rax+30h], rbp
0x18002612d  mov     qword ptr [rax+38h], 7064B50h
0x180026135  mov     [rax+40h], r12
0x180026139  mov     dword ptr [rax+48h], 0
0x180026140  mov     rcx, [r15]; hFile
0x180026143  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x18002614c  call    cs:__imp_WriteFile
0x180026152  test    eax, eax
0x180026154  jz      short loc_1800261B2
0x180026156  cmp     [rsp+78h+NumberOfBytesWritten], 4Ch ; 'L'
0x18002615b  jnz     short loc_1800261B2
0x18002615d  mov     rcx, rbx; Block
0x180026160  call    free
0x180026165  mov     r12d, 0FFFFFFFEh
0x18002616b  jmp     loc_180026033
0x180026170  or      rax, 0FFFFFFFFFFFFFFFFh
0x180026174  mov     ecx, 0FFFEh
0x180026179  cmp     rdi, rcx
0x18002617c  jle     short loc_180026184
0x18002617e  mov     [rbx+8], ax
0x180026182  jmp     short loc_180026188
0x180026184  mov     [rbx+8], di
0x180026188  jle     short loc_180026190
0x18002618a  mov     [rbx+0Ah], ax
0x18002618e  jmp     short loc_180026194
0x180026190  mov     [rbx+0Ah], di
0x180026194  cmp     rsi, r12
0x180026197  jle     short loc_18002619E
0x180026199  mov     [rbx+0Ch], eax
0x18002619c  jmp     short loc_1800261A1
0x18002619e  mov     [rbx+0Ch], esi
0x1800261a1  cmp     rbp, r12
0x1800261a4  jle     loc_180026068
0x1800261aa  mov     [rbx+10h], eax
0x1800261ad  jmp     loc_18002606B
0x1800261b2  mov     rcx, rbx; Block
0x1800261b5  call    free
0x1800261ba  mov     eax, 0Ah
0x1800261bf  jmp     loc_1800260A8
```
