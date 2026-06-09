# CVssWorkerThread::StartJob(void)

- ea: `0x180007148`
- end: `0x18000736d`
- name: `?StartJob@CVssWorkerThread@@QEAAJXZ`
- size: `549`
- prototype: `__int64 __fastcall(CVssWorkerThread *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180004c74`

## callees

- `0x18000212c`
- `0x180007148`
- `0x180033a8c`
- `0x180033c78`
- `0x180035f44`
- `0x1800367b8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800071ea`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800071ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800071fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007266`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800071fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007266`

## string_xrefs

- `0x180007175`: `CVssWorkerThread::StartJob`
- `0x18000724e`: `ResumeThread(%p) = -1, GetLastError() == 0x%08lx, m_eThreadState == %d`
- `0x1800072b3`: `ResumeThread failed. Error: 0x%08lx. State: %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVssWorkerThread::StartJob(CVssWorkerThread *this)
{
  void *v2; // rcx
  int v3; // edi
  DWORD LastError; // ebx
  int v5; // edi
  DWORD v6; // ebx
  DWORD v8; // [rsp+20h] [rbp-E0h]
  __int64 v9; // [rsp+20h] [rbp-E0h]
  int v10; // [rsp+28h] [rbp-D8h]
  const wchar_t *v11; // [rsp+30h] [rbp-D0h] BYREF
  const wchar_t *v12; // [rsp+38h] [rbp-C8h]
  const wchar_t *v13; // [rsp+40h] [rbp-C0h]
  int v14; // [rsp+48h] [rbp-B8h]
  int v15; // [rsp+4Ch] [rbp-B4h]
  int v16; // [rsp+50h] [rbp-B0h]
  _BYTE v17[120]; // [rsp+58h] [rbp-A8h] BYREF
  int v18; // [rsp+D0h] [rbp-30h]
  LPVOID v19[14]; // [rsp+E0h] [rbp-20h] BYREF

  v11 = L"base\\stor\\vss\\inc\\worker.hxx";
  v12 = L"CVssWorkerThread::StartJob";
  v13 = L"INCWORKH";
  v14 = 369;
  v15 = 1;
  v16 = 255;
  v18 = 0x1000000;
  memset_0(v17, 0, sizeof(v17));
  CVssFunctionTracer::CVssFunctionTracer((__int64)v19, (__int64)&v11, 0);
  v2 = (void *)*((_QWORD *)this + 2);
  if ( v2 && *((_DWORD *)this + 7) == 2 )
  {
    if ( ResumeThread(v2) == -1 )
    {
      v3 = *((_DWORD *)this + 7);
      LastError = GetLastError();
      v11 = L"base\\stor\\vss\\inc\\worker.hxx";
      v12 = L"CVssWorkerThread::StartJob";
      v13 = L"INCWORKH";
      v14 = 388;
      v15 = 11;
      v16 = 255;
      v18 = 0x1000000;
      memset_0(v17, 0, sizeof(v17));
      v10 = v3;
      v8 = LastError;
      CVssFunctionTracer::LogGenericWarning(
        v19,
        &v11,
        L"ResumeThread(%p) = -1, GetLastError() == 0x%08lx, m_eThreadState == %d",
        *((_QWORD *)this + 2),
        v8,
        v10);
      v5 = *((_DWORD *)this + 7);
      v6 = GetLastError();
      v11 = L"base\\stor\\vss\\inc\\worker.hxx";
      v12 = L"CVssWorkerThread::StartJob";
      v13 = L"INCWORKH";
      v14 = 391;
      v15 = 11;
      v16 = 255;
      v18 = 0x1000000;
      memset_0(v17, 0, sizeof(v17));
      LODWORD(v9) = v5;
      CVssFunctionTracer::Trace(v19, &v11, L"ResumeThread failed. Error: 0x%08lx. State: %d", v6, v9);
      *((_DWORD *)this + 7) = 5;
      CVssFunctionTracer::~CVssFunctionTracer(v19);
      return 2147942414LL;
    }
    else
    {
      *((_BYTE *)this + 32) = 1;
      CVssFunctionTracer::~CVssFunctionTracer(v19);
      return 0;
    }
  }
  else
  {
    v11 = L"base\\stor\\vss\\inc\\worker.hxx";
    v12 = L"CVssWorkerThread::StartJob";
    v13 = L"INCWORKH";
    v14 = 374;
    v15 = 11;
    v16 = 255;
    v18 = 0x1000000;
    memset_0(v17, 0, sizeof(v17));
    CVssFunctionTracer::Trace(v19, &v11, L"Bad state %d", *((unsigned int *)this + 7));
    CVssFunctionTracer::~CVssFunctionTracer(v19);
    return 2147549183LL;
  }
}

```

## disassembly

```asm
0x180007148  mov     [rsp-8+arg_8], rbx
0x18000714d  mov     [rsp-8+arg_10], rsi
0x180007152  push    rbp
0x180007153  push    rdi
0x180007154  push    r12
0x180007156  push    r13
0x180007158  push    r15
0x18000715a  lea     rbp, [rsp-50h]
0x18000715f  sub     rsp, 150h
0x180007166  mov     rsi, rcx
0x180007169  lea     r15, aBaseStorVssInc_0; "base\\stor\\vss\\inc\\worker.hxx"
0x180007170  mov     [rsp+170h+var_140], r15
0x180007175  lea     r12, aCvssworkerthre_1; "CVssWorkerThread::StartJob"
0x18000717c  mov     [rsp+170h+var_138], r12
0x180007181  lea     r13, aIncworkh; "INCWORKH"
0x180007188  mov     [rsp+170h+var_130], r13
0x18000718d  mov     [rsp+170h+var_128], 171h
0x180007195  mov     [rsp+170h+var_124], 1
0x18000719d  mov     ebx, 0FFh
0x1800071a2  mov     [rsp+170h+var_120], ebx
0x1800071a6  mov     [rbp+70h+var_A0], 1000000h
0x1800071ad  mov     edi, 78h ; 'x'
0x1800071b2  mov     r8d, edi; Size
0x1800071b5  xor     edx, edx; Val
0x1800071b7  lea     rcx, [rsp+170h+var_118]; void *
0x1800071bc  call    memset_0
0x1800071c1  xor     r8d, r8d
0x1800071c4  lea     rdx, [rsp+170h+var_140]
0x1800071c9  lea     rcx, [rbp+70h+var_90]
0x1800071cd  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x1800071d2  nop
0x1800071d3  mov     rcx, [rsi+10h]; hThread
0x1800071d7  test    rcx, rcx
0x1800071da  jz      loc_1800072F0
0x1800071e0  cmp     dword ptr [rsi+1Ch], 2
0x1800071e4  jnz     loc_1800072F0
0x1800071ea  call    cs:__imp_ResumeThread
0x1800071f0  cmp     eax, 0FFFFFFFFh
0x1800071f3  jnz     loc_1800072DF
0x1800071f9  mov     edi, [rsi+1Ch]
0x1800071fc  call    cs:__imp_GetLastError
0x180007202  mov     ebx, eax
0x180007204  mov     [rsp+170h+var_140], r15
0x180007209  mov     [rsp+170h+var_138], r12
0x18000720e  mov     [rsp+170h+var_130], r13
0x180007213  mov     [rsp+170h+var_128], 184h
0x18000721b  mov     [rsp+170h+var_124], 0Bh
0x180007223  mov     [rsp+170h+var_120], 0FFh
0x18000722b  mov     [rbp+70h+var_A0], 1000000h
0x180007232  xor     edx, edx; Val
0x180007234  lea     r8d, [rdx+78h]; Size
0x180007238  lea     rcx, [rsp+170h+var_118]; void *
0x18000723d  call    memset_0
0x180007242  mov     [rsp+170h+var_148], edi
0x180007246  mov     dword ptr [rsp+170h+var_150], ebx
0x18000724a  mov     r9, [rsi+10h]
0x18000724e  lea     r8, aResumethreadP1; "ResumeThread(%p) = -1, GetLastError() ="...
0x180007255  lea     rdx, [rsp+170h+var_140]
0x18000725a  lea     rcx, [rbp+70h+var_90]
0x18000725e  call    ?LogGenericWarning@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::LogGenericWarning(CVssDebugInfo,ushort const *,...)
0x180007263  mov     edi, [rsi+1Ch]
0x180007266  call    cs:__imp_GetLastError
0x18000726c  mov     ebx, eax
0x18000726e  mov     [rsp+170h+var_140], r15
0x180007273  mov     [rsp+170h+var_138], r12
0x180007278  mov     [rsp+170h+var_130], r13
0x18000727d  mov     [rsp+170h+var_128], 187h
0x180007285  mov     [rsp+170h+var_124], 0Bh
0x18000728d  mov     [rsp+170h+var_120], 0FFh
0x180007295  mov     [rbp+70h+var_A0], 1000000h
0x18000729c  xor     edx, edx; Val
0x18000729e  lea     r8d, [rdx+78h]; Size
0x1800072a2  lea     rcx, [rsp+170h+var_118]; void *
0x1800072a7  call    memset_0
0x1800072ac  mov     dword ptr [rsp+170h+var_150], edi
0x1800072b0  mov     r9d, ebx
0x1800072b3  lea     r8, aResumethreadFa; "ResumeThread failed. Error: 0x%08lx. St"...
0x1800072ba  lea     rdx, [rsp+170h+var_140]
0x1800072bf  lea     rcx, [rbp+70h+var_90]
0x1800072c3  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x1800072c8  mov     dword ptr [rsi+1Ch], 5
0x1800072cf  lea     rcx, [rbp+70h+var_90]; this
0x1800072d3  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x1800072d8  mov     eax, 8007000Eh
0x1800072dd  jmp     short loc_180007351
0x1800072df  mov     byte ptr [rsi+20h], 1
0x1800072e3  lea     rcx, [rbp+70h+var_90]; this
0x1800072e7  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x1800072ec  xor     eax, eax
0x1800072ee  jmp     short loc_180007351
0x1800072f0  mov     [rsp+170h+var_140], r15
0x1800072f5  mov     [rsp+170h+var_138], r12
0x1800072fa  mov     [rsp+170h+var_130], r13
0x1800072ff  mov     [rsp+170h+var_128], 176h
0x180007307  mov     [rsp+170h+var_124], 0Bh
0x18000730f  mov     [rsp+170h+var_120], ebx
0x180007313  mov     [rbp+70h+var_A0], 1000000h
0x18000731a  mov     r8, rdi; Size
0x18000731d  xor     edx, edx; Val
0x18000731f  lea     rcx, [rsp+170h+var_118]; void *
0x180007324  call    memset_0
0x180007329  mov     r9d, [rsi+1Ch]
0x18000732d  lea     r8, aBadStateD_0; "Bad state %d"
0x180007334  lea     rdx, [rsp+170h+var_140]
0x180007339  lea     rcx, [rbp+70h+var_90]
0x18000733d  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x180007342  nop
0x180007343  lea     rcx, [rbp+70h+var_90]; this
0x180007347  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x18000734c  mov     eax, 8000FFFFh
0x180007351  lea     r11, [rsp+170h+var_20]
0x180007359  mov     rbx, [r11+38h]
0x18000735d  mov     rsi, [r11+40h]
0x180007361  mov     rsp, r11
0x180007364  pop     r15
0x180007366  pop     r13
0x180007368  pop     r12
0x18000736a  pop     rdi
0x18000736b  pop     rbp
0x18000736c  retn
```
