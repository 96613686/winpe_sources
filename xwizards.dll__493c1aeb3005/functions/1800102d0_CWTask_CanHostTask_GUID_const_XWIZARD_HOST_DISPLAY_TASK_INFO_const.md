# CWTask::CanHostTask(_GUID * const,_XWIZARD_HOST_DISPLAY_TASK_INFO * * const)

- ea: `0x1800102d0`
- end: `0x180010408`
- name: `?CanHostTask@CWTask@@UEAAJQEAU_GUID@@QEAPEAU_XWIZARD_HOST_DISPLAY_TASK_INFO@@@Z`
- size: `312`
- prototype: `__int64 __fastcall(CWTask *__hidden this, struct _GUID *const, struct _XWIZARD_HOST_DISPLAY_TASK_INFO **const)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000ae04`
- `0x1800102d0`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001031c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001031c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010390`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010390`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010382`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010382`

## pseudocode

```c
__int64 __fastcall CWTask::CanHostTask(
        CWTask *this,
        struct _GUID *const a2,
        struct _XWIZARD_HOST_DISPLAY_TASK_INFO **const a3)
{
  __int64 (__fastcall *v3)(char *); // rax
  unsigned int v7; // edi
  struct _XWIZARD_HOST_DISPLAY_TASK_INFO *v8; // rax
  struct _XWIZARD_HOST_DISPLAY_TASK_INFO *v9; // rsi
  _OWORD *v10; // rcx
  _OWORD *v11; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v13; // rcx

  v3 = (__int64 (__fastcall *)(char *))*((_QWORD *)this + 4);
  if ( v3 )
  {
    v7 = v3((char *)this + 8);
    if ( !v7 )
    {
      if ( !*a3 )
        goto LABEL_14;
      v8 = (struct _XWIZARD_HOST_DISPLAY_TASK_INFO *)CoTaskMemAlloc(0x40u);
      v9 = v8;
      if ( v8 )
      {
        v10 = *a3;
        *(_OWORD *)v8 = *(_OWORD *)*a3;
        *((_OWORD *)v8 + 1) = v10[1];
        *((_OWORD *)v8 + 2) = v10[2];
        *((_OWORD *)v8 + 3) = v10[3];
      }
      else
      {
        v7 = -2147024882;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            13,
            WPP_2bc823490ca13860ef0fd20ec53590ea_Traceguids,
            2147942414LL);
      }
      v11 = *a3;
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v11);
      *a3 = v9;
    }
    if ( v7 != -2147467263 )
      goto LABEL_14;
  }
  v13 = *((_QWORD *)this + 18);
  if ( !v13
    || (v7 = (*(__int64 (__fastcall **)(__int64, struct _GUID *const, struct _XWIZARD_HOST_DISPLAY_TASK_INFO **const))(*(_QWORD *)v13 + 48LL))(
               v13,
               a2,
               a3),
        v7 == -2147467263) )
  {
    v7 = 1;
  }
LABEL_14:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_2bc823490ca13860ef0fd20ec53590ea_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x1800102d0  push    rbx
0x1800102d2  push    rbp
0x1800102d3  push    rsi
0x1800102d4  push    rdi
0x1800102d5  push    r12
0x1800102d7  push    r14
0x1800102d9  push    r15
0x1800102db  sub     rsp, 20h
0x1800102df  mov     rax, [rcx+20h]
0x1800102e3  lea     r12, WPP_GLOBAL_Control
0x1800102ea  mov     r14, r8
0x1800102ed  mov     r15, rdx
0x1800102f0  mov     rbp, rcx
0x1800102f3  test    rax, rax
0x1800102f6  jz      loc_1800103A1
0x1800102fc  add     rcx, 8
0x180010300  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010305  mov     edi, eax
0x180010307  test    eax, eax
0x180010309  jnz     loc_180010399
0x18001030f  cmp     qword ptr [r14], 0
0x180010313  jz      loc_1800103CD
0x180010319  lea     ecx, [rax+40h]; cb
0x18001031c  call    cs:__imp_CoTaskMemAlloc
0x180010322  mov     rsi, rax
0x180010325  test    rax, rax
0x180010328  jz      short loc_18001034D
0x18001032a  mov     rcx, [r14]
0x18001032d  movups  xmm0, xmmword ptr [rcx]
0x180010330  movups  xmmword ptr [rax], xmm0
0x180010333  movups  xmm1, xmmword ptr [rcx+10h]
0x180010337  movups  xmmword ptr [rax+10h], xmm1
0x18001033b  movups  xmm0, xmmword ptr [rcx+20h]
0x18001033f  movups  xmmword ptr [rax+20h], xmm0
0x180010343  movups  xmm1, xmmword ptr [rcx+30h]
0x180010347  movups  xmmword ptr [rax+30h], xmm1
0x18001034b  jmp     short loc_18001037F
0x18001034d  mov     edi, 8007000Eh
0x180010352  mov     rcx, cs:WPP_GLOBAL_Control
0x180010359  cmp     rcx, r12
0x18001035c  jz      short loc_18001037F
0x18001035e  test    byte ptr [rcx+1Ch], 4
0x180010362  jz      short loc_18001037F
0x180010364  mov     rcx, [rcx+10h]
0x180010368  lea     r8, WPP_2bc823490ca13860ef0fd20ec53590ea_Traceguids
0x18001036f  mov     edx, 0Dh
0x180010374  mov     r9d, 8007000Eh
0x18001037a  call    WPP_SF_d
0x18001037f  mov     rbx, [r14]
0x180010382  call    cs:__imp_GetProcessHeap
0x180010388  mov     r8, rbx; lpMem
0x18001038b  xor     edx, edx; dwFlags
0x18001038d  mov     rcx, rax; hHeap
0x180010390  call    cs:__imp_HeapFree
0x180010396  mov     [r14], rsi
0x180010399  cmp     edi, 80004001h
0x18001039f  jnz     short loc_1800103CD
0x1800103a1  mov     rcx, [rbp+90h]
0x1800103a8  test    rcx, rcx
0x1800103ab  jz      short loc_1800103C8
0x1800103ad  mov     rax, [rcx]
0x1800103b0  mov     r8, r14
0x1800103b3  mov     rdx, r15
0x1800103b6  mov     rax, [rax+30h]
0x1800103ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103bf  mov     edi, eax
0x1800103c1  cmp     eax, 80004001h
0x1800103c6  jnz     short loc_1800103CD
0x1800103c8  mov     edi, 1
0x1800103cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800103d4  cmp     rcx, r12
0x1800103d7  jz      short loc_1800103F7
0x1800103d9  test    byte ptr [rcx+1Ch], 10h
0x1800103dd  jz      short loc_1800103F7
0x1800103df  mov     rcx, [rcx+10h]
0x1800103e3  lea     r8, WPP_2bc823490ca13860ef0fd20ec53590ea_Traceguids
0x1800103ea  mov     edx, 0Eh
0x1800103ef  mov     r9d, edi
0x1800103f2  call    WPP_SF_d
0x1800103f7  mov     eax, edi
0x1800103f9  add     rsp, 20h
0x1800103fd  pop     r15
0x1800103ff  pop     r14
0x180010401  pop     r12
0x180010403  pop     rdi
0x180010404  pop     rsi
0x180010405  pop     rbp
0x180010406  pop     rbx
0x180010407  retn
```
