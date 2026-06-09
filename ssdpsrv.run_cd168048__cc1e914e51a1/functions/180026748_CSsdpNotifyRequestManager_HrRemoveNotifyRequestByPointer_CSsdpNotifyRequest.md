# CSsdpNotifyRequestManager::HrRemoveNotifyRequestByPointer(CSsdpNotifyRequest *)

- ea: `0x180026748`
- end: `0x1800267cd`
- name: `?HrRemoveNotifyRequestByPointer@CSsdpNotifyRequestManager@@QEAAJPEAVCSsdpNotifyRequest@@@Z`
- size: `133`
- prototype: `__int64 __fastcall(CSsdpNotifyRequestManager *__hidden this, struct CSsdpNotifyRequest *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800211b0`
- `0x18002ff68`

## callees

- `0x180018128`
- `0x180026748`
- `0x180029df0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002677e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002677e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026758`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026758`

## pseudocode

```c
__int64 __fastcall CSsdpNotifyRequestManager::HrRemoveNotifyRequestByPointer(
        struct _RTL_CRITICAL_SECTION *this,
        struct CSsdpNotifyRequest *a2)
{
  EnterCriticalSection(this);
  LODWORD(a2) = CSsdpNotifyRequestManager::HrRemoveInternal((CSsdpNotifyRequestManager *)this, 0, 0, 0, a2);
  LeaveCriticalSection(this);
  return (unsigned int)a2;
}

```

## disassembly

```asm
0x180026748  mov     [rsp+arg_0], rbx
0x18002674d  push    rdi
0x18002674e  sub     rsp, 30h
0x180026752  mov     rbx, rdx
0x180026755  mov     rdi, rcx
0x180026758  call    cs:__imp_EnterCriticalSection
0x18002675f  nop     dword ptr [rax+rax+00h]
0x180026764  mov     [rsp+38h+var_18], rbx; struct CSsdpNotifyRequest *
0x180026769  xor     r9d, r9d; void *
0x18002676c  xor     r8d, r8d; int
0x18002676f  xor     edx, edx; int
0x180026771  mov     rcx, rdi; this
0x180026774  call    ?HrRemoveInternal@CSsdpNotifyRequestManager@@AEAAJHHPEAXPEAVCSsdpNotifyRequest@@@Z; CSsdpNotifyRequestManager::HrRemoveInternal(int,int,void *,CSsdpNotifyRequest *)
0x180026779  mov     ebx, eax
0x18002677b  mov     rcx, rdi; lpCriticalSection
0x18002677e  call    cs:__imp_LeaveCriticalSection
0x180026785  nop     dword ptr [rax+rax+00h]
0x18002678a  mov     eax, ebx
0x18002678c  jmp     short loc_1800267C1
0x18002678e  lea     rax, WPP_GLOBAL_Control
0x180026795  mov     rcx, cs:WPP_GLOBAL_Control
0x18002679c  cmp     rcx, rax
0x18002679f  jz      short loc_1800267BC
0x1800267a1  test    byte ptr [rcx+1Ch], 1
0x1800267a5  jz      short loc_1800267BC
0x1800267a7  mov     edx, 5Bh ; '['
0x1800267ac  lea     r8, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids
0x1800267b3  mov     rcx, [rcx+10h]
0x1800267b7  call    WPP_SF_
0x1800267bc  mov     eax, 80004005h
0x1800267c1  mov     rbx, [rsp+38h+arg_0]
0x1800267c6  add     rsp, 30h
0x1800267ca  pop     rdi
0x1800267cb  retn
```
