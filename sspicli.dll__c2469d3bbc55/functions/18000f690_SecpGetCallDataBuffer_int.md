# SecpGetCallDataBuffer(int *)

- ea: `0x18000f690`
- end: `0x18000f710`
- name: `?SecpGetCallDataBuffer@@YAPEAU_LSA_PER_THREAD_CALL_DATA@@PEAH@Z`
- size: `128`
- prototype: `struct _LSA_PER_THREAD_CALL_DATA *__fastcall(int *)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000f520`
- `0x18000f620`
- `0x180014340`

## callees

- `0x18000f690`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f6d3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f6d3`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000f6f6`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000f6f6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000f6b7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000f6b7`

## pseudocode

```c
struct _LSA_PER_THREAD_CALL_DATA *__fastcall SecpGetCallDataBuffer(int *a1)
{
  LPVOID Value; // rax
  HLOCAL v3; // rbx
  HLOCAL v4; // rax

  if ( (DllState & 0x20000000) != 0 )
  {
    *a1 = 0;
  }
  else
  {
    Value = TlsGetValue(SecTlsIP);
    *a1 = 0;
    v3 = Value;
    if ( Value )
      return (struct _LSA_PER_THREAD_CALL_DATA *)v3;
  }
  v4 = LocalAlloc(0x40u, 0x30u);
  v3 = v4;
  if ( v4 )
  {
    if ( (DllState & 0x20000000) == 0 )
      TlsSetValue(SecTlsIP, v4);
    *a1 = 1;
  }
  return (struct _LSA_PER_THREAD_CALL_DATA *)v3;
}

```

## disassembly

```asm
0x18000f690  mov     [rsp+arg_0], rbx
0x18000f695  push    rdi
0x18000f696  sub     rsp, 20h
0x18000f69a  test    cs:DllState, 20000000h
0x18000f6a4  mov     rdi, rcx
0x18000f6a7  jz      short loc_18000F6B1
0x18000f6a9  mov     dword ptr [rcx], 0
0x18000f6af  jmp     short loc_18000F6CB
0x18000f6b1  mov     ecx, cs:SecTlsIP; dwTlsIndex
0x18000f6b7  call    cs:__imp_TlsGetValue
0x18000f6bd  mov     dword ptr [rdi], 0
0x18000f6c3  mov     rbx, rax
0x18000f6c6  test    rax, rax
0x18000f6c9  jnz     short loc_18000F702
0x18000f6cb  mov     edx, 30h ; '0'; uBytes
0x18000f6d0  lea     ecx, [rdx+10h]; uFlags
0x18000f6d3  call    cs:__imp_LocalAlloc
0x18000f6d9  mov     rbx, rax
0x18000f6dc  test    rax, rax
0x18000f6df  jz      short loc_18000F702
0x18000f6e1  test    cs:DllState, 20000000h
0x18000f6eb  jnz     short loc_18000F6FC
0x18000f6ed  mov     ecx, cs:SecTlsIP; dwTlsIndex
0x18000f6f3  mov     rdx, rax; lpTlsValue
0x18000f6f6  call    cs:__imp_TlsSetValue
0x18000f6fc  mov     dword ptr [rdi], 1
0x18000f702  mov     rax, rbx
0x18000f705  mov     rbx, [rsp+28h+arg_0]
0x18000f70a  add     rsp, 20h
0x18000f70e  pop     rdi
0x18000f70f  retn
```
