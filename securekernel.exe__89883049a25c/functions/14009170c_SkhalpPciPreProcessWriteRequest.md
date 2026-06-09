# SkhalpPciPreProcessWriteRequest

- ea: `0x14009170c`
- end: `0x14009184d`
- name: `SkhalpPciPreProcessWriteRequest`
- size: `321`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x14008ac3c`

## callees

- `0x1400337d4`
- `0x14008938c`
- `0x14008b420`
- `0x14008c018`
- `0x14008c054`
- `0x14008c11c`
- `0x14008c408`
- `0x14009170c`

## pseudocode

```c
__int64 __fastcall SkhalpPciPreProcessWriteRequest(
        char a1,
        unsigned int a2,
        char a3,
        char a4,
        char a5,
        unsigned int a6,
        unsigned int a7,
        __int64 a8)
{
  unsigned int v11; // ebp
  __int64 v12; // r9
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 FunctionInTree; // rax
  __int64 v16; // rdx
  __int64 v17; // rsi
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 v26; // rdx
  int v27; // r15d
  __int64 *v28; // rbx
  __int64 v29; // r12
  unsigned int v30; // edi
  unsigned int v31; // ecx
  char v32; // [rsp+60h] [rbp+8h] BYREF

  v32 = 0;
  if ( !a1 )
  {
    v11 = a7;
    if ( a7 )
    {
      SkhalpPciAcquireSegmentFunctionTreeLock(a2, &v32);
      LOBYTE(v12) = a5;
      LOBYTE(v13) = a4;
      LOBYTE(v14) = a3;
      FunctionInTree = SkhalpPciFindFunctionInTree(a2, v14, v13, v12);
      LOBYTE(v16) = v32;
      v17 = FunctionInTree;
      SkhalpPciReleaseSegmentFunctionTreeLock(a2, v16);
      if ( !v17 )
      {
        if ( (unsigned __int8)SkhalPciEnabled(v19, v18, v20, v21) )
        {
          LOBYTE(v24) = a5;
          LOBYTE(v23) = a4;
          LOBYTE(v22) = a3;
          return (unsigned __int8)SkhalpPciIsRidOnSecurePath(a2, v22, v23, v24) != 0 ? 0xC000000E : 0;
        }
        return 0;
      }
      SkhalpPciAcquireRuleProcessLock(v17, &v32);
      v27 = 0;
      v28 = *(__int64 **)(v17 + 384);
      if ( v28 == (__int64 *)(v17 + 384) )
      {
LABEL_15:
        LOBYTE(v26) = v32;
        SkhalpPciReleaseRuleProcessLock(v17, v26);
        return (unsigned int)v27;
      }
      v29 = a8;
      v30 = a6;
      while ( 1 )
      {
        if ( (v28[3] & 2) != 0 )
        {
          v31 = *((_DWORD *)v28 + 7);
          if ( v31 < v30 )
            goto LABEL_12;
          if ( v30 + v11 - 1 >= v31 )
            goto LABEL_13;
          if ( v31 <= v30 )
          {
LABEL_12:
            if ( *((_DWORD *)v28 + 8) >= v30 )
            {
LABEL_13:
              v27 = ((__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD, __int64))v28[2])(v17, 2, v30, v11, v29);
              if ( v27 < 0 )
                goto LABEL_15;
            }
          }
        }
        v28 = (__int64 *)*v28;
        if ( v28 == (__int64 *)(v17 + 384) )
          goto LABEL_15;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14009170c  mov     rax, rsp
0x14009170f  mov     [rax+10h], rbx
0x140091713  mov     [rax+18h], rbp
0x140091717  push    rsi
0x140091718  push    rdi
0x140091719  push    r12
0x14009171b  push    r14
0x14009171d  push    r15
0x14009171f  sub     rsp, 30h
0x140091723  mov     byte ptr [rax+8], 0
0x140091727  mov     dil, r9b
0x14009172a  mov     r14b, r8b
0x14009172d  mov     ebx, edx
0x14009172f  test    cl, cl
0x140091731  jnz     loc_140091833
0x140091737  mov     ebp, [rsp+58h+arg_30]
0x14009173e  test    ebp, ebp
0x140091740  jz      loc_140091833
0x140091746  lea     rdx, [rax+8]
0x14009174a  mov     ecx, ebx
0x14009174c  call    SkhalpPciAcquireSegmentFunctionTreeLock
0x140091751  mov     r9b, [rsp+58h+arg_20]
0x140091759  mov     r8b, dil
0x14009175c  mov     dl, r14b
0x14009175f  mov     ecx, ebx
0x140091761  call    SkhalpPciFindFunctionInTree
0x140091766  mov     dl, [rsp+58h+arg_0]
0x14009176a  mov     ecx, ebx
0x14009176c  mov     rsi, rax
0x14009176f  call    SkhalpPciReleaseSegmentFunctionTreeLock
0x140091774  test    rsi, rsi
0x140091777  jnz     short loc_1400917A9
0x140091779  call    SkhalPciEnabled
0x14009177e  test    al, al
0x140091780  jz      loc_140091833
0x140091786  mov     r9b, [rsp+58h+arg_20]
0x14009178e  mov     r8b, dil
0x140091791  mov     dl, r14b
0x140091794  mov     ecx, ebx
0x140091796  call    SkhalpPciIsRidOnSecurePath
0x14009179b  neg     al
0x14009179d  sbb     eax, eax
0x14009179f  and     eax, 0C000000Eh
0x1400917a4  jmp     loc_140091835
0x1400917a9  lea     rdx, [rsp+58h+arg_0]
0x1400917ae  mov     rcx, rsi
0x1400917b1  call    SkhalpPciAcquireRuleProcessLock
0x1400917b6  lea     r14, [rsi+180h]
0x1400917bd  xor     r15d, r15d
0x1400917c0  mov     rbx, [r14]
0x1400917c3  cmp     rbx, r14
0x1400917c6  jz      short loc_140091822
0x1400917c8  mov     r12, [rsp+58h+arg_38]
0x1400917d0  mov     edi, [rsp+58h+arg_28]
0x1400917d7  mov     eax, [rbx+18h]
0x1400917da  test    al, 2
0x1400917dc  jz      short loc_14009181A
0x1400917de  mov     ecx, [rbx+1Ch]
0x1400917e1  cmp     ecx, edi
0x1400917e3  jb      short loc_1400917F2
0x1400917e5  lea     eax, [rbp-1]
0x1400917e8  add     eax, edi
0x1400917ea  cmp     eax, ecx
0x1400917ec  jnb     short loc_1400917F7
0x1400917ee  cmp     ecx, edi
0x1400917f0  ja      short loc_14009181A
0x1400917f2  cmp     [rbx+20h], edi
0x1400917f5  jb      short loc_14009181A
0x1400917f7  mov     rax, [rbx+10h]
0x1400917fb  mov     r9d, ebp
0x1400917fe  mov     r8d, edi
0x140091801  mov     [rsp+58h+var_38], r12
0x140091806  mov     edx, 2
0x14009180b  mov     rcx, rsi
0x14009180e  call    rax
0x140091810  nop     dword ptr [rax]
0x140091813  mov     r15d, eax
0x140091816  test    eax, eax
0x140091818  js      short loc_140091822
0x14009181a  mov     rbx, [rbx]
0x14009181d  cmp     rbx, r14
0x140091820  jnz     short loc_1400917D7
0x140091822  mov     dl, [rsp+58h+arg_0]
0x140091826  mov     rcx, rsi
0x140091829  call    SkhalpPciReleaseRuleProcessLock
0x14009182e  mov     eax, r15d
0x140091831  jmp     short loc_140091835
0x140091833  xor     eax, eax
0x140091835  mov     rbx, [rsp+58h+arg_8]
0x14009183a  mov     rbp, [rsp+58h+arg_10]
0x14009183f  add     rsp, 30h
0x140091843  pop     r15
0x140091845  pop     r14
0x140091847  pop     r12
0x140091849  pop     rdi
0x14009184a  pop     rsi
0x14009184b  retn
```
