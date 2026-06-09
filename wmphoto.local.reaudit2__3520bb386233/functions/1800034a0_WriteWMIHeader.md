# WriteWMIHeader

- ea: `0x1800034a0`
- end: `0x18000382a`
- name: `WriteWMIHeader`
- size: `906`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800012bc`
- `0x180007400`

## callees

- `0x180002214`
- `0x1800034a0`
- `0x180003830`
- `0x18000c410`

## pseudocode

```c
__int64 __fastcall WriteWMIHeader(__int64 a1)
{
  __int64 v1; // rsi
  unsigned int v3; // r14d
  _QWORD *v4; // rdx
  _QWORD *v5; // r8
  _QWORD *v6; // rcx
  _QWORD *v7; // rax
  unsigned int v8; // r15d
  __int64 v9; // rbx
  __int64 v10; // r8
  __int64 v11; // r8
  unsigned int v12; // ebx
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r8
  __int64 v17; // r8
  __int64 v18; // r8
  __int64 v19; // rdx
  __int64 v20; // r8
  unsigned int v21; // r11d
  unsigned int v22; // r11d
  int v23; // r8d
  int v24; // r14d
  int v25; // edx
  unsigned int *v26; // rbx
  unsigned int v27; // r11d
  __int64 v28; // r8
  __int64 v29; // rax
  __int64 v30; // r8
  unsigned int v31; // r11d
  __int64 v32; // rax
  __int64 v33; // r8
  unsigned int v34; // r11d
  __int64 v35; // r8
  __int64 v36; // r8
  __int64 v37; // r8

  v1 = *(_QWORD *)(a1 + 34368);
  if ( ((*(_QWORD *)(a1 + 8) + 15LL) & 0xFFFFFFFFFFFFFFF0uLL) > 0xFF0
    || (v3 = 1, ((*(_QWORD *)(a1 + 16) + 15LL) & 0xFFFFFFFFFFFFFFF0uLL) > 0xFF0) )
  {
    v3 = 0;
  }
  v4 = (_QWORD *)(a1 + 34264);
  v5 = (_QWORD *)(a1 + 34272);
  v6 = (_QWORD *)(a1 + 34256);
  v7 = (_QWORD *)(a1 + 34248);
  if ( !*(_DWORD *)(a1 + 34280) )
  {
    *v4 = 0;
    *v5 = 0;
    *v6 = 0;
    *v7 = 0;
  }
  if ( *v7 || *v6 || *v4 || (v8 = 0, *v5) )
    v8 = 1;
  v9 = 0;
  do
    putBit16z(*(_QWORD *)(a1 + 34368), (unsigned __int8)gGDISignature[v9++], 8);
  while ( v9 != v10 );
  putBit16z(v1, 1, 4);
  v12 = v11 - 1;
  if ( *(_DWORD *)(a1 + 160) )
  {
    putBit16z(v1, *(_DWORD *)(a1 + 156) & 1, 1);
    v13 = 1;
    v11 = v12;
  }
  else
  {
    v13 = 0;
  }
  putBit16z(v1, v13, v11);
  if ( *(_DWORD *)(a1 + 216) || (v14 = 0, *(_DWORD *)(a1 + 16604)) )
    v14 = 1;
  putBit16z(v1, v14, 1);
  putBit16z(v1, *(_DWORD *)(a1 + 168) & 1, v15);
  putBit16z(v1, *(_DWORD *)(a1 + 124) & 7, v12);
  putBit16z(v1, *(_DWORD *)(a1 + 34228) & 1, 1);
  putBit16z(v1, v12 & *(_DWORD *)(a1 + 152), 2);
  putBit16z(v1, v3, 1);
  putBit16z(v1, 1, v16);
  putBit16z(v1, v8, v17);
  putBit16z(v1, *(_DWORD *)(a1 + 34232) & 1, v18);
  putBit16z(v1, 0, 2);
  if ( !*(_DWORD *)(a1 + 34220) || (v19 = 1, !*(_DWORD *)(a1 + 56)) )
    v19 = 0;
  putBit16z(v1, v19, 1);
  putBit16z(v1, *(_DWORD *)(a1 + 34220) & 1, v20);
  putBit16z(v1, v21 & *(_DWORD *)(a1 + 24), 4);
  v23 = *(_DWORD *)(a1 + 28);
  if ( v23 || !*(_DWORD *)(a1 + 32996) )
    v22 &= v23;
  putBit16z(v1, v22, 4);
  v24 = v3 ^ 1;
  putBit32(v1, (unsigned int)(*(_DWORD *)(a1 + 8) - 1), (unsigned int)(16 * (v24 + 1)));
  putBit32(v1, (unsigned int)(*(_DWORD *)(a1 + 16) - 1), (unsigned int)(16 * (v24 + 1)));
  v25 = *(_DWORD *)(a1 + 216);
  v26 = (unsigned int *)(a1 + 16604);
  if ( v25 || *v26 )
  {
    putBit16z(v1, v25 & 0xFFF, 12);
    putBit16z(v1, v27 & *v26, v28);
  }
  v29 = 0;
  if ( *(_DWORD *)(a1 + 216) )
  {
    v30 = (unsigned int)(8 * v24 + 8);
    do
    {
      putBit16z(
        v1,
        ~(-1 << (8 * v24 + 8))
      & (unsigned int)(*(_DWORD *)(a1 + 4LL * (unsigned int)(v29 + 1) + 220) - *(_DWORD *)(a1 + 4 * v29 + 220)),
        v30);
      v29 = v31;
    }
    while ( v31 < *(_DWORD *)(a1 + 216) );
    v26 = (unsigned int *)(a1 + 16604);
  }
  v32 = 0;
  if ( *v26 )
  {
    v33 = (unsigned int)(8 * v24 + 8);
    do
    {
      putBit16z(
        v1,
        ~(-1 << (8 * v24 + 8))
      & (unsigned int)(*(_DWORD *)(a1 + 4LL * (unsigned int)(v32 + 1) + 16608) - *(_DWORD *)(a1 + 4 * v32 + 16608)),
        v33);
      v32 = v34;
    }
    while ( v34 < *v26 );
  }
  if ( v8 )
  {
    putBit16z(v1, *(_DWORD *)(a1 + 34248) & 0x3F, 6);
    putBit16z(v1, *(_DWORD *)(a1 + 34256) & 0x3F, v35);
    putBit16z(v1, *(_DWORD *)(a1 + 34264) & 0x3F, v36);
    putBit16z(v1, *(_DWORD *)(a1 + 34272) & 0x3F, v37);
  }
  putBit16z(v1, 0, -*(_DWORD *)(v1 + 8) & 7);
  return WriteImagePlaneHeader(a1);
}

```

## disassembly

```asm
0x1800034a0  push    rbx
0x1800034a2  push    rbp
0x1800034a3  push    rsi
0x1800034a4  push    rdi
0x1800034a5  push    r12
0x1800034a7  push    r14
0x1800034a9  push    r15
0x1800034ab  sub     rsp, 20h
0x1800034af  mov     rax, [rcx+8]
0x1800034b3  mov     r11d, 0Fh
0x1800034b9  mov     rsi, [rcx+8640h]
0x1800034c0  add     rax, r11
0x1800034c3  mov     rdi, rcx
0x1800034c6  and     rax, 0FFFFFFFFFFFFFFF0h
0x1800034ca  xor     r12d, r12d
0x1800034cd  mov     ecx, 0FF0h
0x1800034d2  lea     ebp, [r11-0Eh]
0x1800034d6  cmp     rax, rcx
0x1800034d9  ja      short loc_1800034EE
0x1800034db  mov     rax, [rdi+10h]
0x1800034df  mov     r14d, ebp
0x1800034e2  add     rax, r11
0x1800034e5  and     rax, 0FFFFFFFFFFFFFFF0h
0x1800034e9  cmp     rax, rcx
0x1800034ec  jbe     short loc_1800034F1
0x1800034ee  mov     r14d, r12d
0x1800034f1  lea     rdx, [rdi+85D8h]
0x1800034f8  lea     r8, [rdi+85E0h]
0x1800034ff  lea     rcx, [rdi+85D0h]
0x180003506  lea     rax, [rdi+85C8h]
0x18000350d  cmp     [rdi+85E8h], r12d
0x180003514  jnz     short loc_180003522
0x180003516  mov     [rdx], r12
0x180003519  mov     [r8], r12
0x18000351c  mov     [rcx], r12
0x18000351f  mov     [rax], r12
0x180003522  cmp     [rax], r12
0x180003525  jnz     short loc_180003539
0x180003527  cmp     [rcx], r12
0x18000352a  jnz     short loc_180003539
0x18000352c  cmp     [rdx], r12
0x18000352f  jnz     short loc_180003539
0x180003531  mov     r15d, r12d
0x180003534  cmp     [r8], r12
0x180003537  jz      short loc_18000353C
0x180003539  mov     r15d, ebp
0x18000353c  mov     rbx, r12
0x18000353f  mov     rcx, [rdi+8640h]
0x180003546  lea     rax, gGDISignature; "WMPHOTO"
0x18000354d  movsx   eax, byte ptr [rbx+rax]
0x180003551  mov     r8d, 8
0x180003557  movzx   edx, al
0x18000355a  call    putBit16z
0x18000355f  add     rbx, rbp
0x180003562  cmp     rbx, r8
0x180003565  jnz     short loc_18000353F
0x180003567  mov     r8d, 4
0x18000356d  mov     edx, ebp
0x18000356f  mov     rcx, rsi
0x180003572  call    putBit16z
0x180003577  lea     ebx, [r8-1]
0x18000357b  cmp     [rdi+0A0h], r12d
0x180003582  jnz     short loc_180003589
0x180003584  mov     edx, r12d
0x180003587  jmp     short loc_1800035A1
0x180003589  mov     edx, [rdi+9Ch]
0x18000358f  mov     r8d, ebp
0x180003592  and     edx, ebp
0x180003594  mov     rcx, rsi
0x180003597  call    putBit16z
0x18000359c  mov     edx, ebp
0x18000359e  mov     r8d, ebx
0x1800035a1  mov     rcx, rsi
0x1800035a4  call    putBit16z
0x1800035a9  cmp     [rdi+0D8h], r12d
0x1800035b0  jnz     short loc_1800035BE
0x1800035b2  mov     edx, r12d
0x1800035b5  cmp     [rdi+40DCh], r12d
0x1800035bc  jz      short loc_1800035C0
0x1800035be  mov     edx, ebp
0x1800035c0  mov     r8d, ebp
0x1800035c3  mov     rcx, rsi
0x1800035c6  call    putBit16z
0x1800035cb  mov     edx, [rdi+0A8h]
0x1800035d1  mov     rcx, rsi
0x1800035d4  and     edx, ebp
0x1800035d6  call    putBit16z
0x1800035db  mov     edx, [rdi+7Ch]
0x1800035de  mov     r8d, ebx
0x1800035e1  and     edx, 7
0x1800035e4  mov     rcx, rsi
0x1800035e7  call    putBit16z
0x1800035ec  mov     edx, [rdi+85B4h]
0x1800035f2  mov     r8d, ebp
0x1800035f5  and     edx, ebp
0x1800035f7  mov     rcx, rsi
0x1800035fa  call    putBit16z
0x1800035ff  mov     edx, [rdi+98h]
0x180003605  mov     rcx, rsi
0x180003608  and     edx, ebx
0x18000360a  mov     ebx, 2
0x18000360f  mov     r8d, ebx
0x180003612  call    putBit16z
0x180003617  mov     edx, r14d
0x18000361a  mov     rcx, rsi
0x18000361d  mov     r8d, ebp
0x180003620  call    putBit16z
0x180003625  mov     edx, ebp
0x180003627  mov     rcx, rsi
0x18000362a  call    putBit16z
0x18000362f  mov     edx, r15d
0x180003632  mov     rcx, rsi
0x180003635  call    putBit16z
0x18000363a  mov     edx, [rdi+85B8h]
0x180003640  mov     rcx, rsi
0x180003643  and     edx, ebp
0x180003645  call    putBit16z
0x18000364a  xor     edx, edx
0x18000364c  mov     rcx, rsi
0x18000364f  mov     r8d, ebx
0x180003652  call    putBit16z
0x180003657  cmp     [rdi+85ACh], r12d
0x18000365e  jz      short loc_180003668
0x180003660  mov     edx, ebp
0x180003662  cmp     [rdi+38h], r12d
0x180003666  jnz     short loc_18000366B
0x180003668  mov     edx, r12d
0x18000366b  mov     r8d, ebp
0x18000366e  mov     rcx, rsi
0x180003671  call    putBit16z
0x180003676  mov     edx, [rdi+85ACh]
0x18000367c  mov     rcx, rsi
0x18000367f  and     edx, ebp
0x180003681  call    putBit16z
0x180003686  mov     edx, [rdi+18h]
0x180003689  mov     r8d, 4
0x18000368f  and     edx, r11d
0x180003692  mov     rcx, rsi
0x180003695  call    putBit16z
0x18000369a  mov     r8d, [rdi+1Ch]
0x18000369e  test    r8d, r8d
0x1800036a1  jnz     short loc_1800036AC
0x1800036a3  cmp     [rdi+80E4h], r12d
0x1800036aa  jnz     short loc_1800036AF
0x1800036ac  and     r11d, r8d
0x1800036af  mov     r8d, 4
0x1800036b5  mov     edx, r11d
0x1800036b8  mov     rcx, rsi
0x1800036bb  call    putBit16z
0x1800036c0  mov     edx, [rdi+8]
0x1800036c3  xor     r14d, ebp
0x1800036c6  sub     edx, ebp
0x1800036c8  mov     rcx, rsi
0x1800036cb  lea     ebx, [r14+1]
0x1800036cf  shl     ebx, 4
0x1800036d2  mov     r8d, ebx
0x1800036d5  call    putBit32
0x1800036da  mov     edx, [rdi+10h]
0x1800036dd  mov     r8d, ebx
0x1800036e0  sub     edx, ebp
0x1800036e2  mov     rcx, rsi
0x1800036e5  call    putBit32
0x1800036ea  mov     edx, [rdi+0D8h]
0x1800036f0  lea     rbx, [rdi+40DCh]
0x1800036f7  test    edx, edx
0x1800036f9  jnz     short loc_180003700
0x1800036fb  cmp     [rbx], r12d
0x1800036fe  jz      short loc_180003724
0x180003700  mov     r11d, 0FFFh
0x180003706  mov     r8d, 0Ch
0x18000370c  and     edx, r11d
0x18000370f  mov     rcx, rsi
0x180003712  call    putBit16z
0x180003717  mov     edx, [rbx]
0x180003719  mov     rcx, rsi
0x18000371c  and     edx, r11d
0x18000371f  call    putBit16z
0x180003724  or      ebp, 0FFFFFFFFh
0x180003727  mov     eax, r12d
0x18000372a  cmp     [rdi+0D8h], r12d
0x180003731  jbe     short loc_180003774
0x180003733  lea     r8d, ds:8[r14*8]
0x18000373b  mov     ebx, ebp
0x18000373d  mov     ecx, r8d
0x180003740  shl     ebx, cl
0x180003742  not     ebx
0x180003744  lea     r11d, [rax+1]
0x180003748  mov     rcx, rsi
0x18000374b  mov     edx, [rdi+r11*4+0DCh]
0x180003753  sub     edx, [rdi+rax*4+0DCh]
0x18000375a  and     edx, ebx
0x18000375c  call    putBit16z
0x180003761  mov     eax, r11d
0x180003764  cmp     r11d, [rdi+0D8h]
0x18000376b  jb      short loc_180003744
0x18000376d  lea     rbx, [rdi+40DCh]
0x180003774  mov     eax, r12d
0x180003777  cmp     [rbx], r12d
0x18000377a  jbe     short loc_1800037B0
0x18000377c  lea     r8d, ds:8[r14*8]
0x180003784  mov     ecx, r8d
0x180003787  shl     ebp, cl
0x180003789  not     ebp
0x18000378b  lea     r11d, [rax+1]
0x18000378f  mov     rcx, rsi
0x180003792  mov     edx, [rdi+r11*4+40E0h]
0x18000379a  sub     edx, [rdi+rax*4+40E0h]
0x1800037a1  and     edx, ebp
0x1800037a3  call    putBit16z
0x1800037a8  mov     eax, r11d
0x1800037ab  cmp     r11d, [rbx]
0x1800037ae  jb      short loc_18000378B
0x1800037b0  test    r15d, r15d
0x1800037b3  jz      short loc_1800037FF
0x1800037b5  mov     edx, [rdi+85C8h]
0x1800037bb  mov     r8d, 6
0x1800037c1  and     edx, 3Fh
0x1800037c4  mov     rcx, rsi
0x1800037c7  call    putBit16z
0x1800037cc  mov     edx, [rdi+85D0h]
0x1800037d2  mov     rcx, rsi
0x1800037d5  and     edx, 3Fh
0x1800037d8  call    putBit16z
0x1800037dd  mov     edx, [rdi+85D8h]
0x1800037e3  mov     rcx, rsi
0x1800037e6  and     edx, 3Fh
0x1800037e9  call    putBit16z
0x1800037ee  mov     edx, [rdi+85E0h]
0x1800037f4  mov     rcx, rsi
0x1800037f7  and     edx, 3Fh
0x1800037fa  call    putBit16z
0x1800037ff  mov     r8d, [rsi+8]
0x180003803  xor     edx, edx
0x180003805  neg     r8d
0x180003808  mov     rcx, rsi
0x18000380b  and     r8d, 7
0x18000380f  call    putBit16z
0x180003814  mov     rcx, rdi
0x180003817  add     rsp, 20h
0x18000381b  pop     r15
0x18000381d  pop     r14
0x18000381f  pop     r12
0x180003821  pop     rdi
0x180003822  pop     rsi
0x180003823  pop     rbp
0x180003824  pop     rbx
0x180003825  jmp     WriteImagePlaneHeader
```
