# SBFThunk::Cv1RecAttributesEnum::Next(ulong,STREAMBUFFER_ATTRIBUTE *,ulong *)

- ea: `0x18004b850`
- end: `0x18004baf6`
- name: `?Next@Cv1RecAttributesEnum@SBFThunk@@UEAAJKPEAUSTREAMBUFFER_ATTRIBUTE@@PEAK@Z`
- size: `678`
- prototype: `__int64 __fastcall(SBFThunk::Cv1RecAttributesEnum *__hidden this, unsigned int, struct STREAMBUFFER_ATTRIBUTE *, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x180001c00`
- `0x18004b850`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18004baca`
- `KERNEL32!LeaveCriticalSection` at `0x18004baca`
- `KERNEL32!EnterCriticalSection` at `0x18004b895`
- `KERNEL32!EnterCriticalSection` at `0x18004b895`
- `ole32!CoTaskMemAlloc` at `0x18004b9a5`
- `ole32!CoTaskMemAlloc` at `0x18004b9d8`
- `ole32!CoTaskMemAlloc` at `0x18004b9a5`
- `ole32!CoTaskMemAlloc` at `0x18004b9d8`
- `ole32!CoTaskMemFree` at `0x18004ba66`
- `ole32!CoTaskMemFree` at `0x18004ba88`
- `ole32!CoTaskMemFree` at `0x18004baa3`
- `ole32!CoTaskMemFree` at `0x18004ba66`
- `ole32!CoTaskMemFree` at `0x18004ba88`
- `ole32!CoTaskMemFree` at `0x18004baa3`

## pseudocode

```c
__int64 __fastcall SBFThunk::Cv1RecAttributesEnum::Next(
        SBFThunk::Cv1RecAttributesEnum *this,
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
  int v23; // [rsp+5Ch] [rbp-14h] BYREF

  v21[0] = 0;
  v22[0] = 0;
  v20 = 0;
  v23 = 0;
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
              v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, int *, _QWORD, _WORD *, STREAMBUFFER_ATTR_DATATYPE *, _QWORD, WORD *))(**((_QWORD **)this + 1) + 48LL))(
                     *((_QWORD *)this + 1),
                     *((unsigned __int16 *)this + 8),
                     &v23,
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
              v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, int *, LPWSTR, _WORD *, STREAMBUFFER_ATTR_DATATYPE *, BYTE *, WORD *))(**((_QWORD **)this + 1) + 48LL))(
                     *((_QWORD *)this + 1),
                     *((unsigned __int16 *)this + 8),
                     &v23,
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
0x18004b850  mov     [rsp-38h+arg_8], rbx
0x18004b855  push    rbp
0x18004b856  push    rsi
0x18004b857  push    rdi
0x18004b858  push    r12
0x18004b85a  push    r13
0x18004b85c  push    r14
0x18004b85e  push    r15
0x18004b860  mov     rbp, rsp
0x18004b863  sub     rsp, 70h
0x18004b867  mov     rax, cs:__security_cookie
0x18004b86e  xor     rax, rsp
0x18004b871  mov     [rbp+var_10], rax
0x18004b875  xor     edi, edi
0x18004b877  mov     r15, rcx
0x18004b87a  add     rcx, 18h; lpCriticalSection
0x18004b87e  mov     [rbp+var_1C], di
0x18004b882  mov     [rbp+var_18], di
0x18004b886  mov     r14, r9
0x18004b889  mov     [rbp+var_20], edi
0x18004b88c  mov     rbx, r8
0x18004b88f  mov     [rbp+var_14], edi
0x18004b892  mov     r12d, edx
0x18004b895  call    cs:__imp_EnterCriticalSection
0x18004b89b  mov     rcx, [r15+8]
0x18004b89f  lea     r8, [rbp+var_18]
0x18004b8a3  xor     edx, edx
0x18004b8a5  mov     rax, [rcx]
0x18004b8a8  mov     rax, [rax+20h]
0x18004b8ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b8b1  mov     esi, eax
0x18004b8b3  test    eax, eax
0x18004b8b5  js      loc_18004BAC6
0x18004b8bb  movzx   ecx, [rbp+var_18]
0x18004b8bf  test    cx, cx
0x18004b8c2  jz      loc_18004BAC1
0x18004b8c8  test    r12d, r12d
0x18004b8cb  jnz     short loc_18004B8F0
0x18004b8cd  test    r14, r14
0x18004b8d0  jz      loc_18004BAC6
0x18004b8d6  cmp     cx, [r15+10h]
0x18004b8db  jbe     short loc_18004B8E6
0x18004b8dd  movzx   eax, word ptr [r15+10h]
0x18004b8e2  sub     ecx, eax
0x18004b8e4  jmp     short loc_18004B8E8
0x18004b8e6  mov     ecx, edi
0x18004b8e8  mov     [r14], ecx
0x18004b8eb  jmp     loc_18004BAC6
0x18004b8f0  test    rbx, rbx
0x18004b8f3  jz      loc_18004BABA
0x18004b8f9  mov     eax, 1
0x18004b8fe  test    r14, r14
0x18004b901  jnz     short loc_18004B90C
0x18004b903  cmp     r12d, eax
0x18004b906  jnz     loc_18004BABA
0x18004b90c  test    r14, r14
0x18004b90f  lea     rdi, [rbp+var_20]
0x18004b913  cmovnz  rdi, r14
0x18004b917  xor     r14d, r14d
0x18004b91a  mov     [rdi], r14d
0x18004b91d  cmp     [r15+10h], cx
0x18004b922  jnb     loc_18004BAB6
0x18004b928  cmp     [rdi], r12d
0x18004b92b  jnb     loc_18004BAC6
0x18004b931  mov     eax, [rdi]
0x18004b933  lea     rdx, [rbx+18h]
0x18004b937  shl     rax, 5
0x18004b93b  lea     r9, [rbx+8]
0x18004b93f  mov     [rax+rbx], r14
0x18004b943  mov     eax, [rdi]
0x18004b945  shl     rax, 5
0x18004b949  mov     [rax+rbx+10h], r14
0x18004b94e  mov     rcx, [r15+8]
0x18004b952  mov     r8d, [rdi]
0x18004b955  shl     r8, 5
0x18004b959  add     rdx, r8
0x18004b95c  add     r9, r8
0x18004b95f  mov     rax, [rcx]
0x18004b962  lea     r8, [rbp+var_14]
0x18004b966  mov     [rsp+70h+var_38], rdx
0x18004b96b  lea     rdx, [rbp+var_1C]
0x18004b96f  mov     [rsp+70h+var_40], r14
0x18004b974  mov     [rsp+70h+var_48], r9
0x18004b979  xor     r9d, r9d
0x18004b97c  mov     rax, [rax+30h]
0x18004b980  mov     [rsp+70h+var_50], rdx
0x18004b985  movzx   edx, word ptr [r15+10h]
0x18004b98a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b98f  mov     esi, eax
0x18004b991  test    eax, eax
0x18004b993  js      loc_18004BAC6
0x18004b999  movzx   ecx, [rbp+var_1C]
0x18004b99d  test    cx, cx
0x18004b9a0  jz      short loc_18004B9B9
0x18004b9a2  add     rcx, rcx; cb
0x18004b9a5  call    cs:__imp_CoTaskMemAlloc
0x18004b9ab  mov     ecx, [rdi]
0x18004b9ad  shl     rcx, 5
0x18004b9b1  mov     [rcx+rbx], rax
0x18004b9b5  movzx   ecx, [rbp+var_1C]
0x18004b9b9  mov     eax, [rdi]
0x18004b9bb  shl     rax, 5
0x18004b9bf  cmp     [rax+rbx], r14
0x18004b9c3  jnz     short loc_18004B9CE
0x18004b9c5  test    cx, cx
0x18004b9c8  jnz     loc_18004BA76
0x18004b9ce  movzx   ecx, word ptr [rax+rbx+18h]; cb
0x18004b9d3  test    cx, cx
0x18004b9d6  jz      short loc_18004B9E9
0x18004b9d8  call    cs:__imp_CoTaskMemAlloc
0x18004b9de  mov     ecx, [rdi]
0x18004b9e0  shl     rcx, 5
0x18004b9e4  mov     [rcx+rbx+10h], rax
0x18004b9e9  mov     r9d, [rdi]
0x18004b9ec  lea     r10, [rbx+18h]
0x18004b9f0  shl     r9, 5
0x18004b9f4  add     r10, r9
0x18004b9f7  lea     rdx, [r9+rbx]
0x18004b9fb  cmp     [r10], r14w
0x18004b9ff  jbe     short loc_18004BA07
0x18004ba01  cmp     [rdx+10h], r14
0x18004ba05  jz      short loc_18004BA62
0x18004ba07  mov     rdx, [rdx+10h]
0x18004ba0b  lea     r8, [rbx+8]
0x18004ba0f  mov     rcx, [r15+8]
0x18004ba13  add     r8, r9
0x18004ba16  mov     r9, [r9+rbx]
0x18004ba1a  mov     [rsp+70h+var_38], r10
0x18004ba1f  mov     [rsp+70h+var_40], rdx
0x18004ba24  lea     rdx, [rbp+var_1C]
0x18004ba28  mov     rax, [rcx]
0x18004ba2b  mov     [rsp+70h+var_48], r8
0x18004ba30  lea     r8, [rbp+var_14]
0x18004ba34  mov     [rsp+70h+var_50], rdx
0x18004ba39  movzx   edx, word ptr [r15+10h]
0x18004ba3e  mov     rax, [rax+30h]
0x18004ba42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ba47  mov     esi, eax
0x18004ba49  mov     eax, [rdi]
0x18004ba4b  test    esi, esi
0x18004ba4d  js      short loc_18004BA7D
0x18004ba4f  inc     eax
0x18004ba51  mov     [rdi], eax
0x18004ba53  mov     eax, 1
0x18004ba58  add     [r15+10h], ax
0x18004ba5d  jmp     loc_18004B928
0x18004ba62  mov     rcx, [r9+rbx]; pv
0x18004ba66  call    cs:__imp_CoTaskMemFree
0x18004ba6c  mov     eax, [rdi]
0x18004ba6e  shl     rax, 5
0x18004ba72  mov     [rax+rbx], r14
0x18004ba76  mov     esi, 8007000Eh
0x18004ba7b  jmp     short loc_18004BAC6
0x18004ba7d  mov     rcx, rax
0x18004ba80  shl     rcx, 5
0x18004ba84  mov     rcx, [rcx+rbx]; pv
0x18004ba88  call    cs:__imp_CoTaskMemFree
0x18004ba8e  mov     eax, [rdi]
0x18004ba90  shl     rax, 5
0x18004ba94  mov     [rax+rbx], r14
0x18004ba98  mov     ecx, [rdi]
0x18004ba9a  shl     rcx, 5
0x18004ba9e  mov     rcx, [rcx+rbx+10h]; pv
0x18004baa3  call    cs:__imp_CoTaskMemFree
0x18004baa9  mov     eax, [rdi]
0x18004baab  shl     rax, 5
0x18004baaf  mov     [rax+rbx+10h], r14
0x18004bab4  jmp     short loc_18004BAC6
0x18004bab6  mov     esi, eax
0x18004bab8  jmp     short loc_18004BAC6
0x18004baba  mov     esi, 80004003h
0x18004babf  jmp     short loc_18004BAC6
0x18004bac1  mov     esi, 80004005h
0x18004bac6  lea     rcx, [r15+18h]; lpCriticalSection
0x18004baca  call    cs:__imp_LeaveCriticalSection
0x18004bad0  mov     eax, esi
0x18004bad2  mov     rcx, [rbp+var_10]
0x18004bad6  xor     rcx, rsp; StackCookie
0x18004bad9  call    __security_check_cookie
0x18004bade  mov     rbx, [rsp+70h+arg_8]
0x18004bae6  add     rsp, 70h
0x18004baea  pop     r15
0x18004baec  pop     r14
0x18004baee  pop     r13
0x18004baf0  pop     r12
0x18004baf2  pop     rdi
0x18004baf3  pop     rsi
0x18004baf4  pop     rbp
0x18004baf5  retn
```
