# EFIDECreateDriverEntry

- ea: `0x180014784`
- end: `0x180014906`
- name: `EFIDECreateDriverEntry`
- size: `386`
- prototype: `_QWORD *__fastcall(_DWORD *, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, reparse_path`

## callers

- `0x18001378c`

## callees

- `0x180012d4c`
- `0x180014274`
- `0x180014444`
- `0x180014784`
- `0x180014a40`
- `0x180014a94`
- `0x180014b1c`
- `0x180014b70`
- `0x1800179c5`
- `0x180018010`

## pseudocode

```c
_QWORD *__fastcall EFIDECreateDriverEntry(_DWORD *a1, __int64 a2)
{
  _QWORD *v4; // rsi
  __int64 v5; // rbp
  __int64 v6; // r15
  int v7; // eax
  __int64 v8; // rdx
  _DWORD *v9; // rdi
  char *v10; // r15
  __int64 v11; // rax
  char *v12; // rbx
  unsigned int v14; // [rsp+50h] [rbp+8h] BYREF

  v4 = 0;
  if ( a1 )
  {
    if ( a2 )
    {
      v5 = (unsigned int)a1[5];
      if ( *(_DWORD *)((char *)a1 + v5 + 12) != 3 )
      {
        v6 = (unsigned int)a1[4];
        v14 = 0;
        v7 = EfiTranslateFilePath((char *)a1 + v5 + 4, a2, 0, &v14);
        if ( v7 < 0 )
        {
          if ( v7 == -1073741789 )
          {
            if ( !AllocRoutine )
              return v4;
            v9 = (_DWORD *)AllocRoutine(v14);
            if ( !v9 )
              return v4;
            *v9 = 0;
            v7 = EfiTranslateFilePath((char *)a1 + v5 + 4, v8, v9, &v14);
            if ( v7 >= 0 )
            {
              v10 = (char *)a1 + v6;
              if ( AllocRoutine )
                v4 = (_QWORD *)AllocRoutine(2120);
              memset_0(v4, 0, 0x848u);
              v4[261] = a2;
              v4[264] = EFIDEFlushDriverEntry;
              *(_DWORD *)v4 = a1[3];
              v11 = -1;
              do
                ++v11;
              while ( *((_WORD *)v9 + v11 + 6) );
              v12 = (char *)v9 + 2 * (unsigned int)(v11 + 1);
              OSDriverSetFileName(v4, v12 + 12);
              OSDriverSetNtPath(v4, v9 + 3);
              OSDriverSetDirPath(v4, v12 + 12);
              OSDriverSetFriendlyName(v4, v10 + 4);
LABEL_19:
              SBE_FREE(v9);
              return v4;
            }
          }
          else
          {
            v9 = 0;
          }
          if ( v7 == -1073741766 || v7 == -1073741772 )
            EfiDeleteDriverEntry((unsigned int)a1[3]);
          if ( v9 )
            goto LABEL_19;
        }
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180014784  mov     rax, rsp
0x180014787  mov     [rax+10h], rbx
0x18001478b  mov     [rax+18h], rbp
0x18001478f  push    rsi
0x180014790  push    rdi
0x180014791  push    r12
0x180014793  push    r14
0x180014795  push    r15
0x180014797  sub     rsp, 20h
0x18001479b  xor     r12d, r12d
0x18001479e  mov     r14, rdx
0x1800147a1  mov     rbx, rcx
0x1800147a4  mov     esi, r12d
0x1800147a7  test    rcx, rcx
0x1800147aa  jz      loc_1800148EC
0x1800147b0  test    rdx, rdx
0x1800147b3  jz      loc_1800148EC
0x1800147b9  mov     ebp, [rcx+14h]
0x1800147bc  cmp     dword ptr [rbp+rcx+0Ch], 3
0x1800147c1  jz      loc_1800148EC
0x1800147c7  mov     r15d, [rcx+10h]
0x1800147cb  lea     r9, [rax+8]
0x1800147cf  add     rcx, 4
0x1800147d3  mov     [rax+8], r12d
0x1800147d7  add     rcx, rbp
0x1800147da  xor     r8d, r8d
0x1800147dd  call    EfiTranslateFilePath
0x1800147e2  test    eax, eax
0x1800147e4  jns     loc_1800148EC
0x1800147ea  cmp     eax, 0C0000023h
0x1800147ef  jnz     loc_1800148C6
0x1800147f5  mov     rax, cs:AllocRoutine
0x1800147fc  test    rax, rax
0x1800147ff  jz      loc_1800148EC
0x180014805  mov     ecx, [rsp+48h+arg_0]
0x180014809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001480e  mov     rdi, rax
0x180014811  test    rax, rax
0x180014814  jz      loc_1800148EC
0x18001481a  xor     eax, eax
0x18001481c  lea     rcx, [rbx+4]
0x180014820  add     rcx, rbp
0x180014823  mov     [rdi], eax
0x180014825  lea     r9, [rsp+48h+arg_0]
0x18001482a  mov     r8, rdi
0x18001482d  call    EfiTranslateFilePath
0x180014832  test    eax, eax
0x180014834  js      loc_1800148C9
0x18001483a  mov     rax, cs:AllocRoutine
0x180014841  add     r15, rbx
0x180014844  mov     ebp, 848h
0x180014849  test    rax, rax
0x18001484c  jz      short loc_180014858
0x18001484e  mov     ecx, ebp
0x180014850  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014855  mov     rsi, rax
0x180014858  mov     r8, rbp; Size
0x18001485b  xor     edx, edx; Val
0x18001485d  mov     rcx, rsi; void *
0x180014860  call    memset_0
0x180014865  lea     rax, EFIDEFlushDriverEntry
0x18001486c  mov     [rsi+828h], r14
0x180014873  mov     [rsi+840h], rax
0x18001487a  mov     eax, [rbx+0Ch]
0x18001487d  mov     [rsi], eax
0x18001487f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180014883  inc     rax
0x180014886  cmp     [rdi+rax*2+0Ch], r12w
0x18001488c  jnz     short loc_180014883
0x18001488e  inc     eax
0x180014890  mov     rcx, rsi
0x180014893  lea     rbx, [rdi+rax*2]
0x180014897  lea     rdx, [rbx+0Ch]
0x18001489b  call    OSDriverSetFileName
0x1800148a0  lea     rdx, [rdi+0Ch]
0x1800148a4  mov     rcx, rsi
0x1800148a7  call    OSDriverSetNtPath
0x1800148ac  lea     rdx, [rbx+0Ch]
0x1800148b0  mov     rcx, rsi
0x1800148b3  call    OSDriverSetDirPath
0x1800148b8  lea     rdx, [r15+4]
0x1800148bc  mov     rcx, rsi
0x1800148bf  call    OSDriverSetFriendlyName
0x1800148c4  jmp     short loc_1800148E4
0x1800148c6  mov     rdi, r12
0x1800148c9  cmp     eax, 0C000003Ah
0x1800148ce  jz      short loc_1800148D7
0x1800148d0  cmp     eax, 0C0000034h
0x1800148d5  jnz     short loc_1800148DF
0x1800148d7  mov     ecx, [rbx+0Ch]
0x1800148da  call    EfiDeleteDriverEntry
0x1800148df  test    rdi, rdi
0x1800148e2  jz      short loc_1800148EC
0x1800148e4  mov     rcx, rdi
0x1800148e7  call    SBE_FREE
0x1800148ec  mov     rbx, [rsp+48h+arg_8]
0x1800148f1  mov     rax, rsi
0x1800148f4  mov     rbp, [rsp+48h+arg_10]
0x1800148f9  add     rsp, 20h
0x1800148fd  pop     r15
0x1800148ff  pop     r14
0x180014901  pop     r12
0x180014903  pop     rdi
0x180014904  pop     rsi
0x180014905  retn
```
