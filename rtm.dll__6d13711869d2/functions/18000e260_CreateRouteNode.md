# CreateRouteNode

- ea: `0x18000e260`
- end: `0x18000e4b9`
- name: `CreateRouteNode`
- size: `601`
- prototype: `__int64 __usercall@<rax>(PVOID Context@<rcx>, __int64, void *Src)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18000eea0`
- `0x18000f780`

## callees

- `0x18000e260`
- `0x18001163c`
- `0x180011778`
- `0x180011800`
- `0x18001f946`
- `0x180020010`

## import_xrefs

- `ntdll!RtlQueueWorkItem` at `0x18000e47d`
- `ntdll!RtlQueueWorkItem` at `0x18000e47d`
- `KERNEL32!HeapAlloc` at `0x18000e296`
- `KERNEL32!HeapAlloc` at `0x18000e296`
- `KERNEL32!HeapFree` at `0x18000e32a`
- `KERNEL32!HeapFree` at `0x18000e36a`
- `KERNEL32!HeapFree` at `0x18000e32a`
- `KERNEL32!HeapFree` at `0x18000e36a`
- `KERNEL32!SetLastError` at `0x18000e4a0`
- `KERNEL32!SetLastError` at `0x18000e4a0`

## pseudocode

```c
_QWORD *__fastcall CreateRouteNode(
        int *Context,
        __int64 a2,
        _QWORD *InterfaceList,
        int a4,
        __int64 a5,
        unsigned int *Src)
{
  unsigned int v6; // eax
  _QWORD *v11; // rax
  _QWORD *v12; // rdi
  DWORD v13; // ecx
  __int64 v14; // r14
  _QWORD *v15; // rax
  _QWORD *v16; // rax
  _QWORD *v17; // rcx
  __int64 v18; // rcx
  int *i; // rsi
  int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  int **v23; // rcx

  v6 = Context[70];
  if ( v6 + 84 < v6 )
  {
    v13 = 534;
    goto LABEL_33;
  }
  v11 = HeapAlloc(*(HANDLE *)Context, 0, v6 + 84);
  v12 = v11;
  if ( !v11 )
    goto LABEL_3;
  *((_DWORD *)v11 + 16) = 4;
  v11[9] = a5;
  memcpy_0((char *)v11 + 84, Src, Context[70]);
  v12[7] = v12 + 6;
  v12[6] = v12 + 6;
  v14 = *((_QWORD *)Context + 33) + 32LL * (Src[3] % 0x1F);
  if ( !DoEnterSyncList((__int64)Context, v14, 1) )
  {
    HeapFree(*(HANDLE *)Context, 0, v12);
    v13 = 1450;
    goto LABEL_33;
  }
  if ( !InterfaceList && (InterfaceList = (_QWORD *)FindInterfaceList(v14, Src[3], 1)) == 0
    || !DoEnterSyncList((__int64)Context, (__int64)(Context + 24), 1) )
  {
    LeaveSyncList(Context, v14);
    HeapFree(*(HANDLE *)Context, 0, v12);
LABEL_3:
    v13 = 8;
LABEL_33:
    SetLastError(v13);
    return 0;
  }
  v15 = *(_QWORD **)(a2 + 8);
  if ( *v15 != a2 )
    goto LABEL_31;
  v12[1] = v15;
  *v12 = a2;
  *v15 = v12;
  v16 = v12 + 2;
  *(_QWORD *)(a2 + 8) = v12;
  if ( a4 )
  {
    v17 = (_QWORD *)InterfaceList[1];
    if ( (_QWORD *)*v17 != InterfaceList )
      goto LABEL_31;
    *v16 = InterfaceList;
    v12[3] = v17;
    *v17 = v16;
    InterfaceList[1] = v16;
  }
  else
  {
    v18 = *InterfaceList;
    if ( *(_QWORD **)(*InterfaceList + 8LL) != InterfaceList )
      goto LABEL_31;
    *v16 = v18;
    v12[3] = InterfaceList;
    *(_QWORD *)(v18 + 8) = v16;
    *InterfaceList = v16;
  }
  LeaveSyncList(Context, v14);
  for ( i = (int *)*((_QWORD *)Context + 14); i != Context + 28; i = *(int **)i )
  {
    v20 = (*((__int64 (__fastcall **)(__int64, int *))Context + 36))((__int64)v12 + 116, i + 21);
    if ( v20 < 0 )
      break;
    if ( !v20 )
    {
      v21 = *((_DWORD *)v12 + 23);
      if ( v21 < i[15] )
        break;
      if ( v21 == i[15] )
      {
        v22 = *((_DWORD *)v12 + 24);
        if ( v22 < i[16]
          || v22 == i[16] && (*((int (__fastcall **)(__int64, int *))Context + 37))((__int64)v12 + 84, i + 13) < 0 )
        {
          break;
        }
      }
    }
  }
  v23 = (int **)*((_QWORD *)i + 1);
  if ( *v23 != i )
LABEL_31:
    __fastfail(3u);
  v12[4] = i;
  v12[5] = v23;
  *v23 = (int *)(v12 + 4);
  *((_QWORD *)i + 1) = v12 + 4;
  if ( ++Context[10] == 16 && !_InterlockedIncrement(Context + 12) )
    RtlQueueWorkItem(ConsolidateNetNumberListsWI, Context, 0);
  LeaveSyncList(Context, Context + 24);
  return v12;
}

```

## disassembly

```asm
0x18000e260  push    rbx
0x18000e262  push    rbp
0x18000e263  push    rsi
0x18000e264  push    rdi
0x18000e265  push    r12
0x18000e267  push    r13
0x18000e269  push    r14
0x18000e26b  push    r15
0x18000e26d  sub     rsp, 28h
0x18000e271  mov     eax, [rcx+118h]
0x18000e277  mov     rbx, rcx
0x18000e27a  mov     r12d, r9d
0x18000e27d  mov     rsi, r8
0x18000e280  mov     rbp, rdx
0x18000e283  lea     ecx, [rax+54h]
0x18000e286  cmp     ecx, eax
0x18000e288  jb      loc_18000E49B
0x18000e28e  mov     r8d, ecx; dwBytes
0x18000e291  xor     edx, edx; dwFlags
0x18000e293  mov     rcx, [rbx]; hHeap
0x18000e296  call    cs:__imp_HeapAlloc
0x18000e29c  mov     rdi, rax
0x18000e29f  test    rax, rax
0x18000e2a2  jnz     short loc_18000E2AE
0x18000e2a4  mov     ecx, 8
0x18000e2a9  jmp     loc_18000E4A0
0x18000e2ae  mov     r15, [rsp+68h+Src]
0x18000e2b6  lea     rcx, [rdi+54h]; void *
0x18000e2ba  mov     dword ptr [rax+40h], 4
0x18000e2c1  mov     rdx, r15; Src
0x18000e2c4  mov     rax, [rsp+68h+arg_20]
0x18000e2cc  mov     [rdi+48h], rax
0x18000e2d0  movsxd  r8, dword ptr [rbx+118h]; Size
0x18000e2d7  call    memcpy_0
0x18000e2dc  lea     rax, [rdi+30h]
0x18000e2e0  mov     r8b, 1
0x18000e2e3  mov     [rax+8], rax
0x18000e2e7  mov     [rax], rax
0x18000e2ea  mov     eax, 8421085h
0x18000e2ef  mov     ecx, [r15+0Ch]
0x18000e2f3  mul     ecx
0x18000e2f5  mov     eax, ecx
0x18000e2f7  sub     eax, edx
0x18000e2f9  shr     eax, 1
0x18000e2fb  add     eax, edx
0x18000e2fd  shr     eax, 4
0x18000e300  imul    eax, 1Fh
0x18000e303  sub     ecx, eax
0x18000e305  mov     r14d, ecx
0x18000e308  mov     rcx, rbx
0x18000e30b  shl     r14, 5
0x18000e30f  add     r14, [rbx+108h]
0x18000e316  mov     rdx, r14
0x18000e319  call    DoEnterSyncList
0x18000e31e  test    al, al
0x18000e320  jnz     short loc_18000E33A
0x18000e322  mov     rcx, [rbx]; hHeap
0x18000e325  mov     r8, rdi; lpMem
0x18000e328  xor     edx, edx; dwFlags
0x18000e32a  call    cs:__imp_HeapFree
0x18000e330  mov     ecx, 5AAh
0x18000e335  jmp     loc_18000E4A0
0x18000e33a  test    rsi, rsi
0x18000e33d  jnz     short loc_18000E375
0x18000e33f  mov     edx, [r15+0Ch]
0x18000e343  lea     r8d, [rsi+1]
0x18000e347  mov     rcx, r14
0x18000e34a  call    FindInterfaceList
0x18000e34f  mov     rsi, rax
0x18000e352  test    rax, rax
0x18000e355  jnz     short loc_18000E375
0x18000e357  mov     rdx, r14
0x18000e35a  mov     rcx, rbx
0x18000e35d  call    LeaveSyncList
0x18000e362  mov     rcx, [rbx]; hHeap
0x18000e365  mov     r8, rdi; lpMem
0x18000e368  xor     edx, edx; dwFlags
0x18000e36a  call    cs:__imp_HeapFree
0x18000e370  jmp     loc_18000E2A4
0x18000e375  mov     r8b, 1
0x18000e378  lea     rdx, [rbx+60h]
0x18000e37c  mov     rcx, rbx
0x18000e37f  call    DoEnterSyncList
0x18000e384  test    al, al
0x18000e386  jz      short loc_18000E357
0x18000e388  mov     rax, [rbp+8]
0x18000e38c  cmp     [rax], rbp
0x18000e38f  jnz     loc_18000E494
0x18000e395  mov     [rdi+8], rax
0x18000e399  mov     [rdi], rbp
0x18000e39c  mov     [rax], rdi
0x18000e39f  lea     rax, [rdi+10h]
0x18000e3a3  mov     [rbp+8], rdi
0x18000e3a7  test    r12d, r12d
0x18000e3aa  jz      short loc_18000E3C9
0x18000e3ac  mov     rcx, [rsi+8]
0x18000e3b0  cmp     [rcx], rsi
0x18000e3b3  jnz     loc_18000E494
0x18000e3b9  mov     [rax], rsi
0x18000e3bc  mov     [rax+8], rcx
0x18000e3c0  mov     [rcx], rax
0x18000e3c3  mov     [rsi+8], rax
0x18000e3c7  jmp     short loc_18000E3E4
0x18000e3c9  mov     rcx, [rsi]
0x18000e3cc  cmp     [rcx+8], rsi
0x18000e3d0  jnz     loc_18000E494
0x18000e3d6  mov     [rax], rcx
0x18000e3d9  mov     [rax+8], rsi
0x18000e3dd  mov     [rcx+8], rax
0x18000e3e1  mov     [rsi], rax
0x18000e3e4  mov     rdx, r14
0x18000e3e7  mov     rcx, rbx
0x18000e3ea  call    LeaveSyncList
0x18000e3ef  lea     r14, [rbx+70h]
0x18000e3f3  mov     rsi, [r14]
0x18000e3f6  jmp     short loc_18000E441
0x18000e3f8  mov     rax, [rbx+120h]
0x18000e3ff  lea     rdx, [rsi+54h]
0x18000e403  lea     rcx, [rdi+74h]
0x18000e407  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e40c  test    eax, eax
0x18000e40e  js      short loc_18000E446
0x18000e410  jnz     short loc_18000E43E
0x18000e412  mov     eax, [rdi+5Ch]
0x18000e415  cmp     eax, [rsi+3Ch]
0x18000e418  jb      short loc_18000E446
0x18000e41a  jnz     short loc_18000E43E
0x18000e41c  mov     eax, [rdi+60h]
0x18000e41f  cmp     eax, [rsi+40h]
0x18000e422  jb      short loc_18000E446
0x18000e424  jnz     short loc_18000E43E
0x18000e426  mov     rax, [rbx+128h]
0x18000e42d  lea     rdx, [rsi+34h]
0x18000e431  lea     rcx, [rdi+54h]
0x18000e435  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e43a  test    eax, eax
0x18000e43c  js      short loc_18000E446
0x18000e43e  mov     rsi, [rsi]
0x18000e441  cmp     rsi, r14
0x18000e444  jnz     short loc_18000E3F8
0x18000e446  mov     rcx, [rsi+8]
0x18000e44a  cmp     [rcx], rsi
0x18000e44d  jnz     short loc_18000E494
0x18000e44f  lea     rax, [rdi+20h]
0x18000e453  mov     [rax], rsi
0x18000e456  mov     [rax+8], rcx
0x18000e45a  mov     [rcx], rax
0x18000e45d  mov     [rsi+8], rax
0x18000e461  inc     dword ptr [rbx+28h]
0x18000e464  cmp     dword ptr [rbx+28h], 10h
0x18000e468  jnz     short loc_18000E483
0x18000e46a  lock inc dword ptr [rbx+30h]
0x18000e46e  jnz     short loc_18000E483
0x18000e470  xor     r8d, r8d; Flags
0x18000e473  lea     rcx, ConsolidateNetNumberListsWI; Function
0x18000e47a  mov     rdx, rbx; Context
0x18000e47d  call    cs:__imp_RtlQueueWorkItem
0x18000e483  lea     rdx, [rbx+60h]
0x18000e487  mov     rcx, rbx
0x18000e48a  call    LeaveSyncList
0x18000e48f  mov     rax, rdi
0x18000e492  jmp     short loc_18000E4A8
0x18000e494  mov     ecx, 3
0x18000e499  int     29h; Win8: RtlFailFast(ecx)
0x18000e49b  mov     ecx, 216h; dwErrCode
0x18000e4a0  call    cs:__imp_SetLastError
0x18000e4a6  xor     eax, eax
0x18000e4a8  add     rsp, 28h
0x18000e4ac  pop     r15
0x18000e4ae  pop     r14
0x18000e4b0  pop     r13
0x18000e4b2  pop     r12
0x18000e4b4  pop     rdi
0x18000e4b5  pop     rsi
0x18000e4b6  pop     rbp
0x18000e4b7  pop     rbx
0x18000e4b8  retn
```
