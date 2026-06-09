# wil::init_once_nothrow__lambda_8df301ca4b310c9f46aab921282567ad___

- ea: `0x1800315fc`
- end: `0x18003169e`
- name: `wil::init_once_nothrow__lambda_8df301ca4b310c9f46aab921282567ad___`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180031430`

## callees

- `0x180014754`
- `0x1800315fc`
- `0x1800581b8`
- `0x1800a4d34`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18003161f`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18003161f`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18003167a`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180031690`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18003167a`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180031690`

## pseudocode

```c
__int64 __fastcall wil::init_once_nothrow__lambda_8df301ca4b310c9f46aab921282567ad___(
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
  if ( !InitOnceBeginInitialize(&InitOnce, 0, &fPending, 0) )
    return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0x37A, (unsigned int)"wil", v3);
  if ( fPending )
  {
    v5 = lambda_8df301ca4b310c9f46aab921282567ad_::operator()();
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
0x1800315fc  mov     qword ptr [rsp+fPending], r8
0x180031601  push    rbx; int
0x180031602  sub     rsp, 20h
0x180031606  xor     r9d, r9d; lpContext
0x180031609  mov     [rsp+28h+fPending], 0
0x180031611  lea     r8, [rsp+28h+fPending]; fPending
0x180031616  xor     edx, edx; dwFlags
0x180031618  lea     rcx, InitOnce; lpInitOnce
0x18003161f  call    cs:__imp_InitOnceBeginInitialize
0x180031625  test    eax, eax
0x180031627  jnz     short loc_180031641
0x180031629  mov     rcx, [rsp+28h]; this
0x18003162e  lea     r8, aWil; "wil"
0x180031635  mov     edx, 37Ah; void *
0x18003163a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003163f  jmp     short loc_180031698
0x180031641  cmp     [rsp+28h+fPending], 0
0x180031646  jz      short loc_180031696
0x180031648  call    _lambda_8df301ca4b310c9f46aab921282567ad___operator__
0x18003164d  mov     ebx, eax
0x18003164f  test    eax, eax
0x180031651  jns     short loc_180031684
0x180031653  mov     rcx, [rsp+28h]; this
0x180031658  lea     r8, aWil; "wil"
0x18003165f  mov     r9d, eax; char *
0x180031662  mov     edx, 37Fh; void *
0x180031667  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003166c  xor     r8d, r8d; lpContext
0x18003166f  lea     rcx, InitOnce; lpInitOnce
0x180031676  lea     edx, [r8+4]; dwFlags
0x18003167a  call    cs:__imp_InitOnceComplete
0x180031680  mov     eax, ebx
0x180031682  jmp     short loc_180031698
0x180031684  xor     r8d, r8d; lpContext
0x180031687  lea     rcx, InitOnce; lpInitOnce
0x18003168e  xor     edx, edx; dwFlags
0x180031690  call    cs:__imp_InitOnceComplete
0x180031696  xor     eax, eax
0x180031698  add     rsp, 20h
0x18003169c  pop     rbx
0x18003169d  retn
```
