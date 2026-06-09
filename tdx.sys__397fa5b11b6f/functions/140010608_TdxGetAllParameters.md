# TdxGetAllParameters

- ea: `0x140010608`
- end: `0x1400106b9`
- name: `TdxGetAllParameters`
- size: `177`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x14000cfc0`
- `0x14000e630`
- `0x14001606c`

## callees

- `0x140010608`
- `0x140018590`
- `0x140018900`

## pseudocode

```c
__int64 __fastcall TdxGetAllParameters(
        unsigned int a1,
        unsigned int a2,
        __int64 a3,
        int a4,
        __int64 a5,
        int a6,
        __int64 a7,
        unsigned int a8,
        __int64 a9,
        int a10,
        __int64 a11,
        int a12)
{
  __int64 v16; // rcx
  __int64 result; // rax
  _QWORD v18[18]; // [rsp+20h] [rbp-69h] BYREF

  memset(v18, 0, 0x68u);
  v18[5] = a5;
  LODWORD(v18[6]) = a6;
  v18[7] = a7;
  v18[9] = a9;
  LODWORD(v18[10]) = a10;
  v18[11] = a11;
  LODWORD(v18[12]) = a12;
  v18[2] = a3;
  LODWORD(v18[3]) = a4;
  v16 = *(_QWORD *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters + 8LL);
  LODWORD(v18[8]) = a8;
  v18[4] = __PAIR64__(a2, a1);
  result = (*(__int64 (__fastcall **)(_QWORD *))(v16 + 32))(v18);
  if ( (int)result >= 0 && LODWORD(v18[8]) < a8 )
    return 3221225485LL;
  return result;
}

```

## disassembly

```asm
0x140010608  push    rbp
0x14001060a  push    rbx
0x14001060b  push    rsi
0x14001060c  push    rdi
0x14001060d  push    r14
0x14001060f  lea     rbp, [rsp-7]
0x140010614  sub     rsp, 90h
0x14001061b  mov     r14d, edx
0x14001061e  mov     rbx, r8
0x140010621  xor     edx, edx; Val
0x140010623  mov     esi, ecx
0x140010625  lea     rcx, [rbp+27h+var_90]; void *
0x140010629  mov     edi, r9d
0x14001062c  lea     r8d, [rdx+68h]; Size
0x140010630  call    memset
0x140010635  mov     rax, [rbp+27h+arg_20]
0x140010639  mov     [rbp+27h+var_68], rax
0x14001063d  mov     eax, [rbp+27h+arg_28]
0x140010640  mov     [rbp+27h+var_60], eax
0x140010643  mov     rax, [rbp+27h+arg_30]
0x140010647  mov     [rbp+27h+var_58], rax
0x14001064b  mov     rax, [rbp+27h+arg_40]
0x14001064f  mov     [rbp+27h+var_48], rax
0x140010653  mov     eax, [rbp+27h+arg_48]
0x140010656  mov     [rbp+27h+var_40], eax
0x140010659  mov     rax, [rbp+27h+arg_50]
0x140010660  mov     [rbp+27h+var_38], rax
0x140010664  mov     eax, [rbp+27h+arg_58]
0x14001066a  mov     [rbp+27h+var_30], eax
0x14001066d  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+28h
0x140010674  mov     [rbp+27h+var_80], rbx
0x140010678  mov     ebx, [rbp+27h+arg_38]
0x14001067b  mov     [rbp+27h+var_78], edi
0x14001067e  mov     rcx, [rax+8]
0x140010682  mov     [rbp+27h+var_50], ebx
0x140010685  mov     [rbp+27h+var_70], esi
0x140010688  mov     [rbp+27h+var_6C], r14d
0x14001068c  mov     rax, [rcx+20h]
0x140010690  lea     rcx, [rbp+27h+var_90]
0x140010694  call    _guard_dispatch_icall
0x140010699  test    eax, eax
0x14001069b  jns     short loc_1400106AC
0x14001069d  add     rsp, 90h
0x1400106a4  pop     r14
0x1400106a6  pop     rdi
0x1400106a7  pop     rsi
0x1400106a8  pop     rbx
0x1400106a9  pop     rbp
0x1400106aa  retn
0x1400106ac  cmp     [rbp+27h+var_50], ebx
0x1400106af  mov     ecx, 0C000000Dh
0x1400106b4  cmovb   eax, ecx
0x1400106b7  jmp     short loc_14001069D
```
