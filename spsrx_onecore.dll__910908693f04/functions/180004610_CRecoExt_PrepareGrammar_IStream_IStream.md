# CRecoExt::PrepareGrammar(IStream *,IStream *)

- ea: `0x180004610`
- end: `0x1800047fc`
- name: `?PrepareGrammar@CRecoExt@@UEAAJPEAUIStream@@0@Z`
- size: `492`
- prototype: `__int64 __fastcall(CRecoExt *__hidden this, struct IStream *, struct IStream *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002ec0`
- `0x180004610`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800046e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800046e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800047c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800047d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800047c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800047d5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRecoExt::PrepareGrammar(CRecoExt *this, struct IStream *a2, struct IStream *a3)
{
  int v6; // edi
  struct IStreamVtbl *lpVtbl; // rax
  unsigned __int64 v8; // rsi
  unsigned int v9; // ebx
  char *v10; // rax
  char *v11; // r15
  char *v12; // rbx
  __int64 v13; // r8
  unsigned int v15; // [rsp+30h] [rbp-20h] BYREF
  unsigned __int64 v16; // [rsp+38h] [rbp-18h] BYREF
  LPVOID pv[2]; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v18; // [rsp+98h] [rbp+48h] BYREF
  int v19; // [rsp+A8h] [rbp+58h] BYREF

  pv[0] = 0;
  v19 = 0;
  v15 = 0;
  if ( !a2 || !a3 )
    return (unsigned int)-2147024809;
  v6 = 0;
  if ( *((_QWORD *)this + 11) )
  {
    lpVtbl = a2->lpVtbl;
    pv[1] = 0;
    v16 = 0;
    v18 = 0;
    v6 = ((__int64 (__fastcall *)(struct IStream *, unsigned int *, __int64, _QWORD))lpVtbl->Read)(a2, &v18, 4, 0);
    if ( v6 >= 0 )
    {
      v8 = v18;
      if ( ((int (__fastcall *)(struct IStream *, _QWORD, __int64, unsigned __int64 *))a2->lpVtbl->Seek)(a2, 0, 2, &v16) < 0 )
        goto LABEL_9;
      if ( v16 < v8 || (unsigned int)v8 < 4 )
      {
        v6 = -2147201021;
      }
      else
      {
        v6 = ((__int64 (__fastcall *)(struct IStream *, __int64, _QWORD, unsigned __int64 *))a2->lpVtbl->Seek)(
               a2,
               4,
               0,
               &v16);
        if ( v6 >= 0 )
        {
LABEL_9:
          v9 = v8 + 4;
          v10 = (char *)CoTaskMemAlloc((int)v8 + 4);
          v11 = v10;
          if ( v10 )
          {
            memset_0(v10, 0, (int)v9);
            *(_DWORD *)v11 = 46;
            *((_DWORD *)v11 + 1) = v18;
            v6 = ((__int64 (__fastcall *)(struct IStream *, char *, _QWORD, _QWORD))a2->lpVtbl->Read)(
                   a2,
                   v11 + 8,
                   (unsigned int)(v8 - 4),
                   0);
            if ( v6 >= 0 )
            {
              v6 = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD, LPVOID *, int *))(**((_QWORD **)this + 11) + 32LL))(
                     *((_QWORD *)this + 11),
                     v11,
                     v9,
                     pv,
                     &v19);
              if ( v6 >= 0 )
              {
                v12 = (char *)pv[0];
                if ( pv[0] )
                  LODWORD(v8) = v19;
                else
                  v12 = v11 + 4;
                while ( (_DWORD)v8 )
                {
                  v13 = (unsigned int)v8;
                  if ( (unsigned int)v8 > 0x800000 )
                    v13 = 0x800000;
                  v6 = ((__int64 (__fastcall *)(struct IStream *, char *, __int64, unsigned int *))a3->lpVtbl->Write)(
                         a3,
                         v12,
                         v13,
                         &v15);
                  if ( !v15 )
                  {
                    v6 = -2147467259;
                    break;
                  }
                  if ( v6 < 0 )
                    break;
                  LODWORD(v8) = v8 - v15;
                  v12 += v15;
                }
              }
            }
            CoTaskMemFree(v11);
          }
          else
          {
            v6 = -2147024882;
          }
        }
      }
    }
    if ( pv[0] )
      CoTaskMemFree(pv[0]);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180004610  mov     [rsp-38h+arg_0], rbx
0x180004615  push    rbp
0x180004616  push    rsi
0x180004617  push    rdi
0x180004618  push    r12
0x18000461a  push    r13
0x18000461c  push    r14
0x18000461e  push    r15
0x180004620  mov     rbp, rsp
0x180004623  sub     rsp, 50h
0x180004627  xor     r15d, r15d
0x18000462a  mov     r12, r8
0x18000462d  mov     [rbp+pv], r15
0x180004631  mov     r14, rdx
0x180004634  mov     [rbp+arg_18], r15d
0x180004638  mov     r13, rcx
0x18000463b  mov     [rbp+var_20], r15d
0x18000463f  test    rdx, rdx
0x180004642  jz      loc_1800047DD
0x180004648  test    r8, r8
0x18000464b  jz      loc_1800047DD
0x180004651  mov     edi, r15d
0x180004654  cmp     [rcx+58h], r15
0x180004658  jz      loc_1800047E2
0x18000465e  mov     rax, [rdx]
0x180004661  lea     ebx, [r15+4]
0x180004665  xor     r9d, r9d
0x180004668  mov     [rbp+var_8], r15
0x18000466c  mov     r8d, ebx
0x18000466f  mov     [rbp+var_18], r15
0x180004673  lea     rdx, [rbp+arg_8]
0x180004677  mov     [rbp+arg_8], r15d
0x18000467b  mov     rax, [rax+18h]
0x18000467f  mov     rcx, r14
0x180004682  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004687  mov     edi, eax
0x180004689  test    eax, eax
0x18000468b  js      loc_1800047CC
0x180004691  mov     rax, [r14]
0x180004694  lea     r9, [rbp+var_18]
0x180004698  mov     esi, [rbp+arg_8]
0x18000469b  lea     r8d, [r15+2]
0x18000469f  mov     edx, r15d
0x1800046a2  mov     rcx, r14
0x1800046a5  mov     rax, [rax+28h]
0x1800046a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046ae  test    eax, eax
0x1800046b0  js      short loc_1800046DE
0x1800046b2  cmp     [rbp+var_18], rsi
0x1800046b6  jb      short loc_1800046FF
0x1800046b8  cmp     esi, ebx
0x1800046ba  jb      short loc_1800046FF
0x1800046bc  mov     rax, [r14]
0x1800046bf  lea     r9, [rbp+var_18]
0x1800046c3  xor     r8d, r8d
0x1800046c6  mov     edx, ebx
0x1800046c8  mov     rcx, r14
0x1800046cb  mov     rax, [rax+28h]
0x1800046cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046d4  mov     edi, eax
0x1800046d6  test    eax, eax
0x1800046d8  js      loc_1800047CC
0x1800046de  lea     ebx, [rsi+4]
0x1800046e1  movsxd  rdi, ebx
0x1800046e4  mov     rcx, rdi; cb
0x1800046e7  call    cs:__imp_CoTaskMemAlloc
0x1800046ed  mov     r15, rax
0x1800046f0  test    rax, rax
0x1800046f3  jnz     short loc_180004709
0x1800046f5  mov     edi, 8007000Eh
0x1800046fa  jmp     loc_1800047CC
0x1800046ff  mov     edi, 80045003h
0x180004704  jmp     loc_1800047CC
0x180004709  mov     r8, rdi; Size
0x18000470c  xor     edx, edx; Val
0x18000470e  mov     rcx, r15; void *
0x180004711  call    memset_0
0x180004716  mov     dword ptr [r15], 2Eh ; '.'
0x18000471d  lea     r8d, [rsi-4]
0x180004721  mov     eax, [rbp+arg_8]
0x180004724  lea     rdx, [r15+8]
0x180004728  mov     [r15+4], eax
0x18000472c  xor     r9d, r9d
0x18000472f  mov     rax, [r14]
0x180004732  mov     rcx, r14
0x180004735  mov     rax, [rax+18h]
0x180004739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000473e  mov     edi, eax
0x180004740  test    eax, eax
0x180004742  js      short loc_1800047C3
0x180004744  mov     rcx, [r13+58h]
0x180004748  lea     rdx, [rbp+arg_18]
0x18000474c  mov     [rsp+50h+var_30], rdx
0x180004751  lea     r9, [rbp+pv]
0x180004755  mov     r8d, ebx
0x180004758  mov     rdx, r15
0x18000475b  mov     rax, [rcx]
0x18000475e  mov     rax, [rax+20h]
0x180004762  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004767  mov     edi, eax
0x180004769  test    eax, eax
0x18000476b  js      short loc_1800047C3
0x18000476d  mov     rbx, [rbp+pv]
0x180004771  test    rbx, rbx
0x180004774  jz      short loc_18000477B
0x180004776  mov     esi, [rbp+arg_18]
0x180004779  jmp     short loc_18000477F
0x18000477b  lea     rbx, [r15+4]
0x18000477f  mov     r14d, 800000h
0x180004785  test    esi, esi
0x180004787  jz      short loc_1800047C3
0x180004789  mov     rax, [r12]
0x18000478d  lea     r9, [rbp+var_20]
0x180004791  mov     r8d, esi
0x180004794  cmp     esi, r14d
0x180004797  mov     rdx, rbx
0x18000479a  mov     rcx, r12
0x18000479d  cmova   r8d, r14d
0x1800047a1  mov     rax, [rax+20h]
0x1800047a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047aa  mov     edi, eax
0x1800047ac  mov     eax, [rbp+var_20]
0x1800047af  test    eax, eax
0x1800047b1  jz      short loc_1800047BE
0x1800047b3  test    edi, edi
0x1800047b5  js      short loc_1800047C3
0x1800047b7  sub     esi, eax
0x1800047b9  add     rbx, rax
0x1800047bc  jmp     short loc_180004785
0x1800047be  mov     edi, 80004005h
0x1800047c3  mov     rcx, r15; pv
0x1800047c6  call    cs:__imp_CoTaskMemFree
0x1800047cc  mov     rcx, [rbp+pv]; pv
0x1800047d0  test    rcx, rcx
0x1800047d3  jz      short loc_1800047E2
0x1800047d5  call    cs:__imp_CoTaskMemFree
0x1800047db  jmp     short loc_1800047E2
0x1800047dd  mov     edi, 80070057h
0x1800047e2  mov     rbx, [rsp+50h+arg_0]
0x1800047ea  mov     eax, edi
0x1800047ec  add     rsp, 50h
0x1800047f0  pop     r15
0x1800047f2  pop     r14
0x1800047f4  pop     r13
0x1800047f6  pop     r12
0x1800047f8  pop     rdi
0x1800047f9  pop     rsi
0x1800047fa  pop     rbp
0x1800047fb  retn
```
