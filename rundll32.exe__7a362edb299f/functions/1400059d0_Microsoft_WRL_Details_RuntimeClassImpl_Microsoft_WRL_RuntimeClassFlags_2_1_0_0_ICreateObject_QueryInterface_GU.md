# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICreateObject>::QueryInterface(_GUID const &,void * *)

- ea: `0x1400059d0`
- end: `0x140005a44`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UICreateObject@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `116`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400059d0`
- `0x14000c010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICreateObject>::QueryInterface(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  unsigned int v3; // ebx
  int v4; // eax

  v3 = 0;
  *a3 = 0;
  if ( *a2 )
  {
    if ( *a2 != 1964120402
      || a2[1] != *(_DWORD *)&GUID_75121952_e0d0_43e5_9380_1d80483acf72.Data2
      || a2[2] != *(_DWORD *)GUID_75121952_e0d0_43e5_9380_1d80483acf72.Data4 )
    {
      return (unsigned int)-2147467262;
    }
    v4 = *(_DWORD *)&GUID_75121952_e0d0_43e5_9380_1d80483acf72.Data4[4];
  }
  else
  {
    if ( a2[1] != *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data2
      || a2[2] != *(_DWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4 )
    {
      return (unsigned int)-2147467262;
    }
    v4 = *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data4[4];
  }
  if ( a2[3] != v4 )
    return (unsigned int)-2147467262;
  *a3 = a1;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  return v3;
}

```

## disassembly

```asm
0x1400059d0  push    rbx
0x1400059d2  sub     rsp, 20h
0x1400059d6  xor     ebx, ebx
0x1400059d8  mov     [r8], rbx
0x1400059db  cmp     [rdx], ebx
0x1400059dd  jnz     short loc_140005A11
0x1400059df  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x1400059e5  cmp     [rdx+4], eax
0x1400059e8  jnz     short loc_140005A37
0x1400059ea  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x1400059f0  cmp     [rdx+8], eax
0x1400059f3  jnz     short loc_140005A37
0x1400059f5  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x1400059fb  cmp     [rdx+0Ch], eax
0x1400059fe  jnz     short loc_140005A37
0x140005a00  mov     [r8], rcx
0x140005a03  mov     rax, [rcx]
0x140005a06  mov     rax, [rax+8]
0x140005a0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005a0f  jmp     short loc_140005A3C
0x140005a11  cmp     dword ptr [rdx], 75121952h
0x140005a17  jnz     short loc_140005A37
0x140005a19  mov     eax, dword ptr cs:_GUID_75121952_e0d0_43e5_9380_1d80483acf72.Data2
0x140005a1f  cmp     [rdx+4], eax
0x140005a22  jnz     short loc_140005A37
0x140005a24  mov     eax, dword ptr cs:_GUID_75121952_e0d0_43e5_9380_1d80483acf72.Data4
0x140005a2a  cmp     [rdx+8], eax
0x140005a2d  jnz     short loc_140005A37
0x140005a2f  mov     eax, dword ptr cs:_GUID_75121952_e0d0_43e5_9380_1d80483acf72.Data4+4
0x140005a35  jmp     short loc_1400059FB
0x140005a37  mov     ebx, 80004002h
0x140005a3c  mov     eax, ebx
0x140005a3e  add     rsp, 20h
0x140005a42  pop     rbx
0x140005a43  retn
```
