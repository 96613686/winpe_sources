# CopyOffsetDirectoryTables

- ea: `0x180028388`
- end: `0x1800285c6`
- name: `CopyOffsetDirectoryTables`
- size: `574`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800285cc`

## callees

- `0x180010ae4`
- `0x180011640`
- `0x1800134a0`
- `0x1800134b4`
- `0x180015190`
- `0x1800164a0`
- `0x180028388`
- `0x18002a590`

## pseudocode

```c
__int64 __fastcall CopyOffsetDirectoryTables(__int64 a1, __int64 a2, __int64 a3, _DWORD *a4)
{
  unsigned int v6; // ebx
  __int64 result; // rax
  unsigned int v8; // edi
  unsigned __int16 v9; // r14
  __int64 v10; // rbx
  unsigned int v11; // esi
  unsigned __int16 i; // di
  unsigned __int16 Generic; // r12
  int v14; // eax
  __int64 v15; // rcx
  unsigned int v16; // r14d
  unsigned __int16 v17; // si
  unsigned int v18; // r14d
  _WORD v19[2]; // [rsp+40h] [rbp-39h] BYREF
  unsigned __int16 v20; // [rsp+44h] [rbp-35h] BYREF
  int v21; // [rsp+48h] [rbp-31h] BYREF
  _DWORD *v22; // [rsp+50h] [rbp-29h]
  __int64 v23; // [rsp+58h] [rbp-21h] BYREF
  int v24; // [rsp+60h] [rbp-19h]
  __int128 v25; // [rsp+68h] [rbp-11h] BYREF
  int v26; // [rsp+78h] [rbp-1h]
  __int128 v27; // [rsp+80h] [rbp+7h] BYREF

  v22 = a4;
  v23 = 0;
  v24 = 0;
  v26 = 0;
  v19[0] = 0;
  v27 = 0;
  v20 = 0;
  v25 = 0;
  v21 = 0;
  v6 = TTTableOffset(a1, "dttf");
  if ( !v6 )
    goto LABEL_5;
  result = ReadGeneric((__int64 *)a1, (__int64)&v25, 0x12u, (unsigned __int8 *)&DTTF_HEADER_CONTROL, v6, v19);
  if ( (_WORD)result )
    return result;
  if ( WORD6(v25) != 3 )
    return 1013;
LABEL_5:
  v8 = *(_DWORD *)(a1 + 12);
  result = ReadGeneric((__int64 *)a1, (__int64)&v23, 0xCu, (unsigned __int8 *)OFFSET_TABLE_CONTROL, v8, v19);
  if ( !(_WORD)result )
  {
    v9 = WORD2(v23);
    if ( WORD2(v23) <= 0x3E8u )
    {
      v10 = Mem_Alloc(16 * (WORD2(v23) + (unsigned __int64)(v6 == 0)));
      if ( v10 )
      {
        v11 = v8 + v19[0];
        for ( i = 0; i < v9; ++i )
        {
          Generic = ReadGeneric((__int64 *)a1, (__int64)&v27, 0x10u, (unsigned __int8 *)&DIRECTORY_CONTROL, v11, v19);
          if ( Generic )
          {
            Mem_Free(v10);
            return Generic;
          }
          v11 += v19[0];
          v14 = v27;
          v15 = 2LL * i;
          *(_QWORD *)(v10 + 8 * v15 + 8) = 0;
          *(_DWORD *)(v10 + 8 * v15) = v14;
        }
        v16 = *(_DWORD *)(a2 + 12);
        WORD2(v23) = i;
        v17 = WriteGeneric(a2, (__int64)&v23, 0xCu, (unsigned __int8 *)OFFSET_TABLE_CONTROL, v16, &v20);
        if ( !v17 )
        {
          v18 = v20 + v16;
          v17 = WriteGenericRepeat(a2, v10, (unsigned int)&DIRECTORY_CONTROL, v18, (__int64)&v21, i, 16);
          if ( !v17 )
            *v22 = v18 + v21;
        }
        Mem_Free(v10);
        return v17;
      }
      else
      {
        return 1005;
      }
    }
    else
    {
      return 1006;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180028388  mov     [rsp-8+arg_10], rbx
0x18002838d  push    rbp
0x18002838e  push    rsi
0x18002838f  push    rdi
0x180028390  push    r12
0x180028392  push    r13
0x180028394  push    r14
0x180028396  push    r15
0x180028398  lea     rbp, [rsp-27h]
0x18002839d  sub     rsp, 0A0h
0x1800283a4  mov     rax, cs:__security_cookie
0x1800283ab  xor     rax, rsp
0x1800283ae  mov     [rbp+57h+var_40], rax
0x1800283b2  xor     eax, eax
0x1800283b4  mov     [rbp+57h+var_80], r9
0x1800283b8  xorps   xmm0, xmm0
0x1800283bb  mov     [rbp+57h+var_78], rax
0x1800283bf  xor     r12d, r12d
0x1800283c2  mov     [rbp+57h+var_70], eax
0x1800283c5  mov     r13, rdx
0x1800283c8  mov     [rbp+57h+var_58], eax
0x1800283cb  lea     rdx, aDttf; "dttf"
0x1800283d2  mov     [rbp+57h+var_90], r12w
0x1800283d7  movups  [rbp+57h+var_50], xmm0
0x1800283db  mov     [rbp+57h+var_8C], r12w
0x1800283e0  mov     r15, rcx
0x1800283e3  movups  [rbp+57h+var_68], xmm0
0x1800283e7  mov     [rbp+57h+var_88], r12d
0x1800283eb  call    TTTableOffset
0x1800283f0  mov     ebx, eax
0x1800283f2  test    eax, eax
0x1800283f4  jz      short loc_180028435
0x1800283f6  lea     rax, [rbp+57h+var_90]
0x1800283fa  mov     rcx, r15
0x1800283fd  mov     [rsp+0D0h+var_A8], rax
0x180028402  lea     r8d, [r12+12h]
0x180028407  lea     r9, DTTF_HEADER_CONTROL
0x18002840e  mov     dword ptr [rsp+0D0h+var_B0], ebx
0x180028412  lea     rdx, [rbp+57h+var_68]
0x180028416  call    ReadGeneric
0x18002841b  test    ax, ax
0x18002841e  jnz     loc_18002859F
0x180028424  cmp     word ptr [rbp+57h+var_68+0Ch], 3
0x180028429  jz      short loc_180028435
0x18002842b  mov     eax, 3F5h
0x180028430  jmp     loc_18002859F
0x180028435  mov     edi, [r15+0Ch]
0x180028439  lea     rax, [rbp+57h+var_90]
0x18002843d  mov     [rsp+0D0h+var_A8], rax
0x180028442  lea     r9, OFFSET_TABLE_CONTROL
0x180028449  mov     r8d, 0Ch
0x18002844f  mov     dword ptr [rsp+0D0h+var_B0], edi
0x180028453  lea     rdx, [rbp+57h+var_78]
0x180028457  mov     rcx, r15
0x18002845a  call    ReadGeneric
0x18002845f  test    ax, ax
0x180028462  jnz     loc_18002859F
0x180028468  movzx   r14d, word ptr [rbp+57h+var_78+4]
0x18002846d  mov     eax, 3E8h
0x180028472  cmp     r14w, ax
0x180028476  jbe     short loc_180028482
0x180028478  mov     eax, 3EEh
0x18002847d  jmp     loc_18002859F
0x180028482  mov     rcx, r12
0x180028485  test    ebx, ebx
0x180028487  setz    cl
0x18002848a  add     rcx, r14
0x18002848d  shl     rcx, 4; Size
0x180028491  call    Mem_Alloc
0x180028496  mov     rbx, rax
0x180028499  test    rax, rax
0x18002849c  jnz     short loc_1800284A8
0x18002849e  mov     eax, 3EDh
0x1800284a3  jmp     loc_18002859F
0x1800284a8  movzx   esi, [rbp+57h+var_90]
0x1800284ac  add     esi, edi
0x1800284ae  mov     edi, r12d
0x1800284b1  mov     eax, 10h
0x1800284b6  cmp     di, r14w
0x1800284ba  jnb     short loc_180028518
0x1800284bc  mov     r8d, eax
0x1800284bf  lea     r9, DIRECTORY_CONTROL
0x1800284c6  lea     rax, [rbp+57h+var_90]
0x1800284ca  mov     rcx, r15
0x1800284cd  mov     [rsp+0D0h+var_A8], rax
0x1800284d2  lea     rdx, [rbp+57h+var_50]
0x1800284d6  mov     dword ptr [rsp+0D0h+var_B0], esi
0x1800284da  call    ReadGeneric
0x1800284df  movzx   r12d, ax
0x1800284e3  test    ax, ax
0x1800284e6  jnz     short loc_180028507
0x1800284e8  movzx   eax, [rbp+57h+var_90]
0x1800284ec  xor     r12d, r12d
0x1800284ef  movzx   ecx, di
0x1800284f2  add     esi, eax
0x1800284f4  mov     eax, dword ptr [rbp+57h+var_50]
0x1800284f7  add     rcx, rcx
0x1800284fa  inc     di
0x1800284fd  mov     [rbx+rcx*8+8], r12
0x180028502  mov     [rbx+rcx*8], eax
0x180028505  jmp     short loc_1800284B1
0x180028507  mov     rcx, rbx
0x18002850a  call    Mem_Free
0x18002850f  movzx   eax, r12w
0x180028513  jmp     loc_18002859F
0x180028518  mov     r14d, [r13+0Ch]
0x18002851c  lea     rax, [rbp+57h+var_8C]
0x180028520  mov     [rsp+0D0h+var_A8], rax
0x180028525  lea     r9, OFFSET_TABLE_CONTROL
0x18002852c  mov     r8d, 0Ch
0x180028532  mov     dword ptr [rsp+0D0h+var_B0], r14d
0x180028537  lea     rdx, [rbp+57h+var_78]
0x18002853b  mov     word ptr [rbp+57h+var_78+4], di
0x18002853f  mov     rcx, r13
0x180028542  call    WriteGeneric
0x180028547  movzx   esi, ax
0x18002854a  test    ax, ax
0x18002854d  jnz     short loc_180028594
0x18002854f  movzx   eax, [rbp+57h+var_8C]
0x180028553  lea     r8, DIRECTORY_CONTROL
0x18002855a  add     r14d, eax
0x18002855d  mov     [rsp+0D0h+var_A0], 10h
0x180028564  lea     rax, [rbp+57h+var_88]
0x180028568  mov     word ptr [rsp+0D0h+var_A8], di
0x18002856d  mov     r9d, r14d
0x180028570  mov     [rsp+0D0h+var_B0], rax
0x180028575  mov     rdx, rbx
0x180028578  mov     rcx, r13
0x18002857b  call    WriteGenericRepeat
0x180028580  movzx   esi, ax
0x180028583  test    ax, ax
0x180028586  jnz     short loc_180028594
0x180028588  mov     rax, [rbp+57h+var_80]
0x18002858c  mov     ecx, [rbp+57h+var_88]
0x18002858f  add     ecx, r14d
0x180028592  mov     [rax], ecx
0x180028594  mov     rcx, rbx
0x180028597  call    Mem_Free
0x18002859c  movzx   eax, si
0x18002859f  mov     rcx, [rbp+57h+var_40]
0x1800285a3  xor     rcx, rsp; StackCookie
0x1800285a6  call    __security_check_cookie
0x1800285ab  mov     rbx, [rsp+0D0h+arg_10]
0x1800285b3  add     rsp, 0A0h
0x1800285ba  pop     r15
0x1800285bc  pop     r14
0x1800285be  pop     r13
0x1800285c0  pop     r12
0x1800285c2  pop     rdi
0x1800285c3  pop     rsi
0x1800285c4  pop     rbp
0x1800285c5  retn
```
