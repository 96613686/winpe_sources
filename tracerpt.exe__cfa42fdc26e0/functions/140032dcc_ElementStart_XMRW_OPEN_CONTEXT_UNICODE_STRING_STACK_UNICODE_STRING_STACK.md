# ElementStart(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING_STACK &,_UNICODE_STRING_STACK *)

- ea: `0x140032dcc`
- end: `0x14003324d`
- name: `?ElementStart@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING_STACK@@PEAU2@@Z`
- size: `1153`
- prototype: `unsigned int __fastcall(struct _XMRW_OPEN_CONTEXT *, struct _UNICODE_STRING_STACK *, struct _UNICODE_STRING_STACK *)`
- caller_count: `1`
- callee_count: `16`
- tags: ``

## callers

- `0x14003809c`

## callees

- `0x140016808`
- `0x1400318f0`
- `0x140032230`
- `0x140032dcc`
- `0x140033ec4`
- `0x14003451c`
- `0x140035300`
- `0x140035880`
- `0x140035f48`
- `0x140036258`
- `0x14003694c`
- `0x140036ce0`
- `0x140037364`
- `0x140037698`
- `0x140037b90`
- `0x140041010`

## pseudocode

```c
unsigned int __fastcall ElementStart(
        struct _XMRW_OPEN_CONTEXT *a1,
        struct _UNICODE_STRING_STACK *a2,
        struct _UNICODE_STRING_STACK *a3)
{
  struct _UNICODE_STRING v3; // xmm1
  __int64 v7; // rsi
  __int64 v8; // rsi
  bool v9; // zf
  __int64 v10; // rbx
  __int64 v11; // rsi
  struct _UNICODE_STRING v12; // [rsp+20h] [rbp-10h] BYREF
  unsigned int v13; // [rsp+58h] [rbp+28h] BYREF

  v3 = *(struct _UNICODE_STRING *)((char *)a2 + 8);
  v12 = v3;
  if ( EqualString(&v12, L"Report", 0) && !a3 && !*((_BYTE *)a1 + 144) )
    return ReportElementStart(a1);
  v12 = v3;
  if ( EqualString(&v12, L"Import", 0) && a3 && !*((_BYTE *)a1 + 144) )
    return ImportElementStart(a1, a3);
  v12 = v3;
  if ( EqualString(&v12, L"Sections", 0) && a3 && !*((_BYTE *)a1 + 144) )
  {
    v7 = *((_QWORD *)a1 + 8);
    if ( v7 && *((_DWORD *)a1 + 12) == 2 )
    {
      v12 = *(struct _UNICODE_STRING *)((char *)a3 + 8);
      if ( EqualString(&v12, L"Report", 0) )
        *(_BYTE *)(v7 + 208) |= 0x10u;
    }
    return 0;
  }
  v12 = v3;
  if ( EqualString(&v12, L"Section", 0) && a3 && !*((_BYTE *)a1 + 144) )
    return SectionElementStart(a1, a3);
  v12 = v3;
  if ( EqualString(&v12, L"EventTable", 0) && a3 && !*((_BYTE *)a1 + 144) )
    return EventTableElementStart(a1, a3);
  v12 = v3;
  if ( EqualString(&v12, L"CounterTable", 0) && a3 && !*((_BYTE *)a1 + 144) )
    return CounterTableElementStart(a1, a3);
  v12 = v3;
  if ( EqualString(&v12, L"Exclude", 0) && a3 && !*((_BYTE *)a1 + 144) )
    return ExcludeElementStart(a1, a3);
  v12 = v3;
  if ( EqualString(&v12, L"Include", 0) && a3 && !*((_BYTE *)a1 + 144) )
    return IncludeElementStart(a1, a3);
  v12 = v3;
  if ( EqualString(&v12, L"Column", 0) && a3 && !*((_BYTE *)a1 + 144) )
    return ColumnElementStart(a1, a3);
  v12 = v3;
  if ( EqualString(&v12, L"EventField", 0) && a3 && !*((_BYTE *)a1 + 144) )
    return EventFieldElementStart(a1, a3);
  v12 = v3;
  if ( EqualString(&v12, L"EqualJoin", 0) && a3 && !*((_BYTE *)a1 + 144) )
  {
    v8 = *((_QWORD *)a1 + 10);
    if ( !v8 )
      return 0;
    v9 = *((_DWORD *)a1 + 12) == 5;
    v13 = 0;
    if ( !v9 )
      return 0;
    v10 = *((_QWORD *)a1 + 3);
    v12 = *(struct _UNICODE_STRING *)((char *)a3 + 8);
    if ( !EqualString(&v12, L"EventTable", 0) )
      return 0;
    if ( (*(_BYTE *)(v8 + 681) & 7) == 1 )
    {
      *(_BYTE *)(v8 + 681) |= 2u;
      return 0;
    }
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v10 + 168LL))(v10, &v13);
    PrintMessage(0x44Fu, v13);
    return -1073222076;
  }
  else
  {
    v12 = v3;
    if ( EqualString(&v12, L"EventJoinField", 0) && a3 && !*((_BYTE *)a1 + 144) )
    {
      return EventJoinFieldElementStart(a1, a3);
    }
    else
    {
      v12 = v3;
      if ( EqualString(&v12, L"SubTable", 0) && a3 && !*((_BYTE *)a1 + 144) )
      {
        return SubTableElementStart(a1, a3);
      }
      else
      {
        v12 = v3;
        if ( EqualString(&v12, L"StringTable", 0) )
        {
          if ( !*((_BYTE *)a1 + 144) )
          {
            v11 = *((_QWORD *)a1 + 8);
            if ( v11 )
            {
              if ( a3 )
              {
                if ( *((_DWORD *)a1 + 12) == 2 )
                {
                  v12 = *(struct _UNICODE_STRING *)((char *)a3 + 8);
                  if ( EqualString(&v12, L"Report", 0) )
                    *(_BYTE *)(v11 + 208) |= 0x20u;
                }
              }
            }
          }
          return 0;
        }
        v12 = v3;
        if ( !EqualString(&v12, L"String", 0) || !a3 )
          return 0;
        return StringElementStart(a1, a3);
      }
    }
  }
}

```

## disassembly

```asm
0x140032dcc  mov     [rsp-18h+arg_0], rbx
0x140032dd1  mov     [rsp-18h+arg_10], rsi
0x140032dd6  push    rbp
0x140032dd7  push    rdi
0x140032dd8  push    r14
0x140032dda  mov     rbp, rsp
0x140032ddd  sub     rsp, 30h
0x140032de1  movups  xmm1, xmmword ptr [rdx+8]
0x140032de5  mov     rdi, r8
0x140032de8  lea     rdx, aReport; "Report"
0x140032def  mov     rbx, rcx
0x140032df2  xor     r8d, r8d; unsigned __int8
0x140032df5  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140032df9  movdqu  xmmword ptr [rbp+var_10.Length], xmm1
0x140032dfe  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140032e03  xor     r14d, r14d
0x140032e06  test    al, al
0x140032e08  jz      short loc_140032E25
0x140032e0a  test    rdi, rdi
0x140032e0d  jnz     short loc_140032E25
0x140032e0f  cmp     [rbx+90h], r14b
0x140032e16  jnz     short loc_140032E25
0x140032e18  mov     rcx, rbx; struct _XMRW_OPEN_CONTEXT *
0x140032e1b  call    ?ReportElementStart@@YAKPEAU_XMRW_OPEN_CONTEXT@@@Z; ReportElementStart(_XMRW_OPEN_CONTEXT *)
0x140032e20  jmp     loc_140032EBF
0x140032e25  xor     r8d, r8d; unsigned __int8
0x140032e28  movdqa  xmmword ptr [rbp+var_10.Length], xmm1
0x140032e2d  lea     rdx, aImport; "Import"
0x140032e34  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140032e38  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140032e3d  test    al, al
0x140032e3f  jz      short loc_140032E5C
0x140032e41  test    rdi, rdi
0x140032e44  jz      short loc_140032E5C
0x140032e46  cmp     [rbx+90h], r14b
0x140032e4d  jnz     short loc_140032E5C
0x140032e4f  mov     rdx, rdi; struct _UNICODE_STRING_STACK *
0x140032e52  mov     rcx, rbx; struct _XMRW_OPEN_CONTEXT *
0x140032e55  call    ?ImportElementStart@@YAKPEAU_XMRW_OPEN_CONTEXT@@PEAU_UNICODE_STRING_STACK@@@Z; ImportElementStart(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING_STACK *)
0x140032e5a  jmp     short loc_140032EBF
0x140032e5c  xor     r8d, r8d; unsigned __int8
0x140032e5f  movdqa  xmmword ptr [rbp+var_10.Length], xmm1
0x140032e64  lea     rdx, aSections; "Sections"
0x140032e6b  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140032e6f  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140032e74  test    al, al
0x140032e76  jz      short loc_140032ED2
0x140032e78  test    rdi, rdi
0x140032e7b  jz      short loc_140032ED2
0x140032e7d  cmp     [rbx+90h], r14b
0x140032e84  jnz     short loc_140032ED2
0x140032e86  mov     rsi, [rbx+40h]
0x140032e8a  test    rsi, rsi
0x140032e8d  jz      short loc_140032EBC
0x140032e8f  cmp     dword ptr [rbx+30h], 2
0x140032e93  jnz     short loc_140032EBC
0x140032e95  movups  xmm0, xmmword ptr [rdi+8]
0x140032e99  xor     r8d, r8d; unsigned __int8
0x140032e9c  lea     rdx, aReport; "Report"
0x140032ea3  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140032ea7  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x140032eac  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140032eb1  test    al, al
0x140032eb3  jz      short loc_140032EBC
0x140032eb5  or      byte ptr [rsi+0D0h], 10h
0x140032ebc  mov     eax, r14d
0x140032ebf  mov     rbx, [rsp+30h+arg_0]
0x140032ec4  mov     rsi, [rsp+30h+arg_10]
0x140032ec9  add     rsp, 30h
0x140032ecd  pop     r14
0x140032ecf  pop     rdi
0x140032ed0  pop     rbp
0x140032ed1  retn
0x140032ed2  xor     r8d, r8d; unsigned __int8
0x140032ed5  movdqa  xmmword ptr [rbp+var_10.Length], xmm1
0x140032eda  lea     rdx, aSection_0; "Section"
0x140032ee1  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140032ee5  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140032eea  test    al, al
0x140032eec  jz      short loc_140032F09
0x140032eee  test    rdi, rdi
0x140032ef1  jz      short loc_140032F09
0x140032ef3  cmp     [rbx+90h], r14b
0x140032efa  jnz     short loc_140032F09
0x140032efc  mov     rdx, rdi; struct _UNICODE_STRING_STACK *
0x140032eff  mov     rcx, rbx; struct _XMRW_OPEN_CONTEXT *
0x140032f02  call    ?SectionElementStart@@YAKPEAU_XMRW_OPEN_CONTEXT@@PEAU_UNICODE_STRING_STACK@@@Z; SectionElementStart(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING_STACK *)
0x140032f07  jmp     short loc_140032EBF
0x140032f09  xor     r8d, r8d; unsigned __int8
0x140032f0c  movdqa  xmmword ptr [rbp+var_10.Length], xmm1
0x140032f11  lea     rdx, aEventtable; "EventTable"
0x140032f18  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140032f1c  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140032f21  test    al, al
0x140032f23  jz      short loc_140032F43
0x140032f25  test    rdi, rdi
0x140032f28  jz      short loc_140032F43
0x140032f2a  cmp     [rbx+90h], r14b
0x140032f31  jnz     short loc_140032F43
0x140032f33  mov     rdx, rdi; struct _UNICODE_STRING_STACK *
0x140032f36  mov     rcx, rbx; struct _XMRW_OPEN_CONTEXT *
0x140032f39  call    ?EventTableElementStart@@YAKPEAU_XMRW_OPEN_CONTEXT@@PEAU_UNICODE_STRING_STACK@@@Z; EventTableElementStart(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING_STACK *)
0x140032f3e  jmp     loc_140032EBF
0x140032f43  xor     r8d, r8d; unsigned __int8
0x140032f46  movdqa  xmmword ptr [rbp+var_10.Length], xmm1
0x140032f4b  lea     rdx, aCountertable; "CounterTable"
0x140032f52  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140032f56  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140032f5b  test    al, al
0x140032f5d  jz      short loc_140032F7D
0x140032f5f  test    rdi, rdi
0x140032f62  jz      short loc_140032F7D
0x140032f64  cmp     [rbx+90h], r14b
0x140032f6b  jnz     short loc_140032F7D
0x140032f6d  mov     rdx, rdi; struct _UNICODE_STRING_STACK *
0x140032f70  mov     rcx, rbx; struct _XMRW_OPEN_CONTEXT *
0x140032f73  call    ?CounterTableElementStart@@YAKPEAU_XMRW_OPEN_CONTEXT@@PEAU_UNICODE_STRING_STACK@@@Z; CounterTableElementStart(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING_STACK *)
0x140032f78  jmp     loc_140032EBF
0x140032f7d  xor     r8d, r8d; unsigned __int8
0x140032f80  movdqa  xmmword ptr [rbp+var_10.Length], xmm1
0x140032f85  lea     rdx, aExclude; "Exclude"
0x140032f8c  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140032f90  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140032f95  test    al, al
0x140032f97  jz      short loc_140032FB7
0x140032f99  test    rdi, rdi
0x140032f9c  jz      short loc_140032FB7
0x140032f9e  cmp     [rbx+90h], r14b
0x140032fa5  jnz     short loc_140032FB7
0x140032fa7  mov     rdx, rdi; struct _UNICODE_STRING_STACK *
0x140032faa  mov     rcx, rbx; struct _XMRW_OPEN_CONTEXT *
0x140032fad  call    ?ExcludeElementStart@@YAKPEAU_XMRW_OPEN_CONTEXT@@PEAU_UNICODE_STRING_STACK@@@Z; ExcludeElementStart(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING_STACK *)
0x140032fb2  jmp     loc_140032EBF
0x140032fb7  xor     r8d, r8d; unsigned __int8
0x140032fba  movdqa  xmmword ptr [rbp+var_10.Length], xmm1
0x140032fbf  lea     rdx, aInclude; "Include"
0x140032fc6  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140032fca  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140032fcf  test    al, al
0x140032fd1  jz      short loc_140032FF1
0x140032fd3  test    rdi, rdi
0x140032fd6  jz      short loc_140032FF1
0x140032fd8  cmp     [rbx+90h], r14b
0x140032fdf  jnz     short loc_140032FF1
0x140032fe1  mov     rdx, rdi; struct _UNICODE_STRING_STACK *
0x140032fe4  mov     rcx, rbx; struct _XMRW_OPEN_CONTEXT *
0x140032fe7  call    ?IncludeElementStart@@YAKPEAU_XMRW_OPEN_CONTEXT@@PEAU_UNICODE_STRING_STACK@@@Z; IncludeElementStart(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING_STACK *)
0x140032fec  jmp     loc_140032EBF
0x140032ff1  xor     r8d, r8d; unsigned __int8
0x140032ff4  movdqa  xmmword ptr [rbp+var_10.Length], xmm1
0x140032ff9  lea     rdx, aColumn_0; "Column"
0x140033000  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140033004  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140033009  test    al, al
0x14003300b  jz      short loc_14003302B
0x14003300d  test    rdi, rdi
0x140033010  jz      short loc_14003302B
0x140033012  cmp     [rbx+90h], r14b
0x140033019  jnz     short loc_14003302B
0x14003301b  mov     rdx, rdi; struct _UNICODE_STRING_STACK *
0x14003301e  mov     rcx, rbx; struct _XMRW_OPEN_CONTEXT *
0x140033021  call    ?ColumnElementStart@@YAKPEAU_XMRW_OPEN_CONTEXT@@PEAU_UNICODE_STRING_STACK@@@Z; ColumnElementStart(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING_STACK *)
0x140033026  jmp     loc_140032EBF
0x14003302b  xor     r8d, r8d; unsigned __int8
0x14003302e  movdqa  xmmword ptr [rbp+var_10.Length], xmm1
0x140033033  lea     rdx, aEventfield; "EventField"
0x14003303a  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x14003303e  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140033043  test    al, al
0x140033045  jz      short loc_140033065
0x140033047  test    rdi, rdi
0x14003304a  jz      short loc_140033065
0x14003304c  cmp     [rbx+90h], r14b
0x140033053  jnz     short loc_140033065
0x140033055  mov     rdx, rdi; struct _UNICODE_STRING_STACK *
0x140033058  mov     rcx, rbx; struct _XMRW_OPEN_CONTEXT *
0x14003305b  call    ?EventFieldElementStart@@YAKPEAU_XMRW_OPEN_CONTEXT@@PEAU_UNICODE_STRING_STACK@@@Z; EventFieldElementStart(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING_STACK *)
0x140033060  jmp     loc_140032EBF
0x140033065  xor     r8d, r8d; unsigned __int8
0x140033068  movdqa  xmmword ptr [rbp+var_10.Length], xmm1
0x14003306d  lea     rdx, aEqualjoin; "EqualJoin"
0x140033074  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140033078  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x14003307d  test    al, al
0x14003307f  jz      loc_140033127
0x140033085  test    rdi, rdi
0x140033088  jz      loc_140033127
0x14003308e  cmp     [rbx+90h], r14b
0x140033095  jnz     loc_140033127
0x14003309b  mov     rsi, [rbx+50h]
0x14003309f  test    rsi, rsi
0x1400330a2  jz      loc_140032EBC
0x1400330a8  cmp     dword ptr [rbx+30h], 5
0x1400330ac  mov     [rbp+arg_8], r14d
0x1400330b0  jnz     loc_140032EBC
0x1400330b6  movups  xmm0, xmmword ptr [rdi+8]
0x1400330ba  mov     rbx, [rbx+18h]
0x1400330be  lea     rdx, aEventtable; "EventTable"
0x1400330c5  xor     r8d, r8d; unsigned __int8
0x1400330c8  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x1400330cc  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x1400330d1  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x1400330d6  test    al, al
0x1400330d8  jz      loc_140032EBC
0x1400330de  mov     cl, [rsi+2A9h]
0x1400330e4  mov     al, cl
0x1400330e6  and     al, 7
0x1400330e8  cmp     al, 1
0x1400330ea  jnz     short loc_1400330FA
0x1400330ec  or      cl, 2
0x1400330ef  mov     [rsi+2A9h], cl
0x1400330f5  jmp     loc_140032EBC
0x1400330fa  mov     rax, [rbx]
0x1400330fd  lea     rdx, [rbp+arg_8]
0x140033101  mov     rcx, rbx
0x140033104  mov     rax, [rax+0A8h]
0x14003310b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033110  mov     edx, [rbp+arg_8]
0x140033113  mov     ecx, 44Fh; unsigned int
0x140033118  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x14003311d  mov     eax, 0C007EE44h
0x140033122  jmp     loc_140032EBF
0x140033127  xor     r8d, r8d; unsigned __int8
0x14003312a  movdqa  xmmword ptr [rbp+var_10.Length], xmm1
0x14003312f  lea     rdx, aEventjoinfield; "EventJoinField"
0x140033136  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x14003313a  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x14003313f  test    al, al
0x140033141  jz      short loc_140033161
0x140033143  test    rdi, rdi
0x140033146  jz      short loc_140033161
0x140033148  cmp     [rbx+90h], r14b
0x14003314f  jnz     short loc_140033161
0x140033151  mov     rdx, rdi; struct _UNICODE_STRING_STACK *
0x140033154  mov     rcx, rbx; struct _XMRW_OPEN_CONTEXT *
0x140033157  call    ?EventJoinFieldElementStart@@YAKPEAU_XMRW_OPEN_CONTEXT@@PEAU_UNICODE_STRING_STACK@@@Z; EventJoinFieldElementStart(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING_STACK *)
0x14003315c  jmp     loc_140032EBF
0x140033161  xor     r8d, r8d; unsigned __int8
0x140033164  movdqa  xmmword ptr [rbp+var_10.Length], xmm1
0x140033169  lea     rdx, aSubtable; "SubTable"
0x140033170  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140033174  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140033179  test    al, al
0x14003317b  jz      short loc_14003319B
0x14003317d  test    rdi, rdi
0x140033180  jz      short loc_14003319B
0x140033182  cmp     [rbx+90h], r14b
0x140033189  jnz     short loc_14003319B
0x14003318b  mov     rdx, rdi; struct _UNICODE_STRING_STACK *
0x14003318e  mov     rcx, rbx; struct _XMRW_OPEN_CONTEXT *
0x140033191  call    ?SubTableElementStart@@YAKPEAU_XMRW_OPEN_CONTEXT@@PEAU_UNICODE_STRING_STACK@@@Z; SubTableElementStart(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING_STACK *)
0x140033196  jmp     loc_140032EBF
0x14003319b  xor     r8d, r8d; unsigned __int8
0x14003319e  movdqa  xmmword ptr [rbp+var_10.Length], xmm1
0x1400331a3  lea     rdx, aStringtable_1; "StringTable"
0x1400331aa  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x1400331ae  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x1400331b3  test    al, al
0x1400331b5  jz      short loc_140033214
0x1400331b7  cmp     [rbx+90h], r14b
0x1400331be  jnz     loc_140032EBC
0x1400331c4  mov     rsi, [rbx+40h]
0x1400331c8  test    rsi, rsi
0x1400331cb  jz      loc_140032EBC
0x1400331d1  test    rdi, rdi
0x1400331d4  jz      loc_140032EBC
0x1400331da  cmp     dword ptr [rbx+30h], 2
0x1400331de  jnz     loc_140032EBC
0x1400331e4  movups  xmm0, xmmword ptr [rdi+8]
0x1400331e8  xor     r8d, r8d; unsigned __int8
0x1400331eb  lea     rdx, aReport; "Report"
0x1400331f2  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x1400331f6  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x1400331fb  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140033200  test    al, al
0x140033202  jz      loc_140032EBC
0x140033208  or      byte ptr [rsi+0D0h], 20h
0x14003320f  jmp     loc_140032EBC
0x140033214  xor     r8d, r8d; unsigned __int8
0x140033217  movdqa  xmmword ptr [rbp+var_10.Length], xmm1
0x14003321c  lea     rdx, aString_1; "String"
0x140033223  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140033227  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x14003322c  test    al, al
0x14003322e  jz      loc_140032EBC
0x140033234  test    rdi, rdi
0x140033237  jz      loc_140032EBC
0x14003323d  mov     rdx, rdi; struct _UNICODE_STRING_STACK *
0x140033240  mov     rcx, rbx; struct _XMRW_OPEN_CONTEXT *
0x140033243  call    ?StringElementStart@@YAKPEAU_XMRW_OPEN_CONTEXT@@PEAU_UNICODE_STRING_STACK@@@Z; StringElementStart(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING_STACK *)
0x140033248  jmp     loc_140032EBF
```
