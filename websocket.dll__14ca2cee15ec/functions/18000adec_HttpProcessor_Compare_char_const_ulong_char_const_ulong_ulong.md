# HttpProcessor::Compare(char * const,ulong,char * const,ulong,ulong)

- ea: `0x18000adec`
- end: `0x18000af28`
- name: `?Compare@HttpProcessor@@SAHQEADK0KK@Z`
- size: `316`
- prototype: `__int64 __fastcall(char *const, int, char *const, int, char)`
- caller_count: `9`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800098e0`
- `0x1800099a0`
- `0x180009aa0`
- `0x18000a438`
- `0x18000a8a0`
- `0x18000ab90`
- `0x18000ac70`
- `0x18000b194`
- `0x18000b4f4`

## callees

- `0x18000adec`

## pseudocode

```c
__int64 __fastcall HttpProcessor::Compare(char *const a1, int a2, char *const a3, int a4, char a5)
{
  BOOL v5; // ebp
  char *v6; // r10
  char *v7; // r11
  int v8; // ebx
  int v9; // edi
  __int64 v10; // r12
  unsigned __int64 v11; // rdx
  unsigned __int64 v12; // r9

  v5 = 0;
  v6 = &a1[a2];
  v7 = &a3[a4];
  v8 = 0;
  v9 = 0;
  v10 = 0x100002600LL;
  while ( a1 < v6 && a3 < v7 )
  {
    v11 = *a1;
    v12 = *a3;
    if ( (a5 & 2) == 0 || v5 )
    {
LABEL_10:
      if ( (_BYTE)v11 == 92 )
      {
        if ( !v8 )
        {
          v8 = 1;
          goto LABEL_7;
        }
        v8 = 0;
      }
      if ( (_BYTE)v12 == 92 )
      {
        if ( !v9 )
        {
          v9 = 1;
          goto LABEL_17;
        }
        v9 = 0;
      }
      if ( (a5 & 1) != 0 )
      {
        if ( (unsigned __int8)(v11 - 65) <= 0x19u )
          LOBYTE(v11) = v11 + 32;
        if ( (unsigned __int8)(v12 - 65) <= 0x19u )
          LOBYTE(v12) = v12 + 32;
      }
      if ( (_BYTE)v11 != (_BYTE)v12 )
        return (unsigned int)((char)v12 - (char)v11);
      if ( (_BYTE)v11 == 34 && !v8 && !v9 )
        v5 = !v5;
      ++a1;
      ++a3;
      v9 = 0;
      v8 = 0;
    }
    else if ( (unsigned __int8)v11 <= 0x20u && _bittest64(&v10, v11) )
    {
LABEL_7:
      ++a1;
    }
    else
    {
      if ( (unsigned __int8)v12 > 0x20u || !_bittest64(&v10, v12) )
        goto LABEL_10;
LABEL_17:
      ++a3;
    }
  }
  if ( (a5 & 2) != 0 )
  {
    while ( a1 < v6 && (unsigned __int8)*a1 <= 0x20u && _bittest64(&v10, *a1) )
      ++a1;
    while ( a3 < v7 && (unsigned __int8)*a3 <= 0x20u && _bittest64(&v10, *a3) )
      ++a3;
  }
  if ( a1 < v6 )
    return (unsigned int)(a3 != v7) - 1;
  if ( a1 == v6 )
    return a3 < v7;
  return 0;
}

```

## disassembly

```asm
0x18000adec  push    rbx
0x18000adee  push    rbp
0x18000adef  push    rdi
0x18000adf0  push    r12
0x18000adf2  mov     r10d, edx
0x18000adf5  xor     ebp, ebp
0x18000adf7  mov     r11d, r9d
0x18000adfa  add     r10, rcx
0x18000adfd  add     r11, r8
0x18000ae00  xor     ebx, ebx
0x18000ae02  xor     edi, edi
0x18000ae04  mov     r12, 100002600h
0x18000ae0e  jmp     loc_18000AEB5
0x18000ae13  cmp     r8, r11
0x18000ae16  jnb     loc_18000AEBE
0x18000ae1c  test    [rsp+20h+arg_20], 2
0x18000ae21  movsx   rdx, byte ptr [rcx]
0x18000ae25  movsx   r9, byte ptr [r8]
0x18000ae29  jz      short loc_18000AE4B
0x18000ae2b  test    ebp, ebp
0x18000ae2d  jnz     short loc_18000AE4B
0x18000ae2f  cmp     dl, 20h ; ' '
0x18000ae32  ja      short loc_18000AE3F
0x18000ae34  bt      r12, rdx
0x18000ae38  jnb     short loc_18000AE3F
0x18000ae3a  inc     rcx
0x18000ae3d  jmp     short loc_18000AEB5
0x18000ae3f  cmp     r9b, 20h ; ' '
0x18000ae43  ja      short loc_18000AE4B
0x18000ae45  bt      r12, r9
0x18000ae49  jb      short loc_18000AE6C
0x18000ae4b  cmp     dl, 5Ch ; '\'
0x18000ae4e  jnz     short loc_18000AE5D
0x18000ae50  test    ebx, ebx
0x18000ae52  jnz     short loc_18000AE5B
0x18000ae54  mov     ebx, 1
0x18000ae59  jmp     short loc_18000AE3A
0x18000ae5b  xor     ebx, ebx
0x18000ae5d  cmp     r9b, 5Ch ; '\'
0x18000ae61  jnz     short loc_18000AE73
0x18000ae63  test    edi, edi
0x18000ae65  jnz     short loc_18000AE71
0x18000ae67  mov     edi, 1
0x18000ae6c  inc     r8
0x18000ae6f  jmp     short loc_18000AEB5
0x18000ae71  xor     edi, edi
0x18000ae73  test    [rsp+20h+arg_20], 1
0x18000ae78  jz      short loc_18000AE90
0x18000ae7a  lea     eax, [rdx-41h]
0x18000ae7d  cmp     al, 19h
0x18000ae7f  ja      short loc_18000AE84
0x18000ae81  add     dl, 20h ; ' '
0x18000ae84  lea     eax, [r9-41h]
0x18000ae88  cmp     al, 19h
0x18000ae8a  ja      short loc_18000AE90
0x18000ae8c  add     r9b, 20h ; ' '
0x18000ae90  cmp     dl, r9b
0x18000ae93  jnz     short loc_18000AEC7
0x18000ae95  cmp     dl, 22h ; '"'
0x18000ae98  jnz     short loc_18000AEAB
0x18000ae9a  test    ebx, ebx
0x18000ae9c  jnz     short loc_18000AEAB
0x18000ae9e  test    edi, edi
0x18000aea0  jnz     short loc_18000AEAB
0x18000aea2  xor     eax, eax
0x18000aea4  test    ebp, ebp
0x18000aea6  setz    al
0x18000aea9  mov     ebp, eax
0x18000aeab  inc     rcx
0x18000aeae  inc     r8
0x18000aeb1  xor     edi, edi
0x18000aeb3  xor     ebx, ebx
0x18000aeb5  cmp     rcx, r10
0x18000aeb8  jb      loc_18000AE13
0x18000aebe  test    [rsp+20h+arg_20], 2
0x18000aec3  jz      short loc_18000AF03
0x18000aec5  jmp     short loc_18000AEE4
0x18000aec7  movsx   eax, r9b
0x18000aecb  movsx   ecx, dl
0x18000aece  sub     eax, ecx
0x18000aed0  jmp     short loc_18000AF22
0x18000aed2  cmp     byte ptr [rcx], 20h ; ' '
0x18000aed5  ja      short loc_18000AEFE
0x18000aed7  movsx   rax, byte ptr [rcx]
0x18000aedb  bt      r12, rax
0x18000aedf  jnb     short loc_18000AEFE
0x18000aee1  inc     rcx
0x18000aee4  cmp     rcx, r10
0x18000aee7  jb      short loc_18000AED2
0x18000aee9  jmp     short loc_18000AEFE
0x18000aeeb  cmp     byte ptr [r8], 20h ; ' '
0x18000aeef  ja      short loc_18000AF03
0x18000aef1  movsx   rax, byte ptr [r8]
0x18000aef5  bt      r12, rax
0x18000aef9  jnb     short loc_18000AF03
0x18000aefb  inc     r8
0x18000aefe  cmp     r8, r11
0x18000af01  jb      short loc_18000AEEB
0x18000af03  cmp     rcx, r10
0x18000af06  jnb     short loc_18000AF14
0x18000af08  xor     eax, eax
0x18000af0a  cmp     r8, r11
0x18000af0d  setnz   al
0x18000af10  dec     eax
0x18000af12  jmp     short loc_18000AF22
0x18000af14  jnz     short loc_18000AF20
0x18000af16  xor     eax, eax
0x18000af18  cmp     r8, r11
0x18000af1b  setb    al
0x18000af1e  jmp     short loc_18000AF22
0x18000af20  xor     eax, eax
0x18000af22  pop     r12
0x18000af24  pop     rdi
0x18000af25  pop     rbp
0x18000af26  pop     rbx
0x18000af27  retn
```
