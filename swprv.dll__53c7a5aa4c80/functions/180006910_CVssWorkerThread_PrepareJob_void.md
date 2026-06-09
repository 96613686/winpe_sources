# CVssWorkerThread::PrepareJob(void)

- ea: `0x180006910`
- end: `0x180006c8a`
- name: `?PrepareJob@CVssWorkerThread@@QEAAJXZ`
- size: `890`
- prototype: `__int64 __fastcall(CVssWorkerThread *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180004c74`

## callees

- `0x18000212c`
- `0x180006910`
- `0x180033a8c`
- `0x180033c2c`
- `0x180033c78`
- `0x180033e60`
- `0x1800358f4`
- `0x1800367b8`
- `0x18004b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800069d9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006a8d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006aed`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006af8`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006baa`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800069d9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006a8d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006aed`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006af8`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006baa`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x1800069ca`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x1800069ca`

## string_xrefs

- `0x18000693d`: `CVssWorkerThread::PrepareJob`
- `0x180006a23`: `_beginthreadex failed. errno = 0x%08lx`
- `0x180006b42`: `_beginthreadex failed. errno = 0x%08lx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVssWorkerThread::PrepareJob(CVssWorkerThread *this)
{
  __int64 v2; // rax
  unsigned int *v3; // rbx
  struct CVssDebugInfo *v4; // rbx
  DWORD *v5; // rax
  CVssDebugInfo *v6; // rax
  CVssDebugInfo *v7; // rcx
  unsigned int *v9; // rbx
  struct CVssDebugInfo *v10; // rbx
  DWORD *v11; // rax
  CVssDebugInfo *v12; // rax
  const wchar_t *v13; // [rsp+30h] [rbp-D0h] BYREF
  const wchar_t *v14; // [rsp+38h] [rbp-C8h]
  const wchar_t *v15; // [rsp+40h] [rbp-C0h]
  __int64 v16; // [rsp+48h] [rbp-B8h]
  int v17; // [rsp+50h] [rbp-B0h]
  _BYTE v18[120]; // [rsp+58h] [rbp-A8h] BYREF
  int v19; // [rsp+D0h] [rbp-30h]
  LPVOID v20[14]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v21[168]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v22[168]; // [rsp+1F8h] [rbp+F8h] BYREF

  v13 = L"base\\stor\\vss\\inc\\worker.hxx";
  v14 = L"CVssWorkerThread::PrepareJob";
  v15 = L"INCWORKH";
  v16 = 0x100000122LL;
  v17 = 255;
  v19 = 0x1000000;
  memset_0(v18, 0, sizeof(v18));
  CVssFunctionTracer::CVssFunctionTracer((__int64)v20, (__int64)&v13, 0);
  if ( *((_QWORD *)this + 2) || *((_DWORD *)this + 7) != 1 )
  {
    v13 = L"base\\stor\\vss\\inc\\worker.hxx";
    v14 = L"CVssWorkerThread::PrepareJob";
    v15 = L"INCWORKH";
    v16 = 0xB00000127LL;
    v17 = 255;
    v19 = 0x1000000;
    memset_0(v18, 0, sizeof(v18));
    CVssFunctionTracer::Trace(v20, &v13, L"Bad state %d", *((unsigned int *)this + 7));
    CVssFunctionTracer::~CVssFunctionTracer(v20);
    return 2147549183LL;
  }
  else
  {
    v2 = _o__beginthreadex(0, 0, CVssWorkerThread::_ThreadFunction, this, 4, (char *)this + 24, v13, v14, v15, v16, v17);
    if ( !v2 )
    {
      v3 = (unsigned int *)_o__errno();
      v13 = L"base\\stor\\vss\\inc\\worker.hxx";
      v14 = L"CVssWorkerThread::PrepareJob";
      v15 = L"INCWORKH";
      v16 = 0xB0000013ALL;
      v17 = 255;
      v19 = 0x1000000;
      memset_0(v18, 0, sizeof(v18));
      CVssFunctionTracer::Trace(v20, &v13, L"_beginthreadex failed. errno = 0x%08lx", *v3);
      v13 = L"base\\stor\\vss\\inc\\worker.hxx";
      v14 = L"CVssWorkerThread::PrepareJob";
      v15 = L"INCWORKH";
      v16 = 0xB0000013BLL;
      v17 = 255;
      v19 = 0x1000000;
      memset_0(v18, 0, sizeof(v18));
      v4 = CVssDebugInfo::operator<<((struct CVssDebugInfo *)&v13, (CVssDebugInfo *)v22, 0);
      v5 = (DWORD *)_o__errno();
      v6 = CVssDebugInfo::operator<<(v4, (CVssDebugInfo *)v21, *v5);
      CVssFunctionTracer::LogError((__int64)v20, 0x3008u, (__int64)v6, 1u);
      v7 = (CVssDebugInfo *)v22;
      goto LABEL_5;
    }
    if ( v2 == -1 )
    {
      if ( *(_DWORD *)_o__errno() == 11 )
        goto LABEL_6;
      v9 = (unsigned int *)_o__errno();
      v13 = L"base\\stor\\vss\\inc\\worker.hxx";
      v14 = L"CVssWorkerThread::PrepareJob";
      v15 = L"INCWORKH";
      v16 = 0xB00000147LL;
      v17 = 255;
      v19 = 0x1000000;
      memset_0(v18, 0, sizeof(v18));
      CVssFunctionTracer::Trace(v20, &v13, L"_beginthreadex failed. errno = 0x%08lx", *v9);
      v13 = L"base\\stor\\vss\\inc\\worker.hxx";
      v14 = L"CVssWorkerThread::PrepareJob";
      v15 = L"INCWORKH";
      v16 = 0xB00000148LL;
      v17 = 255;
      v19 = 0x1000000;
      memset_0(v18, 0, sizeof(v18));
      v10 = CVssDebugInfo::operator<<((struct CVssDebugInfo *)&v13, (CVssDebugInfo *)v21, 0xFFFFFFFF);
      v11 = (DWORD *)_o__errno();
      v12 = CVssDebugInfo::operator<<(v10, (CVssDebugInfo *)v22, *v11);
      CVssFunctionTracer::LogError((__int64)v20, 0x3008u, (__int64)v12, 1u);
      v7 = (CVssDebugInfo *)v21;
LABEL_5:
      CVssDebugInfo::~CVssDebugInfo(v7);
      CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v13);
LABEL_6:
      CVssFunctionTracer::~CVssFunctionTracer(v20);
      return 2147942414LL;
    }
    *((_QWORD *)this + 2) = v2;
    *((_BYTE *)this + 8) = (**(__int64 (__fastcall ***)(CVssWorkerThread *))this)(this);
    *((_DWORD *)this + 7) = 2;
    CVssFunctionTracer::~CVssFunctionTracer(v20);
    return 0;
  }
}

```

## disassembly

```asm
0x180006910  mov     [rsp-8+arg_8], rbx
0x180006915  mov     [rsp-8+arg_10], r12
0x18000691a  push    rbp
0x18000691b  push    r13
0x18000691d  push    r15
0x18000691f  lea     rbp, [rsp-1A0h]
0x180006927  sub     rsp, 2A0h
0x18000692e  mov     rbx, rcx
0x180006931  lea     r15, aBaseStorVssInc_0; "base\\stor\\vss\\inc\\worker.hxx"
0x180006938  mov     [rsp+2B0h+var_280], r15
0x18000693d  lea     r12, aCvssworkerthre_0; "CVssWorkerThread::PrepareJob"
0x180006944  mov     [rsp+2B0h+var_278], r12
0x180006949  lea     r13, aIncworkh; "INCWORKH"
0x180006950  mov     [rsp+2B0h+var_270], r13
0x180006955  mov     [rsp+2B0h+var_268], 122h
0x18000695d  mov     [rsp+2B0h+var_264], 1
0x180006965  mov     [rsp+2B0h+var_260], 0FFh
0x18000696d  mov     [rbp+1B0h+var_1E0], 1000000h
0x180006974  xor     edx, edx; Val
0x180006976  lea     r8d, [rdx+78h]; Size
0x18000697a  lea     rcx, [rsp+2B0h+var_258]; void *
0x18000697f  call    memset_0
0x180006984  xor     r8d, r8d
0x180006987  lea     rdx, [rsp+2B0h+var_280]
0x18000698c  lea     rcx, [rbp+1B0h+var_1D0]
0x180006990  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x180006995  nop
0x180006996  cmp     qword ptr [rbx+10h], 0
0x18000699b  jnz     loc_180006C0B
0x1800069a1  cmp     dword ptr [rbx+1Ch], 1
0x1800069a5  jnz     loc_180006C0B
0x1800069ab  lea     rax, [rbx+18h]
0x1800069af  mov     [rsp+2B0h+var_288], rax
0x1800069b4  mov     [rsp+2B0h+var_290], 4
0x1800069bc  mov     r9, rbx
0x1800069bf  lea     r8, ?_ThreadFunction@CVssWorkerThread@@CAIPEAPEAX@Z; CVssWorkerThread::_ThreadFunction(void * *)
0x1800069c6  xor     edx, edx
0x1800069c8  xor     ecx, ecx
0x1800069ca  call    cs:__imp__o__beginthreadex
0x1800069d0  test    rax, rax
0x1800069d3  jnz     loc_180006AE3
0x1800069d9  call    cs:__imp__o__errno
0x1800069df  mov     rbx, rax
0x1800069e2  mov     [rsp+2B0h+var_280], r15
0x1800069e7  mov     [rsp+2B0h+var_278], r12
0x1800069ec  mov     [rsp+2B0h+var_270], r13
0x1800069f1  mov     [rsp+2B0h+var_268], 13Ah
0x1800069f9  mov     [rsp+2B0h+var_264], 0Bh
0x180006a01  mov     [rsp+2B0h+var_260], 0FFh
0x180006a09  mov     [rbp+1B0h+var_1E0], 1000000h
0x180006a10  xor     edx, edx; Val
0x180006a12  lea     r8d, [rdx+78h]; Size
0x180006a16  lea     rcx, [rsp+2B0h+var_258]; void *
0x180006a1b  call    memset_0
0x180006a20  mov     r9d, [rbx]
0x180006a23  lea     r8, aBeginthreadexF; "_beginthreadex failed. errno = 0x%08lx"
0x180006a2a  lea     rdx, [rsp+2B0h+var_280]
0x180006a2f  lea     rcx, [rbp+1B0h+var_1D0]
0x180006a33  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x180006a38  mov     [rsp+2B0h+var_280], r15
0x180006a3d  mov     [rsp+2B0h+var_278], r12
0x180006a42  mov     [rsp+2B0h+var_270], r13
0x180006a47  mov     [rsp+2B0h+var_268], 13Bh
0x180006a4f  mov     [rsp+2B0h+var_264], 0Bh
0x180006a57  mov     [rsp+2B0h+var_260], 0FFh
0x180006a5f  mov     [rbp+1B0h+var_1E0], 1000000h
0x180006a66  xor     edx, edx; Val
0x180006a68  lea     r8d, [rdx+78h]; Size
0x180006a6c  lea     rcx, [rsp+2B0h+var_258]; void *
0x180006a71  call    memset_0
0x180006a76  xor     r8d, r8d; dwMessageId
0x180006a79  lea     rdx, [rbp+1B0h+var_B8]; this
0x180006a80  lea     rcx, [rsp+2B0h+var_280]; struct CVssDebugInfo *
0x180006a85  call    ??6CVssDebugInfo@@QEAA?AU0@J@Z; CVssDebugInfo::operator<<(long)
0x180006a8a  mov     rbx, rax
0x180006a8d  call    cs:__imp__o__errno
0x180006a93  mov     r8d, [rax]; dwMessageId
0x180006a96  lea     rdx, [rbp+1B0h+var_160]; this
0x180006a9a  mov     rcx, rbx; struct CVssDebugInfo *
0x180006a9d  call    ??6CVssDebugInfo@@QEAA?AU0@J@Z; CVssDebugInfo::operator<<(long)
0x180006aa2  mov     r9d, 1
0x180006aa8  mov     r8, rax
0x180006aab  mov     edx, 3008h
0x180006ab0  lea     rcx, [rbp+1B0h+var_1D0]
0x180006ab4  call    ?LogError@CVssFunctionTracer@@QEAAXKUCVssDebugInfo@@G@Z; CVssFunctionTracer::LogError(ulong,CVssDebugInfo,ushort)
0x180006ab9  lea     rcx, [rbp+1B0h+var_B8]; this
0x180006ac0  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x180006ac5  lea     rcx, [rsp+2B0h+var_280]; this
0x180006aca  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x180006acf  nop
0x180006ad0  lea     rcx, [rbp+1B0h+var_1D0]; this
0x180006ad4  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x180006ad9  mov     eax, 8007000Eh
0x180006ade  jmp     loc_180006C71
0x180006ae3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180006ae7  jnz     loc_180006BE2
0x180006aed  call    cs:__imp__o__errno
0x180006af3  cmp     dword ptr [rax], 0Bh
0x180006af6  jz      short loc_180006AD0
0x180006af8  call    cs:__imp__o__errno
0x180006afe  mov     rbx, rax
0x180006b01  mov     [rsp+2B0h+var_280], r15
0x180006b06  mov     [rsp+2B0h+var_278], r12
0x180006b0b  mov     [rsp+2B0h+var_270], r13
0x180006b10  mov     [rsp+2B0h+var_268], 147h
0x180006b18  mov     [rsp+2B0h+var_264], 0Bh
0x180006b20  mov     [rsp+2B0h+var_260], 0FFh
0x180006b28  mov     [rbp+1B0h+var_1E0], 1000000h
0x180006b2f  xor     edx, edx; Val
0x180006b31  lea     r8d, [rdx+78h]; Size
0x180006b35  lea     rcx, [rsp+2B0h+var_258]; void *
0x180006b3a  call    memset_0
0x180006b3f  mov     r9d, [rbx]
0x180006b42  lea     r8, aBeginthreadexF; "_beginthreadex failed. errno = 0x%08lx"
0x180006b49  lea     rdx, [rsp+2B0h+var_280]
0x180006b4e  lea     rcx, [rbp+1B0h+var_1D0]
0x180006b52  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x180006b57  mov     [rsp+2B0h+var_280], r15
0x180006b5c  mov     [rsp+2B0h+var_278], r12
0x180006b61  mov     [rsp+2B0h+var_270], r13
0x180006b66  mov     [rsp+2B0h+var_268], 148h
0x180006b6e  mov     [rsp+2B0h+var_264], 0Bh
0x180006b76  mov     [rsp+2B0h+var_260], 0FFh
0x180006b7e  mov     [rbp+1B0h+var_1E0], 1000000h
0x180006b85  xor     edx, edx; Val
0x180006b87  lea     r8d, [rdx+78h]; Size
0x180006b8b  lea     rcx, [rsp+2B0h+var_258]; void *
0x180006b90  call    memset_0
0x180006b95  or      r8d, 0FFFFFFFFh; dwMessageId
0x180006b99  lea     rdx, [rbp+1B0h+var_160]; this
0x180006b9d  lea     rcx, [rsp+2B0h+var_280]; struct CVssDebugInfo *
0x180006ba2  call    ??6CVssDebugInfo@@QEAA?AU0@J@Z; CVssDebugInfo::operator<<(long)
0x180006ba7  mov     rbx, rax
0x180006baa  call    cs:__imp__o__errno
0x180006bb0  mov     r8d, [rax]; dwMessageId
0x180006bb3  lea     rdx, [rbp+1B0h+var_B8]; this
0x180006bba  mov     rcx, rbx; struct CVssDebugInfo *
0x180006bbd  call    ??6CVssDebugInfo@@QEAA?AU0@J@Z; CVssDebugInfo::operator<<(long)
0x180006bc2  mov     r9d, 1
0x180006bc8  mov     r8, rax
0x180006bcb  mov     edx, 3008h
0x180006bd0  lea     rcx, [rbp+1B0h+var_1D0]
0x180006bd4  call    ?LogError@CVssFunctionTracer@@QEAAXKUCVssDebugInfo@@G@Z; CVssFunctionTracer::LogError(ulong,CVssDebugInfo,ushort)
0x180006bd9  lea     rcx, [rbp+1B0h+var_160]
0x180006bdd  jmp     loc_180006AC0
0x180006be2  mov     [rbx+10h], rax
0x180006be6  mov     rax, [rbx]
0x180006be9  mov     rcx, rbx
0x180006bec  mov     rax, [rax]
0x180006bef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bf4  mov     [rbx+8], al
0x180006bf7  mov     dword ptr [rbx+1Ch], 2
0x180006bfe  lea     rcx, [rbp+1B0h+var_1D0]; this
0x180006c02  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x180006c07  xor     eax, eax
0x180006c09  jmp     short loc_180006C71
0x180006c0b  mov     [rsp+2B0h+var_280], r15
0x180006c10  mov     [rsp+2B0h+var_278], r12
0x180006c15  mov     [rsp+2B0h+var_270], r13
0x180006c1a  mov     [rsp+2B0h+var_268], 127h
0x180006c22  mov     [rsp+2B0h+var_264], 0Bh
0x180006c2a  mov     [rsp+2B0h+var_260], 0FFh
0x180006c32  mov     [rbp+1B0h+var_1E0], 1000000h
0x180006c39  xor     edx, edx; Val
0x180006c3b  lea     r8d, [rdx+78h]; Size
0x180006c3f  lea     rcx, [rsp+2B0h+var_258]; void *
0x180006c44  call    memset_0
0x180006c49  mov     r9d, [rbx+1Ch]
0x180006c4d  lea     r8, aBadStateD_0; "Bad state %d"
0x180006c54  lea     rdx, [rsp+2B0h+var_280]
0x180006c59  lea     rcx, [rbp+1B0h+var_1D0]
0x180006c5d  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x180006c62  nop
0x180006c63  lea     rcx, [rbp+1B0h+var_1D0]; this
0x180006c67  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x180006c6c  mov     eax, 8000FFFFh
0x180006c71  lea     r11, [rsp+2B0h+var_10]
0x180006c79  mov     rbx, [r11+28h]
0x180006c7d  mov     r12, [r11+30h]
0x180006c81  mov     rsp, r11
0x180006c84  pop     r15
0x180006c86  pop     r13
0x180006c88  pop     rbp
0x180006c89  retn
```
