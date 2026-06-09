# InterlockedCloseHandle(void * *,void *,int)

- ea: `0x180001678`
- end: `0x1800016b2`
- name: `?InterlockedCloseHandle@@YAXPEAPEAXPEAXH@Z`
- size: `58`
- prototype: `void __fastcall(void **, void *, int)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001624`
- `0x180007a50`
- `0x180007b20`
- `0x18000da90`

## callees

- `0x180001678`

## import_xrefs

- `ntdll!NtClose` at `0x1800016a6`
- `ntdll!NtClose` at `0x1800016a6`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x18000169d`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x18000169d`

## pseudocode

```c
void __fastcall InterlockedCloseHandle(void **a1, void *a2, int a3)
{
  void *v3; // rbx

  v3 = *a1;
  if ( v3 == (void *)_InterlockedCompareExchange64(
                       (volatile signed __int64 *)a1,
                       (signed __int64)a2,
                       (signed __int64)*a1)
    && a2 != v3 )
  {
    if ( a3 )
      CancelIoEx(v3, 0);
    NtClose(v3);
  }
}

```

## disassembly

```asm
0x180001678  push    rbx
0x18000167a  sub     rsp, 20h
0x18000167e  mov     rbx, [rcx]
0x180001681  mov     rax, rbx
0x180001684  lock cmpxchg [rcx], rdx
0x180001689  cmp     rbx, rax
0x18000168c  jnz     short loc_1800016AC
0x18000168e  cmp     rdx, rbx
0x180001691  jz      short loc_1800016AC
0x180001693  test    r8d, r8d
0x180001696  jz      short loc_1800016A3
0x180001698  xor     edx, edx; lpOverlapped
0x18000169a  mov     rcx, rbx; hFile
0x18000169d  call    cs:__imp_CancelIoEx
0x1800016a3  mov     rcx, rbx; Handle
0x1800016a6  call    cs:__imp_NtClose
0x1800016ac  add     rsp, 20h
0x1800016b0  pop     rbx
0x1800016b1  retn
```
