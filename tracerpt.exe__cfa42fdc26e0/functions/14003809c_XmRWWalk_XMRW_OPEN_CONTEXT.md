# XmRWWalk(_XMRW_OPEN_CONTEXT *)

- ea: `0x14003809c`
- end: `0x140038329`
- name: `?XmRWWalk@@YAKPEAU_XMRW_OPEN_CONTEXT@@@Z`
- size: `653`
- prototype: `unsigned int __fastcall(struct _XMRW_OPEN_CONTEXT *)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x140017398`
- `0x14002e418`
- `0x140035db4`

## callees

- `0x140016808`
- `0x140030910`
- `0x14003290c`
- `0x140032dcc`
- `0x14003694c`
- `0x14003809c`
- `0x140041010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400382d2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400382d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003825b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400382c4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003825b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400382c4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14003826d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14003826d`

## pseudocode

```c
unsigned int __fastcall XmRWWalk(struct _XMRW_OPEN_CONTEXT *a1)
{
  __int64 v1; // rsi
  unsigned int v3; // edi
  int v4; // ecx
  __int64 v5; // rdx
  bool v6; // zf
  __int64 v7; // rax
  int v8; // ecx
  __int64 *v9; // rdi
  __int64 v10; // rcx
  unsigned int result; // eax
  int v12; // edi
  struct _UNICODE_STRING_STACK *v13; // r8
  HANDLE v14; // rax
  _QWORD *v15; // rax
  __int64 v16; // xmm1_8
  _QWORD *v17; // rdi
  HANDLE ProcessHeap; // rax
  __int64 v19; // rcx
  __int128 v20; // [rsp+20h] [rbp-48h] BYREF
  struct _UNICODE_STRING v21; // [rsp+30h] [rbp-38h] BYREF
  __int128 v22; // [rsp+40h] [rbp-28h] BYREF
  __int64 v23; // [rsp+50h] [rbp-18h]
  int v24; // [rsp+90h] [rbp+28h] BYREF
  unsigned int v25; // [rsp+98h] [rbp+30h] BYREF
  unsigned int v26; // [rsp+A0h] [rbp+38h] BYREF
  __int64 v27; // [rsp+A8h] [rbp+40h] BYREF

  v1 = *((_QWORD *)a1 + 3);
  v25 = 0;
  v22 = 0;
  v23 = 0;
  v20 = 0;
  v27 = 0;
  v24 = 0;
  while ( 1 )
  {
    v3 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v1 + 48LL))(v1, &v25);
    if ( v3 )
      break;
    if ( v25 <= 0xF )
    {
      v4 = 32778;
      if ( _bittest(&v4, v25) )
      {
        if ( v25 == 3 )
        {
          (*(void (__fastcall **)(__int64, __int64 *, int *))(*(_QWORD *)v1 + 128LL))(v1, &v27, &v24);
          v5 = 0;
          *((_QWORD *)&v20 + 1) = v27;
          v6 = *((_QWORD *)a1 + 7) == 0;
          WORD1(v20) = 2 * v24;
          if ( !v6 )
            v5 = *((_QWORD *)a1 + 7);
          LOWORD(v20) = 2 * v24;
          if ( *((_BYTE *)a1 + 144) == (_BYTE)v3 )
          {
            v7 = *((_QWORD *)a1 + 8);
            if ( !v7 )
              goto LABEL_33;
            v8 = v3 + 3;
            v9 = (__int64 *)(v7 + 24);
          }
          else
          {
            v8 = 2;
            v9 = (__int64 *)((char *)a1 + 136);
          }
          if ( !v5 )
            goto LABEL_33;
          if ( v8 != *((_DWORD *)a1 + 12) )
            goto LABEL_33;
          v21 = *(struct _UNICODE_STRING *)(v5 + 8);
          if ( !EqualString(&v21, L"String", 0) )
            goto LABEL_33;
          v10 = *v9;
          if ( *v9 )
          {
            *(_BYTE *)(v10 + 96) |= 2u;
            *(_BYTE *)(v10 + 88) = 0;
            RPT_STRING::operator=(v10 + 56, (const void **)&v20);
LABEL_33:
            result = 0;
            goto LABEL_34;
          }
          result = -1073222126;
        }
        else
        {
          ++*((_DWORD *)a1 + 10);
          (*(void (__fastcall **)(__int64, __int64 *, int *))(*(_QWORD *)v1 + 112LL))(v1, &v27, &v24);
          v23 = v27;
          WORD5(v22) = 2 * v24;
          WORD4(v22) = 2 * v24;
          v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 160LL))(v1);
          if ( v25 != 1 )
          {
            if ( v25 != 15 )
              goto LABEL_33;
            result = ElementEnd(a1, (struct _UNICODE_STRING_STACK *)&v22);
            if ( result )
              return result;
            v17 = (_QWORD *)*((_QWORD *)a1 + 7);
            if ( v17 )
            {
              *((_QWORD *)a1 + 7) = *v17;
              ProcessHeap = GetProcessHeap();
              HeapFree(ProcessHeap, 0, v17);
            }
LABEL_32:
            --*((_DWORD *)a1 + 12);
            goto LABEL_33;
          }
          ++*((_DWORD *)a1 + 12);
          v13 = 0;
          if ( *((_QWORD *)a1 + 7) )
            v13 = (struct _UNICODE_STRING_STACK *)*((_QWORD *)a1 + 7);
          result = ElementStart(a1, (struct _UNICODE_STRING_STACK *)&v22, v13);
          if ( result )
            return result;
          if ( v12 )
          {
            result = ElementEnd(a1, (struct _UNICODE_STRING_STACK *)&v22);
            if ( result )
              goto LABEL_34;
            goto LABEL_32;
          }
          v14 = GetProcessHeap();
          v15 = HeapAlloc(v14, 8u, 0x18u);
          if ( v15 )
          {
            v16 = v23;
            *(_OWORD *)v15 = v22;
            v15[2] = v16;
            *v15 = *((_QWORD *)a1 + 7);
            *((_QWORD *)a1 + 7) = v15;
            goto LABEL_33;
          }
          result = 8;
        }
LABEL_34:
        if ( result )
          return result;
      }
    }
  }
  if ( v3 == 1 )
    return 0;
  v19 = *((_QWORD *)a1 + 3);
  v26 = 0;
  (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v19 + 168LL))(v19, &v26);
  PrintMessage(0x3E9u, v26, v3);
  return v3;
}

```

## disassembly

```asm
0x14003809c  push    rbp
0x14003809e  push    rbx
0x14003809f  push    rsi
0x1400380a0  push    rdi
0x1400380a1  mov     rbp, rsp
0x1400380a4  sub     rsp, 68h
0x1400380a8  mov     rsi, [rcx+18h]
0x1400380ac  xorps   xmm0, xmm0
0x1400380af  xor     eax, eax
0x1400380b1  mov     [rbp+arg_8], 0
0x1400380b8  movups  [rbp+var_28], xmm0
0x1400380bc  mov     [rbp+var_18], rax
0x1400380c0  mov     rbx, rcx
0x1400380c3  movups  [rbp+var_48], xmm0
0x1400380c7  mov     [rbp+arg_18], 0
0x1400380cf  mov     [rbp+arg_0], 0
0x1400380d6  mov     rax, [rsi]
0x1400380d9  lea     rdx, [rbp+arg_8]
0x1400380dd  mov     rcx, rsi
0x1400380e0  mov     rax, [rax+30h]
0x1400380e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400380e9  mov     edi, eax
0x1400380eb  test    eax, eax
0x1400380ed  jnz     loc_1400382E7
0x1400380f3  mov     eax, [rbp+arg_8]
0x1400380f6  cmp     eax, 0Fh
0x1400380f9  ja      short loc_1400380D6
0x1400380fb  mov     ecx, 800Ah
0x140038100  bt      ecx, eax
0x140038103  jnb     short loc_1400380D6
0x140038105  lea     r8, [rbp+arg_0]
0x140038109  mov     rcx, rsi
0x14003810c  lea     rdx, [rbp+arg_18]
0x140038110  cmp     eax, 3
0x140038113  jnz     loc_1400381D7
0x140038119  mov     rax, [rsi]
0x14003811c  mov     rax, [rax+80h]
0x140038123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038128  mov     rax, [rbp+arg_18]
0x14003812c  xor     edx, edx
0x14003812e  mov     qword ptr [rbp+var_48+8], rax
0x140038132  movzx   eax, word ptr [rbp+arg_0]
0x140038136  add     ax, ax
0x140038139  cmp     [rbx+38h], rdx
0x14003813d  mov     word ptr [rbp+var_48+2], ax
0x140038141  cmovnz  rdx, [rbx+38h]
0x140038146  mov     word ptr [rbp+var_48], ax
0x14003814a  cmp     [rbx+90h], dil
0x140038151  jnz     short loc_140038169
0x140038153  mov     rax, [rbx+40h]
0x140038157  test    rax, rax
0x14003815a  jz      loc_1400382DB
0x140038160  lea     ecx, [rdi+3]
0x140038163  lea     rdi, [rax+18h]
0x140038167  jmp     short loc_140038175
0x140038169  mov     ecx, 2
0x14003816e  lea     rdi, [rbx+88h]
0x140038175  test    rdx, rdx
0x140038178  jz      loc_1400382DB
0x14003817e  cmp     ecx, [rbx+30h]
0x140038181  jnz     loc_1400382DB
0x140038187  movups  xmm0, xmmword ptr [rdx+8]
0x14003818b  xor     r8d, r8d; unsigned __int8
0x14003818e  lea     rdx, aString_1; "String"
0x140038195  lea     rcx, [rbp+var_38]; struct _UNICODE_STRING
0x140038199  movdqu  xmmword ptr [rbp+var_38.Length], xmm0
0x14003819e  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x1400381a3  test    al, al
0x1400381a5  jz      loc_1400382DB
0x1400381ab  mov     rcx, [rdi]
0x1400381ae  test    rcx, rcx
0x1400381b1  jz      short loc_1400381CD
0x1400381b3  or      byte ptr [rcx+60h], 2
0x1400381b7  lea     rdx, [rbp+var_48]
0x1400381bb  mov     byte ptr [rcx+58h], 0
0x1400381bf  add     rcx, 38h ; '8'
0x1400381c3  call    ??4RPT_STRING@@QEAAPEBV0@AEAU_UNICODE_STRING@@@Z; RPT_STRING::operator=(_UNICODE_STRING &)
0x1400381c8  jmp     loc_1400382DB
0x1400381cd  mov     eax, 0C007EE12h
0x1400381d2  jmp     loc_1400382DD
0x1400381d7  inc     dword ptr [rbx+28h]
0x1400381da  mov     rax, [rsi]
0x1400381dd  mov     rax, [rax+70h]
0x1400381e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400381e6  mov     rax, [rbp+arg_18]
0x1400381ea  mov     rcx, rsi
0x1400381ed  mov     [rbp+var_18], rax
0x1400381f1  movzx   eax, word ptr [rbp+arg_0]
0x1400381f5  add     ax, ax
0x1400381f8  mov     word ptr [rbp+var_28+0Ah], ax
0x1400381fc  mov     word ptr [rbp+var_28+8], ax
0x140038200  mov     rax, [rsi]
0x140038203  mov     rax, [rax+0A0h]
0x14003820a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003820f  cmp     [rbp+arg_8], 1
0x140038213  mov     edi, eax
0x140038215  jnz     loc_14003829E
0x14003821b  inc     dword ptr [rbx+30h]
0x14003821e  lea     rdx, [rbp+var_28]; struct _UNICODE_STRING_STACK *
0x140038222  xor     r8d, r8d
0x140038225  mov     rcx, rbx; struct _XMRW_OPEN_CONTEXT *
0x140038228  cmp     [rbx+38h], r8
0x14003822c  cmovnz  r8, [rbx+38h]; struct _UNICODE_STRING_STACK *
0x140038231  call    ?ElementStart@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING_STACK@@PEAU2@@Z; ElementStart(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING_STACK &,_UNICODE_STRING_STACK *)
0x140038236  test    eax, eax
0x140038238  jnz     loc_140038320
0x14003823e  test    edi, edi
0x140038240  jz      short loc_14003825B
0x140038242  lea     rdx, [rbp+var_28]; struct _UNICODE_STRING_STACK *
0x140038246  mov     rcx, rbx; struct _XMRW_OPEN_CONTEXT *
0x140038249  call    ?ElementEnd@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING_STACK@@@Z; ElementEnd(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING_STACK &)
0x14003824e  test    eax, eax
0x140038250  jz      loc_1400382D8
0x140038256  jmp     loc_1400382DD
0x14003825b  call    cs:__imp_GetProcessHeap
0x140038261  mov     edx, 8; dwFlags
0x140038266  mov     rcx, rax; hHeap
0x140038269  lea     r8d, [rdx+10h]; dwBytes
0x14003826d  call    cs:__imp_HeapAlloc
0x140038273  mov     rcx, rax
0x140038276  test    rax, rax
0x140038279  jnz     short loc_140038280
0x14003827b  lea     eax, [rcx+8]
0x14003827e  jmp     short loc_1400382DD
0x140038280  movups  xmm0, [rbp+var_28]
0x140038284  movsd   xmm1, [rbp+var_18]
0x140038289  movups  xmmword ptr [rax], xmm0
0x14003828c  movsd   qword ptr [rax+10h], xmm1
0x140038291  mov     rax, [rbx+38h]
0x140038295  mov     [rcx], rax
0x140038298  mov     [rbx+38h], rcx
0x14003829c  jmp     short loc_1400382DB
0x14003829e  cmp     [rbp+arg_8], 0Fh
0x1400382a2  jnz     short loc_1400382DB
0x1400382a4  lea     rdx, [rbp+var_28]; struct _UNICODE_STRING_STACK *
0x1400382a8  mov     rcx, rbx; struct _XMRW_OPEN_CONTEXT *
0x1400382ab  call    ?ElementEnd@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING_STACK@@@Z; ElementEnd(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING_STACK &)
0x1400382b0  test    eax, eax
0x1400382b2  jnz     short loc_140038320
0x1400382b4  mov     rdi, [rbx+38h]
0x1400382b8  test    rdi, rdi
0x1400382bb  jz      short loc_1400382D8
0x1400382bd  mov     rax, [rdi]
0x1400382c0  mov     [rbx+38h], rax
0x1400382c4  call    cs:__imp_GetProcessHeap
0x1400382ca  mov     r8, rdi; lpMem
0x1400382cd  xor     edx, edx; dwFlags
0x1400382cf  mov     rcx, rax; hHeap
0x1400382d2  call    cs:__imp_HeapFree
0x1400382d8  dec     dword ptr [rbx+30h]
0x1400382db  xor     eax, eax
0x1400382dd  test    eax, eax
0x1400382df  jz      loc_1400380D6
0x1400382e5  jmp     short loc_140038320
0x1400382e7  cmp     edi, 1
0x1400382ea  jnz     short loc_1400382F0
0x1400382ec  xor     eax, eax
0x1400382ee  jmp     short loc_140038320
0x1400382f0  mov     rcx, [rbx+18h]
0x1400382f4  lea     rdx, [rbp+arg_10]
0x1400382f8  mov     [rbp+arg_10], 0
0x1400382ff  mov     rax, [rcx]
0x140038302  mov     rax, [rax+0A8h]
0x140038309  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003830e  mov     edx, [rbp+arg_10]
0x140038311  mov     r8d, edi
0x140038314  mov     ecx, 3E9h; unsigned int
0x140038319  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x14003831e  mov     eax, edi
0x140038320  add     rsp, 68h
0x140038324  pop     rdi
0x140038325  pop     rsi
0x140038326  pop     rbx
0x140038327  pop     rbp
0x140038328  retn
```
