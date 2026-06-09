# WString2::CopyBuffer(ushort const *,unsigned __int64)

- ea: `0x180013310`
- end: `0x18001355d`
- name: `?CopyBuffer@WString2@@AEAAXPEBG_K@Z`
- size: `589`
- prototype: `void __fastcall(WString2 *__hidden this, const unsigned __int16 *, unsigned __int64)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180013290`
- `0x180028290`
- `0x180040680`

## callees

- `0x180013310`
- `0x180013564`
- `0x180014120`
- `0x18002ca74`
- `0x18002ee7c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001340c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001340c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180013445`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180013445`

## pseudocode

```c
void __fastcall WString2::CopyBuffer(WString2 *this, const unsigned __int16 *a2, __int64 a3)
{
  const unsigned __int16 *v4; // rsi
  unsigned __int64 v6; // rax
  unsigned __int64 v7; // rax
  _WORD *v8; // rdx
  __int64 v9; // rcx
  _WORD *v10; // rcx
  unsigned int v11; // ebx
  unsigned __int64 v12; // r14
  unsigned __int64 v13; // rdx
  __int64 v14; // rax
  void *v15; // r8
  HANDLE v16; // rcx
  unsigned __int64 v17; // rax
  SIZE_T v18; // rax
  LPVOID v19; // rax
  char pExceptionObject; // [rsp+48h] [rbp+10h] BYREF

  v4 = a2;
  if ( a2 && a3 )
  {
    v6 = *((_QWORD *)this + 1);
    if ( 2 * a3 + 2 > v6 )
    {
      v12 = *((_QWORD *)this + 4);
      v13 = (unsigned __int64)(a3 + 1) % *((_QWORD *)this + 3);
      v14 = a3 + 1;
      v15 = *(void **)this;
      v16 = hHeap;
      v17 = v13 + v14;
      if ( v17 >= v12 )
        v12 = v17;
      if ( v15 != &unk_180070020 )
      {
        if ( hHeap && v15 )
        {
          HeapFree(hHeap, 0, v15);
          v16 = hHeap;
        }
        *((_QWORD *)this + 1) = 0;
        *(_QWORD *)this = &unk_180070020;
        *((_QWORD *)this + 2) = 0;
      }
      if ( !v16 )
        goto LABEL_34;
      v18 = 2 * v12;
      if ( !is_mul_ok(v12, 2u) )
        v18 = -1;
      v19 = HeapAlloc(v16, 0, v18);
      if ( !v19 )
      {
LABEL_34:
        CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, 0xFFFFFFFE);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            10,
            &WPP_7ea248c7c68f38396e9085d61ca851e0_Traceguids,
            "CX_MemoryException()");
        }
        throw (CX_MemoryException *)&pExceptionObject;
      }
      *(_QWORD *)this = v19;
      v6 = 2 * v12;
      *((_QWORD *)this + 1) = 2 * v12;
    }
    v7 = v6 >> 1;
    v8 = *(_WORD **)this;
    *((_QWORD *)this + 2) = a3;
    if ( v7 )
    {
      if ( v7 > 0x7FFFFFFF )
      {
        v11 = -2147024809;
        *v8 = 0;
      }
      else
      {
        v9 = 2147483646;
        do
        {
          if ( !v9 )
            break;
          if ( !*v4 )
            break;
          *v8++ = *v4++;
          --v9;
          --v7;
        }
        while ( v7 );
        v10 = v8 - 1;
        v11 = -2147024774;
        if ( v7 )
        {
          v10 = v8;
          v11 = 0;
        }
        *v10 = 0;
        if ( v7 )
          return;
      }
    }
    else
    {
      v11 = -2147024809;
    }
    CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, v11);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_7ea248c7c68f38396e9085d61ca851e0_Traceguids, v11);
    }
    return;
  }
  if ( *(_UNKNOWN **)this != &unk_180070020 )
  {
    if ( *((_QWORD *)this + 1) > 2u )
      **(_WORD **)this = 0;
    *((_QWORD *)this + 2) = 0;
  }
}

```

## disassembly

```asm
0x180013310  mov     [rsp+arg_10], rbx
0x180013315  mov     [rsp+arg_18], rbp
0x18001331a  push    rsi
0x18001331b  push    rdi
0x18001331c  push    r15
0x18001331e  sub     rsp, 20h
0x180013322  mov     rbx, r8
0x180013325  mov     rsi, rdx
0x180013328  mov     rdi, rcx
0x18001332b  test    rdx, rdx
0x18001332e  jz      loc_1800134BA
0x180013334  test    rbx, rbx
0x180013337  jz      loc_1800134BA
0x18001333d  mov     rax, [rcx+8]
0x180013341  lea     rdx, ds:2[r8*2]
0x180013349  xor     ebp, ebp
0x18001334b  mov     [rsp+38h+arg_0], r14
0x180013350  cmp     rdx, rax
0x180013353  ja      short loc_1800133CE
0x180013355  shr     rax, 1
0x180013358  mov     rdx, [rdi]
0x18001335b  mov     [rdi+10h], rbx
0x18001335f  jz      loc_180013547
0x180013365  cmp     rax, 7FFFFFFFh
0x18001336b  ja      loc_180013540
0x180013371  mov     ecx, 7FFFFFFEh
0x180013376  test    rcx, rcx
0x180013379  jz      short loc_18001339A
0x18001337b  movzx   r8d, word ptr [rsi]
0x18001337f  test    r8w, r8w
0x180013383  jz      short loc_18001339A
0x180013385  mov     [rdx], r8w
0x180013389  add     rsi, 2
0x18001338d  add     rdx, 2
0x180013391  dec     rcx
0x180013394  sub     rax, 1
0x180013398  jnz     short loc_180013376
0x18001339a  test    rax, rax
0x18001339d  lea     rcx, [rdx-2]
0x1800133a1  mov     ebx, 8007007Ah
0x1800133a6  cmovnz  rcx, rdx
0x1800133aa  cmovnz  ebx, ebp
0x1800133ad  mov     [rcx], bp
0x1800133b0  jz      loc_180013464
0x1800133b6  mov     r14, [rsp+38h+arg_0]
0x1800133bb  mov     rbx, [rsp+38h+arg_10]
0x1800133c0  mov     rbp, [rsp+38h+arg_18]
0x1800133c5  add     rsp, 20h
0x1800133c9  pop     r15
0x1800133cb  pop     rdi
0x1800133cc  pop     rsi
0x1800133cd  retn
0x1800133ce  mov     r14, [rcx+20h]
0x1800133d2  lea     rax, [r8+1]
0x1800133d6  xor     edx, edx
0x1800133d8  lea     r15, unk_180070020
0x1800133df  div     qword ptr [rcx+18h]
0x1800133e3  lea     rax, [r8+1]
0x1800133e7  mov     r8, [rcx]; lpMem
0x1800133ea  mov     rcx, cs:hHeap; hHeap
0x1800133f1  add     rax, rdx
0x1800133f4  cmp     rax, r14
0x1800133f7  cmovnb  r14, rax
0x1800133fb  cmp     r8, r15
0x1800133fe  jz      short loc_180013424
0x180013400  test    rcx, rcx
0x180013403  jz      short loc_180013419
0x180013405  test    r8, r8
0x180013408  jz      short loc_180013419
0x18001340a  xor     edx, edx; dwFlags
0x18001340c  call    cs:__imp_HeapFree
0x180013412  mov     rcx, cs:hHeap; hHeap
0x180013419  mov     [rdi+8], rbp
0x18001341d  mov     [rdi], r15
0x180013420  mov     [rdi+10h], rbp
0x180013424  test    rcx, rcx
0x180013427  jz      loc_1800134E2
0x18001342d  mov     eax, 2
0x180013432  mul     r14
0x180013435  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x18001343c  cmovb   rax, rdx
0x180013440  xor     edx, edx; dwFlags
0x180013442  mov     r8, rax; dwBytes
0x180013445  call    cs:__imp_HeapAlloc
0x18001344b  test    rax, rax
0x18001344e  jz      loc_1800134E2
0x180013454  mov     [rdi], rax
0x180013457  lea     rax, [r14+r14]
0x18001345b  mov     [rdi+8], rax
0x18001345f  jmp     loc_180013355
0x180013464  mov     edx, ebx; int
0x180013466  lea     rcx, unk_18006A9C0; this
0x18001346d  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180013472  mov     rcx, cs:WPP_GLOBAL_Control
0x180013479  lea     rax, WPP_GLOBAL_Control
0x180013480  cmp     rcx, rax
0x180013483  jz      loc_1800133B6
0x180013489  test    byte ptr [rcx+1Ch], 1
0x18001348d  jz      loc_1800133B6
0x180013493  cmp     byte ptr [rcx+19h], 2
0x180013497  jb      loc_1800133B6
0x18001349d  mov     rcx, [rcx+10h]
0x1800134a1  lea     r8, WPP_7ea248c7c68f38396e9085d61ca851e0_Traceguids
0x1800134a8  mov     edx, 0Bh
0x1800134ad  mov     r9d, ebx
0x1800134b0  call    WPP_SF_D
0x1800134b5  jmp     loc_1800133B6
0x1800134ba  mov     rax, [rcx]
0x1800134bd  lea     r15, unk_180070020
0x1800134c4  cmp     rax, r15
0x1800134c7  jz      loc_1800133BB
0x1800134cd  xor     ebp, ebp
0x1800134cf  cmp     qword ptr [rcx+8], 2
0x1800134d4  jbe     short loc_1800134D9
0x1800134d6  mov     [rax], bp
0x1800134d9  mov     [rcx+10h], rbp
0x1800134dd  jmp     loc_1800133BB
0x1800134e2  mov     edx, 0FFFFFFFEh; int
0x1800134e7  lea     rcx, unk_18006A9C0; this
0x1800134ee  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800134f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800134fa  lea     rax, WPP_GLOBAL_Control
0x180013501  cmp     rcx, rax
0x180013504  jz      short loc_18001352E
0x180013506  test    byte ptr [rcx+1Ch], 1
0x18001350a  jz      short loc_18001352E
0x18001350c  cmp     byte ptr [rcx+19h], 2
0x180013510  jb      short loc_18001352E
0x180013512  mov     rcx, [rcx+10h]
0x180013516  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x18001351d  mov     edx, 0Ah
0x180013522  lea     r8, WPP_7ea248c7c68f38396e9085d61ca851e0_Traceguids
0x180013529  call    WPP_SF_s
0x18001352e  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x180013535  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18001353a  call    _CxxThrowException_0
0x180013540  mov     ebx, 80070057h
0x180013545  jmp     short loc_180013555
0x180013547  mov     ebx, 80070057h
0x18001354c  test    rax, rax
0x18001354f  jz      loc_180013464
0x180013555  mov     [rdx], bp
0x180013558  jmp     loc_180013464
```
