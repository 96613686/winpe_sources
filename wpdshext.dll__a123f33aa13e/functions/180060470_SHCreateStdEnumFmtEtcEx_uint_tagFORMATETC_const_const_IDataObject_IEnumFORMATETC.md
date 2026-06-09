# SHCreateStdEnumFmtEtcEx(uint,tagFORMATETC const * const,IDataObject *,IEnumFORMATETC * *)

- ea: `0x180060470`
- end: `0x18006067c`
- name: `?SHCreateStdEnumFmtEtcEx@@YAJIQEBUtagFORMATETC@@PEAUIDataObject@@PEAPEAUIEnumFORMATETC@@@Z`
- size: `524`
- prototype: `int(unsigned int, const struct tagFORMATETC *const, struct IDataObject *, struct IEnumFORMATETC **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18005ff10`

## callees

- `0x180060470`
- `0x1800755a8`
- `0x180078010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180060655`
- `KERNEL32!LocalFree` at `0x180060655`
- `KERNEL32!LocalAlloc` at `0x18006056f`
- `KERNEL32!LocalAlloc` at `0x18006056f`
- `ole32!CoTaskMemFree` at `0x180060512`
- `ole32!CoTaskMemFree` at `0x1800605c2`
- `ole32!CoTaskMemFree` at `0x180060512`
- `ole32!CoTaskMemFree` at `0x1800605c2`
- `SHELL32!__imp_SHCreateStdEnumFmtEtc` at `0x180060645`
- `SHELL32!__imp_SHCreateStdEnumFmtEtc` at `0x180060645`

## pseudocode

```c
__int64 __fastcall SHCreateStdEnumFmtEtcEx(
        unsigned int a1,
        const struct tagFORMATETC *const a2,
        struct IDataObject *a3,
        struct IEnumFORMATETC **a4)
{
  __int64 v4; // r12
  IEnumFORMATETC **v5; // r15
  const struct tagFORMATETC *v6; // r13
  struct IDataObjectVtbl *lpVtbl; // rax
  HRESULT v8; // ebx
  FORMATETC *v9; // rdi
  unsigned int v10; // esi
  UINT v11; // r14d
  unsigned int v12; // r15d
  __int64 v13; // r13
  __int64 v14; // rax
  FORMATETC *v15; // rax
  DVTARGETDEVICE *ptd; // rcx
  __int64 *v18; // [rsp+30h] [rbp-30h] BYREF
  FORMATETC *v19; // [rsp+38h] [rbp-28h]
  LPVOID pv[2]; // [rsp+40h] [rbp-20h] BYREF
  __int128 v21; // [rsp+50h] [rbp-10h]
  int v23; // [rsp+B0h] [rbp+50h] BYREF
  struct IEnumFORMATETC **v24; // [rsp+B8h] [rbp+58h]

  v24 = a4;
  v4 = a1;
  v5 = a4;
  v6 = a2;
  if ( a3 )
  {
    lpVtbl = a3->lpVtbl;
    v18 = 0;
    v8 = ((__int64 (__fastcall *)(struct IDataObject *, __int64, __int64 **))lpVtbl->EnumFormatEtc)(a3, 1, &v18);
    if ( v8 >= 0 )
    {
      v23 = 0;
      *(_OWORD *)pv = 0;
      v9 = 0;
      v10 = 0;
      v21 = 0;
      while ( !(*(unsigned int (__fastcall **)(__int64 *, __int64, LPVOID *, int *))(*v18 + 24))(v18, 1, pv, &v23) )
      {
        if ( pv[1] )
        {
          CoTaskMemFree(pv[1]);
          pv[1] = 0;
        }
        ++v10;
      }
      (*(void (__fastcall **)(__int64 *))(*v18 + 40))(v18);
      if ( (unsigned int)v4 >= ~v10 )
        v8 = -2147418113;
      v11 = (unsigned int)v4 < ~v10 ? v10 + v4 : 0;
      if ( v8 >= 0 )
      {
        if ( (v11 & 0x7FFFFFF) == v11 )
        {
          v9 = (FORMATETC *)LocalAlloc(0x40u, 32 * v11);
          if ( v9 )
          {
            v12 = 0;
            if ( v10 )
            {
              v13 = 0;
              do
              {
                v14 = *v18;
                v19 = &v9[v13];
                (*(void (__fastcall **)(__int64 *, __int64, FORMATETC *, int *))(v14 + 24))(v18, 1, v19, &v23);
                v15 = v19;
                ptd = v19->ptd;
                if ( ptd )
                {
                  CoTaskMemFree(ptd);
                  v15 = v19;
                }
                ++v12;
                v15->ptd = 0;
                ++v13;
              }
              while ( v12 < v10 );
              v6 = a2;
            }
            if ( (_DWORD)v4 )
              memcpy_0(&v9[v10], v6, 32 * v4);
            v5 = v24;
          }
          else
          {
            v8 = -2147024882;
          }
        }
        else
        {
          v8 = -2147418113;
        }
      }
      if ( v18 )
      {
        (*(void (__fastcall **)(__int64 *))(*v18 + 16))(v18);
        v18 = 0;
      }
      if ( v8 >= 0 )
        goto LABEL_29;
    }
    if ( v8 == -2147024882 || v8 == -2147418113 )
      return (unsigned int)v8;
  }
  v9 = (FORMATETC *)v6;
  v11 = v4;
LABEL_29:
  v8 = SHCreateStdEnumFmtEtc(v11, v9, v5);
  if ( v9 != v6 )
    LocalFree(v9);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180060470  mov     [rsp-38h+arg_0], rbx
0x180060475  mov     [rsp-38h+arg_18], r9
0x18006047a  mov     [rsp-38h+arg_8], rdx
0x18006047f  push    rbp
0x180060480  push    rsi
0x180060481  push    rdi
0x180060482  push    r12
0x180060484  push    r13
0x180060486  push    r14
0x180060488  push    r15
0x18006048a  mov     rbp, rsp
0x18006048d  sub     rsp, 60h
0x180060491  xor     r14d, r14d
0x180060494  mov     r12d, ecx
0x180060497  mov     r15, r9
0x18006049a  mov     r10, r8
0x18006049d  mov     r13, rdx
0x1800604a0  test    r8, r8
0x1800604a3  jz      loc_180060636
0x1800604a9  mov     rax, [r8]
0x1800604ac  lea     edx, [r14+1]
0x1800604b0  lea     r8, [rbp+var_30]
0x1800604b4  mov     [rbp+var_30], r14
0x1800604b8  mov     rcx, r10
0x1800604bb  mov     rax, [rax+40h]
0x1800604bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800604c4  mov     ebx, eax
0x1800604c6  mov     eax, 8000FFFFh
0x1800604cb  test    ebx, ebx
0x1800604cd  js      loc_18006062A
0x1800604d3  xorps   xmm0, xmm0
0x1800604d6  mov     [rbp+arg_10], r14d
0x1800604da  movups  xmmword ptr [rbp+pv], xmm0
0x1800604de  mov     edi, r14d
0x1800604e1  mov     esi, r14d
0x1800604e4  movups  [rbp+var_10], xmm0
0x1800604e8  mov     rcx, [rbp+var_30]
0x1800604ec  lea     r9, [rbp+arg_10]
0x1800604f0  lea     r8, [rbp+pv]
0x1800604f4  mov     edx, 1
0x1800604f9  mov     rax, [rcx]
0x1800604fc  mov     rax, [rax+18h]
0x180060500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060505  test    eax, eax
0x180060507  jnz     short loc_180060520
0x180060509  mov     rcx, [rbp+pv+8]; pv
0x18006050d  test    rcx, rcx
0x180060510  jz      short loc_18006051C
0x180060512  call    cs:__imp_CoTaskMemFree
0x180060518  mov     [rbp+pv+8], r14
0x18006051c  inc     esi
0x18006051e  jmp     short loc_1800604E8
0x180060520  mov     rcx, [rbp+var_30]
0x180060524  mov     rax, [rcx]
0x180060527  mov     rax, [rax+28h]
0x18006052b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060530  mov     ecx, esi
0x180060532  lea     eax, [rsi+r12]
0x180060536  not     ecx
0x180060538  mov     edx, 8000FFFFh
0x18006053d  cmp     r12d, ecx
0x180060540  cmovnb  ebx, edx
0x180060543  sbb     r14d, r14d
0x180060546  and     r14d, eax
0x180060549  test    ebx, ebx
0x18006054b  js      loc_180060604
0x180060551  mov     ecx, r14d
0x180060554  shl     ecx, 5
0x180060557  mov     eax, ecx
0x180060559  shr     eax, 5
0x18006055c  cmp     eax, r14d
0x18006055f  jz      short loc_180060568
0x180060561  mov     ebx, edx
0x180060563  jmp     loc_180060604
0x180060568  mov     edx, ecx; uBytes
0x18006056a  mov     ecx, 40h ; '@'; uFlags
0x18006056f  call    cs:__imp_LocalAlloc
0x180060575  mov     rdi, rax
0x180060578  test    rax, rax
0x18006057b  jz      loc_180060675
0x180060581  xor     r15d, r15d
0x180060584  test    esi, esi
0x180060586  jz      short loc_1800605E3
0x180060588  xor     r13d, r13d
0x18006058b  mov     rcx, [rbp+var_30]
0x18006058f  lea     r9, [rbp+arg_10]
0x180060593  mov     rdx, r13
0x180060596  shl     rdx, 5
0x18006059a  add     rdx, rdi
0x18006059d  mov     rax, [rcx]
0x1800605a0  mov     r8, rdx
0x1800605a3  mov     [rbp+var_28], rdx
0x1800605a7  mov     edx, 1
0x1800605ac  mov     rax, [rax+18h]
0x1800605b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800605b5  mov     rax, [rbp+var_28]
0x1800605b9  mov     rcx, [rax+8]; pv
0x1800605bd  test    rcx, rcx
0x1800605c0  jz      short loc_1800605CC
0x1800605c2  call    cs:__imp_CoTaskMemFree
0x1800605c8  mov     rax, [rbp+var_28]
0x1800605cc  inc     r15d
0x1800605cf  mov     qword ptr [rax+8], 0
0x1800605d7  inc     r13
0x1800605da  cmp     r15d, esi
0x1800605dd  jb      short loc_18006058B
0x1800605df  mov     r13, [rbp+arg_8]
0x1800605e3  test    r12d, r12d
0x1800605e6  jz      short loc_180060600
0x1800605e8  mov     ecx, esi
0x1800605ea  mov     r8, r12
0x1800605ed  shl     rcx, 5
0x1800605f1  mov     rdx, r13; Src
0x1800605f4  add     rcx, rdi; void *
0x1800605f7  shl     r8, 5; Size
0x1800605fb  call    memcpy_0
0x180060600  mov     r15, [rbp+arg_18]
0x180060604  mov     rcx, [rbp+var_30]
0x180060608  test    rcx, rcx
0x18006060b  jz      short loc_180060621
0x18006060d  mov     rax, [rcx]
0x180060610  mov     rax, [rax+10h]
0x180060614  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060619  mov     [rbp+var_30], 0
0x180060621  test    ebx, ebx
0x180060623  jns     short loc_18006063C
0x180060625  mov     eax, 8000FFFFh
0x18006062a  cmp     ebx, 8007000Eh
0x180060630  jz      short loc_18006065B
0x180060632  cmp     ebx, eax
0x180060634  jz      short loc_18006065B
0x180060636  mov     rdi, r13
0x180060639  mov     r14d, r12d
0x18006063c  mov     r8, r15; ppenumFormatEtc
0x18006063f  mov     rdx, rdi; afmt
0x180060642  mov     ecx, r14d; cfmt
0x180060645  call    cs:__imp_SHCreateStdEnumFmtEtc
0x18006064b  mov     ebx, eax
0x18006064d  cmp     rdi, r13
0x180060650  jz      short loc_18006065B
0x180060652  mov     rcx, rdi; hMem
0x180060655  call    cs:__imp_LocalFree
0x18006065b  mov     eax, ebx
0x18006065d  mov     rbx, [rsp+60h+arg_0]
0x180060665  add     rsp, 60h
0x180060669  pop     r15
0x18006066b  pop     r14
0x18006066d  pop     r13
0x18006066f  pop     r12
0x180060671  pop     rdi
0x180060672  pop     rsi
0x180060673  pop     rbp
0x180060674  retn
0x180060675  mov     ebx, 8007000Eh
0x18006067a  jmp     short loc_180060604
```
