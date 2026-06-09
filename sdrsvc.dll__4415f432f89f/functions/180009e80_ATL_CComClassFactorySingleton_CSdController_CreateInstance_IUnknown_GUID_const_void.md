# ATL::CComClassFactorySingleton<CSdController>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180009e80`
- end: `0x180009f75`
- name: `?CreateInstance@?$CComClassFactorySingleton@VCSdController@@@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `245`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001554`
- `0x180008a40`
- `0x180009e80`
- `0x18000a7a8`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009f41`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009f41`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009ed7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009ed7`

## pseudocode

```c
__int64 __fastcall ATL::CComClassFactorySingleton<CSdController>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  __int64 result; // rax
  _QWORD *v8; // rsi
  int v9; // eax
  CSdController *v10; // rdi
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
            v9 = ATL::CComObjectCached<CSdController>::CreateInstance(&Block);
            *(_DWORD *)(a1 + 72) = v9;
            if ( v9 >= 0 )
            {
              v10 = (CSdController *)Block;
              v11 = (**(__int64 (__fastcall ***)(void *, GUID *, _QWORD *))Block)(Block, &IID_IUnknown, v8);
              *(_DWORD *)(a1 + 72) = v11;
              if ( v11 < 0 )
              {
                if ( v10 )
                {
                  ATL::CComObjectCached<CSdController>::~CComObjectCached<CSdController>(v10);
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
0x180009e80  mov     [rsp+arg_8], rbx
0x180009e85  mov     [rsp+arg_0], rcx
0x180009e8a  push    rsi
0x180009e8b  push    rdi
0x180009e8c  push    r12
0x180009e8e  push    r14
0x180009e90  push    r15
0x180009e92  sub     rsp, 20h
0x180009e96  mov     r14, r9
0x180009e99  mov     r12, r8
0x180009e9c  mov     rbx, rcx
0x180009e9f  mov     eax, 80004003h
0x180009ea4  test    r9, r9
0x180009ea7  jz      loc_180009F63
0x180009ead  mov     qword ptr [r9], 0
0x180009eb4  test    rdx, rdx
0x180009eb7  jz      short loc_180009EC3
0x180009eb9  mov     eax, 80040110h
0x180009ebe  jmp     loc_180009F63
0x180009ec3  cmp     dword ptr [rcx+48h], 0
0x180009ec7  jnz     short loc_180009F47
0x180009ec9  lea     rsi, [rcx+50h]
0x180009ecd  cmp     qword ptr [rsi], 0
0x180009ed1  jnz     short loc_180009F47
0x180009ed3  add     rcx, 10h; lpCriticalSection
0x180009ed7  call    cs:__imp_EnterCriticalSection
0x180009edd  cmp     dword ptr [rbx+48h], 0
0x180009ee1  jnz     short loc_180009F3D
0x180009ee3  cmp     qword ptr [rsi], 0
0x180009ee7  jnz     short loc_180009F3D
0x180009ee9  mov     [rsp+48h+Block], 0
0x180009ef2  lea     rcx, [rsp+48h+Block]
0x180009ef7  call    ?CreateInstance@?$CComObjectCached@VCSdController@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObjectCached<CSdController>::CreateInstance(ATL::CComObjectCached<CSdController> * *)
0x180009efc  mov     [rbx+48h], eax
0x180009eff  test    eax, eax
0x180009f01  js      short loc_180009F3D
0x180009f03  mov     rdi, [rsp+48h+Block]
0x180009f08  mov     rax, [rdi]
0x180009f0b  mov     r8, rsi
0x180009f0e  lea     rdx, IID_IUnknown
0x180009f15  mov     rcx, rdi
0x180009f18  mov     rax, [rax]
0x180009f1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f20  mov     [rbx+48h], eax
0x180009f23  test    eax, eax
0x180009f25  jns     short loc_180009F3D
0x180009f27  test    rdi, rdi
0x180009f2a  jz      short loc_180009F3D
0x180009f2c  mov     rcx, rdi; this
0x180009f2f  call    ??1?$CComObjectCached@VCSdController@@@ATL@@QEAA@XZ; ATL::CComObjectCached<CSdController>::~CComObjectCached<CSdController>(void)
0x180009f34  mov     rcx, rdi; Block
0x180009f37  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009f3c  nop
0x180009f3d  lea     rcx, [rbx+10h]; lpCriticalSection
0x180009f41  call    cs:__imp_LeaveCriticalSection
0x180009f47  mov     eax, [rbx+48h]
0x180009f4a  test    eax, eax
0x180009f4c  jnz     short loc_180009F63
0x180009f4e  mov     rcx, [rbx+50h]
0x180009f52  mov     rax, [rcx]
0x180009f55  mov     r8, r14
0x180009f58  mov     rdx, r12
0x180009f5b  mov     rax, [rax]
0x180009f5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f63  mov     rbx, [rsp+48h+arg_8]
0x180009f68  add     rsp, 20h
0x180009f6c  pop     r15
0x180009f6e  pop     r14
0x180009f70  pop     r12
0x180009f72  pop     rdi
0x180009f73  pop     rsi
0x180009f74  retn
0x180021b26  push    rbp
0x180021b28  sub     rsp, 20h
0x180021b2c  mov     rbp, rdx
0x180021b2f  mov     rcx, [rbp+50h]
0x180021b33  add     rcx, 10h
0x180021b37  add     rsp, 20h
0x180021b3b  pop     rbp
0x180021b3c  jmp     cs:__imp_LeaveCriticalSection
```
