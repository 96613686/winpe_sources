# TSInitPrimaryCreds(_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,_TS_PRIMARY_CREDENTIAL * *)

- ea: `0x1800034b0`
- end: `0x180003826`
- name: `?TSInitPrimaryCreds@@YAJPEAU_UNICODE_STRING@@00PEAPEAU_TS_PRIMARY_CREDENTIAL@@@Z`
- size: `886`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _TS_PRIMARY_CREDENTIAL **)`
- caller_count: `5`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800029b0`
- `0x180012af0`
- `0x180013468`
- `0x1800147b0`
- `0x180016b38`

## callees

- `0x1800034b0`
- `0x180003830`
- `0x18000c1a4`
- `0x18001c63c`
- `0x18001d010`

## pseudocode

```c
__int64 __fastcall TSInitPrimaryCreds(
        struct _UNICODE_STRING *a1,
        struct _UNICODE_STRING *a2,
        struct _UNICODE_STRING *a3,
        struct _TS_PRIMARY_CREDENTIAL **a4)
{
  __int64 v8; // rbx
  int v9; // eax
  size_t v10; // rbp
  void *v11; // rsi
  unsigned __int64 v12; // rcx
  unsigned int v13; // edi
  int Length; // eax
  size_t v15; // rbp
  void *v16; // rsi
  USHORT v17; // dx
  __int16 v18; // si
  USHORT v19; // si
  void *v20; // rbp
  size_t MaximumLength; // r8
  void *v23; // rax
  void *v24; // rax
  void *v25; // rax
  void *v26; // rax

  if ( TSGlobalState == 1 )
  {
    v8 = ((__int64 (__fastcall *)(__int64))TSGlobalLsaFunctions->AllocatePrivateHeap)(232);
  }
  else
  {
    v23 = (void *)((__int64 (__fastcall *)(__int64))TSGlobalDllFunctions->AllocateHeap)(232);
    v8 = (__int64)v23;
    if ( v23 )
    {
      memset_0(v23, 0, 0xE8u);
      goto LABEL_4;
    }
  }
  if ( v8 )
  {
LABEL_4:
    if ( !a1 || !a1->Buffer )
    {
      v13 = 0;
      *(_QWORD *)(v8 + 32) = 0;
      *(_DWORD *)(v8 + 24) = 0;
LABEL_11:
      if ( !a2 || !a2->Buffer )
      {
        *(_QWORD *)(v8 + 16) = 0;
        *(_DWORD *)(v8 + 8) = 0;
        goto LABEL_18;
      }
      Length = a2->Length;
      if ( (unsigned __int16)Length > 0xFFFCu )
      {
        *(_QWORD *)(v8 + 16) = 0;
        v13 = -1073741562;
        goto LABEL_33;
      }
      v15 = (unsigned int)(Length + 2);
      if ( TSGlobalState == 1 )
      {
        v16 = (void *)((__int64 (__fastcall *)(_QWORD))TSGlobalLsaFunctions->AllocatePrivateHeap)((unsigned int)v15);
      }
      else
      {
        v25 = (void *)((__int64 (__fastcall *)(_QWORD))TSGlobalDllFunctions->AllocateHeap)((unsigned int)v15);
        v16 = v25;
        if ( v25 )
        {
          memset_0(v25, 0, v15);
          *(_QWORD *)(v8 + 16) = v16;
          goto LABEL_17;
        }
      }
      *(_QWORD *)(v8 + 16) = v16;
      if ( v16 )
      {
LABEL_17:
        *(_WORD *)(v8 + 8) = a2->Length;
        *(_WORD *)(v8 + 10) = v15;
        memcpy_0(v16, a2->Buffer, a2->Length);
        *(_WORD *)(*(_QWORD *)(v8 + 16) + 2 * ((unsigned __int64)a2->Length >> 1)) = 0;
LABEL_18:
        if ( !a3->Buffer || (*(_QWORD *)(v8 + 48) = 0, *(_DWORD *)(v8 + 40) = 0, !a3->Buffer) )
        {
LABEL_30:
          *(_DWORD *)v8 = 1;
          *a4 = (struct _TS_PRIMARY_CREDENTIAL *)v8;
          return v13;
        }
        v17 = a3->Length;
        v18 = 0;
        if ( (a3->Length & 7) != 0 )
          v18 = 8 - (a3->Length & 7);
        if ( v17 > 0xFFF4u || (v19 = v17 + v18, v19 < v17) )
        {
          v13 = -1073741717;
        }
        else
        {
          if ( TSGlobalState == 1 )
          {
            v20 = (void *)((__int64 (__fastcall *)(_QWORD))TSGlobalLsaFunctions->AllocatePrivateHeap)(v19);
          }
          else
          {
            v26 = (void *)((__int64 (__fastcall *)(_QWORD))TSGlobalDllFunctions->AllocateHeap)(v19);
            v20 = v26;
            if ( v26 )
            {
              memset_0(v26, 0, v19);
              *(_QWORD *)(v8 + 48) = v20;
              goto LABEL_27;
            }
          }
          *(_QWORD *)(v8 + 48) = v20;
          if ( v20 )
          {
LABEL_27:
            *(_WORD *)(v8 + 40) = a3->Length;
            *(_WORD *)(v8 + 42) = v19;
            if ( v19 == a3->MaximumLength )
              MaximumLength = a3->MaximumLength;
            else
              MaximumLength = a3->Length;
            memcpy_0(v20, a3->Buffer, MaximumLength);
            goto LABEL_30;
          }
          v13 = -1073741801;
        }
LABEL_33:
        TSFreePrimaryCredentials((struct _TS_PRIMARY_CREDENTIAL *)v8);
        return v13;
      }
LABEL_47:
      v13 = -1073741670;
      goto LABEL_33;
    }
    v9 = a1->Length;
    if ( (unsigned __int16)v9 > 0xFFFCu )
    {
      *(_QWORD *)(v8 + 32) = 0;
      v13 = -1073741562;
      goto LABEL_33;
    }
    v10 = (unsigned int)(v9 + 2);
    if ( TSGlobalState == 1 )
    {
      v11 = (void *)((__int64 (__fastcall *)(_QWORD))TSGlobalLsaFunctions->AllocatePrivateHeap)((unsigned int)v10);
    }
    else
    {
      v24 = (void *)((__int64 (__fastcall *)(_QWORD))TSGlobalDllFunctions->AllocateHeap)((unsigned int)v10);
      v11 = v24;
      if ( v24 )
      {
        memset_0(v24, 0, v10);
        *(_QWORD *)(v8 + 32) = v11;
LABEL_10:
        *(_WORD *)(v8 + 24) = a1->Length;
        *(_WORD *)(v8 + 26) = v10;
        memcpy_0(v11, a1->Buffer, a1->Length);
        v12 = (unsigned __int64)a1->Length >> 1;
        v13 = 0;
        *(_WORD *)(*(_QWORD *)(v8 + 32) + 2 * v12) = 0;
        goto LABEL_11;
      }
    }
    *(_QWORD *)(v8 + 32) = v11;
    if ( !v11 )
      goto LABEL_47;
    goto LABEL_10;
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x1800034b0  push    rbx
0x1800034b2  push    rdi
0x1800034b3  push    r12
0x1800034b5  push    r14
0x1800034b7  push    r15
0x1800034b9  sub     rsp, 20h
0x1800034bd  cmp     cs:?TSGlobalState@@3W4_TS_STATE@@A, 1; _TS_STATE TSGlobalState
0x1800034c4  mov     r12, r9
0x1800034c7  mov     r14, r8
0x1800034ca  mov     r15, rdx
0x1800034cd  mov     rdi, rcx
0x1800034d0  jnz     loc_18000371F
0x1800034d6  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x1800034dd  mov     ecx, 0E8h
0x1800034e2  mov     rax, [rax+180h]
0x1800034e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034ee  mov     rbx, rax
0x1800034f1  test    rbx, rbx
0x1800034f4  jz      loc_1800037EC
0x1800034fa  mov     [rsp+48h+arg_0], rbp
0x1800034ff  mov     [rsp+48h+arg_8], rsi
0x180003504  mov     [rsp+48h+arg_10], r13
0x180003509  mov     r13d, 0FFFCh
0x18000350f  test    rdi, rdi
0x180003512  jz      loc_1800036FA
0x180003518  cmp     qword ptr [rdi+8], 0
0x18000351d  jz      loc_1800036FA
0x180003523  movzx   eax, word ptr [rdi]
0x180003526  cmp     ax, r13w
0x18000352a  ja      loc_1800037F6
0x180003530  cmp     cs:?TSGlobalState@@3W4_TS_STATE@@A, 1; _TS_STATE TSGlobalState
0x180003537  lea     ebp, [rax+2]
0x18000353a  jnz     loc_180003754
0x180003540  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x180003547  mov     ecx, ebp
0x180003549  mov     rax, [rax+180h]
0x180003550  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003555  mov     rsi, rax
0x180003558  mov     [rbx+20h], rsi
0x18000355c  test    rsi, rsi
0x18000355f  jz      loc_180003806
0x180003565  movzx   eax, word ptr [rdi]
0x180003568  mov     rcx, rsi; void *
0x18000356b  mov     [rbx+18h], ax
0x18000356f  mov     [rbx+1Ah], bp
0x180003573  movzx   r8d, word ptr [rdi]; Size
0x180003577  mov     rdx, [rdi+8]; Src
0x18000357b  call    memcpy_0
0x180003580  movzx   ecx, word ptr [rdi]
0x180003583  mov     rax, [rbx+20h]
0x180003587  shr     rcx, 1
0x18000358a  xor     edi, edi
0x18000358c  mov     [rax+rcx*2], di
0x180003590  test    r15, r15
0x180003593  jz      loc_180003708
0x180003599  cmp     qword ptr [r15+8], 0
0x18000359e  jz      loc_180003708
0x1800035a4  movzx   eax, word ptr [r15]
0x1800035a8  cmp     ax, r13w
0x1800035ac  ja      loc_180003810
0x1800035b2  cmp     cs:?TSGlobalState@@3W4_TS_STATE@@A, 1; _TS_STATE TSGlobalState
0x1800035b9  lea     ebp, [rax+2]
0x1800035bc  jnz     loc_180003787
0x1800035c2  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x1800035c9  mov     ecx, ebp
0x1800035cb  mov     rax, [rax+180h]
0x1800035d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035d7  mov     rsi, rax
0x1800035da  mov     [rbx+10h], rsi
0x1800035de  test    rsi, rsi
0x1800035e1  jz      loc_180003806
0x1800035e7  movzx   eax, word ptr [r15]
0x1800035eb  mov     rcx, rsi; void *
0x1800035ee  mov     [rbx+8], ax
0x1800035f2  mov     [rbx+0Ah], bp
0x1800035f6  movzx   r8d, word ptr [r15]; Size
0x1800035fa  mov     rdx, [r15+8]; Src
0x1800035fe  call    memcpy_0
0x180003603  movzx   ecx, word ptr [r15]
0x180003607  mov     rax, [rbx+10h]
0x18000360b  shr     rcx, 1
0x18000360e  mov     [rax+rcx*2], di
0x180003612  cmp     qword ptr [r14+8], 0
0x180003617  jz      loc_1800036C3
0x18000361d  mov     [rbx+30h], rdi
0x180003621  mov     dword ptr [rbx+28h], 0
0x180003628  cmp     qword ptr [r14+8], 0
0x18000362d  jz      loc_1800036C3
0x180003633  movzx   edx, word ptr [r14]
0x180003637  mov     ecx, 8
0x18000363c  movzx   eax, dx
0x18000363f  mov     esi, edi
0x180003641  and     ax, 7
0x180003645  sub     cx, ax
0x180003648  mov     eax, 0FFF4h
0x18000364d  cmp     cx, 8
0x180003651  cmovnz  si, cx
0x180003655  cmp     dx, ax
0x180003658  ja      loc_1800036EB
0x18000365e  add     si, dx
0x180003661  cmp     si, dx
0x180003664  jb      loc_1800036EB
0x18000366a  cmp     cs:?TSGlobalState@@3W4_TS_STATE@@A, 1; _TS_STATE TSGlobalState
0x180003671  movzx   ecx, si
0x180003674  jnz     loc_1800037BA
0x18000367a  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x180003681  mov     rax, [rax+180h]
0x180003688  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000368d  mov     rbp, rax
0x180003690  mov     [rbx+30h], rbp
0x180003694  test    rbp, rbp
0x180003697  jz      short loc_180003718
0x180003699  movzx   eax, word ptr [r14]
0x18000369d  mov     rcx, rbp; void *
0x1800036a0  mov     [rbx+28h], ax
0x1800036a4  mov     [rbx+2Ah], si
0x1800036a8  movzx   eax, word ptr [r14+2]
0x1800036ad  mov     rdx, [r14+8]; Src
0x1800036b1  cmp     si, ax
0x1800036b4  jz      loc_18000381E
0x1800036ba  movzx   r8d, word ptr [r14]; Size
0x1800036be  call    memcpy_0
0x1800036c3  mov     dword ptr [rbx], 1
0x1800036c9  mov     [r12], rbx
0x1800036cd  mov     rsi, [rsp+48h+arg_8]
0x1800036d2  mov     eax, edi
0x1800036d4  mov     rbp, [rsp+48h+arg_0]
0x1800036d9  mov     r13, [rsp+48h+arg_10]
0x1800036de  add     rsp, 20h
0x1800036e2  pop     r15
0x1800036e4  pop     r14
0x1800036e6  pop     r12
0x1800036e8  pop     rdi
0x1800036e9  pop     rbx
0x1800036ea  retn
0x1800036eb  mov     edi, 0C000006Bh
0x1800036f0  mov     rcx, rbx; struct _TS_PRIMARY_CREDENTIAL *
0x1800036f3  call    ?TSFreePrimaryCredentials@@YAJPEAU_TS_PRIMARY_CREDENTIAL@@@Z; TSFreePrimaryCredentials(_TS_PRIMARY_CREDENTIAL *)
0x1800036f8  jmp     short loc_1800036CD
0x1800036fa  xor     edi, edi
0x1800036fc  mov     [rbx+20h], rdi
0x180003700  mov     [rbx+18h], edi
0x180003703  jmp     loc_180003590
0x180003708  mov     [rbx+10h], rdi
0x18000370c  mov     dword ptr [rbx+8], 0
0x180003713  jmp     loc_180003612
0x180003718  mov     edi, 0C0000017h
0x18000371d  jmp     short loc_1800036F0
0x18000371f  mov     rax, cs:?TSGlobalDllFunctions@@3PEAU_SECPKG_DLL_FUNCTIONS@@EA; _SECPKG_DLL_FUNCTIONS * TSGlobalDllFunctions
0x180003726  mov     ecx, 0E8h
0x18000372b  mov     rax, [rax]
0x18000372e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003733  mov     rbx, rax
0x180003736  test    rax, rax
0x180003739  jz      loc_1800034F1
0x18000373f  xor     edx, edx; Val
0x180003741  mov     r8d, 0E8h; Size
0x180003747  mov     rcx, rax; void *
0x18000374a  call    memset_0
0x18000374f  jmp     loc_1800034FA
0x180003754  mov     rax, cs:?TSGlobalDllFunctions@@3PEAU_SECPKG_DLL_FUNCTIONS@@EA; _SECPKG_DLL_FUNCTIONS * TSGlobalDllFunctions
0x18000375b  mov     ecx, ebp
0x18000375d  mov     rax, [rax]
0x180003760  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003765  mov     rsi, rax
0x180003768  test    rax, rax
0x18000376b  jz      loc_180003558
0x180003771  mov     r8, rbp; Size
0x180003774  xor     edx, edx; Val
0x180003776  mov     rcx, rax; void *
0x180003779  call    memset_0
0x18000377e  mov     [rbx+20h], rsi
0x180003782  jmp     loc_180003565
0x180003787  mov     rax, cs:?TSGlobalDllFunctions@@3PEAU_SECPKG_DLL_FUNCTIONS@@EA; _SECPKG_DLL_FUNCTIONS * TSGlobalDllFunctions
0x18000378e  mov     ecx, ebp
0x180003790  mov     rax, [rax]
0x180003793  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003798  mov     rsi, rax
0x18000379b  test    rax, rax
0x18000379e  jz      loc_1800035DA
0x1800037a4  mov     r8, rbp; Size
0x1800037a7  xor     edx, edx; Val
0x1800037a9  mov     rcx, rax; void *
0x1800037ac  call    memset_0
0x1800037b1  mov     [rbx+10h], rsi
0x1800037b5  jmp     loc_1800035E7
0x1800037ba  mov     rax, cs:?TSGlobalDllFunctions@@3PEAU_SECPKG_DLL_FUNCTIONS@@EA; _SECPKG_DLL_FUNCTIONS * TSGlobalDllFunctions
0x1800037c1  mov     rax, [rax]
0x1800037c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037c9  mov     rbp, rax
0x1800037cc  test    rax, rax
0x1800037cf  jz      loc_180003690
0x1800037d5  movzx   r8d, si; Size
0x1800037d9  xor     edx, edx; Val
0x1800037db  mov     rcx, rax; void *
0x1800037de  call    memset_0
0x1800037e3  mov     [rbx+30h], rbp
0x1800037e7  jmp     loc_180003699
0x1800037ec  mov     eax, 0C000009Ah
0x1800037f1  jmp     loc_1800036DE
0x1800037f6  xor     edi, edi
0x1800037f8  mov     [rbx+20h], rdi
0x1800037fc  mov     edi, 0C0000106h
0x180003801  jmp     loc_1800036F0
0x180003806  mov     edi, 0C000009Ah
0x18000380b  jmp     loc_1800036F0
0x180003810  mov     [rbx+10h], rdi
0x180003814  mov     edi, 0C0000106h
0x180003819  jmp     loc_1800036F0
0x18000381e  mov     r8, rax
0x180003821  jmp     loc_1800036BE
```
