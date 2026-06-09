# wil_details_FeatureReporting_IncrementUsageInCache

- ea: `0x18000ac40`
- end: `0x18000ad15`
- name: `wil_details_FeatureReporting_IncrementUsageInCache`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000aac4`

## callees

- `0x18000ac40`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_IncrementUsageInCache(
        volatile signed __int32 *a1,
        int a2,
        __int64 a3,
        _DWORD *a4)
{
  signed __int32 v4; // r8d
  _DWORD *v5; // r10
  BOOL v8; // edi
  unsigned int v9; // eax
  int v10; // edx
  unsigned int v11; // ecx
  unsigned int v12; // edx
  __int64 result; // rax

  v4 = *a1;
  v5 = a4 + 2;
  v8 = a2 == 4;
  while ( 1 )
  {
    a4[1] = 0;
    v9 = v4 | 1;
    if ( (((v4 | 1u) >> 14) & 1) != v8 )
    {
      if ( ((v9 >> 5) & 0x1FF) != 0 )
      {
        a4[1] = (v9 >> 5) & 0x1FF;
        v5 = a4 + 2;
        a4[2] = a2 == 0 ? 4 : 0;
        v9 = v4 & 0xFFFFC01E | 1;
      }
      v10 = 0;
      if ( a2 == 4 )
        v10 = 0x4000;
      v9 = v9 & 0xFFFFBFFF | v10;
    }
    v11 = (v9 >> 5) & 0x1FF;
    v12 = v11 + 1;
    if ( v11 + 1 > 0x1FF || v12 < v11 )
    {
      LOWORD(v12) = 1;
      *v5 = a2;
      a4[1] = v11;
    }
    else
    {
      v5 = a4 + 2;
    }
    result = (unsigned int)_InterlockedCompareExchange(
                             a1,
                             v9 ^ ((unsigned __int16)v9 ^ (unsigned __int16)(32 * v12)) & 0x3FE0,
                             v4);
    if ( v4 == (_DWORD)result )
      break;
    v4 = result;
  }
  a4[4] = 0;
  *a4 = (v4 & 1) == 0;
  return result;
}

```

## disassembly

```asm
0x18000ac40  push    rbx
0x18000ac42  push    rsi
0x18000ac43  push    rdi
0x18000ac44  mov     r8d, [rcx]
0x18000ac47  lea     r10, [r9+8]
0x18000ac4b  xor     edi, edi
0x18000ac4d  mov     ebx, edx
0x18000ac4f  cmp     edx, 4
0x18000ac52  mov     rsi, rcx
0x18000ac55  setz    dil
0x18000ac59  mov     eax, r8d
0x18000ac5c  mov     dword ptr [r9+4], 0
0x18000ac64  or      eax, 1
0x18000ac67  mov     ecx, eax
0x18000ac69  shr     ecx, 0Eh
0x18000ac6c  and     ecx, 1
0x18000ac6f  cmp     ecx, edi
0x18000ac71  jz      short loc_18000ACB5
0x18000ac73  mov     r11d, eax
0x18000ac76  shr     r11d, 5
0x18000ac7a  and     r11d, 1FFh
0x18000ac81  jbe     short loc_18000AC9E
0x18000ac83  mov     ecx, ebx
0x18000ac85  mov     [r9+4], r11d
0x18000ac89  neg     ecx
0x18000ac8b  lea     r10, [r9+8]
0x18000ac8f  sbb     edx, edx
0x18000ac91  not     edx
0x18000ac93  and     edx, 4
0x18000ac96  mov     [r10], edx
0x18000ac99  and     eax, 0FFFFC01Fh
0x18000ac9e  xor     edx, edx
0x18000aca0  mov     ecx, 4000h
0x18000aca5  cmp     ebx, 4
0x18000aca8  cmovz   edx, ecx
0x18000acab  mov     ecx, eax
0x18000acad  btr     ecx, 0Eh
0x18000acb1  mov     eax, edx
0x18000acb3  or      eax, ecx
0x18000acb5  mov     ecx, eax
0x18000acb7  shr     ecx, 5
0x18000acba  and     ecx, 1FFh
0x18000acc0  lea     edx, [rcx+1]
0x18000acc3  cmp     edx, 1FFh
0x18000acc9  ja      short loc_18000ACD5
0x18000accb  cmp     edx, ecx
0x18000accd  jb      short loc_18000ACD5
0x18000accf  lea     r10, [r9+8]
0x18000acd3  jmp     short loc_18000ACE1
0x18000acd5  mov     edx, 1
0x18000acda  mov     [r10], ebx
0x18000acdd  mov     [r9+4], ecx
0x18000ace1  shl     edx, 5
0x18000ace4  xor     edx, eax
0x18000ace6  and     edx, 3FE0h
0x18000acec  xor     edx, eax
0x18000acee  mov     eax, r8d
0x18000acf1  lock cmpxchg [rsi], edx
0x18000acf5  jz      short loc_18000ACFF
0x18000acf7  mov     r8d, eax
0x18000acfa  jmp     loc_18000AC59
0x18000acff  not     r8d
0x18000ad02  mov     dword ptr [r9+10h], 0
0x18000ad0a  and     r8d, 1
0x18000ad0e  mov     [r9], r8d
0x18000ad11  pop     rdi
0x18000ad12  pop     rsi
0x18000ad13  pop     rbx
0x18000ad14  retn
```
