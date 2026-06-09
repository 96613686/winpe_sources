# wil::init_once_nothrow__lambda_bcf300600359ba7ed7b15fae2fa007a0___

- ea: `0x1401aebbc`
- end: `0x1401aec89`
- name: `wil::init_once_nothrow__lambda_bcf300600359ba7ed7b15fae2fa007a0___`
- size: `205`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400844c8`

## callees

- `0x1400b42d0`
- `0x1400d6a94`
- `0x140132960`
- `0x1401aebbc`
- `0x1401af3e8`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1401aec4b`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1401aec67`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1401aec4b`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1401aec67`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1401aebea`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1401aebea`

## pseudocode

```c
__int64 wil::init_once_nothrow__lambda_bcf300600359ba7ed7b15fae2fa007a0___()
{
  const char *v0; // r9
  int v2; // eax
  unsigned int v3; // ebx
  WINBOOL fPending; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  fPending = 0;
  if ( !InitOnceBeginInitialize(&InitOnce, 0, &fPending, 0) )
    return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0x37A, (unsigned int)"wil", v0);
  if ( fPending )
  {
    v2 = lambda_bcf300600359ba7ed7b15fae2fa007a0_::operator()();
    v3 = v2;
    if ( v2 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x37F,
        (unsigned int)"wil",
        (const char *)(unsigned int)v2,
        fPending);
      InitOnceComplete(&InitOnce, 4u, 0);
      return v3;
    }
    InitOnceComplete(&InitOnce, 0, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x1401aebbc  push    rbx
0x1401aebbe  sub     rsp, 30h
0x1401aebc2  mov     rax, cs:__security_cookie
0x1401aebc9  xor     rax, rsp
0x1401aebcc  mov     [rsp+38h+var_10], rax
0x1401aebd1  mov     [rsp+38h+fPending], 0; int
0x1401aebd9  xor     r9d, r9d; lpContext
0x1401aebdc  lea     r8, [rsp+38h+fPending]; fPending
0x1401aebe1  xor     edx, edx; dwFlags
0x1401aebe3  lea     rcx, InitOnce; lpInitOnce
0x1401aebea  call    cs:__imp_InitOnceBeginInitialize
0x1401aebf1  nop     dword ptr [rax+rax+00h]
0x1401aebf6  test    eax, eax
0x1401aebf8  jnz     short loc_1401AEC12
0x1401aebfa  mov     rcx, [rsp+38h]; this
0x1401aebff  lea     r8, aWil; "wil"
0x1401aec06  mov     edx, 37Ah; void *
0x1401aec0b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1401aec10  jmp     short loc_1401AEC75
0x1401aec12  cmp     [rsp+38h+fPending], 0
0x1401aec17  jz      short loc_1401AEC73
0x1401aec19  call    _lambda_bcf300600359ba7ed7b15fae2fa007a0___operator__
0x1401aec1e  mov     ebx, eax
0x1401aec20  test    eax, eax
0x1401aec22  jns     short loc_1401AEC5B
0x1401aec24  mov     rcx, [rsp+38h]; this
0x1401aec29  mov     r9d, eax; char *
0x1401aec2c  lea     r8, aWil; "wil"
0x1401aec33  mov     edx, 37Fh; void *
0x1401aec38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1401aec3d  xor     r8d, r8d; lpContext
0x1401aec40  lea     edx, [r8+4]; dwFlags
0x1401aec44  lea     rcx, InitOnce; lpInitOnce
0x1401aec4b  call    cs:__imp_InitOnceComplete
0x1401aec52  nop     dword ptr [rax+rax+00h]
0x1401aec57  mov     eax, ebx
0x1401aec59  jmp     short loc_1401AEC75
0x1401aec5b  xor     r8d, r8d; lpContext
0x1401aec5e  xor     edx, edx; dwFlags
0x1401aec60  lea     rcx, InitOnce; lpInitOnce
0x1401aec67  call    cs:__imp_InitOnceComplete
0x1401aec6e  nop     dword ptr [rax+rax+00h]
0x1401aec73  xor     eax, eax
0x1401aec75  mov     rcx, [rsp+38h+var_10]
0x1401aec7a  xor     rcx, rsp; StackCookie
0x1401aec7d  call    __security_check_cookie
0x1401aec82  add     rsp, 30h
0x1401aec86  pop     rbx
0x1401aec87  retn
```
