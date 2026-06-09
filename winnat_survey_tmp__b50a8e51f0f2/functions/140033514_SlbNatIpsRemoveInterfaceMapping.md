# SlbNatIpsRemoveInterfaceMapping

- ea: `0x140033514`
- end: `0x140033585`
- name: `SlbNatIpsRemoveInterfaceMapping`
- size: `113`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x14000820c`
- `0x140008928`
- `0x14002f9fc`
- `0x1400310f8`
- `0x1400314d4`

## callees

- `0x14001536c`
- `0x14002d008`
- `0x140033514`
- `0x140034310`
- `0x140034678`

## pseudocode

```c
__int64 __fastcall SlbNatIpsRemoveInterfaceMapping(unsigned int a1, __int64 a2, __int64 a3)
{
  __int64 result; // rax
  __int64 v6; // rbx

  if ( (xmmword_1400262E0 & 4) != 0 )
    WPP_SF_d(1026, 19, WPP_2017c49255f13d724299eee942b0d5fe_Traceguids, a1);
  result = SlbNatIpsFindInterfaceContext(a1);
  v6 = result;
  if ( result )
  {
    if ( a3 )
      result = SlbNatIpsRemoveTCAP(result, a3);
    if ( (*(_DWORD *)(v6 + 16))-- == 1 )
    {
      result = SlbNatIpsClearInterfaceContext(v6);
      *(_DWORD *)(v6 + 24) = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140033514  mov     [rsp+arg_0], rbx
0x140033519  push    rdi
0x14003351a  sub     rsp, 20h
0x14003351e  mov     rdi, r8
0x140033521  mov     ebx, ecx
0x140033523  test    byte ptr cs:xmmword_1400262E0, 4
0x14003352a  jz      short loc_140033545
0x14003352c  mov     edx, 13h
0x140033531  lea     r8, WPP_2017c49255f13d724299eee942b0d5fe_Traceguids
0x140033538  mov     ecx, 402h
0x14003353d  mov     r9d, ebx
0x140033540  call    WPP_SF_d
0x140033545  mov     ecx, ebx
0x140033547  call    SlbNatIpsFindInterfaceContext
0x14003354c  mov     rbx, rax
0x14003354f  test    rax, rax
0x140033552  jz      short loc_140033579
0x140033554  test    rdi, rdi
0x140033557  jz      short loc_140033564
0x140033559  mov     rdx, rdi
0x14003355c  mov     rcx, rax
0x14003355f  call    SlbNatIpsRemoveTCAP
0x140033564  sub     dword ptr [rbx+10h], 1
0x140033568  jnz     short loc_140033579
0x14003356a  mov     rcx, rbx
0x14003356d  call    SlbNatIpsClearInterfaceContext
0x140033572  mov     dword ptr [rbx+18h], 0
0x140033579  mov     rbx, [rsp+28h+arg_0]
0x14003357e  add     rsp, 20h
0x140033582  pop     rdi
0x140033583  retn
```
