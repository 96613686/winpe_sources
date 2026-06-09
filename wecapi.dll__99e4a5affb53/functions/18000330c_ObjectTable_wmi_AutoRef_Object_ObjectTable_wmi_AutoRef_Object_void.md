# ObjectTable<wmi::AutoRef<Object>>::~ObjectTable<wmi::AutoRef<Object>>(void)

- ea: `0x18000330c`
- end: `0x180003377`
- name: `??1?$ObjectTable@V?$AutoRef@VObject@@@wmi@@@@QEAA@XZ`
- size: `107`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000c7f0`

## callees

- `0x1800026c0`
- `0x18000330c`
- `0x1800033e4`
- `0x180003f60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003370`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ObjectTable<wmi::AutoRef<Object>>::~ObjectTable<wmi::AutoRef<Object>>(__int64 a1)
{
  void **v2; // rdi
  __int64 v3; // rax
  __int64 v4; // rax

  v2 = (void **)(a1 + 40);
  std::_Tree<std::_Tmap_traits<unsigned long,wmi::AutoRef<Object>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,wmi::AutoRef<Object>>>,0>>::clear(a1 + 40);
  while ( 1 )
  {
    v3 = *(_QWORD *)(a1 + 88);
    if ( !v3 )
      break;
    v4 = v3 - 1;
    *(_QWORD *)(a1 + 88) = v4;
    if ( v4 )
      ++*(_QWORD *)(a1 + 80);
    else
      *(_QWORD *)(a1 + 80) = 0;
  }
  std::deque<unsigned long>::~deque<unsigned long>(a1 + 56);
  std::_Tree<std::_Tmap_traits<unsigned long,wmi::AutoRef<Object>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,wmi::AutoRef<Object>>>,0>>::clear(v2);
  operator delete(*v2);
  DeleteCriticalSection((LPCRITICAL_SECTION)a1);
}

```

## disassembly

```asm
0x18000330c  mov     [rsp+arg_0], rbx
0x180003311  push    rdi
0x180003312  sub     rsp, 20h
0x180003316  mov     rbx, rcx
0x180003319  lea     rdi, [rcx+28h]
0x18000331d  mov     rcx, rdi
0x180003320  call    ?clear@?$_Tree@V?$_Tmap_traits@KV?$AutoRef@VObject@@@wmi@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKV?$AutoRef@VObject@@@wmi@@@std@@@4@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<ulong,wmi::AutoRef<Object>,std::less<ulong>,std::allocator<std::pair<ulong const,wmi::AutoRef<Object>>>,0>>::clear(void)
0x180003325  lea     rcx, [rbx+38h]
0x180003329  mov     rax, [rbx+58h]
0x18000332d  test    rax, rax
0x180003330  jz      short loc_18000334C
0x180003332  sub     rax, 1
0x180003336  mov     [rcx+20h], rax
0x18000333a  jnz     short loc_180003346
0x18000333c  mov     qword ptr [rcx+18h], 0
0x180003344  jmp     short loc_180003329
0x180003346  inc     qword ptr [rcx+18h]
0x18000334a  jmp     short loc_180003329
0x18000334c  call    ??1?$deque@KV?$allocator@K@std@@@std@@QEAA@XZ; std::deque<ulong>::~deque<ulong>(void)
0x180003351  nop
0x180003352  mov     rcx, rdi
0x180003355  call    ?clear@?$_Tree@V?$_Tmap_traits@KV?$AutoRef@VObject@@@wmi@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKV?$AutoRef@VObject@@@wmi@@@std@@@4@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<ulong,wmi::AutoRef<Object>,std::less<ulong>,std::allocator<std::pair<ulong const,wmi::AutoRef<Object>>>,0>>::clear(void)
0x18000335a  mov     rcx, [rdi]; void *
0x18000335d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003362  nop
0x180003363  mov     rcx, rbx
0x180003366  mov     rbx, [rsp+28h+arg_0]
0x18000336b  add     rsp, 20h
0x18000336f  pop     rdi
0x180003370  jmp     cs:__imp_DeleteCriticalSection
```
