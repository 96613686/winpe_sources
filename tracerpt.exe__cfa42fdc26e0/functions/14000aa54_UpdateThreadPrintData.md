# UpdateThreadPrintData

- ea: `0x14000aa54`
- end: `0x14000abad`
- name: `UpdateThreadPrintData`
- size: `345`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140007ec4`

## callees

- `0x14000aa54`

## pseudocode

```c
void __fastcall UpdateThreadPrintData(__int64 a1, _DWORD *a2, __int64 a3)
{
  __int64 v6; // r8
  _DWORD *v7; // r10
  int v8; // edx
  char v9; // al
  _DWORD *v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // r10
  int v13; // ecx
  int v14; // ecx
  int v15; // r8d
  int v16; // ecx

  if ( !a1 || !a2 || !a3 )
    return;
  v6 = 0;
  v7 = (_DWORD *)(a1 + 128);
  if ( !*(_DWORD *)(a1 + 128) )
  {
    v10 = (_DWORD *)(a1 + 128);
    goto LABEL_16;
  }
  v8 = a2[2];
  while ( *(_DWORD *)(a1 + 40 * v6 + 132) != v8 )
  {
    v6 = (unsigned int)(v6 + 1);
    if ( (unsigned int)v6 >= *v7 )
    {
      v9 = 0;
      goto LABEL_10;
    }
  }
  v9 = 1;
LABEL_10:
  if ( (unsigned int)v6 >= 0xA )
  {
    if ( !v9 )
      return;
    goto LABEL_17;
  }
  if ( !v9 )
  {
    v10 = (_DWORD *)(a1 + 128);
LABEL_16:
    *(_DWORD *)(a1 + 40 * v6 + 132) = a2[2];
    *v7 = *v10 + 1;
  }
LABEL_17:
  v11 = 5 * v6;
  v12 = (unsigned int)v6;
  v13 = *(_DWORD *)(a1 + 40 * v6 + 136);
  if ( v13 )
    *(_DWORD *)(a1 + 40 * v6 + 152) += dword_1400820F8 * a2[14] - v13;
  v14 = *(_DWORD *)(a1 + 40 * v6 + 140);
  if ( v14 )
    *(_DWORD *)(a1 + 40 * v6 + 156) += dword_1400820F8 * a2[15] - v14;
  v15 = *(_DWORD *)(a1 + 40 * v6 + 144);
  if ( v15 )
    *(_DWORD *)(a1 + 40 * v12 + 160) += *(_DWORD *)(a3 + 120) - v15;
  v16 = *(_DWORD *)(a1 + 8 * v11 + 148);
  if ( v16 )
    *(_DWORD *)(a1 + 8 * v11 + 164) += *(_DWORD *)(a3 + 124) - v16;
  *(_DWORD *)(a1 + 40 * v12 + 136) = dword_1400820F8 * a2[14];
  *(_DWORD *)(a1 + 40 * v12 + 140) = dword_1400820F8 * a2[15];
  *(_DWORD *)(a1 + 8 * v11 + 144) = *(_DWORD *)(a3 + 120);
  *(_DWORD *)(a1 + 8 * v11 + 148) = *(_DWORD *)(a3 + 124);
}

```

## disassembly

```asm
0x14000aa54  mov     [rsp+arg_0], rbx
0x14000aa59  mov     rbx, r8
0x14000aa5c  mov     r11, rdx
0x14000aa5f  mov     r9, rcx
0x14000aa62  test    rcx, rcx
0x14000aa65  jz      loc_14000ABA7
0x14000aa6b  test    rdx, rdx
0x14000aa6e  jz      loc_14000ABA7
0x14000aa74  test    rbx, rbx
0x14000aa77  jz      loc_14000ABA7
0x14000aa7d  xor     r8d, r8d
0x14000aa80  lea     r10, [rcx+80h]
0x14000aa87  cmp     [r10], r8d
0x14000aa8a  jbe     short loc_14000AAC8
0x14000aa8c  mov     edx, [rdx+8]
0x14000aa8f  lea     rcx, [r8+r8*4]
0x14000aa93  cmp     [r9+rcx*8+84h], edx
0x14000aa9b  jz      short loc_14000AAA9
0x14000aa9d  inc     r8d
0x14000aaa0  cmp     r8d, [r10]
0x14000aaa3  jb      short loc_14000AA8F
0x14000aaa5  xor     al, al
0x14000aaa7  jmp     short loc_14000AAAB
0x14000aaa9  mov     al, 1
0x14000aaab  cmp     r8d, 0Ah
0x14000aaaf  jnb     short loc_14000AABE
0x14000aab1  test    al, al
0x14000aab3  jnz     short loc_14000AAE2
0x14000aab5  lea     rdx, [r9+80h]
0x14000aabc  jmp     short loc_14000AACB
0x14000aabe  test    al, al
0x14000aac0  jz      loc_14000ABA7
0x14000aac6  jmp     short loc_14000AAE2
0x14000aac8  mov     rdx, r10
0x14000aacb  mov     eax, [r11+8]
0x14000aacf  lea     rcx, [r8+r8*4]
0x14000aad3  mov     [r9+rcx*8+84h], eax
0x14000aadb  mov     eax, [rdx]
0x14000aadd  inc     eax
0x14000aadf  mov     [r10], eax
0x14000aae2  lea     rdx, [r8+r8*4]
0x14000aae6  mov     r10d, r8d
0x14000aae9  mov     ecx, [r9+rdx*8+88h]
0x14000aaf1  test    ecx, ecx
0x14000aaf3  jz      short loc_14000AB0A
0x14000aaf5  mov     eax, [r11+38h]
0x14000aaf9  imul    eax, cs:dword_1400820F8
0x14000ab00  sub     eax, ecx
0x14000ab02  add     [r9+rdx*8+98h], eax
0x14000ab0a  mov     ecx, [r9+rdx*8+8Ch]
0x14000ab12  test    ecx, ecx
0x14000ab14  jz      short loc_14000AB2B
0x14000ab16  mov     eax, [r11+3Ch]
0x14000ab1a  imul    eax, cs:dword_1400820F8
0x14000ab21  sub     eax, ecx
0x14000ab23  add     [r9+rdx*8+9Ch], eax
0x14000ab2b  mov     r8d, [r9+rdx*8+90h]
0x14000ab33  test    r8d, r8d
0x14000ab36  jz      short loc_14000AB4A
0x14000ab38  mov     eax, [rbx+78h]
0x14000ab3b  lea     rcx, [r10+r10*4]
0x14000ab3f  sub     eax, r8d
0x14000ab42  add     [r9+rcx*8+0A0h], eax
0x14000ab4a  mov     ecx, [r9+rdx*8+94h]
0x14000ab52  test    ecx, ecx
0x14000ab54  jz      short loc_14000AB63
0x14000ab56  mov     eax, [rbx+7Ch]
0x14000ab59  sub     eax, ecx
0x14000ab5b  add     [r9+rdx*8+0A4h], eax
0x14000ab63  mov     ecx, [r11+38h]
0x14000ab67  lea     rax, [r10+r10*4]
0x14000ab6b  imul    ecx, cs:dword_1400820F8
0x14000ab72  mov     [r9+rax*8+88h], ecx
0x14000ab7a  lea     rax, [r10+r10*4]
0x14000ab7e  mov     ecx, [r11+3Ch]
0x14000ab82  imul    ecx, cs:dword_1400820F8
0x14000ab89  mov     [r9+rax*8+8Ch], ecx
0x14000ab91  mov     eax, [rbx+78h]
0x14000ab94  mov     [r9+rdx*8+90h], eax
0x14000ab9c  mov     eax, [rbx+7Ch]
0x14000ab9f  mov     [r9+rdx*8+94h], eax
0x14000aba7  mov     rbx, [rsp+arg_0]
0x14000abac  retn
```
