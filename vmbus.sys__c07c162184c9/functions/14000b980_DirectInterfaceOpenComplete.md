# DirectInterfaceOpenComplete

- ea: `0x14000b980`
- end: `0x14000ba4b`
- name: `DirectInterfaceOpenComplete`
- size: `203`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140002e20`
- `0x140002ed0`
- `0x14000b980`
- `0x14000bddc`
- `0x140017190`

## pseudocode

```c
__int64 __fastcall DirectInterfaceOpenComplete(__int64 a1, int a2)
{
  __int64 (__fastcall *v4)(__int64, _QWORD); // rbp
  __int64 v5; // rsi
  __int64 result; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_b7e7155a638734823fba4b93e4cd9774_Traceguids, a1, a2);
  }
  InstanceWaitLockAcquire(a1);
  v4 = *(__int64 (__fastcall **)(__int64, _QWORD))(a1 + 96);
  v5 = *(_QWORD *)(a1 + 104);
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 96) = 0;
  *(_QWORD *)(a1 + 104) = 0;
  if ( a2 >= 0 )
    *(_BYTE *)(a1 + 304) = 1;
  InstanceWaitLockRelease(a1);
  result = v4(v5, (unsigned int)a2);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (result & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      return WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_b7e7155a638734823fba4b93e4cd9774_Traceguids, a1, a2);
  }
  return result;
}

```

## disassembly

```asm
0x14000b980  push    rbx
0x14000b982  push    rbp
0x14000b983  push    rsi
0x14000b984  push    rdi
0x14000b985  push    r14
0x14000b987  sub     rsp, 30h
0x14000b98b  mov     edi, edx
0x14000b98d  mov     rbx, rcx
0x14000b990  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b997  lea     r14, WPP_GLOBAL_Control
0x14000b99e  cmp     rcx, r14
0x14000b9a1  jz      short loc_14000B9CC
0x14000b9a3  mov     eax, [rcx+2Ch]
0x14000b9a6  test    al, 10h
0x14000b9a8  jz      short loc_14000B9CC
0x14000b9aa  cmp     byte ptr [rcx+29h], 4
0x14000b9ae  jb      short loc_14000B9CC
0x14000b9b0  mov     rcx, [rcx+18h]
0x14000b9b4  lea     r8, WPP_b7e7155a638734823fba4b93e4cd9774_Traceguids
0x14000b9bb  mov     edx, 18h
0x14000b9c0  mov     [rsp+58h+var_38], edi
0x14000b9c4  mov     r9, rbx
0x14000b9c7  call    WPP_SF_qd
0x14000b9cc  mov     rcx, rbx
0x14000b9cf  call    InstanceWaitLockAcquire
0x14000b9d4  mov     rbp, [rbx+60h]
0x14000b9d8  xor     eax, eax
0x14000b9da  mov     rsi, [rbx+68h]
0x14000b9de  mov     [rbx+50h], rax
0x14000b9e2  mov     [rbx+60h], rax
0x14000b9e6  mov     [rbx+68h], rax
0x14000b9ea  test    edi, edi
0x14000b9ec  js      short loc_14000B9F5
0x14000b9ee  mov     byte ptr [rbx+130h], 1
0x14000b9f5  mov     rcx, rbx
0x14000b9f8  call    InstanceWaitLockRelease
0x14000b9fd  mov     edx, edi
0x14000b9ff  mov     rcx, rsi
0x14000ba02  mov     rax, rbp
0x14000ba05  call    _guard_dispatch_icall
0x14000ba0a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ba11  cmp     rcx, r14
0x14000ba14  jz      short loc_14000BA3F
0x14000ba16  mov     eax, [rcx+2Ch]
0x14000ba19  test    al, 10h
0x14000ba1b  jz      short loc_14000BA3F
0x14000ba1d  cmp     byte ptr [rcx+29h], 4
0x14000ba21  jb      short loc_14000BA3F
0x14000ba23  mov     rcx, [rcx+18h]
0x14000ba27  lea     r8, WPP_b7e7155a638734823fba4b93e4cd9774_Traceguids
0x14000ba2e  mov     edx, 19h
0x14000ba33  mov     [rsp+58h+var_38], edi
0x14000ba37  mov     r9, rbx
0x14000ba3a  call    WPP_SF_qd
0x14000ba3f  add     rsp, 30h
0x14000ba43  pop     r14
0x14000ba45  pop     rdi
0x14000ba46  pop     rsi
0x14000ba47  pop     rbp
0x14000ba48  pop     rbx
0x14000ba49  retn
```
