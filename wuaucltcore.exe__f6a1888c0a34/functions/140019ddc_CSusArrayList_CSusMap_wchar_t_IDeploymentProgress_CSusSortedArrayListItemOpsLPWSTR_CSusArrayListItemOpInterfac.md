# CSusArrayList<CSusMap<wchar_t *,IDeploymentProgress *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentProgress *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentProgress *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentProgress *>>::CMapEntryOps>::RemoveArraySection(ulong,ulong,int)

- ea: `0x140019ddc`
- end: `0x140019eda`
- name: `?RemoveArraySection@?$CSusArrayList@U_tagMapEntry@?$CSusMap@PEA_WPEAUIDeploymentProgress@@VCSusSortedArrayListItemOpsLPWSTR@@V?$CSusArrayListItemOpInterfacePtr@PEAUIDeploymentProgress@@@@@@VCMapEntryOps@2@@@IEAAXKKH@Z`
- size: `254`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x140018ddc`
- `0x1400195a0`
- `0x1400196b0`
- `0x1400199a0`
- `0x140019a84`

## callees

- `0x14000d4cc`
- `0x140019ddc`
- `0x1400206e0`
- `0x140020760`
- `0x140020b20`

## pseudocode

```c
unsigned __int64 __fastcall CSusArrayList<CSusMap<wchar_t *,IDeploymentProgress *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentProgress *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentProgress *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentProgress *>>::CMapEntryOps>::RemoveArraySection(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        int a4)
{
  unsigned __int64 result; // rax
  unsigned int v5; // ebx
  __int64 v6; // rbp
  unsigned int v8; // esi
  unsigned int i; // r15d
  __int64 v10; // r12
  __int64 v11; // r14
  void *v12; // rcx
  __int64 v13; // rcx
  int v14; // ecx

  result = *(unsigned int *)(a1 + 20);
  v5 = a3;
  v6 = a2;
  if ( (_DWORD)result && a2 < (unsigned int)result )
  {
    if ( a3 >= (unsigned int)result )
      v5 = result - 1;
    v8 = v5 - a2 + 1;
    if ( a4 )
    {
      for ( i = a2; i <= v5; *(_QWORD *)(v10 + 8 * v11) = 0 )
      {
        v10 = *(_QWORD *)(a1 + 8);
        v11 = 2LL * i;
        v12 = *(void **)(v10 + 16LL * i + 8);
        if ( v12 )
          SusFree(v12);
        v13 = *(_QWORD *)(v10 + 16LL * i);
        if ( v13 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
        ++i;
      }
    }
    v14 = *(_DWORD *)(a1 + 20);
    result = (unsigned int)(v14 - 1);
    if ( v5 < (unsigned int)result )
    {
      memmove(
        (void *)(*(_QWORD *)(a1 + 8) + 16 * v6),
        (const void *)(*(_QWORD *)(a1 + 8) + 16LL * (v5 + 1)),
        16LL * (v14 + ~v5));
      result = (unsigned __int64)memset(
                                   (void *)(*(_QWORD *)(a1 + 8) + 16LL * (*(_DWORD *)(a1 + 20) - v8)),
                                   0,
                                   16LL * v8);
    }
    *(_DWORD *)(a1 + 20) -= v8;
  }
  return result;
}

```

## disassembly

```asm
0x140019ddc  mov     rax, rsp
0x140019ddf  mov     [rax+8], rbx
0x140019de3  mov     [rax+10h], rbp
0x140019de7  mov     [rax+18h], rsi
0x140019deb  mov     [rax+20h], rdi
0x140019def  push    r12
0x140019df1  push    r14
0x140019df3  push    r15
0x140019df5  sub     rsp, 20h
0x140019df9  mov     eax, [rcx+14h]
0x140019dfc  mov     ebx, r8d
0x140019dff  mov     ebp, edx
0x140019e01  mov     rdi, rcx
0x140019e04  test    eax, eax
0x140019e06  jz      loc_140019EBB
0x140019e0c  cmp     ebp, eax
0x140019e0e  jnb     loc_140019EBB
0x140019e14  cmp     ebx, eax
0x140019e16  jb      short loc_140019E1B
0x140019e18  lea     ebx, [rax-1]
0x140019e1b  mov     esi, ebx
0x140019e1d  sub     esi, ebp
0x140019e1f  inc     esi
0x140019e21  test    r9d, r9d
0x140019e24  jz      short loc_140019E6B
0x140019e26  mov     r15d, ebp
0x140019e29  cmp     ebp, ebx
0x140019e2b  ja      short loc_140019E6B
0x140019e2d  mov     r12, [rdi+8]
0x140019e31  mov     r14d, r15d
0x140019e34  add     r14, r14
0x140019e37  mov     rcx, [r12+r14*8+8]; lpMem
0x140019e3c  test    rcx, rcx
0x140019e3f  jz      short loc_140019E46
0x140019e41  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x140019e46  mov     rcx, [r12+r14*8]
0x140019e4a  test    rcx, rcx
0x140019e4d  jz      short loc_140019E5B
0x140019e4f  mov     rax, [rcx]
0x140019e52  mov     rax, [rax+10h]
0x140019e56  call    _guard_dispatch_icall
0x140019e5b  inc     r15d
0x140019e5e  mov     qword ptr [r12+r14*8], 0
0x140019e66  cmp     r15d, ebx
0x140019e69  jbe     short loc_140019E2D
0x140019e6b  mov     ecx, [rdi+14h]
0x140019e6e  lea     eax, [rcx-1]
0x140019e71  cmp     ebx, eax
0x140019e73  jnb     short loc_140019EB8
0x140019e75  mov     r8d, ebx
0x140019e78  lea     edx, [rbx+1]
0x140019e7b  not     r8d
0x140019e7e  shl     rdx, 4
0x140019e82  add     rdx, [rdi+8]; Src
0x140019e86  add     r8d, ecx
0x140019e89  mov     rcx, rbp
0x140019e8c  shl     r8, 4; Size
0x140019e90  shl     rcx, 4
0x140019e94  add     rcx, [rdi+8]; void *
0x140019e98  call    memmove
0x140019e9d  mov     ecx, [rdi+14h]
0x140019ea0  xor     edx, edx; Val
0x140019ea2  sub     ecx, esi
0x140019ea4  mov     r8d, esi
0x140019ea7  shl     rcx, 4
0x140019eab  add     rcx, [rdi+8]; void *
0x140019eaf  shl     r8, 4; Size
0x140019eb3  call    memset
0x140019eb8  sub     [rdi+14h], esi
0x140019ebb  mov     rbx, [rsp+38h+arg_0]
0x140019ec0  mov     rbp, [rsp+38h+arg_8]
0x140019ec5  mov     rsi, [rsp+38h+arg_10]
0x140019eca  mov     rdi, [rsp+38h+arg_18]
0x140019ecf  add     rsp, 20h
0x140019ed3  pop     r15
0x140019ed5  pop     r14
0x140019ed7  pop     r12
0x140019ed9  retn
```
