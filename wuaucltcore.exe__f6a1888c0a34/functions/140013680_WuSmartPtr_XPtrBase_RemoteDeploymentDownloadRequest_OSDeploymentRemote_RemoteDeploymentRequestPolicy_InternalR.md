# WuSmartPtr::XPtrBase<RemoteDeploymentDownloadRequest,OSDeploymentRemote::RemoteDeploymentRequestPolicy>::InternalRelease(void)

- ea: `0x140013680`
- end: `0x140013722`
- name: `?InternalRelease@?$XPtrBase@URemoteDeploymentDownloadRequest@@URemoteDeploymentRequestPolicy@OSDeploymentRemote@@@WuSmartPtr@@IEAAXXZ`
- size: `162`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140012be0`
- `0x1400135f4`

## callees

- `0x140013680`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400136a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400136c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400136d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400136e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400136f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400136fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400136a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400136c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400136d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400136e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400136f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400136fa`

## pseudocode

```c
void __fastcall WuSmartPtr::XPtrBase<RemoteDeploymentDownloadRequest,OSDeploymentRemote::RemoteDeploymentRequestPolicy>::InternalRelease(
        __int64 *a1)
{
  __int64 v1; // rdi
  unsigned int v3; // ebp
  LPVOID *i; // rsi
  __int64 v5; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    CoTaskMemFree(*(LPVOID *)v1);
    v3 = 0;
    for ( i = (LPVOID *)(v1 + 32); v3 < *(_DWORD *)(v1 + 24); ++v3 )
    {
      v5 = 32LL * v3;
      CoTaskMemFree(*(LPVOID *)((char *)*i + v5));
      CoTaskMemFree(*(LPVOID *)((char *)*i + v5 + 8));
      CoTaskMemFree(*(LPVOID *)((char *)*i + v5 + 24));
    }
    CoTaskMemFree(*i);
    CoTaskMemFree((LPVOID)v1);
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x140013680  mov     rax, rsp
0x140013683  mov     [rax+8], rbx
0x140013687  mov     [rax+10h], rbp
0x14001368b  mov     [rax+18h], rsi
0x14001368f  mov     [rax+20h], rdi
0x140013693  push    r14
0x140013695  sub     rsp, 20h
0x140013699  mov     rdi, [rcx]
0x14001369c  mov     r14, rcx
0x14001369f  test    rdi, rdi
0x1400136a2  jz      short loc_140013707
0x1400136a4  mov     rcx, [rdi]; pv
0x1400136a7  call    cs:__imp_CoTaskMemFree
0x1400136ad  xor     ebp, ebp
0x1400136af  lea     rsi, [rdi+20h]
0x1400136b3  cmp     [rdi+18h], ebp
0x1400136b6  jbe     short loc_1400136EE
0x1400136b8  mov     rcx, [rsi]
0x1400136bb  mov     ebx, ebp
0x1400136bd  shl     rbx, 5
0x1400136c1  mov     rcx, [rcx+rbx]; pv
0x1400136c5  call    cs:__imp_CoTaskMemFree
0x1400136cb  mov     rcx, [rsi]
0x1400136ce  mov     rcx, [rcx+rbx+8]; pv
0x1400136d3  call    cs:__imp_CoTaskMemFree
0x1400136d9  mov     rcx, [rsi]
0x1400136dc  mov     rcx, [rcx+rbx+18h]; pv
0x1400136e1  call    cs:__imp_CoTaskMemFree
0x1400136e7  inc     ebp
0x1400136e9  cmp     ebp, [rdi+18h]
0x1400136ec  jb      short loc_1400136B8
0x1400136ee  mov     rcx, [rsi]; pv
0x1400136f1  call    cs:__imp_CoTaskMemFree
0x1400136f7  mov     rcx, rdi; pv
0x1400136fa  call    cs:__imp_CoTaskMemFree
0x140013700  mov     qword ptr [r14], 0
0x140013707  mov     rbx, [rsp+28h+arg_0]
0x14001370c  mov     rbp, [rsp+28h+arg_8]
0x140013711  mov     rsi, [rsp+28h+arg_10]
0x140013716  mov     rdi, [rsp+28h+arg_18]
0x14001371b  add     rsp, 20h
0x14001371f  pop     r14
0x140013721  retn
```
