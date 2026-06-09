# CTDCArr::find(__int64,__int64,tagVARIANT,OSPFIND,OSPCOMP,__int64 *)

- ea: `0x18000d670`
- end: `0x18000d7cc`
- name: `?find@CTDCArr@@UEAAJ_J0UtagVARIANT@@W4OSPFIND@@W4OSPCOMP@@PEA_J@Z`
- size: `348`
- prototype: `int(CTDCArr *__hidden this, __int64, __int64, struct tagVARIANT *__struct_ptr, enum OSPFIND, enum OSPCOMP, __int64 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000d1cc`
- `0x18000d670`

## pseudocode

```c
__int64 __fastcall CTDCArr::find(
        CTDCArr *this,
        __int64 a2,
        int a3,
        struct tagVARIANT *a4,
        enum OSPFIND a5,
        enum OSPCOMP a6,
        __int64 *a7)
{
  struct tagVARIANT *v7; // r10
  int v8; // ebx
  VARTYPE vt; // r13
  __int64 v11; // rsi
  signed int v13; // eax
  unsigned int v14; // ecx

  v7 = a4;
  v8 = a2;
  *a7 = -1;
  if ( a2 < 1 || (int)a2 < 0 || (int)a2 > *((_DWORD *)this + 27) || a3 < 1 || a3 > *((_DWORD *)this + 28) )
    return 2147942487LL;
  vt = a4->vt;
  v11 = a3 - 1LL;
  if ( *(_WORD *)(*((_QWORD *)this + 22) + 8 * v11) != a4->vt )
    return 2147614725LL;
  if ( (a5 & 1) != 0 )
    goto LABEL_26;
  while ( v8 <= *((_DWORD *)this + 27) )
  {
    while ( 1 )
    {
      LOBYTE(v13) = CTDCArr::VariantComp(
                      (CTDCArr *)(3 * v11),
                      (struct tagVARIANT *)(**(_QWORD **)(*((_QWORD *)this + 19) + 8LL * v8) + 24 * v11),
                      v7,
                      vt,
                      (a5 & 2) != 0);
      if ( a6 == OSPCOMP_EQ )
      {
        if ( !v13 )
          goto LABEL_22;
      }
      else
      {
        switch ( a6 )
        {
          case OSPCOMP_LT:
            v14 = (unsigned int)v13 >> 31;
            break;
          case OSPCOMP_LE:
            LOBYTE(v14) = v13 <= 0;
            break;
          case OSPCOMP_GE:
            LOBYTE(v14) = v13 >= 0;
            break;
          case OSPCOMP_GT:
            LOBYTE(v14) = v13 > 0;
            break;
          case OSPCOMP_NE:
            LOBYTE(v14) = v13 != 0;
            break;
          default:
            return 2147942487LL;
        }
        if ( (_BYTE)v14 )
        {
LABEL_22:
          *a7 = v8;
          return 0;
        }
      }
      v7 = a4;
      if ( (a5 & 1) == 0 )
        break;
      --v8;
LABEL_26:
      if ( v8 <= 0 )
        return 2147500037LL;
    }
    ++v8;
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x18000d670  mov     [rsp+arg_18], r9
0x18000d675  push    rbx
0x18000d676  push    rbp
0x18000d677  push    rsi
0x18000d678  push    rdi
0x18000d679  push    r12
0x18000d67b  push    r13
0x18000d67d  push    r14
0x18000d67f  push    r15
0x18000d681  sub     rsp, 38h
0x18000d685  mov     r15, [rsp+78h+arg_30]
0x18000d68d  mov     r10, r9
0x18000d690  mov     rbx, rdx
0x18000d693  mov     rdi, rcx
0x18000d696  mov     qword ptr [r15], 0FFFFFFFFFFFFFFFFh
0x18000d69d  cmp     rdx, 1
0x18000d6a1  jl      loc_18000D7B6
0x18000d6a7  test    edx, edx
0x18000d6a9  js      loc_18000D7B6
0x18000d6af  cmp     edx, [rcx+6Ch]
0x18000d6b2  jg      loc_18000D7B6
0x18000d6b8  cmp     r8d, 1
0x18000d6bc  jl      loc_18000D7B6
0x18000d6c2  cmp     r8d, [rcx+70h]
0x18000d6c6  jg      loc_18000D7B6
0x18000d6cc  mov     rax, [rcx+0B0h]
0x18000d6d3  movzx   r13d, word ptr [r9]
0x18000d6d7  movsxd  rsi, r8d
0x18000d6da  dec     rsi
0x18000d6dd  cmp     [rax+rsi*8], r13w
0x18000d6e2  jz      short loc_18000D6EE
0x18000d6e4  mov     eax, 80020005h
0x18000d6e9  jmp     loc_18000D7BB
0x18000d6ee  mov     ebp, [rsp+78h+arg_20]
0x18000d6f5  mov     r14b, bpl
0x18000d6f8  shr     ebp, 1
0x18000d6fa  and     bpl, 1
0x18000d6fe  and     r14b, 1
0x18000d702  jnz     loc_18000D7A0
0x18000d708  cmp     ebx, [rdi+6Ch]
0x18000d70b  jg      loc_18000D7A8
0x18000d711  mov     rax, [rdi+98h]
0x18000d718  lea     rcx, [rsi+rsi*2]; this
0x18000d71c  movsxd  r12, ebx
0x18000d71f  movzx   r9d, r13w; unsigned __int16
0x18000d723  mov     r8, r10; struct tagVARIANT *
0x18000d726  mov     [rsp+78h+var_58], bpl; char
0x18000d72b  mov     rax, [rax+r12*8]
0x18000d72f  mov     rax, [rax]
0x18000d732  lea     rdx, [rax+rcx*8]; struct tagVARIANT *
0x18000d736  call    ?VariantComp@CTDCArr@@AEAAHPEAUtagVARIANT@@0GE@Z; CTDCArr::VariantComp(tagVARIANT *,tagVARIANT *,ushort,uchar)
0x18000d73b  mov     edx, [rsp+78h+arg_28]
0x18000d742  mov     ecx, eax
0x18000d744  sub     edx, 1
0x18000d747  jz      short loc_18000D78D
0x18000d749  sub     edx, 1
0x18000d74c  jz      short loc_18000D77F
0x18000d74e  sub     edx, 1
0x18000d751  jz      short loc_18000D778
0x18000d753  sub     edx, 1
0x18000d756  jz      short loc_18000D770
0x18000d758  sub     edx, 1
0x18000d75b  jz      short loc_18000D769
0x18000d75d  cmp     edx, 1
0x18000d760  jnz     short loc_18000D7B6
0x18000d762  test    eax, eax
0x18000d764  setnz   cl
0x18000d767  jmp     short loc_18000D782
0x18000d769  test    ecx, ecx
0x18000d76b  setnle  cl
0x18000d76e  jmp     short loc_18000D782
0x18000d770  shr     ecx, 1Fh
0x18000d773  xor     cl, 1
0x18000d776  jmp     short loc_18000D782
0x18000d778  test    ecx, ecx
0x18000d77a  setle   cl
0x18000d77d  jmp     short loc_18000D782
0x18000d77f  shr     ecx, 1Fh
0x18000d782  test    cl, cl
0x18000d784  jz      short loc_18000D791
0x18000d786  mov     [r15], r12
0x18000d789  xor     eax, eax
0x18000d78b  jmp     short loc_18000D7BB
0x18000d78d  test    ecx, ecx
0x18000d78f  jz      short loc_18000D786
0x18000d791  mov     r10, [rsp+78h+arg_18]
0x18000d799  test    r14b, r14b
0x18000d79c  jz      short loc_18000D7AF
0x18000d79e  dec     ebx
0x18000d7a0  test    ebx, ebx
0x18000d7a2  jg      loc_18000D711
0x18000d7a8  mov     eax, 80004005h
0x18000d7ad  jmp     short loc_18000D7BB
0x18000d7af  inc     ebx
0x18000d7b1  jmp     loc_18000D708
0x18000d7b6  mov     eax, 80070057h
0x18000d7bb  add     rsp, 38h
0x18000d7bf  pop     r15
0x18000d7c1  pop     r14
0x18000d7c3  pop     r13
0x18000d7c5  pop     r12
0x18000d7c7  pop     rdi
0x18000d7c8  pop     rsi
0x18000d7c9  pop     rbp
0x18000d7ca  pop     rbx
0x18000d7cb  retn
```
