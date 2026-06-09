# _EcRpcDeleteSubscription

- ea: `0x180003560`
- end: `0x180003593`
- name: `_EcRpcDeleteSubscription`
- size: `51`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180003560`
- `0x180003f08`

## pseudocode

```c
__int64 __fastcall EcRpcDeleteSubscription(__int64 a1, const unsigned __int16 *a2, unsigned int a3)
{
  __int64 result; // rax
  wmi::Exception *v4; // [rsp+20h] [rbp-18h] BYREF

  if ( !a2 || !*a2 )
    return 87;
  try
  {
    CollectorService::DeleteSubscription(g_service, a2, a3);
    result = 0;
  }
  catch ( wmi::Exception *v4 )
  {
    return (**(unsigned int (__fastcall ***)(wmi::Exception *))v4)(v4);
  }
  catch ( ... )
  {
    EcTerminateService();
  }
  return result;
}

```

## disassembly

```asm
0x180003560  push    rbx
0x180003562  sub     rsp, 30h
0x180003566  xor     ebx, ebx
0x180003568  test    rdx, rdx
0x18000356b  jz      short loc_180003588
0x18000356d  cmp     [rdx], bx
0x180003570  jz      short loc_180003588
0x180003572  mov     rcx, cs:?g_service@@3PEAVCollectorService@@EA; this
0x180003579  call    ?DeleteSubscription@CollectorService@@QEAAXPEBGK@Z; CollectorService::DeleteSubscription(ushort const *,ulong)
0x18000357e  mov     eax, ebx
0x180003580  jmp     short loc_18000358D
0x180003582  mov     eax, [rsp+38h+arg_8]
0x180003586  jmp     short loc_18000358D
0x180003588  mov     eax, 57h ; 'W'
0x18000358d  add     rsp, 30h
0x180003591  pop     rbx
0x180003592  retn
```
