# CTask::HrAddPageToParsingStack(_GUID const *,_GUID const *,IXWizardPageEvent const *,IEnumXWizardPage const *,ulong,int,int)

- ea: `0x180020f0c`
- end: `0x18002115b`
- name: `?HrAddPageToParsingStack@CTask@@AEAAJPEBU_GUID@@0PEBUIXWizardPageEvent@@PEBUIEnumXWizardPage@@KHH@Z`
- size: `591`
- prototype: `__int64 __fastcall(CTask *__hidden this, const struct _GUID *, const struct _GUID *, const struct IXWizardPageEvent *, const struct IEnumXWizardPage *, unsigned int, int, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800207c0`
- `0x180020b3c`

## callees

- `0x180004370`
- `0x18000ae04`
- `0x180020f0c`
- `0x180024a8c`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800210d6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800210d6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020f47`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020f47`

## pseudocode

```c
__int64 __fastcall CTask::HrAddPageToParsingStack(
        HANDLE *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        const struct IXWizardPageEvent *a4,
        const struct IEnumXWizardPage *a5,
        unsigned int a6,
        int a7,
        int a8)
{
  HANDLE *v12; // r15
  struct _GUID *v13; // rax
  struct _GUID *v14; // rdi
  unsigned int v15; // r14d
  PVOID *v16; // rcx
  __int64 *v17; // rbx
  bool v18; // cl
  HANDLE v19; // rax
  __int64 v20; // rdi
  unsigned int v21; // eax
  unsigned int LastErrorHRESULT; // eax
  struct _GUID *v24; // [rsp+20h] [rbp-38h] BYREF
  HANDLE *v25; // [rsp+28h] [rbp-30h]

  v12 = this + 50;
  v25 = this + 50;
  v13 = (struct _GUID *)HeapAlloc(this[50], 8u, 0x40u);
  v14 = v13;
  v24 = v13;
  if ( v13 )
  {
    v15 = 0;
    if ( a2 )
      *v13 = *a2;
    if ( a3 )
      v13[1] = *a3;
    *(_QWORD *)v13[2].Data4 = a4;
    if ( a4 )
      (*(void (__fastcall **)(const struct IXWizardPageEvent *))(*(_QWORD *)a4 + 8LL))(a4);
    *(_QWORD *)&v14[2].Data1 = a5;
    if ( a5 )
      (*(void (__fastcall **)(const struct IEnumXWizardPage *))(*(_QWORD *)a5 + 8LL))(a5);
    v14[3].Data1 = a6;
    *(_DWORD *)v14[3].Data4 = a8;
    *(_DWORD *)&v14[3].Data2 = a7;
    try
    {
      v17 = (__int64 *)(this + 39);
      v18 = &v24 < this[40] && *v17 <= (unsigned __int64)&v24;
      v19 = this[41];
      if ( v18 )
      {
        v20 = *v17;
        if ( this[40] == v19 )
          std::vector<_GUID *>::_Reserve(this + 39);
        *(_QWORD *)this[40] = *((_QWORD *)this[39] + (((__int64)&v24 - v20) >> 3));
      }
      else
      {
        if ( this[40] == v19 )
          std::vector<_GUID *>::_Reserve(this + 39);
        *(_QWORD *)this[40] = v14;
      }
      this[40] = (char *)this[40] + 8;
      ++*((_DWORD *)this + 96);
      v21 = ++*((_DWORD *)this + 97);
      if ( v21 > *((_DWORD *)this + 98) )
        *((_DWORD *)this + 98) = v21;
    }
    catch ( std::bad_alloc )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          61,
          &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids,
          2147942414LL);
      v15 = -2147024882;
      v14 = v24;
      v12 = v25;
      goto LABEL_27;
    }
    goto LABEL_33;
  }
  v15 = -2147024882;
  v16 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids, 2147942414LL);
LABEL_27:
    v16 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !v14 )
    goto LABEL_34;
  if ( HeapFree(*v12, 0, v14) )
    goto LABEL_33;
  v16 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v15;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    LastErrorHRESULT = GetLastErrorHRESULT();
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      62,
      &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids,
      LastErrorHRESULT);
LABEL_33:
    v16 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_34:
  if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 0x10) != 0 )
    WPP_SF_d(v16[2], 63, &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids, v15);
  return v15;
}

```

## disassembly

```asm
0x180020f0c  mov     [rsp+arg_8], rbx
0x180020f11  mov     [rsp+arg_10], rsi
0x180020f16  push    rdi
0x180020f17  push    r12
0x180020f19  push    r13
0x180020f1b  push    r14
0x180020f1d  push    r15
0x180020f1f  sub     rsp, 30h
0x180020f23  mov     rbx, r9
0x180020f26  mov     r13, r8
0x180020f29  mov     r12, rdx
0x180020f2c  mov     rsi, rcx
0x180020f2f  lea     r15, [rcx+190h]
0x180020f36  mov     [rsp+58h+var_30], r15
0x180020f3b  mov     edx, 8; dwFlags
0x180020f40  lea     r8d, [rdx+38h]; dwBytes
0x180020f44  mov     rcx, [r15]; hHeap
0x180020f47  call    cs:__imp_HeapAlloc
0x180020f4d  mov     rdi, rax
0x180020f50  mov     [rsp+58h+var_38], rax
0x180020f55  test    rax, rax
0x180020f58  jnz     short loc_180020F9F
0x180020f5a  mov     r14d, 8007000Eh
0x180020f60  lea     rbx, WPP_GLOBAL_Control
0x180020f67  mov     rcx, cs:WPP_GLOBAL_Control
0x180020f6e  cmp     rcx, rbx
0x180020f71  jz      loc_1800210C9
0x180020f77  test    byte ptr [rcx+1Ch], 4
0x180020f7b  jz      loc_1800210C9
0x180020f81  lea     edx, [rax+3Ch]
0x180020f84  mov     r9d, 8007000Eh
0x180020f8a  lea     r8, WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids
0x180020f91  mov     rcx, [rcx+10h]
0x180020f95  call    WPP_SF_d
0x180020f9a  jmp     loc_1800210C2
0x180020f9f  xor     r14d, r14d
0x180020fa2  test    r12, r12
0x180020fa5  jz      short loc_180020FB0
0x180020fa7  movups  xmm0, xmmword ptr [r12]
0x180020fac  movdqu  xmmword ptr [rax], xmm0
0x180020fb0  test    r13, r13
0x180020fb3  jz      short loc_180020FBF
0x180020fb5  movups  xmm0, xmmword ptr [r13+0]
0x180020fba  movdqu  xmmword ptr [rax+10h], xmm0
0x180020fbf  mov     [rax+28h], rbx
0x180020fc3  test    rbx, rbx
0x180020fc6  jz      short loc_180020FD7
0x180020fc8  mov     rax, [rbx]
0x180020fcb  mov     rcx, rbx
0x180020fce  mov     rax, [rax+8]
0x180020fd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020fd7  mov     rcx, [rsp+58h+arg_20]
0x180020fdf  mov     [rdi+20h], rcx
0x180020fe3  test    rcx, rcx
0x180020fe6  jz      short loc_180020FF4
0x180020fe8  mov     rax, [rcx]
0x180020feb  mov     rax, [rax+8]
0x180020fef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ff4  mov     eax, [rsp+58h+arg_28]
0x180020ffb  mov     [rdi+30h], eax
0x180020ffe  mov     eax, [rsp+58h+arg_38]
0x180021005  mov     [rdi+38h], eax
0x180021008  mov     eax, [rsp+58h+arg_30]
0x18002100f  mov     [rdi+34h], eax
0x180021012  lea     rbx, [rsi+138h]
0x180021019  lea     rax, [rsp+58h+var_38]
0x18002101e  cmp     rax, [rbx+8]
0x180021022  jnb     short loc_180021032
0x180021024  lea     rax, [rsp+58h+var_38]
0x180021029  cmp     [rbx], rax
0x18002102c  ja      short loc_180021032
0x18002102e  mov     cl, 1
0x180021030  jmp     short loc_180021034
0x180021032  xor     cl, cl
0x180021034  mov     rax, [rbx+10h]
0x180021038  test    cl, cl
0x18002103a  jz      short loc_180021069
0x18002103c  mov     rdi, [rbx]
0x18002103f  cmp     [rbx+8], rax
0x180021043  jnz     short loc_18002104D
0x180021045  mov     rcx, rbx
0x180021048  call    ?_Reserve@?$vector@PEAU_GUID@@V?$allocator@PEAU_GUID@@@std@@@std@@IEAAX_K@Z; std::vector<_GUID *>::_Reserve(unsigned __int64)
0x18002104d  lea     rdx, [rsp+58h+var_38]
0x180021052  sub     rdx, rdi
0x180021055  sar     rdx, 3
0x180021059  mov     rax, [rbx]
0x18002105c  mov     rcx, [rbx+8]
0x180021060  mov     rax, [rax+rdx*8]
0x180021064  mov     [rcx], rax
0x180021067  jmp     short loc_18002107E
0x180021069  cmp     [rbx+8], rax
0x18002106d  jnz     short loc_180021077
0x18002106f  mov     rcx, rbx
0x180021072  call    ?_Reserve@?$vector@PEAU_GUID@@V?$allocator@PEAU_GUID@@@std@@@std@@IEAAX_K@Z; std::vector<_GUID *>::_Reserve(unsigned __int64)
0x180021077  mov     rax, [rbx+8]
0x18002107b  mov     [rax], rdi
0x18002107e  add     qword ptr [rbx+8], 8
0x180021083  inc     dword ptr [rsi+180h]
0x180021089  inc     dword ptr [rsi+184h]
0x18002108f  mov     eax, [rsi+184h]
0x180021095  cmp     eax, [rsi+188h]
0x18002109b  jbe     short loc_1800210A3
0x18002109d  mov     [rsi+188h], eax
0x1800210a3  lea     rbx, WPP_GLOBAL_Control
0x1800210aa  jmp     short loc_180021116
0x1800210ac  lea     rbx, WPP_GLOBAL_Control
0x1800210b3  mov     r14d, [rsp+58h+arg_0]
0x1800210b8  mov     rdi, [rsp+58h+var_38]
0x1800210bd  mov     r15, [rsp+58h+var_30]
0x1800210c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800210c9  test    rdi, rdi
0x1800210cc  jz      short loc_18002111D
0x1800210ce  mov     r8, rdi; lpMem
0x1800210d1  xor     edx, edx; dwFlags
0x1800210d3  mov     rcx, [r15]; hHeap
0x1800210d6  call    cs:__imp_HeapFree
0x1800210dc  test    eax, eax
0x1800210de  jnz     short loc_180021116
0x1800210e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800210e7  cmp     rcx, rbx
0x1800210ea  jz      short loc_180021140
0x1800210ec  test    byte ptr [rcx+1Ch], 4
0x1800210f0  jz      short loc_18002111D
0x1800210f2  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x1800210f7  mov     edx, 3Eh ; '>'
0x1800210fc  mov     r9d, eax
0x1800210ff  lea     r8, WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids
0x180021106  mov     rcx, cs:WPP_GLOBAL_Control
0x18002110d  mov     rcx, [rcx+10h]
0x180021111  call    WPP_SF_d
0x180021116  mov     rcx, cs:WPP_GLOBAL_Control
0x18002111d  cmp     rcx, rbx
0x180021120  jz      short loc_180021140
0x180021122  test    byte ptr [rcx+1Ch], 10h
0x180021126  jz      short loc_180021140
0x180021128  mov     edx, 3Fh ; '?'
0x18002112d  mov     r9d, r14d
0x180021130  lea     r8, WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids
0x180021137  mov     rcx, [rcx+10h]
0x18002113b  call    WPP_SF_d
0x180021140  mov     eax, r14d
0x180021143  mov     rbx, [rsp+58h+arg_8]
0x180021148  mov     rsi, [rsp+58h+arg_10]
0x18002114d  add     rsp, 30h
0x180021151  pop     r15
0x180021153  pop     r14
0x180021155  pop     r13
0x180021157  pop     r12
0x180021159  pop     rdi
0x18002115a  retn
```
