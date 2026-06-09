# VmpBuildName

- ea: `0x140015490`
- end: `0x1400156be`
- name: `VmpBuildName`
- size: `558`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14000f19c`
- `0x1400114f8`
- `0x140011920`

## callees

- `0x140005240`
- `0x140015490`

## import_xrefs

- `ntoskrnl!_itow_s` at `0x14001550c`
- `ntoskrnl!_itow_s` at `0x14001568c`
- `ntoskrnl!_itow_s` at `0x14001550c`
- `ntoskrnl!_itow_s` at `0x14001568c`

## pseudocode

```c
__int64 __fastcall VmpBuildName(__int64 a1, int a2, int a3, int a4)
{
  unsigned __int64 v4; // rbp
  unsigned __int16 v6; // r15
  const wchar_t *v7; // rdx
  char *v10; // rsi
  wchar_t *v11; // rdi
  errno_t v12; // ecx
  __int64 v14; // r15
  __int64 v15; // r8
  int v16; // r14d
  int v17; // r14d
  int v18; // r14d
  wchar_t *v19; // rdx
  wchar_t *v20; // rsi
  __int64 v21; // rax
  wchar_t *Src; // [rsp+60h] [rbp+8h]

  LOWORD(v4) = *(_WORD *)(a1 + 2);
  v6 = 0;
  v7 = 0;
  *(_WORD *)a1 = 0;
  Src = 0;
  switch ( a2 )
  {
    case 0:
      v7 = L"\\Device\\HarddiskVolume";
      v6 = 44;
      goto LABEL_14;
    case 1:
    case 2:
      v7 = L"\\Device\\Harddisk";
      v6 = 32;
      goto LABEL_14;
    case 3:
      v7 = L"\\DosDevices\\HarddiskVolume";
      v6 = 52;
      goto LABEL_14;
    case 4:
    case 5:
      v7 = L"\\DosDevices\\Harddisk";
      v6 = 40;
LABEL_14:
      Src = (wchar_t *)v7;
      if ( (unsigned __int16)v4 >= v6 )
        goto LABEL_2;
      v12 = -1073741789;
      goto LABEL_4;
    default:
LABEL_2:
      v10 = *(char **)(a1 + 8);
      memmove(v10, v7, v6);
      LODWORD(v4) = (unsigned __int16)(v4 - v6);
      v11 = (wchar_t *)&v10[2 * ((unsigned __int64)v6 >> 1)];
      v12 = _itow_s(a3, v11, (unsigned __int64)(unsigned int)v4 >> 1, 10);
      if ( v12 < 0 )
        goto LABEL_3;
      v14 = -1;
      do
        ++v14;
      while ( v11[v14] );
      LOWORD(v4) = v4 - 2 * v14;
      if ( a2 != 3 )
      {
        v15 = (unsigned __int16)v14;
        if ( a2 )
        {
          v16 = a2 - 1;
          if ( v16 )
          {
            v17 = v16 - 1;
            if ( v17 )
            {
              v18 = v17 - 2;
              if ( v18 )
              {
                if ( v18 == 1 )
                {
                  v19 = L"ClusterPartition";
                  LOWORD(v14) = 32;
                }
                else
                {
                  v19 = Src;
                }
              }
              else
              {
                v19 = L"Partition";
                LOWORD(v14) = 18;
              }
            }
            else
            {
              v19 = L"\\ClusterPartition";
              LOWORD(v14) = 34;
            }
          }
          else
          {
            v19 = L"\\Partition";
            LOWORD(v14) = 20;
          }
          if ( (unsigned __int16)v4 < (unsigned __int16)v14
            || (v20 = &v11[v15],
                memmove(v20, v19, (unsigned __int16)v14),
                v4 = (unsigned __int16)(v4 - v14),
                v12 = _itow_s(a4, &v20[(unsigned __int64)(unsigned __int16)v14 >> 1], v4 >> 1, 10),
                v12 < 0) )
          {
LABEL_3:
            v12 = -1073741789;
          }
          else
          {
            v21 = -1;
            do
              ++v21;
            while ( v20[((unsigned __int64)(unsigned __int16)v14 >> 1) + v21] );
            LOWORD(v4) = v4 - 2 * v21;
          }
        }
      }
LABEL_4:
      *(_WORD *)a1 = *(_WORD *)(a1 + 2) - v4;
      return (unsigned int)v12;
  }
}

```

## disassembly

```asm
0x140015490  mov     [rsp+Val], r9d
0x140015495  push    rbx
0x140015496  push    rbp
0x140015497  push    r12
0x140015499  push    r13
0x14001549b  push    r14
0x14001549d  push    r15
0x14001549f  sub     rsp, 28h
0x1400154a3  movzx   ebp, word ptr [rcx+2]
0x1400154a7  xor     eax, eax
0x1400154a9  movsxd  r14, edx
0x1400154ac  xor     r15d, r15d
0x1400154af  xor     edx, edx; Src
0x1400154b1  mov     [rcx], ax
0x1400154b4  mov     [rsp+58h+Src], rdx
0x1400154b9  mov     r13d, r8d
0x1400154bc  mov     rbx, rcx
0x1400154bf  mov     r12d, 20h ; ' '
0x1400154c5  cmp     r14d, 5; switch 6 cases
0x1400154c9  jbe     loc_1400155C9
0x1400154cf  mov     [rsp+58h+arg_8], rsi; jumptable 00000001400155DB default case
0x1400154d4  mov     rsi, [rbx+8]
0x1400154d8  mov     [rsp+58h+var_38], rdi
0x1400154dd  mov     rcx, rsi; void *
0x1400154e0  movzx   edi, r15w
0x1400154e4  mov     r8d, edi; Size
0x1400154e7  call    memmove
0x1400154ec  shr     rdi, 1
0x1400154ef  sub     bp, r15w
0x1400154f3  movzx   ebp, bp
0x1400154f6  mov     r9d, 0Ah; Radix
0x1400154fc  mov     r8d, ebp
0x1400154ff  mov     ecx, r13d; Val
0x140015502  shr     r8, 1; SizeInWords
0x140015505  lea     rdi, [rsi+rdi*2]
0x140015509  mov     rdx, rdi; DstBuf
0x14001550c  call    cs:__imp__itow_s
0x140015513  nop     dword ptr [rax+rax+00h]
0x140015518  mov     ecx, eax
0x14001551a  test    eax, eax
0x14001551c  jns     short loc_140015549
0x14001551e  mov     ecx, 0C0000023h
0x140015523  mov     rsi, [rsp+58h+arg_8]
0x140015528  mov     rdi, [rsp+58h+var_38]
0x14001552d  movzx   eax, word ptr [rbx+2]
0x140015531  sub     ax, bp
0x140015534  mov     [rbx], ax
0x140015537  mov     eax, ecx
0x140015539  add     rsp, 28h
0x14001553d  pop     r15
0x14001553f  pop     r14
0x140015541  pop     r13
0x140015543  pop     r12
0x140015545  pop     rbp
0x140015546  pop     rbx
0x140015547  retn
0x140015549  mov     r15, 0FFFFFFFFFFFFFFFFh
0x140015550  inc     r15
0x140015553  cmp     word ptr [rdi+r15*2], 0
0x140015559  jnz     short loc_140015550
0x14001555b  movzx   eax, r15w
0x14001555f  add     ax, ax
0x140015562  sub     bp, ax
0x140015565  movzx   r13d, bp
0x140015569  cmp     r14d, 3
0x14001556d  jz      short loc_140015523
0x14001556f  movzx   r8d, r15w
0x140015573  test    r14d, r14d
0x140015576  jz      short loc_140015523
0x140015578  sub     r14d, 1
0x14001557c  jz      loc_140015639
0x140015582  sub     r14d, 1
0x140015586  jz      loc_14001562A
0x14001558c  sub     r14d, 2
0x140015590  jz      loc_14001561B
0x140015596  cmp     r14d, 1
0x14001559a  jnz     loc_140015648
0x1400155a0  lea     rdx, aClusterpartiti+2; "ClusterPartition"
0x1400155a7  movzx   r15d, r12w
0x1400155ab  jmp     loc_14001564D
0x1400155b0  mov     [rsp+58h+Src], rdx
0x1400155b5  cmp     bp, r15w
0x1400155b9  jnb     def_1400155DB; jumptable 00000001400155DB default case
0x1400155bf  mov     ecx, 0C0000023h
0x1400155c4  jmp     loc_14001552D
0x1400155c9  lea     r8, cs:140000000h
0x1400155d0  mov     ecx, ds:(jpt_1400155DB - 140000000h)[r8+r14*4]
0x1400155d8  add     rcx, r8
0x1400155db  jmp     rcx; switch jump
0x1400155e1  lea     rdx, aDeviceHarddisk_0; jumptable 00000001400155DB case 0
0x1400155e8  mov     r15d, 2Ch ; ','
0x1400155ee  jmp     short loc_1400155B0
0x1400155f0  lea     rdx, aDeviceHarddisk_1; jumptable 00000001400155DB cases 1,2
0x1400155f7  movzx   r15d, r12w
0x1400155fb  jmp     short loc_1400155B0
0x1400155fd  lea     rdx, aDosdevicesHard; jumptable 00000001400155DB case 3
0x140015604  mov     r15d, 34h ; '4'
0x14001560a  jmp     short loc_1400155B0
0x14001560c  lea     rdx, aDosdevicesHard_0; jumptable 00000001400155DB cases 4,5
0x140015613  mov     r15d, 28h ; '('
0x140015619  jmp     short loc_1400155B0
0x14001561b  lea     rdx, aPartition+2; "Partition"
0x140015622  mov     r15d, 12h
0x140015628  jmp     short loc_14001564D
0x14001562a  lea     rdx, aClusterpartiti; "\\ClusterPartition"
0x140015631  mov     r15d, 22h ; '"'
0x140015637  jmp     short loc_14001564D
0x140015639  lea     rdx, aPartition; "\\Partition"
0x140015640  mov     r15d, 14h
0x140015646  jmp     short loc_14001564D
0x140015648  mov     rdx, [rsp+58h+Src]; Src
0x14001564d  cmp     r13w, r15w
0x140015651  jb      loc_14001551E
0x140015657  lea     rsi, [rdi+r8*2]
0x14001565b  movzx   edi, r15w
0x14001565f  mov     r8d, edi; Size
0x140015662  mov     rcx, rsi; void *
0x140015665  call    memmove
0x14001566a  mov     ecx, [rsp+58h+Val]; Val
0x14001566e  sub     r13w, r15w
0x140015672  shr     rdi, 1
0x140015675  mov     r9d, 0Ah; Radix
0x14001567b  movzx   ebp, r13w
0x14001567f  mov     r8d, ebp
0x140015682  shr     r8, 1; SizeInWords
0x140015685  lea     rdi, [rsi+rdi*2]
0x140015689  mov     rdx, rdi; DstBuf
0x14001568c  call    cs:__imp__itow_s
0x140015693  nop     dword ptr [rax+rax+00h]
0x140015698  mov     ecx, eax
0x14001569a  test    eax, eax
0x14001569c  js      loc_14001551E
0x1400156a2  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1400156a9  inc     rax
0x1400156ac  cmp     word ptr [rdi+rax*2], 0
0x1400156b1  jnz     short loc_1400156A9
0x1400156b3  add     ax, ax
0x1400156b6  sub     bp, ax
0x1400156b9  jmp     loc_140015523
```
