# CAttachmentServices::_OpStaticFileTypeTrust(void)

- ea: `0x180010dbc`
- end: `0x180010e33`
- name: `?_OpStaticFileTypeTrust@CAttachmentServices@@AEAAXXZ`
- size: `119`
- prototype: `void __fastcall(CAttachmentServices *__hidden this)`
- caller_count: `5`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ce10`
- `0x18000d110`
- `0x18000f420`
- `0x1800113a0`
- `0x18001143c`

## callees

- `0x180002d10`
- `0x180003080`
- `0x180003f30`
- `0x180006844`
- `0x18000699c`
- `0x180010dbc`

## import_xrefs

- `SHLWAPI!__imp_AssocGetUrlAction` at `0x180010e18`
- `SHLWAPI!__imp_AssocGetUrlAction` at `0x180010e18`

## pseudocode

```c
void __fastcall CAttachmentServices::_OpStaticFileTypeTrust(CAttachmentServices *this)
{
  CAttachmentServices *v2; // rcx
  const unsigned __int16 *v3; // rax
  CAttachmentServices *v4; // rcx
  const unsigned __int16 *Type; // rax
  unsigned int v6; // [rsp+38h] [rbp+10h] BYREF

  v6 = 0;
  if ( (unsigned int)CAttachmentServices::PushOp(this, 6, &v6) )
  {
    if ( *((_DWORD *)v2 + 2) )
    {
      *((_DWORD *)v2 + 22) = 6150;
    }
    else
    {
      v3 = CAttachmentServices::_FileName(v2);
      if ( (unsigned int)CAttachmentServices::ReportResult(this, v3 == 0 ? 0x8000FFFF : 0, 0) )
      {
        Type = CAttachmentServices::_GetType(v4);
        *((_DWORD *)this + 22) = AssocGetUrlAction(Type);
      }
    }
    CAttachmentServices::PopOp(this, v6);
  }
}

```

## disassembly

```asm
0x180010dbc  push    rbx
0x180010dbe  sub     rsp, 20h
0x180010dc2  lea     r8, [rsp+28h+arg_8]
0x180010dc7  mov     [rsp+28h+arg_8], 0
0x180010dcf  mov     edx, 6
0x180010dd4  mov     rbx, rcx
0x180010dd7  call    ?PushOp@CAttachmentServices@@AEAAHW4ATTACHMENT_OP@@PEAW42@@Z; CAttachmentServices::PushOp(ATTACHMENT_OP,ATTACHMENT_OP *)
0x180010ddc  test    eax, eax
0x180010dde  jz      short loc_180010E2D
0x180010de0  cmp     dword ptr [rcx+8], 0
0x180010de4  jz      short loc_180010DEF
0x180010de6  mov     dword ptr [rcx+58h], 1806h
0x180010ded  jmp     short loc_180010E21
0x180010def  call    ?_FileName@CAttachmentServices@@AEAAPEBGXZ; CAttachmentServices::_FileName(void)
0x180010df4  neg     rax
0x180010df7  mov     rcx, rbx
0x180010dfa  sbb     edx, edx
0x180010dfc  xor     r8d, r8d
0x180010dff  not     edx
0x180010e01  and     edx, 8000FFFFh
0x180010e07  call    ?ReportResult@CAttachmentServices@@AEAAHJW4OP_RESULT@1@@Z; CAttachmentServices::ReportResult(long,CAttachmentServices::OP_RESULT)
0x180010e0c  test    eax, eax
0x180010e0e  jz      short loc_180010E21
0x180010e10  call    ?_GetType@CAttachmentServices@@AEAAPEBGXZ; CAttachmentServices::_GetType(void)
0x180010e15  mov     rcx, rax
0x180010e18  call    cs:__imp_AssocGetUrlAction
0x180010e1e  mov     [rbx+58h], eax
0x180010e21  mov     edx, [rsp+28h+arg_8]
0x180010e25  mov     rcx, rbx
0x180010e28  call    ?PopOp@CAttachmentServices@@AEAAXW4ATTACHMENT_OP@@@Z; CAttachmentServices::PopOp(ATTACHMENT_OP)
0x180010e2d  add     rsp, 20h
0x180010e31  pop     rbx
0x180010e32  retn
```
