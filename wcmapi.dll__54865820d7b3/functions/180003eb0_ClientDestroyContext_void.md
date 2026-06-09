# ClientDestroyContext(void *)

- ea: `0x180003eb0`
- end: `0x180003f83`
- name: `?ClientDestroyContext@@YAXPEAX@Z`
- size: `211`
- prototype: `void __fastcall(void *lpMem)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180003f90`

## callees

- `0x180003eb0`
- `0x180004450`
- `0x1800044b0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003f2d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003f2d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003f14`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003f14`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003f08`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003f08`

## pseudocode

```c
void __fastcall ClientDestroyContext(char *lpMem)
{
  WcmPolicyManager *v2; // rcx
  HANDLE ProcessHeap; // rax

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      32,
      &WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids,
      "ClientDestroyContext");
    v2 = WPP_GLOBAL_Control;
  }
  if ( lpMem )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)(lpMem + 16));
    ProcessHeap = GetProcessHeap();
    if ( ProcessHeap )
      HeapFree(ProcessHeap, 0, lpMem);
    v2 = WPP_GLOBAL_Control;
  }
  if ( v2 != (WcmPolicyManager *)&WPP_GLOBAL_Control && *((_BYTE *)v2 + 25) >= 5u && (*((_BYTE *)v2 + 28) & 1) != 0 )
    WPP_SF_sL(
      *((_QWORD *)v2 + 2),
      33,
      (unsigned int)&WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids,
      (unsigned int)"ClientDestroyContext",
      0);
}

```

## disassembly

```asm
0x180003eb0  mov     [rsp+arg_0], rbx
0x180003eb5  push    rdi
0x180003eb6  sub     rsp, 30h
0x180003eba  mov     rbx, rcx
0x180003ebd  mov     rcx, cs:WPP_GLOBAL_Control
0x180003ec4  lea     rdi, WPP_GLOBAL_Control
0x180003ecb  cmp     rcx, rdi
0x180003ece  jz      short loc_180003EFF
0x180003ed0  cmp     byte ptr [rcx+19h], 5
0x180003ed4  jb      short loc_180003EFF
0x180003ed6  test    byte ptr [rcx+1Ch], 1
0x180003eda  jz      short loc_180003EFF
0x180003edc  mov     rcx, [rcx+10h]
0x180003ee0  lea     r9, aClientdestroyc; "ClientDestroyContext"
0x180003ee7  mov     edx, 20h ; ' '
0x180003eec  lea     r8, WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids
0x180003ef3  call    WPP_SF_s
0x180003ef8  mov     rcx, cs:WPP_GLOBAL_Control
0x180003eff  test    rbx, rbx
0x180003f02  jz      short loc_180003F40
0x180003f04  lea     rcx, [rbx+10h]; lpCriticalSection
0x180003f08  call    cs:__imp_DeleteCriticalSection
0x180003f0f  nop     dword ptr [rax+rax+00h]
0x180003f14  call    cs:__imp_GetProcessHeap
0x180003f1b  nop     dword ptr [rax+rax+00h]
0x180003f20  test    rax, rax
0x180003f23  jz      short loc_180003F39
0x180003f25  mov     r8, rbx; lpMem
0x180003f28  xor     edx, edx; dwFlags
0x180003f2a  mov     rcx, rax; hHeap
0x180003f2d  call    cs:__imp_HeapFree
0x180003f34  nop     dword ptr [rax+rax+00h]
0x180003f39  mov     rcx, cs:WPP_GLOBAL_Control
0x180003f40  cmp     rcx, rdi
0x180003f43  jnz     short loc_180003F51
0x180003f45  mov     rbx, [rsp+38h+arg_0]
0x180003f4a  add     rsp, 30h
0x180003f4e  pop     rdi
0x180003f4f  retn
0x180003f51  cmp     byte ptr [rcx+19h], 5
0x180003f55  jb      short loc_180003F45
0x180003f57  test    byte ptr [rcx+1Ch], 1
0x180003f5b  jz      short loc_180003F45
0x180003f5d  mov     rcx, [rcx+10h]
0x180003f61  lea     r9, aClientdestroyc; "ClientDestroyContext"
0x180003f68  mov     edx, 21h ; '!'
0x180003f6d  mov     [rsp+38h+var_18], 0
0x180003f75  lea     r8, WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids
0x180003f7c  call    WPP_SF_sL
0x180003f81  jmp     short loc_180003F45
```
