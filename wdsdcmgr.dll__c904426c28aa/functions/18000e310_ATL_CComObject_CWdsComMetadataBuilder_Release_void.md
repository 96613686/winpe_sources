# ATL::CComObject<CWdsComMetadataBuilder>::Release(void)

- ea: `0x18000e310`
- end: `0x18000e37d`
- name: `?Release@?$CComObject@VCWdsComMetadataBuilder@@@ATL@@UEAAKXZ`
- size: `109`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000e310`
- `0x180015cc0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWdsComMetadataBuilder>::Release(volatile signed __int32 *a1)
{
  signed __int32 i; // r8d
  unsigned __int32 v2; // ebx

  for ( i = *((_DWORD *)a1 + 2);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange(a1 + 2, i - 1, i);
        i = *((_DWORD *)a1 + 2) )
  {
    ;
  }
  v2 = i - 1;
  if ( i == 1 )
  {
    _InterlockedAdd((volatile signed __int32 *)ATL::_pAtlModule + 3, 1u);
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)a1 + 344LL))(a1);
    _InterlockedDecrement((volatile signed __int32 *)ATL::_pAtlModule + 3);
  }
  return v2;
}

```

## disassembly

```asm
0x18000e310  push    rbx
0x18000e312  sub     rsp, 20h
0x18000e316  mov     r8d, [rcx+8]
0x18000e31a  mov     r9, rcx
0x18000e31d  mov     ecx, 7FFFFFFFh
0x18000e322  jmp     short loc_18000E337
0x18000e324  lea     edx, [r8-1]
0x18000e328  mov     eax, r8d
0x18000e32b  lock cmpxchg [r9+8], edx
0x18000e331  jz      short loc_18000E33C
0x18000e333  mov     r8d, [r9+8]
0x18000e337  cmp     r8d, ecx
0x18000e33a  jnz     short loc_18000E324
0x18000e33c  lea     ebx, [r8-1]
0x18000e340  test    ebx, ebx
0x18000e342  jnz     short loc_18000E375
0x18000e344  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000e34b  lea     edx, [rbx+1]
0x18000e34e  lock add [rax+0Ch], edx
0x18000e352  test    r9, r9
0x18000e355  jz      short loc_18000E36A
0x18000e357  mov     rcx, [r9]
0x18000e35a  mov     rax, [rcx+158h]
0x18000e361  mov     rcx, r9
0x18000e364  call    cs:__guard_dispatch_icall_fptr
0x18000e36a  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000e371  lock dec dword ptr [rcx+0Ch]
0x18000e375  mov     eax, ebx
0x18000e377  add     rsp, 20h
0x18000e37b  pop     rbx
0x18000e37c  retn
```
