# EventTableElementEnd(_XMRW_OPEN_CONTEXT *)

- ea: `0x14003506c`
- end: `0x1400352f7`
- name: `?EventTableElementEnd@@YAKPEAU_XMRW_OPEN_CONTEXT@@@Z`
- size: `651`
- prototype: `__int64 __fastcall(struct _XMRW_OPEN_CONTEXT *, __int64, __int64, __int64 j)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14003290c`

## callees

- `0x140016808`
- `0x14003506c`
- `0x14003694c`
- `0x140041010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400350df`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400350df`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400350f4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400350f4`

## pseudocode

```c
__int64 __fastcall EventTableElementEnd(struct _XMRW_OPEN_CONTEXT *a1, __int64 a2, __int64 a3, __int64 j)
{
  __int64 v4; // rbx
  __int64 v5; // rdi
  __int64 *v6; // rsi
  __int64 *v7; // rax
  unsigned int v9; // r14d
  HANDLE ProcessHeap; // rax
  LPVOID v11; // rax
  __int64 *v12; // rdx
  char v13; // al
  __int64 *v14; // r14
  __int64 *i; // rcx
  char v16; // dl
  struct _UNICODE_STRING v17; // [rsp+20h] [rbp-10h] BYREF
  unsigned int v18; // [rsp+50h] [rbp+20h] BYREF

  v4 = *((_QWORD *)a1 + 10);
  v18 = 0;
  if ( !v4 )
    return 0;
  v5 = *((_QWORD *)a1 + 3);
  v6 = (__int64 *)(v4 + 16);
  v7 = *(__int64 **)(v4 + 16);
  if ( v7 == (__int64 *)(v4 + 16) )
  {
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v5 + 168LL))(v5, &v18);
    PrintMessage(0x464u, v18);
    return 3221745168LL;
  }
  v9 = *(_DWORD *)(v4 + 36);
  if ( !v9 )
  {
    do
    {
      v14 = (__int64 *)*v7;
      if ( (v7[44] & 0x40) != 0 )
      {
        v17 = *(struct _UNICODE_STRING *)(v7 + 23);
        if ( !EqualString(&v17, L"sys:RequestRate", 0) )
        {
          (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v5 + 168LL))(v5, &v18);
          PrintMessage(0x466u, v18);
          return 3221745198LL;
        }
      }
      v7 = v14;
    }
    while ( v6 != v14 );
LABEL_15:
    LOBYTE(a3) = *(_BYTE *)(v4 + 208);
    if ( (_BYTE)a3 )
    {
      v13 = *(_BYTE *)(v4 + 681);
      if ( (v13 & 2) != 0 )
      {
        (*(void (__fastcall **)(__int64, unsigned int *, __int64, __int64))(*(_QWORD *)v5 + 168LL))(v5, &v18, a3, j);
        PrintMessage(0x467u, v18);
        return 3221745199LL;
      }
      if ( (v13 & 0x30u) > 0x10
        && (*(_QWORD *)(v4 + 632) != *(_QWORD *)(v4 + 656) || *(_QWORD *)(v4 + 640) != *(_QWORD *)(v4 + 664)) )
      {
LABEL_37:
        (*(void (__fastcall **)(__int64, unsigned int *, __int64, __int64))(*(_QWORD *)v5 + 168LL))(v5, &v18, a3, j);
        PrintMessage(0x468u, v18);
        return 3221745199LL;
      }
      for ( i = (__int64 *)*v6; v6 != i; i = (__int64 *)*i )
      {
        if ( (*((_WORD *)i + 122) & 0x100) != 0 )
        {
          v16 = *((_BYTE *)i + 285);
          if ( (unsigned __int8)(v16 - 1) > 3u && (unsigned __int8)(v16 - 7) > 1u )
            goto LABEL_37;
        }
      }
    }
    if ( (*(_BYTE *)(v4 + 681) & 0x30) == 0x20 && (*(_BYTE *)(v4 + 681) & 2) == 0 && !(_BYTE)a3 )
    {
      (*(void (__fastcall **)(__int64, unsigned int *, __int64, __int64))(*(_QWORD *)v5 + 168LL))(v5, &v18, a3, j);
      PrintMessage(0x469u, v18);
      return 3221745200LL;
    }
    return 0;
  }
  ProcessHeap = GetProcessHeap();
  v11 = HeapAlloc(ProcessHeap, 8u, 4LL * v9);
  *(_QWORD *)(v4 + 40) = v11;
  if ( v11 )
  {
    v12 = (__int64 *)*v6;
    a3 = 0;
    for ( j = 0; ; j = (unsigned int)(j + 1) )
    {
      if ( v6 == v12 )
        goto LABEL_15;
      if ( (v12[44] & 0x40) != 0 )
      {
        if ( (v12[46] & 0x10) == 0 )
          goto LABEL_13;
      }
      else if ( (v12[46] & 0x10) == 0 )
      {
        break;
      }
      if ( (unsigned int)a3 < *(_DWORD *)(v4 + 36) )
      {
        *(_DWORD *)(*(_QWORD *)(v4 + 40) + 4 * a3) = j;
        a3 = (unsigned int)(a3 + 1);
      }
LABEL_13:
      v12 = (__int64 *)*v12;
    }
  }
  (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v5 + 168LL))(v5, &v18);
  PrintMessage(0x465u, v18);
  return 3221745196LL;
}

```

## disassembly

```asm
0x14003506c  mov     [rsp-18h+arg_8], rbx
0x140035071  mov     [rsp-18h+arg_10], rsi
0x140035076  push    rbp
0x140035077  push    rdi
0x140035078  push    r14
0x14003507a  mov     rbp, rsp
0x14003507d  sub     rsp, 30h
0x140035081  mov     rbx, [rcx+50h]
0x140035085  mov     [rbp+arg_0], 0
0x14003508c  test    rbx, rbx
0x14003508f  jz      loc_1400352E2
0x140035095  mov     rdi, [rcx+18h]
0x140035099  lea     rsi, [rbx+10h]
0x14003509d  mov     rax, [rsi]
0x1400350a0  cmp     rax, rsi
0x1400350a3  jnz     short loc_1400350D2
0x1400350a5  mov     rax, [rdi]
0x1400350a8  lea     rdx, [rbp+arg_0]
0x1400350ac  mov     rcx, rdi
0x1400350af  mov     rax, [rax+0A8h]
0x1400350b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400350bb  mov     edx, [rbp+arg_0]
0x1400350be  mov     ecx, 464h; unsigned int
0x1400350c3  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x1400350c8  mov     eax, 0C007EE10h
0x1400350cd  jmp     loc_1400352E4
0x1400350d2  mov     r14d, [rbx+24h]
0x1400350d6  test    r14d, r14d
0x1400350d9  jz      loc_1400351BD
0x1400350df  call    cs:__imp_GetProcessHeap
0x1400350e5  mov     r8d, r14d
0x1400350e8  mov     edx, 8; dwFlags
0x1400350ed  shl     r8, 2; dwBytes
0x1400350f1  mov     rcx, rax; hHeap
0x1400350f4  call    cs:__imp_HeapAlloc
0x1400350fa  mov     [rbx+28h], rax
0x1400350fe  test    rax, rax
0x140035101  jz      short loc_140035120
0x140035103  mov     rdx, [rsi]
0x140035106  xor     r8d, r8d
0x140035109  xor     r9d, r9d
0x14003510c  jmp     short loc_14003516D
0x14003510e  test    byte ptr [rdx+160h], 40h
0x140035115  jnz     short loc_14003514D
0x140035117  test    byte ptr [rdx+170h], 10h
0x14003511e  jnz     short loc_140035156
0x140035120  mov     rax, [rdi]
0x140035123  lea     rdx, [rbp+arg_0]
0x140035127  mov     rcx, rdi
0x14003512a  mov     rax, [rax+0A8h]
0x140035131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035136  mov     edx, [rbp+arg_0]
0x140035139  mov     ecx, 465h; unsigned int
0x14003513e  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140035143  mov     eax, 0C007EE2Ch
0x140035148  jmp     loc_1400352E4
0x14003514d  test    byte ptr [rdx+170h], 10h
0x140035154  jz      short loc_140035167
0x140035156  cmp     r8d, [rbx+24h]
0x14003515a  jnb     short loc_140035167
0x14003515c  mov     rax, [rbx+28h]
0x140035160  mov     [rax+r8*4], r9d
0x140035164  inc     r8d
0x140035167  mov     rdx, [rdx]
0x14003516a  inc     r9d
0x14003516d  cmp     rsi, rdx
0x140035170  jnz     short loc_14003510E
0x140035172  mov     r8b, [rbx+0D0h]
0x140035179  test    r8b, r8b
0x14003517c  jz      loc_140035280
0x140035182  mov     al, [rbx+2A9h]
0x140035188  test    al, 2
0x14003518a  jz      loc_140035226
0x140035190  mov     rax, [rdi]
0x140035193  lea     rdx, [rbp+arg_0]
0x140035197  mov     rcx, rdi
0x14003519a  mov     rax, [rax+0A8h]
0x1400351a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400351a6  mov     ecx, 467h; unsigned int
0x1400351ab  mov     edx, [rbp+arg_0]
0x1400351ae  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x1400351b3  mov     eax, 0C007EE2Fh
0x1400351b8  jmp     loc_1400352E4
0x1400351bd  test    byte ptr [rax+160h], 40h
0x1400351c4  mov     r14, [rax]
0x1400351c7  jz      short loc_1400351EC
0x1400351c9  movups  xmm0, xmmword ptr [rax+0B8h]
0x1400351d0  xor     r8d, r8d; unsigned __int8
0x1400351d3  lea     rdx, aSysRequestrate; "sys:RequestRate"
0x1400351da  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x1400351de  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x1400351e3  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x1400351e8  test    al, al
0x1400351ea  jz      short loc_1400351F9
0x1400351ec  mov     rax, r14
0x1400351ef  cmp     rsi, r14
0x1400351f2  jnz     short loc_1400351BD
0x1400351f4  jmp     loc_140035172
0x1400351f9  mov     rax, [rdi]
0x1400351fc  lea     rdx, [rbp+arg_0]
0x140035200  mov     rcx, rdi
0x140035203  mov     rax, [rax+0A8h]
0x14003520a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003520f  mov     edx, [rbp+arg_0]
0x140035212  mov     ecx, 466h; unsigned int
0x140035217  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x14003521c  mov     eax, 0C007EE2Eh
0x140035221  jmp     loc_1400352E4
0x140035226  and     al, 30h
0x140035228  cmp     al, 10h
0x14003522a  jbe     short loc_140035250
0x14003522c  mov     rax, [rbx+278h]
0x140035233  cmp     rax, [rbx+290h]
0x14003523a  jnz     loc_1400352C2
0x140035240  mov     rax, [rbx+280h]
0x140035247  cmp     rax, [rbx+298h]
0x14003524e  jnz     short loc_1400352C2
0x140035250  mov     rcx, [rsi]
0x140035253  jmp     short loc_14003527B
0x140035255  mov     eax, 100h
0x14003525a  test    [rcx+0F4h], ax
0x140035261  jz      short loc_140035278
0x140035263  mov     dl, [rcx+11Dh]
0x140035269  lea     eax, [rdx-1]
0x14003526c  cmp     al, 3
0x14003526e  jbe     short loc_140035278
0x140035270  sub     dl, 7
0x140035273  cmp     dl, 1
0x140035276  ja      short loc_1400352C2
0x140035278  mov     rcx, [rcx]
0x14003527b  cmp     rsi, rcx
0x14003527e  jnz     short loc_140035255
0x140035280  mov     cl, [rbx+2A9h]
0x140035286  mov     al, cl
0x140035288  and     al, 30h
0x14003528a  cmp     al, 20h ; ' '
0x14003528c  jnz     short loc_1400352E2
0x14003528e  test    cl, 2
0x140035291  jnz     short loc_1400352E2
0x140035293  test    r8b, r8b
0x140035296  jnz     short loc_1400352E2
0x140035298  mov     rax, [rdi]
0x14003529b  lea     rdx, [rbp+arg_0]
0x14003529f  mov     rcx, rdi
0x1400352a2  mov     rax, [rax+0A8h]
0x1400352a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400352ae  mov     edx, [rbp+arg_0]
0x1400352b1  mov     ecx, 469h; unsigned int
0x1400352b6  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x1400352bb  mov     eax, 0C007EE30h
0x1400352c0  jmp     short loc_1400352E4
0x1400352c2  mov     rax, [rdi]
0x1400352c5  lea     rdx, [rbp+arg_0]
0x1400352c9  mov     rcx, rdi
0x1400352cc  mov     rax, [rax+0A8h]
0x1400352d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400352d8  mov     ecx, 468h
0x1400352dd  jmp     loc_1400351AB
0x1400352e2  xor     eax, eax
0x1400352e4  mov     rbx, [rsp+30h+arg_8]
0x1400352e9  mov     rsi, [rsp+30h+arg_10]
0x1400352ee  add     rsp, 30h
0x1400352f2  pop     r14
0x1400352f4  pop     rdi
0x1400352f5  pop     rbp
0x1400352f6  retn
```
