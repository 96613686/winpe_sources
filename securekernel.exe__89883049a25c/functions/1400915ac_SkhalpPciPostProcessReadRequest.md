# SkhalpPciPostProcessReadRequest

- ea: `0x1400915ac`
- end: `0x140091705`
- name: `SkhalpPciPostProcessReadRequest`
- size: `345`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14008ac3c`

## callees

- `0x140033544`
- `0x1400337d4`
- `0x14008ac3c`
- `0x14008b420`
- `0x14008b580`
- `0x14008c054`
- `0x1400915ac`

## pseudocode

```c
__int64 __fastcall SkhalpPciPostProcessReadRequest(
        char a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        char a5,
        char a6,
        __int16 a7,
        unsigned int a8,
        __int64 a9)
{
  unsigned __int8 v9; // r14
  char v11; // r15
  __int64 v12; // r8
  char v13; // r9
  __int64 v14; // rcx
  char v15; // dl
  char v16; // si
  char v17; // bp
  char v18; // r10
  __int64 v19; // r9
  __int64 v20; // r8
  __int64 v21; // rdx
  __int64 FunctionInTree; // rax
  __int64 v23; // rdx
  __int64 v24; // rbx
  __int64 result; // rax
  ULONG_PTR v26; // [rsp+30h] [rbp-58h]
  size_t Size; // [rsp+38h] [rbp-50h]
  char v28; // [rsp+90h] [rbp+8h] BYREF

  v9 = a4;
  v28 = 0;
  v11 = a2;
  a7 = 0;
  if ( a1 )
    return 0;
  v12 = a8;
  if ( !a8 )
    return 0;
  v13 = 1;
  v14 = 0;
  v15 = 1;
  while ( 1 )
  {
    v16 = a6;
    v17 = a5;
    if ( (unsigned int)v14 >= a8 )
      break;
    v18 = *(_BYTE *)(v14 + a9);
    if ( v18 )
    {
      if ( v18 != -1 )
        goto LABEL_13;
      v15 = 0;
    }
    else
    {
      v13 = 0;
    }
    v14 = (unsigned int)(v14 + 1);
  }
  if ( v15 || v13 )
  {
    LOBYTE(a4) = a6;
    LOBYTE(v12) = a5;
    LOBYTE(a2) = v9;
    SkhalpPciRevalidateDeviceTree(a3, a2, v12, a4);
  }
LABEL_13:
  SkhalpPciAcquireSegmentFunctionTreeLock(a3, &v28);
  LOBYTE(v19) = v16;
  LOBYTE(v20) = v17;
  LOBYTE(v21) = v9;
  FunctionInTree = SkhalpPciFindFunctionInTree(a3, v21, v20, v19);
  LOBYTE(v23) = v28;
  v24 = FunctionInTree;
  SkhalpPciReleaseSegmentFunctionTreeLock(a3, v23);
  if ( v24 )
    return 0;
  a7 = -1;
  LODWORD(Size) = 2;
  LODWORD(v26) = 0;
  result = SkhalpPciAccessDeviceInternal(1, 0, a3, v9, v17, v16, v26, Size, &a7);
  if ( (int)result < 0 )
    return result;
  if ( (unsigned __int16)(a7 - 2) > 0xFFFCu || v11 )
    return 0;
  else
    return SkhalpPciInsertFunctionInTree(a3, 0);
}

```

## disassembly

```asm
0x1400915ac  mov     rax, rsp
0x1400915af  push    rbx
0x1400915b0  push    rbp
0x1400915b1  push    rsi
0x1400915b2  push    rdi
0x1400915b3  push    r14
0x1400915b5  push    r15
0x1400915b7  sub     rsp, 58h
0x1400915bb  mov     r11, [rsp+88h+arg_40]
0x1400915c3  mov     r14b, r9b
0x1400915c6  mov     byte ptr [rax+8], 0
0x1400915ca  mov     edi, r8d
0x1400915cd  xor     eax, eax
0x1400915cf  mov     r15b, dl
0x1400915d2  mov     [rsp+88h+arg_30], ax
0x1400915da  test    cl, cl
0x1400915dc  jnz     loc_1400916F5
0x1400915e2  mov     r8d, [rsp+88h+arg_38]
0x1400915ea  test    r8d, r8d
0x1400915ed  jz      loc_1400916F5
0x1400915f3  mov     r9b, 1
0x1400915f6  xor     ecx, ecx
0x1400915f8  mov     dl, r9b
0x1400915fb  mov     sil, [rsp+88h+arg_28]
0x140091603  mov     bpl, [rsp+88h+arg_20]
0x14009160b  cmp     ecx, r8d
0x14009160e  jnb     short loc_14009162A
0x140091610  mov     r10b, [rcx+r11]
0x140091614  test    r10b, r10b
0x140091617  jnz     short loc_14009161E
0x140091619  xor     r9b, r9b
0x14009161c  jmp     short loc_140091626
0x14009161e  cmp     r10b, 0FFh
0x140091622  jnz     short loc_140091643
0x140091624  xor     dl, dl
0x140091626  inc     ecx
0x140091628  jmp     short loc_1400915FB
0x14009162a  test    dl, dl
0x14009162c  jnz     short loc_140091633
0x14009162e  test    r9b, r9b
0x140091631  jz      short loc_140091643
0x140091633  mov     r9b, sil
0x140091636  mov     r8b, bpl
0x140091639  mov     dl, r14b
0x14009163c  mov     ecx, edi
0x14009163e  call    SkhalpPciRevalidateDeviceTree
0x140091643  lea     rdx, [rsp+88h+arg_0]
0x14009164b  mov     ecx, edi
0x14009164d  call    SkhalpPciAcquireSegmentFunctionTreeLock
0x140091652  mov     r9b, sil
0x140091655  mov     r8b, bpl
0x140091658  mov     dl, r14b
0x14009165b  mov     ecx, edi
0x14009165d  call    SkhalpPciFindFunctionInTree
0x140091662  mov     dl, [rsp+88h+arg_0]
0x140091669  mov     ecx, edi
0x14009166b  mov     rbx, rax
0x14009166e  call    SkhalpPciReleaseSegmentFunctionTreeLock
0x140091673  test    rbx, rbx
0x140091676  jnz     short loc_1400916F5
0x140091678  mov     eax, 0FFFFh
0x14009167d  mov     ebx, 2
0x140091682  mov     [rsp+88h+arg_30], ax
0x14009168a  mov     r9b, r14b; int
0x14009168d  lea     rax, [rsp+88h+arg_30]
0x140091695  mov     r8d, edi; int
0x140091698  mov     [rsp+88h+var_48], rax; void *
0x14009169d  xor     edx, edx; int
0x14009169f  mov     dword ptr [rsp+88h+Size], ebx; Size
0x1400916a3  mov     cl, 1; int
0x1400916a5  mov     dword ptr [rsp+88h+var_58], 0; ULONG_PTR
0x1400916ad  mov     [rsp+88h+var_60], sil; char
0x1400916b2  mov     [rsp+88h+var_68], bpl; char
0x1400916b7  call    SkhalpPciAccessDeviceInternal
0x1400916bc  test    eax, eax
0x1400916be  js      short loc_1400916F7
0x1400916c0  movzx   eax, [rsp+88h+arg_30]
0x1400916c8  mov     ecx, 0FFFCh
0x1400916cd  sub     ax, bx
0x1400916d0  cmp     ax, cx
0x1400916d3  ja      short loc_1400916F5
0x1400916d5  test    r15b, r15b
0x1400916d8  jnz     short loc_1400916F5
0x1400916da  mov     r9b, sil
0x1400916dd  mov     qword ptr [rsp+88h+var_68], 0; __int64
0x1400916e6  mov     r8b, bpl
0x1400916e9  mov     dl, r14b
0x1400916ec  mov     ecx, edi; int
0x1400916ee  call    SkhalpPciInsertFunctionInTree
0x1400916f3  jmp     short loc_1400916F7
0x1400916f5  xor     eax, eax
0x1400916f7  add     rsp, 58h
0x1400916fb  pop     r15
0x1400916fd  pop     r14
0x1400916ff  pop     rdi
0x140091700  pop     rsi
0x140091701  pop     rbp
0x140091702  pop     rbx
0x140091703  retn
```
