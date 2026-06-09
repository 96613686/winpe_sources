# CSsdpSearchRequestManager::StartSearchForListeners(void)

- ea: `0x1800102bc`
- end: `0x180010388`
- name: `?StartSearchForListeners@CSsdpSearchRequestManager@@QEAAKXZ`
- size: `204`
- prototype: `unsigned int __fastcall(CSsdpSearchRequestManager *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000fec0`
- `0x180011d00`
- `0x18001ca60`

## callees

- `0x1800102bc`
- `0x180029df0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001036e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001036e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001030f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001030f`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180010358`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180010358`

## pseudocode

```c
__int64 __fastcall CSsdpSearchRequestManager::StartSearchForListeners(CSsdpSearchRequestManager *this)
{
  bool v2; // zf

  if ( !*((_DWORD *)this + 168) )
  {
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 688));
    v2 = *((_QWORD *)this + 92) == 0;
    *((_DWORD *)this + 182) = 1;
    if ( v2 && *((_QWORD *)this + 93) )
      *((_QWORD *)this + 92) = CreateThread(
                                 0,
                                 0,
                                 CSsdpSearchRequestManager::SendSearchForListenersThread,
                                 this,
                                 0,
                                 (LPDWORD)this + 14);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 688));
  }
  return 0;
}

```

## disassembly

```asm
0x1800102bc  mov     [rsp+arg_0], rbx
0x1800102c1  push    rdi
0x1800102c2  sub     rsp, 30h
0x1800102c6  mov     eax, [rcx+2A0h]
0x1800102cc  mov     rbx, rcx
0x1800102cf  test    eax, eax
0x1800102d1  jnz     loc_18001037A
0x1800102d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800102de  lea     rax, WPP_GLOBAL_Control
0x1800102e5  cmp     rcx, rax
0x1800102e8  jz      short loc_180010305
0x1800102ea  test    byte ptr [rcx+1Ch], 8
0x1800102ee  jz      short loc_180010305
0x1800102f0  mov     rcx, [rcx+10h]
0x1800102f4  lea     r8, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids
0x1800102fb  mov     edx, 3Ah ; ':'
0x180010300  call    WPP_SF_
0x180010305  lea     rdi, [rbx+2B0h]
0x18001030c  mov     rcx, rdi; lpCriticalSection
0x18001030f  call    cs:__imp_EnterCriticalSection
0x180010316  nop     dword ptr [rax+rax+00h]
0x18001031b  cmp     qword ptr [rbx+2E0h], 0
0x180010323  mov     dword ptr [rbx+2D8h], 1
0x18001032d  jnz     short loc_18001036B
0x18001032f  cmp     qword ptr [rbx+2E8h], 0
0x180010337  jz      short loc_18001036B
0x180010339  lea     rax, [rbx+38h]
0x18001033d  mov     r9, rbx; lpParameter
0x180010340  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x180010345  lea     r8, ?SendSearchForListenersThread@CSsdpSearchRequestManager@@CAKPEAX@Z; lpStartAddress
0x18001034c  xor     edx, edx; dwStackSize
0x18001034e  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x180010356  xor     ecx, ecx; lpThreadAttributes
0x180010358  call    cs:__imp_CreateThread
0x18001035f  nop     dword ptr [rax+rax+00h]
0x180010364  mov     [rbx+2E0h], rax
0x18001036b  mov     rcx, rdi; lpCriticalSection
0x18001036e  call    cs:__imp_LeaveCriticalSection
0x180010375  nop     dword ptr [rax+rax+00h]
0x18001037a  mov     rbx, [rsp+38h+arg_0]
0x18001037f  xor     eax, eax
0x180010381  add     rsp, 30h
0x180010385  pop     rdi
0x180010386  retn
```
