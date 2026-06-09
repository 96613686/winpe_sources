# CleanupRpcAsyncStateObject(VPNIKE_ASYNC_RPC_CALL_STATE_ *)

- ea: `0x1800022c4`
- end: `0x180002359`
- name: `?CleanupRpcAsyncStateObject@@YAXPEAUVPNIKE_ASYNC_RPC_CALL_STATE_@@@Z`
- size: `149`
- prototype: `void __fastcall(struct VPNIKE_ASYNC_RPC_CALL_STATE_ *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180002360`
- `0x180002660`
- `0x180004f80`

## callees

- `0x180001390`
- `0x1800022c4`
- `0x1800063a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000231a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000231a`

## pseudocode

```c
void __fastcall CleanupRpcAsyncStateObject(struct VPNIKE_ASYNC_RPC_CALL_STATE_ *a1)
{
  PVOID *v2; // rcx

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    if ( *((_DWORD *)a1 + 44) )
      DeleteCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 136));
    MIDL_user_free(a1);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 && *((_BYTE *)v2 + 25) >= 6u )
    WPP_SF_(v2[2], 11);
}

```

## disassembly

```asm
0x1800022c4  mov     [rsp+arg_0], rbx
0x1800022c9  push    rdi
0x1800022ca  sub     rsp, 20h
0x1800022ce  mov     rbx, rcx
0x1800022d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800022d8  lea     rdi, WPP_GLOBAL_Control
0x1800022df  cmp     rcx, rdi
0x1800022e2  jz      short loc_180002305
0x1800022e4  test    byte ptr [rcx+1Ch], 1
0x1800022e8  jz      short loc_180002305
0x1800022ea  cmp     byte ptr [rcx+19h], 6
0x1800022ee  jb      short loc_180002305
0x1800022f0  mov     rcx, [rcx+10h]
0x1800022f4  mov     edx, 0Ah
0x1800022f9  call    WPP_SF_
0x1800022fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180002305  test    rbx, rbx
0x180002308  jz      short loc_18000232F
0x18000230a  cmp     dword ptr [rbx+0B0h], 0
0x180002311  jz      short loc_180002320
0x180002313  lea     rcx, [rbx+88h]; lpCriticalSection
0x18000231a  call    cs:__imp_DeleteCriticalSection
0x180002320  mov     rcx, rbx; void *
0x180002323  call    MIDL_user_free
0x180002328  mov     rcx, cs:WPP_GLOBAL_Control
0x18000232f  cmp     rcx, rdi
0x180002332  jz      short loc_18000234E
0x180002334  test    byte ptr [rcx+1Ch], 1
0x180002338  jz      short loc_18000234E
0x18000233a  cmp     byte ptr [rcx+19h], 6
0x18000233e  jb      short loc_18000234E
0x180002340  mov     rcx, [rcx+10h]
0x180002344  mov     edx, 0Bh
0x180002349  call    WPP_SF_
0x18000234e  mov     rbx, [rsp+28h+arg_0]
0x180002353  add     rsp, 20h
0x180002357  pop     rdi
0x180002358  retn
```
