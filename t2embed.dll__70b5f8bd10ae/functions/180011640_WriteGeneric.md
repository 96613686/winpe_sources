# WriteGeneric

- ea: `0x180011640`
- end: `0x180011913`
- name: `WriteGeneric`
- size: `723`
- prototype: ``
- caller_count: `25`
- callee_count: `5`
- tags: ``

## callers

- `0x18000ee80`
- `0x18000fd44`
- `0x18001009c`
- `0x180010448`
- `0x1800106c8`
- `0x180010ae4`
- `0x180010b90`
- `0x1800110d0`
- `0x1800119f8`
- `0x1800120bc`
- `0x180012a18`
- `0x180016770`
- `0x18001be6c`
- `0x18001cfc0`
- `0x18001dc84`
- `0x180027504`
- `0x1800275d4`
- `0x180027ea8`
- `0x180027f64`
- `0x180028388`
- `0x180028dfc`
- `0x18002912c`
- `0x180029228`
- `0x1800297f8`
- `0x180029a94`

## callees

- `0x180010618`
- `0x180011640`
- `0x18001191c`
- `0x180011fc8`
- `0x18002b010`

## pseudocode

```c
__int16 __fastcall WriteGeneric(
        __int64 a1,
        __int64 a2,
        unsigned __int16 a3,
        unsigned __int8 *a4,
        unsigned int a5,
        _WORD *a6)
{
  unsigned __int16 v6; // r14
  unsigned __int16 v7; // di
  unsigned __int64 v8; // r13
  __int64 v9; // r10
  __int64 v10; // r11
  unsigned int v11; // ebx
  unsigned __int16 v12; // si
  unsigned __int8 v13; // dl
  int v14; // eax
  unsigned __int16 *v15; // r15
  __int64 v16; // r8
  unsigned __int16 v17; // r15
  unsigned int v18; // ebp
  unsigned __int64 v19; // rax
  __int64 v20; // rax
  __int16 result; // ax
  int v22; // eax
  unsigned int v23; // ebx
  __int64 (__fastcall *v24)(__int64, _QWORD); // r10
  unsigned __int64 v25; // rax
  __int64 v26; // rax
  unsigned __int8 *v29; // [rsp+88h] [rbp+20h]

  v29 = a4;
  v6 = *a4;
  v7 = 1;
  v8 = a3;
  v9 = a2;
  v10 = a1;
  v11 = a5;
  v12 = 0;
  while ( v7 <= v6 )
  {
    v13 = a4[v7];
    v14 = v13 & 7;
    if ( v14 == 2 )
    {
      if ( (v13 & 0x10) == 0 )
      {
        if ( (unsigned __int64)v12 + 2 > v8 )
          return 1004;
        v15 = (unsigned __int16 *)(v12 + v9);
        if ( (v13 & 0x20) != 0 )
        {
          result = WriteBytes(v10, v15, v11, 2);
          if ( result )
            return result;
          v10 = a1;
          v11 += 2;
          v9 = a2;
        }
        else
        {
          v16 = *(_QWORD *)v10;
          v17 = *v15;
          if ( !*(_QWORD *)v10 )
            return 1002;
          v18 = v11 + 2;
          if ( v11 + 2 < v11 )
            return 1002;
          v19 = *(unsigned int *)(v10 + 8);
          if ( v18 > v19 )
          {
            v24 = *(__int64 (__fastcall **)(__int64, _QWORD))(v10 + 16);
            if ( !v24 )
              return 1002;
            v25 = 11 * (int)v19 / 0xAu;
            if ( v25 <= v18 )
            {
              *(_DWORD *)(v10 + 8) = v18;
              LODWORD(v25) = v11 + 2;
            }
            else
            {
              *(_DWORD *)(v10 + 8) = v25;
            }
            v26 = v24(v16, (unsigned int)v25);
            v10 = a1;
            v16 = v26;
            *(_QWORD *)a1 = v26;
            if ( !v26 )
            {
              *(_DWORD *)(a1 + 8) = 0;
              return 1005;
            }
            v9 = a2;
          }
          v20 = v11;
          v11 += 2;
          *(_WORD *)(v20 + v16) = _byteswap_ushort(v17);
        }
        a4 = v29;
      }
      ++v7;
      v12 += 2;
    }
    else
    {
      v22 = v14 - 1;
      if ( v22 )
      {
        if ( v22 != 3 )
          return 1004;
        if ( (v13 & 0x10) == 0 )
        {
          if ( (unsigned __int64)v12 + 4 > v8 )
            return 1004;
          if ( (v13 & 0x20) != 0 )
            result = WriteBytes(v10, v12 + v9, v11, 4);
          else
            result = WriteLong(v10, *(unsigned int *)(v12 + v9), v11);
          if ( result )
            return result;
          v10 = a1;
          v11 += 4;
          a4 = v29;
          v9 = a2;
        }
        ++v7;
        v12 += 4;
      }
      else
      {
        if ( (v13 & 0x10) == 0 )
        {
          if ( (unsigned __int64)v12 + 1 > v8 )
            return 1004;
          result = WriteByte(v10, *(unsigned __int8 *)(v12 + v9), v11);
          if ( result )
            return result;
          v10 = a1;
          ++v11;
          a4 = v29;
          v9 = a2;
        }
        ++v7;
        ++v12;
      }
    }
  }
  if ( v12 < (unsigned __int16)v8 )
    return 1004;
  v23 = v11 - a5;
  *a6 = v23;
  result = 0;
  if ( v23 != (unsigned __int16)v23 )
    return 1006;
  return result;
}

```

## disassembly

```asm
0x180011640  mov     [rsp+arg_10], rbx
0x180011645  mov     [rsp+arg_18], r9
0x18001164a  mov     [rsp+arg_8], rdx
0x18001164f  mov     [rsp+arg_0], rcx
0x180011654  push    rbp
0x180011655  push    rsi
0x180011656  push    rdi
0x180011657  push    r12
0x180011659  push    r13
0x18001165b  push    r14
0x18001165d  push    r15
0x18001165f  sub     rsp, 30h
0x180011663  mov     r12d, [rsp+68h+arg_20]
0x18001166b  mov     r15d, 1
0x180011671  movzx   r14d, byte ptr [r9]
0x180011675  movzx   edi, r15w
0x180011679  movzx   r13d, r8w
0x18001167d  mov     r10, rdx
0x180011680  mov     r11, rcx
0x180011683  mov     ebx, r12d
0x180011686  xor     esi, esi
0x180011688  mov     ebp, 2
0x18001168d  mov     r8d, 4
0x180011693  cmp     di, r14w
0x180011697  ja      loc_1800117E0
0x18001169d  movzx   eax, di
0x1800116a0  movzx   edx, byte ptr [rax+r9]
0x1800116a5  mov     eax, edx
0x1800116a7  and     eax, 7
0x1800116aa  cmp     eax, 2
0x1800116ad  jnz     loc_180011775
0x1800116b3  test    dl, 10h
0x1800116b6  jnz     loc_18001174A
0x1800116bc  movzx   r8d, si
0x1800116c0  lea     rcx, [r8+2]
0x1800116c4  cmp     rcx, r13
0x1800116c7  ja      loc_1800118A3
0x1800116cd  lea     r15, [r8+r10]
0x1800116d1  test    dl, 20h
0x1800116d4  jnz     loc_180011877
0x1800116da  mov     r8, [r11]
0x1800116dd  movzx   r15d, word ptr [r15]
0x1800116e1  mov     word ptr [rsp+68h+arg_20], r15w
0x1800116ea  mov     [rsp+68h+var_48], 0
0x1800116f3  test    r8, r8
0x1800116f6  jz      short loc_180011758
0x1800116f8  lea     ebp, [rbx+2]
0x1800116fb  cmp     ebp, ebx
0x1800116fd  jb      short loc_180011758
0x1800116ff  mov     eax, [r11+8]
0x180011703  mov     dword ptr [rsp+68h+var_48], ebp
0x180011707  mov     r9, [rsp+68h+var_48]
0x18001170c  cmp     r9, rax
0x18001170f  ja      loc_1800118AD
0x180011715  movzx   eax, byte ptr [rsp+68h+arg_20+1]
0x18001171d  movzx   ecx, r15b
0x180011721  shl     cx, 8
0x180011725  or      cx, ax
0x180011728  mov     eax, ebx
0x18001172a  mov     ebx, ebp
0x18001172c  mov     ebp, 2
0x180011731  mov     [rax+r8], cx
0x180011736  mov     r9, [rsp+68h+arg_18]
0x18001173e  mov     r15d, 1
0x180011744  mov     r8d, 4
0x18001174a  movzx   eax, bp
0x18001174d  inc     di
0x180011750  add     si, ax
0x180011753  jmp     loc_180011693
0x180011758  mov     eax, 3EAh
0x18001175d  mov     rbx, [rsp+68h+arg_10]
0x180011765  add     rsp, 30h
0x180011769  pop     r15
0x18001176b  pop     r14
0x18001176d  pop     r13
0x18001176f  pop     r12
0x180011771  pop     rdi
0x180011772  pop     rsi
0x180011773  pop     rbp
0x180011774  retn
0x180011775  sub     eax, 1
0x180011778  jz      loc_180011825
0x18001177e  cmp     eax, 3
0x180011781  jnz     loc_1800118A3
0x180011787  test    dl, 10h
0x18001178a  jnz     short loc_1800117D1
0x18001178c  movzx   r9d, si
0x180011790  lea     rcx, [r9+4]
0x180011794  cmp     rcx, r13
0x180011797  ja      loc_1800118A3
0x18001179d  mov     rcx, r11
0x1800117a0  test    dl, 20h
0x1800117a3  jnz     short loc_180011814
0x1800117a5  mov     edx, [r9+r10]
0x1800117a9  mov     r8d, ebx
0x1800117ac  call    WriteLong
0x1800117b1  test    ax, ax
0x1800117b4  jnz     short loc_18001175D
0x1800117b6  mov     r11, [rsp+68h+arg_0]
0x1800117bb  add     ebx, 4
0x1800117be  mov     r9, [rsp+68h+arg_18]
0x1800117c6  mov     r8d, 4
0x1800117cc  mov     r10, [rsp+68h+arg_8]
0x1800117d1  movzx   eax, r8w
0x1800117d5  inc     di
0x1800117d8  add     si, ax
0x1800117db  jmp     loc_180011693
0x1800117e0  cmp     si, r13w
0x1800117e4  jb      loc_1800118A3
0x1800117ea  movzx   eax, bx
0x1800117ed  mov     edx, 3EEh
0x1800117f2  sub     ax, r12w
0x1800117f6  sub     ebx, r12d
0x1800117f9  movzx   ecx, ax
0x1800117fc  mov     rax, [rsp+68h+arg_28]
0x180011804  mov     [rax], cx
0x180011807  xor     eax, eax
0x180011809  cmp     ebx, ecx
0x18001180b  cmovnz  ax, dx
0x18001180f  jmp     loc_18001175D
0x180011814  lea     rdx, [r9+r10]
0x180011818  mov     r9, r8
0x18001181b  mov     r8d, ebx
0x18001181e  call    WriteBytes
0x180011823  jmp     short loc_1800117B1
0x180011825  test    dl, 10h
0x180011828  jnz     short loc_180011869
0x18001182a  movzx   edx, si
0x18001182d  lea     rcx, [rdx+1]
0x180011831  cmp     rcx, r13
0x180011834  ja      short loc_1800118A3
0x180011836  movzx   edx, byte ptr [rdx+r10]
0x18001183b  mov     r8d, ebx
0x18001183e  mov     rcx, r11
0x180011841  call    WriteByte
0x180011846  test    ax, ax
0x180011849  jnz     loc_18001175D
0x18001184f  mov     r11, [rsp+68h+arg_0]
0x180011854  inc     ebx
0x180011856  mov     r9, [rsp+68h+arg_18]
0x18001185e  mov     r8d, 4
0x180011864  mov     r10, [rsp+68h+arg_8]
0x180011869  mov     eax, r15d
0x18001186c  inc     di
0x18001186f  add     si, ax
0x180011872  jmp     loc_180011693
0x180011877  mov     r9, rbp
0x18001187a  mov     r8d, ebx
0x18001187d  mov     rdx, r15
0x180011880  mov     rcx, r11
0x180011883  call    WriteBytes
0x180011888  test    ax, ax
0x18001188b  jnz     loc_18001175D
0x180011891  mov     r11, [rsp+68h+arg_0]
0x180011896  add     ebx, 2
0x180011899  mov     r10, [rsp+68h+arg_8]
0x18001189e  jmp     loc_180011736
0x1800118a3  mov     eax, 3ECh
0x1800118a8  jmp     loc_18001175D
0x1800118ad  mov     r10, [r11+10h]
0x1800118b1  test    r10, r10
0x1800118b4  jz      loc_180011758
0x1800118ba  imul    ecx, eax, 0Bh
0x1800118bd  mov     eax, 0CCCCCCCDh
0x1800118c2  mul     ecx
0x1800118c4  shr     edx, 3
0x1800118c7  mov     eax, edx
0x1800118c9  cmp     rax, r9
0x1800118cc  jbe     short loc_1800118D4
0x1800118ce  mov     [r11+8], eax
0x1800118d2  jmp     short loc_1800118DA
0x1800118d4  mov     [r11+8], ebp
0x1800118d8  mov     eax, ebp
0x1800118da  mov     edx, eax
0x1800118dc  mov     rcx, r8
0x1800118df  mov     rax, r10
0x1800118e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118e7  mov     r11, [rsp+68h+arg_0]
0x1800118ec  mov     r8, rax
0x1800118ef  mov     [r11], rax
0x1800118f2  test    rax, rax
0x1800118f5  jz      short loc_180011901
0x1800118f7  mov     r10, [rsp+68h+arg_8]
0x1800118fc  jmp     loc_180011715
0x180011901  mov     dword ptr [r11+8], 0
0x180011909  mov     eax, 3EDh
0x18001190e  jmp     loc_18001175D
```
