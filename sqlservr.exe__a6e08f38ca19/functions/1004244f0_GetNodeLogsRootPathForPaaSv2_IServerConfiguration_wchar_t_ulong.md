# GetNodeLogsRootPathForPaaSv2(IServerConfiguration *,wchar_t * *,ulong)

- ea: `0x1004244f0`
- end: `0x100424609`
- name: `?GetNodeLogsRootPathForPaaSv2@@YAJPEAVIServerConfiguration@@PEAPEA_WK@Z`
- size: `281`
- prototype: `__int64 __fastcall(struct IServerConfiguration *, wchar_t **, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, registry_config`

## callers

- `0x10042a380`

## callees

- `0x1004244f0`

## import_xrefs

- `sqllang!?XDB_GetWFRoot@@YAJPEA_WK@Z` at `0x1004245cd`
- `sqllang!?XDB_GetWFRoot@@YAJPEA_WK@Z` at `0x1004245cd`
- `sqldk!??_V@YAXPEAX@Z` at `0x1004245ad`
- `sqldk!??_V@YAXPEAX@Z` at `0x1004245ad`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100424558`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100424558`
- `sqldk!SystemThread_TlsOffset` at `0x10042453d`
- `sqldk!SystemThread_TlsIndex` at `0x100424534`
- `api-ms-win-crt-string-l1-1-0!wcscat_s` at `0x100424600`
- `api-ms-win-crt-string-l1-1-0!wcscat_s` at `0x100424600`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetNodeLogsRootPathForPaaSv2(struct IServerConfiguration *a1, wchar_t **a2, unsigned int a3)
{
  __int64 v3; // rbp
  unsigned int v7; // ebx
  __int64 v8; // rdi
  __int64 v9; // rax
  int WFRoot; // eax
  wchar_t *v11; // rcx
  __int64 v12; // rax
  wchar_t *v13; // [rsp+60h] [rbp+8h] BYREF

  v3 = a3;
  if ( !a1 )
    return 2147942560LL;
  v7 = 0;
  v13 = 0;
  v8 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v9 = *(_QWORD *)(v8 + 256);
  if ( !v9 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v9 = *(_QWORD *)(v8 + 256);
  }
  if ( (*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, _QWORD, wchar_t **, _QWORD, __int64))(*(_QWORD *)a1 + 528LL))(
         a1,
         L"SQL",
         L"NodeLogsRootSQLPaaSV2",
         *(_QWORD *)(*(_QWORD *)(v9 + 992) + 320LL),
         &v13,
         0,
         -2) )
  {
    WFRoot = XDB_GetWFRoot(*a2, v3);
    if ( !WFRoot )
    {
      v11 = *a2;
      v12 = -1;
      do
        ++v12;
      while ( v11[v12] );
      wcscat_s(v11, v3 - v12, v13 + 19);
      goto LABEL_8;
    }
  }
  else
  {
    WFRoot = -2147024883;
  }
  v7 = WFRoot;
LABEL_8:
  operator delete[](v13);
  return v7;
}

```

## disassembly

```asm
0x1004244f0  push    rsi
0x1004244f2  push    rdi
0x1004244f3  push    r14
0x1004244f5  sub     rsp, 40h
0x1004244f9  mov     [rsp+58h+var_28], 0FFFFFFFFFFFFFFFEh
0x100424502  mov     [rsp+58h+arg_8], rbx
0x100424507  mov     [rsp+58h+arg_10], rbp
0x10042450c  mov     ebp, r8d
0x10042450f  mov     r14, rdx
0x100424512  mov     rsi, rcx
0x100424515  test    rcx, rcx
0x100424518  jnz     short loc_100424524
0x10042451a  mov     eax, 800700A0h
0x10042451f  jmp     loc_1004245B5
0x100424524  xor     ebx, ebx
0x100424526  mov     [rsp+58h+arg_0], rbx
0x10042452b  mov     rdx, gs:58h
0x100424534  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10042453b  mov     ecx, [rax]
0x10042453d  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100424544  mov     edi, [rax]
0x100424546  add     rdi, [rdx+rcx*8]
0x10042454a  mov     rax, [rdi+100h]
0x100424551  test    rax, rax
0x100424554  jnz     short loc_100424565
0x100424556  xor     ecx, ecx
0x100424558  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10042455e  mov     rax, [rdi+100h]
0x100424565  mov     rax, [rax+3E0h]
0x10042456c  mov     r10, [rsi]
0x10042456f  mov     [rsp+58h+var_30], rbx
0x100424574  lea     rcx, [rsp+58h+arg_0]
0x100424579  mov     [rsp+58h+var_38], rcx
0x10042457e  mov     r9, [rax+140h]
0x100424585  lea     r8, aNodelogsrootsq_0; "NodeLogsRootSQLPaaSV2"
0x10042458c  lea     rdx, aSql; "SQL"
0x100424593  mov     rcx, rsi
0x100424596  call    qword ptr [r10+210h]
0x10042459d  test    al, al
0x10042459f  jnz     short loc_1004245C8
0x1004245a1  mov     eax, 8007000Dh
0x1004245a6  mov     ebx, eax
0x1004245a8  mov     rcx, [rsp+58h+arg_0]
0x1004245ad  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1004245b3  mov     eax, ebx
0x1004245b5  mov     rbx, [rsp+58h+arg_8]
0x1004245ba  mov     rbp, [rsp+58h+arg_10]
0x1004245bf  add     rsp, 40h
0x1004245c3  pop     r14
0x1004245c5  pop     rdi
0x1004245c6  pop     rsi
0x1004245c7  retn
0x1004245c8  mov     edx, ebp
0x1004245ca  mov     rcx, [r14]
0x1004245cd  call    cs:__imp_?XDB_GetWFRoot@@YAJPEA_WK@Z; XDB_GetWFRoot(wchar_t *,ulong)
0x1004245d3  test    eax, eax
0x1004245d5  jnz     short loc_1004245A6
0x1004245d7  mov     rcx, [r14]; Destination
0x1004245da  mov     r8, [rsp+58h+arg_0]
0x1004245df  add     r8, 26h ; '&'; Source
0x1004245e3  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1004245ea  nop     word ptr [rax+rax+00h]
0x1004245f0  inc     rax
0x1004245f3  cmp     word ptr [rcx+rax*2], 0
0x1004245f8  jnz     short loc_1004245F0
0x1004245fa  mov     rdx, rbp
0x1004245fd  sub     rdx, rax; SizeInWords
0x100424600  call    cs:__imp_wcscat_s
0x100424606  jmp     short loc_1004245A8
```
