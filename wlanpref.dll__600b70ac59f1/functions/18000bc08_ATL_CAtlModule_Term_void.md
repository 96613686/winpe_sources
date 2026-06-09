# ATL::CAtlModule::Term(void)

- ea: `0x18000bc08`
- end: `0x18000bcba`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `178`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180003ed0`
- `0x18000bcc0`
- `0x18002f1d0`

## callees

- `0x1800012e8`
- `0x18000bc08`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000bc48`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000bc48`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000bca1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000bca1`

## pseudocode

```c
void __fastcall ATL::CAtlModule::Term(ATL::CAtlModule *this)
{
  unsigned __int64 v2; // r14
  __int64 v3; // rsi
  _QWORD *v4; // r15
  _QWORD *v5; // rbx
  __int64 v6; // rcx

  v2 = (unsigned __int64)this + 8;
  if ( *((_DWORD *)this + 2) )
  {
    if ( *((_QWORD *)this + 2) )
    {
      v3 = v2 & -(__int64)(this != 0);
      if ( !v3 )
      {
        RaiseException(0xC0000005, 1u, 0, 0);
        __debugbreak();
      }
      v4 = *(_QWORD **)((v2 & -(__int64)(this != 0)) + 8);
      if ( v4 )
      {
        do
        {
          ((void (__fastcall *)(_QWORD))*v4)(v4[1]);
          v5 = (_QWORD *)v4[2];
          operator delete(v4);
          v4 = v5;
        }
        while ( v5 );
      }
      *(_QWORD *)(v3 + 8) = 0;
      *((_QWORD *)this + 2) = 0;
    }
    v6 = *((_QWORD *)this + 8);
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    *(_DWORD *)v2 = 0;
  }
}

```

## disassembly

```asm
0x18000bc08  push    rbx
0x18000bc0a  push    rsi
0x18000bc0b  push    rdi
0x18000bc0c  push    r14
0x18000bc0e  push    r15
0x18000bc10  sub     rsp, 20h
0x18000bc14  mov     rdi, rcx
0x18000bc17  lea     r14, [rcx+8]
0x18000bc1b  cmp     dword ptr [r14], 0
0x18000bc1f  jz      loc_18000BCAE
0x18000bc25  cmp     qword ptr [rcx+10h], 0
0x18000bc2a  jz      short loc_18000BC88
0x18000bc2c  mov     rax, rcx
0x18000bc2f  neg     rax
0x18000bc32  sbb     rsi, rsi
0x18000bc35  and     rsi, r14
0x18000bc38  jnz     short loc_18000BC4F
0x18000bc3a  xor     r9d, r9d; lpArguments
0x18000bc3d  xor     r8d, r8d; nNumberOfArguments
0x18000bc40  lea     edx, [rsi+1]; dwExceptionFlags
0x18000bc43  mov     ecx, 0C0000005h; dwExceptionCode
0x18000bc48  call    cs:__imp_RaiseException
0x18000bc4e  int     3; Trap to Debugger
0x18000bc4f  mov     r15, [rsi+8]
0x18000bc53  test    r15, r15
0x18000bc56  jz      short loc_18000BC78
0x18000bc58  mov     rcx, [r15+8]
0x18000bc5c  mov     rax, [r15]
0x18000bc5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc64  mov     rbx, [r15+10h]
0x18000bc68  mov     rcx, r15; Block
0x18000bc6b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000bc70  mov     r15, rbx
0x18000bc73  test    rbx, rbx
0x18000bc76  jnz     short loc_18000BC58
0x18000bc78  mov     qword ptr [rsi+8], 0
0x18000bc80  mov     qword ptr [rdi+10h], 0
0x18000bc88  mov     rcx, [rdi+40h]
0x18000bc8c  test    rcx, rcx
0x18000bc8f  jz      short loc_18000BC9D
0x18000bc91  mov     rax, [rcx]
0x18000bc94  mov     rax, [rax+10h]
0x18000bc98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc9d  lea     rcx, [rdi+18h]; lpCriticalSection
0x18000bca1  call    cs:__imp_DeleteCriticalSection
0x18000bca7  mov     dword ptr [r14], 0
0x18000bcae  add     rsp, 20h
0x18000bcb2  pop     r15
0x18000bcb4  pop     r14
0x18000bcb6  pop     rdi
0x18000bcb7  pop     rsi
0x18000bcb8  pop     rbx
0x18000bcb9  retn
```
