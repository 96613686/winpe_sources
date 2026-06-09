# WinHvScanTdComprehensive

- ea: `0x1400252c0`
- end: `0x1400253cf`
- name: `WinHvScanTdComprehensive`
- size: `271`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140002240`
- `0x140003610`
- `0x140009c90`
- `0x14000a040`
- `0x1400252c0`

## pseudocode

```c
__int64 __fastcall WinHvScanTdComprehensive(
        __int64 a1,
        __int64 a2,
        __int16 a3,
        char a4,
        char a5,
        _DWORD *a6,
        _DWORD *a7)
{
  __int64 *v11; // r14
  bool v12; // cl
  _DWORD *v13; // rdi
  int v14; // eax
  unsigned int v15; // ebx
  _DWORD *v16; // rax
  _QWORD v18[8]; // [rsp+20h] [rbp-58h] BYREF
  __int64 *v19; // [rsp+80h] [rbp+8h] BYREF
  _DWORD *v20; // [rsp+88h] [rbp+10h] BYREF

  v19 = 0;
  v20 = 0;
  memset(v18, 0, sizeof(v18));
  WinHvpSetupHypercall(&v19, (__int64 *)&v20, (__int64)v18);
  v11 = v19;
  v12 = a5 != 0;
  *(_OWORD *)v19 = 0;
  v11[2] = 0;
  *v11 = a1;
  v11[1] = a2;
  v13 = v20;
  *((_WORD *)v11 + 10) = a3;
  *((_BYTE *)v11 + 22) = a4;
  *((_BYTE *)v11 + 23) = *((_BYTE *)v11 + 23) & 0xFC | v12 & 0xFD;
  *((_DWORD *)v11 + 4) = 0;
  do
  {
    v14 = WinHvpSimplePoolHypercall_CallViaMacro(v18[0], 331);
    *((_BYTE *)v11 + 23) |= 2u;
    v15 = v14;
    *((_DWORD *)v11 + 4) = v13[2];
  }
  while ( v14 == -1070268294 );
  if ( v14 >= 0 )
  {
    v16 = a7;
    *a6 = v13[1];
    *v16 = *v13;
  }
  ((void (__fastcall *)(_QWORD))v18[7])(v18[0]);
  return v15;
}

```

## disassembly

```asm
0x1400252c0  mov     rax, rsp
0x1400252c3  mov     [rax+18h], rbx
0x1400252c7  mov     [rax+20h], rbp
0x1400252cb  push    rsi
0x1400252cc  push    rdi
0x1400252cd  push    r14
0x1400252cf  sub     rsp, 60h
0x1400252d3  mov     rdi, rdx
0x1400252d6  mov     qword ptr [rax+8], 0
0x1400252de  xor     edx, edx; Val
0x1400252e0  mov     qword ptr [rax+10h], 0
0x1400252e8  movzx   esi, r8w
0x1400252ec  mov     rbx, rcx
0x1400252ef  lea     rcx, [rax-58h]; void *
0x1400252f3  mov     bpl, r9b
0x1400252f6  lea     r8d, [rdx+40h]; Size
0x1400252fa  call    memset
0x1400252ff  lea     r8, [rsp+78h+var_58]
0x140025304  lea     rdx, [rsp+78h+arg_8]
0x14002530c  lea     rcx, [rsp+78h+arg_0]
0x140025314  call    WinHvpSetupHypercall
0x140025319  mov     r14, [rsp+78h+arg_0]
0x140025321  xor     eax, eax
0x140025323  cmp     [rsp+78h+arg_20], al
0x14002532a  xorps   xmm0, xmm0
0x14002532d  setnz   cl
0x140025330  movups  xmmword ptr [r14], xmm0
0x140025334  mov     [r14+10h], rax
0x140025338  mov     [r14], rbx
0x14002533b  mov     [r14+8], rdi
0x14002533f  mov     rdi, [rsp+78h+arg_8]
0x140025347  mov     [r14+14h], si
0x14002534c  mov     [r14+16h], bpl
0x140025350  mov     al, [r14+17h]
0x140025354  and     al, 0FEh
0x140025356  or      cl, al
0x140025358  and     cl, 0FDh
0x14002535b  mov     [r14+17h], cl
0x14002535f  mov     dword ptr [r14+10h], 0
0x140025367  mov     rcx, [rsp+78h+var_58]
0x14002536c  mov     edx, 14Bh
0x140025371  call    WinHvpSimplePoolHypercall_CallViaMacro
0x140025376  or      byte ptr [r14+17h], 2
0x14002537b  mov     ebx, eax
0x14002537d  mov     ecx, [rdi+8]
0x140025380  mov     [r14+10h], ecx
0x140025384  cmp     eax, 0C035007Ah
0x140025389  jz      short loc_140025367
0x14002538b  test    eax, eax
0x14002538d  js      short loc_1400253A8
0x14002538f  mov     rcx, [rsp+78h+arg_28]
0x140025397  mov     edx, [rdi+4]
0x14002539a  mov     rax, [rsp+78h+arg_30]
0x1400253a2  mov     [rcx], edx
0x1400253a4  mov     ecx, [rdi]
0x1400253a6  mov     [rax], ecx
0x1400253a8  mov     rcx, [rsp+78h+var_58]
0x1400253ad  mov     rax, [rsp+78h+var_20]
0x1400253b2  call    _guard_dispatch_icall
0x1400253b7  lea     r11, [rsp+78h+var_18]
0x1400253bc  mov     eax, ebx
0x1400253be  mov     rbx, [r11+30h]
0x1400253c2  mov     rbp, [r11+38h]
0x1400253c6  mov     rsp, r11
0x1400253c9  pop     r14
0x1400253cb  pop     rdi
0x1400253cc  pop     rsi
0x1400253cd  retn
```
