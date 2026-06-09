# UL_NATIVE_REQUEST::Cleanup(void)

- ea: `0x18000f840`
- end: `0x18000f8bf`
- name: `?Cleanup@UL_NATIVE_REQUEST@@AEAAXXZ`
- size: `127`
- prototype: `void __fastcall(UL_NATIVE_REQUEST *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f770`
- `0x18000f7f0`

## callees

- `0x18000f840`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f891`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f8a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f891`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f8a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f8b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f8b7`

## pseudocode

```c
void __fastcall UL_NATIVE_REQUEST::Cleanup(UL_NATIVE_REQUEST *this)
{
  void *v2; // rcx
  void *v3; // rcx
  char *v4; // rcx

  v2 = (void *)*((_QWORD *)this + 376);
  if ( v2 )
  {
    CloseHandle(v2);
    *((_QWORD *)this + 376) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 377);
  if ( v3 )
  {
    CloseHandle(v3);
    *((_QWORD *)this + 377) = 0;
  }
  v4 = (char *)*((_QWORD *)this + 368);
  if ( v4 != (char *)this + 32 )
    LocalFree(v4);
  *((_DWORD *)this + 738) = 2912;
  *((_QWORD *)this + 368) = (char *)this + 32;
}

```

## disassembly

```asm
0x18000f840  mov     [rsp+arg_0], rbx
0x18000f845  push    rdi
0x18000f846  sub     rsp, 20h
0x18000f84a  mov     rbx, rcx
0x18000f84d  mov     rcx, [rcx+0BC0h]; hObject
0x18000f854  test    rcx, rcx
0x18000f857  jnz     short loc_18000F891
0x18000f859  mov     rcx, [rbx+0BC8h]; hObject
0x18000f860  test    rcx, rcx
0x18000f863  jnz     short loc_18000F8A4
0x18000f865  mov     rcx, [rbx+0B80h]; hMem
0x18000f86c  lea     rdi, [rbx+20h]
0x18000f870  cmp     rcx, rdi
0x18000f873  jnz     short loc_18000F8B7
0x18000f875  mov     dword ptr [rbx+0B88h], 0B60h
0x18000f87f  mov     [rbx+0B80h], rdi
0x18000f886  mov     rbx, [rsp+28h+arg_0]
0x18000f88b  add     rsp, 20h
0x18000f88f  pop     rdi
0x18000f890  retn
0x18000f891  call    cs:__imp_CloseHandle
0x18000f897  mov     qword ptr [rbx+0BC0h], 0
0x18000f8a2  jmp     short loc_18000F859
0x18000f8a4  call    cs:__imp_CloseHandle
0x18000f8aa  mov     qword ptr [rbx+0BC8h], 0
0x18000f8b5  jmp     short loc_18000F865
0x18000f8b7  call    cs:__imp_LocalFree
0x18000f8bd  jmp     short loc_18000F875
```
