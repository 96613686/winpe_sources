# OnWriteBytesComplete(_EXTENSION_CONTROL_BLOCK *,void *,ulong,ulong)

- ea: `0x18001e710`
- end: `0x18001e89b`
- name: `?OnWriteBytesComplete@@YAXPEAU_EXTENSION_CONTROL_BLOCK@@PEAXKK@Z`
- size: `395`
- prototype: `void(struct _EXTENSION_CONTROL_BLOCK *, void *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x18000baf0`
- `0x18001cf70`
- `0x18001e680`
- `0x18001e710`
- `0x180044984`
- `0x18004d754`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18001e7d8`
- `KERNEL32!CloseHandle` at `0x18001e853`
- `KERNEL32!CloseHandle` at `0x18001e7d8`
- `KERNEL32!CloseHandle` at `0x18001e853`
- `KERNEL32!SwitchToThread` at `0x18001e7a3`
- `KERNEL32!SwitchToThread` at `0x18001e85b`
- `KERNEL32!SwitchToThread` at `0x18001e7a3`
- `KERNEL32!SwitchToThread` at `0x18001e85b`
- `KERNEL32!GetCurrentThreadId` at `0x18001e78c`
- `KERNEL32!GetCurrentThreadId` at `0x18001e832`
- `KERNEL32!GetCurrentThreadId` at `0x18001e78c`
- `KERNEL32!GetCurrentThreadId` at `0x18001e832`
- `ADVAPI32!SetThreadToken` at `0x18001e732`
- `ADVAPI32!SetThreadToken` at `0x18001e732`

## pseudocode

```c
void __fastcall OnWriteBytesComplete(struct _EXTENSION_CONTROL_BLOCK *a1, void *a2, __int64 a3, int a4)
{
  int v4; // ebx
  struct CResponseContext *v6; // rax
  struct CResponseContext *v7; // rbx
  volatile signed __int32 *v8; // rdi
  __int64 v9; // rsi
  __int64 v10; // rsi
  struct _EXTENSION_CONTROL_BLOCK *v11; // r15
  char *v12; // rbp
  int v13; // r14d
  int v14; // ebx
  char *v15; // rbp

  v4 = (int)a2;
  SetThreadToken(0, 0);
  _InterlockedDecrement(&g_lNumAsyncPending);
  v6 = CResponseContextHolder::Remove(v4);
  v7 = v6;
  if ( !v6 )
  {
    _InterlockedIncrement(&g_lBug38658Count);
    return;
  }
  v8 = (volatile signed __int32 *)*((_QWORD *)v6 + 2);
  if ( v8 )
  {
    v9 = *((_QWORD *)v6 + 3);
    if ( v9 )
    {
      if ( (unsigned int)(a4 - 10053) <= 1 )
      {
        v15 = (char *)*((_QWORD *)v6 + 1);
        CProcessEntry::OnRequestComplete(
          (CProcessEntry *)v8,
          *(_DWORD *)(v9 + 76),
          *((struct _EXTENSION_CONTROL_BLOCK **)v6 + 6),
          0);
        if ( *((_DWORD *)v7 + 8) == 1 && GetCurrentThreadId() == *((_DWORD *)v7 + 10) )
        {
          *((_DWORD *)v7 + 9) = 2;
          return;
        }
        if ( (unsigned __int64)(v15 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(v15);
        while ( *((_DWORD *)v7 + 8) )
          SwitchToThread();
        CAsyncPipe::ReturnBuffer((CAsyncPipe *)(v8 + 20), (struct CAsyncPipeOverlapped *)v9);
        MemFree(v7);
      }
      else
      {
        if ( *((_DWORD *)v6 + 8) == 1 )
        {
          if ( GetCurrentThreadId() == *((_DWORD *)v6 + 10) )
          {
            *((_DWORD *)v7 + 9) = 1;
            return;
          }
          while ( *((_DWORD *)v7 + 8) )
            SwitchToThread();
        }
        v10 = *((_QWORD *)v7 + 3);
        v8 = (volatile signed __int32 *)*((_QWORD *)v7 + 2);
        v11 = (struct _EXTENSION_CONTROL_BLOCK *)*((_QWORD *)v7 + 6);
        v12 = (char *)*((_QWORD *)v7 + 1);
        v13 = *(_DWORD *)(v10 + 76);
        MemFree(v7);
        if ( (unsigned __int64)(v12 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(v12);
        if ( *(_DWORD *)(v10 + 72) == 3 )
        {
          v14 = *(_DWORD *)(v10 + 92);
          CAsyncPipe::ReturnBuffer((CAsyncPipe *)(v8 + 20), (struct CAsyncPipeOverlapped *)v10);
          CProcessEntry::OnRequestComplete((CProcessEntry *)v8, v13, v11, v14);
        }
        else
        {
          CProcessEntry::ExecuteWorkItemsForRequest((CProcessEntry *)v8, v13, (struct CAsyncPipeOverlapped *)v10);
        }
      }
      _InterlockedDecrement(v8 + 40);
    }
  }
}

```

## disassembly

```asm
0x18001e710  mov     [rsp+arg_0], rbx
0x18001e715  mov     [rsp+arg_8], rbp
0x18001e71a  mov     [rsp+arg_10], rsi
0x18001e71f  push    rdi
0x18001e720  push    r14
0x18001e722  push    r15
0x18001e724  sub     rsp, 20h
0x18001e728  mov     rbx, rdx
0x18001e72b  xor     ecx, ecx; Thread
0x18001e72d  xor     edx, edx; Token
0x18001e72f  mov     ebp, r9d
0x18001e732  call    cs:__imp_SetThreadToken
0x18001e738  lock dec cs:?g_lNumAsyncPending@@3JA; long g_lNumAsyncPending
0x18001e73f  mov     ecx, ebx; int
0x18001e741  call    ?Remove@CResponseContextHolder@@SAPEAUCResponseContext@@J@Z; CResponseContextHolder::Remove(long)
0x18001e746  xor     r14d, r14d
0x18001e749  mov     rbx, rax
0x18001e74c  test    rax, rax
0x18001e74f  jnz     short loc_18001E75D
0x18001e751  lock inc cs:?g_lBug38658Count@@3JA; long g_lBug38658Count
0x18001e758  jmp     loc_18001E882
0x18001e75d  mov     rdi, [rax+10h]
0x18001e761  test    rdi, rdi
0x18001e764  jz      loc_18001E882
0x18001e76a  mov     rsi, [rax+18h]
0x18001e76e  test    rsi, rsi
0x18001e771  jz      loc_18001E882
0x18001e777  lea     eax, [rbp-2745h]
0x18001e77d  cmp     eax, 1
0x18001e780  jbe     loc_18001E816
0x18001e786  cmp     dword ptr [rbx+20h], 1
0x18001e78a  jnz     short loc_18001E7AF
0x18001e78c  call    cs:__imp_GetCurrentThreadId
0x18001e792  cmp     eax, [rbx+28h]
0x18001e795  jnz     short loc_18001E7A9
0x18001e797  mov     dword ptr [rbx+24h], 1
0x18001e79e  jmp     loc_18001E882
0x18001e7a3  call    cs:__imp_SwitchToThread
0x18001e7a9  cmp     [rbx+20h], r14d
0x18001e7ad  jnz     short loc_18001E7A3
0x18001e7af  mov     rsi, [rbx+18h]
0x18001e7b3  mov     rcx, rbx; lpMem
0x18001e7b6  mov     rdi, [rbx+10h]
0x18001e7ba  mov     r15, [rbx+30h]
0x18001e7be  mov     rbp, [rbx+8]
0x18001e7c2  mov     r14d, [rsi+4Ch]
0x18001e7c6  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18001e7cb  lea     rax, [rbp-1]
0x18001e7cf  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001e7d3  ja      short loc_18001E7DE
0x18001e7d5  mov     rcx, rbp; hObject
0x18001e7d8  call    cs:__imp_CloseHandle
0x18001e7de  cmp     dword ptr [rsi+48h], 3
0x18001e7e2  jnz     short loc_18001E806
0x18001e7e4  mov     ebx, [rsi+5Ch]
0x18001e7e7  lea     rcx, [rdi+50h]; this
0x18001e7eb  mov     rdx, rsi; struct CAsyncPipeOverlapped *
0x18001e7ee  call    ?ReturnBuffer@CAsyncPipe@@QEAAXPEAUCAsyncPipeOverlapped@@@Z; CAsyncPipe::ReturnBuffer(CAsyncPipeOverlapped *)
0x18001e7f3  mov     r9d, ebx; int
0x18001e7f6  mov     r8, r15; struct _EXTENSION_CONTROL_BLOCK *
0x18001e7f9  mov     edx, r14d; int
0x18001e7fc  mov     rcx, rdi; this
0x18001e7ff  call    ?OnRequestComplete@CProcessEntry@@QEAAXJPEAU_EXTENSION_CONTROL_BLOCK@@H@Z; CProcessEntry::OnRequestComplete(long,_EXTENSION_CONTROL_BLOCK *,int)
0x18001e804  jmp     short loc_18001E87B
0x18001e806  mov     r8, rsi; struct CAsyncPipeOverlapped *
0x18001e809  mov     edx, r14d; int
0x18001e80c  mov     rcx, rdi; this
0x18001e80f  call    ?ExecuteWorkItemsForRequest@CProcessEntry@@QEAAXJPEAUCAsyncPipeOverlapped@@@Z; CProcessEntry::ExecuteWorkItemsForRequest(long,CAsyncPipeOverlapped *)
0x18001e814  jmp     short loc_18001E87B
0x18001e816  mov     r8, [rbx+30h]; struct _EXTENSION_CONTROL_BLOCK *
0x18001e81a  xor     r9d, r9d; int
0x18001e81d  mov     edx, [rsi+4Ch]; int
0x18001e820  mov     rcx, rdi; this
0x18001e823  mov     rbp, [rbx+8]
0x18001e827  call    ?OnRequestComplete@CProcessEntry@@QEAAXJPEAU_EXTENSION_CONTROL_BLOCK@@H@Z; CProcessEntry::OnRequestComplete(long,_EXTENSION_CONTROL_BLOCK *,int)
0x18001e82c  cmp     dword ptr [rbx+20h], 1
0x18001e830  jnz     short loc_18001E846
0x18001e832  call    cs:__imp_GetCurrentThreadId
0x18001e838  cmp     eax, [rbx+28h]
0x18001e83b  jnz     short loc_18001E846
0x18001e83d  mov     dword ptr [rbx+24h], 2
0x18001e844  jmp     short loc_18001E882
0x18001e846  lea     rax, [rbp-1]
0x18001e84a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001e84e  ja      short loc_18001E861
0x18001e850  mov     rcx, rbp; hObject
0x18001e853  call    cs:__imp_CloseHandle
0x18001e859  jmp     short loc_18001E861
0x18001e85b  call    cs:__imp_SwitchToThread
0x18001e861  cmp     [rbx+20h], r14d
0x18001e865  jnz     short loc_18001E85B
0x18001e867  lea     rcx, [rdi+50h]; this
0x18001e86b  mov     rdx, rsi; struct CAsyncPipeOverlapped *
0x18001e86e  call    ?ReturnBuffer@CAsyncPipe@@QEAAXPEAUCAsyncPipeOverlapped@@@Z; CAsyncPipe::ReturnBuffer(CAsyncPipeOverlapped *)
0x18001e873  mov     rcx, rbx; lpMem
0x18001e876  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18001e87b  lock dec dword ptr [rdi+0A0h]
0x18001e882  mov     rbx, [rsp+38h+arg_0]
0x18001e887  mov     rbp, [rsp+38h+arg_8]
0x18001e88c  mov     rsi, [rsp+38h+arg_10]
0x18001e891  add     rsp, 20h
0x18001e895  pop     r15
0x18001e897  pop     r14
0x18001e899  pop     rdi
0x18001e89a  retn
```
