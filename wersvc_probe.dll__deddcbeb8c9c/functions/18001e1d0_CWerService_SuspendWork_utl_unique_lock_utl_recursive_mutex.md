# CWerService::_SuspendWork(utl::unique_lock<utl::recursive_mutex> &)

- ea: `0x18001e1d0`
- end: `0x18001e290`
- name: `?_SuspendWork@CWerService@@AEAAJAEAV?$unique_lock@Vrecursive_mutex@utl@@@utl@@@Z`
- size: `192`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180018950`
- `0x18001e054`

## callees

- `0x180006a80`
- `0x180011ef8`
- `0x18001c258`
- `0x18001e1d0`
- `0x180025a0c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e261`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e261`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e278`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e278`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWerService::_SuspendWork(__int64 a1, __int64 a2)
{
  int v4; // eax
  unsigned int v5; // ebx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids);
  v4 = CWerService::_CleanupLpcServer(a1, a2);
  v5 = v4;
  if ( v4 >= 0 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 416));
    CHangrepServer::_Cleanup((CHangrepServer *)(a1 + 416));
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 416));
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        57,
        &WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids,
        (unsigned int)v4);
    return v5;
  }
}

```

## disassembly

```asm
0x18001e1d0  mov     [rsp+arg_0], rbx
0x18001e1d5  mov     [rsp+arg_8], rsi
0x18001e1da  push    rdi
0x18001e1db  sub     rsp, 30h
0x18001e1df  mov     rbx, rdx
0x18001e1e2  mov     rdi, rcx
0x18001e1e5  lea     rsi, WPP_GLOBAL_Control
0x18001e1ec  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e1f3  cmp     rcx, rsi
0x18001e1f6  jz      short loc_18001E213
0x18001e1f8  test    byte ptr [rcx+1Ch], 4
0x18001e1fc  jz      short loc_18001E213
0x18001e1fe  mov     edx, 38h ; '8'
0x18001e203  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x18001e20a  mov     rcx, [rcx+10h]
0x18001e20e  call    WPP_SF_
0x18001e213  mov     rdx, rbx
0x18001e216  mov     rcx, rdi
0x18001e219  call    ?_CleanupLpcServer@CWerService@@AEAAJAEAV?$unique_lock@Vrecursive_mutex@utl@@@utl@@@Z; CWerService::_CleanupLpcServer(utl::unique_lock<utl::recursive_mutex> &)
0x18001e21e  mov     ebx, eax
0x18001e220  test    eax, eax
0x18001e222  jns     short loc_18001E252
0x18001e224  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e22b  cmp     rcx, rsi
0x18001e22e  jz      short loc_18001E24E
0x18001e230  test    byte ptr [rcx+1Ch], 1
0x18001e234  jz      short loc_18001E24E
0x18001e236  mov     edx, 39h ; '9'
0x18001e23b  mov     r9d, eax
0x18001e23e  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x18001e245  mov     rcx, [rcx+10h]
0x18001e249  call    WPP_SF_d
0x18001e24e  mov     eax, ebx
0x18001e250  jmp     short loc_18001E280
0x18001e252  lea     rbx, [rdi+1A0h]
0x18001e259  mov     [rsp+38h+var_18], rbx
0x18001e25e  mov     rcx, rbx; lpCriticalSection
0x18001e261  call    cs:__imp_EnterCriticalSection
0x18001e267  mov     [rsp+38h+var_10], 1
0x18001e26c  mov     rcx, rbx; this
0x18001e26f  call    ?_Cleanup@CHangrepServer@@AEAAXXZ; CHangrepServer::_Cleanup(void)
0x18001e274  nop
0x18001e275  mov     rcx, rbx; lpCriticalSection
0x18001e278  call    cs:__imp_LeaveCriticalSection
0x18001e27e  xor     eax, eax
0x18001e280  mov     rbx, [rsp+38h+arg_0]
0x18001e285  mov     rsi, [rsp+38h+arg_8]
0x18001e28a  add     rsp, 30h
0x18001e28e  pop     rdi
0x18001e28f  retn
```
