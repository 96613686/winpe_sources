# wfdClientDestroyContext(_WFD_CLIENT_CONTEXT *)

- ea: `0x180006f80`
- end: `0x18000707c`
- name: `?wfdClientDestroyContext@@YAKPEAU_WFD_CLIENT_CONTEXT@@@Z`
- size: `252`
- prototype: `unsigned int __fastcall(struct _WFD_CLIENT_CONTEXT *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800038fc`
- `0x180053cf8`

## callees

- `0x180005610`
- `0x1800063a0`
- `0x180006934`
- `0x180006f80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006fd5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006fd5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007031`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007031`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180006fc8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180006fc8`

## pseudocode

```c
__int64 __fastcall wfdClientDestroyContext(struct _WFD_CLIENT_CONTEXT *a1)
{
  union DOT11_OUI_HEADER *v2; // rcx
  void *v4; // rcx
  __int64 v5; // rax
  __int64 v6; // rcx

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 40, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    CloseThreadpoolCleanupGroup(*((PTP_CLEANUP_GROUP *)a1 + 38));
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 168));
    v4 = (void *)*((_QWORD *)a1 + 26);
    if ( v4 )
      CloseHandle(v4);
    v5 = *((_QWORD *)a1 + 20);
    if ( v5 )
    {
      v6 = *(_QWORD *)(v5 + 32);
      if ( v6 )
        FreeWLMem(v6);
      FreeWLMem(*((_QWORD *)a1 + 20));
    }
    FreeWLMem(a1);
    v2 = WPP_GLOBAL_Control;
  }
  if ( v2 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)v2 + 105) >= 4u
    && (*((_BYTE *)v2 + 108) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)v2 + 12), 41, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x180006f80  mov     [rsp+arg_0], rbx
0x180006f85  push    rdi
0x180006f86  sub     rsp, 20h
0x180006f8a  mov     rbx, rcx
0x180006f8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006f94  lea     rdi, WPP_GLOBAL_Control
0x180006f9b  cmp     rcx, rdi
0x180006f9e  jnz     short loc_180007004
0x180006fa0  test    rbx, rbx
0x180006fa3  jnz     short loc_180006FC1
0x180006fa5  cmp     rcx, rdi
0x180006fa8  jz      short loc_180006FB4
0x180006faa  cmp     byte ptr [rcx+69h], 4
0x180006fae  jnb     loc_180007055
0x180006fb4  mov     rbx, [rsp+28h+arg_0]
0x180006fb9  xor     eax, eax
0x180006fbb  add     rsp, 20h
0x180006fbf  pop     rdi
0x180006fc0  retn
0x180006fc1  mov     rcx, [rbx+130h]; ptpcg
0x180006fc8  call    cs:__imp_CloseThreadpoolCleanupGroup
0x180006fce  lea     rcx, [rbx+0A8h]; lpCriticalSection
0x180006fd5  call    cs:__imp_DeleteCriticalSection
0x180006fdb  mov     rcx, [rbx+0D0h]; hObject
0x180006fe2  test    rcx, rcx
0x180006fe5  jnz     short loc_180007031
0x180006fe7  mov     rax, [rbx+0A0h]
0x180006fee  test    rax, rax
0x180006ff1  jnz     short loc_180007039
0x180006ff3  mov     rcx, rbx
0x180006ff6  call    FreeWLMem
0x180006ffb  mov     rcx, cs:WPP_GLOBAL_Control
0x180007002  jmp     short loc_180006FA5
0x180007004  cmp     byte ptr [rcx+69h], 4
0x180007008  jb      short loc_180006FA0
0x18000700a  test    byte ptr [rcx+6Ch], 2
0x18000700e  jz      short loc_180006FA0
0x180007010  mov     rcx, [rcx+60h]
0x180007014  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x18000701b  mov     edx, 28h ; '('
0x180007020  call    WPP_SF_
0x180007025  mov     rcx, cs:WPP_GLOBAL_Control
0x18000702c  jmp     loc_180006FA0
0x180007031  call    cs:__imp_CloseHandle
0x180007037  jmp     short loc_180006FE7
0x180007039  mov     rcx, [rax+20h]
0x18000703d  test    rcx, rcx
0x180007040  jz      short loc_180007047
0x180007042  call    FreeWLMem
0x180007047  mov     rcx, [rbx+0A0h]
0x18000704e  call    FreeWLMem
0x180007053  jmp     short loc_180006FF3
0x180007055  test    byte ptr [rcx+6Ch], 2
0x180007059  jz      loc_180006FB4
0x18000705f  mov     rcx, [rcx+60h]
0x180007063  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x18000706a  mov     edx, 29h ; ')'
0x18000706f  xor     r9d, r9d
0x180007072  call    WPP_SF_d
0x180007077  jmp     loc_180006FB4
```
