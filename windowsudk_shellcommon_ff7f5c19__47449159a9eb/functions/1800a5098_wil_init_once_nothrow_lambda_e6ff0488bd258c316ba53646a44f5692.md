# wil::init_once_nothrow__lambda_e6ff0488bd258c316ba53646a44f5692___

- ea: `0x1800a5098`
- end: `0x1800a513a`
- name: `wil::init_once_nothrow__lambda_e6ff0488bd258c316ba53646a44f5692___`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800bd7f0`

## callees

- `0x1800a5098`
- `0x1800e2988`
- `0x1800e34bc`
- `0x1803027b0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800a5116`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800a512c`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800a5116`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800a512c`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800a50bb`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800a50bb`

## pseudocode

```c
__int64 __fastcall wil::init_once_nothrow__lambda_e6ff0488bd258c316ba53646a44f5692___(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  const char *v3; // r9
  int v5; // eax
  unsigned int v6; // ebx
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  WINBOOL fPending; // [rsp+40h] [rbp+18h] BYREF
  int v10; // [rsp+44h] [rbp+1Ch]

  v10 = HIDWORD(a3);
  fPending = 0;
  if ( !__std_init_once_begin_initialize(&InitOnce, 0, &fPending, 0) )
    return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0x37A, (unsigned int)"wil", v3);
  if ( fPending )
  {
    v5 = lambda_e6ff0488bd258c316ba53646a44f5692_::operator()();
    v6 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x37F, (unsigned int)"wil", (const char *)(unsigned int)v5, v7);
      InitOnceComplete(&InitOnce, 4u, 0);
      return v6;
    }
    InitOnceComplete(&InitOnce, 0, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x1800a5098  mov     qword ptr [rsp+fPending], r8
0x1800a509d  push    rbx; int
0x1800a509e  sub     rsp, 20h
0x1800a50a2  mov     [rsp+28h+fPending], 0
0x1800a50aa  xor     r9d, r9d; lpContext
0x1800a50ad  lea     r8, [rsp+28h+fPending]; fPending
0x1800a50b2  xor     edx, edx; dwFlags
0x1800a50b4  lea     rcx, InitOnce; lpInitOnce
0x1800a50bb  call    cs:__imp___std_init_once_begin_initialize
0x1800a50c1  test    eax, eax
0x1800a50c3  jnz     short loc_1800A50DD
0x1800a50c5  mov     rcx, [rsp+28h]; this
0x1800a50ca  lea     r8, aWil; "wil"
0x1800a50d1  mov     edx, 37Ah; void *
0x1800a50d6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a50db  jmp     short loc_1800A5134
0x1800a50dd  cmp     [rsp+28h+fPending], 0
0x1800a50e2  jz      short loc_1800A5132
0x1800a50e4  call    _lambda_e6ff0488bd258c316ba53646a44f5692___operator__
0x1800a50e9  mov     ebx, eax
0x1800a50eb  test    eax, eax
0x1800a50ed  jns     short loc_1800A5120
0x1800a50ef  mov     rcx, [rsp+28h]; this
0x1800a50f4  mov     r9d, eax; char *
0x1800a50f7  lea     r8, aWil; "wil"
0x1800a50fe  mov     edx, 37Fh; void *
0x1800a5103  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a5108  xor     r8d, r8d; lpContext
0x1800a510b  lea     edx, [r8+4]; dwFlags
0x1800a510f  lea     rcx, InitOnce; lpInitOnce
0x1800a5116  call    cs:__imp_InitOnceComplete
0x1800a511c  mov     eax, ebx
0x1800a511e  jmp     short loc_1800A5134
0x1800a5120  xor     r8d, r8d; lpContext
0x1800a5123  xor     edx, edx; dwFlags
0x1800a5125  lea     rcx, InitOnce; lpInitOnce
0x1800a512c  call    cs:__imp_InitOnceComplete
0x1800a5132  xor     eax, eax
0x1800a5134  add     rsp, 20h
0x1800a5138  pop     rbx
0x1800a5139  retn
```
