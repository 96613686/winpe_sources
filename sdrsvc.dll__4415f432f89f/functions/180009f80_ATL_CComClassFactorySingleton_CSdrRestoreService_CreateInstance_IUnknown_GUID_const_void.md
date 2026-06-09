# ATL::CComClassFactorySingleton<CSdrRestoreService>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180009f80`
- end: `0x18000a075`
- name: `?CreateInstance@?$CComClassFactorySingleton@VCSdrRestoreService@@@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `245`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180001554`
- `0x180008a80`
- `0x180009f80`
- `0x18000a8fc`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a041`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a041`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021b3c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009fd7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009fd7`

## pseudocode

```c
__int64 __fastcall ATL::CComClassFactorySingleton<CSdrRestoreService>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  __int64 result; // rax
  _QWORD *v8; // rsi
  int v9; // eax
  CSdrRestoreService *v10; // rdi
  int v11; // eax
  void *Block; // [rsp+68h] [rbp+20h] BYREF

  result = 2147500035LL;
  if ( a4 )
  {
    *a4 = 0;
    if ( a2 )
    {
      return 2147746064LL;
    }
    else
    {
      if ( !*(_DWORD *)(a1 + 72) )
      {
        v8 = (_QWORD *)(a1 + 80);
        if ( !*(_QWORD *)(a1 + 80) )
        {
          EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
          if ( !*(_DWORD *)(a1 + 72) && !*v8 )
          {
            Block = 0;
            v9 = ATL::CComObjectCached<CSdrRestoreService>::CreateInstance(&Block);
            *(_DWORD *)(a1 + 72) = v9;
            if ( v9 >= 0 )
            {
              v10 = (CSdrRestoreService *)Block;
              v11 = (**(__int64 (__fastcall ***)(void *, GUID *, _QWORD *))Block)(Block, &IID_IUnknown, v8);
              *(_DWORD *)(a1 + 72) = v11;
              if ( v11 < 0 )
              {
                if ( v10 )
                {
                  ATL::CComObjectCached<CSdrRestoreService>::~CComObjectCached<CSdrRestoreService>(v10);
                  operator delete(v10);
                }
              }
            }
          }
          LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
        }
      }
      result = *(unsigned int *)(a1 + 72);
      if ( !(_DWORD)result )
        return (***(__int64 (__fastcall ****)(_QWORD, __int64, _QWORD *))(a1 + 80))(*(_QWORD *)(a1 + 80), a3, a4);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180009f80  mov     [rsp+arg_8], rbx
0x180009f85  mov     [rsp+arg_0], rcx
0x180009f8a  push    rsi
0x180009f8b  push    rdi
0x180009f8c  push    r12
0x180009f8e  push    r14
0x180009f90  push    r15
0x180009f92  sub     rsp, 20h
0x180009f96  mov     r14, r9
0x180009f99  mov     r12, r8
0x180009f9c  mov     rbx, rcx
0x180009f9f  mov     eax, 80004003h
0x180009fa4  test    r9, r9
0x180009fa7  jz      loc_18000A063
0x180009fad  mov     qword ptr [r9], 0
0x180009fb4  test    rdx, rdx
0x180009fb7  jz      short loc_180009FC3
0x180009fb9  mov     eax, 80040110h
0x180009fbe  jmp     loc_18000A063
0x180009fc3  cmp     dword ptr [rcx+48h], 0
0x180009fc7  jnz     short loc_18000A047
0x180009fc9  lea     rsi, [rcx+50h]
0x180009fcd  cmp     qword ptr [rsi], 0
0x180009fd1  jnz     short loc_18000A047
0x180009fd3  add     rcx, 10h; lpCriticalSection
0x180009fd7  call    cs:__imp_EnterCriticalSection
0x180009fdd  cmp     dword ptr [rbx+48h], 0
0x180009fe1  jnz     short loc_18000A03D
0x180009fe3  cmp     qword ptr [rsi], 0
0x180009fe7  jnz     short loc_18000A03D
0x180009fe9  mov     [rsp+48h+Block], 0
0x180009ff2  lea     rcx, [rsp+48h+Block]
0x180009ff7  call    ?CreateInstance@?$CComObjectCached@VCSdrRestoreService@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObjectCached<CSdrRestoreService>::CreateInstance(ATL::CComObjectCached<CSdrRestoreService> * *)
0x180009ffc  mov     [rbx+48h], eax
0x180009fff  test    eax, eax
0x18000a001  js      short loc_18000A03D
0x18000a003  mov     rdi, [rsp+48h+Block]
0x18000a008  mov     rax, [rdi]
0x18000a00b  mov     r8, rsi
0x18000a00e  lea     rdx, IID_IUnknown
0x18000a015  mov     rcx, rdi
0x18000a018  mov     rax, [rax]
0x18000a01b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a020  mov     [rbx+48h], eax
0x18000a023  test    eax, eax
0x18000a025  jns     short loc_18000A03D
0x18000a027  test    rdi, rdi
0x18000a02a  jz      short loc_18000A03D
0x18000a02c  mov     rcx, rdi
0x18000a02f  call    ??1?$CComObjectCached@VCSdrRestoreService@@@ATL@@QEAA@XZ; ATL::CComObjectCached<CSdrRestoreService>::~CComObjectCached<CSdrRestoreService>(void)
0x18000a034  mov     rcx, rdi; Block
0x18000a037  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a03c  nop
0x18000a03d  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000a041  call    cs:__imp_LeaveCriticalSection
0x18000a047  mov     eax, [rbx+48h]
0x18000a04a  test    eax, eax
0x18000a04c  jnz     short loc_18000A063
0x18000a04e  mov     rcx, [rbx+50h]
0x18000a052  mov     rax, [rcx]
0x18000a055  mov     r8, r14
0x18000a058  mov     rdx, r12
0x18000a05b  mov     rax, [rax]
0x18000a05e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a063  mov     rbx, [rsp+48h+arg_8]
0x18000a068  add     rsp, 20h
0x18000a06c  pop     r15
0x18000a06e  pop     r14
0x18000a070  pop     r12
0x18000a072  pop     rdi
0x18000a073  pop     rsi
0x18000a074  retn
0x180021b26  push    rbp
0x180021b28  sub     rsp, 20h
0x180021b2c  mov     rbp, rdx
0x180021b2f  mov     rcx, [rbp+50h]
0x180021b33  add     rcx, 10h
0x180021b37  add     rsp, 20h
0x180021b3b  pop     rbp
0x180021b3c  jmp     cs:__imp_LeaveCriticalSection
```
