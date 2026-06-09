# CiDeserializePolicyFileData

- ea: `0x18004762c`
- end: `0x180047800`
- name: `CiDeserializePolicyFileData`
- size: `468`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int, _DWORD *, _DWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18004b950`

## callees

- `0x180006f10`
- `0x180010a88`
- `0x18004762c`

## import_xrefs

- `securekernel!SkFreePool` at `0x1800477c1`
- `securekernel!SkFreePool` at `0x1800477c1`

## pseudocode

```c
__int64 __fastcall CiDeserializePolicyFileData(unsigned int *a1, unsigned int a2, _DWORD *a3, _DWORD *a4, __int64 *a5)
{
  NTSTATUS v8; // ebx
  __int64 v9; // rsi
  __int64 v10; // rcx
  ULONG v11; // edi
  ULONG v12; // edi
  __int64 v13; // r15
  ULONG v14; // edi
  __int64 v15; // r12
  unsigned int v16; // edi
  __int64 v17; // rbp
  __int64 v18; // r9
  __int64 PoolHelper; // rdx
  unsigned int v20; // r11d
  char *v21; // r15
  char *v22; // r10
  char *v23; // r9
  __int64 v24; // r8
  __int64 v25; // rcx
  char v26; // al
  __int64 v27; // rcx
  unsigned int v28; // eax
  __int64 v29; // rax
  int v30; // eax
  _DWORD *v31; // rcx
  ULONG pulResult; // [rsp+68h] [rbp+10h] BYREF
  _DWORD *v34; // [rsp+70h] [rbp+18h]

  v34 = a3;
  pulResult = 0;
  if ( a2 < 4 )
    return (unsigned int)-1073741811;
  v9 = *a1;
  v8 = RtlULongLongToULong((unsigned int)v9, &pulResult);
  if ( v8 < 0 )
    return (unsigned int)v8;
  v11 = a2 - 4;
  if ( v11 < pulResult )
    return (unsigned int)-1073741811;
  v12 = v11 - pulResult;
  v13 = pulResult;
  v8 = RtlULongLongToULong(16 * v10, &pulResult);
  if ( v8 < 0 )
    return (unsigned int)v8;
  if ( v12 < pulResult )
    return (unsigned int)-1073741811;
  v14 = v12 - pulResult;
  v15 = pulResult;
  v8 = RtlULongLongToULong(4 * v9, &pulResult);
  if ( v8 < 0 )
    return (unsigned int)v8;
  if ( v14 < pulResult )
  {
    return (unsigned int)-1073741811;
  }
  else
  {
    v16 = v14 - pulResult;
    v17 = pulResult;
    v8 = RtlULongLongToULong(8 * v9, &pulResult);
    if ( v8 >= 0 )
    {
      v8 = RtlULongLongToULong(56 * v18, &pulResult);
      if ( v8 >= 0 )
      {
        PoolHelper = SkAllocatePoolHelper(256, pulResult, 1668499779);
        if ( PoolHelper )
        {
          v20 = 0;
          v21 = (char *)a1 + v13 + 4;
          v22 = &v21[v15];
          v23 = &v21[v15 + v17];
          if ( (_DWORD)v9 )
          {
            v24 = 0;
            do
            {
              v25 = 56 * v24;
              ++v20;
              *(_OWORD *)(v25 + PoolHelper + 24) = *(_OWORD *)&v21[16 * v24];
              *(_DWORD *)(v25 + PoolHelper + 48) = *(_DWORD *)&v22[4 * v24];
              v26 = *((_BYTE *)a1 + v24++ + 4);
              *(_BYTE *)(v25 + PoolHelper + 16) = v26;
              *(_QWORD *)(v25 + PoolHelper + 40) = 0;
            }
            while ( v20 < (unsigned int)v9 );
            v27 = 0;
            while ( 1 )
            {
              v28 = *(_DWORD *)&v22[4 * v27];
              if ( v16 < v28 || !v28 )
                break;
              *(_QWORD *)(56LL * (unsigned int)v27 + PoolHelper + 40) = v23;
              v29 = *(unsigned int *)&v22[4 * v27];
              v27 = (unsigned int)(v27 + 1);
              v16 -= v29;
              v23 += v29;
              if ( (unsigned int)v27 >= (unsigned int)v9 )
                goto LABEL_20;
            }
          }
          else
          {
LABEL_20:
            if ( v16 >= 4 )
            {
              v30 = *(_DWORD *)v23;
              v31 = v34;
              *a4 = v9;
              *v31 = v30;
              *a5 = PoolHelper;
              return (unsigned int)v8;
            }
          }
          v8 = -1073741811;
          SkFreePool(1, PoolHelper);
        }
        else
        {
          return (unsigned int)-1073741801;
        }
      }
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18004762c  mov     [rsp+arg_0], rbx
0x180047631  mov     [rsp+arg_10], r8
0x180047636  push    rbp
0x180047637  push    rsi
0x180047638  push    rdi
0x180047639  push    r12
0x18004763b  push    r13
0x18004763d  push    r14
0x18004763f  push    r15
0x180047641  sub     rsp, 20h
0x180047645  mov     [rsp+58h+pulResult], 0
0x18004764d  mov     r13, r9
0x180047650  mov     edi, edx
0x180047652  mov     r14, rcx
0x180047655  cmp     edx, 4
0x180047658  jnb     short loc_180047664
0x18004765a  mov     ebx, 0C000000Dh
0x18004765f  jmp     loc_1800477E8
0x180047664  mov     esi, [rcx]
0x180047666  lea     rdx, [rsp+58h+pulResult]; pulResult
0x18004766b  mov     ecx, esi; ullOperand
0x18004766d  mov     r9d, esi
0x180047670  call    RtlULongLongToULong
0x180047675  mov     ebx, eax
0x180047677  test    eax, eax
0x180047679  js      loc_1800477E8
0x18004767f  mov     eax, [rsp+58h+pulResult]
0x180047683  add     edi, 0FFFFFFFCh
0x180047686  cmp     edi, eax
0x180047688  jb      short loc_18004765A
0x18004768a  shl     rcx, 4; ullOperand
0x18004768e  lea     rdx, [rsp+58h+pulResult]; pulResult
0x180047693  sub     edi, eax
0x180047695  mov     r15d, eax
0x180047698  call    RtlULongLongToULong
0x18004769d  mov     ebx, eax
0x18004769f  test    eax, eax
0x1800476a1  js      loc_1800477E8
0x1800476a7  mov     eax, [rsp+58h+pulResult]
0x1800476ab  cmp     edi, eax
0x1800476ad  jb      short loc_18004765A
0x1800476af  lea     rcx, ds:0[rsi*4]; ullOperand
0x1800476b7  sub     edi, eax
0x1800476b9  lea     rdx, [rsp+58h+pulResult]; pulResult
0x1800476be  mov     r12d, eax
0x1800476c1  call    RtlULongLongToULong
0x1800476c6  mov     ebx, eax
0x1800476c8  test    eax, eax
0x1800476ca  js      loc_1800477E8
0x1800476d0  mov     eax, [rsp+58h+pulResult]
0x1800476d4  cmp     edi, eax
0x1800476d6  jb      short loc_18004765A
0x1800476d8  lea     rcx, ds:0[rsi*8]; ullOperand
0x1800476e0  sub     edi, eax
0x1800476e2  lea     rdx, [rsp+58h+pulResult]; pulResult
0x1800476e7  mov     ebp, eax
0x1800476e9  call    RtlULongLongToULong
0x1800476ee  mov     ebx, eax
0x1800476f0  test    eax, eax
0x1800476f2  js      loc_1800477E8
0x1800476f8  imul    rcx, r9, 38h ; '8'; ullOperand
0x1800476fc  lea     rdx, [rsp+58h+pulResult]; pulResult
0x180047701  call    RtlULongLongToULong
0x180047706  mov     ebx, eax
0x180047708  test    eax, eax
0x18004770a  js      loc_1800477E8
0x180047710  mov     edx, [rsp+58h+pulResult]
0x180047714  mov     ecx, 100h
0x180047719  mov     r8d, 63734943h
0x18004771f  call    SkAllocatePoolHelper
0x180047724  mov     rdx, rax
0x180047727  test    rax, rax
0x18004772a  jnz     short loc_180047736
0x18004772c  mov     ebx, 0C0000017h
0x180047731  jmp     loc_1800477E8
0x180047736  add     r15, 4
0x18004773a  xor     r11d, r11d
0x18004773d  add     r15, r14
0x180047740  lea     r10, [r15+r12]
0x180047744  lea     r9, [r10+rbp]
0x180047748  test    esi, esi
0x18004774a  jz      short loc_1800477B2
0x18004774c  xor     r8d, r8d
0x18004774f  imul    rcx, r8, 38h ; '8'
0x180047753  mov     rax, r8
0x180047756  inc     r11d
0x180047759  add     rax, rax
0x18004775c  movups  xmm0, xmmword ptr [r15+rax*8]
0x180047761  movdqu  xmmword ptr [rcx+rdx+18h], xmm0
0x180047767  mov     eax, [r10+r8*4]
0x18004776b  mov     [rcx+rdx+30h], eax
0x18004776f  mov     al, [r14+r8+4]
0x180047774  inc     r8
0x180047777  mov     [rcx+rdx+10h], al
0x18004777b  mov     qword ptr [rcx+rdx+28h], 0
0x180047784  cmp     r11d, esi
0x180047787  jb      short loc_18004774F
0x180047789  xor     ecx, ecx
0x18004778b  mov     eax, [r10+rcx*4]
0x18004778f  mov     r8d, ecx
0x180047792  cmp     edi, eax
0x180047794  jb      short loc_1800477B7
0x180047796  test    eax, eax
0x180047798  jz      short loc_1800477B7
0x18004779a  imul    rax, r8, 38h ; '8'
0x18004779e  mov     [rax+rdx+28h], r9
0x1800477a3  mov     eax, [r10+rcx*4]
0x1800477a7  inc     ecx
0x1800477a9  sub     edi, eax
0x1800477ab  add     r9, rax
0x1800477ae  cmp     ecx, esi
0x1800477b0  jb      short loc_18004778B
0x1800477b2  cmp     edi, 4
0x1800477b5  jnb     short loc_1800477CF
0x1800477b7  mov     ecx, 1
0x1800477bc  mov     ebx, 0C000000Dh
0x1800477c1  call    cs:__imp_SkFreePool
0x1800477c8  nop     dword ptr [rax+rax+00h]
0x1800477cd  jmp     short loc_1800477E8
0x1800477cf  mov     eax, [r9]
0x1800477d2  mov     rcx, [rsp+58h+arg_10]
0x1800477d7  mov     [r13+0], esi
0x1800477db  mov     [rcx], eax
0x1800477dd  mov     rax, [rsp+58h+arg_20]
0x1800477e5  mov     [rax], rdx
0x1800477e8  mov     eax, ebx
0x1800477ea  mov     rbx, [rsp+58h+arg_0]
0x1800477ef  add     rsp, 20h
0x1800477f3  pop     r15
0x1800477f5  pop     r14
0x1800477f7  pop     r13
0x1800477f9  pop     r12
0x1800477fb  pop     rdi
0x1800477fc  pop     rsi
0x1800477fd  pop     rbp
0x1800477fe  retn
```
