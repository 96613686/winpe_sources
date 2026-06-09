# CEcsThreadPool::Initialize(void)

- ea: `0x18004414c`
- end: `0x180044289`
- name: `?Initialize@CEcsThreadPool@@QEAAXXZ`
- size: `317`
- prototype: `void __fastcall(CEcsThreadPool *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800421c4`

## callees

- `0x180003604`
- `0x180007b9c`
- `0x180007e10`
- `0x180042e28`
- `0x18004414c`

## import_xrefs

- `KERNEL32!CreateThreadpool` at `0x1800441cc`
- `KERNEL32!CreateThreadpool` at `0x1800441cc`
- `KERNEL32!CreateThreadpoolCleanupGroup` at `0x18004417f`
- `KERNEL32!CreateThreadpoolCleanupGroup` at `0x18004417f`

## string_xrefs

- `0x18004416e`: `CEcsThreadPool::Initialize`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CEcsThreadPool::Initialize(CEcsThreadPool *this)
{
  CEcsThreadPool *v1; // rdi
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  PTP_POOL Threadpool; // rdx
  int pExceptionObject; // [rsp+20h] [rbp-48h] BYREF
  int v5; // [rsp+24h] [rbp-44h] BYREF
  int v6; // [rsp+28h] [rbp-40h] BYREF
  int v7; // [rsp+2Ch] [rbp-3Ch] BYREF
  const ATL::CAtlException *v8; // [rsp+30h] [rbp-38h] BYREF
  int LastFailureAsHRESULT; // [rsp+38h] [rbp-30h] BYREF
  int v10; // [rsp+3Ch] [rbp-2Ch]
  char v11; // [rsp+40h] [rbp-28h]
  const char *v12; // [rsp+48h] [rbp-20h]
  __int64 v13; // [rsp+50h] [rbp-18h]

  v1 = this;
  LastFailureAsHRESULT = 0;
  v10 = 70;
  v11 = 0;
  v12 = "CEcsThreadPool::Initialize";
  v13 = 0;
  try
  {
    ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
    *((_QWORD *)v1 + 1) = ThreadpoolCleanupGroup;
    if ( !ThreadpoolCleanupGroup )
    {
      LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
      HIWORD(v10) = 81;
      pExceptionObject = LastFailureAsHRESULT;
      throw (long *)&pExceptionObject;
    }
    LastFailureAsHRESULT = 0;
    LOWORD(v10) = 81;
    Threadpool = CreateThreadpool(0);
    *(_QWORD *)v1 = Threadpool;
    if ( !Threadpool )
    {
      LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
      HIWORD(v10) = 84;
      v5 = LastFailureAsHRESULT;
      throw (long *)&v5;
    }
    LastFailureAsHRESULT = 0;
    LOWORD(v10) = 84;
    *((_QWORD *)v1 + 4) = *((_QWORD *)v1 + 1);
    *((_QWORD *)v1 + 5) = 0;
    *((_QWORD *)v1 + 3) = Threadpool;
  }
  catch ( long v7 )
  {
    LastFailureAsHRESULT = v7;
    v1 = this;
  }
  catch ( std::bad_alloc )
  {
    HIWORD(v10) = 91;
    LastFailureAsHRESULT = -2147024882;
    v1 = this;
  }
  catch ( std::exception )
  {
    HIWORD(v10) = 91;
    LastFailureAsHRESULT = -2147418113;
    v1 = this;
  }
  catch ( const ATL::CAtlException *v8 )
  {
    HIWORD(v10) = 91;
    LastFailureAsHRESULT = *(_DWORD *)v8;
    v1 = this;
  }
  if ( LastFailureAsHRESULT < 0 )
  {
    CEcsThreadPool::Cleanup(v1);
    HIWORD(v10) = 96;
    v6 = LastFailureAsHRESULT;
    throw (long *)&v6;
  }
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&LastFailureAsHRESULT);
}

```

## disassembly

```asm
0x18004414c  mov     rax, rsp
0x18004414f  mov     [rax+10h], rbx
0x180044153  mov     [rax+8], rcx
0x180044157  push    rdi
0x180044158  sub     rsp, 60h
0x18004415c  mov     rdi, rcx
0x18004415f  xor     ebx, ebx
0x180044161  mov     [rax-30h], ebx
0x180044164  mov     dword ptr [rax-2Ch], 46h ; 'F'
0x18004416b  mov     [rax-28h], bl
0x18004416e  lea     rax, aCecsthreadpool; "CEcsThreadPool::Initialize"
0x180044175  mov     [rsp+68h+var_20], rax
0x18004417a  mov     [rsp+68h+var_18], rbx
0x18004417f  call    cs:__imp_CreateThreadpoolCleanupGroup
0x180044185  mov     [rdi+8], rax
0x180044189  mov     ecx, [rsp+68h+var_30]
0x18004418d  mov     [rsp+68h+var_30], ecx
0x180044191  test    rax, rax
0x180044194  jnz     short loc_1800441BC
0x180044196  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x18004419b  mov     [rsp+68h+var_30], eax
0x18004419f  lea     ecx, [rbx+51h]
0x1800441a2  mov     [rsp+68h+var_2A], cx
0x1800441a7  mov     [rsp+68h+pExceptionObject], eax
0x1800441ab  lea     rdx, _TI1J; pThrowInfo
0x1800441b2  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x1800441b7  call    _CxxThrowException_0
0x1800441bc  mov     [rsp+68h+var_30], ebx
0x1800441c0  mov     ecx, 51h ; 'Q'
0x1800441c5  mov     [rsp+68h+var_2C], cx
0x1800441ca  xor     ecx, ecx; reserved
0x1800441cc  call    cs:__imp_CreateThreadpool
0x1800441d2  mov     rdx, rax
0x1800441d5  mov     [rdi], rax
0x1800441d8  mov     ecx, [rsp+68h+var_30]
0x1800441dc  mov     [rsp+68h+var_30], ecx
0x1800441e0  test    rax, rax
0x1800441e3  jnz     short loc_18004420D
0x1800441e5  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x1800441ea  mov     [rsp+68h+var_30], eax
0x1800441ee  mov     ecx, 54h ; 'T'
0x1800441f3  mov     [rsp+68h+var_2A], cx
0x1800441f8  mov     [rsp+68h+var_44], eax
0x1800441fc  lea     rdx, _TI1J; pThrowInfo
0x180044203  lea     rcx, [rsp+68h+var_44]; pExceptionObject
0x180044208  call    _CxxThrowException_0
0x18004420d  mov     [rsp+68h+var_30], ebx
0x180044211  mov     ecx, 54h ; 'T'
0x180044216  mov     [rsp+68h+var_2C], cx
0x18004421b  mov     rax, [rdi+8]
0x18004421f  mov     [rdi+20h], rax
0x180044223  mov     [rdi+28h], rbx
0x180044227  mov     [rdi+18h], rdx
0x18004422b  jmp     short loc_18004423A
0x18004422d  jmp     short loc_180044233
0x18004422f  jmp     short loc_180044233
0x180044231  jmp     short $+2
0x180044233  mov     rdi, [rsp+68h+arg_0]
0x180044238  xor     ebx, ebx
0x18004423a  cmp     [rsp+68h+var_30], ebx
0x18004423e  jge     short loc_180044274
0x180044240  mov     rcx, rdi; this
0x180044243  call    ?Cleanup@CEcsThreadPool@@QEAAX_N@Z; CEcsThreadPool::Cleanup(bool)
0x180044248  mov     eax, [rsp+68h+var_30]
0x18004424c  mov     [rsp+68h+var_30], eax
0x180044250  mov     [rsp+68h+var_30], eax
0x180044254  mov     ecx, 60h ; '`'
0x180044259  mov     [rsp+68h+var_2A], cx
0x18004425e  mov     [rsp+68h+var_40], eax
0x180044262  lea     rdx, _TI1J; pThrowInfo
0x180044269  lea     rcx, [rsp+68h+var_40]; pExceptionObject
0x18004426e  call    _CxxThrowException_0
0x180044274  lea     rcx, [rsp+68h+var_30]; this
0x180044279  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x18004427e  mov     rbx, [rsp+68h+arg_8]
0x180044283  add     rsp, 60h
0x180044287  pop     rdi
0x180044288  retn
```
