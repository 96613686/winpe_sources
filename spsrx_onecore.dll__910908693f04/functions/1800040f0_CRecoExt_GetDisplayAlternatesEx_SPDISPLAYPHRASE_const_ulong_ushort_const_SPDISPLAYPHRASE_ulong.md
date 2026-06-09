# CRecoExt::GetDisplayAlternatesEx(SPDISPLAYPHRASE const *,ulong,ushort const *,SPDISPLAYPHRASE * *,ulong *)

- ea: `0x1800040f0`
- end: `0x18000433c`
- name: `?GetDisplayAlternatesEx@CRecoExt@@UEAAJPEBUSPDISPLAYPHRASE@@KPEBGPEAPEAU2@PEAK@Z`
- size: `588`
- prototype: `__int64 __fastcall(CRecoExt *this, const struct SPDISPLAYPHRASE *, unsigned int, const unsigned __int16 *, struct SPDISPLAYPHRASE **, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180001c50`
- `0x180002ec0`
- `0x1800031c8`
- `0x1800040f0`
- `0x180008938`
- `0x180008b08`
- `0x180010010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180004215`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180004215`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800041d4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800041d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800042a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004307`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000431c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800042a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004307`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000431c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRecoExt::GetDisplayAlternatesEx(
        CRecoExt *this,
        const struct SPDISPLAYPHRASE *a2,
        unsigned int a3,
        const unsigned __int16 *a4,
        struct SPDISPLAYPHRASE **a5,
        unsigned int *a6)
{
  unsigned int *v10; // rsi
  struct SPDISPLAYPHRASE **v11; // r12
  __int64 (__fastcall ***v12)(_QWORD, GUID *, char *); // rcx
  _QWORD *v13; // r15
  int v14; // edi
  __int64 v15; // rdi
  _DWORD *v16; // rax
  _DWORD *v17; // rbx
  unsigned int *v18; // rcx
  const struct SPSERIALIZEDDISPLAYPHRASE *v19; // r15
  __int64 v20; // r14
  int v21; // eax
  __int64 v22; // rax
  unsigned int i; // r14d
  __int64 v24; // rbx
  void *Src; // [rsp+30h] [rbp-28h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-20h] BYREF
  _QWORD *v28; // [rsp+40h] [rbp-18h]
  int v29; // [rsp+A8h] [rbp+50h] BYREF

  Src = 0;
  v10 = 0;
  if ( a2 )
  {
    v11 = a5;
    if ( a5 )
    {
      if ( a6 )
      {
        memset_0(a5, 0, 8LL * a3);
        v12 = (__int64 (__fastcall ***)(_QWORD, GUID *, char *))*((_QWORD *)this + 6);
        v13 = (_QWORD *)((char *)this + 112);
        v28 = (_QWORD *)((char *)this + 112);
        v14 = (**v12)(v12, &IID_ISpPrivateEngineCallEx, (char *)this + 112);
        if ( v14 >= 0 )
        {
          if ( !*v13 )
          {
LABEL_29:
            CoTaskMemFree(v10);
            return (unsigned int)v14;
          }
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v13 + 16LL))(*v13);
          v14 = SerializeDisplayPhrase(a2, (struct SPSERIALIZEDDISPLAYPHRASE **)&Src);
          if ( v14 >= 0 )
          {
            if ( !a4 )
            {
              v15 = 0;
              goto LABEL_9;
            }
            v22 = -1;
            do
              ++v22;
            while ( a4[v22] );
            v15 = v22 + 1;
            if ( (unsigned __int64)(v22 + 1) <= 0x80 )
            {
LABEL_9:
              v10 = (unsigned int *)Src;
              if ( g_heap
                && (LODWORD(Src) = *(_DWORD *)Src + 267, v16 = HeapAlloc(g_heap, 0, (int)Src), (v17 = v16) != 0) )
              {
                *v16 = 41;
                v16[1] = a3;
                memset_0(v16 + 2, 0, 0x100u);
                if ( v15 )
                  _o_wcsncpy_s(v17 + 2, 128, a4, v15);
                memcpy_0(v17 + 66, v10, *v10);
                pv = 0;
                v29 = 0;
                v14 = (*(__int64 (__fastcall **)(_QWORD, _DWORD *, _QWORD, LPVOID *, int *))(*(_QWORD *)*v28 + 32LL))(
                        *v28,
                        v17,
                        (unsigned int)Src,
                        &pv,
                        &v29);
                if ( v14 >= 0 )
                {
                  v18 = (unsigned int *)pv;
                  if ( pv )
                  {
                    v19 = (const struct SPSERIALIZEDDISPLAYPHRASE *)((char *)pv + 4);
                    v20 = 0;
                    do
                    {
                      if ( (unsigned int)v20 >= *v18 )
                        break;
                      v21 = DeserializeDisplayPhrase(v19, &v11[v20]);
                      v18 = (unsigned int *)pv;
                      v14 = v21;
                      v20 = (unsigned int)(v20 + 1);
                      v19 = (const struct SPSERIALIZEDDISPLAYPHRASE *)((char *)v19
                                                                     + ((*(unsigned int *)v19 + 7LL)
                                                                      & 0xFFFFFFFFFFFFFFF8uLL));
                    }
                    while ( v21 >= 0 );
                    *a6 = *v18;
                    CoTaskMemFree(v18);
                  }
                }
                CWinHeap::Free((CWinHeap *)&g_heap, v17);
                if ( v14 >= 0 )
                  goto LABEL_29;
              }
              else
              {
                v14 = -2147024882;
              }
              goto LABEL_27;
            }
            v14 = -2147024809;
          }
          v10 = (unsigned int *)Src;
        }
LABEL_27:
        for ( i = 0; i < a3; v11[v24] = 0 )
        {
          v24 = i;
          CoTaskMemFree(v11[i++]);
        }
        goto LABEL_29;
      }
    }
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800040f0  push    rbp
0x1800040f2  push    rbx
0x1800040f3  push    rsi
0x1800040f4  push    rdi
0x1800040f5  push    r12
0x1800040f7  push    r13
0x1800040f9  push    r14
0x1800040fb  push    r15
0x1800040fd  mov     rbp, rsp
0x180004100  sub     rsp, 58h
0x180004104  xor     eax, eax
0x180004106  mov     r13d, r8d
0x180004109  mov     [rbp+Src], rax
0x18000410d  mov     r14, r9
0x180004110  mov     rbx, rdx
0x180004113  mov     rdi, rcx
0x180004116  mov     esi, eax
0x180004118  test    rdx, rdx
0x18000411b  jz      loc_180004326
0x180004121  mov     r12, [rbp+arg_20]
0x180004125  test    r12, r12
0x180004128  jz      loc_180004326
0x18000412e  cmp     [rbp+arg_28], rax
0x180004132  jz      loc_180004326
0x180004138  mov     r8d, r13d
0x18000413b  xor     edx, edx; Val
0x18000413d  shl     r8, 3; Size
0x180004141  mov     rcx, r12; void *
0x180004144  call    memset_0
0x180004149  mov     rcx, [rdi+30h]
0x18000414d  lea     r15, [rdi+70h]
0x180004151  mov     r8, r15
0x180004154  mov     [rbp+var_18], r15
0x180004158  lea     rdx, IID_ISpPrivateEngineCallEx
0x18000415f  mov     rax, [rcx]
0x180004162  mov     rax, [rax]
0x180004165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000416a  mov     edi, eax
0x18000416c  test    eax, eax
0x18000416e  js      loc_1800042F5
0x180004174  mov     rcx, [r15]
0x180004177  xor     r15d, r15d
0x18000417a  test    rcx, rcx
0x18000417d  jz      loc_180004319
0x180004183  mov     rax, [rcx]
0x180004186  mov     rax, [rax+10h]
0x18000418a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000418f  lea     rdx, [rbp+Src]; struct SPSERIALIZEDDISPLAYPHRASE **
0x180004193  mov     rcx, rbx; struct SPDISPLAYPHRASE *
0x180004196  call    ?SerializeDisplayPhrase@@YAJPEBUSPDISPLAYPHRASE@@PEAPEAUSPSERIALIZEDDISPLAYPHRASE@@@Z; SerializeDisplayPhrase(SPDISPLAYPHRASE const *,SPSERIALIZEDDISPLAYPHRASE * *)
0x18000419b  mov     edi, eax
0x18000419d  test    eax, eax
0x18000419f  js      loc_1800042E8
0x1800041a5  test    r14, r14
0x1800041a8  jnz     loc_1800042C4
0x1800041ae  mov     edi, r15d
0x1800041b1  mov     rcx, cs:?g_heap@@3VCHeap@@A; hHeap
0x1800041b8  mov     rsi, [rbp+Src]
0x1800041bc  test    rcx, rcx
0x1800041bf  jz      loc_1800042EE
0x1800041c5  mov     eax, [rsi]
0x1800041c7  xor     edx, edx; dwFlags
0x1800041c9  add     eax, 10Bh
0x1800041ce  movsxd  r8, eax; dwBytes
0x1800041d1  mov     dword ptr [rbp+Src], eax
0x1800041d4  call    cs:__imp_HeapAlloc
0x1800041da  mov     rbx, rax
0x1800041dd  test    rax, rax
0x1800041e0  jz      loc_1800042EE
0x1800041e6  xor     edx, edx; Val
0x1800041e8  mov     dword ptr [rax], 29h ; ')'
0x1800041ee  mov     r8d, 100h; Size
0x1800041f4  mov     [rax+4], r13d
0x1800041f8  lea     rcx, [rax+8]; void *
0x1800041fc  call    memset_0
0x180004201  test    rdi, rdi
0x180004204  jz      short loc_18000421B
0x180004206  mov     r9, rdi
0x180004209  lea     rcx, [rbx+8]
0x18000420d  mov     r8, r14
0x180004210  mov     edx, 80h
0x180004215  call    cs:__imp__o_wcsncpy_s
0x18000421b  mov     r8d, [rsi]; Size
0x18000421e  lea     rcx, [rbx+108h]; void *
0x180004225  mov     rdx, rsi; Src
0x180004228  call    memcpy_0
0x18000422d  mov     rcx, [rbp+var_18]
0x180004231  lea     rdx, [rbp+arg_8]
0x180004235  mov     r8d, dword ptr [rbp+Src]
0x180004239  lea     r9, [rbp+pv]
0x18000423d  mov     [rbp+pv], r15
0x180004241  mov     [rbp+arg_8], r15d
0x180004245  mov     rcx, [rcx]
0x180004248  mov     [rsp+58h+var_38], rdx
0x18000424d  mov     rdx, rbx
0x180004250  mov     rax, [rcx]
0x180004253  mov     rax, [rax+20h]
0x180004257  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000425c  mov     edi, eax
0x18000425e  test    eax, eax
0x180004260  js      short loc_1800042AF
0x180004262  mov     rcx, [rbp+pv]
0x180004266  test    rcx, rcx
0x180004269  jz      short loc_1800042AF
0x18000426b  lea     r15, [rcx+4]
0x18000426f  xor     r14d, r14d
0x180004272  cmp     r14d, [rcx]
0x180004275  jnb     short loc_18000429E
0x180004277  lea     rdx, [r12+r14*8]; struct SPDISPLAYPHRASE **
0x18000427b  mov     rcx, r15; struct SPSERIALIZEDDISPLAYPHRASE *
0x18000427e  call    ?DeserializeDisplayPhrase@@YAJPEBUSPSERIALIZEDDISPLAYPHRASE@@PEAPEAUSPDISPLAYPHRASE@@@Z; DeserializeDisplayPhrase(SPSERIALIZEDDISPLAYPHRASE const *,SPDISPLAYPHRASE * *)
0x180004283  mov     rcx, [rbp+pv]; pv
0x180004287  mov     edi, eax
0x180004289  mov     eax, [r15]
0x18000428c  inc     r14d
0x18000428f  add     rax, 7
0x180004293  and     rax, 0FFFFFFFFFFFFFFF8h
0x180004297  add     r15, rax
0x18000429a  test    edi, edi
0x18000429c  jns     short loc_180004272
0x18000429e  mov     rdx, [rbp+arg_28]
0x1800042a2  mov     eax, [rcx]
0x1800042a4  mov     [rdx], eax
0x1800042a6  call    cs:__imp_CoTaskMemFree
0x1800042ac  xor     r15d, r15d
0x1800042af  mov     rdx, rbx; void *
0x1800042b2  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x1800042b9  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x1800042be  test    edi, edi
0x1800042c0  jns     short loc_180004319
0x1800042c2  jmp     short loc_1800042F8
0x1800042c4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800042c8  inc     rax
0x1800042cb  cmp     [r14+rax*2], r15w
0x1800042d0  jnz     short loc_1800042C8
0x1800042d2  lea     rdi, [rax+1]
0x1800042d6  cmp     rdi, 80h
0x1800042dd  jbe     loc_1800041B1
0x1800042e3  mov     edi, 80070057h
0x1800042e8  mov     rsi, [rbp+Src]
0x1800042ec  jmp     short loc_1800042F8
0x1800042ee  mov     edi, 8007000Eh
0x1800042f3  jmp     short loc_1800042F8
0x1800042f5  xor     r15d, r15d
0x1800042f8  mov     r14d, r15d
0x1800042fb  test    r13d, r13d
0x1800042fe  jz      short loc_180004319
0x180004300  mov     ebx, r14d
0x180004303  mov     rcx, [r12+rbx*8]; pv
0x180004307  call    cs:__imp_CoTaskMemFree
0x18000430d  inc     r14d
0x180004310  mov     [r12+rbx*8], r15
0x180004314  cmp     r14d, r13d
0x180004317  jb      short loc_180004300
0x180004319  mov     rcx, rsi; pv
0x18000431c  call    cs:__imp_CoTaskMemFree
0x180004322  mov     eax, edi
0x180004324  jmp     short loc_18000432B
0x180004326  mov     eax, 80070057h
0x18000432b  add     rsp, 58h
0x18000432f  pop     r15
0x180004331  pop     r14
0x180004333  pop     r13
0x180004335  pop     r12
0x180004337  pop     rdi
0x180004338  pop     rsi
0x180004339  pop     rbx
0x18000433a  pop     rbp
0x18000433b  retn
```
