# QL_LEVEL_1_RPN_EXPRESSION::AddToken(_tag_WbemQl1Token const &)

- ea: `0x180024030`
- end: `0x180024261`
- name: `?AddToken@QL_LEVEL_1_RPN_EXPRESSION@@UEAAXAEBU_tag_WbemQl1Token@@@Z`
- size: `561`
- prototype: `void __fastcall(QL_LEVEL_1_RPN_EXPRESSION *this, const VARIANTARG *)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x1800099b0`
- `0x180009c40`
- `0x18000a290`
- `0x180014120`
- `0x180024030`
- `0x180024268`
- `0x18002ca74`
- `0x18002ea9c`
- `0x18002ee7c`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x18002407a`
- `OLEAUT32!__imp_VariantCopy` at `0x18002407a`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
void __fastcall QL_LEVEL_1_RPN_EXPRESSION::AddToken(QL_LEVEL_1_RPN_EXPRESSION *this, const VARIANTARG *a2)
{
  int v4; // r8d
  _DWORD *v5; // r14
  int *v6; // rax
  __int64 v7; // rax
  __int64 v8; // rbx
  __int64 v9; // rsi
  int v10; // r8d
  unsigned __int64 v11; // rbp
  __int64 v12; // rax
  bool v13; // cf
  unsigned __int64 v14; // rax
  unsigned __int64 *v15; // rax
  unsigned int v16; // edx
  _QWORD *v17; // rbx
  int i; // ebp
  QL_LEVEL_1_TOKEN *v19; // rcx
  unsigned __int64 *pExceptionObject; // [rsp+50h] [rbp+8h] BYREF

  v4 = *((_DWORD *)this + 3);
  v5 = (_DWORD *)((char *)this + 8);
  v6 = (int *)((char *)this + 8);
  if ( v4 == *((_DWORD *)this + 2) )
  {
    v10 = 2 * v4;
    *((_DWORD *)this + 3) = v10 + 2;
    v11 = v10 + 2LL;
    v12 = v11 << 7;
    if ( !is_mul_ok(v11, 0x80u) )
      v12 = -1;
    v13 = __CFADD__(v12, 8);
    v14 = v12 + 8;
    if ( v13 )
      v14 = -1;
    v15 = (unsigned __int64 *)CWin32DefaultArena::WbemMemAlloc(v14);
    pExceptionObject = v15;
    if ( v15 )
    {
      *v15 = v11;
      v17 = v15 + 1;
      `eh vector constructor iterator'(
        v15 + 1,
        0x80u,
        v11,
        (void (*)(void *))QL_LEVEL_1_TOKEN::QL_LEVEL_1_TOKEN,
        (void (*)(void *))QL_LEVEL_1_TOKEN::~QL_LEVEL_1_TOKEN);
    }
    else
    {
      v17 = 0;
    }
    if ( !v17 )
    {
      CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, -2);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          22,
          WPP_2122daa7e8023666a1921e333e1159b1_Traceguids,
          "CX_MemoryException()");
      }
      throw (CX_MemoryException *)&pExceptionObject;
    }
    for ( i = 0; i < *v5; ++i )
      QL_LEVEL_1_TOKEN::operator=(&v17[16 * (__int64)i], ((__int64)i << 7) + *((_QWORD *)this + 2));
    v19 = (QL_LEVEL_1_TOKEN *)*((_QWORD *)this + 2);
    if ( v19 )
      QL_LEVEL_1_TOKEN::`vector deleting destructor'(v19, v16);
    *((_QWORD *)this + 2) = v17;
    v6 = (int *)((char *)this + 8);
  }
  v7 = *v6;
  v8 = v7 << 7;
  v9 = *((_QWORD *)this + 2);
  *v5 = v7 + 1;
  if ( VariantCopy((VARIANTARG *)((v7 << 7) + v9 + 48), a2 + 2) < 0 )
  {
    CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, -2);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        28,
        WPP_2122daa7e8023666a1921e333e1159b1_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  *(_DWORD *)(v8 + v9) = *(_DWORD *)&a2->vt;
  CPropertyName::operator=(v8 + v9 + 8, &a2->decVal.Lo32);
  if ( a2[3].cyVal.Hi )
    CPropertyName::operator=(v8 + v9 + 80, &a2[1]);
  *(_DWORD *)(v8 + v9 + 40) = *((_DWORD *)&a2[1].decVal + 4);
  *(_DWORD *)(v8 + v9 + 116) = *(_DWORD *)&a2[3].vt;
  *(_DWORD *)(v8 + v9 + 120) = a2[3].decVal.Hi32;
  *(_DWORD *)(v8 + v9 + 72) = a2[3].lVal;
  *(_DWORD *)(v8 + v9 + 112) = a2[3].cyVal.Hi;
}

```

## disassembly

```asm
0x180024030  mov     [rsp+arg_8], rbx
0x180024035  mov     [rsp+arg_10], rbp
0x18002403a  push    rsi
0x18002403b  push    rdi
0x18002403c  push    r14
0x18002403e  sub     rsp, 30h
0x180024042  mov     rdi, rdx
0x180024045  mov     rsi, rcx
0x180024048  mov     r8d, [rcx+0Ch]
0x18002404c  lea     r14, [rcx+8]
0x180024050  mov     rax, r14
0x180024053  cmp     r8d, [r14]
0x180024056  jz      loc_1800240DD
0x18002405c  movsxd  rax, dword ptr [rax]
0x18002405f  mov     rbx, rax
0x180024062  shl     rbx, 7
0x180024066  mov     rsi, [rsi+10h]
0x18002406a  inc     eax
0x18002406c  mov     [r14], eax
0x18002406f  lea     rdx, [rdi+30h]; pvargSrc
0x180024073  lea     rcx, [rsi+30h]
0x180024077  add     rcx, rbx; pvargDest
0x18002407a  call    cs:__imp_VariantCopy
0x180024080  test    eax, eax
0x180024082  js      loc_1800241EE
0x180024088  mov     eax, [rdi]
0x18002408a  mov     [rbx+rsi], eax
0x18002408d  lea     rdx, [rdi+8]
0x180024091  lea     rcx, [rsi+8]
0x180024095  add     rcx, rbx
0x180024098  call    ??4CPropertyName@@QEAAXAEBU_tag_WbemPropertyName@@@Z; CPropertyName::operator=(_tag_WbemPropertyName const &)
0x18002409d  cmp     dword ptr [rdi+54h], 0
0x1800240a1  jnz     loc_18002424C
0x1800240a7  mov     eax, [rdi+28h]
0x1800240aa  mov     [rbx+rsi+28h], eax
0x1800240ae  mov     eax, [rdi+48h]
0x1800240b1  mov     [rbx+rsi+74h], eax
0x1800240b5  mov     eax, [rdi+4Ch]
0x1800240b8  mov     [rbx+rsi+78h], eax
0x1800240bc  mov     eax, [rdi+50h]
0x1800240bf  mov     [rbx+rsi+48h], eax
0x1800240c3  mov     eax, [rdi+54h]
0x1800240c6  mov     [rbx+rsi+70h], eax
0x1800240ca  mov     rbx, [rsp+48h+arg_8]
0x1800240cf  mov     rbp, [rsp+48h+arg_10]
0x1800240d4  add     rsp, 30h
0x1800240d8  pop     r14
0x1800240da  pop     rdi
0x1800240db  pop     rsi
0x1800240dc  retn
0x1800240dd  add     r8d, r8d
0x1800240e0  lea     eax, [r8+2]
0x1800240e4  mov     [rcx+0Ch], eax
0x1800240e7  movsxd  rbp, r8d
0x1800240ea  add     rbp, 2
0x1800240ee  mov     eax, 80h
0x1800240f3  mul     rbp
0x1800240f6  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800240fd  cmovb   rax, rcx
0x180024101  add     rax, 8
0x180024105  cmovb   rax, rcx
0x180024109  mov     rcx, rax; unsigned __int64
0x18002410c  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180024111  mov     [rsp+48h+pExceptionObject], rax
0x180024116  test    rax, rax
0x180024119  jz      short loc_18002418C
0x18002411b  mov     [rax], rbp
0x18002411e  lea     rbx, [rax+8]
0x180024122  lea     rax, ??1QL_LEVEL_1_TOKEN@@QEAA@XZ; QL_LEVEL_1_TOKEN::~QL_LEVEL_1_TOKEN(void)
0x180024129  mov     [rsp+48h+var_28], rax; void (*)(void *)
0x18002412e  lea     r9, ??0QL_LEVEL_1_TOKEN@@QEAA@XZ; void (*)(void *)
0x180024135  mov     r8, rbp; unsigned __int64
0x180024138  mov     edx, 80h; unsigned __int64
0x18002413d  mov     rcx, rbx; void *
0x180024140  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180024145  nop
0x180024146  test    rbx, rbx
0x180024149  jz      short loc_180024190
0x18002414b  xor     ebp, ebp
0x18002414d  cmp     [r14], ebp
0x180024150  jle     short loc_18002416F
0x180024152  movsxd  rcx, ebp
0x180024155  shl     rcx, 7
0x180024159  mov     rdx, [rsi+10h]
0x18002415d  add     rdx, rcx
0x180024160  add     rcx, rbx
0x180024163  call    ??4QL_LEVEL_1_TOKEN@@QEAAAEAU0@AEBU0@@Z; QL_LEVEL_1_TOKEN::operator=(QL_LEVEL_1_TOKEN const &)
0x180024168  inc     ebp
0x18002416a  cmp     ebp, [r14]
0x18002416d  jl      short loc_180024152
0x18002416f  mov     rcx, [rsi+10h]; this
0x180024173  test    rcx, rcx
0x180024176  jnz     short loc_180024185
0x180024178  mov     [rsi+10h], rbx
0x18002417c  lea     rax, [rsi+8]
0x180024180  jmp     loc_18002405C
0x180024185  call    ??_EQL_LEVEL_1_TOKEN@@QEAAPEAXI@Z; QL_LEVEL_1_TOKEN::`vector deleting destructor'(uint)
0x18002418a  jmp     short loc_180024178
0x18002418c  xor     ebx, ebx
0x18002418e  jmp     short loc_180024146
0x180024190  mov     edx, 0FFFFFFFEh; int
0x180024195  lea     rcx, qword_18006A9C0; this
0x18002419c  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800241a1  lea     rax, WPP_GLOBAL_Control
0x1800241a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800241af  cmp     rcx, rax
0x1800241b2  jz      short loc_1800241DC
0x1800241b4  test    byte ptr [rcx+1Ch], 1
0x1800241b8  jz      short loc_1800241DC
0x1800241ba  cmp     byte ptr [rcx+19h], 2
0x1800241be  jb      short loc_1800241DC
0x1800241c0  mov     edx, 16h
0x1800241c5  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800241cc  lea     r8, WPP_2122daa7e8023666a1921e333e1159b1_Traceguids
0x1800241d3  mov     rcx, [rcx+10h]
0x1800241d7  call    WPP_SF_s
0x1800241dc  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800241e3  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800241e8  call    _CxxThrowException_0
0x1800241ee  mov     edx, 0FFFFFFFEh; int
0x1800241f3  lea     rcx, qword_18006A9C0; this
0x1800241fa  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800241ff  lea     rax, WPP_GLOBAL_Control
0x180024206  mov     rcx, cs:WPP_GLOBAL_Control
0x18002420d  cmp     rcx, rax
0x180024210  jz      short loc_18002423A
0x180024212  test    byte ptr [rcx+1Ch], 1
0x180024216  jz      short loc_18002423A
0x180024218  cmp     byte ptr [rcx+19h], 2
0x18002421c  jb      short loc_18002423A
0x18002421e  mov     edx, 1Ch
0x180024223  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x18002422a  lea     r8, WPP_2122daa7e8023666a1921e333e1159b1_Traceguids
0x180024231  mov     rcx, [rcx+10h]
0x180024235  call    WPP_SF_s
0x18002423a  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x180024241  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180024246  call    _CxxThrowException_0
0x18002424c  lea     rdx, [rdi+18h]
0x180024250  lea     rcx, [rsi+50h]
0x180024254  add     rcx, rbx
0x180024257  call    ??4CPropertyName@@QEAAXAEBU_tag_WbemPropertyName@@@Z; CPropertyName::operator=(_tag_WbemPropertyName const &)
0x18002425c  jmp     loc_1800240A7
```
