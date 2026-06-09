# CAttachmentServices::_OpValidateLocalPath(void)

- ea: `0x1800110cc`
- end: `0x18001113f`
- name: `?_OpValidateLocalPath@CAttachmentServices@@AEAAXXZ`
- size: `115`
- prototype: `void __fastcall(CAttachmentServices *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000d110`
- `0x18000f420`
- `0x1800113a0`
- `0x18001143c`

## callees

- `0x180002d10`
- `0x180003080`
- `0x180003f30`
- `0x1800110cc`

## import_xrefs

- `SHLWAPI!__imp_PathFileExistsAndAttributesW` at `0x180011113`
- `SHLWAPI!__imp_PathFileExistsAndAttributesW` at `0x180011113`

## pseudocode

```c
void __fastcall CAttachmentServices::_OpValidateLocalPath(CAttachmentServices *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  unsigned int v4; // [rsp+38h] [rbp+10h] BYREF

  v4 = 0;
  if ( (unsigned int)CAttachmentServices::PushOp(this, 1, &v4) )
  {
    if ( (unsigned int)CAttachmentServices::ReportResult(v2, *(_QWORD *)(v2 + 40) == 0 ? 0x8000FFFF : 0, 0) )
    {
      if ( !(unsigned int)PathFileExistsAndAttributesW(*(_QWORD *)(v3 + 40), 0) )
        CAttachmentServices::ReportResult(this, 2147942402LL, 0);
    }
    CAttachmentServices::PopOp(this, v4);
  }
}

```

## disassembly

```asm
0x1800110cc  push    rbx
0x1800110ce  sub     rsp, 20h
0x1800110d2  lea     r8, [rsp+28h+arg_8]
0x1800110d7  mov     [rsp+28h+arg_8], 0
0x1800110df  mov     edx, 1
0x1800110e4  mov     rbx, rcx
0x1800110e7  call    ?PushOp@CAttachmentServices@@AEAAHW4ATTACHMENT_OP@@PEAW42@@Z; CAttachmentServices::PushOp(ATTACHMENT_OP,ATTACHMENT_OP *)
0x1800110ec  test    eax, eax
0x1800110ee  jz      short loc_180011139
0x1800110f0  mov     rax, [rcx+28h]
0x1800110f4  neg     rax
0x1800110f7  sbb     edx, edx
0x1800110f9  xor     r8d, r8d
0x1800110fc  not     edx
0x1800110fe  and     edx, 8000FFFFh
0x180011104  call    ?ReportResult@CAttachmentServices@@AEAAHJW4OP_RESULT@1@@Z; CAttachmentServices::ReportResult(long,CAttachmentServices::OP_RESULT)
0x180011109  test    eax, eax
0x18001110b  jz      short loc_18001112D
0x18001110d  mov     rcx, [rcx+28h]
0x180011111  xor     edx, edx
0x180011113  call    cs:__imp_PathFileExistsAndAttributesW
0x180011119  test    eax, eax
0x18001111b  jnz     short loc_18001112D
0x18001111d  xor     r8d, r8d
0x180011120  mov     edx, 80070002h
0x180011125  mov     rcx, rbx
0x180011128  call    ?ReportResult@CAttachmentServices@@AEAAHJW4OP_RESULT@1@@Z; CAttachmentServices::ReportResult(long,CAttachmentServices::OP_RESULT)
0x18001112d  mov     edx, [rsp+28h+arg_8]
0x180011131  mov     rcx, rbx
0x180011134  call    ?PopOp@CAttachmentServices@@AEAAXW4ATTACHMENT_OP@@@Z; CAttachmentServices::PopOp(ATTACHMENT_OP)
0x180011139  add     rsp, 20h
0x18001113d  pop     rbx
0x18001113e  retn
```
