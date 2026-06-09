# RtmDeleteEnumHandle

- ea: `0x1800060a0`
- end: `0x18000623d`
- name: `RtmDeleteEnumHandle`
- size: `413`
- prototype: `DWORD __stdcall(RTM_ENTITY_HANDLE RtmRegHandle, RTM_ENUM_HANDLE EnumHandle)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800060a0`
- `0x180008ebc`

## callees

- `0x1800060a0`
- `0x180009adc`
- `0x18000a1bc`
- `0x18000a298`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x1800060f3`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800060f3`
- `ntdll!RtlReleaseResource` at `0x18000611a`
- `ntdll!RtlReleaseResource` at `0x18000611a`
- `KERNEL32!GetProcessHeap` at `0x18000615c`
- `KERNEL32!GetProcessHeap` at `0x1800061bf`
- `KERNEL32!GetProcessHeap` at `0x1800061df`
- `KERNEL32!GetProcessHeap` at `0x180006217`
- `KERNEL32!GetProcessHeap` at `0x18000615c`
- `KERNEL32!GetProcessHeap` at `0x1800061bf`
- `KERNEL32!GetProcessHeap` at `0x1800061df`
- `KERNEL32!GetProcessHeap` at `0x180006217`
- `KERNEL32!HeapFree` at `0x18000616a`
- `KERNEL32!HeapFree` at `0x1800061cd`
- `KERNEL32!HeapFree` at `0x1800061ed`
- `KERNEL32!HeapFree` at `0x180006225`
- `KERNEL32!HeapFree` at `0x18000616a`
- `KERNEL32!HeapFree` at `0x1800061cd`
- `KERNEL32!HeapFree` at `0x1800061ed`
- `KERNEL32!HeapFree` at `0x180006225`
- `KERNEL32!DeleteCriticalSection` at `0x1800061fd`
- `KERNEL32!DeleteCriticalSection` at `0x1800061fd`

## pseudocode

```c
DWORD __stdcall RtmDeleteEnumHandle(RTM_ENTITY_HANDLE RtmRegHandle, RTM_ENUM_HANDLE EnumHandle)
{
  unsigned __int64 v2; // rdi
  unsigned __int64 v4; // rbx
  __int64 v5; // r8
  _QWORD *v6; // rax
  struct _RTL_CRITICAL_SECTION *v7; // rcx
  volatile signed __int32 *v8; // rcx
  void *v9; // rsi
  HANDLE ProcessHeap; // rax
  void *v11; // rdx
  unsigned int i; // esi
  void *v13; // rsi
  HANDLE v14; // rax
  void *v15; // rsi
  HANDLE v16; // rax
  HANDLE v17; // rax

  v2 = (unsigned __int64)RtmRegHandle ^ 0x7754DF32;
  if ( (unsigned __int64)RtmRegHandle == 0x7754DF32
    || *(_DWORD *)(((unsigned __int64)RtmRegHandle ^ 0x7754DF32) + 0x30) == 1 )
  {
    return 6;
  }
  v4 = (unsigned __int64)EnumHandle ^ 0x7754DF32;
  switch ( *(_BYTE *)(((unsigned __int64)EnumHandle ^ 0x7754DF32) + 4) )
  {
    case 7:
      v7 = (struct _RTL_CRITICAL_SECTION *)(v4 + 48);
      break;
    case 8:
      v8 = *(volatile signed __int32 **)(((unsigned __int64)EnumHandle ^ 0x7754DF32) + 0x68);
      if ( v8 && _InterlockedExchangeAdd(v8, 0xFFFFFFFF) == 1 )
        DestroyDest(*(LPVOID *)(((unsigned __int64)EnumHandle ^ 0x7754DF32) + 0x68));
      v9 = *(void **)(v4 + 88);
      if ( v9 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v9);
      }
      v11 = *(void **)(v4 + 80);
      if ( v11 )
        RtmDeleteEnumHandle(RtmRegHandle, v11);
      for ( i = *(_DWORD *)(v4 + 112); i < *(_DWORD *)(v4 + 120); ++i )
      {
        if ( _InterlockedExchangeAdd(*(volatile signed __int32 **)(*(_QWORD *)(v4 + 128) + 8LL * i), 0xFFFFFFFF) == 1 )
          DestroyRoute(*(LPVOID *)(*(_QWORD *)(v4 + 128) + 8LL * i));
      }
      v13 = *(void **)(v4 + 24);
      if ( v13 )
      {
        v14 = GetProcessHeap();
        HeapFree(v14, 0, v13);
      }
      v15 = *(void **)(v4 + 128);
      if ( v15 )
      {
        v16 = GetProcessHeap();
        HeapFree(v16, 0, v15);
      }
      v7 = (struct _RTL_CRITICAL_SECTION *)(v4 + 40);
      break;
    case 9:
      v7 = (struct _RTL_CRITICAL_SECTION *)(v4 + 32);
      break;
    case 0xC:
      RtlAcquireResourceExclusive((PRTL_RESOURCE)(v2 + 56), 1u);
      v5 = *(_QWORD *)(v4 + 40);
      if ( *(_QWORD *)(v5 + 8) != v4 + 40 || (v6 = *(_QWORD **)(v4 + 48), *v6 != v4 + 40) )
        __fastfail(3u);
      *v6 = v5;
      *(_QWORD *)(v5 + 8) = v6;
      RtlReleaseResource((PRTL_RESOURCE)(v2 + 56));
      goto LABEL_31;
    default:
      return 6;
  }
  DeleteCriticalSection(v7);
LABEL_31:
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v2, 0xFFFFFFFF) == 1 )
    DestroyEntity((char *)v2);
  v17 = GetProcessHeap();
  HeapFree(v17, 0, (LPVOID)v4);
  return 0;
}

```

## disassembly

```asm
0x1800060a0  push    rbx
0x1800060a2  push    rbp
0x1800060a3  push    rsi
0x1800060a4  push    rdi
0x1800060a5  sub     rsp, 28h
0x1800060a9  mov     rdi, rcx
0x1800060ac  mov     eax, 7754DF32h
0x1800060b1  xor     rdi, rax
0x1800060b4  mov     rbx, rdx
0x1800060b7  mov     rbp, rcx
0x1800060ba  jz      loc_18000622F
0x1800060c0  cmp     dword ptr [rdi+30h], 1
0x1800060c4  jz      loc_18000622F
0x1800060ca  xor     rbx, rax
0x1800060cd  movzx   ecx, byte ptr [rbx+4]
0x1800060d1  sub     ecx, 7
0x1800060d4  jz      loc_1800061F9
0x1800060da  sub     ecx, 1
0x1800060dd  jz      short loc_180006135
0x1800060df  sub     ecx, 1
0x1800060e2  jz      short loc_18000612C
0x1800060e4  cmp     ecx, 3
0x1800060e7  jnz     loc_18000622F
0x1800060ed  mov     dl, 1; Wait
0x1800060ef  lea     rcx, [rdi+38h]; Resource
0x1800060f3  call    cs:__imp_RtlAcquireResourceExclusive
0x1800060f9  lea     rdx, [rbx+28h]
0x1800060fd  mov     r8, [rdx]
0x180006100  cmp     [r8+8], rdx
0x180006104  jnz     short loc_180006125
0x180006106  mov     rax, [rdx+8]
0x18000610a  cmp     [rax], rdx
0x18000610d  jnz     short loc_180006125
0x18000610f  mov     [rax], r8
0x180006112  lea     rcx, [rdi+38h]; Resource
0x180006116  mov     [r8+8], rax
0x18000611a  call    cs:__imp_RtlReleaseResource
0x180006120  jmp     loc_180006203
0x180006125  mov     ecx, 3
0x18000612a  int     29h; Win8: RtlFailFast(ecx)
0x18000612c  lea     rcx, [rbx+20h]
0x180006130  jmp     loc_1800061FD
0x180006135  mov     rcx, [rbx+68h]
0x180006139  test    rcx, rcx
0x18000613c  jz      short loc_180006153
0x18000613e  or      eax, 0FFFFFFFFh
0x180006141  lock xadd [rcx], eax
0x180006145  cmp     eax, 1
0x180006148  jnz     short loc_180006153
0x18000614a  mov     rcx, [rbx+68h]; lpMem
0x18000614e  call    DestroyDest
0x180006153  mov     rsi, [rbx+58h]
0x180006157  test    rsi, rsi
0x18000615a  jz      short loc_180006170
0x18000615c  call    cs:__imp_GetProcessHeap
0x180006162  mov     r8, rsi; lpMem
0x180006165  xor     edx, edx; dwFlags
0x180006167  mov     rcx, rax; hHeap
0x18000616a  call    cs:__imp_HeapFree
0x180006170  mov     rdx, [rbx+50h]; EnumHandle
0x180006174  test    rdx, rdx
0x180006177  jz      short loc_180006181
0x180006179  mov     rcx, rbp; RtmRegHandle
0x18000617c  call    RtmDeleteEnumHandle
0x180006181  mov     esi, [rbx+70h]
0x180006184  jmp     short loc_1800061B1
0x180006186  mov     rax, [rbx+80h]
0x18000618d  mov     edx, esi
0x18000618f  mov     rcx, [rax+rdx*8]
0x180006193  or      eax, 0FFFFFFFFh
0x180006196  lock xadd [rcx], eax
0x18000619a  cmp     eax, 1
0x18000619d  jnz     short loc_1800061AF
0x18000619f  mov     rcx, [rbx+80h]
0x1800061a6  mov     rcx, [rcx+rdx*8]; lpMem
0x1800061aa  call    DestroyRoute
0x1800061af  inc     esi
0x1800061b1  cmp     esi, [rbx+78h]
0x1800061b4  jb      short loc_180006186
0x1800061b6  mov     rsi, [rbx+18h]
0x1800061ba  test    rsi, rsi
0x1800061bd  jz      short loc_1800061D3
0x1800061bf  call    cs:__imp_GetProcessHeap
0x1800061c5  mov     r8, rsi; lpMem
0x1800061c8  xor     edx, edx; dwFlags
0x1800061ca  mov     rcx, rax; hHeap
0x1800061cd  call    cs:__imp_HeapFree
0x1800061d3  mov     rsi, [rbx+80h]
0x1800061da  test    rsi, rsi
0x1800061dd  jz      short loc_1800061F3
0x1800061df  call    cs:__imp_GetProcessHeap
0x1800061e5  mov     r8, rsi; lpMem
0x1800061e8  xor     edx, edx; dwFlags
0x1800061ea  mov     rcx, rax; hHeap
0x1800061ed  call    cs:__imp_HeapFree
0x1800061f3  lea     rcx, [rbx+28h]
0x1800061f7  jmp     short loc_1800061FD
0x1800061f9  lea     rcx, [rbx+30h]; lpCriticalSection
0x1800061fd  call    cs:__imp_DeleteCriticalSection
0x180006203  or      eax, 0FFFFFFFFh
0x180006206  lock xadd [rdi], eax
0x18000620a  cmp     eax, 1
0x18000620d  jnz     short loc_180006217
0x18000620f  mov     rcx, rdi; lpMem
0x180006212  call    DestroyEntity
0x180006217  call    cs:__imp_GetProcessHeap
0x18000621d  mov     r8, rbx; lpMem
0x180006220  xor     edx, edx; dwFlags
0x180006222  mov     rcx, rax; hHeap
0x180006225  call    cs:__imp_HeapFree
0x18000622b  xor     eax, eax
0x18000622d  jmp     short loc_180006234
0x18000622f  mov     eax, 6
0x180006234  add     rsp, 28h
0x180006238  pop     rdi
0x180006239  pop     rsi
0x18000623a  pop     rbp
0x18000623b  pop     rbx
0x18000623c  retn
```
