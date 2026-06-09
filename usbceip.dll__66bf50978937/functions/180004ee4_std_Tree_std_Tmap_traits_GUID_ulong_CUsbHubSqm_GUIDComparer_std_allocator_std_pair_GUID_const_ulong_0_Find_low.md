# std::_Tree<std::_Tmap_traits<_GUID,ulong,CUsbHubSqm::GUIDComparer,std::allocator<std::pair<_GUID const,ulong>>,0>>::_Find_lower_bound<_GUID>(_GUID const &)

- ea: `0x180004ee4`
- end: `0x180004f5f`
- name: `??$_Find_lower_bound@U_GUID@@@?$_Tree@V?$_Tmap_traits@U_GUID@@KUGUIDComparer@CUsbHubSqm@@V?$allocator@U?$pair@$$CBU_GUID@@K@std@@@std@@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@K@std@@PEAX@std@@@1@AEBU_GUID@@@Z`
- size: `123`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004f98`
- `0x180005258`

## callees

- `0x180004ee4`
- `0x1800051e0`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<_GUID,unsigned long,CUsbHubSqm::GUIDComparer,std::allocator<std::pair<_GUID const,unsigned long>>,0>>::_Find_lower_bound<_GUID>(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  __int64 *v5; // r9
  __int64 *v6; // rbx
  int v7; // eax

  v5 = *(__int64 **)(*(_QWORD *)a1 + 8LL);
  *a2 = v5;
  v6 = v5;
  a2[1] = 0;
  for ( a2[2] = *(_QWORD *)a1; !*((_BYTE *)v6 + 25); v6 = (__int64 *)*v6 )
  {
    *a2 = v6;
    if ( (unsigned __int8)CUsbHubSqm::GUIDComparer::operator()(a1, (char *)v6 + 28, a3) )
    {
      v6 += 2;
      v7 = 0;
    }
    else
    {
      a2[2] = v6;
      v7 = 1;
    }
    *((_DWORD *)a2 + 2) = v7;
  }
  return a2;
}

```

## disassembly

```asm
0x180004ee4  mov     [rsp+arg_0], rbx
0x180004ee9  mov     [rsp+arg_8], rsi
0x180004eee  push    rdi
0x180004eef  sub     rsp, 20h
0x180004ef3  mov     rax, [rcx]
0x180004ef6  mov     rsi, r8
0x180004ef9  mov     rdi, rdx
0x180004efc  mov     r9, [rax+8]
0x180004f00  mov     [rdx], r9
0x180004f03  mov     rbx, r9
0x180004f06  mov     qword ptr [rdx+8], 0
0x180004f0e  mov     rax, [rcx]
0x180004f11  mov     [rdx+10h], rax
0x180004f15  cmp     byte ptr [r9+19h], 0
0x180004f1a  jnz     short loc_180004F4C
0x180004f1c  lea     rdx, [rbx+1Ch]
0x180004f20  mov     [rdi], rbx
0x180004f23  mov     r8, rsi
0x180004f26  call    ??RGUIDComparer@CUsbHubSqm@@QEBA_NAEBU_GUID@@0@Z; CUsbHubSqm::GUIDComparer::operator()(_GUID const &,_GUID const &)
0x180004f2b  test    al, al
0x180004f2d  jz      short loc_180004F37
0x180004f2f  add     rbx, 10h
0x180004f33  xor     eax, eax
0x180004f35  jmp     short loc_180004F40
0x180004f37  mov     [rdi+10h], rbx
0x180004f3b  mov     eax, 1
0x180004f40  mov     [rdi+8], eax
0x180004f43  mov     rbx, [rbx]
0x180004f46  cmp     byte ptr [rbx+19h], 0
0x180004f4a  jz      short loc_180004F1C
0x180004f4c  mov     rbx, [rsp+28h+arg_0]
0x180004f51  mov     rax, rdi
0x180004f54  mov     rsi, [rsp+28h+arg_8]
0x180004f59  add     rsp, 20h
0x180004f5d  pop     rdi
0x180004f5e  retn
```
