# CiGetNtHeaderDirectoryEntry

- ea: `0x180047128`
- end: `0x180047221`
- name: `CiGetNtHeaderDirectoryEntry`
- size: `249`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180012d40`

## callees

- `0x180010a88`
- `0x180047128`

## pseudocode

```c
NTSTATUS __fastcall CiGetNtHeaderDirectoryEntry(__int64 a1, unsigned int a2, unsigned int a3, _QWORD *a4)
{
  __int64 v6; // rcx
  unsigned int v7; // r9d
  NTSTATUS result; // eax
  ULONG v9; // r9d
  __int64 v10; // r10
  unsigned int v11; // r11d
  unsigned int v12; // ecx
  int v13; // edx
  unsigned int v14; // eax
  ULONG pulResult; // [rsp+20h] [rbp-18h] BYREF
  int v16; // [rsp+24h] [rbp-14h]

  pulResult = 0;
  v6 = 116;
  if ( *(_WORD *)(a1 + 24) != 267 )
    v6 = 132;
  v7 = 120;
  if ( *(_WORD *)(a1 + 24) != 267 )
    v7 = 136;
  if ( a2 < v7 )
    return -1073741275;
  if ( *(_DWORD *)(v6 + a1) > a3 )
  {
    result = RtlULongLongToULong(8LL * a3, &pulResult);
    v16 = result;
    if ( result >= 0 )
    {
      v12 = v9 + pulResult;
      v13 = -1073741675;
      if ( v9 + pulResult < v9 )
      {
        pulResult = -1;
        result = -1073741675;
        v12 = -1;
      }
      else
      {
        pulResult += v9;
        result = 0;
      }
      v16 = result;
      if ( result >= 0 )
      {
        v14 = v12 + 8;
        if ( v12 + 8 < v12 )
        {
          pulResult = -1;
          v14 = -1;
        }
        else
        {
          pulResult = v12 + 8;
          v13 = 0;
        }
        v16 = v13;
        if ( v13 < 0 || v14 > v11 )
        {
          return -1073741275;
        }
        else
        {
          *a4 = *(_QWORD *)(v12 + v10);
          return 0;
        }
      }
    }
  }
  else
  {
    result = -1073741275;
    v16 = -1073741275;
  }
  return result;
}

```

## disassembly

```asm
0x180047128  mov     [rsp+arg_0], rbx
0x18004712d  push    rdi
0x18004712e  sub     rsp, 30h
0x180047132  mov     rbx, r9
0x180047135  mov     r11d, edx
0x180047138  mov     r10, rcx
0x18004713b  mov     [rsp+38h+pulResult], 0
0x180047143  mov     edi, 10Bh
0x180047148  mov     ecx, 74h ; 't'
0x18004714d  lea     edx, [rcx+10h]
0x180047150  cmp     [r10+18h], di
0x180047155  cmovnz  ecx, edx
0x180047158  mov     edx, 88h
0x18004715d  lea     r9d, [rdx-10h]
0x180047161  cmovnz  r9d, edx
0x180047165  cmp     r11d, r9d
0x180047168  jnb     short loc_180047174
0x18004716a  mov     eax, 0C0000225h
0x18004716f  jmp     loc_180047215
0x180047174  cmp     [rcx+r10], r8d
0x180047178  ja      short loc_180047188
0x18004717a  mov     eax, 0C0000225h
0x18004717f  mov     [rsp+38h+var_14], eax
0x180047183  jmp     loc_180047215
0x180047188  mov     ecx, r8d
0x18004718b  shl     rcx, 3; ullOperand
0x18004718f  lea     rdx, [rsp+38h+pulResult]; pulResult
0x180047194  call    RtlULongLongToULong
0x180047199  mov     [rsp+38h+var_14], eax
0x18004719d  test    eax, eax
0x18004719f  js      short loc_180047215
0x1800471a1  mov     ecx, [rsp+38h+pulResult]
0x1800471a5  add     ecx, r9d
0x1800471a8  mov     edx, 0C0000095h
0x1800471ad  cmp     ecx, r9d
0x1800471b0  jb      short loc_1800471BE
0x1800471b2  mov     [rsp+38h+pulResult], ecx
0x1800471b6  xor     eax, eax
0x1800471b8  or      r8d, 0FFFFFFFFh
0x1800471bc  jmp     short loc_1800471CC
0x1800471be  or      r8d, 0FFFFFFFFh
0x1800471c2  mov     [rsp+38h+pulResult], r8d
0x1800471c7  mov     eax, edx
0x1800471c9  mov     ecx, r8d
0x1800471cc  mov     [rsp+38h+var_14], eax
0x1800471d0  test    eax, eax
0x1800471d2  js      short loc_180047215
0x1800471d4  mov     r9d, ecx
0x1800471d7  lea     eax, [rcx+8]
0x1800471da  cmp     eax, ecx
0x1800471dc  jb      short loc_1800471E6
0x1800471de  mov     [rsp+38h+pulResult], eax
0x1800471e2  xor     edx, edx
0x1800471e4  jmp     short loc_1800471EE
0x1800471e6  mov     [rsp+38h+pulResult], r8d
0x1800471eb  mov     eax, r8d
0x1800471ee  mov     [rsp+38h+var_14], edx
0x1800471f2  test    edx, edx
0x1800471f4  js      short loc_180047206
0x1800471f6  cmp     eax, r11d
0x1800471f9  ja      short loc_180047206
0x1800471fb  mov     rax, [r9+r10]
0x1800471ff  mov     [rbx], rax
0x180047202  xor     eax, eax
0x180047204  jmp     short loc_180047215
0x180047206  mov     eax, 0C0000225h
0x18004720b  mov     [rsp+38h+var_14], eax
0x18004720f  jmp     short loc_180047215
0x180047211  mov     [rsp+38h+var_14], eax
0x180047215  mov     rbx, [rsp+38h+arg_0]
0x18004721a  add     rsp, 30h
0x18004721e  pop     rdi
0x18004721f  retn
```
