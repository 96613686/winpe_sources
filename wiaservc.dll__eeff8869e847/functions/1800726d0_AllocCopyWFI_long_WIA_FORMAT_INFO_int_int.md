# AllocCopyWFI(long *,_WIA_FORMAT_INFO *,int,int)

- ea: `0x1800726d0`
- end: `0x18007292b`
- name: `?AllocCopyWFI@@YAPEAU_WIA_FORMAT_INFO@@PEAJPEAU1@HH@Z`
- size: `603`
- prototype: `struct _WIA_FORMAT_INFO *__fastcall(unsigned int *, struct _WIA_FORMAT_INFO *, int, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x18001d584`

## callees

- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x18002de18`
- `0x18002def8`
- `0x1800726d0`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180072797`
- `ole32!CoTaskMemAlloc` at `0x180072797`

## string_xrefs

- `0x1800726ea`: `::AllocCopyWFI`
- `0x1800728b3`: `CEnumWiaFormatInfo : AllocCopyFe, unable to allocate WIA_FORMAT_INFO buffer`
- `0x1800728d9`: `CEnumWiaFormatInfo : AllocCopyFe, unable to allocate WIA_FORMAT_INFO buffer`
- `0x1800726fc`: `AllocCopyWFI`
- `0x1800728c2`: `AllocCopyWFI`
- `0x1800728f0`: `AllocCopyWFI`

## pseudocode

```c
struct _WIA_FORMAT_INFO *__fastcall AllocCopyWFI(unsigned int *a1, struct _WIA_FORMAT_INFO *a2, int a3, int a4)
{
  char ***v8; // rax
  char *v9; // rdx
  __int64 v10; // r8
  unsigned int v11; // ebx
  int v12; // esi
  int v13; // r8d
  __int64 i; // rdx
  int v15; // eax
  __int64 j; // rdx
  unsigned int v17; // r15d
  _DWORD *v18; // rax
  _DWORD *v19; // rdi
  __int64 v20; // r10
  __int64 k; // r9
  struct _WIA_FORMAT_INFO *v22; // r8
  __int64 v23; // rax
  __int64 v24; // rcx
  struct _WIA_FORMAT_INFO *v25; // rdx
  GUID guidFormatID; // xmm0
  __int64 v27; // rcx
  unsigned __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // rcx
  unsigned __int64 v31; // rcx
  char *v32; // rbx
  void *v33; // rdx
  void **v34; // rax
  void *v35; // rdx
  __int64 v36; // rcx
  unsigned int lpMem; // [rsp+20h] [rbp-A8h]
  _BYTE v39[152]; // [rsp+30h] [rbp-98h] BYREF
  unsigned int v40; // [rsp+D0h] [rbp+8h]

  v8 = (char ***)WiaTrace_Trace("::AllocCopyWFI");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v39, v9, v10, (char **)"AllocCopyWFI", lpMem, v8);
  if ( a1 && (v11 = *a1) != 0 )
  {
    v12 = 0;
    v13 = 0;
    if ( a3 )
    {
      for ( i = 0; (unsigned int)i < v11; v12 = v15 )
      {
        v15 = v12 + 1;
        if ( a2[i].lTymed != 2 )
          v15 = v12;
        i = (unsigned int)(i + 1);
      }
    }
    else if ( a4 )
    {
      for ( j = 0; (unsigned int)j < v11; j = (unsigned int)(j + 1) )
      {
        if ( a2[j].lTymed == 128 || a2[j].lTymed == 512 )
          ++v13;
      }
    }
    v17 = v11 - v13;
    v40 = v11 - v13 + v12;
    v18 = CoTaskMemAlloc(20LL * v40);
    v19 = v18;
    if ( v18 )
    {
      if ( a3 )
      {
        v20 = 0;
        for ( k = 0; (unsigned int)v20 < v11; v19[v27 + 4] = v22->lTymed )
        {
          if ( (unsigned int)k >= v11 + v12 )
            break;
          v22 = &a2[v20];
          if ( v22->lTymed == 2 )
          {
            v23 = *(_QWORD *)&WiaImgFmt_BMP.Data1 - *(_QWORD *)&v22->guidFormatID.Data1;
            if ( *(_QWORD *)&WiaImgFmt_BMP.Data1 == *(_QWORD *)&v22->guidFormatID.Data1 )
              v23 = *(_QWORD *)WiaImgFmt_BMP.Data4 - *(_QWORD *)v22->guidFormatID.Data4;
            v24 = 5 * k;
            v25 = (struct _WIA_FORMAT_INFO *)&WiaImgFmt_MEMORYBMP;
            if ( v23 )
              v25 = &a2[v20];
            k = (unsigned int)(k + 1);
            guidFormatID = v25->guidFormatID;
            v19[v24 + 4] = 128;
            *(GUID *)&v19[v24] = guidFormatID;
          }
          v27 = 5 * k;
          v20 = (unsigned int)(v20 + 1);
          k = (unsigned int)(k + 1);
          *(GUID *)&v19[v27] = v22->guidFormatID;
        }
      }
      else
      {
        v28 = 0;
        if ( a4 )
        {
          v29 = 0;
          if ( v11 )
          {
            do
            {
              if ( (unsigned int)v29 >= v17 )
                break;
              if ( a2[v28].lTymed != 128 && a2[v28].lTymed != 512 )
              {
                v30 = 5 * v29;
                v29 = (unsigned int)(v29 + 1);
                *(GUID *)&v18[v30] = a2[v28].guidFormatID;
                v18[v30 + 4] = a2[v28].lTymed;
              }
              v28 = (unsigned int)(v28 + 1);
            }
            while ( (unsigned int)v28 < v11 );
          }
        }
        else if ( v11 )
        {
          do
          {
            v31 = v28;
            v28 = (unsigned int)(v28 + 1);
            *(GUID *)&v18[v31 * 5] = a2[v31].guidFormatID;
            v18[v31 * 5 + 4] = a2[v31].lTymed;
          }
          while ( (unsigned int)v28 < v11 );
        }
      }
      *a1 = v40;
    }
    else
    {
      v32 = (char *)WiaTrace_TraceLog("CEnumWiaFormatInfo : AllocCopyFe, unable to allocate WIA_FORMAT_INFO buffer");
      WriteDbgTraceErrorWI("AllocCopyWFI", v32);
      WiaTrcLib::Free((WiaTrcLib *)v32, v33);
      v34 = (void **)WiaTrace_Trace("CEnumWiaFormatInfo : AllocCopyFe, unable to allocate WIA_FORMAT_INFO buffer");
      WiaTrace_ProcessTrace_Ex(v36, v35, (void *)"AllocCopyWFI", 1, v34);
    }
    CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v39);
    return (struct _WIA_FORMAT_INFO *)v19;
  }
  else
  {
    CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v39);
    return 0;
  }
}

```

## disassembly

```asm
0x1800726d0  push    rbx
0x1800726d2  push    rbp
0x1800726d3  push    rsi
0x1800726d4  push    rdi
0x1800726d5  push    r12
0x1800726d7  push    r13
0x1800726d9  push    r14
0x1800726db  push    r15
0x1800726dd  sub     rsp, 88h
0x1800726e4  mov     r13, rcx
0x1800726e7  mov     ebp, r9d
0x1800726ea  lea     rcx, aAlloccopywfi_0; "::AllocCopyWFI"
0x1800726f1  mov     r12d, r8d
0x1800726f4  mov     r14, rdx
0x1800726f7  call    WiaTrace_Trace
0x1800726fc  lea     r9, aAlloccopywfi; "AllocCopyWFI"
0x180072703  mov     [rsp+0C8h+var_A0], rax; struct tagWiaTraceData_Type *
0x180072708  lea     rcx, [rsp+0C8h+var_98]; this
0x18007270d  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x180072712  test    r13, r13
0x180072715  jz      loc_18007290B
0x18007271b  mov     ebx, [r13+0]
0x18007271f  test    ebx, ebx
0x180072721  jz      loc_18007290B
0x180072727  xor     esi, esi
0x180072729  xor     r8d, r8d
0x18007272c  test    r12d, r12d
0x18007272f  jz      short loc_180072751
0x180072731  xor     edx, edx
0x180072733  test    ebx, ebx
0x180072735  jz      short loc_18007277E
0x180072737  lea     rcx, [rdx+rdx*4]
0x18007273b  cmp     dword ptr [r14+rcx*4+10h], 2
0x180072741  lea     eax, [rsi+1]
0x180072744  cmovnz  eax, esi
0x180072747  inc     edx
0x180072749  mov     esi, eax
0x18007274b  cmp     edx, ebx
0x18007274d  jb      short loc_180072737
0x18007274f  jmp     short loc_18007277E
0x180072751  test    ebp, ebp
0x180072753  jz      short loc_18007277E
0x180072755  xor     edx, edx
0x180072757  test    ebx, ebx
0x180072759  jz      short loc_18007277E
0x18007275b  lea     rcx, [rdx+rdx*4]
0x18007275f  cmp     dword ptr [r14+rcx*4+10h], 80h
0x180072768  jz      short loc_180072775
0x18007276a  cmp     dword ptr [r14+rcx*4+10h], 200h
0x180072773  jnz     short loc_180072778
0x180072775  inc     r8d
0x180072778  inc     edx
0x18007277a  cmp     edx, ebx
0x18007277c  jb      short loc_18007275B
0x18007277e  mov     r15d, ebx
0x180072781  sub     r15d, r8d
0x180072784  lea     eax, [r15+rsi]
0x180072788  lea     rcx, [rax+rax*4]
0x18007278c  mov     [rsp+0C8h+arg_0], eax
0x180072793  shl     rcx, 2; cb
0x180072797  call    cs:__imp_CoTaskMemAlloc
0x18007279d  mov     rdi, rax
0x1800727a0  test    rax, rax
0x1800727a3  jz      loc_1800728B3
0x1800727a9  test    r12d, r12d
0x1800727ac  jz      loc_180072839
0x1800727b2  xor     r10d, r10d
0x1800727b5  xor     r9d, r9d
0x1800727b8  test    ebx, ebx
0x1800727ba  jz      loc_1800728A6
0x1800727c0  lea     r11d, [rbx+rsi]
0x1800727c4  cmp     r9d, r11d
0x1800727c7  jnb     loc_1800728A6
0x1800727cd  lea     rcx, [r10+r10*4]
0x1800727d1  lea     r8, [r14+rcx*4]
0x1800727d5  cmp     dword ptr [r8+10h], 2
0x1800727da  jnz     short loc_180072818
0x1800727dc  mov     rax, qword ptr cs:WiaImgFmt_BMP.Data1
0x1800727e3  sub     rax, [r8]
0x1800727e6  jnz     short loc_1800727F3
0x1800727e8  mov     rax, qword ptr cs:WiaImgFmt_BMP.Data4
0x1800727ef  sub     rax, [r8+8]
0x1800727f3  lea     rcx, [r9+r9*4]
0x1800727f7  test    rax, rax
0x1800727fa  lea     rdx, WiaImgFmt_MEMORYBMP
0x180072801  cmovnz  rdx, r8
0x180072805  inc     r9d
0x180072808  movups  xmm0, xmmword ptr [rdx]
0x18007280b  mov     dword ptr [rdi+rcx*4+10h], 80h
0x180072813  movdqu  xmmword ptr [rdi+rcx*4], xmm0
0x180072818  movups  xmm0, xmmword ptr [r8]
0x18007281c  lea     rcx, [r9+r9*4]
0x180072820  inc     r10d
0x180072823  inc     r9d
0x180072826  movups  xmmword ptr [rdi+rcx*4], xmm0
0x18007282a  mov     eax, [r8+10h]
0x18007282e  mov     [rdi+rcx*4+10h], eax
0x180072832  cmp     r10d, ebx
0x180072835  jb      short loc_1800727C4
0x180072837  jmp     short loc_1800728A6
0x180072839  xor     edx, edx
0x18007283b  test    ebp, ebp
0x18007283d  jz      short loc_180072886
0x18007283f  xor     r8d, r8d
0x180072842  test    ebx, ebx
0x180072844  jz      short loc_1800728A6
0x180072846  cmp     r8d, r15d
0x180072849  jnb     short loc_1800728A6
0x18007284b  lea     r9, [rdx+rdx*4]
0x18007284f  cmp     dword ptr [r14+r9*4+10h], 80h
0x180072858  jz      short loc_18007287E
0x18007285a  cmp     dword ptr [r14+r9*4+10h], 200h
0x180072863  jz      short loc_18007287E
0x180072865  movups  xmm0, xmmword ptr [r14+r9*4]
0x18007286a  lea     rcx, [r8+r8*4]
0x18007286e  inc     r8d
0x180072871  movups  xmmword ptr [rdi+rcx*4], xmm0
0x180072875  mov     eax, [r14+r9*4+10h]
0x18007287a  mov     [rdi+rcx*4+10h], eax
0x18007287e  inc     edx
0x180072880  cmp     edx, ebx
0x180072882  jb      short loc_180072846
0x180072884  jmp     short loc_1800728A6
0x180072886  test    ebx, ebx
0x180072888  jz      short loc_1800728A6
0x18007288a  lea     rcx, [rdx+rdx*4]
0x18007288e  inc     edx
0x180072890  movups  xmm0, xmmword ptr [r14+rcx*4]
0x180072895  movups  xmmword ptr [rdi+rcx*4], xmm0
0x180072899  mov     eax, [r14+rcx*4+10h]
0x18007289e  mov     [rdi+rcx*4+10h], eax
0x1800728a2  cmp     edx, ebx
0x1800728a4  jb      short loc_18007288A
0x1800728a6  mov     eax, [rsp+0C8h+arg_0]
0x1800728ad  mov     [r13+0], eax
0x1800728b1  jmp     short loc_1800728FC
0x1800728b3  lea     rcx, aCenumwiaformat_2; "CEnumWiaFormatInfo : AllocCopyFe, unabl"...
0x1800728ba  call    WiaTrace_TraceLog
0x1800728bf  mov     rdx, rax; char *
0x1800728c2  lea     rcx, aAlloccopywfi; "AllocCopyWFI"
0x1800728c9  mov     rbx, rax
0x1800728cc  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800728d1  mov     rcx, rbx; this
0x1800728d4  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800728d9  lea     rcx, aCenumwiaformat_2; "CEnumWiaFormatInfo : AllocCopyFe, unabl"...
0x1800728e0  call    WiaTrace_Trace
0x1800728e5  mov     r9d, 1; int
0x1800728eb  mov     [rsp+0C8h+lpMem], rax; lpMem
0x1800728f0  lea     r8, aAlloccopywfi; "AllocCopyWFI"
0x1800728f7  call    WiaTrace_ProcessTrace_Ex
0x1800728fc  lea     rcx, [rsp+0C8h+var_98]; this
0x180072901  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x180072906  mov     rax, rdi
0x180072909  jmp     short loc_180072917
0x18007290b  lea     rcx, [rsp+0C8h+var_98]; this
0x180072910  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x180072915  xor     eax, eax
0x180072917  add     rsp, 88h
0x18007291e  pop     r15
0x180072920  pop     r14
0x180072922  pop     r13
0x180072924  pop     r12
0x180072926  pop     rdi
0x180072927  pop     rsi
0x180072928  pop     rbp
0x180072929  pop     rbx
0x18007292a  retn
```
