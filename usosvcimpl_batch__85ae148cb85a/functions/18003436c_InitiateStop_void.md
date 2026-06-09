# InitiateStop(void)

- ea: `0x18003436c`
- end: `0x1800343f3`
- name: `?InitiateStop@@YAXXZ`
- size: `135`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180034400`
- `0x180035350`

## callees

- `0x18003436c`
- `0x180037f8c`
- `0x180043f2c`
- `0x1800dd768`
- `0x1800dd930`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18003439d`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18003439d`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800343ca`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800343ca`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void InitiateStop(void)
{
  __int64 v0; // rdx
  __int64 v1; // rcx
  __int64 v2; // rdx
  __int64 v3; // rcx
  WINBOOL fPending; // [rsp+30h] [rbp-18h] BYREF

  fPending = 0;
  if ( !__std_init_once_begin_initialize(&InitOnce, 0, &fPending, 0) )
    abort();
  if ( fPending )
  {
    std::invoke__InitiateStop_::_2_::_lambda_1___(v1, v0);
    if ( !InitOnceComplete(&InitOnce, 0, 0) )
      _std_init_once_link_alternate_names_and_abort(v3, v2);
  }
}

```

## disassembly

```asm
0x18003436c  push    rbx
0x18003436e  sub     rsp, 40h
0x180034372  mov     rax, cs:__security_cookie
0x180034379  xor     rax, rsp
0x18003437c  mov     [rsp+48h+var_10], rax
0x180034381  mov     [rsp+48h+fPending], 0
0x180034389  xor     r9d, r9d; lpContext
0x18003438c  lea     r8, [rsp+48h+fPending]; fPending
0x180034391  xor     edx, edx; dwFlags
0x180034393  lea     rbx, InitOnce
0x18003439a  mov     rcx, rbx; lpInitOnce
0x18003439d  call    cs:__imp___std_init_once_begin_initialize
0x1800343a3  test    eax, eax
0x1800343a5  jz      short loc_1800343ED
0x1800343a7  cmp     [rsp+48h+fPending], 0
0x1800343ac  jz      short loc_1800343D4
0x1800343ae  mov     [rsp+48h+var_28], rbx
0x1800343b3  mov     [rsp+48h+var_20], 4
0x1800343bc  call    std__invoke__InitiateStop____2____lambda_1___
0x1800343c1  nop
0x1800343c2  xor     r8d, r8d; lpContext
0x1800343c5  xor     edx, edx; dwFlags
0x1800343c7  mov     rcx, rbx; lpInitOnce
0x1800343ca  call    cs:__imp_InitOnceComplete
0x1800343d0  test    eax, eax
0x1800343d2  jz      short loc_1800343E7
0x1800343d4  mov     rcx, [rsp+48h+var_10]
0x1800343d9  xor     rcx, rsp; StackCookie
0x1800343dc  call    __security_check_cookie
0x1800343e1  add     rsp, 40h
0x1800343e5  pop     rbx
0x1800343e6  retn
0x1800343e7  call    __std_init_once_link_alternate_names_and_abort
0x1800343ed  call    abort
```
