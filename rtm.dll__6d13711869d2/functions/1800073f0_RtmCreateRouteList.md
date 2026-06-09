# RtmCreateRouteList

- ea: `0x1800073f0`
- end: `0x180007460`
- name: `RtmCreateRouteList`
- size: `112`
- prototype: `DWORD __stdcall(RTM_ENTITY_HANDLE RtmRegHandle, PRTM_ROUTE_LIST_HANDLE RouteListHandle)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800073f0`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180007421`
- `KERNEL32!HeapAlloc` at `0x180007421`
- `KERNEL32!GetProcessHeap` at `0x18000740f`
- `KERNEL32!GetProcessHeap` at `0x18000740f`

## pseudocode

```c
DWORD __stdcall RtmCreateRouteList(RTM_ENTITY_HANDLE RtmRegHandle, PRTM_ROUTE_LIST_HANDLE RouteListHandle)
{
  volatile signed __int32 *v3; // rbx
  HANDLE ProcessHeap; // rax
  char *v5; // rax
  unsigned __int64 v6; // rcx
  _QWORD *v8; // rax

  v3 = (volatile signed __int32 *)((unsigned __int64)RtmRegHandle ^ 0x7754DF32);
  if ( (unsigned __int64)RtmRegHandle == 0x7754DF32
    || *(_DWORD *)(((unsigned __int64)RtmRegHandle ^ 0x7754DF32) + 0x30) == 1 )
  {
    return 6;
  }
  ProcessHeap = GetProcessHeap();
  v5 = (char *)HeapAlloc(ProcessHeap, 8u, 0x18u);
  v6 = (unsigned __int64)v5;
  if ( !v5 )
    return 8;
  v8 = v5 + 8;
  v8[1] = v8;
  *v8 = v8;
  _InterlockedIncrement(v3);
  *RouteListHandle = (HANDLE)(v6 ^ 0x7754DF32);
  return 0;
}

```

## disassembly

```asm
0x1800073f0  mov     [rsp+arg_0], rbx
0x1800073f5  push    rdi
0x1800073f6  sub     rsp, 20h
0x1800073fa  mov     rbx, rcx
0x1800073fd  mov     rdi, rdx
0x180007400  xor     rbx, 7754DF32h
0x180007407  jz      short loc_180007450
0x180007409  cmp     dword ptr [rbx+30h], 1
0x18000740d  jz      short loc_180007450
0x18000740f  call    cs:__imp_GetProcessHeap
0x180007415  mov     edx, 8; dwFlags
0x18000741a  mov     rcx, rax; hHeap
0x18000741d  lea     r8d, [rdx+10h]; dwBytes
0x180007421  call    cs:__imp_HeapAlloc
0x180007427  mov     rcx, rax
0x18000742a  test    rax, rax
0x18000742d  jnz     short loc_180007434
0x18000742f  lea     eax, [rcx+8]
0x180007432  jmp     short loc_180007455
0x180007434  add     rax, 8
0x180007438  mov     [rax+8], rax
0x18000743c  mov     [rax], rax
0x18000743f  lock inc dword ptr [rbx]
0x180007442  xor     rcx, 7754DF32h
0x180007449  mov     [rdi], rcx
0x18000744c  xor     eax, eax
0x18000744e  jmp     short loc_180007455
0x180007450  mov     eax, 6
0x180007455  mov     rbx, [rsp+28h+arg_0]
0x18000745a  add     rsp, 20h
0x18000745e  pop     rdi
0x18000745f  retn
```
