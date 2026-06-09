# WuSmartPtr::XPtrBase<RemoteDeploymentDownloadRequest,OSDeploymentRemote::RemoteDeploymentRequestPolicy>::InternalRelease(void)

- ea: `0x180023f6c`
- end: `0x18002400e`
- name: `?InternalRelease@?$XPtrBase@URemoteDeploymentDownloadRequest@@URemoteDeploymentRequestPolicy@OSDeploymentRemote@@@WuSmartPtr@@IEAAXXZ`
- size: `162`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180021730`
- `0x180023c10`

## callees

- `0x180023f6c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023f93`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023fb1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023fbf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023fcd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023fdd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023fe6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023f93`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023fb1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023fbf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023fcd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023fdd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023fe6`

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
0x180023f6c  mov     rax, rsp
0x180023f6f  mov     [rax+8], rbx
0x180023f73  mov     [rax+10h], rbp
0x180023f77  mov     [rax+18h], rsi
0x180023f7b  mov     [rax+20h], rdi
0x180023f7f  push    r14
0x180023f81  sub     rsp, 20h
0x180023f85  mov     rdi, [rcx]
0x180023f88  mov     r14, rcx
0x180023f8b  test    rdi, rdi
0x180023f8e  jz      short loc_180023FF3
0x180023f90  mov     rcx, [rdi]; pv
0x180023f93  call    cs:__imp_CoTaskMemFree
0x180023f99  xor     ebp, ebp
0x180023f9b  lea     rsi, [rdi+20h]
0x180023f9f  cmp     [rdi+18h], ebp
0x180023fa2  jbe     short loc_180023FDA
0x180023fa4  mov     rcx, [rsi]
0x180023fa7  mov     ebx, ebp
0x180023fa9  shl     rbx, 5
0x180023fad  mov     rcx, [rcx+rbx]; pv
0x180023fb1  call    cs:__imp_CoTaskMemFree
0x180023fb7  mov     rcx, [rsi]
0x180023fba  mov     rcx, [rcx+rbx+8]; pv
0x180023fbf  call    cs:__imp_CoTaskMemFree
0x180023fc5  mov     rcx, [rsi]
0x180023fc8  mov     rcx, [rcx+rbx+18h]; pv
0x180023fcd  call    cs:__imp_CoTaskMemFree
0x180023fd3  inc     ebp
0x180023fd5  cmp     ebp, [rdi+18h]
0x180023fd8  jb      short loc_180023FA4
0x180023fda  mov     rcx, [rsi]; pv
0x180023fdd  call    cs:__imp_CoTaskMemFree
0x180023fe3  mov     rcx, rdi; pv
0x180023fe6  call    cs:__imp_CoTaskMemFree
0x180023fec  mov     qword ptr [r14], 0
0x180023ff3  mov     rbx, [rsp+28h+arg_0]
0x180023ff8  mov     rbp, [rsp+28h+arg_8]
0x180023ffd  mov     rsi, [rsp+28h+arg_10]
0x180024002  mov     rdi, [rsp+28h+arg_18]
0x180024007  add     rsp, 20h
0x18002400b  pop     r14
0x18002400d  retn
```
