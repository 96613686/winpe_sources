# ATL::CComObject<CWdsDeviceControllerRequest>::Release(void)

- ea: `0x180001ac0`
- end: `0x180001b2a`
- name: `?Release@?$CComObject@VCWdsDeviceControllerRequest@@@ATL@@UEAAKXZ`
- size: `106`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001ac0`
- `0x180015cc0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWdsDeviceControllerRequest>::Release(volatile signed __int32 *a1)
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
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)a1 + 72LL))(a1);
    _InterlockedDecrement((volatile signed __int32 *)ATL::_pAtlModule + 3);
  }
  return v2;
}

```

## disassembly

```asm
0x180001ac0  push    rbx
0x180001ac2  sub     rsp, 20h
0x180001ac6  mov     r8d, [rcx+8]
0x180001aca  mov     r9, rcx
0x180001acd  mov     ecx, 7FFFFFFFh
0x180001ad2  jmp     short loc_180001AE7
0x180001ad4  lea     edx, [r8-1]
0x180001ad8  mov     eax, r8d
0x180001adb  lock cmpxchg [r9+8], edx
0x180001ae1  jz      short loc_180001AEC
0x180001ae3  mov     r8d, [r9+8]
0x180001ae7  cmp     r8d, ecx
0x180001aea  jnz     short loc_180001AD4
0x180001aec  lea     ebx, [r8-1]
0x180001af0  test    ebx, ebx
0x180001af2  jnz     short loc_180001B22
0x180001af4  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180001afb  lea     edx, [rbx+1]
0x180001afe  lock add [rax+0Ch], edx
0x180001b02  test    r9, r9
0x180001b05  jz      short loc_180001B17
0x180001b07  mov     rcx, [r9]
0x180001b0a  mov     rax, [rcx+48h]
0x180001b0e  mov     rcx, r9
0x180001b11  call    cs:__guard_dispatch_icall_fptr
0x180001b17  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180001b1e  lock dec dword ptr [rcx+0Ch]
0x180001b22  mov     eax, ebx
0x180001b24  add     rsp, 20h
0x180001b28  pop     rbx
0x180001b29  retn
```
