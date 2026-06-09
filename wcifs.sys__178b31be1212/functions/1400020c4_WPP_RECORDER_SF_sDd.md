# WPP_RECORDER_SF_sDd

- ea: `0x1400020c4`
- end: `0x14000225e`
- name: `WPP_RECORDER_SF_sDd`
- size: `410`
- prototype: `__int64(__int64, unsigned __int8, unsigned int, unsigned __int16, __int64, const char *, ...)`
- caller_count: `79`
- callee_count: `2`
- tags: ``

## callers

- `0x140001710`
- `0x140002520`
- `0x140002be4`
- `0x140002d20`
- `0x14000308c`
- `0x140006160`
- `0x14000696c`
- `0x140014570`
- `0x140014c90`
- `0x140015a70`
- `0x140015dc4`
- `0x140016734`
- `0x140016aa8`
- `0x140016d68`
- `0x14001771c`
- `0x1400184f0`
- `0x140018b9c`
- `0x140018e28`
- `0x14001a62c`
- `0x14001b0bc`
- `0x14001bf24`
- `0x14001c244`
- `0x14001c688`
- `0x14001cff0`
- `0x14001d8dc`
- `0x14001e028`
- `0x14001e228`
- `0x14001e374`
- `0x14001e80c`
- `0x14001eadc`
- `0x14001f1c8`
- `0x14001f488`
- `0x14001fa5c`
- `0x14001fe40`
- `0x140020840`
- `0x140020b60`
- `0x140020e60`
- `0x140022270`
- `0x140024380`
- `0x140024880`
- `0x140024c40`
- `0x140025270`
- `0x140026260`
- `0x140026ba8`
- `0x140026e30`
- `0x1400278a4`
- `0x140027f74`
- `0x140028ad0`
- `0x140029504`
- `0x140029658`

## callees

- `0x1400020c4`
- `0x140007d40`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140002240`
- `WppRecorder!WppAutoLogTrace` at `0x140002240`

## pseudocode

```c
__int64 WPP_RECORDER_SF_sDd(
        __int64 a1,
        unsigned __int8 a2,
        unsigned int a3,
        unsigned __int16 a4,
        __int64 a5,
        const char *a6,
        ...)
{
  __int64 v6; // rdi
  unsigned __int64 v8; // rsi
  unsigned int v9; // r15d
  __int64 v10; // rbp
  const char *v12; // rbx
  int v13; // eax
  __int64 v14; // rax
  __int64 v15; // rdx
  const char *v16; // rcx
  bool v17; // zf
  int v19; // [rsp+20h] [rbp-88h]
  __int64 v20; // [rsp+B0h] [rbp+8h]
  __int64 v21; // [rsp+E0h] [rbp+38h] BYREF
  va_list va; // [rsp+E0h] [rbp+38h]
  va_list va1; // [rsp+E8h] [rbp+40h] BYREF

  va_start(va1, a6);
  va_start(va, a6);
  v21 = va_arg(va1, _QWORD);
  v20 = a1;
  v6 = -1;
  v8 = (unsigned __int64)a3 >> 16;
  v9 = a2;
  v10 = 5;
  v12 = a6;
  v13 = *((_DWORD *)&wil_details_featureDescriptors_a->Timer + 20 * v8 + (((a3 - 1) >> 5) & 0x7FF) + 1);
  if ( _bittest(&v13, (a3 - 1) & 0x1F) && *((_BYTE *)&wil_details_featureDescriptors_a->Timer + 80 * v8 + 1) >= a2 )
  {
    if ( a6 )
    {
      v14 = -1;
      do
        ++v14;
      while ( a6[v14] );
      v15 = v14 + 1;
    }
    else
    {
      v15 = 5;
    }
    v16 = a6;
    if ( !a6 )
      v16 = "NULL";
    pfnWppTraceMessage(
      *((_QWORD *)&wil_details_featureDescriptors_a->AttachedDevice + 10 * v8),
      43,
      a5,
      a4,
      v16,
      v15,
      (__int64 *)va,
      4,
      va1);
    a1 = v20;
  }
  v17 = a6 == 0;
  if ( a6 )
  {
    do
      ++v6;
    while ( a6[v6] );
    v10 = v6 + 1;
    v17 = a6 == 0;
  }
  if ( v17 )
    v12 = "NULL";
  LOWORD(v19) = a4;
  return WppAutoLogTrace(a1, v9, a3, a5, v19, v12, v10, (__int64 *)va, 4, va1);
}

```

## disassembly

```asm
0x1400020c4  mov     [rsp+arg_0], rcx
0x1400020c9  push    rbx
0x1400020ca  push    rbp
0x1400020cb  push    rsi
0x1400020cc  push    rdi
0x1400020cd  push    r12
0x1400020cf  push    r13
0x1400020d1  push    r14
0x1400020d3  push    r15
0x1400020d5  sub     rsp, 68h
0x1400020d9  mov     r14, cs:wil_details_featureDescriptors_a
0x1400020e0  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1400020e4  mov     r13d, r8d
0x1400020e7  mov     esi, r8d
0x1400020ea  lea     r8, aNull; "NULL"
0x1400020f1  shr     rsi, 10h
0x1400020f5  movzx   r15d, dl
0x1400020f9  lea     ebp, [rdi+6]
0x1400020fc  lea     ebx, [r13-1]
0x140002100  movzx   r12d, r9w
0x140002104  mov     r10d, ebx
0x140002107  lea     r9d, [rdi+5]
0x14000210b  shr     r10, 5
0x14000210f  lea     rax, [rsi+rsi*4]
0x140002113  and     ebx, 1Fh
0x140002116  and     r10d, 7FFh
0x14000211d  mov     edx, ebx
0x14000211f  mov     rbx, [rsp+0A8h+arg_28]
0x140002127  lea     r11, [r10+rax*4]
0x14000212b  mov     eax, [r14+r11*4+2Ch]
0x140002130  bt      eax, edx
0x140002133  jnb     loc_1400021DC
0x140002139  lea     r10, [rsi+rsi*4]
0x14000213d  add     r10, r10
0x140002140  cmp     [r14+r10*8+29h], r15b
0x140002145  jb      loc_1400021DC
0x14000214b  test    rbx, rbx
0x14000214e  jz      short loc_140002162
0x140002150  mov     rax, rdi
0x140002153  inc     rax
0x140002156  cmp     byte ptr [rbx+rax], 0
0x14000215a  jnz     short loc_140002153
0x14000215c  lea     rdx, [rax+1]
0x140002160  jmp     short loc_140002165
0x140002162  mov     rdx, rbp
0x140002165  mov     rax, cs:pfnWppTraceMessage
0x14000216c  test    rbx, rbx
0x14000216f  mov     [rsp+0A8h+var_58], 0
0x140002178  mov     rcx, rbx
0x14000217b  mov     [rsp+0A8h+var_60], r9
0x140002180  cmovz   rcx, r8
0x140002184  lea     r8, [rsp+0A8h+arg_38]
0x14000218c  mov     [rsp+0A8h+var_68], r8
0x140002191  lea     r8, [rsp+0A8h+arg_30]
0x140002199  mov     [rsp+0A8h+var_70], r9
0x14000219e  mov     r9d, r12d
0x1400021a1  mov     [rsp+0A8h+var_78], r8
0x1400021a6  mov     r8, [rsp+0A8h+arg_20]
0x1400021ae  mov     [rsp+0A8h+var_80], rdx
0x1400021b3  mov     edx, 2Bh ; '+'
0x1400021b8  mov     [rsp+0A8h+var_88], rcx
0x1400021bd  mov     rcx, [r14+r10*8+18h]
0x1400021c2  call    _guard_dispatch_icall
0x1400021c7  mov     rcx, [rsp+0A8h+arg_0]
0x1400021cf  lea     r8, aNull; "NULL"
0x1400021d6  mov     r9d, 4
0x1400021dc  test    rbx, rbx
0x1400021df  jz      short loc_1400021F1
0x1400021e1  inc     rdi
0x1400021e4  cmp     byte ptr [rbx+rdi], 0
0x1400021e8  jnz     short loc_1400021E1
0x1400021ea  lea     rbp, [rdi+1]
0x1400021ee  test    rbx, rbx
0x1400021f1  mov     [rsp+0A8h+var_50], 0
0x1400021fa  lea     rax, [rsp+0A8h+arg_38]
0x140002202  mov     [rsp+0A8h+var_58], r9
0x140002207  cmovz   rbx, r8
0x14000220b  mov     [rsp+0A8h+var_60], rax
0x140002210  mov     r8d, r13d
0x140002213  mov     [rsp+0A8h+var_68], r9
0x140002218  lea     rax, [rsp+0A8h+arg_30]
0x140002220  mov     r9, [rsp+0A8h+arg_20]
0x140002228  mov     edx, r15d
0x14000222b  mov     [rsp+0A8h+var_70], rax
0x140002230  mov     [rsp+0A8h+var_78], rbp
0x140002235  mov     [rsp+0A8h+var_80], rbx
0x14000223a  mov     word ptr [rsp+0A8h+var_88], r12w
0x140002240  call    cs:__imp_WppAutoLogTrace
0x140002247  nop     dword ptr [rax+rax+00h]
0x14000224c  add     rsp, 68h
0x140002250  pop     r15
0x140002252  pop     r14
0x140002254  pop     r13
0x140002256  pop     r12
0x140002258  pop     rdi
0x140002259  pop     rsi
0x14000225a  pop     rbp
0x14000225b  pop     rbx
0x14000225c  retn
```
