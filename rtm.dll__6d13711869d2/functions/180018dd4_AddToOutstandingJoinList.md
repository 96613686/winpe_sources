# AddToOutstandingJoinList

- ea: `0x180018dd4`
- end: `0x18001908d`
- name: `AddToOutstandingJoinList`
- size: `697`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18001928c`
- `0x180019a1c`

## callees

- `0x180014d2c`
- `0x180015178`
- `0x180018dd4`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`
- `0x180020010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180018fb5`
- `KERNEL32!HeapAlloc` at `0x180018fb5`
- `KERNEL32!HeapFree` at `0x180018f9a`
- `KERNEL32!HeapFree` at `0x180018f9a`

## string_xrefs

- `0x180018fdb`: `Failed to create Join Entry : %x`

## pseudocode

```c
__int64 __fastcall AddToOutstandingJoinList(
        unsigned int a1,
        int a2,
        unsigned int a3,
        int a4,
        unsigned int a5,
        unsigned int a6,
        int a7)
{
  LPVOID *v11; // rcx
  LPVOID *v12; // rbx
  LPVOID *v13; // rdi
  unsigned int v14; // r8d
  int v15; // edx
  unsigned int v16; // r8d
  int v17; // edx
  unsigned int v18; // r8d
  int v19; // edx
  _QWORD *v20; // rax
  LPVOID *v21; // rdx
  LPVOID **v22; // rax
  LPVOID **v23; // rcx
  unsigned int v24; // ebx
  LPVOID **v25; // rax
  int v27; // [rsp+20h] [rbp-858h] BYREF
  char v28[2044]; // [rsp+24h] [rbp-854h] BYREF

  v27 = 0;
  memset_0(v28, 0, sizeof(v28));
  AcquireWriteLock(&qword_18002B9D8);
  v11 = (LPVOID *)qword_18002B9C8;
  v12 = &qword_18002B9C8;
  v13 = 0;
  if ( qword_18002B9C8 != &qword_18002B9C8 )
  {
    while ( 1 )
    {
      v14 = *((_DWORD *)v11 + 6);
      v15 = (unsigned __int8)v14 - (unsigned __int8)a3;
      if ( (unsigned __int8)v14 == (unsigned __int8)a3 )
      {
        v15 = ((_DWORD)v11[3] & 0xFF00) - (a3 & 0xFF00);
        if ( ((_DWORD)v11[3] & 0xFF00) == (a3 & 0xFF00) )
        {
          v15 = (v14 & 0xFF0000) - (a3 & 0xFF0000);
          if ( (v14 & 0xFF0000) == (a3 & 0xFF0000) )
            v15 = ((v14 >> 8) & 0xFF0000) - ((a3 >> 8) & 0xFF0000);
        }
      }
      if ( v15 >= 0 )
      {
        if ( v15 > 0 )
          goto LABEL_28;
        v16 = *((_DWORD *)v11 + 4);
        v17 = (unsigned __int8)v16 - (unsigned __int8)a1;
        if ( (unsigned __int8)v16 == (unsigned __int8)a1 )
        {
          v17 = ((_DWORD)v11[2] & 0xFF00) - (a1 & 0xFF00);
          if ( ((_DWORD)v11[2] & 0xFF00) == (a1 & 0xFF00) )
          {
            v17 = (v16 & 0xFF0000) - (a1 & 0xFF0000);
            if ( (v16 & 0xFF0000) == (a1 & 0xFF0000) )
              v17 = ((v16 >> 8) & 0xFF0000) - ((a1 >> 8) & 0xFF0000);
          }
        }
        if ( v17 >= 0 )
        {
          if ( v17 > 0 )
            goto LABEL_28;
          if ( *((_DWORD *)v11 + 8) >= a5 )
          {
            if ( *((_DWORD *)v11 + 8) > a5 )
              goto LABEL_28;
            v18 = *((_DWORD *)v11 + 9);
            v19 = (unsigned __int8)v18 - (unsigned __int8)a6;
            if ( (unsigned __int8)v18 == (unsigned __int8)a6 )
            {
              v19 = (*((_DWORD *)v11 + 9) & 0xFF00) - (a6 & 0xFF00);
              if ( (*((_DWORD *)v11 + 9) & 0xFF00) == (a6 & 0xFF00) )
              {
                v19 = (v18 & 0xFF0000) - (a6 & 0xFF0000);
                if ( (v18 & 0xFF0000) == (a6 & 0xFF0000) )
                  v19 = ((v18 >> 8) & 0xFF0000) - ((a6 >> 8) & 0xFF0000);
              }
            }
            if ( v19 >= 0 )
              break;
          }
        }
      }
      v11 = (LPVOID *)*v11;
      if ( v11 == &qword_18002B9C8 )
        goto LABEL_29;
    }
    if ( v19 <= 0 )
    {
      if ( *((_DWORD *)v11 + 10) == a7 )
      {
LABEL_37:
        v24 = 0;
        goto LABEL_38;
      }
      v20 = *v11;
      if ( *((LPVOID **)*v11 + 1) == v11 )
      {
        v21 = (LPVOID *)v11[1];
        if ( *v21 == v11 )
        {
          *v21 = v20;
          v20[1] = v21;
          HeapFree(hHeap, 0, v11);
          goto LABEL_37;
        }
      }
LABEL_35:
      __fastfail(3u);
    }
LABEL_28:
    v13 = v11;
  }
LABEL_29:
  v22 = (LPVOID **)HeapAlloc(hHeap, 0, 0x30u);
  v23 = v22;
  if ( v22 )
  {
    v22[1] = (LPVOID *)v22;
    *v22 = (LPVOID *)v22;
    *((_DWORD *)v22 + 4) = a1;
    if ( v13 )
      v12 = v13;
    *((_DWORD *)v22 + 5) = a2;
    *((_DWORD *)v22 + 6) = a3;
    *((_DWORD *)v22 + 7) = a4;
    *((_DWORD *)v22 + 8) = a5;
    *((_DWORD *)v22 + 9) = a6;
    *((_DWORD *)v22 + 10) = a7;
    v25 = (LPVOID **)v12[1];
    if ( *v25 == v12 )
    {
      *v23 = v12;
      v23[1] = (LPVOID *)v25;
      *v25 = (LPVOID *)v23;
      v12[1] = v23;
      goto LABEL_37;
    }
    goto LABEL_35;
  }
  v24 = 8;
  if ( qword_18002B8A8 )
  {
    LOWORD(v27) = 0;
    FormatRRASErrorString(&v27, L"Failed to create Join Entry : %x", 8);
    ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v27);
  }
LABEL_38:
  ReleaseWriteLock(&qword_18002B9D8);
  return v24;
}

```

## disassembly

```asm
0x180018dd4  push    rbx
0x180018dd6  push    rbp
0x180018dd7  push    rsi
0x180018dd8  push    rdi
0x180018dd9  push    r12
0x180018ddb  push    r13
0x180018ddd  push    r14
0x180018ddf  push    r15
0x180018de1  sub     rsp, 838h
0x180018de8  mov     rax, cs:__security_cookie
0x180018def  xor     rax, rsp
0x180018df2  mov     [rsp+878h+var_58], rax
0x180018dfa  mov     esi, r8d
0x180018dfd  mov     r13d, edx
0x180018e00  mov     ebp, ecx
0x180018e02  xor     eax, eax
0x180018e04  xor     edx, edx; Val
0x180018e06  mov     [rsp+878h+var_858], eax
0x180018e0a  mov     r8d, 7FCh; Size
0x180018e10  lea     rcx, [rsp+878h+var_854]; void *
0x180018e15  mov     r12d, r9d
0x180018e18  call    memset_0
0x180018e1d  lea     rcx, qword_18002B9D8
0x180018e24  call    AcquireWriteLock
0x180018e29  mov     rcx, cs:qword_18002B9C8
0x180018e30  lea     rbx, qword_18002B9C8
0x180018e37  mov     r14d, [rsp+878h+arg_28]
0x180018e3f  xor     edi, edi
0x180018e41  mov     r15d, [rsp+878h+arg_20]
0x180018e49  cmp     rcx, rbx
0x180018e4c  jz      loc_180018FA8
0x180018e52  movzx   r9d, sil
0x180018e56  mov     r11d, 0FF00h
0x180018e5c  mov     r10d, 0FF0000h
0x180018e62  mov     r8d, [rcx+18h]
0x180018e66  movzx   edx, r8b
0x180018e6a  sub     edx, r9d
0x180018e6d  jnz     short loc_180018EA0
0x180018e6f  mov     eax, esi
0x180018e71  mov     edx, r8d
0x180018e74  and     eax, r11d
0x180018e77  and     edx, r11d
0x180018e7a  sub     edx, eax
0x180018e7c  jnz     short loc_180018EA0
0x180018e7e  mov     edx, r8d
0x180018e81  mov     eax, esi
0x180018e83  and     edx, r10d
0x180018e86  and     eax, r10d
0x180018e89  sub     edx, eax
0x180018e8b  jnz     short loc_180018EA0
0x180018e8d  mov     edx, r8d
0x180018e90  mov     eax, esi
0x180018e92  shr     edx, 8
0x180018e95  shr     eax, 8
0x180018e98  and     edx, r10d
0x180018e9b  and     eax, r10d
0x180018e9e  sub     edx, eax
0x180018ea0  test    edx, edx
0x180018ea2  js      loc_180018F4D
0x180018ea8  jg      loc_180018FA5
0x180018eae  mov     r8d, [rcx+10h]
0x180018eb2  movzx   edx, r8b
0x180018eb6  movzx   eax, bpl
0x180018eba  sub     edx, eax
0x180018ebc  jnz     short loc_180018EEF
0x180018ebe  mov     eax, ebp
0x180018ec0  mov     edx, r8d
0x180018ec3  and     eax, r11d
0x180018ec6  and     edx, r11d
0x180018ec9  sub     edx, eax
0x180018ecb  jnz     short loc_180018EEF
0x180018ecd  mov     edx, r8d
0x180018ed0  mov     eax, ebp
0x180018ed2  and     edx, r10d
0x180018ed5  and     eax, r10d
0x180018ed8  sub     edx, eax
0x180018eda  jnz     short loc_180018EEF
0x180018edc  mov     edx, r8d
0x180018edf  mov     eax, ebp
0x180018ee1  shr     edx, 8
0x180018ee4  shr     eax, 8
0x180018ee7  and     edx, r10d
0x180018eea  and     eax, r10d
0x180018eed  sub     edx, eax
0x180018eef  test    edx, edx
0x180018ef1  js      short loc_180018F4D
0x180018ef3  jg      loc_180018FA5
0x180018ef9  cmp     [rcx+20h], r15d
0x180018efd  jb      short loc_180018F4D
0x180018eff  ja      loc_180018FA5
0x180018f05  mov     r8d, [rcx+24h]
0x180018f09  movzx   edx, r8b
0x180018f0d  movzx   eax, r14b
0x180018f11  sub     edx, eax
0x180018f13  jnz     short loc_180018F49
0x180018f15  mov     eax, r14d
0x180018f18  mov     edx, r8d
0x180018f1b  and     eax, r11d
0x180018f1e  and     edx, r11d
0x180018f21  sub     edx, eax
0x180018f23  jnz     short loc_180018F49
0x180018f25  mov     edx, r8d
0x180018f28  mov     eax, r14d
0x180018f2b  and     edx, r10d
0x180018f2e  and     eax, r10d
0x180018f31  sub     edx, eax
0x180018f33  jnz     short loc_180018F49
0x180018f35  mov     edx, r8d
0x180018f38  mov     eax, r14d
0x180018f3b  shr     edx, 8
0x180018f3e  shr     eax, 8
0x180018f41  and     edx, r10d
0x180018f44  and     eax, r10d
0x180018f47  sub     edx, eax
0x180018f49  test    edx, edx
0x180018f4b  jns     short loc_180018F5B
0x180018f4d  mov     rcx, [rcx]
0x180018f50  cmp     rcx, rbx
0x180018f53  jnz     loc_180018E62
0x180018f59  jmp     short loc_180018FA8
0x180018f5b  jg      short loc_180018FA5
0x180018f5d  mov     eax, [rsp+878h+arg_30]
0x180018f64  cmp     [rcx+28h], eax
0x180018f67  jz      loc_180019059
0x180018f6d  mov     rax, [rcx]
0x180018f70  cmp     [rax+8], rcx
0x180018f74  jnz     loc_180019044
0x180018f7a  mov     rdx, [rcx+8]
0x180018f7e  cmp     [rdx], rcx
0x180018f81  jnz     loc_180019044
0x180018f87  mov     [rdx], rax
0x180018f8a  mov     r8, rcx; lpMem
0x180018f8d  mov     [rax+8], rdx
0x180018f91  xor     edx, edx; dwFlags
0x180018f93  mov     rcx, cs:hHeap; hHeap
0x180018f9a  call    cs:__imp_HeapFree
0x180018fa0  jmp     loc_180019059
0x180018fa5  mov     rdi, rcx
0x180018fa8  mov     rcx, cs:hHeap; hHeap
0x180018faf  xor     edx, edx; dwFlags
0x180018fb1  lea     r8d, [rdx+30h]; dwBytes
0x180018fb5  call    cs:__imp_HeapAlloc
0x180018fbb  mov     rcx, rax
0x180018fbe  test    rax, rax
0x180018fc1  jnz     short loc_18001900D
0x180018fc3  cmp     cs:qword_18002B8A8, rax
0x180018fca  lea     ebx, [rax+8]
0x180018fcd  jz      loc_18001905B
0x180018fd3  mov     r8d, ebx
0x180018fd6  mov     word ptr [rsp+878h+var_858], ax
0x180018fdb  lea     rdx, aFailedToCreate_0; "Failed to create Join Entry : %x"
0x180018fe2  lea     rcx, [rsp+878h+var_858]
0x180018fe7  call    FormatRRASErrorString
0x180018fec  mov     rdx, cs:qword_18002B8A8
0x180018ff3  lea     r8, [rsp+878h+var_858]
0x180018ff8  mov     rcx, cs:gMgmEtwContext
0x180018fff  mov     rax, cs:gMgmTemplateFunc
0x180019006  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001900b  jmp     short loc_18001905B
0x18001900d  mov     [rax+8], rcx
0x180019011  test    rdi, rdi
0x180019014  mov     [rax], rcx
0x180019017  mov     [rax+10h], ebp
0x18001901a  cmovnz  rbx, rdi
0x18001901e  mov     [rax+14h], r13d
0x180019022  mov     [rax+18h], esi
0x180019025  mov     [rax+1Ch], r12d
0x180019029  mov     [rax+20h], r15d
0x18001902d  mov     [rax+24h], r14d
0x180019031  mov     eax, [rsp+878h+arg_30]
0x180019038  mov     [rcx+28h], eax
0x18001903b  mov     rax, [rbx+8]
0x18001903f  cmp     [rax], rbx
0x180019042  jz      short loc_18001904B
0x180019044  mov     ecx, 3
0x180019049  int     29h; Win8: RtlFailFast(ecx)
0x18001904b  mov     [rcx], rbx
0x18001904e  mov     [rcx+8], rax
0x180019052  mov     [rax], rcx
0x180019055  mov     [rbx+8], rcx
0x180019059  xor     ebx, ebx
0x18001905b  lea     rcx, qword_18002B9D8
0x180019062  call    ReleaseWriteLock
0x180019067  mov     eax, ebx
0x180019069  mov     rcx, [rsp+878h+var_58]
0x180019071  xor     rcx, rsp; StackCookie
0x180019074  call    __security_check_cookie
0x180019079  add     rsp, 838h
0x180019080  pop     r15
0x180019082  pop     r14
0x180019084  pop     r13
0x180019086  pop     r12
0x180019088  pop     rdi
0x180019089  pop     rsi
0x18001908a  pop     rbp
0x18001908b  pop     rbx
0x18001908c  retn
```
