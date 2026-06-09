# LoadIndex(_tagMPSWabFileInfo *,ulong,void *)

- ea: `0x180032200`
- end: `0x1800323b1`
- name: `?LoadIndex@@YAHPEAU_tagMPSWabFileInfo@@KPEAX@Z`
- size: `433`
- prototype: `int(struct _tagMPSWabFileInfo *, unsigned int, void *)`
- caller_count: `7`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180030300`
- `0x180030ec0`
- `0x180031618`
- `0x180032704`
- `0x180040930`
- `0x180040e30`
- `0x180043ffc`

## callees

- `0x180032200`
- `0x180032eb4`
- `0x180033ae0`

## import_xrefs

- `KERNEL32!SetFilePointer` at `0x18003227a`
- `KERNEL32!SetFilePointer` at `0x18003227a`
- `KERNEL32!LocalAlloc` at `0x1800322a3`
- `KERNEL32!LocalAlloc` at `0x1800322a3`
- `KERNEL32!GetFileSize` at `0x1800322fc`
- `KERNEL32!GetFileSize` at `0x1800322fc`
- `KERNEL32!ReadFile` at `0x1800322d3`
- `KERNEL32!ReadFile` at `0x180032349`
- `KERNEL32!ReadFile` at `0x1800322d3`
- `KERNEL32!ReadFile` at `0x180032349`

## pseudocode

```c
__int64 __fastcall LoadIndex(void **a1, unsigned int a2, void *a3)
{
  unsigned int v3; // esi
  __int64 v4; // rbp
  __int64 v7; // rdi
  unsigned int v8; // ecx
  HLOCAL v9; // rax
  _DWORD *v10; // rbp
  unsigned int *v11; // rbx
  DWORD FileSize; // eax
  __int64 i; // r8
  _DWORD *v14; // rcx
  unsigned int v15; // edi
  unsigned int v16; // r11d
  int v17; // r11d
  DWORD NumberOfBytesRead; // [rsp+50h] [rbp+8h] BYREF
  unsigned __int64 v20; // [rsp+68h] [rbp+20h] BYREF

  v3 = 0;
  v4 = a2;
  NumberOfBytesRead = 0;
  if ( a1 )
  {
    if ( !*((_DWORD *)a1[3] + 30) )
    {
      LocalFreeAndNull(a1 + 5);
      LocalFreeAndNull(a1 + 4);
      return 1;
    }
    LocalFreeAndNull((void **)((char *)a1 + (-(__int64)(a2 != 0) & 0xFFFFFFFFFFFFFFF8uLL) + 40));
    if ( SetFilePointer(a3, *((_DWORD *)a1[3] + 4 * v4 + 8), 0, 0) != -1 )
    {
      v7 = 2 * v4;
      v8 = *((_DWORD *)a1[3] + 4 * v4 + 7);
      if ( v8 )
      {
        v9 = LocalAlloc(0x40u, v8);
        if ( (_DWORD)v4 )
        {
          a1[4] = v9;
          if ( v9 )
          {
            if ( ReadFile(a3, v9, *((_DWORD *)a1[3] + 4 * v4 + 7), &NumberOfBytesRead, 0) )
            {
              v14 = a1[3];
              if ( NumberOfBytesRead == v14[4 * v4 + 7] )
              {
                v15 = v14[4 * v4 + 9];
                v16 = 0;
                v20 = 0;
                while ( v16 < v15 )
                {
                  if ( (int)StringCchLengthW((const unsigned __int16 *)a1[4] + 34 * v16, 0x20u, &v20) < 0 )
                    return v3;
                  v16 = v17 + 1;
                }
                *(_DWORD *)a1 = v4;
                return 1;
              }
            }
          }
        }
        else
        {
          a1[5] = v9;
          if ( v9 )
          {
            if ( ReadFile(a3, v9, *((_DWORD *)a1[3] + 4 * v4 + 7), &NumberOfBytesRead, 0) )
            {
              v10 = a1[3];
              if ( NumberOfBytesRead == v10[2 * v7 + 7] )
              {
                v11 = (unsigned int *)a1[5];
                FileSize = GetFileSize(a3, 0);
                for ( i = 0; (unsigned int)i < v10[9]; i = (unsigned int)(i + 1) )
                {
                  if ( (unsigned __int64)v11[2 * i + 1] + 32 > FileSize )
                    return v3;
                }
                return 1;
              }
            }
          }
        }
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180032200  mov     [rsp+arg_8], rbx
0x180032205  mov     [rsp+arg_10], rbp
0x18003220a  push    rsi
0x18003220b  push    rdi
0x18003220c  push    r14
0x18003220e  sub     rsp, 30h
0x180032212  xor     esi, esi
0x180032214  mov     ebp, edx
0x180032216  mov     [rsp+48h+NumberOfBytesRead], esi
0x18003221a  mov     r14, r8
0x18003221d  mov     rbx, rcx
0x180032220  test    rcx, rcx
0x180032223  jz      loc_18003239C
0x180032229  mov     rax, [rcx+18h]
0x18003222d  cmp     [rax+78h], esi
0x180032230  jnz     short loc_180032249
0x180032232  add     rcx, 28h ; '('; void **
0x180032236  call    ?LocalFreeAndNull@@YAXPEAPEAX@Z; LocalFreeAndNull(void * *)
0x18003223b  lea     rcx, [rbx+20h]; void **
0x18003223f  call    ?LocalFreeAndNull@@YAXPEAPEAX@Z; LocalFreeAndNull(void * *)
0x180032244  jmp     loc_180032397
0x180032249  mov     eax, ebp
0x18003224b  neg     eax
0x18003224d  sbb     rcx, rcx
0x180032250  and     rcx, 0FFFFFFFFFFFFFFF8h
0x180032254  add     rcx, 28h ; '('
0x180032258  add     rcx, rbx; void **
0x18003225b  call    ?LocalFreeAndNull@@YAXPEAPEAX@Z; LocalFreeAndNull(void * *)
0x180032260  mov     rdx, [rbx+18h]
0x180032264  lea     rax, [rbp+2]
0x180032268  add     rax, rax
0x18003226b  xor     r9d, r9d; dwMoveMethod
0x18003226e  xor     r8d, r8d; lpDistanceToMoveHigh
0x180032271  mov     rcx, r14; hFile
0x180032274  mov     rdi, rbp
0x180032277  mov     edx, [rdx+rax*8]; lDistanceToMove
0x18003227a  call    cs:__imp_SetFilePointer
0x180032280  cmp     eax, 0FFFFFFFFh
0x180032283  jz      loc_18003239C
0x180032289  mov     rax, [rbx+18h]
0x18003228d  add     rdi, rdi
0x180032290  mov     ecx, [rax+rdi*8+1Ch]
0x180032294  test    ecx, ecx
0x180032296  jz      loc_18003239C
0x18003229c  mov     edx, ecx; uBytes
0x18003229e  mov     ecx, 40h ; '@'; uFlags
0x1800322a3  call    cs:__imp_LocalAlloc
0x1800322a9  test    ebp, ebp
0x1800322ab  jnz     short loc_180032327
0x1800322ad  mov     [rbx+28h], rax
0x1800322b1  test    rax, rax
0x1800322b4  jz      loc_18003239C
0x1800322ba  mov     r8, [rbx+18h]
0x1800322be  lea     r9, [rsp+48h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800322c3  mov     rdx, rax; lpBuffer
0x1800322c6  mov     [rsp+48h+lpOverlapped], rsi; lpOverlapped
0x1800322cb  mov     rcx, r14; hFile
0x1800322ce  mov     r8d, [r8+rdi*8+1Ch]; nNumberOfBytesToRead
0x1800322d3  call    cs:__imp_ReadFile
0x1800322d9  test    eax, eax
0x1800322db  jz      loc_18003239C
0x1800322e1  mov     rbp, [rbx+18h]
0x1800322e5  mov     eax, [rbp+rdi*8+1Ch]
0x1800322e9  cmp     [rsp+48h+NumberOfBytesRead], eax
0x1800322ed  jnz     loc_18003239C
0x1800322f3  mov     rbx, [rbx+28h]
0x1800322f7  xor     edx, edx; lpFileSizeHigh
0x1800322f9  mov     rcx, r14; hFile
0x1800322fc  call    cs:__imp_GetFileSize
0x180032302  mov     r9d, [rbp+24h]
0x180032306  xor     r8d, r8d
0x180032309  cmp     r8d, r9d
0x18003230c  jnb     loc_180032397
0x180032312  mov     edx, [rbx+r8*8+4]
0x180032317  add     rdx, 20h ; ' '
0x18003231b  mov     ecx, eax
0x18003231d  cmp     rdx, rcx
0x180032320  ja      short loc_18003239C
0x180032322  inc     r8d
0x180032325  jmp     short loc_180032309
0x180032327  mov     [rbx+20h], rax
0x18003232b  test    rax, rax
0x18003232e  jz      short loc_18003239C
0x180032330  mov     r8, [rbx+18h]
0x180032334  lea     r9, [rsp+48h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180032339  mov     rdx, rax; lpBuffer
0x18003233c  mov     [rsp+48h+lpOverlapped], rsi; lpOverlapped
0x180032341  mov     rcx, r14; hFile
0x180032344  mov     r8d, [r8+rdi*8+1Ch]; nNumberOfBytesToRead
0x180032349  call    cs:__imp_ReadFile
0x18003234f  test    eax, eax
0x180032351  jz      short loc_18003239C
0x180032353  mov     rcx, [rbx+18h]
0x180032357  mov     eax, [rcx+rdi*8+1Ch]
0x18003235b  cmp     [rsp+48h+NumberOfBytesRead], eax
0x18003235f  jnz     short loc_18003239C
0x180032361  mov     edi, [rcx+rdi*8+24h]
0x180032365  xor     r11d, r11d
0x180032368  mov     [rsp+48h+arg_18], rsi
0x18003236d  cmp     r11d, edi
0x180032370  jnb     short loc_180032395
0x180032372  mov     eax, r11d
0x180032375  lea     r8, [rsp+48h+arg_18]; unsigned __int64 *
0x18003237a  imul    rcx, rax, 44h ; 'D'
0x18003237e  mov     edx, 20h ; ' '; unsigned __int64
0x180032383  add     rcx, [rbx+20h]; unsigned __int16 *
0x180032387  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18003238c  test    eax, eax
0x18003238e  js      short loc_18003239C
0x180032390  inc     r11d
0x180032393  jmp     short loc_18003236D
0x180032395  mov     [rbx], ebp
0x180032397  mov     esi, 1
0x18003239c  mov     rbx, [rsp+48h+arg_8]
0x1800323a1  mov     eax, esi
0x1800323a3  mov     rbp, [rsp+48h+arg_10]
0x1800323a8  add     rsp, 30h
0x1800323ac  pop     r14
0x1800323ae  pop     rdi
0x1800323af  pop     rsi
0x1800323b0  retn
```
