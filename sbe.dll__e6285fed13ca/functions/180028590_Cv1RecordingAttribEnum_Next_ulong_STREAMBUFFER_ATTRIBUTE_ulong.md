# Cv1RecordingAttribEnum::Next(ulong,STREAMBUFFER_ATTRIBUTE *,ulong *)

- ea: `0x180028590`
- end: `0x180028837`
- name: `?Next@Cv1RecordingAttribEnum@@UEAAJKPEAUSTREAMBUFFER_ATTRIBUTE@@PEAK@Z`
- size: `679`
- prototype: `__int64 __fastcall(Cv1RecordingAttribEnum *__hidden this, unsigned int, struct STREAMBUFFER_ATTRIBUTE *, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x180001c00`
- `0x180028590`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18002880b`
- `KERNEL32!LeaveCriticalSection` at `0x18002880b`
- `KERNEL32!EnterCriticalSection` at `0x1800285d6`
- `KERNEL32!EnterCriticalSection` at `0x1800285d6`
- `ole32!CoTaskMemAlloc` at `0x1800286e6`
- `ole32!CoTaskMemAlloc` at `0x180028719`
- `ole32!CoTaskMemAlloc` at `0x1800286e6`
- `ole32!CoTaskMemAlloc` at `0x180028719`
- `ole32!CoTaskMemFree` at `0x1800287a7`
- `ole32!CoTaskMemFree` at `0x1800287c9`
- `ole32!CoTaskMemFree` at `0x1800287e4`
- `ole32!CoTaskMemFree` at `0x1800287a7`
- `ole32!CoTaskMemFree` at `0x1800287c9`
- `ole32!CoTaskMemFree` at `0x1800287e4`

## pseudocode

```c
__int64 __fastcall Cv1RecordingAttribEnum::Next(
        Cv1RecordingAttribEnum *this,
        unsigned int a2,
        struct STREAMBUFFER_ATTRIBUTE *a3,
        unsigned int *a4)
{
  int v8; // esi
  unsigned __int16 v9; // cx
  int v10; // ecx
  unsigned int *v11; // rdi
  __int16 v12; // cx
  __int64 v13; // rax
  SIZE_T cbLength; // rcx
  __int64 v15; // r9
  WORD *p_cbLength; // r10
  struct STREAMBUFFER_ATTRIBUTE *v17; // rdx
  __int64 v18; // rax
  int v20; // [rsp+50h] [rbp-20h] BYREF
  _WORD v21[2]; // [rsp+54h] [rbp-1Ch] BYREF
  _WORD v22[2]; // [rsp+58h] [rbp-18h] BYREF
  _WORD v23[2]; // [rsp+5Ch] [rbp-14h] BYREF

  v21[0] = 0;
  v22[0] = 0;
  v20 = 0;
  v23[0] = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _WORD *))(**((_QWORD **)this + 1) + 32LL))(
         *((_QWORD *)this + 1),
         0,
         v22);
  if ( v8 >= 0 )
  {
    v9 = v22[0];
    if ( v22[0] )
    {
      if ( a2 )
      {
        if ( a3 && (a4 || a2 == 1) )
        {
          v11 = (unsigned int *)&v20;
          if ( a4 )
            v11 = a4;
          *v11 = 0;
          if ( *((_WORD *)this + 8) >= v9 )
          {
            v8 = 1;
          }
          else
          {
            while ( *v11 < a2 )
            {
              a3[*v11].pszName = 0;
              a3[*v11].pbAttribute = 0;
              v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _WORD *, _QWORD, _WORD *, STREAMBUFFER_ATTR_DATATYPE *, _QWORD, WORD *))(**((_QWORD **)this + 1) + 48LL))(
                     *((_QWORD *)this + 1),
                     *((unsigned __int16 *)this + 8),
                     v23,
                     0,
                     v21,
                     &a3[*v11].StreamBufferAttributeType,
                     0,
                     &a3[*v11].cbLength);
              if ( v8 < 0 )
                break;
              v12 = v21[0];
              if ( v21[0] )
              {
                a3[*v11].pszName = (LPWSTR)CoTaskMemAlloc(2LL * v21[0]);
                v12 = v21[0];
              }
              v13 = *v11;
              if ( !a3[v13].pszName && v12 )
                goto LABEL_28;
              cbLength = a3[v13].cbLength;
              if ( (_WORD)cbLength )
                a3[*v11].pbAttribute = (BYTE *)CoTaskMemAlloc(cbLength);
              v15 = *v11;
              p_cbLength = &a3[v15].cbLength;
              v17 = &a3[v15];
              if ( *p_cbLength && !v17->pbAttribute )
              {
                CoTaskMemFree(a3[v15].pszName);
                a3[*v11].pszName = 0;
LABEL_28:
                v8 = -2147024882;
                break;
              }
              v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _WORD *, LPWSTR, _WORD *, STREAMBUFFER_ATTR_DATATYPE *, BYTE *, WORD *))(**((_QWORD **)this + 1) + 48LL))(
                     *((_QWORD *)this + 1),
                     *((unsigned __int16 *)this + 8),
                     v23,
                     a3[v15].pszName,
                     v21,
                     &a3[v15].StreamBufferAttributeType,
                     v17->pbAttribute,
                     p_cbLength);
              v18 = *v11;
              if ( v8 < 0 )
              {
                CoTaskMemFree(a3[v18].pszName);
                a3[*v11].pszName = 0;
                CoTaskMemFree(a3[*v11].pbAttribute);
                a3[*v11].pbAttribute = 0;
                break;
              }
              *v11 = v18 + 1;
              ++*((_WORD *)this + 8);
            }
          }
        }
        else
        {
          v8 = -2147467261;
        }
      }
      else if ( a4 )
      {
        if ( v22[0] <= *((_WORD *)this + 8) )
          v10 = 0;
        else
          v10 = v22[0] - *((unsigned __int16 *)this + 8);
        *a4 = v10;
      }
    }
    else
    {
      v8 = -2147467259;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180028590  mov     [rsp-38h+arg_8], rbx
0x180028595  push    rbp
0x180028596  push    rsi
0x180028597  push    rdi
0x180028598  push    r12
0x18002859a  push    r13
0x18002859c  push    r14
0x18002859e  push    r15
0x1800285a0  mov     rbp, rsp
0x1800285a3  sub     rsp, 70h
0x1800285a7  mov     rax, cs:__security_cookie
0x1800285ae  xor     rax, rsp
0x1800285b1  mov     [rbp+var_10], rax
0x1800285b5  xor     edi, edi
0x1800285b7  mov     r15, rcx
0x1800285ba  add     rcx, 18h; lpCriticalSection
0x1800285be  mov     [rbp+var_1C], di
0x1800285c2  mov     [rbp+var_18], di
0x1800285c6  mov     r14, r9
0x1800285c9  mov     [rbp+var_20], edi
0x1800285cc  mov     rbx, r8
0x1800285cf  mov     [rbp+var_14], di
0x1800285d3  mov     r12d, edx
0x1800285d6  call    cs:__imp_EnterCriticalSection
0x1800285dc  mov     rcx, [r15+8]
0x1800285e0  lea     r8, [rbp+var_18]
0x1800285e4  xor     edx, edx
0x1800285e6  mov     rax, [rcx]
0x1800285e9  mov     rax, [rax+20h]
0x1800285ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800285f2  mov     esi, eax
0x1800285f4  test    eax, eax
0x1800285f6  js      loc_180028807
0x1800285fc  movzx   ecx, [rbp+var_18]
0x180028600  test    cx, cx
0x180028603  jz      loc_180028802
0x180028609  test    r12d, r12d
0x18002860c  jnz     short loc_180028631
0x18002860e  test    r14, r14
0x180028611  jz      loc_180028807
0x180028617  cmp     cx, [r15+10h]
0x18002861c  jbe     short loc_180028627
0x18002861e  movzx   eax, word ptr [r15+10h]
0x180028623  sub     ecx, eax
0x180028625  jmp     short loc_180028629
0x180028627  mov     ecx, edi
0x180028629  mov     [r14], ecx
0x18002862c  jmp     loc_180028807
0x180028631  test    rbx, rbx
0x180028634  jz      loc_1800287FB
0x18002863a  mov     eax, 1
0x18002863f  test    r14, r14
0x180028642  jnz     short loc_18002864D
0x180028644  cmp     r12d, eax
0x180028647  jnz     loc_1800287FB
0x18002864d  test    r14, r14
0x180028650  lea     rdi, [rbp+var_20]
0x180028654  cmovnz  rdi, r14
0x180028658  xor     r14d, r14d
0x18002865b  mov     [rdi], r14d
0x18002865e  cmp     [r15+10h], cx
0x180028663  jnb     loc_1800287F7
0x180028669  cmp     [rdi], r12d
0x18002866c  jnb     loc_180028807
0x180028672  mov     eax, [rdi]
0x180028674  lea     rdx, [rbx+18h]
0x180028678  shl     rax, 5
0x18002867c  lea     r9, [rbx+8]
0x180028680  mov     [rax+rbx], r14
0x180028684  mov     eax, [rdi]
0x180028686  shl     rax, 5
0x18002868a  mov     [rax+rbx+10h], r14
0x18002868f  mov     rcx, [r15+8]
0x180028693  mov     r8d, [rdi]
0x180028696  shl     r8, 5
0x18002869a  add     rdx, r8
0x18002869d  add     r9, r8
0x1800286a0  mov     rax, [rcx]
0x1800286a3  lea     r8, [rbp+var_14]
0x1800286a7  mov     [rsp+70h+var_38], rdx
0x1800286ac  lea     rdx, [rbp+var_1C]
0x1800286b0  mov     [rsp+70h+var_40], r14
0x1800286b5  mov     [rsp+70h+var_48], r9
0x1800286ba  xor     r9d, r9d
0x1800286bd  mov     rax, [rax+30h]
0x1800286c1  mov     [rsp+70h+var_50], rdx
0x1800286c6  movzx   edx, word ptr [r15+10h]
0x1800286cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800286d0  mov     esi, eax
0x1800286d2  test    eax, eax
0x1800286d4  js      loc_180028807
0x1800286da  movzx   ecx, [rbp+var_1C]
0x1800286de  test    cx, cx
0x1800286e1  jz      short loc_1800286FA
0x1800286e3  add     rcx, rcx; cb
0x1800286e6  call    cs:__imp_CoTaskMemAlloc
0x1800286ec  mov     ecx, [rdi]
0x1800286ee  shl     rcx, 5
0x1800286f2  mov     [rcx+rbx], rax
0x1800286f6  movzx   ecx, [rbp+var_1C]
0x1800286fa  mov     eax, [rdi]
0x1800286fc  shl     rax, 5
0x180028700  cmp     [rax+rbx], r14
0x180028704  jnz     short loc_18002870F
0x180028706  test    cx, cx
0x180028709  jnz     loc_1800287B7
0x18002870f  movzx   ecx, word ptr [rax+rbx+18h]; cb
0x180028714  test    cx, cx
0x180028717  jz      short loc_18002872A
0x180028719  call    cs:__imp_CoTaskMemAlloc
0x18002871f  mov     ecx, [rdi]
0x180028721  shl     rcx, 5
0x180028725  mov     [rcx+rbx+10h], rax
0x18002872a  mov     r9d, [rdi]
0x18002872d  lea     r10, [rbx+18h]
0x180028731  shl     r9, 5
0x180028735  add     r10, r9
0x180028738  lea     rdx, [r9+rbx]
0x18002873c  cmp     [r10], r14w
0x180028740  jbe     short loc_180028748
0x180028742  cmp     [rdx+10h], r14
0x180028746  jz      short loc_1800287A3
0x180028748  mov     rdx, [rdx+10h]
0x18002874c  lea     r8, [rbx+8]
0x180028750  mov     rcx, [r15+8]
0x180028754  add     r8, r9
0x180028757  mov     r9, [r9+rbx]
0x18002875b  mov     [rsp+70h+var_38], r10
0x180028760  mov     [rsp+70h+var_40], rdx
0x180028765  lea     rdx, [rbp+var_1C]
0x180028769  mov     rax, [rcx]
0x18002876c  mov     [rsp+70h+var_48], r8
0x180028771  lea     r8, [rbp+var_14]
0x180028775  mov     [rsp+70h+var_50], rdx
0x18002877a  movzx   edx, word ptr [r15+10h]
0x18002877f  mov     rax, [rax+30h]
0x180028783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028788  mov     esi, eax
0x18002878a  mov     eax, [rdi]
0x18002878c  test    esi, esi
0x18002878e  js      short loc_1800287BE
0x180028790  inc     eax
0x180028792  mov     [rdi], eax
0x180028794  mov     eax, 1
0x180028799  add     [r15+10h], ax
0x18002879e  jmp     loc_180028669
0x1800287a3  mov     rcx, [r9+rbx]; pv
0x1800287a7  call    cs:__imp_CoTaskMemFree
0x1800287ad  mov     eax, [rdi]
0x1800287af  shl     rax, 5
0x1800287b3  mov     [rax+rbx], r14
0x1800287b7  mov     esi, 8007000Eh
0x1800287bc  jmp     short loc_180028807
0x1800287be  mov     rcx, rax
0x1800287c1  shl     rcx, 5
0x1800287c5  mov     rcx, [rcx+rbx]; pv
0x1800287c9  call    cs:__imp_CoTaskMemFree
0x1800287cf  mov     eax, [rdi]
0x1800287d1  shl     rax, 5
0x1800287d5  mov     [rax+rbx], r14
0x1800287d9  mov     ecx, [rdi]
0x1800287db  shl     rcx, 5
0x1800287df  mov     rcx, [rcx+rbx+10h]; pv
0x1800287e4  call    cs:__imp_CoTaskMemFree
0x1800287ea  mov     eax, [rdi]
0x1800287ec  shl     rax, 5
0x1800287f0  mov     [rax+rbx+10h], r14
0x1800287f5  jmp     short loc_180028807
0x1800287f7  mov     esi, eax
0x1800287f9  jmp     short loc_180028807
0x1800287fb  mov     esi, 80004003h
0x180028800  jmp     short loc_180028807
0x180028802  mov     esi, 80004005h
0x180028807  lea     rcx, [r15+18h]; lpCriticalSection
0x18002880b  call    cs:__imp_LeaveCriticalSection
0x180028811  mov     eax, esi
0x180028813  mov     rcx, [rbp+var_10]
0x180028817  xor     rcx, rsp; StackCookie
0x18002881a  call    __security_check_cookie
0x18002881f  mov     rbx, [rsp+70h+arg_8]
0x180028827  add     rsp, 70h
0x18002882b  pop     r15
0x18002882d  pop     r14
0x18002882f  pop     r13
0x180028831  pop     r12
0x180028833  pop     rdi
0x180028834  pop     rsi
0x180028835  pop     rbp
0x180028836  retn
```
