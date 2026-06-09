# CAttachmentServices::CheckPolicy(void)

- ea: `0x18000ce10`
- end: `0x18000ce86`
- name: `?CheckPolicy@CAttachmentServices@@UEAAJXZ`
- size: `118`
- prototype: `__int64 __fastcall(CAttachmentServices *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task`

## callees

- `0x180002d10`
- `0x180003080`
- `0x180003f30`
- `0x180004340`
- `0x18000ce10`
- `0x18001003c`
- `0x180010dbc`
- `0x180011148`

## pseudocode

```c
__int64 __fastcall CAttachmentServices::CheckPolicy(CAttachmentServices *this)
{
  CAttachmentServices *v2; // rcx
  _DWORD *v3; // rcx
  int v5; // [rsp+38h] [rbp+10h] BYREF

  v5 = 0;
  if ( (unsigned int)CAttachmentServices::PushOp(this, 2, &v5) )
  {
    CAttachmentServices::_OpStaticFileTypeTrust(v2);
    CAttachmentServices::_OpZoneCheck(this);
    if ( CAttachmentServices::Continuable(this) && *((_DWORD *)this + 70) != 1 && !*((_DWORD *)this + 71) )
      CAttachmentServices::ReportResult(v3, 1, 1);
    CAttachmentServices::PopOp((int *)this, v5);
  }
  return CAttachmentServices::Result(this);
}

```

## disassembly

```asm
0x18000ce10  push    rbx
0x18000ce12  sub     rsp, 20h
0x18000ce16  lea     r8, [rsp+28h+arg_8]
0x18000ce1b  mov     [rsp+28h+arg_8], 0
0x18000ce23  mov     edx, 2
0x18000ce28  mov     rbx, rcx
0x18000ce2b  call    ?PushOp@CAttachmentServices@@AEAAHW4ATTACHMENT_OP@@PEAW42@@Z; CAttachmentServices::PushOp(ATTACHMENT_OP,ATTACHMENT_OP *)
0x18000ce30  test    eax, eax
0x18000ce32  jz      short loc_18000CE79
0x18000ce34  call    ?_OpStaticFileTypeTrust@CAttachmentServices@@AEAAXXZ; CAttachmentServices::_OpStaticFileTypeTrust(void)
0x18000ce39  mov     rcx, rbx; this
0x18000ce3c  call    ?_OpZoneCheck@CAttachmentServices@@AEAAXXZ; CAttachmentServices::_OpZoneCheck(void)
0x18000ce41  mov     rcx, rbx; this
0x18000ce44  call    ?Continuable@CAttachmentServices@@AEAAHXZ; CAttachmentServices::Continuable(void)
0x18000ce49  test    eax, eax
0x18000ce4b  jz      short loc_18000CE6D
0x18000ce4d  mov     r8d, 1
0x18000ce53  cmp     [rbx+118h], r8d
0x18000ce5a  jz      short loc_18000CE6D
0x18000ce5c  cmp     dword ptr [rbx+11Ch], 0
0x18000ce63  jnz     short loc_18000CE6D
0x18000ce65  mov     edx, r8d
0x18000ce68  call    ?ReportResult@CAttachmentServices@@AEAAHJW4OP_RESULT@1@@Z; CAttachmentServices::ReportResult(long,CAttachmentServices::OP_RESULT)
0x18000ce6d  mov     edx, [rsp+28h+arg_8]
0x18000ce71  mov     rcx, rbx
0x18000ce74  call    ?PopOp@CAttachmentServices@@AEAAXW4ATTACHMENT_OP@@@Z; CAttachmentServices::PopOp(ATTACHMENT_OP)
0x18000ce79  mov     rcx, rbx; this
0x18000ce7c  add     rsp, 20h
0x18000ce80  pop     rbx
0x18000ce81  jmp     ?Result@CAttachmentServices@@AEAAJXZ; CAttachmentServices::Result(void)
```
