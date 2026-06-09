# SlbNatIpsRemoveInterfaceMapping

- ea: `0x140034644`
- end: `0x1400346b5`
- name: `SlbNatIpsRemoveInterfaceMapping`
- size: `113`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x14000820c`
- `0x140008928`
- `0x140030b2c`
- `0x140032228`
- `0x140032604`

## callees

- `0x140015ce8`
- `0x14002e008`
- `0x140034644`
- `0x140035620`
- `0x140035988`

## pseudocode

```c
__int64 __fastcall SlbNatIpsRemoveInterfaceMapping(unsigned int a1, __int64 a2, __int64 a3)
{
  __int64 result; // rax
  __int64 v6; // rbx

  if ( (xmmword_1400272E0 & 4) != 0 )
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
0x140034644  mov     [rsp+arg_0], rbx
0x140034649  push    rdi
0x14003464a  sub     rsp, 20h
0x14003464e  mov     rdi, r8
0x140034651  mov     ebx, ecx
0x140034653  test    byte ptr cs:xmmword_1400272E0, 4
0x14003465a  jz      short loc_140034675
0x14003465c  mov     edx, 13h
0x140034661  lea     r8, WPP_2017c49255f13d724299eee942b0d5fe_Traceguids
0x140034668  mov     ecx, 402h
0x14003466d  mov     r9d, ebx
0x140034670  call    WPP_SF_d
0x140034675  mov     ecx, ebx
0x140034677  call    SlbNatIpsFindInterfaceContext
0x14003467c  mov     rbx, rax
0x14003467f  test    rax, rax
0x140034682  jz      short loc_1400346A9
0x140034684  test    rdi, rdi
0x140034687  jz      short loc_140034694
0x140034689  mov     rdx, rdi
0x14003468c  mov     rcx, rax
0x14003468f  call    SlbNatIpsRemoveTCAP
0x140034694  sub     dword ptr [rbx+10h], 1
0x140034698  jnz     short loc_1400346A9
0x14003469a  mov     rcx, rbx
0x14003469d  call    SlbNatIpsClearInterfaceContext
0x1400346a2  mov     dword ptr [rbx+18h], 0
0x1400346a9  mov     rbx, [rsp+28h+arg_0]
0x1400346ae  add     rsp, 20h
0x1400346b2  pop     rdi
0x1400346b3  retn
```
