# CLightDismissClientStore::_CleanOutWaits(void)

- ea: `0x180027ef0`
- end: `0x180028064`
- name: `?_CleanOutWaits@CLightDismissClientStore@@AEAAXXZ`
- size: `372`
- prototype: `void __fastcall(CLightDismissClientStore *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180027d58`
- `0x180084284`

## callees

- `0x180027ef0`
- `0x18004a5f0`
- `0x18005a1c2`
- `0x180083e24`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180027fb0`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180027fb0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028020`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028020`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180028011`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180028011`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002803e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002803e`

## pseudocode

```c
void __fastcall CLightDismissClientStore::_CleanOutWaits(CLightDismissClientStore *this)
{
  _DWORD *v1; // rsi
  unsigned __int64 v2; // rdi
  unsigned __int64 v3; // r15
  __int64 j; // r14
  int v6; // eax
  _DWORD *v7; // rcx
  unsigned __int64 v8; // r14
  DWORD ProcessId; // eax
  unsigned __int64 k; // rcx
  unsigned __int64 v11; // r8
  __int64 v12; // rcx
  void *v13; // r15
  void *v14; // r12
  _DWORD *v15; // [rsp+20h] [rbp-20h] BYREF
  __int64 v16; // [rsp+28h] [rbp-18h]
  __int64 v17; // [rsp+30h] [rbp-10h]
  __int64 i; // [rsp+38h] [rbp-8h]
  char v19; // [rsp+70h] [rbp+30h] BYREF

  v1 = 0;
  v2 = 0;
  v3 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  for ( i = 0; v3 < *((_QWORD *)this + 12); ++v3 )
  {
    for ( j = *(_QWORD *)(*((_QWORD *)this + 11) + 8 * v3); j; j = *(_QWORD *)(j + 56) )
    {
      if ( (int)CTSimpleFixedArray<unsigned long,CSimpleArrayStandardCompareHelper<unsigned long>>::Find(
                  &v15,
                  j + 20,
                  &v19) < 0 )
      {
        if ( v2 != i
          || (v6 = CTSimpleArray<unsigned long,4294967294,CTPolicyCoTaskMem<unsigned long>,CSimpleArrayStandardCompareHelper<unsigned long>,CSimpleArrayStandardMergeHelper<unsigned long>>::_EnsureCapacity(
                     &v15,
                     v2 + 1),
              v2 = v16,
              v1 = v15,
              v6 >= 0) )
        {
          v16 = ++v2;
          v7 = &v1[v2 - 1];
          if ( v7 )
            *v7 = *(_DWORD *)(j + 20);
        }
      }
    }
  }
  v8 = 0;
  while ( v8 < *((_QWORD *)this + 8) )
  {
    ProcessId = GetProcessId(*(HANDLE *)(*((_QWORD *)this + 7) + 16 * v8 + 8));
    for ( k = 0; k < v2; ++k )
    {
      if ( v1[k] == ProcessId )
      {
        ++v8;
        goto LABEL_22;
      }
    }
    v11 = *((_QWORD *)this + 8);
    v12 = 16 * v8 + *((_QWORD *)this + 7);
    v13 = *(void **)v12;
    v14 = *(void **)(v12 + 8);
    if ( v8 < v11 )
    {
      if ( v8 != v11 - 1 )
        memmove_0((void *)v12, (const void *)(v12 + 16), 16 * (v11 - v8) - 16);
      --*((_QWORD *)this + 8);
    }
    UnregisterWaitEx(v13, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    CloseHandle(v14);
LABEL_22:
    ;
  }
  if ( v1 )
    CoTaskMemFree(v1);
}

```

## disassembly

```asm
0x180027ef0  mov     [rsp-28h+arg_8], rbx
0x180027ef5  mov     [rsp-28h+arg_10], rsi
0x180027efa  push    rbp
0x180027efb  push    rdi
0x180027efc  push    r12
0x180027efe  push    r14
0x180027f00  push    r15
0x180027f02  mov     rbp, rsp
0x180027f05  sub     rsp, 40h
0x180027f09  xor     esi, esi
0x180027f0b  xor     edi, edi
0x180027f0d  xor     r15d, r15d
0x180027f10  mov     [rbp+var_20], rsi
0x180027f14  mov     rbx, rcx
0x180027f17  mov     [rbp+var_18], rdi
0x180027f1b  mov     [rbp+var_10], rsi
0x180027f1f  mov     [rbp+var_8], rsi
0x180027f23  cmp     [rcx+60h], rsi
0x180027f27  jbe     short loc_180027F93
0x180027f29  mov     rax, [rbx+58h]
0x180027f2d  mov     r14, [rax+r15*8]
0x180027f31  jmp     short loc_180027F85
0x180027f33  lea     r8, [rbp+arg_0]
0x180027f37  lea     rdx, [r14+14h]
0x180027f3b  lea     rcx, [rbp+var_20]
0x180027f3f  call    ?Find@?$CTSimpleFixedArray@KV?$CSimpleArrayStandardCompareHelper@K@@@@QEBAJAEBKPEA_K_K@Z; CTSimpleFixedArray<ulong,CSimpleArrayStandardCompareHelper<ulong>>::Find(ulong const &,unsigned __int64 *,unsigned __int64)
0x180027f44  test    eax, eax
0x180027f46  jns     short loc_180027F81
0x180027f48  cmp     rdi, [rbp+var_8]
0x180027f4c  jnz     short loc_180027F67
0x180027f4e  lea     rdx, [rdi+1]
0x180027f52  lea     rcx, [rbp+var_20]
0x180027f56  call    ?_EnsureCapacity@?$CTSimpleArray@K$0PPPPPPPO@V?$CTPolicyCoTaskMem@K@@V?$CSimpleArrayStandardCompareHelper@K@@V?$CSimpleArrayStandardMergeHelper@K@@@@QEAAJ_K0@Z; CTSimpleArray<ulong,4294967294,CTPolicyCoTaskMem<ulong>,CSimpleArrayStandardCompareHelper<ulong>,CSimpleArrayStandardMergeHelper<ulong>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x180027f5b  mov     rdi, [rbp+var_18]
0x180027f5f  mov     rsi, [rbp+var_20]
0x180027f63  test    eax, eax
0x180027f65  js      short loc_180027F81
0x180027f67  inc     rdi
0x180027f6a  mov     [rbp+var_18], rdi
0x180027f6e  lea     rcx, [rdi-1]
0x180027f72  lea     rcx, [rsi+rcx*4]
0x180027f76  test    rcx, rcx
0x180027f79  jz      short loc_180027F81
0x180027f7b  mov     eax, [r14+14h]
0x180027f7f  mov     [rcx], eax
0x180027f81  mov     r14, [r14+38h]
0x180027f85  test    r14, r14
0x180027f88  jnz     short loc_180027F33
0x180027f8a  inc     r15
0x180027f8d  cmp     r15, [rbx+60h]
0x180027f91  jb      short loc_180027F29
0x180027f93  xor     r14d, r14d
0x180027f96  cmp     [rbx+40h], r14
0x180027f9a  jbe     loc_180028036
0x180027fa0  mov     rcx, [rbx+38h]
0x180027fa4  mov     r15, r14
0x180027fa7  shl     r15, 4
0x180027fab  mov     rcx, [rcx+r15+8]; Process
0x180027fb0  call    cs:__imp_GetProcessId
0x180027fb7  nop     dword ptr [rax+rax+00h]
0x180027fbc  xor     ecx, ecx
0x180027fbe  cmp     rcx, rdi
0x180027fc1  jnb     short loc_180027FD2
0x180027fc3  cmp     [rsi+rcx*4], eax
0x180027fc6  jz      short loc_180027FCD
0x180027fc8  inc     rcx
0x180027fcb  jmp     short loc_180027FBE
0x180027fcd  inc     r14
0x180027fd0  jmp     short loc_18002802C
0x180027fd2  mov     rcx, [rbx+38h]
0x180027fd6  mov     r8, [rbx+40h]
0x180027fda  add     rcx, r15; void *
0x180027fdd  mov     r15, [rcx]
0x180027fe0  mov     r12, [rcx+8]
0x180027fe4  cmp     r14, r8
0x180027fe7  jnb     short loc_18002800A
0x180027fe9  lea     rax, [r8-1]
0x180027fed  cmp     r14, rax
0x180027ff0  jz      short loc_180028006
0x180027ff2  sub     r8, r14
0x180027ff5  lea     rdx, [rcx+10h]; Src
0x180027ff9  shl     r8, 4
0x180027ffd  sub     r8, 10h; Size
0x180028001  call    memmove_0
0x180028006  dec     qword ptr [rbx+40h]
0x18002800a  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18002800e  mov     rcx, r15; WaitHandle
0x180028011  call    cs:__imp_UnregisterWaitEx
0x180028018  nop     dword ptr [rax+rax+00h]
0x18002801d  mov     rcx, r12; hObject
0x180028020  call    cs:__imp_CloseHandle
0x180028027  nop     dword ptr [rax+rax+00h]
0x18002802c  cmp     r14, [rbx+40h]
0x180028030  jb      loc_180027FA0
0x180028036  test    rsi, rsi
0x180028039  jz      short loc_18002804A
0x18002803b  mov     rcx, rsi; pv
0x18002803e  call    cs:__imp_CoTaskMemFree
0x180028045  nop     dword ptr [rax+rax+00h]
0x18002804a  lea     r11, [rsp+40h+var_s0]
0x18002804f  mov     rbx, [r11+38h]
0x180028053  mov     rsi, [r11+40h]
0x180028057  mov     rsp, r11
0x18002805a  pop     r15
0x18002805c  pop     r14
0x18002805e  pop     r12
0x180028060  pop     rdi
0x180028061  pop     rbp
0x180028062  retn
```
