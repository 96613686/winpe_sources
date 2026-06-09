# mciGetDeviceIDA

- ea: `0x1800150e0`
- end: `0x180015128`
- name: `mciGetDeviceIDA`
- size: `72`
- prototype: `MCIDEVICEID __stdcall(LPCSTR pszDevice)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180013e9c`
- `0x1800150e0`
- `0x180015d50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800150f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800150f7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015115`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015115`

## pseudocode

```c
MCIDEVICEID __stdcall mciGetDeviceIDA(LPCSTR pszDevice)
{
  __int64 v1; // rax
  WCHAR *v2; // rdi
  DWORD CurrentThreadId; // eax
  unsigned int DeviceIDInternal; // ebx

  v1 = AllocUnicodeStr((CHAR *)pszDevice);
  v2 = (WCHAR *)v1;
  if ( v1 )
  {
    CurrentThreadId = GetCurrentThreadId();
    DeviceIDInternal = mciGetDeviceIDInternal(v2, (void *)CurrentThreadId);
    HeapFree(hHeap, 0, v2);
    LODWORD(v1) = DeviceIDInternal;
  }
  return v1;
}

```

## disassembly

```asm
0x1800150e0  mov     [rsp+arg_0], rbx
0x1800150e5  push    rdi
0x1800150e6  sub     rsp, 20h
0x1800150ea  call    AllocUnicodeStr
0x1800150ef  mov     rdi, rax
0x1800150f2  test    rax, rax
0x1800150f5  jz      short loc_18001511D
0x1800150f7  call    cs:__imp_GetCurrentThreadId
0x1800150fd  mov     edx, eax; void *
0x1800150ff  mov     rcx, rdi; lpString2
0x180015102  call    ?mciGetDeviceIDInternal@@YAIPEBGPEAX@Z; mciGetDeviceIDInternal(ushort const *,void *)
0x180015107  mov     rcx, cs:hHeap; hHeap
0x18001510e  mov     r8, rdi; lpMem
0x180015111  xor     edx, edx; dwFlags
0x180015113  mov     ebx, eax
0x180015115  call    cs:__imp_HeapFree
0x18001511b  mov     eax, ebx
0x18001511d  mov     rbx, [rsp+28h+arg_0]
0x180015122  add     rsp, 20h
0x180015126  pop     rdi
0x180015127  retn
```
