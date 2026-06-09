# ExcludeElementStart(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING_STACK *)

- ea: `0x140035880`
- end: `0x140035a0e`
- name: `?ExcludeElementStart@@YAKPEAU_XMRW_OPEN_CONTEXT@@PEAU_UNICODE_STRING_STACK@@@Z`
- size: `398`
- prototype: `__int64 __fastcall(struct _XMRW_OPEN_CONTEXT *, struct _UNICODE_STRING_STACK *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x140032dcc`

## callees

- `0x1400020f0`
- `0x140002730`
- `0x140016808`
- `0x14003579c`
- `0x140035880`
- `0x140041010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400359b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400359b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400359a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400359a4`

## pseudocode

```c
__int64 __fastcall ExcludeElementStart(struct _XMRW_OPEN_CONTEXT *a1, struct _UNICODE_STRING_STACK *a2)
{
  struct _TRACERPT_COUNTER_TABLE *v2; // r15
  __int64 v4; // r14
  char *v5; // rax
  struct _TRACERPT_EXCLUSIVE_COUNTER *v6; // rbx
  unsigned int v7; // esi
  int v8; // eax
  void *v9; // rdi
  HANDLE ProcessHeap; // rax
  struct _TRACERPT_COUNTER_TABLE **v12; // rcx
  struct _UNICODE_STRING v13; // [rsp+20h] [rbp-20h] BYREF
  struct _UNICODE_STRING v14; // [rsp+30h] [rbp-10h] BYREF
  int v15; // [rsp+70h] [rbp+30h] BYREF
  WCHAR *v16; // [rsp+80h] [rbp+40h] BYREF

  v2 = (struct _TRACERPT_COUNTER_TABLE *)*((_QWORD *)a1 + 11);
  v16 = 0;
  v15 = 0;
  v13 = 0;
  if ( !v2 )
    return 0;
  if ( !a2 )
    return 0;
  if ( *((_DWORD *)a1 + 12) != 5 )
    return 0;
  v4 = *((_QWORD *)a1 + 3);
  v14 = *(struct _UNICODE_STRING *)((char *)a2 + 8);
  if ( !EqualString(&v14, L"CounterTable", 0) )
    return 0;
  v5 = (char *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v6 = (struct _TRACERPT_EXCLUSIVE_COUNTER *)v5;
  if ( v5 )
  {
    *((_DWORD *)v5 + 4) = 31678523;
    *((_QWORD *)v5 + 5) = 0;
    v5[48] = 0;
    *(_OWORD *)(v5 + 24) = 0;
    *((_WORD *)v5 + 28) = 0;
    while ( 1 )
    {
      v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 72LL))(v4);
      v7 = v8;
      if ( v8 )
        break;
      ++*((_DWORD *)a1 + 11);
      (*(void (__fastcall **)(__int64, WCHAR **, int *))(*(_QWORD *)v4 + 112LL))(v4, &v16, &v15);
      v13.Buffer = v16;
      v13.MaximumLength = 2 * v15;
      v13.Length = 2 * v15;
      v7 = ExcludeAttributesCheck(a1, &v13, v6, v2);
      if ( v7 )
        goto LABEL_10;
    }
    if ( v8 < 0 )
    {
LABEL_10:
      v9 = (void *)*((_QWORD *)v6 + 4);
      if ( v9 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v9);
      }
      operator delete(v6);
      return v7;
    }
    if ( (*((_BYTE *)v6 + 56) & 1) != 0 )
    {
      v12 = (struct _TRACERPT_COUNTER_TABLE **)*((_QWORD *)v2 + 3);
      if ( *v12 != (struct _TRACERPT_COUNTER_TABLE *)((char *)v2 + 16) )
        __fastfail(3u);
      *(_QWORD *)v6 = (char *)v2 + 16;
      *((_QWORD *)v6 + 1) = v12;
      *v12 = v6;
      *((_QWORD *)v2 + 3) = v6;
    }
    return 0;
  }
  return 8;
}

```

## disassembly

```asm
0x140035880  mov     [rsp-28h+arg_8], rbx
0x140035885  mov     [rsp-28h+arg_18], rsi
0x14003588a  push    rbp
0x14003588b  push    rdi
0x14003588c  push    r12
0x14003588e  push    r14
0x140035890  push    r15
0x140035892  mov     rbp, rsp
0x140035895  sub     rsp, 40h
0x140035899  mov     r15, [rcx+58h]
0x14003589d  xorps   xmm0, xmm0
0x1400358a0  mov     [rbp+arg_10], 0
0x1400358a8  mov     rdi, rcx
0x1400358ab  mov     [rbp+arg_0], 0
0x1400358b2  movups  xmmword ptr [rbp+var_20.Length], xmm0
0x1400358b6  test    r15, r15
0x1400358b9  jz      loc_1400359EC
0x1400358bf  test    rdx, rdx
0x1400358c2  jz      loc_1400359EC
0x1400358c8  cmp     dword ptr [rcx+30h], 5
0x1400358cc  jnz     loc_1400359EC
0x1400358d2  movups  xmm0, xmmword ptr [rdx+8]
0x1400358d6  mov     r14, [rcx+18h]
0x1400358da  lea     rdx, aCountertable; "CounterTable"
0x1400358e1  xor     r8d, r8d; unsigned __int8
0x1400358e4  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x1400358e8  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x1400358ed  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x1400358f2  test    al, al
0x1400358f4  jz      loc_1400359EC
0x1400358fa  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140035901  mov     ecx, 40h ; '@'; unsigned __int64
0x140035906  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14003590b  mov     rbx, rax
0x14003590e  test    rax, rax
0x140035911  jz      loc_140035A07
0x140035917  mov     dword ptr [rax+10h], 1E3603Bh
0x14003591e  xorps   xmm0, xmm0
0x140035921  mov     qword ptr [rax+28h], 0
0x140035929  mov     byte ptr [rax+30h], 0
0x14003592d  movups  xmmword ptr [rax+18h], xmm0
0x140035931  xor     eax, eax
0x140035933  mov     [rbx+38h], ax
0x140035937  jmp     short loc_140035982
0x140035939  inc     dword ptr [rdi+2Ch]
0x14003593c  lea     r8, [rbp+arg_0]
0x140035940  mov     rax, [r14]
0x140035943  lea     rdx, [rbp+arg_10]
0x140035947  mov     rcx, r14
0x14003594a  mov     rax, [rax+70h]
0x14003594e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035953  mov     rax, [rbp+arg_10]
0x140035957  lea     rdx, [rbp+var_20]; struct _UNICODE_STRING *
0x14003595b  mov     [rbp+var_20.Buffer], rax
0x14003595f  mov     r9, r15; struct _TRACERPT_COUNTER_TABLE *
0x140035962  movzx   eax, word ptr [rbp+arg_0]
0x140035966  mov     r8, rbx; struct _TRACERPT_EXCLUSIVE_COUNTER *
0x140035969  add     ax, ax
0x14003596c  mov     rcx, rdi; struct _XMRW_OPEN_CONTEXT *
0x14003596f  mov     [rbp+var_20.MaximumLength], ax
0x140035973  mov     [rbp+var_20.Length], ax
0x140035977  call    ?ExcludeAttributesCheck@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_EXCLUSIVE_COUNTER@@PEAU_TRACERPT_COUNTER_TABLE@@@Z; ExcludeAttributesCheck(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_EXCLUSIVE_COUNTER *,_TRACERPT_COUNTER_TABLE *)
0x14003597c  mov     esi, eax
0x14003597e  test    eax, eax
0x140035980  jnz     short loc_14003599B
0x140035982  mov     rax, [r14]
0x140035985  mov     rcx, r14
0x140035988  mov     rax, [rax+48h]
0x14003598c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035991  mov     esi, eax
0x140035993  test    eax, eax
0x140035995  jz      short loc_140035939
0x140035997  test    eax, eax
0x140035999  jns     short loc_1400359C4
0x14003599b  mov     rdi, [rbx+20h]
0x14003599f  test    rdi, rdi
0x1400359a2  jz      short loc_1400359B8
0x1400359a4  call    cs:__imp_GetProcessHeap
0x1400359aa  mov     r8, rdi; lpMem
0x1400359ad  xor     edx, edx; dwFlags
0x1400359af  mov     rcx, rax; hHeap
0x1400359b2  call    cs:__imp_HeapFree
0x1400359b8  mov     rcx, rbx; Block
0x1400359bb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400359c0  mov     eax, esi
0x1400359c2  jmp     short loc_1400359EE
0x1400359c4  test    byte ptr [rbx+38h], 1
0x1400359c8  jz      short loc_1400359EC
0x1400359ca  lea     rax, [r15+10h]
0x1400359ce  mov     rcx, [rax+8]
0x1400359d2  cmp     [rcx], rax
0x1400359d5  jz      short loc_1400359DE
0x1400359d7  mov     ecx, 3
0x1400359dc  int     29h; Win8: RtlFailFast(ecx)
0x1400359de  mov     [rbx], rax
0x1400359e1  mov     [rbx+8], rcx
0x1400359e5  mov     [rcx], rbx
0x1400359e8  mov     [rax+8], rbx
0x1400359ec  xor     eax, eax
0x1400359ee  lea     r11, [rsp+40h+var_s0]
0x1400359f3  mov     rbx, [r11+38h]
0x1400359f7  mov     rsi, [r11+48h]
0x1400359fb  mov     rsp, r11
0x1400359fe  pop     r15
0x140035a00  pop     r14
0x140035a02  pop     r12
0x140035a04  pop     rdi
0x140035a05  pop     rbp
0x140035a06  retn
0x140035a07  mov     eax, 8
0x140035a0c  jmp     short loc_1400359EE
```
