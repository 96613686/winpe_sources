# ElementEnd(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING_STACK &)

- ea: `0x14003290c`
- end: `0x140032dc5`
- name: `?ElementEnd@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING_STACK@@@Z`
- size: `1209`
- prototype: `unsigned int __fastcall(struct _XMRW_OPEN_CONTEXT *, struct _UNICODE_STRING_STACK *)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x14003809c`

## callees

- `0x140016808`
- `0x14003290c`
- `0x140033254`
- `0x140033bac`
- `0x1400343e8`
- `0x14003506c`
- `0x14003694c`
- `0x140036c08`
- `0x140037ddc`
- `0x1400400d6`
- `0x140041010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400329ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400329ab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003299d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003299d`

## pseudocode

```c
unsigned int __fastcall ElementEnd(struct _XMRW_OPEN_CONTEXT *a1, struct _UNICODE_STRING_STACK *a2)
{
  struct _UNICODE_STRING v2; // xmm1
  _BYTE *v4; // rdi
  __int64 v6; // rdi
  _QWORD *v7; // rsi
  HANDLE ProcessHeap; // rax
  _QWORD *v9; // rax
  __int64 v10; // rcx
  _BYTE *v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rax
  _QWORD *v15; // rax
  __int64 v16; // rax
  char *v17; // rax
  struct _UNICODE_STRING v18; // [rsp+20h] [rbp-10h] BYREF
  unsigned int v19; // [rsp+58h] [rbp+28h] BYREF

  v2 = *(struct _UNICODE_STRING *)((char *)a2 + 8);
  v4 = (char *)a1 + 144;
  v18 = v2;
  if ( EqualString(&v18, L"Report", 0) && !*v4 )
    return ReportElementEnd(a1);
  v18 = v2;
  if ( EqualString(&v18, L"Import", 0) && !*v4 )
  {
    if ( *((_QWORD *)a1 + 8) )
    {
      v6 = *((_QWORD *)a1 + 14);
      if ( v6 )
      {
        while ( 1 )
        {
          v7 = *(_QWORD **)(v6 + 56);
          if ( !v7 )
            break;
          *(_QWORD *)(v6 + 56) = *v7;
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v7);
        }
        XmRWCloseFile(*((_QWORD *)a1 + 14));
        memset_0(*((void **)a1 + 14), 0, 0x98u);
      }
    }
    return 0;
  }
  v18 = v2;
  if ( EqualString(&v18, L"Sections", 0) && !*v4 )
  {
    v9 = (_QWORD *)*((_QWORD *)a1 + 8);
    v19 = 0;
    if ( v9 && (_QWORD *)*v9 == v9 )
    {
      (*(void (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)a1 + 3) + 168LL))(*((_QWORD *)a1 + 3), &v19);
      PrintMessage(0x462u, v19);
      return -1073222128;
    }
    return 0;
  }
  v18 = v2;
  if ( EqualString(&v18, L"Section", 0) && !*v4 )
  {
    v10 = *((_QWORD *)a1 + 9);
    v19 = 0;
    if ( v10 && *(_QWORD *)(v10 + 16) == v10 + 16 && *(_QWORD *)(v10 + 32) == v10 + 32 )
    {
      (*(void (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)a1 + 3) + 168LL))(*((_QWORD *)a1 + 3), &v19);
      PrintMessage(0x463u, v19);
      return -1073222128;
    }
    return 0;
  }
  v18 = v2;
  if ( EqualString(&v18, L"EventTable", 0) && !*v4 )
    return EventTableElementEnd(a1);
  v18 = v2;
  if ( EqualString(&v18, L"CounterTable", 0) && !*v4 )
    return 0;
  v18 = v2;
  if ( EqualString(&v18, L"Exclude", 0) )
  {
    if ( !*v4 )
      return 0;
  }
  v18 = v2;
  if ( !EqualString(&v18, L"Column", 0) || *((_BYTE *)a1 + 144) )
  {
    v18 = v2;
    if ( !EqualString(&v18, L"EventField", 0) || *((_BYTE *)a1 + 144) )
    {
      v18 = v2;
      if ( !EqualString(&v18, L"EqualJoin", 0) || *((_BYTE *)a1 + 144) )
      {
        v18 = v2;
        if ( !EqualString(&v18, L"EventJoinField", 0) || *((_BYTE *)a1 + 144) )
        {
          v18 = v2;
          if ( EqualString(&v18, L"SubTable", 0) && !*((_BYTE *)a1 + 144) )
          {
            v13 = *((_QWORD *)a1 + 10);
            v19 = 0;
            if ( v13 && *(_QWORD *)(v13 + 584) == v13 + 584 )
            {
              (*(void (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)a1 + 3) + 168LL))(
                *((_QWORD *)a1 + 3),
                &v19);
              PrintMessage(0x477u, v19);
              return -1073222128;
            }
            return 0;
          }
          v18 = v2;
          if ( EqualString(&v18, L"StringTable", 0) )
          {
            v19 = 0;
            if ( *((_BYTE *)a1 + 144) )
            {
              v15 = (_QWORD *)((char *)a1 + 128);
            }
            else
            {
              v14 = *((_QWORD *)a1 + 8);
              if ( !v14 )
                return 0;
              v15 = (_QWORD *)(v14 + 16);
            }
            if ( (_QWORD *)*v15 == v15 )
            {
              (*(void (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)a1 + 3) + 168LL))(
                *((_QWORD *)a1 + 3),
                &v19);
              PrintMessage(0x478u, v19);
              return -1073222128;
            }
            return 0;
          }
          v18 = v2;
          if ( !EqualString(&v18, L"String", 0) )
            return 0;
          v19 = 0;
          if ( *((_BYTE *)a1 + 144) )
          {
            v17 = (char *)a1 + 136;
          }
          else
          {
            v16 = *((_QWORD *)a1 + 8);
            if ( !v16 )
              return 0;
            v17 = (char *)(v16 + 24);
          }
          if ( *(_QWORD *)v17 && (*(_BYTE *)(*(_QWORD *)v17 + 96LL) & 2) != 0 )
            return 0;
          (*(void (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)a1 + 3) + 168LL))(*((_QWORD *)a1 + 3), &v19);
          PrintMessage(0x479u, v19);
          return -1073222126;
        }
        else
        {
          return EventJoinFieldElementEnd(a1);
        }
      }
      else
      {
        return EqualJoinElementEnd(a1);
      }
    }
    else
    {
      return EventFieldElementEnd(a1);
    }
  }
  else
  {
    v11 = (_BYTE *)*((_QWORD *)a1 + 12);
    v19 = 0;
    if ( !v11 )
      return 0;
    v12 = *((_QWORD *)a1 + 3);
    if ( (v11[370] & 1) == 0 )
    {
      (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v12 + 168LL))(v12, &v19);
      PrintMessage(0x46Bu, v19);
      return -1073222128;
    }
    if ( (v11[353] & 2) != 0 || (v11[369] & 8) == 0 )
      return 0;
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v12 + 168LL))(v12, &v19);
    PrintMessage(0x46Cu, v19);
    return -1073222102;
  }
}

```

## disassembly

```asm
0x14003290c  mov     [rsp-18h+arg_0], rbx
0x140032911  mov     [rsp-18h+arg_10], rsi
0x140032916  push    rbp
0x140032917  push    rdi
0x140032918  push    r14
0x14003291a  mov     rbp, rsp
0x14003291d  sub     rsp, 30h
0x140032921  movups  xmm1, xmmword ptr [rdx+8]
0x140032925  mov     rbx, rcx
0x140032928  lea     rdi, [rcx+90h]
0x14003292f  xor     r8d, r8d; unsigned __int8
0x140032932  lea     rdx, aReport; "Report"
0x140032939  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x14003293d  movdqu  xmmword ptr [rbp+var_10.Length], xmm1
0x140032942  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140032947  xor     r14d, r14d
0x14003294a  test    al, al
0x14003294c  jz      short loc_14003295D
0x14003294e  cmp     [rdi], r14b
0x140032951  jnz     short loc_14003295D
0x140032953  mov     rcx, rbx; struct _XMRW_OPEN_CONTEXT *
0x140032956  call    ?ReportElementEnd@@YAKPEAU_XMRW_OPEN_CONTEXT@@@Z; ReportElementEnd(_XMRW_OPEN_CONTEXT *)
0x14003295b  jmp     short loc_1400329D0
0x14003295d  xor     r8d, r8d; unsigned __int8
0x140032960  movdqa  xmmword ptr [rbp+var_10.Length], xmm1
0x140032965  lea     rdx, aImport; "Import"
0x14003296c  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140032970  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140032975  test    al, al
0x140032977  jz      short loc_1400329E3
0x140032979  cmp     [rdi], r14b
0x14003297c  jnz     short loc_1400329E3
0x14003297e  cmp     [rbx+40h], r14
0x140032982  jz      short loc_1400329CD
0x140032984  mov     rdi, [rbx+70h]
0x140032988  test    rdi, rdi
0x14003298b  jz      short loc_1400329CD
0x14003298d  mov     rsi, [rdi+38h]
0x140032991  test    rsi, rsi
0x140032994  jz      short loc_1400329B3
0x140032996  mov     rax, [rsi]
0x140032999  mov     [rdi+38h], rax
0x14003299d  call    cs:__imp_GetProcessHeap
0x1400329a3  mov     r8, rsi; lpMem
0x1400329a6  xor     edx, edx; dwFlags
0x1400329a8  mov     rcx, rax; hHeap
0x1400329ab  call    cs:__imp_HeapFree
0x1400329b1  jmp     short loc_14003298D
0x1400329b3  mov     rcx, [rbx+70h]
0x1400329b7  call    XmRWCloseFile
0x1400329bc  mov     rcx, [rbx+70h]; void *
0x1400329c0  xor     edx, edx; Val
0x1400329c2  mov     r8d, 98h; Size
0x1400329c8  call    memset_0
0x1400329cd  mov     eax, r14d
0x1400329d0  mov     rbx, [rsp+30h+arg_0]
0x1400329d5  mov     rsi, [rsp+30h+arg_10]
0x1400329da  add     rsp, 30h
0x1400329de  pop     r14
0x1400329e0  pop     rdi
0x1400329e1  pop     rbp
0x1400329e2  retn
0x1400329e3  xor     r8d, r8d; unsigned __int8
0x1400329e6  movdqa  xmmword ptr [rbp+var_10.Length], xmm1
0x1400329eb  lea     rdx, aSections; "Sections"
0x1400329f2  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x1400329f6  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x1400329fb  test    al, al
0x1400329fd  jz      short loc_140032A37
0x1400329ff  cmp     [rdi], r14b
0x140032a02  jnz     short loc_140032A37
0x140032a04  mov     rax, [rbx+40h]
0x140032a08  mov     [rbp+arg_8], r14d
0x140032a0c  test    rax, rax
0x140032a0f  jz      short loc_1400329CD
0x140032a11  cmp     [rax], rax
0x140032a14  jnz     short loc_1400329CD
0x140032a16  mov     rcx, [rbx+18h]
0x140032a1a  lea     rdx, [rbp+arg_8]
0x140032a1e  mov     rax, [rcx]
0x140032a21  mov     rax, [rax+0A8h]
0x140032a28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032a2d  mov     ecx, 462h
0x140032a32  jmp     loc_140032B7F
0x140032a37  xor     r8d, r8d; unsigned __int8
0x140032a3a  movdqa  xmmword ptr [rbp+var_10.Length], xmm1
0x140032a3f  lea     rdx, aSection_0; "Section"
0x140032a46  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140032a4a  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140032a4f  test    al, al
0x140032a51  jz      short loc_140032AA4
0x140032a53  cmp     [rdi], r14b
0x140032a56  jnz     short loc_140032AA4
0x140032a58  mov     rcx, [rbx+48h]
0x140032a5c  mov     [rbp+arg_8], r14d
0x140032a60  test    rcx, rcx
0x140032a63  jz      loc_1400329CD
0x140032a69  lea     rax, [rcx+10h]
0x140032a6d  cmp     [rax], rax
0x140032a70  jnz     loc_1400329CD
0x140032a76  lea     rax, [rcx+20h]
0x140032a7a  cmp     [rax], rax
0x140032a7d  jnz     loc_1400329CD
0x140032a83  mov     rcx, [rbx+18h]
0x140032a87  lea     rdx, [rbp+arg_8]
0x140032a8b  mov     rax, [rcx]
0x140032a8e  mov     rax, [rax+0A8h]
0x140032a95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032a9a  mov     ecx, 463h
0x140032a9f  jmp     loc_140032B7F
0x140032aa4  xor     r8d, r8d; unsigned __int8
0x140032aa7  movdqa  xmmword ptr [rbp+var_10.Length], xmm1
0x140032aac  lea     rdx, aEventtable; "EventTable"
0x140032ab3  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140032ab7  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140032abc  test    al, al
0x140032abe  jz      short loc_140032AD2
0x140032ac0  cmp     [rdi], r14b
0x140032ac3  jnz     short loc_140032AD2
0x140032ac5  mov     rcx, rbx; struct _XMRW_OPEN_CONTEXT *
0x140032ac8  call    ?EventTableElementEnd@@YAKPEAU_XMRW_OPEN_CONTEXT@@@Z; EventTableElementEnd(_XMRW_OPEN_CONTEXT *)
0x140032acd  jmp     loc_1400329D0
0x140032ad2  xor     r8d, r8d; unsigned __int8
0x140032ad5  movdqa  xmmword ptr [rbp+var_10.Length], xmm1
0x140032ada  lea     rdx, aCountertable; "CounterTable"
0x140032ae1  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140032ae5  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140032aea  test    al, al
0x140032aec  jz      short loc_140032AF7
0x140032aee  cmp     [rdi], r14b
0x140032af1  jz      loc_1400329CD
0x140032af7  xor     r8d, r8d; unsigned __int8
0x140032afa  movdqa  xmmword ptr [rbp+var_10.Length], xmm1
0x140032aff  lea     rdx, aExclude; "Exclude"
0x140032b06  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140032b0a  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140032b0f  test    al, al
0x140032b11  jz      short loc_140032B1C
0x140032b13  cmp     [rdi], r14b
0x140032b16  jz      loc_1400329CD
0x140032b1c  xor     r8d, r8d; unsigned __int8
0x140032b1f  movdqa  xmmword ptr [rbp+var_10.Length], xmm1
0x140032b24  lea     rdx, aColumn_0; "Column"
0x140032b2b  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140032b2f  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140032b34  test    al, al
0x140032b36  jz      loc_140032BD5
0x140032b3c  cmp     [rbx+90h], r14b
0x140032b43  jnz     loc_140032BD5
0x140032b49  mov     rax, [rbx+60h]
0x140032b4d  mov     [rbp+arg_8], r14d
0x140032b51  test    rax, rax
0x140032b54  jz      loc_1400329CD
0x140032b5a  test    byte ptr [rax+172h], 1
0x140032b61  mov     rcx, [rbx+18h]
0x140032b65  jnz     short loc_140032B91
0x140032b67  mov     rax, [rcx]
0x140032b6a  lea     rdx, [rbp+arg_8]
0x140032b6e  mov     rax, [rax+0A8h]
0x140032b75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032b7a  mov     ecx, 46Bh; unsigned int
0x140032b7f  mov     edx, [rbp+arg_8]
0x140032b82  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140032b87  mov     eax, 0C007EE10h
0x140032b8c  jmp     loc_1400329D0
0x140032b91  test    byte ptr [rax+161h], 2
0x140032b98  jnz     loc_1400329CD
0x140032b9e  test    byte ptr [rax+171h], 8
0x140032ba5  jz      loc_1400329CD
0x140032bab  mov     rax, [rcx]
0x140032bae  lea     rdx, [rbp+arg_8]
0x140032bb2  mov     rax, [rax+0A8h]
0x140032bb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032bbe  mov     edx, [rbp+arg_8]
0x140032bc1  mov     ecx, 46Ch; unsigned int
0x140032bc6  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140032bcb  mov     eax, 0C007EE2Ah
0x140032bd0  jmp     loc_1400329D0
0x140032bd5  xor     r8d, r8d; unsigned __int8
0x140032bd8  movdqa  xmmword ptr [rbp+var_10.Length], xmm1
0x140032bdd  lea     rdx, aEventfield; "EventField"
0x140032be4  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140032be8  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140032bed  test    al, al
0x140032bef  jz      short loc_140032C07
0x140032bf1  cmp     [rbx+90h], r14b
0x140032bf8  jnz     short loc_140032C07
0x140032bfa  mov     rcx, rbx; struct _XMRW_OPEN_CONTEXT *
0x140032bfd  call    ?EventFieldElementEnd@@YAKPEAU_XMRW_OPEN_CONTEXT@@@Z; EventFieldElementEnd(_XMRW_OPEN_CONTEXT *)
0x140032c02  jmp     loc_1400329D0
0x140032c07  xor     r8d, r8d; unsigned __int8
0x140032c0a  movdqa  xmmword ptr [rbp+var_10.Length], xmm1
0x140032c0f  lea     rdx, aEqualjoin; "EqualJoin"
0x140032c16  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140032c1a  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140032c1f  test    al, al
0x140032c21  jz      short loc_140032C39
0x140032c23  cmp     [rbx+90h], r14b
0x140032c2a  jnz     short loc_140032C39
0x140032c2c  mov     rcx, rbx; struct _XMRW_OPEN_CONTEXT *
0x140032c2f  call    ?EqualJoinElementEnd@@YAKPEAU_XMRW_OPEN_CONTEXT@@@Z; EqualJoinElementEnd(_XMRW_OPEN_CONTEXT *)
0x140032c34  jmp     loc_1400329D0
0x140032c39  xor     r8d, r8d; unsigned __int8
0x140032c3c  movdqa  xmmword ptr [rbp+var_10.Length], xmm1
0x140032c41  lea     rdx, aEventjoinfield; "EventJoinField"
0x140032c48  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140032c4c  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140032c51  test    al, al
0x140032c53  jz      short loc_140032C6B
0x140032c55  cmp     [rbx+90h], r14b
0x140032c5c  jnz     short loc_140032C6B
0x140032c5e  mov     rcx, rbx; struct _XMRW_OPEN_CONTEXT *
0x140032c61  call    ?EventJoinFieldElementEnd@@YAKPEAU_XMRW_OPEN_CONTEXT@@@Z; EventJoinFieldElementEnd(_XMRW_OPEN_CONTEXT *)
0x140032c66  jmp     loc_1400329D0
0x140032c6b  xor     r8d, r8d; unsigned __int8
0x140032c6e  movdqa  xmmword ptr [rbp+var_10.Length], xmm1
0x140032c73  lea     rdx, aSubtable; "SubTable"
0x140032c7a  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140032c7e  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140032c83  test    al, al
0x140032c85  jz      short loc_140032CD1
0x140032c87  cmp     [rbx+90h], r14b
0x140032c8e  jnz     short loc_140032CD1
0x140032c90  mov     rax, [rbx+50h]
0x140032c94  mov     [rbp+arg_8], r14d
0x140032c98  test    rax, rax
0x140032c9b  jz      loc_1400329CD
0x140032ca1  add     rax, 248h
0x140032ca7  cmp     [rax], rax
0x140032caa  jnz     loc_1400329CD
0x140032cb0  mov     rcx, [rbx+18h]
0x140032cb4  lea     rdx, [rbp+arg_8]
0x140032cb8  mov     rax, [rcx]
0x140032cbb  mov     rax, [rax+0A8h]
0x140032cc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032cc7  mov     ecx, 477h
0x140032ccc  jmp     loc_140032B7F
0x140032cd1  xor     r8d, r8d; unsigned __int8
0x140032cd4  movdqa  xmmword ptr [rbp+var_10.Length], xmm1
0x140032cd9  lea     rdx, aStringtable_1; "StringTable"
0x140032ce0  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140032ce4  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140032ce9  test    al, al
0x140032ceb  jz      short loc_140032D3E
0x140032ced  mov     [rbp+arg_8], r14d
0x140032cf1  cmp     [rbx+90h], r14b
0x140032cf8  jnz     short loc_140032D0D
0x140032cfa  mov     rax, [rbx+40h]
0x140032cfe  test    rax, rax
0x140032d01  jz      loc_1400329CD
0x140032d07  add     rax, 10h
0x140032d0b  jmp     short loc_140032D14
0x140032d0d  lea     rax, [rbx+80h]
0x140032d14  cmp     [rax], rax
0x140032d17  jnz     loc_1400329CD
0x140032d1d  mov     rcx, [rbx+18h]
0x140032d21  lea     rdx, [rbp+arg_8]
0x140032d25  mov     rax, [rcx]
0x140032d28  mov     rax, [rax+0A8h]
0x140032d2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032d34  mov     ecx, 478h
0x140032d39  jmp     loc_140032B7F
0x140032d3e  xor     r8d, r8d; unsigned __int8
0x140032d41  movdqa  xmmword ptr [rbp+var_10.Length], xmm1
0x140032d46  lea     rdx, aString_1; "String"
0x140032d4d  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140032d51  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140032d56  test    al, al
0x140032d58  jz      loc_1400329CD
0x140032d5e  mov     [rbp+arg_8], r14d
0x140032d62  cmp     [rbx+90h], r14b
0x140032d69  jnz     short loc_140032D7E
0x140032d6b  mov     rax, [rbx+40h]
0x140032d6f  test    rax, rax
0x140032d72  jz      loc_1400329CD
0x140032d78  add     rax, 18h
0x140032d7c  jmp     short loc_140032D85
0x140032d7e  lea     rax, [rbx+88h]
0x140032d85  mov     rcx, [rax]
0x140032d88  test    rcx, rcx
0x140032d8b  jz      short loc_140032D97
0x140032d8d  test    byte ptr [rcx+60h], 2
0x140032d91  jnz     loc_1400329CD
0x140032d97  mov     rcx, [rbx+18h]
0x140032d9b  lea     rdx, [rbp+arg_8]
0x140032d9f  mov     rax, [rcx]
0x140032da2  mov     rax, [rax+0A8h]
0x140032da9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032dae  mov     edx, [rbp+arg_8]
0x140032db1  mov     ecx, 479h; unsigned int
0x140032db6  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140032dbb  mov     eax, 0C007EE12h
0x140032dc0  jmp     loc_1400329D0
```
